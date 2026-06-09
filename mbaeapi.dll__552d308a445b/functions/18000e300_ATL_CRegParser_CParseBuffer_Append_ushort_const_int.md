# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18000e300`
- end: `0x18000e3b6`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `182`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010d9c`

## callees

- `0x18000e300`
- `0x180013c4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e353`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e353`

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
  unsigned __int64 v12; // [rsp+20h] [rbp-28h]

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
          ATL::Checked::memcpy_s(
            (ATL::Checked *)(*((_QWORD *)this + 1) + 2LL * *(int *)this),
            (void *)(2LL * v10),
            (unsigned __int64)a2,
            (const void *)(2 * a3),
            v12);
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
0x18000e300  push    rbx
0x18000e302  push    rbp
0x18000e303  push    rsi
0x18000e304  push    rdi
0x18000e305  sub     rsp, 28h
0x18000e309  mov     rdi, rcx
0x18000e30c  mov     esi, r8d
0x18000e30f  lea     ecx, [r8+1]
0x18000e313  mov     rbp, rdx
0x18000e316  add     ecx, [rdi]
0x18000e318  cmp     ecx, [rdi]
0x18000e31a  jle     loc_18000E3AB
0x18000e320  cmp     ecx, r8d
0x18000e323  jle     loc_18000E3AB
0x18000e329  mov     ebx, [rdi+4]
0x18000e32c  cmp     ecx, ebx
0x18000e32e  jl      short loc_18000E365
0x18000e330  cmp     ebx, 3FFFFFFFh
0x18000e336  jg      short loc_18000E3AB
0x18000e338  add     ebx, ebx
0x18000e33a  cmp     ecx, ebx
0x18000e33c  jge     short loc_18000E330
0x18000e33e  mov     eax, ebx
0x18000e340  mov     ecx, 0FFFFFFFFh
0x18000e345  add     rax, rax
0x18000e348  cmp     rax, rcx
0x18000e34b  ja      short loc_18000E3AB
0x18000e34d  mov     rcx, [rdi+8]; pv
0x18000e351  mov     edx, eax; cb
0x18000e353  call    cs:__imp_CoTaskMemRealloc
0x18000e359  test    rax, rax
0x18000e35c  jz      short loc_18000E3AB
0x18000e35e  mov     [rdi+8], rax
0x18000e362  mov     [rdi+4], ebx
0x18000e365  cmp     dword ptr [rdi], 0
0x18000e368  jl      short loc_18000E3AB
0x18000e36a  cmp     [rdi], ebx
0x18000e36c  jge     short loc_18000E3AB
0x18000e36e  mov     ecx, ebx
0x18000e370  sub     ecx, [rdi]
0x18000e372  cmp     ecx, ebx
0x18000e374  jg      short loc_18000E3AB
0x18000e376  movsxd  rdx, ecx
0x18000e379  lea     eax, [rsi+rsi]
0x18000e37c  movsxd  rcx, dword ptr [rdi]
0x18000e37f  add     rdx, rdx; void *
0x18000e382  movsxd  r9, eax; void *
0x18000e385  mov     r8, rbp; unsigned __int64
0x18000e388  mov     rax, [rdi+8]
0x18000e38c  lea     rcx, [rax+rcx*2]; this
0x18000e390  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18000e395  add     [rdi], esi
0x18000e397  movsxd  rdx, dword ptr [rdi]
0x18000e39a  xor     eax, eax
0x18000e39c  mov     rcx, [rdi+8]
0x18000e3a0  mov     [rcx+rdx*2], ax
0x18000e3a4  mov     eax, 1
0x18000e3a9  jmp     short loc_18000E3AD
0x18000e3ab  xor     eax, eax
0x18000e3ad  add     rsp, 28h
0x18000e3b1  pop     rdi
0x18000e3b2  pop     rsi
0x18000e3b3  pop     rbp
0x18000e3b4  pop     rbx
0x18000e3b5  retn
```
