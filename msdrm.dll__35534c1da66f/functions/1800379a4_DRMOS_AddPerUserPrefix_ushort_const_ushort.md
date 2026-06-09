# DRMOS::AddPerUserPrefix(ushort const *,ushort * *)

- ea: `0x1800379a4`
- end: `0x180037b51`
- name: `?AddPerUserPrefix@DRMOS@@YAJPEBGPEAPEAG@Z`
- size: `429`
- prototype: `__int64 __fastcall(DRMOS *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x1800370d8`
- `0x180037b58`
- `0x1800385a0`

## callees

- `0x180001244`
- `0x180001284`
- `0x180004654`
- `0x1800046c8`
- `0x180015438`
- `0x180017210`
- `0x1800379a4`
- `0x18004cedc`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180037b19`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180037b19`

## string_xrefs

- `0x180037a84`: `[msdrm]: AddPerUserPrefix: Event Name is greater than MAX_PATH`

## pseudocode

```c
__int64 __fastcall DRMOS::AddPerUserPrefix(DRMOS *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned int v5; // r14d
  unsigned __int16 *v6; // rdi
  __int64 v7; // rdx
  DRMOS *v8; // rax
  unsigned __int64 v9; // rax
  _WORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rsi
  unsigned __int16 *v15; // rax
  unsigned __int16 *v17; // [rsp+20h] [rbp-48h]
  __int64 v18; // [rsp+30h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+20h] BYREF

  v5 = 0;
  hMem = 0;
  v6 = 0;
  v17 = 0;
  if ( (int)UDGetProcessUserSIDStringW((LPWSTR *)&hMem) >= 0 )
  {
    try
    {
      if ( this )
      {
        v7 = 0x7FFFFFFF;
        v8 = this;
        do
        {
          if ( !*(_WORD *)v8 )
            break;
          v8 = (DRMOS *)((char *)v8 + 2);
          --v7;
        }
        while ( v7 );
        v9 = (0x7FFFFFFF - v7) & -(__int64)(v7 != 0);
        if ( v7 )
        {
          v10 = hMem;
          if ( hMem )
          {
            v11 = 0x7FFFFFFF;
            do
            {
              if ( !*v10 )
                break;
              ++v10;
              --v11;
            }
            while ( v11 );
            v12 = (0x7FFFFFFF - v11) & -(__int64)(v11 != 0);
            if ( v11 )
            {
              v13 = v12 + v9;
              if ( v12 + v9 < v9 )
                SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v13);
              v14 = v13 + 1;
              if ( v13 + 1 < v13 )
                SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v13);
              if ( v14 <= 0x104 )
              {
                v15 = (unsigned __int16 *)operator new(saturated_mul(v14, 2u));
                v6 = v15;
                v17 = v15;
                if ( v15 )
                {
                  if ( (int)StringCchCopyW(v15, v14, (const unsigned __int16 *)hMem) >= 0
                    && (int)StringCchCatW(v6, v14, (const unsigned __int16 *)this) >= 0 )
                  {
                    *(_QWORD *)a2 = v6;
                    v6 = 0;
                  }
                }
                else
                {
                  v5 = -2147024882;
                }
              }
              else
              {
                _RTLTRACE("[msdrm]: AddPerUserPrefix: Event Name is greater than MAX_PATH");
                v5 = -2147467259;
              }
            }
          }
        }
      }
    }
    catch ( SafeIntException v18 )
    {
      _RTLTRACE("[msdrm]: AddPerUserPrefix: SafeIntException");
      v5 = -2147467259;
      v6 = v17;
    }
  }
  LocalFree(hMem);
  hMem = 0;
  operator delete(v6);
  return v5;
}

```

## disassembly

