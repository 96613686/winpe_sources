# ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)

- ea: `0x18000bbc4`
- end: `0x18000bc98`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000eccc`

## callees

- `0x180008f58`
- `0x18000913c`
- `0x18000bbc4`
- `0x18000be84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000bc2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000bc2e`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const wchar_t *a2,
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
0x18000bbc4  push    rbx
0x18000bbc6  push    rbp
0x18000bbc7  push    rsi
0x18000bbc8  push    rdi
0x18000bbc9  sub     rsp, 28h
0x18000bbcd  mov     rdi, rcx
0x18000bbd0  mov     esi, r8d
0x18000bbd3  lea     ecx, [r8+1]
0x18000bbd7  mov     rbp, rdx
0x18000bbda  add     ecx, [rdi]
0x18000bbdc  cmp     ecx, [rdi]
0x18000bbde  jle     loc_18000BC8D
0x18000bbe4  cmp     ecx, r8d
0x18000bbe7  jle     loc_18000BC8D
0x18000bbed  mov     ebx, [rdi+4]
0x18000bbf0  cmp     ecx, ebx
0x18000bbf2  jl      short loc_18000BC40
0x18000bbf4  cmp     ecx, ebx
0x18000bbf6  jl      short loc_18000BC08
0x18000bbf8  cmp     ebx, 3FFFFFFFh
0x18000bbfe  jg      loc_18000BC8D
0x18000bc04  add     ebx, ebx
0x18000bc06  jmp     short loc_18000BBF4
0x18000bc08  mov     r8d, 2
0x18000bc0e  mov     dword ptr [rsp+48h+cb], 0
0x18000bc16  mov     edx, ebx
0x18000bc18  lea     rcx, [rsp+48h+cb]
0x18000bc1d  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18000bc22  test    eax, eax
0x18000bc24  js      short loc_18000BC8D
0x18000bc26  mov     edx, dword ptr [rsp+48h+cb]; cb
0x18000bc2a  mov     rcx, [rdi+8]; pv
0x18000bc2e  call    cs:__imp_CoTaskMemRealloc
0x18000bc34  test    rax, rax
0x18000bc37  jz      short loc_18000BC8D
0x18000bc39  mov     [rdi+8], rax
0x18000bc3d  mov     [rdi+4], ebx
0x18000bc40  cmp     dword ptr [rdi], 0
0x18000bc43  jl      short loc_18000BC8D
0x18000bc45  cmp     [rdi], ebx
0x18000bc47  jge     short loc_18000BC8D
0x18000bc49  mov     ecx, ebx
0x18000bc4b  sub     ecx, [rdi]
0x18000bc4d  cmp     ecx, ebx
0x18000bc4f  jg      short loc_18000BC8D
0x18000bc51  movsxd  rdx, ecx
0x18000bc54  lea     eax, [rsi+rsi]
0x18000bc57  movsxd  rcx, dword ptr [rdi]
0x18000bc5a  add     rdx, rdx; DestinationSize
0x18000bc5d  movsxd  r9, eax; SourceSize
0x18000bc60  mov     r8, rbp; Source
0x18000bc63  mov     rax, [rdi+8]
0x18000bc67  lea     rcx, [rax+rcx*2]; Destination
0x18000bc6b  call    memcpy_s
0x18000bc70  mov     ecx, eax; int
0x18000bc72  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000bc77  add     [rdi], esi
0x18000bc79  movsxd  rdx, dword ptr [rdi]
0x18000bc7c  xor     eax, eax
0x18000bc7e  mov     rcx, [rdi+8]
0x18000bc82  mov     [rcx+rdx*2], ax
0x18000bc86  mov     eax, 1
0x18000bc8b  jmp     short loc_18000BC8F
0x18000bc8d  xor     eax, eax
0x18000bc8f  add     rsp, 28h
0x18000bc93  pop     rdi
0x18000bc94  pop     rsi
0x18000bc95  pop     rbp
0x18000bc96  pop     rbx
0x18000bc97  retn
```
