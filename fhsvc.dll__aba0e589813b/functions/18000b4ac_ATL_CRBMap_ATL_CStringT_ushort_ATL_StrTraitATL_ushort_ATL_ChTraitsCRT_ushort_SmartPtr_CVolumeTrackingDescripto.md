# ATL::CRBMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Lookup(ushort const *,SmartPtr<CVolumeTrackingDescriptor> &)

- ea: `0x18000b4ac`
- end: `0x18000b5ad`
- name: `?Lookup@?$CRBMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@QEBA_NPEBGAEAV?$SmartPtr@VCVolumeTrackingDescriptor@@@@@Z`
- size: `257`
- prototype: `char __fastcall(__int64 **, unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a360`

## callees

- `0x18000b4ac`
- `0x18000b5b4`

## pseudocode

```c
char __fastcall ATL::CRBMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Lookup(
        __int64 **a1,
        unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 *v3; // rax
  __int64 *v5; // r11
  __int64 *v6; // rdx
  unsigned __int16 *v8; // rcx
  int v9; // r10d
  int v10; // r8d
  __int64 *v11; // rax
  __int64 *v12; // rcx
  __int64 *v13; // rax
  char v14; // r8
  unsigned __int16 *v15; // rcx
  int v16; // r10d
  int v17; // r8d

  v3 = *a1;
  v5 = a1[5];
  v6 = 0;
  while ( v3 != v5 )
  {
    if ( v6 )
      goto LABEL_13;
    v8 = a2;
    do
    {
      v9 = *(unsigned __int16 *)((char *)v8 + *v3 - (_QWORD)a2);
      v10 = *v8 - v9;
      if ( v10 )
        break;
      ++v8;
    }
    while ( v9 );
    if ( v10 )
    {
      if ( v10 >= 0 )
        v3 = (__int64 *)v3[4];
      else
        v3 = (__int64 *)v3[3];
    }
    else
    {
      v6 = v3;
    }
  }
  if ( !v6 )
    return 0;
  while ( 1 )
  {
LABEL_13:
    v11 = (__int64 *)v6[3];
    if ( v11 == v5 )
    {
      v12 = (__int64 *)v6[5];
      v13 = v6;
      while ( v12 != v5 )
      {
        if ( v13 != (__int64 *)v12[3] )
        {
          v14 = 0;
          goto LABEL_23;
        }
        v13 = v12;
        v12 = (__int64 *)v12[5];
      }
      v14 = 1;
LABEL_23:
      v11 = 0;
      if ( !v14 )
        v11 = v12;
    }
    else if ( v11 )
    {
      while ( (__int64 *)v11[4] != v5 )
        v11 = (__int64 *)v11[4];
    }
    if ( !v11 )
      break;
    v15 = a2;
    do
    {
      v16 = *(unsigned __int16 *)((char *)v15 + *v11 - (_QWORD)a2);
      v17 = *v15 - v16;
      if ( v17 )
        break;
      ++v15;
    }
    while ( v16 );
    if ( v17 )
      break;
    v6 = v11;
  }
  SmartPtr<CVolumeTrackingDescriptor>::operator=(a3, v6 + 1);
  return 1;
}

```

## disassembly

```asm
0x18000b4ac  mov     [rsp+arg_0], rbx
0x18000b4b1  push    rdi
0x18000b4b2  sub     rsp, 20h
0x18000b4b6  mov     rax, [rcx]
0x18000b4b9  mov     rbx, rdx
0x18000b4bc  mov     r11, [rcx+28h]
0x18000b4c0  xor     edx, edx
0x18000b4c2  mov     rdi, r8
0x18000b4c5  cmp     rax, r11
0x18000b4c8  jz      short loc_18000B507
0x18000b4ca  test    rdx, rdx
0x18000b4cd  jnz     short loc_18000B519
0x18000b4cf  mov     r9, [rax]
0x18000b4d2  mov     rcx, rbx
0x18000b4d5  sub     r9, rbx
0x18000b4d8  movzx   r8d, word ptr [rcx]
0x18000b4dc  movzx   r10d, word ptr [rcx+r9]
0x18000b4e1  sub     r8d, r10d
0x18000b4e4  jnz     short loc_18000B4EF
0x18000b4e6  add     rcx, 2
0x18000b4ea  test    r10d, r10d
0x18000b4ed  jnz     short loc_18000B4D8
0x18000b4ef  test    r8d, r8d
0x18000b4f2  jnz     short loc_18000B4F9
0x18000b4f4  mov     rdx, rax
0x18000b4f7  jmp     short loc_18000B4C5
0x18000b4f9  jns     short loc_18000B501
0x18000b4fb  mov     rax, [rax+18h]
0x18000b4ff  jmp     short loc_18000B4C5
0x18000b501  mov     rax, [rax+20h]
0x18000b505  jmp     short loc_18000B4C5
0x18000b507  test    rdx, rdx
0x18000b50a  jz      loc_18000B5A0
0x18000b510  test    rdx, rdx
0x18000b513  jz      loc_18000B5A0
0x18000b519  mov     rax, [rdx+18h]
0x18000b51d  cmp     rax, r11
0x18000b520  jz      short loc_18000B535
0x18000b522  test    rax, rax
0x18000b525  jz      short loc_18000B561
0x18000b527  mov     rcx, [rax+20h]
0x18000b52b  cmp     rcx, r11
0x18000b52e  jz      short loc_18000B561
0x18000b530  mov     rax, rcx
0x18000b533  jmp     short loc_18000B527
0x18000b535  mov     rcx, [rdx+28h]
0x18000b539  mov     rax, rdx
0x18000b53c  cmp     rcx, r11
0x18000b53f  jz      short loc_18000B555
0x18000b541  cmp     rax, [rcx+18h]
0x18000b545  jnz     short loc_18000B550
0x18000b547  mov     rax, rcx
0x18000b54a  mov     rcx, [rcx+28h]
0x18000b54e  jmp     short loc_18000B53C
0x18000b550  xor     r8b, r8b
0x18000b553  jmp     short loc_18000B558
0x18000b555  mov     r8b, 1
0x18000b558  xor     eax, eax
0x18000b55a  test    r8b, r8b
0x18000b55d  cmovz   rax, rcx
0x18000b561  test    rax, rax
0x18000b564  jz      short loc_18000B590
0x18000b566  mov     r9, [rax]
0x18000b569  mov     rcx, rbx
0x18000b56c  sub     r9, rbx
0x18000b56f  movzx   r8d, word ptr [rcx]
0x18000b573  movzx   r10d, word ptr [rcx+r9]
0x18000b578  sub     r8d, r10d
0x18000b57b  jnz     short loc_18000B586
0x18000b57d  add     rcx, 2
0x18000b581  test    r10d, r10d
0x18000b584  jnz     short loc_18000B56F
0x18000b586  test    r8d, r8d
0x18000b589  jnz     short loc_18000B590
0x18000b58b  mov     rdx, rax
0x18000b58e  jmp     short loc_18000B510
0x18000b590  add     rdx, 8
0x18000b594  mov     rcx, rdi
0x18000b597  call    ??4?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<CVolumeTrackingDescriptor>::operator=(SmartPtr<CVolumeTrackingDescriptor> const &)
0x18000b59c  mov     al, 1
0x18000b59e  jmp     short loc_18000B5A2
0x18000b5a0  xor     al, al
0x18000b5a2  mov     rbx, [rsp+28h+arg_0]
0x18000b5a7  add     rsp, 20h
0x18000b5ab  pop     rdi
0x18000b5ac  retn
```
