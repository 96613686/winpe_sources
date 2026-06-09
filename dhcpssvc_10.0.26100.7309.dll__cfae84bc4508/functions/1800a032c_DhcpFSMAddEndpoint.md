# DhcpFSMAddEndpoint

- ea: `0x1800a032c`
- end: `0x1800a071a`
- name: `DhcpFSMAddEndpoint`
- size: `1006`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task`

## callers

- `0x18008474c`
- `0x180085680`

## callees

- `0x18001e08c`
- `0x180025b98`
- `0x1800947e4`
- `0x1800948b0`
- `0x1800a032c`
- `0x1800a2e30`
- `0x1800a8b5c`
- `0x1800a9270`
- `0x1800a9374`
- `0x1800ad008`
- `0x1800ad31c`
- `0x1800af1a0`
- `0x1800bf9cc`
- `0x1800cb6e0`
- `0x1800cbae8`
- `0x1800cbce0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800a03a8`
- `KERNEL32!HeapAlloc` at `0x1800a03a8`
- `KERNEL32!GetProcessHeap` at `0x1800a06f5`
- `KERNEL32!GetProcessHeap` at `0x1800a06f5`
- `KERNEL32!DeleteCriticalSection` at `0x1800a03ff`
- `KERNEL32!DeleteCriticalSection` at `0x1800a0412`
- `KERNEL32!DeleteCriticalSection` at `0x1800a03ff`
- `KERNEL32!DeleteCriticalSection` at `0x1800a0412`
- `KERNEL32!InitializeCriticalSection` at `0x1800a03cd`
- `KERNEL32!InitializeCriticalSection` at `0x1800a03e0`
- `KERNEL32!InitializeCriticalSection` at `0x1800a03cd`
- `KERNEL32!InitializeCriticalSection` at `0x1800a03e0`
- `KERNEL32!EnterCriticalSection` at `0x1800a04a6`
- `KERNEL32!EnterCriticalSection` at `0x1800a0535`
- `KERNEL32!EnterCriticalSection` at `0x1800a0555`
- `KERNEL32!EnterCriticalSection` at `0x1800a069c`
- `KERNEL32!EnterCriticalSection` at `0x1800a04a6`
- `KERNEL32!EnterCriticalSection` at `0x1800a0535`
- `KERNEL32!EnterCriticalSection` at `0x1800a0555`
- `KERNEL32!EnterCriticalSection` at `0x1800a069c`
- `KERNEL32!LeaveCriticalSection` at `0x1800a04c7`
- `KERNEL32!LeaveCriticalSection` at `0x1800a04e7`
- `KERNEL32!LeaveCriticalSection` at `0x1800a057a`
- `KERNEL32!LeaveCriticalSection` at `0x1800a0596`
- `KERNEL32!LeaveCriticalSection` at `0x1800a0616`
- `KERNEL32!LeaveCriticalSection` at `0x1800a0660`
- `KERNEL32!LeaveCriticalSection` at `0x1800a06dc`
- `KERNEL32!LeaveCriticalSection` at `0x1800a04c7`
- `KERNEL32!LeaveCriticalSection` at `0x1800a04e7`
- `KERNEL32!LeaveCriticalSection` at `0x1800a057a`
- `KERNEL32!LeaveCriticalSection` at `0x1800a0596`
- `KERNEL32!LeaveCriticalSection` at `0x1800a0616`
- `KERNEL32!LeaveCriticalSection` at `0x1800a0660`
- `KERNEL32!LeaveCriticalSection` at `0x1800a06dc`
- `KERNEL32!HeapFree` at `0x1800a042e`
- `KERNEL32!HeapFree` at `0x1800a0709`
- `KERNEL32!HeapFree` at `0x1800a042e`
- `KERNEL32!HeapFree` at `0x1800a0709`

## pseudocode

```c
__int64 __fastcall DhcpFSMAddEndpoint(__int64 a1, unsigned int a2, int a3)
{
  __int64 result; // rax
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  __int64 v8; // rdx
  __int64 *v9; // r8
  __int64 String; // rax
  int v11; // edx
  __int64 *v12; // r8
  struct _RTL_CRITICAL_SECTION *v13; // rax
  LPCRITICAL_SECTION v14; // rax
  LONG *p_LockCount; // rdx
  unsigned int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rbx
  struct _RTL_CRITICAL_SECTION *v20; // rcx
  unsigned int RegistryWithSharedSecretInfo; // eax
  bool v22; // zf
  unsigned int v23; // eax
  struct _RTL_CRITICAL_SECTION *v24; // rcx
  LONG LockCount; // ecx
  unsigned int v26; // eax
  LONG *v27; // rcx
  void *v28; // rdi
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-10h] BYREF
  __int64 v31; // [rsp+28h] [rbp-8h] BYREF
  int v32; // [rsp+50h] [rbp+20h] BYREF
  int v33; // [rsp+68h] [rbp+38h] BYREF

  lpMem = 0;
  v32 = 0;
  v33 = 0;
  if ( !a1 )
    return 87;
  v7 = g_FailoverEndpoints;
  if ( !g_FailoverEndpoints )
  {
    v8 = 0;
    v9 = FailoverRejectReasonDescription;
    do
    {
      String = GetString((unsigned int)(v8 + 1349), v8, v9);
      v8 = (unsigned int)(v11 + 1);
      *v12 = String;
      v9 = v12 + 1;
    }
    while ( (unsigned int)v8 < 0x19 );
    v13 = (struct _RTL_CRITICAL_SECTION *)HeapAlloc(gDhcpHeap, 8u, 0x40u);
    g_FailoverEndpoints = v13;
    if ( !v13 )
      return 8;
    InitializeCriticalSection(v13);
    InitializeCriticalSection(&gXidCS);
    v14 = g_FailoverEndpoints;
    p_LockCount = &g_FailoverEndpoints[1].LockCount;
    if ( g_FailoverEndpoints == (LPCRITICAL_SECTION)-48LL )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)0xFFFFFFFFFFFFFFD0LL);
      DeleteCriticalSection(&gXidCS);
      HeapFree(gDhcpHeap, 0, g_FailoverEndpoints);
      g_FailoverEndpoints = 0;
      return 87;
    }
    g_FailoverEndpoints[1].RecursionCount = 0;
    *p_LockCount = 0;
    *((_QWORD *)p_LockCount + 1) = 0;
    LODWORD(v14[1].DebugInfo) |= 8u;
    v16 = MessageQInitialize(&gFailoverFreePacketPool, 0, 1);
    if ( v16
      || (LODWORD(g_FailoverEndpoints[1].DebugInfo) |= 4u, (v16 = DhcpBNDInitialize()) != 0)
      || (LODWORD(g_FailoverEndpoints[1].DebugInfo) |= 1u, (v16 = DhcpCMInitialize()) != 0) )
    {
      DhcpFSMModuleCleanup();
      return v16;
    }
    v7 = g_FailoverEndpoints;
    LODWORD(g_FailoverEndpoints[1].DebugInfo) |= 2u;
  }
  EnterCriticalSection(v7);
  if ( g_FailoverEndpoints != (LPCRITICAL_SECTION)-48LL && g_FailoverEndpoints[1].LockCount >= 0x1Fu )
  {
    LeaveCriticalSection(g_FailoverEndpoints);
    return 20128;
  }
  LeaveCriticalSection(g_FailoverEndpoints);
  v17 = *(_QWORD *)(a1 + 56);
  if ( !v17 || (v18 = 0, !*(_DWORD *)v17) )
  {
LABEL_23:
    EnterCriticalSection(g_FailoverEndpoints);
    v19 = *(_QWORD *)(a1 + 32);
    v32 = 0;
    v31 = 0;
    EnterCriticalSection(g_FailoverEndpoints);
    v16 = FSMGetElement(v19, &v31, &v32);
    LeaveCriticalSection(g_FailoverEndpoints);
    if ( !v16 )
    {
      v16 = 20114;
LABEL_25:
      v20 = g_FailoverEndpoints;
LABEL_26:
      LeaveCriticalSection(v20);
      return v16;
    }
    if ( v16 != 20115 )
      goto LABEL_25;
    if ( !a3 )
    {
      if ( *(_QWORD *)(a1 + 72) )
      {
        RegistryWithSharedSecretInfo = CreateRegistryWithSharedSecretInfo(a1);
        v22 = RegistryWithSharedSecretInfo == 0;
      }
      else
      {
        RegistryWithSharedSecretInfo = DhcpRegDeleteKey(DhcpGlobalServicePrivateData, *(const WCHAR **)(a1 + 32));
        v22 = (RegistryWithSharedSecretInfo & 0xFFFFFFFD) == 0;
      }
      v16 = RegistryWithSharedSecretInfo;
      if ( !v22 )
        goto LABEL_25;
    }
    v23 = FSMFailoverRelationshipInit(&lpMem, a1, a2);
    v20 = g_FailoverEndpoints;
    v16 = v23;
    if ( v23 )
      goto LABEL_26;
    v16 = MemArrayAddElement((unsigned int *)&g_FailoverEndpoints[1].LockCount, (__int64)lpMem);
    if ( v16 )
    {
      v24 = g_FailoverEndpoints;
    }
    else
    {
      if ( g_FailoverEndpoints == (LPCRITICAL_SECTION)-48LL )
        LockCount = 0;
      else
        LockCount = g_FailoverEndpoints[1].LockCount;
      v26 = InitializeFreePacketPool(LockCount);
      v24 = g_FailoverEndpoints;
      v16 = v26;
      if ( !v26 )
      {
        LeaveCriticalSection(g_FailoverEndpoints);
        v16 = InitializeFiniteStateMachine((DWORD *)lpMem);
        if ( !v16 )
          return v16;
        v27 = &g_FailoverEndpoints[1].LockCount;
        if ( g_FailoverEndpoints != (LPCRITICAL_SECTION)-48LL )
          LODWORD(v27) = *v27;
        UnInitializeFreePacketPool((unsigned int)((_DWORD)v27 - 1));
LABEL_48:
        EnterCriticalSection(g_FailoverEndpoints);
        if ( !(unsigned int)FSMGetElement(*(_QWORD *)(a1 + 32), &lpMem, &v33) )
          MemArrayDelElement(&g_FailoverEndpoints[1].LockCount, &v33, &lpMem);
        LeaveCriticalSection(g_FailoverEndpoints);
        v28 = lpMem;
        if ( lpMem )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v28);
        }
        return v16;
      }
    }
    LeaveCriticalSection(v24);
    goto LABEL_48;
  }
  while ( 1 )
  {
    result = FSMScopeInFailoverRelation(*(unsigned int *)(*(_QWORD *)(v17 + 8) + 4 * v18), &v32);
    if ( (_DWORD)result )
      return result;
    if ( v32 == 1 )
      return 20113;
    v17 = *(_QWORD *)(a1 + 56);
    v18 = (unsigned int)(v18 + 1);
    if ( (unsigned int)v18 >= *(_DWORD *)v17 )
      goto LABEL_23;
  }
}

