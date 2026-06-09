# CFveApiBase::SetBootEntryValidationOverride(uchar)

- ea: `0x18009dd3c`
- end: `0x18009e2f0`
- name: `?SetBootEntryValidationOverride@CFveApiBase@@SAJE@Z`
- size: `1460`
- prototype: `__int64 __fastcall(unsigned __int8)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18009e2f8`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x18000ba30`
- `0x180018b10`
- `0x180047570`
- `0x18009ba80`
- `0x18009befc`
- `0x18009dd3c`
- `0x18009f384`
- `0x18011f010`

## import_xrefs

- `bcd!BcdCloseObject` at `0x18009e273`
- `bcd!BcdCloseObject` at `0x18009e289`
- `bcd!BcdCloseObject` at `0x180124998`
- `bcd!BcdCloseObject` at `0x1801249ae`
- `bcd!BcdCloseObject` at `0x18009e273`
- `bcd!BcdCloseObject` at `0x18009e289`
- `bcd!BcdCloseObject` at `0x180124998`
- `bcd!BcdCloseObject` at `0x1801249ae`
- `bcd!BcdDeleteElement` at `0x18009e1a0`
- `bcd!BcdDeleteElement` at `0x18009e1e5`
- `bcd!BcdDeleteElement` at `0x18009e1a0`
- `bcd!BcdDeleteElement` at `0x18009e1e5`
- `bcd!BcdGetElementData` at `0x18009df28`
- `bcd!BcdGetElementData` at `0x18009df28`
- `bcd!BcdOpenObject` at `0x18009decb`
- `bcd!BcdOpenObject` at `0x18009df87`
- `bcd!BcdOpenObject` at `0x18009decb`
- `bcd!BcdOpenObject` at `0x18009df87`
- `bcd!BcdCloseStore` at `0x18009e29a`
- `bcd!BcdCloseStore` at `0x1801249bf`
- `bcd!BcdCloseStore` at `0x18009e29a`
- `bcd!BcdCloseStore` at `0x1801249bf`
- `bcd!BcdOpenSystemStore` at `0x18009ddf3`
- `bcd!BcdOpenSystemStore` at `0x18009ddf3`
- `bcd!BcdSetElementData` at `0x18009e084`
- `bcd!BcdSetElementData` at `0x18009e0dc`
- `bcd!BcdSetElementData` at `0x18009e084`
- `bcd!BcdSetElementData` at `0x18009e0dc`

## pseudocode

```c
__int64 __fastcall CFveApiBase::SetBootEntryValidationOverride(char a1, __int64 a2)
{
  int v3; // esi
  int v4; // eax
  int DoesRegKeyExist; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // ebx
  PVOID *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  int ElementData; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  int v20; // eax
  int v22; // [rsp+34h] [rbp-94h] BYREF
  void *lpMem; // [rsp+38h] [rbp-90h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-88h] BYREF
  void *v25; // [rsp+48h] [rbp-80h] BYREF
  void *v26; // [rsp+50h] [rbp-78h] BYREF
  __int64 v27; // [rsp+58h] [rbp-70h] BYREF
  _WORD v28[2]; // [rsp+60h] [rbp-68h] BYREF
  int v29; // [rsp+64h] [rbp-64h] BYREF
  __int128 v30; // [rsp+68h] [rbp-60h] BYREF
  struct _GUID v31; // [rsp+78h] [rbp-50h] BYREF

  v30 = 0;
  v29 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v22 = 0;
  v31 = GUID_CURRENT_BOOT_ENTRY;
  lpMem = 0;
  v24 = 0;
  v3 = 0;
  v28[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 201, &WPP_1559182127783aab3882fe828952d989_Traceguids);
  v4 = BcdOpenSystemStore(&v25, a2);
  DoesRegKeyExist = FromNtStatus(v4);
  v8 = DoesRegKeyExist;
  if ( DoesRegKeyExist < 0 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = 202;
LABEL_8:
      WPP_SF_d(v9[2], v10, &WPP_1559182127783aab3882fe828952d989_Traceguids, (unsigned int)DoesRegKeyExist);
LABEL_77:
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_78;
    }
    goto LABEL_78;
  }
  DoesRegKeyExist = NgscbpDoesRegKeyExist(v7, v6, &v22);
  v8 = DoesRegKeyExist;
  if ( DoesRegKeyExist >= 0 )
  {
    if ( v22 )
    {
      DoesRegKeyExist = CFveApiBase::GetAssociatedOs(v25, &v31);
      v8 = DoesRegKeyExist;
      if ( DoesRegKeyExist < 0 )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v10 = 204;
          goto LABEL_8;
        }
        goto LABEL_78;
      }
    }
    v11 = BcdOpenObject(v25, &v31, &v26);
    DoesRegKeyExist = FromNtStatus(v11);
    v8 = DoesRegKeyExist;
    if ( DoesRegKeyExist < 0 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v10 = 205;
        goto LABEL_8;
      }
      goto LABEL_78;
    }
    v29 = 16;
    ElementData = BcdGetElementData(v26, 587202563, &v30, &v29);
    DoesRegKeyExist = FromNtStatus(ElementData);
    v8 = DoesRegKeyExist;
    if ( DoesRegKeyExist != -2147023728 )
    {
      if ( DoesRegKeyExist < 0 )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v10 = 206;
          goto LABEL_8;
        }
        goto LABEL_78;
      }
      v13 = BcdOpenObject(v25, &v30, &v27);
      v14 = FromNtStatus(v13);
      v8 = v14;
      if ( v14 >= 0 )
      {
        v3 = 1;
      }
      else if ( v14 != -2147023728 && v14 != -2147024894 )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF__guid_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            207,
            &WPP_1559182127783aab3882fe828952d989_Traceguids,
            &v30,
            v14);
          goto LABEL_77;
        }
        goto LABEL_78;
      }
    }
    DoesRegKeyExist = CFveApiBase::GetBcdElementData(v26, 0x16BDEDECu, &lpMem, &v24);
    v8 = DoesRegKeyExist;
    if ( a1 )
    {
      if ( DoesRegKeyExist >= 0 && lpMem && *(_BYTE *)lpMem )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_43;
        v15 = 208;
LABEL_42:
        WPP_SF_(v9[2], v15, &WPP_1559182127783aab3882fe828952d989_Traceguids);
        v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_43:
        v8 = 0;
        goto LABEL_78;
      }
      LOBYTE(v28[0]) = 1;
      v16 = BcdSetElementData(v26, 381545964, v28, 2);
      DoesRegKeyExist = FromNtStatus(v16);
      v8 = DoesRegKeyExist;
      if ( DoesRegKeyExist < 0 )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v10 = 209;
          goto LABEL_8;
        }
        goto LABEL_78;
      }
      if ( v3 )
      {
        v17 = BcdSetElementData(v27, 381545964, v28, 2);
        DoesRegKeyExist = FromNtStatus(v17);
        v8 = DoesRegKeyExist;
        if ( DoesRegKeyExist < 0 )
        {
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v10 = 210;
            goto LABEL_8;
          }
          goto LABEL_78;
        }
      }
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_78;
      v18 = 211;
    }
    else
    {
      if ( DoesRegKeyExist == -2147023728 )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_43;
        v15 = 212;
        goto LABEL_42;
      }
      if ( DoesRegKeyExist < 0 )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v10 = 213;
          goto LABEL_8;
        }
        goto LABEL_78;
      }
      v19 = BcdDeleteElement(v26, 381545964);
      DoesRegKeyExist = FromNtStatus(v19);
      v8 = DoesRegKeyExist;
      if ( DoesRegKeyExist < 0 )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v10 = 214;
          goto LABEL_8;
        }
        goto LABEL_78;
      }
      if ( v3 )
      {
        v20 = BcdDeleteElement(v27, 381545964);
        DoesRegKeyExist = FromNtStatus(v20);
        v8 = DoesRegKeyExist;
        if ( DoesRegKeyExist < 0 )
        {
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v10 = 215;
            goto LABEL_8;
          }
          goto LABEL_78;
        }
      }
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_78;
      v18 = 216;
    }
    WPP_SF_(v9[2], v18, &WPP_1559182127783aab3882fe828952d989_Traceguids);
    goto LABEL_77;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v10 = 203;
    goto LABEL_8;
  }
