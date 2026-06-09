# NatAddConnectionEntry(IUnknown *,_MIB_IPADDRTABLE const *)

- ea: `0x18007e1f0`
- end: `0x18007e696`
- name: `?NatAddConnectionEntry@@YAJPEAUIUnknown@@PEBU_MIB_IPADDRTABLE@@@Z`
- size: `1190`
- prototype: `__int64 __fastcall(struct IUnknown *, const struct _MIB_IPADDRTABLE *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004ff48`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x1800507a4`
- `0x180052bf4`
- `0x18007e1f0`
- `0x18007e84c`
- `0x18007f530`
- `0x180080298`
- `0x180080348`
- `0x180081fa0`
- `0x18008213c`
- `0x1800832e4`
- `0x18008336c`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007e24e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007e24e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e269`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e269`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e3d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e413`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e3d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e413`

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
    v20 = (__int64 *)qword_1800AFA10;
    if ( *(struct _NAT_CONNECTION_INFO ***)qword_1800AFA10 == &NatConnectionList )
    {
      *(_QWORD *)v6 = &NatConnectionList;
      *(_QWORD *)(v6 + 8) = v20;
      *v20 = v6;
      qword_1800AFA10 = v6;
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
  v23 = (__int64 *)qword_1800AFA10;
  if ( *(struct _NAT_CONNECTION_INFO ***)qword_1800AFA10 != &NatConnectionList )
    goto LABEL_55;
  *(_QWORD *)v6 = &NatConnectionList;
  *(_QWORD *)(v6 + 8) = v23;
  *v23 = v6;
  qword_1800AFA10 = v6;
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
0x18007e1f0  mov     [rsp-38h+arg_0], rbx
0x18007e1f5  push    rbp
0x18007e1f6  push    rsi
0x18007e1f7  push    rdi
0x18007e1f8  push    r12
0x18007e1fa  push    r13
0x18007e1fc  push    r14
0x18007e1fe  push    r15
0x18007e200  mov     rbp, rsp
0x18007e203  sub     rsp, 50h
0x18007e207  mov     r12, rdx
0x18007e20a  mov     rdi, rcx
0x18007e20d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e214  lea     rax, WPP_GLOBAL_Control
0x18007e21b  mov     r15d, 200h
0x18007e221  cmp     rcx, rax
0x18007e224  jz      short loc_18007E247
0x18007e226  test    [rcx+1Ch], r15d
0x18007e22a  jz      short loc_18007E247
0x18007e22c  cmp     byte ptr [rcx+19h], 6
0x18007e230  jb      short loc_18007E247
0x18007e232  mov     rcx, [rcx+10h]
0x18007e236  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x18007e23d  mov     edx, 1Ch
0x18007e242  call    WPP_SF_
0x18007e247  xor     r13d, r13d
0x18007e24a  mov     [rbp+arg_10], r13
0x18007e24e  call    cs:__imp_GetProcessHeap
0x18007e255  nop     dword ptr [rax+rax+00h]
0x18007e25a  mov     esi, 0C0h
0x18007e25f  lea     edx, [r13+8]; dwFlags
0x18007e263  mov     rcx, rax; hHeap
0x18007e266  mov     r8d, esi; dwBytes
0x18007e269  call    cs:__imp_HeapAlloc
0x18007e270  nop     dword ptr [rax+rax+00h]
0x18007e275  mov     rbx, rax
0x18007e278  test    rax, rax
0x18007e27b  jnz     loc_18007E30F
0x18007e281  mov     edi, 8007000Eh
0x18007e286  lea     rsi, WPP_GLOBAL_Control
0x18007e28d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e294  mov     rdx, [rbp+arg_10]
0x18007e298  test    rdx, rdx
0x18007e29b  jz      short loc_18007E2B3
0x18007e29d  mov     rax, [rdx]
0x18007e2a0  mov     rcx, rdx
0x18007e2a3  mov     rax, [rax+10h]
0x18007e2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e2ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e2b3  test    edi, edi
0x18007e2b5  jns     short loc_18007E2CB
0x18007e2b7  test    rbx, rbx
0x18007e2ba  jz      short loc_18007E2CB
0x18007e2bc  mov     rcx, rbx; struct _NAT_CONNECTION_INFO *
0x18007e2bf  call    ?NatFreeConnectionEntry@@YAXPEAU_NAT_CONNECTION_INFO@@@Z; NatFreeConnectionEntry(_NAT_CONNECTION_INFO *)
0x18007e2c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e2cb  cmp     rcx, rsi
0x18007e2ce  jz      short loc_18007E2F4
0x18007e2d0  test    [rcx+1Ch], r15d
0x18007e2d4  jz      short loc_18007E2F4
0x18007e2d6  cmp     byte ptr [rcx+19h], 6
0x18007e2da  jb      short loc_18007E2F4
0x18007e2dc  mov     rcx, [rcx+10h]
0x18007e2e0  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x18007e2e7  mov     edx, 20h ; ' '
0x18007e2ec  mov     r9d, edi
0x18007e2ef  call    WPP_SF_d
0x18007e2f4  mov     rbx, [rsp+50h+arg_0]
0x18007e2fc  mov     eax, edi
0x18007e2fe  add     rsp, 50h
0x18007e302  pop     r15
0x18007e304  pop     r14
0x18007e306  pop     r13
0x18007e308  pop     r12
0x18007e30a  pop     rdi
0x18007e30b  pop     rsi
0x18007e30c  pop     rbp
0x18007e30d  retn
0x18007e30f  mov     r8, rsi; Size
0x18007e312  xor     edx, edx; Val
0x18007e314  mov     rcx, rbx; void *
0x18007e317  call    memset_0
0x18007e31c  mov     [rbx+8], rbx
0x18007e320  lea     rax, [rbx+0A0h]
0x18007e327  mov     [rbx], rbx
0x18007e32a  lea     r8, [rbp+arg_10]
0x18007e32e  mov     [rax+8], rax
0x18007e332  lea     rdx, _GUID_85d18b71_3032_11d4_9348_00c04f8eeb71
0x18007e339  mov     [rax], rax
0x18007e33c  mov     rcx, rdi
0x18007e33f  mov     dword ptr [rbx+58h], 0FFFFFFFFh
0x18007e346  mov     [rbx+20h], r13
0x18007e34a  mov     [rbx+28h], r13
0x18007e34e  mov     rax, [rdi]
0x18007e351  mov     rax, [rax]
0x18007e354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e359  mov     edi, eax
0x18007e35b  test    eax, eax
0x18007e35d  js      loc_18007E286
0x18007e363  mov     rcx, [rbp+arg_10]
0x18007e367  mov     [rbx+60h], rcx
0x18007e36b  mov     rax, [rcx]
0x18007e36e  mov     rax, [rax+8]
0x18007e372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e377  mov     rcx, [rbp+arg_10]
0x18007e37b  lea     rdx, [rbp+pv]
0x18007e37f  mov     [rbp+pv], r13
0x18007e383  mov     rax, [rcx]
0x18007e386  mov     rax, [rax+38h]
0x18007e38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e38f  mov     edi, eax
0x18007e391  test    eax, eax
0x18007e393  js      loc_18007E286
0x18007e399  mov     rax, [rbp+pv]
0x18007e39d  mov     [rax+1], r13b
0x18007e3a1  cmp     cs:?NhPolicyAllowsSharing@@3HA, r13d; int NhPolicyAllowsSharing
0x18007e3a8  jnz     short loc_18007E3BA
0x18007e3aa  mov     rax, [rbp+pv]
0x18007e3ae  mov     [rax+2], r13b
0x18007e3b2  mov     rax, [rbp+pv]
0x18007e3b6  mov     [rax+3], r13b
0x18007e3ba  mov     rax, [rbp+pv]
0x18007e3be  movsd   xmm0, qword ptr [rax]
0x18007e3c2  movsd   qword ptr [rbx+70h], xmm0
0x18007e3c7  mov     eax, [rax+8]
0x18007e3ca  mov     [rbx+78h], eax
0x18007e3cd  mov     rcx, [rbp+pv]; pv
0x18007e3d1  call    cs:__imp_CoTaskMemFree
0x18007e3d8  nop     dword ptr [rax+rax+00h]
0x18007e3dd  mov     rcx, [rbp+arg_10]
0x18007e3e1  lea     rdx, [rbp+var_10]
0x18007e3e5  mov     [rbp+var_10], r13
0x18007e3e9  mov     rax, [rcx]
0x18007e3ec  mov     rax, [rax+20h]
0x18007e3f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e3f5  mov     edi, eax
0x18007e3f7  test    eax, eax
0x18007e3f9  js      loc_18007E286
0x18007e3ff  mov     rax, [rbp+var_10]
0x18007e403  lea     r14, [rbx+7Ch]
0x18007e407  movups  xmm0, xmmword ptr [rax]
0x18007e40a  movdqu  xmmword ptr [r14], xmm0
0x18007e40f  mov     rcx, [rbp+var_10]; pv
0x18007e413  call    cs:__imp_CoTaskMemFree
0x18007e41a  nop     dword ptr [rax+rax+00h]
0x18007e41f  cmp     [rbx+72h], r13b
0x18007e423  jz      short loc_18007E431
0x18007e425  cmp     cs:?NhPolicyAllowsSharing@@3HA, r13d; int NhPolicyAllowsSharing
0x18007e42c  mov     dil, 1
0x18007e42f  jnz     short loc_18007E434
0x18007e431  mov     dil, r13b
0x18007e434  mov     r9b, dil; bool
0x18007e437  mov     r8b, 1; bool
0x18007e43a  mov     rcx, r14; InterfaceGuid
0x18007e43d  call    ?TrySetEnableRoutingToNsi@NsiWrapperUtil@@SAJAEBU_GUID@@AEBU_NPI_MODULEID@@_N2@Z; NsiWrapperUtil::TrySetEnableRoutingToNsi(_GUID const &,_NPI_MODULEID const &,bool,bool)
0x18007e442  mov     edx, eax
0x18007e444  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e44b  lea     rsi, WPP_GLOBAL_Control
0x18007e452  cmp     rcx, rsi
0x18007e455  jz      short loc_18007E483
0x18007e457  test    [rcx+1Ch], r15d
0x18007e45b  jz      short loc_18007E483
0x18007e45d  cmp     byte ptr [rcx+19h], 5
0x18007e461  jb      short loc_18007E483
0x18007e463  cmp     [rbx+72h], r13b
0x18007e467  mov     r9, r14
0x18007e46a  mov     rcx, [rcx+10h]
0x18007e46e  mov     [rsp+50h+var_18], edx
0x18007e472  setnz   al
0x18007e475  mov     [rsp+50h+var_20], dil
0x18007e47a  mov     byte ptr [rsp+50h+var_30], al
0x18007e47e  call    WPP_SF__guid_cccD
0x18007e483  mov     rcx, [rbp+arg_10]
0x18007e487  lea     rdx, [rbx+68h]
0x18007e48b  mov     rax, [rcx]
0x18007e48e  mov     rax, [rax+28h]
0x18007e492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e497  mov     edi, eax
0x18007e499  mov     al, [rbx+70h]
0x18007e49c  test    edi, edi
0x18007e49e  jns     short loc_18007E4CC
0x18007e4a0  test    al, al
0x18007e4a2  jnz     loc_18007E286
0x18007e4a8  cmp     edi, 80070490h
0x18007e4ae  jnz     loc_18007E286
0x18007e4b4  mov     rcx, [rbp+arg_10]
0x18007e4b8  mov     rax, [rcx]
0x18007e4bb  mov     rax, [rax+90h]
0x18007e4c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e4c7  jmp     loc_18007E28D
0x18007e4cc  test    al, al
0x18007e4ce  jnz     short loc_18007E520
0x18007e4d0  call    ?NatIsRasConfigAllowed@@YAJXZ; NatIsRasConfigAllowed(void)
0x18007e4d5  mov     edi, eax
0x18007e4d7  test    eax, eax
0x18007e4d9  js      loc_18007E286
0x18007e4df  mov     rcx, [rbp+arg_10]
0x18007e4e3  lea     rsi, [rbx+90h]
0x18007e4ea  mov     rdx, rsi
0x18007e4ed  mov     rax, [rcx]
0x18007e4f0  mov     rax, [rax+30h]
0x18007e4f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e4f9  mov     edi, eax
0x18007e4fb  test    eax, eax
0x18007e4fd  js      loc_18007E286
0x18007e503  mov     rdx, [rbx+68h]; LPCWSTR
0x18007e507  lea     r8, [rbx+9Ch]; unsigned __int8 *
0x18007e50e  mov     rcx, [rsi]; LPCWSTR
0x18007e511  call    ?NatIsRasEntryDialUp@@YAJPEBG0PEAE@Z; NatIsRasEntryDialUp(ushort const *,ushort const *,uchar *)
0x18007e516  mov     edi, eax
0x18007e518  test    eax, eax
0x18007e51a  js      loc_18007E286
0x18007e520  mov     rdx, r12; struct _MIB_IPADDRTABLE *
0x18007e523  mov     rcx, rbx; struct _NAT_CONNECTION_INFO *
0x18007e526  call    ?NatBuildPortMappingList@@YAJPEAU_NAT_CONNECTION_INFO@@PEBU_MIB_IPADDRTABLE@@@Z; NatBuildPortMappingList(_NAT_CONNECTION_INFO *,_MIB_IPADDRTABLE const *)
0x18007e52b  mov     edi, eax
0x18007e52d  test    eax, eax
0x18007e52f  js      loc_18007E286
0x18007e535  cmp     [rbx+72h], r13b
0x18007e539  jz      short loc_18007E542
0x18007e53b  mov     cs:?NatSharedConnectionPresent@@3EA, 1; uchar NatSharedConnectionPresent
0x18007e542  cmp     [rbx+73h], r13b
0x18007e546  jz      short loc_18007E55A
0x18007e548  cmp     cs:?NatPrivateConnectionPresent@@3EA, r13b; uchar NatPrivateConnectionPresent
0x18007e54f  jnz     short loc_18007E55A
0x18007e551  mov     cs:?NatPrivateConnectionPresent@@3EA, 1; uchar NatPrivateConnectionPresent
0x18007e558  jmp     short loc_18007E55E
0x18007e55a  mov     [rbx+73h], r13b
0x18007e55e  mov     rcx, r14
0x18007e561  call    NatFindConnectionEntry
0x18007e566  mov     rsi, rax
0x18007e569  test    rax, rax
0x18007e56c  jz      loc_18007E62F
0x18007e572  mov     rdx, rax; struct _NAT_CONNECTION_INFO *
0x18007e575  mov     rcx, rbx; struct _NAT_CONNECTION_INFO *
0x18007e578  call    ?NatAreConnectionsEqual@@YAEPEBU_NAT_CONNECTION_INFO@@0@Z; NatAreConnectionsEqual(_NAT_CONNECTION_INFO const *,_NAT_CONNECTION_INFO const *)
0x18007e57d  test    al, al
0x18007e57f  jnz     short loc_18007E5FF
0x18007e581  mov     dword ptr [rsi+14h], 1
0x18007e588  lea     rax, NatConnectionList
0x18007e58f  mov     dword ptr [rbx+10h], 1
0x18007e596  mov     rcx, cs:qword_1800AFA10
0x18007e59d  cmp     [rcx], rax
0x18007e5a0  jnz     loc_18007E649
0x18007e5a6  mov     [rbx], rax
0x18007e5a9  mov     [rbx+8], rcx
0x18007e5ad  mov     [rcx], rbx
0x18007e5b0  mov     cs:qword_1800AFA10, rbx
0x18007e5b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e5be  lea     rsi, WPP_GLOBAL_Control
0x18007e5c5  cmp     rcx, rsi
0x18007e5c8  jz      loc_18007E294
0x18007e5ce  test    [rcx+1Ch], r15d
0x18007e5d2  jz      loc_18007E294
0x18007e5d8  cmp     byte ptr [rcx+19h], 5
0x18007e5dc  jb      loc_18007E294
0x18007e5e2  mov     edx, 1Eh
0x18007e5e7  mov     eax, [rbx+58h]
0x18007e5ea  mov     r9, r14
0x18007e5ed  mov     rcx, [rcx+10h]
0x18007e5f1  mov     [rsp+50h+var_30], eax
0x18007e5f5  call    WPP_SF__guid_d
0x18007e5fa  jmp     loc_18007E28D
0x18007e5ff  mov     rcx, [rsi+60h]
0x18007e603  mov     dword ptr [rsi+10h], 1
0x18007e60a  mov     rax, [rcx]
0x18007e60d  mov     rax, [rax+10h]
0x18007e611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e616  mov     rax, [rbx+60h]
0x18007e61a  mov     rcx, rbx; struct _NAT_CONNECTION_INFO *
0x18007e61d  mov     [rsi+60h], rax
0x18007e621  mov     [rbx+60h], r13
0x18007e625  call    ?NatFreeConnectionEntry@@YAXPEAU_NAT_CONNECTION_INFO@@@Z; NatFreeConnectionEntry(_NAT_CONNECTION_INFO *)
0x18007e62a  jmp     loc_18007E286
0x18007e62f  mov     dword ptr [rbx+10h], 1
0x18007e636  lea     rax, NatConnectionList
0x18007e63d  mov     rcx, cs:qword_1800AFA10
0x18007e644  cmp     [rcx], rax
0x18007e647  jz      short loc_18007E650
0x18007e649  mov     ecx, 3
0x18007e64e  int     29h; Win8: RtlFailFast(ecx)
0x18007e650  mov     [rbx], rax
0x18007e653  mov     [rbx+8], rcx
0x18007e657  mov     [rcx], rbx
0x18007e65a  mov     cs:qword_1800AFA10, rbx
0x18007e661  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e668  lea     rsi, WPP_GLOBAL_Control
0x18007e66f  cmp     rcx, rsi
0x18007e672  jz      loc_18007E294
0x18007e678  test    [rcx+1Ch], r15d
0x18007e67c  jz      loc_18007E294
0x18007e682  cmp     byte ptr [rcx+19h], 5
0x18007e686  jb      loc_18007E294
0x18007e68c  mov     edx, 1Fh
0x18007e691  jmp     loc_18007E5E7
```
