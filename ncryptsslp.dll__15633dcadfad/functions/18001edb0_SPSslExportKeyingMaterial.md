# SPSslExportKeyingMaterial

- ea: `0x18001edb0`
- end: `0x18001f172`
- name: `SPSslExportKeyingMaterial`
- size: `962`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x1800068e0`
- `0x180007960`
- `0x180008810`
- `0x180009160`
- `0x18000b654`
- `0x18000e7f0`
- `0x180014760`
- `0x180018ac0`
- `0x18001edb0`
- `0x180020718`
- `0x180024ef0`
- `0x180024fb0`
- `0x180026010`

## string_xrefs

- `0x18001ef12`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18001f107`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslExportKeyingMaterial(
        __int64 a1,
        __int64 a2,
        const char *a3,
        size_t *a4,
        int a5,
        void *Src,
        unsigned __int16 a7,
        __int64 a8,
        unsigned int a9,
        int a10)
{
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // r13
  size_t *v16; // rdi
  unsigned __int64 v17; // r15
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned int v20; // ebx
  __int64 v21; // rcx
  void *v22; // r8
  __int64 v23; // r9
  __int64 v24; // rdx
  int v25; // eax
  int v26; // ecx
  unsigned __int64 v27; // rcx
  __int64 v28; // rcx
  unsigned __int64 v29; // rcx
  void *v30; // rsp
  void *v31; // rsp
  size_t *v32; // rax
  int v33; // eax
  __int64 v34; // rax
  size_t *v35; // rcx
  __int64 v37; // [rsp+0h] [rbp-60h] BYREF
  __int64 v38; // [rsp+60h] [rbp+0h] BYREF
  size_t v39; // [rsp+68h] [rbp+8h] BYREF

  v38 = SslpValidateProvHandle(a1);
  v13 = SslpValidateKeyHandle(v12);
  v15 = SslpValidateMasterKeyHandle(v14);
  v16 = 0;
  LODWORD(v17) = 0;
  if ( !v18 )
  {
    v19 = 564;
LABEL_3:
    v20 = -2146893786;
    v21 = 2148073510LL;
    goto LABEL_50;
  }
  if ( !a3
    || (v39 = strnlen(a3, 0xFFFFu), (_DWORD)v39 == 0xFFFF)
    || (v22 = Src, v23 = 0, !Src) && a7
    || !a8
    || (v24 = a9, a9 - 1 > 0xFFFE) )
  {
    v19 = 573;
    goto LABEL_49;
  }
  if ( a10 )
  {
    v20 = -2146893815;
    v19 = 580;
    v21 = 2148073481LL;
    goto LABEL_50;
  }
  if ( !v13 || *(_DWORD *)(v13 + 108) != 6 )
  {
    if ( !v15 )
    {
      v19 = 702;
      goto LABEL_3;
    }
    v26 = *(_DWORD *)(v15 + 8);
    if ( v26 != 65277 && (unsigned int)(v26 - 769) > 2 && v26 != 65279 )
    {
      v19 = 638;
      goto LABEL_16;
    }
    if ( a4 && a5 == 64 )
    {
      if ( a7 )
      {
        v17 = (unsigned int)a7 + 66;
        if ( v17 > g_ulMaxStackAllocSize )
          goto LABEL_60;
        v27 = v17 + g_ulAdditionalProbeSize + 8;
        if ( v27 < v17 || !(unsigned int)VerifyStackAvailable(v27) )
          goto LABEL_60;
        v28 = v17 + 23;
        if ( v17 + 23 <= v17 + 8 )
          v28 = 0xFFFFFFFFFFFFFF0LL;
        v29 = v28 & 0xFFFFFFFFFFFFFFF0uLL;
        v30 = alloca(v29);
        v31 = alloca(v29);
        v16 = (size_t *)&v38;
        if ( &v37 == (__int64 *)-96LL || (LODWORD(v38) = 1801679955, (v16 = &v39) == 0) )
        {
LABEL_60:
          if ( v17 + 8 >= (unsigned int)v17 )
          {
            v32 = (size_t *)((__int64 (__fastcall *)(unsigned __int64, __int64, void *, __int64))g_pfnAllocate)(
                              v17 + 8,
                              v24,
                              v22,
                              v23);
            v16 = v32;
            if ( v32 )
            {
              *(_DWORD *)v32 = 1885431112;
              v16 = v32 + 1;
            }
          }
        }
        if ( !v16 )
        {
          v20 = -2146893810;
          v19 = 661;
          v21 = 2148073486LL;
          goto LABEL_50;
        }
        *(_OWORD *)v16 = *(_OWORD *)a4;
        *((_OWORD *)v16 + 1) = *((_OWORD *)a4 + 1);
        *((_OWORD *)v16 + 2) = *((_OWORD *)a4 + 2);
        *((_OWORD *)v16 + 3) = *((_OWORD *)a4 + 3);
        *((_BYTE *)v16 + 64) = HIBYTE(a7);
        *((_BYTE *)v16 + 65) = a7;
        memmove((char *)v16 + 66, Src, a7);
      }
      else
      {
        LODWORD(v17) = 64;
        v16 = a4;
      }
      v33 = Tls1Prf(
              *(_DWORD *)(v15 + 8),
              *(const WCHAR **)(*(_QWORD *)(v15 + 16) + 104LL),
              *(_QWORD *)(*(_QWORD *)(v15 + 16) + 136LL),
              (UCHAR *)(v15 + 28),
              0x30u,
              (__int64)a3,
              v39,
              (__int64)v16,
              v17,
              a8,
              a9);
      v20 = v33;
      if ( v33 >= 0 )
        goto LABEL_51;
      v19 = 694;
      v21 = (unsigned int)v33;
LABEL_50:
      DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v19);
LABEL_51:
      if ( v16 != a4 )
      {
        v34 = (unsigned int)v17;
        v35 = v16;
        if ( (_DWORD)v17 )
        {
          do
          {
            *(_BYTE *)v35 = 0;
            v35 = (size_t *)((char *)v35 + 1);
            --v34;
          }
          while ( v34 );
        }
        if ( v16 && *((_DWORD *)v16 - 2) == 1885431112 )
          ((void (*)(void))g_pfnFree)();
      }
      return v20;
    }
    v19 = 645;
LABEL_49:
    v20 = -2146893785;
    v21 = 2148073511LL;
    goto LABEL_50;
  }
  if ( *(_DWORD *)(v13 + 8) != 772 )
  {
    v19 = 594;
LABEL_16:
    v20 = -2146893783;
    v21 = 2148073513LL;
    goto LABEL_50;
  }
  if ( a4 || a5 )
  {
    v19 = 605;
    goto LABEL_49;
  }
  v25 = TlsExportKeyingMaterial(v38, v13, (_DWORD)a3, (_DWORD)Src, a7, a8, a9);
  v20 = v25;
  if ( v25 < 0 )
    DebugTraceError((unsigned int)v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 619);
  return v20;
}

