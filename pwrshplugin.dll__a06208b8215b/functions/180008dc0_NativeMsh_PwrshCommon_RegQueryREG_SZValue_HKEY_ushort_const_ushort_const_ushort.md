# NativeMsh::PwrshCommon::RegQueryREG_SZValue(HKEY__ *,ushort const *,ushort const *,ushort * *)

- ea: `0x180008dc0`
- end: `0x180009154`
- name: `?RegQueryREG_SZValue@PwrshCommon@NativeMsh@@IEAA_NPEAUHKEY__@@PEBG1PEAPEAG@Z`
- size: `916`
- prototype: `char __fastcall(NativeMsh::PwrshCommon *this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007c2c`

## callees

- `0x180001318`
- `0x180008dc0`
- `0x18000b010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180008efb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008f4e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800090a8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800090f2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800090fd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008efb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008f4e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800090a8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800090f2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800090fd`
- `KERNEL32!FormatMessageW` at `0x180008e68`
- `KERNEL32!FormatMessageW` at `0x18000901b`
- `KERNEL32!FormatMessageW` at `0x180008e68`
- `KERNEL32!FormatMessageW` at `0x18000901b`
- `KERNEL32!LocalFree` at `0x180008f08`
- `KERNEL32!LocalFree` at `0x1800090b4`
- `KERNEL32!LocalFree` at `0x180008f08`
- `KERNEL32!LocalFree` at `0x1800090b4`
- `ADVAPI32!RegQueryValueExW` at `0x180008e37`
- `ADVAPI32!RegQueryValueExW` at `0x180008fea`
- `ADVAPI32!RegQueryValueExW` at `0x180008e37`
- `ADVAPI32!RegQueryValueExW` at `0x180008fea`

## pseudocode

