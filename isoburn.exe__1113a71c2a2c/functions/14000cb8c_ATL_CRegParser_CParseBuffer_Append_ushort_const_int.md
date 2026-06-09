# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x14000cb8c`
- end: `0x14000cc42`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `182`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000d138`

## callees

- `0x14000cb8c`
- `0x14000eb64`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x14000cbdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x14000cbdf`

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
0x14000cb8c  push    rbx
0x14000cb8e  push    rbp
0x14000cb8f  push    rsi
0x14000cb90  push    rdi
0x14000cb91  sub     rsp, 28h
0x14000cb95  mov     rdi, rcx
0x14000cb98  mov     esi, r8d
0x14000cb9b  lea     ecx, [r8+1]
0x14000cb9f  mov     rbp, rdx
0x14000cba2  add     ecx, [rdi]
0x14000cba4  cmp     ecx, [rdi]
0x14000cba6  jle     loc_14000CC37
0x14000cbac  cmp     ecx, r8d
0x14000cbaf  jle     loc_14000CC37
0x14000cbb5  mov     ebx, [rdi+4]
0x14000cbb8  cmp     ecx, ebx
0x14000cbba  jl      short loc_14000CBF1
0x14000cbbc  cmp     ebx, 3FFFFFFFh
0x14000cbc2  jg      short loc_14000CC37
0x14000cbc4  add     ebx, ebx
0x14000cbc6  cmp     ecx, ebx
0x14000cbc8  jge     short loc_14000CBBC
0x14000cbca  mov     eax, ebx
0x14000cbcc  mov     ecx, 0FFFFFFFFh
0x14000cbd1  add     rax, rax
0x14000cbd4  cmp     rax, rcx
0x14000cbd7  ja      short loc_14000CC37
0x14000cbd9  mov     rcx, [rdi+8]; pv
0x14000cbdd  mov     edx, eax; cb
0x14000cbdf  call    cs:__imp_CoTaskMemRealloc
0x14000cbe5  test    rax, rax
0x14000cbe8  jz      short loc_14000CC37
0x14000cbea  mov     [rdi+8], rax
0x14000cbee  mov     [rdi+4], ebx
0x14000cbf1  cmp     dword ptr [rdi], 0
0x14000cbf4  jl      short loc_14000CC37
0x14000cbf6  cmp     [rdi], ebx
0x14000cbf8  jge     short loc_14000CC37
0x14000cbfa  mov     ecx, ebx
0x14000cbfc  sub     ecx, [rdi]
0x14000cbfe  cmp     ecx, ebx
0x14000cc00  jg      short loc_14000CC37
0x14000cc02  movsxd  rdx, ecx
0x14000cc05  lea     eax, [rsi+rsi]
0x14000cc08  movsxd  rcx, dword ptr [rdi]
0x14000cc0b  add     rdx, rdx; void *
0x14000cc0e  movsxd  r9, eax; void *
0x14000cc11  mov     r8, rbp; unsigned __int64
0x14000cc14  mov     rax, [rdi+8]
0x14000cc18  lea     rcx, [rax+rcx*2]; this
0x14000cc1c  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x14000cc21  add     [rdi], esi
0x14000cc23  movsxd  rdx, dword ptr [rdi]
0x14000cc26  xor     eax, eax
0x14000cc28  mov     rcx, [rdi+8]
0x14000cc2c  mov     [rcx+rdx*2], ax
0x14000cc30  mov     eax, 1
0x14000cc35  jmp     short loc_14000CC39
0x14000cc37  xor     eax, eax
0x14000cc39  add     rsp, 28h
0x14000cc3d  pop     rdi
0x14000cc3e  pop     rsi
0x14000cc3f  pop     rbp
0x14000cc40  pop     rbx
0x14000cc41  retn
```
