# SignalConfigRefreshSemaphore(void * *)

- ea: `0x140012604`
- end: `0x1400127be`
- name: `?SignalConfigRefreshSemaphore@@YAJPEAPEAX@Z`
- size: `442`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400128d4`
- `0x140013ae0`

## callees

- `0x14000cd7c`
- `0x140012604`
- `0x140015690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001270a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001270a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140012663`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140012663`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400126f9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400126f9`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x140012640`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x140012640`
- `omadmapi!__imp_?AcquireConfigRefreshMutex@@YAJPEAPEAXPEBG@Z` at `0x1400126de`
- `omadmapi!__imp_?AcquireConfigRefreshMutex@@YAJPEAPEAXPEBG@Z` at `0x1400126de`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001276f`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x140012787`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001276f`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x140012787`

## string_xrefs

- `0x14001262d`: `__CONFIGREFRESH_NAMED_SEMAPHORE__`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SignalConfigRefreshSemaphore(void **a1)
{
  HANDLE SemaphoreW; // rax
  void *v3; // rdi
  signed int LastError; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  int refreshed; // ebx
  signed int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  signed int v12; // [rsp+30h] [rbp-50h] BYREF
  void *v13; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v14[16]; // [rsp+40h] [rbp-40h] BYREF
  const wchar_t *v15; // [rsp+50h] [rbp-30h]
  __int64 v16; // [rsp+58h] [rbp-28h]
  signed int *v17; // [rsp+60h] [rbp-20h]
  __int64 v18; // [rsp+68h] [rbp-18h]

  SemaphoreW = CreateSemaphoreW(0, 0, 1, L"__CONFIGREFRESH_NAMED_SEMAPHORE__");
  v3 = SemaphoreW;
  if ( SemaphoreW && !ReleaseSemaphore(SemaphoreW, 1, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( (byte_1400242C1 & 2) != 0 )
    {
      v12 = LastError;
      v15 = L"OmaDmPrc";
      v16 = 18;
      v17 = &v12;
      v18 = 4;
      McGenEventWrite_EventWriteTransfer(v5, ReleaseConfigRefreshSemaphoreFailure, v6, 3, v14);
    }
  }
  v13 = 0;
  refreshed = AcquireConfigRefreshMutex(&v13, L"OmaDmPrc");
  if ( refreshed >= 0 )
  {
    if ( v13 )
      ReleaseConfigRefreshMutex(v13);
    *a1 = v3;
  }
  else
  {
    if ( WaitForSingleObject(v3, 0) == -1 )
    {
      v8 = GetLastError();
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      if ( (byte_1400242C1 & 2) != 0 )
      {
        v12 = v8;
        v15 = L"OmaDmPrc";
        v16 = 18;
        v17 = &v12;
        v18 = 4;
        McGenEventWrite_EventWriteTransfer(v9, WaitForConfigRefreshSemaphoreFailure, v10, 3, v14);
      }
    }
    if ( v13 )
      ReleaseConfigRefreshMutex(v13);
  }
  return (unsigned int)refreshed;
}

```

## disassembly

