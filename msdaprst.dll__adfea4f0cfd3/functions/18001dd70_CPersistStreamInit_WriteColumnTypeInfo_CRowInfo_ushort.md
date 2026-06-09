# CPersistStreamInit::WriteColumnTypeInfo(CRowInfo &,ushort)

- ea: `0x18001dd70`
- end: `0x18001e2e5`
- name: `?WriteColumnTypeInfo@CPersistStreamInit@@AEAAJAEAVCRowInfo@@G@Z`
- size: `1397`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *, unsigned __int16)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x18001d42c`

## callees

- `0x180003c38`
- `0x1800041b4`
- `0x180004224`
- `0x1800042f4`
- `0x180004338`
- `0x180004384`
- `0x1800158e0`
- `0x1800164dc`
- `0x18001c0a0`
- `0x18001d1c8`
- `0x18001dd70`
- `0x18001ed5c`
- `0x18001fe94`
- `0x180020204`
- `0x180020274`
- `0x180029c8c`
- `0x18002f0e0`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x18001e267`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18001e267`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistStreamInit::WriteColumnTypeInfo(
        CPersistStreamInit *this,
        struct CRowInfo *a2,
        unsigned __int16 a3)
{
  unsigned __int16 v6; // r15
  unsigned __int16 v7; // dx
  int v8; // ebx
  unsigned __int16 v9; // di
  int v10; // esi
  bool v11; // r9
  bool v12; // r9
  unsigned __int64 v13; // r9
  unsigned int Size; // edx
  bool v15; // r9
  unsigned int v16; // eax
  int v17; // ecx
  unsigned __int8 Scale; // al
  unsigned __int64 v19; // r9
  bool v20; // r9
  unsigned __int8 Precision; // al
  unsigned __int64 v22; // r9
  bool v23; // r9
  char v24; // bl
  unsigned __int16 *Name; // rax
  OLECHAR *v26; // r8
  int v28; // [rsp+20h] [rbp-E0h]
  unsigned int v29; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int Flags; // [rsp+34h] [rbp-CCh]
  _BYTE v31[8]; // [rsp+38h] [rbp-C8h] BYREF
  IErrorInfo *pperrinfo; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+48h] [rbp-B8h]
  __int64 v34; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v35[256]; // [rsp+60h] [rbp-A0h] BYREF

  v29 = 0;
  v6 = CMetaData::mdGetType(a2, a3) & 0xBFFF;
  Flags = CMetaData::mdGetFlags(a2, v7);
  if ( (v6 & 0xB000) != 0 )
    goto LABEL_86;
  if ( v6 > 0x40u )
  {
    v8 = 72;
    switch ( v6 )
    {
      case 0x48u:
        v8 = 89;
        goto LABEL_54;
      case 0x80u:
        v8 = 74;
        goto LABEL_54;
      case 0x81u:
        v8 = 75;
        v9 = 93;
        goto LABEL_55;
      case 0x82u:
        goto LABEL_50;
      case 0x83u:
        v8 = 76;
        v9 = 99;
        goto LABEL_55;
      case 0x85u:
        v8 = 70;
        goto LABEL_54;
      case 0x86u:
        v8 = 71;
        goto LABEL_54;
      case 0x87u:
        v9 = 98;
        goto LABEL_55;
      case 0x8Bu:
        v8 = 76;
        v9 = 100;
        goto LABEL_55;
    }
LABEL_86:
    GetErrorInfo(0, &pperrinfo);
    v33 = 0;
    v34 = 0;
    Name = CMetaData::mdGetName(a2, a3);
    v26 = (OLECHAR *)&strIn;
    if ( Name )
      v26 = Name;
    v10 = -2147217891;
    CPersistErrorCache::AddInternalError((CPersistErrorCache *)v31, -2147217891, v26, 0x90u);
    CPersistErrorCache::~CPersistErrorCache((CPersistErrorCache *)v31);
    return (unsigned int)v10;
  }
  if ( v6 == 64 )
  {
    v8 = 72;
    v9 = 96;
    goto LABEL_55;
  }
  if ( v6 > 0xCu )
  {
    switch ( v6 )
    {
      case 0xEu:
        v8 = 76;
        v9 = 90;
        goto LABEL_55;
      case 0x10u:
        v8 = 84;
        goto LABEL_54;
      case 0x11u:
        v8 = 83;
        goto LABEL_54;
      case 0x12u:
        v8 = 85;
        goto LABEL_54;
      case 0x13u:
        v8 = 86;
        goto LABEL_54;
      case 0x14u:
        v8 = 87;
        goto LABEL_54;
      case 0x15u:
        v8 = 88;
        goto LABEL_54;
    }
    goto LABEL_86;
  }
  switch ( v6 )
  {
    case 0xCu:
      goto LABEL_50;
    case 2u:
      v8 = 79;
      goto LABEL_54;
    case 3u:
      v8 = 78;
      goto LABEL_54;
    case 4u:
      v8 = 81;
      goto LABEL_54;
    case 5u:
      v8 = 77;
      goto LABEL_54;
    case 6u:
      v8 = 76;
      v9 = 91;
      goto LABEL_55;
    case 7u:
      v8 = 72;
      v9 = 97;
      goto LABEL_55;
    case 8u:
LABEL_50:
      v8 = 75;
      goto LABEL_54;
  }
  if ( v6 != 11 )
    goto LABEL_86;
  v8 = 73;
LABEL_54:
  v9 = v8;
LABEL_55:
  CPersistStreamInit::Indent(this, *((_DWORD *)this + 12));
  v10 = CPersistStreamInit::WriteTag(this, 0x30u, &v29);
  if ( v10 < 0 )
    return (unsigned int)v10;
  v10 = CPersistStreamInit::WriteNamespace(this, 0x3Fu);
  if ( v10 < 0 )
    return (unsigned int)v10;
  v10 = CPersistStreamInit::WriteTag(this, 0xBu, &v29);
  if ( v10 < 0 )
    return (unsigned int)v10;
  v10 = CPersistStreamInit::WriteAttributeDefinition(
          this,
          *(void **)(*((_QWORD *)this + 9) + 64LL),
          *(unsigned __int16 **)(*((_QWORD *)this + 9) + 16LL * v8),
          v11,
          61,
          0);
  if ( v10 < 0 )
    return (unsigned int)v10;
  if ( v8 != v9 )
  {
    v10 = CPersistStreamInit::WriteAttributeDefinition(
            this,
            *(void **)(*((_QWORD *)this + 9) + 1632LL),
            *(unsigned __int16 **)(*((_QWORD *)this + 9) + 16LL * v9),
            v12,
            65,
            0);
    if ( v10 < 0 )
      return (unsigned int)v10;
  }
  if ( v6 == 12 )
  {
    v24 = Flags;
LABEL_82:
    if ( (v24 & 0x40) != 0
      || (v10 = CPersistStreamInit::WriteAttributeDefinition(
                  this,
                  *(void **)(*((_QWORD *)this + 9) + 1856LL),
                  *(unsigned __int16 **)(*((_QWORD *)this + 9) + 848LL),
                  v12,
                  65,
                  0),
          v10 >= 0) )
    {
      v10 = CPersistStreamInit::WriteTag(this, 0x32u, &v29);
      if ( v10 >= 0 )
        return (unsigned int)CPersistStreamInit::WriteTag(this, 0x28u, &v29);
    }
    return (unsigned int)v10;
  }
  if ( IsFixedLength(v6) && CMetaData::mdGetSize(a2, a3) == 255
    || (v6 == 7 || v6 == 64 ? (Size = 16) : (Size = CMetaData::mdGetSize(a2, a3)),
        CPersistStreamInit::_ulto(this, Size, v35, v13, v28),
        v10 = CPersistStreamInit::WriteAttributeDefinition(
                this,
                *(void **)(*((_QWORD *)this + 9) + 1616LL),
                v35,
                v15,
                61,
                0),
        v10 >= 0) )
  {
    if ( v6 == 14
      || (v16 = v6, (unsigned __int16)(v6 - 131) <= 8u) && (v17 = 273, LOWORD(v16) = v6 - 131, _bittest(&v17, v16)) )
    {
      Scale = CMetaData::mdGetScale(a2, a3);
      CPersistStreamInit::_ito(this, Scale, v35, v19, v28);
      v10 = CPersistStreamInit::WriteAttributeDefinition(
              this,
              *(void **)(*((_QWORD *)this + 9) + 1648LL),
              v35,
              v20,
              65,
              0);
      if ( v10 < 0 )
        return (unsigned int)v10;
      if ( v6 == 139 )
        goto LABEL_75;
    }
    if ( CMetaData::mdGetPrecision(a2, a3) != 0xFF )
    {
LABEL_75:
      Precision = CMetaData::mdGetPrecision(a2, a3);
      CPersistStreamInit::_ito(this, Precision, v35, v22, v28);
      v10 = CPersistStreamInit::WriteAttributeDefinition(
              this,
              *(void **)(*((_QWORD *)this + 9) + 1664LL),
              v35,
              v23,
              65,
              0);
      if ( v10 < 0 )
        return (unsigned int)v10;
    }
    v24 = Flags;
    if ( (Flags & 0x10) == 0
      || (v10 = CPersistStreamInit::WriteAttributeDefinition(
                  this,
                  *(void **)(*((_QWORD *)this + 9) + 1776LL),
                  *(unsigned __int16 **)(*((_QWORD *)this + 9) + 832LL),
                  v12,
                  65,
                  0),
          v10 >= 0) )
    {
      if ( v24 >= 0 )
        goto LABEL_82;
      v10 = CPersistStreamInit::WriteAttributeDefinition(
              this,
              *(void **)(*((_QWORD *)this + 9) + 1792LL),
              *(unsigned __int16 **)(*((_QWORD *)this + 9) + 832LL),
              v12,
              65,
              0);
      if ( v10 >= 0 )
        goto LABEL_82;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001dd70  mov     [rsp-8+arg_18], rbx
0x18001dd75  push    rbp
0x18001dd76  push    rsi
0x18001dd77  push    rdi
0x18001dd78  push    r12
0x18001dd7a  push    r13
0x18001dd7c  push    r14
0x18001dd7e  push    r15
0x18001dd80  lea     rbp, [rsp-170h]
0x18001dd88  sub     rsp, 270h
0x18001dd8f  mov     rax, cs:__security_cookie
0x18001dd96  xor     rax, rsp
0x18001dd99  mov     [rbp+1A0h+var_40], rax
0x18001dda0  movzx   r13d, r8w
0x18001dda4  mov     r12, rdx
0x18001dda7  mov     r14, rcx
0x18001ddaa  xor     edi, edi
0x18001ddac  mov     [rsp+2A0h+var_270], edi
0x18001ddb0  movzx   edx, r8w; unsigned __int16
0x18001ddb4  mov     rcx, r12; this
0x18001ddb7  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x18001ddbc  movzx   r15d, ax
0x18001ddc0  mov     eax, 0BFFFh
0x18001ddc5  and     r15w, ax
0x18001ddc9  mov     rcx, r12; this
0x18001ddcc  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18001ddd1  mov     [rsp+2A0h+var_26C], eax
0x18001ddd5  mov     eax, 0B000h
0x18001ddda  test    ax, r15w
0x18001ddde  jnz     loc_18001E260
0x18001dde4  movzx   ecx, r15w
0x18001dde8  lea     eax, [rdi+0Ch]
0x18001ddeb  lea     edx, [rdi+40h]
0x18001ddee  cmp     ecx, edx
0x18001ddf0  ja      loc_18001DEFC
0x18001ddf6  jz      loc_18001DEF2
0x18001ddfc  cmp     ecx, eax
0x18001ddfe  ja      loc_18001DE84
0x18001de04  jz      loc_18001DF58
0x18001de0a  sub     ecx, 2
0x18001de0d  jz      short loc_18001DE7A
0x18001de0f  sub     ecx, 1
0x18001de12  jz      short loc_18001DE70
0x18001de14  sub     ecx, 1
0x18001de17  jz      short loc_18001DE66
0x18001de19  sub     ecx, 1
0x18001de1c  jz      short loc_18001DE5C
0x18001de1e  sub     ecx, 1
0x18001de21  jz      short loc_18001DE4F
0x18001de23  sub     ecx, 1
0x18001de26  jz      short loc_18001DE42
0x18001de28  sub     ecx, 1
0x18001de2b  jz      loc_18001DF58
0x18001de31  cmp     ecx, 3
0x18001de34  jnz     loc_18001E260
0x18001de3a  lea     ebx, [rdi+49h]
0x18001de3d  jmp     loc_18001DF75
0x18001de42  mov     ebx, 48h ; 'H'
0x18001de47  lea     edi, [rbx+19h]
0x18001de4a  jmp     loc_18001DF78
0x18001de4f  mov     ebx, 4Ch ; 'L'
0x18001de54  lea     edi, [rbx+0Fh]
0x18001de57  jmp     loc_18001DF78
0x18001de5c  mov     ebx, 4Dh ; 'M'
0x18001de61  jmp     loc_18001DF75
0x18001de66  mov     ebx, 51h ; 'Q'
0x18001de6b  jmp     loc_18001DF75
0x18001de70  mov     ebx, 4Eh ; 'N'
0x18001de75  jmp     loc_18001DF75
0x18001de7a  mov     ebx, 4Fh ; 'O'
0x18001de7f  jmp     loc_18001DF75
0x18001de84  sub     ecx, 0Eh
0x18001de87  jz      short loc_18001DEE5
0x18001de89  sub     ecx, 2
0x18001de8c  jz      short loc_18001DEDB
0x18001de8e  sub     ecx, 1
0x18001de91  jz      short loc_18001DED1
0x18001de93  sub     ecx, 1
0x18001de96  jz      short loc_18001DEC7
0x18001de98  sub     ecx, 1
0x18001de9b  jz      short loc_18001DEBD
0x18001de9d  sub     ecx, 1
0x18001dea0  jz      short loc_18001DEB3
0x18001dea2  cmp     ecx, 1
0x18001dea5  jnz     loc_18001E260
0x18001deab  lea     ebx, [rcx+57h]
0x18001deae  jmp     loc_18001DF75
0x18001deb3  mov     ebx, 57h ; 'W'
0x18001deb8  jmp     loc_18001DF75
0x18001debd  mov     ebx, 56h ; 'V'
0x18001dec2  jmp     loc_18001DF75
0x18001dec7  mov     ebx, 55h ; 'U'
0x18001decc  jmp     loc_18001DF75
0x18001ded1  mov     ebx, 53h ; 'S'
0x18001ded6  jmp     loc_18001DF75
0x18001dedb  mov     ebx, 54h ; 'T'
0x18001dee0  jmp     loc_18001DF75
0x18001dee5  mov     ebx, 4Ch ; 'L'
0x18001deea  lea     edi, [rbx+0Eh]
0x18001deed  jmp     loc_18001DF78
0x18001def2  mov     ebx, 48h ; 'H'
0x18001def7  lea     edi, [rbx+18h]
0x18001defa  jmp     short loc_18001DF78
0x18001defc  mov     ebx, 48h ; 'H'
0x18001df01  sub     ecx, ebx
0x18001df03  jz      short loc_18001DF70
0x18001df05  sub     ecx, 38h ; '8'
0x18001df08  jz      short loc_18001DF69
0x18001df0a  sub     ecx, 1
0x18001df0d  jz      short loc_18001DF5F
0x18001df0f  sub     ecx, 1
0x18001df12  jz      short loc_18001DF58
0x18001df14  sub     ecx, 1
0x18001df17  jz      short loc_18001DF4E
0x18001df19  sub     ecx, 2
0x18001df1c  jz      short loc_18001DF47
0x18001df1e  sub     ecx, 1
0x18001df21  jz      short loc_18001DF40
0x18001df23  sub     ecx, 1
0x18001df26  jz      short loc_18001DF39
0x18001df28  cmp     ecx, 4
0x18001df2b  jnz     loc_18001E260
0x18001df31  lea     ebx, [rcx+48h]
0x18001df34  lea     edi, [rcx+60h]
0x18001df37  jmp     short loc_18001DF78
0x18001df39  mov     edi, 62h ; 'b'
0x18001df3e  jmp     short loc_18001DF78
0x18001df40  mov     ebx, 47h ; 'G'
0x18001df45  jmp     short loc_18001DF75
0x18001df47  mov     ebx, 46h ; 'F'
0x18001df4c  jmp     short loc_18001DF75
0x18001df4e  mov     ebx, 4Ch ; 'L'
0x18001df53  lea     edi, [rbx+17h]
0x18001df56  jmp     short loc_18001DF78
0x18001df58  mov     ebx, 4Bh ; 'K'
0x18001df5d  jmp     short loc_18001DF75
0x18001df5f  mov     ebx, 4Bh ; 'K'
0x18001df64  lea     edi, [rbx+12h]
0x18001df67  jmp     short loc_18001DF78
0x18001df69  mov     ebx, 4Ah ; 'J'
0x18001df6e  jmp     short loc_18001DF75
0x18001df70  mov     ebx, 59h ; 'Y'
0x18001df75  movzx   edi, bx
0x18001df78  mov     edx, [r14+30h]; unsigned int
0x18001df7c  mov     rcx, r14; this
0x18001df7f  call    ?Indent@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::Indent(ulong)
0x18001df84  lea     r8, [rsp+2A0h+var_270]; unsigned int *
0x18001df89  mov     dl, 30h ; '0'; unsigned __int8
0x18001df8b  mov     rcx, r14; this
0x18001df8e  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001df93  mov     esi, eax
0x18001df95  test    eax, eax
0x18001df97  js      loc_18001E2B8
0x18001df9d  mov     dl, 3Fh ; '?'; unsigned __int8
0x18001df9f  mov     rcx, r14; this
0x18001dfa2  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001dfa7  mov     esi, eax
0x18001dfa9  test    eax, eax
0x18001dfab  js      loc_18001E2B8
0x18001dfb1  lea     r8, [rsp+2A0h+var_270]; unsigned int *
0x18001dfb6  mov     dl, 0Bh; unsigned __int8
0x18001dfb8  mov     rcx, r14; this
0x18001dfbb  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001dfc0  mov     esi, eax
0x18001dfc2  test    eax, eax
0x18001dfc4  js      loc_18001E2B8
0x18001dfca  mov     rdx, [r14+48h]
0x18001dfce  movsxd  r8, ebx
0x18001dfd1  add     r8, r8
0x18001dfd4  mov     [rsp+2A0h+var_278], 0; bool
0x18001dfd9  mov     [rsp+2A0h+var_280], 3Dh ; '='; int
0x18001dfde  mov     r8, [rdx+r8*8]; unsigned __int16 *
0x18001dfe2  mov     rdx, [rdx+40h]; void *
0x18001dfe6  mov     rcx, r14; this
0x18001dfe9  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001dfee  mov     esi, eax
0x18001dff0  test    eax, eax
0x18001dff2  js      loc_18001E2B8
0x18001dff8  movzx   eax, di
0x18001dffb  cmp     ebx, eax
0x18001dffd  jz      short loc_18001E035
0x18001dfff  mov     rdx, [r14+48h]
0x18001e003  movzx   r8d, di
0x18001e007  add     r8, r8
0x18001e00a  xor     edi, edi
0x18001e00c  mov     [rsp+2A0h+var_278], dil; bool
0x18001e011  mov     [rsp+2A0h+var_280], 41h ; 'A'; char
0x18001e016  mov     r8, [rdx+r8*8]; unsigned __int16 *
0x18001e01a  mov     rdx, [rdx+660h]; void *
0x18001e021  mov     rcx, r14; this
0x18001e024  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001e029  mov     esi, eax
0x18001e02b  test    eax, eax
0x18001e02d  js      loc_18001E2B8
0x18001e033  jmp     short loc_18001E037
0x18001e035  xor     edi, edi
0x18001e037  mov     eax, 0Ch
0x18001e03c  cmp     r15w, ax
0x18001e040  jz      loc_18001E201
0x18001e046  movzx   ecx, r15w; unsigned __int16
0x18001e04a  call    ?IsFixedLength@@YA_NG@Z; IsFixedLength(ushort)
0x18001e04f  test    al, al
0x18001e051  jz      short loc_18001E066
0x18001e053  movzx   edx, r13w; unsigned __int16
0x18001e057  mov     rcx, r12; this
0x18001e05a  call    ?mdGetSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetSize(ushort)
0x18001e05f  cmp     eax, 0FFh
0x18001e064  jz      short loc_18001E0C6
0x18001e066  cmp     r15w, 7
0x18001e06b  jz      short loc_18001E088
0x18001e06d  mov     eax, 40h ; '@'
0x18001e072  cmp     r15w, ax
0x18001e076  jz      short loc_18001E088
0x18001e078  movzx   edx, r13w; unsigned __int16
0x18001e07c  mov     rcx, r12; this
0x18001e07f  call    ?mdGetSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetSize(ushort)
0x18001e084  mov     edx, eax
0x18001e086  jmp     short loc_18001E08D
0x18001e088  mov     edx, 10h; unsigned int
0x18001e08d  lea     r8, [rsp+2A0h+var_240]; void *
0x18001e092  mov     rcx, r14; this
0x18001e095  call    ?_ulto@CPersistStreamInit@@AEBAXKPEAX_KH@Z; CPersistStreamInit::_ulto(ulong,void *,unsigned __int64,int)
0x18001e09a  mov     rdx, [r14+48h]
0x18001e09e  mov     [rsp+2A0h+var_278], dil; bool
0x18001e0a3  mov     [rsp+2A0h+var_280], 3Dh ; '='; int
0x18001e0a8  lea     r8, [rsp+2A0h+var_240]; unsigned __int16 *
0x18001e0ad  mov     rdx, [rdx+650h]; void *
0x18001e0b4  mov     rcx, r14; this
0x18001e0b7  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001e0bc  mov     esi, eax
0x18001e0be  test    eax, eax
0x18001e0c0  js      loc_18001E2B8
0x18001e0c6  mov     eax, 0Eh
0x18001e0cb  cmp     r15w, ax
0x18001e0cf  jz      short loc_18001E0EB
0x18001e0d1  lea     ecx, [rax+75h]
0x18001e0d4  movzx   eax, r15w
0x18001e0d8  sub     ax, cx
0x18001e0db  cmp     ax, 8
0x18001e0df  ja      short loc_18001E13E
0x18001e0e1  mov     ecx, 111h
0x18001e0e6  bt      ecx, eax
0x18001e0e9  jnb     short loc_18001E13E
0x18001e0eb  movzx   edx, r13w; unsigned __int16
0x18001e0ef  mov     rcx, r12; this
0x18001e0f2  call    ?mdGetScale@CMetaData@@QEAAEG@Z; CMetaData::mdGetScale(ushort)
0x18001e0f7  movzx   edx, al; int
0x18001e0fa  lea     r8, [rsp+2A0h+var_240]; void *
0x18001e0ff  mov     rcx, r14; this
0x18001e102  call    ?_ito@CPersistStreamInit@@AEBAXHPEAX_KH@Z; CPersistStreamInit::_ito(int,void *,unsigned __int64,int)
0x18001e107  mov     rdx, [r14+48h]
0x18001e10b  mov     [rsp+2A0h+var_278], dil; bool
0x18001e110  mov     [rsp+2A0h+var_280], 41h ; 'A'; int
0x18001e115  lea     r8, [rsp+2A0h+var_240]; unsigned __int16 *
0x18001e11a  mov     rdx, [rdx+670h]; void *
0x18001e121  mov     rcx, r14; this
0x18001e124  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001e129  mov     esi, eax
0x18001e12b  test    eax, eax
0x18001e12d  js      loc_18001E2B8
0x18001e133  mov     eax, 8Bh
0x18001e138  cmp     r15w, ax
0x18001e13c  jz      short loc_18001E14E
0x18001e13e  movzx   edx, r13w; unsigned __int16
0x18001e142  mov     rcx, r12; this
0x18001e145  call    ?mdGetPrecision@CMetaData@@QEAAEG@Z; CMetaData::mdGetPrecision(ushort)
0x18001e14a  cmp     al, 0FFh
0x18001e14c  jz      short loc_18001E196
0x18001e14e  movzx   edx, r13w; unsigned __int16
0x18001e152  mov     rcx, r12; this
0x18001e155  call    ?mdGetPrecision@CMetaData@@QEAAEG@Z; CMetaData::mdGetPrecision(ushort)
0x18001e15a  movzx   edx, al; int
0x18001e15d  lea     r8, [rsp+2A0h+var_240]; void *
0x18001e162  mov     rcx, r14; this
0x18001e165  call    ?_ito@CPersistStreamInit@@AEBAXHPEAX_KH@Z; CPersistStreamInit::_ito(int,void *,unsigned __int64,int)
0x18001e16a  mov     rdx, [r14+48h]
0x18001e16e  mov     [rsp+2A0h+var_278], dil; bool
0x18001e173  mov     [rsp+2A0h+var_280], 41h ; 'A'; char
0x18001e178  lea     r8, [rsp+2A0h+var_240]; unsigned __int16 *
0x18001e17d  mov     rdx, [rdx+680h]; void *
0x18001e184  mov     rcx, r14; this
0x18001e187  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001e18c  mov     esi, eax
0x18001e18e  test    eax, eax
0x18001e190  js      loc_18001E2B8
0x18001e196  mov     ebx, [rsp+2A0h+var_26C]
0x18001e19a  test    bl, 10h
0x18001e19d  jz      short loc_18001E1CD
0x18001e19f  mov     rdx, [r14+48h]
0x18001e1a3  mov     [rsp+2A0h+var_278], dil; bool
0x18001e1a8  mov     [rsp+2A0h+var_280], 41h ; 'A'; char
0x18001e1ad  mov     r8, [rdx+340h]; unsigned __int16 *
0x18001e1b4  mov     rdx, [rdx+6F0h]; void *
0x18001e1bb  mov     rcx, r14; this
0x18001e1be  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001e1c3  mov     esi, eax
0x18001e1c5  test    eax, eax
0x18001e1c7  js      loc_18001E2B8
0x18001e1cd  test    bl, bl
0x18001e1cf  jns     short loc_18001E205
  ... truncated ...
```
