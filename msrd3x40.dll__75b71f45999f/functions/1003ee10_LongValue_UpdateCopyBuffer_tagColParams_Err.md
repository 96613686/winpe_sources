# LongValue::UpdateCopyBuffer(tagColParams *,Err &)

- ea: `0x1003ee10`
- end: `0x1003f074`
- name: `?UpdateCopyBuffer@LongValue@@QAEXPAUtagColParams@@AAVErr@@@Z`
- size: `612`
- prototype: `void __thiscall(LongValue *__hidden this, struct tagColParams *, struct Err *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x1001ec40`

## callees

- `0x1000eb60`
- `0x1000f7f0`
- `0x10010580`
- `0x1003a4c0`
- `0x1003d170`
- `0x1003ee10`
- `0x1003f550`
- `0x10043ac0`
- `0x10043d00`
- `0x1005e3b0`
- `0x1005f064`

## pseudocode

```c
void __thiscall LongValue::UpdateCopyBuffer(LongValue *this, struct tagColParams *a2, struct Err *a3)
{
  _DWORD *v4; // eax
  struct tagColParams *v5; // edi
  struct Err *v6; // esi
  int v7; // ecx
  unsigned int v8; // ecx
  unsigned int *v9; // ecx
  unsigned int v10; // eax
  unsigned int v11; // eax
  LvDataNew *v12; // ecx
  int v13; // ecx
  int v14; // eax
  unsigned int v15; // edx
  unsigned __int8 **v16; // eax
  unsigned __int8 *v17; // ecx
  unsigned int v18; // eax
  int v19; // [esp+14h] [ebp-54h] BYREF
  unsigned __int8 *v20; // [esp+18h] [ebp-50h] BYREF
  unsigned int v21; // [esp+1Ch] [ebp-4Ch]
  int v22; // [esp+20h] [ebp-48h]
  struct tagColParams *v23; // [esp+24h] [ebp-44h]
  struct Err *v24; // [esp+28h] [ebp-40h]
  unsigned __int8 Src[4]; // [esp+2Ch] [ebp-3Ch] BYREF
  int v26; // [esp+30h] [ebp-38h]
  int v27; // [esp+34h] [ebp-34h]
  char v28[32]; // [esp+38h] [ebp-30h] BYREF
  int v29; // [esp+64h] [ebp-4h]

  v4 = (_DWORD *)*((_DWORD *)this + 1);
  v5 = a2;
  v6 = a3;
  v23 = a2;
  v7 = v4[521];
  v24 = a3;
  if ( !v7 || v7 >= 3 )
    return;
  if ( v4[520] )
  {
    if ( !*((_DWORD *)this + 7) )
    {
      Record::Replace(*(Record **)a2, *(_DWORD *)(*((_DWORD *)this + 3) + 16), 0, 0, a3);
      if ( (*(_BYTE *)a3 & 8) == 0 )
      {
        Record::MarkNull(*(Record **)a2, *(_DWORD *)(*((_DWORD *)this + 3) + 12), a3);
LABEL_30:
        *(_DWORD *)(*((_DWORD *)this + 1) + 2084) = 3;
        return;
      }
    }
    return;
  }
  v8 = v4[516];
  if ( v8 <= 0x20 && !v4[513] )
    goto LABEL_12;
  if ( !v8 && (*(unsigned __int8 (__thiscall **)(_DWORD))(**((_DWORD **)this + 3) + 60))(*((_DWORD *)this + 3)) )
  {
    v6 = v24;
    v5 = v23;
LABEL_12:
    v9 = (unsigned int *)*((_DWORD *)this + 1);
    v10 = v9[516] | 0x80000000;
    v26 = 0;
    *(_DWORD *)Src = v10;
    v27 = 0;
    LvData::GetData((LvData *)v9, v5, v28, v9[516], v6);
    if ( (*(_BYTE *)v6 & 8) != 0 )
      return;
    Record::Replace(
      *(Record **)v5,
      *(_DWORD *)(*((_DWORD *)this + 3) + 16),
      Src,
      *(_DWORD *)(*((_DWORD *)this + 1) + 2064) + 12,
      v6);
LABEL_28:
    if ( (*(_BYTE *)v6 & 8) == 0 )
    {
      v16 = *(unsigned __int8 ***)v5;
      v22 = 0;
      v17 = *v16;
      v18 = (unsigned int)&v16[1][-(((unsigned int)**v16 + 7) >> 3)];
      v21 = ((unsigned int)*v17 + 7) >> 3;
      v20 = &v17[v18];
      Bitmap::Set((Bitmap *)&v20, *(_DWORD *)(*((_DWORD *)this + 3) + 12), v6);
      if ( (*(_BYTE *)v6 & 8) == 0 )
        goto LABEL_30;
    }
    return;
  }
  if ( (*(unsigned __int8 (__thiscall **)(_DWORD))(**((_DWORD **)this + 3) + 60))(*((_DWORD *)this + 3)) )
  {
    v11 = *(_DWORD *)(*((_DWORD *)this + 1) + 2064);
    if ( v11 <= 0x6F0 )
    {
      if ( v11 )
      {
        LongValue::StoreDataOnSharedPage(this, v23, v24);
        if ( (*(_BYTE *)v24 & 8) == 0 )
          *(_DWORD *)(*((_DWORD *)this + 1) + 2084) = 2;
        return;
      }
    }
  }
  v12 = (LvDataNew *)*((_DWORD *)this + 1);
  if ( *((_DWORD *)v12 + 514) )
  {
    v19 = 0;
    v20 = 0;
    v6 = v24;
    v29 = 0;
    LvDataNew::CreateNewFirstPage(v12, v12, (struct DataPage *)&v19, 0, 0, v24);
    if ( v19 )
      --*(_WORD *)(v19 + 76);
  }
  else
  {
    v6 = v24;
  }
  if ( (*(_BYTE *)v6 & 8) == 0 )
  {
    v13 = *((_DWORD *)this + 1);
    v14 = *(_DWORD *)(v13 + 2072);
    if ( *(int *)(v14 + 4) > 0 )
      v15 = **(_DWORD **)(v14 + 12);
    else
      v15 = 0;
    v5 = v23;
    v20 = *(unsigned __int8 **)(v13 + 2064);
    v21 = v15;
    v22 = 0;
    Record::Replace(*(Record **)v23, *(_DWORD *)(*((_DWORD *)this + 3) + 16), (const unsigned __int8 *)&v20, 0xCu, v6);
    goto LABEL_28;
  }
}

```

