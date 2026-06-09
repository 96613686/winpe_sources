# ActionFveExternalDataGetEntryRawData

- ea: `0x140055c90`
- end: `0x1400561d3`
- name: `ActionFveExternalDataGetEntryRawData`
- size: `1347`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14008b6ec`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000afb4`
- `0x14000ba48`
- `0x140012904`
- `0x140015b0c`
- `0x140022bf0`
- `0x140023040`
- `0x140055c90`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140055f45`
- `ntoskrnl!ProbeForWrite` at `0x140055f68`
- `ntoskrnl!ProbeForWrite` at `0x140055f45`
- `ntoskrnl!ProbeForWrite` at `0x140055f68`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140055d99`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140055d99`
- `ntoskrnl!KeStackAttachProcess` at `0x140055f29`
- `ntoskrnl!KeStackAttachProcess` at `0x140055f29`

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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 154, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids);
  }
  v22[0] = 0;
  if ( *a3 < 0x50u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 155, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids, *a3);
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
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 156, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids, a3[1], v10);
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
          157,
          WPP_314c37a8eeb93938f289173f56a197f3_Traceguids,
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
        160,
        WPP_314c37a8eeb93938f289173f56a197f3_Traceguids,
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
        158,
        WPP_314c37a8eeb93938f289173f56a197f3_Traceguids,
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 161, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x140055c90  mov     r11, rsp
0x140055c93  push    rbx
0x140055c94  push    rsi
0x140055c95  push    rdi
0x140055c96  push    r12
0x140055c98  push    r13
0x140055c9a  push    r14
0x140055c9c  push    r15
0x140055c9e  sub     rsp, 140h
0x140055ca5  mov     rax, cs:__security_cookie
0x140055cac  xor     rax, rsp
0x140055caf  mov     [rsp+178h+var_48], rax
0x140055cb7  mov     rsi, r8
0x140055cba  mov     r13, rdx
0x140055cbd  mov     r15, rcx
0x140055cc0  xorps   xmm0, xmm0
0x140055cc3  movups  [rsp+178h+var_88], xmm0
0x140055ccb  xorps   xmm1, xmm1
0x140055cce  movups  xmmword ptr [r11-78h], xmm1
0x140055cd3  movups  xmmword ptr [r11-68h], xmm1
0x140055cd8  movups  xmmword ptr [r11-58h], xmm1
0x140055cdd  xor     edi, edi
0x140055cdf  mov     word ptr [rsp+178h+var_134], di
0x140055ce4  xor     edx, edx; Val
0x140055ce6  mov     r8d, 90h; Size
0x140055cec  lea     rcx, [rsp+178h+var_118]; void *
0x140055cf1  call    memset
0x140055cf6  lea     r12, WPP_GLOBAL_Control
0x140055cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140055d04  lea     r14d, [rdi+1]
0x140055d08  cmp     rcx, r12
0x140055d0b  jz      short loc_140055D30
0x140055d0d  mov     eax, [rcx+2Ch]
0x140055d10  test    r14b, al
0x140055d13  jz      short loc_140055D30
0x140055d15  cmp     byte ptr [rcx+29h], 5
0x140055d19  jb      short loc_140055D30
0x140055d1b  mov     edx, 9Ah
0x140055d20  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140055d27  mov     rcx, [rcx+18h]
0x140055d2b  call    WPP_SF_
0x140055d30  mov     word ptr [rsp+178h+var_134], di
0x140055d35  movzx   edx, word ptr [rsi]
0x140055d38  cmp     edx, 50h ; 'P'
0x140055d3b  jnb     loc_140055DFD
0x140055d41  mov     rcx, cs:WPP_GLOBAL_Control
0x140055d48  cmp     rcx, r12
0x140055d4b  jz      short loc_140055D73
0x140055d4d  mov     eax, [rcx+2Ch]
0x140055d50  test    r14b, al
0x140055d53  jz      short loc_140055D73
0x140055d55  cmp     byte ptr [rcx+29h], 2
0x140055d59  jb      short loc_140055D73
0x140055d5b  mov     r9d, edx
0x140055d5e  mov     edx, 9Bh
0x140055d63  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140055d6a  mov     rcx, [rcx+18h]
0x140055d6e  call    WPP_SF_d
0x140055d73  mov     ebx, 0C000000Dh
0x140055d78  mov     al, dil
0x140055d7b  mov     r13b, dil
0x140055d7e  test    al, al
0x140055d80  jz      short loc_140055D8C
0x140055d82  lea     rcx, [rsp+178h+var_118]
0x140055d87  call    FvepReleaseDevFveLock
0x140055d8c  test    r13b, r13b
0x140055d8f  jz      short loc_140055DA5
0x140055d91  lea     rcx, [rsp+178h+ApcState]; ApcState
0x140055d99  call    cs:__imp_KeUnstackDetachProcess
0x140055da0  nop     dword ptr [rax+rax+00h]
0x140055da5  mov     rcx, cs:WPP_GLOBAL_Control
0x140055dac  cmp     rcx, r12
0x140055daf  jz      short loc_140055DD7
0x140055db1  mov     eax, [rcx+2Ch]
0x140055db4  test    r14b, al
0x140055db7  jz      short loc_140055DD7
0x140055db9  cmp     byte ptr [rcx+29h], 5
0x140055dbd  jb      short loc_140055DD7
0x140055dbf  mov     edx, 0A1h
0x140055dc4  mov     r9d, ebx
0x140055dc7  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140055dce  mov     rcx, [rcx+18h]
0x140055dd2  call    WPP_SF_d
0x140055dd7  mov     eax, ebx
0x140055dd9  mov     rcx, [rsp+178h+var_48]
0x140055de1  xor     rcx, rsp; StackCookie
0x140055de4  call    __security_check_cookie
0x140055de9  add     rsp, 140h
0x140055df0  pop     r15
0x140055df2  pop     r14
0x140055df4  pop     r13
0x140055df6  pop     r12
0x140055df8  pop     rdi
0x140055df9  pop     rsi
0x140055dfa  pop     rbx
0x140055dfb  retn
0x140055dfd  mov     r8d, [rsi+4]
0x140055e01  cmp     r8d, 1Ch
0x140055e05  jnz     loc_140056189
0x140055e0b  cmp     [rsi+2], r14w
0x140055e10  jnz     loc_140056189
0x140055e16  mov     rbx, [r15+8]
0x140055e1a  mov     [rsp+178h+var_128], rbx
0x140055e1f  mov     rax, [r13+78h]
0x140055e23  mov     [rsp+178h+PROCESS], rax
0x140055e28  cmp     [r13+40h], dil
0x140055e2c  jz      short loc_140055E8A
0x140055e2e  mov     r8d, r14d
0x140055e31  mov     rdx, r13
0x140055e34  mov     rcx, r15
0x140055e37  call    FveCheckAdminAccess
0x140055e3c  mov     ebx, eax
0x140055e3e  test    eax, eax
0x140055e40  jns     short loc_140055E85
0x140055e42  mov     rcx, cs:WPP_GLOBAL_Control
0x140055e49  cmp     rcx, r12
0x140055e4c  jz      loc_140055D78
0x140055e52  mov     edx, [rcx+2Ch]
0x140055e55  test    r14b, dl
0x140055e58  jz      loc_140055D78
0x140055e5e  cmp     byte ptr [rcx+29h], 2
0x140055e62  jb      loc_140055D78
0x140055e68  mov     edx, 9Dh
0x140055e6d  mov     r9d, eax
0x140055e70  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140055e77  mov     rcx, [rcx+18h]
0x140055e7b  call    WPP_SF_d
0x140055e80  jmp     loc_140055D78
0x140055e85  mov     rbx, [rsp+178h+var_128]
0x140055e8a  xor     r8d, r8d
0x140055e8d  lea     rdx, [rsp+178h+var_118]
0x140055e92  mov     rcx, r15
0x140055e95  call    FvepAcquireDevFveLock
0x140055e9a  mov     al, r14b
0x140055e9d  mov     [rsp+178h+var_138], al
0x140055ea1  mov     byte ptr [rsp+178h+var_134+4], al
0x140055ea5  mov     rdx, [r15+3F8h]
0x140055eac  mov     rax, [r15+3D0h]
0x140055eb3  test    rdx, rdx
0x140055eb6  jz      short loc_140055EDC
0x140055eb8  test    rax, rax
0x140055ebb  jz      short loc_140055ECF
0x140055ebd  mov     rax, [r15+3D8h]
0x140055ec4  test    rax, rax
0x140055ec7  jz      short loc_140055ECF
0x140055ec9  movups  xmm0, xmmword ptr [rax+50h]
0x140055ecd  jmp     short loc_140055F09
0x140055ecf  mov     ebx, 0C0210001h
0x140055ed4  mov     al, r14b
0x140055ed7  jmp     loc_140055D7B
0x140055edc  test    rax, rax
0x140055edf  jz      short loc_140055EE8
0x140055ee1  mov     ebx, 0C0210000h
0x140055ee6  jmp     short loc_140055ED4
0x140055ee8  cmp     [rsi+48h], dil
0x140055eec  jz      short loc_140055ECF
0x140055eee  mov     rax, [r15+78h]
0x140055ef2  test    dword ptr [rax+30h], 400100h
0x140055ef9  jnz     short loc_140055F02
0x140055efb  mov     ebx, 0C0000010h
0x140055f00  jmp     short loc_140055ED4
0x140055f02  movups  xmm0, xmmword ptr cs:GUID_FVE_SYNTHETIC_DATASET.Data1
0x140055f09  movdqu  [rsp+178h+var_88], xmm0
0x140055f12  cmp     [r13+40h], dil
0x140055f16  jz      loc_1400560B5
0x140055f1c  lea     rdx, [rsp+178h+ApcState]; ApcState
0x140055f24  mov     rcx, [rsp+178h+PROCESS]; PROCESS
0x140055f29  call    cs:__imp_KeStackAttachProcess
0x140055f30  nop     dword ptr [rax+rax+00h]
0x140055f35  mov     r13b, r14b
0x140055f38  mov     edx, 2; Length
0x140055f3d  lea     r8d, [rdx+2]; Alignment
0x140055f41  mov     rcx, [rsi+38h]; Address
0x140055f45  call    cs:__imp_ProbeForWrite
0x140055f4c  nop     dword ptr [rax+rax+00h]
0x140055f51  movzx   eax, word ptr [rsi+30h]
0x140055f55  test    ax, ax
0x140055f58  jz      short loc_140055F74
0x140055f5a  mov     rcx, [rsi+40h]; Address
0x140055f5e  test    rcx, rcx
0x140055f61  jz      short loc_140055F74
0x140055f63  mov     edx, eax; Length
0x140055f65  mov     r8d, r14d; Alignment
0x140055f68  call    cs:__imp_ProbeForWrite
0x140055f6f  nop     dword ptr [rax+rax+00h]
0x140055f74  cmp     [rsi+48h], dil
0x140055f78  jz      short loc_140055FCE
0x140055f7a  mov     rcx, [rbx+2A8h]
0x140055f81  test    rcx, rcx
0x140055f84  jnz     short loc_140055F98
0x140055f86  mov     ebx, 0C0000225h
0x140055f8b  mov     [rsp+178h+var_12C], ebx
0x140055f8f  mov     al, [rsp+178h+var_138]
0x140055f93  jmp     loc_140055D7E
0x140055f98  lea     r9, [rsi+8]
0x140055f9c  mov     rax, [rsi+40h]
0x140055fa0  mov     [rsp+178h+var_148], rax
0x140055fa5  lea     rax, [rsp+178h+var_134]
0x140055faa  mov     [rsp+178h+var_150], rax
0x140055faf  movzx   eax, word ptr [rsi+30h]
0x140055fb3  mov     word ptr [rsp+178h+var_158], ax
0x140055fb8  mov     r8, [r15+3F8h]
0x140055fbf  lea     rdx, [rsp+178h+var_88]
0x140055fc7  call    FveKeyringGetCachedExternalData
0x140055fcc  jmp     short loc_140056001
0x140055fce  lea     r8, [rsi+8]
0x140055fd2  mov     rcx, [r15+3D8h]
0x140055fd9  add     rcx, 40h ; '@'; char
0x140055fdd  mov     rax, [rsi+40h]
0x140055fe1  mov     [rsp+178h+var_150], rax; void *
0x140055fe6  lea     rax, [rsp+178h+var_134]
0x140055feb  mov     [rsp+178h+var_158], rax; __int64
0x140055ff0  movzx   r9d, word ptr [rsi+30h]
0x140055ff5  mov     rdx, [r15+3F8h]
0x140055ffc  call    FveDataSetExternalDataGetEntryRawData
0x140056001  mov     [rsp+178h+var_12C], eax
0x140056005  mov     ebx, eax
0x140056007  test    eax, eax
0x140056009  jns     short loc_140056046
0x14005600b  mov     rcx, cs:WPP_GLOBAL_Control
0x140056012  cmp     rcx, r12
0x140056015  jz      short loc_14005603D
0x140056017  mov     eax, [rcx+2Ch]
0x14005601a  test    r14b, al
0x14005601d  jz      short loc_14005603D
0x14005601f  cmp     byte ptr [rcx+29h], 2
0x140056023  jb      short loc_14005603D
0x140056025  mov     edx, 9Eh
0x14005602a  mov     r9d, ebx
0x14005602d  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140056034  mov     rcx, [rcx+18h]
0x140056038  call    WPP_SF_d
0x14005603d  mov     al, [rsp+178h+var_138]
0x140056041  jmp     loc_140055D7E
0x140056046  mov     rcx, [rsi+38h]
0x14005604a  movzx   eax, word ptr [rsp+178h+var_134]
0x14005604f  mov     [rcx], ax
0x140056052  mov     al, [rsp+178h+var_138]
0x140056056  jmp     loc_140055D7E
0x14005605b  mov     ebx, 0C000000Dh
0x140056060  mov     [rsp+178h+var_12C], ebx
0x140056064  lea     rax, WPP_GLOBAL_Control
0x14005606b  mov     rcx, cs:WPP_GLOBAL_Control
0x140056072  cmp     rcx, rax
0x140056075  jz      short loc_14005609C
0x140056077  mov     eax, [rcx+2Ch]
0x14005607a  test    al, 1
0x14005607c  jz      short loc_14005609C
0x14005607e  cmp     byte ptr [rcx+29h], 2
0x140056082  jb      short loc_14005609C
0x140056084  mov     edx, 9Fh
0x140056089  mov     r9d, ebx
0x14005608c  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140056093  mov     rcx, [rcx+18h]
0x140056097  call    WPP_SF_d
0x14005609c  lea     r12, WPP_GLOBAL_Control
0x1400560a3  mov     r14d, 1
0x1400560a9  mov     al, byte ptr [rsp+178h+var_134+4]
0x1400560ad  mov     r13b, al
0x1400560b0  jmp     loc_140055D7E
0x1400560b5  cmp     [rsi+48h], dil
0x1400560b9  jz      short loc_140056103
0x1400560bb  mov     rcx, [rbx+2A8h]
0x1400560c2  test    rcx, rcx
0x1400560c5  jnz     short loc_1400560D1
0x1400560c7  mov     ebx, 0C0000225h
0x1400560cc  jmp     loc_140055ED4
0x1400560d1  lea     r9, [rsi+8]
0x1400560d5  mov     rax, [rsi+40h]
0x1400560d9  mov     [rsp+178h+var_148], rax
0x1400560de  lea     rax, [rsp+178h+var_134]
0x1400560e3  mov     [rsp+178h+var_150], rax
0x1400560e8  movzx   eax, word ptr [rsi+30h]
0x1400560ec  mov     word ptr [rsp+178h+var_158], ax
0x1400560f1  mov     r8, rdx
0x1400560f4  lea     rdx, [rsp+178h+var_88]
0x1400560fc  call    FveKeyringGetCachedExternalData
0x140056101  jmp     short loc_14005612F
0x140056103  lea     r8, [rsi+8]
0x140056107  mov     rcx, [r15+3D8h]
0x14005610e  add     rcx, 40h ; '@'; char
0x140056112  mov     rax, [rsi+40h]
0x140056116  mov     [rsp+178h+var_150], rax; void *
0x14005611b  lea     rax, [rsp+178h+var_134]
0x140056120  mov     [rsp+178h+var_158], rax; __int64
0x140056125  movzx   r9d, word ptr [rsi+30h]
0x14005612a  call    FveDataSetExternalDataGetEntryRawData
0x14005612f  mov     ebx, eax
0x140056131  test    eax, eax
0x140056133  jns     short loc_140056178
0x140056135  mov     rcx, cs:WPP_GLOBAL_Control
0x14005613c  cmp     rcx, r12
0x14005613f  jz      loc_140055ED4
0x140056145  mov     eax, [rcx+2Ch]
0x140056148  test    r14b, al
0x14005614b  jz      loc_140055ED4
0x140056151  cmp     byte ptr [rcx+29h], 2
0x140056155  jb      loc_140055ED4
0x14005615b  mov     edx, 0A0h
0x140056160  mov     r9d, ebx
  ... truncated ...
```
