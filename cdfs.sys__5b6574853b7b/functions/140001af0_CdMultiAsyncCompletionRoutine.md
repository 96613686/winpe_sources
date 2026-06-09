# CdMultiAsyncCompletionRoutine

- ea: `0x140001af0`
- end: `0x140001ba9`
- name: `CdMultiAsyncCompletionRoutine`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001af0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001b69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001b69`
- `ntoskrnl!IoFreeMdl` at `0x140001b7d`
- `ntoskrnl!IoFreeMdl` at `0x140001b7d`
- `ntoskrnl!IoFreeIrp` at `0x140001b8c`
- `ntoskrnl!IoFreeIrp` at `0x140001b8c`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140001b58`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140001b58`

## pseudocode

```c
__int64 __fastcall CdMultiAsyncCompletionRoutine(__int64 a1, IRP *a2, __int64 a3)
{
  __int32 Status; // eax
  __int64 v6; // rcx

  Status = a2->IoStatus.Status;
  if ( Status < 0 )
    _InterlockedExchange((volatile __int32 *)(a3 + 16), Status);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a3, 0xFFFFFFFF) == 1 )
  {
    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 184LL) + 3LL) |= 1u;
    *(_DWORD *)(*(_QWORD *)(a3 + 8) + 48LL) = *(_DWORD *)(a3 + 16);
    *(_QWORD *)(*(_QWORD *)(a3 + 8) + 56LL) = 0;
    v6 = *(_QWORD *)(a3 + 8);
    if ( *(int *)(v6 + 48) >= 0 )
      *(_QWORD *)(v6 + 56) = *(unsigned int *)(a3 + 40);
    ExReleaseResourceForThreadLite(*(PERESOURCE *)(a3 + 24), *(_QWORD *)(a3 + 32));
    ExFreePoolWithTag((PVOID)a3, 0);
    return 0;
  }
  else
  {
    IoFreeMdl(a2->MdlAddress);
    IoFreeIrp(a2);
    return 3221225494LL;
  }
}

```

## disassembly

```asm
0x140001af0  mov     [rsp+arg_0], rbx
0x140001af5  push    rdi
0x140001af6  sub     rsp, 20h
0x140001afa  mov     eax, [rdx+30h]
0x140001afd  mov     rbx, r8
0x140001b00  mov     rdi, rdx
0x140001b03  test    eax, eax
0x140001b05  jns     short loc_140001B0B
0x140001b07  xchg    eax, [r8+10h]
0x140001b0b  or      eax, 0FFFFFFFFh
0x140001b0e  lock xadd [r8], eax
0x140001b13  cmp     eax, 1
0x140001b16  jnz     short loc_140001B79
0x140001b18  mov     rax, [r8+8]
0x140001b1c  mov     rcx, [rax+0B8h]
0x140001b23  or      byte ptr [rcx+3], 1
0x140001b27  mov     rcx, [r8+8]
0x140001b2b  mov     eax, [r8+10h]
0x140001b2f  mov     [rcx+30h], eax
0x140001b32  mov     rax, [r8+8]
0x140001b36  mov     qword ptr [rax+38h], 0
0x140001b3e  mov     rcx, [r8+8]
0x140001b42  cmp     dword ptr [rcx+30h], 0
0x140001b46  jl      short loc_140001B50
0x140001b48  mov     eax, [r8+28h]
0x140001b4c  mov     [rcx+38h], rax
0x140001b50  mov     rdx, [r8+20h]; ResourceThreadId
0x140001b54  mov     rcx, [r8+18h]; Resource
0x140001b58  call    cs:__imp_ExReleaseResourceForThreadLite
0x140001b5f  nop     dword ptr [rax+rax+00h]
0x140001b64  xor     edx, edx; Tag
0x140001b66  mov     rcx, rbx; P
0x140001b69  call    cs:__imp_ExFreePoolWithTag
0x140001b70  nop     dword ptr [rax+rax+00h]
0x140001b75  xor     eax, eax
0x140001b77  jmp     short loc_140001B9D
0x140001b79  mov     rcx, [rdx+8]; Mdl
0x140001b7d  call    cs:__imp_IoFreeMdl
0x140001b84  nop     dword ptr [rax+rax+00h]
0x140001b89  mov     rcx, rdi; Irp
0x140001b8c  call    cs:__imp_IoFreeIrp
0x140001b93  nop     dword ptr [rax+rax+00h]
0x140001b98  mov     eax, 0C0000016h
0x140001b9d  mov     rbx, [rsp+28h+arg_0]
0x140001ba2  add     rsp, 20h
0x140001ba6  pop     rdi
0x140001ba7  retn
```
