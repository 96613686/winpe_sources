# CIntelliName::HrGetPseudoMediaTypes(_GUID const &,tagNETCON_MEDIATYPE *,tagNETCON_SUBMEDIATYPE *)

- ea: `0x180032110`
- end: `0x180032390`
- name: `?HrGetPseudoMediaTypes@CIntelliName@@QEBAJAEBU_GUID@@PEAW4tagNETCON_MEDIATYPE@@PEAW4tagNETCON_SUBMEDIATYPE@@@Z`
- size: `640`
- prototype: `int(CIntelliName *__hidden this, const struct _GUID *, enum tagNETCON_MEDIATYPE *, enum tagNETCON_SUBMEDIATYPE *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180025020`
- `0x180031b1c`

## callees

- `0x180001710`
- `0x180031910`
- `0x1800319c0`
- `0x180031a28`
- `0x180032110`
- `0x1800324c4`
- `0x180034a8c`
- `0x180036010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1800322e4`
- `KERNEL32!CompareStringW` at `0x1800322e4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032171`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032171`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800322f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800322f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIntelliName::HrGetPseudoMediaTypes(
        CIntelliName *this,
        const struct _GUID *a2,
        enum tagNETCON_MEDIATYPE *a3,
        enum tagNETCON_SUBMEDIATYPE *a4)
{
  int Instance; // ebx
  struct IUnknown *v8; // r8
  int v9; // r12d
  struct INetCfgComponent *v10; // r14
  int IsLanCapableAdapter; // eax
  __int64 v12; // rdx
  int v13; // esi
  int v15; // [rsp+30h] [rbp-39h] BYREF
  PCNZWCH lpString1; // [rsp+38h] [rbp-31h] BYREF
  struct INetCfg *ppv; // [rsp+40h] [rbp-29h] BYREF
  struct INetCfgComponent *v18; // [rsp+48h] [rbp-21h] BYREF
  struct IUnknown *v19[5]; // [rsp+50h] [rbp-19h] BYREF
  __int128 v20; // [rsp+78h] [rbp+Fh] BYREF

  *(_DWORD *)a4 = 0;
  ppv = 0;
  Instance = CoCreateInstance(&CLSID_CNetCfg, 0, 0x401u, &IID_INetCfg, (LPVOID *)&ppv);
  if ( Instance < 0 )
    return (unsigned int)Instance;
  Instance = ((__int64 (__fastcall *)(struct INetCfg *, _QWORD))ppv->lpVtbl->Initialize)(ppv, 0);
  if ( Instance < 0 )
    goto LABEL_27;
  CIterNetCfgComponent::CIterNetCfgComponent((CIterNetCfgComponent *)v19, ppv, v8);
  v18 = 0;
  v9 = 0;
  do
  {
    if ( Instance < 0 )
      break;
    Instance = CIEnumIter<IEnumNetCfgComponent,INetCfgComponent *>::HrNext(v19, &v18);
    if ( Instance )
      break;
    v20 = 0;
    v10 = v18;
    Instance = ((__int64 (__fastcall *)(struct INetCfgComponent *, __int128 *))v18->lpVtbl->GetInstanceGuid)(v18, &v20);
    if ( Instance )
      goto LABEL_25;
    if ( *(_OWORD *)a2 != v20 )
      goto LABEL_25;
    IsLanCapableAdapter = HrIsLanCapableAdapter(v10);
    Instance = IsLanCapableAdapter;
    if ( IsLanCapableAdapter < 0 )
      goto LABEL_25;
    v9 = 1;
    if ( IsLanCapableAdapter == 1 )
    {
      *a3 = NCM_PHONE;
    }
    else if ( !IsLanCapableAdapter )
    {
      *a3 = NCM_LAN;
      v15 = 0;
      LODWORD(lpString1) = 4;
      Instance = HrQueryNDISAdapterOID(a2, v12, (unsigned int *)&lpString1, &v15);
      if ( Instance )
        goto LABEL_18;
      switch ( v15 )
      {
        case 1:
          goto LABEL_31;
        case 7:
          *(_DWORD *)a4 = 3;
          break;
        case 8:
          *(_DWORD *)a4 = 9;
          break;
        case 9:
LABEL_31:
          *(_DWORD *)a4 = 2;
          break;
        default:
          Instance = 1;
LABEL_18:
          v13 = Instance;
          *(_DWORD *)a4 = 1;
          lpString1 = 0;
          Instance = ((__int64 (__fastcall *)(struct INetCfgComponent *, PCNZWCH *))v10->lpVtbl->GetId)(v10, &lpString1);
          if ( Instance >= 0 )
          {
            if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"sw\\{48926476-2cae-4ded-a86e-73ddebed6779}", -1) == 2 )
              *(_DWORD *)a4 = 8;
            CoTaskMemFree((LPVOID)lpString1);
          }
          if ( v13 < 0 && *(_DWORD *)a4 == 1 )
            Instance = v13;
          break;
      }
    }
LABEL_25:
    ((void (__fastcall *)(struct INetCfgComponent *))v10->lpVtbl->Release)(v10);
  }
  while ( !v9 );
  ((void (__fastcall *)(struct INetCfg *))ppv->lpVtbl->Uninitialize)(ppv);
  CIterNetCfgComponent::~CIterNetCfgComponent(v19);
LABEL_27:
  ((void (__fastcall *)(struct INetCfg *))ppv->lpVtbl->Release)(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180032110  mov     [rsp-8+arg_0], rbx
0x180032115  push    rbp
0x180032116  push    rsi
0x180032117  push    rdi
0x180032118  push    r12
0x18003211a  push    r13
0x18003211c  push    r14
0x18003211e  push    r15
0x180032120  lea     rbp, [rsp-27h]
0x180032125  sub     rsp, 90h
0x18003212c  mov     rax, cs:__security_cookie
0x180032133  xor     rax, rsp
0x180032136  mov     [rbp+57h+var_38], rax
0x18003213a  mov     rdi, r9
0x18003213d  mov     r13, r8
0x180032140  mov     r15, rdx
0x180032143  mov     dword ptr [r9], 0
0x18003214a  mov     [rbp+57h+var_80], 0
0x180032152  lea     rax, [rbp+57h+var_80]
0x180032156  mov     [rsp+0C0h+ppv], rax; ppv
0x18003215b  lea     r9, IID_INetCfg; riid
0x180032162  xor     edx, edx; pUnkOuter
0x180032164  mov     r8d, 401h; dwClsContext
0x18003216a  lea     rcx, CLSID_CNetCfg; rclsid
0x180032171  call    cs:__imp_CoCreateInstance
0x180032177  mov     ebx, eax
0x180032179  test    eax, eax
0x18003217b  js      loc_18003234B
0x180032181  mov     rcx, [rbp+57h+var_80]
0x180032185  mov     rax, [rcx]
0x180032188  xor     edx, edx
0x18003218a  mov     rax, [rax+18h]
0x18003218e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032193  mov     ebx, eax
0x180032195  test    eax, eax
0x180032197  js      loc_18003233B
0x18003219d  mov     rdx, [rbp+57h+var_80]; struct INetCfg *
0x1800321a1  lea     rcx, [rbp+57h+var_70]; this
0x1800321a5  call    ??0CIterNetCfgComponent@@QEAA@PEAUINetCfg@@PEBU_GUID@@@Z; CIterNetCfgComponent::CIterNetCfgComponent(INetCfg *,_GUID const *)
0x1800321aa  nop
0x1800321ab  mov     [rbp+57h+var_78], 0
0x1800321b3  xor     r12d, r12d
0x1800321b6  test    ebx, ebx
0x1800321b8  js      loc_180032321
0x1800321be  lea     rdx, [rbp+57h+var_78]
0x1800321c2  lea     rcx, [rbp+57h+var_70]
0x1800321c6  call    ?HrNext@?$CIEnumIter@UIEnumNetCfgComponent@@PEAUINetCfgComponent@@@@QEAAJPEAPEAUINetCfgComponent@@@Z; CIEnumIter<IEnumNetCfgComponent,INetCfgComponent *>::HrNext(INetCfgComponent * *)
0x1800321cb  mov     ebx, eax
0x1800321cd  test    eax, eax
0x1800321cf  jnz     loc_180032321
0x1800321d5  xorps   xmm0, xmm0
0x1800321d8  movups  [rbp+57h+var_48], xmm0
0x1800321dc  mov     r14, [rbp+57h+var_78]
0x1800321e0  mov     rax, [r14]
0x1800321e3  lea     rdx, [rbp+57h+var_48]
0x1800321e7  mov     rcx, r14
0x1800321ea  mov     rax, [rax+40h]
0x1800321ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800321f3  mov     ebx, eax
0x1800321f5  test    eax, eax
0x1800321f7  jnz     loc_180032309
0x1800321fd  mov     rax, [r15]
0x180032200  cmp     rax, qword ptr [rbp+57h+var_48]
0x180032204  jnz     loc_180032309
0x18003220a  mov     rax, [r15+8]
0x18003220e  cmp     rax, qword ptr [rbp+57h+var_48+8]
0x180032212  jnz     loc_180032309
0x180032218  mov     rcx, r14; struct INetCfgComponent *
0x18003221b  call    ?HrIsLanCapableAdapter@@YAJPEAUINetCfgComponent@@@Z; HrIsLanCapableAdapter(INetCfgComponent *)
0x180032220  mov     ebx, eax
0x180032222  test    eax, eax
0x180032224  js      loc_180032309
0x18003222a  mov     r12d, 1
0x180032230  cmp     eax, r12d
0x180032233  jnz     short loc_180032242
0x180032235  mov     dword ptr [r13+0], 4
0x18003223d  jmp     loc_180032309
0x180032242  test    eax, eax
0x180032244  jnz     loc_180032309
0x18003224a  mov     dword ptr [r13+0], 3
0x180032252  mov     [rbp+57h+var_90], eax
0x180032255  mov     dword ptr [rbp+57h+lpString1], 4
0x18003225c  lea     r9, [rbp+57h+var_90]; void *
0x180032260  lea     r8, [rbp+57h+lpString1]; unsigned int *
0x180032264  mov     rcx, r15; struct _GUID *
0x180032267  call    ?HrQueryNDISAdapterOID@@YAJAEBU_GUID@@KPEAKPEAX@Z; HrQueryNDISAdapterOID(_GUID const &,ulong,ulong *,void *)
0x18003226c  mov     ebx, eax
0x18003226e  test    eax, eax
0x180032270  jnz     short loc_18003229C
0x180032272  mov     eax, [rbp+57h+var_90]
0x180032275  sub     eax, r12d
0x180032278  jz      loc_180032384
0x18003227e  sub     eax, 6
0x180032281  jz      loc_18003237C
0x180032287  sub     eax, r12d
0x18003228a  jz      loc_180032374
0x180032290  cmp     eax, r12d
0x180032293  jz      loc_180032384
0x180032299  mov     ebx, r12d
0x18003229c  mov     esi, ebx
0x18003229e  mov     [rdi], r12d
0x1800322a1  mov     [rbp+57h+lpString1], 0
0x1800322a9  mov     rax, [r14]
0x1800322ac  lea     rdx, [rbp+57h+lpString1]
0x1800322b0  mov     rcx, r14
0x1800322b3  mov     rax, [rax+30h]
0x1800322b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322bc  mov     ebx, eax
0x1800322be  test    eax, eax
0x1800322c0  js      short loc_1800322FF
0x1800322c2  or      ecx, 0FFFFFFFFh
0x1800322c5  mov     [rsp+0C0h+cchCount2], ecx; cchCount2
0x1800322c9  lea     rax, aSw489264762cae; "sw\\{48926476-2cae-4ded-a86e-73ddebed67"...
0x1800322d0  mov     [rsp+0C0h+ppv], rax; lpString2
0x1800322d5  mov     r9d, ecx; cchCount1
0x1800322d8  mov     r8, [rbp+57h+lpString1]; lpString1
0x1800322dc  mov     edx, r12d; dwCmpFlags
0x1800322df  mov     ecx, 7Fh; Locale
0x1800322e4  call    cs:__imp_CompareStringW
0x1800322ea  cmp     eax, 2
0x1800322ed  jnz     short loc_1800322F5
0x1800322ef  mov     dword ptr [rdi], 8
0x1800322f5  mov     rcx, [rbp+57h+lpString1]; pv
0x1800322f9  call    cs:__imp_CoTaskMemFree
0x1800322ff  test    esi, esi
0x180032301  jns     short loc_180032309
0x180032303  cmp     [rdi], r12d
0x180032306  cmovz   ebx, esi
0x180032309  mov     rax, [r14]
0x18003230c  mov     rcx, r14
0x18003230f  mov     rax, [rax+10h]
0x180032313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032318  test    r12d, r12d
0x18003231b  jz      loc_1800321B6
0x180032321  mov     rcx, [rbp+57h+var_80]
0x180032325  mov     rax, [rcx]
0x180032328  mov     rax, [rax+20h]
0x18003232c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032331  nop
0x180032332  lea     rcx, [rbp+57h+var_70]; this
0x180032336  call    ??1CIterNetCfgComponent@@QEAA@XZ; CIterNetCfgComponent::~CIterNetCfgComponent(void)
0x18003233b  mov     rcx, [rbp+57h+var_80]
0x18003233f  mov     rax, [rcx]
0x180032342  mov     rax, [rax+10h]
0x180032346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003234b  mov     eax, ebx
0x18003234d  mov     rcx, [rbp+57h+var_38]
0x180032351  xor     rcx, rsp; StackCookie
0x180032354  call    __security_check_cookie
0x180032359  mov     rbx, [rsp+0C0h+arg_0]
0x180032361  add     rsp, 90h
0x180032368  pop     r15
0x18003236a  pop     r14
0x18003236c  pop     r13
0x18003236e  pop     r12
0x180032370  pop     rdi
0x180032371  pop     rsi
0x180032372  pop     rbp
0x180032373  retn
0x180032374  mov     dword ptr [rdi], 9
0x18003237a  jmp     short loc_180032309
0x18003237c  mov     dword ptr [rdi], 3
0x180032382  jmp     short loc_180032309
0x180032384  mov     dword ptr [rdi], 2
0x18003238a  jmp     loc_180032309
```
