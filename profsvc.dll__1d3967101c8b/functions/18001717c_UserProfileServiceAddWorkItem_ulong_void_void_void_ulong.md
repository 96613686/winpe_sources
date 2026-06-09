# UserProfileServiceAddWorkItem(ulong (*)(void *),void *,void *,ulong)

- ea: `0x18001717c`
- end: `0x18001727b`
- name: `?UserProfileServiceAddWorkItem@@YAJP6AKPEAX@Z00K@Z`
- size: `255`
- prototype: `__int64 __fastcall(unsigned int (*)(void *), void *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180018370`

## callees

- `0x18001717c`
- `0x180017284`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800171ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800171ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001719e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001719e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001726e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001726e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001723d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001723d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017255`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180017233`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180017233`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800171ef`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800171ef`

## pseudocode

```c
__int64 __fastcall UserProfileServiceAddWorkItem(unsigned int (*a1)(void *), void *a2, void *a3)
{
  LPCRITICAL_SECTION v3; // rbp
  HANDLE ProcessHeap; // rax
  void **v8; // rax
  void **v9; // rdi
  signed int v10; // ebx
  void **phNewToken; // rax
  signed int LastError; // eax
  signed int v14; // eax

  v3 = g_pUPSvc;
  if ( !g_pUPSvc )
    return 2147500037LL;
  ProcessHeap = GetProcessHeap();
  v8 = (void **)HeapAlloc(ProcessHeap, 0, 0x20u);
  v9 = v8;
  if ( v8 )
  {
    v8[1] = a2;
    v10 = 0;
    *((_DWORD *)v8 + 6) = 16;
    *v8 = a1;
    phNewToken = v8 + 2;
    *phNewToken = 0;
    if ( !a3 || DuplicateTokenEx(a3, 0xCu, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
      goto LABEL_19;
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
    {
LABEL_19:
      if ( TrySubmitThreadpoolCallback(
             (PTP_SIMPLE_CALLBACK)_WorkItemWrapper,
             v9,
             (PTP_CALLBACK_ENVIRON)&v3[1].LockSemaphore) )
      {
        v9 = 0;
      }
      else
      {
        v14 = GetLastError();
        v10 = v14;
        if ( v14 > 0 )
          v10 = (unsigned __int16)v14 | 0x80070000;
      }
    }
    _DestroyWorkItemInfo((struct WorkItemInfo *)v9);
  }
  else
  {
    SetLastError(8u);
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001717c  push    rbx
0x18001717e  push    rbp
0x18001717f  push    rsi
0x180017180  push    rdi
0x180017181  push    r14
0x180017183  push    r15
0x180017185  sub     rsp, 38h
0x180017189  mov     rbp, cs:?g_pUPSvc@@3PEAVCUserProfileService@@EA; CUserProfileService * g_pUPSvc
0x180017190  mov     rsi, r8
0x180017193  mov     r14, rdx
0x180017196  mov     r15, rcx
0x180017199  test    rbp, rbp
0x18001719c  jz      short loc_180017207
0x18001719e  call    cs:__imp_GetProcessHeap
0x1800171a4  xor     edx, edx; dwFlags
0x1800171a6  mov     rcx, rax; hHeap
0x1800171a9  lea     r8d, [rdx+20h]; dwBytes
0x1800171ad  call    cs:__imp_HeapAlloc
0x1800171b3  mov     rdi, rax
0x1800171b6  test    rax, rax
0x1800171b9  jz      loc_180017269
0x1800171bf  mov     [rax+8], r14
0x1800171c3  xor     ebx, ebx
0x1800171c5  mov     dword ptr [rax+18h], 10h
0x1800171cc  mov     r14d, 80070000h
0x1800171d2  mov     [rax], r15
0x1800171d5  add     rax, 10h
0x1800171d9  mov     [rax], rbx
0x1800171dc  test    rsi, rsi
0x1800171df  jnz     short loc_180017219
0x1800171e1  lea     r8, [rbp+40h]; pcbe
0x1800171e5  mov     rdx, rdi; pv
0x1800171e8  lea     rcx, ?_WorkItemWrapper@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x1800171ef  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800171f5  test    eax, eax
0x1800171f7  jz      short loc_180017255
0x1800171f9  xor     edi, edi
0x1800171fb  mov     rcx, rdi; lpMem
0x1800171fe  call    ?_DestroyWorkItemInfo@@YAXPEAUWorkItemInfo@@@Z; _DestroyWorkItemInfo(WorkItemInfo *)
0x180017203  mov     eax, ebx
0x180017205  jmp     short loc_18001720C
0x180017207  mov     eax, 80004005h
0x18001720c  add     rsp, 38h
0x180017210  pop     r15
0x180017212  pop     r14
0x180017214  pop     rdi
0x180017215  pop     rsi
0x180017216  pop     rbp
0x180017217  pop     rbx
0x180017218  retn
0x180017219  mov     r9d, 2; ImpersonationLevel
0x18001721f  mov     [rsp+68h+phNewToken], rax; phNewToken
0x180017224  xor     r8d, r8d; lpTokenAttributes
0x180017227  mov     [rsp+68h+TokenType], r9d; TokenType
0x18001722c  mov     rcx, rsi; hExistingToken
0x18001722f  lea     edx, [r9+0Ah]; dwDesiredAccess
0x180017233  call    cs:__imp_DuplicateTokenEx
0x180017239  test    eax, eax
0x18001723b  jnz     short loc_1800171E1
0x18001723d  call    cs:__imp_GetLastError
0x180017243  mov     ebx, eax
0x180017245  test    eax, eax
0x180017247  jle     short loc_18001724F
0x180017249  movzx   ebx, ax
0x18001724c  or      ebx, r14d
0x18001724f  test    ebx, ebx
0x180017251  js      short loc_1800171FB
0x180017253  jmp     short loc_1800171E1
0x180017255  call    cs:__imp_GetLastError
0x18001725b  mov     ebx, eax
0x18001725d  test    eax, eax
0x18001725f  jle     short loc_1800171FB
0x180017261  movzx   ebx, ax
0x180017264  or      ebx, r14d
0x180017267  jmp     short loc_1800171FB
0x180017269  mov     ecx, 8; dwErrCode
0x18001726e  call    cs:__imp_SetLastError
0x180017274  mov     ebx, 8007000Eh
0x180017279  jmp     short loc_180017203
```
