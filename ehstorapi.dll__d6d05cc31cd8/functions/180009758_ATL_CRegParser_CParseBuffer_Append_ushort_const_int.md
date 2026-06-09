# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180009758`
- end: `0x18000982d`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `213`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a728`

## callees

- `0x180002210`
- `0x180008b90`
- `0x180009758`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800097ff`
- `msvcrt!memcpy_s` at `0x1800097ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800097c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800097c2`

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
0x180009758  push    rbx
0x18000975a  push    rbp
0x18000975b  push    rsi
0x18000975c  push    rdi
0x18000975d  sub     rsp, 28h
0x180009761  mov     rdi, rcx
0x180009764  mov     esi, r8d
0x180009767  lea     ecx, [r8+1]
0x18000976b  mov     rbp, rdx
0x18000976e  add     ecx, [rdi]
0x180009770  cmp     ecx, [rdi]
0x180009772  jle     loc_180009822
0x180009778  cmp     ecx, r8d
0x18000977b  jle     loc_180009822
0x180009781  mov     ebx, [rdi+4]
0x180009784  cmp     ecx, ebx
0x180009786  jl      short loc_1800097D4
0x180009788  cmp     ecx, ebx
0x18000978a  jl      short loc_18000979C
0x18000978c  cmp     ebx, 3FFFFFFFh
0x180009792  jg      loc_180009822
0x180009798  add     ebx, ebx
0x18000979a  jmp     short loc_180009788
0x18000979c  mov     r8d, 2
0x1800097a2  mov     dword ptr [rsp+48h+cb], 0
0x1800097aa  mov     edx, ebx
0x1800097ac  lea     rcx, [rsp+48h+cb]
0x1800097b1  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x1800097b6  test    eax, eax
0x1800097b8  js      short loc_180009822
0x1800097ba  mov     edx, dword ptr [rsp+48h+cb]; cb
0x1800097be  mov     rcx, [rdi+8]; pv
0x1800097c2  call    cs:__imp_CoTaskMemRealloc
0x1800097c8  test    rax, rax
0x1800097cb  jz      short loc_180009822
0x1800097cd  mov     [rdi+8], rax
0x1800097d1  mov     [rdi+4], ebx
0x1800097d4  cmp     dword ptr [rdi], 0
0x1800097d7  jl      short loc_180009822
0x1800097d9  cmp     [rdi], ebx
0x1800097db  jge     short loc_180009822
0x1800097dd  mov     ecx, ebx
0x1800097df  sub     ecx, [rdi]
0x1800097e1  cmp     ecx, ebx
0x1800097e3  jg      short loc_180009822
0x1800097e5  movsxd  rdx, ecx
0x1800097e8  lea     eax, [rsi+rsi]
0x1800097eb  movsxd  rcx, dword ptr [rdi]
0x1800097ee  add     rdx, rdx; DestinationSize
0x1800097f1  movsxd  r9, eax; SourceSize
0x1800097f4  mov     r8, rbp; Source
0x1800097f7  mov     rax, [rdi+8]
0x1800097fb  lea     rcx, [rax+rcx*2]; Destination
0x1800097ff  call    cs:__imp_memcpy_s
0x180009805  mov     ecx, eax; int
0x180009807  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000980c  add     [rdi], esi
0x18000980e  movsxd  rdx, dword ptr [rdi]
0x180009811  xor     eax, eax
0x180009813  mov     rcx, [rdi+8]
0x180009817  mov     [rcx+rdx*2], ax
0x18000981b  mov     eax, 1
0x180009820  jmp     short loc_180009824
0x180009822  xor     eax, eax
0x180009824  add     rsp, 28h
0x180009828  pop     rdi
0x180009829  pop     rsi
0x18000982a  pop     rbp
0x18000982b  pop     rbx
0x18000982c  retn
```
