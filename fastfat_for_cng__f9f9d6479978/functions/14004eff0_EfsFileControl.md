# EfsFileControl

- ea: `0x14004eff0`
- end: `0x14004f8a8`
- name: `EfsFileControl`
- size: `2232`
- prototype: `__int64 __fastcall(int, int, int, int, int, char, int, int, __int64, __int64, __int64, int, PDEVICE_OBJECT DeviceObject, int, int, char, PSECURITY_DESCRIPTOR SecurityDescriptor, __int64, char, char, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1400077e4`
- `0x140008090`
- `0x14000c260`
- `0x140020008`
- `0x1400201b0`
- `0x14004e560`
- `0x14004ed40`
- `0x14004eff0`
- `0x140051788`
- `0x1400518a8`
- `0x1400518e8`
- `0x140051948`
- `0x140053a88`
- `0x140054480`
- `0x14005489c`
- `0x14005521c`
- `0x1400566c4`
- `0x14005693c`
- `0x140056ccc`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14004f6c3`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14004f767`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14004f6c3`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14004f767`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f676`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f703`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f676`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f703`

## pseudocode

```c
__int64 __fastcall EfsFileControl(
        __int64 a1,
        int a2,
        _DWORD *a3,
        _DWORD *a4,
        int a5,
        char a6,
        int a7,
        int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        int a12,
        PDEVICE_OBJECT DeviceObject,
        int a14,
        int a15,
        char a16,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        _WORD *a18,
        char a19,
        char a20,
        __int64 a21,
        bool *a22,
        _BYTE *a23,
        int *a24,
        _BYTE *a25,
        PVOID *a26)
{
  _UNKNOWN **v26; // rax
  __int64 v28; // rsi
  bool *v29; // r14
  int v30; // r9d
  __int64 v31; // r8
  int EfsData; // edi
  int v33; // r8d
  __int64 v34; // r15
  unsigned int v35; // r12d
  __int64 v36; // r9
  unsigned int v37; // r13d
  bool v38; // si
  __int64 *v39; // rcx
  char v40; // di
  char v41; // al
  int v42; // esi
  void *v43; // r15
  char v45; // [rsp+60h] [rbp-98h] BYREF
  bool v46[3]; // [rsp+61h] [rbp-97h] BYREF
  int v47; // [rsp+64h] [rbp-94h]
  int v48; // [rsp+68h] [rbp-90h] BYREF
  _DWORD Size[3]; // [rsp+6Ch] [rbp-8Ch] BYREF
  __int128 v50; // [rsp+78h] [rbp-80h] BYREF
  __int128 v51; // [rsp+88h] [rbp-70h]
  __int128 v52; // [rsp+98h] [rbp-60h]
  int v53; // [rsp+A8h] [rbp-50h]
  __int64 v54; // [rsp+B0h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+F8h] [rbp+0h] BYREF
  char v56; // [rsp+100h] [rbp+8h]
  _DWORD *v57; // [rsp+110h] [rbp+18h]

  v26 = &retaddr;
  v57 = a3;
  v28 = a1;
  memset(Size, 0, sizeof(Size));
  v48 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v45 = 0;
  LOBYTE(v26) = 0;
  v53 = (int)v26;
  v46[0] = 0;
  v56 = 0;
  if ( !a1 || !byte_140017924 )
  {
    v29 = a22;
LABEL_116:
    v31 = 1338;
    goto LABEL_117;
  }
  v29 = a22;
  if ( !a22 || !a24 )
    goto LABEL_116;
  *a22 = 0;
  if ( a16 )
    *a23 = 0;
  *a25 = 0;
  if ( *(_BYTE *)(a10 + 64) && !EfspHasTCBPrivilege() )
  {
    v30 = -1073741790;
    v31 = 1359;
LABEL_118:
    EfsData = v30;
    EfspTraceLogAssert(a1, 5, v31);
    goto LABEL_119;
  }
  LOBYTE(a3) = *(_BYTE *)(a10 + 64);
  EfsData = EfspValidateAndParseFsctl(v28, a2, (_DWORD)a3, (unsigned int)&v45, (__int64)&v50);
  if ( EfsData < 0 )
    goto LABEL_119;
  v34 = 0;
  v54 = 0;
  v35 = DWORD1(v50);
  if ( v45 )
  {
    v34 = v28;
    v54 = v28;
    LOBYTE(a1) = *(_BYTE *)(v28 + 6);
    *a22 = a1;
  }
  v36 = DWORD2(v50);
  v37 = DWORD2(v50) & 0xF77FFFFF;
  if ( a8 == 590039 )
  {
    if ( (a7 & 1) != 0 )
    {
LABEL_15:
      EfsData = -1073741662;
      goto LABEL_119;
    }
    if ( v35 )
    {
      if ( v35 != 1 && v35 != 4 )
      {
        v31 = 1433;
        goto LABEL_117;
      }
    }
    else if ( (_DWORD)v50 != (DWORD2(v50) & 0x777FFFFF) )
    {
      v31 = 1426;
LABEL_117:
      v30 = -1073741808;
      goto LABEL_118;
    }
  }
  if ( !*a22
    && !v35
    && (SDWORD2(v50) & 0x80000000) == 0
    && (DWORD2(v50) & 0x800000) == 0
    && ((DWORD2(v50) & 0x8000000) != 0 && (v37 == 1 || v37 == 4) || v37 == 3) )
  {
    if ( DeviceObject )
    {
      EfspCanOffloadCrypto(a1, *(unsigned int *)(*((_QWORD *)&v51 + 1) + 4LL), a21, v46);
      v38 = v46[0];
      if ( v46[0] )
        v38 = (unsigned __int8)EfspIsCryptoOffloadTurnedOffByOverride() != 1;
      v36 = DWORD2(v50);
    }
    else
    {
      v38 = v53;
    }
    *a22 = v38;
    if ( v38 )
    {
      EfsData = EfspDevCryptoSetup(DeviceObject);
      if ( EfsData < 0 )
        goto LABEL_119;
      v56 = 1;
      v36 = DWORD2(v50);
    }
  }
  if ( v35 > 5 )
  {
    if ( v35 != 6 )
    {
      if ( v35 == 7 )
        goto LABEL_119;
      if ( v35 != 8 && v35 != 9 )
      {
        if ( v35 != 10 )
        {
          v30 = -1073741808;
          v31 = 1991;
          goto LABEL_118;
        }
LABEL_88:
        if ( v57 && *a4 >= 4u )
        {
          if ( (a5 & 2) != 0 )
          {
            LOBYTE(v33) = v35 == 10;
            EfsData = EfsReadEfsData(a9, a11, v33, (unsigned int)&Size[1], (__int64)Size, (__int64)&v48);
            EfspReleaseFsCtlData(&v50);
            switch ( v48 )
            {
              case 0x10000:
                EfsData = 0;
                v47 = 0;
                v41 = *(_BYTE *)(a10 + 64);
                v42 = Size[0];
                if ( Size[0] <= *a4 )
                {
                  v43 = *(void **)&Size[1];
                  if ( v41 )
                    RtlCopyToUser(v57, *(void **)&Size[1], Size[0]);
                  else
                    RtlCopyVolatileMemory(v57, *(const void **)&Size[1], Size[0]);
                  *a4 = v42;
                  ExFreePoolWithTag(v43, 0);
                }
                else
                {
                  if ( v41 )
                    RtlWriteULongToUser(v57, Size[0]);
                  else
                    *v57 = Size[0];
                  *a4 = 4;
                  ExFreePoolWithTag(*(PVOID *)&Size[1], 0);
                  EfsData = -1073741789;
                  v47 = -1073741789;
                }
                break;
              case 0x200:
                EfsData = -1073741167;
                break;
              case 0x1000:
                v30 = -1073741808;
                v31 = 1784;
                goto LABEL_118;
            }
          }
          else
          {
            EfsData = -1073741808;
          }
        }
        else
        {
          EfsData = -1073741811;
          v47 = -1073741811;
          EfspTraceLogAssert(a1, 5, 1694);
        }
        goto LABEL_119;
      }
    }
    goto LABEL_107;
  }
  if ( v35 == 5 )
  {
LABEL_107:
    if ( a18 && *a18 )
    {
      EfsData = -1073741811;
      goto LABEL_119;
    }
    if ( (a7 & 1) != 0 )
      goto LABEL_15;
    if ( (a6 & 2) == 0
      && !(unsigned __int8)EfspOnlineEncryptionAccessCheck((_DWORD)SecurityDescriptor, v35, v33, v36, a16) )
    {
      v31 = 1892;
      goto LABEL_47;
    }
    LOBYTE(v36) = a16;
    EfsData = EfsModifyEfsState(v35, a9, a11, v36);
    goto LABEL_57;
  }
  if ( v35 )
  {
    if ( v35 == 1 )
    {
      if ( a19 || (v36 & 8) != 0 && (a5 & 2) == 0 || (v36 & 4) != 0 && (a5 & 1) == 0 )
      {
        *a25 = 1;
        goto LABEL_119;
      }
      v39 = (__int64 *)(v34 + 8);
      if ( !v34 )
        v39 = 0;
LABEL_66:
      EfsData = SetEfsData((__int64)&v50, a7, a5, a9, a11, v39, a20, (__int64)DeviceObject, a24, a25, a26);
      EfspReleaseFsCtlData(&v50);
      if ( *a22 && !*a26 )
        *a22 = 0;
      if ( v34 && *(_QWORD *)(v34 + 8) )
        FreeContextDataBlock((PVOID *)(v34 + 8));
      goto LABEL_119;
    }
    if ( v35 != 2 )
    {
      if ( v35 != 3 )
      {
        if ( (a6 & 0x12) == 0 && !EfpsPerformAccessCheck(SecurityDescriptor, 0x102u, 1) )
        {
          v31 = 1928;
LABEL_47:
          v30 = -1073741790;
          goto LABEL_118;
        }
        v39 = (__int64 *)(v34 + 8);
        if ( !v34 )
          v39 = 0;
        goto LABEL_66;
      }
      goto LABEL_88;
    }
    if ( (a7 & 1) != 0 )
      goto LABEL_15;
    if ( (a6 & 2) == 0 )
    {
      v31 = 1807;
      goto LABEL_47;
    }
    if ( a5 )
    {
      v30 = -1073741808;
      v31 = 1822;
      goto LABEL_118;
    }
    EfsData = EfsDeleteEfsData(a9, a11);
LABEL_57:
    EfspReleaseFsCtlData(&v50);
    goto LABEL_119;
  }
  if ( (a6 & 3) != 0 || (unsigned int)(v50 - 3) <= 1 && v37 - 3 <= 1 && (a6 & 0x10) != 0 )
  {
    v40 = a16;
  }
  else
  {
    v40 = a16;
    if ( !(unsigned __int8)EfspOnlineEncryptionAccessCheck((_DWORD)SecurityDescriptor, 0, v33, v36, a16) )
    {
      v31 = 1639;
      goto LABEL_47;
    }
  }
  EfsData = EfsSetEncrypt((unsigned int)&v50, a5, a9, a11, v40, (__int64)a18, (__int64)a23, (__int64)a24, (__int64)a26);
  EfspReleaseFsCtlData(&v50);
  if ( *a22 && !*a26 )
    *a22 = 0;
LABEL_119:
  EfspReleaseFsCtlData(&v50);
  if ( EfsData < 0 && v56 )
    EfspDevCryptoSetup(DeviceObject);
  if ( *v29 && !*a26 )
    *v29 = 0;
  return (unsigned int)EfsData;
}

```

