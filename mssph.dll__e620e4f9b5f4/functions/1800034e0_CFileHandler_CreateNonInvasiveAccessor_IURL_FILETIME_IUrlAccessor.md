# CFileHandler::CreateNonInvasiveAccessor(IURL *,_FILETIME,IUrlAccessor * *)

- ea: `0x1800034e0`
- end: `0x1800035fc`
- name: `?CreateNonInvasiveAccessor@CFileHandler@@UEAAJPEAUIURL@@U_FILETIME@@PEAPEAUIUrlAccessor@@@Z`
- size: `284`
- prototype: `__int64 __fastcall(CFileHandler *__hidden this, struct IURL *, struct _FILETIME, struct IUrlAccessor **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002d00`
- `0x1800034e0`
- `0x1800038e0`
- `0x180003920`
- `0x180003970`
- `0x180004860`
- `0x18000a240`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003517`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003517`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000356d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000356d`

## pseudocode

```c
__int64 __fastcall CFileHandler::CreateNonInvasiveAccessor(
        CFileHandler *this,
        struct IURL *a2,
        struct _FILETIME a3,
        struct IUrlAccessor **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  struct IUrlAccessor *v6; // rbx
  struct CSingleLink *v10; // rax
  struct CSingleLink *v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // esi
  int v15; // esi
  struct IUrlAccessor *v17; // [rsp+60h] [rbp+8h] BYREF
  __int64 v18; // [rsp+78h] [rbp+20h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  *a4 = 0;
  v6 = 0;
  v17 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  if ( *((_DWORD *)this + 22)
    && (v10 = CLnkList::RemoveAfter((CFileHandler *)((char *)this + 64), (CFileHandler *)((char *)this + 64)),
        (v11 = v10) != 0)
    && (v12 = *((_QWORD *)v10 + 1)) != 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    v6 = (struct IUrlAccessor *)*((_QWORD *)v11 + 1);
    v17 = v6;
    TNoUnkSList<CFileAccessor>::DestroyLink(v13, v11);
    v14 = 0;
  }
  else
  {
    v14 = 1;
  }
  if ( v4 )
    LeaveCriticalSection(v4);
  if ( v14 )
  {
    v18 = 0;
    v15 = ATL::CComObject<CFileAccessor>::CreateInstance(&v18);
    if ( v15 < 0 )
      goto LABEL_13;
    TComPointer<CFileStream>::operator=(&v17, v18);
    v6 = v17;
  }
  v15 = CFileAccessor::Init((__int64)v6, (__int64)a2, *(struct _ACL **)&a3, 4, (__int64)this);
  if ( v15 >= 0 )
  {
    ((void (__fastcall *)(struct IUrlAccessor *))v6->lpVtbl->AddRef)(v6);
    *a4 = v6;
  }
LABEL_13:
  TComNoUnkPointer<CFileAccessor>::~TComNoUnkPointer<CFileAccessor>(&v17);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800034e0  mov     [rsp+arg_8], rbx
0x1800034e5  mov     [rsp+arg_10], rbp
0x1800034ea  push    rsi
0x1800034eb  push    rdi
0x1800034ec  push    r12
0x1800034ee  push    r14
0x1800034f0  push    r15
0x1800034f2  sub     rsp, 30h
0x1800034f6  lea     r14, [rcx+60h]
0x1800034fa  mov     qword ptr [r9], 0
0x180003501  mov     rbp, rcx
0x180003504  xor     ebx, ebx
0x180003506  mov     rcx, r14; lpCriticalSection
0x180003509  mov     [rsp+58h+arg_0], rbx
0x18000350e  mov     r15, r9
0x180003511  mov     rdi, r8
0x180003514  mov     r12, rdx
0x180003517  call    cs:__imp_EnterCriticalSection
0x18000351d  cmp     [rbp+58h], ebx
0x180003520  lea     rdx, [rbp+40h]; struct CSingleLink *
0x180003524  jz      short loc_180003560
0x180003526  mov     rcx, rdx; this
0x180003529  call    ?RemoveAfter@CLnkList@@IEAAPEAVCSingleLink@@PEAV2@@Z; CLnkList::RemoveAfter(CSingleLink *)
0x18000352e  mov     rsi, rax
0x180003531  test    rax, rax
0x180003534  jz      short loc_180003560
0x180003536  mov     rcx, [rax+8]
0x18000353a  test    rcx, rcx
0x18000353d  jz      short loc_180003560
0x18000353f  mov     rax, [rcx]
0x180003542  mov     rax, [rax+8]
0x180003546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000354b  mov     rbx, [rsi+8]
0x18000354f  mov     rdx, rsi
0x180003552  mov     [rsp+58h+arg_0], rbx
0x180003557  call    ?DestroyLink@?$TNoUnkSList@VCFileAccessor@@@@IEAAXPEAV?$TNoUnkSingleLink@VCFileAccessor@@@@@Z; TNoUnkSList<CFileAccessor>::DestroyLink(TNoUnkSingleLink<CFileAccessor> *)
0x18000355c  xor     esi, esi
0x18000355e  jmp     short loc_180003565
0x180003560  mov     esi, 1
0x180003565  test    r14, r14
0x180003568  jz      short loc_180003573
0x18000356a  mov     rcx, r14; lpCriticalSection
0x18000356d  call    cs:__imp_LeaveCriticalSection
0x180003573  test    esi, esi
0x180003575  jz      short loc_1800035A6
0x180003577  lea     rcx, [rsp+58h+arg_18]
0x18000357c  mov     [rsp+58h+arg_18], 0
0x180003585  call    ?CreateInstance@?$CComObject@VCFileAccessor@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFileAccessor>::CreateInstance(ATL::CComObject<CFileAccessor> * *)
0x18000358a  mov     esi, eax
0x18000358c  test    eax, eax
0x18000358e  js      short loc_1800035D9
0x180003590  mov     rdx, [rsp+58h+arg_18]
0x180003595  lea     rcx, [rsp+58h+arg_0]
0x18000359a  call    ??4?$TComPointer@VCFileStream@@@@QEAAPEAVCFileStream@@PEAV1@@Z; TComPointer<CFileStream>::operator=(CFileStream *)
0x18000359f  mov     rbx, [rsp+58h+arg_0]
0x1800035a4  jmp     short loc_1800035A8
0x1800035a6  js      short loc_1800035D9
0x1800035a8  mov     r9d, 4
0x1800035ae  mov     [rsp+58h+var_38], rbp
0x1800035b3  mov     r8, rdi
0x1800035b6  mov     rdx, r12
0x1800035b9  mov     rcx, rbx
0x1800035bc  call    ?Init@CFileAccessor@@QEAAJPEAUIURL@@U_FILETIME@@W4CREATE_ACCESSOR_FLAGS@@PEAVCFileHandler@@@Z; CFileAccessor::Init(IURL *,_FILETIME,CREATE_ACCESSOR_FLAGS,CFileHandler *)
0x1800035c1  mov     esi, eax
0x1800035c3  test    eax, eax
0x1800035c5  js      short loc_1800035D9
0x1800035c7  mov     rax, [rbx]
0x1800035ca  mov     rcx, rbx
0x1800035cd  mov     rax, [rax+8]
0x1800035d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035d6  mov     [r15], rbx
0x1800035d9  lea     rcx, [rsp+58h+arg_0]
0x1800035de  call    ??1?$TComNoUnkPointer@VCFileAccessor@@@@QEAA@XZ; TComNoUnkPointer<CFileAccessor>::~TComNoUnkPointer<CFileAccessor>(void)
0x1800035e3  mov     rbx, [rsp+58h+arg_8]
0x1800035e8  mov     eax, esi
0x1800035ea  mov     rbp, [rsp+58h+arg_10]
0x1800035ef  add     rsp, 30h
0x1800035f3  pop     r15
0x1800035f5  pop     r14
0x1800035f7  pop     r12
0x1800035f9  pop     rdi
0x1800035fa  pop     rsi
0x1800035fb  retn
```
