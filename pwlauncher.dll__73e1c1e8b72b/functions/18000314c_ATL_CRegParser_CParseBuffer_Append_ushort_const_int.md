# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18000314c`
- end: `0x180003240`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003cc4`

## callees

- `0x18000314c`
- `0x18000374c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800031e0`
- `msvcrt!memcpy_s` at `0x1800031e0`
- `ole32!CoTaskMemRealloc` at `0x1800031a3`
- `ole32!CoTaskMemRealloc` at `0x1800031a3`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const unsigned __int16 *a2,
        int a3)
{
  int v6; // ecx
  int v7; // ebx
  unsigned __int64 v8; // rax
  LPVOID v9; // rax
  int v10; // ecx
  errno_t v11; // eax

  v6 = *(_DWORD *)this + a3 + 1;
  if ( v6 <= *(_DWORD *)this || v6 <= a3 )
    return 0;
  v7 = *((_DWORD *)this + 1);
  if ( v6 >= v7 )
  {
    while ( v7 <= 0x3FFFFFFF )
    {
      v7 *= 2;
      if ( v6 < v7 )
      {
        v8 = 2LL * (unsigned int)v7;
        if ( v8 <= 0xFFFFFFFF )
        {
          v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
          if ( v9 )
          {
            *((_QWORD *)this + 1) = v9;
            *((_DWORD *)this + 1) = v7;
            goto LABEL_9;
          }
        }
        return 0;
      }
    }
    return 0;
  }
LABEL_9:
  if ( *(int *)this < 0 )
    return 0;
  if ( *(_DWORD *)this >= v7 )
    return 0;
  v10 = v7 - *(_DWORD *)this;
  if ( v10 > v7 )
    return 0;
  v11 = memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v10, a2, 2 * a3);
  if ( v11 )
  {
    if ( v11 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v11 == 22 || v11 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v11 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  *(_DWORD *)this += a3;
  *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
  return 1;
}

```

## disassembly

```asm
0x18000314c  push    rbx
0x18000314e  push    rbp
0x18000314f  push    rsi
0x180003150  push    rdi
0x180003151  sub     rsp, 28h
0x180003155  mov     rdi, rcx
0x180003158  mov     esi, r8d
0x18000315b  lea     ecx, [r8+1]
0x18000315f  mov     rbp, rdx
0x180003162  add     ecx, [rdi]
0x180003164  cmp     ecx, [rdi]
0x180003166  jle     loc_180003214
0x18000316c  cmp     ecx, r8d
0x18000316f  jle     loc_180003214
0x180003175  mov     ebx, [rdi+4]
0x180003178  cmp     ecx, ebx
0x18000317a  jl      short loc_1800031B5
0x18000317c  cmp     ebx, 3FFFFFFFh
0x180003182  jg      loc_180003214
0x180003188  add     ebx, ebx
0x18000318a  cmp     ecx, ebx
0x18000318c  jge     short loc_18000317C
0x18000318e  mov     eax, ebx
0x180003190  mov     ecx, 0FFFFFFFFh
0x180003195  add     rax, rax
0x180003198  cmp     rax, rcx
0x18000319b  ja      short loc_180003214
0x18000319d  mov     rcx, [rdi+8]; pv
0x1800031a1  mov     edx, eax; cb
0x1800031a3  call    cs:__imp_CoTaskMemRealloc
0x1800031a9  test    rax, rax
0x1800031ac  jz      short loc_180003214
0x1800031ae  mov     [rdi+8], rax
0x1800031b2  mov     [rdi+4], ebx
0x1800031b5  cmp     dword ptr [rdi], 0
0x1800031b8  jl      short loc_180003214
0x1800031ba  cmp     [rdi], ebx
0x1800031bc  jge     short loc_180003214
0x1800031be  mov     ecx, ebx
0x1800031c0  sub     ecx, [rdi]
0x1800031c2  cmp     ecx, ebx
0x1800031c4  jg      short loc_180003214
0x1800031c6  movsxd  rdx, ecx
0x1800031c9  lea     eax, [rsi+rsi]
0x1800031cc  movsxd  rcx, dword ptr [rdi]
0x1800031cf  add     rdx, rdx; DestinationSize
0x1800031d2  movsxd  r9, eax; SourceSize
0x1800031d5  mov     r8, rbp; Source
0x1800031d8  mov     rax, [rdi+8]
0x1800031dc  lea     rcx, [rax+rcx*2]; Destination
0x1800031e0  call    cs:__imp_memcpy_s
0x1800031e6  test    eax, eax
0x1800031e8  jz      short loc_1800031FE
0x1800031ea  cmp     eax, 0Ch
0x1800031ed  jz      short loc_180003235
0x1800031ef  cmp     eax, 16h
0x1800031f2  jz      short loc_18000322A
0x1800031f4  cmp     eax, 22h ; '"'
0x1800031f7  jz      short loc_18000322A
0x1800031f9  cmp     eax, 50h ; 'P'
0x1800031fc  jnz     short loc_18000321F
0x1800031fe  add     [rdi], esi
0x180003200  movsxd  rdx, dword ptr [rdi]
0x180003203  xor     eax, eax
0x180003205  mov     rcx, [rdi+8]
0x180003209  mov     [rcx+rdx*2], ax
0x18000320d  mov     eax, 1
0x180003212  jmp     short loc_180003216
0x180003214  xor     eax, eax
0x180003216  add     rsp, 28h
0x18000321a  pop     rdi
0x18000321b  pop     rsi
0x18000321c  pop     rbp
0x18000321d  pop     rbx
0x18000321e  retn
0x18000321f  mov     ecx, 80004005h; int
0x180003224  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000322a  mov     ecx, 80070057h; int
0x18000322f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003235  mov     ecx, 8007000Eh; int
0x18000323a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
