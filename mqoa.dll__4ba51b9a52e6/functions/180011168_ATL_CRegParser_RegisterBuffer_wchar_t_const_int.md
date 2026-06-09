# ATL::CRegParser::RegisterBuffer(wchar_t const *,int)

- ea: `0x180011168`
- end: `0x1800112e1`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEB_WH@Z`
- size: `377`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800112e8`

## callees

- `0x18000fe18`
- `0x1800100cc`
- `0x180011168`
- `0x180011504`
- `0x1800124f8`

## import_xrefs

- `msvcrt!free` at `0x1800112c2`
- `msvcrt!free` at `0x1800112c2`
- `msvcrt!malloc` at `0x180011195`
- `msvcrt!malloc` at `0x180011195`
- `KERNEL32!lstrcmpiW` at `0x180011211`
- `KERNEL32!lstrcmpiW` at `0x180011211`
- `ole32!CoTaskMemFree` at `0x1800112b9`
- `ole32!CoTaskMemFree` at `0x1800112b9`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, const wchar_t *a2, int a3)
{
  wchar_t *v6; // rsi
  int Token; // ebx
  void *v9; // r14
  unsigned int i; // ebx
  HKEY v11; // rbp
  __int64 v12; // r15
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  pv = 0;
  v6 = (wchar_t *)malloc(0x2000u);
  if ( !v6 )
    return 2147942414LL;
  Token = ATL::CRegParser::PreProcessBuffer(this, a2, &pv);
  if ( Token >= 0 )
  {
    v9 = pv;
    *(_QWORD *)this = pv;
    while ( 2 )
    {
      if ( **(_WORD **)this )
      {
        Token = ATL::CRegParser::NextToken(this, v6);
        if ( Token >= 0 )
        {
          for ( i = 0; ; ++i )
          {
            if ( i >= 0xE )
              goto LABEL_20;
            if ( !lstrcmpiW(v6, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * (int)i]) )
              break;
          }
          v11 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * (int)i + 1);
          if ( !v11 )
            goto LABEL_20;
          Token = ATL::CRegParser::NextToken(this, v6);
          if ( Token < 0 )
            break;
          if ( *v6 == 123 )
          {
            if ( !a3 )
            {
              Token = ATL::CRegParser::RegisterSubkeys(this, v6, v11, 0, 0);
              if ( Token < 0 )
                break;
              goto LABEL_18;
            }
            v12 = *(_QWORD *)this;
            Token = ATL::CRegParser::RegisterSubkeys(this, v6, v11, a3, 0);
            if ( Token >= 0 )
            {
LABEL_18:
              ATL::CRegParser::SkipWhiteSpace(this);
              continue;
            }
            *(_QWORD *)this = v12;
            ATL::CRegParser::RegisterSubkeys(this, v6, v11, 0, 0);
          }
          else
          {
LABEL_20:
            Token = -2147352567;
          }
        }
      }
      break;
    }
    CoTaskMemFree(v9);
  }
  free(v6);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x180011168  mov     [rsp+arg_0], rbx
