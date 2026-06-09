# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180013dcc`
- end: `0x180013e8a`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `190`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015db4`

## callees

- `0x180013dcc`
- `0x180014010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180013e5c`
- `msvcrt!memcpy_s` at `0x180013e5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180013e1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180013e1f`

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
0x180013dcc  push    rbx
0x180013dce  push    rbp
0x180013dcf  push    rsi
0x180013dd0  push    rdi
0x180013dd1  sub     rsp, 28h
0x180013dd5  mov     rdi, rcx
0x180013dd8  mov     esi, r8d
0x180013ddb  lea     ecx, [r8+1]
0x180013ddf  mov     rbp, rdx
0x180013de2  add     ecx, [rdi]
0x180013de4  cmp     ecx, [rdi]
0x180013de6  jle     loc_180013E7F
0x180013dec  cmp     ecx, r8d
0x180013def  jle     loc_180013E7F
0x180013df5  mov     ebx, [rdi+4]
0x180013df8  cmp     ecx, ebx
0x180013dfa  jl      short loc_180013E31
0x180013dfc  cmp     ebx, 3FFFFFFFh
0x180013e02  jg      short loc_180013E7F
0x180013e04  add     ebx, ebx
0x180013e06  cmp     ecx, ebx
0x180013e08  jge     short loc_180013DFC
0x180013e0a  mov     eax, ebx
0x180013e0c  mov     ecx, 0FFFFFFFFh
0x180013e11  add     rax, rax
0x180013e14  cmp     rax, rcx
0x180013e17  ja      short loc_180013E7F
0x180013e19  mov     rcx, [rdi+8]; pv
0x180013e1d  mov     edx, eax; cb
0x180013e1f  call    cs:__imp_CoTaskMemRealloc
0x180013e25  test    rax, rax
0x180013e28  jz      short loc_180013E7F
0x180013e2a  mov     [rdi+8], rax
0x180013e2e  mov     [rdi+4], ebx
0x180013e31  cmp     dword ptr [rdi], 0
0x180013e34  jl      short loc_180013E7F
0x180013e36  cmp     [rdi], ebx
0x180013e38  jge     short loc_180013E7F
0x180013e3a  mov     ecx, ebx
0x180013e3c  sub     ecx, [rdi]
0x180013e3e  cmp     ecx, ebx
0x180013e40  jg      short loc_180013E7F
0x180013e42  movsxd  rdx, ecx
0x180013e45  lea     eax, [rsi+rsi]
0x180013e48  movsxd  rcx, dword ptr [rdi]
0x180013e4b  add     rdx, rdx; DestinationSize
0x180013e4e  movsxd  r9, eax; SourceSize
0x180013e51  mov     r8, rbp; Source
0x180013e54  mov     rax, [rdi+8]
0x180013e58  lea     rcx, [rax+rcx*2]; Destination
0x180013e5c  call    cs:__imp_memcpy_s
0x180013e62  mov     ecx, eax; int
0x180013e64  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180013e69  add     [rdi], esi
0x180013e6b  movsxd  rdx, dword ptr [rdi]
0x180013e6e  xor     eax, eax
0x180013e70  mov     rcx, [rdi+8]
0x180013e74  mov     [rcx+rdx*2], ax
0x180013e78  mov     eax, 1
0x180013e7d  jmp     short loc_180013E81
0x180013e7f  xor     eax, eax
0x180013e81  add     rsp, 28h
0x180013e85  pop     rdi
0x180013e86  pop     rsi
0x180013e87  pop     rbp
0x180013e88  pop     rbx
0x180013e89  retn
```
