# PAL_System_Win32_IsRunningInAppContainer(void)

- ea: `0x140109e24`
- end: `0x14010a198`
- name: `?PAL_System_Win32_IsRunningInAppContainer@@YAHXZ`
- size: `884`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400a2138`

## callees

- `0x1400019e8`
- `0x140001b00`
- `0x140003b08`
- `0x140003b2c`
- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x140109e24`
- `0x140114010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x140109e3e`
- `KERNEL32!LoadLibraryW` at `0x140109e3e`
- `KERNEL32!FreeLibrary` at `0x14010a185`
- `KERNEL32!FreeLibrary` at `0x14010a185`
- `KERNEL32!GetProcAddress` at `0x140109ebd`
- `KERNEL32!GetProcAddress` at `0x140109ebd`
- `KERNEL32!GetLastError` at `0x140109e6b`
- `KERNEL32!GetLastError` at `0x140109ea8`
- `KERNEL32!GetLastError` at `0x140109eea`
- `KERNEL32!GetLastError` at `0x140109f1a`
- `KERNEL32!GetLastError` at `0x140109e6b`
- `KERNEL32!GetLastError` at `0x140109ea8`
- `KERNEL32!GetLastError` at `0x140109eea`
- `KERNEL32!GetLastError` at `0x140109f1a`

## string_xrefs

