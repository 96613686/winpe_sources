# DhcpFSMAddEndpoint

- ea: `0x1800a1004`
- end: `0x1800a13fc`
- name: `DhcpFSMAddEndpoint`
- size: `1016`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task`

## callers

- `0x180084600`
- `0x180085570`

## callees

- `0x18001d640`
- `0x1800250e8`
- `0x180094a7c`
- `0x180094b48`
- `0x1800a1004`
- `0x1800a3b60`
- `0x1800a9858`
- `0x1800a9f84`
- `0x1800aa09c`
- `0x1800add5c`
- `0x1800ae074`
- `0x1800aff9c`
- `0x1800c09e8`
- `0x1800cc78c`
- `0x1800ccba0`
- `0x1800ccd98`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800a1089`
- `KERNEL32!HeapAlloc` at `0x1800a1089`
- `KERNEL32!GetProcessHeap` at `0x1800a13d7`
- `KERNEL32!GetProcessHeap` at `0x1800a13d7`
- `KERNEL32!DeleteCriticalSection` at `0x1800a10e0`
- `KERNEL32!DeleteCriticalSection` at `0x1800a10f3`
- `KERNEL32!DeleteCriticalSection` at `0x1800a10e0`
- `KERNEL32!DeleteCriticalSection` at `0x1800a10f3`
- `KERNEL32!InitializeCriticalSection` at `0x1800a10ae`
- `KERNEL32!InitializeCriticalSection` at `0x1800a10c1`
- `KERNEL32!InitializeCriticalSection` at `0x1800a10ae`
- `KERNEL32!InitializeCriticalSection` at `0x1800a10c1`
- `KERNEL32!EnterCriticalSection` at `0x1800a118d`
- `KERNEL32!EnterCriticalSection` at `0x1800a121c`
- `KERNEL32!EnterCriticalSection` at `0x1800a1242`
- `KERNEL32!EnterCriticalSection` at `0x1800a137e`
- `KERNEL32!EnterCriticalSection` at `0x1800a118d`
- `KERNEL32!EnterCriticalSection` at `0x1800a121c`
- `KERNEL32!EnterCriticalSection` at `0x1800a1242`
- `KERNEL32!EnterCriticalSection` at `0x1800a137e`
- `KERNEL32!LeaveCriticalSection` at `0x1800a11ae`
- `KERNEL32!LeaveCriticalSection` at `0x1800a11ce`
- `KERNEL32!LeaveCriticalSection` at `0x1800a1267`
- `KERNEL32!LeaveCriticalSection` at `0x1800a1283`
- `KERNEL32!LeaveCriticalSection` at `0x1800a1303`
- `KERNEL32!LeaveCriticalSection` at `0x1800a1342`
- `KERNEL32!LeaveCriticalSection` at `0x1800a13be`
- `KERNEL32!LeaveCriticalSection` at `0x1800a11ae`
- `KERNEL32!LeaveCriticalSection` at `0x1800a11ce`
- `KERNEL32!LeaveCriticalSection` at `0x1800a1267`
- `KERNEL32!LeaveCriticalSection` at `0x1800a1283`
- `KERNEL32!LeaveCriticalSection` at `0x1800a1303`
- `KERNEL32!LeaveCriticalSection` at `0x1800a1342`
- `KERNEL32!LeaveCriticalSection` at `0x1800a13be`
- `KERNEL32!HeapFree` at `0x1800a110f`
- `KERNEL32!HeapFree` at `0x1800a13eb`
- `KERNEL32!HeapFree` at `0x1800a110f`
- `KERNEL32!HeapFree` at `0x1800a13eb`

## pseudocode

