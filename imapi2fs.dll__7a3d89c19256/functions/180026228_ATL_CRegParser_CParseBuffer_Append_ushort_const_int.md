# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180026228`
- end: `0x1800262fd`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `213`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800270cc`

## callees

- `0x180005cec`
- `0x18002589c`
- `0x180026228`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800262cf`
- `msvcrt!memcpy_s` at `0x1800262cf`
- `ole32!CoTaskMemRealloc` at `0x180026292`
- `ole32!CoTaskMemRealloc` at `0x180026292`

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
0x180026228  push    rbx
0x18002622a  push    rbp
0x18002622b  push    rsi
0x18002622c  push    rdi
0x18002622d  sub     rsp, 28h
0x180026231  mov     rdi, rcx
0x180026234  mov     esi, r8d
0x180026237  lea     ecx, [r8+1]
0x18002623b  mov     rbp, rdx
0x18002623e  add     ecx, [rdi]
0x180026240  cmp     ecx, [rdi]
0x180026242  jle     loc_1800262F2
0x180026248  cmp     ecx, r8d
0x18002624b  jle     loc_1800262F2
0x180026251  mov     ebx, [rdi+4]
0x180026254  cmp     ecx, ebx
0x180026256  jl      short loc_1800262A4
0x180026258  cmp     ecx, ebx
0x18002625a  jl      short loc_18002626C
0x18002625c  cmp     ebx, 3FFFFFFFh
0x180026262  jg      loc_1800262F2
0x180026268  add     ebx, ebx
0x18002626a  jmp     short loc_180026258
0x18002626c  mov     r8d, 2
0x180026272  mov     dword ptr [rsp+48h+cb], 0
0x18002627a  mov     edx, ebx
0x18002627c  lea     rcx, [rsp+48h+cb]
0x180026281  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x180026286  test    eax, eax
0x180026288  js      short loc_1800262F2
0x18002628a  mov     edx, dword ptr [rsp+48h+cb]; cb
0x18002628e  mov     rcx, [rdi+8]; pv
0x180026292  call    cs:__imp_CoTaskMemRealloc
0x180026298  test    rax, rax
0x18002629b  jz      short loc_1800262F2
0x18002629d  mov     [rdi+8], rax
0x1800262a1  mov     [rdi+4], ebx
0x1800262a4  cmp     dword ptr [rdi], 0
0x1800262a7  jl      short loc_1800262F2
0x1800262a9  cmp     [rdi], ebx
0x1800262ab  jge     short loc_1800262F2
0x1800262ad  mov     ecx, ebx
0x1800262af  sub     ecx, [rdi]
0x1800262b1  cmp     ecx, ebx
0x1800262b3  jg      short loc_1800262F2
0x1800262b5  movsxd  rdx, ecx
0x1800262b8  lea     eax, [rsi+rsi]
0x1800262bb  movsxd  rcx, dword ptr [rdi]
0x1800262be  add     rdx, rdx; DestinationSize
0x1800262c1  movsxd  r9, eax; SourceSize
0x1800262c4  mov     r8, rbp; Source
0x1800262c7  mov     rax, [rdi+8]
0x1800262cb  lea     rcx, [rax+rcx*2]; Destination
0x1800262cf  call    cs:__imp_memcpy_s
0x1800262d5  mov     ecx, eax; int
0x1800262d7  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800262dc  add     [rdi], esi
0x1800262de  movsxd  rdx, dword ptr [rdi]
0x1800262e1  xor     eax, eax
0x1800262e3  mov     rcx, [rdi+8]
0x1800262e7  mov     [rcx+rdx*2], ax
0x1800262eb  mov     eax, 1
0x1800262f0  jmp     short loc_1800262F4
0x1800262f2  xor     eax, eax
0x1800262f4  add     rsp, 28h
0x1800262f8  pop     rdi
0x1800262f9  pop     rsi
0x1800262fa  pop     rbp
0x1800262fb  pop     rbx
0x1800262fc  retn
```
