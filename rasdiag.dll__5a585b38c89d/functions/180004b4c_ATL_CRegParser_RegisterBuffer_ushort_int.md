# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180004b4c`
- end: `0x180004ce9`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `413`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004cf0`

## callees

- `0x1800044c4`
- `0x180004694`
- `0x180004b4c`
- `0x180004ef8`
- `0x18000df10`
- `0x18000dfd0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180004bd1`
- `KERNEL32!lstrcmpiW` at `0x180004bd1`
- `USER32!CharNextW` at `0x180004cc8`
- `USER32!CharNextW` at `0x180004cc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004bf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004bf0`

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
        Token = ATL::CRegParser::NextToken(this, String1);
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
        Token = ATL::CRegParser::NextToken(this, String1);
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
0x180004b4c  push    rbx
0x180004b4e  push    rbp
0x180004b4f  push    rsi
0x180004b50  push    rdi
0x180004b51  push    r13
0x180004b53  push    r14
0x180004b55  push    r15
0x180004b57  mov     eax, 2050h
0x180004b5c  call    _alloca_probe
0x180004b61  sub     rsp, rax
0x180004b64  mov     rax, cs:__security_cookie
0x180004b6b  xor     rax, rsp
0x180004b6e  mov     [rsp+2088h+var_48], rax
0x180004b76  mov     r15d, r8d
0x180004b79  mov     [rsp+2088h+pv], 0
0x180004b82  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180004b87  mov     rdi, rcx
0x180004b8a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180004b8f  mov     ebx, eax
0x180004b91  test    eax, eax
0x180004b93  js      short loc_180004BFE
0x180004b95  mov     rbp, [rsp+2088h+pv]
0x180004b9a  xor     eax, eax
0x180004b9c  mov     [rdi], rbp
0x180004b9f  cmp     ax, [rbp+0]
0x180004ba3  jz      short loc_180004BED
0x180004ba5  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180004bac  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004bb1  mov     rcx, rdi; this
0x180004bb4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004bb9  mov     ebx, eax
0x180004bbb  test    eax, eax
0x180004bbd  js      short loc_180004BED
0x180004bbf  xor     ebx, ebx
0x180004bc1  movsxd  rsi, ebx
0x180004bc4  lea     rcx, [rsp+2088h+String1]; lpString1
0x180004bc9  add     rsi, rsi
0x180004bcc  mov     rdx, [r13+rsi*8+0]; lpString2
0x180004bd1  call    cs:__imp_lstrcmpiW
0x180004bd8  nop     dword ptr [rax+rax+00h]
0x180004bdd  test    eax, eax
0x180004bdf  jz      short loc_180004C21
0x180004be1  inc     ebx
0x180004be3  cmp     ebx, 0Eh
0x180004be6  jb      short loc_180004BC1
0x180004be8  mov     ebx, 80020009h
0x180004bed  mov     rcx, rbp; pv
0x180004bf0  call    cs:__imp_CoTaskMemFree
0x180004bf7  nop     dword ptr [rax+rax+00h]
0x180004bfc  mov     eax, ebx
0x180004bfe  mov     rcx, [rsp+2088h+var_48]
0x180004c06  xor     rcx, rsp; StackCookie
0x180004c09  call    __security_check_cookie
0x180004c0e  add     rsp, 2050h
0x180004c15  pop     r15
0x180004c17  pop     r14
0x180004c19  pop     r13
0x180004c1b  pop     rdi
0x180004c1c  pop     rsi
0x180004c1d  pop     rbp
0x180004c1e  pop     rbx
0x180004c1f  retn
0x180004c21  mov     rsi, [r13+rsi*8+8]
0x180004c26  test    rsi, rsi
0x180004c29  jz      short loc_180004BE8
0x180004c2b  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004c30  mov     rcx, rdi; this
0x180004c33  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004c38  mov     ebx, eax
0x180004c3a  test    eax, eax
0x180004c3c  js      short loc_180004BED
0x180004c3e  mov     eax, 7Bh ; '{'
0x180004c43  cmp     ax, [rsp+2088h+String1]
0x180004c48  jnz     short loc_180004BE8
0x180004c4a  mov     [rsp+2088h+var_2068], 0; int
0x180004c52  mov     r8, rsi; HKEY
0x180004c55  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004c5a  mov     rcx, rdi; this
0x180004c5d  test    r15d, r15d
0x180004c60  jz      short loc_180004C96
0x180004c62  mov     r14, [rdi]
0x180004c65  mov     r9d, r15d; int
0x180004c68  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004c6d  mov     ebx, eax
0x180004c6f  test    eax, eax
0x180004c71  jns     short loc_180004CA8
0x180004c73  xor     r9d, r9d; int
0x180004c76  mov     [rdi], r14
0x180004c79  mov     r8, rsi; HKEY
0x180004c7c  mov     [rsp+2088h+var_2068], 0; int
0x180004c84  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004c89  mov     rcx, rdi; this
0x180004c8c  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004c91  jmp     loc_180004BED
0x180004c96  xor     r9d, r9d; int
0x180004c99  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004c9e  mov     ebx, eax
0x180004ca0  test    eax, eax
0x180004ca2  js      loc_180004BED
0x180004ca8  mov     r8, [rdi]
0x180004cab  movzx   edx, word ptr [r8]
0x180004caf  mov     ecx, edx
0x180004cb1  sub     ecx, 9
0x180004cb4  jz      short loc_180004CC5
0x180004cb6  sub     ecx, 1
0x180004cb9  jz      short loc_180004CC5
0x180004cbb  sub     ecx, 3
0x180004cbe  jz      short loc_180004CC5
0x180004cc0  cmp     ecx, 13h
0x180004cc3  jnz     short loc_180004CD9
0x180004cc5  mov     rcx, r8; lpsz
0x180004cc8  call    cs:__imp_CharNextW
0x180004ccf  nop     dword ptr [rax+rax+00h]
0x180004cd4  mov     [rdi], rax
0x180004cd7  jmp     short loc_180004CA8
0x180004cd9  xor     eax, eax
0x180004cdb  cmp     ax, dx
0x180004cde  jnz     loc_180004BAC
0x180004ce4  jmp     loc_180004BED
```
