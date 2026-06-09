# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180023f28`
- end: `0x180023fe7`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `191`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002468c`

## callees

- `0x180023f28`
- `0x180024068`
- `0x180025a60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180023f7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180023f7d`

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
0x180023f28  push    rbx
0x180023f2a  push    rbp
0x180023f2b  push    rsi
0x180023f2c  push    rdi
0x180023f2d  sub     rsp, 28h
0x180023f31  mov     rdi, rcx
0x180023f34  mov     esi, r8d
0x180023f37  lea     ecx, [r8+1]
0x180023f3b  mov     rbp, rdx
0x180023f3e  add     ecx, [rdi]
0x180023f40  cmp     ecx, [rdi]
0x180023f42  jle     loc_180023FDC
0x180023f48  cmp     ecx, r8d
0x180023f4b  jle     loc_180023FDC
0x180023f51  mov     ebx, [rdi+4]
0x180023f54  cmp     ecx, ebx
0x180023f56  jl      short loc_180023F8F
0x180023f58  cmp     ecx, ebx
0x180023f5a  jl      short loc_180023F68
0x180023f5c  cmp     ebx, 3FFFFFFFh
0x180023f62  jg      short loc_180023FDC
0x180023f64  add     ebx, ebx
0x180023f66  jmp     short loc_180023F58
0x180023f68  mov     eax, ebx
0x180023f6a  mov     ecx, 0FFFFFFFFh
0x180023f6f  add     rax, rax
0x180023f72  cmp     rax, rcx
0x180023f75  ja      short loc_180023FDC
0x180023f77  mov     rcx, [rdi+8]; pv
0x180023f7b  mov     edx, eax; cb
0x180023f7d  call    cs:__imp_CoTaskMemRealloc
0x180023f83  test    rax, rax
0x180023f86  jz      short loc_180023FDC
0x180023f88  mov     [rdi+8], rax
0x180023f8c  mov     [rdi+4], ebx
0x180023f8f  cmp     dword ptr [rdi], 0
0x180023f92  jl      short loc_180023FDC
0x180023f94  cmp     [rdi], ebx
0x180023f96  jge     short loc_180023FDC
0x180023f98  mov     ecx, ebx
0x180023f9a  sub     ecx, [rdi]
0x180023f9c  cmp     ecx, ebx
0x180023f9e  jg      short loc_180023FDC
0x180023fa0  movsxd  rdx, ecx
0x180023fa3  lea     eax, [rsi+rsi]
0x180023fa6  movsxd  rcx, dword ptr [rdi]
0x180023fa9  add     rdx, rdx; DestinationSize
0x180023fac  movsxd  r9, eax; SourceSize
0x180023faf  mov     r8, rbp; Source
0x180023fb2  mov     rax, [rdi+8]
0x180023fb6  lea     rcx, [rax+rcx*2]; Destination
0x180023fba  call    memcpy_s_0
0x180023fbf  mov     ecx, eax; int
0x180023fc1  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180023fc6  add     [rdi], esi
0x180023fc8  movsxd  rdx, dword ptr [rdi]
0x180023fcb  xor     eax, eax
0x180023fcd  mov     rcx, [rdi+8]
0x180023fd1  mov     [rcx+rdx*2], ax
0x180023fd5  mov     eax, 1
0x180023fda  jmp     short loc_180023FDE
0x180023fdc  xor     eax, eax
0x180023fde  add     rsp, 28h
0x180023fe2  pop     rdi
0x180023fe3  pop     rsi
0x180023fe4  pop     rbp
0x180023fe5  pop     rbx
0x180023fe6  retn
```
