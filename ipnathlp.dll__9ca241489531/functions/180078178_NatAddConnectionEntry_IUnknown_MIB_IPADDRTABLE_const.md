# NatAddConnectionEntry(IUnknown *,_MIB_IPADDRTABLE const *)

- ea: `0x180078178`
- end: `0x180078605`
- name: `?NatAddConnectionEntry@@YAJPEAUIUnknown@@PEBU_MIB_IPADDRTABLE@@@Z`
- size: `1165`
- prototype: `__int64 __fastcall(struct IUnknown *, const struct _MIB_IPADDRTABLE *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004c214`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18004ca00`
- `0x18004ed64`
- `0x180078178`
- `0x1800787bc`
- `0x180079490`
- `0x18007a1b8`
- `0x18007a264`
- `0x18007bce4`
- `0x18007be70`
- `0x18007cf28`
- `0x18007cfac`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800781d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800781d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800781eb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800781eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007834c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078388`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007834c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078388`

## pseudocode

```c
__int64 __fastcall NatAddConnectionEntry(struct IUnknown *a1, const struct _MIB_IPADDRTABLE *a2)
{
  HANDLE ProcessHeap; // rax
  void *v5; // rax
  __int64 v6; // rbx
  int IsRasConfigAllowed; // edi
  PVOID *v8; // rcx
  __int64 v10; // rcx
  _DWORD *v11; // rax
  const struct _NPI_MODULEID *v12; // rdx
  bool v13; // di
  unsigned int v14; // eax
  __int64 v15; // r8
  char v16; // al
  const struct _NAT_CONNECTION_INFO *ConnectionEntry; // rax
  __int64 v18; // r8
  const struct _NAT_CONNECTION_INFO *v19; // rsi
  __int64 *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 *v23; // rcx
  LPVOID v24[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v25; // [rsp+A0h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids);
  }
  v25 = 0;
  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 8u, 0xC0u);
  v6 = (__int64)v5;
  if ( !v5 )
  {
    IsRasConfigAllowed = -2147024882;
    goto LABEL_7;
  }
  memset_0(v5, 0, 0xC0u);
  *(_QWORD *)(v6 + 8) = v6;
  *(_QWORD *)v6 = v6;
  *(_QWORD *)(v6 + 168) = v6 + 160;
  *(_QWORD *)(v6 + 160) = v6 + 160;
  *(_DWORD *)(v6 + 88) = -1;
  *(_QWORD *)(v6 + 32) = 0;
  *(_QWORD *)(v6 + 40) = 0;
  IsRasConfigAllowed = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
                         a1,
                         &GUID_85d18b71_3032_11d4_9348_00c04f8eeb71,
                         &v25);
  if ( IsRasConfigAllowed < 0 )
    goto LABEL_7;
  v10 = v25;
  *(_QWORD *)(v6 + 96) = v25;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  pv = 0;
  IsRasConfigAllowed = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v25 + 56LL))(v25, &pv);
  if ( IsRasConfigAllowed < 0 )
    goto LABEL_7;
  *((_BYTE *)pv + 1) = 0;
  if ( !NhPolicyAllowsSharing )
  {
    *((_BYTE *)pv + 2) = 0;
    *((_BYTE *)pv + 3) = 0;
  }
  v11 = pv;
  *(_QWORD *)(v6 + 112) = *(_QWORD *)pv;
  *(_DWORD *)(v6 + 120) = v11[2];
  CoTaskMemFree(pv);
  v24[0] = 0;
  IsRasConfigAllowed = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v25 + 32LL))(v25, v24);
  if ( IsRasConfigAllowed < 0 )
    goto LABEL_7;
  *(_OWORD *)(v6 + 124) = *(_OWORD *)v24[0];
  CoTaskMemFree(v24[0]);
  if ( !*(_BYTE *)(v6 + 114) || (v13 = 1, !NhPolicyAllowsSharing) )
    v13 = 0;
  v14 = NsiWrapperUtil::TrySetEnableRoutingToNsi((GUID *)(v6 + 124), v12, 1, v13);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF__guid_cccD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, v6 + 124, *(_BYTE *)(v6 + 114) != 0);
  }
  IsRasConfigAllowed = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 40LL))(v25, v6 + 104);
  v16 = *(_BYTE *)(v6 + 112);
  if ( IsRasConfigAllowed < 0 )
  {
    if ( !v16 && IsRasConfigAllowed == -2147023728 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 144LL))(v25);
    goto LABEL_7;
  }
  if ( !v16
    && ((IsRasConfigAllowed = NatIsRasConfigAllowed(), IsRasConfigAllowed < 0)
     || (IsRasConfigAllowed = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 48LL))(v25, v6 + 144),
         IsRasConfigAllowed < 0)
     || (IsRasConfigAllowed = NatIsRasEntryDialUp(
                                *(LPCWSTR *)(v6 + 144),
                                *(LPCWSTR *)(v6 + 104),
                                (unsigned __int8 *)(v6 + 156)),
         IsRasConfigAllowed < 0))
    || (IsRasConfigAllowed = NatBuildPortMappingList((struct _NAT_CONNECTION_INFO *)v6, a2), IsRasConfigAllowed < 0) )
  {
LABEL_7:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  if ( *(_BYTE *)(v6 + 114) )
    NatSharedConnectionPresent = 1;
  if ( !*(_BYTE *)(v6 + 115) || NatPrivateConnectionPresent )
    *(_BYTE *)(v6 + 115) = 0;
  else
    NatPrivateConnectionPresent = 1;
  ConnectionEntry = (const struct _NAT_CONNECTION_INFO *)NatFindConnectionEntry(v6 + 124);
  v19 = ConnectionEntry;
  if ( ConnectionEntry )
  {
    if ( NatAreConnectionsEqual((const struct _NAT_CONNECTION_INFO *)v6, ConnectionEntry) )
    {
      v22 = *((_QWORD *)v19 + 12);
      *((_DWORD *)v19 + 4) = 1;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      *((_QWORD *)v19 + 12) = *(_QWORD *)(v6 + 96);
      *(_QWORD *)(v6 + 96) = 0;
      NatFreeConnectionEntry((struct _NAT_CONNECTION_INFO *)v6);
      goto LABEL_7;
    }
    *((_DWORD *)v19 + 5) = 1;
    *(_DWORD *)(v6 + 16) = 1;
    v20 = (__int64 *)qword_1800A8950;
    if ( *(struct _NAT_CONNECTION_INFO ***)qword_1800A8950 == &NatConnectionList )
    {
      *(_QWORD *)v6 = &NatConnectionList;
      *(_QWORD *)(v6 + 8) = v20;
      *v20 = v6;
      qword_1800A8950 = v6;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v21 = 30;
LABEL_52:
        WPP_SF__guid_d(v8[2], v21, v18, v6 + 124, *(_DWORD *)(v6 + 88));
        goto LABEL_7;
      }
      goto LABEL_8;
    }
LABEL_55:
    __fastfail(3u);
  }
  *(_DWORD *)(v6 + 16) = 1;
  v23 = (__int64 *)qword_1800A8950;
  if ( *(struct _NAT_CONNECTION_INFO ***)qword_1800A8950 != &NatConnectionList )
    goto LABEL_55;
  *(_QWORD *)v6 = &NatConnectionList;
  *(_QWORD *)(v6 + 8) = v23;
  *v23 = v6;
  qword_1800A8950 = v6;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v21 = 31;
    goto LABEL_52;
  }
