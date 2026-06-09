# NpTimerDispatch

- ea: `0x140001810`
- end: `0x1400018ee`
- name: `NpTimerDispatch`
- size: `222`
- prototype: `void __fastcall(struct _KDPC *Dpc, __int64 *DeferredContext, PVOID SystemArgument1, PVOID SystemArgument2)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001810`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400018bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400018bb`
- `ntoskrnl!IofCompleteRequest` at `0x140001897`
- `ntoskrnl!IofCompleteRequest` at `0x140001897`
- `ntoskrnl!ObfDereferenceObject` at `0x1400018aa`
- `ntoskrnl!ObfDereferenceObject` at `0x1400018aa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000182d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000182d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000187a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000187a`

## pseudocode

```c
void __fastcall NpTimerDispatch(
        struct _KDPC *Dpc,
        __int64 *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  __int64 v4; // rsi
  KIRQL v6; // al
  __int64 v7; // rbx
  __int64 v8; // rdx
  _QWORD *v9; // r8

  v4 = DeferredContext[17];
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 16));
  v7 = *DeferredContext;
  if ( *DeferredContext )
  {
    v8 = *(_QWORD *)(v7 + 168);
    if ( *(_QWORD *)(v8 + 8) != v7 + 168 || (v9 = *(_QWORD **)(v7 + 176), *v9 != v7 + 168) )
      __fastfail(3u);
    *v9 = v8;
    *(_QWORD *)(v8 + 8) = v9;
    if ( !_InterlockedExchange64((volatile __int64 *)(v7 + 104), 0) )
    {
      *(_QWORD *)(v7 + 128) = 0;
      v7 = 0;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 16), v6);
  if ( v7 )
  {
    *(_DWORD *)(v7 + 48) = -1073741643;
    IofCompleteRequest((PIRP)v7, 2);
  }
  ObfDereferenceObject((PVOID)DeferredContext[18]);
  ExFreePoolWithTag(DeferredContext, 0);
}

```

## disassembly

```asm
0x140001810  mov     [rsp+arg_0], rbx
0x140001815  mov     [rsp+arg_8], rsi
0x14000181a  push    rdi
0x14000181b  sub     rsp, 20h
0x14000181f  mov     rsi, [rdx+88h]
0x140001826  mov     rdi, rdx
0x140001829  lea     rcx, [rsi+10h]; SpinLock
0x14000182d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001834  nop     dword ptr [rax+rax+00h]
0x140001839  mov     rbx, [rdi]
0x14000183c  mov     r9b, al
0x14000183f  test    rbx, rbx
0x140001842  jz      short loc_140001873
0x140001844  lea     rcx, [rbx+0A8h]
0x14000184b  mov     rdx, [rcx]
0x14000184e  cmp     [rdx+8], rcx
0x140001852  jnz     loc_1400018D8
0x140001858  mov     r8, [rcx+8]
0x14000185c  cmp     [r8], rcx
0x14000185f  jnz     short loc_1400018D8
0x140001861  mov     [r8], rdx
0x140001864  xor     eax, eax
0x140001866  mov     [rdx+8], r8
0x14000186a  xchg    rax, [rbx+68h]
0x14000186e  test    rax, rax
0x140001871  jz      short loc_1400018DF
0x140001873  mov     dl, r9b; NewIrql
0x140001876  lea     rcx, [rsi+10h]; SpinLock
0x14000187a  call    cs:__imp_KeReleaseSpinLock
0x140001881  nop     dword ptr [rax+rax+00h]
0x140001886  test    rbx, rbx
0x140001889  jz      short loc_1400018A3
0x14000188b  mov     dl, 2; PriorityBoost
0x14000188d  mov     dword ptr [rbx+30h], 0C00000B5h
0x140001894  mov     rcx, rbx; Irp
0x140001897  call    cs:__imp_IofCompleteRequest
0x14000189e  nop     dword ptr [rax+rax+00h]
0x1400018a3  mov     rcx, [rdi+90h]; Object
0x1400018aa  call    cs:__imp_ObfDereferenceObject
0x1400018b1  nop     dword ptr [rax+rax+00h]
0x1400018b6  xor     edx, edx; Tag
0x1400018b8  mov     rcx, rdi; P
0x1400018bb  call    cs:__imp_ExFreePoolWithTag
0x1400018c2  nop     dword ptr [rax+rax+00h]
0x1400018c7  mov     rbx, [rsp+28h+arg_0]
0x1400018cc  mov     rsi, [rsp+28h+arg_8]
0x1400018d1  add     rsp, 20h
0x1400018d5  pop     rdi
0x1400018d6  retn
0x1400018d8  mov     ecx, 3
0x1400018dd  int     29h; Win8: RtlFailFast(ecx)
0x1400018df  mov     qword ptr [rbx+80h], 0
0x1400018ea  xor     ebx, ebx
0x1400018ec  jmp     short loc_140001873
```
