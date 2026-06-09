# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800041ec`
- end: `0x1800042aa`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `190`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800074d4`

## callees

- `0x1800041ec`
- `0x180004430`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000427c`
- `msvcrt!memcpy_s` at `0x18000427c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000423f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000423f`

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
          v11 = memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v10, a2, 2 * a3);
          ATL::AtlCrtErrorCheck(v11);
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
0x1800041ec  push    rbx
0x1800041ee  push    rbp
0x1800041ef  push    rsi
0x1800041f0  push    rdi
0x1800041f1  sub     rsp, 28h
0x1800041f5  mov     rdi, rcx
0x1800041f8  mov     esi, r8d
0x1800041fb  lea     ecx, [r8+1]
0x1800041ff  mov     rbp, rdx
0x180004202  add     ecx, [rdi]
0x180004204  cmp     ecx, [rdi]
0x180004206  jle     loc_18000429F
0x18000420c  cmp     ecx, r8d
0x18000420f  jle     loc_18000429F
0x180004215  mov     ebx, [rdi+4]
0x180004218  cmp     ecx, ebx
0x18000421a  jl      short loc_180004251
0x18000421c  cmp     ebx, 3FFFFFFFh
0x180004222  jg      short loc_18000429F
0x180004224  add     ebx, ebx
0x180004226  cmp     ecx, ebx
0x180004228  jge     short loc_18000421C
0x18000422a  mov     eax, ebx
0x18000422c  mov     ecx, 0FFFFFFFFh
0x180004231  add     rax, rax
0x180004234  cmp     rax, rcx
0x180004237  ja      short loc_18000429F
0x180004239  mov     rcx, [rdi+8]; pv
0x18000423d  mov     edx, eax; cb
0x18000423f  call    cs:__imp_CoTaskMemRealloc
0x180004245  test    rax, rax
0x180004248  jz      short loc_18000429F
0x18000424a  mov     [rdi+8], rax
0x18000424e  mov     [rdi+4], ebx
0x180004251  cmp     dword ptr [rdi], 0
0x180004254  jl      short loc_18000429F
0x180004256  cmp     [rdi], ebx
0x180004258  jge     short loc_18000429F
0x18000425a  mov     ecx, ebx
0x18000425c  sub     ecx, [rdi]
0x18000425e  cmp     ecx, ebx
0x180004260  jg      short loc_18000429F
0x180004262  movsxd  rdx, ecx
0x180004265  lea     eax, [rsi+rsi]
0x180004268  movsxd  rcx, dword ptr [rdi]
0x18000426b  add     rdx, rdx; DestinationSize
0x18000426e  movsxd  r9, eax; SourceSize
0x180004271  mov     r8, rbp; Source
0x180004274  mov     rax, [rdi+8]
0x180004278  lea     rcx, [rax+rcx*2]; Destination
0x18000427c  call    cs:__imp_memcpy_s
0x180004282  mov     ecx, eax; int
0x180004284  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180004289  add     [rdi], esi
0x18000428b  movsxd  rdx, dword ptr [rdi]
0x18000428e  xor     eax, eax
0x180004290  mov     rcx, [rdi+8]
0x180004294  mov     [rcx+rdx*2], ax
0x180004298  mov     eax, 1
0x18000429d  jmp     short loc_1800042A1
0x18000429f  xor     eax, eax
0x1800042a1  add     rsp, 28h
0x1800042a5  pop     rdi
0x1800042a6  pop     rsi
0x1800042a7  pop     rbp
0x1800042a8  pop     rbx
0x1800042a9  retn
```
