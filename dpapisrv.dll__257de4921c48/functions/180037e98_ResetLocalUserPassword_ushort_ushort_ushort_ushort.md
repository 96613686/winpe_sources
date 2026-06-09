# ResetLocalUserPassword(ushort *,ushort *,ushort *,ushort *)

- ea: `0x180037e98`
- end: `0x18003808c`
- name: `?ResetLocalUserPassword@@YAKPEAG000@Z`
- size: `500`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR, PCWSTR, PCWSTR)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180038d40`

## callees

- `0x180003080`
- `0x180007f10`
- `0x18001c9c0`
- `0x180037a5c`
- `0x180037e98`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037feb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037feb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003806d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003806d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038059`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038059`
- `ntdll!RtlNtStatusToDosError` at `0x180037fbb`
- `ntdll!RtlNtStatusToDosError` at `0x180037fbb`
- `ntdll!RtlInitUnicodeString` at `0x180037f10`
- `ntdll!RtlInitUnicodeString` at `0x180037f23`
- `ntdll!RtlInitUnicodeString` at `0x180037f36`
- `ntdll!RtlInitUnicodeString` at `0x180037f49`
- `ntdll!RtlInitUnicodeString` at `0x180037f10`
- `ntdll!RtlInitUnicodeString` at `0x180037f23`
- `ntdll!RtlInitUnicodeString` at `0x180037f36`
- `ntdll!RtlInitUnicodeString` at `0x180037f49`
- `SAMSRV!SamIChangePasswordForeignUser` at `0x180037fa7`
- `SAMSRV!SamIChangePasswordForeignUser` at `0x180037fa7`

## string_xrefs

- `0x180037f7b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x180037ffd`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c
__int64 __fastcall ResetLocalUserPassword(PCWSTR SourceString, PCWSTR a2, PCWSTR a3, PCWSTR a4)
{
  void *v4; // rbx
  ULONG v9; // eax
  ULONG v10; // esi
  __int64 v11; // r9
  const char *v12; // rdx
  __int64 v13; // rcx
  NTSTATUS v14; // eax
  unsigned int v15; // edi
  ULONG v16; // eax
  DWORD LastError; // eax
  HANDLE hObject; // [rsp+50h] [rbp-29h] BYREF
  void *v20; // [rsp+58h] [rbp-21h] BYREF
  struct _UNICODE_STRING v21; // [rsp+60h] [rbp-19h] BYREF
  struct _UNICODE_STRING v22; // [rsp+70h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp+7h] BYREF
  struct _UNICODE_STRING v24; // [rsp+90h] [rbp+17h] BYREF

  hObject = 0;
  v4 = 0;
  DestinationString = 0;
  v20 = 0;
  v21 = 0;
  v24 = 0;
  v22 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 29, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids);
  RtlInitUnicodeString(&DestinationString, SourceString);
  RtlInitUnicodeString(&v21, a2);
  RtlInitUnicodeString(&v24, a3);
  RtlInitUnicodeString(&v22, a4);
  v9 = PRCreateLocalToken(&v21, &DestinationString, &hObject);
  v10 = v9;
  if ( v9 )
  {
    v11 = 2224;
    v12 = "dwError";
    v13 = v9;
LABEL_6:
    DebugTraceError(v13, v12, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", v11);
    goto LABEL_12;
  }
  v14 = SamIChangePasswordForeignUser(0, &v21, &v22, hObject, 64, 0);
  v15 = v14;
  if ( v14 < 0 )
  {
    v16 = RtlNtStatusToDosError(v14);
    v11 = 2243;
    v12 = "Status";
    v10 = v16;
    v13 = v15;
    goto LABEL_6;
  }
  if ( !(unsigned int)GetTokenUserSid(hObject, &v20) )
  {
    LastError = GetLastError();
    DebugTraceError(
      LastError,
      "GetLastError()",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp",
      2254);
  }
  v4 = v20;
  (*((void (__fastcall **)(void *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, _QWORD, _QWORD, struct _UNICODE_STRING *, struct _UNICODE_STRING *, char))g_pDPAPILsasrvIfTable
   + 8))(
    v20,
    &DestinationString,
    &v21,
    0,
    0,
    &v24,
    &v22,
    1);
LABEL_12:
  if ( hObject )
    CloseHandle(hObject);
  if ( v4 )
    LocalFree(v4);
  return v10;
}

```

## disassembly

