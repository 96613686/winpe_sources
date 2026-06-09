# GetCurrentToken

- ea: `0x18002470c`
- end: `0x180024987`
- name: `GetCurrentToken`
- size: `635`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180024d88`

## callees

- `0x180020fd8`
- `0x180021000`
- `0x18002470c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024810`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024810`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800247b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800247b1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024821`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024821`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800247c6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800247c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002482f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002482f`
- `rtutils!TracePrintfExA` at `0x18002479d`
- `rtutils!TracePrintfExA` at `0x18002488a`
- `rtutils!TracePrintfExA` at `0x1800248e7`
- `rtutils!TracePrintfExA` at `0x18002479d`
- `rtutils!TracePrintfExA` at `0x18002488a`
- `rtutils!TracePrintfExA` at `0x1800248e7`

## string_xrefs

- `0x180024791`: `GetCurrentToken: Invalid token pointer`
- `0x18002487c`: `GetCurrentToken: OpenProcessToken failed with %d`
- `0x1800248db`: `OpenThreadToken failed with %d`

## pseudocode

```c
__int64 __fastcall GetCurrentToken(PHANDLE TokenHandle)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  DWORD v8; // eax
  PVOID *v9; // rcx
  __int64 v10; // rdx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, 8);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !TokenHandle )
  {
    v3 = 87;
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 && *((_BYTE *)v2 + 25) >= 2u )
      WPP_SF_d(v2[2], 36, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, 87);
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "GetCurrentToken: Invalid token pointer");
    return v3;
  }
  *TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
    goto LABEL_45;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError != 1008 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "OpenThreadToken failed with %d", LastError);
    if ( v3 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v3;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_41;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v3);
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_41:
    if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 4) == 0 || *((_BYTE *)v9 + 25) < 6u )
      return v3;
    v10 = 41;
    goto LABEL_32;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids);
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
  {
    v8 = GetLastError();
    v3 = v8;
    if ( v8 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_26;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v8);
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_26:
    if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(g_dwTraceId, 0xCu, "GetCurrentToken: OpenProcessToken failed with %d", v3);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 4) == 0 || *((_BYTE *)v9 + 25) < 6u )
      return v3;
    v10 = 39;
LABEL_32:
    WPP_SF_d(v9[2], v10, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v3);
    return v3;
  }
