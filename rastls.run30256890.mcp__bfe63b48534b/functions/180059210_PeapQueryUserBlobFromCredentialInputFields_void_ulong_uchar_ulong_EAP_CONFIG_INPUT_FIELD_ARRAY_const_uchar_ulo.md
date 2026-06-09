# PeapQueryUserBlobFromCredentialInputFields(void *,ulong,uchar *,ulong,_EAP_CONFIG_INPUT_FIELD_ARRAY const *,uchar * *,ulong *)

- ea: `0x180059210`
- end: `0x1800595f7`
- name: `?PeapQueryUserBlobFromCredentialInputFields@@YAKPEAXKPEAEKPEBU_EAP_CONFIG_INPUT_FIELD_ARRAY@@PEAPEAEPEAK@Z`
- size: `999`
- prototype: `unsigned int(void *, unsigned int, unsigned __int8 *, unsigned int, const struct _EAP_CONFIG_INPUT_FIELD_ARRAY *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18005d850`

## callees

- `0x180003118`
- `0x180003240`
- `0x18000437c`
- `0x180005010`
- `0x180007d00`
- `0x180025b08`
- `0x180038e4c`
- `0x18004d58c`
- `0x180059210`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059352`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800593d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059352`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800593d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800593e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800594ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800593e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800594ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800594d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800594d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005952a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005955d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800595ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005952a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005955d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800595ba`

## pseudocode

```c
__int64 __fastcall PeapQueryUserBlobFromCredentialInputFields(
        void *a1,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        const struct _EAP_CONFIG_INPUT_FIELD_ARRAY *a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  FARPROC v7; // r15
  unsigned __int8 *v8; // r13
  unsigned int InnerConnectionData; // eax
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rcx
  DWORD ListNode; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  unsigned int v20; // r14d
  struct _EAPTLS_CONTROL_BLOCK *v21; // rcx
  __int64 v22; // rdx
  struct _PEAP_EAP_INFO *v23; // rbx
  FARPROC ProcAddress; // rdi
  struct _EAPTLS_CONTROL_BLOCK *v25; // rcx
  __int64 v26; // rdx
  size_t v27; // rbx
  void *v28; // r12
  unsigned int v29; // esi
  unsigned __int8 *v30; // rax
  unsigned __int8 *v31; // rdi
  unsigned int v33; // [rsp+50h] [rbp-31h] BYREF
  unsigned int v34; // [rsp+54h] [rbp-2Dh] BYREF
  size_t Size; // [rsp+58h] [rbp-29h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-21h] BYREF
  void *Src; // [rsp+68h] [rbp-19h] BYREF
  HLOCAL v38; // [rsp+70h] [rbp-11h] BYREF
  struct _PEAP_EAP_INFO *v39; // [rsp+78h] [rbp-9h] BYREF

  v7 = 0;
  v38 = 0;
  v8 = 0;
  v39 = 0;
  LODWORD(Size) = 0;
  v33 = 0;
  hMem = 0;
  v34 = 0;
  Src = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 744, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
  InnerConnectionData = GetInnerConnectionData(a2, a4, a3, &v33, (unsigned __int8 **)&hMem, &v34);
  ListNode = InnerConnectionData;
  if ( InnerConnectionData )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v18 = 745;
LABEL_6:
      v19 = InnerConnectionData;
LABEL_40:
      WPP_SF_d(*((_QWORD *)v17 + 2), v18, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v19);
      goto LABEL_41;
    }
    goto LABEL_41;
  }
  InnerConnectionData = PeapEapInfoGetList(v15, v14, (struct _PEAP_EAP_INFO **)&v38);
  ListNode = InnerConnectionData;
  if ( InnerConnectionData )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v18 = 746;
      goto LABEL_6;
    }
LABEL_41:
    LocalFree(0);
    goto LABEL_47;
  }
  v20 = v33;
  ListNode = PeapEapInfoFindListNode(v33, (struct _PEAP_EAP_INFO *)v38, &v39);
  if ( ListNode )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_41;
    v22 = 747;
