# RemoveSavedCredentials

- ea: `0x18001f04c`
- end: `0x18001f1f5`
- name: `RemoveSavedCredentials`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001aa60`

## callees

- `0x18001f04c`
- `0x1800214f0`
- `0x18002d5cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f0be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f106`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f15f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f0be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f106`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f15f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f19d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f19d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001f136`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001f136`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001f091`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001f091`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18001f0ad`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18001f0fc`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18001f0ad`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18001f0fc`
- `MobileNetworking!ReleaseWriteLock` at `0x18001f1ee`
- `MobileNetworking!AcquireWriteLock` at `0x18001f06d`
- `MobileNetworking!AcquireWriteLock` at `0x18001f06d`

## string_xrefs

- `0x18001f058`: `RemoveSavedCredentials`
- `0x18001f1d4`: `RemoveSavedCredentials`

## pseudocode

```c
__int64 RemoveSavedCredentials()
{
  DWORD LastError; // eax
  DWORD v1; // eax
  DWORD v2; // eax
  _QWORD *v3; // rcx
  __int64 v4; // rdx

  AcquireWriteLock(g_OneXSsoInfo, g_OneXSsoInfo, "RemoveSavedCredentials", 704);
  if ( !fSaveToCredMan || hObject == (HANDLE)-1LL )
    return ReleaseWriteLock(g_OneXSsoInfo, g_OneXSsoInfo, "RemoveSavedCredentials", 746);
  if ( ImpersonateLoggedOnUser(hObject) )
  {
    if ( !CredDeleteW(L"*Session", 2u, 0) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 46, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, LastError);
    }
    if ( !CredDeleteW(L"*Session", 3u, 0) )
    {
      v1 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 47, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, v1);
    }
    if ( RevertToSelf() )
      goto LABEL_20;
    v2 = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0 )
      goto LABEL_20;
    v4 = 48;
    goto LABEL_19;
  }
  v2 = GetLastError();
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
  {
    v4 = 49;
LABEL_19:
    WPP_SF_D(v3[7], v4, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, v2);
  }
LABEL_20:
  CloseHandle(hObject);
  pConnectionIdThatLastSavedCreds = 0;
  hObject = (HANDLE)-1LL;
  if ( qword_18003DF20 )
    FreeApplicationTicket(&qword_18003DF20);
  return ReleaseWriteLock(g_OneXSsoInfo, g_OneXSsoInfo, "RemoveSavedCredentials", 746);
}

```

## disassembly

```asm
0x18001f04c  push    rbx
0x18001f04e  sub     rsp, 20h
0x18001f052  mov     r9d, 2C0h
0x18001f058  lea     r8, aRemovesavedcre; "RemoveSavedCredentials"
0x18001f05f  lea     rdx, g_OneXSsoInfo
0x18001f066  lea     rcx, g_OneXSsoInfo
0x18001f06d  call    cs:__imp_AcquireWriteLock
0x18001f073  cmp     cs:fSaveToCredMan, 0
0x18001f07a  jz      loc_18001F1CE
0x18001f080  mov     rcx, cs:hObject; hToken
0x18001f087  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f08b  jz      loc_18001F1CE
0x18001f091  call    cs:__imp_ImpersonateLoggedOnUser
0x18001f097  test    eax, eax
0x18001f099  jz      loc_18001F15F
0x18001f09f  xor     r8d, r8d; Flags
0x18001f0a2  lea     rcx, TargetName; "*Session"
0x18001f0a9  lea     edx, [r8+2]; Type
0x18001f0ad  call    cs:__imp_CredDeleteW
0x18001f0b3  lea     rbx, WPP_GLOBAL_Control
0x18001f0ba  test    eax, eax
0x18001f0bc  jnz     short loc_18001F0EE
0x18001f0be  call    cs:__imp_GetLastError
0x18001f0c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0cb  cmp     rcx, rbx
0x18001f0ce  jz      short loc_18001F0EE
0x18001f0d0  test    byte ptr [rcx+44h], 10h
0x18001f0d4  jz      short loc_18001F0EE
0x18001f0d6  mov     rcx, [rcx+38h]
0x18001f0da  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18001f0e1  mov     edx, 2Eh ; '.'
0x18001f0e6  mov     r9d, eax
0x18001f0e9  call    WPP_SF_D
0x18001f0ee  xor     r8d, r8d; Flags
0x18001f0f1  lea     rcx, TargetName; "*Session"
0x18001f0f8  lea     edx, [r8+3]; Type
0x18001f0fc  call    cs:__imp_CredDeleteW
0x18001f102  test    eax, eax
0x18001f104  jnz     short loc_18001F136
0x18001f106  call    cs:__imp_GetLastError
0x18001f10c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f113  cmp     rcx, rbx
0x18001f116  jz      short loc_18001F136
0x18001f118  test    byte ptr [rcx+44h], 10h
0x18001f11c  jz      short loc_18001F136
0x18001f11e  mov     rcx, [rcx+38h]
0x18001f122  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18001f129  mov     edx, 2Fh ; '/'
0x18001f12e  mov     r9d, eax
0x18001f131  call    WPP_SF_D
0x18001f136  call    cs:__imp_RevertToSelf
0x18001f13c  test    eax, eax
0x18001f13e  jnz     short loc_18001F196
0x18001f140  call    cs:__imp_GetLastError
0x18001f146  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f14d  cmp     rcx, rbx
0x18001f150  jz      short loc_18001F196
0x18001f152  test    byte ptr [rcx+44h], 10h
0x18001f156  jz      short loc_18001F196
0x18001f158  mov     edx, 30h ; '0'
0x18001f15d  jmp     short loc_18001F183
0x18001f15f  call    cs:__imp_GetLastError
0x18001f165  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f16c  lea     rbx, WPP_GLOBAL_Control
0x18001f173  cmp     rcx, rbx
0x18001f176  jz      short loc_18001F196
0x18001f178  test    byte ptr [rcx+44h], 10h
0x18001f17c  jz      short loc_18001F196
0x18001f17e  mov     edx, 31h ; '1'
0x18001f183  mov     rcx, [rcx+38h]
0x18001f187  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18001f18e  mov     r9d, eax
0x18001f191  call    WPP_SF_D
0x18001f196  mov     rcx, cs:hObject; hObject
0x18001f19d  call    cs:__imp_CloseHandle
0x18001f1a3  cmp     cs:qword_18003DF20, 0
0x18001f1ab  xorps   xmm0, xmm0
0x18001f1ae  movups  xmmword ptr cs:pConnectionIdThatLastSavedCreds.Data1, xmm0
0x18001f1b5  mov     cs:hObject, 0FFFFFFFFFFFFFFFFh
0x18001f1c0  jz      short loc_18001F1CE
0x18001f1c2  lea     rcx, qword_18003DF20
0x18001f1c9  call    FreeApplicationTicket
0x18001f1ce  mov     r9d, 2EAh
0x18001f1d4  lea     r8, aRemovesavedcre; "RemoveSavedCredentials"
0x18001f1db  lea     rdx, g_OneXSsoInfo
0x18001f1e2  lea     rcx, g_OneXSsoInfo
0x18001f1e9  add     rsp, 20h
0x18001f1ed  pop     rbx
0x18001f1ee  jmp     cs:__imp_ReleaseWriteLock
```
