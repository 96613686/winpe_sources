# DfscFsctrlSetClientInfo

- ea: `0x140016070`
- end: `0x1400169ef`
- name: `DfscFsctrlSetClientInfo`
- size: `2431`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x140014910`

## callees

- `0x140001010`
- `0x1400015c0`
- `0x140001f4c`
- `0x1400025f4`
- `0x1400027f8`
- `0x1400046bc`
- `0x140004718`
- `0x140005a70`
- `0x140006380`
- `0x140016070`
- `0x14001a718`
- `0x14001d090`
- `0x14001ef20`
- `0x14001f540`
- `0x140020d10`
- `0x140020fd0`
- `0x140021820`
- `0x140028680`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140016102`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016115`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001612b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016102`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016115`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001612b`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140016394`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400163aa`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140016394`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400163aa`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001675b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400168c8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400168eb`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001675b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400168c8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400168eb`

## pseudocode

```c
__int64 __fastcall DfscFsctrlSetClientInfo(__int64 a1, unsigned __int16 *a2, unsigned int a3)
{
  unsigned int v6; // r8d
  __int64 v7; // r9
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  int ReferralFromPath; // ebx
  USHORT v11; // dx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  USHORT v14; // di
  __int64 v15; // r8
  WCHAR *v16; // r13
  int ContainerContextFromIrp; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // r13
  USHORT Length; // cx
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 CurrentTarget; // rax
  WCHAR *v27; // r8
  USHORT v28; // dx
  unsigned __int16 v29; // cx
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-140h] BYREF
  PVOID P; // [rsp+58h] [rbp-130h] BYREF
  int v33; // [rsp+60h] [rbp-128h]
  struct _UNICODE_STRING v34; // [rsp+68h] [rbp-120h] BYREF
  UNICODE_STRING v35; // [rsp+78h] [rbp-110h] BYREF
  unsigned int v36; // [rsp+88h] [rbp-100h]
  __int64 v37; // [rsp+90h] [rbp-F8h] BYREF
  PVOID v38; // [rsp+98h] [rbp-F0h] BYREF
  UNICODE_STRING v39; // [rsp+A0h] [rbp-E8h] BYREF
  UNICODE_STRING String2; // [rsp+B0h] [rbp-D8h] BYREF
  struct _UNICODE_STRING v41; // [rsp+C0h] [rbp-C8h] BYREF
  struct _UNICODE_STRING v42; // [rsp+D0h] [rbp-B8h] BYREF
  __int128 v43; // [rsp+E0h] [rbp-A8h] BYREF
  UNICODE_STRING v44[9]; // [rsp+F0h] [rbp-98h] BYREF
  char v45; // [rsp+1A8h] [rbp+20h] BYREF

  v33 = 0;
  v34 = 0;
  DestinationString = 0;
  String2 = 0;
  v39 = 0;
  v35 = 0;
  P = 0;
  memset(v44, 0, 0x60u);
  v45 = 0;
  v38 = 0;
  v37 = 0;
  if ( a2 && a3 >= 0x14 )
  {
    RtlInitUnicodeString(&DestinationString, 0);
    RtlInitUnicodeString(&v34, 0);
    RtlInitUnicodeString(&String2, 0);
    v6 = *((_DWORD *)a2 + 2);
    v36 = v6;
    if ( v6 == 101 )
    {
      v7 = *((unsigned int *)a2 + 3);
      if ( (_DWORD)v7 != 4 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
        {
          goto LABEL_9;
        }
        v9 = 41;
        goto LABEL_8;
      }
      v11 = a2[1];
      if ( !v11 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
        {
          goto LABEL_9;
        }
        v13 = 42;
        goto LABEL_14;
      }
      v14 = a2[2];
      if ( !v14 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
        {
          goto LABEL_9;
        }
        v13 = 43;
        goto LABEL_14;
      }
    }
    else
    {
      if ( v6 != 102 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
        {
          goto LABEL_9;
        }
        v9 = 44;
        v7 = v6;
LABEL_8:
        WPP_SF_D(v8->AttachedDevice, v9, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids, v7);
LABEL_9:
        ReferralFromPath = -1073741811;
        goto LABEL_122;
      }
      v11 = 0;
      v14 = 0;
      v33 = *((_DWORD *)a2 + 3);
    }
    v15 = *a2;
    if ( (v15 & 1) != 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
      {
        goto LABEL_9;
      }
      v13 = 45;
      goto LABEL_14;
    }
    if ( (v11 & 1) != 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
      {
        goto LABEL_9;
      }
      v13 = 46;
      goto LABEL_14;
    }
    if ( (v14 & 1) != 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
      {
        goto LABEL_9;
      }
      v13 = 47;
      goto LABEL_14;
    }
    if ( v11 + (unsigned int)v15 + v14 > a3 - 16 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
      {
        goto LABEL_9;
      }
      v13 = 48;
      goto LABEL_14;
    }
    v34.MaximumLength = *a2;
    v34.Length = v15;
    v34.Buffer = a2 + 8;
    if ( (unsigned __int16)v15 > 4u && a2[8] == 92 && a2[9] == 92 && a2 != (unsigned __int16 *)-16LL )
    {
      v34.Buffer = a2 + 9;
      v34.Length = v15 - 2;
      v34.MaximumLength = v15 - 2;
    }
    if ( v11 )
    {
      v41 = 0;
      v42 = 0;
      v16 = (unsigned __int16 *)((char *)a2 + v15 + 16);
      DestinationString.Buffer = v16;
      DestinationString.MaximumLength = v11;
      DestinationString.Length = v11;
      RtlInitUnicodeStringEx(&v41, 0);
      RtlInitUnicodeStringEx(&v42, 0);
      if ( DestinationString.Length >= 4u && *DestinationString.Buffer == 92 && DestinationString.Buffer[1] == 92 )
      {
        ++DestinationString.Buffer;
        DestinationString.Length -= 2;
        DestinationString.MaximumLength -= 2;
      }
      if ( (int)DfscGetPathComponents(&DestinationString, &v41, &v42, 0, 0) < 0
        || !v41.Length
        || !v41.Buffer
        || !*v41.Buffer
        || v42.Length && v42.Buffer && *v42.Buffer )
      {
        goto LABEL_9;
      }
      if ( v14 )
      {
        String2.Buffer = (WCHAR *)((char *)v16 + a2[1]);
        String2.MaximumLength = v14;
        String2.Length = v14;
        if ( *String2.Buffer == 92 )
          goto LABEL_9;
      }
    }
    v43 = 0;
    ContainerContextFromIrp = DfscGetContainerContextFromIrp(a1, &v37);
    ReferralFromPath = ContainerContextFromIrp;
    if ( ContainerContextFromIrp >= 0 )
    {
      ReferralFromPath = DfscGetReferralFromPath(a1, 0, &v34, 3, v37, &P, 0, &v43, ContainerContextFromIrp);
      v20 = 0;
      if ( ReferralFromPath < 0 )
      {
        ReferralFromPath = -1073741772;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids, a1);
        }
        goto LABEL_122;
      }
      v21 = *((_QWORD *)P + 2);
      if ( v36 == 102 )
      {
        *(_DWORD *)(v21 + 40) = v33;
        *(_QWORD *)(v21 + 32) = MEMORY[0xFFFFF78000000320];
        ReferralFromPath = 0;
        goto LABEL_122;
      }
      if ( !*(_DWORD *)(v21 + 8) && !*(_WORD *)(v21 + 24) )
      {
        ReferralFromPath = -1073741772;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids, a1);
          v20 = 0;
        }
      }
      Length = DestinationString.Length;
      if ( DestinationString.Length > 2u && DestinationString.Buffer && *DestinationString.Buffer == 92 )
      {
        ++DestinationString.Buffer;
        Length = DestinationString.Length - 2;
        DestinationString.Length -= 2;
        DestinationString.MaximumLength -= 2;
      }
      if ( !Length )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
        {
          goto LABEL_9;
        }
        v13 = 51;
        goto LABEL_14;
      }
      if ( !String2.Length )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
        {
          goto LABEL_9;
        }
        v13 = 52;
LABEL_14:
        WPP_SF_q(v12->AttachedDevice, v13, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids, a1);
        goto LABEL_9;
      }
      while ( !ReferralFromPath )
      {
        v23 = DfscReferralIterate(P, v18, v19, v20);
        ReferralFromPath = v23;
        if ( v23 )
        {
          if ( v23 == -2147483622 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids, a1);
            }
            ReferralFromPath = -1073741772;
            break;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
          {
            WPP_SF_Dq(WPP_GLOBAL_Control->AttachedDevice, v24, v19, v23, a1);
          }
          goto LABEL_90;
        }
        CurrentTarget = DfscReferralGetCurrentTarget(P);
        v27 = *(WCHAR **)(CurrentTarget + 40);
        v39.Buffer = v27;
        v28 = *(_WORD *)(CurrentTarget + 96) + *(_WORD *)(CurrentTarget + 104) - *(_WORD *)(CurrentTarget + 40);
        v39.Length = v28;
        v39.MaximumLength = v28;
        v35 = *(UNICODE_STRING *)(CurrentTarget + 16);
        v29 = _mm_cvtsi128_si32((__m128i)v35);
        if ( v29 > 2u && v35.Buffer && *v35.Buffer == 92 )
        {
          ++v35.Buffer;
          v35.Length = v29 - 2;
          v35.MaximumLength -= 2;
        }
        if ( v28 > 2u && v27 && *v27 == 92 )
        {
          v39.Buffer = v27 + 1;
          v39.Length = v28 - 2;
          v39.MaximumLength = v28 - 2;
        }
        if ( !RtlCompareUnicodeString(&DestinationString, &v35, 1u) && !RtlCompareUnicodeString(&String2, &v39, 1u) )
        {
          *(_WORD *)(*((_QWORD *)P + 2) + 26LL) = *((_WORD *)P + 16);
          *(_BYTE *)(v21 + 14) = 1;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
          {
            WPP_SF_Zq(
              WPP_GLOBAL_Control->AttachedDevice,
              55,
              (unsigned int)WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids,
              (unsigned int)&v35,
              a1);
          }
LABEL_90:
          if ( !ReferralFromPath )
            goto LABEL_122;
          break;
        }
      }
      if ( !(unsigned int)DfscInitDfsPath(&v34, v44, v19, v20)
        && (unsigned __int8)DfscIsSpecialShare(&v44[1])
        && !RtlCompareUnicodeString(&v44[1], &String2, 1u) )
      {
        ReferralFromPath = DfscIsDomainController(v44, &DestinationString, &v45);
        if ( !ReferralFromPath )
        {
          if ( v45 )
          {
            LOBYTE(v25) = 1;
            ReferralFromPath = DfscRmGenerateSysvolNetlogonReferral(v44, &DestinationString, v25, &v38);
            if ( !ReferralFromPath )
            {
              v38 = (PVOID)DfscRefCacheStore(v37, v21, v38, 0);
              DfscRmDereferenceReferral(v38);
            }
          }
        }
        if ( ReferralFromPath || !v45 )
          ReferralFromPath = -1073741772;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids, a3);
    }
    ReferralFromPath = -1073741811;
    *(_QWORD *)(a1 + 56) = 0;
  }
LABEL_122:
  if ( P )
    DfscReferralRelease(P);
  return (unsigned int)ReferralFromPath;
}

```

