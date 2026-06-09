# SockIoCompletion

- ea: `0x18001ca90`
- end: `0x18001cb91`
- name: `SockIoCompletion`
- size: `257`
- prototype: `void __stdcall(PVOID NormalContext, PVOID SystemArgument1, PVOID SystemArgument2)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800052a0`
- `0x18001ca90`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001cab1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001cab1`

## pseudocode

```c
void __fastcall SockIoCompletion(
        void (__fastcall *NormalContext)(_QWORD, _QWORD, NTSTATUS *, _QWORD),
        NTSTATUS *SystemArgument1,
        PVOID SystemArgument2)
{
  _DWORD *Value; // r14
  unsigned int v6; // ebx
  unsigned int v7; // esi
  unsigned int v8; // eax

  Value = TlsGetValue(MSAFD_SockTlsSlot);
  v6 = 0;
  v7 = SystemArgument1[2];
  if ( (*SystemArgument1 & 0xC0000000) == 0xC0000000 )
  {
    if ( *SystemArgument1 == -1073741536 )
      v8 = 995;
    else
      v8 = NtStatusToSocketError(*SystemArgument1);
  }
  else
  {
    v8 = 0;
    switch ( *SystemArgument1 )
    {
      case -2147483643:
        v8 = 10040;
        break;
      case 1073741839:
        v6 = 0x8000;
        break;
      case 1073741840:
        v6 = 1;
        break;
      case 1073741841:
        v6 = 32769;
        break;
    }
  }
  NormalContext(v8, v7, SystemArgument1, v6);
  --Value[16];
  _InterlockedDecrement(&SockProcessPendingAPCCount);
}

```

## disassembly

```asm
0x18001ca90  mov     [rsp+arg_8], rdx
0x18001ca95  mov     [rsp+arg_0], rcx
0x18001ca9a  push    rbx
0x18001ca9b  push    rsi
0x18001ca9c  push    rdi
0x18001ca9d  push    r14
0x18001ca9f  push    r15
0x18001caa1  sub     rsp, 40h
0x18001caa5  mov     rdi, rdx
0x18001caa8  mov     r15, rcx
0x18001caab  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x18001cab1  call    cs:__imp_TlsGetValue
0x18001cab8  nop     dword ptr [rax+rax+00h]
0x18001cabd  mov     r14, rax
0x18001cac0  mov     [rsp+68h+arg_18], rax
0x18001cac8  xor     ebx, ebx
0x18001caca  mov     esi, [rdi+8]
0x18001cacd  mov     [rsp+68h+var_30], esi
0x18001cad1  mov     edx, [rdi]
0x18001cad3  mov     eax, 0C0000000h
0x18001cad8  and     edx, eax
0x18001cada  cmp     edx, eax
0x18001cadc  jz      short loc_18001CB0B
0x18001cade  xor     eax, eax
0x18001cae0  mov     [rsp+68h+var_38], eax
0x18001cae4  cmp     dword ptr [rdi], 80000005h
0x18001caea  jz      short loc_18001CB35
0x18001caec  cmp     dword ptr [rdi], 4000000Fh
0x18001caf2  jz      short loc_18001CB2A
0x18001caf4  cmp     dword ptr [rdi], 40000010h
0x18001cafa  jz      short loc_18001CB23
0x18001cafc  cmp     dword ptr [rdi], 40000011h
0x18001cb02  jnz     short loc_18001CB3E
0x18001cb04  mov     ebx, 8001h
0x18001cb09  jmp     short loc_18001CB2F
0x18001cb0b  cmp     dword ptr [rdi], 0C0000120h
0x18001cb11  jz      short loc_18001CB1C
0x18001cb13  mov     ecx, [rdi]
0x18001cb15  call    NtStatusToSocketError
0x18001cb1a  jmp     short loc_18001CB3A
0x18001cb1c  mov     eax, 3E3h
0x18001cb21  jmp     short loc_18001CB3A
0x18001cb23  mov     ebx, 1
0x18001cb28  jmp     short loc_18001CB2F
0x18001cb2a  mov     ebx, 8000h
0x18001cb2f  mov     [rsp+68h+var_34], ebx
0x18001cb33  jmp     short loc_18001CB3E
0x18001cb35  mov     eax, 2738h
0x18001cb3a  mov     [rsp+68h+var_38], eax
0x18001cb3e  jmp     short loc_18001CB67
0x18001cb40  mov     eax, 271Eh
0x18001cb45  mov     [rsp+68h+var_38], eax
0x18001cb49  xor     esi, esi
0x18001cb4b  mov     [rsp+68h+var_30], esi
0x18001cb4f  xor     ebx, ebx
0x18001cb51  mov     [rsp+68h+var_34], ebx
0x18001cb55  mov     rdi, [rsp+68h+arg_8]
0x18001cb5a  mov     r15, [rsp+68h+arg_0]
0x18001cb5f  mov     r14, [rsp+68h+arg_18]
0x18001cb67  mov     r9d, ebx
0x18001cb6a  mov     r8, rdi
0x18001cb6d  mov     edx, esi
0x18001cb6f  mov     ecx, eax
0x18001cb71  mov     rax, r15
0x18001cb74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb79  dec     dword ptr [r14+40h]
0x18001cb7d  lock dec cs:SockProcessPendingAPCCount
0x18001cb84  add     rsp, 40h
0x18001cb88  pop     r15
0x18001cb8a  pop     r14
0x18001cb8c  pop     rdi
0x18001cb8d  pop     rsi
0x18001cb8e  pop     rbx
0x18001cb8f  retn
```
