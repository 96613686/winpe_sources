# ActionFveExternalDataGetEntryRawData

- ea: `0x140053c80`
- end: `0x1400541c3`
- name: `ActionFveExternalDataGetEntryRawData`
- size: `1347`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14008964c`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000aef4`
- `0x14000b920`
- `0x140011f4c`
- `0x140015154`
- `0x1400218c0`
- `0x140021d00`
- `0x140053c80`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140053f35`
- `ntoskrnl!ProbeForWrite` at `0x140053f58`
- `ntoskrnl!ProbeForWrite` at `0x140053f35`
- `ntoskrnl!ProbeForWrite` at `0x140053f58`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140053d89`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140053d89`
- `ntoskrnl!KeStackAttachProcess` at `0x140053f19`
- `ntoskrnl!KeStackAttachProcess` at `0x140053f19`

## pseudocode

```c
__int64 __fastcall ActionFveExternalDataGetEntryRawData(_QWORD *a1, __int64 a2, unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  char v7; // al
  char v8; // r13
  int v10; // r8d
  __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rax
  GUID *v15; // rax
  GUID v16; // xmm0
  volatile void *v17; // rcx
  __int64 v18; // rcx
  int EntryRawData; // eax
  __int64 v20; // rcx
  int CachedExternalData; // eax
  _WORD v22[2]; // [rsp+44h] [rbp-134h] BYREF
  char v23; // [rsp+48h] [rbp-130h]
  int v24; // [rsp+4Ch] [rbp-12Ch]
  __int64 v25; // [rsp+50h] [rbp-128h]
  PRKPROCESS PROCESS; // [rsp+58h] [rbp-120h]
  _BYTE v27[144]; // [rsp+60h] [rbp-118h] BYREF
  GUID v28; // [rsp+F0h] [rbp-88h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+100h] [rbp-78h] BYREF

  v28 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  v22[0] = 0;
  memset(v27, 0, sizeof(v27));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 153, WPP_db10fbeca6e03e7325aab39114461952_Traceguids);
  }
  v22[0] = 0;
  if ( *a3 < 0x50u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 154, WPP_db10fbeca6e03e7325aab39114461952_Traceguids, *a3);
    }
LABEL_10:
    v6 = -1073741811;
LABEL_11:
    v7 = 0;
LABEL_12:
    v8 = 0;
    goto LABEL_13;
  }
  v10 = *((_DWORD *)a3 + 1);
  if ( v10 != 28 || a3[1] != 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 155, WPP_db10fbeca6e03e7325aab39114461952_Traceguids, a3[1], v10);
    }
    goto LABEL_10;
  }
  v11 = a1[1];
  v25 = v11;
  PROCESS = *(PRKPROCESS *)(a2 + 120);
  if ( *(_BYTE *)(a2 + 64) )
  {
    v12 = FveCheckAdminAccess(a1, a2, 1);
    v6 = v12;
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          156,
          WPP_db10fbeca6e03e7325aab39114461952_Traceguids,
          (unsigned int)v12);
      }
      goto LABEL_11;
    }
    v11 = v25;
  }
  FvepAcquireDevFveLock(a1, v27, 0);
  v23 = 1;
  v13 = a1[127];
  v14 = a1[122];
  if ( v13 )
  {
    if ( v14 )
    {
      v15 = (GUID *)a1[123];
      if ( v15 )
      {
        v16 = v15[5];
        goto LABEL_43;
      }
    }
    goto LABEL_35;
  }
  if ( v14 )
  {
    v6 = -1071579136;
    goto LABEL_36;
  }
  if ( !*((_BYTE *)a3 + 72) )
  {
LABEL_35:
    v6 = -1071579135;
LABEL_36:
    v7 = 1;
    goto LABEL_12;
  }
  if ( (*(_DWORD *)(a1[15] + 48LL) & 0x400100) == 0 )
  {
    v6 = -1073741808;
    goto LABEL_36;
  }
  v16 = GUID_FVE_SYNTHETIC_DATASET;
