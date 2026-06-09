# AddProcessInfo

- ea: `0x180039b28`
- end: `0x180039f16`
- name: `AddProcessInfo`
- size: `1006`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180029300`
- `0x18004946c`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180005c40`
- `0x180038b8c`
- `0x180039b28`
- `0x180040a7c`
- `0x180042ef4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039d3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039d53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039d3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039d53`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180039c0e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180039cb4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180039c0e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180039cb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039bbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039cc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039bbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039cc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039d1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039d1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039e9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e9432`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039e9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e9432`
- `RPCRT4!RpcImpersonateClient` at `0x180039c64`
- `RPCRT4!RpcImpersonateClient` at `0x180039c64`
- `RPCRT4!RpcRevertToSelf` at `0x180039d04`
- `RPCRT4!RpcRevertToSelf` at `0x180039d04`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039b7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039b7c`

## pseudocode

```c
_QWORD *__fastcall AddProcessInfo(DWORD dwProcessId)
{
  _QWORD *v2; // rax
  _QWORD *v3; // r15
  struct _LIST_ENTRY *v4; // rcx
  struct _LIST_ENTRY *Flink; // rbx
  DWORD v6; // eax
  HANDLE v7; // rax
  DWORD LastError; // eax
  unsigned int v9; // eax
  HANDLE v10; // rax
  DWORD v11; // eax
  DWORD CurrentProcessId; // eax
  BOOL v13; // ecx
  _QWORD *v14; // rax
  __int64 v15; // r9

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 82, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, dwProcessId);
  }
  v2 = LocalAlloc(0x40u, 0x58u);
  v3 = v2;
  if ( v2 )
  {
    *((_DWORD *)v2 + 6) = dwProcessId;
    InitializeEventQueue(v2 + 4, dwProcessId);
    v7 = OpenProcess(0x1000u, 0, dwProcessId);
    v3[2] = v7;
    if ( !v7 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 84, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, LastError);
      }
      v9 = RpcImpersonateClient(0);
      if ( v9 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 85, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v9);
        }
      }
      else
      {
        v10 = OpenProcess(0x1000u, 0, dwProcessId);
        v3[2] = v10;
        if ( !v10 )
        {
          v11 = GetLastError();
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 86, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v11);
          }
        }
        RpcRevertToSelf();
      }
    }
    EnterCriticalSection(&g_csClientProcessBlock);
    v13 = 1;
    if ( g_dwAttachedCount || GetCurrentProcessId() == dwProcessId )
    {
      if ( g_dwAttachedCount != 1 || (CurrentProcessId = GetCurrentProcessId(), !FindProcess(CurrentProcessId)) )
        v13 = 0;
    }
    v14 = (_QWORD *)qword_180110D38;
    *v3 = &ClientProcessBlockList;
    v3[1] = v14;
    *v14 = v3;
    qword_180110D38 = (__int64)v3;
    if ( v13 && !g_pDeadClientTimeoutElement )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 87, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
      }
      g_pDeadClientTimeoutElement = AddTimeoutElement(BackGroundCleanUp, 0, 0, 10);
    }
    v15 = (unsigned int)++g_dwAttachedCount;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 88, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v15);
    }
    LeaveCriticalSection(&g_csClientProcessBlock);
    goto LABEL_44;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v3;
  if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    Flink = WPP_GLOBAL_Control[1].Flink;
    v6 = GetLastError();
    WPP_SF_Dd(Flink, 83, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, dwProcessId, v6);
LABEL_44:
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v4[1].Blink) & 0x2000) != 0
    && BYTE1(v4[1].Blink) >= 6u )
  {
    WPP_SF_(v4[1].Flink, 91, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
  }
  return v3;
}

