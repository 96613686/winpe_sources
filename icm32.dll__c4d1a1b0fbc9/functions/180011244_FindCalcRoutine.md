# FindCalcRoutine

- ea: `0x180011244`
- end: `0x180011788`
- name: `FindCalcRoutine`
- size: `1348`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e724`
- `0x18000ee40`
- `0x18001fc68`
- `0x180020380`

## callees

- `0x180011244`
- `0x18001fa7c`

## pseudocode

```c
__int64 (__fastcall *__fastcall FindCalcRoutine(__int64 a1, _DWORD *a2, __int64 a3, char a4))()
{
  __int64 (__fastcall *LookupRoutine)(); // rcx
  __int64 v5; // r11
  _DWORD *v6; // r10
  __int64 (__fastcall *v8)(); // rax

  LookupRoutine = 0;
  v5 = a3;
  v6 = a2;
  if ( a4 )
  {
    LookupRoutine = (__int64 (__fastcall *)())FindLookupRoutine(a2, a3);
    if ( LookupRoutine )
      return LookupRoutine;
  }
  if ( v6[12] == 1 )
  {
    if ( v6[13] == 1 || (unsigned int)(v6[13] - 3) <= 1 )
    {
      if ( *(_DWORD *)(v5 + 8) == 8 )
      {
        if ( *(_DWORD *)(v5 + 12) == 8 )
        {
          if ( v6[15] == 8 )
          {
            if ( v6[14] == 128 )
              return LHCalc1toX_Di8_Do8_Lut8_G128;
          }
          else if ( v6[15] == 16 && v6[14] == 128 )
          {
            return LHCalc1toX_Di8_Do8_Lut16_G128;
          }
        }
      }
      else if ( *(_DWORD *)(v5 + 8) == 16 && *(_DWORD *)(v5 + 12) == 16 )
      {
        if ( v6[15] == 8 )
        {
          if ( v6[14] == 128 )
            return LHCalc1toX_Di16_Do16_Lut8_G128;
        }
        else if ( v6[15] == 16 && v6[14] == 128 )
        {
          return LHCalc1toX_Di16_Do16_Lut16_G128;
        }
      }
    }
    goto LABEL_28;
  }
  if ( v6[12] != 3 )
  {
    if ( v6[12] != 4 )
      goto LABEL_28;
    if ( v6[13] == 3 )
    {
      if ( *(_DWORD *)(v5 + 8) != 8 )
        goto LABEL_29;
      if ( *(_DWORD *)(v5 + 12) != 8 )
        goto LABEL_28;
      if ( v6[15] != 8 )
      {
        if ( v6[15] == 16 )
        {
          if ( v6[14] == 8 )
            return LHCalc4to3_Di8_Do8_Lut16_G8;
          if ( v6[14] == 16 )
            return LHCalc4to3_Di8_Do8_Lut16_G16;
        }
        goto LABEL_28;
      }
      if ( v6[14] != 8 )
      {
        if ( v6[14] == 16 )
          return LHCalc4to3_Di8_Do8_Lut8_G16;
        goto LABEL_28;
      }
      LookupRoutine = LHCalc4to3_Di8_Do8_Lut8_G8;
    }
    else
    {
      if ( v6[13] != 4 )
        goto LABEL_28;
      if ( *(_DWORD *)(v5 + 8) != 8 )
      {
LABEL_29:
        if ( *(_DWORD *)(v5 + 8) == 16 )
        {
          if ( *(_DWORD *)(v5 + 12) == 8 )
          {
            if ( v6[15] == 8 )
            {
              return CalcNDim_Data8To16_Lut8;
            }
            else if ( v6[15] == 16 )
            {
              return CalcNDim_Data8To16_Lut8;
            }
          }
          else if ( *(_DWORD *)(v5 + 12) == 16 )
          {
            if ( v6[15] == 8 )
            {
              return CalcNDim_Data8To16_Lut8;
            }
            else if ( v6[15] == 16 )
            {
              return CalcNDim_Data8To16_Lut8;
            }
          }
        }
        return LookupRoutine;
      }
      if ( *(_DWORD *)(v5 + 12) != 8 )
        goto LABEL_28;
      if ( v6[15] != 8 )
      {
        if ( v6[15] == 16 )
        {
          if ( v6[14] == 8 )
            return LHCalc4to4_Di8_Do8_Lut16_G8;
          if ( v6[14] == 16 )
            return LHCalc4to4_Di8_Do8_Lut16_G16;
        }
        goto LABEL_28;
      }
      if ( v6[14] != 8 )
      {
        if ( v6[14] == 16 )
          return LHCalc4to4_Di8_Do8_Lut8_G16;
        goto LABEL_28;
      }
      LookupRoutine = LHCalc4to4_Di8_Do8_Lut8_G8;
    }
    goto LABEL_12;
  }
  if ( v6[13] == 3 )
  {
    if ( *(_DWORD *)(v5 + 8) == 8 )
    {
      if ( *(_DWORD *)(v5 + 12) != 8 )
        goto LABEL_28;
      if ( v6[15] != 8 )
      {
        if ( v6[15] == 16 )
        {
          if ( v6[14] == 16 )
            return LHCalc3to3_Di8_Do8_Lut16_G16;
          if ( v6[14] == 32 )
            return LHCalc3to3_Di8_Do8_Lut16_G32;
        }
        goto LABEL_28;
      }
      if ( v6[14] != 16 )
      {
        if ( v6[14] == 32 )
        {
          LookupRoutine = LHCalc3to3_Di8_Do8_Lut8_G32;
          v8 = LHCalc3to3_Di8_Do8_Lut8_G32_Old;
LABEL_115:
          if ( !*(_BYTE *)(v5 + 48) )
            return v8;
          return LookupRoutine;
        }
        goto LABEL_28;
      }
      if ( !*(_BYTE *)(v5 + 48) )
        return LHCalc3to3_Di8_Do8_Lut8_G16_Old;
      LookupRoutine = LHCalc3to3_Di8_Do8_Lut8_G16;
    }
    else
    {
      if ( *(_DWORD *)(v5 + 8) != 16 || *(_DWORD *)(v5 + 12) != 16 )
        goto LABEL_28;
      if ( v6[15] != 8 )
      {
        if ( v6[15] == 16 )
        {
          if ( v6[14] == 16 )
            return LHCalc3to3_Di16_Do16_Lut16_G16;
          if ( v6[14] == 32 )
            return LHCalc3to3_Di16_Do16_Lut16_G32;
        }
        goto LABEL_28;
      }
      if ( v6[14] != 16 )
      {
        if ( v6[14] == 32 )
          return LHCalc3to3_Di16_Do16_Lut8_G32;
        goto LABEL_28;
      }
      LookupRoutine = LHCalc3to3_Di16_Do16_Lut8_G16;
    }
LABEL_12:
    if ( LookupRoutine )
      return LookupRoutine;
    goto LABEL_28;
  }
  if ( v6[13] != 4 )
    goto LABEL_28;
  if ( *(_DWORD *)(v5 + 8) != 8 )
  {
    if ( *(_DWORD *)(v5 + 8) != 16 || *(_DWORD *)(v5 + 12) != 16 )
      goto LABEL_28;
    if ( v6[15] != 8 )
    {
      if ( v6[15] == 16 )
      {
        if ( v6[14] == 16 )
          return LHCalc3to4_Di16_Do16_Lut16_G16;
        if ( v6[14] == 32 )
          return LHCalc3to4_Di16_Do16_Lut16_G32;
      }
      goto LABEL_28;
    }
    if ( v6[14] != 16 )
    {
      if ( v6[14] == 32 )
        return LHCalc3to4_Di16_Do16_Lut8_G32;
      goto LABEL_28;
    }
    LookupRoutine = LHCalc3to4_Di16_Do16_Lut8_G16;
    goto LABEL_12;
  }
  if ( *(_DWORD *)(v5 + 12) != 8 )
    goto LABEL_28;
  if ( v6[15] != 8 )
  {
    if ( v6[15] == 16 )
    {
      if ( v6[14] == 16 )
        return LHCalc3to4_Di8_Do8_Lut16_G16;
      if ( v6[14] == 32 )
        return LHCalc3to4_Di8_Do8_Lut16_G32;
    }
    goto LABEL_28;
  }
  if ( v6[14] == 16 )
  {
    if ( !*(_BYTE *)(v5 + 48) )
      return LHCalc3to4_Di8_Do8_Lut8_G16_Old;
    LookupRoutine = LHCalc3to4_Di8_Do8_Lut8_G16;
    goto LABEL_12;
  }
  if ( v6[14] == 32 )
  {
    LookupRoutine = LHCalc3to4_Di8_Do8_Lut8_G32;
    v8 = LHCalc3to4_Di8_Do8_Lut8_G32_Old;
    goto LABEL_115;
  }
LABEL_28:
  if ( *(_DWORD *)(v5 + 8) != 8 )
    goto LABEL_29;
  if ( *(_DWORD *)(v5 + 12) == 8 )
  {
    if ( v6[15] == 8 )
    {
      return CalcNDim_Data8To16_Lut8;
    }
    else if ( v6[15] == 16 )
    {
      return (__int64 (__fastcall *)())CalcNDim_Data8To8_Lut16;
    }
  }
  else if ( *(_DWORD *)(v5 + 12) == 16 )
  {
    if ( v6[15] == 8 )
    {
      return CalcNDim_Data8To16_Lut8;
    }
    else if ( v6[15] == 16 )
    {
      return CalcNDim_Data8To16_Lut8;
    }
  }
  return LookupRoutine;
}

