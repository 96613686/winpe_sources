# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180047ad8`
- end: `0x180047b91`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `185`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180048ad4`

## callees

- `0x180047ad8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180047b6a`
- `msvcrt!memcpy_s` at `0x180047b6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180047b2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180047b2d`

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
        memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v10, a2, 2 * a3);
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
0x180047ad8  push    rbx
0x180047ada  push    rbp
0x180047adb  push    rsi
0x180047adc  push    rdi
0x180047add  sub     rsp, 28h
0x180047ae1  mov     rdi, rcx
0x180047ae4  mov     esi, r8d
0x180047ae7  lea     ecx, [r8+1]
0x180047aeb  mov     rbp, rdx
0x180047aee  add     ecx, [rdi]
0x180047af0  cmp     ecx, [rdi]
0x180047af2  jle     loc_180047B86
0x180047af8  cmp     ecx, r8d
0x180047afb  jle     loc_180047B86
0x180047b01  mov     ebx, [rdi+4]
0x180047b04  cmp     ecx, ebx
0x180047b06  jl      short loc_180047B3F
0x180047b08  cmp     ecx, ebx
0x180047b0a  jl      short loc_180047B18
0x180047b0c  cmp     ebx, 3FFFFFFFh
0x180047b12  jg      short loc_180047B86
0x180047b14  add     ebx, ebx
0x180047b16  jmp     short loc_180047B08
0x180047b18  mov     eax, ebx
0x180047b1a  mov     ecx, 0FFFFFFFFh
0x180047b1f  add     rax, rax
0x180047b22  cmp     rax, rcx
0x180047b25  ja      short loc_180047B86
0x180047b27  mov     rcx, [rdi+8]; pv
0x180047b2b  mov     edx, eax; cb
0x180047b2d  call    cs:__imp_CoTaskMemRealloc
0x180047b33  test    rax, rax
0x180047b36  jz      short loc_180047B86
0x180047b38  mov     [rdi+8], rax
0x180047b3c  mov     [rdi+4], ebx
0x180047b3f  cmp     dword ptr [rdi], 0
0x180047b42  jl      short loc_180047B86
0x180047b44  cmp     [rdi], ebx
0x180047b46  jge     short loc_180047B86
0x180047b48  mov     ecx, ebx
0x180047b4a  sub     ecx, [rdi]
0x180047b4c  cmp     ecx, ebx
0x180047b4e  jg      short loc_180047B86
0x180047b50  movsxd  rdx, ecx
0x180047b53  lea     eax, [rsi+rsi]
0x180047b56  movsxd  rcx, dword ptr [rdi]
0x180047b59  add     rdx, rdx; DestinationSize
0x180047b5c  movsxd  r9, eax; SourceSize
0x180047b5f  mov     r8, rbp; Source
0x180047b62  mov     rax, [rdi+8]
0x180047b66  lea     rcx, [rax+rcx*2]; Destination
0x180047b6a  call    cs:__imp_memcpy_s
0x180047b70  add     [rdi], esi
0x180047b72  movsxd  rdx, dword ptr [rdi]
0x180047b75  xor     eax, eax
0x180047b77  mov     rcx, [rdi+8]
0x180047b7b  mov     [rcx+rdx*2], ax
0x180047b7f  mov     eax, 1
0x180047b84  jmp     short loc_180047B88
0x180047b86  xor     eax, eax
0x180047b88  add     rsp, 28h
0x180047b8c  pop     rdi
0x180047b8d  pop     rsi
0x180047b8e  pop     rbp
0x180047b8f  pop     rbx
0x180047b90  retn
```
