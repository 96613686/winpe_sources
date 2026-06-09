# MapGetUnixCredsFromNTUserName

- ea: `0x140020fa8`
- end: `0x1400219e1`
- name: `MapGetUnixCredsFromNTUserName`
- size: `2617`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: ``

## callers

- `0x140016cb8`
- `0x140028608`
- `0x140029b24`

## callees

- `0x140011f84`
- `0x140013ac0`
- `0x140014bdc`
- `0x140014d04`
- `0x140014ff4`
- `0x1400150a4`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140020c90`
- `0x140020fa8`
- `0x140022220`
- `0x1400222b4`
- `0x140022300`
- `0x140022414`
- `0x14002d1e4`
- `0x14003aba0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140021934`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021934`
- `ntoskrnl!RtlInitAnsiString` at `0x14002103f`
- `ntoskrnl!RtlInitAnsiString` at `0x14002103f`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14002123c`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14002123c`
- `ntoskrnl!RtlFreeAnsiString` at `0x14002190a`
- `ntoskrnl!RtlFreeAnsiString` at `0x14002190a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021946`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002195b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021971`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021946`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002195b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021971`
- `ntoskrnl!ExAllocatePool2` at `0x14002105b`
- `ntoskrnl!ExAllocatePool2` at `0x14002107b`
- `ntoskrnl!ExAllocatePool2` at `0x14002105b`
- `ntoskrnl!ExAllocatePool2` at `0x14002107b`
- `rpcxdr!OncRpcBuildCall` at `0x140021166`
- `rpcxdr!OncRpcBuildCall` at `0x1400212b9`
- `rpcxdr!OncRpcBuildCall` at `0x140021166`
- `rpcxdr!OncRpcBuildCall` at `0x1400212b9`
- `rpcxdr!OncRpcDestroy` at `0x1400218d8`
- `rpcxdr!OncRpcDestroy` at `0x1400218ed`
- `rpcxdr!OncRpcDestroy` at `0x1400218d8`
- `rpcxdr!OncRpcDestroy` at `0x1400218ed`

## pseudocode

```c
__int64 __fastcall MapGetUnixCredsFromNTUserName(__int64 a1, __int64 a2, const UNICODE_STRING *a3, unsigned int *a4)
{
  __int64 v8; // rbx
  void *v9; // r15
  void *Pool2; // rax
  PVOID v11; // rdi
  int MapVersion; // eax
  NTSTATUS v13; // ebx
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  int v19; // edx
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  int v22; // eax
  unsigned int v23; // eax
  unsigned __int64 v24; // r14
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  _WORD *v30; // r12
  unsigned int v31; // eax
  __int64 v32; // r14
  unsigned int v33; // eax
  __int64 v34; // rcx
  unsigned int v35; // eax
  __int64 v36; // rcx
  unsigned int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // r8
  unsigned int i; // r14d
  unsigned int v41; // eax
  unsigned int j; // r14d
  struct _ERESOURCE *v43; // rcx
  PVOID P; // [rsp+50h] [rbp-79h]
  __int64 v46; // [rsp+58h] [rbp-71h] BYREF
  __int64 v47; // [rsp+60h] [rbp-69h] BYREF
  PVOID v48; // [rsp+68h] [rbp-61h]
  struct _STRING DestinationString; // [rsp+70h] [rbp-59h] BYREF
  PERESOURCE Resource[10]; // [rsp+80h] [rbp-49h] BYREF

  memset(Resource, 0, 0x48u);
  v8 = *(_QWORD *)(a1 + 80);
  DestinationString = 0;
  v47 = 0;
  v46 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
  RtlInitAnsiString(&DestinationString, byte_14003D436);
  P = (PVOID)ExAllocatePool2(258, 256, 844260942);
  v9 = P;
  Pool2 = (void *)ExAllocatePool2(258, 512, 844260942);
  v48 = Pool2;
  v11 = Pool2;
  if ( P && Pool2 )
  {
    memset(Resource, 0, 0x48u);
    *a4 = *(_DWORD *)(v8 + 2332);
    a4[1] = *(_DWORD *)(v8 + 2336);
    *((_QWORD *)a4 + 1) = 0;
    MapVersion = GetMapVersion(a1, Resource);
    v13 = MapVersion;
    if ( MapVersion < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_134;
      v15 = 37;
      v16 = (unsigned int)MapVersion;
      goto LABEL_10;
    }
    if ( LODWORD(Resource[2]) < 2 )
    {
      v13 = RtlUnicodeStringToAnsiString(&DestinationString, a3, 1u);
      if ( v13 < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_134;
        v15 = 41;
        v16 = (unsigned int)v13;
LABEL_10:
        WPP_SF_d(v14->AttachedDevice, v15, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids, v16);
LABEL_134:
        if ( v46 )
          OncRpcDestroy(v46);
        if ( v47 )
          OncRpcDestroy(v47);
        if ( DestinationString.Length && DestinationString.Buffer )
          RtlFreeAnsiString(&DestinationString);
        v43 = Resource[0];
        if ( Resource[0] )
        {
          if ( Resource[4] )
          {
            NfsForceDisconnect(Resource, 0);
            v43 = Resource[0];
          }
          ExDeleteResourceLite(v43);
          ExFreePoolWithTag(Resource[0], 0);
        }
        v11 = v48;
        goto LABEL_146;
      }
      if ( (int)OncRpcBuildCall(
                  &v47,
                  (char *)&Resource[5] + 4,
                  LODWORD(Resource[1]),
                  HIDWORD(Resource[1]),
                  Resource[2],
                  2,
                  DestinationString.Length + 5 + (-(DestinationString.Length + 1) & 3u),
                  0) < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_17;
        v18 = 42;
        goto LABEL_16;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids, a3);
      XdrEncodeOpaqueAndLengthUnsafe(v47, DestinationString.Length, DestinationString.Buffer);
      if ( *(int *)(v47 + 264) < 0 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_133;
        v21 = 44;
        goto LABEL_132;
      }
    }
    else
    {
      if ( (int)OncRpcBuildCall(
                  &v47,
                  (char *)&Resource[5] + 4,
                  LODWORD(Resource[1]),
                  HIDWORD(Resource[1]),
                  Resource[2],
                  13,
                  a3->Length + 5 + (-(a3->Length + 1) & 3u),
                  0) < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_17;
        v18 = 38;
LABEL_16:
        WPP_SF_(v17->AttachedDevice, v18, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
LABEL_17:
        v13 = -1073741670;
        goto LABEL_134;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids, a3);
      XdrEncodeOpaqueAndLengthUnsafe(v47, a3->Length, a3->Buffer);
      if ( *(int *)(v47 + 264) < 0 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_133;
        v21 = 40;
LABEL_132:
        WPP_SF_(v20->AttachedDevice, v21, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
LABEL_133:
        v9 = P;
        v13 = *(_DWORD *)(v47 + 264);
        goto LABEL_134;
      }
    }
    v22 = NfsSendWaitReply(*(_QWORD *)(a1 + 80), v19, 0, a1, a2, (__int64)Resource, v47, (__int64)&v46, 0);
    if ( v22 < 0 || !v46 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          45,
          WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids,
          (unsigned int)v22);
      v13 = -1073741261;
      goto LABEL_43;
    }
    v13 = OncRpcMapRpcStatusToNtStatus(v46);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          46,
          WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids,
          (unsigned int)v13);
      goto LABEL_43;
    }
    if ( LODWORD(Resource[2]) < 2 )
    {
      v31 = XdrDecodeInt(v46);
      v32 = v31;
      if ( *(int *)(v46 + 264) < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_69;
        v28 = 51;
        goto LABEL_68;
      }
      if ( !v31 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_51;
        v26 = 52;
        goto LABEL_50;
      }
      if ( v31 > 0x40 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_69;
        v28 = 53;
        goto LABEL_68;
      }
      XdrDecodeString(v46, v31, P);
      if ( *(int *)(v46 + 264) < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
        v13 = -1073741629;
        v9 = P;
        goto LABEL_134;
      }
      *((_BYTE *)P + v32) = 0;
    }
    else
    {
      v23 = XdrDecodeInt(v46);
      v24 = v23;
      if ( *(int *)(v46 + 264) < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_69;
        v28 = 47;
        goto LABEL_68;
      }
      if ( !v23 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_51;
        v26 = 48;
LABEL_50:
        WPP_SF_(v25->AttachedDevice, v26, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
LABEL_51:
        v13 = -1073741715;
LABEL_43:
        v9 = P;
        goto LABEL_134;
      }
      if ( v23 > 0x80 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_69;
        v28 = 49;
        goto LABEL_68;
      }
      v29 = v46;
      if ( *(int *)(v46 + 264) < 0 || (unsigned int)OncRpcBufMgrGetCurrentValidLengthRemaining(v46 + 32) < v23 )
      {
        v30 = v48;
        XdrDecodeOpaqueSlow(v29, (unsigned int)v24, v48);
      }
      else
      {
        v30 = v48;
        XdrDecodeOpaqueUnsafe(v29, (unsigned int)v24, v48);
      }
      if ( *(int *)(v46 + 264) < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_69;
        v28 = 50;
        goto LABEL_68;
      }
      v30[v24 >> 1] = 0;
    }
    v33 = XdrDecodeInt(v46);
    v34 = v46;
    *a4 = v33;
    if ( *(int *)(v34 + 264) < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_69;
      v28 = 55;
    }
    else
    {
      v35 = XdrDecodeInt(v34);
      v36 = v46;
      a4[2] = v35;
      if ( *(int *)(v36 + 264) >= 0 && v35 )
      {
        if ( v35 > 0x10 )
          a4[2] = 16;
        v37 = XdrDecodeInt(v46);
        v38 = v46;
        a4[1] = v37;
        if ( *(int *)(v38 + 264) >= 0 )
        {
          v39 = --a4[2];
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_lll(WPP_GLOBAL_Control->AttachedDevice, v37, v39, *a4, v37, a4[2]);
          }
          for ( i = 0; ; ++i )
          {
            v41 = a4[2];
            if ( i >= v41 )
            {
              if ( v41 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
                }
                for ( j = 0; j < a4[2]; ++j )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                  {
                    WPP_SF_l(WPP_GLOBAL_Control->AttachedDevice, 61, v39, a4[j + 3]);
                  }
                }
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
                }
              }
              goto LABEL_43;
            }
            a4[i + 3] = XdrDecodeInt(v46);
            if ( *(int *)(v46 + 264) < 0 )
              break;
          }
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v28 = 59;
            goto LABEL_68;
          }
          goto LABEL_69;
        }
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        {
LABEL_69:
          v13 = -1073741629;
          goto LABEL_43;
        }
        v28 = 57;
      }
      else
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_69;
        v28 = 56;
      }
    }
