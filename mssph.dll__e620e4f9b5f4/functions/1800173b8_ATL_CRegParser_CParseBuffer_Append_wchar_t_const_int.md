# ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)

- ea: `0x1800173b8`
- end: `0x180017477`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z`
- size: `191`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019e88`

## callees

- `0x18000ebb0`
- `0x1800173b8`
- `0x18001760c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001740d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001740d`

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
0x1800173b8  push    rbx
0x1800173ba  push    rbp
0x1800173bb  push    rsi
0x1800173bc  push    rdi
0x1800173bd  sub     rsp, 28h
0x1800173c1  mov     rdi, rcx
0x1800173c4  mov     esi, r8d
0x1800173c7  lea     ecx, [r8+1]
0x1800173cb  mov     rbp, rdx
0x1800173ce  add     ecx, [rdi]
0x1800173d0  cmp     ecx, [rdi]
0x1800173d2  jle     loc_18001746C
0x1800173d8  cmp     ecx, r8d
0x1800173db  jle     loc_18001746C
0x1800173e1  mov     ebx, [rdi+4]
0x1800173e4  cmp     ecx, ebx
0x1800173e6  jl      short loc_18001741F
0x1800173e8  cmp     ecx, ebx
0x1800173ea  jl      short loc_1800173F8
0x1800173ec  cmp     ebx, 3FFFFFFFh
0x1800173f2  jg      short loc_18001746C
0x1800173f4  add     ebx, ebx
0x1800173f6  jmp     short loc_1800173E8
0x1800173f8  mov     eax, ebx
0x1800173fa  mov     ecx, 0FFFFFFFFh
0x1800173ff  add     rax, rax
0x180017402  cmp     rax, rcx
0x180017405  ja      short loc_18001746C
0x180017407  mov     rcx, [rdi+8]; pv
0x18001740b  mov     edx, eax; cb
0x18001740d  call    cs:__imp_CoTaskMemRealloc
0x180017413  test    rax, rax
0x180017416  jz      short loc_18001746C
0x180017418  mov     [rdi+8], rax
0x18001741c  mov     [rdi+4], ebx
0x18001741f  cmp     dword ptr [rdi], 0
0x180017422  jl      short loc_18001746C
0x180017424  cmp     [rdi], ebx
0x180017426  jge     short loc_18001746C
0x180017428  mov     ecx, ebx
0x18001742a  sub     ecx, [rdi]
0x18001742c  cmp     ecx, ebx
0x18001742e  jg      short loc_18001746C
0x180017430  movsxd  rdx, ecx
0x180017433  lea     eax, [rsi+rsi]
0x180017436  movsxd  rcx, dword ptr [rdi]
0x180017439  add     rdx, rdx; DestinationSize
0x18001743c  movsxd  r9, eax; SourceSize
0x18001743f  mov     r8, rbp; Source
0x180017442  mov     rax, [rdi+8]
0x180017446  lea     rcx, [rax+rcx*2]; Destination
0x18001744a  call    memcpy_s
0x18001744f  mov     ecx, eax; int
0x180017451  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180017456  add     [rdi], esi
0x180017458  movsxd  rdx, dword ptr [rdi]
0x18001745b  xor     eax, eax
0x18001745d  mov     rcx, [rdi+8]
0x180017461  mov     [rcx+rdx*2], ax
0x180017465  mov     eax, 1
0x18001746a  jmp     short loc_18001746E
0x18001746c  xor     eax, eax
0x18001746e  add     rsp, 28h
0x180017472  pop     rdi
0x180017473  pop     rsi
0x180017474  pop     rbp
0x180017475  pop     rbx
0x180017476  retn
```
