# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180004cfc`
- end: `0x180004df0`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180005ae4`

## callees

- `0x180004cfc`
- `0x180005688`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004d90`
- `msvcrt!memcpy_s` at `0x180004d90`
- `ole32!CoTaskMemRealloc` at `0x180004d53`
- `ole32!CoTaskMemRealloc` at `0x180004d53`

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
0x180004cfc  push    rbx
0x180004cfe  push    rbp
0x180004cff  push    rsi
0x180004d00  push    rdi
0x180004d01  sub     rsp, 28h
0x180004d05  mov     rdi, rcx
0x180004d08  mov     esi, r8d
0x180004d0b  lea     ecx, [r8+1]
0x180004d0f  mov     rbp, rdx
0x180004d12  add     ecx, [rdi]
0x180004d14  cmp     ecx, [rdi]
0x180004d16  jle     loc_180004DC4
0x180004d1c  cmp     ecx, r8d
0x180004d1f  jle     loc_180004DC4
0x180004d25  mov     ebx, [rdi+4]
0x180004d28  cmp     ecx, ebx
0x180004d2a  jl      short loc_180004D65
0x180004d2c  cmp     ebx, 3FFFFFFFh
0x180004d32  jg      loc_180004DC4
0x180004d38  add     ebx, ebx
0x180004d3a  cmp     ecx, ebx
0x180004d3c  jge     short loc_180004D2C
0x180004d3e  mov     eax, ebx
0x180004d40  mov     ecx, 0FFFFFFFFh
0x180004d45  add     rax, rax
0x180004d48  cmp     rax, rcx
0x180004d4b  ja      short loc_180004DC4
0x180004d4d  mov     rcx, [rdi+8]; pv
0x180004d51  mov     edx, eax; cb
0x180004d53  call    cs:__imp_CoTaskMemRealloc
0x180004d59  test    rax, rax
0x180004d5c  jz      short loc_180004DC4
0x180004d5e  mov     [rdi+8], rax
0x180004d62  mov     [rdi+4], ebx
0x180004d65  cmp     dword ptr [rdi], 0
0x180004d68  jl      short loc_180004DC4
0x180004d6a  cmp     [rdi], ebx
0x180004d6c  jge     short loc_180004DC4
0x180004d6e  mov     ecx, ebx
0x180004d70  sub     ecx, [rdi]
0x180004d72  cmp     ecx, ebx
0x180004d74  jg      short loc_180004DC4
0x180004d76  movsxd  rdx, ecx
0x180004d79  lea     eax, [rsi+rsi]
0x180004d7c  movsxd  rcx, dword ptr [rdi]
0x180004d7f  add     rdx, rdx; DestinationSize
0x180004d82  movsxd  r9, eax; SourceSize
0x180004d85  mov     r8, rbp; Source
0x180004d88  mov     rax, [rdi+8]
0x180004d8c  lea     rcx, [rax+rcx*2]; Destination
0x180004d90  call    cs:__imp_memcpy_s
0x180004d96  test    eax, eax
0x180004d98  jz      short loc_180004DAE
0x180004d9a  cmp     eax, 0Ch
0x180004d9d  jz      short loc_180004DE5
0x180004d9f  cmp     eax, 16h
0x180004da2  jz      short loc_180004DDA
0x180004da4  cmp     eax, 22h ; '"'
0x180004da7  jz      short loc_180004DDA
0x180004da9  cmp     eax, 50h ; 'P'
0x180004dac  jnz     short loc_180004DCF
0x180004dae  add     [rdi], esi
0x180004db0  movsxd  rdx, dword ptr [rdi]
0x180004db3  xor     eax, eax
0x180004db5  mov     rcx, [rdi+8]
0x180004db9  mov     [rcx+rdx*2], ax
0x180004dbd  mov     eax, 1
0x180004dc2  jmp     short loc_180004DC6
0x180004dc4  xor     eax, eax
0x180004dc6  add     rsp, 28h
0x180004dca  pop     rdi
0x180004dcb  pop     rsi
0x180004dcc  pop     rbp
0x180004dcd  pop     rbx
0x180004dce  retn
0x180004dcf  mov     ecx, 80004005h; int
0x180004dd4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004dda  mov     ecx, 80070057h; int
0x180004ddf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004de5  mov     ecx, 8007000Eh; int
0x180004dea  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
