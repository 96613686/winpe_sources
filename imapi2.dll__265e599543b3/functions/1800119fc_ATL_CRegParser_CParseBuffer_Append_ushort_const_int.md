# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800119fc`
- end: `0x180011abc`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `192`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180012918`

## callees

- `0x1800119fc`
- `0x180011ac4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180011a8e`
- `msvcrt!memcpy_s` at `0x180011a8e`
- `ole32!CoTaskMemRealloc` at `0x180011a51`
- `ole32!CoTaskMemRealloc` at `0x180011a51`

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
0x1800119fc  push    rbx
0x1800119fe  push    rbp
0x1800119ff  push    rsi
0x180011a00  push    rdi
0x180011a01  sub     rsp, 28h
0x180011a05  mov     rdi, rcx
0x180011a08  mov     esi, r8d
0x180011a0b  lea     ecx, [r8+1]
0x180011a0f  mov     rbp, rdx
0x180011a12  add     ecx, [rdi]
0x180011a14  cmp     ecx, [rdi]
0x180011a16  jle     loc_180011AB1
0x180011a1c  cmp     ecx, r8d
0x180011a1f  jle     loc_180011AB1
0x180011a25  mov     ebx, [rdi+4]
0x180011a28  cmp     ecx, ebx
0x180011a2a  jl      short loc_180011A63
0x180011a2c  cmp     ecx, ebx
0x180011a2e  jl      short loc_180011A3C
0x180011a30  cmp     ebx, 3FFFFFFFh
0x180011a36  jg      short loc_180011AB1
0x180011a38  add     ebx, ebx
0x180011a3a  jmp     short loc_180011A2C
0x180011a3c  mov     eax, ebx
0x180011a3e  mov     ecx, 0FFFFFFFFh
0x180011a43  add     rax, rax
0x180011a46  cmp     rax, rcx
0x180011a49  ja      short loc_180011AB1
0x180011a4b  mov     rcx, [rdi+8]; pv
0x180011a4f  mov     edx, eax; cb
0x180011a51  call    cs:__imp_CoTaskMemRealloc
0x180011a57  test    rax, rax
0x180011a5a  jz      short loc_180011AB1
0x180011a5c  mov     [rdi+8], rax
0x180011a60  mov     [rdi+4], ebx
0x180011a63  cmp     dword ptr [rdi], 0
0x180011a66  jl      short loc_180011AB1
0x180011a68  cmp     [rdi], ebx
0x180011a6a  jge     short loc_180011AB1
0x180011a6c  mov     ecx, ebx
0x180011a6e  sub     ecx, [rdi]
0x180011a70  cmp     ecx, ebx
0x180011a72  jg      short loc_180011AB1
0x180011a74  movsxd  rdx, ecx
0x180011a77  lea     eax, [rsi+rsi]
0x180011a7a  movsxd  rcx, dword ptr [rdi]
0x180011a7d  add     rdx, rdx; DestinationSize
0x180011a80  movsxd  r9, eax; SourceSize
0x180011a83  mov     r8, rbp; Source
0x180011a86  mov     rax, [rdi+8]
0x180011a8a  lea     rcx, [rax+rcx*2]; Destination
0x180011a8e  call    cs:__imp_memcpy_s
0x180011a94  mov     ecx, eax; int
0x180011a96  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180011a9b  add     [rdi], esi
0x180011a9d  movsxd  rdx, dword ptr [rdi]
0x180011aa0  xor     eax, eax
0x180011aa2  mov     rcx, [rdi+8]
0x180011aa6  mov     [rcx+rdx*2], ax
0x180011aaa  mov     eax, 1
0x180011aaf  jmp     short loc_180011AB3
0x180011ab1  xor     eax, eax
0x180011ab3  add     rsp, 28h
0x180011ab7  pop     rdi
0x180011ab8  pop     rsi
0x180011ab9  pop     rbp
0x180011aba  pop     rbx
0x180011abb  retn
```
