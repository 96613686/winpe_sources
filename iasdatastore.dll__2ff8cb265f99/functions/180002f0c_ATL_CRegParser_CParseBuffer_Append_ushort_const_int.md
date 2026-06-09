# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180002f0c`
- end: `0x180003000`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000466c`

## callees

- `0x180002f0c`
- `0x1800039a4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002fa0`
- `msvcrt!memcpy_s` at `0x180002fa0`
- `ole32!CoTaskMemRealloc` at `0x180002f63`
- `ole32!CoTaskMemRealloc` at `0x180002f63`

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
0x180002f0c  push    rbx
0x180002f0e  push    rbp
0x180002f0f  push    rsi
0x180002f10  push    rdi
0x180002f11  sub     rsp, 28h
0x180002f15  mov     rdi, rcx
0x180002f18  mov     esi, r8d
0x180002f1b  lea     ecx, [r8+1]
0x180002f1f  mov     rbp, rdx
0x180002f22  add     ecx, [rdi]
0x180002f24  cmp     ecx, [rdi]
0x180002f26  jle     loc_180002FD4
0x180002f2c  cmp     ecx, r8d
0x180002f2f  jle     loc_180002FD4
0x180002f35  mov     ebx, [rdi+4]
0x180002f38  cmp     ecx, ebx
0x180002f3a  jl      short loc_180002F75
0x180002f3c  cmp     ebx, 3FFFFFFFh
0x180002f42  jg      loc_180002FD4
0x180002f48  add     ebx, ebx
0x180002f4a  cmp     ecx, ebx
0x180002f4c  jge     short loc_180002F3C
0x180002f4e  mov     eax, ebx
0x180002f50  mov     ecx, 0FFFFFFFFh
0x180002f55  add     rax, rax
0x180002f58  cmp     rax, rcx
0x180002f5b  ja      short loc_180002FD4
0x180002f5d  mov     rcx, [rdi+8]; pv
0x180002f61  mov     edx, eax; cb
0x180002f63  call    cs:__imp_CoTaskMemRealloc
0x180002f69  test    rax, rax
0x180002f6c  jz      short loc_180002FD4
0x180002f6e  mov     [rdi+8], rax
0x180002f72  mov     [rdi+4], ebx
0x180002f75  cmp     dword ptr [rdi], 0
0x180002f78  jl      short loc_180002FD4
0x180002f7a  cmp     [rdi], ebx
0x180002f7c  jge     short loc_180002FD4
0x180002f7e  mov     ecx, ebx
0x180002f80  sub     ecx, [rdi]
0x180002f82  cmp     ecx, ebx
0x180002f84  jg      short loc_180002FD4
0x180002f86  movsxd  rdx, ecx
0x180002f89  lea     eax, [rsi+rsi]
0x180002f8c  movsxd  rcx, dword ptr [rdi]
0x180002f8f  add     rdx, rdx; DestinationSize
0x180002f92  movsxd  r9, eax; SourceSize
0x180002f95  mov     r8, rbp; Source
0x180002f98  mov     rax, [rdi+8]
0x180002f9c  lea     rcx, [rax+rcx*2]; Destination
0x180002fa0  call    cs:__imp_memcpy_s
0x180002fa6  test    eax, eax
0x180002fa8  jz      short loc_180002FBE
0x180002faa  cmp     eax, 0Ch
0x180002fad  jz      short loc_180002FF5
0x180002faf  cmp     eax, 16h
0x180002fb2  jz      short loc_180002FEA
0x180002fb4  cmp     eax, 22h ; '"'
0x180002fb7  jz      short loc_180002FEA
0x180002fb9  cmp     eax, 50h ; 'P'
0x180002fbc  jnz     short loc_180002FDF
0x180002fbe  add     [rdi], esi
0x180002fc0  movsxd  rdx, dword ptr [rdi]
0x180002fc3  xor     eax, eax
0x180002fc5  mov     rcx, [rdi+8]
0x180002fc9  mov     [rcx+rdx*2], ax
0x180002fcd  mov     eax, 1
0x180002fd2  jmp     short loc_180002FD6
0x180002fd4  xor     eax, eax
0x180002fd6  add     rsp, 28h
0x180002fda  pop     rdi
0x180002fdb  pop     rsi
0x180002fdc  pop     rbp
0x180002fdd  pop     rbx
0x180002fde  retn
0x180002fdf  mov     ecx, 80004005h; int
0x180002fe4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002fea  mov     ecx, 80070057h; int
0x180002fef  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002ff5  mov     ecx, 8007000Eh; int
0x180002ffa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
