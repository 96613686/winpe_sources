# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180006d38`
- end: `0x180006df8`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `192`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ca4c`

## callees

- `0x180006d38`
- `0x180006f14`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006dca`
- `msvcrt!memcpy_s` at `0x180006dca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180006d8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180006d8d`

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
0x180006d38  push    rbx
0x180006d3a  push    rbp
0x180006d3b  push    rsi
0x180006d3c  push    rdi
0x180006d3d  sub     rsp, 28h
0x180006d41  mov     rdi, rcx
0x180006d44  mov     esi, r8d
0x180006d47  lea     ecx, [r8+1]
0x180006d4b  mov     rbp, rdx
0x180006d4e  add     ecx, [rdi]
0x180006d50  cmp     ecx, [rdi]
0x180006d52  jle     loc_180006DED
0x180006d58  cmp     ecx, r8d
0x180006d5b  jle     loc_180006DED
0x180006d61  mov     ebx, [rdi+4]
0x180006d64  cmp     ecx, ebx
0x180006d66  jl      short loc_180006D9F
0x180006d68  cmp     ecx, ebx
0x180006d6a  jl      short loc_180006D78
0x180006d6c  cmp     ebx, 3FFFFFFFh
0x180006d72  jg      short loc_180006DED
0x180006d74  add     ebx, ebx
0x180006d76  jmp     short loc_180006D68
0x180006d78  mov     eax, ebx
0x180006d7a  mov     ecx, 0FFFFFFFFh
0x180006d7f  add     rax, rax
0x180006d82  cmp     rax, rcx
0x180006d85  ja      short loc_180006DED
0x180006d87  mov     rcx, [rdi+8]; pv
0x180006d8b  mov     edx, eax; cb
0x180006d8d  call    cs:__imp_CoTaskMemRealloc
0x180006d93  test    rax, rax
0x180006d96  jz      short loc_180006DED
0x180006d98  mov     [rdi+8], rax
0x180006d9c  mov     [rdi+4], ebx
0x180006d9f  cmp     dword ptr [rdi], 0
0x180006da2  jl      short loc_180006DED
0x180006da4  cmp     [rdi], ebx
0x180006da6  jge     short loc_180006DED
0x180006da8  mov     ecx, ebx
0x180006daa  sub     ecx, [rdi]
0x180006dac  cmp     ecx, ebx
0x180006dae  jg      short loc_180006DED
0x180006db0  movsxd  rdx, ecx
0x180006db3  lea     eax, [rsi+rsi]
0x180006db6  movsxd  rcx, dword ptr [rdi]
0x180006db9  add     rdx, rdx; DestinationSize
0x180006dbc  movsxd  r9, eax; SourceSize
0x180006dbf  mov     r8, rbp; Source
0x180006dc2  mov     rax, [rdi+8]
0x180006dc6  lea     rcx, [rax+rcx*2]; Destination
0x180006dca  call    cs:__imp_memcpy_s
0x180006dd0  mov     ecx, eax; int
0x180006dd2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006dd7  add     [rdi], esi
0x180006dd9  movsxd  rdx, dword ptr [rdi]
0x180006ddc  xor     eax, eax
0x180006dde  mov     rcx, [rdi+8]
0x180006de2  mov     [rcx+rdx*2], ax
0x180006de6  mov     eax, 1
0x180006deb  jmp     short loc_180006DEF
0x180006ded  xor     eax, eax
0x180006def  add     rsp, 28h
0x180006df3  pop     rdi
0x180006df4  pop     rsi
0x180006df5  pop     rbp
0x180006df6  pop     rbx
0x180006df7  retn
```
