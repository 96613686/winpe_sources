# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18000a818`
- end: `0x18000a8d7`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `191`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012918`

## callees

- `0x180004198`
- `0x18000a818`
- `0x18000a938`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000a86d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000a86d`

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
  if ( v6 > *(_DWORD *)this && v6 > a3 )
  {
    v7 = *((_DWORD *)this + 1);
    if ( v6 >= v7 )
    {
      while ( v6 >= v7 )
      {
        if ( v7 > 0x3FFFFFFF )
          return 0;
        v7 *= 2;
      }
      v8 = 2LL * (unsigned int)v7;
      if ( v8 > 0xFFFFFFFF )
        return 0;
      v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
      if ( !v9 )
        return 0;
      *((_QWORD *)this + 1) = v9;
      *((_DWORD *)this + 1) = v7;
    }
    if ( *(int *)this >= 0 && *(_DWORD *)this < v7 )
    {
      v10 = v7 - *(_DWORD *)this;
      if ( v10 <= v7 )
      {
        v11 = memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v10, a2, 2 * a3);
        ATL::AtlCrtErrorCheck(v11);
        *(_DWORD *)this += a3;
        *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a818  push    rbx
0x18000a81a  push    rbp
0x18000a81b  push    rsi
0x18000a81c  push    rdi
0x18000a81d  sub     rsp, 28h
0x18000a821  mov     rdi, rcx
0x18000a824  mov     esi, r8d
0x18000a827  lea     ecx, [r8+1]
0x18000a82b  mov     rbp, rdx
0x18000a82e  add     ecx, [rdi]
0x18000a830  cmp     ecx, [rdi]
0x18000a832  jle     loc_18000A8CC
0x18000a838  cmp     ecx, r8d
0x18000a83b  jle     loc_18000A8CC
0x18000a841  mov     ebx, [rdi+4]
0x18000a844  cmp     ecx, ebx
0x18000a846  jl      short loc_18000A87F
0x18000a848  cmp     ecx, ebx
0x18000a84a  jl      short loc_18000A858
0x18000a84c  cmp     ebx, 3FFFFFFFh
0x18000a852  jg      short loc_18000A8CC
0x18000a854  add     ebx, ebx
0x18000a856  jmp     short loc_18000A848
0x18000a858  mov     eax, ebx
0x18000a85a  mov     ecx, 0FFFFFFFFh
0x18000a85f  add     rax, rax
0x18000a862  cmp     rax, rcx
0x18000a865  ja      short loc_18000A8CC
0x18000a867  mov     rcx, [rdi+8]; pv
0x18000a86b  mov     edx, eax; cb
0x18000a86d  call    cs:__imp_CoTaskMemRealloc
0x18000a873  test    rax, rax
0x18000a876  jz      short loc_18000A8CC
0x18000a878  mov     [rdi+8], rax
0x18000a87c  mov     [rdi+4], ebx
0x18000a87f  cmp     dword ptr [rdi], 0
0x18000a882  jl      short loc_18000A8CC
0x18000a884  cmp     [rdi], ebx
0x18000a886  jge     short loc_18000A8CC
0x18000a888  mov     ecx, ebx
0x18000a88a  sub     ecx, [rdi]
0x18000a88c  cmp     ecx, ebx
0x18000a88e  jg      short loc_18000A8CC
0x18000a890  movsxd  rdx, ecx
0x18000a893  lea     eax, [rsi+rsi]
0x18000a896  movsxd  rcx, dword ptr [rdi]
0x18000a899  add     rdx, rdx; DestinationSize
0x18000a89c  movsxd  r9, eax; SourceSize
0x18000a89f  mov     r8, rbp; Source
0x18000a8a2  mov     rax, [rdi+8]
0x18000a8a6  lea     rcx, [rax+rcx*2]; Destination
0x18000a8aa  call    memcpy_s
0x18000a8af  mov     ecx, eax; int
0x18000a8b1  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000a8b6  add     [rdi], esi
0x18000a8b8  movsxd  rdx, dword ptr [rdi]
0x18000a8bb  xor     eax, eax
0x18000a8bd  mov     rcx, [rdi+8]
0x18000a8c1  mov     [rcx+rdx*2], ax
0x18000a8c5  mov     eax, 1
0x18000a8ca  jmp     short loc_18000A8CE
0x18000a8cc  xor     eax, eax
0x18000a8ce  add     rsp, 28h
0x18000a8d2  pop     rdi
0x18000a8d3  pop     rsi
0x18000a8d4  pop     rbp
0x18000a8d5  pop     rbx
0x18000a8d6  retn
```
