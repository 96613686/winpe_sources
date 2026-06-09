# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180003dbc`
- end: `0x180003eb0`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004d4c`

## callees

- `0x18000278c`
- `0x180003dbc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003e50`
- `msvcrt!memcpy_s` at `0x180003e50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003e13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003e13`

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
0x180003dbc  push    rbx
0x180003dbe  push    rbp
0x180003dbf  push    rsi
0x180003dc0  push    rdi
0x180003dc1  sub     rsp, 28h
0x180003dc5  mov     rdi, rcx
0x180003dc8  mov     esi, r8d
0x180003dcb  lea     ecx, [r8+1]
0x180003dcf  mov     rbp, rdx
0x180003dd2  add     ecx, [rdi]
0x180003dd4  cmp     ecx, [rdi]
0x180003dd6  jle     loc_180003E84
0x180003ddc  cmp     ecx, r8d
0x180003ddf  jle     loc_180003E84
0x180003de5  mov     ebx, [rdi+4]
0x180003de8  cmp     ecx, ebx
0x180003dea  jl      short loc_180003E25
0x180003dec  cmp     ebx, 3FFFFFFFh
0x180003df2  jg      loc_180003E84
0x180003df8  add     ebx, ebx
0x180003dfa  cmp     ecx, ebx
0x180003dfc  jge     short loc_180003DEC
0x180003dfe  mov     eax, ebx
0x180003e00  mov     ecx, 0FFFFFFFFh
0x180003e05  add     rax, rax
0x180003e08  cmp     rax, rcx
0x180003e0b  ja      short loc_180003E84
0x180003e0d  mov     rcx, [rdi+8]; pv
0x180003e11  mov     edx, eax; cb
0x180003e13  call    cs:__imp_CoTaskMemRealloc
0x180003e19  test    rax, rax
0x180003e1c  jz      short loc_180003E84
0x180003e1e  mov     [rdi+8], rax
0x180003e22  mov     [rdi+4], ebx
0x180003e25  cmp     dword ptr [rdi], 0
0x180003e28  jl      short loc_180003E84
0x180003e2a  cmp     [rdi], ebx
0x180003e2c  jge     short loc_180003E84
0x180003e2e  mov     ecx, ebx
0x180003e30  sub     ecx, [rdi]
0x180003e32  cmp     ecx, ebx
0x180003e34  jg      short loc_180003E84
0x180003e36  movsxd  rdx, ecx
0x180003e39  lea     eax, [rsi+rsi]
0x180003e3c  movsxd  rcx, dword ptr [rdi]
0x180003e3f  add     rdx, rdx; DestinationSize
0x180003e42  movsxd  r9, eax; SourceSize
0x180003e45  mov     r8, rbp; Source
0x180003e48  mov     rax, [rdi+8]
0x180003e4c  lea     rcx, [rax+rcx*2]; Destination
0x180003e50  call    cs:__imp_memcpy_s
0x180003e56  test    eax, eax
0x180003e58  jz      short loc_180003E6E
0x180003e5a  cmp     eax, 0Ch
0x180003e5d  jz      short loc_180003EA5
0x180003e5f  cmp     eax, 16h
0x180003e62  jz      short loc_180003E9A
0x180003e64  cmp     eax, 22h ; '"'
0x180003e67  jz      short loc_180003E9A
0x180003e69  cmp     eax, 50h ; 'P'
0x180003e6c  jnz     short loc_180003E8F
0x180003e6e  add     [rdi], esi
0x180003e70  movsxd  rdx, dword ptr [rdi]
0x180003e73  xor     eax, eax
0x180003e75  mov     rcx, [rdi+8]
0x180003e79  mov     [rcx+rdx*2], ax
0x180003e7d  mov     eax, 1
0x180003e82  jmp     short loc_180003E86
0x180003e84  xor     eax, eax
0x180003e86  add     rsp, 28h
0x180003e8a  pop     rdi
0x180003e8b  pop     rsi
0x180003e8c  pop     rbp
0x180003e8d  pop     rbx
0x180003e8e  retn
0x180003e8f  mov     ecx, 80004005h; int
0x180003e94  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003e9a  mov     ecx, 80070057h; int
0x180003e9f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003ea5  mov     ecx, 8007000Eh; int
0x180003eaa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