LABEL_45:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18002470c  push    rbx
0x18002470e  push    rbp
0x18002470f  push    rdi
0x180024710  push    r14
0x180024712  sub     rsp, 28h
0x180024716  mov     rdi, rcx
0x180024719  mov     rcx, cs:WPP_GLOBAL_Control
0x180024720  lea     rbp, WPP_GLOBAL_Control
0x180024727  lea     r14, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18002472e  cmp     rcx, rbp
0x180024731  jz      short loc_18002475B
0x180024733  test    byte ptr [rcx+1Ch], 4
0x180024737  jz      short loc_18002475B
0x180024739  cmp     byte ptr [rcx+19h], 6
0x18002473d  jb      short loc_18002475B
0x18002473f  mov     rcx, [rcx+10h]
0x180024743  mov     edx, 23h ; '#'
0x180024748  mov     r8, r14
0x18002474b  lea     r9d, [rdx-1Bh]
0x18002474f  call    WPP_SF_d
0x180024754  mov     rcx, cs:WPP_GLOBAL_Control
0x18002475b  test    rdi, rdi
0x18002475e  jnz     short loc_1800247AA
0x180024760  lea     ebx, [rdi+57h]
0x180024763  cmp     rcx, rbp
0x180024766  jz      short loc_180024786
0x180024768  test    byte ptr [rcx+1Ch], 4
0x18002476c  jz      short loc_180024786
0x18002476e  cmp     byte ptr [rcx+19h], 2
0x180024772  jb      short loc_180024786
0x180024774  mov     rcx, [rcx+10h]
0x180024778  lea     edx, [rdi+24h]
0x18002477b  mov     r9d, ebx
0x18002477e  mov     r8, r14
0x180024781  call    WPP_SF_d
0x180024786  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002478c  cmp     ecx, 0FFFFFFFFh
0x18002478f  jz      short loc_1800247A3
0x180024791  lea     r8, aGetcurrenttoke_0; "GetCurrentToken: Invalid token pointer"
0x180024798  mov     edx, 0Ch; dwFlags
0x18002479d  call    cs:__imp_TracePrintfExA
0x1800247a3  mov     eax, ebx
0x1800247a5  jmp     loc_18002497D
0x1800247aa  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800247b1  call    cs:__imp_GetCurrentThread
0x1800247b7  mov     edx, 8; DesiredAccess
0x1800247bc  mov     r9, rdi; TokenHandle
0x1800247bf  mov     rcx, rax; ThreadHandle
0x1800247c2  lea     r8d, [rdx-7]; OpenAsSelf
0x1800247c6  call    cs:__imp_OpenThreadToken
0x1800247cc  test    eax, eax
0x1800247ce  jnz     loc_18002494F
0x1800247d4  call    cs:__imp_GetLastError
0x1800247da  mov     ebx, eax
0x1800247dc  cmp     eax, 3F0h
0x1800247e1  jnz     loc_1800248CD
0x1800247e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247ee  cmp     rcx, rbp
0x1800247f1  jz      short loc_180024810
0x1800247f3  test    byte ptr [rcx+1Ch], 4
0x1800247f7  jz      short loc_180024810
0x1800247f9  cmp     byte ptr [rcx+19h], 5
0x1800247fd  jb      short loc_180024810
0x1800247ff  mov     rcx, [rcx+10h]
0x180024803  mov     edx, 25h ; '%'
0x180024808  mov     r8, r14
0x18002480b  call    WPP_SF_
0x180024810  call    cs:__imp_GetCurrentProcess
0x180024816  mov     r8, rdi; TokenHandle
0x180024819  mov     edx, 8; DesiredAccess
0x18002481e  mov     rcx, rax; ProcessHandle
0x180024821  call    cs:__imp_OpenProcessToken
0x180024827  test    eax, eax
0x180024829  jnz     loc_18002494F
0x18002482f  call    cs:__imp_GetLastError
0x180024835  mov     ebx, eax
0x180024837  test    eax, eax
0x180024839  jz      short loc_180024867
0x18002483b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024842  cmp     rcx, rbp
0x180024845  jz      short loc_18002486E
0x180024847  test    byte ptr [rcx+1Ch], 4
0x18002484b  jz      short loc_18002486E
0x18002484d  cmp     byte ptr [rcx+19h], 2
0x180024851  jb      short loc_18002486E
0x180024853  mov     rcx, [rcx+10h]
0x180024857  mov     edx, 26h ; '&'
0x18002485c  mov     r9d, eax
0x18002485f  mov     r8, r14
0x180024862  call    WPP_SF_d
0x180024867  mov     rcx, cs:WPP_GLOBAL_Control
0x18002486e  mov     eax, cs:g_dwTraceId
0x180024874  cmp     eax, 0FFFFFFFFh
0x180024877  jz      short loc_180024897
0x180024879  mov     r9d, ebx
0x18002487c  lea     r8, aGetcurrenttoke; "GetCurrentToken: OpenProcessToken faile"...
0x180024883  mov     edx, 0Ch; dwFlags
0x180024888  mov     ecx, eax; dwTraceID
0x18002488a  call    cs:__imp_TracePrintfExA
0x180024890  mov     rcx, cs:WPP_GLOBAL_Control
0x180024897  cmp     rcx, rbp
0x18002489a  jz      loc_1800247A3
0x1800248a0  test    byte ptr [rcx+1Ch], 4
0x1800248a4  jz      loc_1800247A3
0x1800248aa  cmp     byte ptr [rcx+19h], 6
0x1800248ae  jb      loc_1800247A3
0x1800248b4  mov     edx, 27h ; '''
0x1800248b9  mov     rcx, [rcx+10h]
0x1800248bd  mov     r9d, ebx
0x1800248c0  mov     r8, r14
0x1800248c3  call    WPP_SF_d
0x1800248c8  jmp     loc_1800247A3
0x1800248cd  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800248d3  cmp     ecx, 0FFFFFFFFh
0x1800248d6  jz      short loc_1800248ED
0x1800248d8  mov     r9d, ebx
0x1800248db  lea     r8, aOpenthreadtoke; "OpenThreadToken failed with %d"
0x1800248e2  mov     edx, 0Ch; dwFlags
0x1800248e7  call    cs:__imp_TracePrintfExA
0x1800248ed  test    ebx, ebx
0x1800248ef  jz      short loc_180024921
0x1800248f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248f8  cmp     rcx, rbp
0x1800248fb  jz      loc_1800247A3
0x180024901  test    byte ptr [rcx+1Ch], 4
0x180024905  jz      short loc_180024928
0x180024907  cmp     byte ptr [rcx+19h], 2
0x18002490b  jb      short loc_180024928
0x18002490d  mov     rcx, [rcx+10h]
0x180024911  mov     edx, 28h ; '('
0x180024916  mov     r9d, ebx
0x180024919  mov     r8, r14
0x18002491c  call    WPP_SF_d
0x180024921  mov     rcx, cs:WPP_GLOBAL_Control
0x180024928  cmp     rcx, rbp
0x18002492b  jz      loc_1800247A3
0x180024931  test    byte ptr [rcx+1Ch], 4
0x180024935  jz      loc_1800247A3
0x18002493b  cmp     byte ptr [rcx+19h], 6
0x18002493f  jb      loc_1800247A3
0x180024945  mov     edx, 29h ; ')'
0x18002494a  jmp     loc_1800248B9
0x18002494f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024956  cmp     rcx, rbp
0x180024959  jz      short loc_18002497B
0x18002495b  test    byte ptr [rcx+1Ch], 4
0x18002495f  jz      short loc_18002497B
0x180024961  cmp     byte ptr [rcx+19h], 6
0x180024965  jb      short loc_18002497B
0x180024967  mov     rcx, [rcx+10h]
0x18002496b  mov     edx, 2Ah ; '*'
0x180024970  xor     r9d, r9d
0x180024973  mov     r8, r14
0x180024976  call    WPP_SF_d
0x18002497b  xor     eax, eax
0x18002497d  add     rsp, 28h
0x180024981  pop     r14
0x180024983  pop     rdi
0x180024984  pop     rbp
0x180024985  pop     rbx
0x180024986  retn
```
