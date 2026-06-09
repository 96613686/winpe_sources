# DpspQueueInstanceToUsers

- ea: `0x180007adc`
- end: `0x180007d29`
- name: `DpspQueueInstanceToUsers`
- size: `589`
- prototype: `__int64 __fastcall(PSID pSid1, struct INSTANCEINFO *)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004864`
- `0x180004de4`
- `0x1800137a8`

## callees

- `0x1800013a0`
- `0x180007adc`
- `0x180008f10`
- `0x180009090`
- `0x18000a856`
- `0x180012c50`
- `0x180012cac`
- `0x1800130a8`
- `0x180013148`
- `0x1800152c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007ba7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007cba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007cda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007ba7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007cba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007cda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b87`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007c02`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007c02`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180007c36`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180007c36`

## string_xrefs

- `0x180007c9c`: `DpspCreateSpecificUser`

## pseudocode

```c
__int64 __fastcall DpspQueueInstanceToUsers(PSID pSid1, struct INSTANCEINFO *a2)
{
  int v4; // r8d
  signed int UserFromUserSID; // ebx
  int QueuedResolutions; // eax
  int v7; // r8d
  struct __TARGETUSER *v8; // rbp
  struct __TARGETUSER *v9; // rax
  int v10; // r8d
  int v11; // eax
  size_t LengthSid; // rbx
  void *v13; // rax
  signed int LastError; // eax
  int v15; // eax
  char Args; // [rsp+20h] [rbp-38h]
  struct __TARGETUSER *v18; // [rsp+60h] [rbp+8h] BYREF

  v18 = 0;
  if ( pSid1 )
  {
    if ( !a2 )
    {
      v4 = 709;
      goto LABEL_3;
    }
    if ( !_InterlockedCompareExchange(&g_fQueuedResolutionsRead, 1, 0) )
    {
      QueuedResolutions = DpspReadQueuedResolutions();
      if ( QueuedResolutions < 0 )
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
          (int)L"DpspQueueInstanceToUsers",
          713,
          (int)L"Error = %d",
          QueuedResolutions);
    }
    EnterCriticalSection(&g_csUserList);
    UserFromUserSID = DpspGetUserFromUserSID(pSid1, &v18);
    if ( UserFromUserSID < 0 )
    {
      LeaveCriticalSection(&g_csUserList);
      v7 = 720;
      Args = UserFromUserSID;
LABEL_29:
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
        (int)L"DpspQueueInstanceToUsers",
        v7,
        (int)L"Error = %d",
        Args);
      return (unsigned int)UserFromUserSID;
    }
    v8 = v18;
    if ( !v18 )
    {
      v9 = (struct __TARGETUSER *)WdipAlloc(96);
      v8 = v9;
      if ( !v9 )
      {
        v10 = 121;
LABEL_14:
        UserFromUserSID = -2147024882;
        LOBYTE(v11) = 14;
LABEL_24:
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
          (int)L"DpspCreateSpecificUser",
          v10,
          (int)L"Error = %d",
          v11);
        DpspFreeSpecificUser(v8);
        LeaveCriticalSection(&g_csUserList);
        LOBYTE(v15) = UserFromUserSID;
        v7 = 727;
LABEL_28:
        Args = v15;
        goto LABEL_29;
      }
      memset_0(v9, 0, 0x60u);
      LengthSid = GetLengthSid(pSid1);
      v13 = (void *)WdipAlloc(LengthSid);
      *((_QWORD *)v8 + 8) = v13;
      if ( !v13 )
      {
        v10 = 126;
        goto LABEL_14;
      }
      memset_0(v13, 0, LengthSid);
      if ( !CopySid(LengthSid, *((PSID *)v8 + 8), pSid1) )
      {
        LastError = GetLastError();
        UserFromUserSID = LastError;
        if ( LastError > 0 )
          UserFromUserSID = (unsigned __int16)LastError | 0x80070000;
        if ( UserFromUserSID < 0 )
        {
          v10 = 133;
          LOBYTE(v11) = UserFromUserSID;
          goto LABEL_24;
        }
      }
      *((_DWORD *)v8 + 22) = 0;
      *((_QWORD *)v8 + 10) = (char *)v8 + 72;
      *((_QWORD *)v8 + 9) = (char *)v8 + 72;
      *((_DWORD *)v8 + 14) = 0;
      v11 = WdipInitializeCriticalSection();
      UserFromUserSID = v11;
      if ( v11 < 0 )
      {
        v10 = 140;
        goto LABEL_24;
      }
      DpspAddUserToQueuedList((PSLIST_ENTRY)v8);
    }
    LeaveCriticalSection(&g_csUserList);
    v15 = DpspQueueInstanceToUser(v8, a2);
    UserFromUserSID = v15;
    if ( v15 >= 0 )
      return (unsigned int)UserFromUserSID;
    v7 = 736;
    goto LABEL_28;
  }
  v4 = 708;
LABEL_3:
  UserFromUserSID = -2147024809;
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
    (int)L"DpspQueueInstanceToUsers",
    v4,
    (int)L"Error = %d",
    87);
  return (unsigned int)UserFromUserSID;
}

```

