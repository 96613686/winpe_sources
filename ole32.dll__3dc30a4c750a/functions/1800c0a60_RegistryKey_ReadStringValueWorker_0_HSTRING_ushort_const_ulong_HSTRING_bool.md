# RegistryKey::ReadStringValueWorker<0,HSTRING__ *>(ushort const *,ulong,HSTRING__ * *,bool *)

- ea: `0x1800c0a60`
- end: `0x1800c0d49`
- name: `??$ReadStringValueWorker@$0A@PEAUHSTRING__@@@RegistryKey@@AEBAJPEBGKPEAPEAUHSTRING__@@PEA_N@Z`
- size: `745`
- prototype: `__int64 __fastcall(RegistryKey *this, const wchar_t *value, unsigned int isExpandable, HSTRING__ **valueName, bool *dwFlags)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c2e3c`

## callees

- `0x1800185ec`
- `0x180049ba8`
- `0x18006b1c8`
- `0x18008dc14`
- `0x18008dcf8`
- `0x1800c0a60`
- `0x1800c10d0`
- `0x1800c15b8`
- `0x1800c3618`
- `0x1800c4651`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c0ac5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c0ac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0c29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0cac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0c29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0cac`

## string_xrefs

- `0x1800c0aff`: `onecore\internal\com\inc\combase\RegistryKey.hpp`
- `0x1800c0ba3`: `onecore\internal\com\inc\combase\RegistryKey.hpp`
- `0x1800c0c08`: `onecore\internal\com\inc\combase\RegistryKey.hpp`
- `0x1800c0c8c`: `onecore\internal\com\inc\combase\RegistryKey.hpp`
- `0x1800c0cd7`: `onecore\internal\com\inc\combase\RegistryKey.hpp`
- `0x1800c0d1f`: `onecore\internal\com\inc\combase\RegistryKey.hpp`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall RegistryKey::ReadStringValueWorker<0,HSTRING__ *>(
        RegistryKey *this,
        const wchar_t *value,
        unsigned int isExpandable,
        HSTRING__ **valueName,
        bool *dwFlags)
{
  bool *v5; // r12
  HKEY__ *volatile hkey; // rcx
  LSTATUS v9; // eax
  HRESULT v10; // ebx
  char v11; // di
  __int64 v12; // rsi
  unsigned int v13; // edx
  HRESULT v14; // eax
  const wchar_t *v15; // rdx
  unsigned int v16; // edx
  HRESULT v17; // eax
  unsigned int v18; // ecx
  HSTRING__ *m_ptr; // rbx
  HRESULT v20; // eax
  int v21; // edi
  bool v22; // zf
  unsigned int *formatString; // [rsp+20h] [rbp-38h]
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > result; // [rsp+40h] [rbp-18h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (__cdecl*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer,wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t> > > buffer; // [rsp+48h] [rbp-10h] BYREF
  void *retaddr; // [rsp+98h] [rbp+40h]
  int hasEmbeddedNull; // [rsp+A0h] [rbp+48h] BYREF
  const wchar_t *dataSize; // [rsp+A8h] [rbp+50h] OVERLAPPED BYREF
  unsigned int stackBuffer; // [rsp+B0h] [rbp+58h] OVERLAPPED BYREF
  wchar_t *pszValue; // [rsp+B8h] [rbp+60h] BYREF

  stackBuffer = isExpandable;
  dataSize = value;
  v5 = dwFlags;
  *valueName = 0;
  *v5 = 0;
  hkey = this->_hkey;
  LODWORD(dwFlags) = 0;
  buffer.m_ptr = 0;
  LODWORD(dataSize) = 2;
  v9 = RegQueryValueExW(hkey, &::value, 0, (LPDWORD)&dwFlags, (LPBYTE)&stackBuffer, (LPDWORD)&dataSize);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 < 0 )
  {
    if ( v10 == -2147024894 )
      goto LABEL_8;
    if ( v10 == -2147024662 )
    {
LABEL_10:
      v11 = 0;
      goto LABEL_11;
    }
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      0x6EAu,
      "onecore\\internal\\com\\inc\\combase\\RegistryKey.hpp",
      v10,
      "value:%ls",
      &::value);
  }
  if ( v10 == -2147024774 )
    goto LABEL_10;
LABEL_8:
  v11 = 1;
  if ( v10 < 0 )
    goto LABEL_42;
LABEL_11:
  if ( (_DWORD)dwFlags != 1 || !(_DWORD)dataSize || ((unsigned __int8)dataSize & 1) != 0 )
  {
    v13 = 2078;
    goto LABEL_40;
  }
  v12 = ((unsigned int)dataSize >> 1) - 1;
  if ( (unsigned int)dataSize >> 1 == 1 )
  {
    if ( v11 && !(_WORD)stackBuffer )
    {
      *valueName = 0;
LABEL_18:
      v10 = 0;
      goto LABEL_42;
    }
    v13 = 2103;
    goto LABEL_40;
  }
  pszValue = 0;
  v14 = StringTraits<HSTRING__ *>::Allocate(v12, &pszValue, &buffer.m_ptr);
  v10 = v14;
  if ( v14 < 0 )
  {
    v16 = 2156;
LABEL_22:
    wil::details::in1diag3::Return_Hr(retaddr, v16, "onecore\\internal\\com\\inc\\combase\\RegistryKey.hpp", v14);
    goto LABEL_42;
  }
  if ( v11 )
  {
    if ( *((_WORD *)&stackBuffer + v12) )
    {
      v13 = 2170;
LABEL_40:
      v21 = -2147024883;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        v13,
        "onecore\\internal\\com\\inc\\combase\\RegistryKey.hpp",
        -2147024883,
        "value:%ws",
        &::value);
      goto LABEL_41;
    }
    memcpy_0(pszValue, &stackBuffer, (unsigned int)dataSize);
  }
  else
  {
    v14 = RegistryKey::GetValue(this, v15, &::value, 2u, formatString, pszValue, (unsigned int *)&dataSize);
    v10 = v14;
    if ( v14 < 0 )
    {
      v16 = 2181;
      goto LABEL_22;
    }
  }
  result.m_ptr = 0;
  v17 = StringTraits<HSTRING__ *>::Promote(&buffer, &result.m_ptr);
  v10 = v17;
  if ( v17 >= 0 )
  {
    m_ptr = result.m_ptr;
    hasEmbeddedNull = 0;
    v20 = StringTraits<HSTRING__ *>::VerifyNoEmbeddedNulls(v18, result.m_ptr, &hasEmbeddedNull);
    v21 = v20;
    if ( v20 >= 0 )
    {
      if ( !hasEmbeddedNull )
      {
        v22 = (_DWORD)dwFlags == 2;
        *valueName = m_ptr;
        *v5 = v22;
        goto LABEL_18;
      }
      v21 = -2147024883;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x88Du,
        "onecore\\internal\\com\\inc\\combase\\RegistryKey.hpp",
        -2147024883,
        "value:%ws",
        &::value);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x88Cu, "onecore\\internal\\com\\inc\\combase\\RegistryKey.hpp", v20);
    }
    if ( m_ptr )
      WindowsDeleteString(m_ptr);
LABEL_41:
    v10 = v21;
    goto LABEL_42;
  }
  wil::details::in1diag3::Return_Hr(retaddr, 0x887u, "onecore\\internal\\com\\inc\\combase\\RegistryKey.hpp", v17);
  if ( result.m_ptr )
    WindowsDeleteString(result.m_ptr);
LABEL_42:
  wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&buffer);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800c0a60  mov     r11, rsp
0x1800c0a63  mov     [r11+18h], r8d
0x1800c0a67  mov     [r11+10h], rdx
0x1800c0a6b  push    rbp
0x1800c0a6c  push    rbx
0x1800c0a6d  push    rsi
0x1800c0a6e  push    rdi
0x1800c0a6f  push    r12
0x1800c0a71  push    r13
0x1800c0a73  push    r14
0x1800c0a75  push    r15
0x1800c0a77  mov     rbp, rsp
0x1800c0a7a  sub     rsp, 58h
0x1800c0a7e  mov     r12, [rbp+dwType]
0x1800c0a82  lea     rax, [rbp+dataSize]
0x1800c0a86  xor     r13d, r13d
0x1800c0a89  mov     [r11-70h], rax
0x1800c0a8d  mov     [value], r13
0x1800c0a90  lea     rax, [rbp+stackBuffer]
0x1800c0a94  mov     r14, value
0x1800c0a97  mov     [r11-78h], rax
0x1800c0a9b  mov     r15, this
0x1800c0a9e  mov     [r12], r13b
0x1800c0aa2  mov     this, [this]; hKey
0x1800c0aa5  lea     rsi, value
0x1800c0aac  lea     value, [rbp+dwType]; lpType
0x1800c0ab0  mov     dword ptr [rbp+dwType], r13d
0x1800c0ab4  xor     r8d, r8d; lpReserved
0x1800c0ab7  mov     [rbp+buffer.m_ptr], r13
0x1800c0abb  mov     rdx, rsi; lpValueName
0x1800c0abe  mov     [rbp+dataSize], 2
0x1800c0ac5  call    cs:__imp_RegQueryValueExW
0x1800c0acb  mov     ebx, eax
0x1800c0acd  test    eax, eax
0x1800c0acf  jle     short loc_1800C0ADA
0x1800c0ad1  movzx   ebx, ax
0x1800c0ad4  or      ebx, 80070000h
0x1800c0ada  mov     edi, 800700EAh
0x1800c0adf  test    ebx, ebx
0x1800c0ae1  jns     short loc_1800C0B18
0x1800c0ae3  cmp     ebx, 80070002h
0x1800c0ae9  jz      short loc_1800C0B24
0x1800c0aeb  cmp     ebx, edi
0x1800c0aed  jz      short loc_1800C0B30
0x1800c0aef  mov     this, [rbp+40h]; callerReturnAddress
0x1800c0af3  lea     rax, aValueLs; "value:%ls"
0x1800c0afa  mov     [rsp+58h+pszSubKey], rsi
0x1800c0aff  lea     r8, aOnecoreInterna_6; "onecore\\internal\\com\\inc\\combase\\R"...
0x1800c0b06  mov     r9d, ebx; hr
0x1800c0b09  mov     [rsp+58h+formatString], rax; formatString
0x1800c0b0e  mov     edx, 6EAh; lineNumber
0x1800c0b13  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800c0b18  cmp     ebx, 8007007Ah
0x1800c0b1e  jz      short loc_1800C0B30
0x1800c0b20  cmp     ebx, edi
0x1800c0b22  jz      short loc_1800C0B30
0x1800c0b24  mov     dil, 1
0x1800c0b27  test    ebx, ebx
0x1800c0b29  jns     short loc_1800C0B33
0x1800c0b2b  jmp     loc_1800C0D2D
0x1800c0b30  mov     dil, r13b
0x1800c0b33  cmp     dword ptr [rbp+dwType], 1
0x1800c0b37  jnz     loc_1800C0CFD
0x1800c0b3d  mov     eax, [rbp+dataSize]
0x1800c0b40  test    eax, eax
0x1800c0b42  jz      loc_1800C0CFD
0x1800c0b48  test    al, 1
0x1800c0b4a  jnz     loc_1800C0CFD
0x1800c0b50  shr     eax, 1
0x1800c0b52  lea     esi, [rax-1]
0x1800c0b55  test    esi, esi
0x1800c0b57  jnz     short loc_1800C0B81
0x1800c0b59  test    dil, dil
0x1800c0b5c  jz      short loc_1800C0B70
0x1800c0b5e  cmp     [rbp+stackBuffer], r13w
0x1800c0b63  jnz     short loc_1800C0B70
0x1800c0b65  mov     [r14], r13
0x1800c0b68  mov     ebx, r13d
0x1800c0b6b  jmp     loc_1800C0D2D
0x1800c0b70  lea     rsi, value
0x1800c0b77  mov     edx, 837h
0x1800c0b7c  jmp     loc_1800C0D02
0x1800c0b81  lea     r8, [rbp+buffer]; bufferHandle
0x1800c0b85  mov     [rbp+pszValue], r13
0x1800c0b89  lea     rdx, [rbp+pszValue]; buffer
0x1800c0b8d  mov     ecx, esi; length
0x1800c0b8f  call    ?Allocate@?$StringTraits@PEAUHSTRING__@@@@SAJIPEAPEAGPEAPEAUHSTRING_BUFFER__@@@Z; StringTraits<HSTRING__ *>::Allocate(uint,ushort * *,HSTRING_BUFFER__ * *)
0x1800c0b94  mov     ebx, eax
0x1800c0b96  test    eax, eax
0x1800c0b98  jns     short loc_1800C0BB7
0x1800c0b9a  mov     edx, 86Ch; lineNumber
0x1800c0b9f  mov     this, [rbp+40h]; callerReturnAddress
0x1800c0ba3  lea     r8, aOnecoreInterna_6; "onecore\\internal\\com\\inc\\combase\\R"...
0x1800c0baa  mov     r9d, eax; hr
0x1800c0bad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0bb2  jmp     loc_1800C0D2D
0x1800c0bb7  test    dil, dil
0x1800c0bba  jz      short loc_1800C0C34
0x1800c0bbc  cmp     [rbp+rsi*2+stackBuffer], r13w
0x1800c0bc2  jz      short loc_1800C0BD5
0x1800c0bc4  lea     rsi, value
0x1800c0bcb  mov     edx, 87Ah
0x1800c0bd0  jmp     loc_1800C0D02
0x1800c0bd5  mov     r8d, [rbp+dataSize]; Size
0x1800c0bd9  lea     rdx, [rbp+stackBuffer]; Src
0x1800c0bdd  mov     this, [rbp+pszValue]; void *
0x1800c0be1  call    memcpy_0
0x1800c0be6  lea     rsi, value
0x1800c0bed  lea     rdx, [rbp+result]; value
0x1800c0bf1  mov     [rbp+result.m_ptr], r13
0x1800c0bf5  lea     this, [rbp+buffer]; buffer
0x1800c0bf9  call    ?Promote@?$StringTraits@PEAUHSTRING__@@@@SAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAPEAUHSTRING__@@@Z; StringTraits<HSTRING__ *>::Promote(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &,HSTRING__ * *)
0x1800c0bfe  mov     ebx, eax
0x1800c0c00  test    eax, eax
0x1800c0c02  jns     short loc_1800C0C6E
0x1800c0c04  mov     this, [rbp+40h]; callerReturnAddress
0x1800c0c08  lea     r8, aOnecoreInterna_6; "onecore\\internal\\com\\inc\\combase\\R"...
0x1800c0c0f  mov     r9d, eax; hr
0x1800c0c12  mov     edx, 887h; lineNumber
0x1800c0c17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0c1c  mov     this, [rbp+result.m_ptr]; string
0x1800c0c20  test    this, this
0x1800c0c23  jz      loc_1800C0D2D
0x1800c0c29  call    cs:__imp_WindowsDeleteString
0x1800c0c2f  jmp     loc_1800C0D2D
0x1800c0c34  lea     rax, [rbp+dataSize]
0x1800c0c38  mov     r9d, 2; pvData
0x1800c0c3e  mov     [rsp+58h+var_28], rax; pszValue
0x1800c0c43  lea     rsi, value
0x1800c0c4a  mov     rax, [rbp+pszValue]
0x1800c0c4e  mov     r8, rsi; dwFlags
0x1800c0c51  mov     this, r15; this
0x1800c0c54  mov     [rsp+58h+pszSubKey], rax; pszSubKey
0x1800c0c59  call    ?GetValue@RegistryKey@@QEBAJPEBG0KPEAKPEAX1@Z; RegistryKey::GetValue(ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x1800c0c5e  mov     ebx, eax
0x1800c0c60  test    eax, eax
0x1800c0c62  jns     short loc_1800C0BED
0x1800c0c64  mov     edx, 885h
0x1800c0c69  jmp     loc_1800C0B9F
0x1800c0c6e  mov     rbx, [rbp+result.m_ptr]
0x1800c0c72  lea     r8, [rbp+hasEmbeddedNull]; __formal
0x1800c0c76  mov     rdx, rbx; hasEmbeddedNull
0x1800c0c79  mov     [rbp+hasEmbeddedNull], r13d
0x1800c0c7d  call    ?VerifyNoEmbeddedNulls@?$StringTraits@PEAUHSTRING__@@@@SAJIPEAUHSTRING__@@PEAH@Z; StringTraits<HSTRING__ *>::VerifyNoEmbeddedNulls(uint,HSTRING__ *,int *)
0x1800c0c82  mov     edi, eax
0x1800c0c84  test    eax, eax
0x1800c0c86  jns     short loc_1800C0CB4
0x1800c0c88  mov     this, [rbp+40h]; callerReturnAddress
0x1800c0c8c  lea     r8, aOnecoreInterna_6; "onecore\\internal\\com\\inc\\combase\\R"...
0x1800c0c93  mov     r9d, eax; hr
0x1800c0c96  mov     edx, 88Ch; lineNumber
0x1800c0c9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0ca0  test    rbx, rbx
0x1800c0ca3  jz      loc_1800C0D2B
0x1800c0ca9  mov     this, rbx; string
0x1800c0cac  call    cs:__imp_WindowsDeleteString
0x1800c0cb2  jmp     short loc_1800C0D2B
0x1800c0cb4  cmp     [rbp+hasEmbeddedNull], r13d
0x1800c0cb8  jz      short loc_1800C0CEA
0x1800c0cba  mov     this, [rbp+40h]; callerReturnAddress
0x1800c0cbe  lea     rax, aValueWs; "value:%ws"
0x1800c0cc5  mov     edi, 8007000Dh
0x1800c0cca  mov     [rsp+58h+pszSubKey], rsi
0x1800c0ccf  mov     r9d, edi; hr
0x1800c0cd2  mov     [rsp+58h+formatString], rax; formatString
0x1800c0cd7  lea     r8, aOnecoreInterna_6; "onecore\\internal\\com\\inc\\combase\\R"...
0x1800c0cde  mov     edx, 88Dh; lineNumber
0x1800c0ce3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800c0ce8  jmp     short loc_1800C0CA0
0x1800c0cea  cmp     dword ptr [rbp+dwType], 2
0x1800c0cee  mov     [r14], rbx
0x1800c0cf1  setz    al
0x1800c0cf4  mov     [r12], al
0x1800c0cf8  jmp     loc_1800C0B68
0x1800c0cfd  mov     edx, 81Eh; lineNumber
0x1800c0d02  mov     this, [rbp+40h]; callerReturnAddress
0x1800c0d06  lea     rax, aValueWs; "value:%ws"
0x1800c0d0d  mov     edi, 8007000Dh
0x1800c0d12  mov     [rsp+58h+pszSubKey], rsi
0x1800c0d17  mov     r9d, edi; hr
0x1800c0d1a  mov     [rsp+58h+formatString], rax; formatString
0x1800c0d1f  lea     r8, aOnecoreInterna_6; "onecore\\internal\\com\\inc\\combase\\R"...
0x1800c0d26  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800c0d2b  mov     ebx, edi
0x1800c0d2d  lea     this, [rbp+buffer]; this
0x1800c0d31  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x1800c0d36  mov     eax, ebx
0x1800c0d38  add     rsp, 58h
0x1800c0d3c  pop     r15
0x1800c0d3e  pop     r14
0x1800c0d40  pop     r13
0x1800c0d42  pop     r12
0x1800c0d44  pop     rdi
0x1800c0d45  pop     rsi
0x1800c0d46  pop     rbx
0x1800c0d47  pop     rbp
0x1800c0d48  retn
```
