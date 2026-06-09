# NcaTriggerRegisterWait

- ea: `0x18000b51c`
- end: `0x18000b6cf`
- name: `NcaTriggerRegisterWait`
- size: `435`
- prototype: `__int64 __fastcall(PTP_WAIT_CALLBACK pfnwa, PVOID pv, HANDLE **)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18000b1e8`
- `0x18000b88c`
- `0x18000f654`
- `0x180011744`
- `0x1800169b0`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x18000b51c`
- `0x18000b6d8`
- `0x18001abd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b5dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b5dc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000b621`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000b621`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000b68a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000b68a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b635`

## pseudocode

```c
__int64 __fastcall NcaTriggerRegisterWait(PTP_WAIT_CALLBACK pfnwa, PVOID pv, HANDLE **a3)
{
  PVOID *v6; // rcx
  HANDLE *v7; // rdi
  unsigned int v8; // ebx
  __int64 v9; // rdx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  PVOID *v12; // rcx
  __int64 v13; // rdx
  struct _TP_WAIT *ThreadpoolWait; // rax

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    v7 = 0;
    v8 = 87;
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 1) == 0 )
      goto LABEL_23;
    v9 = 11;
    goto LABEL_8;
  }
  v7 = (HANDLE *)NcaAlloc(0x18u);
  if ( !v7 )
  {
    v8 = 14;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_23;
    v9 = 12;
LABEL_8:
    WPP_SF_d(v6[2], v9, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, v8);
LABEL_23:
    NcaTriggerUnregisterWait(v7);
LABEL_25:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v7[1] = EventW;
  if ( EventW )
  {
    ThreadpoolWait = CreateThreadpoolWait(pfnwa, pv, 0);
    *v7 = ThreadpoolWait;
    if ( ThreadpoolWait )
    {
      v8 = 0;
      SetThreadpoolWait(ThreadpoolWait, v7[1], 0);
      *a3 = v7;
      goto LABEL_25;
    }
    LastError = GetLastError();
    v8 = LastError;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 14;
      goto LABEL_21;
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 13;
LABEL_21:
      WPP_SF_d(v12[2], v13, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, LastError);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v8 )
    goto LABEL_23;
LABEL_26:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    WPP_SF_d(v12[2], 15, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18000b51c  push    rbx
0x18000b51e  push    rbp
0x18000b51f  push    rsi
0x18000b520  push    rdi
0x18000b521  push    r14
0x18000b523  push    r15
0x18000b525  sub     rsp, 28h
0x18000b529  mov     rsi, r8
0x18000b52c  mov     rbx, rdx
0x18000b52f  mov     rbp, rcx
0x18000b532  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b539  lea     r14, WPP_GLOBAL_Control
0x18000b540  lea     r15, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x18000b547  cmp     rcx, r14
0x18000b54a  jz      short loc_18000B56A
0x18000b54c  test    byte ptr [rcx+1Ch], 8
0x18000b550  jz      short loc_18000B56A
0x18000b552  mov     rcx, [rcx+10h]
0x18000b556  mov     edx, 0Ah
0x18000b55b  mov     r8, r15
0x18000b55e  call    WPP_SF_
0x18000b563  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b56a  test    rsi, rsi
0x18000b56d  jnz     short loc_18000B59E
0x18000b56f  xor     edi, edi
0x18000b571  lea     ebx, [rsi+57h]
0x18000b574  cmp     rcx, r14
0x18000b577  jz      loc_18000B674
0x18000b57d  test    byte ptr [rcx+1Ch], 1
0x18000b581  jz      loc_18000B674
0x18000b587  lea     edx, [rsi+0Bh]
0x18000b58a  mov     rcx, [rcx+10h]
0x18000b58e  mov     r9d, ebx
0x18000b591  mov     r8, r15
0x18000b594  call    WPP_SF_d
0x18000b599  jmp     loc_18000B674
0x18000b59e  mov     ecx, 18h
0x18000b5a3  call    NcaAlloc
0x18000b5a8  mov     rdi, rax
0x18000b5ab  test    rax, rax
0x18000b5ae  jnz     short loc_18000B5D2
0x18000b5b0  lea     ebx, [rax+0Eh]
0x18000b5b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5ba  cmp     rcx, r14
0x18000b5bd  jz      loc_18000B674
0x18000b5c3  test    byte ptr [rcx+1Ch], 1
0x18000b5c7  jz      loc_18000B674
0x18000b5cd  lea     edx, [rax+0Ch]
0x18000b5d0  jmp     short loc_18000B58A
0x18000b5d2  xor     r9d, r9d; lpName
0x18000b5d5  xor     r8d, r8d; bInitialState
0x18000b5d8  xor     edx, edx; bManualReset
0x18000b5da  xor     ecx, ecx; lpEventAttributes
0x18000b5dc  call    cs:__imp_CreateEventW
0x18000b5e3  nop     dword ptr [rax+rax+00h]
0x18000b5e8  mov     [rdi+8], rax
0x18000b5ec  test    rax, rax
0x18000b5ef  jnz     short loc_18000B618
0x18000b5f1  call    cs:__imp_GetLastError
0x18000b5f8  nop     dword ptr [rax+rax+00h]
0x18000b5fd  mov     ebx, eax
0x18000b5ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b606  cmp     rcx, r14
0x18000b609  jz      short loc_18000B670
0x18000b60b  test    byte ptr [rcx+1Ch], 1
0x18000b60f  jz      short loc_18000B670
0x18000b611  mov     edx, 0Dh
0x18000b616  jmp     short loc_18000B65A
0x18000b618  xor     r8d, r8d; pcbe
0x18000b61b  mov     rdx, rbx; pv
0x18000b61e  mov     rcx, rbp; pfnwa
0x18000b621  call    cs:__imp_CreateThreadpoolWait
0x18000b628  nop     dword ptr [rax+rax+00h]
0x18000b62d  mov     [rdi], rax
0x18000b630  test    rax, rax
0x18000b633  jnz     short loc_18000B67E
0x18000b635  call    cs:__imp_GetLastError
0x18000b63c  nop     dword ptr [rax+rax+00h]
0x18000b641  mov     ebx, eax
0x18000b643  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b64a  cmp     rcx, r14
0x18000b64d  jz      short loc_18000B670
0x18000b64f  test    byte ptr [rcx+1Ch], 1
0x18000b653  jz      short loc_18000B670
0x18000b655  mov     edx, 0Eh
0x18000b65a  mov     rcx, [rcx+10h]
0x18000b65e  mov     r9d, eax
0x18000b661  mov     r8, r15
0x18000b664  call    WPP_SF_d
0x18000b669  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b670  test    ebx, ebx
0x18000b672  jz      short loc_18000B6A0
0x18000b674  mov     rcx, rdi; lpMem
0x18000b677  call    NcaTriggerUnregisterWait
0x18000b67c  jmp     short loc_18000B699
0x18000b67e  mov     rdx, [rdi+8]; h
0x18000b682  xor     ebx, ebx
0x18000b684  xor     r8d, r8d; pftTimeout
0x18000b687  mov     rcx, rax; pwa
0x18000b68a  call    cs:__imp_SetThreadpoolWait
0x18000b691  nop     dword ptr [rax+rax+00h]
0x18000b696  mov     [rsi], rdi
0x18000b699  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6a0  cmp     rcx, r14
0x18000b6a3  jz      short loc_18000B6BF
0x18000b6a5  test    byte ptr [rcx+1Ch], 8
0x18000b6a9  jz      short loc_18000B6BF
0x18000b6ab  mov     rcx, [rcx+10h]
0x18000b6af  mov     edx, 0Fh
0x18000b6b4  mov     r9d, ebx
0x18000b6b7  mov     r8, r15
0x18000b6ba  call    WPP_SF_d
0x18000b6bf  mov     eax, ebx
0x18000b6c1  add     rsp, 28h
0x18000b6c5  pop     r15
0x18000b6c7  pop     r14
0x18000b6c9  pop     rdi
0x18000b6ca  pop     rsi
0x18000b6cb  pop     rbp
0x18000b6cc  pop     rbx
0x18000b6cd  retn
```
