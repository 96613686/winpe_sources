# ATL::CRegParser::RegisterBuffer(ushort const *,int)

- ea: `0x1800035fc`
- end: `0x18000378e`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEBGH@Z`
- size: `402`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180003794`

## callees

- `0x180003040`
- `0x1800031dc`
- `0x1800035fc`
- `0x1800039f4`

## import_xrefs

- `msvcrt!malloc` at `0x180003629`
- `msvcrt!malloc` at `0x180003629`
- `msvcrt!free` at `0x1800036ad`
- `msvcrt!free` at `0x1800036ad`
- `KERNEL32!lstrcmpiW` at `0x18000368b`
- `KERNEL32!lstrcmpiW` at `0x18000368b`
- `ole32!CoTaskMemFree` at `0x1800036a4`
- `ole32!CoTaskMemFree` at `0x1800036a4`
- `USER32!CharNextW` at `0x180003751`
- `USER32!CharNextW` at `0x180003751`

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
0x1800035fc  mov     [rsp+arg_0], rbx
0x180003601  mov     [rsp+arg_8], rbp
0x180003606  push    rsi
0x180003607  push    rdi
0x180003608  push    r12
0x18000360a  push    r14
0x18000360c  push    r15
0x18000360e  sub     rsp, 30h
0x180003612  mov     rsi, rcx
0x180003615  mov     [rsp+58h+pv], 0
0x18000361e  mov     ecx, 2000h; Size
0x180003623  mov     r12d, r8d
0x180003626  mov     rbx, rdx
0x180003629  call    cs:__imp_malloc
0x18000362f  mov     rdi, rax
0x180003632  test    rax, rax
0x180003635  jnz     short loc_18000363E
0x180003637  mov     eax, 8007000Eh
0x18000363c  jmp     short loc_1800036B5
0x18000363e  lea     r8, [rsp+58h+pv]; unsigned __int16 **
0x180003643  mov     rdx, rbx; unsigned __int16 *
0x180003646  mov     rcx, rsi; this
0x180003649  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)
0x18000364e  mov     ebx, eax
0x180003650  test    eax, eax
0x180003652  js      short loc_1800036AA
0x180003654  mov     r14, [rsp+58h+pv]
0x180003659  xor     eax, eax
0x18000365b  mov     [rsi], r14
0x18000365e  cmp     ax, [r14]
0x180003662  jz      short loc_1800036A1
0x180003664  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000366b  mov     rdx, rdi; unsigned __int16 *
0x18000366e  mov     rcx, rsi; this
0x180003671  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003676  mov     ebx, eax
0x180003678  test    eax, eax
0x18000367a  js      short loc_1800036A1
0x18000367c  xor     ebx, ebx
0x18000367e  movsxd  rbp, ebx
0x180003681  mov     rcx, rdi; lpString1
0x180003684  add     rbp, rbp
0x180003687  mov     rdx, [r15+rbp*8]; lpString2
0x18000368b  call    cs:__imp_lstrcmpiW
0x180003691  test    eax, eax
0x180003693  jz      short loc_1800036CC
0x180003695  inc     ebx
0x180003697  cmp     ebx, 0Eh
0x18000369a  jb      short loc_18000367E
0x18000369c  mov     ebx, 80020009h
0x1800036a1  mov     rcx, r14; pv
0x1800036a4  call    cs:__imp_CoTaskMemFree
0x1800036aa  mov     rcx, rdi; Block
0x1800036ad  call    cs:__imp_free
0x1800036b3  mov     eax, ebx
0x1800036b5  mov     rbx, [rsp+58h+arg_0]
0x1800036ba  mov     rbp, [rsp+58h+arg_8]
0x1800036bf  add     rsp, 30h
0x1800036c3  pop     r15
0x1800036c5  pop     r14
0x1800036c7  pop     r12
0x1800036c9  pop     rdi
0x1800036ca  pop     rsi
0x1800036cb  retn
0x1800036cc  mov     rbp, [r15+rbp*8+8]
0x1800036d1  test    rbp, rbp
0x1800036d4  jz      short loc_18000369C
0x1800036d6  mov     rdx, rdi; unsigned __int16 *
0x1800036d9  mov     rcx, rsi; this
0x1800036dc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800036e1  mov     ebx, eax
0x1800036e3  test    eax, eax
0x1800036e5  js      short loc_1800036A1
0x1800036e7  mov     eax, 7Bh ; '{'
0x1800036ec  cmp     ax, [rdi]
0x1800036ef  jnz     short loc_18000369C
0x1800036f1  mov     [rsp+58h+var_38], 0; int
0x1800036f9  mov     r8, rbp; HKEY
0x1800036fc  mov     rdx, rdi; unsigned __int16 *
0x1800036ff  mov     rcx, rsi; this
0x180003702  test    r12d, r12d
0x180003705  jz      short loc_180003721
0x180003707  mov     r15, [rsi]
0x18000370a  mov     r9d, r12d; int
0x18000370d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180003712  mov     ebx, eax
0x180003714  test    eax, eax
0x180003716  js      short loc_18000376D
0x180003718  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000371f  jmp     short loc_180003733
0x180003721  xor     r9d, r9d; int
0x180003724  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180003729  mov     ebx, eax
0x18000372b  test    eax, eax
0x18000372d  js      loc_1800036A1
0x180003733  mov     rcx, [rsi]; lpsz
0x180003736  movzx   r8d, word ptr [rcx]
0x18000373a  mov     edx, r8d
0x18000373d  sub     edx, 9
0x180003740  jz      short loc_180003751
0x180003742  sub     edx, 1
0x180003745  jz      short loc_180003751
0x180003747  sub     edx, 3
0x18000374a  jz      short loc_180003751
0x18000374c  cmp     edx, 13h
0x18000374f  jnz     short loc_18000375C
0x180003751  call    cs:__imp_CharNextW
0x180003757  mov     [rsi], rax
0x18000375a  jmp     short loc_180003733
0x18000375c  xor     eax, eax
0x18000375e  cmp     ax, r8w
0x180003762  jnz     loc_18000366B
0x180003768  jmp     loc_1800036A1
0x18000376d  xor     r9d, r9d; int
0x180003770  mov     [rsi], r15
0x180003773  mov     r8, rbp; HKEY
0x180003776  mov     [rsp+58h+var_38], 0; int
0x18000377e  mov     rdx, rdi; unsigned __int16 *
0x180003781  mov     rcx, rsi; this
0x180003784  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180003789  jmp     loc_1800036A1
```
