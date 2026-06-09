# ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)

- ea: `0x18000ee58`
- end: `0x18000ef17`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z`
- size: `191`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f7e0`

## callees

- `0x18000a1b4`
- `0x18000ee58`
- `0x18000eff4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000eead`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000eead`

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
0x18000ee58  push    rbx
0x18000ee5a  push    rbp
0x18000ee5b  push    rsi
0x18000ee5c  push    rdi
0x18000ee5d  sub     rsp, 28h
0x18000ee61  mov     rdi, rcx
0x18000ee64  mov     esi, r8d
0x18000ee67  lea     ecx, [r8+1]
0x18000ee6b  mov     rbp, rdx
0x18000ee6e  add     ecx, [rdi]
0x18000ee70  cmp     ecx, [rdi]
0x18000ee72  jle     loc_18000EF0C
0x18000ee78  cmp     ecx, r8d
0x18000ee7b  jle     loc_18000EF0C
0x18000ee81  mov     ebx, [rdi+4]
0x18000ee84  cmp     ecx, ebx
0x18000ee86  jl      short loc_18000EEBF
0x18000ee88  cmp     ecx, ebx
0x18000ee8a  jl      short loc_18000EE98
0x18000ee8c  cmp     ebx, 3FFFFFFFh
0x18000ee92  jg      short loc_18000EF0C
0x18000ee94  add     ebx, ebx
0x18000ee96  jmp     short loc_18000EE88
0x18000ee98  mov     eax, ebx
0x18000ee9a  mov     ecx, 0FFFFFFFFh
0x18000ee9f  add     rax, rax
0x18000eea2  cmp     rax, rcx
0x18000eea5  ja      short loc_18000EF0C
0x18000eea7  mov     rcx, [rdi+8]; pv
0x18000eeab  mov     edx, eax; cb
0x18000eead  call    cs:__imp_CoTaskMemRealloc
0x18000eeb3  test    rax, rax
0x18000eeb6  jz      short loc_18000EF0C
0x18000eeb8  mov     [rdi+8], rax
0x18000eebc  mov     [rdi+4], ebx
0x18000eebf  cmp     dword ptr [rdi], 0
0x18000eec2  jl      short loc_18000EF0C
0x18000eec4  cmp     [rdi], ebx
0x18000eec6  jge     short loc_18000EF0C
0x18000eec8  mov     ecx, ebx
0x18000eeca  sub     ecx, [rdi]
0x18000eecc  cmp     ecx, ebx
0x18000eece  jg      short loc_18000EF0C
0x18000eed0  movsxd  rdx, ecx
0x18000eed3  lea     eax, [rsi+rsi]
0x18000eed6  movsxd  rcx, dword ptr [rdi]
0x18000eed9  add     rdx, rdx; DestinationSize
0x18000eedc  movsxd  r9, eax; SourceSize
0x18000eedf  mov     r8, rbp; Source
0x18000eee2  mov     rax, [rdi+8]
0x18000eee6  lea     rcx, [rax+rcx*2]; Destination
0x18000eeea  call    memcpy_s_0
0x18000eeef  mov     ecx, eax; int
0x18000eef1  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000eef6  add     [rdi], esi
0x18000eef8  movsxd  rdx, dword ptr [rdi]
0x18000eefb  xor     eax, eax
0x18000eefd  mov     rcx, [rdi+8]
0x18000ef01  mov     [rcx+rdx*2], ax
0x18000ef05  mov     eax, 1
0x18000ef0a  jmp     short loc_18000EF0E
0x18000ef0c  xor     eax, eax
0x18000ef0e  add     rsp, 28h
0x18000ef12  pop     rdi
0x18000ef13  pop     rsi
0x18000ef14  pop     rbp
0x18000ef15  pop     rbx
0x18000ef16  retn
```
