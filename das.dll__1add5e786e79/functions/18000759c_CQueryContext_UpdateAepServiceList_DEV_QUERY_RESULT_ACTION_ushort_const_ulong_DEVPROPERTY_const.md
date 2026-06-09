# CQueryContext::UpdateAepServiceList(_DEV_QUERY_RESULT_ACTION,ushort const *,ulong,_DEVPROPERTY * const)

- ea: `0x18000759c`
- end: `0x180007a4d`
- name: `?UpdateAepServiceList@CQueryContext@@QEAAJW4_DEV_QUERY_RESULT_ACTION@@PEBGKQEAU_DEVPROPERTY@@@Z`
- size: `1201`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180005924`
- `0x180008ba0`

## callees

- `0x1800061c0`
- `0x180006208`
- `0x18000759c`
- `0x180008010`
- `0x180008a50`
- `0x1800095bc`
- `0x180009d50`
- `0x18000aad0`
- `0x18001a760`
- `0x180021b14`
- `0x180023f34`
- `0x18003c79c`
- `0x180053b70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000793e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000793e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800075fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800075fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007756`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007756`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800076ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800076ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007964`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800078b2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800078b2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800076b0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800076b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CQueryContext::UpdateAepServiceList(__int64 a1, int a2, const WCHAR *a3, int a4, int a5)
{
  __int64 v8; // rdx
  int v9; // r8d
  int IsObjectInList; // edi
  const WCHAR *v11; // rax
  signed int updated; // ebx
  __int64 v13; // r11
  __int64 v14; // rcx
  __int64 *v15; // rsi
  __int64 v16; // rdi
  int v17; // ecx
  HANDLE ProcessHeap; // rax
  void *v19; // rax
  int v20; // edx
  int v21; // r8d
  struct _RTL_BALANCED_LINKS *i; // rdi
  struct _RTL_BALANCED_LINKS *LeftChild; // rdx
  __int64 v25; // rax
  __int64 *v26; // rcx
  const WCHAR *v27; // r10
  __int64 v28; // rcx
  const WCHAR *v29; // rax
  int v30; // eax
  int v31; // edx
  int v32; // r8d
  __int64 *v33; // rax
  signed int LastError; // eax
  int v35; // [rsp+28h] [rbp-40h]
  _RTL_AVL_TABLE Table; // [rsp+40h] [rbp-28h] BYREF

  memset(&Table.BalancedRoot.LeftChild, 0, 24);
  Table.BalancedRoot.Parent = (struct _RTL_BALANCED_LINKS *)&DafDynamicArray<_DEVPROPERTY>::`vftable';
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sq(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      a2,
      (int)a3,
      26,
      &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
      v35,
      a1);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 208));
  IsObjectInList = 0;
  if ( !a3 )
  {
    updated = -2147024809;
    goto LABEL_12;
  }
  v8 = 768;
  v11 = a3;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v8;
  }
  while ( v8 );
  v9 = -2147024809;
  updated = v8 == 0 ? 0x80070057 : 0;
  v13 = (768 - v8) & -(__int64)(v8 != 0);
  if ( !v8 )
  {
LABEL_12:
    if ( updated < 0 )
      goto LABEL_28;
    goto LABEL_13;
  }
  v14 = *(_QWORD *)(a1 + 136);
  if ( *(_DWORD *)(v14 + 20) == 1 )
  {
    v27 = *(const WCHAR **)(v14 + 24);
    if ( v27 )
    {
      v28 = 768;
      v29 = v27;
      do
      {
        if ( !*v29 )
          break;
        ++v29;
        --v28;
      }
      while ( v28 );
      updated = v28 == 0 ? 0x80070057 : 0;
      v8 = (768 - v28) & ((unsigned __int128)-(__int128)(unsigned __int64)v28 >> 64);
      if ( v28 )
      {
        v30 = CompareStringOrdinal(a3, v13 + 1, v27, v8 + 1, 1);
        if ( v30 )
        {
          LOBYTE(IsObjectInList) = v30 == 2;
          goto LABEL_13;
        }
        LastError = GetLastError();
        updated = LastError;
        if ( LastError > 0 )
          updated = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      updated = -2147024809;
    }
    goto LABEL_12;
  }
  if ( *(_DWORD *)(v14 + 20) != 2 )
    goto LABEL_14;
  IsObjectInList = DafIsObjectInList(*(LPCWCH *)(v14 + 32), a3);
LABEL_13:
  if ( !IsObjectInList )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v8,
        v9,
        27,
        &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
        (__int64)a3);
    goto LABEL_28;
  }
