# GetSidStringByToken

- ea: `0x180085424`
- end: `0x180085588`
- name: `GetSidStringByToken`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18008e0f4`

## callees

- `0x180005bfc`
- `0x18005f32c`
- `0x180061064`
- `0x180085424`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008543f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008543f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008545e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008545e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180085487`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180085487`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008549d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008549d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085569`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800854ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800854ad`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180085553`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180085553`

## pseudocode

```c
__int64 __fastcall GetSidStringByToken(_QWORD *a1)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  struct _LIST_ENTRY *v5; // rcx
  __int64 v6; // rdx
  unsigned int SidFromToken; // eax
  HGLOBAL v9; // rbx
  unsigned int v10; // edi
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF
  HGLOBAL hMem; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        return LastError;
      }
      v6 = 19;
      goto LABEL_8;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle) )
    {
      LastError = GetLastError();
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        return LastError;
      }
      v6 = 18;
LABEL_8:
      WPP_SF_d(v5[1].Flink, v6, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, LastError);
      return LastError;
    }
  }
  hMem = 0;
  SidFromToken = GetSidFromToken(TokenHandle, &hMem);
  v9 = hMem;
  v10 = SidFromToken;
  if ( !SidFromToken )
    *a1 = StrdupWtoA((LPCWCH)hMem);
  if ( v9 )
    GlobalFree(v9);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v10;
}

```

## disassembly

```asm
0x180085424  mov     [rsp+arg_0], rbx
0x180085429  mov     [rsp+arg_18], rsi
0x18008542e  push    rdi
0x18008542f  sub     rsp, 20h
0x180085433  mov     rsi, rcx
0x180085436  mov     [rsp+28h+TokenHandle], 0
0x18008543f  call    cs:__imp_GetCurrentThread
0x180085446  nop     dword ptr [rax+rax+00h]
0x18008544b  mov     edi, 0Ch
0x180085450  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180085455  mov     rcx, rax; ThreadHandle
0x180085458  mov     edx, edi; DesiredAccess
0x18008545a  lea     r8d, [rdi-0Bh]; OpenAsSelf
0x18008545e  call    cs:__imp_OpenThreadToken
0x180085465  nop     dword ptr [rax+rax+00h]
0x18008546a  test    eax, eax
0x18008546c  jnz     loc_18008551D
0x180085472  call    cs:__imp_GetLastError
0x180085479  nop     dword ptr [rax+rax+00h]
0x18008547e  mov     ebx, eax
0x180085480  cmp     eax, 3F0h
0x180085485  jnz     short loc_1800854F7
0x180085487  call    cs:__imp_GetCurrentProcess
0x18008548e  nop     dword ptr [rax+rax+00h]
0x180085493  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180085498  mov     edx, edi; DesiredAccess
0x18008549a  mov     rcx, rax; ProcessHandle
0x18008549d  call    cs:__imp_OpenProcessToken
0x1800854a4  nop     dword ptr [rax+rax+00h]
0x1800854a9  test    eax, eax
0x1800854ab  jnz     short loc_18008551D
0x1800854ad  call    cs:__imp_GetLastError
0x1800854b4  nop     dword ptr [rax+rax+00h]
0x1800854b9  mov     ebx, eax
0x1800854bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800854c2  lea     rdx, WPP_GLOBAL_Control
0x1800854c9  cmp     rcx, rdx
0x1800854cc  jz      short loc_1800854F0
0x1800854ce  test    byte ptr [rcx+1Ch], 80h
0x1800854d2  jz      short loc_1800854F0
0x1800854d4  cmp     byte ptr [rcx+19h], 2
0x1800854d8  jb      short loc_1800854F0
0x1800854da  lea     edx, [rdi+6]
0x1800854dd  mov     rcx, [rcx+10h]
0x1800854e1  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x1800854e8  mov     r9d, ebx
0x1800854eb  call    WPP_SF_d
0x1800854f0  mov     eax, ebx
0x1800854f2  jmp     loc_180085577
0x1800854f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800854fe  lea     rdx, WPP_GLOBAL_Control
0x180085505  cmp     rcx, rdx
0x180085508  jz      short loc_1800854F0
0x18008550a  test    byte ptr [rcx+1Ch], 80h
0x18008550e  jz      short loc_1800854F0
0x180085510  cmp     byte ptr [rcx+19h], 2
0x180085514  jb      short loc_1800854F0
0x180085516  mov     edx, 13h
0x18008551b  jmp     short loc_1800854DD
0x18008551d  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180085522  lea     rdx, [rsp+28h+hMem]
0x180085527  mov     [rsp+28h+hMem], 0
0x180085530  call    GetSidFromToken
0x180085535  mov     rbx, [rsp+28h+hMem]
0x18008553a  mov     edi, eax
0x18008553c  test    eax, eax
0x18008553e  jnz     short loc_18008554B
0x180085540  mov     rcx, rbx; lpWideCharStr
0x180085543  call    _StrdupWtoA
0x180085548  mov     [rsi], rax
0x18008554b  test    rbx, rbx
0x18008554e  jz      short loc_18008555F
0x180085550  mov     rcx, rbx; hMem
0x180085553  call    cs:__imp_GlobalFree
0x18008555a  nop     dword ptr [rax+rax+00h]
0x18008555f  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180085564  test    rcx, rcx
0x180085567  jz      short loc_180085575
0x180085569  call    cs:__imp_CloseHandle
0x180085570  nop     dword ptr [rax+rax+00h]
0x180085575  mov     eax, edi
0x180085577  mov     rbx, [rsp+28h+arg_0]
0x18008557c  mov     rsi, [rsp+28h+arg_18]
0x180085581  add     rsp, 20h
0x180085585  pop     rdi
0x180085586  retn
```
