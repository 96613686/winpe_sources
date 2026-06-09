# MntMount

- ea: `0x140023dd0`
- end: `0x14002471a`
- name: `MntMount`
- size: `2378`
- prototype: `__int64 __fastcall(int, int, int, int, PCUNICODE_STRING SourceString, __int64)`
- caller_count: `5`
- callee_count: `18`
- tags: ``

## callers

- `0x1400029d0`
- `0x14000be20`
- `0x140019044`
- `0x140025484`
- `0x1400273f0`

## callees

- `0x140001010`
- `0x1400010c0`
- `0x140011f84`
- `0x140013ac0`
- `0x140014c30`
- `0x140014e1c`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140022220`
- `0x1400235c0`
- `0x140023dd0`
- `0x140024f6c`
- `0x14002d1e4`
- `0x14002ddac`
- `0x14003aba0`
- `0x14003adc0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140023f0e`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140023f0e`
- `ntoskrnl!RtlFreeAnsiString` at `0x140024283`
- `ntoskrnl!RtlFreeAnsiString` at `0x1400245d2`
- `ntoskrnl!RtlFreeAnsiString` at `0x140024283`
- `ntoskrnl!RtlFreeAnsiString` at `0x1400245d2`
- `rpcxdr!OncRpcBuildCall` at `0x140024021`
- `rpcxdr!OncRpcBuildCall` at `0x140024231`
- `rpcxdr!OncRpcBuildCall` at `0x140024021`
- `rpcxdr!OncRpcBuildCall` at `0x140024231`
- `rpcxdr!OncRpcDestroy` at `0x140024170`
- `rpcxdr!OncRpcDestroy` at `0x1400241cb`
- `rpcxdr!OncRpcDestroy` at `0x1400241dc`
- `rpcxdr!OncRpcDestroy` at `0x1400245a6`
- `rpcxdr!OncRpcDestroy` at `0x1400245b7`
- `rpcxdr!OncRpcDestroy` at `0x1400246b2`
- `rpcxdr!OncRpcDestroy` at `0x1400246ff`
- `rpcxdr!OncRpcDestroy` at `0x140024170`
- `rpcxdr!OncRpcDestroy` at `0x1400241cb`
- `rpcxdr!OncRpcDestroy` at `0x1400241dc`
- `rpcxdr!OncRpcDestroy` at `0x1400245a6`
- `rpcxdr!OncRpcDestroy` at `0x1400245b7`
- `rpcxdr!OncRpcDestroy` at `0x1400246b2`
- `rpcxdr!OncRpcDestroy` at `0x1400246ff`

## pseudocode

