# CRuntimePlugin::AskModuleToClaimCrash(wchar_t const *,void *,ulong *,long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,ulong,wchar_t *,ulong *,wchar_t *,ulong *),long (**)(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,int *,wchar_t *,ulong *,int *),tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *)

- ea: `0x18002d92c`
- end: `0x18002dcad`
- name: `?AskModuleToClaimCrash@CRuntimePlugin@@AEAAJPEB_WPEAXPEAKPEAP6AJ1QEAU_WER_RUNTIME_EXCEPTION_INFORMATION@@KPEA_W242@ZPEAP6AJ13PEAH426@ZPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@@Z`
- size: `897`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002dcdc`

## callees

- `0x180002890`
- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x180016a6c`
- `0x18002d92c`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002da5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002db6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dbfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002da5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002db6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dbfe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d9d8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002dc4a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d9d8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002dc4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d9e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d9e3`
- `ntdll!RtlSetThreadErrorMode` at `0x18002d9be`
- `ntdll!RtlSetThreadErrorMode` at `0x18002da08`
- `ntdll!RtlSetThreadErrorMode` at `0x18002d9be`
- `ntdll!RtlSetThreadErrorMode` at `0x18002da08`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002d9c7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002d9c7`

## pseudocode

```c
__int64 __fastcall CRuntimePlugin::AskModuleToClaimCrash(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        FARPROC *a5,
        FARPROC *a6,
        HMODULE *a7)
{
  signed int v7; // ebx
  HMODULE LibraryW; // rax
  HMODULE v13; // rcx
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  FARPROC v21; // rax
  __int64 v22; // r8
  FARPROC v23; // rax
  HMODULE v24; // rcx
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  ULONG OldMode; // [rsp+44h] [rbp-BCh] BYREF
  int v28; // [rsp+48h] [rbp-B8h] BYREF
  FARPROC *v29; // [rsp+50h] [rbp-B0h]
  _WORD v30[264]; // [rsp+60h] [rbp-A0h] BYREF

  v7 = 0;
  v29 = a6;
  OldMode = 0;
  v26 = 0;
  v28 = 0;
  if ( a4 && a7 && a5 && a2 )
  {
    v30[0] = 0;
    RtlSetThreadErrorMode(0x10u, &OldMode);
    LibraryW = LoadLibraryW(a2);
    v13 = *a7;
    *a7 = LibraryW;
    if ( v13 )
      FreeLibrary(v13);
    if ( !*a7 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147467259;
    }
    RtlSetThreadErrorMode(OldMode, 0);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
          (unsigned int)v7);
      goto LABEL_48;
    }
    ProcAddress = GetProcAddress(*a7, "OutOfProcessExceptionEventCallback");
    if ( !ProcAddress )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_21;
      v17 = 38;
LABEL_20:
      WPP_SF_(v16[2], v17, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
LABEL_21:
      v7 = -2147467259;
      goto LABEL_48;
    }
    v28 = 260;
    v7 = ((__int64 (__fastcall *)(__int64, __int64, int *, _WORD *, int *, __int64))ProcAddress)(
           a3,
           a1 + 848,
           &v26,
           v30,
           &v28,
           a4);
    if ( v7 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 39;
LABEL_42:
        WPP_SF_(v18[2], v19, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
        goto LABEL_48;
      }
      goto LABEL_48;
    }
    v20 = v26;
    v7 = 0;
    if ( v26 )
    {
      if ( *(_DWORD *)(a1 + 2808) )
      {
        v26 = 0;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_47;
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          (unsigned int)&WPP_f577d8521c9b39ef05153804ed8add08_Traceguids,
          (_DWORD)a2,
          (__int64)v30);
        v20 = v26;
      }
      if ( v20 )
      {
        v21 = GetProcAddress(*a7, "OutOfProcessExceptionEventSignatureCallback");
        *a5 = v21;
        if ( !v21 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_21;
          v17 = 41;
          goto LABEL_20;
        }
        v22 = -1;
        do
          ++v22;
        while ( v30[v22] );
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                a1 + 728,
                                v30) )
        {
          v23 = GetProcAddress(*a7, "OutOfProcessExceptionEventDebuggerLaunchCallback");
          *v29 = v23;
          if ( !v23
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
          }
          return (unsigned int)v7;
        }
        v7 = -2147024882;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 42;
          goto LABEL_42;
        }
LABEL_48:
        v24 = *a7;
        *a7 = 0;
        if ( v24 )
          FreeLibrary(v24);
        *a5 = 0;
        return (unsigned int)v7;
      }
    }
LABEL_47:
    v7 = -2147467263;
    goto LABEL_48;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_f577d8521c9b39ef05153804ed8add08_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18002d92c  push    rbp
0x18002d92e  push    rbx
0x18002d92f  push    rsi
0x18002d930  push    rdi
0x18002d931  push    r12
0x18002d933  push    r13
0x18002d935  push    r14
0x18002d937  push    r15
0x18002d939  lea     rbp, [rsp-188h]
0x18002d941  sub     rsp, 288h
0x18002d948  mov     rax, cs:__security_cookie
0x18002d94f  xor     rax, rsp
0x18002d952  mov     [rbp+1C0h+var_50], rax
0x18002d959  mov     rax, [rbp+1C0h+arg_28]
0x18002d960  xor     ebx, ebx
0x18002d962  mov     rsi, [rbp+1C0h+arg_30]
0x18002d969  mov     rdi, r9
0x18002d96c  mov     r15, [rbp+1C0h+arg_20]
0x18002d973  mov     r12, r8
0x18002d976  mov     [rsp+2C0h+var_270], rax
0x18002d97b  mov     r14, rdx
0x18002d97e  mov     [rsp+2C0h+OldMode], ebx
0x18002d982  mov     r13, rcx
0x18002d985  mov     [rsp+2C0h+var_280], ebx
0x18002d989  mov     [rsp+2C0h+var_278], ebx
0x18002d98d  test    r9, r9
0x18002d990  jz      loc_18002DC57
0x18002d996  test    rsi, rsi
0x18002d999  jz      loc_18002DC57
0x18002d99f  test    r15, r15
0x18002d9a2  jz      loc_18002DC57
0x18002d9a8  test    rdx, rdx
0x18002d9ab  jz      loc_18002DC57
0x18002d9b1  lea     rdx, [rsp+2C0h+OldMode]; OldMode
0x18002d9b6  mov     [rsp+2C0h+var_260], bx
0x18002d9bb  lea     ecx, [rbx+10h]; NewMode
0x18002d9be  call    cs:__imp_RtlSetThreadErrorMode
0x18002d9c4  mov     rcx, r14; lpLibFileName
0x18002d9c7  call    cs:__imp_LoadLibraryW
0x18002d9cd  mov     rcx, [rsi]; hLibModule
0x18002d9d0  mov     [rsi], rax
0x18002d9d3  test    rcx, rcx
0x18002d9d6  jz      short loc_18002D9DE
0x18002d9d8  call    cs:__imp_FreeLibrary
0x18002d9de  cmp     [rsi], rbx
0x18002d9e1  jnz     short loc_18002DA02
0x18002d9e3  call    cs:__imp_GetLastError
0x18002d9e9  mov     ebx, eax
0x18002d9eb  test    eax, eax
0x18002d9ed  jle     short loc_18002D9F8
0x18002d9ef  movzx   ebx, ax
0x18002d9f2  or      ebx, 80070000h
0x18002d9f8  test    ebx, ebx
0x18002d9fa  mov     eax, 80004005h
0x18002d9ff  cmovns  ebx, eax
0x18002da02  mov     ecx, [rsp+2C0h+OldMode]; NewMode
0x18002da06  xor     edx, edx; OldMode
0x18002da08  call    cs:__imp_RtlSetThreadErrorMode
0x18002da0e  test    ebx, ebx
0x18002da10  jns     short loc_18002DA50
0x18002da12  mov     rcx, cs:WPP_GLOBAL_Control
0x18002da19  lea     rdi, WPP_GLOBAL_Control
0x18002da20  cmp     rcx, rdi
0x18002da23  jz      loc_18002DC3D
0x18002da29  test    byte ptr [rcx+1Ch], 1
0x18002da2d  jz      loc_18002DC3D
0x18002da33  mov     rcx, [rcx+10h]
0x18002da37  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x18002da3e  mov     edx, 25h ; '%'
0x18002da43  mov     r9d, ebx
0x18002da46  call    WPP_SF_d
0x18002da4b  jmp     loc_18002DC3D
0x18002da50  mov     rcx, [rsi]; hModule
0x18002da53  lea     rdx, aOutofprocessex_0; "OutOfProcessExceptionEventCallback"
0x18002da5a  call    cs:__imp_GetProcAddress
0x18002da60  test    rax, rax
0x18002da63  jnz     short loc_18002DA9B
0x18002da65  mov     rcx, cs:WPP_GLOBAL_Control
0x18002da6c  lea     rdi, WPP_GLOBAL_Control
0x18002da73  cmp     rcx, rdi
0x18002da76  jz      short loc_18002DA91
0x18002da78  test    byte ptr [rcx+1Ch], 1
0x18002da7c  jz      short loc_18002DA91
0x18002da7e  lea     edx, [rax+26h]
0x18002da81  mov     rcx, [rcx+10h]
0x18002da85  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x18002da8c  call    WPP_SF_
0x18002da91  mov     ebx, 80004005h
0x18002da96  jmp     loc_18002DC3D
0x18002da9b  lea     rcx, [rsp+2C0h+var_278]
0x18002daa0  mov     [rsp+2C0h+var_298], rdi
0x18002daa5  mov     [rsp+2C0h+var_2A0], rcx
0x18002daaa  lea     rdx, [r13+350h]
0x18002dab1  mov     rcx, r12
0x18002dab4  mov     [rsp+2C0h+var_278], 104h
0x18002dabc  lea     r9, [rsp+2C0h+var_260]
0x18002dac1  lea     r8, [rsp+2C0h+var_280]
0x18002dac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dacb  mov     ebx, eax
0x18002dacd  test    eax, eax
0x18002dacf  jns     short loc_18002DAFC
0x18002dad1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dad8  lea     rdi, WPP_GLOBAL_Control
0x18002dadf  cmp     rcx, rdi
0x18002dae2  jz      loc_18002DC3D
0x18002dae8  test    byte ptr [rcx+1Ch], 1
0x18002daec  jz      loc_18002DC3D
0x18002daf2  mov     edx, 27h ; '''
0x18002daf7  jmp     loc_18002DBE2
0x18002dafc  mov     eax, [rsp+2C0h+var_280]
0x18002db00  xor     ebx, ebx
0x18002db02  test    eax, eax
0x18002db04  jz      loc_18002DC38
0x18002db0a  lea     rdi, WPP_GLOBAL_Control
0x18002db11  cmp     [r13+0AF8h], ebx
0x18002db18  jz      short loc_18002DB5C
0x18002db1a  mov     [rsp+2C0h+var_280], ebx
0x18002db1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db25  cmp     rcx, rdi
0x18002db28  jz      loc_18002DC38
0x18002db2e  test    byte ptr [rcx+1Ch], 4
0x18002db32  jz      loc_18002DC38
0x18002db38  mov     rcx, [rcx+10h]
0x18002db3c  lea     rax, [rsp+2C0h+var_260]
0x18002db41  lea     edx, [rbx+28h]
0x18002db44  mov     [rsp+2C0h+var_2A0], rax
0x18002db49  mov     r9, r14
0x18002db4c  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x18002db53  call    WPP_SF_SS
0x18002db58  mov     eax, [rsp+2C0h+var_280]
0x18002db5c  test    eax, eax
0x18002db5e  jz      loc_18002DC38
0x18002db64  mov     rcx, [rsi]; hModule
0x18002db67  lea     rdx, aOutofprocessex_1; "OutOfProcessExceptionEventSignatureCall"...
0x18002db6e  call    cs:__imp_GetProcAddress
0x18002db74  mov     [r15], rax
0x18002db77  test    rax, rax
0x18002db7a  jnz     short loc_18002DB9E
0x18002db7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db83  cmp     rcx, rdi
0x18002db86  jz      loc_18002DA91
0x18002db8c  test    byte ptr [rcx+1Ch], 1
0x18002db90  jz      loc_18002DA91
0x18002db96  lea     edx, [rax+29h]
0x18002db99  jmp     loc_18002DA81
0x18002db9e  lea     rax, [rsp+2C0h+var_260]
0x18002dba3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002dba7  inc     r8
0x18002dbaa  cmp     [rax+r8*2], bx
0x18002dbaf  jnz     short loc_18002DBA7
0x18002dbb1  lea     rcx, [r13+2D8h]
0x18002dbb8  lea     rdx, [rsp+2C0h+var_260]
0x18002dbbd  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18002dbc2  test    al, al
0x18002dbc4  jnz     short loc_18002DBF4
0x18002dbc6  mov     ebx, 8007000Eh
0x18002dbcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dbd2  cmp     rcx, rdi
0x18002dbd5  jz      short loc_18002DC3D
0x18002dbd7  test    byte ptr [rcx+1Ch], 1
0x18002dbdb  jz      short loc_18002DC3D
0x18002dbdd  mov     edx, 2Ah ; '*'
0x18002dbe2  mov     rcx, [rcx+10h]
0x18002dbe6  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x18002dbed  call    WPP_SF_
0x18002dbf2  jmp     short loc_18002DC3D
0x18002dbf4  mov     rcx, [rsi]; hModule
0x18002dbf7  lea     rdx, aOutofprocessex; "OutOfProcessExceptionEventDebuggerLaunc"...
0x18002dbfe  call    cs:__imp_GetProcAddress
0x18002dc04  mov     rcx, [rsp+2C0h+var_270]
0x18002dc09  mov     [rcx], rax
0x18002dc0c  test    rax, rax
0x18002dc0f  jnz     short loc_18002DC53
0x18002dc11  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc18  cmp     rcx, rdi
0x18002dc1b  jz      short loc_18002DC53
0x18002dc1d  test    byte ptr [rcx+1Ch], 1
0x18002dc21  jz      short loc_18002DC53
0x18002dc23  mov     rcx, [rcx+10h]
0x18002dc27  lea     edx, [rax+2Bh]
0x18002dc2a  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x18002dc31  call    WPP_SF_
0x18002dc36  jmp     short loc_18002DC53
0x18002dc38  mov     ebx, 80004001h
0x18002dc3d  mov     rcx, [rsi]; hLibModule
0x18002dc40  xor     edi, edi
0x18002dc42  mov     [rsi], rdi
0x18002dc45  test    rcx, rcx
0x18002dc48  jz      short loc_18002DC50
0x18002dc4a  call    cs:__imp_FreeLibrary
0x18002dc50  mov     [r15], rdi
0x18002dc53  mov     eax, ebx
0x18002dc55  jmp     short loc_18002DC8A
0x18002dc57  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc5e  lea     rdi, WPP_GLOBAL_Control
0x18002dc65  cmp     rcx, rdi
0x18002dc68  jz      short loc_18002DC85
0x18002dc6a  test    byte ptr [rcx+1Ch], 1
0x18002dc6e  jz      short loc_18002DC85
0x18002dc70  mov     rcx, [rcx+10h]
0x18002dc74  lea     r8, WPP_f577d8521c9b39ef05153804ed8add08_Traceguids
0x18002dc7b  mov     edx, 24h ; '$'
0x18002dc80  call    WPP_SF_
0x18002dc85  mov     eax, 80070057h
0x18002dc8a  mov     rcx, [rbp+1C0h+var_50]
0x18002dc91  xor     rcx, rsp; StackCookie
0x18002dc94  call    __security_check_cookie
0x18002dc99  add     rsp, 288h
0x18002dca0  pop     r15
0x18002dca2  pop     r14
0x18002dca4  pop     r13
0x18002dca6  pop     r12
0x18002dca8  pop     rdi
0x18002dca9  pop     rsi
0x18002dcaa  pop     rbx
0x18002dcab  pop     rbp
0x18002dcac  retn
```
