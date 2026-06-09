# LongValue::ReadAt(tagColParams *,Err &,ulong *)

- ea: `0x1003e9a0`
- end: `0x1003ec98`
- name: `?ReadAt@LongValue@@QAEKPAUtagColParams@@AAVErr@@PAK@Z`
- size: `760`
- prototype: `unsigned int __thiscall(LongValue *__hidden this, struct tagColParams *, struct Err *, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x10018310`
- `0x10030730`

## callees

- `0x10008180`
- `0x1000eb60`
- `0x10025ee0`
- `0x10026060`
- `0x1003a790`
- `0x1003ab80`
- `0x1003e9a0`
- `0x1003f400`
- `0x1005e7e8`
- `0x1005e7f3`
- `0x1005f07c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1003ec37`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1003ec37`

## pseudocode

```c
unsigned int __thiscall LongValue::ReadAt(LongValue *this, struct tagColParams *a2, struct Err *a3, unsigned int *a4)
{
  int v4; // edi
  char v5; // al
  LongValue *v6; // edi
  unsigned int v7; // esi
  int v8; // esi
  struct Err *v9; // ecx
  LvDataOrig *v10; // esi
  int v11; // edx
  const CHAR *v12; // eax
  _DWORD *v13; // eax
  unsigned int *v14; // edi
  int v15; // eax
  unsigned int v16; // esi
  struct Err *v17; // eax
  int v18; // ecx
  WCHAR *v19; // edx
  int v20; // eax
  int v21; // ecx
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  int v26; // eax
  int v27; // ecx
  int v29; // [esp+Ch] [ebp-24h]
  int v30; // [esp+10h] [ebp-20h]
  WCHAR *Block; // [esp+14h] [ebp-1Ch]
  void *v32; // [esp+18h] [ebp-18h]
  int v33; // [esp+1Ch] [ebp-14h] BYREF
  unsigned int v34; // [esp+20h] [ebp-10h]
  LPCCH lpMultiByteStr; // [esp+24h] [ebp-Ch]
  LongValue *v36; // [esp+28h] [ebp-8h]
  char v37; // [esp+2Fh] [ebp-1h]

  v36 = this;
  v4 = *((_DWORD *)a2 + 5);
  v32 = (void *)*((_DWORD *)a2 + 1);
  lpMultiByteStr = 0;
  v30 = *((_DWORD *)a2 + 2);
  v29 = *((_DWORD *)a2 + 4);
  v5 = (*(int (__thiscall **)(int))(*(_DWORD *)v4 + 16))(v4);
  v6 = v36;
  v7 = 0;
  v37 = v5;
  v34 = 0;
  if ( v5 == 12 )
  {
    if ( *((_DWORD *)a2 + 7) == 1 || !*(_DWORD *)(*((_DWORD *)v36 + 1) + 2084) )
      LvDataOrig::CheckDataHasChanged(*(LvDataOrig **)v36, a2);
    if ( *((_DWORD *)a2 + 7) == 1 || (v8 = *((_DWORD *)v36 + 1), !*(_DWORD *)(v8 + 2084)) )
    {
      v10 = *(LvDataOrig **)v36;
      if ( !*(_DWORD *)(*(_DWORD *)v36 + 2060) )
        LvDataOrig::GetRecordData(v10, (int)a2, 0, a3);
      v9 = a3;
      if ( (*(_BYTE *)a3 & 8) != 0 )
        v7 = 0;
      else
        v7 = *((_DWORD *)v10 + 516);
    }
    else
    {
      v7 = *(_DWORD *)(v8 + 2064);
      v9 = a3;
    }
    if ( (*(_BYTE *)v9 & 8) == 0 )
    {
      v11 = *((_DWORD *)a2 + 4);
      if ( v11 || *((_DWORD *)a2 + 2) )
      {
        v7 *= 2;
        if ( v7 >= v11 + *((_DWORD *)a2 + 2) )
          v7 = v11 + *((_DWORD *)a2 + 2);
      }
      else
      {
        v7 *= 2;
        *((_DWORD *)a2 + 2) = v7;
      }
      if ( v7 )
      {
        v12 = (const CHAR *)operator new[](v7);
        v9 = a3;
        lpMultiByteStr = v12;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v9 = a3;
  }
  v12 = 0;
LABEL_23:
  if ( (*(_BYTE *)v9 & 8) == 0 )
  {
    if ( v37 == 12 )
    {
      *((_DWORD *)a2 + 1) = v12;
      *((_DWORD *)a2 + 2) = v7;
      *((_DWORD *)a2 + 4) = 0;
    }
    if ( *((_DWORD *)a2 + 7) == 1 || (v13 = (_DWORD *)*((_DWORD *)v6 + 1), !v13[521]) )
    {
      v15 = (*(int (__thiscall **)(_DWORD, struct tagColParams *, _DWORD, struct Err *, unsigned int *))(**(_DWORD **)v6 + 4))(
              *(_DWORD *)v6,
              a2,
              0,
              v9,
              a4);
      v14 = a4;
    }
    else
    {
      v14 = a4;
      v15 = (*(int (__thiscall **)(_DWORD *, struct tagColParams *, _DWORD, struct Err *, unsigned int *))(*v13 + 4))(
              v13,
              a2,
              *(_DWORD *)v36,
              v9,
              a4);
    }
    v16 = v15;
    if ( v37 != 12 )
      return v16;
    *((_DWORD *)a2 + 1) = v32;
    *((_DWORD *)a2 + 4) = v29;
    v17 = a3;
    *((_DWORD *)a2 + 2) = v30;
    v18 = *(_DWORD *)a3;
    if ( (*(_DWORD *)a3 & 8) != 0 )
      goto LABEL_64;
    if ( v16 && v30 )
    {
      v33 = v16;
      v19 = (WCHAR *)operator new[](2 * v16);
      Block = v19;
      if ( (*(_DWORD *)a3 & 8) != 0 )
        goto LABEL_64;
      v20 = ErrGenericMultiByteCbToNWide(*(_DWORD *)(*((_DWORD *)v36 + 3) + 44), 0, lpMultiByteStr, v16, v19, (int)&v33);
      if ( v20 >= 0 )
      {
        v22 = *((_DWORD *)a2 + 4);
        v34 = 2 * v33;
        if ( v22 <= 2 * v33 )
        {
          v24 = v33 - (v22 >> 1);
          v23 = *((_DWORD *)a2 + 2) >> 1;
          if ( v23 >= v24 )
            v23 = v24;
        }
        else
        {
          v23 = 0;
        }
        memcpy(v32, (char *)Block + *((_DWORD *)a2 + 4), 2 * v23);
      }
      else
      {
        Err::SetError(a3, v20, v21);
      }
      operator delete[](Block);
      v17 = a3;
      v18 = *(_DWORD *)a3;
    }
    else
    {
      v34 = 0;
    }
    if ( (v18 & 8) != 0 )
    {
LABEL_64:
      if ( lpMultiByteStr )
        operator delete[]((void *)lpMultiByteStr);
      return v16;
    }
    if ( v16 < LongValue::GetSize(v36, a2, v17) )
    {
      if ( v14 )
        *v14 *= 2;
LABEL_63:
      Err::SetWarning(a3, 1006);
      goto LABEL_64;
    }
    v25 = *((_DWORD *)a2 + 4);
    if ( v25 <= v34 && v34 - v25 > *((_DWORD *)a2 + 2) )
    {
      if ( v14 )
        *v14 = v34;
      goto LABEL_63;
    }
    if ( v14 )
    {
      if ( *((_DWORD *)a2 + 2) || !v16 )
      {
        *v14 = v34;
        goto LABEL_61;
      }
      if ( lpMultiByteStr )
      {
        v26 = MultiByteToWideChar(*(_DWORD *)(*((_DWORD *)v36 + 3) + 44), 0, lpMultiByteStr, v16, 0, 0);
        if ( !v26 )
        {
          Err::SetError(a3, -1003, v27);
          goto LABEL_61;
        }
      }
      else
      {
        v26 = 0;
      }
      *v14 = 2 * v26;
    }
LABEL_61:
    if ( *((_DWORD *)a2 + 2) || !v16 )
      goto LABEL_64;
    goto LABEL_63;
  }
  return 0;
}

```

## disassembly

```asm
0x1003e9a0  mov     edi, edi
0x1003e9a2  push    ebp
0x1003e9a3  mov     ebp, esp
0x1003e9a5  sub     esp, 24h
0x1003e9a8  push    ebx
0x1003e9a9  mov     ebx, [ebp+arg_0]
0x1003e9ac  push    esi; unsigned int
0x1003e9ad  push    edi; void *
0x1003e9ae  mov     [ebp+var_8], ecx
0x1003e9b1  mov     eax, [ebx+4]
0x1003e9b4  mov     edi, [ebx+14h]
0x1003e9b7  mov     [ebp+var_18], eax
0x1003e9ba  xor     eax, eax
0x1003e9bc  mov     [ebp+lpMultiByteStr], eax
0x1003e9bf  mov     eax, [ebx+8]
0x1003e9c2  mov     [ebp+var_20], eax
0x1003e9c5  mov     eax, [ebx+10h]
0x1003e9c8  mov     [ebp+var_24], eax
0x1003e9cb  mov     eax, [edi]
0x1003e9cd  mov     esi, [eax+10h]
0x1003e9d0  mov     ecx, esi
0x1003e9d2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003e9d8  mov     ecx, edi
0x1003e9da  call    esi
0x1003e9dc  mov     edi, [ebp+var_8]
0x1003e9df  xor     edx, edx
0x1003e9e1  xor     esi, esi
0x1003e9e3  mov     [ebp+var_1], al
0x1003e9e6  mov     [ebp+var_10], edx
0x1003e9e9  cmp     al, 0Ch
0x1003e9eb  jnz     loc_1003EA8A
0x1003e9f1  cmp     dword ptr [ebx+1Ch], 1
0x1003e9f5  jz      short loc_1003EA02
0x1003e9f7  mov     eax, [edi+4]
0x1003e9fa  cmp     [eax+824h], edx
0x1003ea00  jnz     short loc_1003EA0A
0x1003ea02  mov     ecx, [edi]; this
0x1003ea04  push    ebx; struct tagColParams *
0x1003ea05  call    ?CheckDataHasChanged@LvDataOrig@@QAEXPAUtagColParams@@@Z; LvDataOrig::CheckDataHasChanged(tagColParams *)
0x1003ea0a  cmp     dword ptr [ebx+1Ch], 1
0x1003ea0e  jz      short loc_1003EA27
0x1003ea10  mov     esi, [edi+4]
0x1003ea13  cmp     dword ptr [esi+824h], 0
0x1003ea1a  jz      short loc_1003EA27
0x1003ea1c  mov     esi, [esi+810h]
0x1003ea22  mov     ecx, [ebp+arg_4]
0x1003ea25  jmp     short loc_1003EA51
0x1003ea27  mov     esi, [edi]
0x1003ea29  cmp     dword ptr [esi+80Ch], 0
0x1003ea30  jnz     short loc_1003EA3F
0x1003ea32  push    [ebp+arg_4]
0x1003ea35  mov     ecx, esi
0x1003ea37  push    0
0x1003ea39  push    ebx
0x1003ea3a  call    ?GetRecordData@LvDataOrig@@QAEXPAUtagColParams@@W4LvNullWarningAction@@AAVErr@@@Z; LvDataOrig::GetRecordData(tagColParams *,LvNullWarningAction,Err &)
0x1003ea3f  mov     ecx, [ebp+arg_4]
0x1003ea42  test    byte ptr [ecx], 8
0x1003ea45  jnz     short loc_1003EA4F
0x1003ea47  mov     esi, [esi+810h]
0x1003ea4d  jmp     short loc_1003EA51
0x1003ea4f  xor     esi, esi
0x1003ea51  test    byte ptr [ecx], 8
0x1003ea54  jnz     short loc_1003EA8D
0x1003ea56  mov     edx, [ebx+10h]
0x1003ea59  test    edx, edx
0x1003ea5b  jnz     short loc_1003EA69
0x1003ea5d  cmp     [ebx+8], edx
0x1003ea60  jnz     short loc_1003EA69
0x1003ea62  add     esi, esi
0x1003ea64  mov     [ebx+8], esi
0x1003ea67  jmp     short loc_1003EA75
0x1003ea69  mov     eax, [ebx+8]
0x1003ea6c  add     esi, esi
0x1003ea6e  add     eax, edx
0x1003ea70  cmp     esi, eax
0x1003ea72  cmovnb  esi, eax
0x1003ea75  test    esi, esi
0x1003ea77  jz      short loc_1003EA8D
0x1003ea79  push    esi; unsigned int
0x1003ea7a  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1003ea7f  mov     ecx, [ebp+arg_4]
0x1003ea82  add     esp, 4
0x1003ea85  mov     [ebp+lpMultiByteStr], eax
0x1003ea88  jmp     short loc_1003EA8F
0x1003ea8a  mov     ecx, [ebp+arg_4]
0x1003ea8d  xor     eax, eax
0x1003ea8f  test    byte ptr [ecx], 8
0x1003ea92  jnz     loc_1003EC8D
0x1003ea98  cmp     [ebp+var_1], 0Ch
0x1003ea9c  jnz     short loc_1003EAAB
0x1003ea9e  mov     [ebx+4], eax
0x1003eaa1  mov     [ebx+8], esi
0x1003eaa4  mov     dword ptr [ebx+10h], 0
0x1003eaab  cmp     dword ptr [ebx+1Ch], 1
0x1003eaaf  jz      short loc_1003EADF
0x1003eab1  mov     eax, [edi+4]
0x1003eab4  mov     [ebp+Block], eax
0x1003eab7  cmp     dword ptr [eax+824h], 0
0x1003eabe  jz      short loc_1003EADF
0x1003eac0  mov     eax, [eax]
0x1003eac2  mov     edi, [ebp+arg_8]
0x1003eac5  push    edi
0x1003eac6  push    ecx
0x1003eac7  mov     esi, [eax+4]
0x1003eaca  mov     ecx, esi
0x1003eacc  mov     eax, [ebp+var_8]
0x1003eacf  push    dword ptr [eax]; unsigned int
0x1003ead1  push    ebx; void *
0x1003ead2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003ead8  mov     ecx, [ebp+Block]
0x1003eadb  call    esi
0x1003eadd  jmp     short loc_1003EAFC
0x1003eadf  mov     edi, [edi]
0x1003eae1  push    [ebp+arg_8]
0x1003eae4  push    ecx
0x1003eae5  mov     eax, [edi]
0x1003eae7  push    0; unsigned int
0x1003eae9  push    ebx; void *
0x1003eaea  mov     esi, [eax+4]
0x1003eaed  mov     ecx, esi
0x1003eaef  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003eaf5  mov     ecx, edi
0x1003eaf7  call    esi
0x1003eaf9  mov     edi, [ebp+arg_8]
0x1003eafc  cmp     [ebp+var_1], 0Ch
0x1003eb00  mov     esi, eax
0x1003eb02  jnz     loc_1003EC82
0x1003eb08  mov     eax, [ebp+var_18]
0x1003eb0b  mov     edx, [ebp+var_20]
0x1003eb0e  mov     [ebx+4], eax
0x1003eb11  mov     eax, [ebp+var_24]
0x1003eb14  mov     [ebx+10h], eax
0x1003eb17  mov     eax, [ebp+arg_4]
0x1003eb1a  mov     [ebx+8], edx
0x1003eb1d  mov     ecx, [eax]
0x1003eb1f  test    cl, 8
0x1003eb22  jnz     loc_1003EC72
0x1003eb28  test    esi, esi
0x1003eb2a  jz      loc_1003EBCD
0x1003eb30  test    edx, edx
0x1003eb32  jz      loc_1003EBCD
0x1003eb38  lea     eax, [esi+esi]
0x1003eb3b  mov     [ebp+var_14], esi
0x1003eb3e  push    eax; unsigned int
0x1003eb3f  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1003eb44  mov     edx, eax
0x1003eb46  add     esp, 4
0x1003eb49  mov     eax, [ebp+arg_4]
0x1003eb4c  mov     [ebp+Block], edx
0x1003eb4f  mov     ecx, [eax]
0x1003eb51  test    cl, 8
0x1003eb54  jnz     loc_1003EC72
0x1003eb5a  lea     eax, [ebp+var_14]
0x1003eb5d  push    eax; int
0x1003eb5e  mov     eax, [ebp+lpMultiByteStr]
0x1003eb61  push    edx; lpWideCharStr
0x1003eb62  push    esi; cbMultiByte
0x1003eb63  push    eax; lpMultiByteStr
0x1003eb64  mov     eax, [ebp+var_8]
0x1003eb67  xor     edx, edx; dwFlags
0x1003eb69  mov     ecx, [eax+0Ch]
0x1003eb6c  mov     ecx, [ecx+2Ch]; CodePage
0x1003eb6f  call    _ErrGenericMultiByteCbToNWide@24; ErrGenericMultiByteCbToNWide(x,x,x,x,x,x)
0x1003eb74  test    eax, eax
0x1003eb76  jns     short loc_1003EB84
0x1003eb78  push    ecx
0x1003eb79  mov     ecx, [ebp+arg_4]
0x1003eb7c  push    eax
0x1003eb7d  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1003eb82  jmp     short loc_1003EBBB
0x1003eb84  mov     ecx, [ebp+var_14]
0x1003eb87  mov     eax, [ebx+10h]
0x1003eb8a  lea     edx, [ecx+ecx]
0x1003eb8d  mov     [ebp+var_10], edx
0x1003eb90  cmp     eax, edx
0x1003eb92  jbe     short loc_1003EB98
0x1003eb94  xor     eax, eax
0x1003eb96  jmp     short loc_1003EBA6
0x1003eb98  shr     eax, 1
0x1003eb9a  sub     ecx, eax
0x1003eb9c  mov     eax, [ebx+8]
0x1003eb9f  shr     eax, 1
0x1003eba1  cmp     eax, ecx
0x1003eba3  cmovnb  eax, ecx
0x1003eba6  add     eax, eax
0x1003eba8  push    eax; Size
0x1003eba9  mov     eax, [ebp+Block]
0x1003ebac  add     eax, [ebx+10h]
0x1003ebaf  push    eax; Src
0x1003ebb0  push    [ebp+var_18]; void *
0x1003ebb3  call    _memcpy
0x1003ebb8  add     esp, 0Ch
0x1003ebbb  push    [ebp+Block]; Block
0x1003ebbe  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003ebc3  mov     eax, [ebp+arg_4]
0x1003ebc6  add     esp, 4
0x1003ebc9  mov     ecx, [eax]
0x1003ebcb  jmp     short loc_1003EBD2
0x1003ebcd  xor     edx, edx
0x1003ebcf  mov     [ebp+var_10], edx
0x1003ebd2  test    cl, 8
0x1003ebd5  jnz     loc_1003EC72
0x1003ebdb  mov     ecx, [ebp+var_8]; this
0x1003ebde  push    eax; struct Err *
0x1003ebdf  push    ebx; struct tagColParams *
0x1003ebe0  call    ?GetSize@LongValue@@QAEKPAUtagColParams@@AAVErr@@@Z; LongValue::GetSize(tagColParams *,Err &)
0x1003ebe5  cmp     esi, eax
0x1003ebe7  jnb     short loc_1003EBF5
0x1003ebe9  test    edi, edi
0x1003ebeb  jz      short loc_1003EC65
0x1003ebed  mov     eax, [edi]
0x1003ebef  add     eax, eax
0x1003ebf1  mov     [edi], eax
0x1003ebf3  jmp     short loc_1003EC65
0x1003ebf5  mov     ecx, [ebx+10h]
0x1003ebf8  mov     edx, [ebp+var_10]
0x1003ebfb  cmp     ecx, edx
0x1003ebfd  ja      short loc_1003EC10
0x1003ebff  mov     eax, edx
0x1003ec01  sub     eax, ecx
0x1003ec03  cmp     eax, [ebx+8]
0x1003ec06  jbe     short loc_1003EC10
0x1003ec08  test    edi, edi
0x1003ec0a  jz      short loc_1003EC65
0x1003ec0c  mov     [edi], edx
0x1003ec0e  jmp     short loc_1003EC65
0x1003ec10  test    edi, edi
0x1003ec12  jz      short loc_1003EC5B
0x1003ec14  cmp     dword ptr [ebx+8], 0
0x1003ec18  jnz     short loc_1003EC59
0x1003ec1a  test    esi, esi
0x1003ec1c  jz      short loc_1003EC59
0x1003ec1e  mov     eax, [ebp+var_8]
0x1003ec21  mov     eax, [eax+0Ch]
0x1003ec24  mov     ecx, [eax+2Ch]
0x1003ec27  mov     eax, [ebp+lpMultiByteStr]
0x1003ec2a  test    eax, eax
0x1003ec2c  jz      short loc_1003EC51
0x1003ec2e  push    0; cchWideChar
0x1003ec30  push    0; lpWideCharStr
0x1003ec32  push    esi; cbMultiByte
0x1003ec33  push    eax; lpMultiByteStr
0x1003ec34  push    0; dwFlags
0x1003ec36  push    ecx; CodePage
0x1003ec37  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x1003ec3d  test    eax, eax
0x1003ec3f  jnz     short loc_1003EC53
0x1003ec41  push    ecx
0x1003ec42  mov     ecx, [ebp+arg_4]
0x1003ec45  push    0FFFFFC15h
0x1003ec4a  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1003ec4f  jmp     short loc_1003EC5B
0x1003ec51  xor     eax, eax
0x1003ec53  add     eax, eax
0x1003ec55  mov     [edi], eax
0x1003ec57  jmp     short loc_1003EC5B
0x1003ec59  mov     [edi], edx
0x1003ec5b  cmp     dword ptr [ebx+8], 0
0x1003ec5f  jnz     short loc_1003EC72
0x1003ec61  test    esi, esi
0x1003ec63  jz      short loc_1003EC72
0x1003ec65  mov     ecx, [ebp+arg_4]; this
0x1003ec68  push    3EEh; int
0x1003ec6d  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x1003ec72  mov     eax, [ebp+lpMultiByteStr]
0x1003ec75  test    eax, eax
0x1003ec77  jz      short loc_1003EC82
0x1003ec79  push    eax; Block
0x1003ec7a  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003ec7f  add     esp, 4
0x1003ec82  pop     edi
0x1003ec83  mov     eax, esi
0x1003ec85  pop     esi
0x1003ec86  pop     ebx
0x1003ec87  mov     esp, ebp
0x1003ec89  pop     ebp
0x1003ec8a  retn    0Ch
0x1003ec8d  pop     edi
0x1003ec8e  pop     esi
0x1003ec8f  xor     eax, eax
0x1003ec91  pop     ebx
0x1003ec92  mov     esp, ebp
0x1003ec94  pop     ebp
0x1003ec95  retn    0Ch
```
