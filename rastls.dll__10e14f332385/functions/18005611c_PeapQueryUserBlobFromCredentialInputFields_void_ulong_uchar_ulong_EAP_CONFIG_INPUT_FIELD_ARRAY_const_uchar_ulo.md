# PeapQueryUserBlobFromCredentialInputFields(void *,ulong,uchar *,ulong,_EAP_CONFIG_INPUT_FIELD_ARRAY const *,uchar * *,ulong *)

- ea: `0x18005611c`
- end: `0x1800564c8`
- name: `?PeapQueryUserBlobFromCredentialInputFields@@YAKPEAXKPEAEKPEBU_EAP_CONFIG_INPUT_FIELD_ARRAY@@PEAPEAEPEAK@Z`
- size: `940`
- prototype: `unsigned int(void *, unsigned int, unsigned __int8 *, unsigned int, const struct _EAP_CONFIG_INPUT_FIELD_ARRAY *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18005a4a0`

## callees

- `0x180003000`
- `0x1800030d0`
- `0x180003fec`
- `0x180004bd0`
- `0x1800075b0`
- `0x180023064`
- `0x18003623c`
- `0x18004acb8`
- `0x18005611c`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005625e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800562d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005625e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800562d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005626c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800562e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800563d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005626c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800562e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800563d7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800563c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800563c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005640e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005643b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056492`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005640e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005643b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056492`

## pseudocode