```asm
0x140012604  mov     [rsp-18h+arg_8], rbx
0x140012609  mov     [rsp-18h+arg_10], rsi
0x14001260e  push    rbp
0x14001260f  push    rdi
0x140012610  push    r15
0x140012612  mov     rbp, rsp
0x140012615  sub     rsp, 80h
0x14001261c  mov     rax, cs:__security_cookie
0x140012623  xor     rax, rsp
0x140012626  mov     [rbp+var_10], rax
0x14001262a  mov     rsi, rcx
0x14001262d  lea     r9, Name; "__CONFIGREFRESH_NAMED_SEMAPHORE__"
0x140012634  mov     ebx, 1
0x140012639  mov     r8d, ebx; lMaximumCount
0x14001263c  xor     edx, edx; lInitialCount
0x14001263e  xor     ecx, ecx; lpSemaphoreAttributes
0x140012640  call    cs:__imp_CreateSemaphoreW
0x140012647  nop     dword ptr [rax+rax+00h]
0x14001264c  mov     rdi, rax
0x14001264f  lea     r15, aOmadmprc; "OmaDmPrc"
0x140012656  test    rax, rax
0x140012659  jz      short loc_1400126CF
0x14001265b  xor     r8d, r8d; lpPreviousCount
0x14001265e  mov     edx, ebx; lReleaseCount
0x140012660  mov     rcx, rax; hSemaphore
0x140012663  call    cs:__imp_ReleaseSemaphore
0x14001266a  nop     dword ptr [rax+rax+00h]
0x14001266f  test    eax, eax
0x140012671  jnz     short loc_1400126CF
0x140012673  call    cs:__imp_GetLastError
0x14001267a  nop     dword ptr [rax+rax+00h]
0x14001267f  test    eax, eax
0x140012681  jle     short loc_14001268B
0x140012683  movzx   eax, ax
0x140012686  or      eax, 80070000h
0x14001268b  test    cs:byte_1400242C1, 2
0x140012692  jz      short loc_1400126CF
0x140012694  mov     [rbp+var_50], eax
0x140012697  mov     [rbp+var_30], r15
0x14001269b  mov     [rbp+var_28], 12h
0x1400126a3  lea     rax, [rbp+var_50]
0x1400126a7  mov     [rbp+var_20], rax
0x1400126ab  mov     [rbp+var_18], 4
0x1400126b3  lea     rax, [rbp+var_40]
0x1400126b7  mov     [rsp+80h+var_60], rax
0x1400126bc  mov     r9d, 3
0x1400126c2  lea     rdx, ReleaseConfigRefreshSemaphoreFailure
0x1400126c9  call    McGenEventWrite_EventWriteTransfer
0x1400126ce  nop
0x1400126cf  mov     [rbp+var_48], 0
0x1400126d7  mov     rdx, r15
0x1400126da  lea     rcx, [rbp+var_48]
0x1400126de  call    cs:__imp_?AcquireConfigRefreshMutex@@YAJPEAPEAXPEBG@Z; AcquireConfigRefreshMutex(void * *,ushort const *)
0x1400126e5  nop     dword ptr [rax+rax+00h]
0x1400126ea  mov     ebx, eax
0x1400126ec  test    eax, eax
0x1400126ee  jns     loc_14001277E
0x1400126f4  xor     edx, edx; dwMilliseconds
0x1400126f6  mov     rcx, rdi; hHandle
0x1400126f9  call    cs:__imp_WaitForSingleObject
0x140012700  nop     dword ptr [rax+rax+00h]
0x140012705  cmp     eax, 0FFFFFFFFh
0x140012708  jnz     short loc_140012766
0x14001270a  call    cs:__imp_GetLastError
0x140012711  nop     dword ptr [rax+rax+00h]
0x140012716  test    eax, eax
0x140012718  jle     short loc_140012722
0x14001271a  movzx   eax, ax
0x14001271d  or      eax, 80070000h
0x140012722  test    cs:byte_1400242C1, 2
0x140012729  jz      short loc_140012766
0x14001272b  mov     [rbp+var_50], eax
0x14001272e  mov     [rbp+var_30], r15
0x140012732  mov     [rbp+var_28], 12h
0x14001273a  lea     rax, [rbp+var_50]
0x14001273e  mov     [rbp+var_20], rax
0x140012742  mov     [rbp+var_18], 4
0x14001274a  lea     rax, [rbp+var_40]
0x14001274e  mov     [rsp+80h+var_60], rax
0x140012753  mov     r9d, 3
0x140012759  lea     rdx, WaitForConfigRefreshSemaphoreFailure
0x140012760  call    McGenEventWrite_EventWriteTransfer
0x140012765  nop
0x140012766  mov     rcx, [rbp+var_48]
0x14001276a  test    rcx, rcx
0x14001276d  jz      short loc_140012797
0x14001276f  call    cs:__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z; ReleaseConfigRefreshMutex(void *)
0x140012776  nop     dword ptr [rax+rax+00h]
0x14001277b  nop
0x14001277c  jmp     short loc_140012797
0x14001277e  mov     rcx, [rbp+var_48]
0x140012782  test    rcx, rcx
0x140012785  jz      short loc_140012794
0x140012787  call    cs:__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z; ReleaseConfigRefreshMutex(void *)
0x14001278e  nop     dword ptr [rax+rax+00h]
0x140012793  nop
0x140012794  mov     [rsi], rdi
0x140012797  mov     eax, ebx
0x140012799  mov     rcx, [rbp+var_10]
0x14001279d  xor     rcx, rsp; StackCookie
0x1400127a0  call    __security_check_cookie
0x1400127a5  lea     r11, [rsp+80h+var_s0]
0x1400127ad  mov     rbx, [r11+28h]
0x1400127b1  mov     rsi, [r11+30h]
0x1400127b5  mov     rsp, r11
0x1400127b8  pop     r15
0x1400127ba  pop     rdi
0x1400127bb  pop     rbp
0x1400127bc  retn
```