LABEL_13:
    WPP_SF_DD(*((_QWORD *)v21 + 2), v22, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v20, ListNode);
    goto LABEL_41;
  }
  v23 = v39;
  ProcAddress = GetProcAddress(*((HMODULE *)v39 + 10), "RasEapQueryUserBlobFromCredentialInputFields");
  if ( !ProcAddress )
  {
    ListNode = GetLastError();
    if ( ListNode == 127 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 748, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v20);
      ListNode = 50;
      goto LABEL_41;
    }
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
LABEL_25:
      if ( !ListNode )
        goto LABEL_47;
      goto LABEL_41;
    }
    v26 = 749;
LABEL_24:
    WPP_SF_DD(*((_QWORD *)v25 + 2), v26, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v20, ListNode);
    goto LABEL_25;
  }
  v7 = GetProcAddress(*((HMODULE *)v23 + 10), "RasEapFreeMemory");
  if ( !v7 )
  {
    ListNode = GetLastError();
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_25;
    v26 = 750;
    goto LABEL_24;
  }
  ListNode = ((__int64 (__fastcall *)(_QWORD, void *, _QWORD, HLOCAL, unsigned int, const struct _EAP_CONFIG_INPUT_FIELD_ARRAY *, void **, size_t *))ProcAddress)(
               v20,
               a1,
               a2 | 0x10000,
               hMem,
               v34,
               a5,
               &Src,
               &Size);
  if ( ListNode )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_41;
    v22 = 751;
    goto LABEL_13;
  }
  v27 = (unsigned int)Size;
  v28 = Src;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 733, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
  v29 = 40;
  if ( (_DWORD)v27 )
    v29 = v27 + 59;
  v30 = (unsigned __int8 *)LocalAlloc(0x40u, v29);
  v31 = v30;
  if ( v30 )
  {
    *(_DWORD *)v30 = 2;
    *((_DWORD *)v30 + 1) = v29;
    if ( (_DWORD)v27 )
    {
      *((_DWORD *)v30 + 12) = v20;
      *((_DWORD *)v30 + 9) = 1;
      *((_DWORD *)v30 + 10) = 1;
      *((_DWORD *)v30 + 13) = 0;
      *((_DWORD *)v30 + 11) = v27 + 19;
      memcpy_0(v30 + 56, v28, v27);
    }
    v8 = v31;
    ListNode = 0;
  }
  else
  {
    ListNode = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 734, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
    if ( ListNode )
    {
      LocalFree(0);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v18 = 752;
        v19 = ListNode;
        goto LABEL_40;
      }
      goto LABEL_41;
    }
    v29 = 0;
  }
  *a7 = v29;
  *a6 = v8;
LABEL_47:
  LocalFree(hMem);
  if ( v7 )
    ((void (__fastcall *)(void *))v7)(Src);
  PeapEapInfoFreeList(v38);
  return ListNode;
}