```

## disassembly

```asm
0x18001edb0  push    rbp
0x18001edb2  push    rbx
0x18001edb3  push    rsi
0x18001edb4  push    rdi
0x18001edb5  push    r12
0x18001edb7  push    r13
0x18001edb9  push    r14
0x18001edbb  push    r15
0x18001edbd  sub     rsp, 88h
0x18001edc4  lea     rbp, [rsp+60h]
0x18001edc9  mov     rax, cs:__security_cookie
0x18001edd0  xor     rax, rbp
0x18001edd3  mov     [rbp+60h+var_50], rax
0x18001edd7  mov     r14, r9
0x18001edda  mov     r12, r8
0x18001eddd  call    SslpValidateProvHandle
0x18001ede2  mov     rcx, rdx
0x18001ede5  mov     [rbp+60h+var_60], rax
0x18001ede9  mov     r8, rax
0x18001edec  call    SslpValidateKeyHandle
0x18001edf1  mov     rbx, rax
0x18001edf4  call    SslpValidateMasterKeyHandle
0x18001edf9  mov     r13, rax
0x18001edfc  xor     eax, eax
0x18001edfe  mov     edi, eax
0x18001ee00  mov     r15d, eax
0x18001ee03  test    r8, r8
0x18001ee06  jnz     short loc_18001EE1D
0x18001ee08  mov     r9d, 234h
0x18001ee0e  mov     ebx, 80090026h
0x18001ee13  mov     ecx, 80090026h
0x18001ee18  jmp     loc_18001F107
0x18001ee1d  test    r12, r12
0x18001ee20  jz      loc_18001F0F7
0x18001ee26  mov     esi, 0FFFFh
0x18001ee2b  mov     rcx, r12; String
0x18001ee2e  mov     edx, esi; MaxCount
0x18001ee30  call    strnlen
0x18001ee35  mov     [rbp+60h+var_58], rax
0x18001ee39  cmp     eax, esi
0x18001ee3b  jz      loc_18001F0F7
0x18001ee41  mov     r8, [rbp+60h+Src]
0x18001ee48  xor     r9d, r9d
0x18001ee4b  movzx   esi, [rbp+60h+arg_30]
0x18001ee52  test    r8, r8
0x18001ee55  jnz     short loc_18001EE60
0x18001ee57  test    si, si
0x18001ee5a  jnz     loc_18001F0F7
0x18001ee60  mov     rcx, [rbp+60h+arg_38]
0x18001ee67  test    rcx, rcx
0x18001ee6a  jz      loc_18001F0F7
0x18001ee70  mov     edx, [rbp+60h+arg_40]
0x18001ee76  lea     eax, [rdx-1]
0x18001ee79  cmp     eax, 0FFFEh
0x18001ee7e  ja      loc_18001F0F7
0x18001ee84  cmp     [rbp+60h+arg_48], r9d
0x18001ee8b  jz      short loc_18001EEA2
0x18001ee8d  mov     ebx, 80090009h
0x18001ee92  mov     r9d, 244h
0x18001ee98  mov     ecx, 80090009h
0x18001ee9d  jmp     loc_18001F107
0x18001eea2  test    rbx, rbx
0x18001eea5  jz      loc_18001EF37
0x18001eeab  cmp     dword ptr [rbx+6Ch], 6
0x18001eeaf  jnz     loc_18001EF37
0x18001eeb5  cmp     dword ptr [rbx+8], 304h
0x18001eebc  jz      short loc_18001EED3
0x18001eebe  mov     r9d, 252h
0x18001eec4  mov     ebx, 80090029h
0x18001eec9  mov     ecx, 80090029h
0x18001eece  jmp     loc_18001F107
0x18001eed3  test    r14, r14
0x18001eed6  jnz     short loc_18001EF2C
0x18001eed8  cmp     [rbp+60h+arg_20], r9d
0x18001eedf  jnz     short loc_18001EF2C
0x18001eee1  mov     word ptr [rsp+0C0h+var_90], dx
0x18001eee6  mov     r9, r8
0x18001eee9  mov     [rsp+0C0h+var_98], rcx
0x18001eeee  mov     r8, r12
0x18001eef1  mov     rcx, [rbp+60h+var_60]
0x18001eef5  mov     rdx, rbx
0x18001eef8  mov     word ptr [rsp+0C0h+var_A0], si
0x18001eefd  call    TlsExportKeyingMaterial
0x18001ef02  mov     ebx, eax
0x18001ef04  test    eax, eax
0x18001ef06  jns     loc_18001F153
0x18001ef0c  mov     r9d, 26Bh
0x18001ef12  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ef19  lea     rdx, aStatus; "Status"
0x18001ef20  mov     ecx, eax
0x18001ef22  call    DebugTraceError
0x18001ef27  jmp     loc_18001F153
0x18001ef2c  mov     r9d, 25Dh
0x18001ef32  jmp     loc_18001F0FD
0x18001ef37  test    r13, r13
0x18001ef3a  jz      loc_18001F0EC
0x18001ef40  mov     ecx, [r13+8]
0x18001ef44  cmp     ecx, 0FEFDh
0x18001ef4a  jz      short loc_18001EF6A
0x18001ef4c  lea     eax, [rcx-301h]
0x18001ef52  cmp     eax, 2
0x18001ef55  jbe     short loc_18001EF6A
0x18001ef57  cmp     ecx, 0FEFFh
0x18001ef5d  jz      short loc_18001EF6A
0x18001ef5f  mov     r9d, 27Eh
0x18001ef65  jmp     loc_18001EEC4
0x18001ef6a  test    r14, r14
0x18001ef6d  jz      loc_18001F0E4
0x18001ef73  cmp     [rbp+60h+arg_20], 40h ; '@'
0x18001ef7a  jnz     loc_18001F0E4
0x18001ef80  test    si, si
0x18001ef83  jz      loc_18001F07A
0x18001ef89  lea     r15d, [rsi+42h]
0x18001ef8d  mov     ebx, r15d
0x18001ef90  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18001ef97  ja      short loc_18001EFF1
0x18001ef99  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001efa0  add     rcx, 8
0x18001efa4  add     rcx, rbx
0x18001efa7  cmp     rcx, rbx
0x18001efaa  jb      short loc_18001EFF1
0x18001efac  call    VerifyStackAvailable
0x18001efb1  test    eax, eax
0x18001efb3  jz      short loc_18001EFF1
0x18001efb5  lea     rax, [r15+8]
0x18001efb9  lea     rcx, [rax+0Fh]
0x18001efbd  cmp     rcx, rax
0x18001efc0  ja      short loc_18001EFCC
0x18001efc2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001efcc  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001efd0  mov     rax, rcx
0x18001efd3  call    _alloca_probe
0x18001efd8  sub     rsp, rcx
0x18001efdb  lea     rdi, [rsp+0C0h+var_60]
0x18001efe0  test    rdi, rdi
0x18001efe3  jz      short loc_18001EFF1
0x18001efe5  mov     dword ptr [rdi], 6B637453h
0x18001efeb  add     rdi, 8
0x18001efef  jnz     short loc_18001F01B
0x18001eff1  mov     eax, r15d
0x18001eff4  lea     rcx, [r15+8]
0x18001eff8  cmp     rcx, rax
0x18001effb  jb      short loc_18001F01B
0x18001effd  mov     rax, cs:g_pfnAllocate
0x18001f004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f009  mov     rdi, rax
0x18001f00c  test    rax, rax
0x18001f00f  jz      short loc_18001F01B
0x18001f011  mov     dword ptr [rax], 70616548h
0x18001f017  add     rdi, 8
0x18001f01b  test    rdi, rdi
0x18001f01e  jnz     short loc_18001F035
0x18001f020  mov     ebx, 8009000Eh
0x18001f025  mov     r9d, 295h
0x18001f02b  mov     ecx, 8009000Eh
0x18001f030  jmp     loc_18001F107
0x18001f035  movups  xmm0, xmmword ptr [r14]
0x18001f039  mov     rdx, [rbp+60h+Src]; Src
0x18001f040  lea     rcx, [rdi+42h]; void *
0x18001f044  movzx   eax, si
0x18001f047  mov     r8, rsi; Size
0x18001f04a  movups  xmmword ptr [rdi], xmm0
0x18001f04d  shr     ax, 8
0x18001f051  movups  xmm1, xmmword ptr [r14+10h]
0x18001f056  movups  xmmword ptr [rdi+10h], xmm1
0x18001f05a  movups  xmm0, xmmword ptr [r14+20h]
0x18001f05f  movups  xmmword ptr [rdi+20h], xmm0
0x18001f063  movups  xmm1, xmmword ptr [r14+30h]
0x18001f068  movups  xmmword ptr [rdi+30h], xmm1
0x18001f06c  mov     [rdi+40h], al
0x18001f06f  mov     [rdi+41h], sil
0x18001f073  call    memmove
0x18001f078  jmp     short loc_18001F083
0x18001f07a  mov     r15d, 40h ; '@'
0x18001f080  mov     rdi, r14
0x18001f083  mov     rdx, [r13+10h]
0x18001f087  lea     r9, [r13+1Ch]
0x18001f08b  mov     eax, [rbp+60h+arg_40]
0x18001f091  mov     ecx, [r13+8]
0x18001f095  mov     [rsp+0C0h+var_70], eax
0x18001f099  mov     rax, [rbp+60h+arg_38]
0x18001f0a0  mov     r8, [rdx+88h]
0x18001f0a7  mov     rdx, [rdx+68h]
0x18001f0ab  mov     [rsp+0C0h+var_78], rax
0x18001f0b0  mov     rax, [rbp+60h+var_58]
0x18001f0b4  mov     [rsp+0C0h+var_80], r15d
0x18001f0b9  mov     [rsp+0C0h+var_88], rdi
0x18001f0be  mov     [rsp+0C0h+var_90], eax
0x18001f0c2  mov     [rsp+0C0h+var_98], r12
0x18001f0c7  mov     [rsp+0C0h+var_A0], 30h ; '0'
0x18001f0cf  call    Tls1Prf
0x18001f0d4  mov     ebx, eax
0x18001f0d6  test    eax, eax
0x18001f0d8  jns     short loc_18001F11A
0x18001f0da  mov     r9d, 2B6h
0x18001f0e0  mov     ecx, eax
0x18001f0e2  jmp     short loc_18001F107
0x18001f0e4  mov     r9d, 285h
0x18001f0ea  jmp     short loc_18001F0FD
0x18001f0ec  mov     r9d, 2BEh
0x18001f0f2  jmp     loc_18001EE0E
0x18001f0f7  mov     r9d, 23Dh
0x18001f0fd  mov     ebx, 80090027h
0x18001f102  mov     ecx, 80090027h
0x18001f107  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001f10e  lea     rdx, aStatus; "Status"
0x18001f115  call    DebugTraceError
0x18001f11a  cmp     rdi, r14
0x18001f11d  jz      short loc_18001F153
0x18001f11f  mov     eax, r15d
0x18001f122  mov     rcx, rdi
0x18001f125  test    r15d, r15d
0x18001f128  jz      short loc_18001F136
0x18001f12a  mov     byte ptr [rcx], 0
0x18001f12d  inc     rcx
0x18001f130  sub     rax, 1
0x18001f134  jnz     short loc_18001F12A
0x18001f136  test    rdi, rdi
0x18001f139  jz      short loc_18001F153
0x18001f13b  lea     rcx, [rdi-8]
0x18001f13f  cmp     dword ptr [rcx], 70616548h
0x18001f145  jnz     short loc_18001F153
0x18001f147  mov     rax, cs:g_pfnFree
0x18001f14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f153  mov     eax, ebx
0x18001f155  mov     rcx, [rbp+60h+var_50]
0x18001f159  xor     rcx, rbp; StackCookie
0x18001f15c  call    __security_check_cookie
0x18001f161  lea     rsp, [rbp+28h]
0x18001f165  pop     r15
0x18001f167  pop     r14
0x18001f169  pop     r13
0x18001f16b  pop     r12
0x18001f16d  pop     rdi
0x18001f16e  pop     rsi
0x18001f16f  pop     rbx
0x18001f170  pop     rbp
0x18001f171  retn
```