```c
char __fastcall NativeMsh::PwrshCommon::RegQueryREG_SZValue(
        NativeMsh::PwrshCommon *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  char v5; // bl
  BYTE *v10; // r14
  LSTATUS v11; // eax
  DWORD v12; // eax
  DWORD v13; // r15d
  unsigned __int64 v14; // rsi
  _WORD *v15; // rax
  _WORD *v16; // rdi
  _WORD *v17; // rcx
  __int64 v18; // rax
  _WORD *v19; // rdx
  _WORD *v20; // rcx
  __int64 v21; // r8
  DWORD v22; // edi
  LSTATUS v23; // eax
  DWORD v24; // eax
  DWORD v25; // r15d
  unsigned __int64 v26; // rsi
  _WORD *v27; // rax
  _WORD *v28; // rdi
  _WORD *v29; // rcx
  __int64 v30; // rax
  _WORD *v31; // rdx
  _WORD *v32; // rcx
  DWORD Type; // [rsp+40h] [rbp-10h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+48h] BYREF
  const unsigned __int16 *v38; // [rsp+A0h] [rbp+50h]

  v38 = a3;
  v5 = 0;
  Type = 0;
  cbData = 0;
  v10 = 0;
  if ( !a2 || !a4 || !*a4 || !a5 )
    goto LABEL_50;
  v11 = RegQueryValueExW(a2, a3, 0, &Type, 0, &cbData);
  if ( !v11 )
  {
    v5 = 1;
    if ( Type != 1 )
    {
      v21 = 24;
LABEL_24:
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, const unsigned __int16 *, const unsigned __int16 *))(**((_QWORD **)this + 1) + 8LL))(
        *((_QWORD *)this + 1),
        0,
        v21,
        a4,
        a3);
      v5 = 0;
      goto LABEL_50;
    }
    if ( !cbData )
    {
      v21 = 14;
      goto LABEL_24;
    }
    v22 = cbData >> 1;
    v10 = (BYTE *)operator new[](saturated_mul((cbData >> 1) + 1, 2u));
    if ( !v10 )
    {
      v5 = 0;
      goto LABEL_50;
    }
    *(_WORD *)&v10[2 * v22] = 0;
    v23 = RegQueryValueExW(a2, a3, 0, 0, v10, &cbData);
    if ( !v23 )
    {
      if ( *(_WORD *)v10 )
        goto LABEL_50;
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, const unsigned __int16 *, const unsigned __int16 *))(**((_QWORD **)this + 1) + 8LL))(
        *((_QWORD *)this + 1),
        0,
        14,
        a4,
        a3);
LABEL_49:
      v5 = 0;
      goto LABEL_50;
    }
    *(_QWORD *)Buffer = 0;
    v24 = FormatMessageW(0x1100u, 0, v23, 0, Buffer, 0, 0);
    v25 = v24;
    if ( !v24 )
    {
LABEL_46:
      operator delete[](v10);
      v10 = 0;
      goto LABEL_49;
    }
    v26 = v24 + 1;
    v27 = operator new[](saturated_mul(v26, 2u));
    v28 = v27;
    if ( v27 )
    {
      if ( v26 )
      {
        if ( v26 <= 0x7FFFFFFF )
        {
          v29 = *(_WORD **)Buffer;
          v30 = 2147483646;
          v31 = v28;
          do
          {
            if ( !v30 )
              break;
            if ( !*v29 )
              break;
            *v31++ = *v29++;
            --v30;
            --v26;
          }
          while ( v26 );
          v32 = v31 - 1;
          if ( v26 )
            v32 = v31;
          *v32 = 0;
          if ( v26 )
            goto LABEL_43;
        }
        else
        {
          *v27 = 0;
        }
      }
      v25 = 0;
      operator delete[](v28);
      v28 = 0;
    }
LABEL_43:
    LocalFree(*(HLOCAL *)Buffer);
    if ( v25 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, const unsigned __int16 *, const unsigned __int16 *, _WORD *))(**((_QWORD **)this + 1) + 8LL))(
        *((_QWORD *)this + 1),
        0,
        22,
        a4,
        v38,
        v28);
      if ( v28 )
        operator delete[](v28);
    }
    goto LABEL_46;
  }
  *(_QWORD *)Buffer = 0;
  v12 = FormatMessageW(0x1100u, 0, v11, 0, Buffer, 0, 0);
  v13 = v12;
  if ( !v12 )
    goto LABEL_50;
  v14 = v12 + 1;
  v15 = operator new[](saturated_mul(v14, 2u));
  v16 = v15;
  if ( !v15 )
    goto LABEL_19;
  if ( v14 )
  {
    if ( v14 <= 0x7FFFFFFF )
    {
      v17 = *(_WORD **)Buffer;
      v18 = 2147483646;
      v19 = v16;
      do
      {
        if ( !v18 )
          break;
        if ( !*v17 )
          break;
        *v19++ = *v17++;
        --v18;
        --v14;
      }
      while ( v14 );
      v5 = 0;
      v20 = v19 - 1;
      if ( v14 )
        v20 = v19;
      *v20 = 0;
      if ( v14 )
        goto LABEL_19;
    }
    else
    {
      *v15 = 0;
    }
  }
  v13 = 0;
  operator delete[](v16);
  v16 = 0;
LABEL_19:
  LocalFree(*(HLOCAL *)Buffer);
  if ( v13 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, const unsigned __int16 *, const unsigned __int16 *, _WORD *))(**((_QWORD **)this + 1) + 8LL))(
      *((_QWORD *)this + 1),
      0,
      22,
      a4,
      v38,
      v16);
    if ( v16 )
      operator delete[](v16);
  }
LABEL_50:
  *a5 = (unsigned __int16 *)v10;
  return v5;
}

```

## disassembly

