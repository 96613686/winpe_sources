# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800073b8`
- end: `0x180007478`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `192`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800085c8`

## callees

- `0x1800073b8`
- `0x180007594`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000744a`
- `msvcrt!memcpy_s` at `0x18000744a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000740d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000740d`

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
0x1800073b8  push    rbx
0x1800073ba  push    rbp
0x1800073bb  push    rsi
0x1800073bc  push    rdi
0x1800073bd  sub     rsp, 28h
0x1800073c1  mov     rdi, rcx
0x1800073c4  mov     esi, r8d
0x1800073c7  lea     ecx, [r8+1]
0x1800073cb  mov     rbp, rdx
0x1800073ce  add     ecx, [rdi]
0x1800073d0  cmp     ecx, [rdi]
0x1800073d2  jle     loc_18000746D
0x1800073d8  cmp     ecx, r8d
0x1800073db  jle     loc_18000746D
0x1800073e1  mov     ebx, [rdi+4]
0x1800073e4  cmp     ecx, ebx
0x1800073e6  jl      short loc_18000741F
0x1800073e8  cmp     ecx, ebx
0x1800073ea  jl      short loc_1800073F8
0x1800073ec  cmp     ebx, 3FFFFFFFh
0x1800073f2  jg      short loc_18000746D
0x1800073f4  add     ebx, ebx
0x1800073f6  jmp     short loc_1800073E8
0x1800073f8  mov     eax, ebx
0x1800073fa  mov     ecx, 0FFFFFFFFh
0x1800073ff  add     rax, rax
0x180007402  cmp     rax, rcx
0x180007405  ja      short loc_18000746D
0x180007407  mov     rcx, [rdi+8]; pv
0x18000740b  mov     edx, eax; cb
0x18000740d  call    cs:__imp_CoTaskMemRealloc
0x180007413  test    rax, rax
0x180007416  jz      short loc_18000746D
0x180007418  mov     [rdi+8], rax
0x18000741c  mov     [rdi+4], ebx
0x18000741f  cmp     dword ptr [rdi], 0
0x180007422  jl      short loc_18000746D
0x180007424  cmp     [rdi], ebx
0x180007426  jge     short loc_18000746D
0x180007428  mov     ecx, ebx
0x18000742a  sub     ecx, [rdi]
0x18000742c  cmp     ecx, ebx
0x18000742e  jg      short loc_18000746D
0x180007430  movsxd  rdx, ecx
0x180007433  lea     eax, [rsi+rsi]
0x180007436  movsxd  rcx, dword ptr [rdi]
0x180007439  add     rdx, rdx; DestinationSize
0x18000743c  movsxd  r9, eax; SourceSize
0x18000743f  mov     r8, rbp; Source
0x180007442  mov     rax, [rdi+8]
0x180007446  lea     rcx, [rax+rcx*2]; Destination
0x18000744a  call    cs:__imp_memcpy_s
0x180007450  mov     ecx, eax; int
0x180007452  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007457  add     [rdi], esi
0x180007459  movsxd  rdx, dword ptr [rdi]
0x18000745c  xor     eax, eax
0x18000745e  mov     rcx, [rdi+8]
0x180007462  mov     [rcx+rdx*2], ax
0x180007466  mov     eax, 1
0x18000746b  jmp     short loc_18000746F
0x18000746d  xor     eax, eax
0x18000746f  add     rsp, 28h
0x180007473  pop     rdi
0x180007474  pop     rsi
0x180007475  pop     rbp
0x180007476  pop     rbx
0x180007477  retn
```
