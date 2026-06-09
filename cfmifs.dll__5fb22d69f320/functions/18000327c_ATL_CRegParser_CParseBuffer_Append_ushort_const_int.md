# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18000327c`
- end: `0x180003370`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000420c`

## callees

- `0x18000327c`
- `0x18000397c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003310`
- `msvcrt!memcpy_s` at `0x180003310`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800032d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800032d3`

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
0x18000327c  push    rbx
0x18000327e  push    rbp
0x18000327f  push    rsi
0x180003280  push    rdi
0x180003281  sub     rsp, 28h
0x180003285  mov     rdi, rcx
0x180003288  mov     esi, r8d
0x18000328b  lea     ecx, [r8+1]
0x18000328f  mov     rbp, rdx
0x180003292  add     ecx, [rdi]
0x180003294  cmp     ecx, [rdi]
0x180003296  jle     loc_180003344
0x18000329c  cmp     ecx, r8d
0x18000329f  jle     loc_180003344
0x1800032a5  mov     ebx, [rdi+4]
0x1800032a8  cmp     ecx, ebx
0x1800032aa  jl      short loc_1800032E5
0x1800032ac  cmp     ebx, 3FFFFFFFh
0x1800032b2  jg      loc_180003344
0x1800032b8  add     ebx, ebx
0x1800032ba  cmp     ecx, ebx
0x1800032bc  jge     short loc_1800032AC
0x1800032be  mov     eax, ebx
0x1800032c0  mov     ecx, 0FFFFFFFFh
0x1800032c5  add     rax, rax
0x1800032c8  cmp     rax, rcx
0x1800032cb  ja      short loc_180003344
0x1800032cd  mov     rcx, [rdi+8]; pv
0x1800032d1  mov     edx, eax; cb
0x1800032d3  call    cs:__imp_CoTaskMemRealloc
0x1800032d9  test    rax, rax
0x1800032dc  jz      short loc_180003344
0x1800032de  mov     [rdi+8], rax
0x1800032e2  mov     [rdi+4], ebx
0x1800032e5  cmp     dword ptr [rdi], 0
0x1800032e8  jl      short loc_180003344
0x1800032ea  cmp     [rdi], ebx
0x1800032ec  jge     short loc_180003344
0x1800032ee  mov     ecx, ebx
0x1800032f0  sub     ecx, [rdi]
0x1800032f2  cmp     ecx, ebx
0x1800032f4  jg      short loc_180003344
0x1800032f6  movsxd  rdx, ecx
0x1800032f9  lea     eax, [rsi+rsi]
0x1800032fc  movsxd  rcx, dword ptr [rdi]
0x1800032ff  add     rdx, rdx; DestinationSize
0x180003302  movsxd  r9, eax; SourceSize
0x180003305  mov     r8, rbp; Source
0x180003308  mov     rax, [rdi+8]
0x18000330c  lea     rcx, [rax+rcx*2]; Destination
0x180003310  call    cs:__imp_memcpy_s
0x180003316  test    eax, eax
0x180003318  jz      short loc_18000332E
0x18000331a  cmp     eax, 0Ch
0x18000331d  jz      short loc_180003365
0x18000331f  cmp     eax, 16h
0x180003322  jz      short loc_18000335A
0x180003324  cmp     eax, 22h ; '"'
0x180003327  jz      short loc_18000335A
0x180003329  cmp     eax, 50h ; 'P'
0x18000332c  jnz     short loc_18000334F
0x18000332e  add     [rdi], esi
0x180003330  movsxd  rdx, dword ptr [rdi]
0x180003333  xor     eax, eax
0x180003335  mov     rcx, [rdi+8]
0x180003339  mov     [rcx+rdx*2], ax
0x18000333d  mov     eax, 1
0x180003342  jmp     short loc_180003346
0x180003344  xor     eax, eax
0x180003346  add     rsp, 28h
0x18000334a  pop     rdi
0x18000334b  pop     rsi
0x18000334c  pop     rbp
0x18000334d  pop     rbx
0x18000334e  retn
0x18000334f  mov     ecx, 80004005h; int
0x180003354  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000335a  mov     ecx, 80070057h; int
0x18000335f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003365  mov     ecx, 8007000Eh; int
0x18000336a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
