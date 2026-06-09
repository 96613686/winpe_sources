# PwrshPlugInMediator::ProcessExtraInfo(ushort const *,ushort * *)

- ea: `0x180003a68`
- end: `0x180003f04`
- name: `?ProcessExtraInfo@PwrshPlugInMediator@@QEAAXPEBGPEAPEAG@Z`
- size: `1180`
- prototype: `void __fastcall(PwrshPlugInMediator *this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002fac`

## callees

- `0x180001098`
- `0x180001318`
- `0x180001dfc`
- `0x180002058`
- `0x180002170`
- `0x180002e80`
- `0x180003158`
- `0x180003a68`
- `0x180003f0c`
- `0x1800042ec`
- `0x180004370`
- `0x180008b88`
- `0x18000b010`

## import_xrefs

- `msvcrt!wcschr` at `0x180003ca9`
- `msvcrt!wcschr` at `0x180003cb7`
- `msvcrt!wcschr` at `0x180003d0f`
- `msvcrt!wcschr` at `0x180003d1d`
- `msvcrt!wcschr` at `0x180003ca9`
- `msvcrt!wcschr` at `0x180003cb7`
- `msvcrt!wcschr` at `0x180003d0f`
- `msvcrt!wcschr` at `0x180003d1d`
- `msvcrt!_wcsnicmp` at `0x180003b67`
- `msvcrt!_wcsnicmp` at `0x180003b85`
- `msvcrt!_wcsnicmp` at `0x180003ba3`
- `msvcrt!_wcsnicmp` at `0x180003bbd`
- `msvcrt!_wcsnicmp` at `0x180003bd7`
- `msvcrt!_wcsnicmp` at `0x180003bf1`
- `msvcrt!_wcsnicmp` at `0x180003b67`
- `msvcrt!_wcsnicmp` at `0x180003b85`
- `msvcrt!_wcsnicmp` at `0x180003ba3`
- `msvcrt!_wcsnicmp` at `0x180003bbd`
- `msvcrt!_wcsnicmp` at `0x180003bd7`
- `msvcrt!_wcsnicmp` at `0x180003bf1`
- `msvcrt!isspace` at `0x180003b4d`
- `msvcrt!isspace` at `0x180003b4d`
- `msvcrt!wcsstr` at `0x180003aee`
- `msvcrt!wcsstr` at `0x180003b20`
- `msvcrt!wcsstr` at `0x180003c4b`
- `msvcrt!wcsstr` at `0x180003aee`
- `msvcrt!wcsstr` at `0x180003b20`
- `msvcrt!wcsstr` at `0x180003c4b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003de6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003e3a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003e49`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003de6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003e3a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003e49`

## pseudocode

```c
void __fastcall PwrshPlugInMediator::ProcessExtraInfo(
        PwrshPlugInMediator *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  const unsigned __int16 *v4; // rax
  __int64 v5; // r8
  unsigned __int64 v6; // r15
  unsigned __int16 *v7; // rbx
  unsigned __int16 *v8; // rsi
  unsigned __int16 *v9; // r13
  wchar_t *v10; // rax
  const wchar_t *v11; // r14
  unsigned __int16 *ConfigXmlValue; // r12
  wchar_t *v13; // rax
  const wchar_t *i; // rbx
  PwrshPlugInMediator *v15; // rcx
  PwrshPlugInMediator *v16; // rcx
  PwrshPlugInMediator *v17; // rcx
  wchar_t *v18; // rax
  wchar_t *v19; // rbx
  wchar_t *v20; // rax
  NativeMsh::PwrshCommon *v21; // rcx
  const wchar_t *v22; // rbx
  wchar_t *v23; // rdi
  wchar_t *v24; // rax
  NativeMsh::PwrshCommon *v25; // rcx
  const unsigned __int16 *v26; // r8
  __int64 v27; // rcx
  unsigned __int16 *v28; // rax
  unsigned __int64 v29; // rdi
  unsigned int v30; // edi
  PwrshPlugInMediator *v31; // rbx
  unsigned __int16 *v32; // rax
  unsigned __int16 *v33; // rax
  PlugInException *v34; // rax
  PlugInException *v35; // rax
  unsigned __int16 *v36; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 *v37; // [rsp+38h] [rbp-10h]
  PlugInException *v39; // [rsp+98h] [rbp+50h] BYREF
  unsigned __int16 *pExceptionObject; // [rsp+A0h] [rbp+58h] BYREF
  unsigned __int16 *v41; // [rsp+A8h] [rbp+60h]

  pExceptionObject = (unsigned __int16 *)a3;
  PwrshPlugInMediator::VerifyAndStoreExtraInfo(this, a2, 0);
  if ( !a2 )
    goto LABEL_66;
  v4 = a2;
  v5 = 0x7FFFFFFF;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v5;
  }
  while ( v5 );
  v6 = (0x7FFFFFFF - v5) & -(__int64)(v5 != 0);
  if ( !v5 )
  {
LABEL_66:
    pExceptionObject = 0;
    GetFormattedErrorMessage(&pExceptionObject, 0x805403EE, L"InitializationParameters");
    v34 = (PlugInException *)operator new(0x10u);
    v39 = v34;
    if ( v34 )
      v35 = PlugInException::PlugInException(v34, 0x805403EE, pExceptionObject);
    else
      v35 = 0;
    v39 = v35;
    throw (PlugInException **)&v39;
  }
  v7 = 0;
  v37 = 0;
  v41 = 0;
  v8 = 0;
  v9 = 0;
  v10 = wcsstr(a2, L"<Param ");
  v11 = v10 + 7;
  if ( v10 != (wchar_t *)-14LL )
  {
    ConfigXmlValue = 0;
    do
    {
      if ( v11 - a2 >= v6 )
        break;
      v13 = wcsstr(v11, L"Name=");
      if ( v13 )
      {
        for ( i = v13 + 5; isspace(*i) && i - a2 < v6; ++i )
          ;
        if ( _wcsnicmp(i, L"\"psversion\"", 0xBu) && _wcsnicmp(i, L"'psversion'", 0xBu) )
        {
          if ( _wcsnicmp(i, L"\"maxpsversion\"", 0xEu) && _wcsnicmp(i, L"'maxpsversion'", 0xEu) )
          {
            if ( !_wcsnicmp(i, L"\"assemblyname\"", 0xEu) || !_wcsnicmp(i, L"'assemblyname'", 0xEu) )
              ConfigXmlValue = PwrshPlugInMediator::ReadConfigXmlValue(v17, v11, a2, v6);
          }
          else
          {
            v9 = PwrshPlugInMediator::ReadConfigXmlValue(v16, v11, a2, v6);
          }
        }
        else
        {
          v8 = PwrshPlugInMediator::ReadConfigXmlValue(v15, v11, a2, v6);
        }
        if ( v8 && v9 && ConfigXmlValue )
          break;
      }
      v18 = wcsstr(v11, L"<Param ");
      v11 = v18 + 7;
    }
    while ( v18 != (wchar_t *)-14LL );
    v41 = ConfigXmlValue;
    v7 = ConfigXmlValue;
  }
  v36 = 0;
  if ( v8 )
  {
    if ( !v7 || v9 )
    {
LABEL_51:
      v31 = this;
LABEL_52:
      v30 = 0;
      v37 = PwrshPlugInMediator::CalculatePowershellVersion(v31, v8, v9);
      goto LABEL_53;
    }
    LODWORD(pExceptionObject) = -1;
    if ( *v8 )
    {
      v19 = wcschr(v8, 0x2Eu);
      v20 = wcschr(v8, 0);
      if ( v20 )
      {
        if ( v19 )
        {
          if ( !NativeMsh::PwrshCommon::ParseInt(v21, v8, v19, (int *)&pExceptionObject) )
            goto LABEL_54;
          v22 = v19 + 1;
        }
        else
        {
          if ( !NativeMsh::PwrshCommon::ParseInt(v21, v8, v20, (int *)&pExceptionObject) )
            goto LABEL_54;
          v22 = 0;
        }
        if ( !v22 )
          goto LABEL_72;
        if ( *v22 )
        {
          v23 = wcschr(v22, 0x2Eu);
          v24 = wcschr(v22, 0);
          if ( v24 )
          {
            v26 = v23;
            if ( !v23 )
              v26 = v24;
            if ( NativeMsh::PwrshCommon::ParseInt(v25, v22, v26, (int *)&v39) )
            {
LABEL_72:
              if ( (_DWORD)pExceptionObject == 2 )
              {
                v27 = 0x7FFFFFFF;
                v28 = v8;
                do
                {
                  if ( !*v28 )
                    break;
                  ++v28;
                  --v27;
                }
                while ( v27 );
                v29 = (0x7FFFFFFF - v27) & -(__int64)(v27 != 0);
                if ( !v27
                  || (v9 = (unsigned __int16 *)operator new[](saturated_mul(v29 + 1, 2u)),
                      (int)StringCchCopyNW(v9, v29 + 1, v8, v29) < 0) )
                {
                  v30 = -2141977618;
                  GetFormattedErrorMessage(&v36, 0x805403EE, L"InitializationParameters");
                  v31 = this;
LABEL_53:
                  operator delete[](v8);
                  goto LABEL_56;
                }
              }
              goto LABEL_51;
            }
          }
        }
      }
    }
LABEL_54:
    v31 = this;
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int16 *))(**((_QWORD **)this + 21) + 8LL))(
      *((_QWORD *)this + 21),
      0,
      17,
      v8);
    goto LABEL_52;
  }
  v30 = -2141977619;
  GetFormattedErrorMessage(&v36, 0x805403ED, L"PSVersion", L"InitializationParameters");
  v31 = this;
