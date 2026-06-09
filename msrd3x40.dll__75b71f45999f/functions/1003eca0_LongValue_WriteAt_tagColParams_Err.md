# LongValue::WriteAt(tagColParams *,Err &)

- ea: `0x1003eca0`
- end: `0x1003ee04`
- name: `?WriteAt@LongValue@@QAEKPAUtagColParams@@AAVErr@@@Z`
- size: `356`
- prototype: `unsigned int __thiscall(LongValue *__hidden this, struct tagColParams *, struct Err *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x10018370`
- `0x10030950`

## callees

- `0x10008260`
- `0x1000eb60`
- `0x10025ee0`
- `0x1003c070`
- `0x1003eca0`
- `0x1005e7e8`
- `0x1005e7f3`

## pseudocode

```c
int __thiscall LongValue::WriteAt(LongValue *this, struct tagColParams *a2, void **a3)
{
  int v3; // ecx
  int v4; // edi
  char v5; // al
  int v6; // ecx
  LongValue *v7; // esi
  int v8; // eax
  int v9; // eax
  CHAR *v10; // edx
  unsigned int v11; // ecx
  int v12; // eax
  int v13; // ecx
  int v14; // esi
  int v16; // [esp-8h] [ebp-30h]
  int v17; // [esp-4h] [ebp-2Ch]
  CHAR *Block; // [esp+Ch] [ebp-1Ch]
  int v19; // [esp+10h] [ebp-18h]
  const WCHAR *lpWideCharStr; // [esp+14h] [ebp-14h]
  int v21; // [esp+18h] [ebp-10h] BYREF
  int v22; // [esp+1Ch] [ebp-Ch]
  LongValue *v23; // [esp+20h] [ebp-8h]
  char v24; // [esp+27h] [ebp-1h]

  v23 = this;
  v3 = *((_DWORD *)a2 + 2);
  v4 = *((_DWORD *)a2 + 5);
  lpWideCharStr = (const WCHAR *)*((_DWORD *)a2 + 1);
  v22 = *((_DWORD *)a2 + 4);
  Block = 0;
  v21 = 2 * v3;
  v19 = v3;
  v5 = (*(int (__thiscall **)(int))(*(_DWORD *)v4 + 16))(v4);
  v7 = v23;
  v24 = v5;
  if ( v5 == 12 )
  {
    v8 = *(_DWORD *)(*((_DWORD *)v23 + 3) + 44);
    if ( v8 != 950 && v8 != 936 && v8 != 932 && v8 != 949 )
      goto LABEL_11;
    v9 = *((_DWORD *)v23 + 1);
    if ( *(_DWORD *)(v9 + 2060) )
    {
      if ( v22 == 2 * *(_DWORD *)(v9 + 2064) )
      {
LABEL_11:
        v5 = v24;
        goto LABEL_12;
      }
    }
    else if ( !v22 )
    {
      goto LABEL_11;
    }
    Err::SetError(a3, -1001, v6);
    goto LABEL_11;
  }
LABEL_12:
  if ( (*(_BYTE *)a3 & 8) != 0 || v5 != 12 )
  {
    v10 = 0;
  }
  else
  {
    v10 = (CHAR *)operator new[](2 * v19);
    Block = v10;
  }
  if ( (*(_BYTE *)a3 & 8) != 0 )
    return 0;
  if ( v24 == 12 )
  {
    *((_DWORD *)a2 + 4) >>= 1;
    v11 = *((_DWORD *)a2 + 2);
    *((_DWORD *)a2 + 1) = v10;
    v12 = ErrGenericWideNToCbMultiByte(
            *(_DWORD *)(*((_DWORD *)v7 + 3) + 44),
            lpWideCharStr,
            v11 >> 1,
            v10,
            (int)&v21,
            v16,
            v17);
    if ( v12 >= 0 )
      *((_DWORD *)a2 + 2) = v21;
    else
      Err::SetError(a3, v12, v13);
  }
  v14 = 0;
  if ( (*(_BYTE *)a3 & 8) == 0 && *((_DWORD *)a2 + 2) )
    v14 = LvDataNew::WriteAt(*((LvDataNew **)v23 + 1), a2, *(struct LvDataOrig **)v23, a3);
  if ( v24 == 12 )
  {
    *((_DWORD *)a2 + 1) = lpWideCharStr;
    *((_DWORD *)a2 + 2) = v19;
    *((_DWORD *)a2 + 4) = v22;
    if ( Block )
      operator delete[](Block);
  }
  return v14;
}

```

