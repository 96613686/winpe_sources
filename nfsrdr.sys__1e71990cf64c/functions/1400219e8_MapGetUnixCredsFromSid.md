# MapGetUnixCredsFromSid

- ea: `0x1400219e8`
- end: `0x14002204b`
- name: `MapGetUnixCredsFromSid`
- size: `1635`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140028608`
- `0x140029b24`

## callees

- `0x140011f84`
- `0x140013ac0`
- `0x140014d04`
- `0x1400159cc`
- `0x1400159fc`
- `0x140018310`
- `0x140020c90`
- `0x1400219e8`
- `0x140022220`
- `0x1400222b4`
- `0x140022364`
- `0x140022414`
- `0x14002d1e4`
- `0x14003aba0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140021fdb`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021fdb`
- `ntoskrnl!RtlInitAnsiString` at `0x140021a86`
- `ntoskrnl!RtlInitAnsiString` at `0x140021a86`
- `ntoskrnl!RtlLengthSid` at `0x140021b16`
- `ntoskrnl!RtlLengthSid` at `0x140021b16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021fee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021fee`
- `rpcxdr!OncRpcBuildCall` at `0x140021b52`
- `rpcxdr!OncRpcBuildCall` at `0x140021b52`
- `rpcxdr!OncRpcDestroy` at `0x140021f98`
- `rpcxdr!OncRpcDestroy` at `0x140021fae`
- `rpcxdr!OncRpcDestroy` at `0x140021f98`
- `rpcxdr!OncRpcDestroy` at `0x140021fae`

## pseudocode