```

## disassembly

```asm
0x180039b28  push    rbx
0x180039b2a  push    rsi
0x180039b2b  push    rdi
0x180039b2c  push    r12
0x180039b2e  push    r14
0x180039b30  push    r15
0x180039b32  sub     rsp, 48h
0x180039b36  mov     r14d, ecx
0x180039b39  lea     rsi, WPP_GLOBAL_Control
0x180039b40  mov     rcx, cs:WPP_GLOBAL_Control
0x180039b47  mov     edi, 2000h
0x180039b4c  cmp     rcx, rsi
0x180039b4f  jz      short loc_180039B74
0x180039b51  test    [rcx+1Ch], edi
0x180039b54  jz      short loc_180039B74
0x180039b56  cmp     byte ptr [rcx+19h], 6
0x180039b5a  jb      short loc_180039B74
0x180039b5c  mov     edx, 52h ; 'R'
0x180039b61  mov     r9d, r14d
0x180039b64  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180039b6b  mov     rcx, [rcx+10h]
0x180039b6f  call    WPP_SF_d
0x180039b74  mov     edx, 58h ; 'X'; uBytes
0x180039b79  lea     ecx, [rdx-18h]; uFlags
0x180039b7c  call    cs:__imp_LocalAlloc
0x180039b83  nop     dword ptr [rax+rax+00h]
0x180039b88  mov     r15, rax
0x180039b8b  mov     [rsp+78h+arg_8], rax
0x180039b93  test    rax, rax
0x180039b96  jnz     short loc_180039BEA
0x180039b98  mov     rcx, cs:WPP_GLOBAL_Control
0x180039b9f  cmp     rcx, rsi
0x180039ba2  jz      loc_180039F04
0x180039ba8  test    [rcx+1Ch], edi
0x180039bab  jz      loc_180039EDF
0x180039bb1  cmp     byte ptr [rcx+19h], 2
0x180039bb5  jb      loc_180039EDF
0x180039bbb  mov     rbx, [rcx+10h]
0x180039bbf  call    cs:__imp_GetLastError
0x180039bc6  nop     dword ptr [rax+rax+00h]
0x180039bcb  lea     edx, [r15+53h]
0x180039bcf  mov     [rsp+78h+var_58], eax
0x180039bd3  mov     r9d, r14d
0x180039bd6  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180039bdd  mov     rcx, rbx
0x180039be0  call    WPP_SF_Dd
0x180039be5  jmp     loc_180039ED8
0x180039bea  xor     r12d, r12d
0x180039bed  mov     [rsp+78h+var_44], r12d
0x180039bf2  mov     [rax+18h], r14d
0x180039bf6  lea     rcx, [rax+20h]
0x180039bfa  mov     edx, r14d
0x180039bfd  call    InitializeEventQueue
0x180039c02  mov     r8d, r14d; dwProcessId
0x180039c05  xor     edx, edx; bInheritHandle
0x180039c07  mov     ebx, 1000h
0x180039c0c  mov     ecx, ebx; dwDesiredAccess
0x180039c0e  call    cs:__imp_OpenProcess
0x180039c15  nop     dword ptr [rax+rax+00h]
0x180039c1a  mov     [r15+10h], rax
0x180039c1e  test    rax, rax
0x180039c21  jnz     loc_180039D10
0x180039c27  call    cs:__imp_GetLastError
0x180039c2e  nop     dword ptr [rax+rax+00h]
0x180039c33  mov     rcx, cs:WPP_GLOBAL_Control
0x180039c3a  cmp     rcx, rsi
0x180039c3d  jz      short loc_180039C62
0x180039c3f  test    [rcx+1Ch], edi
0x180039c42  jz      short loc_180039C62
0x180039c44  cmp     byte ptr [rcx+19h], 3
0x180039c48  jb      short loc_180039C62
0x180039c4a  lea     edx, [r12+54h]
0x180039c4f  mov     r9d, eax
0x180039c52  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180039c59  mov     rcx, [rcx+10h]
0x180039c5d  call    WPP_SF_d
0x180039c62  xor     ecx, ecx; BindingHandle
0x180039c64  call    cs:__imp_RpcImpersonateClient
0x180039c6b  nop     dword ptr [rax+rax+00h]
0x180039c70  test    eax, eax
0x180039c72  jz      short loc_180039CAD
0x180039c74  mov     rcx, cs:WPP_GLOBAL_Control
0x180039c7b  cmp     rcx, rsi
0x180039c7e  jz      loc_180039D10
0x180039c84  test    [rcx+1Ch], edi
0x180039c87  jz      loc_180039D10
0x180039c8d  cmp     byte ptr [rcx+19h], 3
0x180039c91  jb      short loc_180039D10
0x180039c93  mov     edx, 55h ; 'U'
0x180039c98  mov     r9d, eax
0x180039c9b  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180039ca2  mov     rcx, [rcx+10h]
0x180039ca6  call    WPP_SF_d
0x180039cab  jmp     short loc_180039D10
0x180039cad  mov     r8d, r14d; dwProcessId
0x180039cb0  xor     edx, edx; bInheritHandle
0x180039cb2  mov     ecx, ebx; dwDesiredAccess
0x180039cb4  call    cs:__imp_OpenProcess
0x180039cbb  nop     dword ptr [rax+rax+00h]
0x180039cc0  mov     [r15+10h], rax
0x180039cc4  test    rax, rax
0x180039cc7  jnz     short loc_180039D04
0x180039cc9  call    cs:__imp_GetLastError
0x180039cd0  nop     dword ptr [rax+rax+00h]
0x180039cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180039cdc  cmp     rcx, rsi
0x180039cdf  jz      short loc_180039D04
0x180039ce1  test    [rcx+1Ch], edi
0x180039ce4  jz      short loc_180039D04
0x180039ce6  cmp     byte ptr [rcx+19h], 2
0x180039cea  jb      short loc_180039D04
0x180039cec  mov     edx, 56h ; 'V'
0x180039cf1  mov     r9d, eax
0x180039cf4  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180039cfb  mov     rcx, [rcx+10h]
0x180039cff  call    WPP_SF_d
0x180039d04  call    cs:__imp_RpcRevertToSelf
0x180039d0b  nop     dword ptr [rax+rax+00h]
0x180039d10  mov     [rsp+78h+var_48], r12d
0x180039d15  lea     rcx, g_csClientProcessBlock; lpCriticalSection
0x180039d1c  call    cs:__imp_EnterCriticalSection
0x180039d23  nop     dword ptr [rax+rax+00h]
0x180039d28  mov     ebx, 1
0x180039d2d  mov     [rsp+78h+var_48], ebx
0x180039d31  cmp     cs:g_dwAttachedCount, 0
0x180039d38  jnz     short loc_180039D4B
0x180039d3a  call    cs:__imp_GetCurrentProcessId
0x180039d41  nop     dword ptr [rax+rax+00h]
0x180039d46  cmp     eax, r14d
0x180039d49  jnz     short loc_180039D6B
0x180039d4b  cmp     cs:g_dwAttachedCount, ebx
0x180039d51  jnz     short loc_180039D6F
0x180039d53  call    cs:__imp_GetCurrentProcessId
0x180039d5a  nop     dword ptr [rax+rax+00h]
0x180039d5f  mov     ecx, eax
0x180039d61  call    FindProcess
0x180039d66  test    rax, rax
0x180039d69  jz      short loc_180039D6F
0x180039d6b  mov     ecx, ebx
0x180039d6d  jmp     short loc_180039D71
0x180039d6f  xor     ecx, ecx
0x180039d71  mov     rax, cs:qword_180110D38
0x180039d78  lea     rdx, ClientProcessBlockList
0x180039d7f  mov     [r15], rdx
0x180039d82  mov     [r15+8], rax
0x180039d86  mov     [rax], r15
0x180039d89  mov     cs:qword_180110D38, r15
0x180039d90  test    ecx, ecx
0x180039d92  jz      short loc_180039DE8
0x180039d94  cmp     cs:g_pDeadClientTimeoutElement, 0
0x180039d9c  jnz     short loc_180039DE8
0x180039d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180039da5  cmp     rcx, rsi
0x180039da8  jz      short loc_180039DCA
0x180039daa  test    [rcx+1Ch], edi
0x180039dad  jz      short loc_180039DCA
0x180039daf  cmp     byte ptr [rcx+19h], 5
0x180039db3  jb      short loc_180039DCA
0x180039db5  mov     edx, 57h ; 'W'
0x180039dba  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180039dc1  mov     rcx, [rcx+10h]
0x180039dc5  call    WPP_SF_
0x180039dca  mov     r9d, 0Ah
0x180039dd0  xor     r8d, r8d
0x180039dd3  xor     edx, edx
0x180039dd5  lea     rcx, BackGroundCleanUp
0x180039ddc  call    AddTimeoutElement
0x180039de1  mov     cs:g_pDeadClientTimeoutElement, rax
0x180039de8  mov     r9d, cs:g_dwAttachedCount
0x180039def  add     r9d, ebx
0x180039df2  mov     cs:g_dwAttachedCount, r9d
0x180039df9  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e00  cmp     rcx, rsi
0x180039e03  jz      short loc_180039E2C
0x180039e05  test    [rcx+1Ch], edi
0x180039e08  jz      short loc_180039E2C
0x180039e0a  cmp     byte ptr [rcx+19h], 4
0x180039e0e  jb      short loc_180039E2C
0x180039e10  mov     edx, 58h ; 'X'
0x180039e15  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180039e1c  mov     rcx, [rcx+10h]
0x180039e20  call    WPP_SF_d
0x180039e25  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e2c  jmp     short loc_180039E92
0x180039e2e  mov     r12d, eax
0x180039e31  mov     [rsp+78h+var_44], eax
0x180039e35  test    eax, eax
0x180039e37  jz      short loc_180039E73
0x180039e39  lea     rax, WPP_GLOBAL_Control
0x180039e40  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e47  cmp     rcx, rax
0x180039e4a  jz      short loc_180039E7A
0x180039e4c  test    dword ptr [rcx+1Ch], 2000h
0x180039e53  jz      short loc_180039E7A
0x180039e55  cmp     byte ptr [rcx+19h], 2
0x180039e59  jb      short loc_180039E7A
0x180039e5b  mov     edx, 59h ; 'Y'
0x180039e60  mov     r9d, r12d
0x180039e63  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180039e6a  mov     rcx, [rcx+10h]
0x180039e6e  call    WPP_SF_d
0x180039e73  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e7a  lea     rsi, WPP_GLOBAL_Control
0x180039e81  mov     edi, 2000h
0x180039e86  mov     ebx, [rsp+78h+var_48]
0x180039e8a  mov     r15, [rsp+78h+arg_8]
0x180039e92  test    ebx, ebx
0x180039e94  jz      short loc_180039EAB
0x180039e96  lea     rcx, g_csClientProcessBlock; lpCriticalSection
0x180039e9d  call    cs:__imp_LeaveCriticalSection
0x180039ea4  nop     dword ptr [rax+rax+00h]
0x180039ea9  jmp     short loc_180039ED8
0x180039eab  test    r12d, r12d
0x180039eae  jz      short loc_180039EDF
0x180039eb0  cmp     rcx, rsi
0x180039eb3  jz      short loc_180039F04
0x180039eb5  test    [rcx+1Ch], edi
0x180039eb8  jz      short loc_180039EDF
0x180039eba  cmp     byte ptr [rcx+19h], 2
0x180039ebe  jb      short loc_180039EDF
0x180039ec0  mov     edx, 5Ah ; 'Z'
0x180039ec5  mov     r9d, r12d
0x180039ec8  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180039ecf  mov     rcx, [rcx+10h]
0x180039ed3  call    WPP_SF_d
0x180039ed8  mov     rcx, cs:WPP_GLOBAL_Control
0x180039edf  cmp     rcx, rsi
0x180039ee2  jz      short loc_180039F04
0x180039ee4  test    [rcx+1Ch], edi
0x180039ee7  jz      short loc_180039F04
0x180039ee9  cmp     byte ptr [rcx+19h], 6
0x180039eed  jb      short loc_180039F04
0x180039eef  mov     edx, 5Bh ; '['
0x180039ef4  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180039efb  mov     rcx, [rcx+10h]
0x180039eff  call    WPP_SF_
0x180039f04  mov     rax, r15
0x180039f07  add     rsp, 48h
0x180039f0b  pop     r15
0x180039f0d  pop     r14
0x180039f0f  pop     r12
0x180039f11  pop     rdi
0x180039f12  pop     rsi
0x180039f13  pop     rbx
0x180039f14  retn
0x1800e941c  push    rbp
0x1800e941e  sub     rsp, 30h
0x1800e9422  mov     rbp, rdx
0x1800e9425  cmp     dword ptr [rbp+30h], 0
0x1800e9429  jz      short loc_1800E9440
0x1800e942b  lea     rcx, g_csClientProcessBlock; lpCriticalSection
0x1800e9432  call    cs:__imp_LeaveCriticalSection
0x1800e9439  nop     dword ptr [rax+rax+00h]
0x1800e943e  jmp     short loc_1800E9481
0x1800e9440  mov     r9d, [rbp+34h]
0x1800e9444  test    r9d, r9d
0x1800e9447  jz      short loc_1800E9481
0x1800e9449  lea     rax, WPP_GLOBAL_Control
0x1800e9450  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9457  cmp     rcx, rax
0x1800e945a  jz      short loc_1800E9481
0x1800e945c  test    dword ptr [rcx+1Ch], 2000h
0x1800e9463  jz      short loc_1800E9481
0x1800e9465  cmp     byte ptr [rcx+19h], 2
0x1800e9469  jb      short loc_1800E9481
0x1800e946b  mov     edx, 5Ah ; 'Z'
0x1800e9470  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x1800e9477  mov     rcx, [rcx+10h]
0x1800e947b  call    WPP_SF_d
0x1800e9480  nop
0x1800e9481  add     rsp, 30h
0x1800e9485  pop     rbp
0x1800e9486  retn
```
