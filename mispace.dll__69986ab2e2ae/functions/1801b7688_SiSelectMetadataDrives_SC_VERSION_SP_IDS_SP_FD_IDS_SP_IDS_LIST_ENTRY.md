# SiSelectMetadataDrives(_SC_VERSION,_SP_IDS *,_SP_FD_IDS *,_SP_IDS *,_LIST_ENTRY *)

- ea: `0x1801b7688`
- end: `0x1801b7b2d`
- name: `?SiSelectMetadataDrives@@YAHW4_SC_VERSION@@PEAU_SP_IDS@@PEAU_SP_FD_IDS@@1PEAU_LIST_ENTRY@@@Z`
- size: `1189`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801b8db0`
- `0x1801bbf68`
- `0x1801c1468`

## callees

- `0x180006350`
- `0x180006dd4`
- `0x1801b6d1c`
- `0x1801b7688`
- `0x1801c2740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b779d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b79f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b779d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b79f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b7a7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b7a7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801b7787`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801b7787`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1801b799d`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1801b7a66`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1801b799d`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1801b7a66`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1801b7936`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1801b7936`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1801b79c6`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1801b7a49`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1801b79c6`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1801b7a49`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1801b78b4`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1801b78b4`
- `bcrypt!BCryptGenRandom` at `0x1801b7916`
- `bcrypt!BCryptGenRandom` at `0x1801b7916`

## pseudocode

