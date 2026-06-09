# MupFastIoMdlWriteCompleteCompressed

- ea: `0x14000f930`
- end: `0x14000f99b`
- name: `MupFastIoMdlWriteCompleteCompressed`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400054e0`
- `0x14000f930`
- `0x14001e6c0`

## pseudocode

```c
char __fastcall MupFastIoMdlWriteCompleteCompressed(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 ProviderFastIoDispatchTable; // rax
  __int64 (__fastcall *v7)(__int64, __int64, __int64, _QWORD); // rax
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF

  v9[0] = 0;
  ProviderFastIoDispatchTable = MupiGetProviderFastIoDispatchTable(a1, v9);
  if ( ProviderFastIoDispatchTable
    && *(_DWORD *)ProviderFastIoDispatchTable >= 0xC0u
    && (v7 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(ProviderFastIoDispatchTable + 184)) != 0 )
  {
    return v7(a1, a2, a3, v9[0]);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x14000f930  mov     rax, rsp
0x14000f933  mov     [rax+8], rbx
0x14000f937  mov     [rax+10h], rsi
0x14000f93b  push    rdi
0x14000f93c  sub     rsp, 40h
0x14000f940  mov     rsi, rdx
0x14000f943  mov     qword ptr [rax-18h], 0
0x14000f94b  lea     rdx, [rax-18h]
0x14000f94f  mov     rdi, r8
0x14000f952  mov     rbx, rcx
0x14000f955  call    MupiGetProviderFastIoDispatchTable
0x14000f95a  test    rax, rax
0x14000f95d  jz      short loc_14000F988
0x14000f95f  cmp     dword ptr [rax], 0C0h
0x14000f965  jb      short loc_14000F988
0x14000f967  mov     rax, [rax+0B8h]
0x14000f96e  test    rax, rax
0x14000f971  jz      short loc_14000F988
0x14000f973  mov     r9, [rsp+48h+var_18]
0x14000f978  mov     r8, rdi
0x14000f97b  mov     rdx, rsi
0x14000f97e  mov     rcx, rbx
0x14000f981  call    _guard_dispatch_icall
0x14000f986  jmp     short loc_14000F98A
0x14000f988  xor     al, al
0x14000f98a  mov     rbx, [rsp+48h+arg_0]
0x14000f98f  mov     rsi, [rsp+48h+arg_8]
0x14000f994  add     rsp, 40h
0x14000f998  pop     rdi
0x14000f999  retn
```
