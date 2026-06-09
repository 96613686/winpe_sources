# ATL::CRegParser::RegisterBuffer(ushort const *,int)

- ea: `0x1800125a8`
- end: `0x180012721`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEBGH@Z`
- size: `377`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180012e94`

## callees

- `0x18000f204`
- `0x18000f368`
- `0x18000f9d8`
- `0x1800125a8`
- `0x180012874`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012702`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012702`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800125d5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800125d5`
- `ole32!CoTaskMemFree` at `0x1800126f9`
- `ole32!CoTaskMemFree` at `0x1800126f9`
- `KERNEL32!lstrcmpiW` at `0x180012651`
- `KERNEL32!lstrcmpiW` at `0x180012651`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, WCHAR *a2, int a3)
{
  unsigned __int16 *v6; // rsi
  int Token; // ebx
  void *v9; // r14
  unsigned int i; // ebx
  HKEY v11; // rbp
  __int64 v12; // r15
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  pv = 0;
  v6 = (unsigned __int16 *)malloc(0x2000u);
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
0x1800125a8  mov     [rsp+arg_0], rbx
0x1800125ad  mov     [rsp+arg_8], rbp
0x1800125b2  push    rsi
0x1800125b3  push    rdi
0x1800125b4  push    r12
0x1800125b6  push    r14
0x1800125b8  push    r15
0x1800125ba  sub     rsp, 30h
0x1800125be  mov     rdi, rcx
0x1800125c1  mov     [rsp+58h+pv], 0
0x1800125ca  mov     ecx, 2000h; Size
0x1800125cf  mov     r12d, r8d
0x1800125d2  mov     rbx, rdx
0x1800125d5  call    cs:__imp_malloc
0x1800125db  mov     rsi, rax
0x1800125de  test    rax, rax
0x1800125e1  jnz     short loc_1800125ED
0x1800125e3  mov     eax, 8007000Eh
0x1800125e8  jmp     loc_18001270A
0x1800125ed  lea     r8, [rsp+58h+pv]; unsigned __int16 **
0x1800125f2  mov     rdx, rbx; unsigned __int16 *
0x1800125f5  mov     rcx, rdi; this
0x1800125f8  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)
0x1800125fd  mov     ebx, eax
0x1800125ff  test    eax, eax
0x180012601  js      loc_1800126FF
0x180012607  mov     r14, [rsp+58h+pv]
0x18001260c  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180012613  mov     [rdi], r14
0x180012616  mov     rcx, [rdi]
0x180012619  xor     eax, eax
0x18001261b  cmp     ax, [rcx]
0x18001261e  jz      loc_1800126F6
0x180012624  mov     rdx, rsi; unsigned __int16 *
0x180012627  mov     rcx, rdi; this
0x18001262a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001262f  mov     ebx, eax
0x180012631  test    eax, eax
0x180012633  js      loc_1800126F6
0x180012639  xor     ebx, ebx
0x18001263b  cmp     ebx, 0Eh
0x18001263e  jnb     loc_1800126F1
0x180012644  movsxd  rbp, ebx
0x180012647  mov     rcx, rsi; lpString1
0x18001264a  add     rbp, rbp
0x18001264d  mov     rdx, [r15+rbp*8]; lpString2
0x180012651  call    cs:__imp_lstrcmpiW
0x180012657  test    eax, eax
0x180012659  jz      short loc_18001265F
0x18001265b  inc     ebx
0x18001265d  jmp     short loc_18001263B
0x18001265f  mov     rbp, [r15+rbp*8+8]
0x180012664  test    rbp, rbp
0x180012667  jz      loc_1800126F1
0x18001266d  mov     rdx, rsi; unsigned __int16 *
0x180012670  mov     rcx, rdi; this
0x180012673  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180012678  mov     ebx, eax
0x18001267a  test    eax, eax
0x18001267c  js      short loc_1800126F6
0x18001267e  mov     eax, 7Bh ; '{'
0x180012683  cmp     ax, [rsi]
0x180012686  jnz     short loc_1800126F1
0x180012688  mov     [rsp+58h+var_38], 0; int
0x180012690  mov     r8, rbp; HKEY
0x180012693  mov     rdx, rsi; unsigned __int16 *
0x180012696  mov     rcx, rdi; this
0x180012699  test    r12d, r12d
0x18001269c  jz      short loc_1800126B8
0x18001269e  mov     r15, [rdi]
0x1800126a1  mov     r9d, r12d; int
0x1800126a4  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800126a9  mov     ebx, eax
0x1800126ab  test    eax, eax
0x1800126ad  js      short loc_1800126D3
0x1800126af  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800126b6  jmp     short loc_1800126C6
0x1800126b8  xor     r9d, r9d; int
0x1800126bb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800126c0  mov     ebx, eax
0x1800126c2  test    eax, eax
0x1800126c4  js      short loc_1800126F6
0x1800126c6  mov     rcx, rdi; this
0x1800126c9  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800126ce  jmp     loc_180012616
0x1800126d3  xor     r9d, r9d; int
0x1800126d6  mov     [rdi], r15
0x1800126d9  mov     r8, rbp; HKEY
0x1800126dc  mov     [rsp+58h+var_38], 0; int
0x1800126e4  mov     rdx, rsi; unsigned __int16 *
0x1800126e7  mov     rcx, rdi; this
0x1800126ea  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800126ef  jmp     short loc_1800126F6
0x1800126f1  mov     ebx, 80020009h
0x1800126f6  mov     rcx, r14; pv
0x1800126f9  call    cs:__imp_CoTaskMemFree
0x1800126ff  mov     rcx, rsi; Block
0x180012702  call    cs:__imp_free
0x180012708  mov     eax, ebx
0x18001270a  mov     rbx, [rsp+58h+arg_0]
0x18001270f  mov     rbp, [rsp+58h+arg_8]
0x180012714  add     rsp, 30h
0x180012718  pop     r15
0x18001271a  pop     r14
0x18001271c  pop     r12
0x18001271e  pop     rdi
0x18001271f  pop     rsi
0x180012720  retn
```
