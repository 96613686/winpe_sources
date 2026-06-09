# Smb2ProcessOnDiskIdEcp

- ea: `0x140007840`
- end: `0x140007bc5`
- name: `Smb2ProcessOnDiskIdEcp`
- size: `901`
- prototype: `__int64 __fastcall(__int64, __int64, _OWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007470`

## callees

- `0x140007840`
- `0x1400297fc`
- `0x14002a9ac`
- `0x14002af1c`
- `0x140037120`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140007aac`
- `ntoskrnl!EtwWriteTransfer` at `0x140007aac`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140007a05`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140007ac0`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140007b05`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140007a05`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140007ac0`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140007b05`

## pseudocode

```c
__int64 __fastcall Smb2ProcessOnDiskIdEcp(__int64 a1, __int64 a2, _OWORD *a3, unsigned int a4)
{
  unsigned int v5; // esi
  __int128 v6; // xmm1
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int64 v9; // rax
  _WORD *v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rdx
  __int64 ConfigurationBlock; // rax
  char v15; // cl
  __int64 v16; // rax
  int v17; // edx
  int v18; // r8d
  const char *v19; // r9
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  char v23; // [rsp+30h] [rbp-39h] BYREF
  char v24; // [rsp+31h] [rbp-38h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-35h]
  __int64 v26; // [rsp+38h] [rbp-31h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-19h] BYREF
  int *v29; // [rsp+60h] [rbp-9h]
  int v30; // [rsp+68h] [rbp-1h]
  int v31; // [rsp+6Ch] [rbp+3h]
  __int64 *v32; // [rsp+70h] [rbp+7h]
  __int64 v33; // [rsp+78h] [rbp+Fh]
  char *v34; // [rsp+80h] [rbp+17h]
  __int64 v35; // [rsp+88h] [rbp+1Fh]
  char *v36; // [rsp+90h] [rbp+27h]
  __int64 v37; // [rsp+98h] [rbp+2Fh]

  if ( a4 < 0x20 )
  {
    v5 = -1073741629;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_ec883060206d3d6ef99cecbe53c54519_Traceguids);
    }
    return v5;
  }
  v5 = 0;
  *(_OWORD *)(a2 + 1) = *a3;
  v6 = a3[1];
  *(_BYTE *)a2 |= 2u;
  *(_OWORD *)(a2 + 17) = v6;
  v7 = *(_QWORD *)(a1 + 56);
  v8 = *(_QWORD *)(v7 + 136);
  *(_QWORD *)(v7 + 240) = *(_QWORD *)a3;
  *(_OWORD *)(v8 + 24) = *a3;
  *(_OWORD *)(v8 + 40) = a3[1];
  v9 = *(_QWORD *)(v8 + 24);
  if ( v9 == -1 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return v5;
    }
    v21 = 18;
