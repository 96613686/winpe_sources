# EapHost::EapError::FillErrorString(ulong,_GUID const *,wchar_t * &,char * *)

- ea: `0x1800141b0`
- end: `0x18001441d`
- name: `?FillErrorString@EapError@EapHost@@AEBAXKPEBU_GUID@@AEAPEA_WPEAPEAD@Z`
- size: `621`
- prototype: `void __fastcall(DWORD *this, DWORD, struct _GUID *, wchar_t **, char **Arguments)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180013df0`
- `0x18002ca08`

## callees

- `0x1800017a0`
- `0x18000439c`
- `0x180006ccc`
- `0x18000bba8`
- `0x18000eb74`
- `0x18000eb94`
- `0x180011d8c`
- `0x180013344`
- `0x1800136f4`
- `0x18001377c`
- `0x180013d10`
- `0x1800141b0`
- `0x1800149a4`
- `0x180014f20`
- `0x180014fc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800143de`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800143de`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001438c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001438c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014396`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800143d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800143d0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800142dd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800142dd`

## string_xrefs

- `0x180014200`: `eapphost.dll`
- `0x180014276`: `mprmsg.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall EapHost::EapError::FillErrorString(
        DWORD *this,
        DWORD a2,
        struct _GUID *a3,
        wchar_t **a4,
        char **Arguments)
{
  void *v9; // rsi
  GUID *v10; // rbx
  const struct EapHost::TableGuidToDword *GuidToMsgIdTable; // rdi
  GUID *v12; // r8
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  const WCHAR *v20; // rax
  HMODULE LibraryW; // rdi
  DWORD LastError; // ebx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // r10
  void *v28; // rbx
  wchar_t *v29; // [rsp+40h] [rbp-51h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp-49h] BYREF
  void *v31; // [rsp+50h] [rbp-41h] BYREF
  _BYTE v32[16]; // [rsp+58h] [rbp-39h] BYREF
  __int64 v33; // [rsp+68h] [rbp-29h]
  _BYTE v34[32]; // [rsp+70h] [rbp-21h] BYREF
  GUID v35; // [rsp+90h] [rbp-1h] BYREF

  v35 = GUID_EapHost_Cause_Generic_AuthFailure;
  *(_QWORD *)Buffer = 0;
  v29 = 0;
  v9 = (void *)BasicSimpleString<wchar_t>::Copy(L"eapphost.dll");
  v31 = v9;
  if ( !a2 )
  {
    v10 = &v35;
    if ( a3 )
      v10 = a3;
    EapHost::EapError::GetGuidToMsgIdTable();
    GuidToMsgIdTable = EapHost::EapError::GetGuidToMsgIdTable();
    std::_Tree<std::_Tmap_traits<_GUID,unsigned long,std::less<_GUID>,std::allocator<std::pair<_GUID const,unsigned long>>,0>>::_Find_lower_bound<_GUID>(
      GuidToMsgIdTable,
      v32,
      v10);
    v12 = v10;
    v13 = v33;
    if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<_GUID,unsigned long,std::less<_GUID>,std::allocator<std::pair<_GUID const,unsigned long>>,0>>::_Lower_bound_duplicate<_GUID>(
                             v14,
                             v33,
                             v12) )
      v13 = *(_QWORD *)GuidToMsgIdTable;
    if ( v13 == *(_QWORD *)EapHost::EapError::GetGuidToMsgIdTable() || (a2 = *(_DWORD *)(v13 + 44)) == 0 )
    {
      a2 = *this;
      if ( *this - 600 <= 0x116 )
      {
        BasicSimpleString<wchar_t>::Assign(&v31, (__int64)L"mprmsg.dll");
        v9 = v31;
      }
    }
  }
  GetWindowsSystemDirectory(v34);
  v15 = std::_WChar_traits<wchar_t>::length(L"\\");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Append<wchar_t>(v34, v16, v15);
  v17 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
  if ( v9 )
    v17 = (__int64 *)v9;
  v18 = std::_WChar_traits<wchar_t>::length(v17);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Append<wchar_t>(v34, v19, v18);
  v20 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  LibraryW = LoadLibraryW(v20);
  if ( LibraryW )
  {
    if ( FormatMessageW(Arguments != 0 ? 6400 : 6912, LibraryW, a2, 0, Buffer, 2u, Arguments) )
    {
      v28 = *a4;
      HeapAllocator::Free(0);
      HeapAllocator::Free(v28);
      v29 = 0;
      BasicSimpleString<wchar_t>::Assign((void **)&v29, *(__int64 *)Buffer);
      *a4 = v29;
    }
    else
    {
      GetLastError();
    }
  }
  else
  {
    LastError = GetLastError();
    if ( (Microsoft_Windows_EapHostEnableBits & 1) != 0 )
    {
      v23 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      McTemplateU0zq_EtwEventWriteTransfer(v25, v24, v23, LastError);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v26 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      WPP_SF_Sd(
        *(_QWORD *)(v27 + 16),
        10,
        (unsigned int)WPP_d8d3577d84c33b157eb1fb0369fb8d9e_Traceguids,
        v26,
        LastError);
    }
  }
  LocalFree(*(HLOCAL *)Buffer);
  if ( LibraryW )
    FreeLibrary(LibraryW);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v34);
  HeapAllocator::Free(v9);
  HeapAllocator::Free(0);
}

