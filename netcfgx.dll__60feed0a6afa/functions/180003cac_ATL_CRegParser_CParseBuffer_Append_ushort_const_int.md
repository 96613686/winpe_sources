# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180003cac`
- end: `0x180003d62`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `182`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000498c`

## callees

- `0x180003cac`
- `0x1800063d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003cff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003cff`

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
  unsigned __int64 v12; // [rsp+20h] [rbp-28h]

  v6 = *(_DWORD *)this + a3 + 1;
  if ( v6 > *(_DWORD *)this && v6 > a3 )
  {
    v7 = *((_DWORD *)this + 1);
    if ( v6 < v7 )
    {
LABEL_9:
      if ( *(int *)this >= 0 && *(_DWORD *)this < v7 )
      {
        v10 = v7 - *(_DWORD *)this;
        if ( v10 <= v7 )
        {
          ATL::Checked::memcpy_s(
            (ATL::Checked *)(*((_QWORD *)this + 1) + 2LL * *(int *)this),
            (void *)(2LL * v10),
            (unsigned __int64)a2,
            (const void *)(2 * a3),
            v12);
          *(_DWORD *)this += a3;
          *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
          return 1;
        }
      }
    }
    else
    {
      while ( v7 <= 0x3FFFFFFF )
      {
        v7 *= 2;
        if ( v6 < v7 )
        {
          v8 = 2LL * (unsigned int)v7;
          if ( v8 <= 0xFFFFFFFF )
          {
            v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
            if ( v9 )
            {
              *((_QWORD *)this + 1) = v9;
              *((_DWORD *)this + 1) = v7;
              goto LABEL_9;
            }
          }
          return 0;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003cac  push    rbx
0x180003cae  push    rbp
0x180003caf  push    rsi
0x180003cb0  push    rdi
0x180003cb1  sub     rsp, 28h
0x180003cb5  mov     rdi, rcx
0x180003cb8  mov     esi, r8d
0x180003cbb  lea     ecx, [r8+1]
0x180003cbf  mov     rbp, rdx
0x180003cc2  add     ecx, [rdi]
0x180003cc4  cmp     ecx, [rdi]
0x180003cc6  jle     loc_180003D57
0x180003ccc  cmp     ecx, r8d
0x180003ccf  jle     loc_180003D57
0x180003cd5  mov     ebx, [rdi+4]
0x180003cd8  cmp     ecx, ebx
0x180003cda  jl      short loc_180003D11
0x180003cdc  cmp     ebx, 3FFFFFFFh
0x180003ce2  jg      short loc_180003D57
0x180003ce4  add     ebx, ebx
0x180003ce6  cmp     ecx, ebx
0x180003ce8  jge     short loc_180003CDC
0x180003cea  mov     eax, ebx
0x180003cec  mov     ecx, 0FFFFFFFFh
0x180003cf1  add     rax, rax
0x180003cf4  cmp     rax, rcx
0x180003cf7  ja      short loc_180003D57
0x180003cf9  mov     rcx, [rdi+8]; pv
0x180003cfd  mov     edx, eax; cb
0x180003cff  call    cs:__imp_CoTaskMemRealloc
0x180003d05  test    rax, rax
0x180003d08  jz      short loc_180003D57
0x180003d0a  mov     [rdi+8], rax
0x180003d0e  mov     [rdi+4], ebx
0x180003d11  cmp     dword ptr [rdi], 0
0x180003d14  jl      short loc_180003D57
0x180003d16  cmp     [rdi], ebx
0x180003d18  jge     short loc_180003D57
0x180003d1a  mov     ecx, ebx
0x180003d1c  sub     ecx, [rdi]
0x180003d1e  cmp     ecx, ebx
0x180003d20  jg      short loc_180003D57
0x180003d22  movsxd  rdx, ecx
0x180003d25  lea     eax, [rsi+rsi]
0x180003d28  movsxd  rcx, dword ptr [rdi]
0x180003d2b  add     rdx, rdx; void *
0x180003d2e  movsxd  r9, eax; void *
0x180003d31  mov     r8, rbp; unsigned __int64
0x180003d34  mov     rax, [rdi+8]
0x180003d38  lea     rcx, [rax+rcx*2]; this
0x180003d3c  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x180003d41  add     [rdi], esi
0x180003d43  movsxd  rdx, dword ptr [rdi]
0x180003d46  xor     eax, eax
0x180003d48  mov     rcx, [rdi+8]
0x180003d4c  mov     [rcx+rdx*2], ax
0x180003d50  mov     eax, 1
0x180003d55  jmp     short loc_180003D59
0x180003d57  xor     eax, eax
0x180003d59  add     rsp, 28h
0x180003d5d  pop     rdi
0x180003d5e  pop     rsi
0x180003d5f  pop     rbp
0x180003d60  pop     rbx
0x180003d61  retn
```