```c
__int64 __fastcall MapGetUnixCredsFromSid(__int64 a1, __int64 a2, void *a3, _DWORD *a4)
{
  __int64 v4; // rbx
  int MapVersion; // eax
  unsigned int v10; // ebx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  ULONG v14; // ebx
  int v15; // edx
  int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rsi
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  unsigned int v24; // eax
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // r8
  unsigned int i; // esi
  unsigned int v30; // eax
  unsigned int j; // esi
  struct _ERESOURCE *v32; // rcx
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  struct _STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  PERESOURCE Resource[10]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v38[256]; // [rsp+C0h] [rbp-40h] BYREF

  v4 = *(_QWORD *)(a1 + 80);
  v35 = 0;
  v34 = 0;
  DestinationString = 0;
  memset(Resource, 0, 0x48u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
  RtlInitAnsiString(&DestinationString, byte_14003D436);
  memset(Resource, 0, 0x48u);
  *a4 = *(_DWORD *)(v4 + 2332);
  a4[1] = *(_DWORD *)(v4 + 2336);
  *((_QWORD *)a4 + 1) = 0;
  MapVersion = GetMapVersion(a1, Resource);
  v10 = MapVersion;
  if ( MapVersion < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v12 = 17;
      v13 = (unsigned int)MapVersion;
LABEL_8:
      WPP_SF_d(v11->AttachedDevice, v12, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids, v13);
      goto LABEL_90;
    }
    goto LABEL_90;
  }
  if ( LODWORD(Resource[2]) < 2 )
  {
    v10 = -1073545126;
    goto LABEL_90;
  }
  v14 = RtlLengthSid(a3);
  if ( (int)OncRpcBuildCall(
              &v35,
              (char *)&Resource[5] + 4,
              LODWORD(Resource[1]),
              HIDWORD(Resource[1]),
              Resource[2],
              9,
              v14 + 4,
              0) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
    v10 = -1073741670;
    goto LABEL_90;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids, v38);
  XdrEncodeOpaqueAndLengthUnsafe(v35, v14, a3);
  if ( *(int *)(v35 + 264) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
    v10 = *(_DWORD *)(v35 + 264);
    goto LABEL_90;
  }
  v16 = NfsSendWaitReply(*(_QWORD *)(a1 + 80), v15, 0, a1, a2, (__int64)Resource, v35, (__int64)&v34, 0);
  if ( v16 < 0 || !v34 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids,
        (unsigned int)v16);
    v10 = -1073741261;
    goto LABEL_90;
  }
  v10 = OncRpcMapRpcStatusToNtStatus(v34);
  if ( (v10 & 0x80000000) == 0 )
  {
    v17 = XdrDecodeInt(v34);
    v18 = v17;
    if ( *(int *)(v34 + 264) < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_81;
      v20 = 23;
    }
    else
    {
      if ( !v17 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
        v10 = -1073741715;
        goto LABEL_90;
      }
      if ( v17 <= 0x40 )
      {
        XdrDecodeString(v34, v17, v38);
        v21 = v34;
        if ( *(int *)(v34 + 264) < 0 )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_81;
          }
          v20 = 26;
        }
        else
        {
          v38[v18] = 0;
          v22 = XdrDecodeInt(v21);
          v23 = v34;
          *a4 = v22;
          if ( *(int *)(v23 + 264) < 0 )
          {
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_81;
            }
            v20 = 27;
          }
          else
          {
            v24 = XdrDecodeInt(v23);
            v25 = v34;
            a4[2] = v24;
            if ( *(int *)(v25 + 264) >= 0 && v24 )
            {
              if ( v24 > 0x10 )
                a4[2] = 16;
              v26 = XdrDecodeInt(v34);
              v27 = v34;
              a4[1] = v26;
              if ( *(int *)(v27 + 264) >= 0 )
              {
                v28 = (unsigned int)--a4[2];
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                {
                  WPP_SF_slll(WPP_GLOBAL_Control->AttachedDevice, v26, v28, (unsigned int)v38, *a4, v26, a4[2]);
                }
                for ( i = 0; ; ++i )
                {
                  v30 = a4[2];
                  if ( i >= v30 )
                  {
                    if ( v30 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                      {
                        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
                      }
                      for ( j = 0; j < a4[2]; ++j )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                        {
                          WPP_SF_l(WPP_GLOBAL_Control->AttachedDevice, 33, v28, (unsigned int)a4[j + 3]);
                        }
                      }
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                      {
                        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
                      }
                    }
                    goto LABEL_90;
                  }
                  a4[i + 3] = XdrDecodeInt(v34);
                  if ( *(int *)(v34 + 264) < 0 )
                    break;
                }
                v19 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                {
                  v20 = 31;
                  goto LABEL_80;
                }
                goto LABEL_81;
              }
              v19 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
              {
LABEL_81:
                v10 = -1073741629;
                goto LABEL_90;
              }
              v20 = 29;
            }
            else
            {
              v19 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
              {
                goto LABEL_81;
              }
              v20 = 28;
            }
          }
        }
      }
      else
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_81;
        v20 = 25;
      }
    }
LABEL_80:
    WPP_SF_(v19->AttachedDevice, v20, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids);
    goto LABEL_81;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v12 = 22;
    v13 = v10;
    goto LABEL_8;
  }
LABEL_90:
  if ( v34 )
    OncRpcDestroy(v34);
  if ( v35 )
    OncRpcDestroy(v35);
  v32 = Resource[0];
  if ( Resource[0] )
  {
    if ( Resource[4] )
    {
      NfsForceDisconnect(Resource, 0);
      v32 = Resource[0];
    }
    ExDeleteResourceLite(v32);
    ExFreePoolWithTag(Resource[0], 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x1400219e8  push    rbp
0x1400219ea  push    rbx
0x1400219eb  push    rsi
0x1400219ec  push    rdi
0x1400219ed  push    r12
0x1400219ef  push    r13
0x1400219f1  push    r14
0x1400219f3  push    r15
0x1400219f5  lea     rbp, [rsp-0D8h]
0x1400219fd  sub     rsp, 1D8h
0x140021a04  mov     rax, cs:__security_cookie
0x140021a0b  xor     rax, rsp
0x140021a0e  mov     [rbp+110h+var_50], rax
0x140021a15  mov     rbx, [rcx+50h]
0x140021a19  xor     r12d, r12d
0x140021a1c  mov     r14, r8
0x140021a1f  mov     [rsp+210h+var_1B8], r12
0x140021a24  mov     r15, rdx
0x140021a27  mov     [rsp+210h+var_1C0], r12
0x140021a2c  mov     rsi, rcx
0x140021a2f  xorps   xmm0, xmm0
0x140021a32  lea     r8d, [r12+48h]; Size
0x140021a37  xor     edx, edx; Val
0x140021a39  lea     rcx, [rsp+210h+Resource]; void *
0x140021a3e  mov     rdi, r9
0x140021a41  movups  xmmword ptr [rsp+210h+DestinationString.Length], xmm0
0x140021a46  call    memset
0x140021a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140021a52  lea     r13, WPP_GLOBAL_Control
0x140021a59  cmp     rcx, r13
0x140021a5c  jz      short loc_140021A7A
0x140021a5e  mov     eax, [rcx+2Ch]
0x140021a61  test    al, 10h
0x140021a63  jz      short loc_140021A7A
0x140021a65  mov     rcx, [rcx+18h]
0x140021a69  lea     edx, [r12+10h]
0x140021a6e  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x140021a75  call    WPP_SF_
0x140021a7a  lea     rdx, byte_14003D436; SourceString
0x140021a81  lea     rcx, [rsp+210h+DestinationString]; DestinationString
0x140021a86  call    cs:__imp_RtlInitAnsiString
0x140021a8d  nop     dword ptr [rax+rax+00h]
0x140021a92  xor     edx, edx; Val
0x140021a94  lea     rcx, [rsp+210h+Resource]; void *
0x140021a99  lea     r8d, [rdx+48h]; Size
0x140021a9d  call    memset
0x140021aa2  mov     eax, [rbx+91Ch]
0x140021aa8  lea     rdx, [rsp+210h+Resource]
0x140021aad  mov     [rdi], eax
0x140021aaf  mov     rcx, rsi
0x140021ab2  mov     eax, [rbx+920h]
0x140021ab8  mov     [rdi+4], eax
0x140021abb  mov     [rdi+8], r12
0x140021abf  call    GetMapVersion
0x140021ac4  mov     ebx, eax
0x140021ac6  test    eax, eax
0x140021ac8  jns     short loc_140021B03
0x140021aca  mov     rcx, cs:WPP_GLOBAL_Control
0x140021ad1  cmp     rcx, r13
0x140021ad4  jz      loc_140021F8E
0x140021ada  mov     edx, [rcx+2Ch]
0x140021add  test    dl, 1
0x140021ae0  jz      loc_140021F8E
0x140021ae6  mov     edx, 11h
0x140021aeb  mov     r9d, eax
0x140021aee  mov     rcx, [rcx+18h]
0x140021af2  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x140021af9  call    WPP_SF_d
0x140021afe  jmp     loc_140021F8E
0x140021b03  cmp     [rbp+110h+var_190], 2
0x140021b07  jnb     short loc_140021B13
0x140021b09  mov     ebx, 0C003005Ah
0x140021b0e  jmp     loc_140021F8E
0x140021b13  mov     rcx, r14; Sid
0x140021b16  call    cs:__imp_RtlLengthSid
0x140021b1d  nop     dword ptr [rax+rax+00h]
0x140021b22  mov     r9d, [rsp+210h+var_194]
0x140021b27  lea     rdx, [rbp+110h+var_174]
0x140021b2b  mov     r8d, [rsp+210h+var_198]
0x140021b30  mov     ebx, eax
0x140021b32  mov     [rsp+210h+var_1D8], r12
0x140021b37  lea     ecx, [rax+4]
0x140021b3a  mov     dword ptr [rsp+210h+var_1E0], ecx
0x140021b3e  mov     ecx, [rbp+110h+var_190]
0x140021b41  mov     dword ptr [rsp+210h+var_1E8], 9
0x140021b49  mov     dword ptr [rsp+210h+var_1F0], ecx
0x140021b4d  lea     rcx, [rsp+210h+var_1B8]
0x140021b52  call    cs:__imp_OncRpcBuildCall
0x140021b59  nop     dword ptr [rax+rax+00h]
0x140021b5e  test    eax, eax
0x140021b60  jns     short loc_140021B94
0x140021b62  mov     rcx, cs:WPP_GLOBAL_Control
0x140021b69  cmp     rcx, r13
0x140021b6c  jz      short loc_140021B8A
0x140021b6e  mov     eax, [rcx+2Ch]
0x140021b71  test    al, 1
0x140021b73  jz      short loc_140021B8A
0x140021b75  mov     rcx, [rcx+18h]
0x140021b79  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x140021b80  mov     edx, 12h
0x140021b85  call    WPP_SF_
0x140021b8a  mov     ebx, 0C000009Ah
0x140021b8f  jmp     loc_140021F8E
0x140021b94  mov     rcx, cs:WPP_GLOBAL_Control
0x140021b9b  cmp     rcx, r13
0x140021b9e  jz      short loc_140021BC0
0x140021ba0  mov     eax, [rcx+2Ch]
0x140021ba3  test    al, 4
0x140021ba5  jz      short loc_140021BC0
0x140021ba7  mov     rcx, [rcx+18h]
0x140021bab  lea     r9, [rbp+110h+var_150]
0x140021baf  mov     edx, 13h
0x140021bb4  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x140021bbb  call    WPP_SF_s
0x140021bc0  mov     rcx, [rsp+210h+var_1B8]
0x140021bc5  mov     r8, r14
0x140021bc8  mov     edx, ebx
0x140021bca  call    XdrEncodeOpaqueAndLengthUnsafe
0x140021bcf  mov     rcx, [rsp+210h+var_1B8]
0x140021bd4  cmp     [rcx+108h], r12d
0x140021bdb  jl      loc_140021F5B
0x140021be1  mov     [rsp+210h+var_1D0], r12d
0x140021be6  lea     rax, [rsp+210h+var_1C0]
0x140021beb  mov     [rsp+210h+var_1D8], rax
0x140021bf0  mov     r9, rsi
0x140021bf3  mov     [rsp+210h+var_1E0], rcx
0x140021bf8  lea     rax, [rsp+210h+Resource]
0x140021bfd  mov     rcx, [rsi+50h]
0x140021c01  xor     r8d, r8d
0x140021c04  mov     [rsp+210h+var_1E8], rax
0x140021c09  mov     [rsp+210h+var_1F0], r15
0x140021c0e  call    NfsSendWaitReply
0x140021c13  mov     r9d, eax
0x140021c16  test    eax, eax
0x140021c18  js      loc_140021F2C
0x140021c1e  mov     rcx, [rsp+210h+var_1C0]
0x140021c23  test    rcx, rcx
0x140021c26  jz      loc_140021F2C
0x140021c2c  call    OncRpcMapRpcStatusToNtStatus
0x140021c31  mov     ebx, eax
0x140021c33  test    eax, eax
0x140021c35  jns     short loc_140021C5F
0x140021c37  mov     rcx, cs:WPP_GLOBAL_Control
0x140021c3e  cmp     rcx, r13
0x140021c41  jz      loc_140021F8E
0x140021c47  mov     eax, [rcx+2Ch]
0x140021c4a  test    al, 1
0x140021c4c  jz      loc_140021F8E
0x140021c52  mov     edx, 16h
0x140021c57  mov     r9d, ebx
0x140021c5a  jmp     loc_140021AEE
0x140021c5f  mov     rcx, [rsp+210h+var_1C0]
0x140021c64  call    XdrDecodeInt
0x140021c69  mov     rcx, [rsp+210h+var_1C0]
0x140021c6e  mov     esi, eax
0x140021c70  cmp     [rcx+108h], r12d
0x140021c77  jl      loc_140021EFD
0x140021c7d  test    eax, eax
0x140021c7f  jnz     short loc_140021CB3
0x140021c81  mov     rcx, cs:WPP_GLOBAL_Control
0x140021c88  cmp     rcx, r13
0x140021c8b  jz      short loc_140021CA9
0x140021c8d  mov     eax, [rcx+2Ch]
0x140021c90  test    al, 1
0x140021c92  jz      short loc_140021CA9
0x140021c94  mov     rcx, [rcx+18h]
0x140021c98  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x140021c9f  mov     edx, 18h
0x140021ca4  call    WPP_SF_
0x140021ca9  mov     ebx, 0C000006Dh
0x140021cae  jmp     loc_140021F8E
0x140021cb3  cmp     esi, 40h ; '@'
0x140021cb6  jbe     short loc_140021CDD
0x140021cb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140021cbf  cmp     rcx, r13
0x140021cc2  jz      loc_140021F25
0x140021cc8  mov     eax, [rcx+2Ch]
0x140021ccb  test    al, 1
0x140021ccd  jz      loc_140021F25
0x140021cd3  mov     edx, 19h
0x140021cd8  jmp     loc_140021F15
0x140021cdd  mov     rcx, [rsp+210h+var_1C0]
0x140021ce2  lea     r8, [rbp+110h+var_150]
0x140021ce6  mov     edx, esi
0x140021ce8  call    XdrDecodeString
0x140021ced  mov     rcx, [rsp+210h+var_1C0]
0x140021cf2  cmp     [rcx+108h], r12d
0x140021cf9  jl      loc_140021EE3
0x140021cff  mov     [rbp+rsi+110h+var_150], r12b
0x140021d04  call    XdrDecodeInt
0x140021d09  mov     rcx, [rsp+210h+var_1C0]
0x140021d0e  mov     [rdi], eax
0x140021d10  cmp     [rcx+108h], r12d
0x140021d17  jl      loc_140021EC9
0x140021d1d  call    XdrDecodeInt
0x140021d22  mov     rcx, [rsp+210h+var_1C0]
0x140021d27  mov     [rdi+8], eax
0x140021d2a  cmp     [rcx+108h], r12d
0x140021d31  jl      loc_140021EAF
0x140021d37  test    eax, eax
0x140021d39  jz      loc_140021EAF
0x140021d3f  cmp     eax, 10h
0x140021d42  jbe     short loc_140021D4B
0x140021d44  mov     dword ptr [rdi+8], 10h
0x140021d4b  mov     rcx, [rsp+210h+var_1C0]
0x140021d50  call    XdrDecodeInt
0x140021d55  mov     rcx, [rsp+210h+var_1C0]
0x140021d5a  mov     edx, eax
0x140021d5c  mov     [rdi+4], eax
0x140021d5f  cmp     [rcx+108h], r12d
0x140021d66  jl      loc_140021E91
0x140021d6c  dec     dword ptr [rdi+8]
0x140021d6f  mov     r8d, [rdi+8]
0x140021d73  mov     rcx, cs:WPP_GLOBAL_Control
0x140021d7a  cmp     rcx, r13
0x140021d7d  jz      short loc_140021DA2
0x140021d7f  mov     eax, [rcx+2Ch]
0x140021d82  test    al, 4
0x140021d84  jz      short loc_140021DA2
0x140021d86  mov     eax, [rdi]
0x140021d88  lea     r9, [rbp+110h+var_150]
0x140021d8c  mov     rcx, [rcx+18h]
0x140021d90  mov     dword ptr [rsp+210h+var_1E0], r8d
0x140021d95  mov     dword ptr [rsp+210h+var_1E8], edx
0x140021d99  mov     dword ptr [rsp+210h+var_1F0], eax
0x140021d9d  call    WPP_SF_slll
0x140021da2  mov     esi, r12d
0x140021da5  mov     eax, [rdi+8]
0x140021da8  cmp     esi, eax
0x140021daa  jnb     short loc_140021DF3
0x140021dac  mov     rcx, [rsp+210h+var_1C0]
0x140021db1  call    XdrDecodeInt
0x140021db6  mov     ecx, esi
0x140021db8  mov     [rdi+rcx*4+0Ch], eax
0x140021dbc  mov     rax, [rsp+210h+var_1C0]
0x140021dc1  cmp     [rax+108h], r12d
0x140021dc8  jl      short loc_140021DCE
0x140021dca  inc     esi
0x140021dcc  jmp     short loc_140021DA5
0x140021dce  mov     rcx, cs:WPP_GLOBAL_Control
0x140021dd5  cmp     rcx, r13
0x140021dd8  jz      loc_140021F25
0x140021dde  mov     eax, [rcx+2Ch]
0x140021de1  test    al, 1
0x140021de3  jz      loc_140021F25
0x140021de9  mov     edx, 1Fh
0x140021dee  jmp     loc_140021F15
0x140021df3  test    eax, eax
0x140021df5  jz      loc_140021F8E
0x140021dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140021e02  cmp     rcx, r13
0x140021e05  jz      short loc_140021E23
0x140021e07  mov     eax, [rcx+2Ch]
0x140021e0a  test    al, 4
0x140021e0c  jz      short loc_140021E23
0x140021e0e  mov     rcx, [rcx+18h]
0x140021e12  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x140021e19  mov     edx, 20h ; ' '
0x140021e1e  call    WPP_SF_
0x140021e23  mov     esi, r12d
0x140021e26  cmp     [rdi+8], r12d
0x140021e2a  jbe     short loc_140021E5C
0x140021e2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140021e33  cmp     rcx, r13
0x140021e36  jz      short loc_140021E55
0x140021e38  mov     eax, [rcx+2Ch]
0x140021e3b  test    al, 4
0x140021e3d  jz      short loc_140021E55
0x140021e3f  mov     rcx, [rcx+18h]
0x140021e43  mov     edx, 21h ; '!'
0x140021e48  mov     r9d, esi
0x140021e4b  mov     r9d, [rdi+r9*4+0Ch]
0x140021e50  call    WPP_SF_l
0x140021e55  inc     esi
0x140021e57  cmp     esi, [rdi+8]
0x140021e5a  jb      short loc_140021E2C
0x140021e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140021e63  cmp     rcx, r13
0x140021e66  jz      loc_140021F8E
0x140021e6c  mov     eax, [rcx+2Ch]
0x140021e6f  test    al, 4
0x140021e71  jz      loc_140021F8E
0x140021e77  mov     rcx, [rcx+18h]
0x140021e7b  lea     r8, WPP_9a6c5869e7783a18bc0d72b4cc4dfd38_Traceguids
0x140021e82  mov     edx, 22h ; '"'
0x140021e87  call    WPP_SF_
0x140021e8c  jmp     loc_140021F8E
0x140021e91  mov     rcx, cs:WPP_GLOBAL_Control
0x140021e98  cmp     rcx, r13
0x140021e9b  jz      loc_140021F25
0x140021ea1  mov     eax, [rcx+2Ch]
0x140021ea4  test    al, 1
0x140021ea6  jz      short loc_140021F25
0x140021ea8  mov     edx, 1Dh
0x140021ead  jmp     short loc_140021F15
0x140021eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x140021eb6  cmp     rcx, r13
0x140021eb9  jz      short loc_140021F25
0x140021ebb  mov     eax, [rcx+2Ch]
0x140021ebe  test    al, 1
  ... truncated ...
```
