# MupFastIoReadCompressed

- ea: `0x14000fa80`
- end: `0x14000fb3e`
- name: `MupFastIoReadCompressed`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400054e0`
- `0x14000fa80`
- `0x14001e710`

## pseudocode

```c
char __fastcall MupFastIoReadCompressed(
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
    if ( *(_DWORD *)ProviderFastIoDispatchTable >= 0xA8u )
    {
      v14 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64, __int64, _DWORD *, __int64, int, _QWORD))(ProviderFastIoDispatchTable + 160);
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
0x14000fa80  push    rbx
0x14000fa82  push    rbp
0x14000fa83  push    rsi
0x14000fa84  push    rdi
0x14000fa85  sub     rsp, 78h
0x14000fa89  mov     rbp, rdx
0x14000fa8c  mov     [rsp+98h+var_38], 0
0x14000fa95  lea     rdx, [rsp+98h+var_38]
0x14000fa9a  mov     edi, r9d
0x14000fa9d  mov     esi, r8d
0x14000faa0  mov     rbx, rcx
0x14000faa3  call    MupiGetProviderFastIoDispatchTable
0x14000faa8  test    rax, rax
0x14000faab  jz      short loc_14000FB22
0x14000faad  cmp     dword ptr [rax], 0A8h
0x14000fab3  jb      short loc_14000FB22
0x14000fab5  mov     r10, [rax+0A0h]
0x14000fabc  test    r10, r10
0x14000fabf  jz      short loc_14000FB22
0x14000fac1  mov     rax, [rsp+98h+var_38]
0x14000fac6  mov     r9d, edi
0x14000fac9  mov     ecx, [rsp+98h+arg_40]
0x14000fad0  mov     r8d, esi
0x14000fad3  mov     [rsp+98h+var_50], rax
0x14000fad8  mov     rdx, rbp
0x14000fadb  mov     [rsp+98h+var_58], ecx
0x14000fadf  mov     rax, r10
0x14000fae2  mov     rcx, [rsp+98h+arg_38]
0x14000faea  mov     [rsp+98h+var_60], rcx
0x14000faef  mov     rcx, [rsp+98h+arg_30]
0x14000faf7  mov     [rsp+98h+var_68], rcx
0x14000fafc  mov     rcx, [rsp+98h+arg_28]
0x14000fb04  mov     [rsp+98h+var_70], rcx
0x14000fb09  mov     rcx, [rsp+98h+arg_20]
0x14000fb11  mov     [rsp+98h+var_78], rcx
0x14000fb16  mov     rcx, rbx
0x14000fb19  call    _guard_dispatch_icall
0x14000fb1e  mov     cl, al
0x14000fb20  jmp     short loc_14000FB32
0x14000fb22  mov     rax, [rsp+98h+arg_30]
0x14000fb2a  xor     cl, cl
0x14000fb2c  mov     dword ptr [rax], 0C00000BBh
0x14000fb32  mov     al, cl
0x14000fb34  add     rsp, 78h
0x14000fb38  pop     rdi
0x14000fb39  pop     rsi
0x14000fb3a  pop     rbp
0x14000fb3b  pop     rbx
0x14000fb3c  retn
```
