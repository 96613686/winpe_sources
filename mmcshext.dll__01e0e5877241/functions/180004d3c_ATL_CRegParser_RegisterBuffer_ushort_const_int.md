# ATL::CRegParser::RegisterBuffer(ushort const *,int)

- ea: `0x180004d3c`
- end: `0x180004ece`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEBGH@Z`
- size: `402`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180004ed4`

## callees

- `0x180004598`
- `0x18000473c`
- `0x180004d3c`
- `0x180005130`

## import_xrefs

- `msvcrt!malloc` at `0x180004d69`
- `msvcrt!malloc` at `0x180004d69`
- `msvcrt!free` at `0x180004ded`
- `msvcrt!free` at `0x180004ded`
- `USER32!CharNextW` at `0x180004e91`
- `USER32!CharNextW` at `0x180004e91`
- `KERNEL32!lstrcmpiW` at `0x180004dcb`
- `KERNEL32!lstrcmpiW` at `0x180004dcb`
- `ole32!CoTaskMemFree` at `0x180004de4`
- `ole32!CoTaskMemFree` at `0x180004de4`

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
0x180004d3c  mov     [rsp+arg_0], rbx
0x180004d41  mov     [rsp+arg_8], rbp
0x180004d46  push    rsi
0x180004d47  push    rdi
0x180004d48  push    r12
0x180004d4a  push    r14
0x180004d4c  push    r15
0x180004d4e  sub     rsp, 30h
0x180004d52  mov     rsi, rcx
0x180004d55  mov     [rsp+58h+pv], 0
0x180004d5e  mov     ecx, 2000h; Size
0x180004d63  mov     r12d, r8d
0x180004d66  mov     rbx, rdx
0x180004d69  call    cs:__imp_malloc
0x180004d6f  mov     rdi, rax
0x180004d72  test    rax, rax
0x180004d75  jnz     short loc_180004D7E
0x180004d77  mov     eax, 8007000Eh
0x180004d7c  jmp     short loc_180004DF5
0x180004d7e  lea     r8, [rsp+58h+pv]; unsigned __int16 **
0x180004d83  mov     rdx, rbx; unsigned __int16 *
0x180004d86  mov     rcx, rsi; this
0x180004d89  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)
0x180004d8e  mov     ebx, eax
0x180004d90  test    eax, eax
0x180004d92  js      short loc_180004DEA
0x180004d94  mov     r14, [rsp+58h+pv]
0x180004d99  xor     eax, eax
0x180004d9b  mov     [rsi], r14
0x180004d9e  cmp     ax, [r14]
0x180004da2  jz      short loc_180004DE1
0x180004da4  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180004dab  mov     rdx, rdi; unsigned __int16 *
0x180004dae  mov     rcx, rsi; this
0x180004db1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004db6  mov     ebx, eax
0x180004db8  test    eax, eax
0x180004dba  js      short loc_180004DE1
0x180004dbc  xor     ebx, ebx
0x180004dbe  movsxd  rbp, ebx
0x180004dc1  mov     rcx, rdi; lpString1
0x180004dc4  add     rbp, rbp
0x180004dc7  mov     rdx, [r15+rbp*8]; lpString2
0x180004dcb  call    cs:__imp_lstrcmpiW
0x180004dd1  test    eax, eax
0x180004dd3  jz      short loc_180004E0C
0x180004dd5  inc     ebx
0x180004dd7  cmp     ebx, 0Eh
0x180004dda  jb      short loc_180004DBE
0x180004ddc  mov     ebx, 80020009h
0x180004de1  mov     rcx, r14; pv
0x180004de4  call    cs:__imp_CoTaskMemFree
0x180004dea  mov     rcx, rdi; Block
0x180004ded  call    cs:__imp_free
0x180004df3  mov     eax, ebx
0x180004df5  mov     rbx, [rsp+58h+arg_0]
0x180004dfa  mov     rbp, [rsp+58h+arg_8]
0x180004dff  add     rsp, 30h
0x180004e03  pop     r15
0x180004e05  pop     r14
0x180004e07  pop     r12
0x180004e09  pop     rdi
0x180004e0a  pop     rsi
0x180004e0b  retn
0x180004e0c  mov     rbp, [r15+rbp*8+8]
0x180004e11  test    rbp, rbp
0x180004e14  jz      short loc_180004DDC
0x180004e16  mov     rdx, rdi; unsigned __int16 *
0x180004e19  mov     rcx, rsi; this
0x180004e1c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004e21  mov     ebx, eax
0x180004e23  test    eax, eax
0x180004e25  js      short loc_180004DE1
0x180004e27  mov     eax, 7Bh ; '{'
0x180004e2c  cmp     ax, [rdi]
0x180004e2f  jnz     short loc_180004DDC
0x180004e31  mov     [rsp+58h+var_38], 0; int
0x180004e39  mov     r8, rbp; HKEY
0x180004e3c  mov     rdx, rdi; unsigned __int16 *
0x180004e3f  mov     rcx, rsi; this
0x180004e42  test    r12d, r12d
0x180004e45  jz      short loc_180004E61
0x180004e47  mov     r15, [rsi]
0x180004e4a  mov     r9d, r12d; int
0x180004e4d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004e52  mov     ebx, eax
0x180004e54  test    eax, eax
0x180004e56  js      short loc_180004EAD
0x180004e58  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180004e5f  jmp     short loc_180004E73
0x180004e61  xor     r9d, r9d; int
0x180004e64  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004e69  mov     ebx, eax
0x180004e6b  test    eax, eax
0x180004e6d  js      loc_180004DE1
0x180004e73  mov     rcx, [rsi]; lpsz
0x180004e76  movzx   r8d, word ptr [rcx]
0x180004e7a  mov     edx, r8d
0x180004e7d  sub     edx, 9
0x180004e80  jz      short loc_180004E91
0x180004e82  sub     edx, 1
0x180004e85  jz      short loc_180004E91
0x180004e87  sub     edx, 3
0x180004e8a  jz      short loc_180004E91
0x180004e8c  cmp     edx, 13h
0x180004e8f  jnz     short loc_180004E9C
0x180004e91  call    cs:__imp_CharNextW
0x180004e97  mov     [rsi], rax
0x180004e9a  jmp     short loc_180004E73
0x180004e9c  xor     eax, eax
0x180004e9e  cmp     ax, r8w
0x180004ea2  jnz     loc_180004DAB
0x180004ea8  jmp     loc_180004DE1
0x180004ead  xor     r9d, r9d; int
0x180004eb0  mov     [rsi], r15
0x180004eb3  mov     r8, rbp; HKEY
0x180004eb6  mov     [rsp+58h+var_38], 0; int
0x180004ebe  mov     rdx, rdi; unsigned __int16 *
0x180004ec1  mov     rcx, rsi; this
0x180004ec4  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004ec9  jmp     loc_180004DE1
```