LABEL_68:
    WPP_SF_(v27->AttachedDevice, v28, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
    goto LABEL_69;
  }
  v13 = -1073741670;
  if ( P )
LABEL_146:
    ExFreePoolWithTag(v9, 0);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids, (unsigned int)v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140020fa8  push    rbp
0x140020faa  push    rbx
0x140020fab  push    rsi
0x140020fac  push    rdi
0x140020fad  push    r12
0x140020faf  push    r13
0x140020fb1  push    r14
0x140020fb3  push    r15
0x140020fb5  lea     rbp, [rsp-1Fh]
0x140020fba  sub     rsp, 0E8h
0x140020fc1  mov     rax, cs:__security_cookie
0x140020fc8  xor     rax, rsp
0x140020fcb  mov     [rbp+57h+var_50], rax
0x140020fcf  mov     r12, rdx
0x140020fd2  mov     r14, r8
0x140020fd5  xor     edx, edx; Val
0x140020fd7  mov     r13, rcx
0x140020fda  lea     rcx, [rbp+57h+Resource]; void *
0x140020fde  mov     rsi, r9
0x140020fe1  lea     r8d, [rdx+48h]; Size
0x140020fe5  call    memset
0x140020fea  mov     rbx, [r13+50h]
0x140020fee  xorps   xmm0, xmm0
0x140020ff1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140020ff5  mov     [rbp+57h+var_C0], 0
0x140020ffd  mov     [rbp+57h+var_C8], 0
0x140021005  mov     rcx, cs:WPP_GLOBAL_Control
0x14002100c  lea     rax, WPP_GLOBAL_Control
0x140021013  cmp     rcx, rax
0x140021016  jz      short loc_140021034
0x140021018  mov     eax, [rcx+2Ch]
0x14002101b  test    al, 10h
0x14002101d  jz      short loc_140021034
0x14002101f  mov     rcx, [rcx+18h]
0x140021023  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x14002102a  mov     edx, 24h ; '$'
0x14002102f  call    WPP_SF_
0x140021034  lea     rdx, byte_14003D436; SourceString
0x14002103b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002103f  call    cs:__imp_RtlInitAnsiString
0x140021046  nop     dword ptr [rax+rax+00h]
0x14002104b  mov     edx, 100h
0x140021050  mov     r8d, 3252664Eh
0x140021056  lea     edi, [rdx+2]
0x140021059  mov     ecx, edi
0x14002105b  call    cs:__imp_ExAllocatePool2
0x140021062  nop     dword ptr [rax+rax+00h]
0x140021067  mov     edx, 200h
0x14002106c  mov     r8d, 3252664Eh
0x140021072  mov     ecx, edi
0x140021074  mov     [rbp+57h+P], rax
0x140021078  mov     r15, rax
0x14002107b  call    cs:__imp_ExAllocatePool2
0x140021082  nop     dword ptr [rax+rax+00h]
0x140021087  mov     [rbp+57h+var_B8], rax
0x14002108b  mov     rdi, rax
0x14002108e  test    r15, r15
0x140021091  jz      loc_1400219D2
0x140021097  test    rax, rax
0x14002109a  jz      loc_1400219D2
0x1400210a0  xor     edx, edx; Val
0x1400210a2  lea     rcx, [rbp+57h+Resource]; void *
0x1400210a6  lea     r8d, [rdx+48h]; Size
0x1400210aa  call    memset
0x1400210af  mov     ecx, [rbx+91Ch]
0x1400210b5  lea     rdx, [rbp+57h+Resource]
0x1400210b9  mov     [rsi], ecx
0x1400210bb  mov     ecx, [rbx+920h]
0x1400210c1  mov     [rsi+4], ecx
0x1400210c4  mov     rcx, r13
0x1400210c7  mov     qword ptr [rsi+8], 0
0x1400210cf  call    GetMapVersion
0x1400210d4  mov     ebx, eax
0x1400210d6  test    eax, eax
0x1400210d8  jns     short loc_14002111D
0x1400210da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400210e1  lea     r12, WPP_GLOBAL_Control
0x1400210e8  cmp     rcx, r12
0x1400210eb  jz      loc_1400218CC
0x1400210f1  mov     edx, [rcx+2Ch]
0x1400210f4  mov     edi, 1
0x1400210f9  test    dil, dl
0x1400210fc  jz      loc_1400218CC
0x140021102  lea     edx, [rdi+24h]
0x140021105  mov     r9d, eax
0x140021108  mov     rcx, [rcx+18h]
0x14002110c  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x140021113  call    WPP_SF_d
0x140021118  jmp     loc_1400218CC
0x14002111d  mov     edx, [rbp+57h+var_90]
0x140021120  mov     edi, 1
0x140021125  cmp     edx, 2
0x140021128  jb      loc_140021232
0x14002112e  movzx   ecx, word ptr [r14]
0x140021132  xor     ebx, ebx
0x140021134  mov     r9d, [rbp+57h+var_94]
0x140021138  mov     r8d, [rbp+57h+var_98]
0x14002113c  mov     [rsp+120h+var_E8], rbx
0x140021141  lea     eax, [rcx+1]
0x140021144  add     ecx, 5
0x140021147  neg     eax
0x140021149  and     eax, 3
0x14002114c  add     eax, ecx
0x14002114e  lea     rcx, [rbp+57h+var_C0]
0x140021152  mov     dword ptr [rsp+120h+var_F0], eax
0x140021156  mov     dword ptr [rsp+120h+var_F8], 0Dh
0x14002115e  mov     dword ptr [rsp+120h+var_100], edx
0x140021162  lea     rdx, [rbp+57h+var_74]
0x140021166  call    cs:__imp_OncRpcBuildCall
0x14002116d  nop     dword ptr [rax+rax+00h]
0x140021172  test    eax, eax
0x140021174  jns     short loc_1400211AE
0x140021176  mov     rcx, cs:WPP_GLOBAL_Control
0x14002117d  lea     rax, WPP_GLOBAL_Control
0x140021184  cmp     rcx, rax
0x140021187  jz      short loc_1400211A4
0x140021189  mov     eax, [rcx+2Ch]
0x14002118c  test    dil, al
0x14002118f  jz      short loc_1400211A4
0x140021191  lea     edx, [rdi+25h]
0x140021194  mov     rcx, [rcx+18h]
0x140021198  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x14002119f  call    WPP_SF_
0x1400211a4  mov     ebx, 0C000009Ah
0x1400211a9  jmp     loc_1400218CC
0x1400211ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400211b5  lea     rax, WPP_GLOBAL_Control
0x1400211bc  mov     r15b, 4
0x1400211bf  cmp     rcx, rax
0x1400211c2  jz      short loc_1400211E4
0x1400211c4  mov     eax, [rcx+2Ch]
0x1400211c7  test    r15b, al
0x1400211ca  jz      short loc_1400211E4
0x1400211cc  mov     rcx, [rcx+18h]
0x1400211d0  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x1400211d7  mov     edx, 27h ; '''
0x1400211dc  mov     r9, r14
0x1400211df  call    WPP_SF_Z
0x1400211e4  movzx   edx, word ptr [r14]
0x1400211e8  mov     r8, [r14+8]
0x1400211ec  mov     rcx, [rbp+57h+var_C0]
0x1400211f0  call    XdrEncodeOpaqueAndLengthUnsafe
0x1400211f5  mov     rax, [rbp+57h+var_C0]
0x1400211f9  cmp     [rax+108h], ebx
0x1400211ff  jge     loc_14002134B
0x140021205  mov     rcx, cs:WPP_GLOBAL_Control
0x14002120c  lea     rax, WPP_GLOBAL_Control
0x140021213  cmp     rcx, rax
0x140021216  jz      loc_1400218BE
0x14002121c  mov     eax, [rcx+2Ch]
0x14002121f  test    dil, al
0x140021222  jz      loc_1400218BE
0x140021228  mov     edx, 28h ; '('
0x14002122d  jmp     loc_1400218AE
0x140021232  mov     r8b, dil; AllocateDestinationString
0x140021235  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140021239  mov     rdx, r14; SourceString
0x14002123c  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140021243  nop     dword ptr [rax+rax+00h]
0x140021248  mov     ebx, eax
0x14002124a  test    eax, eax
0x14002124c  jns     short loc_14002127E
0x14002124e  mov     rcx, cs:WPP_GLOBAL_Control
0x140021255  lea     rax, WPP_GLOBAL_Control
0x14002125c  cmp     rcx, rax
0x14002125f  jz      loc_1400218CC
0x140021265  mov     eax, [rcx+2Ch]
0x140021268  test    dil, al
0x14002126b  jz      loc_1400218CC
0x140021271  mov     edx, 29h ; ')'
0x140021276  mov     r9d, ebx
0x140021279  jmp     loc_140021108
0x14002127e  movzx   ecx, [rbp+57h+DestinationString.Length]
0x140021282  lea     rdx, [rbp+57h+var_74]
0x140021286  mov     r9d, [rbp+57h+var_94]
0x14002128a  xor     ebx, ebx
0x14002128c  mov     r8d, [rbp+57h+var_98]
0x140021290  mov     [rsp+120h+var_E8], rbx
0x140021295  lea     eax, [rcx+1]
0x140021298  add     ecx, 5
0x14002129b  neg     eax
0x14002129d  and     eax, 3
0x1400212a0  add     eax, ecx
0x1400212a2  lea     rcx, [rbp+57h+var_C0]
0x1400212a6  mov     dword ptr [rsp+120h+var_F0], eax
0x1400212aa  mov     eax, [rbp+57h+var_90]
0x1400212ad  mov     dword ptr [rsp+120h+var_F8], 2
0x1400212b5  mov     dword ptr [rsp+120h+var_100], eax
0x1400212b9  call    cs:__imp_OncRpcBuildCall
0x1400212c0  nop     dword ptr [rax+rax+00h]
0x1400212c5  test    eax, eax
0x1400212c7  jns     short loc_1400212F4
0x1400212c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400212d0  lea     rax, WPP_GLOBAL_Control
0x1400212d7  cmp     rcx, rax
0x1400212da  jz      loc_1400211A4
0x1400212e0  mov     eax, [rcx+2Ch]
0x1400212e3  test    dil, al
0x1400212e6  jz      loc_1400211A4
0x1400212ec  lea     edx, [rbx+2Ah]
0x1400212ef  jmp     loc_140021194
0x1400212f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400212fb  lea     rax, WPP_GLOBAL_Control
0x140021302  mov     r15b, 4
0x140021305  cmp     rcx, rax
0x140021308  jz      short loc_14002132A
0x14002130a  mov     eax, [rcx+2Ch]
0x14002130d  test    r15b, al
0x140021310  jz      short loc_14002132A
0x140021312  mov     rcx, [rcx+18h]
0x140021316  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x14002131d  mov     edx, 2Bh ; '+'
0x140021322  mov     r9, r14
0x140021325  call    WPP_SF_Z
0x14002132a  movzx   edx, [rbp+57h+DestinationString.Length]
0x14002132e  mov     r8, [rbp+57h+DestinationString.Buffer]
0x140021332  mov     rcx, [rbp+57h+var_C0]
0x140021336  call    XdrEncodeOpaqueAndLengthUnsafe
0x14002133b  mov     rax, [rbp+57h+var_C0]
0x14002133f  cmp     [rax+108h], ebx
0x140021345  jl      loc_14002188E
0x14002134b  mov     rcx, [r13+50h]
0x14002134f  lea     rax, [rbp+57h+var_C8]
0x140021353  mov     [rsp+120h+var_E0], ebx
0x140021357  mov     r9, r13
0x14002135a  mov     [rsp+120h+var_E8], rax
0x14002135f  xor     r8d, r8d
0x140021362  mov     rax, [rbp+57h+var_C0]
0x140021366  mov     [rsp+120h+var_F0], rax
0x14002136b  lea     rax, [rbp+57h+Resource]
0x14002136f  mov     [rsp+120h+var_F8], rax
0x140021374  mov     [rsp+120h+var_100], r12
0x140021379  call    NfsSendWaitReply
0x14002137e  xor     r13d, r13d
0x140021381  mov     r9d, eax
0x140021384  test    eax, eax
0x140021386  js      loc_140021854
0x14002138c  mov     rcx, [rbp+57h+var_C8]
0x140021390  test    rcx, rcx
0x140021393  jz      loc_140021854
0x140021399  call    OncRpcMapRpcStatusToNtStatus
0x14002139e  mov     ebx, eax
0x1400213a0  test    eax, eax
0x1400213a2  jns     short loc_1400213DF
0x1400213a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400213ab  lea     rax, WPP_GLOBAL_Control
0x1400213b2  cmp     rcx, rax
0x1400213b5  jz      short loc_1400213D6
0x1400213b7  mov     eax, [rcx+2Ch]
0x1400213ba  test    dil, al
0x1400213bd  jz      short loc_1400213D6
0x1400213bf  mov     rcx, [rcx+18h]
0x1400213c3  lea     edx, [r13+2Eh]
0x1400213c7  mov     r9d, ebx
0x1400213ca  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x1400213d1  call    WPP_SF_d
0x1400213d6  mov     r15, [rbp+57h+P]
0x1400213da  jmp     loc_1400218CF
0x1400213df  cmp     [rbp+57h+var_90], 2
0x1400213e3  mov     rcx, [rbp+57h+var_C8]
0x1400213e7  jb      loc_140021531
0x1400213ed  call    XdrDecodeInt
0x1400213f2  mov     rcx, [rbp+57h+var_C8]
0x1400213f6  mov     r14d, eax
0x1400213f9  cmp     [rcx+108h], r13d
0x140021400  jl      loc_1400214F7
0x140021406  test    eax, eax
0x140021408  jnz     short loc_140021441
0x14002140a  mov     rcx, cs:WPP_GLOBAL_Control
0x140021411  lea     rax, WPP_GLOBAL_Control
0x140021418  cmp     rcx, rax
0x14002141b  jz      short loc_14002143A
0x14002141d  mov     eax, [rcx+2Ch]
0x140021420  test    dil, al
0x140021423  jz      short loc_14002143A
0x140021425  mov     edx, 30h ; '0'
0x14002142a  mov     rcx, [rcx+18h]
0x14002142e  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x140021435  call    WPP_SF_
0x14002143a  mov     ebx, 0C000006Dh
0x14002143f  jmp     short loc_1400213D6
0x140021441  cmp     r14d, 80h
0x140021448  jbe     short loc_140021477
0x14002144a  mov     rcx, cs:WPP_GLOBAL_Control
0x140021451  lea     rax, WPP_GLOBAL_Control
0x140021458  cmp     rcx, rax
0x14002145b  jz      loc_140021527
0x140021461  mov     eax, [rcx+2Ch]
0x140021464  test    dil, al
0x140021467  jz      loc_140021527
0x14002146d  mov     edx, 31h ; '1'
0x140021472  jmp     loc_140021517
0x140021477  mov     r9, [rbp+57h+var_C8]
0x14002147b  cmp     [r9+108h], r13d
0x140021482  jl      short loc_1400214A6
0x140021484  lea     rcx, [r9+20h]
0x140021488  call    OncRpcBufMgrGetCurrentValidLengthRemaining
0x14002148d  cmp     eax, r14d
0x140021490  jb      short loc_1400214A6
0x140021492  mov     r12, [rbp+57h+var_B8]
  ... truncated ...
```