## disassembly

```asm
0x14004eff0  mov     rax, rsp
0x14004eff3  mov     [rax+20h], r9
0x14004eff7  mov     [rax+18h], r8
0x14004effb  push    rbx
0x14004effc  push    rsi
0x14004effd  push    rdi
0x14004effe  push    r12
0x14004f000  push    r13
0x14004f002  push    r14
0x14004f004  push    r15
0x14004f006  sub     rsp, 0C0h
0x14004f00d  mov     edi, edx
0x14004f00f  mov     rsi, rcx
0x14004f012  xor     ebx, ebx
0x14004f014  mov     dword ptr [rsp+0F8h+Size], ebx
0x14004f018  mov     [rsp+0F8h+var_90], ebx
0x14004f01c  xorps   xmm0, xmm0
0x14004f01f  movups  xmmword ptr [rax-80h], xmm0
0x14004f023  movups  xmmword ptr [rax-70h], xmm0
0x14004f027  movups  xmmword ptr [rax-60h], xmm0
0x14004f02b  mov     qword ptr [rsp+0F8h+Size+4], rbx
0x14004f030  mov     [rsp+0F8h+var_98], bl
0x14004f034  mov     al, bl
0x14004f036  mov     [rsp+0F8h+var_50], eax
0x14004f03d  mov     [rsp+0F8h+var_97], bl
0x14004f041  mov     [rsp+0F8h+arg_0], bl
0x14004f048  test    rcx, rcx
0x14004f04b  jz      loc_14004F833
0x14004f051  cmp     cs:byte_140017924, bl
0x14004f057  jz      loc_14004F833
0x14004f05d  mov     r14, [rsp+0F8h+arg_A8]
0x14004f065  test    r14, r14
0x14004f068  jz      loc_14004F83B
0x14004f06e  cmp     [rsp+0F8h+arg_B8], rbx
0x14004f076  jz      loc_14004F83B
0x14004f07c  mov     [r14], bl
0x14004f07f  cmp     [rsp+0F8h+arg_78], bl
0x14004f086  jz      short loc_14004F092
0x14004f088  mov     rax, [rsp+0F8h+arg_B0]
0x14004f090  mov     [rax], bl
0x14004f092  mov     rax, [rsp+0F8h+arg_C0]
0x14004f09a  mov     [rax], bl
0x14004f09c  mov     r15, [rsp+0F8h+arg_48]
0x14004f0a4  cmp     [r15+40h], bl
0x14004f0a8  jz      short loc_14004F0C4
0x14004f0aa  call    EfspHasTCBPrivilege
0x14004f0af  test    al, al
0x14004f0b1  jnz     short loc_14004F0C4
0x14004f0b3  mov     r9d, 0C0000022h
0x14004f0b9  mov     r8d, 54Fh
0x14004f0bf  jmp     loc_14004F847
0x14004f0c4  lea     rax, [rsp+0F8h+var_80]
0x14004f0c9  mov     [rsp+0F8h+var_D8], rax
0x14004f0ce  lea     r9, [rsp+0F8h+var_98]
0x14004f0d3  mov     r8b, [r15+40h]
0x14004f0d7  mov     edx, edi
0x14004f0d9  mov     rcx, rsi
0x14004f0dc  call    EfspValidateAndParseFsctl
0x14004f0e1  mov     edi, eax
0x14004f0e3  test    eax, eax
0x14004f0e5  js      loc_14004F854
0x14004f0eb  mov     r15, rbx
0x14004f0ee  mov     [rsp+0F8h+var_48], rbx
0x14004f0f6  mov     r12d, [rsp+0F8h+var_7C]
0x14004f0fb  cmp     [rsp+0F8h+var_98], bl
0x14004f0ff  jz      short loc_14004F112
0x14004f101  mov     r15, rsi
0x14004f104  mov     [rsp+0F8h+var_48], rsi
0x14004f10c  mov     cl, [rsi+6]
0x14004f10f  mov     [r14], cl
0x14004f112  mov     r9d, [rsp+0F8h+var_78]
0x14004f11a  mov     r13d, r9d
0x14004f11d  and     r13d, 0F77FFFFFh
0x14004f124  cmp     [rsp+0F8h+arg_38], 900D7h
0x14004f12f  jnz     short loc_14004F179
0x14004f131  test    byte ptr [rsp+0F8h+arg_30], 1
0x14004f139  jz      short loc_14004F145
0x14004f13b  mov     edi, 0C00000A2h
0x14004f140  jmp     loc_14004F854
0x14004f145  test    r12d, r12d
0x14004f148  jnz     short loc_14004F162
0x14004f14a  mov     eax, r13d
0x14004f14d  btr     eax, 1Fh
0x14004f151  cmp     [rsp+0F8h+var_80], eax
0x14004f155  jz      short loc_14004F179
0x14004f157  mov     r8d, 592h
0x14004f15d  jmp     loc_14004F841
0x14004f162  cmp     r12d, 1
0x14004f166  jz      short loc_14004F179
0x14004f168  cmp     r12d, 4
0x14004f16c  jz      short loc_14004F179
0x14004f16e  mov     r8d, 599h
0x14004f174  jmp     loc_14004F841
0x14004f179  cmp     [r14], bl
0x14004f17c  jnz     loc_14004F237
0x14004f182  test    r12d, r12d
0x14004f185  jnz     loc_14004F237
0x14004f18b  test    r9d, r9d
0x14004f18e  js      loc_14004F237
0x14004f194  bt      r9d, 17h
0x14004f199  jb      loc_14004F237
0x14004f19f  bt      r9d, 1Bh
0x14004f1a4  jnb     short loc_14004F1B2
0x14004f1a6  cmp     r13d, 1
0x14004f1aa  jz      short loc_14004F1B8
0x14004f1ac  cmp     r13d, 4
0x14004f1b0  jz      short loc_14004F1B8
0x14004f1b2  cmp     r13d, 3
0x14004f1b6  jnz     short loc_14004F237
0x14004f1b8  cmp     [rsp+0F8h+DeviceObject], rbx
0x14004f1c0  jz      short loc_14004F1FF
0x14004f1c2  lea     r9, [rsp+0F8h+var_97]
0x14004f1c7  mov     r8, [rsp+0F8h+arg_A0]
0x14004f1cf  mov     rdx, [rsp+0F8h+var_68]
0x14004f1d7  mov     edx, [rdx+4]
0x14004f1da  call    EfspCanOffloadCrypto
0x14004f1df  movzx   esi, [rsp+0F8h+var_97]
0x14004f1e4  cmp     sil, 1
0x14004f1e8  jnz     short loc_14004F1F5
0x14004f1ea  call    EfspIsCryptoOffloadTurnedOffByOverride
0x14004f1ef  cmp     al, sil
0x14004f1f2  cmovz   esi, ebx
0x14004f1f5  mov     r9d, [rsp+0F8h+var_78]
0x14004f1fd  jmp     short loc_14004F206
0x14004f1ff  mov     esi, [rsp+0F8h+var_50]
0x14004f206  mov     [r14], sil
0x14004f209  test    sil, sil
0x14004f20c  jz      short loc_14004F237
0x14004f20e  xor     edx, edx
0x14004f210  mov     rcx, [rsp+0F8h+DeviceObject]; DeviceObject
0x14004f218  call    EfspDevCryptoSetup
0x14004f21d  mov     edi, eax
0x14004f21f  test    eax, eax
0x14004f221  js      loc_14004F854
0x14004f227  mov     [rsp+0F8h+arg_0], 1
0x14004f22f  mov     r9d, [rsp+0F8h+var_78]
0x14004f237  mov     esi, 5
0x14004f23c  cmp     r12d, esi
0x14004f23f  ja      loc_14004F575
0x14004f245  jz      loc_14004F7B1
0x14004f24b  mov     eax, r12d
0x14004f24e  test    r12d, r12d
0x14004f251  jz      loc_14004F491
0x14004f257  sub     eax, 1
0x14004f25a  jz      loc_14004F399
0x14004f260  sub     eax, 1
0x14004f263  jz      loc_14004F336
0x14004f269  sub     eax, 1
0x14004f26c  jz      loc_14004F5B2
0x14004f272  cmp     eax, 1
0x14004f275  jnz     loc_14004F5A1
0x14004f27b  test    [rsp+0F8h+arg_28], 12h
0x14004f283  jnz     short loc_14004F2B1
0x14004f285  mov     r8b, al
0x14004f288  mov     edx, 102h; DesiredAccess
0x14004f28d  mov     rcx, [rsp+0F8h+SecurityDescriptor]; SecurityDescriptor
0x14004f295  call    EfpsPerformAccessCheck
0x14004f29a  test    al, al
0x14004f29c  jnz     short loc_14004F2B1
0x14004f29e  mov     r8d, 788h
0x14004f2a4  mov     r9d, 0C0000022h
0x14004f2aa  mov     edx, esi
0x14004f2ac  jmp     loc_14004F84C
0x14004f2b1  test    r15, r15
0x14004f2b4  lea     rcx, [r15+8]
0x14004f2b8  jnz     short loc_14004F2BD
0x14004f2ba  mov     rcx, rbx
0x14004f2bd  mov     rax, [rsp+0F8h+arg_C8]
0x14004f2c5  mov     [rsp+0F8h+var_A8], rax
0x14004f2ca  mov     rax, [rsp+0F8h+arg_C0]
0x14004f2d2  mov     [rsp+0F8h+var_B0], rax
0x14004f2d7  mov     rax, [rsp+0F8h+arg_B8]
0x14004f2df  mov     [rsp+0F8h+var_B8], rax
0x14004f2e4  mov     rax, [rsp+0F8h+DeviceObject]
0x14004f2ec  mov     [rsp+0F8h+var_C0], rax
0x14004f2f1  mov     al, [rsp+0F8h+arg_98]
0x14004f2f8  mov     byte ptr [rsp+0F8h+var_C8], al
0x14004f2fc  mov     [rsp+0F8h+var_D0], rcx
0x14004f301  mov     rax, [rsp+0F8h+arg_50]
0x14004f309  mov     [rsp+0F8h+var_D8], rax
0x14004f30e  mov     r9, [rsp+0F8h+arg_40]
0x14004f316  mov     r8d, [rsp+0F8h+arg_20]
0x14004f31e  mov     edx, [rsp+0F8h+arg_30]
0x14004f325  lea     rcx, [rsp+0F8h+var_80]
0x14004f32a  call    SetEfsData
0x14004f32f  mov     edi, eax
0x14004f331  jmp     loc_14004F452
0x14004f336  test    byte ptr [rsp+0F8h+arg_30], 1
0x14004f33e  jnz     loc_14004F13B
0x14004f344  test    [rsp+0F8h+arg_28], 2
0x14004f34c  jnz     short loc_14004F359
0x14004f34e  mov     r8d, 70Fh
0x14004f354  jmp     loc_14004F2A4
0x14004f359  cmp     [rsp+0F8h+arg_20], ebx
0x14004f360  jz      short loc_14004F373
0x14004f362  mov     r9d, 0C0000010h
0x14004f368  mov     r8d, 71Eh
0x14004f36e  jmp     loc_14004F2AA
0x14004f373  mov     rdx, [rsp+0F8h+arg_50]
0x14004f37b  mov     rcx, [rsp+0F8h+arg_40]
0x14004f383  call    EfsDeleteEfsData
0x14004f388  mov     edi, eax
0x14004f38a  lea     rcx, [rsp+0F8h+var_80]
0x14004f38f  call    EfspReleaseFsCtlData
0x14004f394  jmp     loc_14004F854
0x14004f399  cmp     [rsp+0F8h+arg_90], bl
0x14004f3a0  jz      short loc_14004F3B2
0x14004f3a2  mov     rax, [rsp+0F8h+arg_C0]
0x14004f3aa  mov     byte ptr [rax], 1
0x14004f3ad  jmp     loc_14004F854
0x14004f3b2  test    r9b, 8
0x14004f3b6  jz      short loc_14004F3C2
0x14004f3b8  test    byte ptr [rsp+0F8h+arg_20], 2
0x14004f3c0  jz      short loc_14004F3A2
0x14004f3c2  test    r9b, 4
0x14004f3c6  jz      short loc_14004F3D2
0x14004f3c8  test    byte ptr [rsp+0F8h+arg_20], 1
0x14004f3d0  jz      short loc_14004F3A2
0x14004f3d2  test    r15, r15
0x14004f3d5  lea     rcx, [r15+8]
0x14004f3d9  jnz     short loc_14004F3DE
0x14004f3db  mov     rcx, rbx
0x14004f3de  mov     rax, [rsp+0F8h+arg_C8]
0x14004f3e6  mov     [rsp+0F8h+var_A8], rax
0x14004f3eb  mov     rax, [rsp+0F8h+arg_C0]
0x14004f3f3  mov     [rsp+0F8h+var_B0], rax
0x14004f3f8  mov     rax, [rsp+0F8h+arg_B8]
0x14004f400  mov     [rsp+0F8h+var_B8], rax
0x14004f405  mov     rax, [rsp+0F8h+DeviceObject]
0x14004f40d  mov     [rsp+0F8h+var_C0], rax
0x14004f412  mov     al, [rsp+0F8h+arg_98]
0x14004f419  mov     byte ptr [rsp+0F8h+var_C8], al
0x14004f41d  mov     [rsp+0F8h+var_D0], rcx
0x14004f422  mov     rax, [rsp+0F8h+arg_50]
0x14004f42a  mov     [rsp+0F8h+var_D8], rax
0x14004f42f  mov     r9, [rsp+0F8h+arg_40]
0x14004f437  mov     r8d, [rsp+0F8h+arg_20]
0x14004f43f  mov     edx, [rsp+0F8h+arg_30]
0x14004f446  lea     rcx, [rsp+0F8h+var_80]
0x14004f44b  call    SetEfsData
0x14004f450  mov     edi, eax
0x14004f452  lea     rcx, [rsp+0F8h+var_80]
0x14004f457  call    EfspReleaseFsCtlData
0x14004f45c  cmp     [r14], bl
0x14004f45f  jz      short loc_14004F471
0x14004f461  mov     rax, [rsp+0F8h+arg_C8]
0x14004f469  cmp     [rax], rbx
0x14004f46c  jnz     short loc_14004F471
0x14004f46e  mov     [r14], bl
0x14004f471  test    r15, r15
0x14004f474  jz      loc_14004F854
0x14004f47a  lea     rcx, [r15+8]
0x14004f47e  cmp     [rcx], rbx
0x14004f481  jz      loc_14004F854
0x14004f487  call    FreeContextDataBlock
0x14004f48c  jmp     loc_14004F854
0x14004f491  test    [rsp+0F8h+arg_28], 3
0x14004f499  jnz     short loc_14004F4E5
0x14004f49b  mov     eax, [rsp+0F8h+var_80]
0x14004f49f  add     eax, 0FFFFFFFDh
0x14004f4a2  cmp     eax, 1
0x14004f4a5  ja      short loc_14004F4BA
0x14004f4a7  lea     eax, [r13-3]
0x14004f4ab  cmp     eax, 1
0x14004f4ae  ja      short loc_14004F4BA
0x14004f4b0  test    [rsp+0F8h+arg_28], 10h
0x14004f4b8  jnz     short loc_14004F4E5
0x14004f4ba  mov     dil, [rsp+0F8h+arg_78]
0x14004f4c2  mov     byte ptr [rsp+0F8h+var_D8], dil
0x14004f4c7  xor     edx, edx
0x14004f4c9  mov     rcx, [rsp+0F8h+SecurityDescriptor]
0x14004f4d1  call    EfspOnlineEncryptionAccessCheck
0x14004f4d6  test    al, al
0x14004f4d8  jnz     short loc_14004F4ED
0x14004f4da  mov     r8d, 667h
0x14004f4e0  jmp     loc_14004F2A4
0x14004f4e5  mov     dil, [rsp+0F8h+arg_78]
0x14004f4ed  mov     rax, [rsp+0F8h+arg_C8]
0x14004f4f5  mov     [rsp+0F8h+var_B8], rax
0x14004f4fa  mov     rax, [rsp+0F8h+arg_B8]
0x14004f502  mov     [rsp+0F8h+var_C0], rax
0x14004f507  mov     rax, [rsp+0F8h+arg_B0]
0x14004f50f  mov     [rsp+0F8h+var_C8], rax
0x14004f514  mov     rax, [rsp+0F8h+arg_88]
0x14004f51c  mov     [rsp+0F8h+var_D0], rax
0x14004f521  mov     byte ptr [rsp+0F8h+var_D8], dil
0x14004f526  mov     r9, [rsp+0F8h+arg_50]
0x14004f52e  mov     r8, [rsp+0F8h+arg_40]
0x14004f536  mov     edx, [rsp+0F8h+arg_20]
0x14004f53d  lea     rcx, [rsp+0F8h+var_80]
0x14004f542  call    EfsSetEncrypt
0x14004f547  mov     edi, eax
0x14004f549  lea     rcx, [rsp+0F8h+var_80]
0x14004f54e  call    EfspReleaseFsCtlData
0x14004f553  cmp     [r14], bl
0x14004f556  jz      loc_14004F854
0x14004f55c  mov     rax, [rsp+0F8h+arg_C8]
0x14004f564  cmp     [rax], rbx
0x14004f567  jnz     loc_14004F854
0x14004f56d  mov     [r14], bl
  ... truncated ...
```