LABEL_43:
  v28 = v16;
  if ( !*(_BYTE *)(a2 + 64) )
  {
    if ( *((_BYTE *)a3 + 72) )
    {
      v20 = *(_QWORD *)(v11 + 680);
      if ( !v20 )
      {
        v6 = -1073741275;
        goto LABEL_36;
      }
      CachedExternalData = FveKeyringGetCachedExternalData(
                             v20,
                             (unsigned int)&v28,
                             v13,
                             (int)a3 + 8,
                             a3[24],
                             (__int64)v22,
                             *((void **)a3 + 8));
    }
    else
    {
      CachedExternalData = FveDataSetExternalDataGetEntryRawData(
                             (unsigned __int8)a1[123] + 64,
                             (__int64)v22,
                             *((void **)a3 + 8));
    }
    v6 = CachedExternalData;
    if ( CachedExternalData >= 0 )
    {
      **((_WORD **)a3 + 7) = v22[0];
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        159,
        WPP_db10fbeca6e03e7325aab39114461952_Traceguids,
        (unsigned int)CachedExternalData);
    }
    goto LABEL_36;
  }
  KeStackAttachProcess(PROCESS, &ApcState);
  v8 = 1;
  ProbeForWrite(*((volatile void **)a3 + 7), 2u, 4u);
  if ( a3[24] )
  {
    v17 = (volatile void *)*((_QWORD *)a3 + 8);
    if ( v17 )
      ProbeForWrite(v17, a3[24], 1u);
  }
  if ( *((_BYTE *)a3 + 72) )
  {
    v18 = *(_QWORD *)(v11 + 680);
    if ( !v18 )
    {
      v6 = -1073741275;
      v24 = -1073741275;
      v7 = 1;
      goto LABEL_13;
    }
    EntryRawData = FveKeyringGetCachedExternalData(
                     v18,
                     (unsigned int)&v28,
                     a1[127],
                     (int)a3 + 8,
                     a3[24],
                     (__int64)v22,
                     *((void **)a3 + 8));
  }
  else
  {
    EntryRawData = FveDataSetExternalDataGetEntryRawData(
                     (unsigned __int8)a1[123] + 64,
                     (__int64)v22,
                     *((void **)a3 + 8));
  }
  v24 = EntryRawData;
  v6 = EntryRawData;
  if ( EntryRawData >= 0 )
  {
    **((_WORD **)a3 + 7) = v22[0];
    v7 = 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        157,
        WPP_db10fbeca6e03e7325aab39114461952_Traceguids,
        (unsigned int)EntryRawData);
    }
    v7 = 1;
  }
LABEL_13:
  if ( v7 )
    FvepReleaseDevFveLock(v27);
  if ( v8 )
    KeUnstackDetachProcess(&ApcState);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 160, WPP_db10fbeca6e03e7325aab39114461952_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x140053c80  mov     r11, rsp