LABEL_38:
    WPP_SF_q(v20->AttachedDevice, v21, WPP_ec883060206d3d6ef99cecbe53c54519_Traceguids, a1);
    return v5;
  }
  if ( v9 )
  {
    *(_DWORD *)(v8 + 8) |= 2u;
    return v5;
  }
  v10 = (_WORD *)(*(_QWORD *)(a1 + 56) + 360LL);
  if ( *(_QWORD *)(a1 + 56) == -360 || *v10 && (*v10 != 2 || **(_WORD **)(*(_QWORD *)(a1 + 56) + 368LL) != 92) )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return v5;
    }
    v21 = 17;
    goto LABEL_38;
  }
  v11 = MEMORY[0xFFFFF78000000320];
  v12 = _InterlockedCompareExchange64((volatile signed __int64 *)&WPP_MAIN_CB.Queue.ListEntry.Flink, 0, 0);
  while ( !v12
       || v12 < MEMORY[0xFFFFF78000000320]
       && (struct _LIST_ENTRY *)(MEMORY[0xFFFFF78000000320] - v12) >= WPP_MAIN_CB.Queue.ListEntry.Blink )
  {
    v13 = v12;
    v12 = _InterlockedCompareExchange64(
            (volatile signed __int64 *)&WPP_MAIN_CB.Queue.ListEntry.Flink,
            MEMORY[0xFFFFF78000000320],
            v12);
    if ( v12 == v13 )
    {
      if ( (unsigned int)dword_140046050 > 5 )
      {
        v11 = qword_140046068;
        if ( (qword_140046060 & 0x400000000000LL) != 0 && (qword_140046068 & 0x400000000000LL) == qword_140046068 )
        {
          v26 = 0x1000000;
          v32 = &v26;
          v34 = &v23;
          v33 = 8;
          v23 = 0;
          v35 = 1;
          ConfigurationBlock = MRxSmbGetConfigurationBlock(qword_140046068);
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0x400000000000LL;
          v15 = *(_BYTE *)(ConfigurationBlock + 516);
          v36 = &v24;
          v24 = v15;
          UserData.Ptr = (ULONGLONG)off_140046058;
          *(_DWORD *)&EventDescriptor.Level = 5;
          v37 = 1;
          UserData.Size = (unsigned __int16)*off_140046058;
          v29 = &dword_14004015C;
          UserData.Reserved = 2;
          v30 = 86;
          v31 = 1;
          v25 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
        }
      }
      break;
    }
  }
  if ( *(_BYTE *)(MRxSmbGetConfigurationBlock(v11) + 516) )
    *(_DWORD *)(v8 + 8) |= 2u;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v16 = MRxSmbGetConfigurationBlock(WPP_GLOBAL_Control);
    v19 = "is";
    if ( !*(_BYTE *)(v16 + 516) )
      v19 = "is not";
    WPP_SF_sq(WPP_GLOBAL_Control->AttachedDevice, v17, v18, (_DWORD)v19, a1);
  }
  return v5;
}