```c
__int64 __fastcall DhcpFSMAddEndpoint(__int64 a1, unsigned int a2, int a3)
{
  __int64 result; // rax
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  unsigned int v8; // edx
  __int64 String; // rax
  int v10; // edx
  __int64 *v11; // r8
  struct _RTL_CRITICAL_SECTION *v12; // rax
  LPCRITICAL_SECTION v13; // rax
  LONG *p_LockCount; // rdx
  unsigned int v15; // ebx
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // rcx
  unsigned int RegistryWithSharedSecretInfo; // eax
  bool v21; // zf
  unsigned int v22; // eax
  unsigned int v23; // eax
  struct _RTL_CRITICAL_SECTION *v24; // rcx
  LONG *v25; // rcx
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
    do
    {
      String = GetString(v8 + 1349);
      v8 = v10 + 1;
      *v11 = String;
    }
    while ( v8 < 0x19 );
    v12 = (struct _RTL_CRITICAL_SECTION *)HeapAlloc(gDhcpHeap, 8u, 0x40u);
    g_FailoverEndpoints = v12;
    if ( !v12 )
      return 8;
    InitializeCriticalSection(v12);
    InitializeCriticalSection(&gXidCS);
    v13 = g_FailoverEndpoints;
    p_LockCount = &g_FailoverEndpoints[1].LockCount;
    if ( g_FailoverEndpoints == (LPCRITICAL_SECTION)-48LL )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)0xFFFFFFFFFFFFFFD0LL);
      DeleteCriticalSection(&gXidCS);
      HeapFree(gDhcpHeap, 0, g_FailoverEndpoints);
      g_FailoverEndpoints = 0;
      return 87;
    }
    *(_QWORD *)p_LockCount = 0;
    *((_QWORD *)p_LockCount + 1) = 0;
    LODWORD(v13[1].DebugInfo) |= 8u;
    v15 = MessageQInitialize(&gFailoverFreePacketPool, 0, 1);
    if ( v15
      || (LODWORD(g_FailoverEndpoints[1].DebugInfo) |= 4u, (v15 = DhcpBNDInitialize()) != 0)
      || (LODWORD(g_FailoverEndpoints[1].DebugInfo) |= 1u, (v15 = DhcpCMInitialize()) != 0) )
    {
      DhcpFSMModuleCleanup();
      return v15;
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
  v16 = *(_QWORD *)(a1 + 56);
  if ( !v16 || (v17 = 0, !*(_DWORD *)v16) )
  {
LABEL_23:
    EnterCriticalSection(g_FailoverEndpoints);
    v18 = *(_QWORD *)(a1 + 32);
    v32 = 0;
    v31 = 0;
    EnterCriticalSection(g_FailoverEndpoints);
    v15 = FSMGetElement(v18, &v31, &v32);
    LeaveCriticalSection(g_FailoverEndpoints);
    if ( v15 )
    {
      if ( v15 == 20115 )
      {
        if ( a3
          || (!*(_QWORD *)(a1 + 72)
            ? (RegistryWithSharedSecretInfo = DhcpRegDeleteKey(DhcpGlobalServicePrivateData, *(const WCHAR **)(a1 + 32)),
               v21 = (RegistryWithSharedSecretInfo & 0xFFFFFFFD) == 0)
            : (RegistryWithSharedSecretInfo = CreateRegistryWithSharedSecretInfo(a1),
               v21 = RegistryWithSharedSecretInfo == 0),
              v15 = RegistryWithSharedSecretInfo,
              v21) )
        {
          v22 = FSMFailoverRelationshipInit(&lpMem, a1, a2);
          v19 = g_FailoverEndpoints;
          v15 = v22;
          if ( !v22 )
          {
            v23 = MemArrayAddElement(&g_FailoverEndpoints[1].LockCount, lpMem);
            v24 = g_FailoverEndpoints;
            v15 = v23;
            if ( v23 )
              goto LABEL_37;
            v25 = &g_FailoverEndpoints[1].LockCount;
            if ( g_FailoverEndpoints != (LPCRITICAL_SECTION)-48LL )
              v25 = (LONG *)(unsigned int)*v25;
            v26 = InitializeFreePacketPool(v25);
            v24 = g_FailoverEndpoints;
            v15 = v26;
            if ( v26 )
            {
LABEL_37:
              LeaveCriticalSection(v24);
            }
            else
            {
              LeaveCriticalSection(g_FailoverEndpoints);
              v15 = InitializeFiniteStateMachine((DWORD *)lpMem);
              if ( !v15 )
                return v15;
              v27 = &g_FailoverEndpoints[1].LockCount;
              if ( g_FailoverEndpoints != (LPCRITICAL_SECTION)-48LL )
                LODWORD(v27) = *v27;
              UnInitializeFreePacketPool((unsigned int)((_DWORD)v27 - 1));
            }
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
            return v15;
          }
          goto LABEL_26;
        }
      }
    }
    else
    {
      v15 = 20114;
    }
    v19 = g_FailoverEndpoints;
LABEL_26:
    LeaveCriticalSection(v19);
    return v15;
  }
  while ( 1 )
  {
    result = FSMScopeInFailoverRelation(*(unsigned int *)(*(_QWORD *)(v16 + 8) + 4 * v17), &v32);
    if ( (_DWORD)result )
      return result;
    if ( v32 == 1 )
      return 20113;
    v16 = *(_QWORD *)(a1 + 56);
    v17 = (unsigned int)(v17 + 1);
    if ( (unsigned int)v17 >= *(_DWORD *)v16 )
      goto LABEL_23;
  }
}

```