```c
__int64 __fastcall SiSelectMetadataDrives(unsigned int a1, __int64 a2, int *a3, __int64 a4, __int64 *a5)
{
  unsigned int v9; // edx
  __int64 v10; // rcx
  int v11; // r12d
  __int64 *k; // rax
  _DWORD *v13; // rax
  __int64 v14; // r8
  __int64 v15; // rcx
  _QWORD *v16; // rax
  int v17; // r14d
  int v18; // ebx
  _QWORD **v19; // rsi
  _QWORD *v20; // rax
  unsigned int v21; // ecx
  unsigned int v22; // r15d
  struct _RTL_AVL_TABLE *v23; // r14
  struct _RTL_AVL_TABLE *Parent; // rsi
  _QWORD **v25; // r13
  _QWORD *i; // rbx
  _QWORD *v27; // rdx
  int LeftChild; // eax
  int v29; // esi
  signed int v30; // r13d
  struct _RTL_AVL_TABLE *j; // rbx
  DWORD v32; // ecx
  _QWORD *v33; // rax
  BOOLEAN v34; // al
  _QWORD **v35; // rbx
  _QWORD *v36; // rax
  __int64 v37; // rcx
  _QWORD *v38; // rdx
  _QWORD *v39; // r14
  struct _RTL_AVL_TABLE *v40; // rsi
  PVOID v41; // rax
  __int64 *v42; // rcx
  __int64 *v43; // rax
  __int64 v44; // rax
  unsigned __int8 NewElement[4]; // [rsp+30h] [rbp-A1h] BYREF
  __int64 v47; // [rsp+38h] [rbp-99h] BYREF
  __int64 *v48; // [rsp+40h] [rbp-91h]
  _QWORD *Buffer; // [rsp+48h] [rbp-89h] BYREF
  PVOID v50; // [rsp+50h] [rbp-81h] BYREF
  PVOID RestartKey; // [rsp+58h] [rbp-79h] BYREF
  __int64 v52; // [rsp+60h] [rbp-71h] BYREF
  _QWORD v53[11]; // [rsp+68h] [rbp-69h] BYREF
  _QWORD v54[2]; // [rsp+C0h] [rbp-11h] BYREF

  v52 = 0;
  memset_0(v53, 0, 0x68u);
  Buffer = 0;
  v48 = &v47;
  v9 = 0;
  RestartKey = 0;
  v47 = (__int64)&v47;
  *(_DWORD *)NewElement = 1;
  do
  {
    v10 = 2LL * (int)v9++;
    v53[v10] = &v53[v10 - 1];
    v53[v10 - 1] = &v53[v10 - 1];
  }
  while ( v9 < 7 );
  v11 = 6;
  if ( a1 > 8 )
  {
    *(_DWORD *)NewElement = SiIncludeDrivesForMetadata(a1, a2, a3, a4, a5, &v47);
    if ( *(_DWORD *)NewElement && (__int64 *)v47 != &v47 )
    {
      v13 = LocalAlloc(0x40u, 0xD8u);
      if ( v13 )
      {
        *v13 = 6;
        v15 = v54[0];
        if ( *(_QWORD **)(v54[0] + 8LL) != v54 )
          goto LABEL_63;
        v16 = v13 + 50;
        v17 = 6;
        *v16 = v54[0];
        v16[1] = v54;
        *(_QWORD *)(v15 + 8) = v16;
        v54[0] = v16;
        if ( !a3 || (v18 = *a3, v18 <= 1) )
          v18 = 5;
        while ( 1 )
        {
          v19 = (_QWORD **)&v53[2 * (unsigned int)v18 - 1];
          *(_DWORD *)NewElement = SiGetFaultDomains(&v47, (unsigned int)v18, v14, v19);
          if ( !*(_DWORD *)NewElement )
            break;
          if ( v18 != 1 )
          {
            v20 = *v19;
            v21 = 0;
            if ( *v19 == v19 )
            {
LABEL_24:
              v17 = v18;
            }
            else
            {
              v14 = *(_QWORD *)&GUID_NULL.Data1;
              while ( *(_QWORD *)((char *)v20 - 196) != *(_QWORD *)&GUID_NULL.Data1
                   || *(_QWORD *)((char *)v20 - 188) != *(_QWORD *)GUID_NULL.Data4 )
              {
                v20 = (_QWORD *)*v20;
                ++v21;
                if ( v20 == v19 )
                {
                  if ( v21 >= 5 )
                    goto LABEL_26;
                  goto LABEL_24;
                }
              }
            }
            if ( --v18 > 0 )
              continue;
          }
LABEL_26:
          v22 = 0;
          v23 = (struct _RTL_AVL_TABLE *)&v53[2 * v17 - 1];
          Parent = (struct _RTL_AVL_TABLE *)v23->BalancedRoot.Parent;
          if ( (struct _RTL_AVL_TABLE *)v23->BalancedRoot.Parent != v23 )
          {
            v25 = (_QWORD **)&v53[2 * v18 - 1];
            while ( 2 )
            {
              RtlInitializeGenericTableAvl(
                Parent - 1,
                SiFdTableCompareRoutine,
                SiTableAllocateRoutine,
                SiTableFreeRoutine,
                0);
              for ( i = *v25; i != v25; i = (_QWORD *)*i )
              {
                v27 = i - 25;
                Buffer = i - 25;
                LeftChild = (int)Parent[-2].BalancedRoot.LeftChild;
                if ( LeftChild == 6
                  || *(struct _RTL_BALANCED_LINKS **)((char *)&v27[2 * (unsigned int)(LeftChild - 2) + 2] + 4) == *(struct _RTL_BALANCED_LINKS **)((char *)&Parent[-2].BalancedRoot.LeftChild + 4)
                  && *(struct _RTL_BALANCED_LINKS **)((char *)&v27[2 * (unsigned int)(LeftChild - 2) + 3] + 4) == *(struct _RTL_BALANCED_LINKS **)((char *)&Parent[-2].BalancedRoot.RightChild + 4) )
                {
                  BCryptGenRandom(0, (PUCHAR)(v27[11] + 16LL), 4u, 2u);
                  RtlInsertElementGenericTableAvl(Parent - 1, &Buffer, 8u, NewElement);
                  if ( !*(_DWORD *)NewElement )
                  {
                    v32 = 5010;
LABEL_46:
                    SetLastError(v32);
                    goto LABEL_47;
                  }
                }
              }
              Parent = (struct _RTL_AVL_TABLE *)Parent->BalancedRoot.Parent;
              ++v22;
              if ( Parent != v23 )
                continue;
              break;
            }
          }
          v29 = 0;
          v30 = (v22 + 4 - (v22 + 4) % v22) / v22;
          if ( v30 > 0 )
          {
            while ( 2 )
            {
              for ( j = (struct _RTL_AVL_TABLE *)v23->BalancedRoot.Parent;
                    j != v23;
                    j = (struct _RTL_AVL_TABLE *)j->BalancedRoot.Parent )
              {
                RestartKey = 0;
                v33 = RtlEnumerateGenericTableWithoutSplayingAvl(j - 1, &RestartKey);
                if ( v33 )
                {
                  Buffer = (_QWORD *)*v33;
                  *(_DWORD *)(Buffer[11] + 20LL) |= 4u;
                  v34 = RtlDeleteElementGenericTableAvl(j - 1, v33);
                  *(_DWORD *)NewElement = v34;
                  if ( !v34 )
                  {
                    v32 = 1168;
                    goto LABEL_46;
                  }
                }
              }
              if ( ++v29 < v30 )
                continue;
              break;
            }
          }
          goto LABEL_47;
        }
      }
      else
      {
        SetLastError(0x5AAu);
        *(_DWORD *)NewElement = 0;
      }
    }
  }
  else
  {
    for ( k = (__int64 *)*a5; k != a5; k = (__int64 *)*k )
      *((_DWORD *)k + 5) |= 4u;
  }
  do
  {
LABEL_47:
    v35 = (_QWORD **)&v53[2 * (unsigned int)v11 - 1];
    while ( 1 )
    {
      v36 = *v35;
      if ( *v35 == v35 )
        break;
      v37 = *v36;
      if ( *(_QWORD **)(*v36 + 8LL) != v36 )
        goto LABEL_63;
      v38 = (_QWORD *)v36[1];
      if ( (_QWORD *)*v38 != v36 )
        goto LABEL_63;
      v39 = v36 - 25;
      *v38 = v37;
      v40 = (struct _RTL_AVL_TABLE *)(v36 - 13);
      *(_QWORD *)(v37 + 8) = v38;
      while ( 1 )
      {
        v50 = 0;
        v41 = RtlEnumerateGenericTableWithoutSplayingAvl(v40, &v50);
        if ( !v41 )
          break;
        RtlDeleteElementGenericTableAvl(v40, v41);
      }
      LocalFree(v39);
    }
    --v11;
  }
  while ( v11 >= 0 );
  if ( *(__int64 **)(*a5 + 8) != a5
    || (v42 = (__int64 *)a5[1], (__int64 *)*v42 != a5)
    || *(__int64 **)(v47 + 8) != &v47
    || (__int64 *)*v48 != &v47
    || (*v42 = (__int64)&v47,
        v43 = v48,
        a5[1] = (__int64)v48,
        *v43 = (__int64)a5,
        v44 = v47,
        v48 = v42,
        *(__int64 **)(v47 + 8) != &v47)
    || (__int64 *)*v42 != &v47 )
  {
LABEL_63:
    __fastfail(3u);
  }
  *v42 = v47;
  *(_QWORD *)(v44 + 8) = v42;
  return *(unsigned int *)NewElement;
}

```

