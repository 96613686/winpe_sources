# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180003730`
- end: `0x180003835`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `261`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004694`

## callees

- `0x180003730`
- `0x18000418c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800037ce`
- `msvcrt!memcpy_s` at `0x1800037ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000378b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000378b`

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
0x180003730  push    rbx
0x180003732  push    rbp
0x180003733  push    rsi
0x180003734  push    rdi
0x180003735  sub     rsp, 28h
0x180003739  mov     rdi, rcx
0x18000373c  mov     esi, r8d
0x18000373f  lea     ecx, [r8+1]
0x180003743  mov     rbp, rdx
0x180003746  add     ecx, [rdi]
0x180003748  cmp     ecx, [rdi]
0x18000374a  jle     loc_180003808
0x180003750  cmp     ecx, r8d
0x180003753  jle     loc_180003808
0x180003759  mov     ebx, [rdi+4]
0x18000375c  cmp     ecx, ebx
0x18000375e  jl      short loc_1800037A3
0x180003760  cmp     ebx, 3FFFFFFFh
0x180003766  jg      loc_180003808
0x18000376c  add     ebx, ebx
0x18000376e  cmp     ecx, ebx
0x180003770  jge     short loc_180003760
0x180003772  mov     eax, ebx
0x180003774  mov     ecx, 0FFFFFFFFh
0x180003779  add     rax, rax
0x18000377c  cmp     rax, rcx
0x18000377f  ja      loc_180003808
0x180003785  mov     rcx, [rdi+8]; pv
0x180003789  mov     edx, eax; cb
0x18000378b  call    cs:__imp_CoTaskMemRealloc
0x180003792  nop     dword ptr [rax+rax+00h]
0x180003797  test    rax, rax
0x18000379a  jz      short loc_180003808
0x18000379c  mov     [rdi+8], rax
0x1800037a0  mov     [rdi+4], ebx
0x1800037a3  cmp     dword ptr [rdi], 0
0x1800037a6  jl      short loc_180003808
0x1800037a8  cmp     [rdi], ebx
0x1800037aa  jge     short loc_180003808
0x1800037ac  mov     ecx, ebx
0x1800037ae  sub     ecx, [rdi]
0x1800037b0  cmp     ecx, ebx
0x1800037b2  jg      short loc_180003808
0x1800037b4  movsxd  rdx, ecx
0x1800037b7  lea     eax, [rsi+rsi]
0x1800037ba  movsxd  rcx, dword ptr [rdi]
0x1800037bd  add     rdx, rdx; DestinationSize
0x1800037c0  movsxd  r9, eax; SourceSize
0x1800037c3  mov     r8, rbp; Source
0x1800037c6  mov     rax, [rdi+8]
0x1800037ca  lea     rcx, [rax+rcx*2]; Destination
0x1800037ce  call    cs:__imp_memcpy_s
0x1800037d5  nop     dword ptr [rax+rax+00h]
0x1800037da  test    eax, eax
0x1800037dc  jz      short loc_1800037F2
0x1800037de  cmp     eax, 0Ch
0x1800037e1  jz      short loc_18000382A
0x1800037e3  cmp     eax, 16h
0x1800037e6  jz      short loc_18000381F
0x1800037e8  cmp     eax, 22h ; '"'
0x1800037eb  jz      short loc_18000381F
0x1800037ed  cmp     eax, 50h ; 'P'
0x1800037f0  jnz     short loc_180003814
0x1800037f2  add     [rdi], esi
0x1800037f4  movsxd  rdx, dword ptr [rdi]
0x1800037f7  xor     eax, eax
0x1800037f9  mov     rcx, [rdi+8]
0x1800037fd  mov     [rcx+rdx*2], ax
0x180003801  mov     eax, 1
0x180003806  jmp     short loc_18000380A
0x180003808  xor     eax, eax
0x18000380a  add     rsp, 28h
0x18000380e  pop     rdi
0x18000380f  pop     rsi
0x180003810  pop     rbp
0x180003811  pop     rbx
0x180003812  retn
0x180003814  mov     ecx, 80004005h; int
0x180003819  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000381f  mov     ecx, 80070057h; int
0x180003824  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000382a  mov     ecx, 8007000Eh; int
0x18000382f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