```

## disassembly

```asm
0x180011244  sub     rsp, 28h
0x180011248  xor     ecx, ecx
0x18001124a  mov     r11, r8
0x18001124d  mov     r10, rdx
0x180011250  test    r9b, r9b
0x180011253  jnz     loc_1800114F6
0x180011259  mov     edx, [r10+30h]
0x18001125d  mov     r9d, 8
0x180011263  lea     r8d, [r9+8]
0x180011267  sub     edx, 1
0x18001126a  jz      loc_18001131C
0x180011270  sub     edx, 2
0x180011273  jnz     short loc_1800112D5
0x180011275  mov     edx, [r10+34h]
0x180011279  sub     edx, 3
0x18001127c  jnz     loc_1800113EC
0x180011282  cmp     [r11+8], r9d
0x180011286  jnz     loc_180011383
0x18001128c  cmp     [r11+0Ch], r9d
0x180011290  jnz     loc_180011349
0x180011296  cmp     [r10+3Ch], r9d
0x18001129a  jz      loc_1800116BC
0x1800112a0  cmp     [r10+3Ch], r8d
0x1800112a4  jnz     loc_180011349
0x1800112aa  cmp     [r10+38h], r8d
0x1800112ae  jz      loc_1800116B0
0x1800112b4  cmp     dword ptr [r10+38h], 20h ; ' '
0x1800112b9  jnz     loc_180011349
0x1800112bf  lea     rcx, LHCalc3to3_Di8_Do8_Lut16_G32
0x1800112c6  jmp     short loc_1800112CD
0x1800112c8  test    rcx, rcx
0x1800112cb  jz      short loc_180011349
0x1800112cd  mov     rax, rcx
0x1800112d0  add     rsp, 28h
0x1800112d4  retn
0x1800112d5  cmp     edx, 1
0x1800112d8  jnz     short loc_180011349
0x1800112da  mov     edx, [r10+34h]
0x1800112de  sub     edx, 3
0x1800112e1  jnz     loc_180011512
0x1800112e7  cmp     [r11+8], r9d
0x1800112eb  jnz     short loc_180011353
0x1800112ed  cmp     [r11+0Ch], r9d
0x1800112f1  jnz     short loc_180011349
0x1800112f3  cmp     [r10+3Ch], r9d
0x1800112f7  jz      loc_18001159B
0x1800112fd  cmp     [r10+3Ch], r8d
0x180011301  jnz     short loc_180011349
0x180011303  cmp     [r10+38h], r9d
0x180011307  jz      loc_18001158F
0x18001130d  cmp     [r10+38h], r8d
0x180011311  jnz     short loc_180011349
0x180011313  lea     rcx, LHCalc4to3_Di8_Do8_Lut16_G16
0x18001131a  jmp     short loc_1800112CD
0x18001131c  mov     edx, [r10+34h]
0x180011320  sub     edx, 1
0x180011323  jz      short loc_18001132F
0x180011325  sub     edx, 2
0x180011328  jz      short loc_18001132F
0x18001132a  cmp     edx, 1
0x18001132d  jnz     short loc_180011349
0x18001132f  cmp     [r11+8], r9d
0x180011333  jz      loc_180011486
0x180011339  cmp     [r11+8], r8d
0x18001133d  jnz     short loc_180011349
0x18001133f  cmp     [r11+0Ch], r8d
0x180011343  jz      loc_1800114BE
0x180011349  cmp     [r11+8], r9d
0x18001134d  jz      loc_180011452
0x180011353  cmp     [r11+8], r8d
0x180011357  jnz     loc_1800112CD
0x18001135d  cmp     [r11+0Ch], r9d
0x180011361  jnz     short loc_1800113C2
0x180011363  cmp     [r10+3Ch], r9d
0x180011367  jz      loc_180011748
0x18001136d  cmp     [r10+3Ch], r8d
0x180011371  jnz     loc_1800112CD
0x180011377  lea     rcx, CalcNDim_Data8To16_Lut8
0x18001137e  jmp     loc_1800112CD
0x180011383  cmp     [r11+8], r8d
0x180011387  jnz     short loc_180011349
0x180011389  cmp     [r11+0Ch], r9d
0x18001138d  jz      short loc_180011349
0x18001138f  cmp     [r11+0Ch], r8d
0x180011393  jnz     short loc_180011349
0x180011395  cmp     [r10+3Ch], r9d
0x180011399  jz      loc_180011687
0x18001139f  cmp     [r10+3Ch], r8d
0x1800113a3  jnz     short loc_180011349
0x1800113a5  cmp     [r10+38h], r8d
0x1800113a9  jz      loc_18001167B
0x1800113af  cmp     dword ptr [r10+38h], 20h ; ' '
0x1800113b4  jnz     short loc_180011349
0x1800113b6  lea     rcx, LHCalc3to3_Di16_Do16_Lut16_G32
0x1800113bd  jmp     loc_1800112CD
0x1800113c2  cmp     [r11+0Ch], r8d
0x1800113c6  jnz     loc_1800112CD
0x1800113cc  cmp     [r10+3Ch], r9d
0x1800113d0  jz      loc_18001173C
0x1800113d6  cmp     [r10+3Ch], r8d
0x1800113da  jnz     loc_1800112CD
0x1800113e0  lea     rcx, CalcNDim_Data8To16_Lut8
0x1800113e7  jmp     loc_1800112CD
0x1800113ec  cmp     edx, 1
0x1800113ef  jnz     loc_180011349
0x1800113f5  cmp     [r11+8], r9d
0x1800113f9  jz      loc_1800115F8
0x1800113ff  cmp     [r11+8], r8d
0x180011403  jnz     loc_180011349
0x180011409  cmp     [r11+0Ch], r9d
0x18001140d  jz      loc_180011349
0x180011413  cmp     [r11+0Ch], r8d
0x180011417  jnz     loc_180011349
0x18001141d  cmp     [r10+3Ch], r9d
0x180011421  jz      loc_1800115CF
0x180011427  cmp     [r10+3Ch], r8d
0x18001142b  jnz     loc_180011349
0x180011431  cmp     [r10+38h], r8d
0x180011435  jz      loc_1800115C3
0x18001143b  cmp     dword ptr [r10+38h], 20h ; ' '
0x180011440  jnz     loc_180011349
0x180011446  lea     rcx, LHCalc3to4_Di16_Do16_Lut16_G32
0x18001144d  jmp     loc_1800112CD
0x180011452  cmp     [r11+0Ch], r9d
0x180011456  jz      loc_180011760
0x18001145c  cmp     [r11+0Ch], r8d
0x180011460  jnz     loc_1800112CD
0x180011466  cmp     [r10+3Ch], r9d
0x18001146a  jz      loc_180011754
0x180011470  cmp     [r10+3Ch], r8d
0x180011474  jnz     loc_1800112CD
0x18001147a  lea     rcx, CalcNDim_Data8To16_Lut8
0x180011481  jmp     loc_1800112CD
0x180011486  cmp     [r11+0Ch], r9d
0x18001148a  jnz     loc_180011349
0x180011490  cmp     [r10+3Ch], r9d
0x180011494  jz      loc_180011722
0x18001149a  cmp     [r10+3Ch], r8d
0x18001149e  jnz     loc_180011349
0x1800114a4  cmp     dword ptr [r10+38h], 80h
0x1800114ac  jnz     loc_180011349
0x1800114b2  lea     rcx, LHCalc1toX_Di8_Do8_Lut16_G128
0x1800114b9  jmp     loc_1800112CD
0x1800114be  cmp     [r11+0Ch], r9d
0x1800114c2  jz      loc_180011349
0x1800114c8  cmp     [r10+3Ch], r9d
0x1800114cc  jz      loc_180011708
0x1800114d2  cmp     [r10+3Ch], r8d
0x1800114d6  jnz     loc_180011349
0x1800114dc  cmp     dword ptr [r10+38h], 80h
0x1800114e4  jnz     loc_180011349
0x1800114ea  lea     rcx, LHCalc1toX_Di16_Do16_Lut16_G128
0x1800114f1  jmp     loc_1800112CD
0x1800114f6  mov     rdx, r11
0x1800114f9  mov     rcx, r10
0x1800114fc  call    FindLookupRoutine
0x180011501  mov     rcx, rax
0x180011504  test    rax, rax
0x180011507  jnz     loc_1800112CD
0x18001150d  jmp     loc_180011259
0x180011512  cmp     edx, 1
0x180011515  jnz     loc_180011349
0x18001151b  cmp     [r11+8], r9d
0x18001151f  jnz     loc_180011353
0x180011525  cmp     [r11+0Ch], r9d
0x180011529  jnz     loc_180011349
0x18001152f  cmp     [r10+3Ch], r9d
0x180011533  jz      short loc_180011567
0x180011535  cmp     [r10+3Ch], r8d
0x180011539  jnz     loc_180011349
0x18001153f  cmp     [r10+38h], r9d
0x180011543  jz      short loc_18001155B
0x180011545  cmp     [r10+38h], r8d
0x180011549  jnz     loc_180011349
0x18001154f  lea     rcx, LHCalc4to4_Di8_Do8_Lut16_G16
0x180011556  jmp     loc_1800112CD
0x18001155b  lea     rcx, LHCalc4to4_Di8_Do8_Lut16_G8
0x180011562  jmp     loc_1800112CD
0x180011567  cmp     [r10+38h], r9d
0x18001156b  jz      short loc_180011583
0x18001156d  cmp     [r10+38h], r8d
0x180011571  jnz     loc_180011349
0x180011577  lea     rcx, LHCalc4to4_Di8_Do8_Lut8_G16
0x18001157e  jmp     loc_1800112CD
0x180011583  lea     rcx, LHCalc4to4_Di8_Do8_Lut8_G8
0x18001158a  jmp     loc_1800112C8
0x18001158f  lea     rcx, LHCalc4to3_Di8_Do8_Lut16_G8
0x180011596  jmp     loc_1800112CD
0x18001159b  cmp     [r10+38h], r9d
0x18001159f  jz      short loc_1800115B7
0x1800115a1  cmp     [r10+38h], r8d
0x1800115a5  jnz     loc_180011349
0x1800115ab  lea     rcx, LHCalc4to3_Di8_Do8_Lut8_G16
0x1800115b2  jmp     loc_1800112CD
0x1800115b7  lea     rcx, LHCalc4to3_Di8_Do8_Lut8_G8
0x1800115be  jmp     loc_1800112C8
0x1800115c3  lea     rcx, LHCalc3to4_Di16_Do16_Lut16_G16
0x1800115ca  jmp     loc_1800112CD
0x1800115cf  cmp     [r10+38h], r8d
0x1800115d3  jz      short loc_1800115EC
0x1800115d5  cmp     dword ptr [r10+38h], 20h ; ' '
0x1800115da  jnz     loc_180011349
0x1800115e0  lea     rcx, LHCalc3to4_Di16_Do16_Lut8_G32
0x1800115e7  jmp     loc_1800112CD
0x1800115ec  lea     rcx, LHCalc3to4_Di16_Do16_Lut8_G16
0x1800115f3  jmp     loc_1800112C8
0x1800115f8  cmp     [r11+0Ch], r9d
0x1800115fc  jnz     loc_180011349
0x180011602  cmp     [r10+3Ch], r9d
0x180011606  jz      short loc_18001163B
0x180011608  cmp     [r10+3Ch], r8d
0x18001160c  jnz     loc_180011349
0x180011612  cmp     [r10+38h], r8d
0x180011616  jz      short loc_18001162F
0x180011618  cmp     dword ptr [r10+38h], 20h ; ' '
0x18001161d  jnz     loc_180011349
0x180011623  lea     rcx, LHCalc3to4_Di8_Do8_Lut16_G32
0x18001162a  jmp     loc_1800112CD
0x18001162f  lea     rcx, LHCalc3to4_Di8_Do8_Lut16_G16
0x180011636  jmp     loc_1800112CD
0x18001163b  cmp     [r10+38h], r8d
0x18001163f  jz      short loc_18001165C
0x180011641  cmp     dword ptr [r10+38h], 20h ; ' '
0x180011646  jnz     loc_180011349
0x18001164c  lea     rcx, LHCalc3to4_Di8_Do8_Lut8_G32
0x180011653  lea     rax, LHCalc3to4_Di8_Do8_Lut8_G32_Old
0x18001165a  jmp     short loc_1800116DB
0x18001165c  cmp     byte ptr [r11+30h], 0
0x180011661  jnz     short loc_18001166F
0x180011663  lea     rcx, LHCalc3to4_Di8_Do8_Lut8_G16_Old
0x18001166a  jmp     loc_1800112CD
0x18001166f  lea     rcx, LHCalc3to4_Di8_Do8_Lut8_G16
0x180011676  jmp     loc_1800112C8
0x18001167b  lea     rcx, LHCalc3to3_Di16_Do16_Lut16_G16
0x180011682  jmp     loc_1800112CD
0x180011687  cmp     [r10+38h], r8d
0x18001168b  jz      short loc_1800116A4
0x18001168d  cmp     dword ptr [r10+38h], 20h ; ' '
0x180011692  jnz     loc_180011349
0x180011698  lea     rcx, LHCalc3to3_Di16_Do16_Lut8_G32
0x18001169f  jmp     loc_1800112CD
0x1800116a4  lea     rcx, LHCalc3to3_Di16_Do16_Lut8_G16
0x1800116ab  jmp     loc_1800112C8
0x1800116b0  lea     rcx, LHCalc3to3_Di8_Do8_Lut16_G16
0x1800116b7  jmp     loc_1800112CD
0x1800116bc  cmp     [r10+38h], r8d
0x1800116c0  jz      short loc_1800116E9
0x1800116c2  cmp     dword ptr [r10+38h], 20h ; ' '
0x1800116c7  jnz     loc_180011349
0x1800116cd  lea     rcx, LHCalc3to3_Di8_Do8_Lut8_G32
0x1800116d4  lea     rax, LHCalc3to3_Di8_Do8_Lut8_G32_Old
0x1800116db  cmp     byte ptr [r11+30h], 0
0x1800116e0  cmovz   rcx, rax
0x1800116e4  jmp     loc_1800112CD
0x1800116e9  cmp     byte ptr [r11+30h], 0
0x1800116ee  jnz     short loc_1800116FC
0x1800116f0  lea     rcx, LHCalc3to3_Di8_Do8_Lut8_G16_Old
0x1800116f7  jmp     loc_1800112CD
0x1800116fc  lea     rcx, LHCalc3to3_Di8_Do8_Lut8_G16
0x180011703  jmp     loc_1800112C8
0x180011708  cmp     dword ptr [r10+38h], 80h
0x180011710  jnz     loc_180011349
0x180011716  lea     rcx, LHCalc1toX_Di16_Do16_Lut8_G128
0x18001171d  jmp     loc_1800112CD
0x180011722  cmp     dword ptr [r10+38h], 80h
0x18001172a  jnz     loc_180011349
0x180011730  lea     rcx, LHCalc1toX_Di8_Do8_Lut8_G128
0x180011737  jmp     loc_1800112CD
0x18001173c  lea     rcx, CalcNDim_Data8To16_Lut8
0x180011743  jmp     loc_1800112CD
0x180011748  lea     rcx, CalcNDim_Data8To16_Lut8
0x18001174f  jmp     loc_1800112CD
0x180011754  lea     rcx, CalcNDim_Data8To16_Lut8
0x18001175b  jmp     loc_1800112CD
0x180011760  cmp     [r10+3Ch], r9d
0x180011764  jz      short loc_18001177C
0x180011766  cmp     [r10+3Ch], r8d
0x18001176a  jnz     loc_1800112CD
0x180011770  lea     rcx, CalcNDim_Data8To8_Lut16
0x180011777  jmp     loc_1800112CD
0x18001177c  lea     rcx, CalcNDim_Data8To16_Lut8
0x180011783  jmp     loc_1800112CD
```
