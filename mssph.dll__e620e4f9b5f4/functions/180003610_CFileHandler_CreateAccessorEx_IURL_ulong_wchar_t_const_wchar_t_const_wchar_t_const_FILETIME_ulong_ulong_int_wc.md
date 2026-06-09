# CFileHandler::CreateAccessorEx(IURL *,ulong,wchar_t const *,wchar_t const *,wchar_t const *,_FILETIME,ulong,ulong,int,wchar_t const *,wchar_t const *,int,int,wchar_t const *,IUrlAccessor * *)

- ea: `0x180003610`
- end: `0x18000375c`
- name: `?CreateAccessorEx@CFileHandler@@UEAAJPEAUIURL@@KPEB_W11U_FILETIME@@KKH11HH1PEAPEAUIUrlAccessor@@@Z`
- size: `332`
- prototype: `__int64 __fastcall(CFileHandler *this, struct IURL *, __int64, const wchar_t *, const wchar_t *, const wchar_t *, struct _ACL *, unsigned int, unsigned int, int, const wchar_t *, const wchar_t *, int, int, const wchar_t *, struct IUrlAccessor **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002d00`
- `0x180003610`
- `0x1800038e0`
- `0x180003920`
- `0x180003970`
- `0x180004860`
- `0x18000a240`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003668`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003668`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800036c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800036c2`

## pseudocode

```c
__int64 __fastcall CFileHandler::CreateAccessorEx(
        CFileHandler *this,
        struct IURL *a2,
        __int64 a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6,
        struct _ACL *a7,
        unsigned int a8,
        unsigned int a9,
        int a10,
        const wchar_t *a11,
        const wchar_t *a12,
        int a13,
        int a14,
        const wchar_t *a15,
        struct IUrlAccessor **a16)
{
  struct IUrlAccessor **v16; // r15
  struct _RTL_CRITICAL_SECTION *v17; // rbp
  struct _RTL_CRITICAL_SECTION *v19; // rcx
  BOOL v21; // eax
  int v22; // esi
  struct IUrlAccessor **v23; // rbx
  struct CSingleLink *v24; // rax
  struct CSingleLink *v25; // rdi
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // edi
  int v29; // edi
  __int64 v31; // [rsp+60h] [rbp+8h] BYREF

