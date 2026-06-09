# GetSidStringByToken

- ea: `0x18008117c`
- end: `0x1800812ac`
- name: `GetSidStringByToken`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180089b70`

## callees

- `0x180005e34`
- `0x18005c398`
- `0x18005dec8`
- `0x18008117c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800811dd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800811dd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800811b0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800811b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180081197`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180081197`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800811cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800811cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081294`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800811be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800811e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800811be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800811e7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180081284`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180081284`

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
0x18008117c  mov     [rsp+arg_0], rbx
0x180081181  mov     [rsp+arg_18], rsi
0x180081186  push    rdi
0x180081187  sub     rsp, 20h
0x18008118b  mov     rsi, rcx
0x18008118e  mov     [rsp+28h+TokenHandle], 0
0x180081197  call    cs:__imp_GetCurrentThread
0x18008119d  mov     edi, 0Ch
0x1800811a2  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800811a7  mov     rcx, rax; ThreadHandle
0x1800811aa  mov     edx, edi; DesiredAccess
0x1800811ac  lea     r8d, [rdi-0Bh]; OpenAsSelf
0x1800811b0  call    cs:__imp_OpenThreadToken
0x1800811b6  test    eax, eax
0x1800811b8  jnz     loc_18008124E
0x1800811be  call    cs:__imp_GetLastError
0x1800811c4  mov     ebx, eax
0x1800811c6  cmp     eax, 3F0h
0x1800811cb  jnz     short loc_180081228
0x1800811cd  call    cs:__imp_GetCurrentProcess
0x1800811d3  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x1800811d8  mov     edx, edi; DesiredAccess
0x1800811da  mov     rcx, rax; ProcessHandle
0x1800811dd  call    cs:__imp_OpenProcessToken
0x1800811e3  test    eax, eax
0x1800811e5  jnz     short loc_18008124E
0x1800811e7  call    cs:__imp_GetLastError
0x1800811ed  mov     ebx, eax
0x1800811ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800811f6  lea     rdx, WPP_GLOBAL_Control
0x1800811fd  cmp     rcx, rdx
0x180081200  jz      short loc_180081224
0x180081202  test    byte ptr [rcx+1Ch], 80h
0x180081206  jz      short loc_180081224
0x180081208  cmp     byte ptr [rcx+19h], 2
0x18008120c  jb      short loc_180081224
0x18008120e  lea     edx, [rdi+6]
0x180081211  mov     rcx, [rcx+10h]
0x180081215  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x18008121c  mov     r9d, ebx
0x18008121f  call    WPP_SF_d
0x180081224  mov     eax, ebx
0x180081226  jmp     short loc_18008129C
0x180081228  mov     rcx, cs:WPP_GLOBAL_Control
0x18008122f  lea     rdx, WPP_GLOBAL_Control
0x180081236  cmp     rcx, rdx
0x180081239  jz      short loc_180081224
0x18008123b  test    byte ptr [rcx+1Ch], 80h
0x18008123f  jz      short loc_180081224
0x180081241  cmp     byte ptr [rcx+19h], 2
0x180081245  jb      short loc_180081224
0x180081247  mov     edx, 13h
0x18008124c  jmp     short loc_180081211
0x18008124e  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180081253  lea     rdx, [rsp+28h+hMem]
0x180081258  mov     [rsp+28h+hMem], 0
0x180081261  call    GetSidFromToken
0x180081266  mov     rbx, [rsp+28h+hMem]
0x18008126b  mov     edi, eax
0x18008126d  test    eax, eax
0x18008126f  jnz     short loc_18008127C
0x180081271  mov     rcx, rbx; lpWideCharStr
0x180081274  call    _StrdupWtoA
0x180081279  mov     [rsi], rax
0x18008127c  test    rbx, rbx
0x18008127f  jz      short loc_18008128A
0x180081281  mov     rcx, rbx; hMem
0x180081284  call    cs:__imp_GlobalFree
0x18008128a  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18008128f  test    rcx, rcx
0x180081292  jz      short loc_18008129A
0x180081294  call    cs:__imp_CloseHandle
0x18008129a  mov     eax, edi
0x18008129c  mov     rbx, [rsp+28h+arg_0]
0x1800812a1  mov     rsi, [rsp+28h+arg_18]
0x1800812a6  add     rsp, 20h
0x1800812aa  pop     rdi
0x1800812ab  retn
```
