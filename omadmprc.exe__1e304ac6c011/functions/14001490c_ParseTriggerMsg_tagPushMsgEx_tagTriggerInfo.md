# ParseTriggerMsg(tagPushMsgEx *,tagTriggerInfo *)

- ea: `0x14001490c`
- end: `0x140014c88`
- name: `?ParseTriggerMsg@@YAJPEAUtagPushMsgEx@@PEAUtagTriggerInfo@@@Z`
- size: `892`
- prototype: `__int64 __fastcall(struct tagPushMsgEx *, struct tagTriggerInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000fff0`

## callees

- `0x140001090`
- `0x1400017e8`
- `0x1400023d6`
- `0x14000271f`
- `0x14001490c`
- `0x140015690`

## import_xrefs

- `DMCmnUtils!MBToUnicode` at `0x140014ab2`
- `DMCmnUtils!MBToUnicode` at `0x140014ab2`
- `DMCmnUtils!CopyString` at `0x140014b4a`
- `DMCmnUtils!CopyString` at `0x140014b4a`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x140014b13`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x140014b13`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x140014b64`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x140014b64`

## pseudocode

```c
__int64 __fastcall ParseTriggerMsg(struct tagPushMsgEx *a1, struct tagTriggerInfo *a2)
{
  unsigned __int8 *v4; // r8
  size_t v5; // r9
  __int64 *v6; // rax
  __int16 *v7; // rdx
  int v8; // eax
  int v9; // ecx
  unsigned __int8 v10; // al
  char v11; // cl
  unsigned int v12; // ecx
  int v13; // ebx
  int v14; // r8d
  int v15; // r9d
  const unsigned __int16 *v16; // r14
  int InitiationInfo; // eax
  __int64 v19; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v20; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h] BYREF
  __int64 v22; // [rsp+78h] [rbp-88h] BYREF
  __int64 v23; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+88h] [rbp-78h] BYREF
  __int64 v25; // [rsp+90h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v27; // [rsp+C0h] [rbp-40h]
  __int64 v28; // [rsp+C8h] [rbp-38h]
  char v29[272]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(v29, 0, 0x104u);
  if ( *((_DWORD *)a1 + 6) < 0x18u || (v4 = (unsigned __int8 *)*((_QWORD *)a1 + 2), v4[23] + 24 != *((_DWORD *)a1 + 6)) )
  {
    if ( (unsigned int)dword_140023000 > 5 )
    {
      v7 = (__int16 *)&byte_14001E557;
      v20 = *((unsigned int *)a1 + 6);
      v6 = &v20;
      goto LABEL_30;
    }
    return (unsigned int)-2102722549;
  }
  v5 = v4[23];
  if ( !v4[23] )
  {
    if ( (unsigned int)dword_140023000 > 5 )
    {
      v19 = v4[23];
      v6 = &v19;
      v7 = (__int16 *)byte_14001E50D;
LABEL_30:
      v28 = 8;
      goto LABEL_31;
    }
    return (unsigned int)-2102722549;
  }
  v8 = 4 * v4[16];
  *(_DWORD *)a2 = v8;
  v9 = v8 | (v4[17] >> 6);
  *(_DWORD *)a2 = v9;
  if ( (unsigned int)(v9 - 11) > 8 )
  {
    if ( (unsigned int)dword_140023000 <= 5 )
      return (unsigned int)-2102722549;
    v19 = *(unsigned int *)a2;
    v6 = &v19;
    v28 = 8;
    v7 = &word_14001E4C6;
LABEL_31:
    v27 = v6;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140023000, (unsigned __int8 *)v7, 0, 0, 3u, v26);
    return (unsigned int)-2102722549;
  }
  v10 = ((v4[17] >> 4) & 3) + 1;
  *((_BYTE *)a2 + 8) = v10;
  if ( v10 > 4u )
  {
    if ( (unsigned int)dword_140023000 <= 5 )
      return (unsigned int)-2102722549;
    v19 = *((unsigned __int8 *)a2 + 8);
    v6 = &v19;
    v28 = 8;
    v7 = (__int16 *)&unk_14001E488;
    goto LABEL_31;
  }
  v11 = (v4[17] & 8) != 0;
  if ( *((_DWORD *)a1 + 14) == 2 )
    v11 = 1;
  *((_BYTE *)a2 + 9) = v11;
  if ( (unsigned __int8)v11 >= 2u )
  {
    if ( (unsigned int)dword_140023000 <= 5 )
      return (unsigned int)-2102722549;
    v19 = *((unsigned __int8 *)a2 + 9);
    v6 = &v19;
    v28 = 8;
    v7 = word_14001E43A;
    goto LABEL_31;
  }
  *((_DWORD *)a2 + 1) = v4[22] | (v4[21] << 8);
  memcpy_0(v29, v4 + 24, v5);
  v13 = MBToUnicode(v29, 0xFDE9u, (unsigned __int16 **)a2 + 2, 0);
  if ( v13 >= 0 )
  {
    *((_DWORD *)a2 + 6) = 0;
    if ( *((_DWORD *)a1 + 14) == 2
      || (v12 = *((_DWORD *)a1 + 18) - 3, v12 > 0x207)
      || (v16 = (const unsigned __int16 *)*((_QWORD *)a1 + 8)) == 0 )
    {
LABEL_26:
      if ( (unsigned int)dword_140023000 > 5 )
      {
        v19 = *((_QWORD *)a2 + 4);
        v21 = *((int *)a2 + 6);
        v22 = *((_QWORD *)a2 + 2);
        v23 = *((unsigned int *)a2 + 1);
        v24 = *((unsigned __int8 *)a2 + 9);
        v25 = *((unsigned __int8 *)a2 + 8);
        v20 = *(unsigned int *)a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          v12,
          (unsigned int)&dword_14001E3B4,
          v14,
          v15,
          (__int64)&v20,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v23,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)&v19);
      }
      return (unsigned int)v13;
    }
    memset_0(v26, 0, 0x40u);
    LODWORD(v26[0].Ptr) = 64;
    InitiationInfo = OmaDmGetInitiationInfo(v16, v26);
    v13 = InitiationInfo;
    if ( InitiationInfo == -2147024894 )
      return (unsigned int)-2102722548;
    if ( InitiationInfo >= 0 )
    {
      *((_DWORD *)a2 + 6) = HIDWORD(v27);
      v13 = CopyString(v16, 0xFFFFFFFF, (unsigned __int16 **)a2 + 4);
      if ( v13 >= 0 )
      {
        OmaDmFreeInitiationInfo(v26);
        goto LABEL_26;
      }
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14001490c  mov     [rsp-8+arg_10], rbx
0x140014911  mov     [rsp-8+arg_18], rsi
0x140014916  push    rbp
0x140014917  push    r14
0x140014919  push    r15
0x14001491b  lea     rbp, [rsp-100h]
0x140014923  sub     rsp, 200h
0x14001492a  mov     rax, cs:__security_cookie
0x140014931  xor     rax, rsp
0x140014934  mov     [rbp+110h+var_20], rax
0x14001493b  mov     rsi, rdx
0x14001493e  mov     r14, rcx
0x140014941  xor     edx, edx; Val
0x140014943  lea     rcx, [rbp+110h+var_130]; void *
0x140014947  mov     r8d, 104h; Size
0x14001494d  call    memset_0
0x140014952  cmp     dword ptr [r14+18h], 18h
0x140014957  jb      loc_140014C09
0x14001495d  mov     r8, [r14+10h]
0x140014961  movzx   eax, byte ptr [r8+17h]
0x140014966  add     eax, 18h
0x140014969  cmp     eax, [r14+18h]
0x14001496d  jnz     loc_140014C09
0x140014973  movzx   r9d, byte ptr [r8+17h]
0x140014978  test    r9, r9
0x14001497b  jnz     short loc_1400149A2
0x14001497d  mov     eax, cs:dword_140023000
0x140014983  cmp     eax, 5
0x140014986  jbe     loc_140014C58
0x14001498c  mov     [rsp+210h+var_1B0], r9
0x140014991  lea     rax, [rsp+210h+var_1B0]
0x140014996  lea     rdx, byte_14001E50D
0x14001499d  jmp     loc_140014C29
0x1400149a2  movzx   eax, byte ptr [r8+10h]
0x1400149a7  mov     edx, 8
0x1400149ac  shl     eax, 2
0x1400149af  mov     [rsi], eax
0x1400149b1  movzx   ecx, byte ptr [r8+11h]
0x1400149b6  shr     ecx, 6
0x1400149b9  or      ecx, eax
0x1400149bb  mov     [rsi], ecx
0x1400149bd  lea     eax, [rcx-0Bh]
0x1400149c0  cmp     eax, edx
0x1400149c2  jbe     short loc_1400149EF
0x1400149c4  mov     eax, cs:dword_140023000
0x1400149ca  cmp     eax, 5
0x1400149cd  jbe     loc_140014C58
0x1400149d3  mov     eax, [rsi]
0x1400149d5  mov     [rsp+210h+var_1B0], rax
0x1400149da  lea     rax, [rsp+210h+var_1B0]
0x1400149df  mov     [rbp+110h+var_148], rdx
0x1400149e3  lea     rdx, word_14001E4C6
0x1400149ea  jmp     loc_140014C31
0x1400149ef  mov     al, [r8+11h]
0x1400149f3  mov     r10d, 1
0x1400149f9  shr     al, 4
0x1400149fc  and     al, 3
0x1400149fe  add     al, r10b
0x140014a01  mov     [rsi+8], al
0x140014a04  cmp     al, 4
0x140014a06  jbe     short loc_140014A35
0x140014a08  mov     eax, cs:dword_140023000
0x140014a0e  cmp     eax, 5
0x140014a11  jbe     loc_140014C58
0x140014a17  movzx   eax, byte ptr [rsi+8]
0x140014a1b  mov     [rsp+210h+var_1B0], rax
0x140014a20  lea     rax, [rsp+210h+var_1B0]
0x140014a25  mov     [rbp+110h+var_148], rdx
0x140014a29  lea     rdx, unk_14001E488
0x140014a30  jmp     loc_140014C31
0x140014a35  mov     al, [r8+11h]
0x140014a39  shr     al, 3
0x140014a3c  and     al, r10b
0x140014a3f  cmp     dword ptr [r14+38h], 2
0x140014a44  movzx   ecx, al
0x140014a47  cmovz   ecx, r10d
0x140014a4b  mov     [rsi+9], cl
0x140014a4e  cmp     cl, 2
0x140014a51  jb      short loc_140014A80
0x140014a53  mov     eax, cs:dword_140023000
0x140014a59  cmp     eax, 5
0x140014a5c  jbe     loc_140014C58
0x140014a62  movzx   eax, byte ptr [rsi+9]
0x140014a66  mov     [rsp+210h+var_1B0], rax
0x140014a6b  lea     rax, [rsp+210h+var_1B0]
0x140014a70  mov     [rbp+110h+var_148], rdx
0x140014a74  lea     rdx, word_14001E43A
0x140014a7b  jmp     loc_140014C31
0x140014a80  movzx   ecx, byte ptr [r8+15h]
0x140014a85  lea     rdx, [r8+18h]; Src
0x140014a89  movzx   eax, byte ptr [r8+16h]
0x140014a8e  mov     r8, r9; Size
0x140014a91  shl     ecx, 8
0x140014a94  or      ecx, eax
0x140014a96  mov     [rsi+4], ecx
0x140014a99  lea     rcx, [rbp+110h+var_130]; void *
0x140014a9d  call    memcpy_0
0x140014aa2  xor     r9d, r9d
0x140014aa5  lea     r8, [rsi+10h]
0x140014aa9  mov     edx, 0FDE9h
0x140014aae  lea     rcx, [rbp+110h+var_130]
0x140014ab2  call    cs:__imp_?MBToUnicode@@YAJPEBDIPEAPEAGPEAK@Z; MBToUnicode(char const *,uint,ushort * *,ulong *)
0x140014ab9  nop     dword ptr [rax+rax+00h]
0x140014abe  mov     ebx, eax
0x140014ac0  test    eax, eax
0x140014ac2  js      loc_140014C5D
0x140014ac8  mov     dword ptr [rsi+18h], 0
0x140014acf  cmp     dword ptr [r14+38h], 2
0x140014ad4  jz      loc_140014B70
0x140014ada  mov     ecx, [r14+48h]
0x140014ade  sub     ecx, 3
0x140014ae1  cmp     ecx, 207h
0x140014ae7  ja      loc_140014B70
0x140014aed  mov     r14, [r14+40h]
0x140014af1  test    r14, r14
0x140014af4  jz      short loc_140014B70
0x140014af6  mov     ebx, 40h ; '@'
0x140014afb  lea     rcx, [rbp+110h+var_170]; void *
0x140014aff  mov     r8d, ebx; Size
0x140014b02  xor     edx, edx; Val
0x140014b04  call    memset_0
0x140014b09  lea     rdx, [rbp+110h+var_170]
0x140014b0d  mov     [rbp+110h+var_170], ebx
0x140014b10  mov     rcx, r14
0x140014b13  call    cs:__imp_OmaDmGetInitiationInfo
0x140014b1a  nop     dword ptr [rax+rax+00h]
0x140014b1f  mov     ebx, eax
0x140014b21  cmp     eax, 80070002h
0x140014b26  jnz     short loc_140014B32
0x140014b28  mov     ebx, 82AB000Ch
0x140014b2d  jmp     loc_140014C5D
0x140014b32  test    eax, eax
0x140014b34  js      loc_140014C5D
0x140014b3a  mov     eax, [rbp+110h+var_14C]
0x140014b3d  lea     r8, [rsi+20h]
0x140014b41  or      edx, 0FFFFFFFFh
0x140014b44  mov     [rsi+18h], eax
0x140014b47  mov     rcx, r14
0x140014b4a  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x140014b51  nop     dword ptr [rax+rax+00h]
0x140014b56  mov     ebx, eax
0x140014b58  test    eax, eax
0x140014b5a  js      loc_140014C5D
0x140014b60  lea     rcx, [rbp+110h+var_170]
0x140014b64  call    cs:__imp_OmaDmFreeInitiationInfo
0x140014b6b  nop     dword ptr [rax+rax+00h]
0x140014b70  mov     eax, cs:dword_140023000
0x140014b76  cmp     eax, 5
0x140014b79  jbe     loc_140014C5D
0x140014b7f  mov     rax, [rsi+20h]
0x140014b83  lea     rdx, dword_14001E3B4
0x140014b8a  mov     [rsp+210h+var_1B0], rax
0x140014b8f  movsxd  rax, dword ptr [rsi+18h]
0x140014b93  mov     [rsp+210h+var_1A0], rax
0x140014b98  mov     rax, [rsi+10h]
0x140014b9c  mov     [rsp+210h+var_198], rax
0x140014ba1  mov     eax, [rsi+4]
0x140014ba4  mov     [rbp+110h+var_190], rax
0x140014ba8  movzx   eax, byte ptr [rsi+9]
0x140014bac  mov     [rbp+110h+var_188], rax
0x140014bb0  movzx   eax, byte ptr [rsi+8]
0x140014bb4  mov     [rbp+110h+var_180], rax
0x140014bb8  mov     eax, [rsi]
0x140014bba  mov     [rsp+210h+var_1A8], rax
0x140014bbf  lea     rax, [rsp+210h+var_1B0]
0x140014bc4  mov     [rsp+210h+var_1C0], rax
0x140014bc9  lea     rax, [rsp+210h+var_1A0]
0x140014bce  mov     [rsp+210h+var_1C8], rax
0x140014bd3  lea     rax, [rsp+210h+var_198]
0x140014bd8  mov     [rsp+210h+var_1D0], rax
0x140014bdd  lea     rax, [rbp+110h+var_190]
0x140014be1  mov     [rsp+210h+var_1D8], rax
0x140014be6  lea     rax, [rbp+110h+var_188]
0x140014bea  mov     [rsp+210h+var_1E0], rax
0x140014bef  lea     rax, [rbp+110h+var_180]
0x140014bf3  mov     [rsp+210h+var_1E8], rax
0x140014bf8  lea     rax, [rsp+210h+var_1A8]
0x140014bfd  mov     [rsp+210h+var_1F0], rax
0x140014c02  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U?$_tlgWrapSz@G@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@333AEBU?$_tlgWrapSz@G@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x140014c07  jmp     short loc_140014C5D
0x140014c09  mov     eax, cs:dword_140023000
0x140014c0f  cmp     eax, 5
0x140014c12  jbe     short loc_140014C58
0x140014c14  mov     eax, [r14+18h]
0x140014c18  lea     rdx, byte_14001E557
0x140014c1f  mov     [rsp+210h+var_1A8], rax
0x140014c24  lea     rax, [rsp+210h+var_1A8]
0x140014c29  mov     [rbp+110h+var_148], 8
0x140014c31  mov     [rbp-40h], rax
0x140014c35  lea     rcx, dword_140023000
0x140014c3c  lea     rax, [rbp+110h+var_170]
0x140014c40  xor     r9d, r9d
0x140014c43  mov     [rsp+210h+var_1E8], rax
0x140014c48  xor     r8d, r8d
0x140014c4b  mov     dword ptr [rsp+210h+var_1F0], 3
0x140014c53  call    _tlgWriteTransfer_EventWriteTransfer
0x140014c58  mov     ebx, 82AB000Bh
0x140014c5d  mov     eax, ebx
0x140014c5f  mov     rcx, [rbp+110h+var_20]
0x140014c66  xor     rcx, rsp; StackCookie
0x140014c69  call    __security_check_cookie
0x140014c6e  lea     r11, [rsp+210h+var_10]
0x140014c76  mov     rbx, [r11+30h]
0x140014c7a  mov     rsi, [r11+38h]
0x140014c7e  mov     rsp, r11
0x140014c81  pop     r15
0x140014c83  pop     r14
0x140014c85  pop     rbp
0x140014c86  retn
```