```

## disassembly

```asm
0x140007840  push    rbp
0x140007842  push    rsi
0x140007843  push    rdi
0x140007844  lea     rbp, [rsp-47h]
0x140007849  sub     rsp, 0B0h
0x140007850  mov     rax, cs:__security_cookie
0x140007857  xor     rax, rsp
0x14000785a  mov     [rbp+57h+var_20], rax
0x14000785e  mov     rdi, rcx
0x140007861  cmp     r9d, 20h ; ' '
0x140007865  jnb     short loc_1400078B2
0x140007867  mov     esi, 0C00000C3h
0x14000786c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140007873  lea     rax, WPP_GLOBAL_Control
0x14000787a  cmp     rcx, rax
0x14000787d  jz      loc_140007BAB
0x140007883  mov     eax, [rcx+2Ch]
0x140007886  test    al, 1
0x140007888  jz      loc_140007BAB
0x14000788e  cmp     byte ptr [rcx+29h], 1
0x140007892  jb      loc_140007BAB
0x140007898  mov     rcx, [rcx+18h]
0x14000789c  lea     r8, WPP_ec883060206d3d6ef99cecbe53c54519_Traceguids
0x1400078a3  mov     edx, 0Fh
0x1400078a8  call    WPP_SF_
0x1400078ad  jmp     loc_140007BAB
0x1400078b2  movups  xmm0, xmmword ptr [r8]
0x1400078b6  mov     [rsp+0C0h+arg_10], rbx
0x1400078be  xor     esi, esi
0x1400078c0  movups  xmmword ptr [rdx+1], xmm0
0x1400078c4  movups  xmm1, xmmword ptr [r8+10h]
0x1400078c9  or      byte ptr [rdx], 2
0x1400078cc  movups  xmmword ptr [rdx+11h], xmm1
0x1400078d0  mov     rcx, [rcx+38h]
0x1400078d4  mov     rax, [r8]
0x1400078d7  mov     rbx, [rcx+88h]
0x1400078de  mov     [rcx+0F0h], rax
0x1400078e5  movups  xmm0, xmmword ptr [r8]
0x1400078e9  movups  xmmword ptr [rbx+18h], xmm0
0x1400078ed  movups  xmm1, xmmword ptr [r8+10h]
0x1400078f2  movups  xmmword ptr [rbx+28h], xmm1
0x1400078f6  mov     rax, [rbx+18h]
0x1400078fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400078fe  jz      loc_140007B6A
0x140007904  test    rax, rax
0x140007907  jz      short loc_140007912
0x140007909  or      dword ptr [rbx+8], 2
0x14000790d  jmp     loc_140007BA3
0x140007912  mov     rax, [rdi+38h]
0x140007916  add     rax, 168h
0x14000791c  jz      loc_140007B43
0x140007922  movzx   ecx, word ptr [rax]
0x140007925  test    cx, cx
0x140007928  jz      short loc_140007942
0x14000792a  cmp     cx, 2
0x14000792e  jnz     loc_140007B43
0x140007934  mov     rax, [rax+8]
0x140007938  cmp     word ptr [rax], 5Ch ; '\'
0x14000793c  jnz     loc_140007B43
0x140007942  mov     rcx, 0FFFFF78000000320h
0x14000794c  xor     edx, edx
0x14000794e  xor     eax, eax
0x140007950  mov     rcx, [rcx]
0x140007953  lock cmpxchg qword ptr cs:WPP_MAIN_CB.Queue, rdx
0x14000795c  nop     dword ptr [rax+00h]
0x140007960  test    rax, rax
0x140007963  jz      short loc_140007981
0x140007965  cmp     rax, rcx
0x140007968  jnb     loc_140007AC0
0x14000796e  mov     rdx, rcx
0x140007971  sub     rdx, rax
0x140007974  cmp     rdx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000797b  jb      loc_140007AC0
0x140007981  mov     rdx, rax
0x140007984  lock cmpxchg qword ptr cs:WPP_MAIN_CB.Queue, rcx
0x14000798d  cmp     rax, rdx
0x140007990  jnz     short loc_140007960
0x140007992  mov     eax, cs:dword_140046050
0x140007998  cmp     eax, 5
0x14000799b  jbe     loc_140007AC0
0x1400079a1  mov     rcx, cs:qword_140046068
0x1400079a8  mov     rax, cs:qword_140046060
0x1400079af  mov     [rsp+0C0h+arg_18], r14
0x1400079b7  mov     r14, 400000000000h
0x1400079c1  test    r14, rax
0x1400079c4  jz      loc_140007AB8
0x1400079ca  mov     rax, rcx
0x1400079cd  and     rax, r14
0x1400079d0  cmp     rax, rcx
0x1400079d3  jnz     loc_140007AB8
0x1400079d9  lea     rax, [rbp+57h+var_88]
0x1400079dd  mov     [rbp+57h+var_88], 1000000h
0x1400079e5  mov     [rbp+57h+var_50], rax
0x1400079e9  lea     rax, [rbp+57h+var_90]
0x1400079ed  mov     [rbp+57h+var_40], rax
0x1400079f1  mov     [rbp+57h+var_48], 8
0x1400079f9  mov     [rbp+57h+var_90], sil
0x1400079fd  mov     [rbp+57h+var_38], 1
0x140007a05  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140007a0c  nop     dword ptr [rax+rax+00h]
0x140007a11  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140007a18  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140007a1c  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x140007a20  xor     r9d, r9d; RelatedActivityId
0x140007a23  xor     r8d, r8d; ActivityId
0x140007a26  movzx   ecx, byte ptr [rax+204h]
0x140007a2d  lea     rax, [rbp+57h+var_8F]
0x140007a31  mov     [rbp+57h+var_30], rax
0x140007a35  mov     rax, cs:qword_140040152
0x140007a3c  mov     [rbp+57h+var_8F], cl
0x140007a3f  movzx   ecx, ax
0x140007a42  mov     rax, cs:off_140046058
0x140007a49  mov     [rbp+57h+var_70.Ptr], rax
0x140007a4d  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x140007a50  lea     rcx, _TraceLoggingMetadata
0x140007a57  mov     [rbp+57h+var_28], 1
0x140007a5f  movzx   eax, word ptr [rax]
0x140007a62  mov     [rbp+57h+var_70.Size], eax
0x140007a65  lea     rax, dword_14004015C
0x140007a6c  mov     [rbp+57h+var_60], rax
0x140007a70  lea     rax, _TraceLoggingMetadataEnd
0x140007a77  sub     eax, ecx
0x140007a79  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x140007a80  mov     [rbp+57h+var_58], 56h ; 'V'
0x140007a87  mov     [rbp+57h+var_54], 1
0x140007a8e  mov     [rbp+57h+var_8C], eax
0x140007a91  mov     eax, [rbp+57h+var_8C]
0x140007a94  mov     rcx, cs:RegHandle; RegHandle
0x140007a9b  lea     rax, [rbp+57h+var_70]
0x140007a9f  mov     [rsp+0C0h+UserData], rax; UserData
0x140007aa4  mov     [rsp+0C0h+UserDataCount], 5; UserDataCount
0x140007aac  call    cs:__imp_EtwWriteTransfer
0x140007ab3  nop     dword ptr [rax+rax+00h]
0x140007ab8  mov     r14, [rsp+0C0h+arg_18]
0x140007ac0  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140007ac7  nop     dword ptr [rax+rax+00h]
0x140007acc  cmp     [rax+204h], sil
0x140007ad3  jz      short loc_140007AD9
0x140007ad5  or      dword ptr [rbx+8], 2
0x140007ad9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140007ae0  lea     rax, WPP_GLOBAL_Control
0x140007ae7  cmp     rcx, rax
0x140007aea  jz      loc_140007BA3
0x140007af0  mov     eax, [rcx+2Ch]
0x140007af3  test    al, 40h
0x140007af5  jz      loc_140007BA3
0x140007afb  cmp     byte ptr [rcx+29h], 2
0x140007aff  jb      loc_140007BA3
0x140007b05  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140007b0c  nop     dword ptr [rax+rax+00h]
0x140007b11  lea     r9, aIs; "is"
0x140007b18  mov     qword ptr [rsp+0C0h+UserDataCount], rdi
0x140007b1d  movzx   ecx, byte ptr [rax+204h]
0x140007b24  lea     rax, aIsNot; "is not"
0x140007b2b  test    cl, cl
0x140007b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140007b34  cmovz   r9, rax
0x140007b38  mov     rcx, [rcx+18h]
0x140007b3c  call    WPP_SF_sq
0x140007b41  jmp     short loc_140007BA3
0x140007b43  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140007b4a  lea     rax, WPP_GLOBAL_Control
0x140007b51  cmp     rcx, rax
0x140007b54  jz      short loc_140007BA3
0x140007b56  mov     eax, [rcx+2Ch]
0x140007b59  test    al, 40h
0x140007b5b  jz      short loc_140007BA3
0x140007b5d  cmp     byte ptr [rcx+29h], 2
0x140007b61  jb      short loc_140007BA3
0x140007b63  mov     edx, 11h
0x140007b68  jmp     short loc_140007B90
0x140007b6a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140007b71  lea     rax, WPP_GLOBAL_Control
0x140007b78  cmp     rcx, rax
0x140007b7b  jz      short loc_140007BA3
0x140007b7d  mov     edx, [rcx+2Ch]
0x140007b80  test    dl, 40h
0x140007b83  jz      short loc_140007BA3
0x140007b85  cmp     byte ptr [rcx+29h], 2
0x140007b89  jb      short loc_140007BA3
0x140007b8b  mov     edx, 12h
0x140007b90  mov     rcx, [rcx+18h]
0x140007b94  lea     r8, WPP_ec883060206d3d6ef99cecbe53c54519_Traceguids
0x140007b9b  mov     r9, rdi
0x140007b9e  call    WPP_SF_q
0x140007ba3  mov     rbx, [rsp+0C0h+arg_10]
0x140007bab  mov     eax, esi
0x140007bad  mov     rcx, [rbp+57h+var_20]
0x140007bb1  xor     rcx, rsp; StackCookie
0x140007bb4  call    __security_check_cookie
0x140007bb9  add     rsp, 0B0h
0x140007bc0  pop     rdi
0x140007bc1  pop     rsi
0x140007bc2  pop     rbp
0x140007bc3  retn
```
