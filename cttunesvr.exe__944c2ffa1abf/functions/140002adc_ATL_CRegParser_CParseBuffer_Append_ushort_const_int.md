# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x140002adc`
- end: `0x140002bd0`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140003abc`

## callees

- `0x140002adc`
- `0x140002c14`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140002b70`
- `msvcrt!memcpy_s` at `0x140002b70`
- `ole32!CoTaskMemRealloc` at `0x140002b33`
- `ole32!CoTaskMemRealloc` at `0x140002b33`

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
0x140002adc  push    rbx
0x140002ade  push    rbp
0x140002adf  push    rsi
0x140002ae0  push    rdi
0x140002ae1  sub     rsp, 28h
0x140002ae5  mov     rdi, rcx
0x140002ae8  mov     esi, r8d
0x140002aeb  lea     ecx, [r8+1]
0x140002aef  mov     rbp, rdx
0x140002af2  add     ecx, [rdi]
0x140002af4  cmp     ecx, [rdi]
0x140002af6  jle     loc_140002BA4
0x140002afc  cmp     ecx, r8d
0x140002aff  jle     loc_140002BA4
0x140002b05  mov     ebx, [rdi+4]
0x140002b08  cmp     ecx, ebx
0x140002b0a  jl      short loc_140002B45
0x140002b0c  cmp     ebx, 3FFFFFFFh
0x140002b12  jg      loc_140002BA4
0x140002b18  add     ebx, ebx
0x140002b1a  cmp     ecx, ebx
0x140002b1c  jge     short loc_140002B0C
0x140002b1e  mov     eax, ebx
0x140002b20  mov     ecx, 0FFFFFFFFh
0x140002b25  add     rax, rax
0x140002b28  cmp     rax, rcx
0x140002b2b  ja      short loc_140002BA4
0x140002b2d  mov     rcx, [rdi+8]; pv
0x140002b31  mov     edx, eax; cb
0x140002b33  call    cs:__imp_CoTaskMemRealloc
0x140002b39  test    rax, rax
0x140002b3c  jz      short loc_140002BA4
0x140002b3e  mov     [rdi+8], rax
0x140002b42  mov     [rdi+4], ebx
0x140002b45  cmp     dword ptr [rdi], 0
0x140002b48  jl      short loc_140002BA4
0x140002b4a  cmp     [rdi], ebx
0x140002b4c  jge     short loc_140002BA4
0x140002b4e  mov     ecx, ebx
0x140002b50  sub     ecx, [rdi]
0x140002b52  cmp     ecx, ebx
0x140002b54  jg      short loc_140002BA4
0x140002b56  movsxd  rdx, ecx
0x140002b59  lea     eax, [rsi+rsi]
0x140002b5c  movsxd  rcx, dword ptr [rdi]
0x140002b5f  add     rdx, rdx; DestinationSize
0x140002b62  movsxd  r9, eax; SourceSize
0x140002b65  mov     r8, rbp; Source
0x140002b68  mov     rax, [rdi+8]
0x140002b6c  lea     rcx, [rax+rcx*2]; Destination
0x140002b70  call    cs:__imp_memcpy_s
0x140002b76  test    eax, eax
0x140002b78  jz      short loc_140002B8E
0x140002b7a  cmp     eax, 0Ch
0x140002b7d  jz      short loc_140002BC5
0x140002b7f  cmp     eax, 16h
0x140002b82  jz      short loc_140002BBA
0x140002b84  cmp     eax, 22h ; '"'
0x140002b87  jz      short loc_140002BBA
0x140002b89  cmp     eax, 50h ; 'P'
0x140002b8c  jnz     short loc_140002BAF
0x140002b8e  add     [rdi], esi
0x140002b90  movsxd  rdx, dword ptr [rdi]
0x140002b93  xor     eax, eax
0x140002b95  mov     rcx, [rdi+8]
0x140002b99  mov     [rcx+rdx*2], ax
0x140002b9d  mov     eax, 1
0x140002ba2  jmp     short loc_140002BA6
0x140002ba4  xor     eax, eax
0x140002ba6  add     rsp, 28h
0x140002baa  pop     rdi
0x140002bab  pop     rsi
0x140002bac  pop     rbp
0x140002bad  pop     rbx
0x140002bae  retn
0x140002baf  mov     ecx, 80004005h; int
0x140002bb4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140002bba  mov     ecx, 80070057h; int
0x140002bbf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140002bc5  mov     ecx, 8007000Eh; int
0x140002bca  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
