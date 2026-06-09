# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18000e6cc`
- end: `0x18000e7c0`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001098c`

## callees

- `0x18000e6cc`
- `0x18000f208`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000e760`
- `msvcrt!memcpy_s` at `0x18000e760`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e723`

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
0x18000e6cc  push    rbx
0x18000e6ce  push    rbp
0x18000e6cf  push    rsi
0x18000e6d0  push    rdi
0x18000e6d1  sub     rsp, 28h
0x18000e6d5  mov     rdi, rcx
0x18000e6d8  mov     esi, r8d
0x18000e6db  lea     ecx, [r8+1]
0x18000e6df  mov     rbp, rdx
0x18000e6e2  add     ecx, [rdi]
0x18000e6e4  cmp     ecx, [rdi]
0x18000e6e6  jle     loc_18000E794
0x18000e6ec  cmp     ecx, r8d
0x18000e6ef  jle     loc_18000E794
0x18000e6f5  mov     ebx, [rdi+4]
0x18000e6f8  cmp     ecx, ebx
0x18000e6fa  jl      short loc_18000E735
0x18000e6fc  cmp     ebx, 3FFFFFFFh
0x18000e702  jg      loc_18000E794
0x18000e708  add     ebx, ebx
0x18000e70a  cmp     ecx, ebx
0x18000e70c  jge     short loc_18000E6FC
0x18000e70e  mov     eax, ebx
0x18000e710  mov     ecx, 0FFFFFFFFh
0x18000e715  add     rax, rax
0x18000e718  cmp     rax, rcx
0x18000e71b  ja      short loc_18000E794
0x18000e71d  mov     rcx, [rdi+8]; pv
0x18000e721  mov     edx, eax; cb
0x18000e723  call    cs:__imp_CoTaskMemRealloc
0x18000e729  test    rax, rax
0x18000e72c  jz      short loc_18000E794
0x18000e72e  mov     [rdi+8], rax
0x18000e732  mov     [rdi+4], ebx
0x18000e735  cmp     dword ptr [rdi], 0
0x18000e738  jl      short loc_18000E794
0x18000e73a  cmp     [rdi], ebx
0x18000e73c  jge     short loc_18000E794
0x18000e73e  mov     ecx, ebx
0x18000e740  sub     ecx, [rdi]
0x18000e742  cmp     ecx, ebx
0x18000e744  jg      short loc_18000E794
0x18000e746  movsxd  rdx, ecx
0x18000e749  lea     eax, [rsi+rsi]
0x18000e74c  movsxd  rcx, dword ptr [rdi]
0x18000e74f  add     rdx, rdx; DestinationSize
0x18000e752  movsxd  r9, eax; SourceSize
0x18000e755  mov     r8, rbp; Source
0x18000e758  mov     rax, [rdi+8]
0x18000e75c  lea     rcx, [rax+rcx*2]; Destination
0x18000e760  call    cs:__imp_memcpy_s
0x18000e766  test    eax, eax
0x18000e768  jz      short loc_18000E77E
0x18000e76a  cmp     eax, 0Ch
0x18000e76d  jz      short loc_18000E7B5
0x18000e76f  cmp     eax, 16h
0x18000e772  jz      short loc_18000E7AA
0x18000e774  cmp     eax, 22h ; '"'
0x18000e777  jz      short loc_18000E7AA
0x18000e779  cmp     eax, 50h ; 'P'
0x18000e77c  jnz     short loc_18000E79F
0x18000e77e  add     [rdi], esi
0x18000e780  movsxd  rdx, dword ptr [rdi]
0x18000e783  xor     eax, eax
0x18000e785  mov     rcx, [rdi+8]
0x18000e789  mov     [rcx+rdx*2], ax
0x18000e78d  mov     eax, 1
0x18000e792  jmp     short loc_18000E796
0x18000e794  xor     eax, eax
0x18000e796  add     rsp, 28h
0x18000e79a  pop     rdi
0x18000e79b  pop     rsi
0x18000e79c  pop     rbp
0x18000e79d  pop     rbx
0x18000e79e  retn
0x18000e79f  mov     ecx, 80004005h; int
0x18000e7a4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000e7aa  mov     ecx, 80070057h; int
0x18000e7af  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000e7b5  mov     ecx, 8007000Eh; int
0x18000e7ba  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
