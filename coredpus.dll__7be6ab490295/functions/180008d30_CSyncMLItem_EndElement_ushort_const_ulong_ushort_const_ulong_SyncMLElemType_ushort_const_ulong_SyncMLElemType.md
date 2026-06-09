# CSyncMLItem::EndElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,ushort const *,ulong,SyncMLElemType *)

- ea: `0x180008d30`
- end: `0x180009377`
- name: `?EndElement@CSyncMLItem@@QEAAJPEBGK0KW4SyncMLElemType@@0KPEAW42@@Z`
- size: `1607`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d510`

## callees

- `0x180008d30`
- `0x180009760`
- `0x180014330`
- `0x180021ae0`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000907e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800091ed`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800092b6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000935c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000907e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800091ed`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800092b6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000935c`
- `DMCmnUtils!InvStrCmpNIW` at `0x180008e44`
- `DMCmnUtils!InvStrCmpNIW` at `0x180008e44`
- `DMCmnUtils!CopyString` at `0x180008f6b`
- `DMCmnUtils!CopyString` at `0x180008f6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSyncMLItem::EndElement(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        unsigned __int16 *a7,
        unsigned int a8,
        _DWORD *a9)
{
  int v11; // ebx
  unsigned __int64 v12; // rbx
  __int64 v13; // rcx
  const unsigned __int16 *v14; // rax
  __int64 v15; // rdi
  const unsigned __int16 **v16; // r15
  enum ListType *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  _DWORD *v20; // rdi
  int v21; // esi
  enum SyncMLProp *v23; // r9
  __int64 v24; // r8
  __int64 v25; // rcx
  int v26; // edx
  unsigned int v27; // [rsp+50h] [rbp-91h] BYREF
  EVENT_DESCRIPTOR v28; // [rsp+58h] [rbp-89h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-79h] BYREF
  char *v30; // [rsp+78h] [rbp-69h]
  int v31; // [rsp+80h] [rbp-61h]
  int v32; // [rsp+84h] [rbp-5Dh]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-51h] BYREF
  char *v34; // [rsp+A0h] [rbp-41h]
  int v35; // [rsp+A8h] [rbp-39h]
  int v36; // [rsp+ACh] [rbp-35h]
  EVENT_DESCRIPTOR *v37; // [rsp+B0h] [rbp-31h]
  __int64 v38; // [rsp+B8h] [rbp-29h]
  const unsigned __int16 *v39; // [rsp+C0h] [rbp-21h]
  int v40; // [rsp+C8h] [rbp-19h]
  int v41; // [rsp+CCh] [rbp-15h]

  *(_QWORD *)&v28.Id = a9;
  if ( (*(_DWORD *)(a1 + 24) & 1) == 0 )
  {
    if ( !a4 || !*a4 )
    {
      v11 = -2147024809;
      goto LABEL_53;
    }
    v12 = a5;
    if ( a5 != 0xFFFFFFFFLL )
      goto LABEL_12;
    v13 = 0x7FFFFFFF;
    v14 = a4;
    do
    {
      if ( !*v14 )
        break;
      ++v14;
      --v13;
    }
    while ( v13 );
    v12 = 0x7FFFFFFF - v13;
    if ( !v13 )
    {
LABEL_16:
      if ( (unsigned int)dword_18003E048 > 2 )
      {
        v27 = a5;
        v18 = -1;
        do
          ++v18;
        while ( a4[v18] );
        v39 = a4;
        v40 = 2 * v18 + 2;
        v41 = 0;
        v37 = (EVENT_DESCRIPTOR *)&v27;
        v38 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 2;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_18003E050;
        UserData.Size = (unsigned __int16)*off_18003E050;
        UserData.Reserved = 2;
        v34 = (char *)&unk_180036320;
        v35 = 50;
        v36 = 1;
        *(_DWORD *)&v28.Id = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
      }
    }
    else
    {
LABEL_12:
      v15 = 0;
      while ( 1 )
      {
        v16 = (const unsigned __int16 **)&(&c_rgszSyncMLElem)[v15];
        LODWORD(v17) = InvStrCmpNIW(a4, *v16, v12);
        if ( !(_DWORD)v17 && !(*v16)[v12] )
          break;
        v15 = (unsigned int)(v15 + 1);
        if ( (int)v15 >= 73 )
          goto LABEL_16;
      }
      v11 = 0;
      switch ( (_DWORD)v15 )
      {
        case 0x16:
          goto LABEL_27;
        case 0xA:
          if ( a7 && a8 )
          {
            if ( a6 == 15 )
            {
              v23 = 0;
            }
            else
            {
              v23 = (enum SyncMLProp *)(a1 + 100);
              v17 = (enum ListType *)(a1 + 104);
            }
            v24 = 64;
            if ( a6 != 15 )
              v24 = 72;
            v11 = CSyncMLItem::ParseLocURI(a7, a8, (struct IConfigManager2URI **)(a1 + v24), v23, v17);
            if ( v11 < 0 )
              goto LABEL_53;
            v25 = a1 + 8;
            if ( *(_DWORD *)(a1 + 100) == 15 || (v26 = *(_DWORD *)(*(_QWORD *)v25 + 92LL), v26 == 32) || v26 == 36 )
            {
              if ( *(_DWORD *)(a1 + 104) == 2 || *(_DWORD *)(*(_QWORD *)v25 + 92LL) == 32 )
                goto LABEL_27;
            }
          }
          else if ( (unsigned int)dword_18003E048 > 2 )
          {
            *(_DWORD *)&v28.Id = 184549376;
            *(_DWORD *)&v28.Level = 2;
            v28.Keyword = 0;
            *(_QWORD *)&EventDescriptor.Id = off_18003E050;
            EventDescriptor.Keyword = (unsigned __int16)*off_18003E050 | 0x200000000LL;
            v30 = byte_1800363B3;
            v31 = 15;
            v32 = 1;
            v27 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &v28, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)&EventDescriptor);
          }
          break;
        case 0xF:
          *(_DWORD *)(a1 + 24) &= ~2u;
          goto LABEL_27;
        case 0x11:
          *(_DWORD *)(a1 + 24) &= ~4u;
          goto LABEL_27;
        case 0x15:
          v11 = CopyString(a7, a8, (unsigned __int16 **)(a1 + 80));
          if ( v11 >= 0 )
          {
            --*(_DWORD *)(a1 + 112);
LABEL_27:
            **(_DWORD **)&v28.Id = v15;
            goto LABEL_28;
          }
LABEL_53:
          if ( (unsigned int)dword_18003E048 > 2 )
          {
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            *(_DWORD *)&EventDescriptor.Level = 2;
            EventDescriptor.Keyword = 0;
            UserData.Ptr = (ULONGLONG)off_18003E050;
            UserData.Size = (unsigned __int16)*off_18003E050;
            UserData.Reserved = 2;
            v34 = &byte_1800364E7;
            v35 = 27;
            v36 = 1;
            *(_DWORD *)&v28.Id = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
          }
          if ( *(int *)(a1 + 88) >= 0 )
            *(_DWORD *)(a1 + 88) = v11;
          goto LABEL_57;
      }
    }
    v11 = -2102788095;
    goto LABEL_53;
  }
  v11 = CSyncMLMeta::EndElement(*(_QWORD *)(a1 + 16), a2, a3, a4, a5, a6, a7, a8, (__int64)a9);
  if ( v11 >= 0 )
  {
    if ( *a9 == 23 )
      *(_DWORD *)(a1 + 24) &= ~1u;
    goto LABEL_28;
  }
LABEL_57:
  if ( (unsigned int)dword_18003E048 > 2 )
  {
    *(_DWORD *)&v28.Id = v11;
    v37 = &v28;
    v38 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    UserData.Size = (unsigned __int16)*off_18003E050;
    UserData.Reserved = 2;
    v34 = byte_18003646B;
    v35 = 36;
    v36 = 1;
    v27 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
LABEL_28:
  v19 = *(_QWORD *)(a1 + 8);
  v20 = *(_DWORD **)(v19 + 80);
  if ( v20 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v20 + 8LL))(*(_QWORD *)(v19 + 80));
  v21 = v20[7];
  if ( v20 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v20 + 16LL))(v20);
  if ( !v21 )
    v11 = 0;
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    *(_DWORD *)&v28.Id = v11;
    v37 = &v28;
    v38 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    UserData.Size = (unsigned __int16)*off_18003E050;
    UserData.Reserved = 2;
    v34 = byte_1800362FD;
    v35 = 23;
    v36 = 1;
    v27 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180008d30  push    rbp
0x180008d32  push    rbx
0x180008d33  push    rsi
0x180008d34  push    rdi
0x180008d35  push    r12
0x180008d37  push    r13
0x180008d39  push    r14
0x180008d3b  push    r15
0x180008d3d  lea     rbp, [rsp-7]
0x180008d42  sub     rsp, 0E8h
0x180008d49  mov     rax, cs:__security_cookie
0x180008d50  xor     rax, rsp
0x180008d53  mov     [rbp+3Fh+var_50], rax
0x180008d57  mov     r14, r9
0x180008d5a  mov     rsi, rcx
0x180008d5d  mov     r13, [rbp+3Fh+arg_30]
0x180008d61  mov     rdi, [rbp+3Fh+arg_40]
0x180008d68  mov     qword ptr [rsp+120h+var_C8.Id], rdi
0x180008d6d  mov     eax, [rcx+18h]
0x180008d70  lea     r9, _TraceLoggingMetadataEnd
0x180008d77  lea     r10, _TraceLoggingMetadata
0x180008d7e  test    al, 1
0x180008d80  jz      short loc_180008DDA
0x180008d82  mov     [rsp+120h+var_E0], rdi
0x180008d87  mov     eax, [rbp+3Fh+arg_38]
0x180008d8d  mov     [rsp+120h+var_E8], eax
0x180008d91  mov     [rsp+120h+var_F0], r13
0x180008d96  mov     eax, [rbp+3Fh+arg_28]
0x180008d99  mov     dword ptr [rsp+120h+UserData], eax
0x180008d9d  mov     eax, [rbp+3Fh+arg_20]
0x180008da0  mov     [rsp+120h+UserDataCount], eax
0x180008da4  mov     r9, r14
0x180008da7  mov     rcx, [rcx+10h]
0x180008dab  call    ?EndElement@CSyncMLMeta@@QEAAJPEBGK0KW4SyncMLElemType@@0KPEAW42@@Z; CSyncMLMeta::EndElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,ushort const *,ulong,SyncMLElemType *)
0x180008db0  mov     ebx, eax
0x180008db2  test    eax, eax
0x180008db4  js      loc_18000920A
0x180008dba  lea     r14, _TraceLoggingMetadataEnd
0x180008dc1  lea     r15, _TraceLoggingMetadata
0x180008dc8  cmp     dword ptr [rdi], 17h
0x180008dcb  jnz     loc_180008FA6
0x180008dd1  and     dword ptr [rsi+18h], 0FFFFFFFEh
0x180008dd5  jmp     loc_180008FA6
0x180008dda  test    r14, r14
0x180008ddd  jz      loc_18000936D
0x180008de3  xor     eax, eax
0x180008de5  cmp     ax, [r14]
0x180008de9  jz      loc_18000936D
0x180008def  mov     r12d, [rbp+3Fh+arg_20]
0x180008df3  mov     ebx, r12d
0x180008df6  mov     eax, 0FFFFFFFFh
0x180008dfb  cmp     r12, rax
0x180008dfe  jnz     short loc_180008E2E
0x180008e00  mov     ebx, 7FFFFFFFh
0x180008e05  mov     ecx, ebx
0x180008e07  mov     rax, r14
0x180008e0a  nop     word ptr [rax+rax+00h]
0x180008e10  cmp     word ptr [rax], 0
0x180008e14  jz      short loc_180008E20
0x180008e16  add     rax, 2
0x180008e1a  sub     rcx, 1
0x180008e1e  jnz     short loc_180008E10
0x180008e20  sub     rbx, rcx
0x180008e23  xor     eax, eax
0x180008e25  test    rcx, rcx
0x180008e28  cmovz   rbx, rax
0x180008e2c  jz      short loc_180008E76
0x180008e2e  xor     edi, edi
0x180008e30  lea     rcx, ?c_rgszSyncMLElem@@3PAPEBGA; ushort const * near * c_rgszSyncMLElem
0x180008e37  lea     r15, [rcx+rdi*8]
0x180008e3b  mov     r8, rbx
0x180008e3e  mov     rdx, [r15]
0x180008e41  mov     rcx, r14
0x180008e44  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x180008e4b  nop     dword ptr [rax+rax+00h]
0x180008e50  test    eax, eax
0x180008e52  jnz     short loc_180008E61
0x180008e54  mov     rcx, [r15]
0x180008e57  cmp     ax, [rcx+rbx*2]
0x180008e5b  jz      loc_180008F33
0x180008e61  inc     edi
0x180008e63  cmp     edi, 49h ; 'I'
0x180008e66  jl      short loc_180008E30
0x180008e68  lea     r9, _TraceLoggingMetadataEnd
0x180008e6f  lea     r10, _TraceLoggingMetadata
0x180008e76  mov     eax, cs:dword_18003E048
0x180008e7c  cmp     eax, 2
0x180008e7f  jbe     loc_180009153
0x180008e85  mov     [rsp+120h+var_D0], r12d
0x180008e8a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008e91  lea     rax, [rax+1]
0x180008e95  cmp     word ptr [r14+rax*2], 0
0x180008e9b  jnz     short loc_180008E91
0x180008e9d  mov     [rbp+3Fh+var_60], r14
0x180008ea1  lea     eax, ds:2[rax*2]
0x180008ea8  mov     [rbp+3Fh+var_58], eax
0x180008eab  mov     [rbp+3Fh+var_54], 0
0x180008eb2  lea     rax, [rsp+120h+var_D0]
0x180008eb7  mov     [rbp+3Fh+var_70], rax
0x180008ebb  mov     [rbp+3Fh+var_68], 4
0x180008ec3  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], 0B000000h
0x180008eca  movzx   eax, cs:word_180036316
0x180008ed1  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x180008ed4  mov     [rbp+3Fh+EventDescriptor.Keyword], 0
0x180008edc  mov     rax, cs:off_18003E050
0x180008ee3  mov     [rbp+3Fh+var_90.Ptr], rax
0x180008ee7  movzx   eax, word ptr [rax]
0x180008eea  mov     [rbp+3Fh+var_90.Size], eax
0x180008eed  mov     dword ptr [rbp+3Fh+var_90.0Ch], 2
0x180008ef4  lea     rax, unk_180036320
0x180008efb  mov     [rbp+3Fh+var_80], rax
0x180008eff  mov     [rbp+3Fh+var_78], 32h ; '2'
0x180008f06  mov     [rbp+3Fh+var_74], 1
0x180008f0d  sub     r9d, r10d
0x180008f10  mov     dword ptr [rsp+120h+var_C8.Id], r9d
0x180008f15  mov     eax, dword ptr [rsp+120h+var_C8.Id]
0x180008f19  lea     rax, [rbp+3Fh+var_90]
0x180008f1d  mov     [rsp+120h+UserData], rax
0x180008f22  mov     [rsp+120h+UserDataCount], 4
0x180008f2a  lea     rdx, [rbp+3Fh+EventDescriptor]
0x180008f2e  jmp     loc_18000934F
0x180008f33  xor     ebx, ebx
0x180008f35  cmp     edi, 16h
0x180008f38  jz      short loc_180008F89
0x180008f3a  cmp     edi, 0Ah
0x180008f3d  jz      loc_1800090BF
0x180008f43  cmp     edi, 0Fh
0x180008f46  jz      loc_1800090B6
0x180008f4c  cmp     edi, 11h
0x180008f4f  jz      loc_1800090AD
0x180008f55  cmp     edi, 15h
0x180008f58  jnz     loc_180009153
0x180008f5e  lea     r8, [rsi+50h]
0x180008f62  mov     edx, [rbp+3Fh+arg_38]
0x180008f68  mov     rcx, r13
0x180008f6b  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180008f72  nop     dword ptr [rax+rax+00h]
0x180008f77  mov     ebx, eax
0x180008f79  test    eax, eax
0x180008f7b  js      loc_180009158
0x180008f81  mov     eax, 0FFFFFFFFh
0x180008f86  add     [rsi+70h], eax
0x180008f89  mov     rax, qword ptr [rsp+120h+var_C8.Id]
0x180008f8e  mov     [rax], edi
0x180008f90  test    ebx, ebx
0x180008f92  js      loc_180009158
0x180008f98  lea     r14, _TraceLoggingMetadataEnd
0x180008f9f  lea     r15, _TraceLoggingMetadata
0x180008fa6  mov     rax, [rsi+8]
0x180008faa  mov     rdi, [rax+50h]
0x180008fae  test    rdi, rdi
0x180008fb1  jz      short loc_180008FC3
0x180008fb3  mov     rax, [rdi]
0x180008fb6  mov     rcx, rdi
0x180008fb9  mov     rax, [rax+8]
0x180008fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fc2  nop
0x180008fc3  mov     esi, [rdi+1Ch]
0x180008fc6  test    rdi, rdi
0x180008fc9  jz      short loc_180008FDB
0x180008fcb  mov     rax, [rdi]
0x180008fce  mov     rcx, rdi
0x180008fd1  mov     rax, [rax+10h]
0x180008fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fda  nop
0x180008fdb  xor     eax, eax
0x180008fdd  test    esi, esi
0x180008fdf  cmovz   ebx, eax
0x180008fe2  mov     eax, cs:dword_18003E048
0x180008fe8  cmp     eax, 5
0x180008feb  jbe     loc_18000908A
0x180008ff1  mov     dword ptr [rsp+120h+var_C8.Id], ebx
0x180008ff5  lea     rax, [rsp+120h+var_C8]
0x180008ffa  mov     [rbp+3Fh+var_70], rax
0x180008ffe  mov     [rbp+3Fh+var_68], 4
0x180009006  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], 0B000000h
0x18000900d  movzx   eax, cs:word_1800362F3
0x180009014  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x180009017  mov     [rbp+3Fh+EventDescriptor.Keyword], 0
0x18000901f  mov     rax, cs:off_18003E050
0x180009026  mov     [rbp+3Fh+var_90.Ptr], rax
0x18000902a  movzx   eax, word ptr [rax]
0x18000902d  mov     [rbp+3Fh+var_90.Size], eax
0x180009030  mov     dword ptr [rbp+3Fh+var_90.0Ch], 2
0x180009037  lea     rax, byte_1800362FD
0x18000903e  mov     [rbp+3Fh+var_80], rax
0x180009042  mov     [rbp+3Fh+var_78], 17h
0x180009049  mov     [rbp+3Fh+var_74], 1
0x180009050  sub     r14d, r15d
0x180009053  mov     [rsp+120h+var_D0], r14d
0x180009058  mov     ecx, [rsp+120h+var_D0]
0x18000905c  lea     rax, [rbp+3Fh+var_90]
0x180009060  mov     [rsp+120h+UserData], rax; UserData
0x180009065  mov     [rsp+120h+UserDataCount], 3; UserDataCount
0x18000906d  xor     r9d, r9d; RelatedActivityId
0x180009070  xor     r8d, r8d; ActivityId
0x180009073  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x180009077  mov     rcx, cs:RegHandle; RegHandle
0x18000907e  call    cs:__imp_EventWriteTransfer
0x180009085  nop     dword ptr [rax+rax+00h]
0x18000908a  mov     eax, ebx
0x18000908c  mov     rcx, [rbp+3Fh+var_50]
0x180009090  xor     rcx, rsp; StackCookie
0x180009093  call    __security_check_cookie
0x180009098  add     rsp, 0E8h
0x18000909f  pop     r15
0x1800090a1  pop     r14
0x1800090a3  pop     r13
0x1800090a5  pop     r12
0x1800090a7  pop     rdi
0x1800090a8  pop     rsi
0x1800090a9  pop     rbx
0x1800090aa  pop     rbp
0x1800090ab  retn
0x1800090ad  and     dword ptr [rsi+18h], 0FFFFFFFBh
0x1800090b1  jmp     loc_180008F89
0x1800090b6  and     dword ptr [rsi+18h], 0FFFFFFFDh
0x1800090ba  jmp     loc_180008F89
0x1800090bf  test    r13, r13
0x1800090c2  jz      loc_1800092C7
0x1800090c8  mov     edx, [rbp+3Fh+arg_38]; unsigned int
0x1800090ce  test    edx, edx
0x1800090d0  jz      loc_1800092C7
0x1800090d6  mov     ecx, [rbp+3Fh+arg_28]
0x1800090d9  cmp     ecx, 0Fh
0x1800090dc  jnz     short loc_1800090EB
0x1800090de  xor     r9d, r9d
0x1800090e1  lea     r14, [rsi+64h]
0x1800090e5  lea     r15, [rsi+68h]
0x1800090e9  jmp     short loc_1800090F9
0x1800090eb  lea     r9, [rsi+64h]; enum SyncMLProp *
0x1800090ef  lea     rax, [rsi+68h]
0x1800090f3  mov     r14, r9
0x1800090f6  mov     r15, rax
0x1800090f9  mov     r8d, 40h ; '@'
0x1800090ff  mov     r10d, 48h ; 'H'
0x180009105  cmp     ecx, 0Fh
0x180009108  cmovnz  r8d, r10d
0x18000910c  add     r8, rsi; struct IConfigManager2URI **
0x18000910f  mov     qword ptr [rsp+120h+UserDataCount], rax; enum ListType *
0x180009114  mov     rcx, r13; unsigned __int16 *
0x180009117  call    ?ParseLocURI@CSyncMLItem@@CAJPEBGKPEAPEAUIConfigManager2URI@@PEAW4SyncMLProp@@PEAW4ListType@@@Z; CSyncMLItem::ParseLocURI(ushort const *,ulong,IConfigManager2URI * *,SyncMLProp *,ListType *)
0x18000911c  mov     ebx, eax
0x18000911e  test    eax, eax
0x180009120  js      short loc_180009158
0x180009122  lea     rcx, [rsi+8]
0x180009126  cmp     dword ptr [r14], 0Fh
0x18000912a  jz      short loc_18000913C
0x18000912c  mov     rax, [rcx]
0x18000912f  mov     edx, [rax+5Ch]
0x180009132  cmp     edx, 20h ; ' '
0x180009135  jz      short loc_18000913C
0x180009137  cmp     edx, 24h ; '$'
0x18000913a  jnz     short loc_180009153
0x18000913c  cmp     dword ptr [r15], 2
0x180009140  jz      loc_180008F89
0x180009146  mov     rax, [rcx]
0x180009149  cmp     dword ptr [rax+5Ch], 20h ; ' '
0x18000914d  jz      loc_180008F89
0x180009153  mov     ebx, 82AA0001h
0x180009158  lea     r10, _TraceLoggingMetadata
0x18000915f  lea     r9, _TraceLoggingMetadataEnd
0x180009166  mov     eax, cs:dword_18003E048
0x18000916c  cmp     eax, 2
0x18000916f  jbe     loc_1800091F9
0x180009175  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], 0B000000h
0x18000917c  movzx   eax, cs:word_1800364DD
0x180009183  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x180009186  mov     [rbp+3Fh+EventDescriptor.Keyword], 0
0x18000918e  mov     rax, cs:off_18003E050
0x180009195  mov     [rbp+3Fh+var_90.Ptr], rax
0x180009199  movzx   eax, word ptr [rax]
0x18000919c  mov     [rbp+3Fh+var_90.Size], eax
0x18000919f  mov     dword ptr [rbp+3Fh+var_90.0Ch], 2
0x1800091a6  lea     rax, byte_1800364E7
0x1800091ad  mov     [rbp+3Fh+var_80], rax
0x1800091b1  mov     [rbp+3Fh+var_78], 1Bh
0x1800091b8  mov     [rbp+3Fh+var_74], 1
0x1800091bf  sub     r9d, r10d
0x1800091c2  mov     dword ptr [rsp+120h+var_C8.Id], r9d
0x1800091c7  mov     eax, dword ptr [rsp+120h+var_C8.Id]
0x1800091cb  lea     rax, [rbp+3Fh+var_90]
0x1800091cf  mov     [rsp+120h+UserData], rax; UserData
0x1800091d4  mov     [rsp+120h+UserDataCount], 2; UserDataCount
0x1800091dc  xor     r9d, r9d; RelatedActivityId
0x1800091df  xor     r8d, r8d; ActivityId
0x1800091e2  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x1800091e6  mov     rcx, cs:RegHandle; RegHandle
0x1800091ed  call    cs:__imp_EventWriteTransfer
0x1800091f4  nop     dword ptr [rax+rax+00h]
0x1800091f9  cmp     dword ptr [rsi+58h], 0
0x1800091fd  jl      short loc_180009202
0x1800091ff  mov     [rsi+58h], ebx
0x180009202  test    ebx, ebx
0x180009204  jns     loc_180008F98
0x18000920a  mov     eax, cs:dword_18003E048
0x180009210  cmp     eax, 2
0x180009213  jbe     loc_180008F98
0x180009219  mov     dword ptr [rsp+120h+var_C8.Id], ebx
0x18000921d  lea     rax, [rsp+120h+var_C8]
  ... truncated ...
```
