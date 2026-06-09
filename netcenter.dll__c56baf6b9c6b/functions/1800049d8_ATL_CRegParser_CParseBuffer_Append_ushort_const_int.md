# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800049d8`
- end: `0x180004a97`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `191`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800051e8`

## callees

- `0x1800049d8`
- `0x180004aa0`
- `0x180006cb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004a2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004a2d`

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
    if ( v6 >= v7 )
    {
      while ( v6 >= v7 )
      {
        if ( v7 > 0x3FFFFFFF )
          return 0;
        v7 *= 2;
      }
      v8 = 2LL * (unsigned int)v7;
      if ( v8 > 0xFFFFFFFF )
        return 0;
      v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
      if ( !v9 )
        return 0;
      *((_QWORD *)this + 1) = v9;
      *((_DWORD *)this + 1) = v7;
    }
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
  return 0;
}

```

## disassembly

```asm
0x1800049d8  push    rbx
0x1800049da  push    rbp
0x1800049db  push    rsi
0x1800049dc  push    rdi
0x1800049dd  sub     rsp, 28h
0x1800049e1  mov     rdi, rcx
0x1800049e4  mov     esi, r8d
0x1800049e7  lea     ecx, [r8+1]
0x1800049eb  mov     rbp, rdx
0x1800049ee  add     ecx, [rdi]
0x1800049f0  cmp     ecx, [rdi]
0x1800049f2  jle     loc_180004A8C
0x1800049f8  cmp     ecx, r8d
0x1800049fb  jle     loc_180004A8C
0x180004a01  mov     ebx, [rdi+4]
0x180004a04  cmp     ecx, ebx
0x180004a06  jl      short loc_180004A3F
0x180004a08  cmp     ecx, ebx
0x180004a0a  jl      short loc_180004A18
0x180004a0c  cmp     ebx, 3FFFFFFFh
0x180004a12  jg      short loc_180004A8C
0x180004a14  add     ebx, ebx
0x180004a16  jmp     short loc_180004A08
0x180004a18  mov     eax, ebx
0x180004a1a  mov     ecx, 0FFFFFFFFh
0x180004a1f  add     rax, rax
0x180004a22  cmp     rax, rcx
0x180004a25  ja      short loc_180004A8C
0x180004a27  mov     rcx, [rdi+8]; pv
0x180004a2b  mov     edx, eax; cb
0x180004a2d  call    cs:__imp_CoTaskMemRealloc
0x180004a33  test    rax, rax
0x180004a36  jz      short loc_180004A8C
0x180004a38  mov     [rdi+8], rax
0x180004a3c  mov     [rdi+4], ebx
0x180004a3f  cmp     dword ptr [rdi], 0
0x180004a42  jl      short loc_180004A8C
0x180004a44  cmp     [rdi], ebx
0x180004a46  jge     short loc_180004A8C
0x180004a48  mov     ecx, ebx
0x180004a4a  sub     ecx, [rdi]
0x180004a4c  cmp     ecx, ebx
0x180004a4e  jg      short loc_180004A8C
0x180004a50  movsxd  rdx, ecx
0x180004a53  lea     eax, [rsi+rsi]
0x180004a56  movsxd  rcx, dword ptr [rdi]
0x180004a59  add     rdx, rdx; DestinationSize
0x180004a5c  movsxd  r9, eax; SourceSize
0x180004a5f  mov     r8, rbp; Source
0x180004a62  mov     rax, [rdi+8]
0x180004a66  lea     rcx, [rax+rcx*2]; Destination
0x180004a6a  call    memcpy_s
0x180004a6f  mov     ecx, eax; int
0x180004a71  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180004a76  add     [rdi], esi
0x180004a78  movsxd  rdx, dword ptr [rdi]
0x180004a7b  xor     eax, eax
0x180004a7d  mov     rcx, [rdi+8]
0x180004a81  mov     [rcx+rdx*2], ax
0x180004a85  mov     eax, 1
0x180004a8a  jmp     short loc_180004A8E
0x180004a8c  xor     eax, eax
0x180004a8e  add     rsp, 28h
0x180004a92  pop     rdi
0x180004a93  pop     rsi
0x180004a94  pop     rbp
0x180004a95  pop     rbx
0x180004a96  retn
```
