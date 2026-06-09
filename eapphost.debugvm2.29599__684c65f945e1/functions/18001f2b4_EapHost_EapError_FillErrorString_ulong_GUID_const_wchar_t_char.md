# EapHost::EapError::FillErrorString(ulong,_GUID const *,wchar_t * &,char * *)

- ea: `0x18001f2b4`
- end: `0x18001f521`
- name: `?FillErrorString@EapError@EapHost@@AEBAXKPEBU_GUID@@AEAPEA_WPEAPEAD@Z`
- size: `621`
- prototype: `void(EapHost::EapError *__hidden this, unsigned int, const struct _GUID *, wchar_t **, char **)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001af5c`
- `0x18001ef0c`

## callees

- `0x180002a90`
- `0x1800052c0`
- `0x1800054c4`
- `0x1800072cc`
- `0x180009844`
- `0x1800118e8`
- `0x180011908`
- `0x1800194d0`
- `0x180019758`
- `0x18001e9f8`
- `0x18001ea80`
- `0x18001f2b4`
- `0x18001faa8`
- `0x18001fdfc`
- `0x18002faa0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001f490`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001f490`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f4e2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f4e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f49a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f49a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001f3e1`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001f3e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f4d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f4d4`

## string_xrefs

- `0x18001f304`: `eapphost.dll`
- `0x18001f37a`: `mprmsg.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall EapHost::EapError::FillErrorString(
        DWORD *this,
        DWORD a2,
        struct _GUID *a3,
        wchar_t **a4,
        char **Arguments)
{
  __int64 *v9; // rsi
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
  __int64 *v31; // [rsp+50h] [rbp-41h] BYREF
  char v32[16]; // [rsp+58h] [rbp-39h] BYREF
  __int64 v33; // [rsp+68h] [rbp-29h]
  _BYTE v34[32]; // [rsp+70h] [rbp-21h] BYREF
  GUID v35; // [rsp+90h] [rbp-1h] BYREF

  v35 = GUID_EapHost_Cause_Generic_AuthFailure;
  *(_QWORD *)Buffer = 0;
  v29 = 0;
  v9 = (__int64 *)BasicSimpleString<wchar_t>::Copy(L"eapphost.dll");
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
        BasicSimpleString<wchar_t>::Assign(&v31, L"mprmsg.dll");
        v9 = v31;
      }
    }
  }
  GetWindowsSystemDirectory((__int64)v34);
  v15 = std::_WChar_traits<wchar_t>::length(L"\\");
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Append<wchar_t>(v34, v16, v15);
  v17 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
  if ( v9 )
    v17 = v9;
  v18 = std::_WChar_traits<wchar_t>::length(v17);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Append<wchar_t>(v34, v19, v18);
  v20 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v34);
  LibraryW = LoadLibraryW(v20);
  if ( LibraryW )
  {
    if ( FormatMessageW(Arguments != 0 ? 6400 : 6912, LibraryW, a2, 0, Buffer, 2u, Arguments) )
    {
      v28 = *a4;
      HeapAllocator::Free(0);
      HeapAllocator::Free(v28);
      v29 = 0;
      BasicSimpleString<wchar_t>::Assign(&v29, *(_QWORD *)Buffer);
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
      v23 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v34);
      McTemplateU0zq_EtwEventWriteTransfer(v25, v24, v23, LastError);
    }
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v26 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v34);
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
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v34);
  HeapAllocator::Free(v9);
  HeapAllocator::Free(0);
}

