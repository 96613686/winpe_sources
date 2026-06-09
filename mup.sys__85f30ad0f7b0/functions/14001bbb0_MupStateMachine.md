# MupStateMachine

- ea: `0x14001bbb0`
- end: `0x14001c0de`
- name: `MupStateMachine`
- size: `1326`
- prototype: `__int64 __fastcall(unsigned __int64 P, unsigned __int64 MajorFunction)`
- caller_count: `8`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140014590`
- `0x140019d10`
- `0x140019f50`
- `0x140019fb0`
- `0x14001a3c0`
- `0x14001a7b0`
- `0x14001b8b0`
- `0x14001d040`

## callees

- `0x140001cf8`
- `0x140002448`
- `0x140002754`
- `0x140002f2c`
- `0x140002f94`
- `0x140010424`
- `0x14001bbb0`
- `0x14001c0f0`
- `0x14001c350`
- `0x14001cd50`
- `0x14001d548`
- `0x14001d564`
- `0x14001d604`

## import_xrefs

- `ntoskrnl!FsRtlPrepareToReuseEcp` at `0x14001bfd6`
- `ntoskrnl!FsRtlPrepareToReuseEcp` at `0x14001bfd6`
- `ntoskrnl!IofCallDriver` at `0x14001bdbd`
- `ntoskrnl!IofCallDriver` at `0x14001bdbd`
- `ntoskrnl!IoGetAttachedDevice` at `0x14001bdab`
- `ntoskrnl!IoGetAttachedDevice` at `0x14001bdab`

## pseudocode

```c
__int64 __fastcall MupStateMachine(unsigned __int64 P, unsigned __int64 MajorFunction)
{
  int v2; // r12d
  signed __int64 v3; // r13
  int v4; // eax
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // kr00_8
  __int64 result; // rax
  IRP *v8; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  __int64 v10; // r14
  char *MasterIrp; // rbx
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
  __int64 v26; // rbx
  int NetworkOpenEcpIntegrityLevelFromHardeningCapabilities; // eax
  __int64 v28; // [rsp+80h] [rbp+8h] BYREF
  PECP_LIST EcpList; // [rsp+88h] [rbp+10h]
  __int64 v30; // [rsp+90h] [rbp+18h]

  v2 = *(_DWORD *)(P + 24);
  v3 = P;
  v4 = v2;
  while ( 2 )
  {
    v5 = 0x140000000uLL;
    v6 = P;
    P = v4;
    switch ( v4 )
    {
      case 0:
        *(_DWORD *)(v3 + 24) = 1;
        v4 = 1;
        continue;
      case 1:
        v8 = *(IRP **)(v3 + 16);
        CurrentStackLocation = v8->Tail.Overlay.CurrentStackLocation;
        MajorFunction = CurrentStackLocation->MajorFunction;
        P = MajorFunction;
        if ( CurrentStackLocation->MajorFunction )
        {
          P = (unsigned int)(MajorFunction - 1);
          if ( (_DWORD)MajorFunction != 1 && (_DWORD)MajorFunction != 19 )
            goto LABEL_25;
        }
        v10 = *(_QWORD *)(*(_QWORD *)(v3 + 40) + 248LL);
        if ( v10 )
          LODWORD(v10) = *(_DWORD *)(v10 + 88);
        EcpList = 0;
        v30 = 0;
        LOBYTE(v28) = 0;
        if ( !(_BYTE)MajorFunction && CurrentStackLocation->Parameters.Create.EaLength )
        {
          MasterIrp = (char *)v8->AssociatedIrp.MasterIrp;
          v12 = RfsUtilFilterEa(
                  MasterIrp,
                  (int *)&CurrentStackLocation->Parameters.Create.EaLength,
                  "ECP{c584edbf-00df-4d28-00b8-8435baca8911e8}-PRIVACY",
                  0x33u) != 0
              ? 4
              : 0;
          v13 = RfsUtilFilterEa(
                  MasterIrp,
                  (int *)&CurrentStackLocation->Parameters.Create.EaLength,
                  "ECP{c584edbf-00df-4d28-00b8-8435baca8911e8}-INTEGRITY",
                  0x35u);
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
        if ( (int)MupiGetOrCreateEcpListForCreateIrp(v8) < 0 || (int)MupiFindOrCreateNetworkOpenEcp(EcpList) < 0 )
          goto LABEL_66;
        v26 = v30;
        if ( !(_BYTE)v28 )
        {
          FsRtlPrepareToReuseEcp(v30);
          *(_QWORD *)(v26 + 16) = 0;
          *(_DWORD *)(v26 + 24) = 0;
        }
        NetworkOpenEcpIntegrityLevelFromHardeningCapabilities = MupiGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities((unsigned int)v10);
        P = *(unsigned int *)(v26 + 8);
        if ( (_DWORD)P == NetworkOpenEcpIntegrityLevelFromHardeningCapabilities )
          goto LABEL_61;
        if ( (P & 0xFFFFFFFB) != 0 )
        {
          v15 = -1073741311;
        }
        else
        {
          *(_DWORD *)(v26 + 8) = NetworkOpenEcpIntegrityLevelFromHardeningCapabilities;
LABEL_61:
          *(_DWORD *)(v26 + 12) |= 8 * (v10 & 1);
LABEL_23:
          v15 = 0;
        }
        if ( v15 < 0 )
LABEL_66:
          v4 = 6;
        else
LABEL_25:
          v4 = 2;
        *(_DWORD *)(v3 + 24) = v4;
        continue;
      case 2:
        result = MupCallSurrogatePrePost(v3);
        if ( (_DWORD)result == 259 )
          return result;
        v4 = (*(_DWORD *)(v3 + 28) != -1073741802) + 3;
        *(_DWORD *)(v3 + 24) = v4;
        continue;
      case 3:
        if ( v2 == 3 )
          goto LABEL_37;
        v16 = *(_QWORD **)(v3 + 40);
        v17 = *(IRP **)(v3 + 16);
        v18 = v16[21];
        v19 = v17->Tail.Overlay.CurrentStackLocation;
        v28 = v18;
        if ( v18 )
          goto LABEL_29;
        if ( (v17->Flags & 0x80u) == 0 )
        {
          v24 = -1073741802;
LABEL_32:
          *(_DWORD *)(v3 + 32) = v24;
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
                &v28,
                0,
                *(_QWORD *)(v3 + 88),
                *(_DWORD *)(v3 + 96),
                0,
                *(struct _UNICODE_PREFIX_TABLE **)(v3 + 48));
        v18 = v28;
        v24 = v25;
        if ( v25 >= 0 )
        {
          v16[21] = v28;
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
            v21[-1].Context = (PVOID)v3;
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
          *(_DWORD *)(v3 + 24) = 4;
          v4 = 4;
          continue;
        }
        return 259;
      case 4:
        result = MupCallSurrogatePrePost(v3);
        if ( (_DWORD)result == 259 )
          return result;
        if ( (*(_DWORD *)(v3 + 8) & 4) != 0 )
        {
          P = (unsigned __int64)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              20,
              WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids,
              *(_QWORD *)(v3 + 16));
          }
          *(_DWORD *)(v3 + 8) &= ~4u;
          v4 = 0;
        }
        else
        {
          v4 = 5;
        }
        *(_DWORD *)(v3 + 24) = v4;
        continue;
      case 5:
        P = *(_QWORD *)(*(_QWORD *)(v3 + 16) + 184LL);
        if ( !*(_BYTE *)P
          || (MajorFunction = (unsigned int)*(unsigned __int8 *)P - 1, *(_BYTE *)P == 1)
          || *(_BYTE *)P == 19 )
        {
          MupUncHardeningPostProcessCreate(v3);
        }
        *(_DWORD *)(v3 + 24) = 6;
        v4 = 6;
        continue;
      case 6:
        return MupiIoPostProcess((PVOID)v3);
      default:
        P = v6;
        continue;
    }
  }
}

