# ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)

- ea: `0x18000f898`
- end: `0x18000f957`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z`
- size: `191`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001009c`

## callees

- `0x180003938`
- `0x18000f898`
- `0x18000fa74`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f8ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f8ed`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const wchar_t *a2,
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
0x18000f898  push    rbx
0x18000f89a  push    rbp
0x18000f89b  push    rsi
0x18000f89c  push    rdi
0x18000f89d  sub     rsp, 28h
0x18000f8a1  mov     rdi, rcx
0x18000f8a4  mov     esi, r8d
0x18000f8a7  lea     ecx, [r8+1]
0x18000f8ab  mov     rbp, rdx
0x18000f8ae  add     ecx, [rdi]
0x18000f8b0  cmp     ecx, [rdi]
0x18000f8b2  jle     loc_18000F94C
0x18000f8b8  cmp     ecx, r8d
0x18000f8bb  jle     loc_18000F94C
0x18000f8c1  mov     ebx, [rdi+4]
0x18000f8c4  cmp     ecx, ebx
0x18000f8c6  jl      short loc_18000F8FF
0x18000f8c8  cmp     ecx, ebx
0x18000f8ca  jl      short loc_18000F8D8
0x18000f8cc  cmp     ebx, 3FFFFFFFh
0x18000f8d2  jg      short loc_18000F94C
0x18000f8d4  add     ebx, ebx
0x18000f8d6  jmp     short loc_18000F8C8
0x18000f8d8  mov     eax, ebx
0x18000f8da  mov     ecx, 0FFFFFFFFh
0x18000f8df  add     rax, rax
0x18000f8e2  cmp     rax, rcx
0x18000f8e5  ja      short loc_18000F94C
0x18000f8e7  mov     rcx, [rdi+8]; pv
0x18000f8eb  mov     edx, eax; cb
0x18000f8ed  call    cs:__imp_CoTaskMemRealloc
0x18000f8f3  test    rax, rax
0x18000f8f6  jz      short loc_18000F94C
0x18000f8f8  mov     [rdi+8], rax
0x18000f8fc  mov     [rdi+4], ebx
0x18000f8ff  cmp     dword ptr [rdi], 0
0x18000f902  jl      short loc_18000F94C
0x18000f904  cmp     [rdi], ebx
0x18000f906  jge     short loc_18000F94C
0x18000f908  mov     ecx, ebx
0x18000f90a  sub     ecx, [rdi]
0x18000f90c  cmp     ecx, ebx
0x18000f90e  jg      short loc_18000F94C
0x18000f910  movsxd  rdx, ecx
0x18000f913  lea     eax, [rsi+rsi]
0x18000f916  movsxd  rcx, dword ptr [rdi]
0x18000f919  add     rdx, rdx; DestinationSize
0x18000f91c  movsxd  r9, eax; SourceSize
0x18000f91f  mov     r8, rbp; Source
0x18000f922  mov     rax, [rdi+8]
0x18000f926  lea     rcx, [rax+rcx*2]; Destination
0x18000f92a  call    memcpy_s
0x18000f92f  mov     ecx, eax; int
0x18000f931  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000f936  add     [rdi], esi
0x18000f938  movsxd  rdx, dword ptr [rdi]
0x18000f93b  xor     eax, eax
0x18000f93d  mov     rcx, [rdi+8]
0x18000f941  mov     [rcx+rdx*2], ax
0x18000f945  mov     eax, 1
0x18000f94a  jmp     short loc_18000F94E
0x18000f94c  xor     eax, eax
0x18000f94e  add     rsp, 28h
0x18000f952  pop     rdi
0x18000f953  pop     rsi
0x18000f954  pop     rbp
0x18000f955  pop     rbx
0x18000f956  retn
```
