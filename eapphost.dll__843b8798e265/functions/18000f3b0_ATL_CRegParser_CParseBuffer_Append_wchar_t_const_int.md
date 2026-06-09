# ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)

- ea: `0x18000f3b0`
- end: `0x18000f476`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z`
- size: `198`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fe68`

## callees

- `0x18000a658`
- `0x18000f3b0`
- `0x18000f558`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f405`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f405`

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
        v11 = memcpy_s_0((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v10, a2, 2 * a3);
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
0x18000f3b0  push    rbx
0x18000f3b2  push    rbp
0x18000f3b3  push    rsi
0x18000f3b4  push    rdi
0x18000f3b5  sub     rsp, 28h
0x18000f3b9  mov     rdi, rcx
0x18000f3bc  mov     esi, r8d
0x18000f3bf  lea     ecx, [r8+1]
0x18000f3c3  mov     rbp, rdx
0x18000f3c6  add     ecx, [rdi]
0x18000f3c8  cmp     ecx, [rdi]
0x18000f3ca  jle     loc_18000F46A
0x18000f3d0  cmp     ecx, r8d
0x18000f3d3  jle     loc_18000F46A
0x18000f3d9  mov     ebx, [rdi+4]
0x18000f3dc  cmp     ecx, ebx
0x18000f3de  jl      short loc_18000F41D
0x18000f3e0  cmp     ecx, ebx
0x18000f3e2  jl      short loc_18000F3F0
0x18000f3e4  cmp     ebx, 3FFFFFFFh
0x18000f3ea  jg      short loc_18000F46A
0x18000f3ec  add     ebx, ebx
0x18000f3ee  jmp     short loc_18000F3E0
0x18000f3f0  mov     eax, ebx
0x18000f3f2  mov     ecx, 0FFFFFFFFh
0x18000f3f7  add     rax, rax
0x18000f3fa  cmp     rax, rcx
0x18000f3fd  ja      short loc_18000F46A
0x18000f3ff  mov     rcx, [rdi+8]; pv
0x18000f403  mov     edx, eax; cb
0x18000f405  call    cs:__imp_CoTaskMemRealloc
0x18000f40c  nop     dword ptr [rax+rax+00h]
0x18000f411  test    rax, rax
0x18000f414  jz      short loc_18000F46A
0x18000f416  mov     [rdi+8], rax
0x18000f41a  mov     [rdi+4], ebx
0x18000f41d  cmp     dword ptr [rdi], 0
0x18000f420  jl      short loc_18000F46A
0x18000f422  cmp     [rdi], ebx
0x18000f424  jge     short loc_18000F46A
0x18000f426  mov     ecx, ebx
0x18000f428  sub     ecx, [rdi]
0x18000f42a  cmp     ecx, ebx
0x18000f42c  jg      short loc_18000F46A
0x18000f42e  movsxd  rdx, ecx
0x18000f431  lea     eax, [rsi+rsi]
0x18000f434  movsxd  rcx, dword ptr [rdi]
0x18000f437  add     rdx, rdx; DestinationSize
0x18000f43a  movsxd  r9, eax; SourceSize
0x18000f43d  mov     r8, rbp; Source
0x18000f440  mov     rax, [rdi+8]
0x18000f444  lea     rcx, [rax+rcx*2]; Destination
0x18000f448  call    memcpy_s_0
0x18000f44d  mov     ecx, eax; int
0x18000f44f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000f454  add     [rdi], esi
0x18000f456  movsxd  rdx, dword ptr [rdi]
0x18000f459  xor     eax, eax
0x18000f45b  mov     rcx, [rdi+8]
0x18000f45f  mov     [rcx+rdx*2], ax
0x18000f463  mov     eax, 1
0x18000f468  jmp     short loc_18000F46C
0x18000f46a  xor     eax, eax
0x18000f46c  add     rsp, 28h
0x18000f470  pop     rdi
0x18000f471  pop     rsi
0x18000f472  pop     rbp
0x18000f473  pop     rbx
0x18000f474  retn
```
