# CWmiProvider::_GetCscItemContainerOrSingleItemFromEncodedQuery(tag_SWbemRpnEncodedQuery const &,IOfflineFilesCache *,IOfflineFilesItemContainer * *,IOfflineFilesItem * *)

- ea: `0x180025fe4`
- end: `0x180026174`
- name: `?_GetCscItemContainerOrSingleItemFromEncodedQuery@CWmiProvider@@AEAAJAEBUtag_SWbemRpnEncodedQuery@@PEAUIOfflineFilesCache@@PEAPEAUIOfflineFilesItemContainer@@PEAPEAUIOfflineFilesItem@@@Z`
- size: `400`
- prototype: `int(CWmiProvider *__hidden this, const struct tag_SWbemRpnEncodedQuery *, struct IOfflineFilesCache *, struct IOfflineFilesItemContainer **, struct IOfflineFilesItem **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002617c`

## callees

- `0x1800046c0`
- `0x180008550`
- `0x18000b7c0`
- `0x180025ee8`
- `0x180025fe4`
- `0x18002c010`

## string_xrefs

- `0x1800260bc`: `ParentItemPath`
- `0x180026062`: `ItemPath`

## pseudocode

```c
__int64 __fastcall CWmiProvider::_GetCscItemContainerOrSingleItemFromEncodedQuery(
        CWmiProvider *this,
        const struct tag_SWbemRpnEncodedQuery *a2,
        struct IOfflineFilesCache *a3,
        struct IOfflineFilesItemContainer **a4,
        struct IOfflineFilesItem **a5)
{
  CWmiProvider *ConstBuffer; // rcx
  int v9; // eax
  int PathFromWhereClause; // ebx
  const unsigned __int16 *v11; // rdx
  struct IOfflineFilesCacheVtbl *lpVtbl; // rax
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v15[260]; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+248h] [rbp+148h]
  _WORD *v17; // [rsp+250h] [rbp+150h]
  _WORD *v18; // [rsp+258h] [rbp+158h]
  _WORD *v19; // [rsp+260h] [rbp+160h]
  __int64 v20; // [rsp+268h] [rbp+168h]
  __int64 v21; // [rsp+270h] [rbp+170h]

  v18 = v15;
  *a4 = 0;
  v19 = v15;
  *a5 = 0;
  v17 = v15;
  v20 = 520;
  v15[0] = 0;
  v21 = 520;
  v16 = 34078720;
  if ( (int)CWmiProvider::_ExtractPathFromWhereClause((CWmiProvider *)0x208, a2, L"ItemPath", (struct CPath *)v15) >= 0 )
  {
    ConstBuffer = (CWmiProvider *)CPath::_GetConstBuffer((CPath *)v15);
    if ( *(_WORD *)ConstBuffer )
    {
      v9 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, CWmiProvider *, _QWORD, struct IOfflineFilesItem **))a3->lpVtbl->FindItem)(
             a3,
             ConstBuffer,
             0,
             a5);
LABEL_7:
      PathFromWhereClause = v9;
      goto LABEL_10;
    }
  }
  PathFromWhereClause = CWmiProvider::_ExtractPathFromWhereClause(
                          ConstBuffer,
                          a2,
                          L"ParentItemPath",
                          (struct CPath *)v15);
  if ( PathFromWhereClause >= 0 )
  {
    v14 = 0;
    v11 = CPath::_GetConstBuffer((CPath *)v15);
    lpVtbl = a3->lpVtbl;
    if ( !*v11 )
    {
      v9 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, GUID *, struct IOfflineFilesItemContainer **))lpVtbl->QueryInterface)(
             a3,
             &GUID_3836f049_9413_45dd_bf46_b5aaa82dc310,
             a4);
      goto LABEL_7;
    }
    PathFromWhereClause = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, const unsigned __int16 *, _QWORD, __int64 *))lpVtbl->FindItem)(
                            a3,
                            v11,
                            0,
                            &v14);
    if ( PathFromWhereClause >= 0 )
    {
      PathFromWhereClause = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IOfflineFilesItemContainer **))v14)(
                              v14,
                              &GUID_3836f049_9413_45dd_bf46_b5aaa82dc310,
                              a4);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
LABEL_10:
  CPath::~CPath((CPath *)v15);
  return (unsigned int)PathFromWhereClause;
}

```

## disassembly

