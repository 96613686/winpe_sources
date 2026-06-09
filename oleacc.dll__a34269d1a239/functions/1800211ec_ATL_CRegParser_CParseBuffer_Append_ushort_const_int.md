# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800211ec`
- end: `0x1800212ab`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `191`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800223b8`

## callees

- `0x1800211ec`
- `0x18002132c`
- `0x180023810`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180021241`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180021241`

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
0x1800211ec  push    rbx
0x1800211ee  push    rbp
0x1800211ef  push    rsi
0x1800211f0  push    rdi
0x1800211f1  sub     rsp, 28h
0x1800211f5  mov     rdi, rcx
0x1800211f8  mov     esi, r8d
0x1800211fb  lea     ecx, [r8+1]
0x1800211ff  mov     rbp, rdx
0x180021202  add     ecx, [rdi]
0x180021204  cmp     ecx, [rdi]
0x180021206  jle     loc_1800212A0
0x18002120c  cmp     ecx, r8d
0x18002120f  jle     loc_1800212A0
0x180021215  mov     ebx, [rdi+4]
0x180021218  cmp     ecx, ebx
0x18002121a  jl      short loc_180021253
0x18002121c  cmp     ecx, ebx
0x18002121e  jl      short loc_18002122C
0x180021220  cmp     ebx, 3FFFFFFFh
0x180021226  jg      short loc_1800212A0
0x180021228  add     ebx, ebx
0x18002122a  jmp     short loc_18002121C
0x18002122c  mov     eax, ebx
0x18002122e  mov     ecx, 0FFFFFFFFh
0x180021233  add     rax, rax
0x180021236  cmp     rax, rcx
0x180021239  ja      short loc_1800212A0
0x18002123b  mov     rcx, [rdi+8]; pv
0x18002123f  mov     edx, eax; cb
0x180021241  call    cs:__imp_CoTaskMemRealloc
0x180021247  test    rax, rax
0x18002124a  jz      short loc_1800212A0
0x18002124c  mov     [rdi+8], rax
0x180021250  mov     [rdi+4], ebx
0x180021253  cmp     dword ptr [rdi], 0
0x180021256  jl      short loc_1800212A0
0x180021258  cmp     [rdi], ebx
0x18002125a  jge     short loc_1800212A0
0x18002125c  mov     ecx, ebx
0x18002125e  sub     ecx, [rdi]
0x180021260  cmp     ecx, ebx
0x180021262  jg      short loc_1800212A0
0x180021264  movsxd  rdx, ecx
0x180021267  lea     eax, [rsi+rsi]
0x18002126a  movsxd  rcx, dword ptr [rdi]
0x18002126d  add     rdx, rdx; DestinationSize
0x180021270  movsxd  r9, eax; SourceSize
0x180021273  mov     r8, rbp; Source
0x180021276  mov     rax, [rdi+8]
0x18002127a  lea     rcx, [rax+rcx*2]; Destination
0x18002127e  call    memcpy_s
0x180021283  mov     ecx, eax; int
0x180021285  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002128a  add     [rdi], esi
0x18002128c  movsxd  rdx, dword ptr [rdi]
0x18002128f  xor     eax, eax
0x180021291  mov     rcx, [rdi+8]
0x180021295  mov     [rcx+rdx*2], ax
0x180021299  mov     eax, 1
0x18002129e  jmp     short loc_1800212A2
0x1800212a0  xor     eax, eax
0x1800212a2  add     rsp, 28h
0x1800212a6  pop     rdi
0x1800212a7  pop     rsi
0x1800212a8  pop     rbp
0x1800212a9  pop     rbx
0x1800212aa  retn
```
