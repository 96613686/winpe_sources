# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x140006800`
- end: `0x1400068fa`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `250`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140007110`

## callees

- `0x1400059dc`
- `0x140006800`
- `0x140006940`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x140006857`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x140006857`

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
0x140006800  push    rbx
0x140006802  push    rbp
0x140006803  push    rsi
0x140006804  push    rdi
0x140006805  sub     rsp, 28h
0x140006809  mov     rdi, rcx
0x14000680c  mov     esi, r8d
0x14000680f  lea     ecx, [r8+1]
0x140006813  mov     rbp, rdx
0x140006816  add     ecx, [rdi]
0x140006818  cmp     ecx, [rdi]
0x14000681a  jle     loc_1400068CD
0x140006820  cmp     ecx, r8d
0x140006823  jle     loc_1400068CD
0x140006829  mov     ebx, [rdi+4]
0x14000682c  cmp     ecx, ebx
0x14000682e  jl      short loc_14000686F
0x140006830  cmp     ebx, 3FFFFFFFh
0x140006836  jg      loc_1400068CD
0x14000683c  add     ebx, ebx
0x14000683e  cmp     ecx, ebx
0x140006840  jge     short loc_140006830
0x140006842  mov     eax, ebx
0x140006844  mov     ecx, 0FFFFFFFFh
0x140006849  add     rax, rax
0x14000684c  cmp     rax, rcx
0x14000684f  ja      short loc_1400068CD
0x140006851  mov     rcx, [rdi+8]; pv
0x140006855  mov     edx, eax; cb
0x140006857  call    cs:__imp_CoTaskMemRealloc
0x14000685e  nop     dword ptr [rax+rax+00h]
0x140006863  test    rax, rax
0x140006866  jz      short loc_1400068CD
0x140006868  mov     [rdi+8], rax
0x14000686c  mov     [rdi+4], ebx
0x14000686f  cmp     dword ptr [rdi], 0
0x140006872  jl      short loc_1400068CD
0x140006874  cmp     [rdi], ebx
0x140006876  jge     short loc_1400068CD
0x140006878  mov     ecx, ebx
0x14000687a  sub     ecx, [rdi]
0x14000687c  cmp     ecx, ebx
0x14000687e  jg      short loc_1400068CD
0x140006880  movsxd  rdx, ecx
0x140006883  lea     eax, [rsi+rsi]
0x140006886  movsxd  rcx, dword ptr [rdi]
0x140006889  add     rdx, rdx; DestinationSize
0x14000688c  movsxd  r9, eax; SourceSize
0x14000688f  mov     r8, rbp; Source
0x140006892  mov     rax, [rdi+8]
0x140006896  lea     rcx, [rax+rcx*2]; Destination
0x14000689a  call    memcpy_s
0x14000689f  test    eax, eax
0x1400068a1  jz      short loc_1400068B7
0x1400068a3  cmp     eax, 0Ch
0x1400068a6  jz      short loc_1400068EF
0x1400068a8  cmp     eax, 16h
0x1400068ab  jz      short loc_1400068E4
0x1400068ad  cmp     eax, 22h ; '"'
0x1400068b0  jz      short loc_1400068E4
0x1400068b2  cmp     eax, 50h ; 'P'
0x1400068b5  jnz     short loc_1400068D9
0x1400068b7  add     [rdi], esi
0x1400068b9  movsxd  rdx, dword ptr [rdi]
0x1400068bc  xor     eax, eax
0x1400068be  mov     rcx, [rdi+8]
0x1400068c2  mov     [rcx+rdx*2], ax
0x1400068c6  mov     eax, 1
0x1400068cb  jmp     short loc_1400068CF
0x1400068cd  xor     eax, eax
0x1400068cf  add     rsp, 28h
0x1400068d3  pop     rdi
0x1400068d4  pop     rsi
0x1400068d5  pop     rbp
0x1400068d6  pop     rbx
0x1400068d7  retn
0x1400068d9  mov     ecx, 80004005h; int
0x1400068de  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400068e4  mov     ecx, 80070057h; int
0x1400068e9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400068ef  mov     ecx, 8007000Eh; int
0x1400068f4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