```

## disassembly

```asm
0x180059210  push    rbp
0x180059212  push    rbx
0x180059213  push    rsi
0x180059214  push    rdi
0x180059215  push    r12
0x180059217  push    r13
0x180059219  push    r14
0x18005921b  push    r15
0x18005921d  lea     rbp, [rsp-7]
0x180059222  sub     rsp, 88h
0x180059229  xor     r15d, r15d
0x18005922c  mov     [rbp+3Fh+var_50], 0
0x180059234  xor     r13d, r13d
0x180059237  mov     [rbp+3Fh+var_48], 0
0x18005923f  mov     dword ptr [rbp+3Fh+Size], r13d
0x180059243  mov     ebx, r9d
0x180059246  mov     rdi, r8
0x180059249  mov     [rbp+3Fh+var_70], r15d
0x18005924d  mov     esi, edx
0x18005924f  mov     [rbp+3Fh+hMem], r15
0x180059253  mov     r12, rcx
0x180059256  mov     [rbp+3Fh+var_6C], r15d
0x18005925a  mov     [rbp+3Fh+Src], r15
0x18005925e  mov     rcx, cs:WPP_GLOBAL_Control
0x180059265  lea     r14, WPP_GLOBAL_Control
0x18005926c  cmp     rcx, r14
0x18005926f  jz      short loc_180059286
0x180059271  mov     rcx, [rcx+10h]
0x180059275  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005927c  mov     edx, 2E8h
0x180059281  call    WPP_SF_
0x180059286  lea     rax, [rbp+3Fh+var_6C]
0x18005928a  mov     r8, rdi; unsigned __int8 *
0x18005928d  mov     [rsp+0C0h+var_98], rax; unsigned int *
0x180059292  lea     r9, [rbp+3Fh+var_70]; unsigned int *
0x180059296  lea     rax, [rbp+3Fh+hMem]
0x18005929a  mov     edx, ebx; unsigned int
0x18005929c  mov     ecx, esi; unsigned int
0x18005929e  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 **
0x1800592a3  call    ?GetInnerConnectionData@@YAKKKPEAEPEAKPEAPEAE1@Z; GetInnerConnectionData(ulong,ulong,uchar *,ulong *,uchar * *,ulong *)
0x1800592a8  mov     ebx, eax
0x1800592aa  test    eax, eax
0x1800592ac  jz      short loc_1800592CB
0x1800592ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800592b5  cmp     rcx, r14
0x1800592b8  jz      loc_18005955A
0x1800592be  mov     edx, 2E9h
0x1800592c3  mov     r9d, eax
0x1800592c6  jmp     loc_18005954A
0x1800592cb  lea     r8, [rbp+3Fh+var_50]; struct _PEAP_EAP_INFO **
0x1800592cf  call    ?PeapEapInfoGetList@@YAKPEBGHPEAPEAU_PEAP_EAP_INFO@@@Z; PeapEapInfoGetList(ushort const *,int,_PEAP_EAP_INFO * *)
0x1800592d4  mov     ebx, eax
0x1800592d6  test    eax, eax
0x1800592d8  jz      short loc_1800592F1
0x1800592da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800592e1  cmp     rcx, r14
0x1800592e4  jz      loc_18005955A
0x1800592ea  mov     edx, 2EAh
0x1800592ef  jmp     short loc_1800592C3
0x1800592f1  mov     r14d, [rbp+3Fh+var_70]
0x1800592f5  lea     r8, [rbp+3Fh+var_48]; struct _PEAP_EAP_INFO **
0x1800592f9  mov     rdx, [rbp+3Fh+var_50]; struct _PEAP_EAP_INFO *
0x1800592fd  mov     ecx, r14d; unsigned int
0x180059300  call    ?PeapEapInfoFindListNode@@YAKKPEAU_PEAP_EAP_INFO@@PEAPEAU1@@Z; PeapEapInfoFindListNode(ulong,_PEAP_EAP_INFO *,_PEAP_EAP_INFO * *)
0x180059305  mov     ebx, eax
0x180059307  test    eax, eax
0x180059309  jz      short loc_180059343
0x18005930b  mov     rcx, cs:WPP_GLOBAL_Control
0x180059312  lea     rax, WPP_GLOBAL_Control
0x180059319  cmp     rcx, rax
0x18005931c  jz      loc_18005955A
0x180059322  mov     edx, 2EBh
0x180059327  mov     rcx, [rcx+10h]
0x18005932b  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180059332  mov     r9d, r14d
0x180059335  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180059339  call    WPP_SF_DD
0x18005933e  jmp     loc_18005955A
0x180059343  mov     rbx, [rbp+3Fh+var_48]
0x180059347  lea     rdx, aRaseapqueryuse_0; "RasEapQueryUserBlobFromCredentialInputF"...
0x18005934e  mov     rcx, [rbx+50h]; hModule
0x180059352  call    cs:__imp_GetProcAddress
0x180059359  nop     dword ptr [rax+rax+00h]
0x18005935e  mov     rdi, rax
0x180059361  test    rax, rax
0x180059364  jnz     short loc_1800593C8
0x180059366  call    cs:__imp_GetLastError
0x18005936d  nop     dword ptr [rax+rax+00h]
0x180059372  mov     ebx, eax
0x180059374  cmp     eax, 7Fh
0x180059377  jnz     short loc_1800593AE
0x180059379  mov     rcx, cs:WPP_GLOBAL_Control
0x180059380  lea     rax, WPP_GLOBAL_Control
0x180059387  cmp     rcx, rax
0x18005938a  jz      short loc_1800593A4
0x18005938c  mov     rcx, [rcx+10h]
0x180059390  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180059397  mov     edx, 2ECh
0x18005939c  mov     r9d, r14d
0x18005939f  call    WPP_SF_d
0x1800593a4  mov     ebx, 32h ; '2'
0x1800593a9  jmp     loc_18005955A
0x1800593ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800593b5  lea     rax, WPP_GLOBAL_Control
0x1800593bc  cmp     rcx, rax
0x1800593bf  jz      short loc_180059424
0x1800593c1  mov     edx, 2EDh
0x1800593c6  jmp     short loc_18005940D
0x1800593c8  mov     rcx, [rbx+50h]; hModule
0x1800593cc  lea     rdx, ProcName; "RasEapFreeMemory"
0x1800593d3  call    cs:__imp_GetProcAddress
0x1800593da  nop     dword ptr [rax+rax+00h]
0x1800593df  mov     r15, rax
0x1800593e2  test    rax, rax
0x1800593e5  jnz     short loc_180059431
0x1800593e7  call    cs:__imp_GetLastError
0x1800593ee  nop     dword ptr [rax+rax+00h]
0x1800593f3  mov     ebx, eax
0x1800593f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800593fc  lea     rax, WPP_GLOBAL_Control
0x180059403  cmp     rcx, rax
0x180059406  jz      short loc_180059424
0x180059408  mov     edx, 2EEh
0x18005940d  mov     rcx, [rcx+10h]
0x180059411  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180059418  mov     r9d, r14d
0x18005941b  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18005941f  call    WPP_SF_DD
0x180059424  test    ebx, ebx
0x180059426  jz      loc_1800595B6
0x18005942c  jmp     loc_18005955A
0x180059431  mov     r9, [rbp+3Fh+hMem]
0x180059435  lea     rax, [rbp+3Fh+Size]
0x180059439  mov     [rsp+0C0h+var_88], rax
0x18005943e  bts     esi, 10h
0x180059442  lea     rax, [rbp+3Fh+Src]
0x180059446  mov     r8d, esi
0x180059449  mov     [rsp+0C0h+var_90], rax
0x18005944e  mov     rdx, r12
0x180059451  mov     rax, [rbp+3Fh+arg_20]
0x180059455  mov     ecx, r14d
0x180059458  mov     [rsp+0C0h+var_98], rax
0x18005945d  mov     eax, [rbp+3Fh+var_6C]
0x180059460  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180059464  mov     rax, rdi
0x180059467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005946c  mov     ebx, eax
0x18005946e  test    eax, eax
0x180059470  jz      short loc_180059493
0x180059472  mov     rcx, cs:WPP_GLOBAL_Control
0x180059479  lea     rax, WPP_GLOBAL_Control
0x180059480  cmp     rcx, rax
0x180059483  jz      loc_18005955A
0x180059489  mov     edx, 2EFh
0x18005948e  jmp     loc_180059327
0x180059493  mov     ebx, dword ptr [rbp+3Fh+Size]
0x180059496  mov     r12, [rbp+3Fh+Src]
0x18005949a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800594a1  lea     rax, WPP_GLOBAL_Control
0x1800594a8  cmp     rcx, rax
0x1800594ab  jz      short loc_1800594C2
0x1800594ad  mov     rcx, [rcx+10h]
0x1800594b1  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x1800594b8  mov     edx, 2DDh
0x1800594bd  call    WPP_SF_
0x1800594c2  mov     esi, 28h ; '('
0x1800594c7  test    ebx, ebx
0x1800594c9  jz      short loc_1800594CE
0x1800594cb  lea     esi, [rbx+3Bh]
0x1800594ce  mov     edx, esi; uBytes
0x1800594d0  mov     ecx, 40h ; '@'; uFlags
0x1800594d5  call    cs:__imp_LocalAlloc
0x1800594dc  nop     dword ptr [rax+rax+00h]
0x1800594e1  mov     rdi, rax
0x1800594e4  test    rax, rax
0x1800594e7  jnz     loc_18005956F
0x1800594ed  call    cs:__imp_GetLastError
0x1800594f4  nop     dword ptr [rax+rax+00h]
0x1800594f9  mov     ebx, eax
0x1800594fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180059502  lea     rsi, WPP_GLOBAL_Control
0x180059509  cmp     rcx, rsi
0x18005950c  jz      short loc_180059523
0x18005950e  mov     rcx, [rcx+10h]
0x180059512  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180059519  mov     edx, 2DEh
0x18005951e  call    WPP_SF_
0x180059523  test    ebx, ebx
0x180059525  jz      short loc_18005956B
0x180059527  mov     rcx, rdi; hMem
0x18005952a  call    cs:__imp_LocalFree
0x180059531  nop     dword ptr [rax+rax+00h]
0x180059536  mov     rcx, cs:WPP_GLOBAL_Control
0x18005953d  cmp     rcx, rsi
0x180059540  jz      short loc_18005955A
0x180059542  mov     edx, 2F0h
0x180059547  mov     r9d, ebx
0x18005954a  mov     rcx, [rcx+10h]
0x18005954e  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180059555  call    WPP_SF_d
0x18005955a  mov     rcx, r13; hMem
0x18005955d  call    cs:__imp_LocalFree
0x180059564  nop     dword ptr [rax+rax+00h]
0x180059569  jmp     short loc_1800595B6
0x18005956b  xor     esi, esi
0x18005956d  jmp     short loc_1800595A9
0x18005956f  mov     dword ptr [rax], 2
0x180059575  mov     [rax+4], esi
0x180059578  test    ebx, ebx
0x18005957a  jz      short loc_1800595A4
0x18005957c  mov     eax, 1
0x180059581  mov     [rdi+30h], r14d
0x180059585  mov     [rdi+24h], eax
0x180059588  lea     rcx, [rdi+38h]; void *
0x18005958c  mov     [rdi+28h], eax
0x18005958f  mov     r8, rbx; Size
0x180059592  lea     eax, [rbx+13h]
0x180059595  mov     [rdi+34h], r13d
0x180059599  mov     rdx, r12; Src
0x18005959c  mov     [rdi+2Ch], eax
0x18005959f  call    memcpy_0
0x1800595a4  mov     r13, rdi
0x1800595a7  xor     ebx, ebx
0x1800595a9  mov     rax, [rbp+3Fh+arg_30]
0x1800595ad  mov     [rax], esi
0x1800595af  mov     rax, [rbp+3Fh+arg_28]
0x1800595b3  mov     [rax], r13
0x1800595b6  mov     rcx, [rbp+3Fh+hMem]; hMem
0x1800595ba  call    cs:__imp_LocalFree
0x1800595c1  nop     dword ptr [rax+rax+00h]
0x1800595c6  test    r15, r15
0x1800595c9  jz      short loc_1800595D7
0x1800595cb  mov     rcx, [rbp+3Fh+Src]
0x1800595cf  mov     rax, r15
0x1800595d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595d7  mov     rcx, [rbp+3Fh+var_50]; hMem
0x1800595db  call    ?PeapEapInfoFreeList@@YAXPEAU_PEAP_EAP_INFO@@@Z; PeapEapInfoFreeList(_PEAP_EAP_INFO *)
0x1800595e0  mov     eax, ebx
0x1800595e2  add     rsp, 88h
0x1800595e9  pop     r15
0x1800595eb  pop     r14
0x1800595ed  pop     r13
0x1800595ef  pop     r12
0x1800595f1  pop     rdi
0x1800595f2  pop     rsi
0x1800595f3  pop     rbx
0x1800595f4  pop     rbp
0x1800595f5  retn
```
