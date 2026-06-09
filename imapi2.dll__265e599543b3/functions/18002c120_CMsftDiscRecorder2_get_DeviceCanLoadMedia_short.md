# CMsftDiscRecorder2::get_DeviceCanLoadMedia(short *)

- ea: `0x18002c120`
- end: `0x18002c3f2`
- name: `?get_DeviceCanLoadMedia@CMsftDiscRecorder2@@UEAAJPEAF@Z`
- size: `722`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1800140f4`
- `0x180014134`
- `0x180016778`
- `0x18002c120`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002c3c7`
- `ole32!CoTaskMemFree` at `0x18002c3d9`
- `ole32!CoTaskMemFree` at `0x18002c3c7`
- `ole32!CoTaskMemFree` at `0x18002c3d9`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::get_DeviceCanLoadMedia(CMsftDiscRecorder2 *this, __int16 *a2)
{
  _BYTE *v2; // r8
  int v4; // esi
  __int64 v5; // r9
  char *v6; // rbx
  __int16 v7; // di
  _BYTE *v8; // rdx
  unsigned int v9; // r9d
  PVOID *v10; // rcx
  LPVOID pv[2]; // [rsp+30h] [rbp-10h] BYREF
  int v13; // [rsp+78h] [rbp+38h] BYREF
  int v14; // [rsp+80h] [rbp+40h] BYREF
  _BYTE *v15; // [rsp+88h] [rbp+48h] BYREF

  v2 = 0;
  v15 = 0;
  v13 = 0;
  pv[0] = 0;
  v14 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 233, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v2 = v15;
    }
    v4 = -2147467261;
    goto LABEL_45;
  }
  *a2 = 0;
  v5 = *((unsigned int *)this + 60);
  if ( (v5 & 2) != 0 )
  {
    v6 = (char *)this + 8;
    v7 = 0;
    v4 = 0;
    (*(void (__fastcall **)(char *, __int64, _QWORD, _BYTE **, int *))(*((_QWORD *)this + 1) + 96LL))(
      (char *)this + 8,
      3,
      0,
      &v15,
      &v13);
    (*(void (__fastcall **)(char *, __int64, _QWORD, LPVOID *, int *))(*(_QWORD *)v6 + 104LL))(v6, 42, 0, pv, &v14);
    v2 = v15;
    if ( v15 )
      goto LABEL_14;
    v8 = pv[0];
    if ( pv[0] )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_23:
      if ( (v8[6] & 0xE0) == 0x20 )
        v7 = -1;
      goto LABEL_27;
    }
    v4 = -2147467259;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
    {
      goto LABEL_45;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 235, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, 2147500037LL);
    v2 = v15;
    if ( v15 )
    {
LABEL_14:
      v8 = pv[0];
      if ( !pv[0] )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_27;
      }
      v9 = *((unsigned __int8 *)pv[0] + 6);
      if ( (((unsigned __int8)v9 ^ v2[4]) & 0xE0) == 0 )
        goto LABEL_21;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
      {
LABEL_22:
        if ( v8 )
          goto LABEL_23;
LABEL_27:
        if ( v2 )
        {
          if ( (v2[4] & 0xE0) == 0x20 )
            v7 = -1;
          if ( (v2[2] & 0x3C) != 0 )
          {
            if ( (v2[4] & 0x10) != 0 )
            {
              v7 = -1;
            }
            else
            {
              if ( v7 == -1
                && v10 != &WPP_GLOBAL_Control
                && (*((_BYTE *)v10 + 188) & 4) != 0
                && *((_BYTE *)v10 + 185) >= 3u )
              {
                WPP_SF_(v10[22], 237, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
                v2 = v15;
              }
              v7 = 0;
            }
          }
        }
        if ( v4 >= 0 )
          *a2 = v7;
        goto LABEL_45;
      }
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        236,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        (unsigned __int8)v2[4] >> 5,
        v9 >> 5);
      v2 = v15;
    }
    v8 = pv[0];
LABEL_21:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  v4 = -2147467259;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 22),
      234,
      &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
      v5,
      -2147467259);
    v2 = v15;
  }
LABEL_45:
  CoTaskMemFree(v2);
  v15 = 0;
  CoTaskMemFree(pv[0]);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002c120  mov     [rsp-28h+arg_0], rbx
