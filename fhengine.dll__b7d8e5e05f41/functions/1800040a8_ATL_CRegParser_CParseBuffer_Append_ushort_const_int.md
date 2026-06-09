# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800040a8`
- end: `0x18000417d`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `213`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800051d4`

## callees

- `0x180002b4c`
- `0x1800040a8`
- `0x180004184`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000414f`
- `msvcrt!memcpy_s` at `0x18000414f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004112`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004112`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const unsigned __int16 *a2,
        int a3)
{
  int v6; // ecx
  int v7; // ebx
  LPVOID v8; // rax
  int v9; // ecx
  errno_t v10; // eax
  SIZE_T cb; // [rsp+60h] [rbp+18h] BYREF

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
      LODWORD(cb) = 0;
      if ( (int)ATL::AtlMultiply<unsigned long>(&cb, (unsigned int)v7, 2) < 0 )
        return 0;
      v8 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)cb);
      if ( !v8 )
        return 0;
      *((_QWORD *)this + 1) = v8;
      *((_DWORD *)this + 1) = v7;
    }
    if ( *(int *)this >= 0 && *(_DWORD *)this < v7 )
    {
      v9 = v7 - *(_DWORD *)this;
      if ( v9 <= v7 )
      {
        v10 = memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v9, a2, 2 * a3);
        ATL::AtlCrtErrorCheck(v10);
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
0x1800040a8  push    rbx
0x1800040aa  push    rbp
0x1800040ab  push    rsi
0x1800040ac  push    rdi
0x1800040ad  sub     rsp, 28h
0x1800040b1  mov     rdi, rcx
0x1800040b4  mov     esi, r8d
0x1800040b7  lea     ecx, [r8+1]
0x1800040bb  mov     rbp, rdx
0x1800040be  add     ecx, [rdi]
0x1800040c0  cmp     ecx, [rdi]
0x1800040c2  jle     loc_180004172
0x1800040c8  cmp     ecx, r8d
0x1800040cb  jle     loc_180004172
0x1800040d1  mov     ebx, [rdi+4]
0x1800040d4  cmp     ecx, ebx
0x1800040d6  jl      short loc_180004124
0x1800040d8  cmp     ecx, ebx
0x1800040da  jl      short loc_1800040EC
0x1800040dc  cmp     ebx, 3FFFFFFFh
0x1800040e2  jg      loc_180004172
0x1800040e8  add     ebx, ebx
0x1800040ea  jmp     short loc_1800040D8
0x1800040ec  mov     r8d, 2
0x1800040f2  mov     dword ptr [rsp+48h+cb], 0
0x1800040fa  mov     edx, ebx
0x1800040fc  lea     rcx, [rsp+48h+cb]
0x180004101  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x180004106  test    eax, eax
0x180004108  js      short loc_180004172
0x18000410a  mov     edx, dword ptr [rsp+48h+cb]; cb
0x18000410e  mov     rcx, [rdi+8]; pv
0x180004112  call    cs:__imp_CoTaskMemRealloc
0x180004118  test    rax, rax
0x18000411b  jz      short loc_180004172
0x18000411d  mov     [rdi+8], rax
0x180004121  mov     [rdi+4], ebx
0x180004124  cmp     dword ptr [rdi], 0
0x180004127  jl      short loc_180004172
0x180004129  cmp     [rdi], ebx
0x18000412b  jge     short loc_180004172
0x18000412d  mov     ecx, ebx
0x18000412f  sub     ecx, [rdi]
0x180004131  cmp     ecx, ebx
0x180004133  jg      short loc_180004172
0x180004135  movsxd  rdx, ecx
0x180004138  lea     eax, [rsi+rsi]
0x18000413b  movsxd  rcx, dword ptr [rdi]
0x18000413e  add     rdx, rdx; DestinationSize
0x180004141  movsxd  r9, eax; SourceSize
0x180004144  mov     r8, rbp; Source
0x180004147  mov     rax, [rdi+8]
0x18000414b  lea     rcx, [rax+rcx*2]; Destination
0x18000414f  call    cs:__imp_memcpy_s
0x180004155  mov     ecx, eax; int
0x180004157  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000415c  add     [rdi], esi
0x18000415e  movsxd  rdx, dword ptr [rdi]
0x180004161  xor     eax, eax
0x180004163  mov     rcx, [rdi+8]
0x180004167  mov     [rcx+rdx*2], ax
0x18000416b  mov     eax, 1
0x180004170  jmp     short loc_180004174
0x180004172  xor     eax, eax
0x180004174  add     rsp, 28h
0x180004178  pop     rdi
0x180004179  pop     rsi
0x18000417a  pop     rbp
0x18000417b  pop     rbx
0x18000417c  retn
```
