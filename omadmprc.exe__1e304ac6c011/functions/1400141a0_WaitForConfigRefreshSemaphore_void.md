# WaitForConfigRefreshSemaphore(void *)

- ea: `0x1400141a0`
- end: `0x1400142a1`
- name: `?WaitForConfigRefreshSemaphore@@YAXPEAX@Z`
- size: `257`
- prototype: `void __fastcall(HANDLE hObject)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400128d4`
- `0x140013ae0`

## callees

- `0x14000cd7c`
- `0x1400141a0`
- `0x140015690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400141fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400141fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400141ed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400141ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001425c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001425c`
- `omadmapi!__imp_?AcquireConfigRefreshMutex@@YAJPEAPEAXPEBG@Z` at `0x1400141dc`
- `omadmapi!__imp_?AcquireConfigRefreshMutex@@YAJPEAPEAXPEBG@Z` at `0x1400141dc`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x140014272`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x140014272`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WaitForConfigRefreshSemaphore(HANDLE hObject)
{
  signed int LastError; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  signed int v5; // [rsp+30h] [rbp-50h] BYREF
  void *v6; // [rsp+38h] [rbp-48h] BYREF
  char v7[16]; // [rsp+40h] [rbp-40h] BYREF
  const wchar_t *v8; // [rsp+50h] [rbp-30h]
  __int64 v9; // [rsp+58h] [rbp-28h]
  signed int *v10; // [rsp+60h] [rbp-20h]
  __int64 v11; // [rsp+68h] [rbp-18h]

  v6 = 0;
  AcquireConfigRefreshMutex(&v6, L"OmaDmPrc");
  if ( WaitForSingleObject(hObject, 0) == -1 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( (byte_1400242C1 & 2) != 0 )
    {
      v5 = LastError;
      v8 = L"OmaDmPrc";
      v9 = 18;
      v10 = &v5;
      v11 = 4;
      McGenEventWrite_EventWriteTransfer(v3, WaitForConfigRefreshSemaphoreFailure, v4, 3, v7);
    }
  }
  CloseHandle(hObject);
  if ( v6 )
    ReleaseConfigRefreshMutex(v6);
}

```

## disassembly

```asm
0x1400141a0  mov     [rsp-8+arg_8], rbx
0x1400141a5  mov     [rsp-8+arg_10], rsi
0x1400141aa  push    rbp
0x1400141ab  mov     rbp, rsp
0x1400141ae  sub     rsp, 80h
0x1400141b5  mov     rax, cs:__security_cookie
0x1400141bc  xor     rax, rsp
0x1400141bf  mov     [rbp+var_10], rax
0x1400141c3  mov     rbx, rcx
0x1400141c6  mov     [rbp+var_48], 0
0x1400141ce  lea     rsi, aOmadmprc; "OmaDmPrc"
0x1400141d5  mov     rdx, rsi
0x1400141d8  lea     rcx, [rbp+var_48]
0x1400141dc  call    cs:__imp_?AcquireConfigRefreshMutex@@YAJPEAPEAXPEBG@Z; AcquireConfigRefreshMutex(void * *,ushort const *)
0x1400141e3  nop     dword ptr [rax+rax+00h]
0x1400141e8  xor     edx, edx; dwMilliseconds
0x1400141ea  mov     rcx, rbx; hHandle
0x1400141ed  call    cs:__imp_WaitForSingleObject
0x1400141f4  nop     dword ptr [rax+rax+00h]
0x1400141f9  cmp     eax, 0FFFFFFFFh
0x1400141fc  jnz     short loc_140014259
0x1400141fe  call    cs:__imp_GetLastError
0x140014205  nop     dword ptr [rax+rax+00h]
0x14001420a  test    eax, eax
0x14001420c  jle     short loc_140014216
0x14001420e  movzx   eax, ax
0x140014211  or      eax, 80070000h
0x140014216  test    cs:byte_1400242C1, 2
0x14001421d  jz      short loc_140014259
0x14001421f  mov     [rbp+var_50], eax
0x140014222  mov     [rbp+var_30], rsi
0x140014226  mov     [rbp+var_28], 12h
0x14001422e  lea     rax, [rbp+var_50]
0x140014232  mov     [rbp+var_20], rax
0x140014236  mov     [rbp+var_18], 4
0x14001423e  lea     rax, [rbp+var_40]
0x140014242  mov     [rsp+80h+var_60], rax
0x140014247  mov     r9d, 3
0x14001424d  lea     rdx, WaitForConfigRefreshSemaphoreFailure
0x140014254  call    McGenEventWrite_EventWriteTransfer
0x140014259  mov     rcx, rbx; hObject
0x14001425c  call    cs:__imp_CloseHandle
0x140014263  nop     dword ptr [rax+rax+00h]
0x140014268  nop
0x140014269  mov     rcx, [rbp+var_48]
0x14001426d  test    rcx, rcx
0x140014270  jz      short loc_14001427F
0x140014272  call    cs:__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z; ReleaseConfigRefreshMutex(void *)
0x140014279  nop     dword ptr [rax+rax+00h]
0x14001427e  nop
0x14001427f  mov     rcx, [rbp+var_10]
0x140014283  xor     rcx, rsp; StackCookie
0x140014286  call    __security_check_cookie
0x14001428b  lea     r11, [rsp+80h+var_s0]
0x140014293  mov     rbx, [r11+18h]
0x140014297  mov     rsi, [r11+20h]
0x14001429b  mov     rsp, r11
0x14001429e  pop     rbp
0x14001429f  retn
```
