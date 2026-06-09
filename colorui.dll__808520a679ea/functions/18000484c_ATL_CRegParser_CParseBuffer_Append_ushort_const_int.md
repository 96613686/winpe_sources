# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18000484c`
- end: `0x180004940`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180007310`

## callees

- `0x18000484c`
- `0x180004a90`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800048e0`
- `msvcrt!memcpy_s` at `0x1800048e0`
- `ole32!CoTaskMemRealloc` at `0x1800048a3`
- `ole32!CoTaskMemRealloc` at `0x1800048a3`

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
0x18000484c  push    rbx
0x18000484e  push    rbp
0x18000484f  push    rsi
0x180004850  push    rdi
0x180004851  sub     rsp, 28h
0x180004855  mov     rdi, rcx
0x180004858  mov     esi, r8d
0x18000485b  lea     ecx, [r8+1]
0x18000485f  mov     rbp, rdx
0x180004862  add     ecx, [rdi]
0x180004864  cmp     ecx, [rdi]
0x180004866  jle     loc_180004914
0x18000486c  cmp     ecx, r8d
0x18000486f  jle     loc_180004914
0x180004875  mov     ebx, [rdi+4]
0x180004878  cmp     ecx, ebx
0x18000487a  jl      short loc_1800048B5
0x18000487c  cmp     ebx, 3FFFFFFFh
0x180004882  jg      loc_180004914
0x180004888  add     ebx, ebx
0x18000488a  cmp     ecx, ebx
0x18000488c  jge     short loc_18000487C
0x18000488e  mov     eax, ebx
0x180004890  mov     ecx, 0FFFFFFFFh
0x180004895  add     rax, rax
0x180004898  cmp     rax, rcx
0x18000489b  ja      short loc_180004914
0x18000489d  mov     rcx, [rdi+8]; pv
0x1800048a1  mov     edx, eax; cb
0x1800048a3  call    cs:__imp_CoTaskMemRealloc
0x1800048a9  test    rax, rax
0x1800048ac  jz      short loc_180004914
0x1800048ae  mov     [rdi+8], rax
0x1800048b2  mov     [rdi+4], ebx
0x1800048b5  cmp     dword ptr [rdi], 0
0x1800048b8  jl      short loc_180004914
0x1800048ba  cmp     [rdi], ebx
0x1800048bc  jge     short loc_180004914
0x1800048be  mov     ecx, ebx
0x1800048c0  sub     ecx, [rdi]
0x1800048c2  cmp     ecx, ebx
0x1800048c4  jg      short loc_180004914
0x1800048c6  movsxd  rdx, ecx
0x1800048c9  lea     eax, [rsi+rsi]
0x1800048cc  movsxd  rcx, dword ptr [rdi]
0x1800048cf  add     rdx, rdx; DestinationSize
0x1800048d2  movsxd  r9, eax; SourceSize
0x1800048d5  mov     r8, rbp; Source
0x1800048d8  mov     rax, [rdi+8]
0x1800048dc  lea     rcx, [rax+rcx*2]; Destination
0x1800048e0  call    cs:__imp_memcpy_s
0x1800048e6  test    eax, eax
0x1800048e8  jz      short loc_1800048FE
0x1800048ea  cmp     eax, 0Ch
0x1800048ed  jz      short loc_180004935
0x1800048ef  cmp     eax, 16h
0x1800048f2  jz      short loc_18000492A
0x1800048f4  cmp     eax, 22h ; '"'
0x1800048f7  jz      short loc_18000492A
0x1800048f9  cmp     eax, 50h ; 'P'
0x1800048fc  jnz     short loc_18000491F
0x1800048fe  add     [rdi], esi
0x180004900  movsxd  rdx, dword ptr [rdi]
0x180004903  xor     eax, eax
0x180004905  mov     rcx, [rdi+8]
0x180004909  mov     [rcx+rdx*2], ax
0x18000490d  mov     eax, 1
0x180004912  jmp     short loc_180004916
0x180004914  xor     eax, eax
0x180004916  add     rsp, 28h
0x18000491a  pop     rdi
0x18000491b  pop     rsi
0x18000491c  pop     rbp
0x18000491d  pop     rbx
0x18000491e  retn
0x18000491f  mov     ecx, 80004005h; int
0x180004924  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000492a  mov     ecx, 80070057h; int
0x18000492f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004935  mov     ecx, 8007000Eh; int
0x18000493a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
