# GetCurrentToken

- ea: `0x18005f0f4`
- end: `0x18005f323`
- name: `GetCurrentToken`
- size: `559`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18005f6f4`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18005f0f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f17c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f17c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005f197`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005f197`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005f1ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005f1ed`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005f204`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005f204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f1ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f1ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f218`

## pseudocode

```c
__int64 __fastcall GetCurrentToken(PHANDLE TokenHandle)
{
  struct _LIST_ENTRY *v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rdx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  DWORD v9; // eax

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 35, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, 8);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !TokenHandle )
  {
    v3 = 87;
    if ( v2 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v2[1].Blink) & 4) == 0 || BYTE1(v2[1].Blink) < 2u )
      return v3;
    v4 = 36;
    goto LABEL_10;
  }
  *TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
    goto LABEL_39;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError != 1008 )
  {
    if ( LastError )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v3;
      if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_35;
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 40, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, LastError);
    }
    v2 = WPP_GLOBAL_Control;
LABEL_35:
    if ( v2 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v2[1].Blink) & 4) == 0 || BYTE1(v2[1].Blink) < 6u )
      return v3;
    v4 = 41;
LABEL_10:
    WPP_SF_d(v2[1].Flink, v4, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v3);
    return v3;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 37, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids);
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
  {
    v9 = GetLastError();
    v3 = v9;
    if ( v9 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v3;
      if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_25;
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 38, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v9);
    }
    v2 = WPP_GLOBAL_Control;
LABEL_25:
    if ( v2 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v2[1].Blink) & 4) == 0 || BYTE1(v2[1].Blink) < 6u )
      return v3;
    v4 = 39;
    goto LABEL_10;
  }
LABEL_39:
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 42, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18005f0f4  push    rbx
0x18005f0f6  push    rbp
0x18005f0f7  push    rdi
0x18005f0f8  push    r14
0x18005f0fa  sub     rsp, 28h
0x18005f0fe  mov     rdi, rcx
0x18005f101  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f108  lea     rbp, WPP_GLOBAL_Control
0x18005f10f  lea     r14, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18005f116  cmp     rcx, rbp
0x18005f119  jz      short loc_18005F143
0x18005f11b  test    byte ptr [rcx+1Ch], 4
0x18005f11f  jz      short loc_18005F143
0x18005f121  cmp     byte ptr [rcx+19h], 6
0x18005f125  jb      short loc_18005F143
0x18005f127  mov     rcx, [rcx+10h]
0x18005f12b  mov     edx, 23h ; '#'
0x18005f130  mov     r8, r14
0x18005f133  lea     r9d, [rdx-1Bh]
0x18005f137  call    WPP_SF_d
0x18005f13c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f143  test    rdi, rdi
0x18005f146  jnz     short loc_18005F175
0x18005f148  lea     ebx, [rdi+57h]
0x18005f14b  cmp     rcx, rbp
0x18005f14e  jz      short loc_18005F16E
0x18005f150  test    byte ptr [rcx+1Ch], 4
0x18005f154  jz      short loc_18005F16E
0x18005f156  cmp     byte ptr [rcx+19h], 2
0x18005f15a  jb      short loc_18005F16E
0x18005f15c  lea     edx, [rdi+24h]
0x18005f15f  mov     rcx, [rcx+10h]
0x18005f163  mov     r9d, ebx
0x18005f166  mov     r8, r14
0x18005f169  call    WPP_SF_d
0x18005f16e  mov     eax, ebx
0x18005f170  jmp     loc_18005F318
0x18005f175  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18005f17c  call    cs:__imp_GetCurrentThread
0x18005f183  nop     dword ptr [rax+rax+00h]
0x18005f188  mov     edx, 8; DesiredAccess
0x18005f18d  mov     r9, rdi; TokenHandle
0x18005f190  mov     rcx, rax; ThreadHandle
0x18005f193  lea     r8d, [rdx-7]; OpenAsSelf
0x18005f197  call    cs:__imp_OpenThreadToken
0x18005f19e  nop     dword ptr [rax+rax+00h]
0x18005f1a3  test    eax, eax
0x18005f1a5  jnz     loc_18005F2EA
0x18005f1ab  call    cs:__imp_GetLastError
0x18005f1b2  nop     dword ptr [rax+rax+00h]
0x18005f1b7  mov     ebx, eax
0x18005f1b9  cmp     eax, 3F0h
0x18005f1be  jnz     loc_18005F288
0x18005f1c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f1cb  cmp     rcx, rbp
0x18005f1ce  jz      short loc_18005F1ED
0x18005f1d0  test    byte ptr [rcx+1Ch], 4
0x18005f1d4  jz      short loc_18005F1ED
0x18005f1d6  cmp     byte ptr [rcx+19h], 5
0x18005f1da  jb      short loc_18005F1ED
0x18005f1dc  mov     rcx, [rcx+10h]
0x18005f1e0  mov     edx, 25h ; '%'
0x18005f1e5  mov     r8, r14
0x18005f1e8  call    WPP_SF_
0x18005f1ed  call    cs:__imp_GetCurrentProcess
0x18005f1f4  nop     dword ptr [rax+rax+00h]
0x18005f1f9  mov     r8, rdi; TokenHandle
0x18005f1fc  mov     edx, 8; DesiredAccess
0x18005f201  mov     rcx, rax; ProcessHandle
0x18005f204  call    cs:__imp_OpenProcessToken
0x18005f20b  nop     dword ptr [rax+rax+00h]
0x18005f210  test    eax, eax
0x18005f212  jnz     loc_18005F2EA
0x18005f218  call    cs:__imp_GetLastError
0x18005f21f  nop     dword ptr [rax+rax+00h]
0x18005f224  mov     ebx, eax
0x18005f226  test    eax, eax
0x18005f228  jz      short loc_18005F25A
0x18005f22a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f231  cmp     rcx, rbp
0x18005f234  jz      loc_18005F16E
0x18005f23a  test    byte ptr [rcx+1Ch], 4
0x18005f23e  jz      short loc_18005F261
0x18005f240  cmp     byte ptr [rcx+19h], 2
0x18005f244  jb      short loc_18005F261
0x18005f246  mov     rcx, [rcx+10h]
0x18005f24a  mov     edx, 26h ; '&'
0x18005f24f  mov     r9d, eax
0x18005f252  mov     r8, r14
0x18005f255  call    WPP_SF_d
0x18005f25a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f261  cmp     rcx, rbp
0x18005f264  jz      loc_18005F16E
0x18005f26a  test    byte ptr [rcx+1Ch], 4
0x18005f26e  jz      loc_18005F16E
0x18005f274  cmp     byte ptr [rcx+19h], 6
0x18005f278  jb      loc_18005F16E
0x18005f27e  mov     edx, 27h ; '''
0x18005f283  jmp     loc_18005F15F
0x18005f288  test    ebx, ebx
0x18005f28a  jz      short loc_18005F2BC
0x18005f28c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f293  cmp     rcx, rbp
0x18005f296  jz      loc_18005F16E
0x18005f29c  test    byte ptr [rcx+1Ch], 4
0x18005f2a0  jz      short loc_18005F2C3
0x18005f2a2  cmp     byte ptr [rcx+19h], 2
0x18005f2a6  jb      short loc_18005F2C3
0x18005f2a8  mov     rcx, [rcx+10h]
0x18005f2ac  mov     edx, 28h ; '('
0x18005f2b1  mov     r9d, ebx
0x18005f2b4  mov     r8, r14
0x18005f2b7  call    WPP_SF_d
0x18005f2bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f2c3  cmp     rcx, rbp
0x18005f2c6  jz      loc_18005F16E
0x18005f2cc  test    byte ptr [rcx+1Ch], 4
0x18005f2d0  jz      loc_18005F16E
0x18005f2d6  cmp     byte ptr [rcx+19h], 6
0x18005f2da  jb      loc_18005F16E
0x18005f2e0  mov     edx, 29h ; ')'
0x18005f2e5  jmp     loc_18005F15F
0x18005f2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f2f1  cmp     rcx, rbp
0x18005f2f4  jz      short loc_18005F316
0x18005f2f6  test    byte ptr [rcx+1Ch], 4
0x18005f2fa  jz      short loc_18005F316
0x18005f2fc  cmp     byte ptr [rcx+19h], 6
0x18005f300  jb      short loc_18005F316
0x18005f302  mov     rcx, [rcx+10h]
0x18005f306  mov     edx, 2Ah ; '*'
0x18005f30b  xor     r9d, r9d
0x18005f30e  mov     r8, r14
0x18005f311  call    WPP_SF_d
0x18005f316  xor     eax, eax
0x18005f318  add     rsp, 28h
0x18005f31c  pop     r14
0x18005f31e  pop     rdi
0x18005f31f  pop     rbp
0x18005f320  pop     rbx
0x18005f321  retn
```
