# OpenClusterGroupImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)

- ea: `0x18004b424`
- end: `0x18004b70f`
- name: `?OpenClusterGroupImpl@@YAPEAU_HGROUP@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z`
- size: `747`
- prototype: `struct _HGROUP *__fastcall(struct _HCLUSTER *, const wchar_t *, unsigned int, unsigned int *, int)`
- caller_count: `10`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180023724`
- `0x180037cb0`
- `0x1800380b8`
- `0x18003a054`
- `0x180041f00`
- `0x18004b424`
- `0x18004c780`
- `0x18004c7b0`
- `0x180083050`
- `0x180087540`

## callees

- `0x18001236c`
- `0x180014638`
- `0x18001e0f8`
- `0x180024908`
- `0x180025478`
- `0x180047ab4`
- `0x18004ae8c`
- `0x18004b06c`
- `0x18004b238`
- `0x18004b424`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b686`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b686`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b657`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b657`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b6f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b6f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b51d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b543`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b54c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b6e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b6ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b51d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b543`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b54c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b6e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b6ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b4c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b50b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b4c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b50b`

## string_xrefs

- `0x18004b6cd`: `OpenClusterGroupImpl`
- `0x18004b5e7`: `ApiOpenGroup`
- `0x18004b59d`: `ApiOpenGroupEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _HGROUP *__fastcall OpenClusterGroupImpl(
        struct _HCLUSTER *a1,
        const wchar_t *a2,
        unsigned int a3,
        unsigned int *a4,
        int a5)
{
  DWORD v9; // ecx
  struct _HCLUSTER **v10; // rbx
  struct _HCLUSTER **v11; // rsi
  struct _HGROUP *v12; // rdi
  _DWORD *v14; // rbx
  unsigned __int64 v15; // r12
  wchar_t *v16; // rax
  int v17; // esi
  void *v18; // rcx
  DWORD v19; // eax
  unsigned int v20; // ecx
  struct _RTL_CRITICAL_SECTION *v21; // rsi
  char *v22; // rdi
  __int64 v23; // rcx
  __int64 v24; // rcx
  DWORD v25; // edi
  DWORD dwErrCode; // [rsp+30h] [rbp-48h] BYREF
  int v27; // [rsp+34h] [rbp-44h] BYREF
  unsigned int v28; // [rsp+38h] [rbp-40h] BYREF
  const char *v29; // [rsp+40h] [rbp-38h] BYREF
  struct _HCLUSTER **v30; // [rsp+48h] [rbp-30h]
  const wchar_t *v31; // [rsp+50h] [rbp-28h]
  DWORD *p_dwErrCode; // [rsp+58h] [rbp-20h]
  int *v33; // [rsp+60h] [rbp-18h]
  DWORD *v34; // [rsp+68h] [rbp-10h]

  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           a1,
                           a1) )
  {
    v9 = 6;
LABEL_40:
    SetLastError(v9);
    return 0;
  }
  dwErrCode = 0;
  v28 = 0;
  v27 = 0;
  if ( !*((_DWORD *)a1 + 87) )
  {
    v14 = LocalAlloc(0, 0x48u);
    if ( !v14 )
    {
LABEL_12:
      v9 = 8;
      goto LABEL_40;
    }
    dwErrCode = MylstrlenW(a2, 0x7FFFFFFFu, &v28);
    if ( dwErrCode )
    {
LABEL_39:
      LocalFree(v14);
      v9 = dwErrCode;
      goto LABEL_40;
    }
    v15 = v28 + 1;
    v16 = (wchar_t *)LocalAlloc(0, 2 * v15);
    *((_QWORD *)v14 + 6) = v16;
    if ( !v16 )
    {
      LocalFree(v14);
      goto LABEL_12;
    }
    *v14 = 1128747600;
    v17 = StringCchCopyW(v16, v15, a2);
    v18 = (void *)*((_QWORD *)v14 + 6);
    if ( v17 < 0 )
    {
      LocalFree(v18);
      LocalFree(v14);
      if ( (v17 & 0x1FFF0000) != 0x70000 || (v9 = (unsigned __int16)v17, !(_WORD)v17) )
        v9 = v17;
      goto LABEL_40;
    }
    StringCchCopyW((wchar_t *)v18, v15, a2);
    *((_QWORD *)v14 + 5) = a1;
    *((_QWORD *)v14 + 4) = v14 + 6;
    *((_QWORD *)v14 + 3) = v14 + 6;
    if ( *((_WORD *)a1 + 162) <= 5u )
    {
      if ( a5 )
      {
        v29 = "ApiOpenGroup";
        v30 = (struct _HCLUSTER **)((char *)a1 + 40);
        v31 = a2;
        p_dwErrCode = &dwErrCode;
        *((_QWORD *)v14 + 7) = ReconnectOnNull<OpenGroupFunctor>(&v29, &dwErrCode, a1);
        v20 = 0x10000000;
        v27 = 0x10000000;
        v19 = dwErrCode;
        goto LABEL_26;
      }
      *((_QWORD *)v14 + 7) = 0;
      v19 = 1745;
      dwErrCode = 1745;
    }
    else
    {
      v29 = "ApiOpenGroupEx";
      v30 = (struct _HCLUSTER **)((char *)a1 + 40);
      v31 = a2;
      LODWORD(p_dwErrCode) = a3;
      v33 = &v27;
      v34 = &dwErrCode;
      *((_QWORD *)v14 + 7) = ReconnectOnNull<OpenGroupExFunctor>(&v29, &dwErrCode, a1);
      v19 = dwErrCode;
    }
    v20 = v27;
LABEL_26:
    if ( *((_QWORD *)v14 + 7) && !v19 )
    {
      if ( a4 )
        *a4 = v20;
      v14[16] = v20;
      v21 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 232);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 232));
      v22 = (char *)a1 + 88;
      v23 = *(_QWORD *)v22;
      if ( *(char **)(*(_QWORD *)v22 + 8LL) != v22 )
        __fastfail(3u);
      *((_QWORD *)v14 + 1) = v23;
      *((_QWORD *)v14 + 2) = v22;
      *(_QWORD *)(v23 + 8) = v14 + 2;
      *(_QWORD *)v22 = v14 + 2;
      LeaveCriticalSection(v21);
      v25 = HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Insert<_HGROUP *>(
              v24,
              v14);
      if ( !v25 )
        return (struct _HGROUP *)v14;
      CloseClusterGroupCommon(v14, 0);
      v9 = v25;
      goto LABEL_40;
    }
    if ( v19 == 1745 && *((_WORD *)a1 + 162) > 5u )
      TraceMsg(
        2u,
        2u,
        (__int64)L"OpenClusterGroupImpl",
        302,
        L"Procnum out of range when we thought we were talking to a post-win2k8 cluster.");
    LocalFree(*((HLOCAL *)v14 + 6));
    goto LABEL_39;
  }
  GetRefCountedHCLUSTER(&v29, a1);
  v10 = (struct _HCLUSTER **)v29;
  v11 = v30;
  while ( v10 != v11 )
  {
    v12 = OpenClusterGroupImpl(*v10, a2, a3, a4, a5);
    if ( v12 )
      goto LABEL_10;
    ++v10;
  }
  v12 = 0;
LABEL_10:
  std::pair<std::vector<_HCLUSTER *>,std::vector<std::shared_ptr<_CLUSTER>>>::~pair<std::vector<_HCLUSTER *>,std::vector<std::shared_ptr<_CLUSTER>>>(&v29);
  return v12;
}

```

