# MupFastIoWriteCompressed

- ea: `0x14000fc30`
- end: `0x14000fcee`
- name: `MupFastIoWriteCompressed`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400054e0`
- `0x14000fc30`
- `0x14001e6c0`

## pseudocode

```c
char __fastcall MupFastIoWriteCompressed(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        _DWORD *a7,
        __int64 a8,
        int a9)
{
  __int64 ProviderFastIoDispatchTable; // rax
  __int64 (__fastcall *v14)(__int64, __int64, _QWORD, _QWORD, __int64, __int64, _DWORD *, __int64, int, _QWORD); // r10
  char v15; // cl
  _QWORD v17[7]; // [rsp+60h] [rbp-38h] BYREF

  v17[0] = 0;
  ProviderFastIoDispatchTable = MupiGetProviderFastIoDispatchTable(a1, v17);
  if ( ProviderFastIoDispatchTable )
  {
    if ( *(_DWORD *)ProviderFastIoDispatchTable >= 0xB0u )
    {
      v14 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64, __int64, _DWORD *, __int64, int, _QWORD))(ProviderFastIoDispatchTable + 168);
      if ( v14 )
        return v14(a1, a2, a3, a4, a5, a6, a7, a8, a9, v17[0]);
    }
  }
  v15 = 0;
  *a7 = -1073741637;
  return v15;
}

```

## disassembly

```asm
0x14000fc30  push    rbx
0x14000fc32  push    rbp
0x14000fc33  push    rsi
0x14000fc34  push    rdi
0x14000fc35  sub     rsp, 78h
0x14000fc39  mov     rbp, rdx
0x14000fc3c  mov     [rsp+98h+var_38], 0
0x14000fc45  lea     rdx, [rsp+98h+var_38]
0x14000fc4a  mov     edi, r9d
0x14000fc4d  mov     esi, r8d
0x14000fc50  mov     rbx, rcx
0x14000fc53  call    MupiGetProviderFastIoDispatchTable
0x14000fc58  test    rax, rax
0x14000fc5b  jz      short loc_14000FCD2
0x14000fc5d  cmp     dword ptr [rax], 0B0h
0x14000fc63  jb      short loc_14000FCD2
0x14000fc65  mov     r10, [rax+0A8h]
0x14000fc6c  test    r10, r10
0x14000fc6f  jz      short loc_14000FCD2
0x14000fc71  mov     rax, [rsp+98h+var_38]
0x14000fc76  mov     r9d, edi
0x14000fc79  mov     ecx, [rsp+98h+arg_40]
0x14000fc80  mov     r8d, esi
0x14000fc83  mov     [rsp+98h+var_50], rax
0x14000fc88  mov     rdx, rbp
0x14000fc8b  mov     [rsp+98h+var_58], ecx
0x14000fc8f  mov     rax, r10
0x14000fc92  mov     rcx, [rsp+98h+arg_38]
0x14000fc9a  mov     [rsp+98h+var_60], rcx
0x14000fc9f  mov     rcx, [rsp+98h+arg_30]
0x14000fca7  mov     [rsp+98h+var_68], rcx
0x14000fcac  mov     rcx, [rsp+98h+arg_28]
0x14000fcb4  mov     [rsp+98h+var_70], rcx
0x14000fcb9  mov     rcx, [rsp+98h+arg_20]
0x14000fcc1  mov     [rsp+98h+var_78], rcx
0x14000fcc6  mov     rcx, rbx
0x14000fcc9  call    _guard_dispatch_icall
0x14000fcce  mov     cl, al
0x14000fcd0  jmp     short loc_14000FCE2
0x14000fcd2  mov     rax, [rsp+98h+arg_30]
0x14000fcda  xor     cl, cl
0x14000fcdc  mov     dword ptr [rax], 0C00000BBh
0x14000fce2  mov     al, cl
0x14000fce4  add     rsp, 78h
0x14000fce8  pop     rdi
0x14000fce9  pop     rsi
0x14000fcea  pop     rbp
0x14000fceb  pop     rbx
0x14000fcec  retn
```