## disassembly

```asm
0x1801b7688  push    rbp
0x1801b768a  push    rbx
0x1801b768b  push    rsi
0x1801b768c  push    rdi
0x1801b768d  push    r12
0x1801b768f  push    r13
0x1801b7691  push    r14
0x1801b7693  push    r15
0x1801b7695  lea     rbp, [rsp-17h]
0x1801b769a  sub     rsp, 0E8h
0x1801b76a1  mov     rax, cs:__security_cookie
0x1801b76a8  xor     rax, rsp
0x1801b76ab  mov     [rbp+4Fh+var_50], rax
0x1801b76af  mov     rdi, [rbp+4Fh+arg_20]
0x1801b76b3  mov     r14, rdx
0x1801b76b6  xor     edx, edx; Val
0x1801b76b8  mov     [rbp+4Fh+var_C0], 0
0x1801b76c0  mov     rbx, r8
0x1801b76c3  mov     esi, ecx
0x1801b76c5  lea     rcx, [rbp+4Fh+var_B8]; void *
0x1801b76c9  mov     r15, r9
0x1801b76cc  lea     r8d, [rdx+68h]; Size
0x1801b76d0  call    memset_0
0x1801b76d5  lea     rax, [rsp+120h+var_E8]
0x1801b76da  mov     [rsp+120h+Buffer], 0
0x1801b76e3  mov     [rsp+120h+var_E0], rax
0x1801b76e8  xor     edx, edx
0x1801b76ea  lea     rax, [rsp+120h+var_E8]
0x1801b76ef  mov     [rbp+4Fh+RestartKey], 0
0x1801b76f7  mov     [rsp+120h+var_E8], rax
0x1801b76fc  mov     dword ptr [rsp+120h+NewElement], 1
0x1801b7704  movsxd  rcx, edx
0x1801b7707  lea     rax, [rbp+4Fh+var_C0]
0x1801b770b  shl     rcx, 4
0x1801b770f  inc     edx
0x1801b7711  add     rax, rcx
0x1801b7714  mov     [rbp+rcx+4Fh+var_B8], rax
0x1801b7719  mov     [rax], rax
0x1801b771c  cmp     edx, 7
0x1801b771f  jb      short loc_1801B7704
0x1801b7721  mov     r12d, 6
0x1801b7727  cmp     esi, 8
0x1801b772a  ja      short loc_1801B7742
0x1801b772c  mov     rax, [rdi]
0x1801b772f  jmp     short loc_1801B7738
0x1801b7731  or      dword ptr [rax+14h], 4
0x1801b7735  mov     rax, [rax]
0x1801b7738  cmp     rax, rdi
0x1801b773b  jnz     short loc_1801B7731
0x1801b773d  jmp     loc_1801B79FF
0x1801b7742  lea     rax, [rsp+120h+var_E8]
0x1801b7747  mov     r9, r15
0x1801b774a  mov     [rsp+120h+var_F8], rax
0x1801b774f  mov     r8, rbx
0x1801b7752  mov     rdx, r14
0x1801b7755  mov     [rsp+120h+TableContext], rdi
0x1801b775a  mov     ecx, esi
0x1801b775c  call    ?SiIncludeDrivesForMetadata@@YAHW4_SC_VERSION@@PEAU_SP_IDS@@PEAU_SP_FD_IDS@@1PEAU_LIST_ENTRY@@3@Z; SiIncludeDrivesForMetadata(_SC_VERSION,_SP_IDS *,_SP_FD_IDS *,_SP_IDS *,_LIST_ENTRY *,_LIST_ENTRY *)
0x1801b7761  mov     dword ptr [rsp+120h+NewElement], eax
0x1801b7765  test    eax, eax
0x1801b7767  jz      loc_1801B79FF
0x1801b776d  lea     rax, [rsp+120h+var_E8]
0x1801b7772  cmp     [rsp+120h+var_E8], rax
0x1801b7777  jz      loc_1801B79FF
0x1801b777d  mov     edx, 0D8h; uBytes
0x1801b7782  mov     ecx, 40h ; '@'; uFlags
0x1801b7787  call    cs:__imp_LocalAlloc
0x1801b778e  nop     dword ptr [rax+rax+00h]
0x1801b7793  test    rax, rax
0x1801b7796  jnz     short loc_1801B77B6
0x1801b7798  mov     ecx, 5AAh; dwErrCode
0x1801b779d  call    cs:__imp_SetLastError
0x1801b77a4  nop     dword ptr [rax+rax+00h]
0x1801b77a9  mov     dword ptr [rsp+120h+NewElement], 0
0x1801b77b1  jmp     loc_1801B79FF
0x1801b77b6  mov     [rax], r12d
0x1801b77b9  lea     rdx, [rbp+4Fh+var_60]
0x1801b77bd  mov     rcx, [rbp+4Fh+var_60]
0x1801b77c1  cmp     [rcx+8], rdx
0x1801b77c5  jnz     loc_1801B7B26
0x1801b77cb  add     rax, 0C8h
0x1801b77d1  lea     rdx, [rbp+4Fh+var_60]
0x1801b77d5  mov     r14d, r12d
0x1801b77d8  mov     [rax], rcx
0x1801b77db  mov     [rax+8], rdx
0x1801b77df  mov     [rcx+8], rax
0x1801b77e3  mov     [rbp+4Fh+var_60], rax
0x1801b77e7  test    rbx, rbx
0x1801b77ea  jz      short loc_1801B77F3
0x1801b77ec  mov     ebx, [rbx]
0x1801b77ee  cmp     ebx, 1
0x1801b77f1  jg      short loc_1801B77F8
0x1801b77f3  mov     ebx, 5
0x1801b77f8  mov     eax, ebx
0x1801b77fa  lea     rsi, [rbp+4Fh+var_C0]
0x1801b77fe  shl     rax, 4
0x1801b7802  lea     rcx, [rsp+120h+var_E8]
0x1801b7807  add     rsi, rax
0x1801b780a  mov     edx, ebx
0x1801b780c  mov     r9, rsi
0x1801b780f  call    ?SiGetFaultDomains@@YAHPEAU_LIST_ENTRY@@W4_SC_FD_TYPE@@H0@Z; SiGetFaultDomains(_LIST_ENTRY *,_SC_FD_TYPE,int,_LIST_ENTRY *)
0x1801b7814  mov     dword ptr [rsp+120h+NewElement], eax
0x1801b7818  test    eax, eax
0x1801b781a  jz      loc_1801B79FF
0x1801b7820  cmp     ebx, 1
0x1801b7823  jz      short loc_1801B7867
0x1801b7825  mov     rax, [rsi]
0x1801b7828  xor     ecx, ecx
0x1801b782a  cmp     rax, rsi
0x1801b782d  jz      short loc_1801B785E
0x1801b782f  mov     rdx, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data4; _GUID const GUID_NULL ...
0x1801b7836  mov     r8, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x1801b783d  cmp     [rax-0C4h], r8
0x1801b7844  jnz     short loc_1801B784F
0x1801b7846  cmp     [rax-0BCh], rdx
0x1801b784d  jz      short loc_1801B7861
0x1801b784f  mov     rax, [rax]
0x1801b7852  inc     ecx
0x1801b7854  cmp     rax, rsi
0x1801b7857  jnz     short loc_1801B783D
0x1801b7859  cmp     ecx, 5
0x1801b785c  jnb     short loc_1801B7867
0x1801b785e  mov     r14d, ebx
0x1801b7861  dec     ebx
0x1801b7863  test    ebx, ebx
0x1801b7865  jg      short loc_1801B77F8
0x1801b7867  movsxd  rax, r14d
0x1801b786a  xor     r15d, r15d
0x1801b786d  shl     rax, 4
0x1801b7871  lea     r14, [rbp+4Fh+var_C0]
0x1801b7875  add     r14, rax
0x1801b7878  mov     rsi, [r14]
0x1801b787b  cmp     rsi, r14
0x1801b787e  jz      loc_1801B7964
0x1801b7884  movsxd  rax, ebx
0x1801b7887  lea     r13, [rbp+4Fh+var_C0]
0x1801b788b  shl     rax, 4
0x1801b788f  add     r13, rax
0x1801b7892  lea     rcx, [rsi-68h]; Table
0x1801b7896  mov     [rsp+120h+TableContext], 0; TableContext
0x1801b789f  lea     r9, ?SiTableFreeRoutine@@YAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1801b78a6  lea     r8, ?SiTableAllocateRoutine@@YAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1801b78ad  lea     rdx, ?SiFdTableCompareRoutine@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1801b78b4  call    cs:__imp_RtlInitializeGenericTableAvl
0x1801b78bb  nop     dword ptr [rax+rax+00h]
0x1801b78c0  mov     rbx, [r13+0]
0x1801b78c4  jmp     loc_1801B794C
0x1801b78c9  lea     rdx, [rbx-0C8h]
0x1801b78d0  mov     [rsp+120h+Buffer], rdx
0x1801b78d5  mov     eax, [rsi-0C8h]
0x1801b78db  cmp     eax, r12d
0x1801b78de  jz      short loc_1801B7904
0x1801b78e0  add     eax, 0FFFFFFFEh
0x1801b78e3  mov     ecx, eax
0x1801b78e5  add     rcx, rcx
0x1801b78e8  mov     rax, [rdx+rcx*8+14h]
0x1801b78ed  cmp     rax, [rsi-0C4h]
0x1801b78f4  jnz     short loc_1801B7949
0x1801b78f6  mov     rax, [rdx+rcx*8+1Ch]
0x1801b78fb  cmp     rax, [rsi-0BCh]
0x1801b7902  jnz     short loc_1801B7949
0x1801b7904  mov     rdx, [rdx+58h]
0x1801b7908  xor     ecx, ecx; hAlgorithm
0x1801b790a  add     rdx, 10h; pbBuffer
0x1801b790e  lea     r9d, [rcx+2]; dwFlags
0x1801b7912  lea     r8d, [rcx+4]; cbBuffer
0x1801b7916  call    cs:__imp_BCryptGenRandom
0x1801b791d  nop     dword ptr [rax+rax+00h]
0x1801b7922  lea     r9, [rsp+120h+NewElement]; NewElement
0x1801b7927  mov     r8d, 8; BufferSize
0x1801b792d  lea     rdx, [rsp+120h+Buffer]; Buffer
0x1801b7932  lea     rcx, [rsi-68h]; Table
0x1801b7936  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1801b793d  nop     dword ptr [rax+rax+00h]
0x1801b7942  cmp     dword ptr [rsp+120h+NewElement], 0
0x1801b7947  jz      short loc_1801B7986
0x1801b7949  mov     rbx, [rbx]
0x1801b794c  cmp     rbx, r13
0x1801b794f  jnz     loc_1801B78C9
0x1801b7955  mov     rsi, [rsi]
0x1801b7958  inc     r15d
0x1801b795b  cmp     rsi, r14
0x1801b795e  jnz     loc_1801B7892
0x1801b7964  xor     edx, edx
0x1801b7966  lea     ecx, [r15+4]
0x1801b796a  mov     eax, ecx
0x1801b796c  xor     esi, esi
0x1801b796e  div     r15d
0x1801b7971  sub     ecx, edx
0x1801b7973  xor     edx, edx
0x1801b7975  mov     eax, ecx
0x1801b7977  div     r15d
0x1801b797a  mov     r13d, eax
0x1801b797d  test    eax, eax
0x1801b797f  jle     short loc_1801B79FF
0x1801b7981  mov     rbx, [r14]
0x1801b7984  jmp     short loc_1801B79E0
0x1801b7986  mov     ecx, 1392h
0x1801b798b  jmp     short loc_1801B79F3
0x1801b798d  lea     rdx, [rbp+4Fh+RestartKey]; RestartKey
0x1801b7991  mov     [rbp+4Fh+RestartKey], 0
0x1801b7999  lea     rcx, [rbx-68h]; Table
0x1801b799d  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1801b79a4  nop     dword ptr [rax+rax+00h]
0x1801b79a9  test    rax, rax
0x1801b79ac  jz      short loc_1801B79DD
0x1801b79ae  mov     rdx, [rax]
0x1801b79b1  lea     rcx, [rbx-68h]; Table
0x1801b79b5  mov     [rsp+120h+Buffer], rdx
0x1801b79ba  mov     r8, [rdx+58h]
0x1801b79be  mov     rdx, rax; Buffer
0x1801b79c1  or      dword ptr [r8+14h], 4
0x1801b79c6  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1801b79cd  nop     dword ptr [rax+rax+00h]
0x1801b79d2  movzx   eax, al
0x1801b79d5  mov     dword ptr [rsp+120h+NewElement], eax
0x1801b79d9  test    eax, eax
0x1801b79db  jz      short loc_1801B79EE
0x1801b79dd  mov     rbx, [rbx]
0x1801b79e0  cmp     rbx, r14
0x1801b79e3  jnz     short loc_1801B798D
0x1801b79e5  inc     esi
0x1801b79e7  cmp     esi, r13d
0x1801b79ea  jl      short loc_1801B7981
0x1801b79ec  jmp     short loc_1801B79FF
0x1801b79ee  mov     ecx, 490h; dwErrCode
0x1801b79f3  call    cs:__imp_SetLastError
0x1801b79fa  nop     dword ptr [rax+rax+00h]
0x1801b79ff  mov     eax, r12d
0x1801b7a02  lea     rbx, [rbp+4Fh+var_C0]
0x1801b7a06  shl     rax, 4
0x1801b7a0a  add     rbx, rax
0x1801b7a0d  mov     rax, [rbx]
0x1801b7a10  cmp     rax, rbx
0x1801b7a13  jz      short loc_1801B7A88
0x1801b7a15  mov     rcx, [rax]
0x1801b7a18  cmp     [rcx+8], rax
0x1801b7a1c  jnz     loc_1801B7B26
0x1801b7a22  mov     rdx, [rax+8]
0x1801b7a26  cmp     [rdx], rax
0x1801b7a29  jnz     loc_1801B7B26
0x1801b7a2f  lea     r14, [rax-0C8h]
0x1801b7a36  mov     [rdx], rcx
0x1801b7a39  lea     rsi, [r14+60h]
0x1801b7a3d  mov     [rcx+8], rdx
0x1801b7a41  jmp     short loc_1801B7A55
0x1801b7a43  mov     rdx, rax; Buffer
0x1801b7a46  mov     rcx, rsi; Table
0x1801b7a49  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1801b7a50  nop     dword ptr [rax+rax+00h]
0x1801b7a55  lea     rdx, [rsp+120h+var_D0]; RestartKey
0x1801b7a5a  mov     [rsp+120h+var_D0], 0
0x1801b7a63  mov     rcx, rsi; Table
0x1801b7a66  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1801b7a6d  nop     dword ptr [rax+rax+00h]
0x1801b7a72  test    rax, rax
0x1801b7a75  jnz     short loc_1801B7A43
0x1801b7a77  mov     rcx, r14; hMem
0x1801b7a7a  call    cs:__imp_LocalFree
0x1801b7a81  nop     dword ptr [rax+rax+00h]
0x1801b7a86  jmp     short loc_1801B7A0D
0x1801b7a88  sub     r12d, 1
0x1801b7a8c  jns     loc_1801B79FF
0x1801b7a92  mov     rax, [rdi]
0x1801b7a95  cmp     [rax+8], rdi
0x1801b7a99  jnz     loc_1801B7B26
0x1801b7a9f  mov     rcx, [rdi+8]
0x1801b7aa3  cmp     [rcx], rdi
0x1801b7aa6  jnz     short loc_1801B7B26
0x1801b7aa8  mov     rax, [rsp+120h+var_E8]
0x1801b7aad  lea     rdx, [rsp+120h+var_E8]
0x1801b7ab2  cmp     [rax+8], rdx
0x1801b7ab6  jnz     short loc_1801B7B26
0x1801b7ab8  mov     rax, [rsp+120h+var_E0]
0x1801b7abd  lea     rdx, [rsp+120h+var_E8]
0x1801b7ac2  cmp     [rax], rdx
0x1801b7ac5  jnz     short loc_1801B7B26
0x1801b7ac7  lea     rax, [rsp+120h+var_E8]
0x1801b7acc  mov     [rcx], rax
0x1801b7acf  lea     rdx, [rsp+120h+var_E8]
0x1801b7ad4  mov     rax, [rsp+120h+var_E0]
0x1801b7ad9  mov     [rdi+8], rax
0x1801b7add  mov     [rax], rdi
0x1801b7ae0  mov     rax, [rsp+120h+var_E8]
0x1801b7ae5  mov     [rsp+120h+var_E0], rcx
0x1801b7aea  cmp     [rax+8], rdx
0x1801b7aee  jnz     short loc_1801B7B26
0x1801b7af0  lea     rdx, [rsp+120h+var_E8]
0x1801b7af5  cmp     [rcx], rdx
0x1801b7af8  jnz     short loc_1801B7B26
0x1801b7afa  mov     [rcx], rax
0x1801b7afd  mov     [rax+8], rcx
0x1801b7b01  mov     eax, dword ptr [rsp+120h+NewElement]
0x1801b7b05  mov     rcx, [rbp+4Fh+var_50]
0x1801b7b09  xor     rcx, rsp; StackCookie
0x1801b7b0c  call    __security_check_cookie
0x1801b7b11  add     rsp, 0E8h
0x1801b7b18  pop     r15
0x1801b7b1a  pop     r14
0x1801b7b1c  pop     r13
  ... truncated ...
```