```c
__int64 __fastcall PeapQueryUserBlobFromCredentialInputFields(
        void *a1,
        int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        const struct _EAP_CONFIG_INPUT_FIELD_ARRAY *a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  FARPROC v7; // r15
  unsigned __int8 *v8; // r13
  DWORD InnerConnectionData; // eax
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 744, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
      WPP_SF_d(*((_QWORD *)v17 + 2), v18, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v19);
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
    WPP_SF_dd(*((_QWORD *)v21 + 2), v22, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v20, ListNode);
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 748, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v20);
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
    WPP_SF_dd(*((_QWORD *)v25 + 2), v26, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v20, ListNode);
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
               a2 | 0x10000u,
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 733, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 734, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
0x18005611c  push    rbp
0x18005611e  push    rbx
0x18005611f  push    rsi
0x180056120  push    rdi
0x180056121  push    r12
0x180056123  push    r13
0x180056125  push    r14
0x180056127  push    r15
0x180056129  lea     rbp, [rsp-7]
0x18005612e  sub     rsp, 88h
0x180056135  xor     r15d, r15d
0x180056138  mov     [rbp+3Fh+var_50], 0
0x180056140  xor     r13d, r13d
0x180056143  mov     [rbp+3Fh+var_48], 0
0x18005614b  mov     dword ptr [rbp+3Fh+Size], r13d
0x18005614f  mov     ebx, r9d
0x180056152  mov     rdi, r8
0x180056155  mov     [rbp+3Fh+var_70], r15d
0x180056159  mov     esi, edx
0x18005615b  mov     [rbp+3Fh+hMem], r15
0x18005615f  mov     r12, rcx
0x180056162  mov     [rbp+3Fh+var_6C], r15d
0x180056166  mov     [rbp+3Fh+Src], r15
0x18005616a  mov     rcx, cs:WPP_GLOBAL_Control
0x180056171  lea     r14, WPP_GLOBAL_Control
0x180056178  cmp     rcx, r14
0x18005617b  jz      short loc_180056192
0x18005617d  mov     rcx, [rcx+10h]
0x180056181  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180056188  mov     edx, 2E8h
0x18005618d  call    WPP_SF_
0x180056192  lea     rax, [rbp+3Fh+var_6C]
0x180056196  mov     r8, rdi; unsigned __int8 *
0x180056199  mov     [rsp+0C0h+var_98], rax; unsigned int *
0x18005619e  lea     r9, [rbp+3Fh+var_70]; unsigned int *
0x1800561a2  lea     rax, [rbp+3Fh+hMem]
0x1800561a6  mov     edx, ebx; unsigned int
0x1800561a8  mov     ecx, esi; unsigned int
0x1800561aa  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 **
0x1800561af  call    ?GetInnerConnectionData@@YAKKKPEAEPEAKPEAPEAE1@Z; GetInnerConnectionData(ulong,ulong,uchar *,ulong *,uchar * *,ulong *)
0x1800561b4  mov     ebx, eax
0x1800561b6  test    eax, eax
0x1800561b8  jz      short loc_1800561D7
0x1800561ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800561c1  cmp     rcx, r14
0x1800561c4  jz      loc_180056438
0x1800561ca  mov     edx, 2E9h
0x1800561cf  mov     r9d, eax
0x1800561d2  jmp     loc_180056428
0x1800561d7  lea     r8, [rbp+3Fh+var_50]; struct _PEAP_EAP_INFO **
0x1800561db  call    ?PeapEapInfoGetList@@YAKPEBGHPEAPEAU_PEAP_EAP_INFO@@@Z; PeapEapInfoGetList(ushort const *,int,_PEAP_EAP_INFO * *)
0x1800561e0  mov     ebx, eax
0x1800561e2  test    eax, eax
0x1800561e4  jz      short loc_1800561FD
0x1800561e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800561ed  cmp     rcx, r14
0x1800561f0  jz      loc_180056438
0x1800561f6  mov     edx, 2EAh
0x1800561fb  jmp     short loc_1800561CF
0x1800561fd  mov     r14d, [rbp+3Fh+var_70]
0x180056201  lea     r8, [rbp+3Fh+var_48]; struct _PEAP_EAP_INFO **
0x180056205  mov     rdx, [rbp+3Fh+var_50]; struct _PEAP_EAP_INFO *
0x180056209  mov     ecx, r14d; unsigned int
0x18005620c  call    ?PeapEapInfoFindListNode@@YAKKPEAU_PEAP_EAP_INFO@@PEAPEAU1@@Z; PeapEapInfoFindListNode(ulong,_PEAP_EAP_INFO *,_PEAP_EAP_INFO * *)
0x180056211  mov     ebx, eax
0x180056213  test    eax, eax
0x180056215  jz      short loc_18005624F
0x180056217  mov     rcx, cs:WPP_GLOBAL_Control
0x18005621e  lea     rax, WPP_GLOBAL_Control
0x180056225  cmp     rcx, rax
0x180056228  jz      loc_180056438
0x18005622e  mov     edx, 2EBh
0x180056233  mov     rcx, [rcx+10h]
0x180056237  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18005623e  mov     r9d, r14d
0x180056241  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180056245  call    WPP_SF_dd
0x18005624a  jmp     loc_180056438
0x18005624f  mov     rbx, [rbp+3Fh+var_48]
0x180056253  lea     rdx, aRaseapqueryuse_0; "RasEapQueryUserBlobFromCredentialInputF"...
0x18005625a  mov     rcx, [rbx+50h]; hModule
0x18005625e  call    cs:__imp_GetProcAddress
0x180056264  mov     rdi, rax
0x180056267  test    rax, rax
0x18005626a  jnz     short loc_1800562C8
0x18005626c  call    cs:__imp_GetLastError
0x180056272  mov     ebx, eax
0x180056274  cmp     eax, 7Fh
0x180056277  jnz     short loc_1800562AE
0x180056279  mov     rcx, cs:WPP_GLOBAL_Control
0x180056280  lea     rax, WPP_GLOBAL_Control
0x180056287  cmp     rcx, rax
0x18005628a  jz      short loc_1800562A4
0x18005628c  mov     rcx, [rcx+10h]
0x180056290  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180056297  mov     edx, 2ECh
0x18005629c  mov     r9d, r14d
0x18005629f  call    WPP_SF_d
0x1800562a4  mov     ebx, 32h ; '2'
0x1800562a9  jmp     loc_180056438
0x1800562ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800562b5  lea     rax, WPP_GLOBAL_Control
0x1800562bc  cmp     rcx, rax
0x1800562bf  jz      short loc_180056318
0x1800562c1  mov     edx, 2EDh
0x1800562c6  jmp     short loc_180056301
0x1800562c8  mov     rcx, [rbx+50h]; hModule
0x1800562cc  lea     rdx, ProcName; "RasEapFreeMemory"
0x1800562d3  call    cs:__imp_GetProcAddress
0x1800562d9  mov     r15, rax
0x1800562dc  test    rax, rax
0x1800562df  jnz     short loc_180056325
0x1800562e1  call    cs:__imp_GetLastError
0x1800562e7  mov     ebx, eax
0x1800562e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800562f0  lea     rax, WPP_GLOBAL_Control
0x1800562f7  cmp     rcx, rax
0x1800562fa  jz      short loc_180056318
0x1800562fc  mov     edx, 2EEh
0x180056301  mov     rcx, [rcx+10h]
0x180056305  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18005630c  mov     r9d, r14d
0x18005630f  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180056313  call    WPP_SF_dd
0x180056318  test    ebx, ebx
0x18005631a  jz      loc_18005648E
0x180056320  jmp     loc_180056438
0x180056325  mov     r9, [rbp+3Fh+hMem]
0x180056329  lea     rax, [rbp+3Fh+Size]
0x18005632d  mov     [rsp+0C0h+var_88], rax
0x180056332  bts     esi, 10h
0x180056336  lea     rax, [rbp+3Fh+Src]
0x18005633a  mov     r8d, esi
0x18005633d  mov     [rsp+0C0h+var_90], rax
0x180056342  mov     rdx, r12
0x180056345  mov     rax, [rbp+3Fh+arg_20]
0x180056349  mov     ecx, r14d
0x18005634c  mov     [rsp+0C0h+var_98], rax
0x180056351  mov     eax, [rbp+3Fh+var_6C]
0x180056354  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180056358  mov     rax, rdi
0x18005635b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056360  mov     ebx, eax
0x180056362  test    eax, eax
0x180056364  jz      short loc_180056387
0x180056366  mov     rcx, cs:WPP_GLOBAL_Control
0x18005636d  lea     rax, WPP_GLOBAL_Control
0x180056374  cmp     rcx, rax
0x180056377  jz      loc_180056438
0x18005637d  mov     edx, 2EFh
0x180056382  jmp     loc_180056233
0x180056387  mov     ebx, dword ptr [rbp+3Fh+Size]
0x18005638a  mov     r12, [rbp+3Fh+Src]
0x18005638e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056395  lea     rax, WPP_GLOBAL_Control
0x18005639c  cmp     rcx, rax
0x18005639f  jz      short loc_1800563B6
0x1800563a1  mov     rcx, [rcx+10h]
0x1800563a5  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x1800563ac  mov     edx, 2DDh
0x1800563b1  call    WPP_SF_
0x1800563b6  mov     esi, 28h ; '('
0x1800563bb  test    ebx, ebx
0x1800563bd  jz      short loc_1800563C2
0x1800563bf  lea     esi, [rbx+3Bh]
0x1800563c2  mov     edx, esi; uBytes
0x1800563c4  mov     ecx, 40h ; '@'; uFlags
0x1800563c9  call    cs:__imp_LocalAlloc
0x1800563cf  mov     rdi, rax
0x1800563d2  test    rax, rax
0x1800563d5  jnz     short loc_180056447
0x1800563d7  call    cs:__imp_GetLastError
0x1800563dd  mov     ebx, eax
0x1800563df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800563e6  lea     rsi, WPP_GLOBAL_Control
0x1800563ed  cmp     rcx, rsi
0x1800563f0  jz      short loc_180056407
0x1800563f2  mov     rcx, [rcx+10h]
0x1800563f6  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x1800563fd  mov     edx, 2DEh
0x180056402  call    WPP_SF_
0x180056407  test    ebx, ebx
0x180056409  jz      short loc_180056443
0x18005640b  mov     rcx, rdi; hMem
0x18005640e  call    cs:__imp_LocalFree
0x180056414  mov     rcx, cs:WPP_GLOBAL_Control
0x18005641b  cmp     rcx, rsi
0x18005641e  jz      short loc_180056438
0x180056420  mov     edx, 2F0h
0x180056425  mov     r9d, ebx
0x180056428  mov     rcx, [rcx+10h]
0x18005642c  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180056433  call    WPP_SF_d
0x180056438  mov     rcx, r13; hMem
0x18005643b  call    cs:__imp_LocalFree
0x180056441  jmp     short loc_18005648E
0x180056443  xor     esi, esi
0x180056445  jmp     short loc_180056481
0x180056447  mov     dword ptr [rax], 2
0x18005644d  mov     [rax+4], esi
0x180056450  test    ebx, ebx
0x180056452  jz      short loc_18005647C
0x180056454  mov     eax, 1
0x180056459  mov     [rdi+30h], r14d
0x18005645d  mov     [rdi+24h], eax
0x180056460  lea     rcx, [rdi+38h]; void *
0x180056464  mov     [rdi+28h], eax
0x180056467  mov     r8, rbx; Size
0x18005646a  lea     eax, [rbx+13h]
0x18005646d  mov     [rdi+34h], r13d
0x180056471  mov     rdx, r12; Src
0x180056474  mov     [rdi+2Ch], eax
0x180056477  call    memcpy_0
0x18005647c  mov     r13, rdi
0x18005647f  xor     ebx, ebx
0x180056481  mov     rax, [rbp+3Fh+arg_30]
0x180056485  mov     [rax], esi
0x180056487  mov     rax, [rbp+3Fh+arg_28]
0x18005648b  mov     [rax], r13
0x18005648e  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180056492  call    cs:__imp_LocalFree
0x180056498  test    r15, r15
0x18005649b  jz      short loc_1800564A9
0x18005649d  mov     rcx, [rbp+3Fh+Src]
0x1800564a1  mov     rax, r15
0x1800564a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800564a9  mov     rcx, [rbp+3Fh+var_50]; hMem
0x1800564ad  call    ?PeapEapInfoFreeList@@YAXPEAU_PEAP_EAP_INFO@@@Z; PeapEapInfoFreeList(_PEAP_EAP_INFO *)
0x1800564b2  mov     eax, ebx
0x1800564b4  add     rsp, 88h
0x1800564bb  pop     r15
0x1800564bd  pop     r14
0x1800564bf  pop     r13
0x1800564c1  pop     r12
0x1800564c3  pop     rdi
0x1800564c4  pop     rsi
0x1800564c5  pop     rbx
0x1800564c6  pop     rbp
0x1800564c7  retn
```
