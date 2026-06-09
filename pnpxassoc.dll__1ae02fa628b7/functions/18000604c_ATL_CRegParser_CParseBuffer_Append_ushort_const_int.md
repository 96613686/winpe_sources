# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18000604c`
- end: `0x180006140`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000729c`

## callees

- `0x18000604c`
- `0x180006764`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800060e0`
- `msvcrt!memcpy_s` at `0x1800060e0`
- `ole32!CoTaskMemRealloc` at `0x1800060a3`
- `ole32!CoTaskMemRealloc` at `0x1800060a3`

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
0x18000604c  push    rbx
0x18000604e  push    rbp
0x18000604f  push    rsi
0x180006050  push    rdi
0x180006051  sub     rsp, 28h
0x180006055  mov     rdi, rcx
0x180006058  mov     esi, r8d
0x18000605b  lea     ecx, [r8+1]
0x18000605f  mov     rbp, rdx
0x180006062  add     ecx, [rdi]
0x180006064  cmp     ecx, [rdi]
0x180006066  jle     loc_180006114
0x18000606c  cmp     ecx, r8d
0x18000606f  jle     loc_180006114
0x180006075  mov     ebx, [rdi+4]
0x180006078  cmp     ecx, ebx
0x18000607a  jl      short loc_1800060B5
0x18000607c  cmp     ebx, 3FFFFFFFh
0x180006082  jg      loc_180006114
0x180006088  add     ebx, ebx
0x18000608a  cmp     ecx, ebx
0x18000608c  jge     short loc_18000607C
0x18000608e  mov     eax, ebx
0x180006090  mov     ecx, 0FFFFFFFFh
0x180006095  add     rax, rax
0x180006098  cmp     rax, rcx
0x18000609b  ja      short loc_180006114
0x18000609d  mov     rcx, [rdi+8]; pv
0x1800060a1  mov     edx, eax; cb
0x1800060a3  call    cs:__imp_CoTaskMemRealloc
0x1800060a9  test    rax, rax
0x1800060ac  jz      short loc_180006114
0x1800060ae  mov     [rdi+8], rax
0x1800060b2  mov     [rdi+4], ebx
0x1800060b5  cmp     dword ptr [rdi], 0
0x1800060b8  jl      short loc_180006114
0x1800060ba  cmp     [rdi], ebx
0x1800060bc  jge     short loc_180006114
0x1800060be  mov     ecx, ebx
0x1800060c0  sub     ecx, [rdi]
0x1800060c2  cmp     ecx, ebx
0x1800060c4  jg      short loc_180006114
0x1800060c6  movsxd  rdx, ecx
0x1800060c9  lea     eax, [rsi+rsi]
0x1800060cc  movsxd  rcx, dword ptr [rdi]
0x1800060cf  add     rdx, rdx; DestinationSize
0x1800060d2  movsxd  r9, eax; SourceSize
0x1800060d5  mov     r8, rbp; Source
0x1800060d8  mov     rax, [rdi+8]
0x1800060dc  lea     rcx, [rax+rcx*2]; Destination
0x1800060e0  call    cs:__imp_memcpy_s
0x1800060e6  test    eax, eax
0x1800060e8  jz      short loc_1800060FE
0x1800060ea  cmp     eax, 0Ch
0x1800060ed  jz      short loc_180006135
0x1800060ef  cmp     eax, 16h
0x1800060f2  jz      short loc_18000612A
0x1800060f4  cmp     eax, 22h ; '"'
0x1800060f7  jz      short loc_18000612A
0x1800060f9  cmp     eax, 50h ; 'P'
0x1800060fc  jnz     short loc_18000611F
0x1800060fe  add     [rdi], esi
0x180006100  movsxd  rdx, dword ptr [rdi]
0x180006103  xor     eax, eax
0x180006105  mov     rcx, [rdi+8]
0x180006109  mov     [rcx+rdx*2], ax
0x18000610d  mov     eax, 1
0x180006112  jmp     short loc_180006116
0x180006114  xor     eax, eax
0x180006116  add     rsp, 28h
0x18000611a  pop     rdi
0x18000611b  pop     rsi
0x18000611c  pop     rbp
0x18000611d  pop     rbx
0x18000611e  retn
0x18000611f  mov     ecx, 80004005h; int
0x180006124  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000612a  mov     ecx, 80070057h; int
0x18000612f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006135  mov     ecx, 8007000Eh; int
0x18000613a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