```

## disassembly

```asm
0x1800141b0  push    rbp
0x1800141b2  push    rbx
0x1800141b3  push    rsi
0x1800141b4  push    rdi
0x1800141b5  push    r12
0x1800141b7  push    r14
0x1800141b9  push    r15
0x1800141bb  lea     rbp, [rsp-1Fh]
0x1800141c0  sub     rsp, 0B0h
0x1800141c7  mov     rax, cs:__security_cookie
0x1800141ce  xor     rax, rsp
0x1800141d1  mov     [rbp+4Fh+var_40], rax
0x1800141d5  mov     r14, r9
0x1800141d8  mov     rdi, r8
0x1800141db  mov     ebx, edx
0x1800141dd  mov     r12, rcx
0x1800141e0  mov     r15, [rbp+4Fh+arg_20]
0x1800141e4  movups  xmm0, xmmword ptr cs:GUID_EapHost_Cause_Generic_AuthFailure.Data1
0x1800141eb  movdqu  [rbp+4Fh+var_50], xmm0
0x1800141f0  mov     qword ptr [rbp+4Fh+Buffer], 0
0x1800141f8  mov     [rbp+4Fh+var_A0], 0
0x180014200  lea     rcx, aEapphostDll; "eapphost.dll"
0x180014207  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18001420c  mov     rsi, rax
0x18001420f  mov     [rbp+4Fh+var_90], rax
0x180014213  test    ebx, ebx
0x180014215  jnz     short loc_18001428A
0x180014217  lea     rbx, [rbp+4Fh+var_50]
0x18001421b  test    rdi, rdi
0x18001421e  cmovnz  rbx, rdi
0x180014222  call    ?GetGuidToMsgIdTable@EapError@EapHost@@CAAEBVTableGuidToDword@2@XZ; EapHost::EapError::GetGuidToMsgIdTable(void)
0x180014227  call    ?GetGuidToMsgIdTable@EapError@EapHost@@CAAEBVTableGuidToDword@2@XZ; EapHost::EapError::GetGuidToMsgIdTable(void)
0x18001422c  mov     rdi, rax
0x18001422f  mov     r8, rbx
0x180014232  lea     rdx, [rbp+4Fh+var_88]
0x180014236  mov     rcx, rax
0x180014239  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@KU?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ulong,std::less<_GUID>,std::allocator<std::pair<_GUID const,ulong>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x18001423e  mov     r8, rbx
0x180014241  mov     rbx, [rbp+4Fh+var_78]
0x180014245  mov     rdx, rbx
0x180014248  call    ??$_Lower_bound_duplicate@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@KU?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@3@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ulong,std::less<_GUID>,std::allocator<std::pair<_GUID const,ulong>>,0>>::_Lower_bound_duplicate<_GUID>(std::_Tree_node<std::pair<_GUID const,ulong>,void *> * const,_GUID const &)
0x18001424d  test    al, al
0x18001424f  jnz     short loc_180014254
0x180014251  mov     rbx, [rdi]
0x180014254  call    ?GetGuidToMsgIdTable@EapError@EapHost@@CAAEBVTableGuidToDword@2@XZ; EapHost::EapError::GetGuidToMsgIdTable(void)
0x180014259  cmp     rbx, [rax]
0x18001425c  jz      short loc_180014265
0x18001425e  mov     ebx, [rbx+2Ch]
0x180014261  test    ebx, ebx
0x180014263  jnz     short loc_18001428A
0x180014265  mov     ebx, [r12]
0x180014269  lea     eax, [rbx-258h]
0x18001426f  cmp     eax, 116h
0x180014274  ja      short loc_18001428A
0x180014276  lea     rdx, aMprmsgDll; "mprmsg.dll"
0x18001427d  lea     rcx, [rbp+4Fh+var_90]
0x180014281  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180014286  mov     rsi, [rbp+4Fh+var_90]
0x18001428a  lea     rcx, [rbp+4Fh+var_70]
0x18001428e  call    ?GetWindowsSystemDirectory@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@XZ; GetWindowsSystemDirectory(void)
0x180014293  nop
0x180014294  lea     rcx, asc_180038ED0; "\\"
0x18001429b  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800142a0  mov     r8, rax
0x1800142a3  mov     rdx, rcx
0x1800142a6  lea     rcx, [rbp+4Fh+var_70]
0x1800142aa  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800142af  lea     rcx, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x1800142b6  test    rsi, rsi
0x1800142b9  cmovnz  rcx, rsi
0x1800142bd  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800142c2  mov     r8, rax
0x1800142c5  mov     rdx, rcx
0x1800142c8  lea     rcx, [rbp+4Fh+var_70]
0x1800142cc  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800142d1  lea     rcx, [rbp+4Fh+var_70]
0x1800142d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800142da  mov     rcx, rax; lpLibFileName
0x1800142dd  call    cs:__imp_LoadLibraryW
0x1800142e3  mov     rdi, rax
0x1800142e6  test    rax, rax
0x1800142e9  jnz     short loc_180014359
0x1800142eb  call    cs:__imp_GetLastError
0x1800142f1  mov     ebx, eax
0x1800142f3  test    cs:Microsoft_Windows_EapHostEnableBits, 1
0x1800142fa  jz      short loc_180014310
0x1800142fc  lea     rcx, [rbp+4Fh+var_70]
0x180014300  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180014305  mov     r8, rax
0x180014308  mov     r9d, ebx
0x18001430b  call    McTemplateU0zq_EtwEventWriteTransfer
0x180014310  lea     rax, WPP_GLOBAL_Control
0x180014317  mov     r10, cs:WPP_GLOBAL_Control
0x18001431e  cmp     r10, rax
0x180014321  jz      loc_1800143CC
0x180014327  test    byte ptr [r10+1Ch], 1
0x18001432c  jz      loc_1800143CC
0x180014332  lea     rcx, [rbp+4Fh+var_70]
0x180014336  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001433b  mov     r9, rax
0x18001433e  mov     edx, 0Ah
0x180014343  mov     dword ptr [rsp+0E0h+lpBuffer], ebx
0x180014347  lea     r8, WPP_d8d3577d84c33b157eb1fb0369fb8d9e_Traceguids
0x18001434e  mov     rcx, [r10+10h]
0x180014352  call    WPP_SF_Sd
0x180014357  jmp     short loc_1800143CC
0x180014359  mov     rax, r15
0x18001435c  neg     rax
0x18001435f  sbb     ecx, ecx
0x180014361  and     ecx, 0FFFFFE00h
0x180014367  add     ecx, 1B00h; dwFlags
0x18001436d  mov     [rsp+0E0h+Arguments], r15; Arguments
0x180014372  mov     [rsp+0E0h+nSize], 2; nSize
0x18001437a  lea     rax, [rbp+4Fh+Buffer]
0x18001437e  mov     [rsp+0E0h+lpBuffer], rax; lpBuffer
0x180014383  xor     r9d, r9d; dwLanguageId
0x180014386  mov     r8d, ebx; dwMessageId
0x180014389  mov     rdx, rdi; lpSource
0x18001438c  call    cs:__imp_FormatMessageW
0x180014392  test    eax, eax
0x180014394  jnz     short loc_18001439E
0x180014396  call    cs:__imp_GetLastError
0x18001439c  jmp     short loc_1800143CC
0x18001439e  mov     rbx, [r14]
0x1800143a1  xor     ecx, ecx; void *
0x1800143a3  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800143a8  mov     rcx, rbx; void *
0x1800143ab  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800143b0  mov     [rbp+4Fh+var_A0], 0
0x1800143b8  mov     rdx, qword ptr [rbp+4Fh+Buffer]
0x1800143bc  lea     rcx, [rbp+4Fh+var_A0]
0x1800143c0  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x1800143c5  mov     rax, [rbp+4Fh+var_A0]
0x1800143c9  mov     [r14], rax
0x1800143cc  mov     rcx, qword ptr [rbp+4Fh+Buffer]; hMem
0x1800143d0  call    cs:__imp_LocalFree
0x1800143d6  test    rdi, rdi
0x1800143d9  jz      short loc_1800143E5
0x1800143db  mov     rcx, rdi; hLibModule
0x1800143de  call    cs:__imp_FreeLibrary
0x1800143e4  nop
0x1800143e5  lea     rcx, [rbp+4Fh+var_70]
0x1800143e9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x1800143ee  nop
0x1800143ef  mov     rcx, rsi; void *
0x1800143f2  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800143f7  nop
0x1800143f8  xor     ecx, ecx; void *
0x1800143fa  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800143ff  mov     rcx, [rbp+4Fh+var_40]
0x180014403  xor     rcx, rsp; StackCookie
0x180014406  call    __security_check_cookie
0x18001440b  add     rsp, 0B0h
0x180014412  pop     r15
0x180014414  pop     r14
0x180014416  pop     r12
0x180014418  pop     rdi
0x180014419  pop     rsi
0x18001441a  pop     rbx
0x18001441b  pop     rbp
0x18001441c  retn
```
