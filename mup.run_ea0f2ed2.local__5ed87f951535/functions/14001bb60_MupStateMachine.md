# MupStateMachine

- ea: `0x14001bb60`
- end: `0x14001c08e`
- name: `MupStateMachine`
- size: `1326`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `8`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140014540`
- `0x140019cc0`
- `0x140019f00`
- `0x140019f60`
- `0x14001a370`
- `0x14001a760`
- `0x14001b860`
- `0x14001cff0`

## callees

- `0x140001cf8`
- `0x140002448`
- `0x140002754`
- `0x140002f2c`
- `0x140002f94`
- `0x140010424`
- `0x14001bb60`
- `0x14001c0a0`
- `0x14001c300`
- `0x14001cd00`
- `0x14001d4f8`
- `0x14001d514`
- `0x14001d5b4`

## import_xrefs

- `ntoskrnl!FsRtlPrepareToReuseEcp` at `0x14001bf86`
- `ntoskrnl!FsRtlPrepareToReuseEcp` at `0x14001bf86`
- `ntoskrnl!IofCallDriver` at `0x14001bd6d`
- `ntoskrnl!IofCallDriver` at `0x14001bd6d`
- `ntoskrnl!IoGetAttachedDevice` at `0x14001bd5b`
- `ntoskrnl!IoGetAttachedDevice` at `0x14001bd5b`

## pseudocode

```c
__int64 __fastcall MupStateMachine(unsigned __int64 P, unsigned __int64 MajorFunction)
{
  int v2; // r12d
  _DWORD *v3; // r13
  int v4; // eax
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // kr00_8
  __int64 result; // rax
  IRP *v8; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  __int64 v10; // r14
  struct _IRP *MasterIrp; // rbx
  int v12; // edi
  char v13; // al
  int v14; // eax
  int v15; // eax
  _QWORD *v16; // r14
  IRP *v17; // rbp
  __int64 v18; // rsi
  struct _IO_STACK_LOCATION *v19; // rdi
  struct _IO_STACK_LOCATION *v20; // rax
  struct _IO_STACK_LOCATION *v21; // rax
  struct _DEVICE_OBJECT *AttachedDevice; // rax
  int v23; // eax
  int v24; // ebx
  int v25; // eax
  __int64 v26; // r8
  __int64 v27; // rbx
  int NetworkOpenEcpIntegrityLevelFromHardeningCapabilities; // eax
  __int64 v29; // [rsp+80h] [rbp+8h] BYREF
  PECP_LIST EcpList; // [rsp+88h] [rbp+10h] BYREF
  __int64 v31; // [rsp+90h] [rbp+18h] BYREF

  v2 = *(_DWORD *)(P + 24);
  v3 = (_DWORD *)P;
  v4 = v2;
  while ( 2 )
  {
    v5 = 0x140000000uLL;
    v6 = P;
    P = v4;
    switch ( v4 )
    {
      case 0:
        v3[6] = 1;
        v4 = 1;
        continue;
      case 1:
        v8 = (IRP *)*((_QWORD *)v3 + 2);
        CurrentStackLocation = v8->Tail.Overlay.CurrentStackLocation;
        MajorFunction = CurrentStackLocation->MajorFunction;
        P = MajorFunction;
        if ( CurrentStackLocation->MajorFunction )
        {
          P = (unsigned int)(MajorFunction - 1);
          if ( (_DWORD)MajorFunction != 1 && (_DWORD)MajorFunction != 19 )
            goto LABEL_25;
        }
        v10 = *(_QWORD *)(*((_QWORD *)v3 + 5) + 248LL);
        if ( v10 )
          LODWORD(v10) = *(_DWORD *)(v10 + 88);
        EcpList = 0;
        v31 = 0;
        LOBYTE(v29) = 0;
        if ( !(_BYTE)MajorFunction && CurrentStackLocation->Parameters.Create.EaLength )
        {
          MasterIrp = v8->AssociatedIrp.MasterIrp;
          v12 = (unsigned __int8)RfsUtilFilterEa(MasterIrp) != 0 ? 4 : 0;
          v13 = RfsUtilFilterEa(MasterIrp);
          P = v12 | 2u;
          if ( v13 )
            v12 |= 2u;
          LODWORD(v10) = v12 | v10;
        }
        if ( !CurrentStackLocation->MajorFunction && (CurrentStackLocation->Parameters.Create.Options & 0x80u) != 0 )
        {
          P = CurrentStackLocation->Parameters.Create.FileAttributes;
          MajorFunction = (CurrentStackLocation->Parameters.Create.FileAttributes >> 12) & 4;
          v14 = (CurrentStackLocation->Parameters.Create.FileAttributes >> 12) & 4 | 2;
          if ( (P & 0x8000) == 0 )
            v14 = (CurrentStackLocation->Parameters.Create.FileAttributes >> 12) & 4;
          LODWORD(v10) = v14 | v10;
        }
        if ( !(_DWORD)v10 )
          goto LABEL_23;
        if ( MupiGetOrCreateEcpListForCreateIrp(v8, &EcpList) < 0
          || MupiFindOrCreateNetworkOpenEcp(EcpList, &v31, v26, &v29) < 0 )
        {
          goto LABEL_66;
        }
        v27 = v31;
        if ( !(_BYTE)v29 )
        {
          FsRtlPrepareToReuseEcp(v31);
          *(_QWORD *)(v27 + 16) = 0;
          *(_DWORD *)(v27 + 24) = 0;
        }
        NetworkOpenEcpIntegrityLevelFromHardeningCapabilities = MupiGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities((unsigned int)v10);
        P = *(unsigned int *)(v27 + 8);
        if ( (_DWORD)P == NetworkOpenEcpIntegrityLevelFromHardeningCapabilities )
          goto LABEL_61;
        if ( (P & 0xFFFFFFFB) != 0 )
        {
          v15 = -1073741311;
        }
        else
        {
          *(_DWORD *)(v27 + 8) = NetworkOpenEcpIntegrityLevelFromHardeningCapabilities;
LABEL_61:
          *(_DWORD *)(v27 + 12) |= 8 * (v10 & 1);
LABEL_23:
          v15 = 0;
        }
        if ( v15 < 0 )
LABEL_66:
          v4 = 6;
        else
LABEL_25:
          v4 = 2;
        v3[6] = v4;
        continue;
      case 2:
        result = MupCallSurrogatePrePost(v3);
        if ( (_DWORD)result == 259 )
          return result;
        v4 = (v3[7] != -1073741802) + 3;
        v3[6] = v4;
        continue;
      case 3:
        if ( v2 == 3 )
          goto LABEL_37;
        v16 = (_QWORD *)*((_QWORD *)v3 + 5);
        v17 = (IRP *)*((_QWORD *)v3 + 2);
        v18 = v16[21];
        v19 = v17->Tail.Overlay.CurrentStackLocation;
        v29 = v18;
        if ( v18 )
          goto LABEL_29;
        if ( (v17->Flags & 0x80u) == 0 )
        {
          v24 = -1073741802;
LABEL_32:
          v3[8] = v24;
          goto LABEL_33;
        }
        v5 = v16[19];
        if ( v5 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
          {
            WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 39);
          }
LABEL_70:
          v24 = -1073741823;
          goto LABEL_32;
        }
        if ( v16[23] )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
          {
            WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 40);
            v24 = -1073741823;
            goto LABEL_32;
          }
          goto LABEL_70;
        }
        v25 = MupLocateUncProviderForPath(
                (__int64)v16,
                v17,
                &v29,
                0,
                *((_QWORD *)v3 + 11),
                v3[24],
                0,
                *((struct _UNICODE_PREFIX_TABLE **)v3 + 6));
        v18 = v29;
        v24 = v25;
        if ( v25 >= 0 )
        {
          v16[21] = v29;
          if ( (*(_DWORD *)(v18 + 148) & 8) != 0 )
          {
            v23 = MupiRerouteCreateToProvider((__int64)v19->FileObject, (const UNICODE_STRING *)(v18 + 24), v5);
          }
          else
          {
LABEL_29:
            v20 = v17->Tail.Overlay.CurrentStackLocation;
            *(_OWORD *)&v20[-1].MajorFunction = *(_OWORD *)&v19->MajorFunction;
            *(_OWORD *)&v20[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v19->Parameters.NotifyDirectoryEx.CompletionFilter;
            *(_OWORD *)(&v20[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v19->Parameters.SetQuota + 6);
            *(_OWORD *)&v20[-1].FileObject = *(_OWORD *)&v19->FileObject;
            v20[-1].Context = v19->Context;
            v21 = v17->Tail.Overlay.CurrentStackLocation;
            v21[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&MupiUncProviderCompletion;
            v21[-1].Context = v3;
            v21[-1].Control = -32;
            AttachedDevice = IoGetAttachedDevice(*(PDEVICE_OBJECT *)(v18 + 168));
            v23 = IofCallDriver(AttachedDevice, v17);
          }
          v24 = v23;
        }
        if ( v24 != 259 )
          goto LABEL_32;
LABEL_33:
        P = (unsigned __int64)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
        {
          WPP_SF_qqqD(WPP_GLOBAL_Control->AttachedDevice, MajorFunction, v5, v17, v18, v3, v24);
        }
        if ( v24 != 259 )
        {
LABEL_37:
          v3[6] = 4;
          v4 = 4;
          continue;
        }
        return 259;
      case 4:
        result = MupCallSurrogatePrePost(v3);
        if ( (_DWORD)result == 259 )
          return result;
        if ( (v3[2] & 4) != 0 )
        {
          P = (unsigned __int64)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              20,
              WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids,
              *((_QWORD *)v3 + 2));
          }
          v3[2] &= ~4u;
          v4 = 0;
        }
        else
        {
          v4 = 5;
        }
        v3[6] = v4;
        continue;
      case 5:
        P = *(_QWORD *)(*((_QWORD *)v3 + 2) + 184LL);
        if ( !*(_BYTE *)P
          || (MajorFunction = (unsigned int)*(unsigned __int8 *)P - 1, *(_BYTE *)P == 1)
          || *(_BYTE *)P == 19 )
        {
          MupUncHardeningPostProcessCreate((ULONG_PTR)v3);
        }
        v3[6] = 6;
        v4 = 6;
        continue;
      case 6:
        return MupiIoPostProcess(v3);
      default:
        P = v6;
        continue;
    }
  }
}

