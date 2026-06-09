# PAL_System_ThreadSignalAlloc(void * *,uint (*)(void *),void *)

- ea: `0x18002b590`
- end: `0x18002b780`
- name: `?PAL_System_ThreadSignalAlloc@@YAJPEAPEAXP6AIPEAX@Z1@Z`
- size: `496`
- prototype: `__int64 __fastcall(void **, unsigned int (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180028f00`

## callees

- `0x18000160c`
- `0x18001f2b8`
- `0x18002a33c`
- `0x18002b590`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b6d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b6d1`

## string_xrefs

- `0x18002b5ec`: `PAL_System_ThreadSignalAlloc`
- `0x18002b666`: `PAL_System_ThreadSignalAlloc`
- `0x18002b702`: `PAL_System_ThreadSignalAlloc`
- `0x18002b605`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommon.cpp`
- `0x18002b67f`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommon.cpp`
- `0x18002b71b`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommon.cpp`
- `0x18002b610`: `Failed to allocated thread signal struct`
- `0x18002b691`: `Failed to create thread signal window`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadSignalAlloc(HWND **a1, unsigned int (*a2)(void *), __int64 a3, __int64 a4)
{
  __int64 v7; // rdx
  HWND *v8; // rbx
  int v9; // edi
  int *v10; // rdx
  const unsigned __int16 **v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  const unsigned __int16 **v16; // [rsp+40h] [rbp-30h]
  const char *v17; // [rsp+50h] [rbp-20h] BYREF
  const char *v18; // [rsp+58h] [rbp-18h] BYREF
  const unsigned __int16 *v19[2]; // [rsp+60h] [rbp-10h] BYREF
  HWND v20; // [rsp+A0h] [rbp+30h] BYREF
  int v21; // [rsp+B8h] [rbp+48h] BYREF

  v20 = 0;
  if ( a1 && a2 )
  {
    v8 = (HWND *)PAL_System_MemAlloc(24);
    if ( v8 )
    {
      v9 = PAL_System_Win32_ThreadCreateWindow(&v20, v7, a3, a4);
      if ( v9 >= 0 )
      {
        v9 = 0;
        *v8 = v20;
        v8[1] = (HWND)a2;
        v8[2] = (HWND)a3;
        *a1 = v8;
      }
      else
      {
        if ( (unsigned int)dword_180044008 > 2 )
        {
          LODWORD(v20) = 111;
          v19[0] = (const unsigned __int16 *)"PAL_System_ThreadSignalAlloc";
          v21 = -2147467259;
          v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\system\\tssystempalwincommon.cpp";
          v17 = "Failed to create thread signal window";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v12,
            (__int64)&byte_18004055F,
            v13,
            v14,
            (const unsigned __int16 **)&v17,
            (__int64)&v21,
            (const unsigned __int16 **)&v18,
            (__int64)&v20,
            v19);
        }
        LocalFree(v8);
      }
    }
    else
    {
      v9 = -2147024882;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v20) = 102;
        v17 = "PAL_System_ThreadSignalAlloc";
        v10 = (int *)byte_1800405E9;
        v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\system\\tssystempalwincommon.cpp";
        v19[0] = (const unsigned __int16 *)"Failed to allocated thread signal struct";
        v16 = (const unsigned __int16 **)&v17;
        v11 = v19;
LABEL_13:
        v21 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (__int64)a1,
          (__int64)v10,
          a3,
          a4,
          v11,
          (__int64)&v21,
          (const unsigned __int16 **)&v18,
          (__int64)&v20,
          v16);
      }
    }
  }
  else
  {
    v9 = -2147024809;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v20) = 91;
      v19[0] = (const unsigned __int16 *)"PAL_System_ThreadSignalAlloc";
      v10 = &dword_1800405A4;
      v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\system\\tssystempalwincommon.cpp";
      v17 = "NULL parameter passed";
      v16 = v19;
      v11 = (const unsigned __int16 **)&v17;
      goto LABEL_13;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002b590  mov     [rsp-28h+arg_8], rbx
