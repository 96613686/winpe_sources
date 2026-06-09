# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800036bc`
- end: `0x1800037b0`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800044a4`

## callees

- `0x1800036bc`
- `0x180004048`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003750`
- `msvcrt!memcpy_s` at `0x180003750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003713`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003713`

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
  if ( v6 <= *(_DWORD *)this || v6 <= a3 )
    return 0;
  v7 = *((_DWORD *)this + 1);
  if ( v6 >= v7 )
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
    return 0;
  }
LABEL_9:
  if ( *(int *)this < 0 )
    return 0;
  if ( *(_DWORD *)this >= v7 )
    return 0;
  v10 = v7 - *(_DWORD *)this;
  if ( v10 > v7 )
    return 0;
  v11 = memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v10, a2, 2 * a3);
  if ( v11 )
  {
    if ( v11 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v11 == 22 || v11 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v11 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  *(_DWORD *)this += a3;
  *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
  return 1;
}

```

## disassembly

```asm
0x1800036bc  push    rbx
0x1800036be  push    rbp
0x1800036bf  push    rsi
0x1800036c0  push    rdi
0x1800036c1  sub     rsp, 28h
0x1800036c5  mov     rdi, rcx
0x1800036c8  mov     esi, r8d
0x1800036cb  lea     ecx, [r8+1]
0x1800036cf  mov     rbp, rdx
0x1800036d2  add     ecx, [rdi]
0x1800036d4  cmp     ecx, [rdi]
0x1800036d6  jle     loc_180003784
0x1800036dc  cmp     ecx, r8d
0x1800036df  jle     loc_180003784
0x1800036e5  mov     ebx, [rdi+4]
0x1800036e8  cmp     ecx, ebx
0x1800036ea  jl      short loc_180003725
0x1800036ec  cmp     ebx, 3FFFFFFFh
0x1800036f2  jg      loc_180003784
0x1800036f8  add     ebx, ebx
0x1800036fa  cmp     ecx, ebx
0x1800036fc  jge     short loc_1800036EC
0x1800036fe  mov     eax, ebx
0x180003700  mov     ecx, 0FFFFFFFFh
0x180003705  add     rax, rax
0x180003708  cmp     rax, rcx
0x18000370b  ja      short loc_180003784
0x18000370d  mov     rcx, [rdi+8]; pv
0x180003711  mov     edx, eax; cb
0x180003713  call    cs:__imp_CoTaskMemRealloc
0x180003719  test    rax, rax
0x18000371c  jz      short loc_180003784
0x18000371e  mov     [rdi+8], rax
0x180003722  mov     [rdi+4], ebx
0x180003725  cmp     dword ptr [rdi], 0
0x180003728  jl      short loc_180003784
0x18000372a  cmp     [rdi], ebx
0x18000372c  jge     short loc_180003784
0x18000372e  mov     ecx, ebx
0x180003730  sub     ecx, [rdi]
0x180003732  cmp     ecx, ebx
0x180003734  jg      short loc_180003784
0x180003736  movsxd  rdx, ecx
0x180003739  lea     eax, [rsi+rsi]
0x18000373c  movsxd  rcx, dword ptr [rdi]
0x18000373f  add     rdx, rdx; DestinationSize
0x180003742  movsxd  r9, eax; SourceSize
0x180003745  mov     r8, rbp; Source
0x180003748  mov     rax, [rdi+8]
0x18000374c  lea     rcx, [rax+rcx*2]; Destination
0x180003750  call    cs:__imp_memcpy_s
0x180003756  test    eax, eax
0x180003758  jz      short loc_18000376E
0x18000375a  cmp     eax, 0Ch
0x18000375d  jz      short loc_1800037A5
0x18000375f  cmp     eax, 16h
0x180003762  jz      short loc_18000379A
0x180003764  cmp     eax, 22h ; '"'
0x180003767  jz      short loc_18000379A
0x180003769  cmp     eax, 50h ; 'P'
0x18000376c  jnz     short loc_18000378F
0x18000376e  add     [rdi], esi
0x180003770  movsxd  rdx, dword ptr [rdi]
0x180003773  xor     eax, eax
0x180003775  mov     rcx, [rdi+8]
0x180003779  mov     [rcx+rdx*2], ax
0x18000377d  mov     eax, 1
0x180003782  jmp     short loc_180003786
0x180003784  xor     eax, eax
0x180003786  add     rsp, 28h
0x18000378a  pop     rdi
0x18000378b  pop     rsi
0x18000378c  pop     rbp
0x18000378d  pop     rbx
0x18000378e  retn
0x18000378f  mov     ecx, 80004005h; int
0x180003794  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000379a  mov     ecx, 80070057h; int
0x18000379f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800037a5  mov     ecx, 8007000Eh; int
0x1800037aa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