## disassembly

```asm
0x180007adc  mov     [rsp+arg_8], rbx
0x180007ae1  mov     [rsp+arg_10], rbp
0x180007ae6  push    rsi
0x180007ae7  push    rdi
0x180007ae8  push    r12
0x180007aea  push    r14
0x180007aec  push    r15
0x180007aee  sub     rsp, 30h
0x180007af2  mov     [rsp+58h+arg_0], 0
0x180007afb  mov     r15, rdx
0x180007afe  mov     r14, rcx
0x180007b01  test    rcx, rcx
0x180007b04  jnz     short loc_180007B2C
0x180007b06  mov     r8d, 2C4h
0x180007b0c  lea     r9, aErrorD; "Error = %d"
0x180007b13  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x180007b1b  mov     ebx, 80070057h
0x180007b20  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007b27  jmp     loc_180007D04
0x180007b2c  test    r15, r15
0x180007b2f  jnz     short loc_180007B39
0x180007b31  mov     r8d, 2C5h
0x180007b37  jmp     short loc_180007B0C
0x180007b39  mov     ecx, 1
0x180007b3e  lea     rdi, aErrorD; "Error = %d"
0x180007b45  xor     eax, eax
0x180007b47  lea     rsi, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007b4e  lock cmpxchg cs:g_fQueuedResolutionsRead, ecx
0x180007b56  jnz     short loc_180007B80
0x180007b58  call    DpspReadQueuedResolutions
0x180007b5d  test    eax, eax
0x180007b5f  jns     short loc_180007B80
0x180007b61  movzx   eax, ax
0x180007b64  lea     rdx, aDpspqueueinsta_1; "DpspQueueInstanceToUsers"
0x180007b6b  mov     r9, rdi; int
0x180007b6e  mov     dword ptr [rsp+58h+Args], eax; Args
0x180007b72  mov     r8d, 2C9h; int
0x180007b78  mov     rcx, rsi; int
0x180007b7b  call    WdipTraceError
0x180007b80  lea     rcx, g_csUserList; lpCriticalSection
0x180007b87  call    cs:__imp_EnterCriticalSection
0x180007b8d  lea     rdx, [rsp+58h+arg_0]; struct __TARGETUSER **
0x180007b92  mov     rcx, r14; pSid1
0x180007b95  call    ?DpspGetUserFromUserSID@@YAJPEAXPEAPEAU__TARGETUSER@@@Z; DpspGetUserFromUserSID(void *,__TARGETUSER * *)
0x180007b9a  mov     ebx, eax
0x180007b9c  test    eax, eax
0x180007b9e  jns     short loc_180007BBF
0x180007ba0  lea     rcx, g_csUserList; lpCriticalSection
0x180007ba7  call    cs:__imp_LeaveCriticalSection
0x180007bad  movzx   ecx, bx
0x180007bb0  mov     r8d, 2D0h
0x180007bb6  mov     dword ptr [rsp+58h+Args], ecx
0x180007bba  jmp     loc_180007CFE
0x180007bbf  mov     rbp, [rsp+58h+arg_0]
0x180007bc4  test    rbp, rbp
0x180007bc7  jnz     loc_180007CD3
0x180007bcd  lea     ebx, [rbp+60h]
0x180007bd0  mov     ecx, ebx
0x180007bd2  call    WdipAlloc
0x180007bd7  mov     rbp, rax
0x180007bda  test    rax, rax
0x180007bdd  jnz     short loc_180007BF2
0x180007bdf  lea     r8d, [rbx+19h]
0x180007be3  mov     ebx, 8007000Eh
0x180007be8  mov     eax, 0Eh
0x180007bed  jmp     loc_180007C95
0x180007bf2  mov     r8, rbx; Size
0x180007bf5  xor     edx, edx; Val
0x180007bf7  mov     rcx, rbp; void *
0x180007bfa  call    memset_0
0x180007bff  mov     rcx, r14; pSid
0x180007c02  call    cs:__imp_GetLengthSid
0x180007c08  mov     ecx, eax
0x180007c0a  mov     ebx, eax
0x180007c0c  call    WdipAlloc
0x180007c11  mov     [rbp+40h], rax
0x180007c15  test    rax, rax
0x180007c18  jnz     short loc_180007C20
0x180007c1a  lea     r8d, [rax+7Eh]
0x180007c1e  jmp     short loc_180007BE3
0x180007c20  mov     r8, rbx; Size
0x180007c23  xor     edx, edx; Val
0x180007c25  mov     rcx, rax; void *
0x180007c28  call    memset_0
0x180007c2d  mov     rdx, [rbp+40h]; pDestinationSid
0x180007c31  mov     r8, r14; pSourceSid
0x180007c34  mov     ecx, ebx; nDestinationSidLength
0x180007c36  call    cs:__imp_CopySid
0x180007c3c  test    eax, eax
0x180007c3e  jnz     short loc_180007C64
0x180007c40  call    cs:__imp_GetLastError
0x180007c46  mov     ebx, eax
0x180007c48  test    eax, eax
0x180007c4a  jle     short loc_180007C55
0x180007c4c  movzx   ebx, ax
0x180007c4f  or      ebx, 80070000h
0x180007c55  test    ebx, ebx
0x180007c57  jns     short loc_180007C64
0x180007c59  mov     r8d, 85h
0x180007c5f  movzx   eax, bx
0x180007c62  jmp     short loc_180007C95
0x180007c64  lea     rax, [rbp+48h]
0x180007c68  mov     dword ptr [rbp+58h], 0
0x180007c6f  lea     rcx, [rbp+10h]
0x180007c73  mov     [rax+8], rax
0x180007c77  mov     [rax], rax
0x180007c7a  mov     dword ptr [rcx+28h], 0
0x180007c81  call    WdipInitializeCriticalSection
0x180007c86  mov     ebx, eax
0x180007c88  test    eax, eax
0x180007c8a  jns     short loc_180007CCB
0x180007c8c  mov     r8d, 8Ch; int
0x180007c92  movzx   eax, ax
0x180007c95  mov     r9, rdi; int
0x180007c98  mov     dword ptr [rsp+58h+Args], eax; Args
0x180007c9c  lea     rdx, aDpspcreatespec_1; "DpspCreateSpecificUser"
0x180007ca3  mov     rcx, rsi; int
0x180007ca6  call    WdipTraceError
0x180007cab  mov     rcx, rbp; struct __TARGETUSER *
0x180007cae  call    ?DpspFreeSpecificUser@@YAJPEAU__TARGETUSER@@@Z; DpspFreeSpecificUser(__TARGETUSER *)
0x180007cb3  lea     rcx, g_csUserList; lpCriticalSection
0x180007cba  call    cs:__imp_LeaveCriticalSection
0x180007cc0  movzx   eax, bx
0x180007cc3  mov     r8d, 2D7h
0x180007cc9  jmp     short loc_180007CFA
0x180007ccb  mov     rcx, rbp; ListEntry
0x180007cce  call    ?DpspAddUserToQueuedList@@YAJPEAU__TARGETUSER@@@Z; DpspAddUserToQueuedList(__TARGETUSER *)
0x180007cd3  lea     rcx, g_csUserList; lpCriticalSection
0x180007cda  call    cs:__imp_LeaveCriticalSection
0x180007ce0  mov     rdx, r15; struct INSTANCEINFO *
0x180007ce3  mov     rcx, rbp; struct __TARGETUSER *
0x180007ce6  call    ?DpspQueueInstanceToUser@@YAJPEAU__TARGETUSER@@PEAUINSTANCEINFO@@@Z; DpspQueueInstanceToUser(__TARGETUSER *,INSTANCEINFO *)
0x180007ceb  mov     ebx, eax
0x180007ced  test    eax, eax
0x180007cef  jns     short loc_180007D10
0x180007cf1  movzx   eax, ax
0x180007cf4  mov     r8d, 2E0h; int
0x180007cfa  mov     dword ptr [rsp+58h+Args], eax; Args
0x180007cfe  mov     r9, rdi; int
0x180007d01  mov     rcx, rsi; int
0x180007d04  lea     rdx, aDpspqueueinsta_1; "DpspQueueInstanceToUsers"
0x180007d0b  call    WdipTraceError
0x180007d10  mov     rbp, [rsp+58h+arg_10]
0x180007d15  mov     eax, ebx
0x180007d17  mov     rbx, [rsp+58h+arg_8]
0x180007d1c  add     rsp, 30h
0x180007d20  pop     r15
0x180007d22  pop     r14
0x180007d24  pop     r12
0x180007d26  pop     rdi
0x180007d27  pop     rsi
0x180007d28  retn
```
