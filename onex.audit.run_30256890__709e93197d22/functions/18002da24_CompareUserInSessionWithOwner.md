# CompareUserInSessionWithOwner

- ea: `0x18002da24`
- end: `0x18002dc2e`
- name: `CompareUserInSessionWithOwner`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027158`

## callees

- `0x18001abb4`
- `0x180025740`
- `0x18002da24`
- `0x18002dc34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dadc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dadc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dc1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dc1b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002dbe1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002dbe1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002dad6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002db94`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002dad6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002db94`
- `MobileNetworking!AllocateMemory` at `0x18002db2f`
- `MobileNetworking!AllocateMemory` at `0x18002db2f`
- `MobileNetworking!FreeMemory` at `0x18002dc0c`
- `MobileNetworking!FreeMemory` at `0x18002dc0c`

## string_xrefs

- `0x18002db1e`: `CompareUserInSessionWithOwner`
- `0x18002dc01`: `CompareUserInSessionWithOwner`

## pseudocode

```c
__int64 __fastcall CompareUserInSessionWithOwner(__int64 *a1, _DWORD *a2)
{
  __int64 v2; // rax
  ULONG v5; // ecx
  unsigned int v6; // esi
  DWORD LastError; // ebx
  __int64 v8; // r8
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  DWORD TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  LPVOID TokenInformation; // [rsp+68h] [rbp+38h] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp+40h] BYREF

  v2 = *a1;
  *a2 = 1;
  v5 = *((_DWORD *)a1 + 112);
  TokenInformation = 0;
  TokenInformationLength = 0;
  TokenHandle = 0;
  v6 = *(_DWORD *)(v2 + 20);
  if ( (unsigned int)OnexQueryUserToken(v5, &TokenHandle) || (LastError = GetLastError()) == 0 )
  {
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      LastError = AllocateMemory(TokenInformationLength, &TokenInformation, "CompareUserInSessionWithOwner", 607);
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_dD(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            56,
            WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids,
            v6,
            LastError);
      }
      else if ( GetTokenInformation(
                  TokenHandle,
                  TokenUser,
                  TokenInformation,
                  TokenInformationLength,
                  &TokenInformationLength)
             || (LastError = GetLastError()) == 0 )
      {
        if ( EqualSid((PSID)(a1[47] + *(unsigned int *)(a1[47] + 24)), *(PSID *)TokenInformation) )
          *a2 = 0;
        LastError = 0;
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v10 = 57;
          goto LABEL_6;
        }
      }
    }
    else
    {
      if ( !LastError )
        LastError = 87;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v10 = 55;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v10 = 54;
LABEL_6:
      WPP_SF_dDd(v9[7], v10, v8, v6, LastError, *((_DWORD *)a1 + 112));
    }
  }
  if ( TokenInformation )
    FreeMemory(&TokenInformation, "CompareUserInSessionWithOwner", 629);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18002da24  push    rbp
0x18002da26  push    rbx
0x18002da27  push    rsi
0x18002da28  push    rdi
0x18002da29  push    r14
0x18002da2b  mov     rbp, rsp
0x18002da2e  sub     rsp, 30h
0x18002da32  mov     rax, [rcx]
0x18002da35  mov     r14, rdx
0x18002da38  mov     rdi, rcx
0x18002da3b  mov     dword ptr [rdx], 1
0x18002da41  mov     ecx, [rcx+1C0h]; SessionId
0x18002da47  lea     rdx, [rbp+TokenHandle]; phToken
0x18002da4b  mov     [rbp+TokenInformation], 0
0x18002da53  mov     [rbp+TokenInformationLength], 0
0x18002da5a  mov     [rbp+TokenHandle], 0
0x18002da62  mov     esi, [rax+14h]
0x18002da65  call    OnexQueryUserToken
0x18002da6a  test    eax, eax
0x18002da6c  jnz     short loc_18002DABF
0x18002da6e  call    cs:__imp_GetLastError
0x18002da74  mov     ebx, eax
0x18002da76  test    eax, eax
0x18002da78  jz      short loc_18002DABF
0x18002da7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002da81  lea     rax, WPP_GLOBAL_Control
0x18002da88  cmp     rcx, rax
0x18002da8b  jz      loc_18002DBF4
0x18002da91  test    byte ptr [rcx+44h], 1
0x18002da95  jz      loc_18002DBF4
0x18002da9b  mov     edx, 36h ; '6'
0x18002daa0  mov     eax, [rdi+1C0h]
0x18002daa6  mov     r9d, esi
0x18002daa9  mov     rcx, [rcx+38h]
0x18002daad  mov     [rsp+30h+var_8], eax
0x18002dab1  mov     dword ptr [rsp+30h+ReturnLength], ebx
0x18002dab5  call    WPP_SF_dDd
0x18002daba  jmp     loc_18002DBF4
0x18002dabf  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002dac3  lea     rax, [rbp+TokenInformationLength]
0x18002dac7  xor     r9d, r9d; TokenInformationLength
0x18002daca  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002dacf  xor     r8d, r8d; TokenInformation
0x18002dad2  lea     edx, [r9+1]; TokenInformationClass
0x18002dad6  call    cs:__imp_GetTokenInformation
0x18002dadc  call    cs:__imp_GetLastError
0x18002dae2  mov     ebx, eax
0x18002dae4  cmp     eax, 7Ah ; 'z'
0x18002dae7  jz      short loc_18002DB1B
0x18002dae9  test    ebx, ebx
0x18002daeb  mov     eax, 57h ; 'W'
0x18002daf0  cmovz   ebx, eax
0x18002daf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dafa  lea     rax, WPP_GLOBAL_Control
0x18002db01  cmp     rcx, rax
0x18002db04  jz      loc_18002DBF4
0x18002db0a  test    byte ptr [rcx+44h], 1
0x18002db0e  jz      loc_18002DBF4
0x18002db14  mov     edx, 37h ; '7'
0x18002db19  jmp     short loc_18002DAA0
0x18002db1b  mov     ecx, [rbp+TokenInformationLength]
0x18002db1e  lea     r8, aCompareuserins; "CompareUserInSessionWithOwner"
0x18002db25  mov     r9d, 25Fh
0x18002db2b  lea     rdx, [rbp+TokenInformation]
0x18002db2f  call    cs:__imp_AllocateMemory
0x18002db35  mov     ebx, eax
0x18002db37  test    eax, eax
0x18002db39  jz      short loc_18002DB7A
0x18002db3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db42  lea     rax, WPP_GLOBAL_Control
0x18002db49  cmp     rcx, rax
0x18002db4c  jz      loc_18002DBF4
0x18002db52  test    byte ptr [rcx+44h], 1
0x18002db56  jz      loc_18002DBF4
0x18002db5c  mov     rcx, [rcx+38h]
0x18002db60  lea     r8, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x18002db67  mov     edx, 38h ; '8'
0x18002db6c  mov     dword ptr [rsp+30h+ReturnLength], ebx
0x18002db70  mov     r9d, esi
0x18002db73  call    WPP_SF_dD
0x18002db78  jmp     short loc_18002DBF4
0x18002db7a  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002db7e  lea     rax, [rbp+TokenInformationLength]
0x18002db82  mov     r8, [rbp+TokenInformation]; TokenInformation
0x18002db86  mov     edx, 1; TokenInformationClass
0x18002db8b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002db8f  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002db94  call    cs:__imp_GetTokenInformation
0x18002db9a  test    eax, eax
0x18002db9c  jnz     short loc_18002DBCD
0x18002db9e  call    cs:__imp_GetLastError
0x18002dba4  mov     ebx, eax
0x18002dba6  test    eax, eax
0x18002dba8  jz      short loc_18002DBCD
0x18002dbaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dbb1  lea     rax, WPP_GLOBAL_Control
0x18002dbb8  cmp     rcx, rax
0x18002dbbb  jz      short loc_18002DBF4
0x18002dbbd  test    byte ptr [rcx+44h], 1
0x18002dbc1  jz      short loc_18002DBF4
0x18002dbc3  mov     edx, 39h ; '9'
0x18002dbc8  jmp     loc_18002DAA0
0x18002dbcd  mov     rax, [rdi+178h]
0x18002dbd4  mov     rdx, [rbp+TokenInformation]
0x18002dbd8  mov     ecx, [rax+18h]
0x18002dbdb  mov     rdx, [rdx]; pSid2
0x18002dbde  add     rcx, rax; pSid1
0x18002dbe1  call    cs:__imp_EqualSid
0x18002dbe7  test    eax, eax
0x18002dbe9  jz      short loc_18002DBF2
0x18002dbeb  mov     dword ptr [r14], 0
0x18002dbf2  xor     ebx, ebx
0x18002dbf4  cmp     [rbp+TokenInformation], 0
0x18002dbf9  jz      short loc_18002DC12
0x18002dbfb  mov     r8d, 275h
0x18002dc01  lea     rdx, aCompareuserins; "CompareUserInSessionWithOwner"
0x18002dc08  lea     rcx, [rbp+TokenInformation]
0x18002dc0c  call    cs:__imp_FreeMemory
0x18002dc12  mov     rcx, [rbp+TokenHandle]; hObject
0x18002dc16  test    rcx, rcx
0x18002dc19  jz      short loc_18002DC21
0x18002dc1b  call    cs:__imp_CloseHandle
0x18002dc21  mov     eax, ebx
0x18002dc23  add     rsp, 30h
0x18002dc27  pop     r14
0x18002dc29  pop     rdi
0x18002dc2a  pop     rsi
0x18002dc2b  pop     rbx
0x18002dc2c  pop     rbp
0x18002dc2d  retn
```