```asm
0x180025fe4  push    rbp
0x180025fe6  push    rbx
0x180025fe7  push    rsi
0x180025fe8  push    rdi
0x180025fe9  push    r14
0x180025feb  lea     rbp, [rsp-190h]
0x180025ff3  sub     rsp, 290h
0x180025ffa  mov     rax, cs:__security_cookie
0x180026001  xor     rax, rsp
0x180026004  mov     [rbp+1B0h+var_30], rax
0x18002600b  mov     r14, [rbp+1B0h+arg_20]
0x180026012  lea     rax, [rsp+2B0h+var_270]
0x180026017  mov     [rbp+1B0h+var_58], rax
0x18002601e  mov     ecx, 208h; this
0x180026023  mov     qword ptr [r9], 0
0x18002602a  lea     rax, [rsp+2B0h+var_270]
0x18002602f  mov     [rbp+1B0h+var_50], rax
0x180026036  mov     rsi, r9
0x180026039  lea     rax, [rsp+2B0h+var_270]
0x18002603e  mov     qword ptr [r14], 0
0x180026045  mov     [rbp+1B0h+var_60], rax
0x18002604c  lea     r9, [rsp+2B0h+var_270]; struct CPath *
0x180026051  xor     eax, eax
0x180026053  mov     [rbp+1B0h+var_48], rcx
0x18002605a  mov     rdi, r8
0x18002605d  mov     [rsp+2B0h+var_270], ax
0x180026062  lea     r8, CSCWMI_STR_PROP_ITEMPATH; "ItemPath"
0x180026069  mov     [rbp+1B0h+var_40], rcx
0x180026070  mov     rbx, rdx
0x180026073  mov     [rbp+1B0h+var_68], 2080000h
0x18002607d  call    ?_ExtractPathFromWhereClause@CWmiProvider@@AEAAJAEBUtag_SWbemRpnEncodedQuery@@PEBGPEAVCPath@@@Z; CWmiProvider::_ExtractPathFromWhereClause(tag_SWbemRpnEncodedQuery const &,ushort const *,CPath *)
0x180026082  test    eax, eax
0x180026084  js      short loc_1800260B4
0x180026086  lea     rcx, [rsp+2B0h+var_270]; this
0x18002608b  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x180026090  xor     edx, edx
0x180026092  mov     rcx, rax
0x180026095  cmp     dx, [rax]
0x180026098  jz      short loc_1800260B4
0x18002609a  mov     rdx, [rdi]
0x18002609d  mov     r9, r14
0x1800260a0  xor     r8d, r8d
0x1800260a3  mov     rax, [rdx+50h]
0x1800260a7  mov     rdx, rcx
0x1800260aa  mov     rcx, rdi
0x1800260ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260b2  jmp     short loc_180026103
0x1800260b4  lea     r9, [rsp+2B0h+var_270]; struct CPath *
0x1800260b9  mov     rdx, rbx; struct tag_SWbemRpnEncodedQuery *
0x1800260bc  lea     r8, CSCWMI_STR_PROP_PARENTITEMPATH; "ParentItemPath"
0x1800260c3  call    ?_ExtractPathFromWhereClause@CWmiProvider@@AEAAJAEBUtag_SWbemRpnEncodedQuery@@PEBGPEAVCPath@@@Z; CWmiProvider::_ExtractPathFromWhereClause(tag_SWbemRpnEncodedQuery const &,ushort const *,CPath *)
0x1800260c8  mov     ebx, eax
0x1800260ca  test    eax, eax
0x1800260cc  js      short loc_18002614B
0x1800260ce  lea     rcx, [rsp+2B0h+var_270]; this
0x1800260d3  mov     [rsp+2B0h+var_280], 0
0x1800260dc  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x1800260e1  xor     ecx, ecx
0x1800260e3  mov     rdx, rax
0x1800260e6  cmp     cx, [rax]
0x1800260e9  mov     rcx, rdi
0x1800260ec  mov     rax, [rdi]
0x1800260ef  jnz     short loc_180026107
0x1800260f1  mov     rax, [rax]
0x1800260f4  lea     rdx, _GUID_3836f049_9413_45dd_bf46_b5aaa82dc310
0x1800260fb  mov     r8, rsi
0x1800260fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026103  mov     ebx, eax
0x180026105  jmp     short loc_18002614B
0x180026107  mov     rax, [rax+50h]
0x18002610b  lea     r9, [rsp+2B0h+var_280]
0x180026110  xor     r8d, r8d
0x180026113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026118  mov     ebx, eax
0x18002611a  test    eax, eax
0x18002611c  js      short loc_18002614B
0x18002611e  mov     rcx, [rsp+2B0h+var_280]
0x180026123  lea     rdx, _GUID_3836f049_9413_45dd_bf46_b5aaa82dc310
0x18002612a  mov     r8, rsi
0x18002612d  mov     rax, [rcx]
0x180026130  mov     rax, [rax]
0x180026133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026138  mov     rcx, [rsp+2B0h+var_280]
0x18002613d  mov     ebx, eax
0x18002613f  mov     rax, [rcx]
0x180026142  mov     rax, [rax+10h]
0x180026146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002614b  lea     rcx, [rsp+2B0h+var_270]; this
0x180026150  call    ??1CPath@@QEAA@XZ; CPath::~CPath(void)
0x180026155  mov     eax, ebx
0x180026157  mov     rcx, [rbp+1B0h+var_30]
0x18002615e  xor     rcx, rsp; StackCookie
0x180026161  call    __security_check_cookie
0x180026166  add     rsp, 290h
0x18002616d  pop     r14
0x18002616f  pop     rdi
0x180026170  pop     rsi
0x180026171  pop     rbx
0x180026172  pop     rbp
0x180026173  retn
```