## disassembly

```asm
0x18004b424  push    rbp
0x18004b426  push    rbx
0x18004b427  push    rsi
0x18004b428  push    rdi
0x18004b429  push    r12
0x18004b42b  push    r13
0x18004b42d  push    r14
0x18004b42f  push    r15
0x18004b431  mov     rbp, rsp
0x18004b434  sub     rsp, 78h
0x18004b438  mov     r15, r9
0x18004b43b  mov     r13d, r8d
0x18004b43e  mov     r14, rdx
0x18004b441  mov     rdi, rcx
0x18004b444  mov     rdx, rcx
0x18004b447  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18004b44c  xor     esi, esi
0x18004b44e  test    al, al
0x18004b450  jnz     short loc_18004B45A
0x18004b452  lea     ecx, [rsi+6]
0x18004b455  jmp     loc_18004B6F6
0x18004b45a  mov     [rbp+dwErrCode], esi
0x18004b45d  mov     [rbp+var_40], esi
0x18004b460  mov     [rbp+var_44], esi
0x18004b463  cmp     [rdi+15Ch], esi
0x18004b469  jz      short loc_18004B4C2
0x18004b46b  mov     rdx, rdi
0x18004b46e  lea     rcx, [rbp+var_38]
0x18004b472  call    ?GetRefCountedHCLUSTER@@YA?AU?$pair@V?$vector@PEAU_HCLUSTER@@V?$allocator@PEAU_HCLUSTER@@@std@@@std@@V?$vector@V?$shared_ptr@U_CLUSTER@@@std@@V?$allocator@V?$shared_ptr@U_CLUSTER@@@std@@@2@@2@@std@@PEAU_CLUSTER@@@Z; GetRefCountedHCLUSTER(_CLUSTER *)
0x18004b477  nop
0x18004b478  mov     rbx, [rbp+var_38]
0x18004b47c  mov     rsi, [rbp+var_30]
0x18004b480  mov     r12d, [rbp+arg_20]
0x18004b484  cmp     rbx, rsi
0x18004b487  jz      short loc_18004B4AF
0x18004b489  mov     [rsp+78h+var_58], r12d; int
0x18004b48e  mov     r9, r15; unsigned int *
0x18004b491  mov     r8d, r13d; unsigned int
0x18004b494  mov     rdx, r14; wchar_t *
0x18004b497  mov     rcx, [rbx]; struct _HCLUSTER *
0x18004b49a  call    ?OpenClusterGroupImpl@@YAPEAU_HGROUP@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z; OpenClusterGroupImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)
0x18004b49f  mov     rdi, rax
0x18004b4a2  test    rax, rax
0x18004b4a5  jnz     short loc_18004B4AD
0x18004b4a7  add     rbx, 8
0x18004b4ab  jmp     short loc_18004B484
0x18004b4ad  jmp     short loc_18004B4B1
0x18004b4af  xor     edi, edi
0x18004b4b1  lea     rcx, [rbp+var_38]
0x18004b4b5  call    ??1?$pair@V?$vector@PEAU_HCLUSTER@@V?$allocator@PEAU_HCLUSTER@@@std@@@std@@V?$vector@V?$shared_ptr@U_CLUSTER@@@std@@V?$allocator@V?$shared_ptr@U_CLUSTER@@@std@@@2@@2@@std@@QEAA@XZ; std::pair<std::vector<_HCLUSTER *>,std::vector<std::shared_ptr<_CLUSTER>>>::~pair<std::vector<_HCLUSTER *>,std::vector<std::shared_ptr<_CLUSTER>>>(void)
0x18004b4ba  mov     rax, rdi
0x18004b4bd  jmp     loc_18004B6FE
0x18004b4c2  mov     edx, 48h ; 'H'; uBytes
0x18004b4c7  xor     ecx, ecx; uFlags
0x18004b4c9  call    cs:__imp_LocalAlloc
0x18004b4cf  mov     rbx, rax
0x18004b4d2  test    rax, rax
0x18004b4d5  jnz     short loc_18004B4E1
0x18004b4d7  mov     ecx, 8
0x18004b4dc  jmp     loc_18004B6F6
0x18004b4e1  lea     r8, [rbp+var_40]; unsigned int *
0x18004b4e5  mov     edx, 7FFFFFFFh; unsigned int
0x18004b4ea  mov     rcx, r14; wchar_t *
0x18004b4ed  call    ?MylstrlenW@@YAKPEB_WKPEAK@Z; MylstrlenW(wchar_t const *,ulong,ulong *)
0x18004b4f2  mov     [rbp+dwErrCode], eax
0x18004b4f5  test    eax, eax
0x18004b4f7  jnz     loc_18004B6EA
0x18004b4fd  mov     eax, [rbp+var_40]
0x18004b500  inc     eax
0x18004b502  mov     r12d, eax
0x18004b505  lea     rdx, [rax+rax]; uBytes
0x18004b509  xor     ecx, ecx; uFlags
0x18004b50b  call    cs:__imp_LocalAlloc
0x18004b511  mov     [rbx+30h], rax
0x18004b515  test    rax, rax
0x18004b518  jnz     short loc_18004B525
0x18004b51a  mov     rcx, rbx; hMem
0x18004b51d  call    cs:__imp_LocalFree
0x18004b523  jmp     short loc_18004B4D7
0x18004b525  mov     dword ptr [rbx], 43475250h
0x18004b52b  mov     r8, r14; wchar_t *
0x18004b52e  mov     rdx, r12; unsigned __int64
0x18004b531  mov     rcx, rax; wchar_t *
0x18004b534  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18004b539  mov     esi, eax
0x18004b53b  mov     rcx, [rbx+30h]; wchar_t *
0x18004b53f  test    eax, eax
0x18004b541  jns     short loc_18004B574
0x18004b543  call    cs:__imp_LocalFree
0x18004b549  mov     rcx, rbx; hMem
0x18004b54c  call    cs:__imp_LocalFree
0x18004b552  mov     ecx, esi
0x18004b554  and     ecx, 1FFF0000h
0x18004b55a  cmp     ecx, 70000h
0x18004b560  jnz     short loc_18004B56D
0x18004b562  movzx   ecx, si
0x18004b565  test    ecx, ecx
0x18004b567  jnz     loc_18004B6F6
0x18004b56d  mov     ecx, esi
0x18004b56f  jmp     loc_18004B6F6
0x18004b574  mov     r8, r14; wchar_t *
0x18004b577  mov     rdx, r12; unsigned __int64
0x18004b57a  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18004b57f  mov     [rbx+28h], rdi
0x18004b583  lea     rax, [rbx+18h]
0x18004b587  mov     [rax+8], rax
0x18004b58b  mov     [rax], rax
0x18004b58e  mov     esi, 6D1h
0x18004b593  cmp     word ptr [rdi+144h], 5
0x18004b59b  jbe     short loc_18004B5E1
0x18004b59d  lea     rax, aApiopengroupex; "ApiOpenGroupEx"
0x18004b5a4  mov     [rbp+var_38], rax
0x18004b5a8  lea     rax, [rdi+28h]
0x18004b5ac  mov     [rbp+var_30], rax
0x18004b5b0  mov     [rbp+var_28], r14
0x18004b5b4  mov     dword ptr [rbp+var_20], r13d
0x18004b5b8  lea     rax, [rbp+var_44]
0x18004b5bc  mov     [rbp+var_18], rax
0x18004b5c0  lea     rax, [rbp+dwErrCode]
0x18004b5c4  mov     [rbp+var_10], rax
0x18004b5c8  mov     r8, rdi
0x18004b5cb  lea     rdx, [rbp+dwErrCode]
0x18004b5cf  lea     rcx, [rbp+var_38]
0x18004b5d3  call    ??$ReconnectOnNull@VOpenGroupExFunctor@@@@YAPEAXAEBVOpenGroupExFunctor@@PEAKPEAU_CLUSTER@@@Z; ReconnectOnNull<OpenGroupExFunctor>(OpenGroupExFunctor const &,ulong *,_CLUSTER *)
0x18004b5d8  mov     [rbx+38h], rax
0x18004b5dc  mov     eax, [rbp+dwErrCode]
0x18004b5df  jmp     short loc_18004B634
0x18004b5e1  cmp     [rbp+arg_20], 0
0x18004b5e5  jz      short loc_18004B627
0x18004b5e7  lea     rax, aApiopengroup; "ApiOpenGroup"
0x18004b5ee  mov     [rbp+var_38], rax
0x18004b5f2  lea     rax, [rdi+28h]
0x18004b5f6  mov     [rbp+var_30], rax
0x18004b5fa  mov     [rbp+var_28], r14
0x18004b5fe  lea     rax, [rbp+dwErrCode]
0x18004b602  mov     [rbp+var_20], rax
0x18004b606  mov     r8, rdi
0x18004b609  lea     rdx, [rbp+dwErrCode]
0x18004b60d  lea     rcx, [rbp+var_38]
0x18004b611  call    ??$ReconnectOnNull@VOpenGroupFunctor@@@@YAPEAXAEBVOpenGroupFunctor@@PEAKPEAU_CLUSTER@@@Z; ReconnectOnNull<OpenGroupFunctor>(OpenGroupFunctor const &,ulong *,_CLUSTER *)
0x18004b616  mov     [rbx+38h], rax
0x18004b61a  mov     ecx, 10000000h
0x18004b61f  mov     [rbp+var_44], ecx
0x18004b622  mov     eax, [rbp+dwErrCode]
0x18004b625  jmp     short loc_18004B637
0x18004b627  mov     qword ptr [rbx+38h], 0
0x18004b62f  mov     eax, esi
0x18004b631  mov     [rbp+dwErrCode], eax
0x18004b634  mov     ecx, [rbp+var_44]
0x18004b637  cmp     qword ptr [rbx+38h], 0
0x18004b63c  jz      short loc_18004B6AD
0x18004b63e  test    eax, eax
0x18004b640  jnz     short loc_18004B6AD
0x18004b642  test    r15, r15
0x18004b645  jz      short loc_18004B64A
0x18004b647  mov     [r15], ecx
0x18004b64a  mov     [rbx+40h], ecx
0x18004b64d  lea     rsi, [rdi+0E8h]
0x18004b654  mov     rcx, rsi; lpCriticalSection
0x18004b657  call    cs:__imp_EnterCriticalSection
0x18004b65d  add     rdi, 58h ; 'X'
0x18004b661  mov     rcx, [rdi]
0x18004b664  cmp     [rcx+8], rdi
0x18004b668  jz      short loc_18004B671
0x18004b66a  mov     ecx, 3
0x18004b66f  int     29h; Win8: RtlFailFast(ecx)
0x18004b671  lea     rax, [rbx+8]
0x18004b675  mov     [rax], rcx
0x18004b678  mov     [rax+8], rdi
0x18004b67c  mov     [rcx+8], rax
0x18004b680  mov     [rdi], rax
0x18004b683  mov     rcx, rsi; lpCriticalSection
0x18004b686  call    cs:__imp_LeaveCriticalSection
0x18004b68c  mov     rdx, rbx
0x18004b68f  call    ??$Insert@PEAU_HGROUP@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAAKPEAU_HGROUP@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Insert<_HGROUP *>(_HGROUP *)
0x18004b694  mov     edi, eax
0x18004b696  test    eax, eax
0x18004b698  jz      short loc_18004B6A8
0x18004b69a  xor     edx, edx; int
0x18004b69c  mov     rcx, rbx; hMem
0x18004b69f  call    ?CloseClusterGroupCommon@@YAHPEAU_HGROUP@@H@Z; CloseClusterGroupCommon(_HGROUP *,int)
0x18004b6a4  mov     ecx, edi
0x18004b6a6  jmp     short loc_18004B6F6
0x18004b6a8  mov     rax, rbx
0x18004b6ab  jmp     short loc_18004B6FE
0x18004b6ad  cmp     eax, esi
0x18004b6af  jnz     short loc_18004B6E0
0x18004b6b1  cmp     word ptr [rdi+144h], 5
0x18004b6b9  jbe     short loc_18004B6E0
0x18004b6bb  lea     rax, aProcnumOutOfRa; "Procnum out of range when we thought we"...
0x18004b6c2  mov     qword ptr [rsp+78h+var_58], rax
0x18004b6c7  mov     r9d, 12Eh
0x18004b6cd  lea     r8, aOpenclustergro_3; "OpenClusterGroupImpl"
0x18004b6d4  mov     ecx, 2
0x18004b6d9  mov     edx, ecx
0x18004b6db  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18004b6e0  mov     rcx, [rbx+30h]; hMem
0x18004b6e4  call    cs:__imp_LocalFree
0x18004b6ea  mov     rcx, rbx; hMem
0x18004b6ed  call    cs:__imp_LocalFree
0x18004b6f3  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18004b6f6  call    cs:__imp_SetLastError
0x18004b6fc  xor     eax, eax
0x18004b6fe  add     rsp, 78h
0x18004b702  pop     r15
0x18004b704  pop     r14
0x18004b706  pop     r13
0x18004b708  pop     r12
0x18004b70a  pop     rdi
0x18004b70b  pop     rsi
0x18004b70c  pop     rbx
0x18004b70d  pop     rbp
0x18004b70e  retn
```