```

## disassembly

```asm
0x1800a032c  mov     [rsp-18h+arg_8], rbx
0x1800a0331  mov     [rsp-18h+arg_10], rsi
0x1800a0336  push    rbp
0x1800a0337  push    rdi
0x1800a0338  push    r14
0x1800a033a  mov     rbp, rsp
0x1800a033d  sub     rsp, 30h
0x1800a0341  and     [rbp+lpMem], 0
0x1800a0346  mov     esi, r8d
0x1800a0349  and     [rbp+arg_0], 0
0x1800a034d  mov     r14d, edx
0x1800a0350  and     [rbp+arg_18], 0
0x1800a0354  mov     rdi, rcx
0x1800a0357  test    rcx, rcx
0x1800a035a  jnz     short loc_1800A0366
0x1800a035c  mov     eax, 57h ; 'W'
0x1800a0361  jmp     loc_1800A05A4
0x1800a0366  mov     rcx, cs:g_FailoverEndpoints
0x1800a036d  test    rcx, rcx
0x1800a0370  jnz     loc_1800A04A6
0x1800a0376  xor     edx, edx
0x1800a0378  lea     r8, FailoverRejectReasonDescription
0x1800a037f  lea     ecx, [rdx+545h]
0x1800a0385  call    GetString
0x1800a038a  inc     edx
0x1800a038c  mov     [r8], rax
0x1800a038f  lea     r8, [r8+8]
0x1800a0393  cmp     edx, 19h
0x1800a0396  jb      short loc_1800A037F
0x1800a0398  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a039f  mov     edx, 8; dwFlags
0x1800a03a4  lea     r8d, [rdx+38h]; dwBytes
0x1800a03a8  call    cs:__imp_HeapAlloc
0x1800a03af  nop     dword ptr [rax+rax+00h]
0x1800a03b4  mov     cs:g_FailoverEndpoints, rax
0x1800a03bb  test    rax, rax
0x1800a03be  jnz     short loc_1800A03CA
0x1800a03c0  mov     eax, 8
0x1800a03c5  jmp     loc_1800A05A4
0x1800a03ca  mov     rcx, rax; lpCriticalSection
0x1800a03cd  call    cs:__imp_InitializeCriticalSection
0x1800a03d4  nop     dword ptr [rax+rax+00h]
0x1800a03d9  lea     rcx, gXidCS; lpCriticalSection
0x1800a03e0  call    cs:__imp_InitializeCriticalSection
0x1800a03e7  nop     dword ptr [rax+rax+00h]
0x1800a03ec  mov     rax, cs:g_FailoverEndpoints
0x1800a03f3  lea     rdx, [rax+30h]
0x1800a03f7  test    rdx, rdx
0x1800a03fa  jnz     short loc_1800A0447
0x1800a03fc  mov     rcx, rax; lpCriticalSection
0x1800a03ff  call    cs:__imp_DeleteCriticalSection
0x1800a0406  nop     dword ptr [rax+rax+00h]
0x1800a040b  lea     rcx, gXidCS; lpCriticalSection
0x1800a0412  call    cs:__imp_DeleteCriticalSection
0x1800a0419  nop     dword ptr [rax+rax+00h]
0x1800a041e  mov     r8, cs:g_FailoverEndpoints; lpMem
0x1800a0425  xor     edx, edx; dwFlags
0x1800a0427  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a042e  call    cs:__imp_HeapFree
0x1800a0435  nop     dword ptr [rax+rax+00h]
0x1800a043a  and     cs:g_FailoverEndpoints, 0
0x1800a0442  jmp     loc_1800A035C
0x1800a0447  and     dword ptr [rdx+4], 0
0x1800a044b  lea     rcx, gFailoverFreePacketPool
0x1800a0452  and     dword ptr [rdx], 0
0x1800a0455  and     qword ptr [rdx+8], 0
0x1800a045a  xor     edx, edx
0x1800a045c  or      dword ptr [rax+28h], 8
0x1800a0460  lea     r8d, [rdx+1]
0x1800a0464  call    MessageQInitialize
0x1800a0469  mov     ebx, eax
0x1800a046b  test    eax, eax
0x1800a046d  jnz     short loc_1800A04DD
0x1800a046f  mov     rax, cs:g_FailoverEndpoints
0x1800a0476  or      dword ptr [rax+28h], 4
0x1800a047a  call    DhcpBNDInitialize
0x1800a047f  mov     ebx, eax
0x1800a0481  test    eax, eax
0x1800a0483  jnz     short loc_1800A04DD
0x1800a0485  mov     rax, cs:g_FailoverEndpoints
0x1800a048c  or      dword ptr [rax+28h], 1
0x1800a0490  call    DhcpCMInitialize
0x1800a0495  mov     ebx, eax
0x1800a0497  test    eax, eax
0x1800a0499  jnz     short loc_1800A04DD
0x1800a049b  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a04a2  or      dword ptr [rcx+28h], 2
0x1800a04a6  call    cs:__imp_EnterCriticalSection
0x1800a04ad  nop     dword ptr [rax+rax+00h]
0x1800a04b2  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a04b9  lea     rax, [rcx+30h]
0x1800a04bd  test    rax, rax
0x1800a04c0  jz      short loc_1800A04E7
0x1800a04c2  cmp     dword ptr [rax], 1Fh
0x1800a04c5  jb      short loc_1800A04E7
0x1800a04c7  call    cs:__imp_LeaveCriticalSection
0x1800a04ce  nop     dword ptr [rax+rax+00h]
0x1800a04d3  mov     eax, 4EA0h
0x1800a04d8  jmp     loc_1800A05A4
0x1800a04dd  call    DhcpFSMModuleCleanup
0x1800a04e2  jmp     loc_1800A05A2
0x1800a04e7  call    cs:__imp_LeaveCriticalSection
0x1800a04ee  nop     dword ptr [rax+rax+00h]
0x1800a04f3  mov     rcx, [rdi+38h]
0x1800a04f7  test    rcx, rcx
0x1800a04fa  jz      short loc_1800A052E
0x1800a04fc  xor     ebx, ebx
0x1800a04fe  cmp     [rcx], ebx
0x1800a0500  jbe     short loc_1800A052E
0x1800a0502  mov     rcx, [rcx+8]
0x1800a0506  lea     rdx, [rbp+arg_0]
0x1800a050a  mov     ecx, [rcx+rbx*4]
0x1800a050d  call    FSMScopeInFailoverRelation
0x1800a0512  test    eax, eax
0x1800a0514  jnz     loc_1800A05A4
0x1800a051a  cmp     [rbp+arg_0], 1
0x1800a051e  jz      loc_1800A05B8
0x1800a0524  mov     rcx, [rdi+38h]
0x1800a0528  inc     ebx
0x1800a052a  cmp     ebx, [rcx]
0x1800a052c  jb      short loc_1800A0502
0x1800a052e  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a0535  call    cs:__imp_EnterCriticalSection
0x1800a053c  nop     dword ptr [rax+rax+00h]
0x1800a0541  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a0548  mov     rbx, [rdi+20h]
0x1800a054c  and     [rbp+arg_0], 0
0x1800a0550  and     [rbp+var_8], 0
0x1800a0555  call    cs:__imp_EnterCriticalSection
0x1800a055c  nop     dword ptr [rax+rax+00h]
0x1800a0561  lea     r8, [rbp+arg_0]
0x1800a0565  mov     rcx, rbx
0x1800a0568  lea     rdx, [rbp+var_8]
0x1800a056c  call    FSMGetElement
0x1800a0571  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a0578  mov     ebx, eax
0x1800a057a  call    cs:__imp_LeaveCriticalSection
0x1800a0581  nop     dword ptr [rax+rax+00h]
0x1800a0586  test    ebx, ebx
0x1800a0588  jnz     short loc_1800A05BF
0x1800a058a  mov     ebx, 4E92h
0x1800a058f  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a0596  call    cs:__imp_LeaveCriticalSection
0x1800a059d  nop     dword ptr [rax+rax+00h]
0x1800a05a2  mov     eax, ebx
0x1800a05a4  mov     rbx, [rsp+30h+arg_8]
0x1800a05a9  mov     rsi, [rsp+30h+arg_10]
0x1800a05ae  add     rsp, 30h
0x1800a05b2  pop     r14
0x1800a05b4  pop     rdi
0x1800a05b5  pop     rbp
0x1800a05b6  retn
0x1800a05b8  mov     eax, 4E91h
0x1800a05bd  jmp     short loc_1800A05A4
0x1800a05bf  cmp     ebx, 4E93h
0x1800a05c5  jnz     short loc_1800A058F
0x1800a05c7  test    esi, esi
0x1800a05c9  jnz     short loc_1800A05E0
0x1800a05cb  cmp     qword ptr [rdi+48h], 0
0x1800a05d0  jz      short loc_1800A0624
0x1800a05d2  mov     rcx, rdi
0x1800a05d5  call    CreateRegistryWithSharedSecretInfo
0x1800a05da  test    eax, eax
0x1800a05dc  mov     ebx, eax
0x1800a05de  jnz     short loc_1800A058F
0x1800a05e0  mov     r8d, r14d
0x1800a05e3  lea     rcx, [rbp+lpMem]
0x1800a05e7  mov     rdx, rdi
0x1800a05ea  call    FSMFailoverRelationshipInit
0x1800a05ef  mov     rcx, cs:g_FailoverEndpoints
0x1800a05f6  mov     ebx, eax
0x1800a05f8  test    eax, eax
0x1800a05fa  jnz     short loc_1800A0596
0x1800a05fc  mov     rdx, [rbp+lpMem]
0x1800a0600  add     rcx, 30h ; '0'
0x1800a0604  call    MemArrayAddElement
0x1800a0609  mov     ebx, eax
0x1800a060b  test    eax, eax
0x1800a060d  jz      short loc_1800A063B
0x1800a060f  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a0616  call    cs:__imp_LeaveCriticalSection
0x1800a061d  nop     dword ptr [rax+rax+00h]
0x1800a0622  jmp     short loc_1800A0695
0x1800a0624  mov     rdx, [rdi+20h]
0x1800a0628  mov     rcx, cs:DhcpGlobalServicePrivateData
0x1800a062f  call    DhcpRegDeleteKey
0x1800a0634  test    eax, 0FFFFFFFDh
0x1800a0639  jmp     short loc_1800A05DC
0x1800a063b  mov     rax, cs:g_FailoverEndpoints
0x1800a0642  add     rax, 30h ; '0'
0x1800a0646  jnz     short loc_1800A064C
0x1800a0648  xor     ecx, ecx
0x1800a064a  jmp     short loc_1800A064E
0x1800a064c  mov     ecx, [rax]
0x1800a064e  call    InitializeFreePacketPool
0x1800a0653  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a065a  mov     ebx, eax
0x1800a065c  test    eax, eax
0x1800a065e  jnz     short loc_1800A0616
0x1800a0660  call    cs:__imp_LeaveCriticalSection
0x1800a0667  nop     dword ptr [rax+rax+00h]
0x1800a066c  mov     rcx, [rbp+lpMem]; lpParameter
0x1800a0670  call    InitializeFiniteStateMachine
0x1800a0675  mov     ebx, eax
0x1800a0677  test    eax, eax
0x1800a0679  jz      loc_1800A05A2
0x1800a067f  mov     rcx, cs:g_FailoverEndpoints
0x1800a0686  add     rcx, 30h ; '0'
0x1800a068a  jz      short loc_1800A068E
0x1800a068c  mov     ecx, [rcx]
0x1800a068e  dec     ecx
0x1800a0690  call    UnInitializeFreePacketPool
0x1800a0695  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a069c  call    cs:__imp_EnterCriticalSection
0x1800a06a3  nop     dword ptr [rax+rax+00h]
0x1800a06a8  mov     rcx, [rdi+20h]
0x1800a06ac  lea     r8, [rbp+arg_18]
0x1800a06b0  lea     rdx, [rbp+lpMem]
0x1800a06b4  call    FSMGetElement
0x1800a06b9  test    eax, eax
0x1800a06bb  jnz     short loc_1800A06D5
0x1800a06bd  mov     rcx, cs:g_FailoverEndpoints
0x1800a06c4  lea     r8, [rbp+lpMem]
0x1800a06c8  add     rcx, 30h ; '0'
0x1800a06cc  lea     rdx, [rbp+arg_18]
0x1800a06d0  call    MemArrayDelElement
0x1800a06d5  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a06dc  call    cs:__imp_LeaveCriticalSection
0x1800a06e3  nop     dword ptr [rax+rax+00h]
0x1800a06e8  mov     rdi, [rbp+lpMem]
0x1800a06ec  test    rdi, rdi
0x1800a06ef  jz      loc_1800A05A2
0x1800a06f5  call    cs:__imp_GetProcessHeap
0x1800a06fc  nop     dword ptr [rax+rax+00h]
0x1800a0701  mov     r8, rdi; lpMem
0x1800a0704  xor     edx, edx; dwFlags
0x1800a0706  mov     rcx, rax; hHeap
0x1800a0709  call    cs:__imp_HeapFree
0x1800a0710  nop     dword ptr [rax+rax+00h]
0x1800a0715  jmp     loc_1800A05A2
```
