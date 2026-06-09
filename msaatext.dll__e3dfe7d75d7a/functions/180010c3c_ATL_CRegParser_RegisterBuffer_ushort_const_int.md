# ATL::CRegParser::RegisterBuffer(ushort const *,int)

- ea: `0x180010c3c`
- end: `0x180010dce`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEBGH@Z`
- size: `402`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010dd4`

## callees

- `0x1800101d0`
- `0x18001036c`
- `0x180010c3c`
- `0x180011038`

## import_xrefs

- `msvcrt!free` at `0x180010ced`
- `msvcrt!free` at `0x180010ced`
- `msvcrt!malloc` at `0x180010c69`
- `msvcrt!malloc` at `0x180010c69`
- `USER32!CharNextW` at `0x180010d91`
- `USER32!CharNextW` at `0x180010d91`
- `KERNEL32!lstrcmpiW` at `0x180010ccb`
- `KERNEL32!lstrcmpiW` at `0x180010ccb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010ce4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010ce4`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, WCHAR *a2, int a3)
{
  unsigned __int16 *v6; // rdi
  int Token; // ebx
  _WORD *v9; // r14
  int v10; // ebx
  HKEY v11; // rbp
  LPCWSTR v12; // r15
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  pv = 0;
  v6 = (unsigned __int16 *)malloc(0x2000u);
  if ( !v6 )
    return 2147942414LL;
  Token = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  if ( Token >= 0 )
  {
    v9 = pv;
    *this = (LPCWSTR)pv;
    if ( *v9 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, v6);
        if ( Token < 0 )
          break;
        v10 = 0;
        while ( lstrcmpiW(v6, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * v10]) )
        {
          if ( (unsigned int)++v10 >= 0xE )
            goto LABEL_9;
        }
        v11 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v10 + 1);
        if ( !v11 )
          goto LABEL_9;
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, v6);
        if ( Token < 0 )
          break;
        if ( *v6 != 123 )
        {
LABEL_9:
          Token = -2147352567;
          break;
        }
        if ( a3 )
        {
          v12 = *this;
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, v6, v11, a3, 0);
          if ( Token < 0 )
          {
            *this = v12;
            ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, v6, v11, 0, 0);
            break;
          }
        }
        else
        {
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, v6, v11, 0, 0);
          if ( Token < 0 )
            break;
        }
        while ( **this == 9 || **this == 10 || **this == 13 || **this == 32 )
          *this = CharNextW(*this);
      }
      while ( **this );
    }
    CoTaskMemFree(v9);
  }
  free(v6);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x180010c3c  mov     [rsp+arg_0], rbx
