# SetCommSettings

- ea: `0x180014df0`
- end: `0x180014f23`
- name: `SetCommSettings`
- size: `307`
- prototype: `__int64 __fastcall(__int64, _BYTE *, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000d92c`
- `0x180012340`
- `0x180014df0`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014eb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014eb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ef0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014ee6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014ee6`
- `api-ms-win-core-comm-l1-1-0!GetCommState` at `0x180014e4d`
- `api-ms-win-core-comm-l1-1-0!GetCommState` at `0x180014e4d`
- `api-ms-win-core-comm-l1-1-0!SetCommState` at `0x180014ea7`
- `api-ms-win-core-comm-l1-1-0!SetCommState` at `0x180014ea7`

## string_xrefs

- `0x180014e26`: `SetCommSettings: NULL hIOPort!`
- `0x180014e63`: `SetCommSettings: GetCommState failed for %s`
- `0x180014e76`: `SetCommSettings: setting parity=%d, stop=%d, data=%d`
- `0x180014ec5`: `SetCommSettings: SetCommState failed for %s.handle=0x%x. %d`
- `0x180014ef8`: `SetCommSettings: done. rc=0x%x`

## pseudocode

```c
__int64 __fastcall SetCommSettings(__int64 a1, _BYTE *a2, __int64 a3, __int64 a4)
{
  DWORD LastError; // edi
  BYTE v8; // r8
  BYTE v9; // dl
  struct _DCB DCB; // [rsp+20h] [rbp-38h] BYREF

  memset(&DCB, 0, sizeof(DCB));
  if ( !a1 )
  {
    RasTapiTrace("SetCommSettings: NULL hIOPort!");
    return 2147942487LL;
  }
  GetMutex(a1, a2, a3, a4);
  if ( !GetCommState(*(HANDLE *)(a1 + 888), &DCB) )
  {
    LastError = GetLastError();
    RasTapiTrace("SetCommSettings: GetCommState failed for %s");
LABEL_7:
    RasTapiTrace(" ");
    goto LABEL_8;
  }
  v8 = a2[5];
  LastError = 0;
  v9 = a2[4];
  DCB.ByteSize = a2[6];
  DCB.StopBits = v8;
  DCB.Parity = v9;
  RasTapiTrace("SetCommSettings: setting parity=%d, stop=%d, data=%d");
  if ( !SetCommState(*(HANDLE *)(a1 + 888), &DCB) )
  {
    LastError = GetLastError();
    RasTapiTrace("SetCommSettings: SetCommState failed for %s.handle=0x%x. %d");
    goto LABEL_7;
  }
LABEL_8:
  if ( !ReleaseMutex(RasTapiMutex) )
    GetLastError();
  RasTapiTrace("SetCommSettings: done. rc=0x%x");
  return LastError;
}

```

## disassembly

```asm
0x180014df0  mov     [rsp+arg_10], rbx
0x180014df5  mov     [rsp+arg_18], rsi
0x180014dfa  push    rdi
0x180014dfb  sub     rsp, 50h
0x180014dff  mov     rax, cs:__security_cookie
0x180014e06  xor     rax, rsp
0x180014e09  mov     [rsp+58h+var_18], rax
0x180014e0e  xorps   xmm0, xmm0
0x180014e11  mov     rsi, rdx
0x180014e14  mov     rbx, rcx
0x180014e17  movups  xmmword ptr [rsp+58h+DCB.DCBlength], xmm0
0x180014e1c  movups  xmmword ptr [rsp+58h+DCB.wReserved], xmm0
0x180014e21  test    rcx, rcx
0x180014e24  jnz     short loc_180014E3C
0x180014e26  lea     rcx, aSetcommsetting_1; "SetCommSettings: NULL hIOPort!"
0x180014e2d  call    RasTapiTrace
0x180014e32  mov     eax, 80070057h
0x180014e37  jmp     loc_180014F06
0x180014e3c  call    GetMutex
0x180014e41  mov     rcx, [rbx+378h]; hFile
0x180014e48  lea     rdx, [rsp+58h+DCB]; lpDCB
0x180014e4d  call    cs:__imp_GetCommState
0x180014e53  test    eax, eax
0x180014e55  jnz     short loc_180014E71
0x180014e57  call    cs:__imp_GetLastError
0x180014e5d  lea     rdx, [rbx+18h]
0x180014e61  mov     edi, eax
0x180014e63  lea     rcx, aSetcommsetting_4; "SetCommSettings: GetCommState failed fo"...
0x180014e6a  call    RasTapiTrace
0x180014e6f  jmp     short loc_180014ED3
0x180014e71  movzx   r9d, byte ptr [rsi+6]
0x180014e76  lea     rcx, aSetcommsetting_3; "SetCommSettings: setting parity=%d, sto"...
0x180014e7d  movzx   r8d, byte ptr [rsi+5]
0x180014e82  xor     edi, edi
0x180014e84  movzx   edx, byte ptr [rsi+4]
0x180014e88  mov     [rsp+58h+DCB.ByteSize], r9b
0x180014e8d  mov     [rsp+58h+DCB.StopBits], r8b
0x180014e92  mov     [rsp+58h+DCB.Parity], dl
0x180014e96  call    RasTapiTrace
0x180014e9b  mov     rcx, [rbx+378h]; hFile
0x180014ea2  lea     rdx, [rsp+58h+DCB]; lpDCB
0x180014ea7  call    cs:__imp_SetCommState
0x180014ead  test    eax, eax
0x180014eaf  jnz     short loc_180014EDF
0x180014eb1  call    cs:__imp_GetLastError
0x180014eb7  mov     r8, [rbx+378h]
0x180014ebe  lea     rdx, [rbx+18h]
0x180014ec2  mov     r9d, eax
0x180014ec5  lea     rcx, aSetcommsetting_0; "SetCommSettings: SetCommState failed fo"...
0x180014ecc  mov     edi, eax
0x180014ece  call    RasTapiTrace
0x180014ed3  lea     rcx, asc_18002C0B8; " "
0x180014eda  call    RasTapiTrace
0x180014edf  mov     rcx, cs:RasTapiMutex; hMutex
0x180014ee6  call    cs:__imp_ReleaseMutex
0x180014eec  test    eax, eax
0x180014eee  jnz     short loc_180014EF6
0x180014ef0  call    cs:__imp_GetLastError
0x180014ef6  mov     edx, edi
0x180014ef8  lea     rcx, aSetcommsetting_2; "SetCommSettings: done. rc=0x%x"
0x180014eff  call    RasTapiTrace
0x180014f04  mov     eax, edi
0x180014f06  mov     rcx, [rsp+58h+var_18]
0x180014f0b  xor     rcx, rsp; StackCookie
0x180014f0e  call    __security_check_cookie
0x180014f13  mov     rbx, [rsp+58h+arg_10]
0x180014f18  mov     rsi, [rsp+58h+arg_18]
0x180014f1d  add     rsp, 50h
0x180014f21  pop     rdi
0x180014f22  retn
```
