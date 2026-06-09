# LvDataNew::ReadAt(tagColParams *,LvDataOrig *,Err &,ulong *)

- ea: `0x1003bda0`
- end: `0x1003c05c`
- name: `?ReadAt@LvDataNew@@UAEKPAUtagColParams@@PAVLvDataOrig@@AAVErr@@PAK@Z`
- size: `700`
- prototype: `unsigned int __thiscall(LvDataNew *__hidden this, struct tagColParams *, struct LvDataOrig *, struct Err *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x10010580`
- `0x10025ee0`
- `0x10026060`
- `0x1003bda0`
- `0x1003e640`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`
- `0x1005f07c`

## pseudocode

```c
unsigned int __thiscall LvDataNew::ReadAt(
        LvDataNew *this,
        struct tagColParams *a2,
        struct LvDataOrig *a3,
        void **a4,
        unsigned int *a5)
{
  struct tagColParams *v5; // eax
  size_t v6; // esi
  unsigned int result; // eax
  struct tagColParams *v8; // ebx
  unsigned int v9; // eax
  unsigned int v10; // edi
  unsigned int v11; // edx
  unsigned int v12; // eax
  struct tagColParams *v13; // ecx
  unsigned int v14; // edx
  Err *v15; // eax
  int v16; // eax
  size_t v17; // ecx
  size_t v18; // eax
  size_t v19; // ecx
  unsigned __int16 v20; // ax
  size_t v21; // edx
  unsigned int v22; // ecx
  unsigned int v23; // eax
  unsigned int v24; // eax
  int v25; // [esp+10h] [ebp-3Ch] BYREF
  int v26; // [esp+14h] [ebp-38h]
  size_t v27; // [esp+20h] [ebp-2Ch]
  int v28; // [esp+24h] [ebp-28h]
  int v29; // [esp+28h] [ebp-24h]
  int v30; // [esp+2Ch] [ebp-20h]
  LvDataNew *v31; // [esp+30h] [ebp-1Ch]
  unsigned int v32; // [esp+34h] [ebp-18h] BYREF
  unsigned int v33; // [esp+38h] [ebp-14h]
  struct tagColParams *v34; // [esp+3Ch] [ebp-10h]
  int v35; // [esp+48h] [ebp-4h]

  v31 = this;
  v5 = (LvDataNew *)((char *)this + 2064);
  v6 = 0;
  v34 = (LvDataNew *)((char *)this + 2064);
  if ( a5 )
  {
    *a5 = *(_DWORD *)v5;
    v5 = v34;
  }
  else
  {
    v34 = (LvDataNew *)((char *)this + 2064);
  }
  if ( !*((_DWORD *)this + 520) )
  {
    v8 = a2;
    v9 = *(_DWORD *)v5;
    v10 = *((_DWORD *)a2 + 4);
    if ( v10 >= v9 )
      return 0;
    v11 = *((_DWORD *)a2 + 2);
    if ( !v11 && v9 )
    {
      Err::SetWarning((Err *)a4, 1006);
      return 0;
    }
    if ( *((_DWORD *)this + 514) )
    {
      v6 = v9 - v10;
      if ( v11 < v9 - v10 )
      {
        Err::SetWarning((Err *)a4, 1006);
        v6 = *((_DWORD *)a2 + 2);
        this = v31;
      }
      memcpy(*((void **)a2 + 1), (char *)this + *((_DWORD *)a2 + 4) + 4, v6);
      return v6;
    }
    v25 = 0;
    v26 = 0;
    v35 = 0;
    v12 = LvDataNew::ReadDPOfOffset(this, this, v10, (struct DataPage *)&v25, &v32, a3, (struct Err *)a4);
    v13 = v34;
    v14 = v12;
    v15 = (Err *)a4;
    v33 = v14;
    if ( (*(_BYTE *)a4 & 8) != 0 )
    {
LABEL_44:
      if ( v6 == *((_DWORD *)v8 + 2) && v10 != *(_DWORD *)v13 )
        Err::SetWarning(v15, 1006);
      if ( v25 )
        --*(_WORD *)(v25 + 76);
      return v6;
    }
    while ( 1 )
    {
      v16 = *(_DWORD *)v13;
      if ( v10 >= *(_DWORD *)v13 )
      {
LABEL_43:
        v15 = (Err *)a4;
        goto LABEL_44;
      }
      v17 = *((_DWORD *)v8 + 2);
      if ( v6 >= v17 )
        goto LABEL_42;
      v18 = v16 - v10;
      v19 = v17 - v6;
      if ( v19 >= v18 )
        v19 = v18;
      v20 = v10 - v14;
      v21 = 2032 - (unsigned __int16)(v10 - v14);
      v28 = v20;
      if ( v19 < v21 )
        v21 = v19;
      v27 = v21;
      v30 = *(unsigned __int16 *)(v26 + 2 * (unsigned __int8)v32 + 10);
      v22 = v30 & 0x3FFF;
      if ( v22 <= 0x800 )
      {
        if ( (_BYTE)v32 )
        {
          v8 = a2;
          v23 = *(_WORD *)(v26 + 2 * (unsigned __int8)v32 + 8) & 0x3FFF;
          if ( v23 > 0x800 || v22 > v23 )
            goto LABEL_35;
        }
        else
        {
          v23 = 2048;
        }
        if ( v23 - v22 <= 0x800 )
        {
          v29 = v22 + v26;
          if ( (v30 & 0xFFFFC000) == 0xC000 )
          {
            Err::SetError(a4, -1017, v30 & 0x3FFF);
LABEL_42:
            v13 = v34;
            goto LABEL_43;
          }
        }
      }
LABEL_35:
      memcpy((void *)(v6 + *((_DWORD *)v8 + 1)), (const void *)(v28 + 4 + v29), v21);
      v13 = v34;
      v10 += v27;
      v6 += v27;
      LOWORD(v14) = v33;
      if ( v10 < *(_DWORD *)v34 && v6 < *((_DWORD *)v8 + 2) && v10 >= v33 + 2032 )
      {
        v24 = LvDataNew::ReadDPOfOffset(v31, v34, v10, (struct DataPage *)&v25, &v32, a3, (struct Err *)a4);
        v13 = v34;
        LOWORD(v14) = v24;
        v33 = v24;
      }
      v15 = (Err *)a4;
      if ( (*(_BYTE *)a4 & 8) != 0 )
        goto LABEL_44;
    }
  }
  if ( (int)*a4 >= 4 )
    return 0;
  if ( ((unsigned int)*a4 & 0xFFFFFFFE) != 0 )
  {
    if ( a4[3] )
      operator delete[](a4[3]);
    if ( a4[4] )
      operator delete[](a4[4]);
  }
  *a4 = (void *)4;
  result = 0;
  a4[1] = (void *)1004;
  a4[2] = 0;
  a4[3] = 0;
  a4[4] = 0;
  return result;
}