LABEL_14:
  v15 = (__int64 *)(a1 + 248);
  if ( a1 != -248 )
  {
    if ( a3 )
    {
      v16 = *v15;
      if ( (__int64 *)*v15 != v15 )
      {
        while ( 1 )
        {
          if ( (__int64 *)v16 == v15 )
            goto LABEL_20;
          if ( !lstrcmpiW(*(LPCWSTR *)(v16 + 16), a3) )
            break;
          v16 = *(_QWORD *)v16;
        }
        if ( v16 )
          goto LABEL_37;
      }
    }
  }
LABEL_20:
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v8,
      v9,
      28,
      &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
      (__int64)a3);
  ProcessHeap = GetProcessHeap();
  v19 = HeapAlloc(ProcessHeap, 0, 0x50u);
  v16 = (__int64)v19;
  if ( !v19 )
  {
    updated = -2147024882;
    goto LABEL_24;
  }
  memset_0(v19, 0, 0x50u);
  updated = DafStringCopy(a3, v16 + 16);
  if ( updated < 0 )
  {
LABEL_24:
    FreeAepServiceEntry((struct _AEP_SERVICE_ENTRY *)v16);
    goto LABEL_28;
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)(v16 + 40));
  v33 = *(__int64 **)(a1 + 256);
  if ( (__int64 *)*v33 != v15 )
    goto LABEL_61;
  *(_QWORD *)v16 = v15;
  *(_QWORD *)(v16 + 8) = v33;
  *v33 = v16;
  *(_QWORD *)(a1 + 256) = v16;
LABEL_37:
  updated = CQueryContext::UpdateAepServiceEntry(v17, a2, a4, a5, v16, (__int64)&Table);
  if ( updated < 0 )
    goto LABEL_38;
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 136) + 40LL) & 1) != 0 )
    updated = CQueryContext::MakeResult(a1, a2);
  if ( v16 )
  {
LABEL_38:
    if ( a2 == 3 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v31,
          v32,
          29,
          &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
          (__int64)a3);
      v25 = *(_QWORD *)v16;
      if ( *(_QWORD *)(*(_QWORD *)v16 + 8LL) == v16 )
      {
        v26 = *(__int64 **)(v16 + 8);
        if ( *v26 == v16 )
        {
          *v26 = v25;
          *(_QWORD *)(v25 + 8) = v26;
          FreeAepServiceEntry((struct _AEP_SERVICE_ENTRY *)v16);
          goto LABEL_28;
        }
      }
LABEL_61:
      __fastfail(3u);
    }
  }
LABEL_28:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 208));
  for ( i = 0; i < Table.BalancedRoot.RightChild; i = (struct _RTL_BALANCED_LINKS *)((char *)i + 1) )
    DafDevPropCompKeyFree(&Table.BalancedRoot.LeftChild[(_QWORD)i]);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v20,
      v21,
      30,
      &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
      v35,
      a1,
      updated);
  Table.BalancedRoot.Parent = (struct _RTL_BALANCED_LINKS *)&DafDynamicArray<_DEVPROPERTY>::`vftable';
  Table.BalancedRoot.RightChild = 0;
  LeftChild = Table.BalancedRoot.LeftChild;
  if ( Table.BalancedRoot.LeftChild )
  {
    FreeTableEntry(&Table, Table.BalancedRoot.LeftChild);
    LeftChild = 0;
    Table.BalancedRoot.LeftChild = 0;
  }
  Table.BalancedRoot.Parent = (struct _RTL_BALANCED_LINKS *)&TDynamicArray<unsigned short *>::`vftable';
  Table.BalancedRoot.RightChild = 0;
  if ( LeftChild )
    TDynamicArray<_DEVPROPERTY>::free(&Table);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000759c  mov     [rsp-40h+arg_18], r9d
