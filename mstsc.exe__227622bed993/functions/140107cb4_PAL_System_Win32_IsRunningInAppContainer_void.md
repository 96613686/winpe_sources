# PAL_System_Win32_IsRunningInAppContainer(void)

- ea: `0x140107cb4`
- end: `0x140108028`
- name: `?PAL_System_Win32_IsRunningInAppContainer@@YAHXZ`
- size: `884`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14009ffc8`

## callees

- `0x1400019e8`
- `0x140001b00`
- `0x140003b08`
- `0x140003b2c`
- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x140107cb4`
- `0x140112010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x140107cce`
- `KERNEL32!LoadLibraryW` at `0x140107cce`
- `KERNEL32!FreeLibrary` at `0x140108015`
- `KERNEL32!FreeLibrary` at `0x140108015`
- `KERNEL32!GetProcAddress` at `0x140107d4d`
- `KERNEL32!GetProcAddress` at `0x140107d4d`
- `KERNEL32!GetLastError` at `0x140107cfb`
- `KERNEL32!GetLastError` at `0x140107d38`
- `KERNEL32!GetLastError` at `0x140107d7a`
- `KERNEL32!GetLastError` at `0x140107daa`
- `KERNEL32!GetLastError` at `0x140107cfb`
- `KERNEL32!GetLastError` at `0x140107d38`
- `KERNEL32!GetLastError` at `0x140107d7a`
- `KERNEL32!GetLastError` at `0x140107daa`

## string_xrefs

- `0x140107cc4`: `kernel32.dll`
- `0x140107e04`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x140107e97`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x140107f03`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x140107fc3`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x140107e16`: `GetCurrentPackageFamilyName(1st attempt) failed, we are likely loaded in a classic process: 0x%x`

## pseudocode

```c
__int64 PAL_System_Win32_IsRunningInAppContainer(void)
{
  unsigned int v0; // edi
  HMODULE LibraryW; // rax
  HMODULE v2; // rsi
  signed int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v7)(unsigned int *, void *); // rbx
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v10; // eax
  int v11; // r8d
  int v12; // r9d
  unsigned int v13; // ecx
  char *v14; // rdx
  const char *v15; // rax
  void *v16; // rax
  void *v17; // r14
  int v18; // ebx
  unsigned int v19; // eax
  const char *v21; // [rsp+50h] [rbp-20h] BYREF
  const char *v22; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v23[2]; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+A0h] [rbp+30h] BYREF
  int v25; // [rsp+A8h] [rbp+38h] BYREF
  int v26; // [rsp+B0h] [rbp+40h] BYREF
  const char *v27; // [rsp+B8h] [rbp+48h] BYREF

  v0 = 0;
  v24 = 0;
  LibraryW = LoadLibraryW(L"kernel32.dll");
  v2 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "GetCurrentPackageFamilyName");
    v7 = (__int64 (__fastcall *)(unsigned int *, void *))ProcAddress;
    if ( !ProcAddress )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
          CurrentThreadActivityIdPrefix,
          LastError);
      }
      GetLastError();
      goto LABEL_37;
    }
    v10 = ((__int64 (__fastcall *)(unsigned int *, _QWORD))ProcAddress)(&v24, 0);
    v13 = v10;
    if ( v10 )
    {
      if ( v10 != 122 )
      {
        if ( v10 > 0 )
          v13 = (unsigned __int16)v10 | 0x80070000;
        if ( (unsigned int)dword_140150118 > 2 )
        {
          v25 = v13;
          v21 = "PAL_System_Win32_IsRunningInAppContainer";
          v26 = 1634;
          v22 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v23[0] = "GetCurrentPackageFamilyName(1st attempt) failed, we are likely loaded in a classic process: 0x%x";
          LODWORD(v27) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v13,
            (unsigned int)byte_140143C3B,
            v11,
            v12,
            (__int64)v23,
            (__int64)&v27,
            (__int64)&v22,
            (__int64)&v26,
            (__int64)&v21,
            (__int64)&v25);
        }
        goto LABEL_37;
      }
      if ( v24 )
      {
        v16 = operator new(saturated_mul(v24, 2u));
        v17 = v16;
        if ( v16 )
        {
          memset_0(v16, 0, 2LL * v24);
          v18 = v7(&v24, v17);
          if ( v18 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v19 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                33,
                WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
                v19,
                v18);
            }
          }
          else
          {
            v0 = 1;
          }
          operator delete(v17);
          goto LABEL_37;
        }
        if ( (unsigned int)dword_140150118 > 2 )
        {
          v25 = 1657;
          v27 = "PAL_System_Win32_IsRunningInAppContainer";
          v14 = byte_140143CC9;
          v26 = -2147024882;
          v23[0] = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v15 = "Could not allocate space for the package family name";
          goto LABEL_36;
        }
      }
      else if ( (unsigned int)dword_140150118 > 2 )
      {
        v25 = 1647;
        v27 = "PAL_System_Win32_IsRunningInAppContainer";
        v14 = (char *)&word_140143BF6;
        v26 = -2147467259;
        v23[0] = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
        v15 = "Null package family monikor name size.Quitting.";
LABEL_36:
        v22 = v15;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v13,
          (_DWORD)v14,
          v11,
          v12,
          (__int64)&v22,
          (__int64)&v26,
          (__int64)v23,
          (__int64)&v25,
          (__int64)&v27);
      }
    }
    else if ( (unsigned int)dword_140150118 > 2 )
    {
      v25 = 1642;
      v27 = "PAL_System_Win32_IsRunningInAppContainer";
      v14 = byte_140143B65;
      v26 = -2147418113;
      v23[0] = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v15 = "GetCurrentPackageFamilyName returned success, expected INSUFFICIENT_BUFFER";
      goto LABEL_36;
    }
LABEL_37:
    FreeLibrary(v2);
    return v0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_c585fe5194613b5687849eb156704f7c_Traceguids, v5, v4);
  }
  GetLastError();
  return v0;
}

```

