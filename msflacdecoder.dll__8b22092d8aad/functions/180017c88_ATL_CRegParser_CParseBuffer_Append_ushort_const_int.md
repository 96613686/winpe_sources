# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180017c88`
- end: `0x180017d47`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `191`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019b28`

## callees

- `0x180017c88`
- `0x180017ebc`
- `0x18001c638`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180017cdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180017cdd`

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
0x180017c88  push    rbx
0x180017c8a  push    rbp
0x180017c8b  push    rsi
0x180017c8c  push    rdi
0x180017c8d  sub     rsp, 28h
0x180017c91  mov     rdi, rcx
0x180017c94  mov     esi, r8d
0x180017c97  lea     ecx, [r8+1]
0x180017c9b  mov     rbp, rdx
0x180017c9e  add     ecx, [rdi]
0x180017ca0  cmp     ecx, [rdi]
0x180017ca2  jle     loc_180017D3C
0x180017ca8  cmp     ecx, r8d
0x180017cab  jle     loc_180017D3C
0x180017cb1  mov     ebx, [rdi+4]
0x180017cb4  cmp     ecx, ebx
0x180017cb6  jl      short loc_180017CEF
0x180017cb8  cmp     ecx, ebx
0x180017cba  jl      short loc_180017CC8
0x180017cbc  cmp     ebx, 3FFFFFFFh
0x180017cc2  jg      short loc_180017D3C
0x180017cc4  add     ebx, ebx
0x180017cc6  jmp     short loc_180017CB8
0x180017cc8  mov     eax, ebx
0x180017cca  mov     ecx, 0FFFFFFFFh
0x180017ccf  add     rax, rax
0x180017cd2  cmp     rax, rcx
0x180017cd5  ja      short loc_180017D3C
0x180017cd7  mov     rcx, [rdi+8]; pv
0x180017cdb  mov     edx, eax; cb
0x180017cdd  call    cs:__imp_CoTaskMemRealloc
0x180017ce3  test    rax, rax
0x180017ce6  jz      short loc_180017D3C
0x180017ce8  mov     [rdi+8], rax
0x180017cec  mov     [rdi+4], ebx
0x180017cef  cmp     dword ptr [rdi], 0
0x180017cf2  jl      short loc_180017D3C
0x180017cf4  cmp     [rdi], ebx
0x180017cf6  jge     short loc_180017D3C
0x180017cf8  mov     ecx, ebx
0x180017cfa  sub     ecx, [rdi]
0x180017cfc  cmp     ecx, ebx
0x180017cfe  jg      short loc_180017D3C
0x180017d00  movsxd  rdx, ecx
0x180017d03  lea     eax, [rsi+rsi]
0x180017d06  movsxd  rcx, dword ptr [rdi]
0x180017d09  add     rdx, rdx; DestinationSize
0x180017d0c  movsxd  r9, eax; SourceSize
0x180017d0f  mov     r8, rbp; Source
0x180017d12  mov     rax, [rdi+8]
0x180017d16  lea     rcx, [rax+rcx*2]; Destination
0x180017d1a  call    memcpy_s
0x180017d1f  mov     ecx, eax; int
0x180017d21  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180017d26  add     [rdi], esi
0x180017d28  movsxd  rdx, dword ptr [rdi]
0x180017d2b  xor     eax, eax
0x180017d2d  mov     rcx, [rdi+8]
0x180017d31  mov     [rcx+rdx*2], ax
0x180017d35  mov     eax, 1
0x180017d3a  jmp     short loc_180017D3E
0x180017d3c  xor     eax, eax
0x180017d3e  add     rsp, 28h
0x180017d42  pop     rdi
0x180017d43  pop     rsi
0x180017d44  pop     rbp
0x180017d45  pop     rbx
0x180017d46  retn
```
