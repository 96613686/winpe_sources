# SHGetLogonID

- ea: `0x1800719b4`
- end: `0x180071ac0`
- name: `SHGetLogonID`
- size: `268`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180063870`

## callees

- `0x1800718e8`
- `0x1800719b4`
- `0x180071ac8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071a7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071a7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071a25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071a8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071a25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071a8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071a9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071a9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071aa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071aa8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800719da`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800719da`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180071a6c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180071a6c`

## pseudocode

```c
__int64 __fastcall SHGetLogonID(LPWSTR *StringSid)
{
  __int64 v2; // rcx
  int TokenInformation_Heap; // ebx
  HANDLE v5; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v7; // r8
  void *v8; // rdi
  unsigned int i; // eax
  signed int LastError; // eax
  HANDLE v11; // rax
  HANDLE hObject; // [rsp+38h] [rbp+10h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp+18h] BYREF

  InitOnceExecuteOnce(&stru_180299FB8, InitOnceDeviceFamily, 0, 0);
  if ( byte_180298C9C )
    return 2147500033LL;
  *StringSid = 0;
  hObject = 0;
  TokenInformation_Heap = SHOpenEffectiveToken(v2, &hObject);
  if ( TokenInformation_Heap >= 0 )
  {
    v5 = hObject;
    lpMem = 0;
    ProcessHeap = GetProcessHeap();
    TokenInformation_Heap = GetTokenInformation_HeapFree<_TOKEN_GROUPS>(ProcessHeap, v5, v7, &lpMem);
    if ( TokenInformation_Heap >= 0 )
    {
      v8 = lpMem;
      TokenInformation_Heap = -2147467259;
      for ( i = 0; i < *(_DWORD *)lpMem; ++i )
      {
        if ( (*((_DWORD *)lpMem + 4 * i + 4) & 0xC0000000) != 0 )
        {
          if ( ConvertSidToStringSidW(*((PSID *)lpMem + 2 * i + 1), StringSid) )
          {
            TokenInformation_Heap = 0;
          }
          else
          {
            LastError = GetLastError();
            TokenInformation_Heap = LastError;
            if ( LastError > 0 )
              TokenInformation_Heap = (unsigned __int16)LastError | 0x80070000;
          }
          break;
        }
      }
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v8);
    }
    CloseHandle(hObject);
  }
  return (unsigned int)TokenInformation_Heap;
}

```

## disassembly

```asm
0x1800719b4  mov     [rsp+arg_0], rbx
0x1800719b9  mov     [rsp+arg_18], rsi
0x1800719be  push    rdi
0x1800719bf  sub     rsp, 20h
0x1800719c3  mov     rsi, rcx
0x1800719c6  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800719cd  lea     rcx, stru_180299FB8; InitOnce
0x1800719d4  xor     r9d, r9d; Context
0x1800719d7  xor     r8d, r8d; Parameter
0x1800719da  call    cs:__imp_InitOnceExecuteOnce
0x1800719e0  cmp     cs:byte_180298C9C, 0
0x1800719e7  jz      short loc_1800719F3
0x1800719e9  mov     eax, 80004001h
0x1800719ee  jmp     loc_180071AB0
0x1800719f3  lea     rdx, [rsp+28h+hObject]
0x1800719f8  mov     qword ptr [rsi], 0
0x1800719ff  mov     [rsp+28h+hObject], 0
0x180071a08  call    SHOpenEffectiveToken
0x180071a0d  mov     ebx, eax
0x180071a0f  test    eax, eax
0x180071a11  js      loc_180071AAE
0x180071a17  mov     rbx, [rsp+28h+hObject]
0x180071a1c  mov     [rsp+28h+lpMem], 0
0x180071a25  call    cs:__imp_GetProcessHeap
0x180071a2b  lea     r9, [rsp+28h+lpMem]
0x180071a30  mov     rdx, rbx; TokenHandle
0x180071a33  mov     rcx, rax; hHeap
0x180071a36  call    ??$GetTokenInformation_HeapFree@U_TOKEN_GROUPS@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_GROUPS@@@Z; GetTokenInformation_HeapFree<_TOKEN_GROUPS>(void *,void *,_TOKEN_INFORMATION_CLASS,_TOKEN_GROUPS * *)
0x180071a3b  mov     ebx, eax
0x180071a3d  test    eax, eax
0x180071a3f  js      short loc_180071AA3
0x180071a41  mov     rdi, [rsp+28h+lpMem]
0x180071a46  mov     ebx, 80004005h
0x180071a4b  xor     eax, eax
0x180071a4d  cmp     eax, [rdi]
0x180071a4f  jnb     short loc_180071A8F
0x180071a51  mov     ecx, eax
0x180071a53  add     rcx, rcx
0x180071a56  test    dword ptr [rdi+rcx*8+10h], 0C0000000h
0x180071a5e  jnz     short loc_180071A64
0x180071a60  inc     eax
0x180071a62  jmp     short loc_180071A4D
0x180071a64  mov     rcx, [rdi+rcx*8+8]; Sid
0x180071a69  mov     rdx, rsi; StringSid
0x180071a6c  call    cs:__imp_ConvertSidToStringSidW
0x180071a72  test    eax, eax
0x180071a74  jz      short loc_180071A7A
0x180071a76  xor     ebx, ebx
0x180071a78  jmp     short loc_180071A8F
0x180071a7a  call    cs:__imp_GetLastError
0x180071a80  mov     ebx, eax
0x180071a82  test    eax, eax
0x180071a84  jle     short loc_180071A8F
0x180071a86  movzx   ebx, ax
0x180071a89  or      ebx, 80070000h
0x180071a8f  call    cs:__imp_GetProcessHeap
0x180071a95  mov     r8, rdi; lpMem
0x180071a98  xor     edx, edx; dwFlags
0x180071a9a  mov     rcx, rax; hHeap
0x180071a9d  call    cs:__imp_HeapFree
0x180071aa3  mov     rcx, [rsp+28h+hObject]; hObject
0x180071aa8  call    cs:__imp_CloseHandle
0x180071aae  mov     eax, ebx
0x180071ab0  mov     rbx, [rsp+28h+arg_0]
0x180071ab5  mov     rsi, [rsp+28h+arg_18]
0x180071aba  add     rsp, 20h
0x180071abe  pop     rdi
0x180071abf  retn
```