0x18002c125  push    rbp
0x18002c126  push    rsi
0x18002c127  push    rdi
0x18002c128  push    r12
0x18002c12a  push    r14
0x18002c12c  mov     rbp, rsp
0x18002c12f  sub     rsp, 40h
0x18002c133  xor     r8d, r8d
0x18002c136  mov     r14, rdx
0x18002c139  mov     [rbp+arg_18], r8
0x18002c13d  mov     [rbp+arg_8], r8d
0x18002c141  mov     [rbp+pv], r8
0x18002c145  mov     [rbp+arg_10], r8d
0x18002c149  test    rdx, rdx
0x18002c14c  jnz     short loc_18002C199
0x18002c14e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c155  lea     rbx, WPP_GLOBAL_Control
0x18002c15c  cmp     rcx, rbx
0x18002c15f  jz      short loc_18002C18F
0x18002c161  test    byte ptr [rcx+0BCh], 4
0x18002c168  jz      short loc_18002C18F
0x18002c16a  cmp     byte ptr [rcx+0B9h], 3
0x18002c171  jb      short loc_18002C18F
0x18002c173  mov     rcx, [rcx+0B0h]
0x18002c17a  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002c181  mov     edx, 0E9h
0x18002c186  call    WPP_SF_
0x18002c18b  mov     r8, [rbp+arg_18]
0x18002c18f  mov     esi, 80004003h
0x18002c194  jmp     loc_18002C3C4
0x18002c199  xor     eax, eax
0x18002c19b  mov     [rdx], ax
0x18002c19e  mov     r9d, [rcx+0F0h]
0x18002c1a5  test    r9b, 2
0x18002c1a9  jz      loc_18002C378
0x18002c1af  lea     rbx, [rcx+8]
0x18002c1b3  xor     edi, edi
0x18002c1b5  mov     rax, [rbx]
0x18002c1b8  lea     rcx, [rbp+arg_8]
0x18002c1bc  mov     [rsp+40h+var_20], rcx
0x18002c1c1  lea     r9, [rbp+arg_18]
0x18002c1c5  mov     rcx, rbx
0x18002c1c8  xor     esi, esi
0x18002c1ca  lea     edx, [rdi+3]
0x18002c1cd  mov     rax, [rax+60h]
0x18002c1d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1d6  mov     rax, [rbx]
0x18002c1d9  lea     rcx, [rbp+arg_10]
0x18002c1dd  mov     [rsp+40h+var_20], rcx
0x18002c1e2  lea     r9, [rbp+pv]
0x18002c1e6  xor     r8d, r8d
0x18002c1e9  lea     edx, [rdi+2Ah]
0x18002c1ec  mov     rcx, rbx
0x18002c1ef  mov     rax, [rax+68h]
0x18002c1f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1f8  mov     r8, [rbp+arg_18]
0x18002c1fc  lea     rbx, WPP_GLOBAL_Control
0x18002c203  or      r12d, 0FFFFFFFFh
0x18002c207  test    r8, r8
0x18002c20a  jnz     short loc_18002C26E
0x18002c20c  mov     rdx, [rbp+pv]
0x18002c210  test    rdx, rdx
0x18002c213  jnz     loc_18002C2F9
0x18002c219  mov     eax, 80004005h
0x18002c21e  mov     esi, eax
0x18002c220  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c227  cmp     rcx, rbx
0x18002c22a  jz      loc_18002C3C4
0x18002c230  test    byte ptr [rcx+0BCh], 4
0x18002c237  jz      loc_18002C3C4
0x18002c23d  cmp     byte ptr [rcx+0B9h], 3
0x18002c244  jb      loc_18002C3C4
0x18002c24a  mov     rcx, [rcx+0B0h]
0x18002c251  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002c258  mov     edx, 0EBh
0x18002c25d  mov     r9d, eax
0x18002c260  call    WPP_SF_d
0x18002c265  mov     r8, [rbp+arg_18]
0x18002c269  test    r8, r8
0x18002c26c  jz      short loc_18002C2DA
0x18002c26e  mov     rdx, [rbp+pv]
0x18002c272  test    rdx, rdx
0x18002c275  jz      loc_18002C302
0x18002c27b  movzx   r10d, byte ptr [r8+4]
0x18002c280  movzx   r9d, byte ptr [rdx+6]
0x18002c285  mov     al, r10b
0x18002c288  xor     al, r9b
0x18002c28b  test    al, 0E0h
0x18002c28d  jz      short loc_18002C2DE
0x18002c28f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c296  cmp     rcx, rbx
0x18002c299  jz      short loc_18002C2E5
0x18002c29b  test    byte ptr [rcx+0BCh], 4
0x18002c2a2  jz      short loc_18002C2E5
0x18002c2a4  cmp     byte ptr [rcx+0B9h], 3
0x18002c2ab  jb      short loc_18002C2E5
0x18002c2ad  mov     rcx, [rcx+0B0h]
0x18002c2b4  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002c2bb  mov     eax, r9d
0x18002c2be  mov     edx, 0ECh
0x18002c2c3  mov     r9d, r10d
0x18002c2c6  shr     eax, 5
0x18002c2c9  shr     r9d, 5
0x18002c2cd  mov     dword ptr [rsp+40h+var_20], eax
0x18002c2d1  call    WPP_SF_Dd
0x18002c2d6  mov     r8, [rbp+arg_18]
0x18002c2da  mov     rdx, [rbp+pv]
0x18002c2de  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2e5  test    rdx, rdx
0x18002c2e8  jz      short loc_18002C309
0x18002c2ea  mov     al, [rdx+6]
0x18002c2ed  and     al, 0E0h
0x18002c2ef  cmp     al, 20h ; ' '
0x18002c2f1  jnz     short loc_18002C309
0x18002c2f3  movzx   edi, r12w
0x18002c2f7  jmp     short loc_18002C309
0x18002c2f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c300  jmp     short loc_18002C2EA
0x18002c302  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c309  test    r8, r8
0x18002c30c  jz      short loc_18002C36E
0x18002c30e  mov     al, [r8+4]
0x18002c312  and     al, 0E0h
0x18002c314  cmp     al, 20h ; ' '
0x18002c316  jnz     short loc_18002C31C
0x18002c318  movzx   edi, r12w
0x18002c31c  test    byte ptr [r8+2], 3Ch
0x18002c321  jbe     short loc_18002C36E
0x18002c323  test    byte ptr [r8+4], 10h
0x18002c328  jz      short loc_18002C330
0x18002c32a  movzx   edi, r12w
0x18002c32e  jmp     short loc_18002C36E
0x18002c330  cmp     r12w, di
0x18002c334  jnz     short loc_18002C369
0x18002c336  cmp     rcx, rbx
0x18002c339  jz      short loc_18002C369
0x18002c33b  test    byte ptr [rcx+0BCh], 4
0x18002c342  jz      short loc_18002C369
0x18002c344  cmp     byte ptr [rcx+0B9h], 3
0x18002c34b  jb      short loc_18002C369
0x18002c34d  mov     rcx, [rcx+0B0h]
0x18002c354  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002c35b  mov     edx, 0EDh
0x18002c360  call    WPP_SF_
0x18002c365  mov     r8, [rbp+arg_18]
0x18002c369  xor     eax, eax
0x18002c36b  movzx   edi, ax
0x18002c36e  test    esi, esi
0x18002c370  js      short loc_18002C3C4
0x18002c372  mov     [r14], di
0x18002c376  jmp     short loc_18002C3C4
0x18002c378  mov     eax, 80004005h
0x18002c37d  mov     esi, eax
0x18002c37f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c386  lea     rbx, WPP_GLOBAL_Control
0x18002c38d  cmp     rcx, rbx
0x18002c390  jz      short loc_18002C3C4
0x18002c392  test    byte ptr [rcx+0BCh], 4
0x18002c399  jz      short loc_18002C3C4
0x18002c39b  cmp     byte ptr [rcx+0B9h], 3
0x18002c3a2  jb      short loc_18002C3C4
0x18002c3a4  mov     rcx, [rcx+0B0h]
0x18002c3ab  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002c3b2  mov     edx, 0EAh
0x18002c3b7  mov     dword ptr [rsp+40h+var_20], eax
0x18002c3bb  call    WPP_SF_Dd
0x18002c3c0  mov     r8, [rbp+arg_18]
0x18002c3c4  mov     rcx, r8; pv
0x18002c3c7  call    cs:__imp_CoTaskMemFree
0x18002c3cd  mov     rcx, [rbp+pv]; pv
0x18002c3d1  mov     [rbp+arg_18], 0
0x18002c3d9  call    cs:__imp_CoTaskMemFree
0x18002c3df  mov     rbx, [rsp+40h+arg_0]
0x18002c3e4  mov     eax, esi
0x18002c3e6  add     rsp, 40h
0x18002c3ea  pop     r14
0x18002c3ec  pop     r12
0x18002c3ee  pop     rdi
0x18002c3ef  pop     rsi
0x18002c3f0  pop     rbp
0x18002c3f1  retn
```
