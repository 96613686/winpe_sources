# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18000ee7c`
- end: `0x18000ef3a`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `190`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010870`

## callees

- `0x18000ee7c`
- `0x18000f0c0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ef0c`
- `msvcrt!memcpy_s` at `0x18000ef0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000eecf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000eecf`

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
0x18000ee7c  push    rbx
0x18000ee7e  push    rbp
0x18000ee7f  push    rsi
0x18000ee80  push    rdi
0x18000ee81  sub     rsp, 28h
0x18000ee85  mov     rdi, rcx
0x18000ee88  mov     esi, r8d
0x18000ee8b  lea     ecx, [r8+1]
0x18000ee8f  mov     rbp, rdx
0x18000ee92  add     ecx, [rdi]
0x18000ee94  cmp     ecx, [rdi]
0x18000ee96  jle     loc_18000EF2F
0x18000ee9c  cmp     ecx, r8d
0x18000ee9f  jle     loc_18000EF2F
0x18000eea5  mov     ebx, [rdi+4]
0x18000eea8  cmp     ecx, ebx
0x18000eeaa  jl      short loc_18000EEE1
0x18000eeac  cmp     ebx, 3FFFFFFFh
0x18000eeb2  jg      short loc_18000EF2F
0x18000eeb4  add     ebx, ebx
0x18000eeb6  cmp     ecx, ebx
0x18000eeb8  jge     short loc_18000EEAC
0x18000eeba  mov     eax, ebx
0x18000eebc  mov     ecx, 0FFFFFFFFh
0x18000eec1  add     rax, rax
0x18000eec4  cmp     rax, rcx
0x18000eec7  ja      short loc_18000EF2F
0x18000eec9  mov     rcx, [rdi+8]; pv
0x18000eecd  mov     edx, eax; cb
0x18000eecf  call    cs:__imp_CoTaskMemRealloc
0x18000eed5  test    rax, rax
0x18000eed8  jz      short loc_18000EF2F
0x18000eeda  mov     [rdi+8], rax
0x18000eede  mov     [rdi+4], ebx
0x18000eee1  cmp     dword ptr [rdi], 0
0x18000eee4  jl      short loc_18000EF2F
0x18000eee6  cmp     [rdi], ebx
0x18000eee8  jge     short loc_18000EF2F
0x18000eeea  mov     ecx, ebx
0x18000eeec  sub     ecx, [rdi]
0x18000eeee  cmp     ecx, ebx
0x18000eef0  jg      short loc_18000EF2F
0x18000eef2  movsxd  rdx, ecx
0x18000eef5  lea     eax, [rsi+rsi]
0x18000eef8  movsxd  rcx, dword ptr [rdi]
0x18000eefb  add     rdx, rdx; DestinationSize
0x18000eefe  movsxd  r9, eax; SourceSize
0x18000ef01  mov     r8, rbp; Source
0x18000ef04  mov     rax, [rdi+8]
0x18000ef08  lea     rcx, [rax+rcx*2]; Destination
0x18000ef0c  call    cs:__imp_memcpy_s
0x18000ef12  mov     ecx, eax; int
0x18000ef14  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000ef19  add     [rdi], esi
0x18000ef1b  movsxd  rdx, dword ptr [rdi]
0x18000ef1e  xor     eax, eax
0x18000ef20  mov     rcx, [rdi+8]
0x18000ef24  mov     [rcx+rdx*2], ax
0x18000ef28  mov     eax, 1
0x18000ef2d  jmp     short loc_18000EF31
0x18000ef2f  xor     eax, eax
0x18000ef31  add     rsp, 28h
0x18000ef35  pop     rdi
0x18000ef36  pop     rsi
0x18000ef37  pop     rbp
0x18000ef38  pop     rbx
0x18000ef39  retn
```