0x18001116d  mov     [rsp+arg_8], rbp
0x180011172  push    rsi
0x180011173  push    rdi
0x180011174  push    r12
0x180011176  push    r14
0x180011178  push    r15
0x18001117a  sub     rsp, 30h
0x18001117e  mov     rdi, rcx
0x180011181  mov     [rsp+58h+pv], 0
0x18001118a  mov     ecx, 2000h; Size
0x18001118f  mov     r12d, r8d
0x180011192  mov     rbx, rdx
0x180011195  call    cs:__imp_malloc
0x18001119b  mov     rsi, rax
0x18001119e  test    rax, rax
0x1800111a1  jnz     short loc_1800111AD
0x1800111a3  mov     eax, 8007000Eh
0x1800111a8  jmp     loc_1800112CA
0x1800111ad  lea     r8, [rsp+58h+pv]; wchar_t **
0x1800111b2  mov     rdx, rbx; wchar_t *
0x1800111b5  mov     rcx, rdi; this
0x1800111b8  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEB_WPEAPEA_W@Z; ATL::CRegParser::PreProcessBuffer(wchar_t const *,wchar_t * *)
0x1800111bd  mov     ebx, eax
0x1800111bf  test    eax, eax
0x1800111c1  js      loc_1800112BF
0x1800111c7  mov     r14, [rsp+58h+pv]
0x1800111cc  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEA_W@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::map
0x1800111d3  mov     [rdi], r14
0x1800111d6  mov     rcx, [rdi]
0x1800111d9  xor     eax, eax
0x1800111db  cmp     ax, [rcx]
0x1800111de  jz      loc_1800112B6
0x1800111e4  mov     rdx, rsi; wchar_t *
0x1800111e7  mov     rcx, rdi; this
0x1800111ea  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800111ef  mov     ebx, eax
0x1800111f1  test    eax, eax
0x1800111f3  js      loc_1800112B6
0x1800111f9  xor     ebx, ebx
0x1800111fb  cmp     ebx, 0Eh
0x1800111fe  jnb     loc_1800112B1
0x180011204  movsxd  rbp, ebx
0x180011207  mov     rcx, rsi; lpString1
0x18001120a  add     rbp, rbp
0x18001120d  mov     rdx, [r15+rbp*8]; lpString2
0x180011211  call    cs:__imp_lstrcmpiW
0x180011217  test    eax, eax
0x180011219  jz      short loc_18001121F
0x18001121b  inc     ebx
0x18001121d  jmp     short loc_1800111FB
0x18001121f  mov     rbp, [r15+rbp*8+8]
0x180011224  test    rbp, rbp
0x180011227  jz      loc_1800112B1
0x18001122d  mov     rdx, rsi; wchar_t *
0x180011230  mov     rcx, rdi; this
0x180011233  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180011238  mov     ebx, eax
0x18001123a  test    eax, eax
0x18001123c  js      short loc_1800112B6
0x18001123e  mov     eax, 7Bh ; '{'
0x180011243  cmp     ax, [rsi]
0x180011246  jnz     short loc_1800112B1
0x180011248  mov     [rsp+58h+var_38], 0; int
0x180011250  mov     r8, rbp; HKEY
0x180011253  mov     rdx, rsi; wchar_t *
0x180011256  mov     rcx, rdi; this
0x180011259  test    r12d, r12d
0x18001125c  jz      short loc_180011278
0x18001125e  mov     r15, [rdi]
0x180011261  mov     r9d, r12d; int
0x180011264  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180011269  mov     ebx, eax
0x18001126b  test    eax, eax
0x18001126d  js      short loc_180011293
0x18001126f  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEA_W@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::map
0x180011276  jmp     short loc_180011286
0x180011278  xor     r9d, r9d; int
0x18001127b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180011280  mov     ebx, eax
0x180011282  test    eax, eax
0x180011284  js      short loc_1800112B6
0x180011286  mov     rcx, rdi; this
0x180011289  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18001128e  jmp     loc_1800111D6
0x180011293  xor     r9d, r9d; int
0x180011296  mov     [rdi], r15
0x180011299  mov     r8, rbp; HKEY
0x18001129c  mov     [rsp+58h+var_38], 0; int
0x1800112a4  mov     rdx, rsi; wchar_t *
0x1800112a7  mov     rcx, rdi; this
0x1800112aa  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x1800112af  jmp     short loc_1800112B6
0x1800112b1  mov     ebx, 80020009h
0x1800112b6  mov     rcx, r14; pv
0x1800112b9  call    cs:__imp_CoTaskMemFree
0x1800112bf  mov     rcx, rsi; Block
0x1800112c2  call    cs:__imp_free
0x1800112c8  mov     eax, ebx
0x1800112ca  mov     rbx, [rsp+58h+arg_0]
0x1800112cf  mov     rbp, [rsp+58h+arg_8]
0x1800112d4  add     rsp, 30h
0x1800112d8  pop     r15
0x1800112da  pop     r14
0x1800112dc  pop     r12
0x1800112de  pop     rdi
0x1800112df  pop     rsi
0x1800112e0  retn
```
