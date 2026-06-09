# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800094b8`
- end: `0x18000958d`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `213`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ac58`

## callees

- `0x1800086e0`
- `0x1800094b8`
- `0x1800096a8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000955f`
- `msvcrt!memcpy_s` at `0x18000955f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180009522`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180009522`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800094b8  push    rbx
0x1800094ba  push    rbp
0x1800094bb  push    rsi
0x1800094bc  push    rdi
0x1800094bd  sub     rsp, 28h
0x1800094c1  mov     rdi, rcx
0x1800094c4  mov     esi, r8d
0x1800094c7  lea     ecx, [r8+1]
0x1800094cb  mov     rbp, rdx
0x1800094ce  add     ecx, [rdi]
0x1800094d0  cmp     ecx, [rdi]
0x1800094d2  jle     loc_180009582
0x1800094d8  cmp     ecx, r8d
0x1800094db  jle     loc_180009582
0x1800094e1  mov     ebx, [rdi+4]
0x1800094e4  cmp     ecx, ebx
0x1800094e6  jl      short loc_180009534
0x1800094e8  cmp     ecx, ebx
0x1800094ea  jl      short loc_1800094FC
0x1800094ec  cmp     ebx, 3FFFFFFFh
0x1800094f2  jg      loc_180009582
0x1800094f8  add     ebx, ebx
0x1800094fa  jmp     short loc_1800094E8
0x1800094fc  mov     r8d, 2
0x180009502  mov     dword ptr [rsp+48h+cb], 0
0x18000950a  mov     edx, ebx
0x18000950c  lea     rcx, [rsp+48h+cb]
0x180009511  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x180009516  test    eax, eax
0x180009518  js      short loc_180009582
0x18000951a  mov     edx, dword ptr [rsp+48h+cb]; cb
0x18000951e  mov     rcx, [rdi+8]; pv
0x180009522  call    cs:__imp_CoTaskMemRealloc
0x180009528  test    rax, rax
0x18000952b  jz      short loc_180009582
0x18000952d  mov     [rdi+8], rax
0x180009531  mov     [rdi+4], ebx
0x180009534  cmp     dword ptr [rdi], 0
0x180009537  jl      short loc_180009582
0x180009539  cmp     [rdi], ebx
0x18000953b  jge     short loc_180009582
0x18000953d  mov     ecx, ebx
0x18000953f  sub     ecx, [rdi]
0x180009541  cmp     ecx, ebx
0x180009543  jg      short loc_180009582
0x180009545  movsxd  rdx, ecx
0x180009548  lea     eax, [rsi+rsi]
0x18000954b  movsxd  rcx, dword ptr [rdi]
0x18000954e  add     rdx, rdx; DestinationSize
0x180009551  movsxd  r9, eax; SourceSize
0x180009554  mov     r8, rbp; Source
0x180009557  mov     rax, [rdi+8]
0x18000955b  lea     rcx, [rax+rcx*2]; Destination
0x18000955f  call    cs:__imp_memcpy_s
0x180009565  mov     ecx, eax; int
0x180009567  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000956c  add     [rdi], esi
0x18000956e  movsxd  rdx, dword ptr [rdi]
0x180009571  xor     eax, eax
0x180009573  mov     rcx, [rdi+8]
0x180009577  mov     [rcx+rdx*2], ax
0x18000957b  mov     eax, 1
0x180009580  jmp     short loc_180009584
0x180009582  xor     eax, eax
0x180009584  add     rsp, 28h
0x180009588  pop     rdi
0x180009589  pop     rsi
0x18000958a  pop     rbp
0x18000958b  pop     rbx
0x18000958c  retn
```
