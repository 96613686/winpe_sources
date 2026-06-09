# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18000298c`
- end: `0x180002a80`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000326c`

## callees

- `0x18000298c`
- `0x180002ac4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002a20`
- `msvcrt!memcpy_s` at `0x180002a20`
- `ole32!CoTaskMemRealloc` at `0x1800029e3`
- `ole32!CoTaskMemRealloc` at `0x1800029e3`

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
0x18000298c  push    rbx
0x18000298e  push    rbp
0x18000298f  push    rsi
0x180002990  push    rdi
0x180002991  sub     rsp, 28h
0x180002995  mov     rdi, rcx
0x180002998  mov     esi, r8d
0x18000299b  lea     ecx, [r8+1]
0x18000299f  mov     rbp, rdx
0x1800029a2  add     ecx, [rdi]
0x1800029a4  cmp     ecx, [rdi]
0x1800029a6  jle     loc_180002A54
0x1800029ac  cmp     ecx, r8d
0x1800029af  jle     loc_180002A54
0x1800029b5  mov     ebx, [rdi+4]
0x1800029b8  cmp     ecx, ebx
0x1800029ba  jl      short loc_1800029F5
0x1800029bc  cmp     ebx, 3FFFFFFFh
0x1800029c2  jg      loc_180002A54
0x1800029c8  add     ebx, ebx
0x1800029ca  cmp     ecx, ebx
0x1800029cc  jge     short loc_1800029BC
0x1800029ce  mov     eax, ebx
0x1800029d0  mov     ecx, 0FFFFFFFFh
0x1800029d5  add     rax, rax
0x1800029d8  cmp     rax, rcx
0x1800029db  ja      short loc_180002A54
0x1800029dd  mov     rcx, [rdi+8]; pv
0x1800029e1  mov     edx, eax; cb
0x1800029e3  call    cs:__imp_CoTaskMemRealloc
0x1800029e9  test    rax, rax
0x1800029ec  jz      short loc_180002A54
0x1800029ee  mov     [rdi+8], rax
0x1800029f2  mov     [rdi+4], ebx
0x1800029f5  cmp     dword ptr [rdi], 0
0x1800029f8  jl      short loc_180002A54
0x1800029fa  cmp     [rdi], ebx
0x1800029fc  jge     short loc_180002A54
0x1800029fe  mov     ecx, ebx
0x180002a00  sub     ecx, [rdi]
0x180002a02  cmp     ecx, ebx
0x180002a04  jg      short loc_180002A54
0x180002a06  movsxd  rdx, ecx
0x180002a09  lea     eax, [rsi+rsi]
0x180002a0c  movsxd  rcx, dword ptr [rdi]
0x180002a0f  add     rdx, rdx; DestinationSize
0x180002a12  movsxd  r9, eax; SourceSize
0x180002a15  mov     r8, rbp; Source
0x180002a18  mov     rax, [rdi+8]
0x180002a1c  lea     rcx, [rax+rcx*2]; Destination
0x180002a20  call    cs:__imp_memcpy_s
0x180002a26  test    eax, eax
0x180002a28  jz      short loc_180002A3E
0x180002a2a  cmp     eax, 0Ch
0x180002a2d  jz      short loc_180002A75
0x180002a2f  cmp     eax, 16h
0x180002a32  jz      short loc_180002A6A
0x180002a34  cmp     eax, 22h ; '"'
0x180002a37  jz      short loc_180002A6A
0x180002a39  cmp     eax, 50h ; 'P'
0x180002a3c  jnz     short loc_180002A5F
0x180002a3e  add     [rdi], esi
0x180002a40  movsxd  rdx, dword ptr [rdi]
0x180002a43  xor     eax, eax
0x180002a45  mov     rcx, [rdi+8]
0x180002a49  mov     [rcx+rdx*2], ax
0x180002a4d  mov     eax, 1
0x180002a52  jmp     short loc_180002A56
0x180002a54  xor     eax, eax
0x180002a56  add     rsp, 28h
0x180002a5a  pop     rdi
0x180002a5b  pop     rsi
0x180002a5c  pop     rbp
0x180002a5d  pop     rbx
0x180002a5e  retn
0x180002a5f  mov     ecx, 80004005h; int
0x180002a64  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002a6a  mov     ecx, 80070057h; int
0x180002a6f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002a75  mov     ecx, 8007000Eh; int
0x180002a7a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
