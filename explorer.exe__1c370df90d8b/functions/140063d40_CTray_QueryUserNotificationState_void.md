# CTray::QueryUserNotificationState(void)

- ea: `0x140063d40`
- end: `0x140063eaf`
- name: `?QueryUserNotificationState@CTray@@QEAA_JXZ`
- size: `367`
- prototype: `__int64 __fastcall(CTray *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14001d860`
- `0x14001e8f0`
- `0x14011c600`

## callees

- `0x140063d40`
- `0x140063eb8`
- `0x1401057ff`
- `0x140105817`
- `0x14010586b`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140063dd2`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140063e07`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140063dd2`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140063e07`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140063d94`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140063d94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140063da2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140063da2`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140063d61`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x140063d61`

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
0x140063d40  push    rbx
0x140063d42  push    rbp
0x140063d43  push    rsi
0x140063d44  push    rdi
0x140063d45  sub     rsp, 28h
0x140063d49  xor     edx, edx; uiParam
0x140063d4b  mov     [rsp+48h+pvParam], 0
0x140063d53  mov     rdi, rcx
0x140063d56  lea     r8, [rsp+48h+pvParam]; pvParam
0x140063d5b  xor     r9d, r9d; fWinIni
0x140063d5e  lea     ecx, [rdx+72h]; uiAction
0x140063d61  call    cs:__imp_SystemParametersInfoW
0x140063d67  test    eax, eax
0x140063d69  jnz     short loc_140063DB9
0x140063d6b  cmp     dword ptr [rdi+1D8h], 0
0x140063d72  jnz     short loc_140063DC0
0x140063d74  mov     eax, [rdi+1ECh]
0x140063d7a  sub     eax, 2
0x140063d7d  test    eax, 0FFFFFFFDh
0x140063d82  jz      short loc_140063DC0
0x140063d84  mov     ebp, 100000h
0x140063d89  lea     r8, aA19652103a9d4b; "{A1965210-3A9D-4bca-822B-433645B3F5A2}"
0x140063d90  mov     ecx, ebp; dwDesiredAccess
0x140063d92  xor     edx, edx; bInheritHandle
0x140063d94  call    cs:__imp_OpenEventW
0x140063d9a  test    rax, rax
0x140063d9d  jz      short loc_140063DC7
0x140063d9f  mov     rcx, rax; hObject
0x140063da2  call    cs:__imp_CloseHandle
0x140063da8  mov     ebx, 4
0x140063dad  mov     rax, rbx
0x140063db0  add     rsp, 28h
0x140063db4  pop     rdi
0x140063db5  pop     rsi
0x140063db6  pop     rbp
0x140063db7  pop     rbx
0x140063db8  retn
0x140063db9  cmp     [rsp+48h+pvParam], 0
0x140063dbe  jz      short loc_140063D6B
0x140063dc0  mov     ebx, 1
0x140063dc5  jmp     short loc_140063DAD
0x140063dc7  lea     r8, aLocalDdrawchec; "Local\\__DDrawCheckExclMode__"
0x140063dce  xor     edx, edx; bInheritHandle
0x140063dd0  mov     ecx, ebp; dwDesiredAccess
0x140063dd2  call    cs:__imp_OpenMutexW
0x140063dd8  mov     rsi, rax
0x140063ddb  test    rax, rax
0x140063dde  jz      short loc_140063E4E
0x140063de0  mov     edx, 1Eh; dwMilliseconds
0x140063de5  mov     rcx, rax; hHandle
0x140063de8  call    WaitForSingleObject_0
0x140063ded  test    eax, eax
0x140063def  jz      short loc_140063DFA
0x140063df1  xor     ebx, ebx
0x140063df3  cmp     eax, 80h
0x140063df8  jnz     short loc_140063E42
0x140063dfa  lea     r8, aLocalDdrawexcl; "Local\\__DDrawExclMode__"
0x140063e01  xor     edx, edx; bInheritHandle
0x140063e03  mov     ecx, ebp; dwDesiredAccess
0x140063e05  xor     ebx, ebx
0x140063e07  call    cs:__imp_OpenMutexW
0x140063e0d  mov     rbp, rax
0x140063e10  test    rax, rax
0x140063e13  jz      short loc_140063E3A
0x140063e15  xor     edx, edx; dwMilliseconds
0x140063e17  mov     rcx, rax; hHandle
0x140063e1a  call    WaitForSingleObject_0
0x140063e1f  test    eax, eax
0x140063e21  jz      short loc_140063E2A
0x140063e23  cmp     eax, 80h
0x140063e28  jnz     short loc_140063E83
0x140063e2a  mov     rcx, rbp; hMutex
0x140063e2d  call    ReleaseMutex_0
0x140063e32  mov     rcx, rbp; hObject
0x140063e35  call    WINRT_IMPL_CloseHandle
0x140063e3a  mov     rcx, rsi; hMutex
0x140063e3d  call    ReleaseMutex_0
0x140063e42  mov     rcx, rsi; hObject
0x140063e45  call    WINRT_IMPL_CloseHandle
0x140063e4a  test    ebx, ebx
0x140063e4c  jnz     short loc_140063E9B
0x140063e4e  call    ?IsQuietPeriodActive@CTray@@CA_NXZ; CTray::IsQuietPeriodActive(void)
0x140063e53  test    al, al
0x140063e55  jnz     short loc_140063EA5
0x140063e57  cmp     [rdi+1E0h], al
0x140063e5d  jnz     short loc_140063E91
0x140063e5f  cmp     [rdi+1E1h], al
0x140063e65  jnz     short loc_140063E91
0x140063e67  cmp     dword ptr [rdi+0C8h], 0
0x140063e6e  mov     ebx, 5
0x140063e73  jz      loc_140063DAD
0x140063e79  mov     ebx, 2
0x140063e7e  jmp     loc_140063DAD
0x140063e83  cmp     eax, 102h
0x140063e88  jnz     short loc_140063E32
0x140063e8a  mov     ebx, 1
0x140063e8f  jmp     short loc_140063E32
0x140063e91  mov     ebx, 7
0x140063e96  jmp     loc_140063DAD
0x140063e9b  mov     ebx, 3
0x140063ea0  jmp     loc_140063DAD
0x140063ea5  mov     ebx, 6
0x140063eaa  jmp     loc_140063DAD
```