LABEL_78:
  if ( lpMem )
  {
    CFveApiBase::FastFree(lpMem);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v25 )
  {
    if ( v26 )
      BcdCloseObject(v26);
    if ( v27 )
      BcdCloseObject(v27);
    BcdCloseStore(v25, v6);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 )
    WPP_SF_d(v9[2], 217, &WPP_1559182127783aab3882fe828952d989_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18009dd3c  push    rbx
0x18009dd3e  push    rsi
0x18009dd3f  push    rdi
0x18009dd40  push    r12
0x18009dd42  push    r13
0x18009dd44  push    r14
0x18009dd46  sub     rsp, 98h
0x18009dd4d  mov     rax, cs:__security_cookie
0x18009dd54  xor     rax, rsp
0x18009dd57  mov     [rsp+0C8h+var_40], rax
0x18009dd5f  mov     r14b, cl
0x18009dd62  xorps   xmm0, xmm0
0x18009dd65  movups  [rsp+0C8h+var_60], xmm0
0x18009dd6a  mov     [rsp+0C8h+var_64], 0
0x18009dd72  mov     [rsp+0C8h+var_80], 0
0x18009dd7b  mov     [rsp+0C8h+var_78], 0
0x18009dd84  mov     [rsp+0C8h+var_70], 0
0x18009dd8d  mov     [rsp+0C8h+var_94], 0
0x18009dd95  movups  xmm0, xmmword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data1
0x18009dd9c  movdqu  xmmword ptr [rsp+0C8h+var_50.Data1], xmm0
0x18009dda2  mov     [rsp+0C8h+lpMem], 0
0x18009ddab  mov     [rsp+0C8h+var_88], 0
0x18009ddb3  xor     esi, esi
0x18009ddb5  xor     eax, eax
0x18009ddb7  mov     [rsp+0C8h+var_68], ax
0x18009ddbc  lea     r12, WPP_GLOBAL_Control
0x18009ddc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ddca  lea     rdi, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009ddd1  cmp     rcx, r12
0x18009ddd4  jz      short loc_18009DDEE
0x18009ddd6  test    byte ptr [rcx+1Ch], 20h
0x18009ddda  jz      short loc_18009DDEE
0x18009dddc  mov     edx, 0C9h
0x18009dde1  mov     r8, rdi
0x18009dde4  mov     rcx, [rcx+10h]
0x18009dde8  call    WPP_SF_
0x18009dded  nop
0x18009ddee  lea     rcx, [rsp+0C8h+var_80]
0x18009ddf3  call    cs:__imp_BcdOpenSystemStore
0x18009ddfa  nop     dword ptr [rax+rax+00h]
0x18009ddff  mov     ecx, eax; int
0x18009de01  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009de06  mov     ebx, eax
0x18009de08  mov     [rsp+0C8h+var_98], eax
0x18009de0c  test    eax, eax
0x18009de0e  jns     short loc_18009DE43
0x18009de10  mov     rcx, cs:WPP_GLOBAL_Control
0x18009de17  cmp     rcx, r12
0x18009de1a  jz      loc_18009E248
0x18009de20  test    byte ptr [rcx+1Ch], 2
0x18009de24  jz      loc_18009E248
0x18009de2a  mov     edx, 0CAh
0x18009de2f  mov     r9d, eax
0x18009de32  mov     r8, rdi
0x18009de35  mov     rcx, [rcx+10h]
0x18009de39  call    WPP_SF_d
0x18009de3e  jmp     loc_18009E241
0x18009de43  lea     r8, [rsp+0C8h+var_94]
0x18009de48  call    NgscbpDoesRegKeyExist
0x18009de4d  mov     ebx, eax
0x18009de4f  mov     [rsp+0C8h+var_98], eax
0x18009de53  test    eax, eax
0x18009de55  jns     short loc_18009DE78
0x18009de57  mov     rcx, cs:WPP_GLOBAL_Control
0x18009de5e  cmp     rcx, r12
0x18009de61  jz      loc_18009E248
0x18009de67  test    byte ptr [rcx+1Ch], 2
0x18009de6b  jz      loc_18009E248
0x18009de71  mov     edx, 0CBh
0x18009de76  jmp     short loc_18009DE2F
0x18009de78  cmp     [rsp+0C8h+var_94], 0
0x18009de7d  jz      short loc_18009DEBC
0x18009de7f  lea     rdx, [rsp+0C8h+var_50]; struct _GUID *
0x18009de84  mov     rcx, [rsp+0C8h+var_80]; void *
0x18009de89  call    ?GetAssociatedOs@CFveApiBase@@KAJPEAXPEAU_GUID@@@Z; CFveApiBase::GetAssociatedOs(void *,_GUID *)
0x18009de8e  mov     ebx, eax
0x18009de90  mov     [rsp+0C8h+var_98], eax
0x18009de94  test    eax, eax
0x18009de96  jns     short loc_18009DEBC
0x18009de98  mov     rcx, cs:WPP_GLOBAL_Control
0x18009de9f  cmp     rcx, r12
0x18009dea2  jz      loc_18009E248
0x18009dea8  test    byte ptr [rcx+1Ch], 2
0x18009deac  jz      loc_18009E248
0x18009deb2  mov     edx, 0CCh
0x18009deb7  jmp     loc_18009DE2F
0x18009debc  lea     r8, [rsp+0C8h+var_78]
0x18009dec1  lea     rdx, [rsp+0C8h+var_50]
0x18009dec6  mov     rcx, [rsp+0C8h+var_80]
0x18009decb  call    cs:__imp_BcdOpenObject
0x18009ded2  nop     dword ptr [rax+rax+00h]
0x18009ded7  mov     ecx, eax; int
0x18009ded9  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009dede  mov     ebx, eax
0x18009dee0  mov     [rsp+0C8h+var_98], eax
0x18009dee4  test    eax, eax
0x18009dee6  jns     short loc_18009DF0C
0x18009dee8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009deef  cmp     rcx, r12
0x18009def2  jz      loc_18009E248
0x18009def8  test    byte ptr [rcx+1Ch], 2
0x18009defc  jz      loc_18009E248
0x18009df02  mov     edx, 0CDh
0x18009df07  jmp     loc_18009DE2F
0x18009df0c  mov     [rsp+0C8h+var_64], 10h
0x18009df14  lea     r9, [rsp+0C8h+var_64]
0x18009df19  lea     r8, [rsp+0C8h+var_60]
0x18009df1e  mov     edx, 23000003h
0x18009df23  mov     rcx, [rsp+0C8h+var_78]
0x18009df28  call    cs:__imp_BcdGetElementData
0x18009df2f  nop     dword ptr [rax+rax+00h]
0x18009df34  mov     ecx, eax; int
0x18009df36  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009df3b  mov     ebx, eax
0x18009df3d  mov     [rsp+0C8h+var_98], eax
0x18009df41  mov     r13d, 80070490h
0x18009df47  cmp     eax, r13d
0x18009df4a  jz      loc_18009DFF4
0x18009df50  test    eax, eax
0x18009df52  jns     short loc_18009DF78
0x18009df54  mov     rcx, cs:WPP_GLOBAL_Control
0x18009df5b  cmp     rcx, r12
0x18009df5e  jz      loc_18009E248
0x18009df64  test    byte ptr [rcx+1Ch], 2
0x18009df68  jz      loc_18009E248
0x18009df6e  mov     edx, 0CEh
0x18009df73  jmp     loc_18009DE2F
0x18009df78  lea     r8, [rsp+0C8h+var_70]
0x18009df7d  lea     rdx, [rsp+0C8h+var_60]
0x18009df82  mov     rcx, [rsp+0C8h+var_80]
0x18009df87  call    cs:__imp_BcdOpenObject
0x18009df8e  nop     dword ptr [rax+rax+00h]
0x18009df93  mov     ecx, eax; int
0x18009df95  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009df9a  mov     ebx, eax
0x18009df9c  mov     [rsp+0C8h+var_98], eax
0x18009dfa0  test    eax, eax
0x18009dfa2  jns     short loc_18009DFED
0x18009dfa4  cmp     eax, r13d
0x18009dfa7  jz      short loc_18009DFE9
0x18009dfa9  cmp     eax, 80070002h
0x18009dfae  jz      short loc_18009DFE9
0x18009dfb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dfb7  cmp     rcx, r12
0x18009dfba  jz      loc_18009E248
0x18009dfc0  test    byte ptr [rcx+1Ch], 2
0x18009dfc4  jz      loc_18009E248
0x18009dfca  mov     edx, 0CFh
0x18009dfcf  mov     [rsp+0C8h+var_A8], eax
0x18009dfd3  lea     r9, [rsp+0C8h+var_60]
0x18009dfd8  mov     r8, rdi
0x18009dfdb  mov     rcx, [rcx+10h]
0x18009dfdf  call    WPP_SF__guid_D
0x18009dfe4  jmp     loc_18009E241
0x18009dfe9  test    eax, eax
0x18009dfeb  js      short loc_18009DFFC
0x18009dfed  mov     esi, 1
0x18009dff2  jmp     short loc_18009DFFC
0x18009dff4  mov     [rsp+0C8h+var_98], 0
0x18009dffc  lea     r9, [rsp+0C8h+var_88]; unsigned int *
0x18009e001  lea     r8, [rsp+0C8h+lpMem]; void **
0x18009e006  mov     r13d, 16BDEDECh
0x18009e00c  mov     edx, r13d; unsigned int
0x18009e00f  mov     rcx, [rsp+0C8h+var_78]; void *
0x18009e014  call    ?GetBcdElementData@CFveApiBase@@SAJPEAXKPEAPEAXPEAK@Z; CFveApiBase::GetBcdElementData(void *,ulong,void * *,ulong *)
0x18009e019  mov     ebx, eax
0x18009e01b  test    r14b, r14b
0x18009e01e  jz      loc_18009E141
0x18009e024  test    eax, eax
0x18009e026  js      short loc_18009E06C
0x18009e028  mov     rax, [rsp+0C8h+lpMem]
0x18009e02d  test    rax, rax
0x18009e030  jz      short loc_18009E06C
0x18009e032  cmp     byte ptr [rax], 0
0x18009e035  jz      short loc_18009E06C
0x18009e037  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e03e  cmp     rcx, r12
0x18009e041  jz      short loc_18009E061
0x18009e043  test    byte ptr [rcx+1Ch], 8
0x18009e047  jz      short loc_18009E061
0x18009e049  mov     edx, 0D0h
0x18009e04e  mov     r8, rdi
0x18009e051  mov     rcx, [rcx+10h]
0x18009e055  call    WPP_SF_
0x18009e05a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e061  xor     ebx, ebx
0x18009e063  mov     [rsp+0C8h+var_98], ebx
0x18009e067  jmp     loc_18009E248
0x18009e06c  mov     byte ptr [rsp+0C8h+var_68], 1
0x18009e071  mov     r9d, 2
0x18009e077  lea     r8, [rsp+0C8h+var_68]
0x18009e07c  mov     edx, r13d
0x18009e07f  mov     rcx, [rsp+0C8h+var_78]
0x18009e084  call    cs:__imp_BcdSetElementData
0x18009e08b  nop     dword ptr [rax+rax+00h]
0x18009e090  mov     ecx, eax; int
0x18009e092  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009e097  mov     ebx, eax
0x18009e099  mov     [rsp+0C8h+var_98], eax
0x18009e09d  test    eax, eax
0x18009e09f  jns     short loc_18009E0C5
0x18009e0a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e0a8  cmp     rcx, r12
0x18009e0ab  jz      loc_18009E248
0x18009e0b1  test    byte ptr [rcx+1Ch], 2
0x18009e0b5  jz      loc_18009E248
0x18009e0bb  mov     edx, 0D1h
0x18009e0c0  jmp     loc_18009DE2F
0x18009e0c5  test    esi, esi
0x18009e0c7  jz      short loc_18009E11D
0x18009e0c9  mov     r9d, 2
0x18009e0cf  lea     r8, [rsp+0C8h+var_68]
0x18009e0d4  mov     edx, r13d
0x18009e0d7  mov     rcx, [rsp+0C8h+var_70]
0x18009e0dc  call    cs:__imp_BcdSetElementData
0x18009e0e3  nop     dword ptr [rax+rax+00h]
0x18009e0e8  mov     ecx, eax; int
0x18009e0ea  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009e0ef  mov     ebx, eax
0x18009e0f1  mov     [rsp+0C8h+var_98], eax
0x18009e0f5  test    eax, eax
0x18009e0f7  jns     short loc_18009E11D
0x18009e0f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e100  cmp     rcx, r12
0x18009e103  jz      loc_18009E248
0x18009e109  test    byte ptr [rcx+1Ch], 2
0x18009e10d  jz      loc_18009E248
0x18009e113  mov     edx, 0D2h
0x18009e118  jmp     loc_18009DE2F
0x18009e11d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e124  cmp     rcx, r12
0x18009e127  jz      loc_18009E248
0x18009e12d  test    byte ptr [rcx+1Ch], 8
0x18009e131  jz      loc_18009E248
0x18009e137  mov     edx, 0D3h
0x18009e13c  jmp     loc_18009E235
0x18009e141  cmp     eax, 80070490h
0x18009e146  jnz     short loc_18009E16C
0x18009e148  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e14f  cmp     rcx, r12
0x18009e152  jz      loc_18009E061
0x18009e158  test    byte ptr [rcx+1Ch], 8
0x18009e15c  jz      loc_18009E061
0x18009e162  mov     edx, 0D4h
0x18009e167  jmp     loc_18009E04E
0x18009e16c  test    eax, eax
0x18009e16e  jns     short loc_18009E198
0x18009e170  mov     [rsp+0C8h+var_98], eax
0x18009e174  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e17b  cmp     rcx, r12
0x18009e17e  jz      loc_18009E248
0x18009e184  test    byte ptr [rcx+1Ch], 2
0x18009e188  jz      loc_18009E248
0x18009e18e  mov     edx, 0D5h
0x18009e193  jmp     loc_18009DE2F
0x18009e198  mov     edx, r13d
0x18009e19b  mov     rcx, [rsp+0C8h+var_78]
0x18009e1a0  call    cs:__imp_BcdDeleteElement
0x18009e1a7  nop     dword ptr [rax+rax+00h]
0x18009e1ac  mov     ecx, eax; int
0x18009e1ae  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009e1b3  mov     ebx, eax
0x18009e1b5  mov     [rsp+0C8h+var_98], eax
0x18009e1b9  test    eax, eax
0x18009e1bb  jns     short loc_18009E1D9
0x18009e1bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e1c4  cmp     rcx, r12
0x18009e1c7  jz      short loc_18009E248
0x18009e1c9  test    byte ptr [rcx+1Ch], 2
0x18009e1cd  jz      short loc_18009E248
0x18009e1cf  mov     edx, 0D6h
0x18009e1d4  jmp     loc_18009DE2F
0x18009e1d9  test    esi, esi
0x18009e1db  jz      short loc_18009E21E
0x18009e1dd  mov     edx, r13d
0x18009e1e0  mov     rcx, [rsp+0C8h+var_70]
0x18009e1e5  call    cs:__imp_BcdDeleteElement
0x18009e1ec  nop     dword ptr [rax+rax+00h]
0x18009e1f1  mov     ecx, eax; int
0x18009e1f3  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009e1f8  mov     ebx, eax
0x18009e1fa  mov     [rsp+0C8h+var_98], eax
0x18009e1fe  test    eax, eax
0x18009e200  jns     short loc_18009E21E
0x18009e202  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e209  cmp     rcx, r12
0x18009e20c  jz      short loc_18009E248
0x18009e20e  test    byte ptr [rcx+1Ch], 2
0x18009e212  jz      short loc_18009E248
0x18009e214  mov     edx, 0D7h
0x18009e219  jmp     loc_18009DE2F
0x18009e21e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e225  cmp     rcx, r12
0x18009e228  jz      short loc_18009E248
0x18009e22a  test    byte ptr [rcx+1Ch], 8
0x18009e22e  jz      short loc_18009E248
0x18009e230  mov     edx, 0D8h
0x18009e235  mov     r8, rdi
0x18009e238  mov     rcx, [rcx+10h]
0x18009e23c  call    WPP_SF_
  ... truncated ...
```