```

## disassembly

```asm
0x14001bbb0  mov     r11, rsp
0x14001bbb3  push    r12
0x14001bbb5  push    r13
0x14001bbb7  push    r15
0x14001bbb9  sub     rsp, 60h
0x14001bbbd  mov     r12d, [rcx+18h]
0x14001bbc1  lea     r15, WPP_GLOBAL_Control
0x14001bbc8  mov     [r11+20h], rbx
0x14001bbcc  mov     r13, rcx
0x14001bbcf  mov     [r11-20h], rbp
0x14001bbd3  mov     eax, r12d
0x14001bbd6  mov     [r11-28h], rsi
0x14001bbda  mov     [r11-30h], rdi
0x14001bbde  mov     [r11-38h], r14
0x14001bbe2  lea     r8, cs:140000000h; jumptable 000000014001BBFC default case
0x14001bbe9  cmp     eax, 6; switch 7 cases
0x14001bbec  ja      short def_14001BBFC; jumptable 000000014001BBFC default case
0x14001bbee  movsxd  rcx, eax
0x14001bbf1  mov     edx, ds:(jpt_14001BBFC - 140000000h)[r8+rcx*4]
0x14001bbf9  add     rdx, r8
0x14001bbfc  jmp     rdx; switch jump
0x14001bc02  mov     rcx, r13; jumptable 000000014001BBFC case 4
0x14001bc05  call    MupCallSurrogatePrePost
0x14001bc0a  cmp     eax, 103h
0x14001bc0f  jz      loc_14001BE8A
0x14001bc15  mov     eax, [r13+8]
0x14001bc19  test    al, 4
0x14001bc1b  jnz     loc_14001C0A4
0x14001bc21  mov     eax, 5
0x14001bc26  mov     [r13+18h], eax
0x14001bc2a  jmp     short def_14001BBFC; jumptable 000000014001BBFC default case
0x14001bc2c  mov     rbp, [r13+10h]; jumptable 000000014001BBFC case 1
0x14001bc30  mov     rsi, [rbp+0B8h]
0x14001bc37  movzx   edx, byte ptr [rsi]
0x14001bc3a  mov     ecx, edx
0x14001bc3c  test    edx, edx
0x14001bc3e  jz      short loc_14001BC4E
0x14001bc40  sub     ecx, 1
0x14001bc43  jz      short loc_14001BC4E
0x14001bc45  cmp     ecx, 12h
0x14001bc48  jnz     loc_14001BD1B
0x14001bc4e  mov     rax, [r13+28h]
0x14001bc52  mov     r14, [rax+0F8h]
0x14001bc59  test    r14, r14
0x14001bc5c  jz      loc_14001BF59
0x14001bc62  mov     r14d, [r14+58h]
0x14001bc66  mov     [rsp+78h+EcpList], 0
0x14001bc72  mov     [rsp+78h+arg_10], 0
0x14001bc7e  mov     byte ptr [rsp+78h+arg_0], 0
0x14001bc86  test    dl, dl
0x14001bc88  jnz     short loc_14001BCE1
0x14001bc8a  cmp     dword ptr [rsi+20h], 0
0x14001bc8e  jz      short loc_14001BCDA
0x14001bc90  mov     rbx, [rbp+18h]
0x14001bc94  lea     r8, aEcpC584edbf00d_0; "ECP{c584edbf-00df-4d28-00b8-8435baca891"...
0x14001bc9b  mov     rcx, rbx; void *
0x14001bc9e  lea     rdx, [rsi+20h]
0x14001bca2  mov     r9d, 33h ; '3'
0x14001bca8  call    RfsUtilFilterEa
0x14001bcad  neg     al
0x14001bcaf  lea     r8, aEcpC584edbf00d; "ECP{c584edbf-00df-4d28-00b8-8435baca891"...
0x14001bcb6  mov     r9d, 35h ; '5'
0x14001bcbc  lea     rdx, [rsi+20h]
0x14001bcc0  sbb     edi, edi
0x14001bcc2  mov     rcx, rbx; void *
0x14001bcc5  and     edi, 4
0x14001bcc8  call    RfsUtilFilterEa
0x14001bccd  mov     ecx, edi
0x14001bccf  or      ecx, 2
0x14001bcd2  test    al, al
0x14001bcd4  cmovnz  edi, ecx
0x14001bcd7  or      r14d, edi
0x14001bcda  lea     r15, WPP_GLOBAL_Control
0x14001bce1  cmp     byte ptr [rsi], 0
0x14001bce4  jnz     short loc_14001BD08
0x14001bce6  mov     eax, [rsi+10h]
0x14001bce9  test    al, al
0x14001bceb  jns     short loc_14001BD08
0x14001bced  movzx   ecx, word ptr [rsi+18h]
0x14001bcf1  mov     edx, ecx
0x14001bcf3  shr     edx, 0Ch
0x14001bcf6  and     edx, 4
0x14001bcf9  mov     eax, edx
0x14001bcfb  or      eax, 2
0x14001bcfe  bt      ecx, 0Fh
0x14001bd02  cmovnb  eax, edx
0x14001bd05  or      r14d, eax
0x14001bd08  test    r14d, r14d
0x14001bd0b  jnz     loc_14001BF5E
0x14001bd11  xor     eax, eax
0x14001bd13  test    eax, eax
0x14001bd15  js      loc_14001C00A
0x14001bd1b  mov     eax, 2
0x14001bd20  mov     [r13+18h], eax
0x14001bd24  jmp     def_14001BBFC; jumptable 000000014001BBFC default case
0x14001bd29  cmp     r12d, 3; jumptable 000000014001BBFC case 3
0x14001bd2d  jz      loc_14001BDFC
0x14001bd33  mov     r14, [r13+28h]
0x14001bd37  mov     rbp, [r13+10h]
0x14001bd3b  mov     rsi, [r14+0A8h]
0x14001bd42  mov     rdi, [rbp+0B8h]
0x14001bd49  mov     [rsp+78h+arg_0], rsi
0x14001bd51  test    rsi, rsi
0x14001bd54  jz      loc_14001BEB6
0x14001bd5a  mov     rax, [rbp+0B8h]
0x14001bd61  lea     rcx, MupiUncProviderCompletion
0x14001bd68  movups  xmm0, xmmword ptr [rdi]
0x14001bd6b  movups  xmmword ptr [rax-48h], xmm0
0x14001bd6f  movups  xmm1, xmmword ptr [rdi+10h]
0x14001bd73  movups  xmmword ptr [rax-38h], xmm1
0x14001bd77  movups  xmm0, xmmword ptr [rdi+20h]
0x14001bd7b  movups  xmmword ptr [rax-28h], xmm0
0x14001bd7f  movups  xmm1, xmmword ptr [rdi+30h]
0x14001bd83  movups  xmmword ptr [rax-18h], xmm1
0x14001bd87  movsd   xmm0, qword ptr [rdi+40h]
0x14001bd8c  movsd   qword ptr [rax-8], xmm0
0x14001bd91  mov     rax, [rbp+0B8h]
0x14001bd98  mov     [rax-10h], rcx
0x14001bd9c  mov     [rax-8], r13
0x14001bda0  mov     byte ptr [rax-45h], 0E0h
0x14001bda4  mov     rcx, [rsi+0A8h]; DeviceObject
0x14001bdab  call    cs:__imp_IoGetAttachedDevice
0x14001bdb2  nop     dword ptr [rax+rax+00h]
0x14001bdb7  mov     rcx, rax; DeviceObject
0x14001bdba  mov     rdx, rbp; Irp
0x14001bdbd  call    cs:__imp_IofCallDriver
0x14001bdc4  nop     dword ptr [rax+rax+00h]
0x14001bdc9  mov     ebx, eax
0x14001bdcb  cmp     ebx, 103h
0x14001bdd1  jz      short loc_14001BDD7
0x14001bdd3  mov     [r13+20h], ebx
0x14001bdd7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bdde  cmp     rcx, r15
0x14001bde1  jz      short loc_14001BDF0
0x14001bde3  test    dword ptr [rcx+2Ch], 4000000h
0x14001bdea  jnz     loc_14001C085
0x14001bdf0  cmp     ebx, 103h
0x14001bdf6  jz      loc_14001BEB2
0x14001bdfc  mov     dword ptr [r13+18h], 4
0x14001be04  mov     eax, 4
0x14001be09  jmp     def_14001BBFC; jumptable 000000014001BBFC default case
0x14001be0e  mov     dword ptr [r13+18h], 1; jumptable 000000014001BBFC case 0
0x14001be16  mov     eax, 1
0x14001be1b  jmp     def_14001BBFC; jumptable 000000014001BBFC default case
0x14001be20  mov     rcx, r13; jumptable 000000014001BBFC case 2
0x14001be23  call    MupCallSurrogatePrePost
0x14001be28  cmp     eax, 103h
0x14001be2d  jz      short loc_14001BE8A
0x14001be2f  xor     eax, eax
0x14001be31  cmp     dword ptr [r13+1Ch], 0C0000016h
0x14001be39  setnz   al
0x14001be3c  add     eax, 3
0x14001be3f  mov     [r13+18h], eax
0x14001be43  jmp     def_14001BBFC; jumptable 000000014001BBFC default case
0x14001be48  mov     rax, [r13+10h]; jumptable 000000014001BBFC case 5
0x14001be4c  mov     rcx, [rax+0B8h]
0x14001be53  movzx   edx, byte ptr [rcx]
0x14001be56  test    edx, edx
0x14001be58  jz      loc_14001BF4C
0x14001be5e  sub     edx, 1
0x14001be61  jz      loc_14001BF4C
0x14001be67  cmp     edx, 12h
0x14001be6a  jz      loc_14001BF4C
0x14001be70  mov     dword ptr [r13+18h], 6
0x14001be78  mov     eax, 6
0x14001be7d  jmp     def_14001BBFC; jumptable 000000014001BBFC default case
0x14001be82  mov     rcx, r13; jumptable 000000014001BBFC case 6
0x14001be85  call    MupiIoPostProcess
0x14001be8a  mov     r14, [rsp+78h+var_38]
0x14001be8f  mov     rdi, [rsp+78h+var_30]
0x14001be94  mov     rsi, [rsp+78h+var_28]
0x14001be99  mov     rbp, [rsp+78h+var_20]
0x14001be9e  mov     rbx, [rsp+78h+arg_18]
0x14001bea6  add     rsp, 60h
0x14001beaa  pop     r15
0x14001beac  pop     r13
0x14001beae  pop     r12
0x14001beb0  retn
0x14001beb2  mov     eax, ebx
0x14001beb4  jmp     short loc_14001BE8A
0x14001beb6  mov     eax, [rbp+10h]
0x14001beb9  test    al, al
0x14001bebb  jns     loc_14001BFC9
0x14001bec1  mov     r8, [r14+98h]
0x14001bec8  test    r8, r8
0x14001becb  jnz     loc_14001C014
0x14001bed1  mov     r9, [r14+0B8h]
0x14001bed8  test    r9, r9
0x14001bedb  jnz     loc_14001C04E
0x14001bee1  mov     rax, [r13+30h]
0x14001bee5  lea     r8, [rsp+78h+arg_0]
0x14001beed  mov     [rsp+78h+var_40], rax
0x14001bef2  mov     rdx, rbp
0x14001bef5  mov     eax, [r13+60h]
0x14001bef9  mov     rcx, r14
0x14001befc  mov     [rsp+78h+var_48], r9
0x14001bf01  mov     dword ptr [rsp+78h+var_50], eax
0x14001bf05  mov     rax, [r13+58h]
0x14001bf09  mov     [rsp+78h+var_58], rax
0x14001bf0e  call    MupLocateUncProviderForPath
0x14001bf13  mov     rsi, [rsp+78h+arg_0]
0x14001bf1b  mov     ebx, eax
0x14001bf1d  test    eax, eax
0x14001bf1f  js      loc_14001BDCB
0x14001bf25  mov     [r14+0A8h], rsi
0x14001bf2c  mov     eax, [rsi+94h]
0x14001bf32  test    al, 8
0x14001bf34  jz      loc_14001BD5A
0x14001bf3a  mov     rcx, [rdi+30h]
0x14001bf3e  lea     rdx, [rsi+18h]
0x14001bf42  call    MupiRerouteCreateToProvider
0x14001bf47  jmp     loc_14001BDC9
0x14001bf4c  mov     rcx, r13; BugCheckParameter3
0x14001bf4f  call    MupUncHardeningPostProcessCreate
0x14001bf54  jmp     loc_14001BE70
0x14001bf59  jmp     loc_14001BC66
0x14001bf5e  lea     rdx, [rsp+78h+EcpList]
0x14001bf66  mov     rcx, rbp; Irp
0x14001bf69  call    MupiGetOrCreateEcpListForCreateIrp
0x14001bf6e  test    eax, eax
0x14001bf70  js      loc_14001C00A
0x14001bf76  mov     rcx, [rsp+78h+EcpList]; EcpList
0x14001bf7e  lea     r9, [rsp+78h+arg_0]
0x14001bf86  lea     rdx, [rsp+78h+arg_10]
0x14001bf8e  call    MupiFindOrCreateNetworkOpenEcp
0x14001bf93  test    eax, eax
0x14001bf95  js      short loc_14001C00A
0x14001bf97  cmp     byte ptr [rsp+78h+arg_0], 0
0x14001bf9f  mov     rbx, [rsp+78h+arg_10]
0x14001bfa7  jz      short loc_14001BFD3
0x14001bfa9  mov     ecx, r14d
0x14001bfac  call    MupiGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities
0x14001bfb1  mov     ecx, [rbx+8]
0x14001bfb4  cmp     ecx, eax
0x14001bfb6  jnz     short loc_14001BFF3
0x14001bfb8  and     r14d, 1
0x14001bfbc  shl     r14d, 3
0x14001bfc0  or      [rbx+0Ch], r14d
0x14001bfc4  jmp     loc_14001BD11
0x14001bfc9  mov     ebx, 0C0000016h
0x14001bfce  jmp     loc_14001BDD3
0x14001bfd3  mov     rcx, rbx
0x14001bfd6  call    cs:__imp_FsRtlPrepareToReuseEcp
0x14001bfdd  nop     dword ptr [rax+rax+00h]
0x14001bfe2  mov     qword ptr [rbx+10h], 0
0x14001bfea  mov     dword ptr [rbx+18h], 0
0x14001bff1  jmp     short loc_14001BFA9
0x14001bff3  test    ecx, 0FFFFFFFBh
0x14001bff9  jz      short loc_14001C005
0x14001bffb  mov     eax, 0C0000201h
0x14001c000  jmp     loc_14001BD13
0x14001c005  mov     [rbx+8], eax
0x14001c008  jmp     short loc_14001BFB8
0x14001c00a  mov     eax, 6
0x14001c00f  jmp     loc_14001BD20
0x14001c014  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c01b  cmp     rcx, r15
0x14001c01e  jz      short loc_14001C044
0x14001c020  test    dword ptr [rcx+2Ch], 4000000h
0x14001c027  jz      short loc_14001C044
0x14001c029  mov     rcx, [rcx+18h]
0x14001c02d  mov     edx, 27h ; '''
0x14001c032  mov     [rsp+78h+var_50], r8
0x14001c037  mov     r9, rbp
0x14001c03a  mov     [rsp+78h+var_58], r14
0x14001c03f  call    WPP_SF_qqq
0x14001c044  mov     ebx, 0C0000001h
0x14001c049  jmp     loc_14001BDD3
0x14001c04e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c055  cmp     rcx, r15
0x14001c058  jz      short loc_14001C044
0x14001c05a  test    dword ptr [rcx+2Ch], 4000000h
0x14001c061  jz      short loc_14001C044
0x14001c063  mov     rcx, [rcx+18h]
0x14001c067  mov     edx, 28h ; '('
0x14001c06c  mov     [rsp+78h+var_50], r14
0x14001c071  mov     [rsp+78h+var_58], rbp
0x14001c076  call    WPP_SF_qqq
0x14001c07b  mov     ebx, 0C0000001h
0x14001c080  jmp     loc_14001BDD3
0x14001c085  mov     rcx, [rcx+18h]
0x14001c089  mov     r9, rbp
0x14001c08c  mov     dword ptr [rsp+78h+var_48], ebx
0x14001c090  mov     [rsp+78h+var_50], r13
0x14001c095  mov     [rsp+78h+var_58], rsi
0x14001c09a  call    WPP_SF_qqqD
0x14001c09f  jmp     loc_14001BDF0
0x14001c0a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c0ab  cmp     rcx, r15
0x14001c0ae  jz      short loc_14001C0D2
0x14001c0b0  test    dword ptr [rcx+2Ch], 2000000h
0x14001c0b7  jz      short loc_14001C0D2
0x14001c0b9  mov     r9, [r13+10h]
0x14001c0bd  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001c0c4  mov     rcx, [rcx+18h]
0x14001c0c8  mov     edx, 14h
0x14001c0cd  call    WPP_SF_q
0x14001c0d2  and     dword ptr [r13+8], 0FFFFFFFBh
0x14001c0d7  xor     eax, eax
0x14001c0d9  jmp     loc_14001BC26
  ... truncated ...
```
