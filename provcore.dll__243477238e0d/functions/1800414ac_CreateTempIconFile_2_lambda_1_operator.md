# _CreateTempIconFile_::_2_::_lambda_1_::operator()

- ea: `0x1800414ac`
- end: `0x1800416ce`
- name: `_CreateTempIconFile_::_2_::_lambda_1_::operator()`
- size: `546`
- prototype: `HRESULT __fastcall(__int64, __int64, std::wstring::reserve::__l2::<lambda_1>)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180041050`

## callees

- `0x180002790`
- `0x18000866c`
- `0x180011844`
- `0x180012400`
- `0x1800127cc`
- `0x180012bc8`
- `0x18003bc1c`
- `0x18003cde4`
- `0x180041258`
- `0x1800414ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041698`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800415e0`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180041500`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18004153a`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180041500`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18004153a`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18004157c`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18004157c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180041618`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180041618`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800415d0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800415d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall CreateTempIconFile_::_2_::_lambda_1_::operator()(
        __int64 a1,
        __int64 a2,
        std::wstring::reserve::__l2::<lambda_1> a3)
{
  std::wstring *v4; // rdi
  unsigned __int64 Mysize; // rbx
  unsigned int TempPath2W; // ebx
  const std::allocator<unsigned short> *v7; // r8
  char v8; // di
  unsigned int v9; // eax
  const std::allocator<unsigned short> *v10; // r8
  unsigned __int64 v11; // rax
  const wchar_t *v12; // rcx
  const WCHAR *v13; // rax
  WWAN_INTERFACE_OBJECT *FileW; // rax
  const wchar_t *v15; // rax
  __int64 v16; // r10
  HRESULT result; // eax
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+40h] [rbp-19h] BYREF
  unsigned int bytesWritten; // [rsp+58h] [rbp-1h] BYREF
  std::vector<unsigned short> tempPath; // [rsp+60h] [rbp+7h] BYREF
  std::vector<unsigned short> tempFileName; // [rsp+78h] [rbp+1Fh] BYREF

  v4 = *(std::wstring **)a1;
  if ( *(_QWORD *)(*(_QWORD *)a1 + 24LL) < 0x104u )
  {
    Mysize = v4->_Mypair._Myval2._Mysize;
    ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAX_K_Z___V___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(
      *(std::wstring **)a1,
      260 - Mysize,
      a3);
    v4->_Mypair._Myval2._Mysize = Mysize;
  }
  TempPath2W = GetTempPath2W(0, 0);
  if ( TempPath2W )
  {
    v8 = 0;
    memset(&tempPath, 0, sizeof(tempPath));
    std::vector<unsigned short>::vector<unsigned short>(&tempPath, TempPath2W, v7);
    v9 = GetTempPath2W(
           tempPath._Mypair._Myval2._Mylast - tempPath._Mypair._Myval2._Myfirst,
           tempPath._Mypair._Myval2._Myfirst);
    if ( v9 && v9 <= TempPath2W )
    {
      memset(&tempFileName, 0, sizeof(tempFileName));
      std::vector<unsigned short>::vector<unsigned short>(&tempFileName, 0x104u, v10);
      if ( GetTempFileNameW(tempPath._Mypair._Myval2._Myfirst, L"MBN", 0, tempFileName._Mypair._Myval2._Myfirst) )
      {
        v11 = std::_WChar_traits<unsigned short>::length(tempFileName._Mypair._Myval2._Myfirst);
        std::wstring::_Assign<unsigned short>(*(std::wstring **)a1, v12, v11);
        v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*(std::_String_val<std::_Simple_types<unsigned short> > **)a1);
        FileW = (WWAN_INTERFACE_OBJECT *)CreateFileW(v13, 0x40000000u, 2u, 0, 2u, 0, 0);
        if ( FileW != (WWAN_INTERFACE_OBJECT *)-1LL )
        {
          j.dismissed_ = 0;
          j.fun_ = (void (__fastcall *)(void *))CloseHandle;
          j.p1_ = FileW;
          bytesWritten = 0;
          if ( WriteFile(
                 FileW,
                 **(LPCVOID **)(a1 + 8),
                 *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8LL) - **(_DWORD **)(a1 + 8),
                 &bytesWritten,
                 0) )
          {
            if ( bytesWritten == *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) - **(_QWORD **)(a1 + 8) )
            {
              v8 = 1;
              if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
              {
                v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*(std::_String_val<std::_Simple_types<unsigned short> > **)a1);
                WPP_SF_S(*(_QWORD *)(v16 + 16), 0x1Fu, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids, v15);
              }
            }
          }
          ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
        }
      }
      std::vector<unsigned short>::_Tidy(&tempFileName);
    }
    std::vector<unsigned short>::_Tidy(&tempPath);
    if ( v8 )
      return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800414ac  mov     [rsp-8+arg_8], rbx
