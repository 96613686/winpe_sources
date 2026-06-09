# ColorDataController::FillProfile(ushort const *,Profile *)

- ea: `0x180011318`
- end: `0x18001150c`
- name: `?FillProfile@ColorDataController@@QEBAJPEBGPEAUProfile@@@Z`
- size: `500`
- prototype: `__int64 __fastcall(ColorDataController *__hidden this, const unsigned __int16 *, struct Profile *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d338`
- `0x18000f074`
- `0x180010780`
- `0x180011050`

## callees

- `0x180011318`
- `0x1800184ce`
- `0x180018500`

## import_xrefs

- `mscms!ColorCplReleaseProfileProperties` at `0x1800114dd`
- `mscms!ColorCplReleaseProfileProperties` at `0x1800114dd`
- `mscms!ColorCplGetProfileProperties` at `0x1800113d0`
- `mscms!ColorCplGetProfileProperties` at `0x1800113d0`

## pseudocode

```c
__int64 __fastcall ColorDataController::FillProfile(
        ColorDataController *this,
        const unsigned __int16 *a2,
        struct Profile *a3)
{
  __int64 v5; // rbp
  _WORD *v6; // r9
  __int64 v7; // rdi
  __int64 v8; // rax
  __int64 v9; // r8
  const unsigned __int16 *v10; // rcx
  _WORD *v11; // rdx
  unsigned int v12; // ebx
  int ProfileProperties; // eax
  __int16 v14; // dx
  unsigned int v15; // ecx
  _WORD *v16; // rcx
  _WORD *v17; // rax
  _WORD *v18; // rcx
  _WORD *v19; // rcx
  _DWORD v21[2]; // [rsp+20h] [rbp-E8h] BYREF
  int v22; // [rsp+28h] [rbp-E0h]
  _WORD *v23; // [rsp+50h] [rbp-B8h]
  _WORD *v24; // [rsp+58h] [rbp-B0h]
  unsigned int v25; // [rsp+98h] [rbp-70h]
  int v26; // [rsp+9Ch] [rbp-6Ch]
  int v27; // [rsp+A0h] [rbp-68h]

  memset_0(v21, 0, 0xA8u);
  v5 = 2147483646;
  v6 = (_WORD *)((char *)a3 + 532);
  v7 = 260;
  v8 = 2147483646;
  v9 = 260;
  v10 = a2;
  do
  {
    if ( !v8 )
      break;
    if ( !*v10 )
      break;
    *v6++ = *v10++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v6 - 1;
  v12 = v9 == 0 ? 0x8007007A : 0;
  if ( v9 )
    v11 = v6;
  *v11 = 0;
  if ( !v9 )
    goto LABEL_37;
  v21[0] = 1;
  v21[1] = 3608;
  ProfileProperties = ColorCplGetProfileProperties(a2, v21);
  v12 = ProfileProperties;
  if ( ProfileProperties < 0 )
  {
    if ( ProfileProperties == -2147022885 )
    {
      *((_DWORD *)a3 + 263) = 0;
      v12 = 0;
    }
    goto LABEL_37;
  }
  v14 = v22;
  if ( (v22 & 0x200) != 0 )
  {
    v15 = v25;
    *(_DWORD *)a3 = v25;
  }
  else
  {
    v15 = *(_DWORD *)a3;
  }
  if ( (v14 & 0x400) != 0 )
  {
    *((_DWORD *)a3 + 1) = v26;
  }
  else
  {
    if ( v15 > 1 )
      goto LABEL_24;
    *((_DWORD *)a3 + 1) = 5;
  }
  if ( !v15 )
  {
    if ( (v14 & 0x10) != 0 )
    {
      v16 = v24;
      if ( v24 )
      {
        v17 = (_WORD *)((char *)a3 + 12);
        do
        {
          if ( !v5 )
            break;
          if ( !*v16 )
            break;
          *v17++ = *v16++;
          --v5;
          --v7;
        }
        while ( v7 );
        goto LABEL_30;
      }
    }
LABEL_33:
    if ( (v14 & 0x800) != 0 )
      *((_DWORD *)a3 + 2) = v27;
    goto LABEL_37;
  }
LABEL_24:
  if ( (v14 & 8) == 0 )
    goto LABEL_33;
  v18 = v23;
  if ( !v23 )
    goto LABEL_33;
  v17 = (_WORD *)((char *)a3 + 12);
  do
  {
    if ( !v5 )
      break;
    if ( !*v18 )
      break;
    *v17++ = *v18++;
    --v5;
    --v7;
  }
  while ( v7 );
LABEL_30:
  v19 = v17 - 1;
  if ( v7 )
    v19 = v17;
  *v19 = 0;
  v12 = v7 == 0 ? 0x8007007A : 0;
  if ( v7 )
    goto LABEL_33;
LABEL_37:
  ColorCplReleaseProfileProperties(v21);
  return v12;
}

```

## disassembly