- `0x140109e34`: `kernel32.dll`
- `0x140109f74`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x14010a007`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x14010a073`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x14010a133`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x140109f86`: `GetCurrentPackageFamilyName(1st attempt) failed, we are likely loaded in a classic process: 0x%x`

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
        if ( (unsigned int)dword_140152118 > 2 )
        {
          v25 = v13;
          v21 = "PAL_System_Win32_IsRunningInAppContainer";
          v26 = 1634;
          v22 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v23[0] = "GetCurrentPackageFamilyName(1st attempt) failed, we are likely loaded in a classic process: 0x%x";
          LODWORD(v27) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v13,
            (unsigned int)byte_140145D73,
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
        if ( (unsigned int)dword_140152118 > 2 )
        {
          v25 = 1657;
          v27 = "PAL_System_Win32_IsRunningInAppContainer";
          v14 = byte_140145E01;
          v26 = -2147024882;
          v23[0] = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v15 = "Could not allocate space for the package family name";
          goto LABEL_36;
        }
      }
      else if ( (unsigned int)dword_140152118 > 2 )
      {
        v25 = 1647;
        v27 = "PAL_System_Win32_IsRunningInAppContainer";
        v14 = (char *)word_140145CE2;
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
    else if ( (unsigned int)dword_140152118 > 2 )
    {
      v25 = 1642;
      v27 = "PAL_System_Win32_IsRunningInAppContainer";
      v14 = byte_140145C9D;
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
0x140109e24  push    rbp
0x140109e26  push    rbx
0x140109e27  push    rsi
0x140109e28  push    rdi
0x140109e29  push    r14
0x140109e2b  mov     rbp, rsp
0x140109e2e  sub     rsp, 70h
0x140109e32  xor     edi, edi
0x140109e34  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x140109e3b  mov     [rbp+arg_0], edi
0x140109e3e  call    cs:__imp_LoadLibraryW
0x140109e44  mov     rsi, rax
0x140109e47  test    rax, rax
0x140109e4a  jnz     short loc_140109EB3
0x140109e4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140109e53  lea     rax, WPP_GLOBAL_Control
0x140109e5a  cmp     rcx, rax
0x140109e5d  jz      short loc_140109EA8
0x140109e5f  test    byte ptr [rcx+1Ch], 8
0x140109e63  jz      short loc_140109EA8
0x140109e65  cmp     byte ptr [rcx+19h], 2
0x140109e69  jb      short loc_140109EA8
0x140109e6b  call    cs:__imp_GetLastError
0x140109e71  mov     ebx, eax
0x140109e73  test    eax, eax
0x140109e75  jle     short loc_140109E80
0x140109e77  movzx   ebx, ax
0x140109e7a  or      ebx, 80070000h
0x140109e80  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140109e85  mov     rcx, cs:WPP_GLOBAL_Control
0x140109e8c  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x140109e93  mov     edx, 1Fh
0x140109e98  mov     dword ptr [rsp+70h+var_50], ebx
0x140109e9c  mov     r9d, eax
0x140109e9f  mov     rcx, [rcx+10h]
0x140109ea3  call    WPP_SF_Dd
0x140109ea8  call    cs:__imp_GetLastError
0x140109eae  jmp     loc_14010A18B
0x140109eb3  lea     rdx, aGetcurrentpack_0; "GetCurrentPackageFamilyName"
0x140109eba  mov     rcx, rsi; hModule
0x140109ebd  call    cs:__imp_GetProcAddress
0x140109ec3  mov     rbx, rax
0x140109ec6  test    rax, rax
0x140109ec9  jnz     short loc_140109F25
0x140109ecb  mov     rcx, cs:WPP_GLOBAL_Control
0x140109ed2  lea     rax, WPP_GLOBAL_Control
0x140109ed9  cmp     rcx, rax
0x140109edc  jz      short loc_140109F1A
0x140109ede  test    byte ptr [rcx+1Ch], 8
0x140109ee2  jz      short loc_140109F1A
0x140109ee4  cmp     byte ptr [rcx+19h], 2
0x140109ee8  jb      short loc_140109F1A
0x140109eea  call    cs:__imp_GetLastError
0x140109ef0  mov     ebx, eax
0x140109ef2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140109ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x140109efe  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x140109f05  mov     edx, 20h ; ' '
0x140109f0a  mov     dword ptr [rsp+70h+var_50], ebx
0x140109f0e  mov     r9d, eax
0x140109f11  mov     rcx, [rcx+10h]
0x140109f15  call    WPP_SF_Dd
0x140109f1a  call    cs:__imp_GetLastError
0x140109f20  jmp     loc_14010A182
0x140109f25  xor     edx, edx
0x140109f27  lea     rcx, [rbp+arg_0]
0x140109f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140109f30  mov     ecx, eax
0x140109f32  test    eax, eax
0x140109f34  jz      loc_14010A10F
0x140109f3a  cmp     eax, 7Ah ; 'z'
0x140109f3d  jz      loc_140109FD8
0x140109f43  test    eax, eax
0x140109f45  jle     short loc_140109F50
0x140109f47  movzx   ecx, ax
0x140109f4a  or      ecx, 80070000h
0x140109f50  mov     eax, cs:dword_140152118
0x140109f56  cmp     eax, 2
0x140109f59  jbe     loc_14010A182
0x140109f5f  lea     rax, aPalSystemWin32_3; "PAL_System_Win32_IsRunningInAppContaine"...
0x140109f66  mov     [rbp+arg_8], ecx
0x140109f69  mov     [rbp+var_20], rax
0x140109f6d  lea     rdx, byte_140145D73
0x140109f74  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140109f7b  mov     [rbp+arg_10], 662h
0x140109f82  mov     [rbp+var_18], rax
0x140109f86  lea     rax, aGetcurrentpack; "GetCurrentPackageFamilyName(1st attempt"...
0x140109f8d  mov     [rbp+var_10], rax
0x140109f91  lea     rax, [rbp+arg_8]
0x140109f95  mov     [rsp+70h+var_28], rax
0x140109f9a  lea     rax, [rbp+var_20]
0x140109f9e  mov     [rsp+70h+var_30], rax
0x140109fa3  lea     rax, [rbp+arg_10]
0x140109fa7  mov     [rsp+70h+var_38], rax
0x140109fac  lea     rax, [rbp+var_18]
0x140109fb0  mov     [rsp+70h+var_40], rax
0x140109fb5  lea     rax, [rbp+arg_18]
0x140109fb9  mov     [rsp+70h+var_48], rax
0x140109fbe  lea     rax, [rbp+var_10]
0x140109fc2  mov     [rsp+70h+var_50], rax
0x140109fc7  mov     dword ptr [rbp+arg_18], 80004005h
0x140109fce  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140109fd3  jmp     loc_14010A182
0x140109fd8  mov     eax, [rbp+arg_0]
0x140109fdb  test    eax, eax
0x140109fdd  jnz     short loc_14010A025
0x140109fdf  mov     eax, cs:dword_140152118
0x140109fe5  cmp     eax, 2
0x140109fe8  jbe     loc_14010A182
0x140109fee  lea     rax, aPalSystemWin32_3; "PAL_System_Win32_IsRunningInAppContaine"...
0x140109ff5  mov     [rbp+arg_8], 66Fh
0x140109ffc  mov     [rbp+arg_18], rax
0x14010a000  lea     rdx, word_140145CE2
0x14010a007  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14010a00e  mov     [rbp+arg_10], 80004005h
0x14010a015  mov     [rbp+var_10], rax
0x14010a019  lea     rax, aNullPackageFam; "Null package family monikor name size.Q"...
0x14010a020  jmp     loc_14010A14C
0x14010a025  mov     rcx, rax
0x14010a028  mov     eax, 2
0x14010a02d  mul     rcx
0x14010a030  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14010a037  cmovb   rax, rcx
0x14010a03b  mov     rcx, rax; Size
0x14010a03e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14010a043  mov     r14, rax
0x14010a046  test    rax, rax
0x14010a049  jnz     short loc_14010A091
0x14010a04b  mov     eax, cs:dword_140152118
0x14010a051  cmp     eax, 2
0x14010a054  jbe     loc_14010A182
0x14010a05a  lea     rax, aPalSystemWin32_3; "PAL_System_Win32_IsRunningInAppContaine"...
0x14010a061  mov     [rbp+arg_8], 679h
0x14010a068  mov     [rbp+arg_18], rax
0x14010a06c  lea     rdx, byte_140145E01
0x14010a073  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14010a07a  mov     [rbp+arg_10], 8007000Eh
0x14010a081  mov     [rbp+var_10], rax
0x14010a085  lea     rax, aCouldNotAlloca_2; "Could not allocate space for the packag"...
0x14010a08c  jmp     loc_14010A14C
0x14010a091  mov     r8d, [rbp+arg_0]
0x14010a095  xor     edx, edx; Val
0x14010a097  add     r8, r8; Size
0x14010a09a  mov     rcx, r14; void *
0x14010a09d  call    memset_0
0x14010a0a2  mov     rdx, r14
0x14010a0a5  lea     rcx, [rbp+arg_0]
0x14010a0a9  mov     rax, rbx
0x14010a0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010a0b1  mov     ebx, eax
0x14010a0b3  test    eax, eax
0x14010a0b5  jz      short loc_14010A100
0x14010a0b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a0be  lea     rax, WPP_GLOBAL_Control
0x14010a0c5  cmp     rcx, rax
0x14010a0c8  jz      short loc_14010A105
0x14010a0ca  test    byte ptr [rcx+1Ch], 8
0x14010a0ce  jz      short loc_14010A105
0x14010a0d0  cmp     byte ptr [rcx+19h], 2
0x14010a0d4  jb      short loc_14010A105
0x14010a0d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14010a0db  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a0e2  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x14010a0e9  mov     edx, 21h ; '!'
0x14010a0ee  mov     dword ptr [rsp+70h+var_50], ebx
0x14010a0f2  mov     r9d, eax
0x14010a0f5  mov     rcx, [rcx+10h]
0x14010a0f9  call    WPP_SF_Dd
0x14010a0fe  jmp     short loc_14010A105
0x14010a100  mov     edi, 1
0x14010a105  mov     rcx, r14; Block
0x14010a108  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14010a10d  jmp     short loc_14010A182
0x14010a10f  mov     eax, cs:dword_140152118
0x14010a115  cmp     eax, 2
0x14010a118  jbe     short loc_14010A182
0x14010a11a  lea     rax, aPalSystemWin32_3; "PAL_System_Win32_IsRunningInAppContaine"...
0x14010a121  mov     [rbp+arg_8], 66Ah
0x14010a128  mov     [rbp+arg_18], rax
0x14010a12c  lea     rdx, byte_140145C9D
0x14010a133  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14010a13a  mov     [rbp+arg_10], 8000FFFFh
0x14010a141  mov     [rbp+var_10], rax
0x14010a145  lea     rax, aGetcurrentpack_1; "GetCurrentPackageFamilyName returned su"...
0x14010a14c  mov     [rbp+var_18], rax
0x14010a150  lea     rax, [rbp+arg_18]
0x14010a154  mov     [rsp+70h+var_30], rax
0x14010a159  lea     rax, [rbp+arg_8]
0x14010a15d  mov     [rsp+70h+var_38], rax
0x14010a162  lea     rax, [rbp+var_10]
0x14010a166  mov     [rsp+70h+var_40], rax
0x14010a16b  lea     rax, [rbp+arg_10]
0x14010a16f  mov     [rsp+70h+var_48], rax
0x14010a174  lea     rax, [rbp+var_18]
0x14010a178  mov     [rsp+70h+var_50], rax
0x14010a17d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14010a182  mov     rcx, rsi; hLibModule
0x14010a185  call    cs:__imp_FreeLibrary
0x14010a18b  mov     eax, edi
0x14010a18d  add     rsp, 70h
0x14010a191  pop     r14
0x14010a193  pop     rdi
0x14010a194  pop     rsi
0x14010a195  pop     rbx
0x14010a196  pop     rbp
0x14010a197  retn
```