```asm
0x1800379a4  mov     rax, rsp
0x1800379a7  push    rsi
0x1800379a8  push    rdi
0x1800379a9  push    r12
0x1800379ab  push    r14
0x1800379ad  push    r15
0x1800379af  sub     rsp, 40h
0x1800379b3  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x1800379bb  mov     [rax+8], rbx
0x1800379bf  mov     r12, rdx
0x1800379c2  mov     r15, rcx
0x1800379c5  xor     ebx, ebx
0x1800379c7  mov     r14d, ebx
0x1800379ca  mov     [rax+20h], rbx
0x1800379ce  mov     edi, ebx
0x1800379d0  mov     [rsp+68h+var_48], rbx
0x1800379d5  lea     rcx, [rax+20h]; StringSid
0x1800379d9  call    ?UDGetProcessUserSIDStringW@@YAJPEAPEAG@Z; UDGetProcessUserSIDStringW(ushort * *)
0x1800379de  test    eax, eax
0x1800379e0  jns     short loc_1800379E7
0x1800379e2  jmp     loc_180037B11
0x1800379e7  test    r15, r15
0x1800379ea  jz      loc_180037B00
0x1800379f0  mov     r8d, 7FFFFFFFh
0x1800379f6  mov     edx, r8d
0x1800379f9  mov     rax, r15
0x1800379fc  cmp     [rax], bx
0x1800379ff  jz      short loc_180037A0B
0x180037a01  add     rax, 2
0x180037a05  sub     rdx, 1
0x180037a09  jnz     short loc_1800379FC
0x180037a0b  mov     rax, rdx
0x180037a0e  mov     rcx, r8
0x180037a11  sub     rcx, rdx
0x180037a14  neg     rax
0x180037a17  sbb     rax, rax
0x180037a1a  and     rax, rcx
0x180037a1d  test    rdx, rdx
0x180037a20  jz      loc_180037B00
0x180037a26  mov     rcx, [rsp+68h+hMem]
0x180037a2e  test    rcx, rcx
0x180037a31  jz      loc_180037AFE
0x180037a37  mov     rdx, r8
0x180037a3a  cmp     [rcx], bx
0x180037a3d  jz      short loc_180037A49
0x180037a3f  add     rcx, 2
0x180037a43  sub     rdx, 1
0x180037a47  jnz     short loc_180037A3A
0x180037a49  mov     rcx, rdx
0x180037a4c  sub     r8, rdx
0x180037a4f  neg     rcx
0x180037a52  sbb     r9, r9
0x180037a55  and     r9, r8
0x180037a58  test    rdx, rdx
0x180037a5b  jz      loc_180037AFE
0x180037a61  lea     rcx, [r9+rax]
0x180037a65  cmp     rcx, rax
0x180037a68  jb      loc_180037B44
0x180037a6e  lea     rsi, [rcx+1]
0x180037a72  cmp     rsi, rcx
0x180037a75  jb      loc_180037B4A
0x180037a7b  cmp     rsi, 104h
0x180037a82  jbe     short loc_180037A98
0x180037a84  lea     rcx, aMsdrmAddperuse; "[msdrm]: AddPerUserPrefix: Event Name i"...
0x180037a8b  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180037a90  mov     r14d, 80004005h
0x180037a96  jmp     short loc_180037B11
0x180037a98  mov     eax, 2
0x180037a9d  mul     rsi
0x180037aa0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180037aa7  cmovb   rax, rcx
0x180037aab  mov     rcx, rax; Size
0x180037aae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037ab3  mov     rdi, rax
0x180037ab6  mov     [rsp+68h+var_48], rax
0x180037abb  test    rax, rax
0x180037abe  jnz     short loc_180037AC8
0x180037ac0  mov     r14d, 8007000Eh
0x180037ac6  jmp     short loc_180037B11
0x180037ac8  mov     r8, [rsp+68h+hMem]; unsigned __int16 *
0x180037ad0  mov     rdx, rsi; unsigned __int64
0x180037ad3  mov     rcx, rdi; unsigned __int16 *
0x180037ad6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037adb  test    eax, eax
0x180037add  jns     short loc_180037AE1
0x180037adf  jmp     short loc_180037B11
0x180037ae1  mov     r8, r15; unsigned __int16 *
0x180037ae4  mov     rdx, rsi; unsigned __int64
0x180037ae7  mov     rcx, rdi; unsigned __int16 *
0x180037aea  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037aef  test    eax, eax
0x180037af1  jns     short loc_180037AF5
0x180037af3  jmp     short loc_180037B11
0x180037af5  mov     [r12], rdi
0x180037af9  mov     rdi, rbx
0x180037afc  jmp     short loc_180037B11
0x180037afe  jmp     short loc_180037B11
0x180037b00  jmp     short loc_180037B11
0x180037b02  xor     ebx, ebx
0x180037b04  mov     r14d, [rsp+68h+arg_10]
0x180037b0c  mov     rdi, [rsp+68h+var_48]
0x180037b11  mov     rcx, [rsp+68h+hMem]; hMem
0x180037b19  call    cs:__imp_LocalFree
0x180037b1f  mov     [rsp+68h+hMem], rbx
0x180037b27  mov     rcx, rdi; Block
0x180037b2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180037b2f  mov     eax, r14d
0x180037b32  mov     rbx, [rsp+68h+arg_0]
0x180037b37  add     rsp, 40h
0x180037b3b  pop     r15
0x180037b3d  pop     r14
0x180037b3f  pop     r12
0x180037b41  pop     rdi
0x180037b42  pop     rsi
0x180037b43  retn
0x180037b44  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180037b4a  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