```asm
0x180011318  mov     [rsp+arg_0], rbx
0x18001131d  push    rbp
0x18001131e  push    rsi
0x18001131f  push    rdi
0x180011320  push    r14
0x180011322  push    r15
0x180011324  sub     rsp, 0E0h
0x18001132b  mov     rax, cs:__security_cookie
0x180011332  xor     rax, rsp
0x180011335  mov     [rsp+108h+var_38], rax
0x18001133d  mov     rsi, r8
0x180011340  lea     rcx, [rsp+108h+var_E8]; void *
0x180011345  mov     r14, rdx
0x180011348  mov     r8d, 0A8h; Size
0x18001134e  xor     edx, edx; Val
0x180011350  call    memset_0
0x180011355  mov     ebp, 7FFFFFFEh
0x18001135a  lea     r9, [rsi+214h]
0x180011361  mov     edi, 104h
0x180011366  mov     eax, ebp
0x180011368  mov     r8d, edi
0x18001136b  mov     rcx, r14
0x18001136e  xor     r15d, r15d
0x180011371  test    rax, rax
0x180011374  jz      short loc_180011393
0x180011376  movzx   edx, word ptr [rcx]
0x180011379  test    dx, dx
0x18001137c  jz      short loc_180011393
0x18001137e  mov     [r9], dx
0x180011382  add     rcx, 2
0x180011386  add     r9, 2
0x18001138a  dec     rax
0x18001138d  sub     r8, 1
0x180011391  jnz     short loc_180011371
0x180011393  mov     rax, r8
0x180011396  lea     rdx, [r9-2]
0x18001139a  neg     rax
0x18001139d  sbb     ebx, ebx
0x18001139f  not     ebx
0x1800113a1  and     ebx, 8007007Ah
0x1800113a7  test    r8, r8
0x1800113aa  cmovnz  rdx, r9
0x1800113ae  mov     [rdx], r15w
0x1800113b2  jz      loc_1800114D8
0x1800113b8  lea     rdx, [rsp+108h+var_E8]
0x1800113bd  mov     [rsp+108h+var_E8], 1
0x1800113c5  mov     rcx, r14
0x1800113c8  mov     [rsp+108h+var_E4], 0E18h
0x1800113d0  call    cs:__imp_ColorCplGetProfileProperties
0x1800113d6  mov     ebx, eax
0x1800113d8  test    eax, eax
0x1800113da  js      loc_1800114C7
0x1800113e0  mov     edx, [rsp+108h+var_E0]
0x1800113e4  bt      edx, 9
0x1800113e8  jnb     short loc_1800113F5
0x1800113ea  mov     ecx, [rsp+108h+var_70]
0x1800113f1  mov     [rsi], ecx
0x1800113f3  jmp     short loc_1800113F7
0x1800113f5  mov     ecx, [rsi]
0x1800113f7  bt      edx, 0Ah
0x1800113fb  jnb     short loc_180011409
0x1800113fd  mov     eax, [rsp+108h+var_6C]
0x180011404  mov     [rsi+4], eax
0x180011407  jmp     short loc_180011415
0x180011409  cmp     ecx, 1
0x18001140c  ja      short loc_18001145A
0x18001140e  mov     dword ptr [rsi+4], 5
0x180011415  test    ecx, ecx
0x180011417  jnz     short loc_18001145A
0x180011419  test    dl, 10h
0x18001141c  jz      loc_1800114B5
0x180011422  mov     rcx, [rsp+108h+var_B0]
0x180011427  test    rcx, rcx
0x18001142a  jz      loc_1800114B5
0x180011430  lea     rax, [rsi+0Ch]
0x180011434  test    rbp, rbp
0x180011437  jz      short loc_180011491
0x180011439  movzx   r8d, word ptr [rcx]
0x18001143d  test    r8w, r8w
0x180011441  jz      short loc_180011491
0x180011443  mov     [rax], r8w
0x180011447  add     rcx, 2
0x18001144b  add     rax, 2
0x18001144f  dec     rbp
0x180011452  sub     rdi, 1
0x180011456  jnz     short loc_180011434
0x180011458  jmp     short loc_180011491
0x18001145a  test    dl, 8
0x18001145d  jz      short loc_1800114B5
0x18001145f  mov     rcx, [rsp+108h+var_B8]
0x180011464  test    rcx, rcx
0x180011467  jz      short loc_1800114B5
0x180011469  lea     rax, [rsi+0Ch]
0x18001146d  test    rbp, rbp
0x180011470  jz      short loc_180011491
0x180011472  movzx   r8d, word ptr [rcx]
0x180011476  test    r8w, r8w
0x18001147a  jz      short loc_180011491
0x18001147c  mov     [rax], r8w
0x180011480  add     rcx, 2
0x180011484  add     rax, 2
0x180011488  dec     rbp
0x18001148b  sub     rdi, 1
0x18001148f  jnz     short loc_18001146D
0x180011491  test    rdi, rdi
0x180011494  lea     rcx, [rax-2]
0x180011498  cmovnz  rcx, rax
0x18001149c  mov     rax, rdi
0x18001149f  neg     rax
0x1800114a2  sbb     ebx, ebx
0x1800114a4  not     ebx
0x1800114a6  mov     [rcx], r15w
0x1800114aa  and     ebx, 8007007Ah
0x1800114b0  test    rdi, rdi
0x1800114b3  jz      short loc_1800114D8
0x1800114b5  bt      edx, 0Bh
0x1800114b9  jnb     short loc_1800114D8
0x1800114bb  mov     eax, [rsp+108h+var_68]
0x1800114c2  mov     [rsi+8], eax
0x1800114c5  jmp     short loc_1800114D8
0x1800114c7  cmp     eax, 800707DBh
0x1800114cc  jnz     short loc_1800114D8
0x1800114ce  mov     [rsi+41Ch], r15d
0x1800114d5  mov     ebx, r15d
0x1800114d8  lea     rcx, [rsp+108h+var_E8]
0x1800114dd  call    cs:__imp_ColorCplReleaseProfileProperties
0x1800114e3  mov     eax, ebx
0x1800114e5  mov     rcx, [rsp+108h+var_38]
0x1800114ed  xor     rcx, rsp; StackCookie
0x1800114f0  call    __security_check_cookie
0x1800114f5  mov     rbx, [rsp+108h+arg_0]
0x1800114fd  add     rsp, 0E0h
0x180011504  pop     r15
0x180011506  pop     r14
0x180011508  pop     rdi
0x180011509  pop     rsi
0x18001150a  pop     rbp
0x18001150b  retn
```