0x180010c41  mov     [rsp+arg_8], rbp
0x180010c46  push    rsi
0x180010c47  push    rdi
0x180010c48  push    r12
0x180010c4a  push    r14
0x180010c4c  push    r15
0x180010c4e  sub     rsp, 30h
0x180010c52  mov     rsi, rcx
0x180010c55  mov     [rsp+58h+pv], 0
0x180010c5e  mov     ecx, 2000h; Size
0x180010c63  mov     r12d, r8d
0x180010c66  mov     rbx, rdx
0x180010c69  call    cs:__imp_malloc
0x180010c6f  mov     rdi, rax
0x180010c72  test    rax, rax
0x180010c75  jnz     short loc_180010C7E
0x180010c77  mov     eax, 8007000Eh
0x180010c7c  jmp     short loc_180010CF5
0x180010c7e  lea     r8, [rsp+58h+pv]; unsigned __int16 **
0x180010c83  mov     rdx, rbx; unsigned __int16 *
0x180010c86  mov     rcx, rsi; this
0x180010c89  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)
0x180010c8e  mov     ebx, eax
0x180010c90  test    eax, eax
0x180010c92  js      short loc_180010CEA
0x180010c94  mov     r14, [rsp+58h+pv]
0x180010c99  xor     eax, eax
0x180010c9b  mov     [rsi], r14
0x180010c9e  cmp     ax, [r14]
0x180010ca2  jz      short loc_180010CE1
0x180010ca4  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180010cab  mov     rdx, rdi; unsigned __int16 *
0x180010cae  mov     rcx, rsi; this
0x180010cb1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180010cb6  mov     ebx, eax
0x180010cb8  test    eax, eax
0x180010cba  js      short loc_180010CE1
0x180010cbc  xor     ebx, ebx
0x180010cbe  movsxd  rbp, ebx
0x180010cc1  mov     rcx, rdi; lpString1
0x180010cc4  add     rbp, rbp
0x180010cc7  mov     rdx, [r15+rbp*8]; lpString2
0x180010ccb  call    cs:__imp_lstrcmpiW
0x180010cd1  test    eax, eax
0x180010cd3  jz      short loc_180010D0C
0x180010cd5  inc     ebx
0x180010cd7  cmp     ebx, 0Eh
0x180010cda  jb      short loc_180010CBE
0x180010cdc  mov     ebx, 80020009h
0x180010ce1  mov     rcx, r14; pv
0x180010ce4  call    cs:__imp_CoTaskMemFree
0x180010cea  mov     rcx, rdi; Block
0x180010ced  call    cs:__imp_free
0x180010cf3  mov     eax, ebx
0x180010cf5  mov     rbx, [rsp+58h+arg_0]
0x180010cfa  mov     rbp, [rsp+58h+arg_8]
0x180010cff  add     rsp, 30h
0x180010d03  pop     r15
0x180010d05  pop     r14
0x180010d07  pop     r12
0x180010d09  pop     rdi
0x180010d0a  pop     rsi
0x180010d0b  retn
0x180010d0c  mov     rbp, [r15+rbp*8+8]
0x180010d11  test    rbp, rbp
0x180010d14  jz      short loc_180010CDC
0x180010d16  mov     rdx, rdi; unsigned __int16 *
0x180010d19  mov     rcx, rsi; this
0x180010d1c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180010d21  mov     ebx, eax
0x180010d23  test    eax, eax
0x180010d25  js      short loc_180010CE1
0x180010d27  mov     eax, 7Bh ; '{'
0x180010d2c  cmp     ax, [rdi]
0x180010d2f  jnz     short loc_180010CDC
0x180010d31  mov     [rsp+58h+var_38], 0; int
0x180010d39  mov     r8, rbp; HKEY
0x180010d3c  mov     rdx, rdi; unsigned __int16 *
0x180010d3f  mov     rcx, rsi; this
0x180010d42  test    r12d, r12d
0x180010d45  jz      short loc_180010D61
0x180010d47  mov     r15, [rsi]
0x180010d4a  mov     r9d, r12d; int
0x180010d4d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180010d52  mov     ebx, eax
0x180010d54  test    eax, eax
0x180010d56  js      short loc_180010DAD
0x180010d58  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180010d5f  jmp     short loc_180010D73
0x180010d61  xor     r9d, r9d; int
0x180010d64  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180010d69  mov     ebx, eax
0x180010d6b  test    eax, eax
0x180010d6d  js      loc_180010CE1
0x180010d73  mov     rcx, [rsi]; lpsz
0x180010d76  movzx   r8d, word ptr [rcx]
0x180010d7a  mov     edx, r8d
0x180010d7d  sub     edx, 9
0x180010d80  jz      short loc_180010D91
0x180010d82  sub     edx, 1
0x180010d85  jz      short loc_180010D91
0x180010d87  sub     edx, 3
0x180010d8a  jz      short loc_180010D91
0x180010d8c  cmp     edx, 13h
0x180010d8f  jnz     short loc_180010D9C
0x180010d91  call    cs:__imp_CharNextW
0x180010d97  mov     [rsi], rax
0x180010d9a  jmp     short loc_180010D73
0x180010d9c  xor     eax, eax
0x180010d9e  cmp     ax, r8w
0x180010da2  jnz     loc_180010CAB
0x180010da8  jmp     loc_180010CE1
0x180010dad  xor     r9d, r9d; int
0x180010db0  mov     [rsi], r15
0x180010db3  mov     r8, rbp; HKEY
0x180010db6  mov     [rsp+58h+var_38], 0; int
0x180010dbe  mov     rdx, rdi; unsigned __int16 *
0x180010dc1  mov     rcx, rsi; this
0x180010dc4  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180010dc9  jmp     loc_180010CE1
```