## disassembly

```asm
0x1800a1004  mov     [rsp-18h+arg_8], rbx
0x1800a1009  mov     [rsp-18h+arg_10], rsi
0x1800a100e  push    rbp
0x1800a100f  push    rdi
0x1800a1010  push    r14
0x1800a1012  mov     rbp, rsp
0x1800a1015  sub     rsp, 30h
0x1800a1019  mov     [rbp+lpMem], 0
0x1800a1021  mov     esi, r8d
0x1800a1024  mov     [rbp+arg_0], 0
0x1800a102b  mov     r14d, edx
0x1800a102e  mov     [rbp+arg_18], 0
0x1800a1035  mov     rdi, rcx
0x1800a1038  test    rcx, rcx
0x1800a103b  jnz     short loc_1800A1047
0x1800a103d  mov     eax, 57h ; 'W'
0x1800a1042  jmp     loc_1800A1291
0x1800a1047  mov     rcx, cs:g_FailoverEndpoints
0x1800a104e  test    rcx, rcx
0x1800a1051  jnz     loc_1800A118D
0x1800a1057  xor     edx, edx
0x1800a1059  lea     r8, FailoverRejectReasonDescription
0x1800a1060  lea     ecx, [rdx+545h]
0x1800a1066  call    GetString
0x1800a106b  inc     edx
0x1800a106d  mov     [r8], rax
0x1800a1070  lea     r8, [r8+8]
0x1800a1074  cmp     edx, 19h
0x1800a1077  jb      short loc_1800A1060
0x1800a1079  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a1080  mov     edx, 8; dwFlags
0x1800a1085  lea     r8d, [rdx+38h]; dwBytes
0x1800a1089  call    cs:__imp_HeapAlloc
0x1800a1090  nop     dword ptr [rax+rax+00h]
0x1800a1095  mov     cs:g_FailoverEndpoints, rax
0x1800a109c  test    rax, rax
0x1800a109f  jnz     short loc_1800A10AB
0x1800a10a1  mov     eax, 8
0x1800a10a6  jmp     loc_1800A1291
0x1800a10ab  mov     rcx, rax; lpCriticalSection
0x1800a10ae  call    cs:__imp_InitializeCriticalSection
0x1800a10b5  nop     dword ptr [rax+rax+00h]
0x1800a10ba  lea     rcx, gXidCS; lpCriticalSection
0x1800a10c1  call    cs:__imp_InitializeCriticalSection
0x1800a10c8  nop     dword ptr [rax+rax+00h]
0x1800a10cd  mov     rax, cs:g_FailoverEndpoints
0x1800a10d4  lea     rdx, [rax+30h]
0x1800a10d8  test    rdx, rdx
0x1800a10db  jnz     short loc_1800A112B
0x1800a10dd  mov     rcx, rax; lpCriticalSection
0x1800a10e0  call    cs:__imp_DeleteCriticalSection
0x1800a10e7  nop     dword ptr [rax+rax+00h]
0x1800a10ec  lea     rcx, gXidCS; lpCriticalSection
0x1800a10f3  call    cs:__imp_DeleteCriticalSection
0x1800a10fa  nop     dword ptr [rax+rax+00h]
0x1800a10ff  mov     r8, cs:g_FailoverEndpoints; lpMem
0x1800a1106  xor     edx, edx; dwFlags
0x1800a1108  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a110f  call    cs:__imp_HeapFree
0x1800a1116  nop     dword ptr [rax+rax+00h]
0x1800a111b  mov     cs:g_FailoverEndpoints, 0
0x1800a1126  jmp     loc_1800A103D
0x1800a112b  mov     qword ptr [rdx], 0
0x1800a1132  lea     rcx, gFailoverFreePacketPool
0x1800a1139  mov     qword ptr [rdx+8], 0
0x1800a1141  xor     edx, edx
0x1800a1143  or      dword ptr [rax+28h], 8
0x1800a1147  lea     r8d, [rdx+1]
0x1800a114b  call    MessageQInitialize
0x1800a1150  mov     ebx, eax
0x1800a1152  test    eax, eax
0x1800a1154  jnz     short loc_1800A11C4
0x1800a1156  mov     rax, cs:g_FailoverEndpoints
0x1800a115d  or      dword ptr [rax+28h], 4
0x1800a1161  call    DhcpBNDInitialize
0x1800a1166  mov     ebx, eax
0x1800a1168  test    eax, eax
0x1800a116a  jnz     short loc_1800A11C4
0x1800a116c  mov     rax, cs:g_FailoverEndpoints
0x1800a1173  or      dword ptr [rax+28h], 1
0x1800a1177  call    DhcpCMInitialize
0x1800a117c  mov     ebx, eax
0x1800a117e  test    eax, eax
0x1800a1180  jnz     short loc_1800A11C4
0x1800a1182  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a1189  or      dword ptr [rcx+28h], 2
0x1800a118d  call    cs:__imp_EnterCriticalSection
0x1800a1194  nop     dword ptr [rax+rax+00h]
0x1800a1199  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a11a0  lea     rax, [rcx+30h]
0x1800a11a4  test    rax, rax
0x1800a11a7  jz      short loc_1800A11CE
0x1800a11a9  cmp     dword ptr [rax], 1Fh
0x1800a11ac  jb      short loc_1800A11CE
0x1800a11ae  call    cs:__imp_LeaveCriticalSection
0x1800a11b5  nop     dword ptr [rax+rax+00h]
0x1800a11ba  mov     eax, 4EA0h
0x1800a11bf  jmp     loc_1800A1291
0x1800a11c4  call    DhcpFSMModuleCleanup
0x1800a11c9  jmp     loc_1800A128F
0x1800a11ce  call    cs:__imp_LeaveCriticalSection
0x1800a11d5  nop     dword ptr [rax+rax+00h]
0x1800a11da  mov     rcx, [rdi+38h]
0x1800a11de  test    rcx, rcx
0x1800a11e1  jz      short loc_1800A1215
0x1800a11e3  xor     ebx, ebx
0x1800a11e5  cmp     [rcx], ebx
0x1800a11e7  jbe     short loc_1800A1215
0x1800a11e9  mov     rcx, [rcx+8]
0x1800a11ed  lea     rdx, [rbp+arg_0]
0x1800a11f1  mov     ecx, [rcx+rbx*4]
0x1800a11f4  call    FSMScopeInFailoverRelation
0x1800a11f9  test    eax, eax
0x1800a11fb  jnz     loc_1800A1291
0x1800a1201  cmp     [rbp+arg_0], 1
0x1800a1205  jz      loc_1800A12A5
0x1800a120b  mov     rcx, [rdi+38h]
0x1800a120f  inc     ebx
0x1800a1211  cmp     ebx, [rcx]
0x1800a1213  jb      short loc_1800A11E9
0x1800a1215  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a121c  call    cs:__imp_EnterCriticalSection
0x1800a1223  nop     dword ptr [rax+rax+00h]
0x1800a1228  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a122f  mov     rbx, [rdi+20h]
0x1800a1233  mov     [rbp+arg_0], 0
0x1800a123a  mov     [rbp+var_8], 0
0x1800a1242  call    cs:__imp_EnterCriticalSection
0x1800a1249  nop     dword ptr [rax+rax+00h]
0x1800a124e  lea     r8, [rbp+arg_0]
0x1800a1252  mov     rcx, rbx
0x1800a1255  lea     rdx, [rbp+var_8]
0x1800a1259  call    FSMGetElement
0x1800a125e  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a1265  mov     ebx, eax
0x1800a1267  call    cs:__imp_LeaveCriticalSection
0x1800a126e  nop     dword ptr [rax+rax+00h]
0x1800a1273  test    ebx, ebx
0x1800a1275  jnz     short loc_1800A12AC
0x1800a1277  mov     ebx, 4E92h
0x1800a127c  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a1283  call    cs:__imp_LeaveCriticalSection
0x1800a128a  nop     dword ptr [rax+rax+00h]
0x1800a128f  mov     eax, ebx
0x1800a1291  mov     rbx, [rsp+30h+arg_8]
0x1800a1296  mov     rsi, [rsp+30h+arg_10]
0x1800a129b  add     rsp, 30h
0x1800a129f  pop     r14
0x1800a12a1  pop     rdi
0x1800a12a2  pop     rbp
0x1800a12a3  retn
0x1800a12a5  mov     eax, 4E91h
0x1800a12aa  jmp     short loc_1800A1291
0x1800a12ac  cmp     ebx, 4E93h
0x1800a12b2  jnz     short loc_1800A127C
0x1800a12b4  test    esi, esi
0x1800a12b6  jnz     short loc_1800A12CD
0x1800a12b8  cmp     qword ptr [rdi+48h], 0
0x1800a12bd  jz      short loc_1800A1311
0x1800a12bf  mov     rcx, rdi
0x1800a12c2  call    CreateRegistryWithSharedSecretInfo
0x1800a12c7  test    eax, eax
0x1800a12c9  mov     ebx, eax
0x1800a12cb  jnz     short loc_1800A127C
0x1800a12cd  mov     r8d, r14d
0x1800a12d0  lea     rcx, [rbp+lpMem]
0x1800a12d4  mov     rdx, rdi
0x1800a12d7  call    FSMFailoverRelationshipInit
0x1800a12dc  mov     rcx, cs:g_FailoverEndpoints
0x1800a12e3  mov     ebx, eax
0x1800a12e5  test    eax, eax
0x1800a12e7  jnz     short loc_1800A1283
0x1800a12e9  mov     rdx, [rbp+lpMem]
0x1800a12ed  add     rcx, 30h ; '0'
0x1800a12f1  call    MemArrayAddElement
0x1800a12f6  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a12fd  mov     ebx, eax
0x1800a12ff  test    eax, eax
0x1800a1301  jz      short loc_1800A1328
0x1800a1303  call    cs:__imp_LeaveCriticalSection
0x1800a130a  nop     dword ptr [rax+rax+00h]
0x1800a130f  jmp     short loc_1800A1377
0x1800a1311  mov     rdx, [rdi+20h]
0x1800a1315  mov     rcx, cs:DhcpGlobalServicePrivateData
0x1800a131c  call    DhcpRegDeleteKey
0x1800a1321  test    eax, 0FFFFFFFDh
0x1800a1326  jmp     short loc_1800A12C9
0x1800a1328  add     rcx, 30h ; '0'
0x1800a132c  jz      short loc_1800A1330
0x1800a132e  mov     ecx, [rcx]
0x1800a1330  call    InitializeFreePacketPool
0x1800a1335  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a133c  mov     ebx, eax
0x1800a133e  test    eax, eax
0x1800a1340  jnz     short loc_1800A1303
0x1800a1342  call    cs:__imp_LeaveCriticalSection
0x1800a1349  nop     dword ptr [rax+rax+00h]
0x1800a134e  mov     rcx, [rbp+lpMem]; lpParameter
0x1800a1352  call    InitializeFiniteStateMachine
0x1800a1357  mov     ebx, eax
0x1800a1359  test    eax, eax
0x1800a135b  jz      loc_1800A128F
0x1800a1361  mov     rcx, cs:g_FailoverEndpoints
0x1800a1368  add     rcx, 30h ; '0'
0x1800a136c  jz      short loc_1800A1370
0x1800a136e  mov     ecx, [rcx]
0x1800a1370  dec     ecx
0x1800a1372  call    UnInitializeFreePacketPool
0x1800a1377  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a137e  call    cs:__imp_EnterCriticalSection
0x1800a1385  nop     dword ptr [rax+rax+00h]
0x1800a138a  mov     rcx, [rdi+20h]
0x1800a138e  lea     r8, [rbp+arg_18]
0x1800a1392  lea     rdx, [rbp+lpMem]
0x1800a1396  call    FSMGetElement
0x1800a139b  test    eax, eax
0x1800a139d  jnz     short loc_1800A13B7
0x1800a139f  mov     rcx, cs:g_FailoverEndpoints
0x1800a13a6  lea     r8, [rbp+lpMem]
0x1800a13aa  add     rcx, 30h ; '0'
0x1800a13ae  lea     rdx, [rbp+arg_18]
0x1800a13b2  call    MemArrayDelElement
0x1800a13b7  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800a13be  call    cs:__imp_LeaveCriticalSection
0x1800a13c5  nop     dword ptr [rax+rax+00h]
0x1800a13ca  mov     rdi, [rbp+lpMem]
0x1800a13ce  test    rdi, rdi
0x1800a13d1  jz      loc_1800A128F
0x1800a13d7  call    cs:__imp_GetProcessHeap
0x1800a13de  nop     dword ptr [rax+rax+00h]
0x1800a13e3  mov     r8, rdi; lpMem
0x1800a13e6  xor     edx, edx; dwFlags
0x1800a13e8  mov     rcx, rax; hHeap
0x1800a13eb  call    cs:__imp_HeapFree
0x1800a13f2  nop     dword ptr [rax+rax+00h]
0x1800a13f7  jmp     loc_1800A128F
```