```

## disassembly

```asm
0x18001f2b4  push    rbp
0x18001f2b6  push    rbx
0x18001f2b7  push    rsi
0x18001f2b8  push    rdi
0x18001f2b9  push    r12
0x18001f2bb  push    r14
0x18001f2bd  push    r15
0x18001f2bf  lea     rbp, [rsp-1Fh]
0x18001f2c4  sub     rsp, 0B0h
0x18001f2cb  mov     rax, cs:__security_cookie
0x18001f2d2  xor     rax, rsp
0x18001f2d5  mov     [rbp+4Fh+var_40], rax
0x18001f2d9  mov     r14, r9
0x18001f2dc  mov     rdi, r8
0x18001f2df  mov     ebx, edx
0x18001f2e1  mov     r12, rcx
0x18001f2e4  mov     r15, [rbp+4Fh+arg_20]
0x18001f2e8  movups  xmm0, xmmword ptr cs:GUID_EapHost_Cause_Generic_AuthFailure.Data1
0x18001f2ef  movdqu  [rbp+4Fh+var_50], xmm0
0x18001f2f4  mov     qword ptr [rbp+4Fh+Buffer], 0
0x18001f2fc  mov     [rbp+4Fh+var_A0], 0
0x18001f304  lea     rcx, aEapphostDll_0; "eapphost.dll"
0x18001f30b  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18001f310  mov     rsi, rax
0x18001f313  mov     [rbp+4Fh+var_90], rax
0x18001f317  test    ebx, ebx
0x18001f319  jnz     short loc_18001F38E
0x18001f31b  lea     rbx, [rbp+4Fh+var_50]
0x18001f31f  test    rdi, rdi
0x18001f322  cmovnz  rbx, rdi
0x18001f326  call    ?GetGuidToMsgIdTable@EapError@EapHost@@CAAEBVTableGuidToDword@2@XZ; EapHost::EapError::GetGuidToMsgIdTable(void)
0x18001f32b  call    ?GetGuidToMsgIdTable@EapError@EapHost@@CAAEBVTableGuidToDword@2@XZ; EapHost::EapError::GetGuidToMsgIdTable(void)
0x18001f330  mov     rdi, rax
0x18001f333  mov     r8, rbx
0x18001f336  lea     rdx, [rbp+4Fh+var_88]
0x18001f33a  mov     rcx, rax
0x18001f33d  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@KU?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ulong,std::less<_GUID>,std::allocator<std::pair<_GUID const,ulong>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x18001f342  mov     r8, rbx
0x18001f345  mov     rbx, [rbp+4Fh+var_78]
0x18001f349  mov     rdx, rbx
0x18001f34c  call    ??$_Lower_bound_duplicate@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@KU?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@3@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ulong,std::less<_GUID>,std::allocator<std::pair<_GUID const,ulong>>,0>>::_Lower_bound_duplicate<_GUID>(std::_Tree_node<std::pair<_GUID const,ulong>,void *> * const,_GUID const &)
0x18001f351  test    al, al
0x18001f353  jnz     short loc_18001F358
0x18001f355  mov     rbx, [rdi]
0x18001f358  call    ?GetGuidToMsgIdTable@EapError@EapHost@@CAAEBVTableGuidToDword@2@XZ; EapHost::EapError::GetGuidToMsgIdTable(void)
0x18001f35d  cmp     rbx, [rax]
0x18001f360  jz      short loc_18001F369
0x18001f362  mov     ebx, [rbx+2Ch]
0x18001f365  test    ebx, ebx
0x18001f367  jnz     short loc_18001F38E
0x18001f369  mov     ebx, [r12]
0x18001f36d  lea     eax, [rbx-258h]
0x18001f373  cmp     eax, 116h
0x18001f378  ja      short loc_18001F38E
0x18001f37a  lea     rdx, aMprmsgDll; "mprmsg.dll"
0x18001f381  lea     rcx, [rbp+4Fh+var_90]
0x18001f385  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x18001f38a  mov     rsi, [rbp+4Fh+var_90]
0x18001f38e  lea     rcx, [rbp+4Fh+var_70]
0x18001f392  call    ?GetWindowsSystemDirectory@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@XZ; GetWindowsSystemDirectory(void)
0x18001f397  nop
0x18001f398  lea     rcx, asc_18003BB1C; "\\"
0x18001f39f  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18001f3a4  mov     r8, rax
0x18001f3a7  mov     rdx, rcx
0x18001f3aa  lea     rcx, [rbp+4Fh+var_70]
0x18001f3ae  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001f3b3  lea     rcx, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x18001f3ba  test    rsi, rsi
0x18001f3bd  cmovnz  rcx, rsi
0x18001f3c1  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18001f3c6  mov     r8, rax
0x18001f3c9  mov     rdx, rcx
0x18001f3cc  lea     rcx, [rbp+4Fh+var_70]
0x18001f3d0  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001f3d5  lea     rcx, [rbp+4Fh+var_70]
0x18001f3d9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001f3de  mov     rcx, rax; lpLibFileName
0x18001f3e1  call    cs:__imp_LoadLibraryW
0x18001f3e7  mov     rdi, rax
0x18001f3ea  test    rax, rax
0x18001f3ed  jnz     short loc_18001F45D
0x18001f3ef  call    cs:__imp_GetLastError
0x18001f3f5  mov     ebx, eax
0x18001f3f7  test    cs:Microsoft_Windows_EapHostEnableBits, 1
0x18001f3fe  jz      short loc_18001F414
0x18001f400  lea     rcx, [rbp+4Fh+var_70]
0x18001f404  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001f409  mov     r8, rax
0x18001f40c  mov     r9d, ebx
0x18001f40f  call    McTemplateU0zq_EtwEventWriteTransfer
0x18001f414  lea     rax, WPP_GLOBAL_Control
0x18001f41b  mov     r10, cs:WPP_GLOBAL_Control
0x18001f422  cmp     r10, rax
0x18001f425  jz      loc_18001F4D0
0x18001f42b  test    byte ptr [r10+1Ch], 1
0x18001f430  jz      loc_18001F4D0
0x18001f436  lea     rcx, [rbp+4Fh+var_70]
0x18001f43a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001f43f  mov     r9, rax
0x18001f442  mov     edx, 0Ah
0x18001f447  mov     dword ptr [rsp+0E0h+lpBuffer], ebx
0x18001f44b  lea     r8, WPP_d8d3577d84c33b157eb1fb0369fb8d9e_Traceguids
0x18001f452  mov     rcx, [r10+10h]
0x18001f456  call    WPP_SF_Sd
0x18001f45b  jmp     short loc_18001F4D0
0x18001f45d  mov     rax, r15
0x18001f460  neg     rax
0x18001f463  sbb     ecx, ecx
0x18001f465  and     ecx, 0FFFFFE00h
0x18001f46b  add     ecx, 1B00h; dwFlags
0x18001f471  mov     [rsp+0E0h+Arguments], r15; Arguments
0x18001f476  mov     [rsp+0E0h+nSize], 2; nSize
0x18001f47e  lea     rax, [rbp+4Fh+Buffer]
0x18001f482  mov     [rsp+0E0h+lpBuffer], rax; lpBuffer
0x18001f487  xor     r9d, r9d; dwLanguageId
0x18001f48a  mov     r8d, ebx; dwMessageId
0x18001f48d  mov     rdx, rdi; lpSource
0x18001f490  call    cs:__imp_FormatMessageW
0x18001f496  test    eax, eax
0x18001f498  jnz     short loc_18001F4A2
0x18001f49a  call    cs:__imp_GetLastError
0x18001f4a0  jmp     short loc_18001F4D0
0x18001f4a2  mov     rbx, [r14]
0x18001f4a5  xor     ecx, ecx; void *
0x18001f4a7  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001f4ac  mov     rcx, rbx; void *
0x18001f4af  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001f4b4  mov     [rbp+4Fh+var_A0], 0
0x18001f4bc  mov     rdx, qword ptr [rbp+4Fh+Buffer]
0x18001f4c0  lea     rcx, [rbp+4Fh+var_A0]
0x18001f4c4  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x18001f4c9  mov     rax, [rbp+4Fh+var_A0]
0x18001f4cd  mov     [r14], rax
0x18001f4d0  mov     rcx, qword ptr [rbp+4Fh+Buffer]; hMem
0x18001f4d4  call    cs:__imp_LocalFree
0x18001f4da  test    rdi, rdi
0x18001f4dd  jz      short loc_18001F4E9
0x18001f4df  mov     rcx, rdi; hLibModule
0x18001f4e2  call    cs:__imp_FreeLibrary
0x18001f4e8  nop
0x18001f4e9  lea     rcx, [rbp+4Fh+var_70]
0x18001f4ed  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001f4f2  nop
0x18001f4f3  mov     rcx, rsi; void *
0x18001f4f6  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001f4fb  nop
0x18001f4fc  xor     ecx, ecx; void *
0x18001f4fe  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001f503  mov     rcx, [rbp+4Fh+var_40]
0x18001f507  xor     rcx, rsp; StackCookie
0x18001f50a  call    __security_check_cookie
0x18001f50f  add     rsp, 0B0h
0x18001f516  pop     r15
0x18001f518  pop     r14
0x18001f51a  pop     r12
0x18001f51c  pop     rdi
0x18001f51d  pop     rsi
0x18001f51e  pop     rbx
0x18001f51f  pop     rbp
0x18001f520  retn
```