## disassembly

```asm
0x1003ee10  mov     edi, edi
0x1003ee12  push    ebp
0x1003ee13  mov     ebp, esp
0x1003ee15  push    0FFFFFFFFh
0x1003ee17  push    offset ?UpdateCopyBuffer@LongValue@@QAEXPAUtagColParams@@AAVErr@@@Z_SEH
0x1003ee1c  mov     eax, large fs:0
0x1003ee22  push    eax
0x1003ee23  sub     esp, 4Ch
0x1003ee26  mov     eax, ___security_cookie
0x1003ee2b  xor     eax, ebp
0x1003ee2d  mov     [ebp+var_10], eax
0x1003ee30  push    ebx
0x1003ee31  push    esi
0x1003ee32  push    edi; unsigned int
0x1003ee33  push    eax; void *
0x1003ee34  lea     eax, [ebp+var_C]
0x1003ee37  mov     large fs:0, eax
0x1003ee3d  mov     ebx, ecx
0x1003ee3f  mov     eax, [ebx+4]
0x1003ee42  mov     edi, [ebp+arg_0]
0x1003ee45  mov     esi, [ebp+arg_4]
0x1003ee48  mov     [ebp+var_44], edi
0x1003ee4b  mov     ecx, [eax+824h]
0x1003ee51  mov     [ebp+var_40], esi
0x1003ee54  test    ecx, ecx
0x1003ee56  jz      loc_1003F056
0x1003ee5c  cmp     ecx, 3
0x1003ee5f  jge     loc_1003F056
0x1003ee65  cmp     dword ptr [eax+820h], 0
0x1003ee6c  jz      short loc_1003EEA6
0x1003ee6e  cmp     dword ptr [ebx+1Ch], 0
0x1003ee72  jnz     loc_1003F056
0x1003ee78  mov     eax, [ebx+0Ch]
0x1003ee7b  mov     ecx, [edi]; this
0x1003ee7d  push    esi; struct Err *
0x1003ee7e  push    0; Size
0x1003ee80  push    0; Src
0x1003ee82  push    dword ptr [eax+10h]; unsigned int
0x1003ee85  call    ?Replace@Record@@QAEXIPBEIAAVErr@@@Z; Record::Replace(uint,uchar const *,uint,Err &)
0x1003ee8a  test    byte ptr [esi], 8
0x1003ee8d  jnz     loc_1003F056
0x1003ee93  mov     edx, [ebx+0Ch]
0x1003ee96  mov     ecx, [edi]; this
0x1003ee98  push    esi; struct Err *
0x1003ee99  mov     edx, [edx+0Ch]; unsigned int
0x1003ee9c  call    ?MarkNull@Record@@QAIXIAAVErr@@@Z; Record::MarkNull(uint,Err &)
0x1003eea1  jmp     loc_1003F049
0x1003eea6  mov     ecx, [eax+810h]
0x1003eeac  cmp     ecx, 20h ; ' '
0x1003eeaf  ja      short loc_1003EEBA
0x1003eeb1  cmp     dword ptr [eax+804h], 0
0x1003eeb8  jz      short loc_1003EEDC
0x1003eeba  test    ecx, ecx
0x1003eebc  jnz     short loc_1003EF2B
0x1003eebe  mov     edi, [ebx+0Ch]
0x1003eec1  mov     eax, [edi]
0x1003eec3  mov     esi, [eax+3Ch]
0x1003eec6  mov     ecx, esi
0x1003eec8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003eece  mov     ecx, edi
0x1003eed0  call    esi
0x1003eed2  test    al, al
0x1003eed4  jz      short loc_1003EF2B
0x1003eed6  mov     esi, [ebp+var_40]
0x1003eed9  mov     edi, [ebp+var_44]
0x1003eedc  mov     ecx, [ebx+4]; this
0x1003eedf  push    esi; struct Err *
0x1003eee0  mov     eax, [ecx+810h]
0x1003eee6  or      eax, 80000000h
0x1003eeeb  mov     [ebp+var_38], 0
0x1003eef2  mov     dword ptr [ebp+Src], eax
0x1003eef5  lea     eax, [ebp+var_30]
0x1003eef8  mov     [ebp+var_34], 0
0x1003eeff  push    dword ptr [ecx+810h]; unsigned int
0x1003ef05  push    eax; char *
0x1003ef06  push    edi; struct tagColParams *
0x1003ef07  call    ?GetData@LvData@@QAEKPAUtagColParams@@PADKAAVErr@@@Z; LvData::GetData(tagColParams *,char *,ulong,Err &)
0x1003ef0c  test    byte ptr [esi], 8
0x1003ef0f  jnz     loc_1003F056
0x1003ef15  mov     eax, [ebx+4]
0x1003ef18  push    esi
0x1003ef19  mov     eax, [eax+810h]
0x1003ef1f  add     eax, 0Ch
0x1003ef22  push    eax
0x1003ef23  lea     eax, [ebp+Src]
0x1003ef26  jmp     loc_1003F001
0x1003ef2b  mov     edi, [ebx+0Ch]
0x1003ef2e  mov     eax, [edi]
0x1003ef30  mov     esi, [eax+3Ch]
0x1003ef33  mov     ecx, esi
0x1003ef35  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003ef3b  mov     ecx, edi
0x1003ef3d  call    esi
0x1003ef3f  test    al, al
0x1003ef41  jz      short loc_1003EF81
0x1003ef43  mov     eax, [ebx+4]
0x1003ef46  mov     eax, [eax+810h]
0x1003ef4c  cmp     eax, 6F0h
0x1003ef51  ja      short loc_1003EF81
0x1003ef53  test    eax, eax
0x1003ef55  jz      short loc_1003EF81
0x1003ef57  mov     esi, [ebp+var_40]
0x1003ef5a  mov     ecx, ebx; this
0x1003ef5c  mov     edi, [ebp+var_44]
0x1003ef5f  push    esi; struct Err *
0x1003ef60  push    edi; struct tagColParams *
0x1003ef61  call    ?StoreDataOnSharedPage@LongValue@@AAEXPAUtagColParams@@AAVErr@@@Z; LongValue::StoreDataOnSharedPage(tagColParams *,Err &)
0x1003ef66  test    byte ptr [esi], 8
0x1003ef69  jnz     loc_1003F056
0x1003ef6f  mov     eax, [ebx+4]
0x1003ef72  mov     dword ptr [eax+824h], 2
0x1003ef7c  jmp     loc_1003F056
0x1003ef81  mov     ecx, [ebx+4]; this
0x1003ef84  cmp     dword ptr [ecx+808h], 0
0x1003ef8b  jz      short loc_1003EFC1
0x1003ef8d  mov     [ebp+var_54], 0
0x1003ef94  mov     [ebp+var_50], 0
0x1003ef9b  mov     esi, [ebp+var_40]
0x1003ef9e  lea     eax, [ebp+var_54]
0x1003efa1  push    esi; struct Err *
0x1003efa2  push    0; unsigned int
0x1003efa4  push    0; Src
0x1003efa6  push    eax; struct DataPage *
0x1003efa7  push    ecx; struct tagColParams *
0x1003efa8  mov     [ebp+var_4], 0
0x1003efaf  call    ?CreateNewFirstPage@LvDataNew@@AAEKPAUtagColParams@@AAVDataPage@@PBDKAAVErr@@@Z; LvDataNew::CreateNewFirstPage(tagColParams *,DataPage &,char const *,ulong,Err &)
0x1003efb4  mov     eax, [ebp+var_54]
0x1003efb7  test    eax, eax
0x1003efb9  jz      short loc_1003EFC4
0x1003efbb  dec     word ptr [eax+4Ch]
0x1003efbf  jmp     short loc_1003EFC4
0x1003efc1  mov     esi, [ebp+var_40]
0x1003efc4  test    byte ptr [esi], 8
0x1003efc7  jnz     loc_1003F056
0x1003efcd  mov     ecx, [ebx+4]
0x1003efd0  mov     eax, [ecx+818h]
0x1003efd6  cmp     dword ptr [eax+4], 0
0x1003efda  jg      short loc_1003EFE0
0x1003efdc  xor     edx, edx
0x1003efde  jmp     short loc_1003EFE5
0x1003efe0  mov     eax, [eax+0Ch]
0x1003efe3  mov     edx, [eax]
0x1003efe5  mov     eax, [ecx+810h]
0x1003efeb  mov     edi, [ebp+var_44]
0x1003efee  push    esi; struct Err *
0x1003efef  mov     [ebp+var_50], eax
0x1003eff2  lea     eax, [ebp+var_50]
0x1003eff5  mov     [ebp+var_4C], edx
0x1003eff8  mov     [ebp+var_48], 0
0x1003efff  push    0Ch; Size
0x1003f001  mov     ecx, [edi]; this
0x1003f003  push    eax; Src
0x1003f004  mov     eax, [ebx+0Ch]
0x1003f007  push    dword ptr [eax+10h]; unsigned int
0x1003f00a  call    ?Replace@Record@@QAEXIPBEIAAVErr@@@Z; Record::Replace(uint,uchar const *,uint,Err &)
0x1003f00f  test    byte ptr [esi], 8
0x1003f012  jnz     short loc_1003F056
0x1003f014  mov     eax, [edi]
0x1003f016  push    esi; struct Err *
0x1003f017  mov     [ebp+var_48], 0
0x1003f01e  mov     ecx, [eax]
0x1003f020  mov     eax, [eax+4]
0x1003f023  movzx   edx, byte ptr [ecx]
0x1003f026  add     edx, 7
0x1003f029  shr     edx, 3
0x1003f02c  sub     eax, edx
0x1003f02e  mov     [ebp+var_4C], edx
0x1003f031  add     eax, ecx
0x1003f033  lea     ecx, [ebp+var_50]; this
0x1003f036  mov     [ebp+var_50], eax
0x1003f039  mov     eax, [ebx+0Ch]
0x1003f03c  push    dword ptr [eax+0Ch]; unsigned int
0x1003f03f  call    ?Set@Bitmap@@QAEXKAAVErr@@@Z; Bitmap::Set(ulong,Err &)
0x1003f044  test    byte ptr [esi], 8
0x1003f047  jnz     short loc_1003F056
0x1003f049  mov     eax, [ebx+4]
0x1003f04c  mov     dword ptr [eax+824h], 3
0x1003f056  mov     ecx, [ebp+var_C]
0x1003f059  mov     large fs:0, ecx
0x1003f060  pop     ecx
0x1003f061  pop     edi
0x1003f062  pop     esi
0x1003f063  pop     ebx
0x1003f064  mov     ecx, [ebp+var_10]
0x1003f067  xor     ecx, ebp; StackCookie
0x1003f069  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003f06e  mov     esp, ebp
0x1003f070  pop     ebp
0x1003f071  retn    8
0x100611d0  lea     ecx, [ebp+var_54]; this
0x100611d3  jmp     ??1DataPage@@QAE@XZ; DataPage::~DataPage(void)
0x100611dd  nop
0x100611de  nop
0x100611df  mov     edx, [esp-4+arg_4]
0x100611e3  lea     eax, [edx+0Ch]
0x100611e6  mov     ecx, [edx-5Ch]
0x100611e9  xor     ecx, eax; StackCookie
0x100611eb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100611f0  mov     ecx, [edx-4]
0x100611f3  xor     ecx, eax; StackCookie
0x100611f5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100611fa  mov     eax, offset stru_10063D0C
0x100611ff  jmp     ___CxxFrameHandler3
```