```

## disassembly

```asm
0x14001bb60  mov     r11, rsp
0x14001bb63  push    r12
0x14001bb65  push    r13
0x14001bb67  push    r15
0x14001bb69  sub     rsp, 60h
0x14001bb6d  mov     r12d, [rcx+18h]
0x14001bb71  lea     r15, WPP_GLOBAL_Control
0x14001bb78  mov     [r11+20h], rbx
0x14001bb7c  mov     r13, rcx
0x14001bb7f  mov     [r11-20h], rbp
0x14001bb83  mov     eax, r12d
0x14001bb86  mov     [r11-28h], rsi
0x14001bb8a  mov     [r11-30h], rdi
0x14001bb8e  mov     [r11-38h], r14
0x14001bb92  lea     r8, cs:140000000h; jumptable 000000014001BBAC default case
0x14001bb99  cmp     eax, 6; switch 7 cases
0x14001bb9c  ja      short def_14001BBAC; jumptable 000000014001BBAC default case
0x14001bb9e  movsxd  rcx, eax
0x14001bba1  mov     edx, ds:(jpt_14001BBAC - 140000000h)[r8+rcx*4]
0x14001bba9  add     rdx, r8
0x14001bbac  jmp     rdx; switch jump
0x14001bbb2  mov     rcx, r13; jumptable 000000014001BBAC case 4
0x14001bbb5  call    MupCallSurrogatePrePost
0x14001bbba  cmp     eax, 103h
0x14001bbbf  jz      loc_14001BE3A
0x14001bbc5  mov     eax, [r13+8]
0x14001bbc9  test    al, 4
0x14001bbcb  jnz     loc_14001C054
0x14001bbd1  mov     eax, 5
0x14001bbd6  mov     [r13+18h], eax
0x14001bbda  jmp     short def_14001BBAC; jumptable 000000014001BBAC default case
0x14001bbdc  mov     rbp, [r13+10h]; jumptable 000000014001BBAC case 1
0x14001bbe0  mov     rsi, [rbp+0B8h]
0x14001bbe7  movzx   edx, byte ptr [rsi]
0x14001bbea  mov     ecx, edx
0x14001bbec  test    edx, edx
0x14001bbee  jz      short loc_14001BBFE
0x14001bbf0  sub     ecx, 1
0x14001bbf3  jz      short loc_14001BBFE
0x14001bbf5  cmp     ecx, 12h
0x14001bbf8  jnz     loc_14001BCCB
0x14001bbfe  mov     rax, [r13+28h]
0x14001bc02  mov     r14, [rax+0F8h]
0x14001bc09  test    r14, r14
0x14001bc0c  jz      loc_14001BF09
0x14001bc12  mov     r14d, [r14+58h]
0x14001bc16  mov     [rsp+78h+EcpList], 0
0x14001bc22  mov     [rsp+78h+arg_10], 0
0x14001bc2e  mov     byte ptr [rsp+78h+arg_0], 0
0x14001bc36  test    dl, dl
0x14001bc38  jnz     short loc_14001BC91
0x14001bc3a  cmp     dword ptr [rsi+20h], 0
0x14001bc3e  jz      short loc_14001BC8A
0x14001bc40  mov     rbx, [rbp+18h]
0x14001bc44  lea     r8, aEcpC584edbf00d_0; "ECP{c584edbf-00df-4d28-00b8-8435baca891"...
0x14001bc4b  mov     rcx, rbx; void *
0x14001bc4e  lea     rdx, [rsi+20h]
0x14001bc52  mov     r9d, 33h ; '3'
0x14001bc58  call    RfsUtilFilterEa
0x14001bc5d  neg     al
0x14001bc5f  lea     r8, aEcpC584edbf00d; "ECP{c584edbf-00df-4d28-00b8-8435baca891"...
0x14001bc66  mov     r9d, 35h ; '5'
0x14001bc6c  lea     rdx, [rsi+20h]
0x14001bc70  sbb     edi, edi
0x14001bc72  mov     rcx, rbx; void *
0x14001bc75  and     edi, 4
0x14001bc78  call    RfsUtilFilterEa
0x14001bc7d  mov     ecx, edi
0x14001bc7f  or      ecx, 2
0x14001bc82  test    al, al
0x14001bc84  cmovnz  edi, ecx
0x14001bc87  or      r14d, edi
0x14001bc8a  lea     r15, WPP_GLOBAL_Control
0x14001bc91  cmp     byte ptr [rsi], 0
0x14001bc94  jnz     short loc_14001BCB8
0x14001bc96  mov     eax, [rsi+10h]
0x14001bc99  test    al, al
0x14001bc9b  jns     short loc_14001BCB8
0x14001bc9d  movzx   ecx, word ptr [rsi+18h]
0x14001bca1  mov     edx, ecx
0x14001bca3  shr     edx, 0Ch
0x14001bca6  and     edx, 4
0x14001bca9  mov     eax, edx
0x14001bcab  or      eax, 2
0x14001bcae  bt      ecx, 0Fh
0x14001bcb2  cmovnb  eax, edx
0x14001bcb5  or      r14d, eax
0x14001bcb8  test    r14d, r14d
0x14001bcbb  jnz     loc_14001BF0E
0x14001bcc1  xor     eax, eax
0x14001bcc3  test    eax, eax
0x14001bcc5  js      loc_14001BFBA
0x14001bccb  mov     eax, 2
0x14001bcd0  mov     [r13+18h], eax
0x14001bcd4  jmp     def_14001BBAC; jumptable 000000014001BBAC default case
0x14001bcd9  cmp     r12d, 3; jumptable 000000014001BBAC case 3
0x14001bcdd  jz      loc_14001BDAC
0x14001bce3  mov     r14, [r13+28h]
0x14001bce7  mov     rbp, [r13+10h]
0x14001bceb  mov     rsi, [r14+0A8h]
0x14001bcf2  mov     rdi, [rbp+0B8h]
0x14001bcf9  mov     [rsp+78h+arg_0], rsi
0x14001bd01  test    rsi, rsi
0x14001bd04  jz      loc_14001BE66
0x14001bd0a  mov     rax, [rbp+0B8h]
0x14001bd11  lea     rcx, MupiUncProviderCompletion
0x14001bd18  movups  xmm0, xmmword ptr [rdi]
0x14001bd1b  movups  xmmword ptr [rax-48h], xmm0
0x14001bd1f  movups  xmm1, xmmword ptr [rdi+10h]
0x14001bd23  movups  xmmword ptr [rax-38h], xmm1
0x14001bd27  movups  xmm0, xmmword ptr [rdi+20h]
0x14001bd2b  movups  xmmword ptr [rax-28h], xmm0
0x14001bd2f  movups  xmm1, xmmword ptr [rdi+30h]
0x14001bd33  movups  xmmword ptr [rax-18h], xmm1
0x14001bd37  movsd   xmm0, qword ptr [rdi+40h]
0x14001bd3c  movsd   qword ptr [rax-8], xmm0
0x14001bd41  mov     rax, [rbp+0B8h]
0x14001bd48  mov     [rax-10h], rcx
0x14001bd4c  mov     [rax-8], r13
0x14001bd50  mov     byte ptr [rax-45h], 0E0h
0x14001bd54  mov     rcx, [rsi+0A8h]; DeviceObject
0x14001bd5b  call    cs:__imp_IoGetAttachedDevice
0x14001bd62  nop     dword ptr [rax+rax+00h]
0x14001bd67  mov     rcx, rax; DeviceObject
0x14001bd6a  mov     rdx, rbp; Irp
0x14001bd6d  call    cs:__imp_IofCallDriver
0x14001bd74  nop     dword ptr [rax+rax+00h]
0x14001bd79  mov     ebx, eax
0x14001bd7b  cmp     ebx, 103h
0x14001bd81  jz      short loc_14001BD87
0x14001bd83  mov     [r13+20h], ebx
0x14001bd87  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bd8e  cmp     rcx, r15
0x14001bd91  jz      short loc_14001BDA0
0x14001bd93  test    dword ptr [rcx+2Ch], 4000000h
0x14001bd9a  jnz     loc_14001C035
0x14001bda0  cmp     ebx, 103h
0x14001bda6  jz      loc_14001BE62
0x14001bdac  mov     dword ptr [r13+18h], 4
0x14001bdb4  mov     eax, 4
0x14001bdb9  jmp     def_14001BBAC; jumptable 000000014001BBAC default case
0x14001bdbe  mov     dword ptr [r13+18h], 1; jumptable 000000014001BBAC case 0
0x14001bdc6  mov     eax, 1
0x14001bdcb  jmp     def_14001BBAC; jumptable 000000014001BBAC default case
0x14001bdd0  mov     rcx, r13; jumptable 000000014001BBAC case 2
0x14001bdd3  call    MupCallSurrogatePrePost
0x14001bdd8  cmp     eax, 103h
0x14001bddd  jz      short loc_14001BE3A
0x14001bddf  xor     eax, eax
0x14001bde1  cmp     dword ptr [r13+1Ch], 0C0000016h
0x14001bde9  setnz   al
0x14001bdec  add     eax, 3
0x14001bdef  mov     [r13+18h], eax
0x14001bdf3  jmp     def_14001BBAC; jumptable 000000014001BBAC default case
0x14001bdf8  mov     rax, [r13+10h]; jumptable 000000014001BBAC case 5
0x14001bdfc  mov     rcx, [rax+0B8h]
0x14001be03  movzx   edx, byte ptr [rcx]
0x14001be06  test    edx, edx
0x14001be08  jz      loc_14001BEFC
0x14001be0e  sub     edx, 1
0x14001be11  jz      loc_14001BEFC
0x14001be17  cmp     edx, 12h
0x14001be1a  jz      loc_14001BEFC
0x14001be20  mov     dword ptr [r13+18h], 6
0x14001be28  mov     eax, 6
0x14001be2d  jmp     def_14001BBAC; jumptable 000000014001BBAC default case
0x14001be32  mov     rcx, r13; jumptable 000000014001BBAC case 6
0x14001be35  call    MupiIoPostProcess
0x14001be3a  mov     r14, [rsp+78h+var_38]
0x14001be3f  mov     rdi, [rsp+78h+var_30]
0x14001be44  mov     rsi, [rsp+78h+var_28]
0x14001be49  mov     rbp, [rsp+78h+var_20]
0x14001be4e  mov     rbx, [rsp+78h+arg_18]
0x14001be56  add     rsp, 60h
0x14001be5a  pop     r15
0x14001be5c  pop     r13
0x14001be5e  pop     r12
0x14001be60  retn
0x14001be62  mov     eax, ebx
0x14001be64  jmp     short loc_14001BE3A
0x14001be66  mov     eax, [rbp+10h]
0x14001be69  test    al, al
0x14001be6b  jns     loc_14001BF79
0x14001be71  mov     r8, [r14+98h]
0x14001be78  test    r8, r8
0x14001be7b  jnz     loc_14001BFC4
0x14001be81  mov     r9, [r14+0B8h]
0x14001be88  test    r9, r9
0x14001be8b  jnz     loc_14001BFFE
0x14001be91  mov     rax, [r13+30h]
0x14001be95  lea     r8, [rsp+78h+arg_0]
0x14001be9d  mov     [rsp+78h+var_40], rax
0x14001bea2  mov     rdx, rbp
0x14001bea5  mov     eax, [r13+60h]
0x14001bea9  mov     rcx, r14
0x14001beac  mov     [rsp+78h+var_48], r9
0x14001beb1  mov     dword ptr [rsp+78h+var_50], eax
0x14001beb5  mov     rax, [r13+58h]
0x14001beb9  mov     [rsp+78h+var_58], rax
0x14001bebe  call    MupLocateUncProviderForPath
0x14001bec3  mov     rsi, [rsp+78h+arg_0]
0x14001becb  mov     ebx, eax
0x14001becd  test    eax, eax
0x14001becf  js      loc_14001BD7B
0x14001bed5  mov     [r14+0A8h], rsi
0x14001bedc  mov     eax, [rsi+94h]
0x14001bee2  test    al, 8
0x14001bee4  jz      loc_14001BD0A
0x14001beea  mov     rcx, [rdi+30h]
0x14001beee  lea     rdx, [rsi+18h]
0x14001bef2  call    MupiRerouteCreateToProvider
0x14001bef7  jmp     loc_14001BD79
0x14001befc  mov     rcx, r13; BugCheckParameter3
0x14001beff  call    MupUncHardeningPostProcessCreate
0x14001bf04  jmp     loc_14001BE20
0x14001bf09  jmp     loc_14001BC16
0x14001bf0e  lea     rdx, [rsp+78h+EcpList]
0x14001bf16  mov     rcx, rbp; Irp
0x14001bf19  call    MupiGetOrCreateEcpListForCreateIrp
0x14001bf1e  test    eax, eax
0x14001bf20  js      loc_14001BFBA
0x14001bf26  mov     rcx, [rsp+78h+EcpList]; EcpList
0x14001bf2e  lea     r9, [rsp+78h+arg_0]
0x14001bf36  lea     rdx, [rsp+78h+arg_10]
0x14001bf3e  call    MupiFindOrCreateNetworkOpenEcp
0x14001bf43  test    eax, eax
0x14001bf45  js      short loc_14001BFBA
0x14001bf47  cmp     byte ptr [rsp+78h+arg_0], 0
0x14001bf4f  mov     rbx, [rsp+78h+arg_10]
0x14001bf57  jz      short loc_14001BF83
0x14001bf59  mov     ecx, r14d
0x14001bf5c  call    MupiGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities
0x14001bf61  mov     ecx, [rbx+8]
0x14001bf64  cmp     ecx, eax
0x14001bf66  jnz     short loc_14001BFA3
0x14001bf68  and     r14d, 1
0x14001bf6c  shl     r14d, 3
0x14001bf70  or      [rbx+0Ch], r14d
0x14001bf74  jmp     loc_14001BCC1
0x14001bf79  mov     ebx, 0C0000016h
0x14001bf7e  jmp     loc_14001BD83
0x14001bf83  mov     rcx, rbx
0x14001bf86  call    cs:__imp_FsRtlPrepareToReuseEcp
0x14001bf8d  nop     dword ptr [rax+rax+00h]
0x14001bf92  mov     qword ptr [rbx+10h], 0
0x14001bf9a  mov     dword ptr [rbx+18h], 0
0x14001bfa1  jmp     short loc_14001BF59
0x14001bfa3  test    ecx, 0FFFFFFFBh
0x14001bfa9  jz      short loc_14001BFB5
0x14001bfab  mov     eax, 0C0000201h
0x14001bfb0  jmp     loc_14001BCC3
0x14001bfb5  mov     [rbx+8], eax
0x14001bfb8  jmp     short loc_14001BF68
0x14001bfba  mov     eax, 6
0x14001bfbf  jmp     loc_14001BCD0
0x14001bfc4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bfcb  cmp     rcx, r15
0x14001bfce  jz      short loc_14001BFF4
0x14001bfd0  test    dword ptr [rcx+2Ch], 4000000h
0x14001bfd7  jz      short loc_14001BFF4
0x14001bfd9  mov     rcx, [rcx+18h]
0x14001bfdd  mov     edx, 27h ; '''
0x14001bfe2  mov     [rsp+78h+var_50], r8
0x14001bfe7  mov     r9, rbp
0x14001bfea  mov     [rsp+78h+var_58], r14
0x14001bfef  call    WPP_SF_qqq
0x14001bff4  mov     ebx, 0C0000001h
0x14001bff9  jmp     loc_14001BD83
0x14001bffe  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c005  cmp     rcx, r15
0x14001c008  jz      short loc_14001BFF4
0x14001c00a  test    dword ptr [rcx+2Ch], 4000000h
0x14001c011  jz      short loc_14001BFF4
0x14001c013  mov     rcx, [rcx+18h]
0x14001c017  mov     edx, 28h ; '('
0x14001c01c  mov     [rsp+78h+var_50], r14
0x14001c021  mov     [rsp+78h+var_58], rbp
0x14001c026  call    WPP_SF_qqq
0x14001c02b  mov     ebx, 0C0000001h
0x14001c030  jmp     loc_14001BD83
0x14001c035  mov     rcx, [rcx+18h]
0x14001c039  mov     r9, rbp
0x14001c03c  mov     dword ptr [rsp+78h+var_48], ebx
0x14001c040  mov     [rsp+78h+var_50], r13
0x14001c045  mov     [rsp+78h+var_58], rsi
0x14001c04a  call    WPP_SF_qqqD
0x14001c04f  jmp     loc_14001BDA0
0x14001c054  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c05b  cmp     rcx, r15
0x14001c05e  jz      short loc_14001C082
0x14001c060  test    dword ptr [rcx+2Ch], 2000000h
0x14001c067  jz      short loc_14001C082
0x14001c069  mov     r9, [r13+10h]
0x14001c06d  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001c074  mov     rcx, [rcx+18h]
0x14001c078  mov     edx, 14h
0x14001c07d  call    WPP_SF_q
0x14001c082  and     dword ptr [r13+8], 0FFFFFFFBh
0x14001c087  xor     eax, eax
0x14001c089  jmp     loc_14001BBD6
  ... truncated ...
```
