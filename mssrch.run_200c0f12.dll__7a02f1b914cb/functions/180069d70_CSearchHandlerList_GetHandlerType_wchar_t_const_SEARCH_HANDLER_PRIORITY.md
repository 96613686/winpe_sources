# CSearchHandlerList::GetHandlerType(wchar_t const *,SEARCH_HANDLER_PRIORITY *)

- ea: `0x180069d70`
- end: `0x18006a039`
- name: `?GetHandlerType@CSearchHandlerList@@UEAAJPEB_WPEAW4SEARCH_HANDLER_PRIORITY@@@Z`
- size: `713`
- prototype: `__int64 __fastcall(CSearchHandlerList *__hidden this, const wchar_t *, enum SEARCH_HANDLER_PRIORITY *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180018e0c`
- `0x180069c48`
- `0x180069d70`
- `0x18006a040`
- `0x18006a618`
- `0x18006b728`
- `0x1800919b4`
- `0x180091a78`
- `0x180092bc0`
- `0x1801244c0`
- `0x180124b5c`
- `0x180124bc4`
- `0x180128f60`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180069fc7`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180069fc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180069ee8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180069f53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180069ee8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180069f53`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180069ec3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180069f0b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180069ec3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180069f0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069ec9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069f11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069ec9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069f11`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180069fe7`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180069fe7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006a021`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006a021`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180069e49`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180069e49`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSearchHandlerList::GetHandlerType(
        RTL_SRWLOCK *this,
        const wchar_t *a2,
        enum SEARCH_HANDLER_PRIORITY *a3)
{
  unsigned __int64 v6; // rdi
  const WCHAR *v7; // rbx
  __int64 last_trivial_2; // rax
  const wchar_t *v9; // rdx
  int v10; // eax
  char v11; // si
  bool HandlerPriorityNoLock; // di
  __int64 v14; // rcx
  __int64 v15; // r8
  int v16; // eax
  unsigned __int64 v17; // rax
  RTL_SRWLOCK *v18; // [rsp+30h] [rbp-C8h] BYREF
  GUID v19; // [rsp+40h] [rbp-B8h] BYREF
  GUID v20; // [rsp+50h] [rbp-A8h] BYREF
  _BYTE v21[8]; // [rsp+60h] [rbp-98h] BYREF
  LPCWSTR lpString1; // [rsp+68h] [rbp-90h]
  void *retaddr; // [rsp+F8h] [rbp+0h]

  *(_DWORD *)a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  try
  {
    if ( !v6
      || (v7 = &a2[v6], last_trivial_2 = _std_find_last_trivial_2(a2, v7, 46), (const WCHAR *)last_trivial_2 == v7)
      || (v17 = (last_trivial_2 - (__int64)a2) >> 1, v17 == -1) )
    {
      v9 = L".";
    }
    else
    {
      if ( v6 < v17 )
      {
        std::_Xout_of_range("invalid string_view position");
        goto LABEL_27;
      }
      v9 = &a2[v17];
    }
    TLMString<32,32,1024>::TLMString<32,32,1024>(v21, v9);
    v7 = lpString1;
    if ( __TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA <= *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + (unsigned int)tls_index)
                                                             + 4LL) )
    {
LABEL_8:
      if ( `stringCmpI'::`2'::lcidSystem == 1055 )
      {
        v11 = 1;
        v10 = CompareStringW(0x7Fu, 1u, v7, -1, L".tif", -1) - 2;
      }
      else
      {
        v10 = lstrcmpiW(v7, L".tif");
        v11 = 1;
      }
      if ( v10 && (unsigned int)stringCmpI(lpString1, L".tiff") )
      {
        CSearchHandlerList::LockAndLoadExtensionList((CSearchHandlerList *)this);
        v18 = this + 5;
        AcquireSRWLockShared(this + 5);
        HIDWORD(this[6].Ptr) = GetCurrentThreadId();
        HandlerPriorityNoLock = CSearchHandlerList::GetHandlerPriorityNoLock((CSearchHandlerList *)this, lpString1, a3);
        ReleaseSRWLockShared(this + 5);
        v20 = 0;
        if ( HandlerPriorityNoLock )
        {
          *(_QWORD *)&v19.Data1 = this + 9;
          AcquireSRWLockShared(this + 9);
          HIDWORD(this[10].Ptr) = GetCurrentThreadId();
          std::_Tree<std::_Tmap_traits<TLMString<32,32,1024>,CSearchHandlerList::StorageClassFilterInfo,CSearchHandlerList::SmallStringLess,std::allocator<std::pair<TLMString<32,32,1024> const,CSearchHandlerList::StorageClassFilterInfo>>,0>>::find(
            &this[7],
            &v18,
            v21);
          if ( v18 == this[7].Ptr )
          {
            v16 = 2 * (unsigned __int8)CSearchHandlerList::StorageClassHasIFilter(v14, (__int64)v21, &v20);
          }
          else
          {
            v11 = 0;
            v16 = LOBYTE(v18[16].Ptr) != 0 ? 2 : 0;
          }
          *(_DWORD *)a3 = v16;
          if ( this != (RTL_SRWLOCK *)-72LL )
            ReleaseSRWLockShared(this + 9);
          if ( v11 )
          {
            v19 = v20;
            LOBYTE(v15) = *(_DWORD *)a3 == 2;
            CSearchHandlerList::LockInsertInClassNameMap(this, v21, v15, &v19);
          }
        }
      }
      else
      {
        *(_DWORD *)a3 = 3;
      }
      TLMString<32,32,1024>::~TLMString<32,32,1024>(v21);
      return 0;
    }
LABEL_27:
    Init_thread_header(&__TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA);
    if ( __TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA == -1 )
    {
      `stringCmpI'::`2'::lcidSystem = GetSystemDefaultLCID();
      Init_thread_footer(&__TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA);
    }
    goto LABEL_8;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      732,
      "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\server\\handlerlist.cxx");
  }
  return 0;
}

