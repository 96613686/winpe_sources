# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180005de0`
- end: `0x180005ea0`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `192`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007df8`

## callees

- `0x180005de0`
- `0x180005fbc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005e72`
- `msvcrt!memcpy_s` at `0x180005e72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180005e35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180005e35`

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
0x180005de0  push    rbx
0x180005de2  push    rbp
0x180005de3  push    rsi
0x180005de4  push    rdi
0x180005de5  sub     rsp, 28h
0x180005de9  mov     rdi, rcx
0x180005dec  mov     esi, r8d
0x180005def  lea     ecx, [r8+1]
0x180005df3  mov     rbp, rdx
0x180005df6  add     ecx, [rdi]
0x180005df8  cmp     ecx, [rdi]
0x180005dfa  jle     loc_180005E95
0x180005e00  cmp     ecx, r8d
0x180005e03  jle     loc_180005E95
0x180005e09  mov     ebx, [rdi+4]
0x180005e0c  cmp     ecx, ebx
0x180005e0e  jl      short loc_180005E47
0x180005e10  cmp     ecx, ebx
0x180005e12  jl      short loc_180005E20
0x180005e14  cmp     ebx, 3FFFFFFFh
0x180005e1a  jg      short loc_180005E95
0x180005e1c  add     ebx, ebx
0x180005e1e  jmp     short loc_180005E10
0x180005e20  mov     eax, ebx
0x180005e22  mov     ecx, 0FFFFFFFFh
0x180005e27  add     rax, rax
0x180005e2a  cmp     rax, rcx
0x180005e2d  ja      short loc_180005E95
0x180005e2f  mov     rcx, [rdi+8]; pv
0x180005e33  mov     edx, eax; cb
0x180005e35  call    cs:__imp_CoTaskMemRealloc
0x180005e3b  test    rax, rax
0x180005e3e  jz      short loc_180005E95
0x180005e40  mov     [rdi+8], rax
0x180005e44  mov     [rdi+4], ebx
0x180005e47  cmp     dword ptr [rdi], 0
0x180005e4a  jl      short loc_180005E95
0x180005e4c  cmp     [rdi], ebx
0x180005e4e  jge     short loc_180005E95
0x180005e50  mov     ecx, ebx
0x180005e52  sub     ecx, [rdi]
0x180005e54  cmp     ecx, ebx
0x180005e56  jg      short loc_180005E95
0x180005e58  movsxd  rdx, ecx
0x180005e5b  lea     eax, [rsi+rsi]
0x180005e5e  movsxd  rcx, dword ptr [rdi]
0x180005e61  add     rdx, rdx; DestinationSize
0x180005e64  movsxd  r9, eax; SourceSize
0x180005e67  mov     r8, rbp; Source
0x180005e6a  mov     rax, [rdi+8]
0x180005e6e  lea     rcx, [rax+rcx*2]; Destination
0x180005e72  call    cs:__imp_memcpy_s
0x180005e78  mov     ecx, eax; int
0x180005e7a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180005e7f  add     [rdi], esi
0x180005e81  movsxd  rdx, dword ptr [rdi]
0x180005e84  xor     eax, eax
0x180005e86  mov     rcx, [rdi+8]
0x180005e8a  mov     [rcx+rdx*2], ax
0x180005e8e  mov     eax, 1
0x180005e93  jmp     short loc_180005E97
0x180005e95  xor     eax, eax
0x180005e97  add     rsp, 28h
0x180005e9b  pop     rdi
0x180005e9c  pop     rsi
0x180005e9d  pop     rbp
0x180005e9e  pop     rbx
0x180005e9f  retn
```
