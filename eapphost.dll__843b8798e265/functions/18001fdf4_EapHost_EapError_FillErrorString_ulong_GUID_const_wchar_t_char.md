# EapHost::EapError::FillErrorString(ulong,_GUID const *,wchar_t * &,char * *)

- ea: `0x18001fdf4`
- end: `0x180020086`
- name: `?FillErrorString@EapError@EapHost@@AEBAXKPEBU_GUID@@AEAPEA_WPEAPEAD@Z`
- size: `658`
- prototype: `void(EapHost::EapError *__hidden this, unsigned int, const struct _GUID *, wchar_t **, char **)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001b964`
- `0x18001fa44`

## callees

- `0x180002af0`
- `0x180005410`
- `0x1800056cc`
- `0x180007564`
- `0x180009c40`
- `0x18001204c`
- `0x18001206c`
- `0x180019eb0`
- `0x18001a140`
- `0x18001f514`
- `0x18001f59c`
- `0x18001fdf4`
- `0x18002062c`
- `0x180020984`
- `0x180030ca8`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001ffdc`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001ffdc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020040`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffec`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001ff21`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001ff21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002002c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002002c`

## string_xrefs

- `0x18001fe44`: `eapphost.dll`
- `0x18001feba`: `mprmsg.dll`

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
0x18001fdf4  push    rbp
0x18001fdf6  push    rbx
0x18001fdf7  push    rsi
0x18001fdf8  push    rdi
0x18001fdf9  push    r12
0x18001fdfb  push    r14
0x18001fdfd  push    r15
0x18001fdff  lea     rbp, [rsp-1Fh]
0x18001fe04  sub     rsp, 0B0h
0x18001fe0b  mov     rax, cs:__security_cookie
0x18001fe12  xor     rax, rsp
0x18001fe15  mov     [rbp+4Fh+var_40], rax
0x18001fe19  mov     r14, r9
0x18001fe1c  mov     rdi, r8
0x18001fe1f  mov     ebx, edx
0x18001fe21  mov     r12, rcx
0x18001fe24  mov     r15, [rbp+4Fh+arg_20]
0x18001fe28  movups  xmm0, xmmword ptr cs:GUID_EapHost_Cause_Generic_AuthFailure.Data1
0x18001fe2f  movdqu  [rbp+4Fh+var_50], xmm0
0x18001fe34  mov     qword ptr [rbp+4Fh+Buffer], 0
0x18001fe3c  mov     [rbp+4Fh+var_A0], 0
0x18001fe44  lea     rcx, aEapphostDll_0; "eapphost.dll"
0x18001fe4b  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18001fe50  mov     rsi, rax
0x18001fe53  mov     [rbp+4Fh+var_90], rax
0x18001fe57  test    ebx, ebx
0x18001fe59  jnz     short loc_18001FECE
0x18001fe5b  lea     rbx, [rbp+4Fh+var_50]
0x18001fe5f  test    rdi, rdi
0x18001fe62  cmovnz  rbx, rdi
0x18001fe66  call    ?GetGuidToMsgIdTable@EapError@EapHost@@CAAEBVTableGuidToDword@2@XZ; EapHost::EapError::GetGuidToMsgIdTable(void)
0x18001fe6b  call    ?GetGuidToMsgIdTable@EapError@EapHost@@CAAEBVTableGuidToDword@2@XZ; EapHost::EapError::GetGuidToMsgIdTable(void)
0x18001fe70  mov     rdi, rax
0x18001fe73  mov     r8, rbx
0x18001fe76  lea     rdx, [rbp+4Fh+var_88]
0x18001fe7a  mov     rcx, rax
0x18001fe7d  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@KU?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ulong,std::less<_GUID>,std::allocator<std::pair<_GUID const,ulong>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x18001fe82  mov     r8, rbx
0x18001fe85  mov     rbx, [rbp+4Fh+var_78]
0x18001fe89  mov     rdx, rbx
0x18001fe8c  call    ??$_Lower_bound_duplicate@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@KU?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@3@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ulong,std::less<_GUID>,std::allocator<std::pair<_GUID const,ulong>>,0>>::_Lower_bound_duplicate<_GUID>(std::_Tree_node<std::pair<_GUID const,ulong>,void *> * const,_GUID const &)
0x18001fe91  test    al, al
0x18001fe93  jnz     short loc_18001FE98
0x18001fe95  mov     rbx, [rdi]
0x18001fe98  call    ?GetGuidToMsgIdTable@EapError@EapHost@@CAAEBVTableGuidToDword@2@XZ; EapHost::EapError::GetGuidToMsgIdTable(void)
0x18001fe9d  cmp     rbx, [rax]
0x18001fea0  jz      short loc_18001FEA9
0x18001fea2  mov     ebx, [rbx+2Ch]
0x18001fea5  test    ebx, ebx
0x18001fea7  jnz     short loc_18001FECE
0x18001fea9  mov     ebx, [r12]
0x18001fead  lea     eax, [rbx-258h]
0x18001feb3  cmp     eax, 116h
0x18001feb8  ja      short loc_18001FECE
0x18001feba  lea     rdx, aMprmsgDll; "mprmsg.dll"
0x18001fec1  lea     rcx, [rbp+4Fh+var_90]
0x18001fec5  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x18001feca  mov     rsi, [rbp+4Fh+var_90]
0x18001fece  lea     rcx, [rbp+4Fh+var_70]
0x18001fed2  call    ?GetWindowsSystemDirectory@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@XZ; GetWindowsSystemDirectory(void)
0x18001fed7  nop
0x18001fed8  lea     rcx, asc_18003CB1C; "\\"
0x18001fedf  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18001fee4  mov     r8, rax
0x18001fee7  mov     rdx, rcx
0x18001feea  lea     rcx, [rbp+4Fh+var_70]
0x18001feee  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001fef3  lea     rcx, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x18001fefa  test    rsi, rsi
0x18001fefd  cmovnz  rcx, rsi
0x18001ff01  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18001ff06  mov     r8, rax
0x18001ff09  mov     rdx, rcx
0x18001ff0c  lea     rcx, [rbp+4Fh+var_70]
0x18001ff10  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001ff15  lea     rcx, [rbp+4Fh+var_70]
0x18001ff19  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ff1e  mov     rcx, rax; lpLibFileName
0x18001ff21  call    cs:__imp_LoadLibraryW
0x18001ff28  nop     dword ptr [rax+rax+00h]
0x18001ff2d  mov     rdi, rax
0x18001ff30  test    rax, rax
0x18001ff33  jnz     short loc_18001FFA9
0x18001ff35  call    cs:__imp_GetLastError
0x18001ff3c  nop     dword ptr [rax+rax+00h]
0x18001ff41  mov     ebx, eax
0x18001ff43  test    cs:Microsoft_Windows_EapHostEnableBits, 1
0x18001ff4a  jz      short loc_18001FF60
0x18001ff4c  lea     rcx, [rbp+4Fh+var_70]
0x18001ff50  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ff55  mov     r8, rax
0x18001ff58  mov     r9d, ebx
0x18001ff5b  call    McTemplateU0zq_EtwEventWriteTransfer
0x18001ff60  lea     rax, WPP_GLOBAL_Control
0x18001ff67  mov     r10, cs:WPP_GLOBAL_Control
0x18001ff6e  cmp     r10, rax
0x18001ff71  jz      loc_180020028
0x18001ff77  test    byte ptr [r10+1Ch], 1
0x18001ff7c  jz      loc_180020028
0x18001ff82  lea     rcx, [rbp+4Fh+var_70]
0x18001ff86  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ff8b  mov     r9, rax
0x18001ff8e  mov     edx, 0Ah
0x18001ff93  mov     dword ptr [rsp+0E0h+lpBuffer], ebx
0x18001ff97  lea     r8, WPP_d8d3577d84c33b157eb1fb0369fb8d9e_Traceguids
0x18001ff9e  mov     rcx, [r10+10h]
0x18001ffa2  call    WPP_SF_Sd
0x18001ffa7  jmp     short loc_180020028
0x18001ffa9  mov     rax, r15
0x18001ffac  neg     rax
0x18001ffaf  sbb     ecx, ecx
0x18001ffb1  and     ecx, 0FFFFFE00h
0x18001ffb7  add     ecx, 1B00h; dwFlags
0x18001ffbd  mov     [rsp+0E0h+Arguments], r15; Arguments
0x18001ffc2  mov     [rsp+0E0h+nSize], 2; nSize
0x18001ffca  lea     rax, [rbp+4Fh+Buffer]
0x18001ffce  mov     [rsp+0E0h+lpBuffer], rax; lpBuffer
0x18001ffd3  xor     r9d, r9d; dwLanguageId
0x18001ffd6  mov     r8d, ebx; dwMessageId
0x18001ffd9  mov     rdx, rdi; lpSource
0x18001ffdc  call    cs:__imp_FormatMessageW
0x18001ffe3  nop     dword ptr [rax+rax+00h]
0x18001ffe8  test    eax, eax
0x18001ffea  jnz     short loc_18001FFFA
0x18001ffec  call    cs:__imp_GetLastError
0x18001fff3  nop     dword ptr [rax+rax+00h]
0x18001fff8  jmp     short loc_180020028
0x18001fffa  mov     rbx, [r14]
0x18001fffd  xor     ecx, ecx; void *
0x18001ffff  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180020004  mov     rcx, rbx; void *
0x180020007  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002000c  mov     [rbp+4Fh+var_A0], 0
0x180020014  mov     rdx, qword ptr [rbp+4Fh+Buffer]
0x180020018  lea     rcx, [rbp+4Fh+var_A0]
0x18002001c  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180020021  mov     rax, [rbp+4Fh+var_A0]
0x180020025  mov     [r14], rax
0x180020028  mov     rcx, qword ptr [rbp+4Fh+Buffer]; hMem
0x18002002c  call    cs:__imp_LocalFree
0x180020033  nop     dword ptr [rax+rax+00h]
0x180020038  test    rdi, rdi
0x18002003b  jz      short loc_18002004D
0x18002003d  mov     rcx, rdi; hLibModule
0x180020040  call    cs:__imp_FreeLibrary
0x180020047  nop     dword ptr [rax+rax+00h]
0x18002004c  nop
0x18002004d  lea     rcx, [rbp+4Fh+var_70]
0x180020051  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180020056  nop
0x180020057  mov     rcx, rsi; void *
0x18002005a  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002005f  nop
0x180020060  xor     ecx, ecx; void *
0x180020062  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180020067  mov     rcx, [rbp+4Fh+var_40]
0x18002006b  xor     rcx, rsp; StackCookie
0x18002006e  call    __security_check_cookie
0x180020073  add     rsp, 0B0h
0x18002007a  pop     r15
0x18002007c  pop     r14
0x18002007e  pop     r12
0x180020080  pop     rdi
0x180020081  pop     rsi
0x180020082  pop     rbx
0x180020083  pop     rbp
0x180020084  retn
```
