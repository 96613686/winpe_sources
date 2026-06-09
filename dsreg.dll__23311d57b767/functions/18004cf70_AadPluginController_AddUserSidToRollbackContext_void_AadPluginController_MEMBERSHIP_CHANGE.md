# AadPluginController::AddUserSidToRollbackContext(void *,AadPluginController::_MEMBERSHIP_CHANGE *)

- ea: `0x18004cf70`
- end: `0x18004d1ac`
- name: `?AddUserSidToRollbackContext@AadPluginController@@AEAAJPEAXPEAU_MEMBERSHIP_CHANGE@1@@Z`
- size: `572`
- prototype: `__int64 __fastcall(AadPluginController *this, void *, struct AadPluginController::_MEMBERSHIP_CHANGE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180040014`

## callees

- `0x1800084f4`
- `0x180012948`
- `0x180012cf0`
- `0x1800307c4`
- `0x180030828`
- `0x18003334c`
- `0x180043ef8`
- `0x180043f04`
- `0x18004cf70`
- `0x1800900a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d10d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d10d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d09a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d09a`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18004d0ae`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18004d0ae`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004cfe3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004cfe3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004d0e2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004d0e2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004d062`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004d062`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004d103`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004d103`

## string_xrefs

- `0x18004d146`: `EventWriteCopySidFailureEvent`
- `0x18004d14d`: `Logger::WriteCopySidFailureEvent`
- `0x18004d01e`: `Logger::WriteInvalidSidEvent`
- `0x18004d017`: `EventWriteInvalidSidEvent`
- `0x18004cf96`: `AadPluginController::AddUserSidToRollbackContext`
- `0x18004cfb0`: `AadPluginController::AddUserSidToRollbackContext`
- `0x18004cfc8`: `AadPluginController::AddUserSidToRollbackContext`
- `0x18004cffd`: `AadPluginController::AddUserSidToRollbackContext`
- `0x18004d031`: `AadPluginController::AddUserSidToRollbackContext`
- `0x18004d0b9`: `AadPluginController::AddUserSidToRollbackContext`
- `0x18004d16e`: `AadPluginController::AddUserSidToRollbackContext`
- `0x18004cfcf`: `%s: empty user SID`
- `0x18004cff6`: `pUserSid`
- `0x18004d038`: `%s: The user SID is invalid`
- `0x18004d167`: `CopySid`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AadPluginController::AddUserSidToRollbackContext(
        AadPluginController *this,
        void *a2,
        struct AadPluginController::_MEMBERSHIP_CHANGE *a3)
{
  void *v3; // rbp
  unsigned int v6; // ebx
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned __int64 i; // r14
  __int64 v10; // rax
  void *v11; // r14
  SIZE_T v12; // r15
  LPVOID v13; // rax
  HANDLE ProcessHeap; // rax
  unsigned __int64 LengthSid; // r14
  void *v16; // rax
  signed int LastError; // eax
  __int64 v18; // rcx
  unsigned int v19; // eax

  v3 = 0;
  if ( !a3 )
  {
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"AadPluginController::AddUserSidToRollbackContext",
      L"pGroupMembershipChange");
    Logger::WriteNullOrEmptyParameterFailureEvent(
      L"AadPluginController::AddUserSidToRollbackContext",
      L"pGroupMembershipChange");
    goto LABEL_32;
  }
  v6 = 0;
  if ( !a2 )
  {
    Logger::TraceInformation(L"%s: empty user SID", L"AadPluginController::AddUserSidToRollbackContext");
    goto LABEL_32;
  }
  if ( !IsValidSid(a2) )
  {
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
    {
      v8 = McTemplateU0zz_EventWriteTransfer(
             v7,
             InvalidSidEvent,
             L"AadPluginController::AddUserSidToRollbackContext",
             L"pUserSid");
      if ( v8 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteInvalidSidEvent",
          L"EventWriteInvalidSidEvent",
          v8);
    }
    Logger::TraceError(L"%s: The user SID is invalid", L"AadPluginController::AddUserSidToRollbackContext");
    v6 = -2147024809;
    goto LABEL_32;
  }
  for ( i = 0; i < *((_QWORD *)a3 + 2); ++i )
  {
    if ( EqualSid(a2, *(PSID *)(*((_QWORD *)a3 + 1) + 8 * i)) )
      goto LABEL_32;
  }
  v10 = *((_QWORD *)a3 + 3);
  if ( *((_QWORD *)a3 + 2) == v10 )
  {
    v11 = (void *)*((_QWORD *)a3 + 1);
    v12 = 8 * v10 + 1024;
    if ( v11 )
    {
      ProcessHeap = GetProcessHeap();
      v13 = HeapReAlloc(ProcessHeap, 8u, v11, v12);
    }
    else
    {
      v13 = SafeAlloc(8 * v10 + 1024);
    }
    if ( !v13 )
      goto LABEL_19;
    *((_QWORD *)a3 + 3) += 128LL;
    *((_QWORD *)a3 + 1) = v13;
  }
  LengthSid = GetLengthSid(a2);
  v16 = operator new[](LengthSid);
  v3 = v16;
  if ( !v16 )
  {
LABEL_19:
    v6 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"AadPluginController::AddUserSidToRollbackContext");
    goto LABEL_32;
  }
  if ( CopySid(LengthSid, v16, a2) )
    goto LABEL_31;
  LastError = GetLastError();
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  else
    v6 = LastError;
  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
  {
    v19 = McTemplateU0kq_EventWriteTransfer(v18, CopySidFailureEvent, a2, (unsigned int)LastError);
    if ( v19 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteCopySidFailureEvent",
        L"EventWriteCopySidFailureEvent",
        v19);
  }
  if ( (v6 & 0x80000000) == 0 )
  {
LABEL_31:
    *(_QWORD *)(*((_QWORD *)a3 + 1) + 8LL * (*((_QWORD *)a3 + 2))++) = v3;
    v3 = 0;
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"AadPluginController::AddUserSidToRollbackContext",
      L"CopySid",
      v6);
  }