LABEL_56:
  if ( v9 )
    operator delete[](v9);
  if ( v41 )
    operator delete[](v41);
  if ( !v37 )
  {
    v32 = (unsigned __int16 *)operator new(0x10u);
    pExceptionObject = v32;
    if ( v32 )
      v33 = (unsigned __int16 *)PlugInException::PlugInException((PlugInException *)v32, v30, v36);
    else
      v33 = 0;
    pExceptionObject = v33;
    throw (PlugInException **)&pExceptionObject;
  }
  PwrshPlugInMediator::LoadPowerShell((const wchar_t **)v31, v37);
}

```

## disassembly

```asm
0x180003a68  mov     [rsp-40h+pExceptionObject], r8
0x180003a6d  mov     [rsp-40h+arg_0], rcx
0x180003a72  push    rbp
0x180003a73  push    rbx
0x180003a74  push    rsi
0x180003a75  push    rdi
0x180003a76  push    r12
0x180003a78  push    r13
0x180003a7a  push    r14
0x180003a7c  push    r15
0x180003a7e  mov     rbp, rsp
0x180003a81  sub     rsp, 48h
0x180003a85  xor     r8d, r8d; unsigned __int16 **
0x180003a88  mov     rdi, rdx
0x180003a8b  call    ?VerifyAndStoreExtraInfo@PwrshPlugInMediator@@QEAAXPEBGPEAPEAG@Z; PwrshPlugInMediator::VerifyAndStoreExtraInfo(ushort const *,ushort * *)
0x180003a90  xor     r14d, r14d
0x180003a93  test    rdi, rdi
0x180003a96  jz      loc_180003EAE
0x180003a9c  mov     r12d, 7FFFFFFFh
0x180003aa2  mov     rax, rdi
0x180003aa5  mov     r8d, r12d
0x180003aa8  cmp     [rax], r14w
0x180003aac  jz      short loc_180003AB8
0x180003aae  add     rax, 2
0x180003ab2  sub     r8, 1
0x180003ab6  jnz     short loc_180003AA8
0x180003ab8  mov     rcx, r12
0x180003abb  mov     rax, r8
0x180003abe  sub     rcx, r8
0x180003ac1  neg     rax
0x180003ac4  sbb     r15, r15
0x180003ac7  and     r15, rcx
0x180003aca  test    r8, r8
0x180003acd  jz      loc_180003EAE
0x180003ad3  mov     rbx, r14
0x180003ad6  mov     [rbp+var_10], r14
0x180003ada  lea     rdx, aParam; "<Param "
0x180003ae1  mov     [rbp+arg_18], rbx
0x180003ae5  mov     rcx, rdi; Str
0x180003ae8  mov     rsi, r14
0x180003aeb  mov     r13, r14
0x180003aee  call    cs:__imp_wcsstr
0x180003af4  mov     r14, rax
0x180003af7  add     r14, 0Eh
0x180003afb  jz      loc_180003C6C
0x180003b01  mov     r12, rbx
0x180003b04  mov     rax, r14
0x180003b07  sub     rax, rdi
0x180003b0a  sar     rax, 1
0x180003b0d  cmp     rax, r15
0x180003b10  jnb     loc_180003C5E
0x180003b16  lea     rdx, aName; "Name="
0x180003b1d  mov     rcx, r14; Str
0x180003b20  call    cs:__imp_wcsstr
0x180003b26  mov     rbx, rax
0x180003b29  test    rax, rax
0x180003b2c  jz      loc_180003C41
0x180003b32  add     rbx, 0Ah
0x180003b36  jmp     short loc_180003B4A
0x180003b38  mov     rax, rbx
0x180003b3b  sub     rax, rdi
0x180003b3e  sar     rax, 1
0x180003b41  cmp     rax, r15
0x180003b44  jnb     short loc_180003B57
0x180003b46  add     rbx, 2
0x180003b4a  movzx   ecx, word ptr [rbx]; C
0x180003b4d  call    cs:__imp_isspace
0x180003b53  test    eax, eax
0x180003b55  jnz     short loc_180003B38
0x180003b57  mov     r8d, 0Bh; MaxCount
0x180003b5d  lea     rdx, aPsversion_1; "\"psversion\""
0x180003b64  mov     rcx, rbx; String1
0x180003b67  call    cs:__imp__wcsnicmp
0x180003b6d  test    eax, eax
0x180003b6f  jz      loc_180003C21
0x180003b75  mov     r8d, 0Bh; MaxCount
0x180003b7b  lea     rdx, aPsversion_0; "'psversion'"
0x180003b82  mov     rcx, rbx; String1
0x180003b85  call    cs:__imp__wcsnicmp
0x180003b8b  test    eax, eax
0x180003b8d  jz      loc_180003C21
0x180003b93  mov     r8d, 0Eh; MaxCount
0x180003b99  lea     rdx, aMaxpsversion_0; "\"maxpsversion\""
0x180003ba0  mov     rcx, rbx; String1
0x180003ba3  call    cs:__imp__wcsnicmp
0x180003ba9  test    eax, eax
0x180003bab  jz      short loc_180003C0E
0x180003bad  mov     r8d, 0Eh; MaxCount
0x180003bb3  lea     rdx, aMaxpsversion; "'maxpsversion'"
0x180003bba  mov     rcx, rbx; String1
0x180003bbd  call    cs:__imp__wcsnicmp
0x180003bc3  test    eax, eax
0x180003bc5  jz      short loc_180003C0E
0x180003bc7  mov     r8d, 0Eh; MaxCount
0x180003bcd  lea     rdx, aAssemblyname; "\"assemblyname\""
0x180003bd4  mov     rcx, rbx; String1
0x180003bd7  call    cs:__imp__wcsnicmp
0x180003bdd  test    eax, eax
0x180003bdf  jz      short loc_180003BFB
0x180003be1  mov     r8d, 0Eh; MaxCount
0x180003be7  lea     rdx, aAssemblyname_0; "'assemblyname'"
0x180003bee  mov     rcx, rbx; String1
0x180003bf1  call    cs:__imp__wcsnicmp
0x180003bf7  test    eax, eax
0x180003bf9  jnz     short loc_180003C32
0x180003bfb  mov     r9, r15; unsigned __int64
0x180003bfe  mov     r8, rdi; unsigned __int16 *
0x180003c01  mov     rdx, r14; unsigned __int16 *
0x180003c04  call    ?ReadConfigXmlValue@PwrshPlugInMediator@@QEAAPEAGPEBG0_K@Z; PwrshPlugInMediator::ReadConfigXmlValue(ushort const *,ushort const *,unsigned __int64)
0x180003c09  mov     r12, rax
0x180003c0c  jmp     short loc_180003C32
0x180003c0e  mov     r9, r15; unsigned __int64
0x180003c11  mov     r8, rdi; unsigned __int16 *
0x180003c14  mov     rdx, r14; unsigned __int16 *
0x180003c17  call    ?ReadConfigXmlValue@PwrshPlugInMediator@@QEAAPEAGPEBG0_K@Z; PwrshPlugInMediator::ReadConfigXmlValue(ushort const *,ushort const *,unsigned __int64)
0x180003c1c  mov     r13, rax
0x180003c1f  jmp     short loc_180003C32
0x180003c21  mov     r9, r15; unsigned __int64
0x180003c24  mov     r8, rdi; unsigned __int16 *
0x180003c27  mov     rdx, r14; unsigned __int16 *
0x180003c2a  call    ?ReadConfigXmlValue@PwrshPlugInMediator@@QEAAPEAGPEBG0_K@Z; PwrshPlugInMediator::ReadConfigXmlValue(ushort const *,ushort const *,unsigned __int64)
0x180003c2f  mov     rsi, rax
0x180003c32  test    rsi, rsi
0x180003c35  jz      short loc_180003C41
0x180003c37  test    r13, r13
0x180003c3a  jz      short loc_180003C41
0x180003c3c  test    r12, r12
0x180003c3f  jnz     short loc_180003C5E
0x180003c41  lea     rdx, aParam; "<Param "
0x180003c48  mov     rcx, r14; Str
0x180003c4b  call    cs:__imp_wcsstr
0x180003c51  mov     r14, rax
0x180003c54  add     r14, 0Eh
0x180003c58  jnz     loc_180003B04
0x180003c5e  mov     [rbp+arg_18], r12
0x180003c62  mov     r12d, 7FFFFFFFh
0x180003c68  mov     rbx, [rbp+arg_18]
0x180003c6c  xor     r14d, r14d
0x180003c6f  mov     [rbp+var_18], r14
0x180003c73  test    rsi, rsi
0x180003c76  jz      loc_180003E10
0x180003c7c  test    rbx, rbx
0x180003c7f  jz      loc_180003DCA
0x180003c85  test    r13, r13
0x180003c88  jnz     loc_180003DCA
0x180003c8e  or      r15, 0FFFFFFFFFFFFFFFFh
0x180003c92  mov     dword ptr [rbp+pExceptionObject], r15d
0x180003c96  cmp     r14w, [rsi]
0x180003c9a  jz      loc_180003DEE
0x180003ca0  lea     edi, [r14+2Eh]
0x180003ca4  mov     rcx, rsi; Str
0x180003ca7  mov     edx, edi; Ch
0x180003ca9  call    cs:__imp_wcschr
0x180003caf  xor     edx, edx; Ch
0x180003cb1  mov     rcx, rsi; Str
0x180003cb4  mov     rbx, rax
0x180003cb7  call    cs:__imp_wcschr
0x180003cbd  test    rax, rax
0x180003cc0  jz      loc_180003DEE
0x180003cc6  lea     r9, [rbp+pExceptionObject]; int *
0x180003cca  mov     rdx, rsi; unsigned __int16 *
0x180003ccd  test    rbx, rbx
0x180003cd0  jz      short loc_180003CE8
0x180003cd2  mov     r8, rbx; unsigned __int16 *
0x180003cd5  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x180003cda  test    al, al
0x180003cdc  jz      loc_180003DEE
0x180003ce2  add     rbx, 2
0x180003ce6  jmp     short loc_180003CFB
0x180003ce8  mov     r8, rax; unsigned __int16 *
0x180003ceb  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x180003cf0  test    al, al
0x180003cf2  jz      loc_180003DEE
0x180003cf8  mov     rbx, r14
0x180003cfb  test    rbx, rbx
0x180003cfe  jz      short loc_180003D4B
0x180003d00  cmp     r14w, [rbx]
0x180003d04  jz      loc_180003DEE
0x180003d0a  mov     edx, edi; Ch
0x180003d0c  mov     rcx, rbx; Str
0x180003d0f  call    cs:__imp_wcschr
0x180003d15  xor     edx, edx; Ch
0x180003d17  mov     rcx, rbx; Str
0x180003d1a  mov     rdi, rax
0x180003d1d  call    cs:__imp_wcschr
0x180003d23  test    rax, rax
0x180003d26  jz      loc_180003DEE
0x180003d2c  lea     r9, [rbp+arg_8]; int *
0x180003d30  mov     rdx, rbx; unsigned __int16 *
0x180003d33  mov     r8, rdi
0x180003d36  test    rdi, rdi
0x180003d39  jnz     short loc_180003D3E
0x180003d3b  mov     r8, rax; unsigned __int16 *
0x180003d3e  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x180003d43  test    al, al
0x180003d45  jz      loc_180003DEE
0x180003d4b  cmp     dword ptr [rbp+pExceptionObject], 2
0x180003d4f  jnz     short loc_180003DCA
0x180003d51  mov     rcx, r12
0x180003d54  mov     rax, rsi
0x180003d57  cmp     [rax], r14w
0x180003d5b  jz      short loc_180003D67
0x180003d5d  add     rax, 2
0x180003d61  sub     rcx, 1
0x180003d65  jnz     short loc_180003D57
0x180003d67  sub     r12, rcx
0x180003d6a  mov     rax, rcx
0x180003d6d  neg     rax
0x180003d70  sbb     rdi, rdi
0x180003d73  and     rdi, r12
0x180003d76  test    rcx, rcx
0x180003d79  jnz     short loc_180003D9A
0x180003d7b  mov     ebx, 805403EEh
0x180003d80  lea     r8, aInitialization; "InitializationParameters"
0x180003d87  mov     edx, ebx; unsigned int
0x180003d89  lea     rcx, [rbp+var_18]; unsigned __int16 **
0x180003d8d  mov     edi, ebx
0x180003d8f  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x180003d94  mov     rbx, [rbp+arg_0]
0x180003d98  jmp     short loc_180003DE3
0x180003d9a  lea     rbx, [rdi+1]
0x180003d9e  mov     eax, 2
0x180003da3  mul     rbx
0x180003da6  cmovb   rax, r15
0x180003daa  mov     rcx, rax; unsigned __int64
0x180003dad  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003db2  mov     r9, rdi; unsigned __int64
0x180003db5  mov     r8, rsi; unsigned __int16 *
0x180003db8  mov     rdx, rbx; unsigned __int64
0x180003dbb  mov     rcx, rax; unsigned __int16 *
0x180003dbe  mov     r13, rax
0x180003dc1  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180003dc6  test    eax, eax
0x180003dc8  js      short loc_180003D7B
0x180003dca  mov     rbx, [rbp+arg_0]
0x180003dce  mov     r8, r13; unsigned __int16 *
0x180003dd1  mov     rdx, rsi; unsigned __int16 *
0x180003dd4  mov     rcx, rbx; this
0x180003dd7  mov     edi, r14d
0x180003dda  call    ?CalculatePowershellVersion@PwrshPlugInMediator@@QEAAPEAGPEAG0@Z; PwrshPlugInMediator::CalculatePowershellVersion(ushort *,ushort *)
0x180003ddf  mov     [rbp+var_10], rax
0x180003de3  mov     rcx, rsi
0x180003de6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003dec  jmp     short loc_180003E32
0x180003dee  mov     rbx, [rbp+arg_0]
0x180003df2  xor     edx, edx
0x180003df4  mov     r9, rsi
0x180003df7  mov     rcx, [rbx+0A8h]
0x180003dfe  lea     r8d, [rdx+11h]
0x180003e02  mov     rax, [rcx]
0x180003e05  mov     rax, [rax+8]
0x180003e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e0e  jmp     short loc_180003DCE
0x180003e10  mov     edi, 805403EDh
0x180003e15  lea     r9, aInitialization; "InitializationParameters"
0x180003e1c  mov     edx, edi; unsigned int
0x180003e1e  lea     r8, aPsversion; "PSVersion"
0x180003e25  lea     rcx, [rbp+var_18]; unsigned __int16 **
0x180003e29  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x180003e2e  mov     rbx, [rbp+arg_0]
0x180003e32  test    r13, r13
0x180003e35  jz      short loc_180003E40
0x180003e37  mov     rcx, r13
0x180003e3a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003e40  mov     rcx, [rbp+arg_18]
0x180003e44  test    rcx, rcx
0x180003e47  jz      short loc_180003E4F
0x180003e49  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003e4f  mov     rax, [rbp+var_10]
0x180003e53  test    rax, rax
0x180003e56  jz      short loc_180003E73
0x180003e58  mov     rdx, rax; unsigned __int16 *
0x180003e5b  mov     rcx, rbx; this
0x180003e5e  add     rsp, 48h
0x180003e62  pop     r15
0x180003e64  pop     r14
0x180003e66  pop     r13
0x180003e68  pop     r12
0x180003e6a  pop     rdi
0x180003e6b  pop     rsi
0x180003e6c  pop     rbx
0x180003e6d  pop     rbp
0x180003e6e  jmp     ?LoadPowerShell@PwrshPlugInMediator@@AEAAXPEBG@Z; PwrshPlugInMediator::LoadPowerShell(ushort const *)
0x180003e73  mov     ecx, 10h; Size
0x180003e78  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003e7d  mov     [rbp+pExceptionObject], rax
0x180003e81  test    rax, rax
0x180003e84  jz      short loc_180003E96
0x180003e86  mov     r8, [rbp+var_18]; unsigned __int16 *
0x180003e8a  mov     edx, edi; unsigned int
0x180003e8c  mov     rcx, rax; this
0x180003e8f  call    ??0PlugInException@@QEAA@KPEAG@Z; PlugInException::PlugInException(ulong,ushort *)
0x180003e94  jmp     short loc_180003E99
0x180003e96  mov     rax, r14
0x180003e99  lea     rdx, _TI2PEAVPlugInException@@; pThrowInfo
0x180003ea0  mov     [rbp+pExceptionObject], rax
0x180003ea4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003ea8  call    _CxxThrowException_0
0x180003eae  mov     ebx, 805403EEh
0x180003eb3  mov     [rbp+pExceptionObject], r14
  ... truncated ...
```