0x140053c83  push    rbx
0x140053c84  push    rsi
0x140053c85  push    rdi
0x140053c86  push    r12
0x140053c88  push    r13
0x140053c8a  push    r14
0x140053c8c  push    r15
0x140053c8e  sub     rsp, 140h
0x140053c95  mov     rax, cs:__security_cookie
0x140053c9c  xor     rax, rsp
0x140053c9f  mov     [rsp+178h+var_48], rax
0x140053ca7  mov     rsi, r8
0x140053caa  mov     r13, rdx
0x140053cad  mov     r15, rcx
0x140053cb0  xorps   xmm0, xmm0
0x140053cb3  movups  [rsp+178h+var_88], xmm0
0x140053cbb  xorps   xmm1, xmm1
0x140053cbe  movups  xmmword ptr [r11-78h], xmm1
0x140053cc3  movups  xmmword ptr [r11-68h], xmm1
0x140053cc8  movups  xmmword ptr [r11-58h], xmm1
0x140053ccd  xor     edi, edi
0x140053ccf  mov     word ptr [rsp+178h+var_134], di
0x140053cd4  xor     edx, edx; Val
0x140053cd6  mov     r8d, 90h; Size
0x140053cdc  lea     rcx, [rsp+178h+var_118]; void *
0x140053ce1  call    memset
0x140053ce6  lea     r12, WPP_GLOBAL_Control
0x140053ced  mov     rcx, cs:WPP_GLOBAL_Control
0x140053cf4  lea     r14d, [rdi+1]
0x140053cf8  cmp     rcx, r12
0x140053cfb  jz      short loc_140053D20
0x140053cfd  mov     eax, [rcx+2Ch]
0x140053d00  test    r14b, al
0x140053d03  jz      short loc_140053D20
0x140053d05  cmp     byte ptr [rcx+29h], 5
0x140053d09  jb      short loc_140053D20
0x140053d0b  mov     edx, 99h
0x140053d10  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x140053d17  mov     rcx, [rcx+18h]
0x140053d1b  call    WPP_SF_
0x140053d20  mov     word ptr [rsp+178h+var_134], di
0x140053d25  movzx   edx, word ptr [rsi]
0x140053d28  cmp     edx, 50h ; 'P'
0x140053d2b  jnb     loc_140053DED
0x140053d31  mov     rcx, cs:WPP_GLOBAL_Control
0x140053d38  cmp     rcx, r12
0x140053d3b  jz      short loc_140053D63
0x140053d3d  mov     eax, [rcx+2Ch]
0x140053d40  test    r14b, al
0x140053d43  jz      short loc_140053D63
0x140053d45  cmp     byte ptr [rcx+29h], 2
0x140053d49  jb      short loc_140053D63
0x140053d4b  mov     r9d, edx
0x140053d4e  mov     edx, 9Ah
0x140053d53  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x140053d5a  mov     rcx, [rcx+18h]
0x140053d5e  call    WPP_SF_d
0x140053d63  mov     ebx, 0C000000Dh
0x140053d68  mov     al, dil
0x140053d6b  mov     r13b, dil
0x140053d6e  test    al, al
0x140053d70  jz      short loc_140053D7C
0x140053d72  lea     rcx, [rsp+178h+var_118]
0x140053d77  call    FvepReleaseDevFveLock
0x140053d7c  test    r13b, r13b
0x140053d7f  jz      short loc_140053D95
0x140053d81  lea     rcx, [rsp+178h+ApcState]; ApcState
0x140053d89  call    cs:__imp_KeUnstackDetachProcess
0x140053d90  nop     dword ptr [rax+rax+00h]
0x140053d95  mov     rcx, cs:WPP_GLOBAL_Control
0x140053d9c  cmp     rcx, r12
0x140053d9f  jz      short loc_140053DC7
0x140053da1  mov     eax, [rcx+2Ch]
0x140053da4  test    r14b, al
0x140053da7  jz      short loc_140053DC7
0x140053da9  cmp     byte ptr [rcx+29h], 5
0x140053dad  jb      short loc_140053DC7
0x140053daf  mov     edx, 0A0h
0x140053db4  mov     r9d, ebx
0x140053db7  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x140053dbe  mov     rcx, [rcx+18h]
0x140053dc2  call    WPP_SF_d
0x140053dc7  mov     eax, ebx
0x140053dc9  mov     rcx, [rsp+178h+var_48]
0x140053dd1  xor     rcx, rsp; StackCookie
0x140053dd4  call    __security_check_cookie
0x140053dd9  add     rsp, 140h
0x140053de0  pop     r15
0x140053de2  pop     r14
0x140053de4  pop     r13
0x140053de6  pop     r12
0x140053de8  pop     rdi
0x140053de9  pop     rsi
0x140053dea  pop     rbx
0x140053deb  retn
0x140053ded  mov     r8d, [rsi+4]
0x140053df1  cmp     r8d, 1Ch
0x140053df5  jnz     loc_140054179
0x140053dfb  cmp     [rsi+2], r14w
0x140053e00  jnz     loc_140054179
0x140053e06  mov     rbx, [r15+8]
0x140053e0a  mov     [rsp+178h+var_128], rbx
0x140053e0f  mov     rax, [r13+78h]
0x140053e13  mov     [rsp+178h+PROCESS], rax
0x140053e18  cmp     [r13+40h], dil
0x140053e1c  jz      short loc_140053E7A
0x140053e1e  mov     r8d, r14d
0x140053e21  mov     rdx, r13
0x140053e24  mov     rcx, r15
0x140053e27  call    FveCheckAdminAccess
0x140053e2c  mov     ebx, eax
0x140053e2e  test    eax, eax
0x140053e30  jns     short loc_140053E75
0x140053e32  mov     rcx, cs:WPP_GLOBAL_Control
0x140053e39  cmp     rcx, r12
0x140053e3c  jz      loc_140053D68
0x140053e42  mov     edx, [rcx+2Ch]
0x140053e45  test    r14b, dl
0x140053e48  jz      loc_140053D68
0x140053e4e  cmp     byte ptr [rcx+29h], 2
0x140053e52  jb      loc_140053D68
0x140053e58  mov     edx, 9Ch
0x140053e5d  mov     r9d, eax
0x140053e60  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x140053e67  mov     rcx, [rcx+18h]
0x140053e6b  call    WPP_SF_d
0x140053e70  jmp     loc_140053D68
0x140053e75  mov     rbx, [rsp+178h+var_128]
0x140053e7a  xor     r8d, r8d
0x140053e7d  lea     rdx, [rsp+178h+var_118]
0x140053e82  mov     rcx, r15
0x140053e85  call    FvepAcquireDevFveLock
0x140053e8a  mov     al, r14b
0x140053e8d  mov     [rsp+178h+var_138], al
0x140053e91  mov     byte ptr [rsp+178h+var_134+4], al
0x140053e95  mov     rdx, [r15+3F8h]
0x140053e9c  mov     rax, [r15+3D0h]
0x140053ea3  test    rdx, rdx
0x140053ea6  jz      short loc_140053ECC
0x140053ea8  test    rax, rax
0x140053eab  jz      short loc_140053EBF
0x140053ead  mov     rax, [r15+3D8h]
0x140053eb4  test    rax, rax
0x140053eb7  jz      short loc_140053EBF
0x140053eb9  movups  xmm0, xmmword ptr [rax+50h]
0x140053ebd  jmp     short loc_140053EF9
0x140053ebf  mov     ebx, 0C0210001h
0x140053ec4  mov     al, r14b
0x140053ec7  jmp     loc_140053D6B
0x140053ecc  test    rax, rax
0x140053ecf  jz      short loc_140053ED8
0x140053ed1  mov     ebx, 0C0210000h
0x140053ed6  jmp     short loc_140053EC4
0x140053ed8  cmp     [rsi+48h], dil
0x140053edc  jz      short loc_140053EBF
0x140053ede  mov     rax, [r15+78h]
0x140053ee2  test    dword ptr [rax+30h], 400100h
0x140053ee9  jnz     short loc_140053EF2
0x140053eeb  mov     ebx, 0C0000010h
0x140053ef0  jmp     short loc_140053EC4
0x140053ef2  movups  xmm0, xmmword ptr cs:GUID_FVE_SYNTHETIC_DATASET.Data1
0x140053ef9  movdqu  [rsp+178h+var_88], xmm0
0x140053f02  cmp     [r13+40h], dil
0x140053f06  jz      loc_1400540A5
0x140053f0c  lea     rdx, [rsp+178h+ApcState]; ApcState
0x140053f14  mov     rcx, [rsp+178h+PROCESS]; PROCESS
0x140053f19  call    cs:__imp_KeStackAttachProcess
0x140053f20  nop     dword ptr [rax+rax+00h]
0x140053f25  mov     r13b, r14b
0x140053f28  mov     edx, 2; Length
0x140053f2d  lea     r8d, [rdx+2]; Alignment
0x140053f31  mov     rcx, [rsi+38h]; Address
0x140053f35  call    cs:__imp_ProbeForWrite
0x140053f3c  nop     dword ptr [rax+rax+00h]
0x140053f41  movzx   eax, word ptr [rsi+30h]
0x140053f45  test    ax, ax
0x140053f48  jz      short loc_140053F64
0x140053f4a  mov     rcx, [rsi+40h]; Address
0x140053f4e  test    rcx, rcx
0x140053f51  jz      short loc_140053F64
0x140053f53  mov     edx, eax; Length
0x140053f55  mov     r8d, r14d; Alignment
0x140053f58  call    cs:__imp_ProbeForWrite
0x140053f5f  nop     dword ptr [rax+rax+00h]
0x140053f64  cmp     [rsi+48h], dil
0x140053f68  jz      short loc_140053FBE
0x140053f6a  mov     rcx, [rbx+2A8h]
0x140053f71  test    rcx, rcx
0x140053f74  jnz     short loc_140053F88
0x140053f76  mov     ebx, 0C0000225h
0x140053f7b  mov     [rsp+178h+var_12C], ebx
0x140053f7f  mov     al, [rsp+178h+var_138]
0x140053f83  jmp     loc_140053D6E
0x140053f88  lea     r9, [rsi+8]
0x140053f8c  mov     rax, [rsi+40h]
0x140053f90  mov     [rsp+178h+var_148], rax
0x140053f95  lea     rax, [rsp+178h+var_134]
0x140053f9a  mov     [rsp+178h+var_150], rax
0x140053f9f  movzx   eax, word ptr [rsi+30h]
0x140053fa3  mov     word ptr [rsp+178h+var_158], ax
0x140053fa8  mov     r8, [r15+3F8h]
0x140053faf  lea     rdx, [rsp+178h+var_88]
0x140053fb7  call    FveKeyringGetCachedExternalData
0x140053fbc  jmp     short loc_140053FF1
0x140053fbe  lea     r8, [rsi+8]
0x140053fc2  mov     rcx, [r15+3D8h]
0x140053fc9  add     rcx, 40h ; '@'; char
0x140053fcd  mov     rax, [rsi+40h]
0x140053fd1  mov     [rsp+178h+var_150], rax; void *
0x140053fd6  lea     rax, [rsp+178h+var_134]
0x140053fdb  mov     [rsp+178h+var_158], rax; __int64
0x140053fe0  movzx   r9d, word ptr [rsi+30h]
0x140053fe5  mov     rdx, [r15+3F8h]
0x140053fec  call    FveDataSetExternalDataGetEntryRawData
0x140053ff1  mov     [rsp+178h+var_12C], eax
0x140053ff5  mov     ebx, eax
0x140053ff7  test    eax, eax
0x140053ff9  jns     short loc_140054036
0x140053ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x140054002  cmp     rcx, r12
0x140054005  jz      short loc_14005402D
0x140054007  mov     eax, [rcx+2Ch]
0x14005400a  test    r14b, al
0x14005400d  jz      short loc_14005402D
0x14005400f  cmp     byte ptr [rcx+29h], 2
0x140054013  jb      short loc_14005402D
0x140054015  mov     edx, 9Dh
0x14005401a  mov     r9d, ebx
0x14005401d  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x140054024  mov     rcx, [rcx+18h]
0x140054028  call    WPP_SF_d
0x14005402d  mov     al, [rsp+178h+var_138]
0x140054031  jmp     loc_140053D6E
0x140054036  mov     rcx, [rsi+38h]
0x14005403a  movzx   eax, word ptr [rsp+178h+var_134]
0x14005403f  mov     [rcx], ax
0x140054042  mov     al, [rsp+178h+var_138]
0x140054046  jmp     loc_140053D6E
0x14005404b  mov     ebx, 0C000000Dh
0x140054050  mov     [rsp+178h+var_12C], ebx
0x140054054  lea     rax, WPP_GLOBAL_Control
0x14005405b  mov     rcx, cs:WPP_GLOBAL_Control
0x140054062  cmp     rcx, rax
0x140054065  jz      short loc_14005408C
0x140054067  mov     eax, [rcx+2Ch]
0x14005406a  test    al, 1
0x14005406c  jz      short loc_14005408C
0x14005406e  cmp     byte ptr [rcx+29h], 2
0x140054072  jb      short loc_14005408C
0x140054074  mov     edx, 9Eh
0x140054079  mov     r9d, ebx
0x14005407c  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x140054083  mov     rcx, [rcx+18h]
0x140054087  call    WPP_SF_d
0x14005408c  lea     r12, WPP_GLOBAL_Control
0x140054093  mov     r14d, 1
0x140054099  mov     al, byte ptr [rsp+178h+var_134+4]
0x14005409d  mov     r13b, al
0x1400540a0  jmp     loc_140053D6E
0x1400540a5  cmp     [rsi+48h], dil
0x1400540a9  jz      short loc_1400540F3
0x1400540ab  mov     rcx, [rbx+2A8h]
0x1400540b2  test    rcx, rcx
0x1400540b5  jnz     short loc_1400540C1
0x1400540b7  mov     ebx, 0C0000225h
0x1400540bc  jmp     loc_140053EC4
0x1400540c1  lea     r9, [rsi+8]
0x1400540c5  mov     rax, [rsi+40h]
0x1400540c9  mov     [rsp+178h+var_148], rax
0x1400540ce  lea     rax, [rsp+178h+var_134]
0x1400540d3  mov     [rsp+178h+var_150], rax
0x1400540d8  movzx   eax, word ptr [rsi+30h]
0x1400540dc  mov     word ptr [rsp+178h+var_158], ax
0x1400540e1  mov     r8, rdx
0x1400540e4  lea     rdx, [rsp+178h+var_88]
0x1400540ec  call    FveKeyringGetCachedExternalData
0x1400540f1  jmp     short loc_14005411F
0x1400540f3  lea     r8, [rsi+8]
0x1400540f7  mov     rcx, [r15+3D8h]
0x1400540fe  add     rcx, 40h ; '@'; char
0x140054102  mov     rax, [rsi+40h]
0x140054106  mov     [rsp+178h+var_150], rax; void *
0x14005410b  lea     rax, [rsp+178h+var_134]
0x140054110  mov     [rsp+178h+var_158], rax; __int64
0x140054115  movzx   r9d, word ptr [rsi+30h]
0x14005411a  call    FveDataSetExternalDataGetEntryRawData
0x14005411f  mov     ebx, eax
0x140054121  test    eax, eax
0x140054123  jns     short loc_140054168
0x140054125  mov     rcx, cs:WPP_GLOBAL_Control
0x14005412c  cmp     rcx, r12
0x14005412f  jz      loc_140053EC4
0x140054135  mov     eax, [rcx+2Ch]
0x140054138  test    r14b, al
0x14005413b  jz      loc_140053EC4
0x140054141  cmp     byte ptr [rcx+29h], 2
0x140054145  jb      loc_140053EC4
0x14005414b  mov     edx, 9Fh
0x140054150  mov     r9d, ebx
  ... truncated ...
```