```asm
0x180037e98  push    rbp
0x180037e9a  push    rbx
0x180037e9b  push    rsi
0x180037e9c  push    rdi
0x180037e9d  push    r14
0x180037e9f  push    r15
0x180037ea1  lea     rbp, [rsp-2Fh]
0x180037ea6  sub     rsp, 0A8h
0x180037ead  xorps   xmm0, xmm0
0x180037eb0  mov     [rbp+57h+hObject], 0
0x180037eb8  xorps   xmm1, xmm1
0x180037ebb  xor     ebx, ebx
0x180037ebd  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180037ec1  mov     [rbp+57h+var_78], rbx
0x180037ec5  mov     rdi, r9
0x180037ec8  movups  xmmword ptr [rbp+57h+var_70.Length], xmm1
0x180037ecc  mov     rsi, r8
0x180037ecf  mov     r14, rdx
0x180037ed2  movups  xmmword ptr [rbp+57h+var_40.Length], xmm0
0x180037ed6  mov     r15, rcx
0x180037ed9  movups  xmmword ptr [rbp+57h+var_60.Length], xmm1
0x180037edd  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ee4  lea     rax, WPP_GLOBAL_Control
0x180037eeb  cmp     rcx, rax
0x180037eee  jz      short loc_180037F09
0x180037ef0  test    byte ptr [rcx+1Ch], 8
0x180037ef4  jz      short loc_180037F09
0x180037ef6  mov     rcx, [rcx+10h]
0x180037efa  lea     edx, [rbx+1Dh]
0x180037efd  lea     r8, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids
0x180037f04  call    WPP_SF_
0x180037f09  mov     rdx, r15; SourceString
0x180037f0c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180037f10  call    cs:__imp_RtlInitUnicodeString
0x180037f17  nop     dword ptr [rax+rax+00h]
0x180037f1c  mov     rdx, r14; SourceString
0x180037f1f  lea     rcx, [rbp+57h+var_70]; DestinationString
0x180037f23  call    cs:__imp_RtlInitUnicodeString
0x180037f2a  nop     dword ptr [rax+rax+00h]
0x180037f2f  mov     rdx, rsi; SourceString
0x180037f32  lea     rcx, [rbp+57h+var_40]; DestinationString
0x180037f36  call    cs:__imp_RtlInitUnicodeString
0x180037f3d  nop     dword ptr [rax+rax+00h]
0x180037f42  mov     rdx, rdi; SourceString
0x180037f45  lea     rcx, [rbp+57h+var_60]; DestinationString
0x180037f49  call    cs:__imp_RtlInitUnicodeString
0x180037f50  nop     dword ptr [rax+rax+00h]
0x180037f55  lea     r8, [rbp+57h+hObject]; void **
0x180037f59  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x180037f5d  lea     rcx, [rbp+57h+var_70]; struct _UNICODE_STRING *
0x180037f61  call    ?PRCreateLocalToken@@YAKPEAU_UNICODE_STRING@@0PEAPEAX@Z; PRCreateLocalToken(_UNICODE_STRING *,_UNICODE_STRING *,void * *)
0x180037f66  mov     esi, eax
0x180037f68  test    eax, eax
0x180037f6a  jz      short loc_180037F8C
0x180037f6c  mov     r9d, 8B0h
0x180037f72  lea     rdx, aDwerror; "dwError"
0x180037f79  mov     ecx, eax
0x180037f7b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180037f82  call    DebugTraceError
0x180037f87  jmp     loc_180038050
0x180037f8c  mov     r9, [rbp+57h+hObject]
0x180037f90  lea     r8, [rbp+57h+var_60]
0x180037f94  mov     [rsp+0D0h+var_A8], rbx
0x180037f99  lea     rdx, [rbp+57h+var_70]
0x180037f9d  xor     ecx, ecx
0x180037f9f  mov     dword ptr [rsp+0D0h+var_B0], 40h ; '@'
0x180037fa7  call    cs:__imp_SamIChangePasswordForeignUser
0x180037fae  nop     dword ptr [rax+rax+00h]
0x180037fb3  mov     edi, eax
0x180037fb5  test    eax, eax
0x180037fb7  jns     short loc_180037FDA
0x180037fb9  mov     ecx, eax; Status
0x180037fbb  call    cs:__imp_RtlNtStatusToDosError
0x180037fc2  nop     dword ptr [rax+rax+00h]
0x180037fc7  mov     r9d, 8C3h
0x180037fcd  lea     rdx, aStatus; "Status"
0x180037fd4  mov     esi, eax
0x180037fd6  mov     ecx, edi
0x180037fd8  jmp     short loc_180037F7B
0x180037fda  mov     rcx, [rbp+57h+hObject]
0x180037fde  lea     rdx, [rbp+57h+var_78]
0x180037fe2  call    GetTokenUserSid
0x180037fe7  test    eax, eax
0x180037fe9  jnz     short loc_180038012
0x180037feb  call    cs:__imp_GetLastError
0x180037ff2  nop     dword ptr [rax+rax+00h]
0x180037ff7  mov     r9d, 8CEh
0x180037ffd  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180038004  mov     ecx, eax
0x180038006  lea     rdx, aGetlasterror; "GetLastError()"
0x18003800d  call    DebugTraceError
0x180038012  mov     rax, cs:?g_pDPAPILsasrvIfTable@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pDPAPILsasrvIfTable
0x180038019  lea     rcx, [rbp+57h+var_60]
0x18003801d  mov     [rsp+0D0h+var_98], 1
0x180038022  lea     r8, [rbp+57h+var_70]
0x180038026  mov     [rsp+0D0h+var_A0], rcx
0x18003802b  lea     rdx, [rbp+57h+DestinationString]
0x18003802f  lea     rcx, [rbp+57h+var_40]
0x180038033  xor     r9d, r9d
0x180038036  mov     rax, [rax+40h]
0x18003803a  mov     [rsp+0D0h+var_A8], rcx
0x18003803f  mov     [rsp+0D0h+var_B0], rbx
0x180038044  mov     rbx, [rbp+57h+var_78]
0x180038048  mov     rcx, rbx
0x18003804b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038050  mov     rcx, [rbp+57h+hObject]; hObject
0x180038054  test    rcx, rcx
0x180038057  jz      short loc_180038065
0x180038059  call    cs:__imp_CloseHandle
0x180038060  nop     dword ptr [rax+rax+00h]
0x180038065  test    rbx, rbx
0x180038068  jz      short loc_180038079
0x18003806a  mov     rcx, rbx; hMem
0x18003806d  call    cs:__imp_LocalFree
0x180038074  nop     dword ptr [rax+rax+00h]
0x180038079  mov     eax, esi
0x18003807b  add     rsp, 0A8h
0x180038082  pop     r15
0x180038084  pop     r14
0x180038086  pop     rdi
0x180038087  pop     rsi
0x180038088  pop     rbx
0x180038089  pop     rbp
0x18003808a  retn
```
