# CSimpleDataTableCache::SetupMeta(ulong,ulong,__MIDL___MIDL_itf_stable_0000_0000_0001 *)

- ea: `0x180054bd0`
- end: `0x180054e7f`
- name: `?SetupMeta@CSimpleDataTableCache@@IEAAJKKPEAU__MIDL___MIDL_itf_stable_0000_0000_0001@@@Z`
- size: `687`
- prototype: `__int64 __fastcall(CSimpleDataTableCache *this, int, unsigned int, struct __MIDL___MIDL_itf_stable_0000_0000_0001 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800547cc`

## callees

- `0x180054bd0`
- `0x18005582e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054c14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054c44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054e4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054c14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054c44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054e4d`

## pseudocode

```c
__int64 __fastcall CSimpleDataTableCache::SetupMeta(
        CSimpleDataTableCache *this,
        int a2,
        unsigned int a3,
        struct __MIDL___MIDL_itf_stable_0000_0000_0001 *a4)
{
  void *v7; // rax
  _WORD *v8; // rax
  _WORD *v9; // rdx
  int *v10; // r8
  unsigned int v11; // edi
  unsigned int v12; // r11d
  unsigned int v13; // r9d
  __int64 v14; // rcx
  int v15; // esi
  int v16; // r10d
  bool v17; // zf
  int v18; // ecx
  __int16 v19; // ax
  __int64 v20; // r8
  __int16 v21; // ax
  __int16 v22; // dx
  LPVOID v23; // rax

  if ( *((_DWORD *)this + 10) )
    return 2148599813LL;
  if ( a3 >= 0x8000 )
    return 2147942487LL;
  *(_DWORD *)this = a2;
  *((_DWORD *)this + 1) = a3;
  v7 = CoTaskMemAlloc(12LL * a3);
  *((_QWORD *)this + 3) = v7;
  if ( !v7 )
    return 2147942414LL;
  memcpy_0(v7, a4, 12LL * *((unsigned int *)this + 1));
  v8 = CoTaskMemAlloc(8LL * *((unsigned int *)this + 1));
  *((_QWORD *)this + 4) = v8;
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  v10 = (int *)*((_QWORD *)this + 3);
  v11 = 0;
  v12 = 0;
  *((_DWORD *)this + 2) = 0;
  v13 = 0;
  v14 = (__int64)v8;
  v15 = 0;
  while ( v12 < *((_DWORD *)this + 1) )
  {
    v16 = *v10;
    if ( *v10 == 19 )
    {
      v17 = v10[1] == 4;
    }
    else
    {
      if ( *v10 != 72 )
      {
        if ( *v10 == 128 || *v10 == 130 )
        {
          if ( !v10[1] )
            return 2148599814LL;
          goto LABEL_19;
        }
        if ( *v10 != 135 )
          goto LABEL_19;
      }
      v17 = v10[1] == 16;
    }
    if ( !v17 )
      return 2148599814LL;
LABEL_19:
    v18 = v10[2];
    if ( (v18 & 0xFFFFFFC0) != 0 )
      return 2148599814LL;
    if ( v16 == 19 || v16 == 72 || v16 == 135 )
    {
      if ( (v18 & 4) != 0 )
        return 2148599814LL;
      v18 |= 4u;
      v10[2] = v18;
    }
    if ( ((v16 - 128) & 0xFFFFFFFD) == 0 && (v18 & 4) == 0 )
    {
      v18 |= 0x40000u;
      v10[2] = v18;
    }
    if ( (v18 & 1) != 0 )
    {
      v18 |= 2u;
      v15 = 1;
      v10[2] = v18;
    }
    if ( (v18 & 6) == 4 )
    {
      v18 |= 0x80000u;
      v10[2] = v18;
    }
    if ( v16 == 128 && (v18 & 4) == 0 )
    {
      v10[2] = v18 | 0x20000;
      ++*((_DWORD *)this + 2);
    }
    if ( v12 > 0xFFFF )
    {
      *v9 = -1;
      return 2147942934LL;
    }
    *v9 = v12;
    if ( (v10[2] & 0x20000) != 0 )
      v19 = *((_DWORD *)this + 2) - 1;
    else
      v19 = -1;
    v9[1] = v19;
    *((_DWORD *)v9 + 1) = v13 >> 2;
    if ( (v10[2] & 0x40000) != 0 )
    {
      ++v11;
      v13 += 4;
    }
    else
    {
      v13 += (v10[1] + 3) & 0xFFFFFFFC;
    }
    v10 = (int *)(*((_QWORD *)this + 3) + 12LL * ++v12);
    v14 = *((_QWORD *)this + 4);
    v9 = (_WORD *)(v14 + 8LL * v12);
  }
  if ( !v15 )
    return 2148599814LL;
  *((_DWORD *)this + 3) = (v12 + 3) >> 2;
  if ( (v13 & 3) != 0 )
    return 2147549183LL;
  LODWORD(v20) = 0;
  *((_DWORD *)this + 4) = v13 >> 2;
  if ( *((_DWORD *)this + 1) )
  {
    do
    {
      v21 = *(_WORD *)(v14 + 2);
      if ( v21 == -1 )
        v22 = 0;
      else
        v22 = *((_WORD *)this + 6);
      v20 = (unsigned int)(v20 + 1);
      *(_WORD *)(v14 + 2) = v22 + v21;
      *(_DWORD *)(v14 + 4) += (unsigned __int16)(*((_WORD *)this + 4) + *((_WORD *)this + 6));
      v14 = *((_QWORD *)this + 4) + 8 * v20;
    }
    while ( (unsigned int)v20 < *((_DWORD *)this + 1) );
  }
  if ( !v11 || *((_QWORD *)this + 16) )
  {
LABEL_57:
    *((_DWORD *)this + 10) = 1;
    return 0;
  }
  else
  {
    v23 = CoTaskMemAlloc(saturated_mul(v11, 0x10u));
    *((_QWORD *)this + 16) = v23;
    if ( v23 )
    {
      *((_DWORD *)this + 34) = v11;
      goto LABEL_57;
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180054bd0  push    rbx
0x180054bd2  push    rsi
0x180054bd3  push    rdi
0x180054bd4  push    r12
0x180054bd6  sub     rsp, 28h
0x180054bda  cmp     dword ptr [rcx+28h], 0
0x180054bde  mov     rdi, r9
0x180054be1  mov     rbx, rcx
0x180054be4  jz      short loc_180054BF0
0x180054be6  mov     eax, 80110805h
0x180054beb  jmp     loc_180054E75
0x180054bf0  cmp     r8d, 8000h
0x180054bf7  jb      short loc_180054C03
0x180054bf9  mov     eax, 80070057h
0x180054bfe  jmp     loc_180054E75
0x180054c03  mov     [rcx], edx
0x180054c05  mov     [rcx+4], r8d
0x180054c09  mov     eax, r8d
0x180054c0c  lea     rcx, [rax+rax*2]
0x180054c10  shl     rcx, 2; cb
0x180054c14  call    cs:__imp_CoTaskMemAlloc
0x180054c1a  mov     [rbx+18h], rax
0x180054c1e  test    rax, rax
0x180054c21  jz      loc_180054E70
0x180054c27  mov     ecx, [rbx+4]
0x180054c2a  mov     rdx, rdi; Src
0x180054c2d  lea     r8, [rcx+rcx*2]
0x180054c31  mov     rcx, rax; void *
0x180054c34  shl     r8, 2; Size
0x180054c38  call    memcpy_0
0x180054c3d  mov     ecx, [rbx+4]
0x180054c40  shl     rcx, 3; cb
0x180054c44  call    cs:__imp_CoTaskMemAlloc
0x180054c4a  mov     [rbx+20h], rax
0x180054c4e  mov     rdx, rax
0x180054c51  test    rax, rax
0x180054c54  jz      loc_180054E70
0x180054c5a  mov     r8, [rbx+18h]
0x180054c5e  xor     edi, edi
0x180054c60  xor     r11d, r11d
0x180054c63  mov     [rbx+8], edi
0x180054c66  xor     r9d, r9d
0x180054c69  mov     rcx, rax
0x180054c6c  xor     esi, esi
0x180054c6e  mov     r12d, 0FFFFh
0x180054c74  cmp     r11d, [rbx+4]
0x180054c78  jnb     loc_180054DB6
0x180054c7e  mov     r10d, [r8]
0x180054c81  mov     eax, r10d
0x180054c84  sub     eax, 13h
0x180054c87  jz      short loc_180054CB1
0x180054c89  sub     eax, 35h ; '5'
0x180054c8c  jz      short loc_180054C9D
0x180054c8e  sub     eax, 38h ; '8'
0x180054c91  jz      short loc_180054CA4
0x180054c93  sub     eax, 2
0x180054c96  jz      short loc_180054CA4
0x180054c98  cmp     eax, 5
0x180054c9b  jnz     short loc_180054CBC
0x180054c9d  cmp     dword ptr [r8+4], 10h
0x180054ca2  jmp     short loc_180054CB6
0x180054ca4  cmp     dword ptr [r8+4], 0
0x180054ca9  jz      loc_180054DBA
0x180054caf  jmp     short loc_180054CBC
0x180054cb1  cmp     dword ptr [r8+4], 4
0x180054cb6  jnz     loc_180054DBA
0x180054cbc  mov     ecx, [r8+8]
0x180054cc0  test    ecx, 0FFFFFFC0h
0x180054cc6  jnz     loc_180054DBA
0x180054ccc  cmp     r10d, 13h
0x180054cd0  jz      short loc_180054CE1
0x180054cd2  cmp     r10d, 48h ; 'H'
0x180054cd6  jz      short loc_180054CE1
0x180054cd8  cmp     r10d, 87h
0x180054cdf  jnz     short loc_180054CF1
0x180054ce1  test    cl, 4
0x180054ce4  jnz     loc_180054DBA
0x180054cea  or      ecx, 4
0x180054ced  mov     [r8+8], ecx
0x180054cf1  lea     eax, [r10-80h]
0x180054cf5  test    eax, 0FFFFFFFDh
0x180054cfa  jnz     short loc_180054D09
0x180054cfc  test    cl, 4
0x180054cff  jnz     short loc_180054D09
0x180054d01  bts     ecx, 12h
0x180054d05  mov     [r8+8], ecx
0x180054d09  test    cl, 1
0x180054d0c  jz      short loc_180054D1A
0x180054d0e  or      ecx, 2
0x180054d11  mov     esi, 1
0x180054d16  mov     [r8+8], ecx
0x180054d1a  mov     eax, ecx
0x180054d1c  and     al, 6
0x180054d1e  cmp     al, 4
0x180054d20  jnz     short loc_180054D2A
0x180054d22  bts     ecx, 13h
0x180054d26  mov     [r8+8], ecx
0x180054d2a  cmp     r10d, 80h
0x180054d31  jnz     short loc_180054D43
0x180054d33  test    cl, 4
0x180054d36  jnz     short loc_180054D43
0x180054d38  bts     ecx, 11h
0x180054d3c  mov     [r8+8], ecx
0x180054d40  inc     dword ptr [rbx+8]
0x180054d43  cmp     r11d, r12d
0x180054d46  ja      short loc_180054DA8
0x180054d48  mov     [rdx], r11w
0x180054d4c  test    dword ptr [r8+8], 20000h
0x180054d54  jz      short loc_180054D5D
0x180054d56  mov     eax, [rbx+8]
0x180054d59  dec     eax
0x180054d5b  jmp     short loc_180054D60
0x180054d5d  or      eax, 0FFFFFFFFh
0x180054d60  mov     [rdx+2], ax
0x180054d64  mov     eax, r9d
0x180054d67  shr     eax, 2
0x180054d6a  mov     [rdx+4], eax
0x180054d6d  test    dword ptr [r8+8], 40000h
0x180054d75  jz      short loc_180054D7F
0x180054d77  inc     edi
0x180054d79  add     r9d, 4
0x180054d7d  jmp     short loc_180054D8C
0x180054d7f  mov     eax, [r8+4]
0x180054d83  add     eax, 3
0x180054d86  and     eax, 0FFFFFFFCh
0x180054d89  add     r9d, eax
0x180054d8c  mov     rax, [rbx+18h]
0x180054d90  inc     r11d
0x180054d93  lea     rcx, [r11+r11*2]
0x180054d97  lea     r8, [rax+rcx*4]
0x180054d9b  mov     rcx, [rbx+20h]
0x180054d9f  lea     rdx, [rcx+r11*8]
0x180054da3  jmp     loc_180054C74
0x180054da8  mov     [rdx], r12w
0x180054dac  mov     eax, 80070216h
0x180054db1  jmp     loc_180054E75
0x180054db6  test    esi, esi
0x180054db8  jnz     short loc_180054DC4
0x180054dba  mov     eax, 80110806h
0x180054dbf  jmp     loc_180054E75
0x180054dc4  lea     eax, [r11+3]
0x180054dc8  shr     eax, 2
0x180054dcb  mov     [rbx+0Ch], eax
0x180054dce  test    r9b, 3
0x180054dd2  jz      short loc_180054DDE
0x180054dd4  mov     eax, 8000FFFFh
0x180054dd9  jmp     loc_180054E75
0x180054dde  shr     r9d, 2
0x180054de2  xor     r8d, r8d
0x180054de5  mov     [rbx+10h], r9d
0x180054de9  cmp     [rbx+4], r8d
0x180054ded  jbe     short loc_180054E27
0x180054def  movzx   eax, word ptr [rcx+2]
0x180054df3  cmp     r12w, ax
0x180054df7  jnz     short loc_180054DFD
0x180054df9  xor     edx, edx
0x180054dfb  jmp     short loc_180054E01
0x180054dfd  movzx   edx, word ptr [rbx+0Ch]
0x180054e01  add     ax, dx
0x180054e04  inc     r8d
0x180054e07  mov     [rcx+2], ax
0x180054e0b  movzx   eax, word ptr [rbx+0Ch]
0x180054e0f  add     ax, [rbx+8]
0x180054e13  movzx   eax, ax
0x180054e16  add     [rcx+4], eax
0x180054e19  mov     rcx, [rbx+20h]
0x180054e1d  lea     rcx, [rcx+r8*8]
0x180054e21  cmp     r8d, [rbx+4]
0x180054e25  jb      short loc_180054DEF
0x180054e27  test    edi, edi
0x180054e29  jz      short loc_180054E65
0x180054e2b  cmp     qword ptr [rbx+80h], 0
0x180054e33  jnz     short loc_180054E65
0x180054e35  mov     ecx, edi
0x180054e37  mov     eax, 10h
0x180054e3c  mul     rcx
0x180054e3f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180054e46  cmovb   rax, rcx
0x180054e4a  mov     rcx, rax; cb
0x180054e4d  call    cs:__imp_CoTaskMemAlloc
0x180054e53  mov     [rbx+80h], rax
0x180054e5a  test    rax, rax
0x180054e5d  jz      short loc_180054E70
0x180054e5f  mov     [rbx+88h], edi
0x180054e65  mov     dword ptr [rbx+28h], 1
0x180054e6c  xor     eax, eax
0x180054e6e  jmp     short loc_180054E75
0x180054e70  mov     eax, 8007000Eh
0x180054e75  add     rsp, 28h
0x180054e79  pop     r12
0x180054e7b  pop     rdi
0x180054e7c  pop     rsi
0x180054e7d  pop     rbx
0x180054e7e  retn
```
