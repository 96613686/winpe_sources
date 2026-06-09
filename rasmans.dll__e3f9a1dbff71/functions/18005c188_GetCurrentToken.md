# GetCurrentToken

- ea: `0x18005c188`
- end: `0x18005c392`
- name: `GetCurrentToken`
- size: `522`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18005c710`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18005c188`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005c280`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005c280`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005c225`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005c225`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005c210`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005c210`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005c26f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005c26f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c28e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c28e`

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
0x18005c188  push    rbx
0x18005c18a  push    rbp
0x18005c18b  push    rdi
0x18005c18c  push    r14
0x18005c18e  sub     rsp, 28h
0x18005c192  mov     rdi, rcx
0x18005c195  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c19c  lea     rbp, WPP_GLOBAL_Control
0x18005c1a3  lea     r14, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18005c1aa  cmp     rcx, rbp
0x18005c1ad  jz      short loc_18005C1D7
0x18005c1af  test    byte ptr [rcx+1Ch], 4
0x18005c1b3  jz      short loc_18005C1D7
0x18005c1b5  cmp     byte ptr [rcx+19h], 6
0x18005c1b9  jb      short loc_18005C1D7
0x18005c1bb  mov     rcx, [rcx+10h]
0x18005c1bf  mov     edx, 23h ; '#'
0x18005c1c4  mov     r8, r14
0x18005c1c7  lea     r9d, [rdx-1Bh]
0x18005c1cb  call    WPP_SF_d
0x18005c1d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c1d7  test    rdi, rdi
0x18005c1da  jnz     short loc_18005C209
0x18005c1dc  lea     ebx, [rdi+57h]
0x18005c1df  cmp     rcx, rbp
0x18005c1e2  jz      short loc_18005C202
0x18005c1e4  test    byte ptr [rcx+1Ch], 4
0x18005c1e8  jz      short loc_18005C202
0x18005c1ea  cmp     byte ptr [rcx+19h], 2
0x18005c1ee  jb      short loc_18005C202
0x18005c1f0  lea     edx, [rdi+24h]
0x18005c1f3  mov     rcx, [rcx+10h]
0x18005c1f7  mov     r9d, ebx
0x18005c1fa  mov     r8, r14
0x18005c1fd  call    WPP_SF_d
0x18005c202  mov     eax, ebx
0x18005c204  jmp     loc_18005C388
0x18005c209  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18005c210  call    cs:__imp_GetCurrentThread
0x18005c216  mov     edx, 8; DesiredAccess
0x18005c21b  mov     r9, rdi; TokenHandle
0x18005c21e  mov     rcx, rax; ThreadHandle
0x18005c221  lea     r8d, [rdx-7]; OpenAsSelf
0x18005c225  call    cs:__imp_OpenThreadToken
0x18005c22b  test    eax, eax
0x18005c22d  jnz     loc_18005C35A
0x18005c233  call    cs:__imp_GetLastError
0x18005c239  mov     ebx, eax
0x18005c23b  cmp     eax, 3F0h
0x18005c240  jnz     loc_18005C2F8
0x18005c246  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c24d  cmp     rcx, rbp
0x18005c250  jz      short loc_18005C26F
0x18005c252  test    byte ptr [rcx+1Ch], 4
0x18005c256  jz      short loc_18005C26F
0x18005c258  cmp     byte ptr [rcx+19h], 5
0x18005c25c  jb      short loc_18005C26F
0x18005c25e  mov     rcx, [rcx+10h]
0x18005c262  mov     edx, 25h ; '%'
0x18005c267  mov     r8, r14
0x18005c26a  call    WPP_SF_
0x18005c26f  call    cs:__imp_GetCurrentProcess
0x18005c275  mov     r8, rdi; TokenHandle
0x18005c278  mov     edx, 8; DesiredAccess
0x18005c27d  mov     rcx, rax; ProcessHandle
0x18005c280  call    cs:__imp_OpenProcessToken
0x18005c286  test    eax, eax
0x18005c288  jnz     loc_18005C35A
0x18005c28e  call    cs:__imp_GetLastError
0x18005c294  mov     ebx, eax
0x18005c296  test    eax, eax
0x18005c298  jz      short loc_18005C2CA
0x18005c29a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c2a1  cmp     rcx, rbp
0x18005c2a4  jz      loc_18005C202
0x18005c2aa  test    byte ptr [rcx+1Ch], 4
0x18005c2ae  jz      short loc_18005C2D1
0x18005c2b0  cmp     byte ptr [rcx+19h], 2
0x18005c2b4  jb      short loc_18005C2D1
0x18005c2b6  mov     rcx, [rcx+10h]
0x18005c2ba  mov     edx, 26h ; '&'
0x18005c2bf  mov     r9d, eax
0x18005c2c2  mov     r8, r14
0x18005c2c5  call    WPP_SF_d
0x18005c2ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c2d1  cmp     rcx, rbp
0x18005c2d4  jz      loc_18005C202
0x18005c2da  test    byte ptr [rcx+1Ch], 4
0x18005c2de  jz      loc_18005C202
0x18005c2e4  cmp     byte ptr [rcx+19h], 6
0x18005c2e8  jb      loc_18005C202
0x18005c2ee  mov     edx, 27h ; '''
0x18005c2f3  jmp     loc_18005C1F3
0x18005c2f8  test    ebx, ebx
0x18005c2fa  jz      short loc_18005C32C
0x18005c2fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c303  cmp     rcx, rbp
0x18005c306  jz      loc_18005C202
0x18005c30c  test    byte ptr [rcx+1Ch], 4
0x18005c310  jz      short loc_18005C333
0x18005c312  cmp     byte ptr [rcx+19h], 2
0x18005c316  jb      short loc_18005C333
0x18005c318  mov     rcx, [rcx+10h]
0x18005c31c  mov     edx, 28h ; '('
0x18005c321  mov     r9d, ebx
0x18005c324  mov     r8, r14
0x18005c327  call    WPP_SF_d
0x18005c32c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c333  cmp     rcx, rbp
0x18005c336  jz      loc_18005C202
0x18005c33c  test    byte ptr [rcx+1Ch], 4
0x18005c340  jz      loc_18005C202
0x18005c346  cmp     byte ptr [rcx+19h], 6
0x18005c34a  jb      loc_18005C202
0x18005c350  mov     edx, 29h ; ')'
0x18005c355  jmp     loc_18005C1F3
0x18005c35a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c361  cmp     rcx, rbp
0x18005c364  jz      short loc_18005C386
0x18005c366  test    byte ptr [rcx+1Ch], 4
0x18005c36a  jz      short loc_18005C386
0x18005c36c  cmp     byte ptr [rcx+19h], 6
0x18005c370  jb      short loc_18005C386
0x18005c372  mov     rcx, [rcx+10h]
0x18005c376  mov     edx, 2Ah ; '*'
0x18005c37b  xor     r9d, r9d
0x18005c37e  mov     r8, r14
0x18005c381  call    WPP_SF_d
0x18005c386  xor     eax, eax
0x18005c388  add     rsp, 28h
0x18005c38c  pop     r14
0x18005c38e  pop     rdi
0x18005c38f  pop     rbp
0x18005c390  pop     rbx
0x18005c391  retn
```
