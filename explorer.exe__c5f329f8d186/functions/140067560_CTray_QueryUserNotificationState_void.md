# CTray::QueryUserNotificationState(void)

- ea: `0x140067560`
- end: `0x1400676ee`
- name: `?QueryUserNotificationState@CTray@@QEAA_JXZ`
- size: `398`
- prototype: `__int64 __fastcall(CTray *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140019eb0`
- `0x14001aff0`
- `0x1401277d0`

## callees

- `0x140067560`
- `0x1400676f4`
- `0x14010f85b`
- `0x14010f873`
- `0x14010f8c7`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140067605`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140067640`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140067605`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140067640`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1400675ba`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1400675ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400675ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400675ce`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140067581`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140067581`

## pseudocode

```c
__int64 __fastcall CTray::QueryUserNotificationState(CTray *this)
{
  HANDLE v2; // rax
  __int64 v3; // rbx
  HANDLE v5; // rax
  void *v6; // rsi
  DWORD v7; // eax
  BOOL v8; // ebx
  HANDLE v9; // rax
  void *v10; // rbp
  DWORD v11; // eax
  int pvParam; // [rsp+58h] [rbp+10h] BYREF

  pvParam = 0;
  if ( SystemParametersInfoW(0x72u, 0, &pvParam, 0) && pvParam
    || *((_DWORD *)this + 118)
    || ((*((_DWORD *)this + 123) - 2) & 0xFFFFFFFD) == 0 )
  {
    return 1;
  }
  v2 = OpenEventW(0x100000u, 0, L"{A1965210-3A9D-4bca-822B-433645B3F5A2}");
  if ( v2 )
  {
    CloseHandle(v2);
    return 4;
  }
  else
  {
    v5 = OpenMutexW(0x100000u, 0, L"Local\\__DDrawCheckExclMode__");
    v6 = v5;
    if ( !v5 )
      goto LABEL_30;
    v7 = WaitForSingleObject_0(v5, 0x1Eu);
    if ( !v7 || (v8 = 0, v7 == 128) )
    {
      v8 = 0;
      v9 = OpenMutexW(0x100000u, 0, L"Local\\__DDrawExclMode__");
      v10 = v9;
      if ( v9 )
      {
        v11 = WaitForSingleObject_0(v9, 0);
        if ( v11 && v11 != 128 )
          v8 = v11 == 258;
        else
          ReleaseMutex_0(v10);
        WINRT_IMPL_CloseHandle(v10);
      }
      ReleaseMutex_0(v6);
    }
    WINRT_IMPL_CloseHandle(v6);
    if ( v8 )
    {
      return 3;
    }
    else
    {
LABEL_30:
      if ( CTray::IsQuietPeriodActive() )
      {
        return 6;
      }
      else if ( *((_BYTE *)this + 480) || *((_BYTE *)this + 481) )
      {
        return 7;
      }
      else
      {
        v3 = 5;
        if ( *((_DWORD *)this + 50) )
          return 2;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140067560  push    rbx
0x140067562  push    rbp
0x140067563  push    rsi
0x140067564  push    rdi
0x140067565  sub     rsp, 28h
0x140067569  xor     edx, edx; uiParam
0x14006756b  mov     [rsp+48h+pvParam], 0
0x140067573  mov     rdi, rcx
0x140067576  lea     r8, [rsp+48h+pvParam]; pvParam
0x14006757b  xor     r9d, r9d; fWinIni
0x14006757e  lea     ecx, [rdx+72h]; uiAction
0x140067581  call    cs:__imp_SystemParametersInfoW
0x140067588  nop     dword ptr [rax+rax+00h]
0x14006758d  test    eax, eax
0x14006758f  jnz     short loc_1400675EC
0x140067591  cmp     dword ptr [rdi+1D8h], 0
0x140067598  jnz     short loc_1400675F3
0x14006759a  mov     eax, [rdi+1ECh]
0x1400675a0  sub     eax, 2
0x1400675a3  test    eax, 0FFFFFFFDh
0x1400675a8  jz      short loc_1400675F3
0x1400675aa  mov     ebp, 100000h
0x1400675af  lea     r8, aA19652103a9d4b; "{A1965210-3A9D-4bca-822B-433645B3F5A2}"
0x1400675b6  mov     ecx, ebp; dwDesiredAccess
0x1400675b8  xor     edx, edx; bInheritHandle
0x1400675ba  call    cs:__imp_OpenEventW
0x1400675c1  nop     dword ptr [rax+rax+00h]
0x1400675c6  test    rax, rax
0x1400675c9  jz      short loc_1400675FA
0x1400675cb  mov     rcx, rax; hObject
0x1400675ce  call    cs:__imp_CloseHandle
0x1400675d5  nop     dword ptr [rax+rax+00h]
0x1400675da  mov     ebx, 4
0x1400675df  mov     rax, rbx
0x1400675e2  add     rsp, 28h
0x1400675e6  pop     rdi
0x1400675e7  pop     rsi
0x1400675e8  pop     rbp
0x1400675e9  pop     rbx
0x1400675ea  retn
0x1400675ec  cmp     [rsp+48h+pvParam], 0
0x1400675f1  jz      short loc_140067591
0x1400675f3  mov     ebx, 1
0x1400675f8  jmp     short loc_1400675DF
0x1400675fa  lea     r8, aLocalDdrawchec; "Local\\__DDrawCheckExclMode__"
0x140067601  xor     edx, edx; bInheritHandle
0x140067603  mov     ecx, ebp; dwDesiredAccess
0x140067605  call    cs:__imp_OpenMutexW
0x14006760c  nop     dword ptr [rax+rax+00h]
0x140067611  mov     rsi, rax
0x140067614  test    rax, rax
0x140067617  jz      short loc_14006768D
0x140067619  mov     edx, 1Eh; dwMilliseconds
0x14006761e  mov     rcx, rax; hHandle
0x140067621  call    WaitForSingleObject_0
0x140067626  test    eax, eax
0x140067628  jz      short loc_140067633
0x14006762a  xor     ebx, ebx
0x14006762c  cmp     eax, 80h
0x140067631  jnz     short loc_140067681
0x140067633  lea     r8, aLocalDdrawexcl; "Local\\__DDrawExclMode__"
0x14006763a  xor     edx, edx; bInheritHandle
0x14006763c  mov     ecx, ebp; dwDesiredAccess
0x14006763e  xor     ebx, ebx
0x140067640  call    cs:__imp_OpenMutexW
0x140067647  nop     dword ptr [rax+rax+00h]
0x14006764c  mov     rbp, rax
0x14006764f  test    rax, rax
0x140067652  jz      short loc_140067679
0x140067654  xor     edx, edx; dwMilliseconds
0x140067656  mov     rcx, rax; hHandle
0x140067659  call    WaitForSingleObject_0
0x14006765e  test    eax, eax
0x140067660  jz      short loc_140067669
0x140067662  cmp     eax, 80h
0x140067667  jnz     short loc_1400676C2
0x140067669  mov     rcx, rbp; hMutex
0x14006766c  call    ReleaseMutex_0
0x140067671  mov     rcx, rbp; hObject
0x140067674  call    WINRT_IMPL_CloseHandle
0x140067679  mov     rcx, rsi; hMutex
0x14006767c  call    ReleaseMutex_0
0x140067681  mov     rcx, rsi; hObject
0x140067684  call    WINRT_IMPL_CloseHandle
0x140067689  test    ebx, ebx
0x14006768b  jnz     short loc_1400676DA
0x14006768d  call    ?IsQuietPeriodActive@CTray@@CA_NXZ; CTray::IsQuietPeriodActive(void)
0x140067692  test    al, al
0x140067694  jnz     short loc_1400676E4
0x140067696  cmp     [rdi+1E0h], al
0x14006769c  jnz     short loc_1400676D0
0x14006769e  cmp     [rdi+1E1h], al
0x1400676a4  jnz     short loc_1400676D0
0x1400676a6  cmp     dword ptr [rdi+0C8h], 0
0x1400676ad  mov     ebx, 5
0x1400676b2  jz      loc_1400675DF
0x1400676b8  mov     ebx, 2
0x1400676bd  jmp     loc_1400675DF
0x1400676c2  cmp     eax, 102h
0x1400676c7  jnz     short loc_140067671
0x1400676c9  mov     ebx, 1
0x1400676ce  jmp     short loc_140067671
0x1400676d0  mov     ebx, 7
0x1400676d5  jmp     loc_1400675DF
0x1400676da  mov     ebx, 3
0x1400676df  jmp     loc_1400675DF
0x1400676e4  mov     ebx, 6
0x1400676e9  jmp     loc_1400675DF
```
