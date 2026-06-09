# _InitializeConfigurationOnce_::_1_::catch$5

- ea: `0x180015802`
- end: `0x180015868`
- name: `_InitializeConfigurationOnce_::_1_::catch$5`
- size: `102`
- prototype: `__int64 __fastcall(wil *, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800062c4`
- `0x1800077a0`
- `0x180015802`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015850`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015850`

## pseudocode

```c
__int64 __fastcall InitializeConfigurationOnce_::_1_::catch_5(wil *a1, __int64 a2, unsigned int a3)
{
  __int64 v4; // rcx
  __int64 v5; // r8

  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 0x20) != 0 )
  {
    *(_DWORD *)(a2 + 48) = wil::ResultFromCaughtException(a1, (void *)a2, a3);
    *(_QWORD *)(a2 + 72) = a2 + 48;
    *(_QWORD *)(a2 + 80) = 4;
    McGenEventWrite_EventWriteTransfer(v4, "\v", v5, 2, a2 + 56);
  }
  SetLastError(0x24Du);
  return 0;
}

```

## disassembly

```asm
0x180015802  mov     [rsp+arg_8], rdx
0x180015807  push    rbp
0x180015808  sub     rsp, 30h
0x18001580c  mov     rbp, rdx
0x18001580f  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 20h
0x180015816  jz      short loc_18001584B
0x180015818  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18001581d  mov     [rbp+30h], eax
0x180015820  lea     rax, [rbp+30h]
0x180015824  mov     [rbp+48h], rax
0x180015828  mov     qword ptr [rbp+50h], 4
0x180015830  lea     rax, [rbp+38h]
0x180015834  mov     [rsp+38h+var_18], rax
0x180015839  mov     r9d, 2
0x18001583f  lea     rdx, ConfigurationLoadFailed; "\v"
0x180015846  call    McGenEventWrite_EventWriteTransfer
0x18001584b  mov     ecx, 24Dh; dwErrCode
0x180015850  call    cs:__imp_SetLastError
0x180015856  nop
0x180015857  mov     rax, 0
0x180015861  add     rsp, 30h
0x180015865  pop     rbp
0x180015866  retn
```
