# CFileHandler::CreateAccessorNoContent(IURL *,_FILETIME,int,int,IUrlAccessor * *)

- ea: `0x180003770`
- end: `0x1800038d9`
- name: `?CreateAccessorNoContent@CFileHandler@@UEAAJPEAUIURL@@U_FILETIME@@HHPEAPEAUIUrlAccessor@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(CFileHandler *__hidden this, struct IURL *, struct _FILETIME, int, int, struct IUrlAccessor **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002d00`
- `0x180003770`
- `0x1800038e0`
- `0x180003920`
- `0x180003970`
- `0x180004860`
- `0x18000a240`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800037c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800037c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003890`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003890`

## pseudocode

```c
__int64 __fastcall CFileHandler::CreateAccessorNoContent(
        CFileHandler *this,
        struct IURL *a2,
        struct _FILETIME a3,
        int a4,
        int a5,
        struct IUrlAccessor **a6)
{
  int v9; // r12d
  struct IUrlAccessor **v10; // r15
  struct _RTL_CRITICAL_SECTION *v11; // r14
  struct IUrlAccessor **v12; // rbx
  struct CSingleLink *v13; // rax
  struct CSingleLink *v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // esi
  int v18; // esi
  __int64 v20; // [rsp+80h] [rbp+8h] BYREF

  v9 = 8;
  if ( a4 )
    v9 = 9;
  if ( a5 )
    v9 |= 2u;
  v10 = a6;
  v11 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  v12 = 0;
  a6 = 0;
  *v10 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  if ( *((_DWORD *)this + 22)
    && (v13 = CLnkList::RemoveAfter((CFileHandler *)((char *)this + 64), (CFileHandler *)((char *)this + 64)),
        (v14 = v13) != 0)
    && (v15 = *((_QWORD *)v13 + 1)) != 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    v12 = (struct IUrlAccessor **)*((_QWORD *)v14 + 1);
    a6 = v12;
    TNoUnkSList<CFileAccessor>::DestroyLink(v16, v14);
    v17 = 0;
  }
  else
  {
    v17 = 1;
  }
  if ( v11 )
    LeaveCriticalSection(v11);
  if ( v17 )
  {
    v20 = 0;
    v18 = ATL::CComObject<CFileAccessor>::CreateInstance(&v20);
    if ( v18 < 0 )
      goto LABEL_14;
    TComPointer<CFileStream>::operator=(&a6, v20);
    v12 = a6;
  }
  v18 = CFileAccessor::Init((__int64)v12, (__int64)a2, *(struct _ACL **)&a3, v9, (__int64)this);
  if ( v18 >= 0 )
  {
    ((void (__fastcall *)(struct IUrlAccessor **))(*v12)[1].lpVtbl)(v12);
    *v10 = (struct IUrlAccessor *)v12;
  }
LABEL_14:
  TComNoUnkPointer<CFileAccessor>::~TComNoUnkPointer<CFileAccessor>(&a6);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180003770  push    rbx
0x180003772  push    rbp
0x180003773  push    rsi
0x180003774  push    rdi
0x180003775  push    r12
0x180003777  push    r13
0x180003779  push    r14
0x18000377b  push    r15
0x18000377d  sub     rsp, 38h
0x180003781  mov     rdi, r8
0x180003784  mov     r13, rdx
0x180003787  mov     rbp, rcx
0x18000378a  mov     r12d, 8
0x180003790  test    r9d, r9d
0x180003793  jnz     loc_180003879
0x180003799  cmp     [rsp+78h+arg_20], 0
0x1800037a1  jnz     loc_180003884
0x1800037a7  mov     r15, [rsp+78h+arg_28]
0x1800037af  lea     r14, [rcx+60h]
0x1800037b3  xor     ebx, ebx
0x1800037b5  mov     rcx, r14; lpCriticalSection
0x1800037b8  mov     [rsp+78h+arg_28], rbx
0x1800037c0  mov     qword ptr [r15], 0
0x1800037c7  call    cs:__imp_EnterCriticalSection
0x1800037cd  cmp     [rbp+58h], ebx
0x1800037d0  lea     rdx, [rbp+40h]; struct CSingleLink *
0x1800037d4  jz      loc_180003872
0x1800037da  mov     rcx, rdx; this
0x1800037dd  call    ?RemoveAfter@CLnkList@@IEAAPEAVCSingleLink@@PEAV2@@Z; CLnkList::RemoveAfter(CSingleLink *)
0x1800037e2  mov     rsi, rax
0x1800037e5  test    rax, rax
0x1800037e8  jz      loc_180003872
0x1800037ee  mov     rcx, [rax+8]
0x1800037f2  test    rcx, rcx
0x1800037f5  jz      short loc_180003872
0x1800037f7  mov     rax, [rcx]
0x1800037fa  mov     rax, [rax+8]
0x1800037fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003803  mov     rbx, [rsi+8]
0x180003807  mov     rdx, rsi
0x18000380a  mov     [rsp+78h+arg_28], rbx
0x180003812  call    ?DestroyLink@?$TNoUnkSList@VCFileAccessor@@@@IEAAXPEAV?$TNoUnkSingleLink@VCFileAccessor@@@@@Z; TNoUnkSList<CFileAccessor>::DestroyLink(TNoUnkSingleLink<CFileAccessor> *)
0x180003817  xor     esi, esi
0x180003819  test    r14, r14
0x18000381c  jnz     short loc_18000388D
0x18000381e  test    esi, esi
0x180003820  jnz     short loc_180003898
0x180003822  js      short loc_180003852
0x180003824  mov     r9d, r12d
0x180003827  mov     [rsp+78h+var_58], rbp
0x18000382c  mov     r8, rdi
0x18000382f  mov     rdx, r13
0x180003832  mov     rcx, rbx
0x180003835  call    ?Init@CFileAccessor@@QEAAJPEAUIURL@@U_FILETIME@@W4CREATE_ACCESSOR_FLAGS@@PEAVCFileHandler@@@Z; CFileAccessor::Init(IURL *,_FILETIME,CREATE_ACCESSOR_FLAGS,CFileHandler *)
0x18000383a  mov     esi, eax
0x18000383c  test    eax, eax
0x18000383e  js      short loc_180003852
0x180003840  mov     rax, [rbx]
0x180003843  mov     rcx, rbx
0x180003846  mov     rax, [rax+8]
0x18000384a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000384f  mov     [r15], rbx
0x180003852  lea     rcx, [rsp+78h+arg_28]
0x18000385a  call    ??1?$TComNoUnkPointer@VCFileAccessor@@@@QEAA@XZ; TComNoUnkPointer<CFileAccessor>::~TComNoUnkPointer<CFileAccessor>(void)
0x18000385f  mov     eax, esi
0x180003861  add     rsp, 38h
0x180003865  pop     r15
0x180003867  pop     r14
0x180003869  pop     r13
0x18000386b  pop     r12
0x18000386d  pop     rdi
0x18000386e  pop     rsi
0x18000386f  pop     rbp
0x180003870  pop     rbx
0x180003871  retn
0x180003872  mov     esi, 1
0x180003877  jmp     short loc_180003819
0x180003879  mov     r12d, 9
0x18000387f  jmp     loc_180003799
0x180003884  or      r12d, 2
0x180003888  jmp     loc_1800037A7
0x18000388d  mov     rcx, r14; lpCriticalSection
0x180003890  call    cs:__imp_LeaveCriticalSection
0x180003896  jmp     short loc_18000381E
0x180003898  lea     rcx, [rsp+78h+arg_0]
0x1800038a0  mov     [rsp+78h+arg_0], 0
0x1800038ac  call    ?CreateInstance@?$CComObject@VCFileAccessor@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFileAccessor>::CreateInstance(ATL::CComObject<CFileAccessor> * *)
0x1800038b1  mov     esi, eax
0x1800038b3  test    eax, eax
0x1800038b5  js      short loc_180003852
0x1800038b7  mov     rdx, [rsp+78h+arg_0]
0x1800038bf  lea     rcx, [rsp+78h+arg_28]
0x1800038c7  call    ??4?$TComPointer@VCFileStream@@@@QEAAPEAVCFileStream@@PEAV1@@Z; TComPointer<CFileStream>::operator=(CFileStream *)
0x1800038cc  mov     rbx, [rsp+78h+arg_28]
0x1800038d4  jmp     loc_180003824
```
