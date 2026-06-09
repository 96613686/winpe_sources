# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800048f8`
- end: `0x180004a82`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004a88`

## callees

- `0x180004304`
- `0x1800044a4`
- `0x1800048f8`
- `0x180004c68`
- `0x180011340`
- `0x180011400`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004996`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004996`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004a67`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004a67`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000497d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000497d`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  int v8; // ebx
  HKEY v9; // rsi
  LPCWSTR v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (LPCWSTR)pv;
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
        if ( Token < 0 )
          break;
        v8 = 0;
        while ( lstrcmpiW(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * v8]) )
        {
          if ( (unsigned int)++v8 >= 0xE )
            goto LABEL_7;
        }
        v9 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v8 + 1);
        if ( !v9 )
          goto LABEL_7;
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
        if ( Token < 0 )
          break;
        if ( String1[0] != 123 )
        {
LABEL_7:
          Token = -2147352567;
          break;
        }
        if ( a3 )
        {
          v10 = *this;
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, a3, 0);
          if ( Token < 0 )
          {
            *this = v10;
            ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, 0, 0);
            break;
          }
        }
        else
        {
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, 0, 0);
          if ( Token < 0 )
            break;
        }
        while ( **this == 9 || **this == 10 || **this == 13 || **this == 32 )
          *this = CharNextW(*this);
      }
      while ( **this );
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x1800048f8  push    rbx
0x1800048fa  push    rbp
0x1800048fb  push    rsi
0x1800048fc  push    rdi
0x1800048fd  push    r13
0x1800048ff  push    r14
0x180004901  push    r15
0x180004903  mov     eax, 2050h
0x180004908  call    _alloca_probe
0x18000490d  sub     rsp, rax
0x180004910  mov     rax, cs:__security_cookie
0x180004917  xor     rax, rsp
0x18000491a  mov     [rsp+2088h+var_48], rax
0x180004922  mov     r15d, r8d
0x180004925  mov     [rsp+2088h+pv], 0
0x18000492e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180004933  mov     rdi, rcx
0x180004936  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000493b  mov     ebx, eax
0x18000493d  test    eax, eax
0x18000493f  js      short loc_18000499E
0x180004941  mov     rbp, [rsp+2088h+pv]
0x180004946  xor     eax, eax
0x180004948  mov     [rdi], rbp
0x18000494b  cmp     ax, [rbp+0]
0x18000494f  jz      short loc_180004993
0x180004951  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180004958  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000495d  mov     rcx, rdi; this
0x180004960  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004965  mov     ebx, eax
0x180004967  test    eax, eax
0x180004969  js      short loc_180004993
0x18000496b  xor     ebx, ebx
0x18000496d  movsxd  rsi, ebx
0x180004970  lea     rcx, [rsp+2088h+String1]; lpString1
0x180004975  add     rsi, rsi
0x180004978  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000497d  call    cs:__imp_lstrcmpiW
0x180004983  test    eax, eax
0x180004985  jz      short loc_1800049C0
0x180004987  inc     ebx
0x180004989  cmp     ebx, 0Eh
0x18000498c  jb      short loc_18000496D
0x18000498e  mov     ebx, 80020009h
0x180004993  mov     rcx, rbp; pv
0x180004996  call    cs:__imp_CoTaskMemFree
0x18000499c  mov     eax, ebx
0x18000499e  mov     rcx, [rsp+2088h+var_48]
0x1800049a6  xor     rcx, rsp; StackCookie
0x1800049a9  call    __security_check_cookie
0x1800049ae  add     rsp, 2050h
0x1800049b5  pop     r15
0x1800049b7  pop     r14
0x1800049b9  pop     r13
0x1800049bb  pop     rdi
0x1800049bc  pop     rsi
0x1800049bd  pop     rbp
0x1800049be  pop     rbx
0x1800049bf  retn
0x1800049c0  mov     rsi, [r13+rsi*8+8]
0x1800049c5  test    rsi, rsi
0x1800049c8  jz      short loc_18000498E
0x1800049ca  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800049cf  mov     rcx, rdi; this
0x1800049d2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800049d7  mov     ebx, eax
0x1800049d9  test    eax, eax
0x1800049db  js      short loc_180004993
0x1800049dd  mov     eax, 7Bh ; '{'
0x1800049e2  cmp     ax, [rsp+2088h+String1]
0x1800049e7  jnz     short loc_18000498E
0x1800049e9  mov     [rsp+2088h+var_2068], 0; int
0x1800049f1  mov     r8, rsi; HKEY
0x1800049f4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800049f9  mov     rcx, rdi; this
0x1800049fc  test    r15d, r15d
0x1800049ff  jz      short loc_180004A35
0x180004a01  mov     r14, [rdi]
0x180004a04  mov     r9d, r15d; int
0x180004a07  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004a0c  mov     ebx, eax
0x180004a0e  test    eax, eax
0x180004a10  jns     short loc_180004A47
0x180004a12  xor     r9d, r9d; int
0x180004a15  mov     [rdi], r14
0x180004a18  mov     r8, rsi; HKEY
0x180004a1b  mov     [rsp+2088h+var_2068], 0; int
0x180004a23  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004a28  mov     rcx, rdi; this
0x180004a2b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004a30  jmp     loc_180004993
0x180004a35  xor     r9d, r9d; int
0x180004a38  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004a3d  mov     ebx, eax
0x180004a3f  test    eax, eax
0x180004a41  js      loc_180004993
0x180004a47  mov     r8, [rdi]
0x180004a4a  movzx   edx, word ptr [r8]
0x180004a4e  mov     ecx, edx
0x180004a50  sub     ecx, 9
0x180004a53  jz      short loc_180004A64
0x180004a55  sub     ecx, 1
0x180004a58  jz      short loc_180004A64
0x180004a5a  sub     ecx, 3
0x180004a5d  jz      short loc_180004A64
0x180004a5f  cmp     ecx, 13h
0x180004a62  jnz     short loc_180004A72
0x180004a64  mov     rcx, r8; lpsz
0x180004a67  call    cs:__imp_CharNextW
0x180004a6d  mov     [rdi], rax
0x180004a70  jmp     short loc_180004A47
0x180004a72  xor     eax, eax
0x180004a74  cmp     ax, dx
0x180004a77  jnz     loc_180004958
0x180004a7d  jmp     loc_180004993
```