  v16 = a16;
  v17 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  v19 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  v21 = a13 != 0;
  *a16 = 0;
  v22 = v21 | 2;
  if ( !a14 )
    v22 = v21;
  v23 = 0;
  a16 = 0;
  EnterCriticalSection(v19);
  if ( *((_DWORD *)this + 22)
    && (v24 = CLnkList::RemoveAfter((CFileHandler *)((char *)this + 64), (CFileHandler *)((char *)this + 64)),
        (v25 = v24) != 0)
    && (v26 = *((_QWORD *)v24 + 1)) != 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
    v23 = (struct IUrlAccessor **)*((_QWORD *)v25 + 1);
    a16 = v23;
    TNoUnkSList<CFileAccessor>::DestroyLink(v27, v25);
    v28 = 0;
  }
  else
  {
    v28 = 1;
  }
  if ( v17 )
    LeaveCriticalSection(v17);
  if ( v28 )
  {
    v31 = 0;
    v29 = ATL::CComObject<CFileAccessor>::CreateInstance(&v31);
    if ( v29 < 0 )
      goto LABEL_15;
    TComPointer<CFileStream>::operator=(&a16, v31);
    v23 = a16;
  }
  v29 = CFileAccessor::Init((__int64)v23, (__int64)a2, a7, v22, (__int64)this);
  if ( v29 >= 0 )
  {
    ((void (__fastcall *)(struct IUrlAccessor **))(*v23)[1].lpVtbl)(v23);
    *v16 = (struct IUrlAccessor *)v23;
  }
LABEL_15:
  TComNoUnkPointer<CFileAccessor>::~TComNoUnkPointer<CFileAccessor>(&a16);
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x180003610  mov     [rsp+arg_8], rbx
0x180003615  mov     [rsp+arg_10], rbp
0x18000361a  push    rsi
0x18000361b  push    rdi
0x18000361c  push    r12
0x18000361e  push    r14
0x180003620  push    r15
0x180003622  sub     rsp, 30h
0x180003626  mov     r15, [rsp+58h+arg_78]
0x18000362e  lea     rbp, [rcx+60h]
0x180003632  xor     eax, eax
0x180003634  mov     r14, rcx
0x180003637  cmp     [rsp+58h+arg_60], eax
0x18000363e  mov     rcx, rbp; lpCriticalSection
0x180003641  mov     r12, rdx
0x180003644  setnz   al
0x180003647  mov     qword ptr [r15], 0
0x18000364e  mov     esi, eax
0x180003650  or      esi, 2
0x180003653  cmp     [rsp+58h+arg_68], 0
0x18000365b  cmovz   esi, eax
0x18000365e  xor     ebx, ebx
0x180003660  mov     [rsp+58h+arg_78], rbx
0x180003668  call    cs:__imp_EnterCriticalSection
0x18000366e  cmp     [r14+58h], ebx
0x180003672  lea     rdx, [r14+40h]; struct CSingleLink *
0x180003676  jz      short loc_1800036B5
0x180003678  mov     rcx, rdx; this
0x18000367b  call    ?RemoveAfter@CLnkList@@IEAAPEAVCSingleLink@@PEAV2@@Z; CLnkList::RemoveAfter(CSingleLink *)
0x180003680  mov     rdi, rax
0x180003683  test    rax, rax
0x180003686  jz      short loc_1800036B5
0x180003688  mov     rcx, [rax+8]
0x18000368c  test    rcx, rcx
0x18000368f  jz      short loc_1800036B5
0x180003691  mov     rax, [rcx]
0x180003694  mov     rax, [rax+8]
0x180003698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000369d  mov     rbx, [rdi+8]
0x1800036a1  mov     rdx, rdi
0x1800036a4  mov     [rsp+58h+arg_78], rbx
0x1800036ac  call    ?DestroyLink@?$TNoUnkSList@VCFileAccessor@@@@IEAAXPEAV?$TNoUnkSingleLink@VCFileAccessor@@@@@Z; TNoUnkSList<CFileAccessor>::DestroyLink(TNoUnkSingleLink<CFileAccessor> *)
0x1800036b1  xor     edi, edi
0x1800036b3  jmp     short loc_1800036BA
0x1800036b5  mov     edi, 1
0x1800036ba  test    rbp, rbp
0x1800036bd  jz      short loc_1800036C8
0x1800036bf  mov     rcx, rbp; lpCriticalSection
0x1800036c2  call    cs:__imp_LeaveCriticalSection
0x1800036c8  test    edi, edi
0x1800036ca  jz      short loc_180003701
0x1800036cc  lea     rcx, [rsp+58h+arg_0]
0x1800036d1  mov     [rsp+58h+arg_0], 0
0x1800036da  call    ?CreateInstance@?$CComObject@VCFileAccessor@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFileAccessor>::CreateInstance(ATL::CComObject<CFileAccessor> * *)
0x1800036df  mov     edi, eax
0x1800036e1  test    eax, eax
0x1800036e3  js      short loc_180003736
0x1800036e5  mov     rdx, [rsp+58h+arg_0]
0x1800036ea  lea     rcx, [rsp+58h+arg_78]
0x1800036f2  call    ??4?$TComPointer@VCFileStream@@@@QEAAPEAVCFileStream@@PEAV1@@Z; TComPointer<CFileStream>::operator=(CFileStream *)
0x1800036f7  mov     rbx, [rsp+58h+arg_78]
0x1800036ff  jmp     short loc_180003703
0x180003701  js      short loc_180003736
0x180003703  mov     r8, qword ptr [rsp+58h+arg_30.dwLowDateTime]
0x18000370b  mov     r9d, esi
0x18000370e  mov     rdx, r12
0x180003711  mov     [rsp+58h+var_38], r14
0x180003716  mov     rcx, rbx
0x180003719  call    ?Init@CFileAccessor@@QEAAJPEAUIURL@@U_FILETIME@@W4CREATE_ACCESSOR_FLAGS@@PEAVCFileHandler@@@Z; CFileAccessor::Init(IURL *,_FILETIME,CREATE_ACCESSOR_FLAGS,CFileHandler *)
0x18000371e  mov     edi, eax
0x180003720  test    eax, eax
0x180003722  js      short loc_180003736
0x180003724  mov     rax, [rbx]
0x180003727  mov     rcx, rbx
0x18000372a  mov     rax, [rax+8]
0x18000372e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003733  mov     [r15], rbx
0x180003736  lea     rcx, [rsp+58h+arg_78]
0x18000373e  call    ??1?$TComNoUnkPointer@VCFileAccessor@@@@QEAA@XZ; TComNoUnkPointer<CFileAccessor>::~TComNoUnkPointer<CFileAccessor>(void)
0x180003743  mov     rbx, [rsp+58h+arg_8]
0x180003748  mov     eax, edi
0x18000374a  mov     rbp, [rsp+58h+arg_10]
0x18000374f  add     rsp, 30h
0x180003753  pop     r15
0x180003755  pop     r14
0x180003757  pop     r12
0x180003759  pop     rdi
0x18000375a  pop     rsi
0x18000375b  retn
```
