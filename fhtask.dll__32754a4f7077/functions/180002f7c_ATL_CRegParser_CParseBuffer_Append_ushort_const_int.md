# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180002f7c`
- end: `0x180003070`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003cec`

## callees

- `0x180002f7c`
- `0x1800030b4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003010`
- `msvcrt!memcpy_s` at `0x180003010`
- `ole32!CoTaskMemRealloc` at `0x180002fd3`
- `ole32!CoTaskMemRealloc` at `0x180002fd3`

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
0x180002f7c  push    rbx
0x180002f7e  push    rbp
0x180002f7f  push    rsi
0x180002f80  push    rdi
0x180002f81  sub     rsp, 28h
0x180002f85  mov     rdi, rcx
0x180002f88  mov     esi, r8d
0x180002f8b  lea     ecx, [r8+1]
0x180002f8f  mov     rbp, rdx
0x180002f92  add     ecx, [rdi]
0x180002f94  cmp     ecx, [rdi]
0x180002f96  jle     loc_180003044
0x180002f9c  cmp     ecx, r8d
0x180002f9f  jle     loc_180003044
0x180002fa5  mov     ebx, [rdi+4]
0x180002fa8  cmp     ecx, ebx
0x180002faa  jl      short loc_180002FE5
0x180002fac  cmp     ebx, 3FFFFFFFh
0x180002fb2  jg      loc_180003044
0x180002fb8  add     ebx, ebx
0x180002fba  cmp     ecx, ebx
0x180002fbc  jge     short loc_180002FAC
0x180002fbe  mov     eax, ebx
0x180002fc0  mov     ecx, 0FFFFFFFFh
0x180002fc5  add     rax, rax
0x180002fc8  cmp     rax, rcx
0x180002fcb  ja      short loc_180003044
0x180002fcd  mov     rcx, [rdi+8]; pv
0x180002fd1  mov     edx, eax; cb
0x180002fd3  call    cs:__imp_CoTaskMemRealloc
0x180002fd9  test    rax, rax
0x180002fdc  jz      short loc_180003044
0x180002fde  mov     [rdi+8], rax
0x180002fe2  mov     [rdi+4], ebx
0x180002fe5  cmp     dword ptr [rdi], 0
0x180002fe8  jl      short loc_180003044
0x180002fea  cmp     [rdi], ebx
0x180002fec  jge     short loc_180003044
0x180002fee  mov     ecx, ebx
0x180002ff0  sub     ecx, [rdi]
0x180002ff2  cmp     ecx, ebx
0x180002ff4  jg      short loc_180003044
0x180002ff6  movsxd  rdx, ecx
0x180002ff9  lea     eax, [rsi+rsi]
0x180002ffc  movsxd  rcx, dword ptr [rdi]
0x180002fff  add     rdx, rdx; DestinationSize
0x180003002  movsxd  r9, eax; SourceSize
0x180003005  mov     r8, rbp; Source
0x180003008  mov     rax, [rdi+8]
0x18000300c  lea     rcx, [rax+rcx*2]; Destination
0x180003010  call    cs:__imp_memcpy_s
0x180003016  test    eax, eax
0x180003018  jz      short loc_18000302E
0x18000301a  cmp     eax, 0Ch
0x18000301d  jz      short loc_180003065
0x18000301f  cmp     eax, 16h
0x180003022  jz      short loc_18000305A
0x180003024  cmp     eax, 22h ; '"'
0x180003027  jz      short loc_18000305A
0x180003029  cmp     eax, 50h ; 'P'
0x18000302c  jnz     short loc_18000304F
0x18000302e  add     [rdi], esi
0x180003030  movsxd  rdx, dword ptr [rdi]
0x180003033  xor     eax, eax
0x180003035  mov     rcx, [rdi+8]
0x180003039  mov     [rcx+rdx*2], ax
0x18000303d  mov     eax, 1
0x180003042  jmp     short loc_180003046
0x180003044  xor     eax, eax
0x180003046  add     rsp, 28h
0x18000304a  pop     rdi
0x18000304b  pop     rsi
0x18000304c  pop     rbp
0x18000304d  pop     rbx
0x18000304e  retn
0x18000304f  mov     ecx, 80004005h; int
0x180003054  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000305a  mov     ecx, 80070057h; int
0x18000305f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003065  mov     ecx, 8007000Eh; int
0x18000306a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