LABEL_8:
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( IsRasConfigAllowed < 0 && v6 )
  {
    NatFreeConnectionEntry((struct _NAT_CONNECTION_INFO *)v6);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x200) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 32, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, (unsigned int)IsRasConfigAllowed);
  return (unsigned int)IsRasConfigAllowed;
}

```

## disassembly

```asm
0x180078178  mov     [rsp-38h+arg_0], rbx
0x18007817d  push    rbp
0x18007817e  push    rsi
0x18007817f  push    rdi
0x180078180  push    r12
0x180078182  push    r13
0x180078184  push    r14
0x180078186  push    r15
0x180078188  mov     rbp, rsp
0x18007818b  sub     rsp, 50h
0x18007818f  mov     r12, rdx
0x180078192  mov     rdi, rcx
0x180078195  mov     rcx, cs:WPP_GLOBAL_Control
0x18007819c  lea     rax, WPP_GLOBAL_Control
0x1800781a3  mov     r15d, 200h
0x1800781a9  cmp     rcx, rax
0x1800781ac  jz      short loc_1800781CF
0x1800781ae  test    [rcx+1Ch], r15d
0x1800781b2  jz      short loc_1800781CF
0x1800781b4  cmp     byte ptr [rcx+19h], 6
0x1800781b8  jb      short loc_1800781CF
0x1800781ba  mov     rcx, [rcx+10h]
0x1800781be  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x1800781c5  mov     edx, 1Ch
0x1800781ca  call    WPP_SF_
0x1800781cf  xor     r13d, r13d
0x1800781d2  mov     [rbp+arg_10], r13
0x1800781d6  call    cs:__imp_GetProcessHeap
0x1800781dc  mov     esi, 0C0h
0x1800781e1  lea     edx, [r13+8]; dwFlags
0x1800781e5  mov     rcx, rax; hHeap
0x1800781e8  mov     r8d, esi; dwBytes
0x1800781eb  call    cs:__imp_HeapAlloc
0x1800781f1  mov     rbx, rax
0x1800781f4  test    rax, rax
0x1800781f7  jnz     loc_18007828A
0x1800781fd  mov     edi, 8007000Eh
0x180078202  lea     rsi, WPP_GLOBAL_Control
0x180078209  mov     rcx, cs:WPP_GLOBAL_Control
0x180078210  mov     rdx, [rbp+arg_10]
0x180078214  test    rdx, rdx
0x180078217  jz      short loc_18007822F
0x180078219  mov     rax, [rdx]
0x18007821c  mov     rcx, rdx
0x18007821f  mov     rax, [rax+10h]
0x180078223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078228  mov     rcx, cs:WPP_GLOBAL_Control
0x18007822f  test    edi, edi
0x180078231  jns     short loc_180078247
0x180078233  test    rbx, rbx
0x180078236  jz      short loc_180078247
0x180078238  mov     rcx, rbx; struct _NAT_CONNECTION_INFO *
0x18007823b  call    ?NatFreeConnectionEntry@@YAXPEAU_NAT_CONNECTION_INFO@@@Z; NatFreeConnectionEntry(_NAT_CONNECTION_INFO *)
0x180078240  mov     rcx, cs:WPP_GLOBAL_Control
0x180078247  cmp     rcx, rsi
0x18007824a  jz      short loc_180078270
0x18007824c  test    [rcx+1Ch], r15d
0x180078250  jz      short loc_180078270
0x180078252  cmp     byte ptr [rcx+19h], 6
0x180078256  jb      short loc_180078270
0x180078258  mov     rcx, [rcx+10h]
0x18007825c  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x180078263  mov     edx, 20h ; ' '
0x180078268  mov     r9d, edi
0x18007826b  call    WPP_SF_d
0x180078270  mov     rbx, [rsp+50h+arg_0]
0x180078278  mov     eax, edi
0x18007827a  add     rsp, 50h
0x18007827e  pop     r15
0x180078280  pop     r14
0x180078282  pop     r13
0x180078284  pop     r12
0x180078286  pop     rdi
0x180078287  pop     rsi
0x180078288  pop     rbp
0x180078289  retn
0x18007828a  mov     r8, rsi; Size
0x18007828d  xor     edx, edx; Val
0x18007828f  mov     rcx, rbx; void *
0x180078292  call    memset_0
0x180078297  mov     [rbx+8], rbx
0x18007829b  lea     rax, [rbx+0A0h]
0x1800782a2  mov     [rbx], rbx
0x1800782a5  lea     r8, [rbp+arg_10]
0x1800782a9  mov     [rax+8], rax
0x1800782ad  lea     rdx, _GUID_85d18b71_3032_11d4_9348_00c04f8eeb71
0x1800782b4  mov     [rax], rax
0x1800782b7  mov     rcx, rdi
0x1800782ba  mov     dword ptr [rbx+58h], 0FFFFFFFFh
0x1800782c1  mov     [rbx+20h], r13
0x1800782c5  mov     [rbx+28h], r13
0x1800782c9  mov     rax, [rdi]
0x1800782cc  mov     rax, [rax]
0x1800782cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800782d4  mov     edi, eax
0x1800782d6  test    eax, eax
0x1800782d8  js      loc_180078202
0x1800782de  mov     rcx, [rbp+arg_10]
0x1800782e2  mov     [rbx+60h], rcx
0x1800782e6  mov     rax, [rcx]
0x1800782e9  mov     rax, [rax+8]
0x1800782ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800782f2  mov     rcx, [rbp+arg_10]
0x1800782f6  lea     rdx, [rbp+pv]
0x1800782fa  mov     [rbp+pv], r13
0x1800782fe  mov     rax, [rcx]
0x180078301  mov     rax, [rax+38h]
0x180078305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007830a  mov     edi, eax
0x18007830c  test    eax, eax
0x18007830e  js      loc_180078202
0x180078314  mov     rax, [rbp+pv]
0x180078318  mov     [rax+1], r13b
0x18007831c  cmp     cs:?NhPolicyAllowsSharing@@3HA, r13d; int NhPolicyAllowsSharing
0x180078323  jnz     short loc_180078335
0x180078325  mov     rax, [rbp+pv]
0x180078329  mov     [rax+2], r13b
0x18007832d  mov     rax, [rbp+pv]
0x180078331  mov     [rax+3], r13b
0x180078335  mov     rax, [rbp+pv]
0x180078339  movsd   xmm0, qword ptr [rax]
0x18007833d  movsd   qword ptr [rbx+70h], xmm0
0x180078342  mov     eax, [rax+8]
0x180078345  mov     [rbx+78h], eax
0x180078348  mov     rcx, [rbp+pv]; pv
0x18007834c  call    cs:__imp_CoTaskMemFree
0x180078352  mov     rcx, [rbp+arg_10]
0x180078356  lea     rdx, [rbp+var_10]
0x18007835a  mov     [rbp+var_10], r13
0x18007835e  mov     rax, [rcx]
0x180078361  mov     rax, [rax+20h]
0x180078365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007836a  mov     edi, eax
0x18007836c  test    eax, eax
0x18007836e  js      loc_180078202
0x180078374  mov     rax, [rbp+var_10]
0x180078378  lea     r14, [rbx+7Ch]
0x18007837c  movups  xmm0, xmmword ptr [rax]
0x18007837f  movdqu  xmmword ptr [r14], xmm0
0x180078384  mov     rcx, [rbp+var_10]; pv
0x180078388  call    cs:__imp_CoTaskMemFree
0x18007838e  cmp     [rbx+72h], r13b
0x180078392  jz      short loc_1800783A0
0x180078394  cmp     cs:?NhPolicyAllowsSharing@@3HA, r13d; int NhPolicyAllowsSharing
0x18007839b  mov     dil, 1
0x18007839e  jnz     short loc_1800783A3
0x1800783a0  mov     dil, r13b
0x1800783a3  mov     r9b, dil; bool
0x1800783a6  mov     r8b, 1; bool
0x1800783a9  mov     rcx, r14; InterfaceGuid
0x1800783ac  call    ?TrySetEnableRoutingToNsi@NsiWrapperUtil@@SAJAEBU_GUID@@AEBU_NPI_MODULEID@@_N2@Z; NsiWrapperUtil::TrySetEnableRoutingToNsi(_GUID const &,_NPI_MODULEID const &,bool,bool)
0x1800783b1  mov     edx, eax
0x1800783b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800783ba  lea     rsi, WPP_GLOBAL_Control
0x1800783c1  cmp     rcx, rsi
0x1800783c4  jz      short loc_1800783F2
0x1800783c6  test    [rcx+1Ch], r15d
0x1800783ca  jz      short loc_1800783F2
0x1800783cc  cmp     byte ptr [rcx+19h], 5
0x1800783d0  jb      short loc_1800783F2
0x1800783d2  cmp     [rbx+72h], r13b
0x1800783d6  mov     r9, r14
0x1800783d9  mov     rcx, [rcx+10h]
0x1800783dd  mov     [rsp+50h+var_18], edx
0x1800783e1  setnz   al
0x1800783e4  mov     [rsp+50h+var_20], dil
0x1800783e9  mov     byte ptr [rsp+50h+var_30], al
0x1800783ed  call    WPP_SF__guid_cccD
0x1800783f2  mov     rcx, [rbp+arg_10]
0x1800783f6  lea     rdx, [rbx+68h]
0x1800783fa  mov     rax, [rcx]
0x1800783fd  mov     rax, [rax+28h]
0x180078401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078406  mov     edi, eax
0x180078408  mov     al, [rbx+70h]
0x18007840b  test    edi, edi
0x18007840d  jns     short loc_18007843B
0x18007840f  test    al, al
0x180078411  jnz     loc_180078202
0x180078417  cmp     edi, 80070490h
0x18007841d  jnz     loc_180078202
0x180078423  mov     rcx, [rbp+arg_10]
0x180078427  mov     rax, [rcx]
0x18007842a  mov     rax, [rax+90h]
0x180078431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078436  jmp     loc_180078209
0x18007843b  test    al, al
0x18007843d  jnz     short loc_18007848F
0x18007843f  call    ?NatIsRasConfigAllowed@@YAJXZ; NatIsRasConfigAllowed(void)
0x180078444  mov     edi, eax
0x180078446  test    eax, eax
0x180078448  js      loc_180078202
0x18007844e  mov     rcx, [rbp+arg_10]
0x180078452  lea     rsi, [rbx+90h]
0x180078459  mov     rdx, rsi
0x18007845c  mov     rax, [rcx]
0x18007845f  mov     rax, [rax+30h]
0x180078463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078468  mov     edi, eax
0x18007846a  test    eax, eax
0x18007846c  js      loc_180078202
0x180078472  mov     rdx, [rbx+68h]; LPCWSTR
0x180078476  lea     r8, [rbx+9Ch]; unsigned __int8 *
0x18007847d  mov     rcx, [rsi]; LPCWSTR
0x180078480  call    ?NatIsRasEntryDialUp@@YAJPEBG0PEAE@Z; NatIsRasEntryDialUp(ushort const *,ushort const *,uchar *)
0x180078485  mov     edi, eax
0x180078487  test    eax, eax
0x180078489  js      loc_180078202
0x18007848f  mov     rdx, r12; struct _MIB_IPADDRTABLE *
0x180078492  mov     rcx, rbx; struct _NAT_CONNECTION_INFO *
0x180078495  call    ?NatBuildPortMappingList@@YAJPEAU_NAT_CONNECTION_INFO@@PEBU_MIB_IPADDRTABLE@@@Z; NatBuildPortMappingList(_NAT_CONNECTION_INFO *,_MIB_IPADDRTABLE const *)
0x18007849a  mov     edi, eax
0x18007849c  test    eax, eax
0x18007849e  js      loc_180078202
0x1800784a4  cmp     [rbx+72h], r13b
0x1800784a8  jz      short loc_1800784B1
0x1800784aa  mov     cs:?NatSharedConnectionPresent@@3EA, 1; uchar NatSharedConnectionPresent
0x1800784b1  cmp     [rbx+73h], r13b
0x1800784b5  jz      short loc_1800784C9
0x1800784b7  cmp     cs:?NatPrivateConnectionPresent@@3EA, r13b; uchar NatPrivateConnectionPresent
0x1800784be  jnz     short loc_1800784C9
0x1800784c0  mov     cs:?NatPrivateConnectionPresent@@3EA, 1; uchar NatPrivateConnectionPresent
0x1800784c7  jmp     short loc_1800784CD
0x1800784c9  mov     [rbx+73h], r13b
0x1800784cd  mov     rcx, r14
0x1800784d0  call    NatFindConnectionEntry
0x1800784d5  mov     rsi, rax
0x1800784d8  test    rax, rax
0x1800784db  jz      loc_18007859E
0x1800784e1  mov     rdx, rax; struct _NAT_CONNECTION_INFO *
0x1800784e4  mov     rcx, rbx; struct _NAT_CONNECTION_INFO *
0x1800784e7  call    ?NatAreConnectionsEqual@@YAEPEBU_NAT_CONNECTION_INFO@@0@Z; NatAreConnectionsEqual(_NAT_CONNECTION_INFO const *,_NAT_CONNECTION_INFO const *)
0x1800784ec  test    al, al
0x1800784ee  jnz     short loc_18007856E
0x1800784f0  mov     dword ptr [rsi+14h], 1
0x1800784f7  lea     rax, NatConnectionList
0x1800784fe  mov     dword ptr [rbx+10h], 1
0x180078505  mov     rcx, cs:qword_1800A8950
0x18007850c  cmp     [rcx], rax
0x18007850f  jnz     loc_1800785B8
0x180078515  mov     [rbx], rax
0x180078518  mov     [rbx+8], rcx
0x18007851c  mov     [rcx], rbx
0x18007851f  mov     cs:qword_1800A8950, rbx
0x180078526  mov     rcx, cs:WPP_GLOBAL_Control
0x18007852d  lea     rsi, WPP_GLOBAL_Control
0x180078534  cmp     rcx, rsi
0x180078537  jz      loc_180078210
0x18007853d  test    [rcx+1Ch], r15d
0x180078541  jz      loc_180078210
0x180078547  cmp     byte ptr [rcx+19h], 5
0x18007854b  jb      loc_180078210
0x180078551  mov     edx, 1Eh
0x180078556  mov     eax, [rbx+58h]
0x180078559  mov     r9, r14
0x18007855c  mov     rcx, [rcx+10h]
0x180078560  mov     [rsp+50h+var_30], eax
0x180078564  call    WPP_SF__guid_d
0x180078569  jmp     loc_180078209
0x18007856e  mov     rcx, [rsi+60h]
0x180078572  mov     dword ptr [rsi+10h], 1
0x180078579  mov     rax, [rcx]
0x18007857c  mov     rax, [rax+10h]
0x180078580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078585  mov     rax, [rbx+60h]
0x180078589  mov     rcx, rbx; struct _NAT_CONNECTION_INFO *
0x18007858c  mov     [rsi+60h], rax
0x180078590  mov     [rbx+60h], r13
0x180078594  call    ?NatFreeConnectionEntry@@YAXPEAU_NAT_CONNECTION_INFO@@@Z; NatFreeConnectionEntry(_NAT_CONNECTION_INFO *)
0x180078599  jmp     loc_180078202
0x18007859e  mov     dword ptr [rbx+10h], 1
0x1800785a5  lea     rax, NatConnectionList
0x1800785ac  mov     rcx, cs:qword_1800A8950
0x1800785b3  cmp     [rcx], rax
0x1800785b6  jz      short loc_1800785BF
0x1800785b8  mov     ecx, 3
0x1800785bd  int     29h; Win8: RtlFailFast(ecx)
0x1800785bf  mov     [rbx], rax
0x1800785c2  mov     [rbx+8], rcx
0x1800785c6  mov     [rcx], rbx
0x1800785c9  mov     cs:qword_1800A8950, rbx
0x1800785d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800785d7  lea     rsi, WPP_GLOBAL_Control
0x1800785de  cmp     rcx, rsi
0x1800785e1  jz      loc_180078210
0x1800785e7  test    [rcx+1Ch], r15d
0x1800785eb  jz      loc_180078210
0x1800785f1  cmp     byte ptr [rcx+19h], 5
0x1800785f5  jb      loc_180078210
0x1800785fb  mov     edx, 1Fh
0x180078600  jmp     loc_180078556
```
