# CSyncMLMeta::StartElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,SyncMLElemType *,int *)

- ea: `0x18000fee0`
- end: `0x18001047e`
- name: `?StartElement@CSyncMLMeta@@QEAAJPEBGK0KW4SyncMLElemType@@PEAW42@PEAH@Z`
- size: `1438`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a0d0`
- `0x18000ec70`
- `0x18000f220`

## callees

- `0x1800043f0`
- `0x18000fee0`
- `0x1800110e4`
- `0x180014330`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001012d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800101cf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800102c9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010385`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010454`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001012d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800101cf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800102c9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010385`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010454`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010018`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800101ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010216`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800102e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010018`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800101ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010216`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800102e9`
- `DMCmnUtils!InvStrCmpNIW` at `0x18000ffe4`
- `DMCmnUtils!InvStrCmpNIW` at `0x18000ffe4`

## pseudocode

```c
__int64 __fastcall CSyncMLMeta::StartElement(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        __int64 a7)
{
  __int64 v7; // rdi
  int v8; // ebx
  const unsigned __int16 *v9; // r14
  int v10; // r15d
  unsigned __int64 v11; // rdi
  _WORD *v12; // rax
  __int64 v13; // rcx
  unsigned int v14; // ebx
  const OLECHAR *v15; // rcx
  __int64 v16; // rax
  int v18; // eax
  HLOCAL v19; // rcx
  HLOCAL v20; // rcx
  __int64 v22; // [rsp+48h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B8h] BYREF
  EVENT_DESCRIPTOR v24; // [rsp+58h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+68h] [rbp-A0h] BYREF
  int *v26; // [rsp+78h] [rbp-90h]
  int v27; // [rsp+80h] [rbp-88h]
  int v28; // [rsp+84h] [rbp-84h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+88h] [rbp-80h] BYREF
  char *v30; // [rsp+98h] [rbp-70h]
  int v31; // [rsp+A0h] [rbp-68h]
  int v32; // [rsp+A4h] [rbp-64h]
  EVENT_DESCRIPTOR *v33; // [rsp+A8h] [rbp-60h]
  __int64 v34; // [rsp+B0h] [rbp-58h]
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+B8h] [rbp-50h] BYREF
  void *v36; // [rsp+C8h] [rbp-40h]
  int v37; // [rsp+D0h] [rbp-38h]
  int v38; // [rsp+D4h] [rbp-34h]
  __int64 *v39; // [rsp+D8h] [rbp-30h]
  __int64 v40; // [rsp+E0h] [rbp-28h]
  const OLECHAR *v41; // [rsp+E8h] [rbp-20h]
  int v42; // [rsp+F0h] [rbp-18h]
  int v43; // [rsp+F4h] [rbp-14h]

  *(_QWORD *)&EventDescriptor.Id = a1;
  v7 = a1;
  *(_QWORD *)&v24.Id = a7;
  hMem = 0;
  LODWORD(v22) = 0;
  v8 = CanonicalizeTag(a4, a5, a2, a3, a6, (unsigned __int16 **)&hMem, (unsigned int *)&v22);
  if ( v8 < 0 )
  {
    v20 = hMem;
    goto LABEL_33;
  }
  v9 = (const unsigned __int16 *)hMem;
  if ( !hMem || !*(_WORD *)hMem )
  {
    v8 = -2147024809;
    v20 = hMem;
LABEL_33:
    LocalFree(v20);
    goto LABEL_34;
  }
  v10 = v22;
  v11 = (unsigned int)v22;
  if ( (unsigned int)v22 == 0xFFFFFFFFLL )
  {
    v12 = hMem;
    v13 = 0x7FFFFFFF;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v13;
    }
    while ( v13 );
    v11 = 0x7FFFFFFF - v13;
    if ( !v13 )
    {
LABEL_16:
      if ( (unsigned int)dword_18003E048 > 5 )
      {
        v15 = (const OLECHAR *)hMem;
        LODWORD(v22) = v10;
        if ( hMem )
        {
          v16 = -1;
          while ( *((_WORD *)hMem + ++v16) != 0 )
            ;
          v18 = 2 * v16 + 2;
        }
        else
        {
          v15 = &word_180032B28;
          v18 = 2;
        }
        v42 = v18;
        v41 = v15;
        v39 = &v22;
        v35.Ptr = (ULONGLONG)off_18003E050;
        v43 = 0;
        v40 = 4;
        UserData.Ptr = 0x50B000000LL;
        *(_QWORD *)&UserData.Size = 0;
        v35.Size = (unsigned __int16)*off_18003E050;
        v36 = &unk_180037460;
        v35.Reserved = 2;
        v37 = 46;
        v38 = 1;
        *(_DWORD *)&v24.Id = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 4u, &v35);
      }
      goto LABEL_27;
    }
  }
  v14 = 0;
  while ( InvStrCmpNIW(v9, (&c_rgszSyncMLElem)[v14], v11) || (&c_rgszSyncMLElem)[v14][v11] )
  {
    if ( (int)++v14 >= 73 )
      goto LABEL_16;
  }
  if ( v14 == 23 )
    goto LABEL_28;
  if ( a6 == 23 )
  {
    if ( (unsigned int)CSyncMLMeta::SyncMLElemToPropIndex(v14) == -1 )
    {
      if ( v14 - 41 > 0x18 )
      {
        if ( (unsigned int)dword_18003E048 > 2 )
        {
          *(_DWORD *)&v24.Level = 2;
          UserData.Ptr = (ULONGLONG)off_18003E050;
          *(_DWORD *)&v24.Id = 184549376;
          v24.Keyword = 0;
          UserData.Size = (unsigned __int16)*off_18003E050;
          v26 = &dword_18003733C;
          UserData.Reserved = 2;
          v27 = 19;
          v28 = 1;
          LODWORD(v22) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &v24, 0, 0, 2u, &UserData);
        }
        goto LABEL_27;
      }
      if ( (unsigned int)dword_18003E048 > 5 )
      {
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = (ULONGLONG)off_18003E050;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = (unsigned __int16)*off_18003E050;
        v26 = &dword_1800373A4;
        UserData.Reserved = 2;
        v27 = 24;
        v28 = 1;
        LODWORD(v22) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
      }
    }
LABEL_28:
    v19 = hMem;
    **(_DWORD **)&v24.Id = v14;
    LocalFree(v19);
    v8 = 0;
    goto LABEL_38;
  }
LABEL_27:
  v8 = -2102788095;
  LocalFree(hMem);
  v7 = *(_QWORD *)&EventDescriptor.Id;
LABEL_34:
  if ( (unsigned int)dword_18003E048 > 2 )
  {
    *(_QWORD *)&EventDescriptor.Id = off_18003E050;
    UserData.Ptr = 0x20B000000LL;
    *(_QWORD *)&UserData.Size = 0;
    EventDescriptor.Keyword = (unsigned __int16)*off_18003E050 | 0x200000000LL;
    v30 = byte_1800373F5;
    v31 = 27;
    v32 = 1;
    *(_DWORD *)&v24.Id = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)&EventDescriptor);
  }
  if ( *(int *)(v7 + 132) >= 0 )
    *(_DWORD *)(v7 + 132) = v8;
LABEL_38:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    *(_DWORD *)&v24.Id = v8;
    v33 = &v24;
    *(_QWORD *)&EventDescriptor.Id = off_18003E050;
    v34 = 4;
    UserData.Ptr = 0x50B000000LL;
    *(_QWORD *)&UserData.Size = 0;
    EventDescriptor.Keyword = (unsigned __int16)*off_18003E050 | 0x200000000LL;
    v30 = &byte_18003737F;
    v31 = 25;
    v32 = 1;
    LODWORD(v22) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 3u, (PEVENT_DATA_DESCRIPTOR)&EventDescriptor);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000fee0  mov     r11, rsp
0x18000fee3  push    rbp
0x18000fee4  push    rbx
0x18000fee5  push    rsi
0x18000fee6  push    r12
0x18000fee8  push    r14
0x18000feea  lea     rbp, [r11-48h]
0x18000feee  sub     rsp, 120h
0x18000fef5  mov     rax, cs:__security_cookie
0x18000fefc  xor     rax, rsp
0x18000feff  mov     [rbp+40h+var_50], rax
0x18000ff03  mov     qword ptr [rbp+40h+EventDescriptor.Id], rcx
0x18000ff07  mov     rax, r9
0x18000ff0a  mov     [r11-30h], rdi
0x18000ff0e  mov     r9d, r8d
0x18000ff11  mov     rdi, rcx
0x18000ff14  mov     [r11-38h], r13
0x18000ff18  mov     rcx, [rbp+40h+arg_30]
0x18000ff1f  xor     esi, esi
0x18000ff21  mov     r13d, [rbp+40h+arg_28]
0x18000ff25  mov     r8, rdx
0x18000ff28  mov     edx, [rbp+40h+arg_20]
0x18000ff2b  mov     qword ptr [rsp+140h+var_F0.Id], rcx
0x18000ff30  lea     rcx, [rsp+140h+var_100]
0x18000ff35  mov     [rsp+30h], rcx
0x18000ff3a  lea     rcx, [rsp+140h+hMem]
0x18000ff3f  mov     [rsp+140h+UserData], rcx
0x18000ff44  mov     rcx, rax
0x18000ff47  mov     [r11-40h], r15
0x18000ff4b  mov     [rsp+140h+hMem], rsi
0x18000ff50  mov     dword ptr [rsp+140h+var_100], esi
0x18000ff54  mov     [rsp+140h+UserDataCount], r13d
0x18000ff59  call    ?CanonicalizeTag@@YAJPEBGK0KW4SyncMLElemType@@PEAPEAGPEAK@Z; CanonicalizeTag(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,ushort * *,ulong *)
0x18000ff5e  lea     r12, _TraceLoggingMetadataEnd
0x18000ff65  mov     ebx, eax
0x18000ff67  lea     rdx, _TraceLoggingMetadata
0x18000ff6e  test    eax, eax
0x18000ff70  js      loc_1800102E4
0x18000ff76  mov     r14, [rsp+140h+hMem]
0x18000ff7b  test    r14, r14
0x18000ff7e  jz      loc_1800102DA
0x18000ff84  cmp     si, [r14]
0x18000ff88  jz      loc_1800102DA
0x18000ff8e  mov     r15d, dword ptr [rsp+140h+var_100]
0x18000ff93  mov     eax, 0FFFFFFFFh
0x18000ff98  mov     edi, r15d
0x18000ff9b  cmp     r15, rax
0x18000ff9e  jnz     short loc_18000FFCB
0x18000ffa0  mov     edi, 7FFFFFFFh
0x18000ffa5  mov     rax, r14
0x18000ffa8  mov     ecx, edi
0x18000ffaa  nop     word ptr [rax+rax+00h]
0x18000ffb0  cmp     [rax], si
0x18000ffb3  jz      short loc_18000FFBF
0x18000ffb5  add     rax, 2
0x18000ffb9  sub     rcx, 1
0x18000ffbd  jnz     short loc_18000FFB0
0x18000ffbf  sub     rdi, rcx
0x18000ffc2  test    rcx, rcx
0x18000ffc5  cmovz   rdi, rsi
0x18000ffc9  jz      short loc_18001003D
0x18000ffcb  mov     ebx, esi
0x18000ffcd  mov     eax, ebx
0x18000ffcf  lea     rcx, ?c_rgszSyncMLElem@@3PAPEBGA; ushort const * near * c_rgszSyncMLElem
0x18000ffd6  mov     rdx, [rcx+rax*8]
0x18000ffda  lea     rsi, [rcx+rax*8]
0x18000ffde  mov     r8, rdi
0x18000ffe1  mov     rcx, r14
0x18000ffe4  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x18000ffeb  nop     dword ptr [rax+rax+00h]
0x18000fff0  test    eax, eax
0x18000fff2  jnz     short loc_18001002D
0x18000fff4  mov     rcx, [rsi]
0x18000fff7  xor     esi, esi
0x18000fff9  cmp     si, [rcx+rdi*2]
0x18000fffd  jnz     short loc_18001002F
0x18000ffff  cmp     ebx, 17h
0x180010002  jz      loc_180010203
0x180010008  cmp     r13d, 17h
0x18001000c  jz      short loc_18001007A
0x18001000e  mov     rcx, [rsp+140h+hMem]; hMem
0x180010013  mov     ebx, 82AA0001h
0x180010018  call    cs:__imp_LocalFree
0x18001001f  nop     dword ptr [rax+rax+00h]
0x180010024  mov     rdi, qword ptr [rbp+40h+EventDescriptor.Id]
0x180010028  jmp     loc_1800102F5
0x18001002d  xor     esi, esi
0x18001002f  inc     ebx
0x180010031  cmp     ebx, 49h ; 'I'
0x180010034  jl      short loc_18000FFCD
0x180010036  lea     rdx, _TraceLoggingMetadata
0x18001003d  mov     eax, cs:dword_18003E048
0x180010043  cmp     eax, 5
0x180010046  jbe     short loc_18001000E
0x180010048  mov     rcx, [rsp+140h+hMem]
0x18001004d  mov     dword ptr [rsp+140h+var_100], r15d
0x180010052  test    rcx, rcx
0x180010055  jz      loc_180010229
0x18001005b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180010062  cmp     word ptr [rcx+rax*2+2], 0
0x180010068  lea     rax, [rax+1]
0x18001006c  jnz     short loc_180010062
0x18001006e  lea     eax, ds:2[rax*2]
0x180010075  jmp     loc_180010235
0x18001007a  mov     ecx, ebx
0x18001007c  call    ?SyncMLElemToPropIndex@CSyncMLMeta@@CAKW4SyncMLElemType@@@Z; CSyncMLMeta::SyncMLElemToPropIndex(SyncMLElemType)
0x180010081  mov     ecx, 0FFFFFFFFh
0x180010086  cmp     eax, ecx
0x180010088  jnz     loc_180010203
0x18001008e  lea     eax, [rbx-29h]
0x180010091  cmp     eax, 18h
0x180010094  mov     eax, cs:dword_18003E048
0x18001009a  ja      loc_18001013E
0x1800100a0  cmp     eax, 5
0x1800100a3  jbe     loc_180010203
0x1800100a9  movzx   eax, cs:word_18003739A
0x1800100b0  lea     r14, _TraceLoggingMetadata
0x1800100b7  mov     dword ptr [rbp+40h+EventDescriptor.Level], eax
0x1800100ba  lea     rdx, [rbp+40h+EventDescriptor]; EventDescriptor
0x1800100be  mov     rax, cs:off_18003E050
0x1800100c5  xor     r9d, r9d; RelatedActivityId
0x1800100c8  mov     [rsp+140h+var_E0.Ptr], rax
0x1800100cd  xor     r8d, r8d; ActivityId
0x1800100d0  mov     dword ptr [rbp+40h+EventDescriptor.Id], 0B000000h
0x1800100d7  mov     [rbp+40h+EventDescriptor.Keyword], rsi
0x1800100db  movzx   eax, word ptr [rax]
0x1800100de  mov     [rsp+140h+var_E0.Size], eax
0x1800100e2  lea     rax, dword_1800373A4
0x1800100e9  mov     qword ptr [rsp+140h+var_D0], rax
0x1800100ee  mov     rax, r12
0x1800100f1  sub     eax, r14d
0x1800100f4  mov     dword ptr [rsp+140h+var_E0.0Ch], 2
0x1800100fc  mov     [rsp+140h+var_C8], 18h
0x180010104  mov     [rsp+140h+var_C4], 1
0x18001010c  mov     dword ptr [rsp+140h+var_100], eax
0x180010110  mov     eax, dword ptr [rsp+140h+var_100]
0x180010114  mov     rcx, cs:RegHandle; RegHandle
0x18001011b  lea     rax, [rsp+140h+var_E0]
0x180010120  mov     [rsp+140h+UserData], rax; UserData
0x180010125  mov     [rsp+140h+UserDataCount], 2; UserDataCount
0x18001012d  call    cs:__imp_EventWriteTransfer
0x180010134  nop     dword ptr [rax+rax+00h]
0x180010139  jmp     loc_18001020A
0x18001013e  cmp     eax, 2
0x180010141  jbe     loc_1800101DD
0x180010147  movzx   eax, cs:word_180037332
0x18001014e  lea     r14, _TraceLoggingMetadata
0x180010155  mov     dword ptr [rsp+140h+var_F0.Level], eax
0x180010159  lea     rdx, [rsp+140h+var_F0]; EventDescriptor
0x18001015e  mov     rax, cs:off_18003E050
0x180010165  xor     r9d, r9d; RelatedActivityId
0x180010168  mov     [rsp+140h+var_E0.Ptr], rax
0x18001016d  xor     r8d, r8d; ActivityId
0x180010170  mov     dword ptr [rsp+140h+var_F0.Id], 0B000000h
0x180010178  mov     [rsp+140h+var_F0.Keyword], rsi
0x18001017d  movzx   eax, word ptr [rax]
0x180010180  mov     [rsp+140h+var_E0.Size], eax
0x180010184  lea     rax, dword_18003733C
0x18001018b  mov     qword ptr [rsp+140h+var_D0], rax
0x180010190  mov     rax, r12
0x180010193  sub     eax, r14d
0x180010196  mov     dword ptr [rsp+140h+var_E0.0Ch], 2
0x18001019e  mov     [rsp+140h+var_C8], 13h
0x1800101a6  mov     [rsp+140h+var_C4], 1
0x1800101ae  mov     dword ptr [rsp+140h+var_100], eax
0x1800101b2  mov     eax, dword ptr [rsp+140h+var_100]
0x1800101b6  mov     rcx, cs:RegHandle; RegHandle
0x1800101bd  lea     rax, [rsp+140h+var_E0]
0x1800101c2  mov     [rsp+140h+UserData], rax; UserData
0x1800101c7  mov     [rsp+140h+UserDataCount], 2; UserDataCount
0x1800101cf  call    cs:__imp_EventWriteTransfer
0x1800101d6  nop     dword ptr [rax+rax+00h]
0x1800101db  jmp     short loc_1800101E4
0x1800101dd  lea     r14, _TraceLoggingMetadata
0x1800101e4  mov     rcx, [rsp+140h+hMem]; hMem
0x1800101e9  mov     ebx, 82AA0001h
0x1800101ee  call    cs:__imp_LocalFree
0x1800101f5  nop     dword ptr [rax+rax+00h]
0x1800101fa  mov     rdi, qword ptr [rbp+40h+EventDescriptor.Id]
0x1800101fe  jmp     loc_1800102FC
0x180010203  lea     r14, _TraceLoggingMetadata
0x18001020a  mov     rax, qword ptr [rsp+140h+var_F0.Id]
0x18001020f  mov     rcx, [rsp+140h+hMem]; hMem
0x180010214  mov     [rax], ebx
0x180010216  call    cs:__imp_LocalFree
0x18001021d  nop     dword ptr [rax+rax+00h]
0x180010222  mov     ebx, esi
0x180010224  jmp     loc_1800103A0
0x180010229  lea     rcx, word_180032B28
0x180010230  mov     eax, 2
0x180010235  mov     [rbp+40h+var_58], eax
0x180010238  xor     r9d, r9d; RelatedActivityId
0x18001023b  mov     [rbp+40h+var_60], rcx
0x18001023f  lea     rax, [rsp+140h+var_100]
0x180010244  mov     [rbp+40h+var_70], rax
0x180010248  xor     r8d, r8d; ActivityId
0x18001024b  movzx   eax, cs:word_180037456
0x180010252  mov     dword ptr [rsp+140h+var_E0.Ptr+4], eax
0x180010256  mov     rax, cs:off_18003E050
0x18001025d  mov     [rbp+40h+var_90.Ptr], rax
0x180010261  mov     [rbp+40h+var_54], esi
0x180010264  mov     [rbp+40h+var_68], 4
0x18001026c  mov     dword ptr [rsp+140h+var_E0.Ptr], 0B000000h
0x180010274  mov     qword ptr [rsp+140h+var_E0.Size], rsi
0x180010279  movzx   eax, word ptr [rax]
0x18001027c  mov     [rbp+40h+var_90.Size], eax
0x18001027f  lea     rax, unk_180037460
0x180010286  mov     [rbp+40h+var_80], rax
0x18001028a  mov     rax, r12
0x18001028d  sub     eax, edx
0x18001028f  mov     dword ptr [rbp+40h+var_90.0Ch], 2
0x180010296  mov     [rbp+40h+var_78], 2Eh ; '.'
0x18001029d  lea     rdx, [rsp+140h+var_E0]; EventDescriptor
0x1800102a2  mov     [rbp+40h+var_74], 1
0x1800102a9  mov     dword ptr [rsp+140h+var_F0.Id], eax
0x1800102ad  mov     eax, dword ptr [rsp+140h+var_F0.Id]
0x1800102b1  mov     rcx, cs:RegHandle; RegHandle
0x1800102b8  lea     rax, [rbp+40h+var_90]
0x1800102bc  mov     [rsp+140h+UserData], rax; UserData
0x1800102c1  mov     [rsp+140h+UserDataCount], 4; UserDataCount
0x1800102c9  call    cs:__imp_EventWriteTransfer
0x1800102d0  nop     dword ptr [rax+rax+00h]
0x1800102d5  jmp     loc_18001000E
0x1800102da  mov     ebx, 80070057h
0x1800102df  mov     rcx, r14
0x1800102e2  jmp     short loc_1800102E9
0x1800102e4  mov     rcx, [rsp+140h+hMem]; hMem
0x1800102e9  call    cs:__imp_LocalFree
0x1800102f0  nop     dword ptr [rax+rax+00h]
0x1800102f5  lea     r14, _TraceLoggingMetadata
0x1800102fc  mov     eax, cs:dword_18003E048
0x180010302  cmp     eax, 2
0x180010305  jbe     loc_180010391
0x18001030b  movzx   eax, cs:word_1800373EB
0x180010312  lea     rdx, [rsp+140h+var_E0]; EventDescriptor
0x180010317  mov     dword ptr [rsp+140h+var_E0.Ptr+4], eax
0x18001031b  xor     r9d, r9d; RelatedActivityId
0x18001031e  mov     rax, cs:off_18003E050
0x180010325  xor     r8d, r8d; ActivityId
0x180010328  mov     qword ptr [rbp+40h+EventDescriptor.Id], rax
0x18001032c  mov     dword ptr [rsp+140h+var_E0.Ptr], 0B000000h
0x180010334  mov     qword ptr [rsp+140h+var_E0.Size], rsi
0x180010339  movzx   eax, word ptr [rax]
0x18001033c  mov     dword ptr [rbp+40h+EventDescriptor.Keyword], eax
0x18001033f  lea     rax, byte_1800373F5
0x180010346  mov     [rbp+40h+var_B0], rax
0x18001034a  mov     rax, r12
0x18001034d  sub     eax, r14d
0x180010350  mov     dword ptr [rbp+40h+EventDescriptor.Keyword+4], 2
0x180010357  mov     [rbp+40h+var_A8], 1Bh
0x18001035e  mov     [rbp+40h+var_A4], 1
0x180010365  mov     dword ptr [rsp+140h+var_F0.Id], eax
0x180010369  mov     eax, dword ptr [rsp+140h+var_F0.Id]
0x18001036d  mov     rcx, cs:RegHandle; RegHandle
0x180010374  lea     rax, [rbp+40h+EventDescriptor]
0x180010378  mov     [rsp+140h+UserData], rax; UserData
0x18001037d  mov     [rsp+140h+UserDataCount], 2; UserDataCount
0x180010385  call    cs:__imp_EventWriteTransfer
0x18001038c  nop     dword ptr [rax+rax+00h]
0x180010391  cmp     dword ptr [rdi+84h], 0
0x180010398  jl      short loc_1800103A0
0x18001039a  mov     [rdi+84h], ebx
0x1800103a0  mov     eax, cs:dword_18003E048
0x1800103a6  mov     r15, [rsp+140h+var_38]
0x1800103ae  mov     r13, [rsp+140h+var_30]
0x1800103b6  mov     rdi, [rsp+118h]
0x1800103be  cmp     eax, 5
0x1800103c1  jbe     loc_180010460
0x1800103c7  lea     rax, [rsp+140h+var_F0]
0x1800103cc  mov     dword ptr [rsp+140h+var_F0.Id], ebx
0x1800103d0  mov     [rbp+40h+var_A0], rax
0x1800103d4  lea     rdx, [rsp+140h+var_E0]; EventDescriptor
0x1800103d9  movzx   eax, cs:word_180037375
0x1800103e0  sub     r12d, r14d
0x1800103e3  mov     dword ptr [rsp+140h+var_E0.Ptr+4], eax
0x1800103e7  xor     r9d, r9d; RelatedActivityId
0x1800103ea  mov     rax, cs:off_18003E050
0x1800103f1  xor     r8d, r8d; ActivityId
0x1800103f4  mov     qword ptr [rbp+40h+EventDescriptor.Id], rax
0x1800103f8  mov     [rbp+40h+var_98], 4
0x180010400  mov     dword ptr [rsp+140h+var_E0.Ptr], 0B000000h
0x180010408  mov     qword ptr [rsp+140h+var_E0.Size], rsi
0x18001040d  movzx   eax, word ptr [rax]
0x180010410  mov     dword ptr [rbp+40h+EventDescriptor.Keyword], eax
0x180010413  lea     rax, byte_18003737F
0x18001041a  mov     [rbp+40h+var_B0], rax
0x18001041e  mov     dword ptr [rbp+40h+EventDescriptor.Keyword+4], 2
0x180010425  mov     [rbp+40h+var_A8], 19h
0x18001042c  mov     [rbp+40h+var_A4], 1
0x180010433  mov     dword ptr [rsp+140h+var_100], r12d
0x180010438  mov     eax, dword ptr [rsp+140h+var_100]
0x18001043c  mov     rcx, cs:RegHandle; RegHandle
0x180010443  lea     rax, [rbp+40h+EventDescriptor]
0x180010447  mov     [rsp+140h+UserData], rax; UserData
0x18001044c  mov     [rsp+140h+UserDataCount], 3; UserDataCount
0x180010454  call    cs:__imp_EventWriteTransfer
0x18001045b  nop     dword ptr [rax+rax+00h]
0x180010460  mov     eax, ebx
0x180010462  mov     rcx, [rbp+40h+var_50]
0x180010466  xor     rcx, rsp; StackCookie
  ... truncated ...
```