0x18002b595  push    rbp
0x18002b596  push    rsi
0x18002b597  push    rdi
0x18002b598  push    r14
0x18002b59a  push    r15
0x18002b59c  mov     rbp, rsp
0x18002b59f  sub     rsp, 70h
0x18002b5a3  mov     [rbp+arg_0], 0
0x18002b5ab  mov     r15, r8
0x18002b5ae  mov     rsi, rdx
0x18002b5b1  mov     r14, rcx
0x18002b5b4  test    rcx, rcx
0x18002b5b7  jz      loc_18002B6F2
0x18002b5bd  test    rdx, rdx
0x18002b5c0  jz      loc_18002B6F2
0x18002b5c6  mov     ecx, 18h
0x18002b5cb  call    PAL_System_MemAlloc
0x18002b5d0  mov     rbx, rax
0x18002b5d3  test    rax, rax
0x18002b5d6  jnz     short loc_18002B648
0x18002b5d8  mov     eax, cs:dword_180044008
0x18002b5de  mov     edi, 8007000Eh
0x18002b5e3  cmp     eax, 2
0x18002b5e6  jbe     loc_18002B76A
0x18002b5ec  lea     rax, aPalSystemThrea_0; "PAL_System_ThreadSignalAlloc"
0x18002b5f3  mov     dword ptr [rbp+arg_0], 66h ; 'f'
0x18002b5fa  mov     [rbp+var_20], rax
0x18002b5fe  lea     rdx, byte_1800405E9
0x18002b605  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002b60c  mov     [rbp+var_18], rax
0x18002b610  lea     rax, aFailedToAlloca_0; "Failed to allocated thread signal struc"...
0x18002b617  mov     [rbp+var_10], rax
0x18002b61b  lea     rax, [rbp+var_20]
0x18002b61f  mov     [rsp+70h+var_30], rax
0x18002b624  lea     rax, [rbp+arg_0]
0x18002b628  mov     [rsp+70h+var_38], rax
0x18002b62d  lea     rax, [rbp+var_18]
0x18002b631  mov     [rsp+70h+var_40], rax
0x18002b636  lea     rax, [rbp+arg_18]
0x18002b63a  mov     [rsp+70h+var_48], rax
0x18002b63f  lea     rax, [rbp+var_10]
0x18002b643  jmp     loc_18002B759
0x18002b648  lea     rcx, [rbp+arg_0]; HWND *
0x18002b64c  call    ?PAL_System_Win32_ThreadCreateWindow@@YAJPEAPEAUHWND__@@@Z; PAL_System_Win32_ThreadCreateWindow(HWND__ * *)
0x18002b651  mov     edi, eax
0x18002b653  test    eax, eax
0x18002b655  jns     loc_18002B6DC
0x18002b65b  mov     eax, cs:dword_180044008
0x18002b661  cmp     eax, 2
0x18002b664  jbe     short loc_18002B6CE
0x18002b666  lea     rax, aPalSystemThrea_0; "PAL_System_ThreadSignalAlloc"
0x18002b66d  mov     dword ptr [rbp+arg_0], 6Fh ; 'o'
0x18002b674  mov     [rbp+var_10], rax
0x18002b678  lea     rdx, byte_18004055F
0x18002b67f  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002b686  mov     [rbp+arg_18], 80004005h
0x18002b68d  mov     [rbp+var_18], rax
0x18002b691  lea     rax, aFailedToCreate_7; "Failed to create thread signal window"
0x18002b698  mov     [rbp+var_20], rax
0x18002b69c  lea     rax, [rbp+var_10]
0x18002b6a0  mov     [rsp+70h+var_30], rax
0x18002b6a5  lea     rax, [rbp+arg_0]
0x18002b6a9  mov     [rsp+70h+var_38], rax
0x18002b6ae  lea     rax, [rbp+var_18]
0x18002b6b2  mov     [rsp+70h+var_40], rax
0x18002b6b7  lea     rax, [rbp+arg_18]
0x18002b6bb  mov     [rsp+70h+var_48], rax
0x18002b6c0  lea     rax, [rbp+var_20]
0x18002b6c4  mov     [rsp+70h+var_50], rax
0x18002b6c9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002b6ce  mov     rcx, rbx; hMem
0x18002b6d1  call    cs:__imp_LocalFree
0x18002b6d7  jmp     loc_18002B76A
0x18002b6dc  mov     rax, [rbp+arg_0]
0x18002b6e0  xor     edi, edi
0x18002b6e2  mov     [rbx], rax
0x18002b6e5  mov     [rbx+8], rsi
0x18002b6e9  mov     [rbx+10h], r15
0x18002b6ed  mov     [r14], rbx
0x18002b6f0  jmp     short loc_18002B76A
0x18002b6f2  mov     eax, cs:dword_180044008
0x18002b6f8  mov     edi, 80070057h
0x18002b6fd  cmp     eax, 2
0x18002b700  jbe     short loc_18002B76A
0x18002b702  lea     rax, aPalSystemThrea_0; "PAL_System_ThreadSignalAlloc"
0x18002b709  mov     dword ptr [rbp+arg_0], 5Bh ; '['
0x18002b710  mov     [rbp+var_10], rax
0x18002b714  lea     rdx, dword_1800405A4
0x18002b71b  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002b722  mov     [rbp+var_18], rax
0x18002b726  lea     rax, aNullParameterP; "NULL parameter passed"
0x18002b72d  mov     [rbp+var_20], rax
0x18002b731  lea     rax, [rbp+var_10]
0x18002b735  mov     [rsp+70h+var_30], rax
0x18002b73a  lea     rax, [rbp+arg_0]
0x18002b73e  mov     [rsp+70h+var_38], rax
0x18002b743  lea     rax, [rbp+var_18]
0x18002b747  mov     [rsp+70h+var_40], rax
0x18002b74c  lea     rax, [rbp+arg_18]
0x18002b750  mov     [rsp+70h+var_48], rax
0x18002b755  lea     rax, [rbp+var_20]
0x18002b759  mov     [rsp+70h+var_50], rax
0x18002b75e  mov     [rbp+arg_18], 80004005h
0x18002b765  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002b76a  mov     rbx, [rsp+70h+arg_8]
0x18002b772  mov     eax, edi
0x18002b774  add     rsp, 70h
0x18002b778  pop     r15
0x18002b77a  pop     r14
0x18002b77c  pop     rdi
0x18002b77d  pop     rsi
0x18002b77e  pop     rbp
0x18002b77f  retn
```