```c
__int64 __fastcall MntMount(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PCUNICODE_STRING SourceString,
        unsigned int *a6)
{
  __int64 v6; // rax
  unsigned int *v8; // r14
  int v10; // edx
  int v11; // r8d
  PWSTR Buffer; // rax
  int MountPort; // ebx
  NTSTATUS v14; // eax
  USHORT Length; // ax
  char v16; // r15
  __int64 v17; // rdi
  PCHAR v18; // r9
  size_t v19; // rdx
  __int64 v20; // rax
  _DWORD *v21; // rcx
  _QWORD *v22; // rcx
  size_t v23; // rbx
  int v24; // edx
  char *v25; // r9
  char *v26; // r8
  __int64 v27; // rdi
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  PDEVICE_OBJECT v32; // rcx
  __int64 v33; // rdx
  int *v34; // r9
  unsigned int v35; // eax
  unsigned int v36; // ebx
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // ebx
  int v40; // edi
  int v41; // eax
  PDEVICE_OBJECT v42; // rcx
  __int64 v43; // rdx
  int *v44; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h] BYREF
  struct _STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v47; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+78h] [rbp-88h]
  _QWORD v49[12]; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v50; // [rsp+E0h] [rbp-20h] BYREF
  __int64 *v51; // [rsp+100h] [rbp+0h]
  __int64 v52; // [rsp+108h] [rbp+8h]

  v6 = *(_QWORD *)(a1 + 48);
  v8 = *(unsigned int **)(a1 + 32);
  v47 = a4;
  v45 = 0;
  v44 = 0;
  DestinationString = 0;
  v48 = v6;
  memset(v49, 0, 0x54u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_Zl(WPP_GLOBAL_Control->AttachedDevice, v10, v11, (_DWORD)SourceString, SourceString->Length);
  if ( SourceString->Length >= 0xAu )
  {
    Buffer = SourceString->Buffer;
    if ( *(_DWORD *)Buffer == 4784175
      && Buffer[2] == 80
      && Buffer[3] == 67
      && Buffer[4] == 36
      && (SourceString->Length == 10 || Buffer[5] == 47) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids, SourceString);
      MountPort = -1073741634;
      goto LABEL_56;
    }
  }
  v14 = RtlUnicodeStringToAnsiString(&DestinationString, SourceString, 1u);
  MountPort = v14;
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
LABEL_59:
      if ( (unsigned int)dword_140041028 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn() )
        {
          LODWORD(v47) = MountPort;
          v51 = &v47;
          v52 = 4;
          tlgWriteTransfer_EtwWriteTransfer(v28, (unsigned __int8 *)&word_14003E49E, v29, v30, 3u, &v50);
        }
      }
      return (unsigned int)MountPort;
    }
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids,
        (unsigned int)v14);
LABEL_56:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        32,
        WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids,
        (unsigned int)MountPort);
    goto LABEL_59;
  }
  Length = DestinationString.Length;
  v16 = 1;
  if ( DestinationString.Length == 2 && *DestinationString.Buffer == 47 && DestinationString.Buffer[1] == 33 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids);
    Length = 1;
    DestinationString.Length = 1;
  }
  *(_OWORD *)&v49[1] = DaSystemUnixId;
  *(_OWORD *)&v49[5] = xmmword_1400410F0;
  LODWORD(v49[0]) = 1;
  *(_OWORD *)&v49[3] = xmmword_1400410E0;
  *(_OWORD *)&v49[7] = xmmword_140041100;
  *(_OWORD *)((char *)&v49[8] + 4) = *(__int128 *)((char *)&xmmword_140041100 + 12);
  if ( (int)OncRpcBuildCall(&v45, v8 + 11, v8[2], v8[3], v8[4], 1, Length + 8 + (-Length & 3u), v49) < 0 )
  {
LABEL_51:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids);
    MountPort = -1073741670;
LABEL_55:
    RtlFreeAnsiString(&DestinationString);
    goto LABEL_56;
  }
  while ( 1 )
  {
    v17 = v45;
    v18 = DestinationString.Buffer;
    v19 = DestinationString.Length;
    v20 = *(_QWORD *)(v45 + 72);
    if ( v20 )
      v21 = *(_DWORD **)(v20 + 64);
    else
      v21 = 0;
    *v21 = _byteswap_ulong(DestinationString.Length);
    *(_QWORD *)(*(_QWORD *)(v17 + 72) + 64LL) += 4LL;
    v22 = *(_QWORD **)(v17 + 72);
    if ( v22 )
      v22 = (_QWORD *)v22[8];
    v23 = v19;
    memmove(v22, v18, v19);
    *(_QWORD *)(*(_QWORD *)(v17 + 72) + 64LL) += v23;
    XdrNextMod4Boundary(v17);
    v26 = *(char **)(v17 + 72);
    if ( v26 )
      v26 = (char *)*((_QWORD *)v26 + 8);
    if ( v25 != v26 )
      memset(v25, 0, v26 - v25);
    if ( *(int *)(v45 + 264) < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids);
      MountPort = *(_DWORD *)(v45 + 264);
      goto LABEL_133;
    }
    v27 = v48;
    MountPort = NfsSendWaitReply(v48, v24, 0, a2, v47, (__int64)v8, v45, (__int64)&v44, 0);
    if ( MountPort < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids,
          (unsigned int)MountPort);
      if ( MountPort != -1073741643 || !v16 )
        goto LABEL_133;
      MountPort = FindMountPort(v27, a2, v8);
      if ( MountPort < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            21,
            WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids,
            (unsigned int)MountPort);
        goto LABEL_133;
      }
      OncRpcDestroy(v45);
      v16 = 0;
      goto LABEL_50;
    }
    if ( v44[68] || !v16 || v44[160] != 1 )
      break;
    MountPort = FindMountPort(v27, a2, v8);
    if ( MountPort < 0 )
    {
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        v33 = 22;
        goto LABEL_74;
      }
      goto LABEL_75;
    }
    v16 = 0;
    OncRpcDestroy(v44);
    OncRpcDestroy(v45);
LABEL_50:
    NfsForceDisconnect(v8, 0);
    if ( (int)OncRpcBuildCall(
                &v45,
                v8 + 11,
                v8[2],
                v8[3],
                v8[4],
                1,
                DestinationString.Length + 8 + (-DestinationString.Length & 3u),
                v49) < 0 )
      goto LABEL_51;
  }
  MountPort = OncRpcMapRpcStatusToNtStatus(v44);
  if ( MountPort < 0 )
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v33 = 23;
LABEL_74:
      WPP_SF_d(v32->AttachedDevice, v33, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids, (unsigned int)MountPort);
LABEL_75:
      v34 = v44;
    }
LABEL_128:
    OncRpcDestroy(v34);
LABEL_133:
    OncRpcDestroy(v45);
    NfsForceDisconnect(v8, 0);
    goto LABEL_55;
  }
  v35 = XdrDecodeInt(v34);
  v34 = v44;
  v36 = v35;
  if ( v44[66] < 0 )
  {
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_127;
    v43 = 24;
LABEL_126:
    WPP_SF_(v42->AttachedDevice, v43, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids);
    v34 = v44;
    goto LABEL_127;
  }
  if ( v35 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids, v35);
    MountPort = MapNFSStatusToNtStatus(v36);
    goto LABEL_128;
  }
  if ( v8[4] == 3 )
  {
    v37 = XdrDecodeInt(v44);
    *a6 = v37;
    if ( v37 > 0x40 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids);
      MountPort = -1073741628;
      goto LABEL_75;
    }
    v34 = v44;
  }
  else
  {
    v37 = 32;
    *a6 = 32;
  }
  XdrDecodeOpaque_0(v34, v37, a6 + 1);
  v34 = v44;
  if ( v44[66] < 0 )
  {
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_127;
    v43 = 27;
    goto LABEL_126;
  }
  if ( v8[4] != 3 )
    goto LABEL_110;
  v38 = XdrDecodeInt(v44);
  v34 = v44;
  v39 = v38;
  if ( v44[66] < 0 )
  {
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_127;
    v43 = 28;
    goto LABEL_126;
  }
  if ( v38 <= 0x10 )
  {
    v40 = 0;
    if ( v38 )
      goto LABEL_99;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids, v38);
      v34 = v44;
    }
    v39 = 16;
    v40 = 0;
LABEL_99:
    if ( a3 )
    {
      while ( 1 )
      {
        v41 = XdrDecodeInt(v34);
        v34 = v44;
        if ( v44[66] < 0 )
          break;
        switch ( v41 )
        {
          case 1:
            *(_DWORD *)(a3 + 80) |= 1u;
            break;
          case 390003:
            *(_DWORD *)(a3 + 80) |= 2u;
            break;
          case 390004:
            *(_DWORD *)(a3 + 80) |= 4u;
            break;
          case 390005:
            *(_DWORD *)(a3 + 80) |= 8u;
            break;
        }
        if ( ++v40 >= v39 )
          goto LABEL_110;
      }
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v43 = 30;
        goto LABEL_126;
      }
LABEL_127:
      MountPort = v34[66];
      goto LABEL_128;
    }
  }
LABEL_110:
  OncRpcDestroy(v45);
  OncRpcDestroy(v44);
  NfsForceDisconnect(v8, 0);
  RtlFreeAnsiString(&DestinationString);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140023dd0  push    rbp
0x140023dd2  push    rbx
0x140023dd3  push    rsi
0x140023dd4  push    rdi
0x140023dd5  push    r12
0x140023dd7  push    r13
0x140023dd9  push    r14
0x140023ddb  push    r15
0x140023ddd  lea     rbp, [rsp-28h]
0x140023de2  sub     rsp, 128h
0x140023de9  mov     rax, cs:__security_cookie
0x140023df0  xor     rax, rsp
0x140023df3  mov     [rbp+60h+var_50], rax
0x140023df7  mov     rax, [rcx+30h]
0x140023dfb  mov     rsi, r8
0x140023dfe  mov     r14, [rcx+20h]
0x140023e02  mov     r13, rdx
0x140023e05  mov     r12, [rbp+60h+arg_28]
0x140023e0c  xor     ecx, ecx
0x140023e0e  mov     rbx, [rbp+60h+SourceString]
0x140023e15  xorps   xmm0, xmm0
0x140023e18  mov     [rbp+60h+var_DC], ecx
0x140023e1b  xor     edx, edx; Val
0x140023e1d  mov     [rsp+160h+var_F0], r9
0x140023e22  lea     r8d, [rcx+54h]; Size
0x140023e26  mov     [rsp+160h+var_108], 0
0x140023e2f  lea     rcx, [rbp+60h+var_E0]; void *
0x140023e33  mov     [rsp+160h+var_110], 0
0x140023e3c  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x140023e41  mov     [rsp+160h+var_E8], rax
0x140023e46  call    memset
0x140023e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140023e52  lea     r15, WPP_GLOBAL_Control
0x140023e59  cmp     rcx, r15
0x140023e5c  jz      short loc_140023E78
0x140023e5e  mov     eax, [rcx+2Ch]
0x140023e61  test    al, 10h
0x140023e63  jz      short loc_140023E78
0x140023e65  movzx   eax, word ptr [rbx]
0x140023e68  mov     r9, rbx
0x140023e6b  mov     rcx, [rcx+18h]
0x140023e6f  mov     [rsp+160h+var_140], eax
0x140023e73  call    WPP_SF_Zl
0x140023e78  movzx   ecx, word ptr [rbx]
0x140023e7b  mov     edi, 2
0x140023e80  lea     r9d, [rdi+8]
0x140023e84  lea     r8d, [rdi+2Dh]
0x140023e88  cmp     cx, r9w
0x140023e8c  jb      short loc_140023EFE
0x140023e8e  mov     rax, [rbx+8]
0x140023e92  cmp     r8w, [rax]
0x140023e96  jnz     short loc_140023EFE
0x140023e98  lea     edx, [rdi+47h]
0x140023e9b  cmp     dx, [rax+2]
0x140023e9f  jnz     short loc_140023EFE
0x140023ea1  lea     edx, [rdi+4Eh]
0x140023ea4  cmp     dx, [rax+4]
0x140023ea8  jnz     short loc_140023EFE
0x140023eaa  lea     edx, [rdi+41h]
0x140023ead  cmp     dx, [rax+6]
0x140023eb1  jnz     short loc_140023EFE
0x140023eb3  lea     edx, [rdi+22h]
0x140023eb6  cmp     dx, [rax+8]
0x140023eba  jnz     short loc_140023EFE
0x140023ebc  cmp     r9w, cx
0x140023ec0  jz      short loc_140023EC9
0x140023ec2  cmp     [rax+0Ah], r8w
0x140023ec7  jnz     short loc_140023EFE
0x140023ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x140023ed0  cmp     rcx, r15
0x140023ed3  jz      short loc_140023EF4
0x140023ed5  mov     eax, [rcx+2Ch]
0x140023ed8  test    al, 10h
0x140023eda  jz      short loc_140023EF4
0x140023edc  mov     rcx, [rcx+18h]
0x140023ee0  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x140023ee7  mov     edx, 0Fh
0x140023eec  mov     r9, rbx
0x140023eef  call    WPP_SF_Z
0x140023ef4  mov     ebx, 0C00000BEh
0x140023ef9  jmp     loc_140024294
0x140023efe  mov     edi, 1
0x140023f03  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x140023f08  mov     r8b, dil; AllocateDestinationString
0x140023f0b  mov     rdx, rbx; SourceString
0x140023f0e  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140023f15  nop     dword ptr [rax+rax+00h]
0x140023f1a  mov     ebx, eax
0x140023f1c  test    eax, eax
0x140023f1e  jns     short loc_140023F58
0x140023f20  mov     rcx, cs:WPP_GLOBAL_Control
0x140023f27  cmp     rcx, r15
0x140023f2a  jz      loc_1400242C0
0x140023f30  mov     r8d, [rcx+2Ch]
0x140023f34  test    dil, r8b
0x140023f37  jz      loc_14002428F
0x140023f3d  mov     rcx, [rcx+18h]
0x140023f41  lea     edx, [rdi+0Fh]
0x140023f44  mov     r9d, eax
0x140023f47  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x140023f4e  call    WPP_SF_d
0x140023f53  jmp     loc_14002428F
0x140023f58  movzx   eax, [rsp+160h+DestinationString.Length]
0x140023f5d  mov     ebx, 2
0x140023f62  mov     r15b, dil
0x140023f65  cmp     ax, bx
0x140023f68  jnz     short loc_140023FAE
0x140023f6a  mov     rcx, [rsp+160h+DestinationString.Buffer]
0x140023f6f  cmp     byte ptr [rcx], 2Fh ; '/'
0x140023f72  jnz     short loc_140023FAE
0x140023f74  cmp     byte ptr [rcx+1], 21h ; '!'
0x140023f78  jnz     short loc_140023FAE
0x140023f7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140023f81  lea     rax, WPP_GLOBAL_Control
0x140023f88  cmp     rcx, rax
0x140023f8b  jz      short loc_140023FA7
0x140023f8d  mov     eax, [rcx+2Ch]
0x140023f90  test    bl, al
0x140023f92  jz      short loc_140023FA7
0x140023f94  mov     rcx, [rcx+18h]
0x140023f98  lea     edx, [rbx+0Fh]
0x140023f9b  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x140023fa2  call    WPP_SF_
0x140023fa7  mov     eax, edi
0x140023fa9  mov     [rsp+160h+DestinationString.Length], ax
0x140023fae  movaps  xmm0, cs:DaSystemUnixId
0x140023fb5  lea     rdx, [r14+2Ch]
0x140023fb9  movaps  xmm1, cs:xmmword_1400410E0
0x140023fc0  movzx   ecx, ax
0x140023fc3  movups  [rbp+60h+var_D8], xmm0
0x140023fc7  mov     eax, ecx
0x140023fc9  add     ecx, 8
0x140023fcc  movaps  xmm0, cs:xmmword_1400410F0
0x140023fd3  neg     eax
0x140023fd5  movups  [rbp+60h+var_B8], xmm0
0x140023fd9  mov     [rbp+60h+var_E0], edi
0x140023fdc  and     eax, 3
0x140023fdf  movups  xmm0, cs:xmmword_140041100+0Ch
0x140023fe6  add     eax, ecx
0x140023fe8  lea     rcx, [rbp+60h+var_E0]
0x140023fec  movups  [rbp+60h+var_C8], xmm1
0x140023ff0  mov     [rsp+160h+var_128], rcx
0x140023ff5  lea     rcx, [rsp+160h+var_108]
0x140023ffa  movaps  xmm1, cs:xmmword_140041100
0x140024001  movups  [rbp+60h+var_A8], xmm1
0x140024005  mov     dword ptr [rsp+160h+var_130], eax
0x140024009  movups  [rbp+60h+var_A8+0Ch], xmm0
0x14002400d  mov     eax, [r14+10h]
0x140024011  mov     r9d, [r14+0Ch]
0x140024015  mov     r8d, [r14+8]
0x140024019  mov     dword ptr [rsp+160h+var_138], edi
0x14002401d  mov     [rsp+160h+var_140], eax
0x140024021  call    cs:__imp_OncRpcBuildCall
0x140024028  nop     dword ptr [rax+rax+00h]
0x14002402d  test    eax, eax
0x14002402f  js      loc_14002424A
0x140024035  mov     rdi, [rsp+160h+var_108]
0x14002403a  mov     r9, [rsp+160h+DestinationString.Buffer]
0x14002403f  movzx   edx, [rsp+160h+DestinationString.Length]
0x140024044  mov     rax, [rdi+48h]
0x140024048  test    rax, rax
0x14002404b  jnz     short loc_140024051
0x14002404d  xor     ecx, ecx
0x14002404f  jmp     short loc_140024055
0x140024051  mov     rcx, [rax+40h]
0x140024055  mov     eax, edx
0x140024057  bswap   eax
0x140024059  mov     [rcx], eax
0x14002405b  mov     rax, [rdi+48h]
0x14002405f  add     qword ptr [rax+40h], 4
0x140024064  mov     rcx, [rdi+48h]
0x140024068  test    rcx, rcx
0x14002406b  jz      short loc_140024071
0x14002406d  mov     rcx, [rcx+40h]; void *
0x140024071  mov     rbx, rdx
0x140024074  mov     r8, rdx; Size
0x140024077  mov     rdx, r9; Src
0x14002407a  call    memmove
0x14002407f  mov     rax, [rdi+48h]
0x140024083  add     [rax+40h], rbx
0x140024087  mov     r9, [rdi+48h]
0x14002408b  test    r9, r9
0x14002408e  jz      short loc_140024094
0x140024090  mov     r9, [r9+40h]
0x140024094  mov     rcx, rdi
0x140024097  call    XdrNextMod4Boundary
0x14002409c  mov     r8, [rdi+48h]
0x1400240a0  test    r8, r8
0x1400240a3  jz      short loc_1400240A9
0x1400240a5  mov     r8, [r8+40h]
0x1400240a9  cmp     r9, r8
0x1400240ac  jz      short loc_1400240BB
0x1400240ae  sub     r8, r9; Size
0x1400240b1  xor     edx, edx; Val
0x1400240b3  mov     rcx, r9; void *
0x1400240b6  call    memset
0x1400240bb  mov     rax, [rsp+160h+var_108]
0x1400240c0  cmp     dword ptr [rax+108h], 0
0x1400240c7  jl      loc_1400246C0
0x1400240cd  mov     rdi, [rsp+160h+var_E8]
0x1400240d2  lea     rcx, [rsp+160h+var_110]
0x1400240d7  mov     [rsp+160h+var_120], 0
0x1400240df  mov     r9, r13
0x1400240e2  mov     [rsp+160h+var_128], rcx
0x1400240e7  xor     r8d, r8d
0x1400240ea  mov     [rsp+160h+var_130], rax
0x1400240ef  mov     rcx, rdi
0x1400240f2  mov     rax, [rsp+160h+var_F0]
0x1400240f7  mov     [rsp+160h+var_138], r14
0x1400240fc  mov     qword ptr [rsp+160h+var_140], rax
0x140024101  call    NfsSendWaitReply
0x140024106  mov     ebx, eax
0x140024108  test    eax, eax
0x14002410a  jns     short loc_140024181
0x14002410c  mov     rcx, cs:WPP_GLOBAL_Control
0x140024113  lea     rax, WPP_GLOBAL_Control
0x14002411a  cmp     rcx, rax
0x14002411d  jz      short loc_14002413E
0x14002411f  mov     eax, [rcx+2Ch]
0x140024122  test    al, 1
0x140024124  jz      short loc_14002413E
0x140024126  mov     rcx, [rcx+18h]
0x14002412a  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x140024131  mov     edx, 14h
0x140024136  mov     r9d, ebx
0x140024139  call    WPP_SF_d
0x14002413e  cmp     ebx, 0C00000B5h
0x140024144  jnz     loc_140024368
0x14002414a  test    r15b, r15b
0x14002414d  jz      loc_140024368
0x140024153  mov     r8, r14
0x140024156  mov     rdx, r13
0x140024159  mov     rcx, rdi
0x14002415c  call    FindMountPort
0x140024161  mov     ebx, eax
0x140024163  test    eax, eax
0x140024165  js      loc_140024329
0x14002416b  mov     rcx, [rsp+160h+var_108]
0x140024170  call    cs:__imp_OncRpcDestroy
0x140024177  nop     dword ptr [rax+rax+00h]
0x14002417c  xor     r15b, r15b
0x14002417f  jmp     short loc_1400241E8
0x140024181  mov     r9, [rsp+160h+var_110]
0x140024186  cmp     dword ptr [r9+110h], 0
0x14002418e  jnz     loc_140024395
0x140024194  test    r15b, r15b
0x140024197  jz      loc_140024395
0x14002419d  cmp     dword ptr [r9+280h], 1
0x1400241a5  jnz     loc_140024395
0x1400241ab  mov     r8, r14
0x1400241ae  mov     rdx, r13
0x1400241b1  mov     rcx, rdi
0x1400241b4  call    FindMountPort
0x1400241b9  mov     ebx, eax
0x1400241bb  test    eax, eax
0x1400241bd  js      loc_140024374
0x1400241c3  mov     rcx, [rsp+160h+var_110]
0x1400241c8  xor     r15b, r15b
0x1400241cb  call    cs:__imp_OncRpcDestroy
0x1400241d2  nop     dword ptr [rax+rax+00h]
0x1400241d7  mov     rcx, [rsp+160h+var_108]
0x1400241dc  call    cs:__imp_OncRpcDestroy
0x1400241e3  nop     dword ptr [rax+rax+00h]
0x1400241e8  xor     edx, edx
0x1400241ea  mov     rcx, r14
0x1400241ed  call    NfsForceDisconnect
0x1400241f2  movzx   ecx, [rsp+160h+DestinationString.Length]
0x1400241f7  lea     rdx, [r14+2Ch]
0x1400241fb  mov     r9d, [r14+0Ch]
0x1400241ff  mov     eax, ecx
0x140024201  mov     r8d, [r14+8]
0x140024205  neg     eax
0x140024207  add     ecx, 8
0x14002420a  and     eax, 3
0x14002420d  add     eax, ecx
0x14002420f  lea     rcx, [rbp+60h+var_E0]
0x140024213  mov     [rsp+160h+var_128], rcx
0x140024218  lea     rcx, [rsp+160h+var_108]
0x14002421d  mov     dword ptr [rsp+160h+var_130], eax
0x140024221  mov     eax, [r14+10h]
0x140024225  mov     dword ptr [rsp+160h+var_138], 1
0x14002422d  mov     [rsp+160h+var_140], eax
0x140024231  call    cs:__imp_OncRpcBuildCall
0x140024238  nop     dword ptr [rax+rax+00h]
0x14002423d  test    eax, eax
0x14002423f  jns     loc_140024035
0x140024245  mov     ebx, 2
0x14002424a  mov     rcx, cs:WPP_GLOBAL_Control
0x140024251  lea     r15, WPP_GLOBAL_Control
0x140024258  cmp     rcx, r15
0x14002425b  jz      short loc_140024279
0x14002425d  mov     eax, [rcx+2Ch]
0x140024260  test    bl, al
0x140024262  jz      short loc_140024279
0x140024264  mov     rcx, [rcx+18h]
0x140024268  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x14002426f  mov     edx, 12h
0x140024274  call    WPP_SF_
0x140024279  mov     ebx, 0C000009Ah
0x14002427e  lea     rcx, [rsp+160h+DestinationString]; AnsiString
  ... truncated ...
```
