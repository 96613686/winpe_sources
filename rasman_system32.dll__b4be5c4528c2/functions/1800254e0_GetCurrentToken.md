# GetCurrentToken

- ea: `0x1800254e0`
- end: `0x180025792`
- name: `GetCurrentToken`
- size: `690`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180025bf8`

## callees

- `0x180021ae4`
- `0x180021b14`
- `0x1800254e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800255fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800255fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002558b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002558b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025613`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025613`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800255a6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800255a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800255ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800255ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025627`
- `rtutils!TracePrintfExA` at `0x180025571`
- `rtutils!TracePrintfExA` at `0x180025688`
- `rtutils!TracePrintfExA` at `0x1800256eb`
- `rtutils!TracePrintfExA` at `0x180025571`
- `rtutils!TracePrintfExA` at `0x180025688`
- `rtutils!TracePrintfExA` at `0x1800256eb`

## string_xrefs

- `0x180025565`: `GetCurrentToken: Invalid token pointer`
- `0x18002567a`: `GetCurrentToken: OpenProcessToken failed with %d`
- `0x1800256df`: `OpenThreadToken failed with %d`

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
0x1800254e0  push    rbx
0x1800254e2  push    rbp
0x1800254e3  push    rdi
0x1800254e4  push    r14
0x1800254e6  sub     rsp, 28h
0x1800254ea  mov     rdi, rcx
0x1800254ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254f4  lea     rbp, WPP_GLOBAL_Control
0x1800254fb  lea     r14, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x180025502  cmp     rcx, rbp
0x180025505  jz      short loc_18002552F
0x180025507  test    byte ptr [rcx+1Ch], 4
0x18002550b  jz      short loc_18002552F
0x18002550d  cmp     byte ptr [rcx+19h], 6
0x180025511  jb      short loc_18002552F
0x180025513  mov     rcx, [rcx+10h]
0x180025517  mov     edx, 23h ; '#'
0x18002551c  mov     r8, r14
0x18002551f  lea     r9d, [rdx-1Bh]
0x180025523  call    WPP_SF_d
0x180025528  mov     rcx, cs:WPP_GLOBAL_Control
0x18002552f  test    rdi, rdi
0x180025532  jnz     short loc_180025584
0x180025534  lea     ebx, [rdi+57h]
0x180025537  cmp     rcx, rbp
0x18002553a  jz      short loc_18002555A
0x18002553c  test    byte ptr [rcx+1Ch], 4
0x180025540  jz      short loc_18002555A
0x180025542  cmp     byte ptr [rcx+19h], 2
0x180025546  jb      short loc_18002555A
0x180025548  mov     rcx, [rcx+10h]
0x18002554c  lea     edx, [rdi+24h]
0x18002554f  mov     r9d, ebx
0x180025552  mov     r8, r14
0x180025555  call    WPP_SF_d
0x18002555a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180025560  cmp     ecx, 0FFFFFFFFh
0x180025563  jz      short loc_18002557D
0x180025565  lea     r8, aGetcurrenttoke_0; "GetCurrentToken: Invalid token pointer"
0x18002556c  mov     edx, 0Ch; dwFlags
0x180025571  call    cs:__imp_TracePrintfExA
0x180025578  nop     dword ptr [rax+rax+00h]
0x18002557d  mov     eax, ebx
0x18002557f  jmp     loc_180025787
0x180025584  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18002558b  call    cs:__imp_GetCurrentThread
0x180025592  nop     dword ptr [rax+rax+00h]
0x180025597  mov     edx, 8; DesiredAccess
0x18002559c  mov     r9, rdi; TokenHandle
0x18002559f  mov     rcx, rax; ThreadHandle
0x1800255a2  lea     r8d, [rdx-7]; OpenAsSelf
0x1800255a6  call    cs:__imp_OpenThreadToken
0x1800255ad  nop     dword ptr [rax+rax+00h]
0x1800255b2  test    eax, eax
0x1800255b4  jnz     loc_180025759
0x1800255ba  call    cs:__imp_GetLastError
0x1800255c1  nop     dword ptr [rax+rax+00h]
0x1800255c6  mov     ebx, eax
0x1800255c8  cmp     eax, 3F0h
0x1800255cd  jnz     loc_1800256D1
0x1800255d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255da  cmp     rcx, rbp
0x1800255dd  jz      short loc_1800255FC
0x1800255df  test    byte ptr [rcx+1Ch], 4
0x1800255e3  jz      short loc_1800255FC
0x1800255e5  cmp     byte ptr [rcx+19h], 5
0x1800255e9  jb      short loc_1800255FC
0x1800255eb  mov     rcx, [rcx+10h]
0x1800255ef  mov     edx, 25h ; '%'
0x1800255f4  mov     r8, r14
0x1800255f7  call    WPP_SF_
0x1800255fc  call    cs:__imp_GetCurrentProcess
0x180025603  nop     dword ptr [rax+rax+00h]
0x180025608  mov     r8, rdi; TokenHandle
0x18002560b  mov     edx, 8; DesiredAccess
0x180025610  mov     rcx, rax; ProcessHandle
0x180025613  call    cs:__imp_OpenProcessToken
0x18002561a  nop     dword ptr [rax+rax+00h]
0x18002561f  test    eax, eax
0x180025621  jnz     loc_180025759
0x180025627  call    cs:__imp_GetLastError
0x18002562e  nop     dword ptr [rax+rax+00h]
0x180025633  mov     ebx, eax
0x180025635  test    eax, eax
0x180025637  jz      short loc_180025665
0x180025639  mov     rcx, cs:WPP_GLOBAL_Control
0x180025640  cmp     rcx, rbp
0x180025643  jz      short loc_18002566C
0x180025645  test    byte ptr [rcx+1Ch], 4
0x180025649  jz      short loc_18002566C
0x18002564b  cmp     byte ptr [rcx+19h], 2
0x18002564f  jb      short loc_18002566C
0x180025651  mov     rcx, [rcx+10h]
0x180025655  mov     edx, 26h ; '&'
0x18002565a  mov     r9d, eax
0x18002565d  mov     r8, r14
0x180025660  call    WPP_SF_d
0x180025665  mov     rcx, cs:WPP_GLOBAL_Control
0x18002566c  mov     eax, cs:g_dwTraceId
0x180025672  cmp     eax, 0FFFFFFFFh
0x180025675  jz      short loc_18002569B
0x180025677  mov     r9d, ebx
0x18002567a  lea     r8, aGetcurrenttoke; "GetCurrentToken: OpenProcessToken faile"...
0x180025681  mov     edx, 0Ch; dwFlags
0x180025686  mov     ecx, eax; dwTraceID
0x180025688  call    cs:__imp_TracePrintfExA
0x18002568f  nop     dword ptr [rax+rax+00h]
0x180025694  mov     rcx, cs:WPP_GLOBAL_Control
0x18002569b  cmp     rcx, rbp
0x18002569e  jz      loc_18002557D
0x1800256a4  test    byte ptr [rcx+1Ch], 4
0x1800256a8  jz      loc_18002557D
0x1800256ae  cmp     byte ptr [rcx+19h], 6
0x1800256b2  jb      loc_18002557D
0x1800256b8  mov     edx, 27h ; '''
0x1800256bd  mov     rcx, [rcx+10h]
0x1800256c1  mov     r9d, ebx
0x1800256c4  mov     r8, r14
0x1800256c7  call    WPP_SF_d
0x1800256cc  jmp     loc_18002557D
0x1800256d1  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800256d7  cmp     ecx, 0FFFFFFFFh
0x1800256da  jz      short loc_1800256F7
0x1800256dc  mov     r9d, ebx
0x1800256df  lea     r8, aOpenthreadtoke; "OpenThreadToken failed with %d"
0x1800256e6  mov     edx, 0Ch; dwFlags
0x1800256eb  call    cs:__imp_TracePrintfExA
0x1800256f2  nop     dword ptr [rax+rax+00h]
0x1800256f7  test    ebx, ebx
0x1800256f9  jz      short loc_18002572B
0x1800256fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180025702  cmp     rcx, rbp
0x180025705  jz      loc_18002557D
0x18002570b  test    byte ptr [rcx+1Ch], 4
0x18002570f  jz      short loc_180025732
0x180025711  cmp     byte ptr [rcx+19h], 2
0x180025715  jb      short loc_180025732
0x180025717  mov     rcx, [rcx+10h]
0x18002571b  mov     edx, 28h ; '('
0x180025720  mov     r9d, ebx
0x180025723  mov     r8, r14
0x180025726  call    WPP_SF_d
0x18002572b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025732  cmp     rcx, rbp
0x180025735  jz      loc_18002557D
0x18002573b  test    byte ptr [rcx+1Ch], 4
0x18002573f  jz      loc_18002557D
0x180025745  cmp     byte ptr [rcx+19h], 6
0x180025749  jb      loc_18002557D
0x18002574f  mov     edx, 29h ; ')'
0x180025754  jmp     loc_1800256BD
0x180025759  mov     rcx, cs:WPP_GLOBAL_Control
0x180025760  cmp     rcx, rbp
0x180025763  jz      short loc_180025785
0x180025765  test    byte ptr [rcx+1Ch], 4
0x180025769  jz      short loc_180025785
0x18002576b  cmp     byte ptr [rcx+19h], 6
0x18002576f  jb      short loc_180025785
0x180025771  mov     rcx, [rcx+10h]
0x180025775  mov     edx, 2Ah ; '*'
0x18002577a  xor     r9d, r9d
0x18002577d  mov     r8, r14
0x180025780  call    WPP_SF_d
0x180025785  xor     eax, eax
0x180025787  add     rsp, 28h
0x18002578b  pop     r14
0x18002578d  pop     rdi
0x18002578e  pop     rbp
0x18002578f  pop     rbx
0x180025790  retn
```
