# CRegistry::GetValue(wchar_t const *,CLMString &)

- ea: `0x18003665c`
- end: `0x1800368ab`
- name: `?GetValue@CRegistry@@QEAAHPEB_WAEAVCLMString@@@Z`
- size: `591`
- prototype: `int(CRegistry *__hidden this, const wchar_t *, struct CLMString *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017200`

## callees

- `0x180004dc0`
- `0x180006270`
- `0x180016360`
- `0x18001869c`
- `0x18003665c`
- `0x180036be0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036686`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800366a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036686`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800366a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800366da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800367b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800366da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800367b9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180036746`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180036746`

## string_xrefs

- `0x18003671b`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x180036771`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x1800367d8`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`

## pseudocode

```c
__int64 __fastcall CRegistry::GetValue(CRegistry *this, const wchar_t *a2, struct CLMString *a3)
{
  HKEY v5; // rcx
  DWORD v6; // ecx
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  WCHAR *Buffer; // rax
  DWORD v10; // eax
  unsigned int v11; // eax
  BYTE *v12; // rax
  unsigned __int64 v13; // rdi
  wchar_t *v14; // rax
  BYTE *v15; // rdx
  unsigned int v16; // r8d
  unsigned __int64 v17; // rdi
  __int64 v18; // rcx
  wchar_t *v19; // rcx
  __int64 v20; // r9
  unsigned int lpData; // [rsp+20h] [rbp-258h]
  DWORD cbData; // [rsp+30h] [rbp-248h] BYREF
  DWORD Type[3]; // [rsp+34h] [rbp-244h] BYREF
  WCHAR Data[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  SetLastError(0);
  Type[0] = 0;
  v5 = (HKEY)*((_QWORD *)this + 22);
  if ( !v5 )
  {
    v6 = 6;
LABEL_3:
    SetLastError(v6);
    return 0;
  }
  cbData = 520;
  v7 = RegQueryValueExW(v5, L"Content Type", 0, Type, (LPBYTE)Data, &cbData);
  v8 = v7;
  if ( v7 && v7 != 234 || Type[0] - 1 > 1 && Type[0] != 7 )
  {
    v6 = v7;
    goto LABEL_3;
  }
  try
  {
    if ( Type[0] == 2 )
    {
      if ( v7 == 234 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2E3,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
          (const char *)0xCE,
          lpData);
      Buffer = CLMString::GetBuffer(a3, 260);
      v10 = ExpandEnvironmentStringsW(Data, Buffer, 0x104u);
      cbData = v10;
      if ( v10 - 1 > 0x102 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2E9,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
          (const char *)0xCE,
          lpData);
      v11 = 2 * v10;
      cbData = v11;
    }
    else
    {
      if ( v7 == 234 )
      {
        v12 = (BYTE *)CLMString::GetBuffer(a3, cbData >> 1);
        v8 = RegQueryValueExW(*((HKEY *)this + 22), L"Content Type", 0, Type, v12, &cbData);
      }
      else
      {
        v13 = cbData;
        v14 = CLMString::GetBuffer(a3, cbData >> 1);
        v17 = v13 >> 1;
        if ( v17 )
        {
          v18 = 2147483646;
          v15 = (BYTE *)Data;
          do
          {
            if ( !v18 )
              break;
            v16 = *(unsigned __int16 *)v15;
            if ( !(_WORD)v16 )
              break;
            v15 += 2;
            *v14++ = v16;
            --v18;
            --v17;
          }
          while ( v17 );
          v19 = v14 - 1;
          if ( v17 )
            v19 = v14;
          *v19 = 0;
          v20 = v17 == 0 ? 0x8007007A : 0;
        }
        else
        {
          v20 = 2147942487LL;
        }
        if ( (int)v20 < 0 )
          wil::details::in1diag3::_Throw_Hr(retaddr, v15, v16, (const char *)v20, lpData);
      }
      v11 = cbData;
    }
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2FD,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
        (const char *)v8,
        lpData);
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      770,
      "onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx");
  }
  cbData = v11 >> 1;
  CLMString::Truncate(a3, v11 >> 1 != 0 ? (v11 >> 1) - 1 : 0);
  return 1;
}

```

## disassembly