```asm
0x180008dc0  mov     r11, rsp
0x180008dc3  mov     [r11+20h], rbx
0x180008dc7  mov     [r11+18h], r8
0x180008dcb  mov     [r11+8], rcx
0x180008dcf  push    rbp
0x180008dd0  push    rsi
0x180008dd1  push    rdi
0x180008dd2  push    r12
0x180008dd4  push    r13
0x180008dd6  push    r14
0x180008dd8  push    r15
0x180008dda  mov     rbp, rsp
0x180008ddd  sub     rsp, 50h
0x180008de1  xor     ebx, ebx
0x180008de3  mov     r12, r9
0x180008de6  mov     [rbp+Type], ebx
0x180008de9  mov     r15, r8
0x180008dec  mov     [rbp+cbData], ebx
0x180008def  mov     rsi, rdx
0x180008df2  mov     r13, rcx
0x180008df5  mov     r14d, ebx
0x180008df8  test    rdx, rdx
0x180008dfb  jz      loc_180009133
0x180008e01  test    r9, r9
0x180008e04  jz      loc_180009133
0x180008e0a  cmp     bx, [r9]
0x180008e0e  jz      loc_180009133
0x180008e14  cmp     [rbp+arg_20], rbx
0x180008e18  jz      loc_180009133
0x180008e1e  lea     rax, [rbp+cbData]
0x180008e22  xor     r8d, r8d; lpReserved
0x180008e25  mov     [r11-60h], rax
0x180008e29  lea     r9, [rbp+Type]; lpType
0x180008e2d  mov     rdx, r15; lpValueName
0x180008e30  mov     [r11-68h], rbx
0x180008e34  mov     rcx, rsi; hKey
0x180008e37  call    cs:__imp_RegQueryValueExW
0x180008e3d  test    eax, eax
0x180008e3f  jz      loc_180008F59
0x180008e45  lea     rcx, [rbp+Buffer]
0x180008e49  mov     [rsp+50h+Arguments], rbx; Arguments
0x180008e4e  mov     [rsp+50h+nSize], ebx; nSize
0x180008e52  xor     r9d, r9d; dwLanguageId
0x180008e55  mov     [rsp+50h+lpBuffer], rcx; lpBuffer
0x180008e5a  mov     r8d, eax; dwMessageId
0x180008e5d  mov     ecx, 1100h; dwFlags
0x180008e62  mov     qword ptr [rbp+Buffer], rbx
0x180008e66  xor     edx, edx; lpSource
0x180008e68  call    cs:__imp_FormatMessageW
0x180008e6e  mov     r15d, eax
0x180008e71  test    eax, eax
0x180008e73  jz      loc_180009133
0x180008e79  lea     esi, [rax+1]
0x180008e7c  lea     rcx, [rbx-1]
0x180008e80  lea     r13d, [rbx+2]
0x180008e84  mov     eax, r13d
0x180008e87  mul     rsi
0x180008e8a  cmovb   rax, rcx
0x180008e8e  mov     rcx, rax; unsigned __int64
0x180008e91  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008e96  mov     rdi, rax
0x180008e99  test    rax, rax
0x180008e9c  jz      short loc_180008F04
0x180008e9e  test    rsi, rsi
0x180008ea1  jz      short loc_180008EF5
0x180008ea3  cmp     rsi, 7FFFFFFFh
0x180008eaa  jbe     short loc_180008EB1
0x180008eac  mov     [rax], bx
0x180008eaf  jmp     short loc_180008EF5
0x180008eb1  mov     rcx, qword ptr [rbp+Buffer]
0x180008eb5  mov     eax, 7FFFFFFEh
0x180008eba  mov     rdx, rdi
0x180008ebd  mov     ebx, 1
0x180008ec2  test    rax, rax
0x180008ec5  jz      short loc_180008EE3
0x180008ec7  movzx   r8d, word ptr [rcx]
0x180008ecb  test    r8w, r8w
0x180008ecf  jz      short loc_180008EE3
0x180008ed1  mov     [rdx], r8w
0x180008ed5  add     rcx, r13
0x180008ed8  add     rdx, r13
0x180008edb  sub     rax, rbx
0x180008ede  sub     rsi, rbx
0x180008ee1  jnz     short loc_180008EC2
0x180008ee3  xor     ebx, ebx
0x180008ee5  lea     rcx, [rdx-2]
0x180008ee9  test    rsi, rsi
0x180008eec  cmovnz  rcx, rdx
0x180008ef0  mov     [rcx], bx
0x180008ef3  jnz     short loc_180008F04
0x180008ef5  mov     rcx, rdi
0x180008ef8  mov     r15d, ebx
0x180008efb  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008f01  mov     rdi, rbx
0x180008f04  mov     rcx, qword ptr [rbp+Buffer]; hMem
0x180008f08  call    cs:__imp_LocalFree
0x180008f0e  test    r15d, r15d
0x180008f11  jz      loc_180009133
0x180008f17  mov     rdx, [rbp+arg_10]
0x180008f1b  mov     r9, r12
0x180008f1e  mov     rcx, [rbp+arg_0]
0x180008f22  mov     qword ptr [rsp+50h+nSize], rdi
0x180008f27  mov     [rsp+50h+lpBuffer], rdx
0x180008f2c  xor     edx, edx
0x180008f2e  mov     rcx, [rcx+8]
0x180008f32  lea     r8d, [rdx+16h]
0x180008f36  mov     rax, [rcx]
0x180008f39  mov     rax, [rax+8]
0x180008f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f42  test    rdi, rdi
0x180008f45  jz      loc_180009133
0x180008f4b  mov     rcx, rdi
0x180008f4e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008f54  jmp     loc_180009133
0x180008f59  mov     ebx, 1
0x180008f5e  cmp     [rbp+Type], ebx
0x180008f61  jz      short loc_180008F88
0x180008f63  lea     r8d, [rbx+17h]
0x180008f67  mov     rcx, [r13+8]
0x180008f6b  xor     edx, edx
0x180008f6d  mov     r9, r12
0x180008f70  mov     [rsp+50h+lpBuffer], r15
0x180008f75  mov     rax, [rcx]
0x180008f78  mov     rax, [rax+8]
0x180008f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f81  xor     bl, bl
0x180008f83  jmp     loc_180009133
0x180008f88  mov     edi, [rbp+cbData]
0x180008f8b  test    edi, edi
0x180008f8d  jnz     short loc_180008F95
0x180008f8f  lea     r8d, [rdi+0Eh]
0x180008f93  jmp     short loc_180008F67
0x180008f95  shr     edi, 1
0x180008f97  mov     r13d, 2
0x180008f9d  mov     eax, r13d
0x180008fa0  lea     ecx, [rdi+1]
0x180008fa3  mul     rcx
0x180008fa6  lea     rcx, [r13-3]
0x180008faa  cmovb   rax, rcx
0x180008fae  mov     rcx, rax; unsigned __int64
0x180008fb1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008fb6  mov     r14, rax
0x180008fb9  xor     eax, eax
0x180008fbb  test    r14, r14
0x180008fbe  jnz     short loc_180008FC7
0x180008fc0  mov     bl, al
0x180008fc2  jmp     loc_180009133
0x180008fc7  mov     ecx, edi
0x180008fc9  lea     rax, [rbp+cbData]
0x180008fcd  mov     qword ptr [rsp+50h+nSize], rax; lpcbData
0x180008fd2  xor     edi, edi
0x180008fd4  xor     r9d, r9d; lpType
0x180008fd7  mov     [rsp+50h+lpBuffer], r14; lpData
0x180008fdc  xor     r8d, r8d; lpReserved
0x180008fdf  mov     rdx, r15; lpValueName
0x180008fe2  mov     [r14+rcx*2], di
0x180008fe7  mov     rcx, rsi; hKey
0x180008fea  call    cs:__imp_RegQueryValueExW
0x180008ff0  test    eax, eax
0x180008ff2  jz      loc_180009108
0x180008ff8  lea     rcx, [rbp+Buffer]
0x180008ffc  mov     [rsp+50h+Arguments], rdi; Arguments
0x180009001  mov     [rsp+50h+nSize], edi; nSize
0x180009005  xor     r9d, r9d; dwLanguageId
0x180009008  mov     [rsp+50h+lpBuffer], rcx; lpBuffer
0x18000900d  mov     r8d, eax; dwMessageId
0x180009010  mov     ecx, 1100h; dwFlags
0x180009015  mov     qword ptr [rbp+Buffer], rdi
0x180009019  xor     edx, edx; lpSource
0x18000901b  call    cs:__imp_FormatMessageW
0x180009021  mov     r15d, eax
0x180009024  test    eax, eax
0x180009026  jz      loc_1800090FA
0x18000902c  lea     esi, [rax+1]
0x18000902f  mov     rax, r13
0x180009032  mul     rsi
0x180009035  lea     rcx, [rdi-1]
0x180009039  cmovb   rax, rcx
0x18000903d  mov     rcx, rax; unsigned __int64
0x180009040  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009045  xor     r9d, r9d
0x180009048  mov     rdi, rax
0x18000904b  test    rax, rax
0x18000904e  jz      short loc_1800090B0
0x180009050  test    rsi, rsi
0x180009053  jz      short loc_1800090A2
0x180009055  cmp     rsi, 7FFFFFFFh
0x18000905c  jbe     short loc_180009064
0x18000905e  mov     [rax], r9w
0x180009062  jmp     short loc_1800090A2
0x180009064  mov     rcx, qword ptr [rbp+Buffer]
0x180009068  mov     eax, 7FFFFFFEh
0x18000906d  mov     rdx, rdi
0x180009070  test    rax, rax
0x180009073  jz      short loc_180009091
0x180009075  movzx   r8d, word ptr [rcx]
0x180009079  test    r8w, r8w
0x18000907d  jz      short loc_180009091
0x18000907f  mov     [rdx], r8w
0x180009083  add     rcx, r13
0x180009086  add     rdx, r13
0x180009089  sub     rax, rbx
0x18000908c  sub     rsi, rbx
0x18000908f  jnz     short loc_180009070
0x180009091  test    rsi, rsi
0x180009094  lea     rcx, [rdx-2]
0x180009098  cmovnz  rcx, rdx
0x18000909c  mov     [rcx], r9w
0x1800090a0  jnz     short loc_1800090B0
0x1800090a2  mov     rcx, rdi
0x1800090a5  mov     r15d, r9d
0x1800090a8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800090ae  xor     edi, edi
0x1800090b0  mov     rcx, qword ptr [rbp+Buffer]; hMem
0x1800090b4  call    cs:__imp_LocalFree
0x1800090ba  test    r15d, r15d
0x1800090bd  jz      short loc_1800090F8
0x1800090bf  mov     rdx, [rbp+arg_10]
0x1800090c3  mov     r9, r12
0x1800090c6  mov     rcx, [rbp+arg_0]
0x1800090ca  mov     qword ptr [rsp+50h+nSize], rdi
0x1800090cf  mov     [rsp+50h+lpBuffer], rdx
0x1800090d4  xor     edx, edx
0x1800090d6  mov     rcx, [rcx+8]
0x1800090da  lea     r8d, [rdx+16h]
0x1800090de  mov     rax, [rcx]
0x1800090e1  mov     rax, [rax+8]
0x1800090e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090ea  test    rdi, rdi
0x1800090ed  jz      short loc_1800090F8
0x1800090ef  mov     rcx, rdi
0x1800090f2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800090f8  xor     edi, edi
0x1800090fa  mov     rcx, r14
0x1800090fd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009103  mov     r14, rdi
0x180009106  jmp     short loc_180009130
0x180009108  cmp     di, [r14]
0x18000910c  jnz     short loc_180009133
0x18000910e  mov     rcx, [rbp+arg_0]
0x180009112  xor     edx, edx
0x180009114  mov     r9, r12
0x180009117  mov     [rsp+50h+lpBuffer], r15
0x18000911c  mov     rcx, [rcx+8]
0x180009120  lea     r8d, [rdx+0Eh]
0x180009124  mov     rax, [rcx]
0x180009127  mov     rax, [rax+8]
0x18000912b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009130  mov     bl, dil
0x180009133  mov     rax, [rbp+arg_20]
0x180009137  mov     [rax], r14
0x18000913a  mov     al, bl
0x18000913c  mov     rbx, [rsp+50h+arg_18]
0x180009144  add     rsp, 50h
0x180009148  pop     r15
0x18000914a  pop     r14
0x18000914c  pop     r13
0x18000914e  pop     r12
0x180009150  pop     rdi
0x180009151  pop     rsi
0x180009152  pop     rbp
0x180009153  retn
```
