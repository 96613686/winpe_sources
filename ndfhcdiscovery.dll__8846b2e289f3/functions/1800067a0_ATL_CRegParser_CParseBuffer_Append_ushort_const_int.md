# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800067a0`
- end: `0x1800068a5`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `261`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800086fc`

## callees

- `0x1800067a0`
- `0x1800068ec`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000683e`
- `msvcrt!memcpy_s` at `0x18000683e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800067fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800067fb`

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
0x1800067a0  push    rbx
0x1800067a2  push    rbp
0x1800067a3  push    rsi
0x1800067a4  push    rdi
0x1800067a5  sub     rsp, 28h
0x1800067a9  mov     rdi, rcx
0x1800067ac  mov     esi, r8d
0x1800067af  lea     ecx, [r8+1]
0x1800067b3  mov     rbp, rdx
0x1800067b6  add     ecx, [rdi]
0x1800067b8  cmp     ecx, [rdi]
0x1800067ba  jle     loc_180006878
0x1800067c0  cmp     ecx, r8d
0x1800067c3  jle     loc_180006878
0x1800067c9  mov     ebx, [rdi+4]
0x1800067cc  cmp     ecx, ebx
0x1800067ce  jl      short loc_180006813
0x1800067d0  cmp     ebx, 3FFFFFFFh
0x1800067d6  jg      loc_180006878
0x1800067dc  add     ebx, ebx
0x1800067de  cmp     ecx, ebx
0x1800067e0  jge     short loc_1800067D0
0x1800067e2  mov     eax, ebx
0x1800067e4  mov     ecx, 0FFFFFFFFh
0x1800067e9  add     rax, rax
0x1800067ec  cmp     rax, rcx
0x1800067ef  ja      loc_180006878
0x1800067f5  mov     rcx, [rdi+8]; pv
0x1800067f9  mov     edx, eax; cb
0x1800067fb  call    cs:__imp_CoTaskMemRealloc
0x180006802  nop     dword ptr [rax+rax+00h]
0x180006807  test    rax, rax
0x18000680a  jz      short loc_180006878
0x18000680c  mov     [rdi+8], rax
0x180006810  mov     [rdi+4], ebx
0x180006813  cmp     dword ptr [rdi], 0
0x180006816  jl      short loc_180006878
0x180006818  cmp     [rdi], ebx
0x18000681a  jge     short loc_180006878
0x18000681c  mov     ecx, ebx
0x18000681e  sub     ecx, [rdi]
0x180006820  cmp     ecx, ebx
0x180006822  jg      short loc_180006878
0x180006824  movsxd  rdx, ecx
0x180006827  lea     eax, [rsi+rsi]
0x18000682a  movsxd  rcx, dword ptr [rdi]
0x18000682d  add     rdx, rdx; DestinationSize
0x180006830  movsxd  r9, eax; SourceSize
0x180006833  mov     r8, rbp; Source
0x180006836  mov     rax, [rdi+8]
0x18000683a  lea     rcx, [rax+rcx*2]; Destination
0x18000683e  call    cs:__imp_memcpy_s
0x180006845  nop     dword ptr [rax+rax+00h]
0x18000684a  test    eax, eax
0x18000684c  jz      short loc_180006862
0x18000684e  cmp     eax, 0Ch
0x180006851  jz      short loc_18000689A
0x180006853  cmp     eax, 16h
0x180006856  jz      short loc_18000688F
0x180006858  cmp     eax, 22h ; '"'
0x18000685b  jz      short loc_18000688F
0x18000685d  cmp     eax, 50h ; 'P'
0x180006860  jnz     short loc_180006884
0x180006862  add     [rdi], esi
0x180006864  movsxd  rdx, dword ptr [rdi]
0x180006867  xor     eax, eax
0x180006869  mov     rcx, [rdi+8]
0x18000686d  mov     [rcx+rdx*2], ax
0x180006871  mov     eax, 1
0x180006876  jmp     short loc_18000687A
0x180006878  xor     eax, eax
0x18000687a  add     rsp, 28h
0x18000687e  pop     rdi
0x18000687f  pop     rsi
0x180006880  pop     rbp
0x180006881  pop     rbx
0x180006882  retn
0x180006884  mov     ecx, 80004005h; int
0x180006889  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000688f  mov     ecx, 80070057h; int
0x180006894  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000689a  mov     ecx, 8007000Eh; int
0x18000689f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