0x1800414b1  mov     [rsp-8+arg_10], rsi
0x1800414b6  push    rbp
0x1800414b7  push    rdi
0x1800414b8  push    r15
0x1800414ba  lea     rbp, [rsp-47h]
0x1800414bf  sub     rsp, 0A0h
0x1800414c6  mov     rax, cs:__security_cookie
0x1800414cd  xor     rax, rsp
0x1800414d0  mov     [rbp+57h+var_20], rax
0x1800414d4  mov     rsi, this
0x1800414d7  mov     rdi, [this]
0x1800414da  mov     r15d, 104h
0x1800414e0  cmp     [rdi+18h], r15
0x1800414e4  jnb     short loc_1800414FC
0x1800414e6  mov     rbx, [rdi+10h]
0x1800414ea  mov     edx, r15d
0x1800414ed  sub     rdx, rbx; _Size_increase
0x1800414f0  mov     this, rdi; this
0x1800414f3  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x1800414f8  mov     [rdi+10h], rbx
0x1800414fc  xor     edx, edx
0x1800414fe  xor     ecx, ecx
0x180041500  call    cs:__imp_GetTempPath2W
0x180041506  mov     ebx, eax
0x180041508  test    eax, eax
0x18004150a  jz      loc_180041698
0x180041510  xor     dil, dil
0x180041513  xorps   xmm0, xmm0
0x180041516  xor     eax, eax
0x180041518  movups  xmmword ptr [rbp+57h+tempPath._Mypair._Myval2._Myfirst], xmm0
0x18004151c  mov     [rbp+57h+tempPath._Mypair._Myval2._Myend], rax
0x180041520  mov     edx, ebx; _Count
0x180041522  lea     this, [rbp+57h+tempPath]; this
0x180041526  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18004152b  nop
0x18004152c  mov     rdx, [rbp+57h+tempPath._Mypair._Myval2._Myfirst]
0x180041530  mov     this, [rbp+57h+tempPath._Mypair._Myval2._Mylast]
0x180041534  sub     this, rdx
0x180041537  sar     this, 1
0x18004153a  call    cs:__imp_GetTempPath2W
0x180041540  test    eax, eax
0x180041542  jz      loc_180041686
0x180041548  cmp     eax, ebx
0x18004154a  ja      loc_180041686
0x180041550  xorps   xmm0, xmm0
0x180041553  xor     eax, eax
0x180041555  movups  xmmword ptr [rbp+57h+tempFileName._Mypair._Myval2._Myfirst], xmm0
0x180041559  mov     [rbp+57h+tempFileName._Mypair._Myval2._Myend], rax
0x18004155d  mov     rdx, r15; _Count
0x180041560  lea     this, [rbp+57h+tempFileName]; this
0x180041564  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180041569  nop
0x18004156a  mov     r9, [rbp+57h+tempFileName._Mypair._Myval2._Myfirst]; lpTempFileName
0x18004156e  xor     r8d, r8d; uUnique
0x180041571  lea     rdx, PrefixString; "MBN"
0x180041578  mov     this, [rbp+57h+tempPath._Mypair._Myval2._Myfirst]; lpPathName
0x18004157c  call    cs:__imp_GetTempFileNameW
0x180041582  test    eax, eax
0x180041584  jz      loc_18004167C
0x18004158a  mov     this, [rbp+57h+tempFileName._Mypair._Myval2._Myfirst]; _First
0x18004158e  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180041593  mov     r8, rax; _Count
0x180041596  mov     rdx, this; _Ptr
0x180041599  mov     this, [rsi]; this
0x18004159c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800415a1  mov     this, [rsi]; this
0x1800415a4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800415a9  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x1800415b2  mov     [rsp+0B0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800415ba  mov     r8d, 2; dwShareMode
0x1800415c0  mov     [rsp+0B0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800415c5  xor     r9d, r9d; lpSecurityAttributes
0x1800415c8  mov     edx, 40000000h; dwDesiredAccess
0x1800415cd  mov     this, rax; lpFileName
0x1800415d0  call    cs:__imp_CreateFileW
0x1800415d6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800415da  jz      loc_18004167C
0x1800415e0  mov     this, cs:__imp_CloseHandle
0x1800415e7  mov     [rbp+57h+j.dismissed_], dil
0x1800415eb  mov     [rbp+57h+j.fun_], this
0x1800415ef  mov     [rbp+57h+j.p1_], rax
0x1800415f3  mov     [rbp+57h+bytesWritten], 0
0x1800415fa  mov     this, [rsi+8]
0x1800415fe  mov     r8d, [this+8]
0x180041602  sub     r8d, [this]; nNumberOfBytesToWrite
0x180041605  mov     qword ptr [rsp+0B0h+dwCreationDisposition], 0; lpOverlapped
0x18004160e  lea     r9, [rbp+57h+bytesWritten]; lpNumberOfBytesWritten
0x180041612  mov     rdx, [this]; lpBuffer
0x180041615  mov     this, rax; hFile
0x180041618  call    cs:__imp_WriteFile
0x18004161e  test    eax, eax
0x180041620  jz      short loc_180041672
0x180041622  mov     rax, [rsi+8]
0x180041626  mov     this, [rax+8]
0x18004162a  sub     this, [rax]
0x18004162d  mov     eax, [rbp+57h+bytesWritten]
0x180041630  cmp     rax, this
0x180041633  jnz     short loc_180041672
0x180041635  mov     dil, 1
0x180041638  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x18004163f  mov     r10, cs:WPP_GLOBAL_Control
0x180041646  cmp     r10, rax
0x180041649  jz      short loc_180041672
0x18004164b  test    byte ptr [r10+1Ch], 8
0x180041650  jz      short loc_180041672
0x180041652  mov     this, [rsi]; this
0x180041655  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004165a  mov     edx, 1Fh; id
0x18004165f  mov     r9, rax; _a1
0x180041662  lea     r8, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x180041669  mov     this, [r10+10h]; Logger
0x18004166d  call    WPP_SF_S
0x180041672  lea     this, [rbp+57h+j]; j
0x180041676  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x18004167b  nop
0x18004167c  lea     this, [rbp+57h+tempFileName]; this
0x180041680  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180041685  nop
0x180041686  lea     this, [rbp+57h+tempPath]; this
0x18004168a  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004168f  test    dil, dil
0x180041692  jz      short loc_180041698
0x180041694  xor     eax, eax
0x180041696  jmp     short loc_1800416AA
0x180041698  call    cs:__imp_GetLastError
0x18004169e  test    eax, eax
0x1800416a0  jle     short loc_1800416AA
0x1800416a2  movzx   eax, ax
0x1800416a5  or      eax, 80070000h
0x1800416aa  mov     this, [rbp+57h+var_20]
0x1800416ae  xor     this, rsp; StackCookie
0x1800416b1  call    __security_check_cookie
0x1800416b6  lea     r11, [rsp+0B0h+var_10]
0x1800416be  mov     rbx, [r11+28h]
0x1800416c2  mov     rsi, [r11+30h]
0x1800416c6  mov     rsp, r11
0x1800416c9  pop     r15
0x1800416cb  pop     rdi
0x1800416cc  pop     rbp
0x1800416cd  retn
```