```asm
0x18003665c  mov     [rsp+arg_8], rbx
0x180036661  push    rsi
0x180036662  push    rdi
0x180036663  push    r14
0x180036665  sub     rsp, 260h
0x18003666c  mov     rax, cs:__security_cookie
0x180036673  xor     rax, rsp
0x180036676  mov     [rsp+278h+var_28], rax
0x18003667e  mov     rsi, r8
0x180036681  mov     rdi, rcx
0x180036684  xor     ecx, ecx; dwErrCode
0x180036686  call    cs:__imp_SetLastError
0x18003668c  xor     r14d, r14d
0x18003668f  mov     [rsp+278h+Type], r14d
0x180036694  mov     rcx, [rdi+0B0h]; hKey
0x18003669b  test    rcx, rcx
0x18003669e  jnz     short loc_1800366AF
0x1800366a0  lea     ecx, [r14+6]; dwErrCode
0x1800366a4  call    cs:__imp_SetLastError
0x1800366aa  jmp     loc_180036885
0x1800366af  mov     [rsp+278h+cbData], 208h
0x1800366b7  lea     rax, [rsp+278h+cbData]
0x1800366bc  mov     [rsp+278h+lpcbData], rax; lpcbData
0x1800366c1  lea     rax, [rsp+278h+Data]
0x1800366c6  mov     [rsp+278h+lpData], rax; int
0x1800366cb  lea     r9, [rsp+278h+Type]; lpType
0x1800366d0  xor     r8d, r8d; lpReserved
0x1800366d3  lea     rdx, ValueName; "Content Type"
0x1800366da  call    cs:__imp_RegQueryValueExW
0x1800366e0  mov     ebx, eax
0x1800366e2  mov     ecx, 0EAh
0x1800366e7  test    eax, eax
0x1800366e9  jz      short loc_1800366EF
0x1800366eb  cmp     eax, ecx
0x1800366ed  jnz     short loc_180036700
0x1800366ef  mov     edx, [rsp+278h+Type]
0x1800366f3  lea     eax, [rdx-1]
0x1800366f6  cmp     eax, 1
0x1800366f9  jbe     short loc_180036704
0x1800366fb  cmp     edx, 7
0x1800366fe  jz      short loc_180036704
0x180036700  mov     ecx, ebx
0x180036702  jmp     short loc_1800366A4
0x180036704  cmp     edx, 2
0x180036707  jnz     short loc_180036782
0x180036709  cmp     ebx, ecx
0x18003670b  jnz     short loc_18003672C
0x18003670d  mov     rcx, [rsp+278h]; this
0x180036715  mov     r9d, 0CEh; char *
0x18003671b  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\com"...
0x180036722  mov     edx, 2E3h; void *
0x180036727  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003672c  mov     edi, 104h
0x180036731  mov     edx, edi; int
0x180036733  mov     rcx, rsi; this
0x180036736  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x18003673b  mov     r8d, edi; nSize
0x18003673e  mov     rdx, rax; lpDst
0x180036741  lea     rcx, [rsp+278h+Data]; lpSrc
0x180036746  call    cs:__imp_ExpandEnvironmentStringsW
0x18003674c  mov     [rsp+278h+cbData], eax
0x180036750  lea     ecx, [rax-1]
0x180036753  cmp     ecx, 102h
0x180036759  ja      short loc_180036763
0x18003675b  add     eax, eax
0x18003675d  mov     [rsp+278h+cbData], eax
0x180036761  jmp     short loc_1800367C5
0x180036763  mov     rcx, [rsp+278h]; this
0x18003676b  mov     r9d, 0CEh; char *
0x180036771  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\com"...
0x180036778  mov     edx, 2E9h; void *
0x18003677d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180036782  cmp     ebx, ecx
0x180036784  mov     rcx, rsi; this
0x180036787  jnz     short loc_1800367E9
0x180036789  mov     edx, [rsp+278h+cbData]
0x18003678d  shr     edx, 1; int
0x18003678f  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180036794  lea     rcx, [rsp+278h+cbData]
0x180036799  mov     [rsp+278h+lpcbData], rcx; lpcbData
0x18003679e  mov     [rsp+278h+lpData], rax; unsigned int
0x1800367a3  lea     r9, [rsp+278h+Type]; lpType
0x1800367a8  xor     r8d, r8d; lpReserved
0x1800367ab  lea     rdx, ValueName; "Content Type"
0x1800367b2  mov     rcx, [rdi+0B0h]; hKey
0x1800367b9  call    cs:__imp_RegQueryValueExW
0x1800367bf  mov     ebx, eax
0x1800367c1  mov     eax, [rsp+278h+cbData]
0x1800367c5  test    ebx, ebx
0x1800367c7  jz      loc_180036867
0x1800367cd  mov     rcx, [rsp+278h]; this
0x1800367d5  mov     r9d, ebx; char *
0x1800367d8  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800367df  mov     edx, 2FDh; void *
0x1800367e4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800367e9  mov     edx, [rsp+278h+cbData]
0x1800367ed  mov     edi, edx
0x1800367ef  shr     edx, 1; int
0x1800367f1  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x1800367f6  shr     rdi, 1
0x1800367f9  jz      short loc_18003684A
0x1800367fb  mov     ecx, 7FFFFFFEh
0x180036800  lea     rdx, [rsp+278h+Data]
0x180036805  test    rcx, rcx
0x180036808  jz      short loc_180036829
0x18003680a  movzx   r8d, word ptr [rdx]
0x18003680e  test    r8w, r8w
0x180036812  jz      short loc_180036829
0x180036814  add     rdx, 2
0x180036818  mov     [rax], r8w
0x18003681c  add     rax, 2
0x180036820  dec     rcx
0x180036823  sub     rdi, 1
0x180036827  jnz     short loc_180036805
0x180036829  lea     rcx, [rax-2]
0x18003682d  test    rdi, rdi
0x180036830  cmovnz  rcx, rax
0x180036834  mov     [rcx], r14w
0x180036838  neg     rdi
0x18003683b  sbb     r9d, r9d
0x18003683e  not     r9d
0x180036841  and     r9d, 8007007Ah
0x180036848  jmp     short loc_180036850
0x18003684a  mov     r9d, 80070057h; char *
0x180036850  mov     rcx, [rsp+278h]; this
0x180036858  test    r9d, r9d
0x18003685b  jns     loc_1800367C1
0x180036861  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180036867  shr     eax, 1
0x180036869  mov     [rsp+278h+cbData], eax
0x18003686d  lea     ecx, [rax-1]
0x180036870  neg     eax
0x180036872  sbb     edx, edx
0x180036874  and     edx, ecx; unsigned int
0x180036876  mov     rcx, rsi; this
0x180036879  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x18003687e  mov     eax, 1
0x180036883  jmp     short loc_180036887
0x180036885  xor     eax, eax
0x180036887  mov     rcx, [rsp+278h+var_28]
0x18003688f  xor     rcx, rsp; StackCookie
0x180036892  call    __security_check_cookie
0x180036897  mov     rbx, [rsp+278h+arg_8]
0x18003689f  add     rsp, 260h
0x1800368a6  pop     r14
0x1800368a8  pop     rdi
0x1800368a9  pop     rsi
0x1800368aa  retn
```