LABEL_32:
  operator delete(v3);
  return v6;
}

```

## disassembly

```asm
0x18004cf70  push    rbx
0x18004cf72  push    rbp
0x18004cf73  push    rsi
0x18004cf74  push    rdi
0x18004cf75  push    r14
0x18004cf77  push    r15
0x18004cf79  sub     rsp, 28h
0x18004cf7d  xor     ebp, ebp
0x18004cf7f  mov     rdi, r8
0x18004cf82  mov     rsi, rdx
0x18004cf85  test    r8, r8
0x18004cf88  jnz     short loc_18004CFC1
0x18004cf8a  lea     r8, aPgroupmembersh; "pGroupMembershipChange"
0x18004cf91  mov     ebx, 80070057h
0x18004cf96  lea     rdx, aAadplugincontr_10; "AadPluginController::AddUserSidToRollba"...
0x18004cf9d  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18004cfa4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004cfa9  lea     rdx, aPgroupmembersh; "pGroupMembershipChange"
0x18004cfb0  lea     rcx, aAadplugincontr_10; "AadPluginController::AddUserSidToRollba"...
0x18004cfb7  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18004cfbc  jmp     loc_18004D195
0x18004cfc1  xor     ebx, ebx
0x18004cfc3  test    rsi, rsi
0x18004cfc6  jnz     short loc_18004CFE0
0x18004cfc8  lea     rdx, aAadplugincontr_10; "AadPluginController::AddUserSidToRollba"...
0x18004cfcf  lea     rcx, aSEmptyUserSid; "%s: empty user SID"
0x18004cfd6  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18004cfdb  jmp     loc_18004D195
0x18004cfe0  mov     rcx, rsi; pSid
0x18004cfe3  call    cs:__imp_IsValidSid
0x18004cfe9  test    eax, eax
0x18004cfeb  jnz     short loc_18004D04E
0x18004cfed  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x18004cff4  jz      short loc_18004D031
0x18004cff6  lea     r9, aPusersid; "pUserSid"
0x18004cffd  lea     r8, aAadplugincontr_10; "AadPluginController::AddUserSidToRollba"...
0x18004d004  lea     rdx, InvalidSidEvent
0x18004d00b  call    McTemplateU0zz_EventWriteTransfer
0x18004d010  test    eax, eax
0x18004d012  jz      short loc_18004D031
0x18004d014  mov     r9d, eax
0x18004d017  lea     r8, aEventwriteinva_1; "EventWriteInvalidSidEvent"
0x18004d01e  lea     rdx, aLoggerWriteinv_1; "Logger::WriteInvalidSidEvent"
0x18004d025  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18004d02c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004d031  lea     rdx, aAadplugincontr_10; "AadPluginController::AddUserSidToRollba"...
0x18004d038  lea     rcx, aSTheUserSidIsI; "%s: The user SID is invalid"
0x18004d03f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004d044  mov     ebx, 80070057h
0x18004d049  jmp     loc_18004D195
0x18004d04e  xor     r14d, r14d
0x18004d051  cmp     r14, [rdi+10h]
0x18004d055  jnb     short loc_18004D075
0x18004d057  mov     rdx, [rdi+8]
0x18004d05b  mov     rcx, rsi; pSid1
0x18004d05e  mov     rdx, [rdx+r14*8]; pSid2
0x18004d062  call    cs:__imp_EqualSid
0x18004d068  test    eax, eax
0x18004d06a  jnz     loc_18004D195
0x18004d070  inc     r14
0x18004d073  jmp     short loc_18004D051
0x18004d075  mov     rax, [rdi+18h]
0x18004d079  cmp     [rdi+10h], rax
0x18004d07d  jnz     short loc_18004D0DF
0x18004d07f  mov     r14, [rdi+8]
0x18004d083  lea     r15, ds:400h[rax*8]
0x18004d08b  test    r14, r14
0x18004d08e  jnz     short loc_18004D09A
0x18004d090  mov     rcx, r15; unsigned __int64
0x18004d093  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18004d098  jmp     short loc_18004D0B4
0x18004d09a  call    cs:__imp_GetProcessHeap
0x18004d0a0  mov     r9, r15; dwBytes
0x18004d0a3  mov     r8, r14; lpMem
0x18004d0a6  mov     rcx, rax; hHeap
0x18004d0a9  mov     edx, 8; dwFlags
0x18004d0ae  call    cs:__imp_HeapReAlloc
0x18004d0b4  test    rax, rax
0x18004d0b7  jnz     short loc_18004D0D6
0x18004d0b9  lea     rdx, aAadplugincontr_10; "AadPluginController::AddUserSidToRollba"...
0x18004d0c0  mov     ebx, 8007000Eh
0x18004d0c5  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18004d0cc  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18004d0d1  jmp     loc_18004D195
0x18004d0d6  sub     qword ptr [rdi+18h], 0FFFFFFFFFFFFFF80h
0x18004d0db  mov     [rdi+8], rax
0x18004d0df  mov     rcx, rsi; pSid
0x18004d0e2  call    cs:__imp_GetLengthSid
0x18004d0e8  mov     ecx, eax; unsigned __int64
0x18004d0ea  mov     r14d, eax
0x18004d0ed  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004d0f2  mov     rbp, rax
0x18004d0f5  test    rax, rax
0x18004d0f8  jz      short loc_18004D0B9
0x18004d0fa  mov     r8, rsi; pSourceSid
0x18004d0fd  mov     rdx, rax; pDestinationSid
0x18004d100  mov     ecx, r14d; nDestinationSidLength
0x18004d103  call    cs:__imp_CopySid
0x18004d109  test    eax, eax
0x18004d10b  jnz     short loc_18004D183
0x18004d10d  call    cs:__imp_GetLastError
0x18004d113  test    eax, eax
0x18004d115  jg      short loc_18004D11B
0x18004d117  mov     ebx, eax
0x18004d119  jmp     short loc_18004D124
0x18004d11b  movzx   ebx, ax
0x18004d11e  or      ebx, 80070000h
0x18004d124  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x18004d12b  jz      short loc_18004D160
0x18004d12d  mov     r9d, eax
0x18004d130  lea     rdx, CopySidFailureEvent
0x18004d137  mov     r8, rsi
0x18004d13a  call    McTemplateU0kq_EventWriteTransfer
0x18004d13f  test    eax, eax
0x18004d141  jz      short loc_18004D160
0x18004d143  mov     r9d, eax
0x18004d146  lea     r8, aEventwritecopy; "EventWriteCopySidFailureEvent"
0x18004d14d  lea     rdx, aLoggerWritecop; "Logger::WriteCopySidFailureEvent"
0x18004d154  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18004d15b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004d160  test    ebx, ebx
0x18004d162  jns     short loc_18004D183
0x18004d164  mov     r9d, ebx
0x18004d167  lea     r8, aCopysid; "CopySid"
0x18004d16e  lea     rdx, aAadplugincontr_10; "AadPluginController::AddUserSidToRollba"...
0x18004d175  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18004d17c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004d181  jmp     short loc_18004D195
0x18004d183  mov     rdx, [rdi+10h]
0x18004d187  mov     rcx, [rdi+8]
0x18004d18b  mov     [rcx+rdx*8], rbp
0x18004d18f  inc     qword ptr [rdi+10h]
0x18004d193  xor     ebp, ebp
0x18004d195  mov     rcx, rbp; Block
0x18004d198  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004d19d  mov     eax, ebx
0x18004d19f  add     rsp, 28h
0x18004d1a3  pop     r15
0x18004d1a5  pop     r14
0x18004d1a7  pop     rdi
0x18004d1a8  pop     rsi
0x18004d1a9  pop     rbp
0x18004d1aa  pop     rbx
0x18004d1ab  retn
```