## disassembly

```asm
0x140016070  push    rbx
0x140016072  push    rsi
0x140016073  push    rdi
0x140016074  push    r12
0x140016076  push    r13
0x140016078  push    r14
0x14001607a  sub     rsp, 158h
0x140016081  mov     r14d, r8d
0x140016084  mov     rbx, rdx
0x140016087  mov     rsi, rcx
0x14001608a  xor     eax, eax
0x14001608c  mov     [rsp+188h+var_128], eax
0x140016090  xorps   xmm0, xmm0
0x140016093  movups  xmmword ptr [rsp+188h+var_120.Length], xmm0
0x140016098  xorps   xmm1, xmm1
0x14001609b  movups  xmmword ptr [rsp+188h+DestinationString.Length], xmm1
0x1400160a0  movups  xmmword ptr [rsp+188h+String2.Length], xmm0
0x1400160a8  movups  xmmword ptr [rsp+188h+var_E8.Length], xmm1
0x1400160b0  movups  xmmword ptr [rsp+188h+var_110.Length], xmm0
0x1400160b5  mov     [rsp+188h+P], rax
0x1400160ba  xor     edx, edx; Val
0x1400160bc  lea     r8d, [rax+60h]; Size
0x1400160c0  lea     rcx, [rsp+188h+var_98]; void *
0x1400160c8  call    memset
0x1400160cd  xor     r9d, r9d
0x1400160d0  mov     [rsp+188h+arg_18], r9b
0x1400160d8  mov     [rsp+188h+var_F0], r9
0x1400160e0  mov     [rsp+188h+var_F8], r9
0x1400160e8  test    rbx, rbx
0x1400160eb  jz      loc_140016988
0x1400160f1  cmp     r14d, 14h
0x1400160f5  jb      loc_140016988
0x1400160fb  xor     edx, edx; SourceString
0x1400160fd  lea     rcx, [rsp+188h+DestinationString]; DestinationString
0x140016102  call    cs:__imp_RtlInitUnicodeString
0x140016109  nop     dword ptr [rax+rax+00h]
0x14001610e  xor     edx, edx; SourceString
0x140016110  lea     rcx, [rsp+188h+var_120]; DestinationString
0x140016115  call    cs:__imp_RtlInitUnicodeString
0x14001611c  nop     dword ptr [rax+rax+00h]
0x140016121  xor     edx, edx; SourceString
0x140016123  lea     rcx, [rsp+188h+String2]; DestinationString
0x14001612b  call    cs:__imp_RtlInitUnicodeString
0x140016132  nop     dword ptr [rax+rax+00h]
0x140016137  mov     r8d, [rbx+8]
0x14001613b  mov     [rsp+188h+var_100], r8d
0x140016143  cmp     r8d, 65h ; 'e'
0x140016147  jnz     loc_140016203
0x14001614d  mov     r9d, [rbx+0Ch]
0x140016151  lea     r12d, [r8-61h]
0x140016155  cmp     r9d, r12d
0x140016158  jz      short loc_140016198
0x14001615a  lea     rdi, WPP_GLOBAL_Control
0x140016161  mov     rcx, cs:WPP_GLOBAL_Control
0x140016168  cmp     rcx, rdi
0x14001616b  jz      short loc_14001618A
0x14001616d  mov     eax, [rcx+2Ch]
0x140016170  bt      eax, 14h
0x140016174  jnb     short loc_14001618A
0x140016176  lea     edx, [r8-3Ch]
0x14001617a  lea     r8, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids
0x140016181  mov     rcx, [rcx+18h]
0x140016185  call    WPP_SF_D
0x14001618a  mov     ebx, 0C000000Dh
0x14001618f  mov     [rsp+188h+var_148], ebx
0x140016193  jmp     loc_1400169CC
0x140016198  movzx   edx, word ptr [rbx+2]
0x14001619c  test    dx, dx
0x14001619f  jnz     short loc_1400161D7
0x1400161a1  lea     rdi, WPP_GLOBAL_Control
0x1400161a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400161af  cmp     rcx, rdi
0x1400161b2  jz      short loc_14001618A
0x1400161b4  mov     eax, [rcx+2Ch]
0x1400161b7  bt      eax, 14h
0x1400161bb  jnb     short loc_14001618A
0x1400161bd  mov     edx, 2Ah ; '*'
0x1400161c2  mov     r9, rsi
0x1400161c5  lea     r8, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids
0x1400161cc  mov     rcx, [rcx+18h]
0x1400161d0  call    WPP_SF_q
0x1400161d5  jmp     short loc_14001618A
0x1400161d7  movzx   edi, word ptr [rbx+4]
0x1400161db  test    di, di
0x1400161de  jnz     short loc_140016221
0x1400161e0  lea     rdi, WPP_GLOBAL_Control
0x1400161e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400161ee  cmp     rcx, rdi
0x1400161f1  jz      short loc_14001618A
0x1400161f3  mov     eax, [rcx+2Ch]
0x1400161f6  bt      eax, 14h
0x1400161fa  jnb     short loc_14001618A
0x1400161fc  mov     edx, 2Bh ; '+'
0x140016201  jmp     short loc_1400161C2
0x140016203  cmp     r8d, 66h ; 'f'
0x140016207  jnz     loc_140016957
0x14001620d  xor     r9d, r9d
0x140016210  mov     edx, r9d
0x140016213  mov     edi, r9d
0x140016216  mov     eax, [rbx+0Ch]
0x140016219  mov     [rsp+188h+var_128], eax
0x14001621d  lea     r12d, [r8-62h]
0x140016221  movzx   r8d, word ptr [rbx]
0x140016225  mov     al, 1
0x140016227  test    al, r8b
0x14001622a  jz      short loc_14001625A
0x14001622c  lea     rdi, WPP_GLOBAL_Control
0x140016233  mov     rcx, cs:WPP_GLOBAL_Control
0x14001623a  cmp     rcx, rdi
0x14001623d  jz      loc_14001618A
0x140016243  mov     eax, [rcx+2Ch]
0x140016246  bt      eax, 14h
0x14001624a  jnb     loc_14001618A
0x140016250  mov     edx, 2Dh ; '-'
0x140016255  jmp     loc_1400161C2
0x14001625a  test    al, dl
0x14001625c  jz      short loc_14001628C
0x14001625e  lea     rdi, WPP_GLOBAL_Control
0x140016265  mov     rcx, cs:WPP_GLOBAL_Control
0x14001626c  cmp     rcx, rdi
0x14001626f  jz      loc_14001618A
0x140016275  mov     eax, [rcx+2Ch]
0x140016278  bt      eax, 14h
0x14001627c  jnb     loc_14001618A
0x140016282  mov     edx, 2Eh ; '.'
0x140016287  jmp     loc_1400161C2
0x14001628c  test    al, dil
0x14001628f  jz      short loc_1400162BF
0x140016291  lea     rdi, WPP_GLOBAL_Control
0x140016298  mov     rcx, cs:WPP_GLOBAL_Control
0x14001629f  cmp     rcx, rdi
0x1400162a2  jz      loc_14001618A
0x1400162a8  mov     eax, [rcx+2Ch]
0x1400162ab  bt      eax, 14h
0x1400162af  jnb     loc_14001618A
0x1400162b5  mov     edx, 2Fh ; '/'
0x1400162ba  jmp     loc_1400161C2
0x1400162bf  movzx   ecx, di
0x1400162c2  add     ecx, r8d
0x1400162c5  movzx   eax, dx
0x1400162c8  add     ecx, eax
0x1400162ca  lea     eax, [r14-10h]
0x1400162ce  cmp     ecx, eax
0x1400162d0  jbe     short loc_140016300
0x1400162d2  lea     rdi, WPP_GLOBAL_Control
0x1400162d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400162e0  cmp     rcx, rdi
0x1400162e3  jz      loc_14001618A
0x1400162e9  mov     eax, [rcx+2Ch]
0x1400162ec  bt      eax, 14h
0x1400162f0  jnb     loc_14001618A
0x1400162f6  mov     edx, 30h ; '0'
0x1400162fb  jmp     loc_1400161C2
0x140016300  mov     [rsp+188h+var_120.MaximumLength], r8w
0x140016306  mov     [rsp+188h+var_120.Length], r8w
0x14001630c  lea     rax, [rbx+10h]
0x140016310  mov     [rsp+188h+var_120.Buffer], rax
0x140016315  cmp     r8w, r12w
0x140016319  jbe     short loc_14001634F
0x14001631b  cmp     word ptr [rax], 5Ch ; '\'
0x14001631f  jnz     short loc_14001634F
0x140016321  lea     rcx, [rax+2]
0x140016325  cmp     word ptr [rcx], 5Ch ; '\'
0x140016329  jnz     short loc_14001634F
0x14001632b  mov     r14d, 2
0x140016331  test    rax, rax
0x140016334  jz      short loc_140016355
0x140016336  mov     [rsp+188h+var_120.Buffer], rcx
0x14001633b  movzx   eax, r8w
0x14001633f  sub     ax, r14w
0x140016343  mov     [rsp+188h+var_120.Length], ax
0x140016348  mov     [rsp+188h+var_120.MaximumLength], ax
0x14001634d  jmp     short loc_140016355
0x14001634f  mov     r14d, 2
0x140016355  test    dx, dx
0x140016358  jz      loc_1400164AC
0x14001635e  xorps   xmm0, xmm0
0x140016361  movups  xmmword ptr [rsp+188h+var_C8.Length], xmm0
0x140016369  xorps   xmm1, xmm1
0x14001636c  movups  xmmword ptr [rsp+188h+var_B8.Length], xmm1
0x140016374  lea     r13, [r8+10h]
0x140016378  add     r13, rbx
0x14001637b  mov     [rsp+188h+DestinationString.Buffer], r13
0x140016380  mov     [rsp+188h+DestinationString.MaximumLength], dx
0x140016385  mov     [rsp+188h+DestinationString.Length], dx
0x14001638a  xor     edx, edx; SourceString
0x14001638c  lea     rcx, [rsp+188h+var_C8]; DestinationString
0x140016394  call    cs:__imp_RtlInitUnicodeStringEx
0x14001639b  nop     dword ptr [rax+rax+00h]
0x1400163a0  xor     edx, edx; SourceString
0x1400163a2  lea     rcx, [rsp+188h+var_B8]; DestinationString
0x1400163aa  call    cs:__imp_RtlInitUnicodeStringEx
0x1400163b1  nop     dword ptr [rax+rax+00h]
0x1400163b6  movzx   eax, [rsp+188h+DestinationString.Length]
0x1400163bb  cmp     ax, r12w
0x1400163bf  jb      short loc_1400163F8
0x1400163c1  mov     rcx, [rsp+188h+DestinationString.Buffer]
0x1400163c6  cmp     word ptr [rcx], 5Ch ; '\'
0x1400163ca  jnz     short loc_1400163F8
0x1400163cc  add     rcx, 2
0x1400163d0  cmp     word ptr [rcx], 5Ch ; '\'
0x1400163d4  jnz     short loc_1400163F8
0x1400163d6  cmp     ax, r14w
0x1400163da  jbe     short loc_1400163F8
0x1400163dc  mov     [rsp+188h+DestinationString.Buffer], rcx
0x1400163e1  mov     r12d, 0FFFEh
0x1400163e7  add     ax, r12w
0x1400163eb  mov     [rsp+188h+DestinationString.Length], ax
0x1400163f0  add     [rsp+188h+DestinationString.MaximumLength], r12w
0x1400163f6  jmp     short loc_1400163FE
0x1400163f8  mov     r12d, 0FFFEh
0x1400163fe  xor     eax, eax
0x140016400  mov     [rsp+188h+var_168], rax
0x140016405  xor     r9d, r9d
0x140016408  lea     r8, [rsp+188h+var_B8]
0x140016410  lea     rdx, [rsp+188h+var_C8]
0x140016418  lea     rcx, [rsp+188h+DestinationString]
0x14001641d  call    DfscGetPathComponents
0x140016422  mov     [rsp+188h+var_148], eax
0x140016426  xor     r9d, r9d
0x140016429  test    eax, eax
0x14001642b  js      loc_14001618A
0x140016431  cmp     [rsp+188h+var_C8.Length], r9w
0x14001643a  jz      loc_14001618A
0x140016440  mov     rax, [rsp+188h+var_C8.Buffer]
0x140016448  test    rax, rax
0x14001644b  jz      loc_14001618A
0x140016451  cmp     [rax], r9w
0x140016455  jz      loc_14001618A
0x14001645b  cmp     [rsp+188h+var_B8.Length], r9w
0x140016464  jz      short loc_14001647D
0x140016466  mov     rax, [rsp+188h+var_B8.Buffer]
0x14001646e  test    rax, rax
0x140016471  jz      short loc_14001647D
0x140016473  cmp     [rax], r9w
0x140016477  jnz     loc_14001618A
0x14001647d  test    di, di
0x140016480  jz      short loc_1400164B2
0x140016482  movzx   eax, word ptr [rbx+2]
0x140016486  add     rax, r13
0x140016489  mov     [rsp+188h+String2.Buffer], rax
0x140016491  mov     [rsp+188h+String2.MaximumLength], di
0x140016499  mov     [rsp+188h+String2.Length], di
0x1400164a1  cmp     word ptr [rax], 5Ch ; '\'
0x1400164a5  jnz     short loc_1400164B2
0x1400164a7  jmp     loc_14001618A
0x1400164ac  mov     r12d, 0FFFEh
0x1400164b2  xorps   xmm0, xmm0
0x1400164b5  movups  [rsp+188h+var_A8], xmm0
0x1400164bd  lea     rdx, [rsp+188h+var_F8]
0x1400164c5  mov     rcx, rsi
0x1400164c8  call    DfscGetContainerContextFromIrp
0x1400164cd  mov     ebx, eax
0x1400164cf  mov     [rsp+188h+var_148], eax
0x1400164d3  xor     r9d, r9d
0x1400164d6  test    eax, eax
0x1400164d8  js      loc_1400169CC
0x1400164de  lea     rax, [rsp+188h+var_A8]
0x1400164e6  mov     [rsp+188h+var_150], rax
0x1400164eb  mov     [rsp+188h+var_158], r9
0x1400164f0  lea     rax, [rsp+188h+P]
0x1400164f5  mov     [rsp+188h+var_160], rax
0x1400164fa  mov     rax, [rsp+188h+var_F8]
0x140016502  mov     [rsp+188h+var_168], rax
0x140016507  mov     r9d, 3
0x14001650d  lea     r8, [rsp+188h+var_120]
0x140016512  xor     edx, edx
0x140016514  mov     rcx, rsi
0x140016517  call    DfscGetReferralFromPath
0x14001651c  mov     ebx, eax
0x14001651e  mov     [rsp+188h+var_148], eax
0x140016522  xor     r9d, r9d
0x140016525  test    eax, eax
0x140016527  jns     short loc_140016572
0x140016529  mov     ebx, 0C0000034h
0x14001652e  mov     [rsp+188h+var_148], ebx
0x140016532  lea     rdi, WPP_GLOBAL_Control
0x140016539  mov     rcx, cs:WPP_GLOBAL_Control
0x140016540  cmp     rcx, rdi
0x140016543  jz      loc_1400169CC
0x140016549  mov     eax, [rcx+2Ch]
0x14001654c  bt      eax, 15h
0x140016550  jnb     loc_1400169CC
0x140016556  lea     edx, [r9+31h]
0x14001655a  mov     r9, rsi
0x14001655d  lea     r8, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids
0x140016564  mov     rcx, [rcx+18h]
0x140016568  call    WPP_SF_q
0x14001656d  jmp     loc_1400169CC
0x140016572  mov     rax, [rsp+188h+P]
0x140016577  mov     r13, [rax+10h]
0x14001657b  cmp     [rsp+188h+var_100], 66h ; 'f'
0x140016583  jnz     short loc_1400165A6
0x140016585  mov     eax, [rsp+188h+var_128]
0x140016589  mov     [r13+28h], eax
0x14001658d  mov     rax, 0FFFFF78000000320h
0x140016597  mov     rax, [rax]
0x14001659a  mov     [r13+20h], rax
0x14001659e  mov     ebx, r9d
0x1400165a1  jmp     loc_14001618F
  ... truncated ...
```
