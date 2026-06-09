# utils::CProcess::IsCurrentProcessElevated(void)

- ea: `0x18000fb3c`
- end: `0x18000fd20`
- name: `?IsCurrentProcessElevated@CProcess@utils@@SA_NXZ`
- size: `484`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000d3d0`

## callees

- `0x180002148`
- `0x18000253c`
- `0x180005528`
- `0x180008b30`
- `0x18000fb3c`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x18000fb97`
- `ADVAPI32!GetTokenInformation` at `0x18000fb97`
- `ADVAPI32!OpenProcessToken` at `0x18000fb60`
- `ADVAPI32!OpenProcessToken` at `0x18000fb60`
- `KERNEL32!CloseHandle` at `0x18000fbbb`
- `KERNEL32!CloseHandle` at `0x18000fbbb`
- `KERNEL32!GetLastError` at `0x18000fc26`
- `KERNEL32!GetLastError` at `0x18000fca3`
- `KERNEL32!GetLastError` at `0x18000fc26`
- `KERNEL32!GetLastError` at `0x18000fca3`
- `KERNEL32!GetCurrentProcess` at `0x18000fb4e`
- `KERNEL32!GetCurrentProcess` at `0x18000fb4e`

## pseudocode

```c
bool utils::CProcess::IsCurrentProcessElevated(void)
{
  HANDLE CurrentProcess; // rax
  bool v1; // bl
  signed int LastError; // eax
  unsigned int v4; // edx
  char v5; // r8
  signed int v6; // eax
  unsigned int v7; // edx
  char v8; // r8
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF
  int TokenInformation; // [rsp+58h] [rbp+20h] BYREF
  int pExceptionObject; // [rsp+60h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+30h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    else
      v4 = LastError;
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, v4);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)&WPP_4568c9a8a9263859e817b7a52717e421_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\creator\\lib\\utils\\cprocess.cpp",
        42,
        v5);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  TokenInformation = 0;
  ReturnLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenElevation, &TokenInformation, 4u, &ReturnLength) )
  {
    v6 = GetLastError();
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    else
      v7 = v6;
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, v7);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_4568c9a8a9263859e817b7a52717e421_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\creator\\lib\\utils\\cprocess.cpp",
        51,
        v8);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  if ( ReturnLength != 4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)&WPP_4568c9a8a9263859e817b7a52717e421_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\creator\\lib\\utils\\cprocess.cpp",
        53);
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, -2147467259);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  v1 = TokenInformation != 0;
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x18000fb3c  push    rbp
0x18000fb3e  push    rbx
0x18000fb3f  mov     rbp, rsp
0x18000fb42  sub     rsp, 38h
0x18000fb46  mov     [rbp+TokenHandle], 0
0x18000fb4e  call    cs:__imp_GetCurrentProcess
0x18000fb54  mov     rcx, rax; ProcessHandle
0x18000fb57  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000fb5b  mov     edx, 8; DesiredAccess
0x18000fb60  call    cs:__imp_OpenProcessToken
0x18000fb66  test    eax, eax
0x18000fb68  jz      loc_18000FC26
0x18000fb6e  mov     [rbp+TokenInformation], 0
0x18000fb75  mov     [rbp+arg_0], 0
0x18000fb7c  lea     rax, [rbp+arg_0]
0x18000fb80  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18000fb85  mov     r9d, 4; TokenInformationLength
0x18000fb8b  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000fb8f  lea     edx, [r9+10h]; TokenInformationClass
0x18000fb93  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000fb97  call    cs:__imp_GetTokenInformation
0x18000fb9d  test    eax, eax
0x18000fb9f  jz      loc_18000FCA3
0x18000fba5  cmp     [rbp+arg_0], 4
0x18000fba9  jnz     short loc_18000FBCA
0x18000fbab  cmp     [rbp+TokenInformation], 0
0x18000fbaf  setnz   bl
0x18000fbb2  mov     rcx, [rbp+TokenHandle]; hObject
0x18000fbb6  test    rcx, rcx
0x18000fbb9  jz      short loc_18000FBC1
0x18000fbbb  call    cs:__imp_CloseHandle
0x18000fbc1  mov     al, bl
0x18000fbc3  add     rsp, 38h
0x18000fbc7  pop     rbx
0x18000fbc8  pop     rbp
0x18000fbc9  retn
0x18000fbca  lea     rax, WPP_GLOBAL_Control
0x18000fbd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbd8  cmp     rcx, rax
0x18000fbdb  jz      short loc_18000FC07
0x18000fbdd  test    byte ptr [rcx+1Ch], 1
0x18000fbe1  jz      short loc_18000FC07
0x18000fbe3  mov     edx, 0Ch
0x18000fbe8  mov     dword ptr [rsp+38h+ReturnLength], 35h ; '5'
0x18000fbf0  lea     r9, aDriversWdmUsbp_11; "drivers\\wdm\\usbpw\\creator\\lib\\util"...
0x18000fbf7  lea     r8, WPP_4568c9a8a9263859e817b7a52717e421_Traceguids
0x18000fbfe  mov     rcx, [rcx+10h]
0x18000fc02  call    WPP_SF_sd
0x18000fc07  mov     edx, 80004005h; int
0x18000fc0c  lea     rcx, [rbp+pExceptionObject]; this
0x18000fc10  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000fc15  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000fc1c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000fc20  call    _CxxThrowException_0
0x18000fc26  call    cs:__imp_GetLastError
0x18000fc2c  mov     r8d, eax
0x18000fc2f  test    eax, eax
0x18000fc31  jg      short loc_18000FC37
0x18000fc33  mov     edx, eax
0x18000fc35  jmp     short loc_18000FC41
0x18000fc37  movzx   edx, r8w
0x18000fc3b  or      edx, 80070000h; int
0x18000fc41  lea     rcx, [rbp+pExceptionObject]; this
0x18000fc45  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000fc4a  lea     rax, WPP_GLOBAL_Control
0x18000fc51  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc58  cmp     rcx, rax
0x18000fc5b  jz      short loc_18000FC8C
0x18000fc5d  test    byte ptr [rcx+1Ch], 1
0x18000fc61  jz      short loc_18000FC8C
0x18000fc63  mov     edx, 0Ah
0x18000fc68  mov     [rsp+38h+var_10], r8d
0x18000fc6d  mov     dword ptr [rsp+38h+ReturnLength], 2Ah ; '*'
0x18000fc75  lea     r9, aDriversWdmUsbp_11; "drivers\\wdm\\usbpw\\creator\\lib\\util"...
0x18000fc7c  lea     r8, WPP_4568c9a8a9263859e817b7a52717e421_Traceguids
0x18000fc83  mov     rcx, [rcx+10h]
0x18000fc87  call    WPP_SF_sdD
0x18000fc8c  mov     eax, [rbp+pExceptionObject]
0x18000fc8f  mov     [rbp+pExceptionObject], eax
0x18000fc92  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000fc99  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000fc9d  call    _CxxThrowException_0
0x18000fca3  call    cs:__imp_GetLastError
0x18000fca9  mov     r8d, eax
0x18000fcac  test    eax, eax
0x18000fcae  jg      short loc_18000FCB4
0x18000fcb0  mov     edx, eax
0x18000fcb2  jmp     short loc_18000FCBE
0x18000fcb4  movzx   edx, r8w
0x18000fcb8  or      edx, 80070000h; int
0x18000fcbe  lea     rcx, [rbp+pExceptionObject]; this
0x18000fcc2  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000fcc7  lea     rax, WPP_GLOBAL_Control
0x18000fcce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcd5  cmp     rcx, rax
0x18000fcd8  jz      short loc_18000FD09
0x18000fcda  test    byte ptr [rcx+1Ch], 1
0x18000fcde  jz      short loc_18000FD09
0x18000fce0  mov     edx, 0Bh
0x18000fce5  mov     [rsp+38h+var_10], r8d
0x18000fcea  mov     dword ptr [rsp+38h+ReturnLength], 33h ; '3'
0x18000fcf2  lea     r9, aDriversWdmUsbp_11; "drivers\\wdm\\usbpw\\creator\\lib\\util"...
0x18000fcf9  lea     r8, WPP_4568c9a8a9263859e817b7a52717e421_Traceguids
0x18000fd00  mov     rcx, [rcx+10h]
0x18000fd04  call    WPP_SF_sdD
0x18000fd09  mov     eax, [rbp+pExceptionObject]
0x18000fd0c  mov     [rbp+pExceptionObject], eax
0x18000fd0f  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000fd16  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000fd1a  call    _CxxThrowException_0
```
