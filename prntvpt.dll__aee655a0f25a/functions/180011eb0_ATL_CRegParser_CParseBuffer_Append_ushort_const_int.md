# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180011eb0`
- end: `0x180011f6f`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `191`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001472c`

## callees

- `0x18000d3c8`
- `0x180011eb0`
- `0x180011f78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180011f05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180011f05`

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
0x180011eb0  push    rbx
0x180011eb2  push    rbp
0x180011eb3  push    rsi
0x180011eb4  push    rdi
0x180011eb5  sub     rsp, 28h
0x180011eb9  mov     rdi, rcx
0x180011ebc  mov     esi, r8d
0x180011ebf  lea     ecx, [r8+1]
0x180011ec3  mov     rbp, rdx
0x180011ec6  add     ecx, [rdi]
0x180011ec8  cmp     ecx, [rdi]
0x180011eca  jle     loc_180011F64
0x180011ed0  cmp     ecx, r8d
0x180011ed3  jle     loc_180011F64
0x180011ed9  mov     ebx, [rdi+4]
0x180011edc  cmp     ecx, ebx
0x180011ede  jl      short loc_180011F17
0x180011ee0  cmp     ecx, ebx
0x180011ee2  jl      short loc_180011EF0
0x180011ee4  cmp     ebx, 3FFFFFFFh
0x180011eea  jg      short loc_180011F64
0x180011eec  add     ebx, ebx
0x180011eee  jmp     short loc_180011EE0
0x180011ef0  mov     eax, ebx
0x180011ef2  mov     ecx, 0FFFFFFFFh
0x180011ef7  add     rax, rax
0x180011efa  cmp     rax, rcx
0x180011efd  ja      short loc_180011F64
0x180011eff  mov     rcx, [rdi+8]; pv
0x180011f03  mov     edx, eax; cb
0x180011f05  call    cs:__imp_CoTaskMemRealloc
0x180011f0b  test    rax, rax
0x180011f0e  jz      short loc_180011F64
0x180011f10  mov     [rdi+8], rax
0x180011f14  mov     [rdi+4], ebx
0x180011f17  cmp     dword ptr [rdi], 0
0x180011f1a  jl      short loc_180011F64
0x180011f1c  cmp     [rdi], ebx
0x180011f1e  jge     short loc_180011F64
0x180011f20  mov     ecx, ebx
0x180011f22  sub     ecx, [rdi]
0x180011f24  cmp     ecx, ebx
0x180011f26  jg      short loc_180011F64
0x180011f28  movsxd  rdx, ecx
0x180011f2b  lea     eax, [rsi+rsi]
0x180011f2e  movsxd  rcx, dword ptr [rdi]
0x180011f31  add     rdx, rdx; DestinationSize
0x180011f34  movsxd  r9, eax; SourceSize
0x180011f37  mov     r8, rbp; Source
0x180011f3a  mov     rax, [rdi+8]
0x180011f3e  lea     rcx, [rax+rcx*2]; Destination
0x180011f42  call    memcpy_s
0x180011f47  mov     ecx, eax; int
0x180011f49  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180011f4e  add     [rdi], esi
0x180011f50  movsxd  rdx, dword ptr [rdi]
0x180011f53  xor     eax, eax
0x180011f55  mov     rcx, [rdi+8]
0x180011f59  mov     [rcx+rdx*2], ax
0x180011f5d  mov     eax, 1
0x180011f62  jmp     short loc_180011F66
0x180011f64  xor     eax, eax
0x180011f66  add     rsp, 28h
0x180011f6a  pop     rdi
0x180011f6b  pop     rsi
0x180011f6c  pop     rbp
0x180011f6d  pop     rbx
0x180011f6e  retn
```
