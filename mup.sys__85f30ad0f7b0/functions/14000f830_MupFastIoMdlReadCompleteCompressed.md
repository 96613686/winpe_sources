# MupFastIoMdlReadCompleteCompressed

- ea: `0x14000f830`
- end: `0x14000f88c`
- name: `MupFastIoMdlReadCompleteCompressed`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400054e0`
- `0x14000f830`
- `0x14001e710`

## pseudocode

```c
char __fastcall MupFastIoMdlReadCompleteCompressed(__int64 a1, __int64 a2)
{
  __int64 ProviderFastIoDispatchTable; // rax
  __int64 (__fastcall *v5)(__int64, __int64, __int64); // rax
  __int64 v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  ProviderFastIoDispatchTable = MupiGetProviderFastIoDispatchTable(a1, &v7);
  if ( ProviderFastIoDispatchTable
    && *(_DWORD *)ProviderFastIoDispatchTable >= 0xB8u
    && (v5 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(ProviderFastIoDispatchTable + 176)) != 0 )
  {
    return v5(a1, a2, v7);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x14000f830  mov     [rsp+arg_0], rbx
0x14000f835  push    rdi
0x14000f836  sub     rsp, 20h
0x14000f83a  mov     rdi, rdx
0x14000f83d  mov     [rsp+28h+arg_18], 0
0x14000f846  lea     rdx, [rsp+28h+arg_18]
0x14000f84b  mov     rbx, rcx
0x14000f84e  call    MupiGetProviderFastIoDispatchTable
0x14000f853  test    rax, rax
0x14000f856  jz      short loc_14000F87E
0x14000f858  cmp     dword ptr [rax], 0B8h
0x14000f85e  jb      short loc_14000F87E
0x14000f860  mov     rax, [rax+0B0h]
0x14000f867  test    rax, rax
0x14000f86a  jz      short loc_14000F87E
0x14000f86c  mov     r8, [rsp+28h+arg_18]
0x14000f871  mov     rdx, rdi
0x14000f874  mov     rcx, rbx
0x14000f877  call    _guard_dispatch_icall
0x14000f87c  jmp     short loc_14000F880
0x14000f87e  xor     al, al
0x14000f880  mov     rbx, [rsp+28h+arg_0]
0x14000f885  add     rsp, 20h
0x14000f889  pop     rdi
0x14000f88a  retn
```