## disassembly

```asm
0x140107cb4  push    rbp
0x140107cb6  push    rbx
0x140107cb7  push    rsi
0x140107cb8  push    rdi
0x140107cb9  push    r14
0x140107cbb  mov     rbp, rsp
0x140107cbe  sub     rsp, 70h
0x140107cc2  xor     edi, edi
0x140107cc4  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x140107ccb  mov     [rbp+arg_0], edi
0x140107cce  call    cs:__imp_LoadLibraryW
0x140107cd4  mov     rsi, rax
0x140107cd7  test    rax, rax
0x140107cda  jnz     short loc_140107D43
0x140107cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x140107ce3  lea     rax, WPP_GLOBAL_Control
0x140107cea  cmp     rcx, rax
0x140107ced  jz      short loc_140107D38
0x140107cef  test    byte ptr [rcx+1Ch], 8
0x140107cf3  jz      short loc_140107D38
0x140107cf5  cmp     byte ptr [rcx+19h], 2
0x140107cf9  jb      short loc_140107D38
0x140107cfb  call    cs:__imp_GetLastError
0x140107d01  mov     ebx, eax
0x140107d03  test    eax, eax
0x140107d05  jle     short loc_140107D10
0x140107d07  movzx   ebx, ax
0x140107d0a  or      ebx, 80070000h
0x140107d10  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140107d15  mov     rcx, cs:WPP_GLOBAL_Control
0x140107d1c  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x140107d23  mov     edx, 1Fh
0x140107d28  mov     dword ptr [rsp+70h+var_50], ebx
0x140107d2c  mov     r9d, eax
0x140107d2f  mov     rcx, [rcx+10h]
0x140107d33  call    WPP_SF_Dd
0x140107d38  call    cs:__imp_GetLastError
0x140107d3e  jmp     loc_14010801B
0x140107d43  lea     rdx, aGetcurrentpack_0; "GetCurrentPackageFamilyName"
0x140107d4a  mov     rcx, rsi; hModule
0x140107d4d  call    cs:__imp_GetProcAddress
0x140107d53  mov     rbx, rax
0x140107d56  test    rax, rax
0x140107d59  jnz     short loc_140107DB5
0x140107d5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140107d62  lea     rax, WPP_GLOBAL_Control
0x140107d69  cmp     rcx, rax
0x140107d6c  jz      short loc_140107DAA
0x140107d6e  test    byte ptr [rcx+1Ch], 8
0x140107d72  jz      short loc_140107DAA
0x140107d74  cmp     byte ptr [rcx+19h], 2
0x140107d78  jb      short loc_140107DAA
0x140107d7a  call    cs:__imp_GetLastError
0x140107d80  mov     ebx, eax
0x140107d82  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140107d87  mov     rcx, cs:WPP_GLOBAL_Control
0x140107d8e  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x140107d95  mov     edx, 20h ; ' '
0x140107d9a  mov     dword ptr [rsp+70h+var_50], ebx
0x140107d9e  mov     r9d, eax
0x140107da1  mov     rcx, [rcx+10h]
0x140107da5  call    WPP_SF_Dd
0x140107daa  call    cs:__imp_GetLastError
0x140107db0  jmp     loc_140108012
0x140107db5  xor     edx, edx
0x140107db7  lea     rcx, [rbp+arg_0]
0x140107dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140107dc0  mov     ecx, eax
0x140107dc2  test    eax, eax
0x140107dc4  jz      loc_140107F9F
0x140107dca  cmp     eax, 7Ah ; 'z'
0x140107dcd  jz      loc_140107E68
0x140107dd3  test    eax, eax
0x140107dd5  jle     short loc_140107DE0
0x140107dd7  movzx   ecx, ax
0x140107dda  or      ecx, 80070000h
0x140107de0  mov     eax, cs:dword_140150118
0x140107de6  cmp     eax, 2
0x140107de9  jbe     loc_140108012
0x140107def  lea     rax, aPalSystemWin32_3; "PAL_System_Win32_IsRunningInAppContaine"...
0x140107df6  mov     [rbp+arg_8], ecx
0x140107df9  mov     [rbp+var_20], rax
0x140107dfd  lea     rdx, byte_140143C3B
0x140107e04  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140107e0b  mov     [rbp+arg_10], 662h
0x140107e12  mov     [rbp+var_18], rax
0x140107e16  lea     rax, aGetcurrentpack; "GetCurrentPackageFamilyName(1st attempt"...
0x140107e1d  mov     [rbp+var_10], rax
0x140107e21  lea     rax, [rbp+arg_8]
0x140107e25  mov     [rsp+70h+var_28], rax
0x140107e2a  lea     rax, [rbp+var_20]
0x140107e2e  mov     [rsp+70h+var_30], rax
0x140107e33  lea     rax, [rbp+arg_10]
0x140107e37  mov     [rsp+70h+var_38], rax
0x140107e3c  lea     rax, [rbp+var_18]
0x140107e40  mov     [rsp+70h+var_40], rax
0x140107e45  lea     rax, [rbp+arg_18]
0x140107e49  mov     [rsp+70h+var_48], rax
0x140107e4e  lea     rax, [rbp+var_10]
0x140107e52  mov     [rsp+70h+var_50], rax
0x140107e57  mov     dword ptr [rbp+arg_18], 80004005h
0x140107e5e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140107e63  jmp     loc_140108012
0x140107e68  mov     eax, [rbp+arg_0]
0x140107e6b  test    eax, eax
0x140107e6d  jnz     short loc_140107EB5
0x140107e6f  mov     eax, cs:dword_140150118
0x140107e75  cmp     eax, 2
0x140107e78  jbe     loc_140108012
0x140107e7e  lea     rax, aPalSystemWin32_3; "PAL_System_Win32_IsRunningInAppContaine"...
0x140107e85  mov     [rbp+arg_8], 66Fh
0x140107e8c  mov     [rbp+arg_18], rax
0x140107e90  lea     rdx, word_140143BF6
0x140107e97  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140107e9e  mov     [rbp+arg_10], 80004005h
0x140107ea5  mov     [rbp+var_10], rax
0x140107ea9  lea     rax, aNullPackageFam; "Null package family monikor name size.Q"...
0x140107eb0  jmp     loc_140107FDC
0x140107eb5  mov     rcx, rax
0x140107eb8  mov     eax, 2
0x140107ebd  mul     rcx
0x140107ec0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140107ec7  cmovb   rax, rcx
0x140107ecb  mov     rcx, rax; Size
0x140107ece  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140107ed3  mov     r14, rax
0x140107ed6  test    rax, rax
0x140107ed9  jnz     short loc_140107F21
0x140107edb  mov     eax, cs:dword_140150118
0x140107ee1  cmp     eax, 2
0x140107ee4  jbe     loc_140108012
0x140107eea  lea     rax, aPalSystemWin32_3; "PAL_System_Win32_IsRunningInAppContaine"...
0x140107ef1  mov     [rbp+arg_8], 679h
0x140107ef8  mov     [rbp+arg_18], rax
0x140107efc  lea     rdx, byte_140143CC9
0x140107f03  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140107f0a  mov     [rbp+arg_10], 8007000Eh
0x140107f11  mov     [rbp+var_10], rax
0x140107f15  lea     rax, aCouldNotAlloca_2; "Could not allocate space for the packag"...
0x140107f1c  jmp     loc_140107FDC
0x140107f21  mov     r8d, [rbp+arg_0]
0x140107f25  xor     edx, edx; Val
0x140107f27  add     r8, r8; Size
0x140107f2a  mov     rcx, r14; void *
0x140107f2d  call    memset_0
0x140107f32  mov     rdx, r14
0x140107f35  lea     rcx, [rbp+arg_0]
0x140107f39  mov     rax, rbx
0x140107f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140107f41  mov     ebx, eax
0x140107f43  test    eax, eax
0x140107f45  jz      short loc_140107F90
0x140107f47  mov     rcx, cs:WPP_GLOBAL_Control
0x140107f4e  lea     rax, WPP_GLOBAL_Control
0x140107f55  cmp     rcx, rax
0x140107f58  jz      short loc_140107F95
0x140107f5a  test    byte ptr [rcx+1Ch], 8
0x140107f5e  jz      short loc_140107F95
0x140107f60  cmp     byte ptr [rcx+19h], 2
0x140107f64  jb      short loc_140107F95
0x140107f66  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140107f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140107f72  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x140107f79  mov     edx, 21h ; '!'
0x140107f7e  mov     dword ptr [rsp+70h+var_50], ebx
0x140107f82  mov     r9d, eax
0x140107f85  mov     rcx, [rcx+10h]
0x140107f89  call    WPP_SF_Dd
0x140107f8e  jmp     short loc_140107F95
0x140107f90  mov     edi, 1
0x140107f95  mov     rcx, r14; Block
0x140107f98  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140107f9d  jmp     short loc_140108012
0x140107f9f  mov     eax, cs:dword_140150118
0x140107fa5  cmp     eax, 2
0x140107fa8  jbe     short loc_140108012
0x140107faa  lea     rax, aPalSystemWin32_3; "PAL_System_Win32_IsRunningInAppContaine"...
0x140107fb1  mov     [rbp+arg_8], 66Ah
0x140107fb8  mov     [rbp+arg_18], rax
0x140107fbc  lea     rdx, byte_140143B65
0x140107fc3  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140107fca  mov     [rbp+arg_10], 8000FFFFh
0x140107fd1  mov     [rbp+var_10], rax
0x140107fd5  lea     rax, aGetcurrentpack_1; "GetCurrentPackageFamilyName returned su"...
0x140107fdc  mov     [rbp+var_18], rax
0x140107fe0  lea     rax, [rbp+arg_18]
0x140107fe4  mov     [rsp+70h+var_30], rax
0x140107fe9  lea     rax, [rbp+arg_8]
0x140107fed  mov     [rsp+70h+var_38], rax
0x140107ff2  lea     rax, [rbp+var_10]
0x140107ff6  mov     [rsp+70h+var_40], rax
0x140107ffb  lea     rax, [rbp+arg_10]
0x140107fff  mov     [rsp+70h+var_48], rax
0x140108004  lea     rax, [rbp+var_18]
0x140108008  mov     [rsp+70h+var_50], rax
0x14010800d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140108012  mov     rcx, rsi; hLibModule
0x140108015  call    cs:__imp_FreeLibrary
0x14010801b  mov     eax, edi
0x14010801d  add     rsp, 70h
0x140108021  pop     r14
0x140108023  pop     rdi
0x140108024  pop     rsi
0x140108025  pop     rbx
0x140108026  pop     rbp
0x140108027  retn
```