0x1800075a1  push    rbp
0x1800075a2  push    rbx
0x1800075a3  push    rsi
0x1800075a4  push    rdi
0x1800075a5  push    r12
0x1800075a7  push    r13
0x1800075a9  push    r14
0x1800075ab  push    r15
0x1800075ad  mov     rbp, rsp
0x1800075b0  sub     rsp, 68h
0x1800075b4  mov     r14, r8
0x1800075b7  mov     r12d, edx
0x1800075ba  mov     r15, rcx
0x1800075bd  xor     esi, esi
0x1800075bf  mov     [rbp+Table.BalancedRoot.LeftChild], rsi
0x1800075c3  mov     [rbp+Table.BalancedRoot.RightChild], rsi
0x1800075c7  mov     qword ptr [rbp+Table.BalancedRoot.Balance], rsi
0x1800075cb  lea     rax, ??_7?$DafDynamicArray@U_DEVPROPERTY@@@@6B@; const DafDynamicArray<_DEVPROPERTY>::`vftable'
0x1800075d2  mov     [rbp+Table.BalancedRoot.Parent], rax
0x1800075d6  lea     rax, WPP_RECORDER_INITIALIZED
0x1800075dd  lea     rcx, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x1800075e4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800075eb  jnz     loc_180007982
0x1800075f1  lea     r13, [r15+0D0h]
0x1800075f8  mov     rcx, r13; lpCriticalSection
0x1800075fb  call    cs:__imp_EnterCriticalSection
0x180007601  mov     edi, esi
0x180007603  test    r14, r14
0x180007606  jz      loc_180007930
0x18000760c  mov     r9d, 300h
0x180007612  mov     edx, r9d
0x180007615  mov     rax, r14
0x180007618  cmp     [rax], si
0x18000761b  jz      short loc_180007627
0x18000761d  add     rax, 2
0x180007621  sub     rdx, 1; int
0x180007625  jnz     short loc_180007618
0x180007627  mov     rax, rdx
0x18000762a  neg     rax
0x18000762d  sbb     ebx, ebx
0x18000762f  not     ebx
0x180007631  mov     r8d, 80070057h; int
0x180007637  and     ebx, r8d
0x18000763a  mov     rax, rdx
0x18000763d  mov     rcx, r9
0x180007640  sub     rcx, rdx
0x180007643  neg     rax
0x180007646  sbb     r11, r11
0x180007649  and     r11, rcx
0x18000764c  test    rdx, rdx
0x18000764f  jz      short loc_18000767B
0x180007651  mov     rcx, [r15+88h]
0x180007658  cmp     dword ptr [rcx+14h], 1
0x18000765c  jz      loc_180007855
0x180007662  cmp     dword ptr [rcx+14h], 2
0x180007666  jnz     short loc_18000768B
0x180007668  mov     rdx, r14; lpString2
0x18000766b  mov     rcx, [rcx+20h]; lpString1
0x18000766f  call    DafIsObjectInList
0x180007674  mov     edi, eax
0x180007676  jmp     short loc_180007683
0x180007678  mov     ebx, r8d
0x18000767b  test    ebx, ebx
0x18000767d  js      loc_180007745
0x180007683  test    edi, edi
0x180007685  jz      loc_1800079A7
0x18000768b  lea     rsi, [r15+0F8h]
0x180007692  test    rsi, rsi
0x180007695  jz      short loc_1800076C3
0x180007697  test    r14, r14
0x18000769a  jz      short loc_1800076C3
0x18000769c  mov     rdi, [rsi]
0x18000769f  cmp     rdi, rsi
0x1800076a2  jz      short loc_1800076C3
0x1800076a4  cmp     rdi, rsi
0x1800076a7  jz      short loc_1800076C3
0x1800076a9  mov     rdx, r14; lpString2
0x1800076ac  mov     rcx, [rdi+10h]; lpString1
0x1800076b0  call    cs:__imp_lstrcmpiW
0x1800076b6  test    eax, eax
0x1800076b8  jz      loc_1800077CF
0x1800076be  mov     rdi, [rdi]
0x1800076c1  jmp     short loc_1800076A4
0x1800076c3  lea     rax, WPP_RECORDER_INITIALIZED
0x1800076ca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800076d1  jnz     loc_1800078EB
0x1800076d7  call    cs:__imp_GetProcessHeap
0x1800076dd  mov     rcx, rax; hHeap
0x1800076e0  mov     ebx, 50h ; 'P'
0x1800076e5  mov     r8d, ebx; dwBytes
0x1800076e8  xor     edx, edx; dwFlags
0x1800076ea  call    cs:__imp_HeapAlloc
0x1800076f0  mov     rdi, rax
0x1800076f3  test    rax, rax
0x1800076f6  jz      loc_1800079E7
0x1800076fc  mov     r8d, ebx; Size
0x1800076ff  xor     edx, edx; Val
0x180007701  mov     rcx, rax; void *
0x180007704  call    memset_0
0x180007709  lea     rdx, [rdi+10h]
0x18000770d  mov     rcx, r14
0x180007710  call    DafStringCopy
0x180007715  mov     ebx, eax
0x180007717  test    eax, eax
0x180007719  jns     loc_18000793A
0x18000771f  mov     rcx, rdi; lpMem
0x180007722  call    ?FreeAepServiceEntry@@YAXPEAU_AEP_SERVICE_ENTRY@@@Z; FreeAepServiceEntry(_AEP_SERVICE_ENTRY *)
0x180007727  xor     esi, esi
0x180007729  jmp     short loc_180007745
0x18000772b  mov     rcx, [r15+88h]
0x180007732  test    byte ptr [rcx+28h], 1
0x180007736  jnz     loc_180007917
0x18000773c  test    rdi, rdi
0x18000773f  jnz     loc_180007802
0x180007745  lea     r12, WPP_RECORDER_INITIALIZED
0x18000774c  lea     r14, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x180007753  mov     rcx, r13; lpCriticalSection
0x180007756  call    cs:__imp_LeaveCriticalSection
0x18000775c  mov     rdi, rsi
0x18000775f  cmp     [rbp+Table.BalancedRoot.RightChild], rsi
0x180007763  ja      loc_1800078CC
0x180007769  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180007770  jnz     loc_180007A24
0x180007776  lea     rax, ??_7?$DafDynamicArray@U_DEVPROPERTY@@@@6B@; const DafDynamicArray<_DEVPROPERTY>::`vftable'
0x18000777d  mov     [rbp+Table.BalancedRoot.Parent], rax
0x180007781  mov     [rbp+Table.BalancedRoot.RightChild], rsi
0x180007785  mov     rdx, [rbp+Table.BalancedRoot.LeftChild]; Buffer
0x180007789  test    rdx, rdx
0x18000778c  jz      short loc_18000779E
0x18000778e  lea     rcx, [rbp+Table]; Table
0x180007792  call    FreeTableEntry
0x180007797  mov     rdx, rsi
0x18000779a  mov     [rbp+Table.BalancedRoot.LeftChild], rdx
0x18000779e  lea     rax, ??_7?$TDynamicArray@PEAG@@6B@; const TDynamicArray<ushort *>::`vftable'
0x1800077a5  mov     [rbp+Table.BalancedRoot.Parent], rax
0x1800077a9  mov     [rbp+Table.BalancedRoot.RightChild], rsi
0x1800077ad  test    rdx, rdx
0x1800077b0  jz      short loc_1800077BC
0x1800077b2  lea     rcx, [rbp+Table]
0x1800077b6  call    ?free@?$TDynamicArray@U_DEVPROPERTY@@@@MEAAXPEAX@Z; TDynamicArray<_DEVPROPERTY>::free(void *)
0x1800077bb  nop
0x1800077bc  mov     eax, ebx
0x1800077be  add     rsp, 68h
0x1800077c2  pop     r15
0x1800077c4  pop     r14
0x1800077c6  pop     r13
0x1800077c8  pop     r12
0x1800077ca  pop     rdi
0x1800077cb  pop     rsi
0x1800077cc  pop     rbx
0x1800077cd  pop     rbp
0x1800077ce  retn
0x1800077cf  test    rdi, rdi
0x1800077d2  jz      loc_1800076C3
0x1800077d8  lea     rax, [rbp+Table]
0x1800077dc  mov     [rsp+68h+var_40], rax; int
0x1800077e1  mov     qword ptr [rsp+68h+bIgnoreCase], rdi
0x1800077e6  mov     r9, [rbp+arg_20]
0x1800077ea  mov     r8d, [rbp+arg_18]
0x1800077ee  mov     edx, r12d
0x1800077f1  call    ?UpdateAepServiceEntry@CQueryContext@@IEAAJW4_DEV_QUERY_RESULT_ACTION@@KQEAU_DEVPROPERTY@@PEAU_AEP_SERVICE_ENTRY@@AEAV?$DafDynamicArray@U_DEVPROPCOMPKEY@@@@@Z; CQueryContext::UpdateAepServiceEntry(_DEV_QUERY_RESULT_ACTION,ulong,_DEVPROPERTY * const,_AEP_SERVICE_ENTRY *,DafDynamicArray<_DEVPROPCOMPKEY> &)
0x1800077f6  mov     ebx, eax
0x1800077f8  xor     esi, esi
0x1800077fa  test    eax, eax
0x1800077fc  jns     loc_18000772B
0x180007802  cmp     r12d, 3
0x180007806  jnz     loc_180007745
0x18000780c  lea     r12, WPP_RECORDER_INITIALIZED
0x180007813  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000781a  jnz     loc_1800079F1
0x180007820  lea     r14, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x180007827  mov     rax, [rdi]
0x18000782a  cmp     [rax+8], rdi
0x18000782e  jnz     loc_180007A1D
0x180007834  mov     rcx, [rdi+8]
0x180007838  cmp     [rcx], rdi
0x18000783b  jnz     loc_180007A1D
0x180007841  mov     [rcx], rax
0x180007844  mov     [rax+8], rcx
0x180007848  mov     rcx, rdi; lpMem
0x18000784b  call    ?FreeAepServiceEntry@@YAXPEAU_AEP_SERVICE_ENTRY@@@Z; FreeAepServiceEntry(_AEP_SERVICE_ENTRY *)
0x180007850  jmp     loc_180007753
0x180007855  mov     r10, [rcx+18h]
0x180007859  test    r10, r10
0x18000785c  jz      loc_180007678
0x180007862  mov     rcx, r9
0x180007865  mov     rax, r10
0x180007868  cmp     [rax], si
0x18000786b  jz      short loc_180007877
0x18000786d  add     rax, 2
0x180007871  sub     rcx, 1
0x180007875  jnz     short loc_180007868
0x180007877  mov     rax, rcx
0x18000787a  neg     rax
0x18000787d  sbb     ebx, ebx
0x18000787f  not     ebx
0x180007881  and     ebx, r8d
0x180007884  mov     rax, rcx
0x180007887  sub     r9, rcx
0x18000788a  neg     rax
0x18000788d  sbb     rdx, rdx
0x180007890  and     rdx, r9
0x180007893  test    rcx, rcx
0x180007896  jz      loc_18000767B
0x18000789c  lea     r9d, [rdx+1]; cchCount2
0x1800078a0  lea     edx, [r11+1]; cchCount1
0x1800078a4  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x1800078ac  mov     r8, r10; lpString2
0x1800078af  mov     rcx, r14; lpString1
0x1800078b2  call    cs:__imp_CompareStringOrdinal
0x1800078b8  test    eax, eax
0x1800078ba  jz      loc_180007964
0x1800078c0  cmp     eax, 2
0x1800078c3  setz    dil
0x1800078c7  jmp     loc_180007683
0x1800078cc  mov     rcx, rdi
0x1800078cf  shl     rcx, 5
0x1800078d3  add     rcx, [rbp+Table.BalancedRoot.LeftChild]
0x1800078d7  call    DafDevPropCompKeyFree
0x1800078dc  inc     rdi
0x1800078df  cmp     rdi, [rbp+Table.BalancedRoot.RightChild]
0x1800078e3  jnb     loc_180007769
0x1800078e9  jmp     short loc_1800078CC
0x1800078eb  mov     r9d, 1Ch; int
0x1800078f1  mov     [rsp+68h+var_40], r14; __int64
0x1800078f6  lea     rax, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x1800078fd  mov     qword ptr [rsp+68h+bIgnoreCase], rax; MessageGuid
0x180007902  mov     rcx, cs:WPP_GLOBAL_Control
0x180007909  mov     rcx, [rcx+28h]; int
0x18000790d  call    WPP_RECORDER_SF_S
0x180007912  jmp     loc_1800076D7
0x180007917  lea     r9, [rbp+Table]
0x18000791b  mov     r8, rdi
0x18000791e  mov     edx, r12d; char
0x180007921  mov     rcx, r15; char
0x180007924  call    ?MakeResult@CQueryContext@@IEAAJW4_DEV_QUERY_RESULT_ACTION@@PEAU_LIST_ENTRY@@AEAV?$DafDynamicArray@U_DEVPROPCOMPKEY@@@@@Z; CQueryContext::MakeResult(_DEV_QUERY_RESULT_ACTION,_LIST_ENTRY *,DafDynamicArray<_DEVPROPCOMPKEY> &)
0x180007929  mov     ebx, eax
0x18000792b  jmp     loc_18000773C
0x180007930  mov     ebx, 80070057h
0x180007935  jmp     loc_18000767B
0x18000793a  lea     rcx, [rdi+28h]; lpCriticalSection
0x18000793e  call    cs:__imp_InitializeCriticalSection
0x180007944  mov     rax, [rsi+8]
0x180007948  cmp     [rax], rsi
0x18000794b  jnz     loc_180007A1D
0x180007951  mov     [rdi], rsi
0x180007954  mov     [rdi+8], rax
0x180007958  mov     [rax], rdi
0x18000795b  mov     [rsi+8], rdi
0x18000795f  jmp     loc_1800077D8
0x180007964  call    cs:__imp_GetLastError
0x18000796a  mov     ebx, eax
0x18000796c  test    eax, eax
0x18000796e  jle     loc_18000767B
0x180007974  movzx   ebx, ax
0x180007977  or      ebx, 80070000h
0x18000797d  jmp     loc_18000767B
0x180007982  mov     r9d, 1Ah; int
0x180007988  mov     qword ptr [rsp+68h+var_38], r15; char
0x18000798d  mov     qword ptr [rsp+68h+bIgnoreCase], rcx; MessageGuid
0x180007992  mov     rcx, cs:WPP_GLOBAL_Control
0x180007999  mov     rcx, [rcx+28h]; int
0x18000799d  call    WPP_RECORDER_SF_sq
0x1800079a2  jmp     loc_1800075F1
0x1800079a7  lea     r12, WPP_RECORDER_INITIALIZED
0x1800079ae  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800079b5  jz      loc_18000774C
0x1800079bb  mov     r9d, 1Bh; int
0x1800079c1  mov     [rsp+68h+var_40], r14; __int64
0x1800079c6  lea     r14, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x1800079cd  mov     qword ptr [rsp+68h+bIgnoreCase], r14; MessageGuid
0x1800079d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079d9  mov     rcx, [rcx+28h]; int
0x1800079dd  call    WPP_RECORDER_SF_S
0x1800079e2  jmp     loc_180007753
0x1800079e7  mov     ebx, 8007000Eh
0x1800079ec  jmp     loc_18000771F
0x1800079f1  mov     r9d, 1Dh; int
0x1800079f7  mov     [rsp+68h+var_40], r14; __int64
0x1800079fc  lea     r14, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x180007a03  mov     qword ptr [rsp+68h+bIgnoreCase], r14; MessageGuid
0x180007a08  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a0f  mov     rcx, [rcx+28h]; int
0x180007a13  call    WPP_RECORDER_SF_S
0x180007a18  jmp     loc_180007827
0x180007a1d  mov     ecx, 3
0x180007a22  int     29h; Win8: RtlFailFast(ecx)
0x180007a24  mov     r9d, 1Eh; int
0x180007a2a  mov     dword ptr [rsp+68h+var_30], ebx; char
0x180007a2e  mov     qword ptr [rsp+68h+var_38], r15; char
0x180007a33  mov     qword ptr [rsp+68h+bIgnoreCase], r14; MessageGuid
0x180007a38  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a3f  mov     rcx, [rcx+28h]; int
0x180007a43  call    WPP_RECORDER_SF_sqd
0x180007a48  jmp     loc_180007776
```
