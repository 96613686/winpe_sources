# CSyncMLCmd::StartElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,SyncMLElemType *,int *)

- ea: `0x18000f220`
- end: `0x18000fac9`
- name: `?StartElement@CSyncMLCmd@@QEAAJPEBGK0KW4SyncMLElemType@@PEAW42@PEAH@Z`
- size: `2217`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180008620`
- `0x18000f220`

## callees

- `0x180003380`
- `0x18000a0d0`
- `0x18000f220`
- `0x18000fee0`
- `0x180010e04`
- `0x180014330`
- `0x18001fa3c`
- `0x180020f24`
- `0x180021a68`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f3a5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f487`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f6af`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f8c9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f3a5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f487`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f6af`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f8c9`
- `DMCmnUtils!InvStrCmpNIW` at `0x18000f5a5`
- `DMCmnUtils!InvStrCmpNIW` at `0x18000f5a5`

## pseudocode

```c
__int64 __fastcall CSyncMLCmd::StartElement(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        _DWORD *a7,
        _DWORD *a8)
{
  __int64 v9; // r12
  int v11; // eax
  int started; // ebx
  __int64 v13; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned int v17; // edx
  unsigned __int64 v18; // rbx
  const unsigned __int16 *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // rax
  __int64 v24; // rcx
  int v25; // eax
  char *v26; // rax
  __int64 v27; // r8
  const unsigned __int16 *v28; // rdx
  _DWORD *v29; // [rsp+38h] [rbp-D0h]
  __int64 v30; // [rsp+40h] [rbp-C8h]
  int v31; // [rsp+58h] [rbp-B0h]
  unsigned int v32; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 v33; // [rsp+60h] [rbp-A8h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-A0h] BYREF
  const unsigned __int16 *v35; // [rsp+78h] [rbp-90h] BYREF
  _DWORD *v36; // [rsp+80h] [rbp-88h]
  __int64 v37; // [rsp+88h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+98h] [rbp-70h] BYREF
  char *v39; // [rsp+A8h] [rbp-60h]
  int v40; // [rsp+B0h] [rbp-58h]
  int v41; // [rsp+B4h] [rbp-54h]
  unsigned int *v42; // [rsp+B8h] [rbp-50h]
  __int64 v43; // [rsp+C0h] [rbp-48h]
  const unsigned __int16 *v44; // [rsp+C8h] [rbp-40h]
  int v45; // [rsp+D0h] [rbp-38h]
  int v46; // [rsp+D4h] [rbp-34h]

  v9 = 0;
  v31 = 0;
  v11 = *(_DWORD *)(a1 + 144);
  v36 = a7;
  v32 = a3;
  v35 = a2;
  *(_QWORD *)&EventDescriptor.Id = a8;
  v33 = 0;
  v37 = 0;
  if ( (v11 & 1) != 0 )
  {
    started = CSyncMLMeta::StartElement(*(_QWORD *)(a1 + 96), a2, a3, a4, a5, a6, (__int64)a7);
    if ( started < 0 )
    {
LABEL_3:
      v13 = 0;
      goto LABEL_4;
    }
LABEL_73:
    if ( !*(_QWORD *)(a1 + 128) )
    {
      if ( v9 )
      {
        *(_QWORD *)(a1 + 128) = v9;
        v13 = 0;
        LODWORD(v9) = v31;
        goto LABEL_4;
      }
LABEL_67:
      v13 = v33;
      LODWORD(v9) = v31;
      goto LABEL_4;
    }
LABEL_47:
    v13 = v33;
    LODWORD(v9) = v31;
    goto LABEL_4;
  }
  v15 = *(_QWORD *)(a1 + 120);
  if ( v15 )
  {
    started = CSyncMLItem::StartElement(v15, a2, a3, a4, a5, a6, a7, a8);
    if ( started < 0 )
      goto LABEL_3;
    goto LABEL_73;
  }
  v16 = *(_QWORD *)(a1 + 128);
  if ( v16 )
  {
    started = CSyncMLCmd::StartElement(v16, a2, a3, a4, a5, a6, a7, a8);
    if ( started < 0 )
      goto LABEL_3;
    if ( !*a8 )
      ++*(_DWORD *)(a1 + 148);
    goto LABEL_73;
  }
  LODWORD(v9) = 1;
  v31 = 1;
  if ( !a4 || !*a4 )
  {
    v13 = v33;
    started = -2147024809;
    goto LABEL_4;
  }
  v17 = a5;
  v18 = a5;
  if ( a5 == 0xFFFFFFFFLL )
  {
    v19 = a4;
    v20 = 0x7FFFFFFF;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v20;
    }
    while ( v20 );
    v18 = 0x7FFFFFFF - v20;
    if ( !v20 )
    {
LABEL_36:
      if ( (unsigned int)dword_18003E048 > 2 )
      {
        v32 = v17;
        v22 = -1;
        while ( a4[++v22] != 0 )
          ;
        v44 = a4;
        v45 = 2 * v22 + 2;
        v46 = 0;
        v42 = &v32;
        *(_DWORD *)&EventDescriptor.Level = 2;
        UserData.Ptr = (ULONGLONG)off_18003E050;
        v43 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = (unsigned __int16)*off_18003E050;
        v39 = byte_180036FB9;
        UserData.Reserved = 2;
        v40 = 50;
        v41 = 1;
        LODWORD(v35) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
      }
      started = -2102788095;
      if ( *(_DWORD *)(a1 + 92) != 73 || !(unsigned int)CSyncMLCmd::IsParentElementOfCmd(a6) )
        goto LABEL_47;
      LODWORD(v21) = 73;
      started = 0;
LABEL_43:
      if ( a6 > 0x27 || (v24 = 0x8010000004LL, !_bittest64(&v24, a6)) || a6 == (_DWORD)v21 )
      {
        started = -2102788095;
        goto LABEL_47;
      }
      goto LABEL_71;
    }
  }
  v21 = 0;
  while ( InvStrCmpNIW(a4, (&c_rgszSyncMLElem)[v21], v18) || (&c_rgszSyncMLElem)[v21][v18] )
  {
    v21 = (unsigned int)(v21 + 1);
    if ( (int)v21 >= 73 )
    {
      v17 = a5;
      goto LABEL_36;
    }
  }
  v25 = *(_DWORD *)(a1 + 92);
  started = 0;
  if ( (_DWORD)v21 == v25 )
    goto LABEL_43;
  if ( v25 != a6 )
    goto LABEL_83;
  switch ( (_DWORD)v21 )
  {
    case 5:
      v9 = 0;
      goto LABEL_72;
    case 0x16:
      if ( *(_QWORD *)(a1 + 120) )
      {
        if ( (unsigned int)dword_18003E048 > 2 )
        {
          *(_DWORD *)&EventDescriptor.Level = 2;
          UserData.Ptr = (ULONGLONG)off_18003E050;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0;
          UserData.Size = (unsigned __int16)*off_18003E050;
          v26 = byte_180036681;
          v40 = 27;
          goto LABEL_65;
        }
        goto LABEL_66;
      }
      *(_QWORD *)(a1 + 120) = 0;
      started = CSyncMLItem::CreateItem((struct CSyncMLItem **)(a1 + 120));
      if ( started < 0 )
        goto LABEL_47;
      v27 = v32;
      v28 = v35;
      v30 = *(_QWORD *)&EventDescriptor.Id;
      v29 = v36;
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = a1;
      v31 = 0;
      started = CSyncMLItem::StartElement(*(_QWORD *)(a1 + 120), v28, v27, a4, a5, a6, v29, v30);
      if ( started >= 0 )
        goto LABEL_71;
      goto LABEL_81;
    case 0x17:
      if ( *(_QWORD *)(a1 + 96) )
      {
        if ( (unsigned int)dword_18003E048 > 2 )
        {
          *(_DWORD *)&EventDescriptor.Level = 2;
          UserData.Ptr = (ULONGLONG)off_18003E050;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0;
          UserData.Size = (unsigned __int16)*off_18003E050;
          v26 = (char *)&unk_1800366A8;
          v40 = 23;
          goto LABEL_65;
        }
LABEL_66:
        started = -2102788095;
        goto LABEL_67;
      }
      started = CSyncMLMeta::CreateMeta((struct CSyncMLMeta **)(a1 + 96));
      if ( started < 0 )
        goto LABEL_47;
      v31 = 0;
      started = CSyncMLMeta::StartElement(*(_QWORD *)(a1 + 96), v35, v32, a4, a5, a6, (__int64)v36);
      if ( started >= 0 )
      {
        *(_DWORD *)(a1 + 144) |= 1u;
LABEL_71:
        v9 = v33;
LABEL_72:
        *v36 = v21;
        goto LABEL_73;
      }
LABEL_81:
      v13 = v33;
      LODWORD(v9) = v33;
      goto LABEL_4;
  }
  if ( !(unsigned int)CSyncMLCmd::IsCmdType((unsigned int)v21) )
  {
LABEL_83:
    started = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, const unsigned __int16 *, unsigned int, unsigned int, _DWORD *, _QWORD))(*(_QWORD *)a1 + 48LL))(
                a1,
                v35,
                v32,
                a4,
                a5,
                a6,
                v36,
                *(_QWORD *)&EventDescriptor.Id);
    if ( started < 0 )
      goto LABEL_47;
    goto LABEL_71;
  }
  if ( !*(_DWORD *)(a1 + 164) )
  {
    if ( (unsigned int)dword_18003E048 > 2 )
    {
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_18003E050;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = (unsigned __int16)*off_18003E050;
      v26 = (char *)&unk_1800369C8;
      v40 = 24;
LABEL_65:
      v39 = v26;
      UserData.Reserved = 2;
      v41 = 1;
      v32 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
      v13 = v33;
      started = -2102788095;
      LODWORD(v9) = 1;
      goto LABEL_4;
    }
    goto LABEL_66;
  }
  started = CSyncMLCmd::CreateCmd((unsigned int)v21, a1, *(_QWORD *)(a1 + 80), 0, 0, &v37);
  if ( started < 0 )
  {
    v13 = v37;
    LODWORD(v9) = 1;
    goto LABEL_4;
  }
  v9 = v37;
  v33 = v37;
  started = CSyncMLCmd::StartElement(v37, v35, v32, a4, a5, a6, v36, *(_QWORD *)&EventDescriptor.Id);
  if ( started >= 0 )
  {
    if ( !**(_DWORD **)&EventDescriptor.Id )
      ++*(_DWORD *)(a1 + 148);
    goto LABEL_72;
  }
  v13 = v9;
  LODWORD(v9) = 1;
LABEL_4:
  if ( v13 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 40LL))(v13, 1);
  if ( started < 0 && (_DWORD)v9 )
  {
    if ( (unsigned int)dword_18003E048 > 2 )
    {
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_18003E050;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = (unsigned __int16)*off_18003E050;
      v39 = byte_180036771;
      UserData.Reserved = 2;
      v40 = 27;
      v41 = 1;
      LODWORD(v35) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
    }
    if ( *(int *)(a1 + 56) >= 0 )
      *(_DWORD *)(a1 + 56) = started;
    if ( started != -2147024882 )
    {
      started = 0;
      *(_DWORD *)(*(_QWORD *)(a1 + 80) + 240LL) = 1;
    }
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    LODWORD(v35) = started;
    v42 = (unsigned int *)&v35;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v43 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v39 = (char *)qword_180036A40;
    UserData.Reserved = 2;
    v40 = 25;
    v41 = 1;
    v32 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18000f220  mov     r11, rsp
0x18000f223  push    rbp
0x18000f224  push    rbx
0x18000f225  push    rdi
0x18000f226  lea     rbp, [r11-28h]
0x18000f22a  sub     rsp, 110h
0x18000f231  mov     rax, cs:__security_cookie
0x18000f238  xor     rax, rsp
0x18000f23b  mov     [rbp+20h+var_50], rax
0x18000f23f  mov     rdi, [rbp+20h+arg_38]
0x18000f243  lea     r10, _TraceLoggingMetadataEnd
0x18000f24a  mov     [r11-20h], rsi
0x18000f24e  xor     eax, eax
0x18000f250  mov     [r11-28h], r12
0x18000f254  mov     rsi, rcx
0x18000f257  mov     [r11-30h], r13
0x18000f25b  xor     r12d, r12d
0x18000f25e  mov     [r11-38h], r14
0x18000f262  mov     r14, r9
0x18000f265  mov     r9, [rbp+20h+arg_30]
0x18000f269  mov     dword ptr [rsp+120h+var_D0], eax
0x18000f26d  mov     eax, [rcx+90h]
0x18000f273  mov     [r11-40h], r15
0x18000f277  lea     r11, _TraceLoggingMetadata
0x18000f27e  mov     [rsp+120h+var_A8], r9
0x18000f283  mov     dword ptr [rsp+120h+var_D0+4], r8d
0x18000f288  mov     [rsp+120h+var_B0], rdx
0x18000f28d  mov     qword ptr [rsp+120h+EventDescriptor.Id], rdi
0x18000f292  mov     [rsp+120h+var_C8], r12
0x18000f297  mov     [rbp+20h+var_A0], r12
0x18000f29b  test    al, 1
0x18000f29d  jz      loc_18000F4AD
0x18000f2a3  mov     eax, [rbp+20h+arg_28]
0x18000f2a6  mov     rcx, [rcx+60h]
0x18000f2aa  mov     [rsp+120h+var_F0], r9
0x18000f2af  mov     r9, r14
0x18000f2b2  mov     dword ptr [rsp+120h+UserData], eax
0x18000f2b6  mov     eax, [rbp+20h+arg_20]
0x18000f2b9  mov     [rsp+120h+UserDataCount], eax
0x18000f2bd  call    ?StartElement@CSyncMLMeta@@QEAAJPEBGK0KW4SyncMLElemType@@PEAW42@PEAH@Z; CSyncMLMeta::StartElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,SyncMLElemType *,int *)
0x18000f2c2  mov     ebx, eax
0x18000f2c4  test    eax, eax
0x18000f2c6  jns     loc_18000F966
0x18000f2cc  mov     rcx, r12
0x18000f2cf  lea     rdi, _TraceLoggingMetadata
0x18000f2d6  mov     r15, [rsp+120h+var_38]
0x18000f2de  mov     r14, [rsp+120h+var_30]
0x18000f2e6  mov     r13, [rsp+120h+var_28]
0x18000f2ee  test    rcx, rcx
0x18000f2f1  jz      short loc_18000F304
0x18000f2f3  mov     rax, [rcx]
0x18000f2f6  mov     edx, 1
0x18000f2fb  mov     rax, [rax+28h]
0x18000f2ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f304  test    ebx, ebx
0x18000f306  jns     loc_18000F3D2
0x18000f30c  test    r12d, r12d
0x18000f30f  jz      loc_18000F3D2
0x18000f315  mov     eax, cs:dword_18003E048
0x18000f31b  cmp     eax, 2
0x18000f31e  jbe     loc_18000F3B1
0x18000f324  movzx   eax, cs:word_180036767
0x18000f32b  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x18000f330  mov     dword ptr [rsp+120h+EventDescriptor.Level], eax
0x18000f334  xor     r9d, r9d; RelatedActivityId
0x18000f337  mov     rax, cs:off_18003E050
0x18000f33e  xor     r8d, r8d; ActivityId
0x18000f341  mov     [rbp+20h+var_90.Ptr], rax
0x18000f345  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x18000f34d  mov     [rsp+120h+EventDescriptor.Keyword], 0
0x18000f356  movzx   eax, word ptr [rax]
0x18000f359  mov     [rbp+20h+var_90.Size], eax
0x18000f35c  lea     rax, byte_180036771
0x18000f363  mov     [rbp+20h+var_80], rax
0x18000f367  lea     rax, _TraceLoggingMetadataEnd
0x18000f36e  sub     eax, edi
0x18000f370  mov     dword ptr [rbp+20h+var_90.0Ch], 2
0x18000f377  mov     [rbp+20h+var_78], 1Bh
0x18000f37e  mov     [rbp+20h+var_74], 1
0x18000f385  mov     dword ptr [rsp+120h+var_B0], eax
0x18000f389  mov     eax, dword ptr [rsp+120h+var_B0]
0x18000f38d  mov     rcx, cs:RegHandle; RegHandle
0x18000f394  lea     rax, [rbp+20h+var_90]
0x18000f398  mov     [rsp+120h+UserData], rax; UserData
0x18000f39d  mov     [rsp+120h+UserDataCount], 2; UserDataCount
0x18000f3a5  call    cs:__imp_EventWriteTransfer
0x18000f3ac  nop     dword ptr [rax+rax+00h]
0x18000f3b1  cmp     dword ptr [rsi+38h], 0
0x18000f3b5  jl      short loc_18000F3BA
0x18000f3b7  mov     [rsi+38h], ebx
0x18000f3ba  cmp     ebx, 8007000Eh
0x18000f3c0  jz      short loc_18000F3D2
0x18000f3c2  mov     rax, [rsi+50h]
0x18000f3c6  xor     ebx, ebx
0x18000f3c8  mov     dword ptr [rax+0F0h], 1
0x18000f3d2  mov     eax, cs:dword_18003E048
0x18000f3d8  mov     r12, [rsp+120h+var_20]
0x18000f3e0  mov     rsi, [rsp+108h]
0x18000f3e8  cmp     eax, 5
0x18000f3eb  jbe     loc_18000F493
0x18000f3f1  lea     rax, [rsp+120h+var_B0]
0x18000f3f6  mov     dword ptr [rsp+120h+var_B0], ebx
0x18000f3fa  mov     [rbp+20h+var_70], rax
0x18000f3fe  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x18000f403  movzx   eax, cs:word_180036A36
0x18000f40a  xor     r9d, r9d; RelatedActivityId
0x18000f40d  mov     dword ptr [rsp+120h+EventDescriptor.Level], eax
0x18000f411  xor     r8d, r8d; ActivityId
0x18000f414  mov     rax, cs:off_18003E050
0x18000f41b  mov     [rbp+20h+var_90.Ptr], rax
0x18000f41f  mov     [rbp+20h+var_68], 4
0x18000f427  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x18000f42f  mov     [rsp+120h+EventDescriptor.Keyword], 0
0x18000f438  movzx   eax, word ptr [rax]
0x18000f43b  mov     [rbp+20h+var_90.Size], eax
0x18000f43e  lea     rax, qword_180036A40
0x18000f445  mov     [rbp+20h+var_80], rax
0x18000f449  lea     rax, _TraceLoggingMetadataEnd
0x18000f450  sub     eax, edi
0x18000f452  mov     dword ptr [rbp+20h+var_90.0Ch], 2
0x18000f459  mov     [rbp+20h+var_78], 19h
0x18000f460  mov     [rbp+20h+var_74], 1
0x18000f467  mov     dword ptr [rsp+120h+var_D0+4], eax
0x18000f46b  mov     eax, dword ptr [rsp+120h+var_D0+4]
0x18000f46f  mov     rcx, cs:RegHandle; RegHandle
0x18000f476  lea     rax, [rbp+20h+var_90]
0x18000f47a  mov     [rsp+120h+UserData], rax; UserData
0x18000f47f  mov     [rsp+120h+UserDataCount], 3; UserDataCount
0x18000f487  call    cs:__imp_EventWriteTransfer
0x18000f48e  nop     dword ptr [rax+rax+00h]
0x18000f493  mov     eax, ebx
0x18000f495  mov     rcx, [rbp+20h+var_50]
0x18000f499  xor     rcx, rsp; StackCookie
0x18000f49c  call    __security_check_cookie
0x18000f4a1  add     rsp, 110h
0x18000f4a8  pop     rdi
0x18000f4a9  pop     rbx
0x18000f4aa  pop     rbp
0x18000f4ab  retn
0x18000f4ad  mov     rcx, [rcx+78h]
0x18000f4b1  test    rcx, rcx
0x18000f4b4  jz      short loc_18000F4E5
0x18000f4b6  mov     eax, [rbp+20h+arg_28]
0x18000f4b9  mov     [rsp+38h], rdi
0x18000f4be  mov     [rsp+120h+var_F0], r9
0x18000f4c3  mov     r9, r14
0x18000f4c6  mov     dword ptr [rsp+120h+UserData], eax
0x18000f4ca  mov     eax, [rbp+20h+arg_20]
0x18000f4cd  mov     [rsp+120h+UserDataCount], eax
0x18000f4d1  call    ?StartElement@CSyncMLItem@@QEAAJPEBGK0KW4SyncMLElemType@@PEAW42@PEAH@Z; CSyncMLItem::StartElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,SyncMLElemType *,int *)
0x18000f4d6  mov     ebx, eax
0x18000f4d8  test    eax, eax
0x18000f4da  js      loc_18000F2CC
0x18000f4e0  jmp     loc_18000F966
0x18000f4e5  mov     rcx, [rsi+80h]
0x18000f4ec  test    rcx, rcx
0x18000f4ef  jz      short loc_18000F52F
0x18000f4f1  mov     eax, [rbp+20h+arg_28]
0x18000f4f4  mov     [rsp+38h], rdi
0x18000f4f9  mov     [rsp+120h+var_F0], r9
0x18000f4fe  mov     r9, r14
0x18000f501  mov     dword ptr [rsp+120h+UserData], eax
0x18000f505  mov     eax, [rbp+20h+arg_20]
0x18000f508  mov     [rsp+120h+UserDataCount], eax
0x18000f50c  call    ?StartElement@CSyncMLCmd@@QEAAJPEBGK0KW4SyncMLElemType@@PEAW42@PEAH@Z; CSyncMLCmd::StartElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,SyncMLElemType *,int *)
0x18000f511  mov     ebx, eax
0x18000f513  test    eax, eax
0x18000f515  js      loc_18000F2CC
0x18000f51b  cmp     [rdi], r12d
0x18000f51e  jnz     loc_18000F966
0x18000f524  inc     dword ptr [rsi+94h]
0x18000f52a  jmp     loc_18000F966
0x18000f52f  mov     r12d, 1
0x18000f535  mov     dword ptr [rsp+120h+var_D0], r12d
0x18000f53a  test    r14, r14
0x18000f53d  jz      loc_18000FAAD
0x18000f543  xor     eax, eax
0x18000f545  cmp     ax, [r14]
0x18000f549  jz      loc_18000FAAD
0x18000f54f  mov     edx, [rbp+20h+arg_20]
0x18000f552  mov     eax, 0FFFFFFFFh
0x18000f557  mov     r12d, [rbp+20h+arg_28]
0x18000f55b  mov     ebx, edx
0x18000f55d  cmp     rdx, rax
0x18000f560  jnz     short loc_18000F58E
0x18000f562  mov     ebx, 7FFFFFFFh
0x18000f567  mov     rax, r14
0x18000f56a  mov     ecx, ebx
0x18000f56c  nop     dword ptr [rax+00h]
0x18000f570  cmp     word ptr [rax], 0
0x18000f574  jz      short loc_18000F580
0x18000f576  add     rax, 2
0x18000f57a  sub     rcx, 1
0x18000f57e  jnz     short loc_18000F570
0x18000f580  sub     rbx, rcx
0x18000f583  xor     eax, eax
0x18000f585  test    rcx, rcx
0x18000f588  cmovz   rbx, rax
0x18000f58c  jz      short loc_18000F5DA
0x18000f58e  xor     edi, edi
0x18000f590  lea     rcx, ?c_rgszSyncMLElem@@3PAPEBGA; ushort const * near * c_rgszSyncMLElem
0x18000f597  mov     r8, rbx
0x18000f59a  mov     rdx, [rcx+rdi*8]
0x18000f59e  lea     r15, [rcx+rdi*8]
0x18000f5a2  mov     rcx, r14
0x18000f5a5  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x18000f5ac  nop     dword ptr [rax+rax+00h]
0x18000f5b1  test    eax, eax
0x18000f5b3  jnz     short loc_18000F5C2
0x18000f5b5  mov     rcx, [r15]
0x18000f5b8  cmp     ax, [rcx+rbx*2]
0x18000f5bc  jz      loc_18000F70C
0x18000f5c2  inc     edi
0x18000f5c4  cmp     edi, 49h ; 'I'
0x18000f5c7  jl      short loc_18000F590
0x18000f5c9  mov     edx, [rbp+20h+arg_20]
0x18000f5cc  lea     r10, _TraceLoggingMetadataEnd
0x18000f5d3  lea     r11, _TraceLoggingMetadata
0x18000f5da  mov     eax, cs:dword_18003E048
0x18000f5e0  cmp     eax, 2
0x18000f5e3  jbe     loc_18000F6BB
0x18000f5e9  mov     dword ptr [rsp+120h+var_D0+4], edx
0x18000f5ed  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000f5f4  nop     dword ptr [rax+00h]
0x18000f5f8  nop     dword ptr [rax+rax+00000000h]
0x18000f600  cmp     word ptr [r14+rax*2+2], 0
0x18000f607  lea     rax, [rax+1]
0x18000f60b  jnz     short loc_18000F600
0x18000f60d  lea     eax, ds:2[rax*2]
0x18000f614  mov     [rbp+20h+var_60], r14
0x18000f618  mov     [rbp+20h+var_58], eax
0x18000f61b  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x18000f620  lea     rax, [rsp+120h+var_D0+4]
0x18000f625  mov     [rbp+20h+var_54], 0
0x18000f62c  mov     [rbp+20h+var_70], rax
0x18000f630  sub     r10d, r11d
0x18000f633  movzx   eax, cs:word_180036FAF
0x18000f63a  xor     r9d, r9d; RelatedActivityId
0x18000f63d  mov     dword ptr [rsp+120h+EventDescriptor.Level], eax
0x18000f641  xor     r8d, r8d; ActivityId
0x18000f644  mov     rax, cs:off_18003E050
0x18000f64b  mov     [rbp+20h+var_90.Ptr], rax
0x18000f64f  mov     [rbp+20h+var_68], 4
0x18000f657  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x18000f65f  mov     [rsp+120h+EventDescriptor.Keyword], 0
0x18000f668  movzx   eax, word ptr [rax]
0x18000f66b  mov     [rbp+20h+var_90.Size], eax
0x18000f66e  lea     rax, byte_180036FB9
0x18000f675  mov     [rbp+20h+var_80], rax
0x18000f679  mov     dword ptr [rbp+20h+var_90.0Ch], 2
0x18000f680  mov     [rbp+20h+var_78], 32h ; '2'
0x18000f687  mov     [rbp+20h+var_74], 1
0x18000f68e  mov     dword ptr [rsp+120h+var_B0], r10d
0x18000f693  mov     eax, dword ptr [rsp+120h+var_B0]
0x18000f697  mov     rcx, cs:RegHandle; RegHandle
0x18000f69e  lea     rax, [rbp+20h+var_90]
0x18000f6a2  mov     [rsp+120h+UserData], rax; UserData
0x18000f6a7  mov     [rsp+120h+UserDataCount], 4; UserDataCount
0x18000f6af  call    cs:__imp_EventWriteTransfer
0x18000f6b6  nop     dword ptr [rax+rax+00h]
0x18000f6bb  cmp     dword ptr [rsi+5Ch], 49h ; 'I'
0x18000f6bf  mov     ebx, 82AA0001h
0x18000f6c4  jnz     short loc_18000F6FD
0x18000f6c6  mov     ecx, r12d
0x18000f6c9  call    ?IsParentElementOfCmd@CSyncMLCmd@@CAHW4SyncMLElemType@@@Z; CSyncMLCmd::IsParentElementOfCmd(SyncMLElemType)
0x18000f6ce  test    eax, eax
0x18000f6d0  jz      short loc_18000F6FD
0x18000f6d2  mov     edi, 49h ; 'I'
0x18000f6d7  xor     ebx, ebx
0x18000f6d9  cmp     r12d, 27h ; '''
0x18000f6dd  ja      short loc_18000F6F8
0x18000f6df  mov     rcx, 8010000004h
0x18000f6e9  bt      rcx, r12
0x18000f6ed  jnb     short loc_18000F6F8
0x18000f6ef  cmp     r12d, edi
0x18000f6f2  jnz     loc_18000F95A
0x18000f6f8  mov     ebx, 82AA0001h
0x18000f6fd  mov     rcx, [rsp+120h+var_C8]
0x18000f702  mov     r12d, dword ptr [rsp+120h+var_D0]
0x18000f707  jmp     loc_18000F2CF
0x18000f70c  mov     eax, [rsi+5Ch]
0x18000f70f  xor     ebx, ebx
0x18000f711  cmp     edi, eax
0x18000f713  jz      short loc_18000F6D9
0x18000f715  cmp     eax, r12d
0x18000f718  jnz     loc_18000FA62
0x18000f71e  mov     ecx, edi
0x18000f720  sub     ecx, 5
0x18000f723  jz      loc_18000FA5A
0x18000f729  sub     ecx, 11h
0x18000f72c  jz      loc_18000F997
0x18000f732  cmp     ecx, 1
0x18000f735  jz      loc_18000F82C
0x18000f73b  mov     ecx, edi
0x18000f73d  call    ?IsCmdType@CSyncMLCmd@@SAHW4SyncMLElemType@@@Z; CSyncMLCmd::IsCmdType(SyncMLElemType)
0x18000f742  test    eax, eax
0x18000f744  jz      loc_18000FA62
0x18000f74a  cmp     [rsi+0A4h], ebx
0x18000f750  jnz     short loc_18000F79D
0x18000f752  mov     eax, cs:dword_18003E048
  ... truncated ...
```
