# Table::RenameIndex(Instance *,ushort const *,ushort const *,Err &,TblRefOrIdx)

- ea: `0x10055bc0`
- end: `0x10055ebb`
- name: `?RenameIndex@Table@@QAEXPAVInstance@@PBG1AAVErr@@W4TblRefOrIdx@@@Z`
- size: `763`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x10029b70`
- `0x1002a0c0`
- `0x10056280`

## callees

- `0x10012dd0`
- `0x10025ee0`
- `0x10031a90`
- `0x10031c70`
- `0x100358c0`
- `0x1004dbb0`
- `0x10051890`
- `0x10055bc0`
- `0x10057150`
- `0x100574a0`
- `0x10057520`
- `0x1005e3b0`
- `0x1005f064`
- `0x1005f07c`
- `0x1005f4cd`

## pseudocode

```c
void __thiscall Table::RenameIndex(
        _DWORD *this,
        struct Instance *a2,
        char *a3,
        const unsigned __int16 *Src,
        struct Err *a5,
        int a6)
{
  Collection *v7; // ebx
  bool v8; // zf
  int v9; // eax
  int v10; // eax
  struct Err *v11; // esi
  int v12; // edx
  int v13; // ebx
  char *v14; // ecx
  __int16 v15; // ax
  int v16; // ecx
  int IndexOrRef; // ecx
  struct Instance *v18; // ecx
  Index *v19; // eax
  Index *v20; // edx
  Collection *v21; // eax
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  int v24; // eax
  const unsigned __int16 *v25; // esi
  size_t v27; // esi
  struct Instance *v28; // ecx
  int v29; // ecx
  struct Instance *v30; // ecx
  int v31; // eax
  int v32; // [esp-8h] [ebp-58h]
  _DWORD *v33; // [esp-4h] [ebp-54h]
  _DWORD v34[3]; // [esp+10h] [ebp-40h] BYREF
  __int16 v35; // [esp+1Ch] [ebp-34h]
  int v36; // [esp+20h] [ebp-30h]
  int v37; // [esp+24h] [ebp-2Ch]
  _DWORD *v38; // [esp+28h] [ebp-28h]
  const unsigned __int16 *v39; // [esp+2Ch] [ebp-24h]
  Collection *v40; // [esp+30h] [ebp-20h] BYREF
  Index *v41; // [esp+34h] [ebp-1Ch]
  Collection *v42; // [esp+38h] [ebp-18h] BYREF
  int IndexFromName; // [esp+3Ch] [ebp-14h]
  struct Instance *v44; // [esp+40h] [ebp-10h]
  int v45; // [esp+4Ch] [ebp-4h]

  ++this[85];
  v38 = this;
  v45 = 0;
  v7 = 0;
  v8 = this[11] == 2;
  v40 = 0;
  v42 = 0;
  IndexFromName = 0;
  if ( !v8 && this[12] != 8 )
  {
    v33 = this;
    v32 = -1309;
LABEL_8:
    v11 = a5;
    Err::SetError(a5, v32, v33);
    v44 = (struct Instance *)(this + 9);
    goto LABEL_9;
  }
  v9 = this[9];
  v44 = (struct Instance *)(this + 9);
  v10 = *(_DWORD *)(v9 + 104);
  if ( !v10 || v10 == 3 )
  {
    v33 = this + 9;
    v32 = -1809;
    goto LABEL_8;
  }
  v11 = a5;
LABEL_9:
  if ( (*(_BYTE *)v11 & 8) != 0 )
    goto LABEL_19;
  IndexFromName = Table::FindIndexFromName((Table *)this, Src, (int *)&v42);
  if ( IndexFromName != -1 )
  {
    v12 = *(_DWORD *)v44;
    v13 = *(_DWORD *)(*(_DWORD *)v44 + 224);
    if ( !v13 )
      v13 = *(unsigned __int16 *)(v12 + 86);
    v14 = a3;
    v41 = (Index *)(a3 + 2);
    do
    {
      v15 = *(_WORD *)v14;
      v14 += 2;
    }
    while ( v15 );
    v34[0] = a3;
    v36 = v13;
    v37 = 0;
    v34[1] = 2 * ((v14 - (char *)v41) >> 1);
    v34[2] = *(_DWORD *)(v12 + 92);
    v35 = *(_WORD *)(*(_DWORD *)(v12 + 60) + 100);
    if ( LString::Compare(v34, Src, 2 * wcslen(Src), 0) )
      Err::SetError(v11, -1403, v16);
  }
  v7 = v42;
  if ( (*(_BYTE *)v11 & 8) != 0 )
  {
LABEL_19:
    IndexOrRef = IndexFromName;
  }
  else
  {
    IndexOrRef = Table::FindIndexOrRef(this, a3, &v40, a6, v11);
    IndexFromName = IndexOrRef;
  }
  if ( (*(_BYTE *)v11 & 8) == 0 )
  {
    v18 = (struct Instance *)this[IndexOrRef + 349];
    v44 = v18;
    v39 = *(const unsigned __int16 **)(*((_DWORD *)a2 + 3) + 56);
    if ( (int)v39 <= *((_DWORD *)v18 + 3) )
    {
LABEL_29:
      v24 = *(_DWORD *)v11;
      if ( (*(_DWORD *)v11 & 8) == 0 )
      {
        v25 = Src;
        v39 = Src + 1;
        while ( *v25++ )
          ;
        v27 = 2 * (v25 - v39);
        memcpy(*(void **)v18, Src, v27);
        v28 = v44;
        *(_WORD *)(v27 + *(_DWORD *)v44) = 0;
        *((_DWORD *)v28 + 1) = v27;
        v11 = a5;
        v24 = *(_DWORD *)a5;
      }
      if ( (int)v7 > (int)v40 )
        v7 = (Collection *)((char *)v7 - 1);
      if ( (v24 & 8) == 0 && v40 != v7 )
      {
        memcpy(&this[(_DWORD)v40 + 381], &this[(_DWORD)v40 + 382], 4 * (this[6] - (_DWORD)v40) - 4);
        this[this[6] + 380] = -1;
        v29 = this[6];
        if ( v7 != (Collection *)(v29 - 1) )
          memmove(&this[(_DWORD)v7 + 382], &this[(_DWORD)v7 + 381], 4 * (v29 - (_DWORD)v7) - 4);
        this[(_DWORD)v7 + 381] = IndexFromName;
      }
      if ( (*(_BYTE *)v11 & 8) == 0 )
        Table::DDLPerformed((Table *)this, a2);
      goto LABEL_42;
    }
    v19 = Index::Clone(v18, v11);
    v8 = (*(_BYTE *)v11 & 8) == 0;
    v41 = v19;
    if ( !v8 )
    {
LABEL_28:
      v18 = v44;
      goto LABEL_29;
    }
    Session::DropInstance(*((Session **)v44 + 2), v44);
    v20 = v41;
    v21 = (Collection *)*((_DWORD *)v41 + 2);
    v42 = v21;
    v22 = *((_DWORD *)v21 + 2);
    if ( v22 >= *((_DWORD *)v21 + 1) )
    {
      Collection::Grow(v42, v22 + 1, v11);
      v20 = v41;
      if ( (*(_BYTE *)v11 & 8) != 0 )
      {
LABEL_27:
        Index::`scalar deleting destructor'(v20, v23);
        goto LABEL_28;
      }
      v21 = v42;
    }
    v23 = *((_DWORD *)v21 + 2);
    *(_DWORD *)(*(_DWORD *)v21 + 4 * v23) = v20;
    ++*((_DWORD *)v42 + 2);
    if ( (*(_BYTE *)v11 & 8) == 0 )
    {
      v30 = v44;
      *((_DWORD *)v20 + 3) = v39;
      v31 = IndexFromName;
      *((_DWORD *)v20 + 5) = v30;
      v18 = v20;
      v44 = v20;
      this[v31 + 349] = v20;
      goto LABEL_29;
    }
    goto LABEL_27;
  }
LABEL_42:
  --this[85];
}

```

## disassembly

```asm
0x10055bc0  mov     edi, edi
0x10055bc2  push    ebp
0x10055bc3  mov     ebp, esp
0x10055bc5  push    0FFFFFFFFh
0x10055bc7  push    offset ?RenameIndex@Table@@QAEXPAVInstance@@PBG1AAVErr@@W4TblRefOrIdx@@@Z_SEH
0x10055bcc  mov     eax, large fs:0
0x10055bd2  push    eax
0x10055bd3  sub     esp, 34h
0x10055bd6  push    ebx
0x10055bd7  push    esi
0x10055bd8  push    edi
0x10055bd9  mov     eax, ___security_cookie
0x10055bde  xor     eax, ebp
0x10055be0  push    eax
0x10055be1  lea     eax, [ebp+var_C]
0x10055be4  mov     large fs:0, eax
0x10055bea  mov     edi, ecx
0x10055bec  inc     dword ptr [edi+154h]
0x10055bf2  mov     [ebp+var_28], edi
0x10055bf5  mov     [ebp+var_4], 0
0x10055bfc  xor     ebx, ebx
0x10055bfe  cmp     dword ptr [edi+2Ch], 2
0x10055c02  mov     [ebp+var_20], 0
0x10055c09  mov     [ebp+var_18], ebx
0x10055c0c  mov     [ebp+var_14], ebx
0x10055c0f  jz      short loc_10055C1F
0x10055c11  cmp     dword ptr [edi+30h], 8
0x10055c15  jz      short loc_10055C1F
0x10055c17  push    ecx
0x10055c18  push    0FFFFFAE3h
0x10055c1d  jmp     short loc_10055C3F
0x10055c1f  mov     eax, [edi+24h]
0x10055c22  lea     ecx, [edi+24h]
0x10055c25  mov     [ebp+var_10], ecx
0x10055c28  mov     eax, [eax+68h]
0x10055c2b  test    eax, eax
0x10055c2d  jz      short loc_10055C39
0x10055c2f  cmp     eax, 3
0x10055c32  jz      short loc_10055C39
0x10055c34  mov     esi, [ebp+arg_C]
0x10055c37  jmp     short loc_10055C4F
0x10055c39  push    ecx
0x10055c3a  push    0FFFFF8EFh
0x10055c3f  mov     esi, [ebp+arg_C]
0x10055c42  mov     ecx, esi
0x10055c44  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10055c49  lea     eax, [edi+24h]
0x10055c4c  mov     [ebp+var_10], eax
0x10055c4f  test    byte ptr [esi], 8
0x10055c52  jnz     loc_10055D20
0x10055c58  lea     eax, [ebp+var_18]
0x10055c5b  mov     ecx, edi; this
0x10055c5d  push    eax; int *
0x10055c5e  push    [ebp+Src]; unsigned __int16 *
0x10055c61  call    ?FindIndexFromName@Table@@QAEJPBGPAJ@Z; Table::FindIndexFromName(ushort const *,long *)
0x10055c66  mov     [ebp+var_14], eax
0x10055c69  cmp     eax, 0FFFFFFFFh
0x10055c6c  jz      loc_10055CFF
0x10055c72  mov     ecx, [ebp+var_10]
0x10055c75  mov     edx, [ecx]
0x10055c77  mov     ebx, [edx+0E0h]
0x10055c7d  test    ebx, ebx
0x10055c7f  jnz     short loc_10055C85
0x10055c81  movzx   ebx, word ptr [edx+56h]
0x10055c85  mov     ecx, [ebp+arg_4]
0x10055c88  lea     eax, [ecx+2]
0x10055c8b  mov     [ebp+var_1C], eax
0x10055c8e  mov     edi, edi
0x10055c90  mov     ax, [ecx]
0x10055c93  add     ecx, 2
0x10055c96  test    ax, ax
0x10055c99  jnz     short loc_10055C90
0x10055c9b  sub     ecx, [ebp+var_1C]
0x10055c9e  mov     eax, [ebp+arg_4]
0x10055ca1  sar     ecx, 1
0x10055ca3  mov     [ebp+var_40], eax
0x10055ca6  mov     [ebp+var_30], ebx
0x10055ca9  mov     [ebp+var_2C], 0
0x10055cb0  lea     eax, [ecx+ecx]
0x10055cb3  mov     [ebp+var_3C], eax
0x10055cb6  mov     eax, [edx+5Ch]
0x10055cb9  mov     [ebp+var_38], eax
0x10055cbc  mov     eax, [edx+3Ch]
0x10055cbf  mov     edx, [ebp+Src]
0x10055cc2  mov     ecx, edx
0x10055cc4  mov     ax, [eax+64h]
0x10055cc8  mov     [ebp+var_34], ax
0x10055ccc  lea     ebx, [ecx+2]
0x10055ccf  nop
0x10055cd0  mov     ax, [ecx]
0x10055cd3  add     ecx, 2
0x10055cd6  test    ax, ax
0x10055cd9  jnz     short loc_10055CD0
0x10055cdb  sub     ecx, ebx
0x10055cdd  sar     ecx, 1
0x10055cdf  push    0
0x10055ce1  lea     eax, [ecx+ecx]
0x10055ce4  push    eax
0x10055ce5  push    edx
0x10055ce6  lea     ecx, [ebp+var_40]
0x10055ce9  call    ?Compare@LString@@QAE?AW4LCmp@@PAEIW4LSpec@@@Z; LString::Compare(uchar *,uint,LSpec)
0x10055cee  test    eax, eax
0x10055cf0  jz      short loc_10055CFF
0x10055cf2  push    ecx
0x10055cf3  push    0FFFFFA85h
0x10055cf8  mov     ecx, esi
0x10055cfa  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10055cff  test    byte ptr [esi], 8
0x10055d02  mov     ebx, [ebp+var_18]
0x10055d05  jnz     short loc_10055D20
0x10055d07  push    esi
0x10055d08  push    [ebp+arg_10]
0x10055d0b  lea     eax, [ebp+var_20]
0x10055d0e  mov     ecx, edi
0x10055d10  push    eax
0x10055d11  push    [ebp+arg_4]
0x10055d14  call    ?FindIndexOrRef@Table@@AAEJPBGPAJW4TblRefOrIdx@@AAVErr@@@Z; Table::FindIndexOrRef(ushort const *,long *,TblRefOrIdx,Err &)
0x10055d19  mov     ecx, eax
0x10055d1b  mov     [ebp+var_14], ecx
0x10055d1e  jmp     short loc_10055D23
0x10055d20  mov     ecx, [ebp+var_14]
0x10055d23  test    byte ptr [esi], 8
0x10055d26  jnz     loc_10055E81
0x10055d2c  mov     eax, [ebp+arg_0]
0x10055d2f  mov     ecx, [edi+ecx*4+574h]; this
0x10055d36  mov     [ebp+var_10], ecx
0x10055d39  mov     eax, [eax+0Ch]
0x10055d3c  mov     eax, [eax+38h]
0x10055d3f  mov     [ebp+var_24], eax
0x10055d42  cmp     eax, [ecx+0Ch]
0x10055d45  jle     short loc_10055DAC
0x10055d47  push    esi; struct Err *
0x10055d48  call    ?Clone@Index@@QAEPAV1@AAVErr@@@Z; Index::Clone(Err &)
0x10055d4d  test    byte ptr [esi], 8
0x10055d50  mov     [ebp+var_1C], eax
0x10055d53  jnz     short loc_10055DA9
0x10055d55  mov     eax, [ebp+var_10]
0x10055d58  push    eax; struct Instance *
0x10055d59  mov     ecx, [eax+8]; this
0x10055d5c  call    ?DropInstance@Session@@QAEXPAVInstance@@@Z; Session::DropInstance(Instance *)
0x10055d61  mov     edx, [ebp+var_1C]
0x10055d64  mov     eax, [edx+8]
0x10055d67  mov     [ebp+var_18], eax
0x10055d6a  mov     ecx, [eax+8]
0x10055d6d  cmp     ecx, [eax+4]
0x10055d70  jb      short loc_10055D8A
0x10055d72  lea     eax, [ecx+1]
0x10055d75  mov     ecx, [ebp+var_18]; this
0x10055d78  push    esi; struct Err *
0x10055d79  push    eax; unsigned int
0x10055d7a  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x10055d7f  test    byte ptr [esi], 8
0x10055d82  mov     edx, [ebp+var_1C]
0x10055d85  jnz     short loc_10055DA1
0x10055d87  mov     eax, [ebp+var_18]
0x10055d8a  mov     ecx, [eax+8]
0x10055d8d  mov     eax, [eax]
0x10055d8f  mov     [eax+ecx*4], edx
0x10055d92  mov     eax, [ebp+var_18]
0x10055d95  inc     dword ptr [eax+8]
0x10055d98  test    byte ptr [esi], 8
0x10055d9b  jz      loc_10055E9B
0x10055da1  push    ecx; unsigned int
0x10055da2  mov     ecx, edx; this
0x10055da4  call    ??_GIndex@@QAEPAXI@Z; Index::`scalar deleting destructor'(uint)
0x10055da9  mov     ecx, [ebp+var_10]
0x10055dac  mov     eax, [esi]
0x10055dae  test    al, 8
0x10055db0  jnz     short loc_10055DF1
0x10055db2  mov     edx, [ebp+Src]
0x10055db5  mov     esi, edx
0x10055db7  lea     eax, [esi+2]
0x10055dba  mov     [ebp+var_24], eax
0x10055dbd  nop     dword ptr [eax]
0x10055dc0  mov     ax, [esi]
0x10055dc3  add     esi, 2
0x10055dc6  test    ax, ax
0x10055dc9  jnz     short loc_10055DC0
0x10055dcb  sub     esi, [ebp+var_24]
0x10055dce  sar     esi, 1
0x10055dd0  add     esi, esi
0x10055dd2  push    esi; Size
0x10055dd3  push    edx; Src
0x10055dd4  push    dword ptr [ecx]; void *
0x10055dd6  call    _memcpy
0x10055ddb  mov     ecx, [ebp+var_10]
0x10055dde  add     esp, 0Ch
0x10055de1  xor     edx, edx
0x10055de3  mov     eax, [ecx]
0x10055de5  mov     [esi+eax], dx
0x10055de9  mov     [ecx+4], esi
0x10055dec  mov     esi, [ebp+arg_C]
0x10055def  mov     eax, [esi]
0x10055df1  mov     ecx, [ebp+var_20]
0x10055df4  cmp     ebx, ecx
0x10055df6  jle     short loc_10055DF9
0x10055df8  dec     ebx
0x10055df9  test    al, 8
0x10055dfb  jnz     short loc_10055E72
0x10055dfd  cmp     ecx, ebx
0x10055dff  jz      short loc_10055E72
0x10055e01  mov     eax, [edi+18h]
0x10055e04  sub     eax, ecx
0x10055e06  lea     eax, ds:0FFFFFFFCh[eax*4]
0x10055e0d  push    eax; Size
0x10055e0e  lea     eax, [ecx+17Eh]
0x10055e14  add     ecx, 17Dh
0x10055e1a  lea     eax, [edi+eax*4]
0x10055e1d  push    eax; Src
0x10055e1e  lea     eax, [edi+ecx*4]
0x10055e21  push    eax; void *
0x10055e22  call    _memcpy
0x10055e27  mov     eax, [edi+18h]
0x10055e2a  add     esp, 0Ch
0x10055e2d  mov     dword ptr [edi+eax*4+5F0h], 0FFFFFFFFh
0x10055e38  mov     ecx, [edi+18h]
0x10055e3b  lea     eax, [ecx-1]
0x10055e3e  cmp     ebx, eax
0x10055e40  jz      short loc_10055E68
0x10055e42  sub     ecx, ebx
0x10055e44  lea     eax, ds:0FFFFFFFCh[ecx*4]
0x10055e4b  push    eax; Size
0x10055e4c  lea     eax, [edi+5F4h]
0x10055e52  lea     eax, [eax+ebx*4]
0x10055e55  push    eax; Src
0x10055e56  lea     eax, [edi+5F8h]
0x10055e5c  lea     eax, [eax+ebx*4]
0x10055e5f  push    eax; void *
0x10055e60  call    _memmove
0x10055e65  add     esp, 0Ch
0x10055e68  mov     eax, [ebp+var_14]
0x10055e6b  mov     [edi+ebx*4+5F4h], eax
0x10055e72  test    byte ptr [esi], 8
0x10055e75  jnz     short loc_10055E81
0x10055e77  push    [ebp+arg_0]; struct Instance *
0x10055e7a  mov     ecx, edi; this
0x10055e7c  call    ?DDLPerformed@Table@@AAEXPAVInstance@@@Z; Table::DDLPerformed(Instance *)
0x10055e81  dec     dword ptr [edi+154h]
0x10055e87  mov     ecx, [ebp+var_C]
0x10055e8a  mov     large fs:0, ecx
0x10055e91  pop     ecx
0x10055e92  pop     edi
0x10055e93  pop     esi
0x10055e94  pop     ebx
0x10055e95  mov     esp, ebp
0x10055e97  pop     ebp
0x10055e98  retn    14h
0x10055e9b  mov     eax, [ebp+var_24]
0x10055e9e  mov     ecx, [ebp+var_10]
0x10055ea1  mov     [edx+0Ch], eax
0x10055ea4  mov     eax, [ebp+var_14]
0x10055ea7  mov     [edx+14h], ecx
0x10055eaa  mov     ecx, edx
0x10055eac  mov     [ebp+var_10], ecx
0x10055eaf  mov     [edi+eax*4+574h], edx
0x10055eb6  jmp     loc_10055DAC
0x10061fd0  lea     ecx, [ebp+var_28]; this
0x10061fd3  jmp     ??1TblSemaphore@@QAE@XZ; TblSemaphore::~TblSemaphore(void)
0x10061fdd  nop
0x10061fde  nop
0x10061fdf  mov     edx, [esp-4+arg_4]
0x10061fe3  lea     eax, [edx+0Ch]
0x10061fe6  mov     ecx, [edx-44h]
0x10061fe9  xor     ecx, eax; StackCookie
0x10061feb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10061ff0  mov     eax, offset stru_10064724
0x10061ff5  jmp     ___CxxFrameHandler3
```
