# CreateClusterGroupSet

- ea: `0x180086e60`
- end: `0x180087055`
- name: `CreateClusterGroupSet`
- size: `501`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180086ba0`
- `0x180087540`

## callees

- `0x18001236c`
- `0x180014638`
- `0x180025478`
- `0x1800841d0`
- `0x18008611c`
- `0x18008652c`
- `0x180086e60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180086ffd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180086ffd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180086fcb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180086fcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008703a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008703a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086f1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086f3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086f45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180087028`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180087031`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086f1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086f3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086f45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180087028`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180087031`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180086ec3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180086f0a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180086ec3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180086f0a`
- `api-ms-win-security-base-l1-1-0!AreAnyAccessesGranted` at `0x180086eaa`
- `api-ms-win-security-base-l1-1-0!AreAnyAccessesGranted` at `0x180086eaa`

## string_xrefs

- `0x180086f84`: `ApiCreateGroupSet`

## pseudocode

```c
_DWORD *__fastcall CreateClusterGroupSet(__int64 a1, const wchar_t *a2)
{
  DWORD v4; // ecx
  DWORD v5; // ecx
  _DWORD *v6; // rbx
  __int64 v7; // rax
  unsigned __int64 v8; // rsi
  wchar_t *v9; // rax
  int v10; // esi
  __int64 v11; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rsi
  __int64 *v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rcx
  DWORD v16; // edi
  _QWORD v18[4]; // [rsp+20h] [rbp-20h] BYREF
  DWORD dwErrCode; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v20; // [rsp+78h] [rbp+38h] BYREF

  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           a1,
                           a1) )
  {
    v4 = 6;
    goto LABEL_23;
  }
  v5 = *(_DWORD *)(a1 + 320);
  dwErrCode = 0;
  v20 = 0;
  if ( !AreAnyAccessesGranted(v5, 0x10000003u) )
  {
    v4 = 5;
    goto LABEL_23;
  }
  v6 = LocalAlloc(0, 0x48u);
  if ( !v6 )
  {
LABEL_6:
    v4 = 8;
    goto LABEL_23;
  }
  dwErrCode = MylstrlenW(a2, 0x7FFFFFFFu, &v20);
  if ( dwErrCode )
  {
LABEL_22:
    LocalFree(v6);
    v4 = dwErrCode;
    goto LABEL_23;
  }
  v7 = v20 + 1;
  *v6 = 1128484684;
  v8 = (unsigned int)v7;
  v9 = (wchar_t *)LocalAlloc(0, 2 * v7);
  *((_QWORD *)v6 + 6) = v9;
  if ( !v9 )
  {
    LocalFree(v6);
    goto LABEL_6;
  }
  v10 = StringCchCopyW(v9, v8, a2);
  if ( v10 < 0 )
  {
    LocalFree(*((HLOCAL *)v6 + 6));
    LocalFree(v6);
    if ( (v10 & 0x1FFF0000) != 0x70000 || (v4 = (unsigned __int16)v10, !(_WORD)v10) )
      v4 = v10;
    goto LABEL_23;
  }
  *((_QWORD *)v6 + 5) = a1;
  *((_QWORD *)v6 + 4) = v6 + 6;
  *((_QWORD *)v6 + 3) = v6 + 6;
  v18[2] = a2;
  v18[0] = "ApiCreateGroupSet";
  v18[1] = a1 + 40;
  v18[3] = &dwErrCode;
  v11 = ReconnectOnNull<CreateGroupSetFunctor>(v18, &dwErrCode, a1);
  *((_QWORD *)v6 + 7) = v11;
  v6[16] = 0x10000000;
  if ( !v11 || dwErrCode )
  {
    LocalFree(*((HLOCAL *)v6 + 6));
    goto LABEL_22;
  }
  v12 = (struct _RTL_CRITICAL_SECTION *)(a1 + 232);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 232));
  v13 = (__int64 *)(a1 + 184);
  v14 = *v13;
  if ( *(__int64 **)(*v13 + 8) != v13 )
    __fastfail(3u);
  *((_QWORD *)v6 + 1) = v14;
  *((_QWORD *)v6 + 2) = v13;
  *(_QWORD *)(v14 + 8) = v6 + 2;
  *v13 = (__int64)(v6 + 2);
  LeaveCriticalSection(v12);
  v16 = HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Insert<_HGROUPSET *>(
          v15,
          v6);
  if ( !v16 )
    return v6;
  CloseClusterGroupSetCommon(v6, 0);
  v4 = v16;
