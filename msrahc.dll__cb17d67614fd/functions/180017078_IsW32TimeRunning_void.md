# IsW32TimeRunning(void)

- ea: `0x180017078`
- end: `0x1800171d3`
- name: `?IsW32TimeRunning@@YAJXZ`
- size: `347`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016eac`
- `0x1800174e4`

## callees

- `0x180014660`
- `0x180017078`
- `0x18001a5e0`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x1800171a3`
- `ADVAPI32!CloseServiceHandle` at `0x1800171ac`
- `ADVAPI32!CloseServiceHandle` at `0x1800171a3`
- `ADVAPI32!CloseServiceHandle` at `0x1800171ac`
- `ADVAPI32!QueryServiceStatusEx` at `0x180017155`
- `ADVAPI32!QueryServiceStatusEx` at `0x180017155`
- `ADVAPI32!OpenServiceW` at `0x180017104`
- `ADVAPI32!OpenServiceW` at `0x180017104`
- `ADVAPI32!OpenSCManagerW` at `0x1800170ba`
- `ADVAPI32!OpenSCManagerW` at `0x1800170ba`

## string_xrefs

- `0x1800170cc`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x180017116`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x18001718f`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x180017098`: `ServicesActive`

## pseudocode

```c
__int64 IsW32TimeRunning(void)
{
  SC_HANDLE v0; // rax
  const struct _EVENT_DESCRIPTOR *v1; // rdx
  CEventLogger *v2; // rcx
  SC_HANDLE v3; // rdi
  unsigned int v4; // ebx
  const struct _EVENT_DESCRIPTOR *v5; // rdx
  CEventLogger *v6; // rcx
  SC_HANDLE v7; // rsi
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx
  unsigned int v10; // r9d
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v14; // [rsp+48h] [rbp-30h]
  int v15; // [rsp+58h] [rbp-20h]

  v15 = 0;
  pcbBytesNeeded = 0;
  *(_OWORD *)Buffer = 0;
  v14 = 0;
  v0 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v3 = v0;
  if ( v0 )
  {
    v7 = OpenServiceW(v0, L"w32time", 4u);
    if ( !v7 )
    {
      CEventLogger::LogError(
        v6,
        v5,
        L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
        0x223u,
        L"IsW32TimeRunning",
        0);
      v4 = -2147467259;
LABEL_11:
      CloseServiceHandle(v3);
      return v4;
    }
    if ( QueryServiceStatusEx(v7, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
    {
      v4 = 0;
      if ( *(_DWORD *)&Buffer[4] == 4 )
      {
LABEL_10:
        CloseServiceHandle(v7);
        goto LABEL_11;
      }
      v4 = -2147023834;
      v10 = 564;
    }
    else
    {
      v4 = -2147467259;
      v10 = 556;
    }
    CEventLogger::LogError(v9, v8, L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp", v10, L"IsW32TimeRunning", 0);
    goto LABEL_10;
  }
  CEventLogger::LogError(v2, v1, L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp", 0x21Eu, L"IsW32TimeRunning", 0);
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x180017078  mov     [rsp+arg_0], rbx
0x18001707d  mov     [rsp+arg_8], rsi
0x180017082  push    rdi
0x180017083  sub     rsp, 70h
0x180017087  mov     rax, cs:__security_cookie
0x18001708e  xor     rax, rsp
0x180017091  mov     [rsp+78h+var_18], rax
0x180017096  xor     eax, eax
0x180017098  lea     rdx, DatabaseName; "ServicesActive"
0x18001709f  xorps   xmm0, xmm0
0x1800170a2  mov     [rsp+78h+var_20], eax
0x1800170a6  xor     ecx, ecx; lpMachineName
0x1800170a8  mov     [rsp+78h+var_48], eax
0x1800170ac  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x1800170b1  lea     r8d, [rax+1]; dwDesiredAccess
0x1800170b5  movups  [rsp+78h+var_30], xmm0
0x1800170ba  call    cs:__imp_OpenSCManagerW
0x1800170c0  mov     rdi, rax
0x1800170c3  test    rax, rax
0x1800170c6  jnz     short loc_1800170F4
0x1800170c8  mov     [rsp+78h+var_50], eax; unsigned int
0x1800170cc  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x1800170d3  lea     rax, aIsw32timerunni; "IsW32TimeRunning"
0x1800170da  mov     r9d, 21Eh; unsigned int
0x1800170e0  mov     [rsp+78h+pcbBytesNeeded], rax; unsigned __int16 *
0x1800170e5  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800170ea  mov     ebx, 80004005h
0x1800170ef  jmp     loc_1800171B2
0x1800170f4  mov     r8d, 4; dwDesiredAccess
0x1800170fa  lea     rdx, ServiceName; "w32time"
0x180017101  mov     rcx, rdi; hSCManager
0x180017104  call    cs:__imp_OpenServiceW
0x18001710a  mov     rsi, rax
0x18001710d  test    rax, rax
0x180017110  jnz     short loc_18001713B
0x180017112  mov     [rsp+78h+var_50], eax; unsigned int
0x180017116  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x18001711d  lea     rax, aIsw32timerunni; "IsW32TimeRunning"
0x180017124  mov     r9d, 223h; unsigned int
0x18001712a  mov     [rsp+78h+pcbBytesNeeded], rax; unsigned __int16 *
0x18001712f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180017134  mov     ebx, 80004005h
0x180017139  jmp     short loc_1800171A9
0x18001713b  lea     rax, [rsp+78h+var_48]
0x180017140  mov     r9d, 24h ; '$'; cbBufSize
0x180017146  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x18001714b  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180017150  xor     edx, edx; InfoLevel
0x180017152  mov     rcx, rsi; hService
0x180017155  call    cs:__imp_QueryServiceStatusEx
0x18001715b  test    eax, eax
0x18001715d  jnz     short loc_18001716C
0x18001715f  mov     ebx, 80004005h
0x180017164  mov     r9d, 22Ch
0x18001716a  jmp     short loc_180017180
0x18001716c  xor     ebx, ebx
0x18001716e  cmp     dword ptr [rsp+78h+Buffer+4], 4
0x180017173  jz      short loc_1800171A0
0x180017175  mov     ebx, 80070426h
0x18001717a  mov     r9d, 234h; unsigned int
0x180017180  lea     rax, aIsw32timerunni; "IsW32TimeRunning"
0x180017187  mov     [rsp+78h+var_50], 0; unsigned int
0x18001718f  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180017196  mov     [rsp+78h+pcbBytesNeeded], rax; unsigned __int16 *
0x18001719b  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800171a0  mov     rcx, rsi; hSCObject
0x1800171a3  call    cs:__imp_CloseServiceHandle
0x1800171a9  mov     rcx, rdi; hSCObject
0x1800171ac  call    cs:__imp_CloseServiceHandle
0x1800171b2  mov     eax, ebx
0x1800171b4  mov     rcx, [rsp+78h+var_18]
0x1800171b9  xor     rcx, rsp; StackCookie
0x1800171bc  call    __security_check_cookie
0x1800171c1  lea     r11, [rsp+78h+var_8]
0x1800171c6  mov     rbx, [r11+10h]
0x1800171ca  mov     rsi, [r11+18h]
0x1800171ce  mov     rsp, r11
0x1800171d1  pop     rdi
0x1800171d2  retn
```