## disassembly

```asm
0x1003eca0  mov     edi, edi
0x1003eca2  push    ebp
0x1003eca3  mov     ebp, esp
0x1003eca5  sub     esp, 1Ch
0x1003eca8  push    ebx
0x1003eca9  mov     ebx, [ebp+arg_0]
0x1003ecac  mov     [ebp+var_8], ecx
0x1003ecaf  push    esi; unsigned int
0x1003ecb0  push    edi; void *
0x1003ecb1  mov     eax, [ebx+4]
0x1003ecb4  mov     ecx, [ebx+8]
0x1003ecb7  mov     edi, [ebx+14h]
0x1003ecba  mov     [ebp+lpWideCharStr], eax
0x1003ecbd  mov     eax, [ebx+10h]
0x1003ecc0  mov     [ebp+var_C], eax
0x1003ecc3  xor     eax, eax
0x1003ecc5  mov     [ebp+Block], eax
0x1003ecc8  lea     eax, [ecx+ecx]
0x1003eccb  mov     [ebp+var_10], eax
0x1003ecce  mov     eax, [edi]
0x1003ecd0  mov     [ebp+var_18], ecx
0x1003ecd3  mov     esi, [eax+10h]
0x1003ecd6  mov     ecx, esi
0x1003ecd8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003ecde  mov     ecx, edi
0x1003ece0  call    esi
0x1003ece2  mov     edi, [ebp+arg_4]
0x1003ece5  mov     esi, [ebp+var_8]
0x1003ece8  mov     [ebp+var_1], al
0x1003eceb  cmp     al, 0Ch
0x1003eced  jnz     short loc_1003ED42
0x1003ecef  mov     eax, [esi+0Ch]
0x1003ecf2  mov     eax, [eax+2Ch]
0x1003ecf5  cmp     eax, 3B6h
0x1003ecfa  jz      short loc_1003ED11
0x1003ecfc  cmp     eax, 3A8h
0x1003ed01  jz      short loc_1003ED11
0x1003ed03  cmp     eax, 3A4h
0x1003ed08  jz      short loc_1003ED11
0x1003ed0a  cmp     eax, 3B5h
0x1003ed0f  jnz     short loc_1003ED3F
0x1003ed11  mov     eax, [esi+4]
0x1003ed14  cmp     dword ptr [eax+80Ch], 0
0x1003ed1b  jnz     short loc_1003ED25
0x1003ed1d  cmp     [ebp+var_C], 0
0x1003ed21  jnz     short loc_1003ED32
0x1003ed23  jmp     short loc_1003ED3F
0x1003ed25  mov     eax, [eax+810h]
0x1003ed2b  add     eax, eax
0x1003ed2d  cmp     [ebp+var_C], eax
0x1003ed30  jz      short loc_1003ED3F
0x1003ed32  push    ecx; int
0x1003ed33  push    0FFFFFC17h; int
0x1003ed38  mov     ecx, edi
0x1003ed3a  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1003ed3f  mov     al, [ebp+var_1]
0x1003ed42  test    byte ptr [edi], 8
0x1003ed45  jnz     short loc_1003ED61
0x1003ed47  cmp     al, 0Ch
0x1003ed49  jnz     short loc_1003ED61
0x1003ed4b  mov     ecx, [ebp+var_18]
0x1003ed4e  lea     eax, [ecx+ecx]
0x1003ed51  push    eax; unsigned int
0x1003ed52  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1003ed57  mov     edx, eax
0x1003ed59  add     esp, 4
0x1003ed5c  mov     [ebp+Block], edx
0x1003ed5f  jmp     short loc_1003ED63
0x1003ed61  xor     edx, edx
0x1003ed63  test    byte ptr [edi], 8
0x1003ed66  jnz     loc_1003EDF9
0x1003ed6c  cmp     [ebp+var_1], 0Ch
0x1003ed70  jnz     short loc_1003EDA9
0x1003ed72  shr     dword ptr [ebx+10h], 1
0x1003ed75  sub     esp, 8
0x1003ed78  mov     ecx, [ebx+8]
0x1003ed7b  mov     [ebx+4], edx
0x1003ed7e  mov     eax, [esi+0Ch]
0x1003ed81  lea     esi, [ebp+var_10]
0x1003ed84  push    esi; int
0x1003ed85  shr     ecx, 1
0x1003ed87  push    edx; lpMultiByteStr
0x1003ed88  push    ecx; cchWideChar
0x1003ed89  push    [ebp+lpWideCharStr]; lpWideCharStr
0x1003ed8c  mov     ecx, [eax+2Ch]; CodePage
0x1003ed8f  call    _ErrGenericWideNToCbMultiByte@32; ErrGenericWideNToCbMultiByte(x,x,x,x,x,x,x,x)
0x1003ed94  test    eax, eax
0x1003ed96  jns     short loc_1003EDA3
0x1003ed98  push    ecx
0x1003ed99  push    eax
0x1003ed9a  mov     ecx, edi
0x1003ed9c  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1003eda1  jmp     short loc_1003EDA9
0x1003eda3  mov     eax, [ebp+var_10]
0x1003eda6  mov     [ebx+8], eax
0x1003eda9  xor     esi, esi
0x1003edab  test    byte ptr [edi], 8
0x1003edae  jnz     short loc_1003EDC6
0x1003edb0  cmp     [ebx+8], esi
0x1003edb3  jz      short loc_1003EDC6
0x1003edb5  mov     ecx, [ebp+var_8]
0x1003edb8  push    edi; struct Err *
0x1003edb9  push    dword ptr [ecx]; struct LvDataOrig *
0x1003edbb  mov     ecx, [ecx+4]; this
0x1003edbe  push    ebx; struct tagColParams *
0x1003edbf  call    ?WriteAt@LvDataNew@@QAEKPAUtagColParams@@PAVLvDataOrig@@AAVErr@@@Z; LvDataNew::WriteAt(tagColParams *,LvDataOrig *,Err &)
0x1003edc4  mov     esi, eax
0x1003edc6  cmp     [ebp+var_1], 0Ch
0x1003edca  jnz     short loc_1003EDEE
0x1003edcc  mov     eax, [ebp+lpWideCharStr]
0x1003edcf  mov     [ebx+4], eax
0x1003edd2  mov     eax, [ebp+var_18]
0x1003edd5  mov     [ebx+8], eax
0x1003edd8  mov     eax, [ebp+var_C]
0x1003eddb  mov     [ebx+10h], eax
0x1003edde  mov     eax, [ebp+Block]
0x1003ede1  test    eax, eax
0x1003ede3  jz      short loc_1003EDEE
0x1003ede5  push    eax; Block
0x1003ede6  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003edeb  add     esp, 4
0x1003edee  pop     edi
0x1003edef  mov     eax, esi
0x1003edf1  pop     esi
0x1003edf2  pop     ebx
0x1003edf3  mov     esp, ebp
0x1003edf5  pop     ebp
0x1003edf6  retn    8
0x1003edf9  pop     edi
0x1003edfa  pop     esi
0x1003edfb  xor     eax, eax
0x1003edfd  pop     ebx
0x1003edfe  mov     esp, ebp
0x1003ee00  pop     ebp
0x1003ee01  retn    8
```