```

## disassembly

```asm
0x1003bda0  mov     edi, edi
0x1003bda2  push    ebp
0x1003bda3  mov     ebp, esp
0x1003bda5  push    0FFFFFFFFh
0x1003bda7  push    offset ?ReadAt@LvDataNew@@UAEKPAUtagColParams@@PAVLvDataOrig@@AAVErr@@PAK@Z_SEH
0x1003bdac  mov     eax, large fs:0
0x1003bdb2  push    eax
0x1003bdb3  sub     esp, 30h
0x1003bdb6  push    ebx
0x1003bdb7  push    esi
0x1003bdb8  push    edi
0x1003bdb9  mov     eax, ___security_cookie
0x1003bdbe  xor     eax, ebp
0x1003bdc0  push    eax
0x1003bdc1  lea     eax, [ebp+var_C]
0x1003bdc4  mov     large fs:0, eax
0x1003bdca  mov     [ebp+var_1C], ecx
0x1003bdcd  mov     edx, [ebp+arg_C]
0x1003bdd0  lea     eax, [ecx+810h]
0x1003bdd6  xor     esi, esi
0x1003bdd8  mov     [ebp+var_10], eax
0x1003bddb  test    edx, edx
0x1003bddd  jz      short loc_1003BDE8
0x1003bddf  mov     eax, [eax]
0x1003bde1  mov     [edx], eax
0x1003bde3  mov     eax, [ebp+var_10]
0x1003bde6  jmp     short loc_1003BDEB
0x1003bde8  mov     [ebp+var_10], eax
0x1003bdeb  cmp     [ecx+820h], esi
0x1003bdf1  jz      short loc_1003BE60
0x1003bdf3  mov     esi, [ebp+arg_8]
0x1003bdf6  mov     eax, [esi]
0x1003bdf8  cmp     eax, 4
0x1003bdfb  jge     loc_1003BE84
0x1003be01  test    eax, 0FFFFFFFEh
0x1003be06  jz      short loc_1003BE28
0x1003be08  mov     eax, [esi+0Ch]
0x1003be0b  test    eax, eax
0x1003be0d  jz      short loc_1003BE18
0x1003be0f  push    eax; Block
0x1003be10  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003be15  add     esp, 4
0x1003be18  mov     eax, [esi+10h]
0x1003be1b  test    eax, eax
0x1003be1d  jz      short loc_1003BE28
0x1003be1f  push    eax; Block
0x1003be20  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003be25  add     esp, 4
0x1003be28  mov     dword ptr [esi], 4
0x1003be2e  xor     eax, eax
0x1003be30  mov     dword ptr [esi+4], 3ECh
0x1003be37  mov     dword ptr [esi+8], 0
0x1003be3e  mov     dword ptr [esi+0Ch], 0
0x1003be45  mov     dword ptr [esi+10h], 0
0x1003be4c  mov     ecx, [ebp+var_C]
0x1003be4f  mov     large fs:0, ecx
0x1003be56  pop     ecx
0x1003be57  pop     edi
0x1003be58  pop     esi
0x1003be59  pop     ebx
0x1003be5a  mov     esp, ebp
0x1003be5c  pop     ebp
0x1003be5d  retn    10h
0x1003be60  mov     ebx, [ebp+arg_0]
0x1003be63  mov     eax, [eax]
0x1003be65  mov     edi, [ebx+10h]
0x1003be68  cmp     edi, eax
0x1003be6a  jnb     short loc_1003BE84
0x1003be6c  mov     edx, [ebx+8]
0x1003be6f  test    edx, edx
0x1003be71  jnz     short loc_1003BE9A
0x1003be73  test    eax, eax
0x1003be75  jz      short loc_1003BE9A
0x1003be77  mov     ecx, [ebp+arg_8]; this
0x1003be7a  push    3EEh; int
0x1003be7f  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x1003be84  xor     eax, eax
0x1003be86  mov     ecx, [ebp+var_C]
0x1003be89  mov     large fs:0, ecx
0x1003be90  pop     ecx
0x1003be91  pop     edi
0x1003be92  pop     esi
0x1003be93  pop     ebx
0x1003be94  mov     esp, ebp
0x1003be96  pop     ebp
0x1003be97  retn    10h
0x1003be9a  cmp     [ecx+808h], esi
0x1003bea0  jz      short loc_1003BED7
0x1003bea2  mov     esi, eax
0x1003bea4  sub     esi, edi
0x1003bea6  cmp     edx, esi
0x1003bea8  jnb     short loc_1003BEBD
0x1003beaa  mov     ecx, [ebp+arg_8]; this
0x1003bead  push    3EEh; int
0x1003beb2  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x1003beb7  mov     esi, [ebx+8]
0x1003beba  mov     ecx, [ebp+var_1C]
0x1003bebd  mov     eax, [ebx+10h]
0x1003bec0  add     eax, 4
0x1003bec3  push    esi; Size
0x1003bec4  add     eax, ecx
0x1003bec6  push    eax; Src
0x1003bec7  push    dword ptr [ebx+4]; void *
0x1003beca  call    _memcpy
0x1003becf  add     esp, 0Ch
0x1003bed2  jmp     loc_1003C046
0x1003bed7  mov     [ebp+var_3C], esi
0x1003beda  mov     [ebp+var_38], esi
0x1003bedd  push    [ebp+arg_8]; struct Err *
0x1003bee0  lea     eax, [ebp+var_18]
0x1003bee3  mov     [ebp+var_4], 0
0x1003beea  push    [ebp+arg_4]; struct LvDataOrig *
0x1003beed  push    eax; unsigned int *
0x1003beee  lea     eax, [ebp+var_3C]
0x1003bef1  push    eax; struct DataPage *
0x1003bef2  push    edi; unsigned int
0x1003bef3  push    ecx; struct tagColParams *
0x1003bef4  call    ?ReadDPOfOffset@LvDataNew@@AAEKPAUtagColParams@@KAAVDataPage@@PAKPAVLvDataOrig@@AAVErr@@@Z; LvDataNew::ReadDPOfOffset(tagColParams *,ulong,DataPage &,ulong *,LvDataOrig *,Err &)
0x1003bef9  mov     ecx, [ebp+var_10]
0x1003befc  mov     edx, eax
0x1003befe  mov     eax, [ebp+arg_8]
0x1003bf01  mov     [ebp+var_14], edx
0x1003bf04  test    byte ptr [eax], 8
0x1003bf07  jnz     loc_1003C026
0x1003bf0d  nop     dword ptr [eax]
0x1003bf10  mov     eax, [ecx]
0x1003bf12  cmp     edi, eax
0x1003bf14  jnb     loc_1003C023
0x1003bf1a  mov     ecx, [ebx+8]
0x1003bf1d  cmp     esi, ecx
0x1003bf1f  jnb     loc_1003C020
0x1003bf25  sub     eax, edi
0x1003bf27  sub     ecx, esi
0x1003bf29  cmp     ecx, eax
0x1003bf2b  cmovnb  ecx, eax
0x1003bf2e  mov     eax, edi
0x1003bf30  sub     eax, edx
0x1003bf32  mov     edx, 7F0h
0x1003bf37  movzx   eax, ax
0x1003bf3a  sub     edx, eax
0x1003bf3c  mov     [ebp+var_28], eax
0x1003bf3f  movzx   eax, byte ptr [ebp+var_18]
0x1003bf43  cmp     ecx, edx
0x1003bf45  cmovb   edx, ecx
0x1003bf48  mov     ecx, [ebp+var_38]
0x1003bf4b  mov     [ebp+var_2C], edx
0x1003bf4e  movzx   ecx, word ptr [ecx+eax*2+0Ah]
0x1003bf53  mov     [ebp+var_20], ecx
0x1003bf56  and     ecx, 3FFFh
0x1003bf5c  cmp     ecx, 800h
0x1003bf62  ja      short loc_1003BFAA
0x1003bf64  test    eax, eax
0x1003bf66  jnz     short loc_1003BF6F
0x1003bf68  mov     eax, 800h
0x1003bf6d  jmp     short loc_1003BF8A
0x1003bf6f  mov     ebx, [ebp+var_38]
0x1003bf72  movzx   eax, word ptr [ebx+eax*2+8]
0x1003bf77  mov     ebx, [ebp+arg_0]
0x1003bf7a  and     eax, 3FFFh
0x1003bf7f  cmp     eax, 800h
0x1003bf84  ja      short loc_1003BFAA
0x1003bf86  cmp     ecx, eax
0x1003bf88  ja      short loc_1003BFAA
0x1003bf8a  sub     eax, ecx
0x1003bf8c  cmp     eax, 800h
0x1003bf91  ja      short loc_1003BFAA
0x1003bf93  mov     eax, [ebp+var_38]
0x1003bf96  add     eax, ecx
0x1003bf98  mov     [ebp+var_24], eax
0x1003bf9b  mov     eax, [ebp+var_20]
0x1003bf9e  and     eax, 0FFFFC000h
0x1003bfa3  cmp     eax, 0C000h
0x1003bfa8  jz      short loc_1003C012
0x1003bfaa  mov     ecx, [ebp+var_28]
0x1003bfad  mov     eax, [ebp+var_24]
0x1003bfb0  add     ecx, 4
0x1003bfb3  add     eax, ecx
0x1003bfb5  push    edx; Size
0x1003bfb6  push    eax; Src
0x1003bfb7  mov     eax, [ebx+4]
0x1003bfba  add     eax, esi
0x1003bfbc  push    eax; void *
0x1003bfbd  call    _memcpy
0x1003bfc2  mov     ecx, [ebp+var_10]
0x1003bfc5  add     esp, 0Ch
0x1003bfc8  add     edi, [ebp+var_2C]
0x1003bfcb  add     esi, [ebp+var_2C]
0x1003bfce  mov     edx, [ebp+var_14]
0x1003bfd1  cmp     edi, [ecx]
0x1003bfd3  jnb     short loc_1003C004
0x1003bfd5  cmp     esi, [ebx+8]
0x1003bfd8  jnb     short loc_1003C004
0x1003bfda  lea     eax, [edx+7F0h]
0x1003bfe0  cmp     edi, eax
0x1003bfe2  jb      short loc_1003C004
0x1003bfe4  push    [ebp+arg_8]; struct Err *
0x1003bfe7  lea     eax, [ebp+var_18]
0x1003bfea  push    [ebp+arg_4]; struct LvDataOrig *
0x1003bfed  push    eax; unsigned int *
0x1003bfee  lea     eax, [ebp+var_3C]
0x1003bff1  push    eax; struct DataPage *
0x1003bff2  push    edi; unsigned int
0x1003bff3  push    ecx; struct tagColParams *
0x1003bff4  mov     ecx, [ebp+var_1C]; this
0x1003bff7  call    ?ReadDPOfOffset@LvDataNew@@AAEKPAUtagColParams@@KAAVDataPage@@PAKPAVLvDataOrig@@AAVErr@@@Z; LvDataNew::ReadDPOfOffset(tagColParams *,ulong,DataPage &,ulong *,LvDataOrig *,Err &)
0x1003bffc  mov     ecx, [ebp+var_10]
0x1003bfff  mov     edx, eax
0x1003c001  mov     [ebp+var_14], edx
0x1003c004  mov     eax, [ebp+arg_8]
0x1003c007  test    byte ptr [eax], 8
0x1003c00a  jz      loc_1003BF10
0x1003c010  jmp     short loc_1003C026
0x1003c012  push    ecx
0x1003c013  mov     ecx, [ebp+arg_8]
0x1003c016  push    0FFFFFC07h
0x1003c01b  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1003c020  mov     ecx, [ebp+var_10]
0x1003c023  mov     eax, [ebp+arg_8]
0x1003c026  cmp     esi, [ebx+8]
0x1003c029  jnz     short loc_1003C03B
0x1003c02b  cmp     edi, [ecx]
0x1003c02d  jz      short loc_1003C03B
0x1003c02f  push    3EEh; int
0x1003c034  mov     ecx, eax; this
0x1003c036  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x1003c03b  mov     ecx, [ebp+var_3C]
0x1003c03e  test    ecx, ecx
0x1003c040  jz      short loc_1003C046
0x1003c042  dec     word ptr [ecx+4Ch]
0x1003c046  mov     eax, esi
0x1003c048  mov     ecx, [ebp+var_C]
0x1003c04b  mov     large fs:0, ecx
0x1003c052  pop     ecx
0x1003c053  pop     edi
0x1003c054  pop     esi
0x1003c055  pop     ebx
0x1003c056  mov     esp, ebp
0x1003c058  pop     ebp
0x1003c059  retn    10h
0x100600f0  lea     ecx, [ebp+var_3C]; this
0x100600f3  jmp     ??1DataPage@@QAE@XZ; DataPage::~DataPage(void)
0x100600fd  nop
0x100600fe  nop
0x100600ff  mov     edx, [esp-4+arg_4]
0x10060103  lea     eax, [edx+0Ch]
0x10060106  mov     ecx, [edx-40h]
0x10060109  xor     ecx, eax; StackCookie
0x1006010b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060110  mov     eax, offset stru_10063118
0x10060115  jmp     ___CxxFrameHandler3
```