```

## disassembly

```asm
0x180069d70  mov     [rsp+arg_8], rbx
0x180069d75  mov     [rsp+arg_18], rsi
0x180069d7a  push    rdi
0x180069d7b  push    r12
0x180069d7d  push    r13
0x180069d7f  push    r14
0x180069d81  push    r15
0x180069d83  sub     rsp, 0D0h
0x180069d8a  mov     rax, cs:__security_cookie
0x180069d91  xor     rax, rsp
0x180069d94  mov     [rsp+0F8h+var_38], rax
0x180069d9c  mov     r14, r8
0x180069d9f  mov     rsi, rdx
0x180069da2  mov     r15, rcx
0x180069da5  xor     r13d, r13d
0x180069da8  mov     [r8], r13d
0x180069dab  mov     r12d, r13d
0x180069dae  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180069db2  mov     rdi, rcx
0x180069db5  inc     rdi
0x180069db8  cmp     [rdx+rdi*2], r13w
0x180069dbd  jnz     short loc_180069DB5
0x180069dbf  test    rdi, rdi
0x180069dc2  jz      short loc_180069DF1
0x180069dc4  lea     rax, [rdi-1]
0x180069dc8  cmp     rax, rcx
0x180069dcb  cmovnb  rax, rcx
0x180069dcf  add     rdx, 2
0x180069dd3  lea     rbx, [rdx+rax*2]
0x180069dd7  mov     r8d, 2Eh ; '.'
0x180069ddd  mov     rdx, rbx
0x180069de0  mov     rcx, rsi
0x180069de3  call    __std_find_last_trivial_2
0x180069de8  cmp     rax, rbx
0x180069deb  jnz     loc_180069F8C
0x180069df1  lea     rdx, Src; "."
0x180069df8  lea     rcx, [rsp+0F8h+var_98]
0x180069dfd  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x180069e02  nop
0x180069e03  mov     rbx, [rsp+0F8h+lpString1]
0x180069e08  mov     ecx, cs:_tls_index
0x180069e0e  mov     rax, gs:58h
0x180069e17  mov     edx, 4
0x180069e1c  mov     rax, [rax+rcx*8]
0x180069e20  mov     ecx, [rdx+rax]
0x180069e23  cmp     cs:?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA, ecx
0x180069e29  jg      loc_180069FCE
0x180069e2f  lea     rdx, aTif; ".tif"
0x180069e36  cmp     cs:?lcidSystem@?1??stringCmpI@@YAHPEB_W0@Z@4KA, 41Fh; ulong `stringCmpI(wchar_t const *,wchar_t const *)'::`2'::lcidSystem
0x180069e40  jz      loc_18006A004
0x180069e46  mov     rcx, rbx; lpString1
0x180069e49  call    cs:__imp_lstrcmpiW
0x180069e4f  mov     esi, 1
0x180069e54  test    eax, eax
0x180069e56  jnz     short loc_180069E9A
0x180069e58  mov     dword ptr [r14], 3
0x180069e5f  lea     rcx, [rsp+0F8h+var_98]
0x180069e64  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x180069e69  nop
0x180069e6a  mov     eax, r12d
0x180069e6d  mov     rcx, [rsp+0F8h+var_38]
0x180069e75  xor     rcx, rsp; StackCookie
0x180069e78  call    __security_check_cookie
0x180069e7d  lea     r11, [rsp+0F8h+var_28]
0x180069e85  mov     rbx, [r11+38h]
0x180069e89  mov     rsi, [r11+48h]
0x180069e8d  mov     rsp, r11
0x180069e90  pop     r15
0x180069e92  pop     r14
0x180069e94  pop     r13
0x180069e96  pop     r12
0x180069e98  pop     rdi
0x180069e99  retn
0x180069e9a  lea     rdx, aTiff; ".tiff"
0x180069ea1  mov     rcx, [rsp+0F8h+lpString1]; lpString1
0x180069ea6  call    ?stringCmpI@@YAHPEB_W0@Z; stringCmpI(wchar_t const *,wchar_t const *)
0x180069eab  test    eax, eax
0x180069ead  jz      short loc_180069E58
0x180069eaf  mov     rcx, r15; this
0x180069eb2  call    ?LockAndLoadExtensionList@CSearchHandlerList@@IEAA_NXZ; CSearchHandlerList::LockAndLoadExtensionList(void)
0x180069eb7  lea     rbx, [r15+28h]
0x180069ebb  mov     [rsp+0F8h+var_C8], rbx
0x180069ec0  mov     rcx, rbx; SRWLock
0x180069ec3  call    cs:__imp_AcquireSRWLockShared
0x180069ec9  call    cs:__imp_GetCurrentThreadId
0x180069ecf  mov     [rbx+0Ch], eax
0x180069ed2  mov     r8, r14; enum SEARCH_HANDLER_PRIORITY *
0x180069ed5  mov     rdx, [rsp+0F8h+lpString1]; wchar_t *
0x180069eda  mov     rcx, r15; this
0x180069edd  call    ?GetHandlerPriorityNoLock@CSearchHandlerList@@IEAA_NPEB_WPEAW4SEARCH_HANDLER_PRIORITY@@@Z; CSearchHandlerList::GetHandlerPriorityNoLock(wchar_t const *,SEARCH_HANDLER_PRIORITY *)
0x180069ee2  mov     dil, al
0x180069ee5  mov     rcx, rbx; SRWLock
0x180069ee8  call    cs:__imp_ReleaseSRWLockShared
0x180069eee  xorps   xmm0, xmm0
0x180069ef1  movups  [rsp+0F8h+var_A8], xmm0
0x180069ef6  test    dil, dil
0x180069ef9  jz      loc_180069E5F
0x180069eff  lea     rdi, [r15+48h]
0x180069f03  mov     qword ptr [rsp+0F8h+var_B8], rdi
0x180069f08  mov     rcx, rdi; SRWLock
0x180069f0b  call    cs:__imp_AcquireSRWLockShared
0x180069f11  call    cs:__imp_GetCurrentThreadId
0x180069f17  mov     [rdi+0Ch], eax
0x180069f1a  lea     r8, [rsp+0F8h+var_98]
0x180069f1f  lea     rdx, [rsp+0F8h+var_C8]
0x180069f24  lea     rcx, [r15+38h]
0x180069f28  call    ?find@?$_Tree@V?$_Tmap_traits@V?$TLMString@$0CA@$0CA@$0EAA@@@UStorageClassFilterInfo@CSearchHandlerList@@USmallStringLess@3@V?$allocator@U?$pair@$$CBV?$TLMString@$0CA@$0CA@$0EAA@@@UStorageClassFilterInfo@CSearchHandlerList@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$TLMString@$0CA@$0CA@$0EAA@@@UStorageClassFilterInfo@CSearchHandlerList@@@std@@@std@@@std@@@2@AEBV?$TLMString@$0CA@$0CA@$0EAA@@@@Z; std::_Tree<std::_Tmap_traits<TLMString<32,32,1024>,CSearchHandlerList::StorageClassFilterInfo,CSearchHandlerList::SmallStringLess,std::allocator<std::pair<TLMString<32,32,1024> const,CSearchHandlerList::StorageClassFilterInfo>>,0>>::find(TLMString<32,32,1024> const &)
0x180069f2d  mov     rax, [rsp+0F8h+var_C8]
0x180069f32  cmp     rax, [r15+38h]
0x180069f36  jz      short loc_180069FAA
0x180069f38  mov     sil, r13b
0x180069f3b  mov     cl, [rax+80h]
0x180069f41  neg     cl
0x180069f43  sbb     eax, eax
0x180069f45  and     eax, 2
0x180069f48  mov     [r14], eax
0x180069f4b  test    rdi, rdi
0x180069f4e  jz      short loc_180069F59
0x180069f50  mov     rcx, rdi; SRWLock
0x180069f53  call    cs:__imp_ReleaseSRWLockShared
0x180069f59  test    sil, sil
0x180069f5c  jz      loc_180069E5F
0x180069f62  movups  xmm0, [rsp+0F8h+var_A8]
0x180069f67  movdqu  [rsp+0F8h+var_B8], xmm0
0x180069f6d  cmp     dword ptr [r14], 2
0x180069f71  setz    r8b
0x180069f75  lea     r9, [rsp+0F8h+var_B8]
0x180069f7a  lea     rdx, [rsp+0F8h+var_98]
0x180069f7f  mov     rcx, r15
0x180069f82  call    ?LockInsertInClassNameMap@CSearchHandlerList@@IEAAXAEAV?$TLMString@$0CA@$0CA@$0EAA@@@_NU_GUID@@@Z; CSearchHandlerList::LockInsertInClassNameMap(TLMString<32,32,1024> &,bool,_GUID)
0x180069f87  jmp     loc_180069E5F
0x180069f8c  sub     rax, rsi
0x180069f8f  sar     rax, 1
0x180069f92  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180069f96  jz      loc_180069DF1
0x180069f9c  cmp     rdi, rax
0x180069f9f  jb      short loc_180069FC0
0x180069fa1  lea     rdx, [rsi+rax*2]
0x180069fa5  jmp     loc_180069DF8
0x180069faa  lea     r8, [rsp+0F8h+var_A8]
0x180069faf  lea     rdx, [rsp+0F8h+var_98]
0x180069fb4  call    ?StorageClassHasIFilter@CSearchHandlerList@@IEAA_NAEAV?$TLMString@$0CA@$0CA@$0EAA@@@PEAU_GUID@@@Z; CSearchHandlerList::StorageClassHasIFilter(TLMString<32,32,1024> &,_GUID *)
0x180069fb9  movzx   eax, al
0x180069fbc  add     eax, eax
0x180069fbe  jmp     short loc_180069F48
0x180069fc0  lea     rcx, aInvalidStringV; "invalid string_view position"
0x180069fc7  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180069fcd  nop
0x180069fce  lea     rcx, ?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA
0x180069fd5  call    _Init_thread_header
0x180069fda  cmp     cs:?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA, 0FFFFFFFFh
0x180069fe1  jnz     loc_180069E2F
0x180069fe7  call    cs:__imp_GetSystemDefaultLCID
0x180069fed  mov     cs:?lcidSystem@?1??stringCmpI@@YAHPEB_W0@Z@4KA, eax; ulong `stringCmpI(wchar_t const *,wchar_t const *)'::`2'::lcidSystem
0x180069ff3  lea     rcx, ?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA
0x180069ffa  call    _Init_thread_footer
0x180069fff  jmp     loc_180069E2F
0x18006a004  mov     [rsp+0F8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18006a00c  mov     [rsp+0F8h+lpString2], rdx; lpString2
0x18006a011  or      r9d, 0FFFFFFFFh; cchCount1
0x18006a015  mov     r8, rbx; lpString1
0x18006a018  lea     esi, [r9+2]
0x18006a01c  mov     edx, esi; dwCmpFlags
0x18006a01e  lea     ecx, [rsi+7Eh]; Locale
0x18006a021  call    cs:__imp_CompareStringW
0x18006a027  add     eax, 0FFFFFFFEh
0x18006a02a  jmp     loc_180069E54
0x18006a02f  mov     r12d, dword ptr [rsp+0F8h+var_C8]
0x18006a034  jmp     loc_180069E6A
```