LABEL_23:
  SetLastError(v4);
  return 0;
}

```

## disassembly

```asm
0x180086e60  mov     [rsp-18h+arg_0], rbx
0x180086e65  mov     [rsp-18h+arg_8], rsi
0x180086e6a  push    rbp
0x180086e6b  push    rdi
0x180086e6c  push    r14
0x180086e6e  mov     rbp, rsp
0x180086e71  sub     rsp, 40h
0x180086e75  mov     r14, rdx
0x180086e78  mov     rdi, rcx
0x180086e7b  mov     rdx, rcx
0x180086e7e  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x180086e83  test    al, al
0x180086e85  jnz     short loc_180086E91
0x180086e87  mov     ecx, 6
0x180086e8c  jmp     loc_18008703A
0x180086e91  mov     ecx, [rdi+140h]; GrantedAccess
0x180086e97  mov     edx, 10000003h; DesiredAccess
0x180086e9c  mov     [rbp+dwErrCode], 0
0x180086ea3  mov     [rbp+arg_18], 0
0x180086eaa  call    cs:__imp_AreAnyAccessesGranted
0x180086eb0  test    eax, eax
0x180086eb2  jnz     short loc_180086EBC
0x180086eb4  lea     ecx, [rax+5]
0x180086eb7  jmp     loc_18008703A
0x180086ebc  mov     edx, 48h ; 'H'; uBytes
0x180086ec1  xor     ecx, ecx; uFlags
0x180086ec3  call    cs:__imp_LocalAlloc
0x180086ec9  mov     rbx, rax
0x180086ecc  test    rax, rax
0x180086ecf  jnz     short loc_180086EDB
0x180086ed1  mov     ecx, 8
0x180086ed6  jmp     loc_18008703A
0x180086edb  lea     r8, [rbp+arg_18]; unsigned int *
0x180086edf  mov     edx, 7FFFFFFFh; unsigned int
0x180086ee4  mov     rcx, r14; wchar_t *
0x180086ee7  call    ?MylstrlenW@@YAKPEB_WKPEAK@Z; MylstrlenW(wchar_t const *,ulong,ulong *)
0x180086eec  mov     [rbp+dwErrCode], eax
0x180086eef  test    eax, eax
0x180086ef1  jnz     loc_18008702E
0x180086ef7  mov     eax, [rbp+arg_18]
0x180086efa  xor     ecx, ecx; uFlags
0x180086efc  inc     eax
0x180086efe  mov     dword ptr [rbx], 43434F4Ch
0x180086f04  mov     esi, eax
0x180086f06  lea     rdx, [rax+rax]; uBytes
0x180086f0a  call    cs:__imp_LocalAlloc
0x180086f10  mov     [rbx+30h], rax
0x180086f14  test    rax, rax
0x180086f17  jnz     short loc_180086F24
0x180086f19  mov     rcx, rbx; hMem
0x180086f1c  call    cs:__imp_LocalFree
0x180086f22  jmp     short loc_180086ED1
0x180086f24  mov     r8, r14; wchar_t *
0x180086f27  mov     rdx, rsi; unsigned __int64
0x180086f2a  mov     rcx, rax; wchar_t *
0x180086f2d  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180086f32  mov     esi, eax
0x180086f34  test    eax, eax
0x180086f36  jns     short loc_180086F6D
0x180086f38  mov     rcx, [rbx+30h]; hMem
0x180086f3c  call    cs:__imp_LocalFree
0x180086f42  mov     rcx, rbx; hMem
0x180086f45  call    cs:__imp_LocalFree
0x180086f4b  mov     ecx, esi
0x180086f4d  and     ecx, 1FFF0000h
0x180086f53  cmp     ecx, 70000h
0x180086f59  jnz     short loc_180086F66
0x180086f5b  movzx   ecx, si
0x180086f5e  test    ecx, ecx
0x180086f60  jnz     loc_18008703A
0x180086f66  mov     ecx, esi
0x180086f68  jmp     loc_18008703A
0x180086f6d  lea     rax, [rbx+18h]
0x180086f71  mov     [rbx+28h], rdi
0x180086f75  mov     [rax+8], rax
0x180086f79  lea     rdx, [rbp+dwErrCode]
0x180086f7d  mov     [rax], rax
0x180086f80  lea     rcx, [rbp+var_20]
0x180086f84  lea     rax, aApicreategroup_2; "ApiCreateGroupSet"
0x180086f8b  mov     [rbp+var_10], r14
0x180086f8f  mov     [rbp+var_20], rax
0x180086f93  mov     r8, rdi
0x180086f96  lea     rax, [rdi+28h]
0x180086f9a  mov     [rbp+var_18], rax
0x180086f9e  lea     rax, [rbp+dwErrCode]
0x180086fa2  mov     [rbp+var_8], rax
0x180086fa6  call    ??$ReconnectOnNull@VCreateGroupSetFunctor@@@@YAPEAXAEBVCreateGroupSetFunctor@@PEAKPEAU_CLUSTER@@@Z; ReconnectOnNull<CreateGroupSetFunctor>(CreateGroupSetFunctor const &,ulong *,_CLUSTER *)
0x180086fab  mov     [rbx+38h], rax
0x180086faf  mov     dword ptr [rbx+40h], 10000000h
0x180086fb6  test    rax, rax
0x180086fb9  jz      short loc_180087024
0x180086fbb  cmp     [rbp+dwErrCode], 0
0x180086fbf  jnz     short loc_180087024
0x180086fc1  lea     rsi, [rdi+0E8h]
0x180086fc8  mov     rcx, rsi; lpCriticalSection
0x180086fcb  call    cs:__imp_EnterCriticalSection
0x180086fd1  add     rdi, 0B8h
0x180086fd8  mov     rcx, [rdi]
0x180086fdb  cmp     [rcx+8], rdi
0x180086fdf  jz      short loc_180086FE8
0x180086fe1  mov     ecx, 3
0x180086fe6  int     29h; Win8: RtlFailFast(ecx)
0x180086fe8  lea     rax, [rbx+8]
0x180086fec  mov     [rax], rcx
0x180086fef  mov     [rax+8], rdi
0x180086ff3  mov     [rcx+8], rax
0x180086ff7  mov     rcx, rsi; lpCriticalSection
0x180086ffa  mov     [rdi], rax
0x180086ffd  call    cs:__imp_LeaveCriticalSection
0x180087003  mov     rdx, rbx
0x180087006  call    ??$Insert@PEAU_HGROUPSET@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAAKPEAU_HGROUPSET@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Insert<_HGROUPSET *>(_HGROUPSET *)
0x18008700b  mov     edi, eax
0x18008700d  test    eax, eax
0x18008700f  jz      short loc_18008701F
0x180087011  xor     edx, edx; int
0x180087013  mov     rcx, rbx; hMem
0x180087016  call    ?CloseClusterGroupSetCommon@@YAHPEAU_HGROUPSET@@H@Z; CloseClusterGroupSetCommon(_HGROUPSET *,int)
0x18008701b  mov     ecx, edi
0x18008701d  jmp     short loc_18008703A
0x18008701f  mov     rax, rbx
0x180087022  jmp     short loc_180087042
0x180087024  mov     rcx, [rbx+30h]; hMem
0x180087028  call    cs:__imp_LocalFree
0x18008702e  mov     rcx, rbx; hMem
0x180087031  call    cs:__imp_LocalFree
0x180087037  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18008703a  call    cs:__imp_SetLastError
0x180087040  xor     eax, eax
0x180087042  mov     rbx, [rsp+40h+arg_0]
0x180087047  mov     rsi, [rsp+40h+arg_8]
0x18008704c  add     rsp, 40h
0x180087050  pop     r14
0x180087052  pop     rdi
0x180087053  pop     rbp
0x180087054  retn
```
