# CSyncMLItem::StartElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,SyncMLElemType *,int *)

- ea: `0x18000a0d0`
- end: `0x18000a756`
- name: `?StartElement@CSyncMLItem@@QEAAJPEBGK0KW4SyncMLElemType@@PEAW42@PEAH@Z`
- size: `1670`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000f220`

## callees

- `0x180003260`
- `0x18000a0d0`
- `0x18000fee0`
- `0x180014330`
- `0x18001c2d4`
- `0x180021a68`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a35d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a474`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a591`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a727`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a35d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a474`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a591`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a727`
- `DMCmnUtils!InvStrCmpNIW` at `0x18000a1b9`
- `DMCmnUtils!InvStrCmpNIW` at `0x18000a1b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSyncMLItem::StartElement(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        int *a7,
        _DWORD *a8)
{
  _DWORD *v10; // r14
  int started; // ebx
  int v12; // r15d
  unsigned __int64 v13; // rsi
  __int64 v14; // rcx
  const unsigned __int16 *v15; // rax
  __int64 v16; // rbx
  const unsigned __int16 **v17; // r14
  const unsigned __int16 *v18; // rdx
  CSyncMLDPU *v19; // rsi
  char *v20; // rax
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  __int64 v24; // rax
  _DWORD *v25; // rdi
  unsigned int v27; // [rsp+40h] [rbp-61h] BYREF
  unsigned int v28; // [rsp+44h] [rbp-5Dh]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-59h] BYREF
  _DWORD *v30; // [rsp+58h] [rbp-49h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-41h] BYREF
  __int16 *v32; // [rsp+70h] [rbp-31h]
  int v33; // [rsp+78h] [rbp-29h]
  int v34; // [rsp+7Ch] [rbp-25h]
  unsigned int *v35; // [rsp+80h] [rbp-21h]
  __int64 v36; // [rsp+88h] [rbp-19h]

  v27 = a3;
  *(_QWORD *)&EventDescriptor.Id = a2;
  v10 = a8;
  v30 = a8;
  if ( (*(_DWORD *)(a1 + 24) & 1) != 0 )
  {
    started = CSyncMLMeta::StartElement(*(_QWORD *)(a1 + 16), a2, a3, a4, a5, a6, (__int64)a7);
    goto LABEL_74;
  }
  v12 = 73;
  v28 = 1;
  if ( !a4 || !*a4 )
  {
    started = -2147024809;
LABEL_18:
    if ( !*(_DWORD *)(a1 + 112) || !(unsigned int)CSyncMLItem::IsDataTypeXML((CSyncMLItem *)a1) )
    {
      if ( started == -2147023728 )
        started = -2102788095;
      goto LABEL_58;
    }
    v19 = *(CSyncMLDPU **)(*(_QWORD *)(a1 + 8) + 80LL);
    *(_QWORD *)&EventDescriptor.Id = v19;
    if ( v19 )
      (*(void (__fastcall **)(CSyncMLDPU *))(*(_QWORD *)v19 + 8LL))(v19);
    started = CSyncMLDPU::SetXMLContent(v19, v18, a5);
    if ( v19 )
      (*(void (__fastcall **)(CSyncMLDPU *))(*(_QWORD *)v19 + 16LL))(v19);
    *v10 = 1;
    goto LABEL_56;
  }
  v13 = a5;
  if ( a5 == 0xFFFFFFFFLL )
  {
    v14 = 0x7FFFFFFF;
    v15 = a4;
    do
    {
      if ( !*v15 )
        break;
      ++v15;
      --v14;
    }
    while ( v14 );
    v13 = 0x7FFFFFFF - v14;
    if ( !v14 )
    {
LABEL_15:
      started = -2147023728;
      goto LABEL_18;
    }
  }
  v16 = 0;
  while ( 1 )
  {
    v17 = (const unsigned __int16 **)&(&c_rgszSyncMLElem)[v16];
    if ( !InvStrCmpNIW(a4, *v17, v13) && !(*v17)[v13] )
      break;
    v16 = (unsigned int)(v16 + 1);
    if ( (int)v16 >= 73 )
    {
      v10 = v30;
      goto LABEL_15;
    }
  }
  v12 = v16;
  started = 0;
  switch ( v12 )
  {
    case 22:
      goto LABEL_56;
    case 10:
      if ( ((a6 - 15) & 0xFFFFFFFD) != 0 )
      {
        started = -2102788095;
        goto LABEL_58;
      }
      goto LABEL_56;
    case 15:
      if ( a6 != 22 )
        goto LABEL_40;
      v23 = *(_DWORD *)(a1 + 24);
      if ( (v23 & 2) != 0 )
      {
        if ( (unsigned int)dword_18003E048 > 2 )
        {
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 2;
          EventDescriptor.Keyword = 0;
          UserData.Ptr = (ULONGLONG)off_18003E050;
          UserData.Size = (unsigned __int16)*off_18003E050;
          v20 = (char *)word_1800364C2;
          v33 = 25;
          goto LABEL_49;
        }
        goto LABEL_40;
      }
      v22 = v23 | 2;
      goto LABEL_55;
    case 17:
      v21 = *(_DWORD *)(a1 + 24);
      if ( (v21 & 4) != 0 )
      {
        if ( (unsigned int)dword_18003E048 > 2 )
        {
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 2;
          EventDescriptor.Keyword = 0;
          UserData.Ptr = (ULONGLONG)off_18003E050;
          UserData.Size = (unsigned __int16)*off_18003E050;
          v20 = byte_18003641D;
          v33 = 25;
          goto LABEL_49;
        }
LABEL_40:
        started = -2102788095;
        goto LABEL_58;
      }
      v22 = v21 | 4;
LABEL_55:
      *(_DWORD *)(a1 + 24) = v22;
      goto LABEL_56;
    case 21:
      if ( a6 != 22 )
      {
        started = -2102788095;
        goto LABEL_58;
      }
      if ( !*(_QWORD *)(a1 + 80) )
      {
        ++*(_DWORD *)(a1 + 112);
        goto LABEL_56;
      }
      if ( (unsigned int)dword_18003E048 > 2 )
      {
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 2;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_18003E050;
        UserData.Size = (unsigned __int16)*off_18003E050;
        v20 = byte_1800362B5;
        v33 = 23;
LABEL_49:
        UserData.Reserved = 2;
        v32 = (__int16 *)v20;
        v34 = 1;
        v27 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
        started = -2102788095;
        goto LABEL_58;
      }
      goto LABEL_40;
    case 23:
      if ( a6 != 22 )
      {
        started = -2102788095;
        goto LABEL_58;
      }
      if ( *(_QWORD *)(a1 + 16) )
      {
        if ( (unsigned int)dword_18003E048 > 2 )
        {
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 2;
          EventDescriptor.Keyword = 0;
          UserData.Ptr = (ULONGLONG)off_18003E050;
          UserData.Size = (unsigned __int16)*off_18003E050;
          UserData.Reserved = 2;
          v32 = &word_1800363CE;
          v33 = 23;
          v34 = 1;
          v28 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
        }
        goto LABEL_40;
      }
      started = CSyncMLMeta::CreateMeta((struct CSyncMLMeta **)(a1 + 16));
      if ( started < 0 )
        goto LABEL_58;
      started = CSyncMLMeta::StartElement(
                  *(_QWORD *)(a1 + 16),
                  *(const unsigned __int16 **)&EventDescriptor.Id,
                  v27,
                  a4,
                  a5,
                  22,
                  (__int64)a7);
      if ( started < 0 )
        goto LABEL_74;
      v28 = 0;
      *(_DWORD *)(a1 + 24) |= 1u;
LABEL_56:
      *a7 = v12;
      if ( started >= 0 || !v28 )
        goto LABEL_74;
      goto LABEL_58;
  }
  started = -2102788095;
LABEL_58:
  if ( (unsigned int)dword_18003E048 > 2 )
  {
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    UserData.Size = (unsigned __int16)*off_18003E050;
    UserData.Reserved = 2;
    v32 = (__int16 *)byte_18003649B;
    v33 = 27;
    v34 = 1;
    v27 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
  }
  if ( *(int *)(a1 + 88) >= 0 )
    *(_DWORD *)(a1 + 88) = started;
  if ( started != -2147024882 )
  {
    started = 0;
    v24 = *(_QWORD *)(a1 + 8);
    v25 = *(_DWORD **)(v24 + 80);
    if ( v25 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v25 + 8LL))(*(_QWORD *)(v24 + 80));
    v25[60] = 1;
    if ( v25 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v25 + 16LL))(v25);
  }
LABEL_74:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v27 = started;
    v35 = &v27;
    v36 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    UserData.Size = (unsigned __int16)*off_18003E050;
    UserData.Reserved = 2;
    v32 = (__int16 *)qword_180036290;
    v33 = 25;
    v34 = 1;
    v28 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18000a0d0  push    rbp
0x18000a0d2  push    rbx
0x18000a0d3  push    rsi
0x18000a0d4  push    rdi
0x18000a0d5  push    r12
0x18000a0d7  push    r13
0x18000a0d9  push    r14
0x18000a0db  push    r15
0x18000a0dd  lea     rbp, [rsp-7]
0x18000a0e2  sub     rsp, 0A8h
0x18000a0e9  mov     rax, cs:__security_cookie
0x18000a0f0  xor     rax, rsp
0x18000a0f3  mov     [rbp+3Fh+var_50], rax
0x18000a0f7  mov     r12, r9
0x18000a0fa  mov     [rbp+3Fh+var_A0], r8d
0x18000a0fe  mov     qword ptr [rbp+3Fh+EventDescriptor.Id], rdx
0x18000a102  mov     rdi, rcx
0x18000a105  mov     r13, [rbp+3Fh+arg_30]
0x18000a109  mov     r14, [rbp+3Fh+arg_38]
0x18000a110  mov     [rbp+3Fh+var_88], r14
0x18000a114  mov     eax, [rcx+18h]
0x18000a117  lea     rsi, _TraceLoggingMetadataEnd
0x18000a11e  lea     r15, _TraceLoggingMetadata
0x18000a125  test    al, 1
0x18000a127  jz      short loc_18000A14C
0x18000a129  mov     [rsp+0E0h+var_B0], r13
0x18000a12e  mov     eax, [rbp+3Fh+arg_28]
0x18000a131  mov     dword ptr [rsp+0E0h+UserData], eax
0x18000a135  mov     eax, [rbp+3Fh+arg_20]
0x18000a138  mov     [rsp+0E0h+UserDataCount], eax
0x18000a13c  mov     rcx, [rcx+10h]
0x18000a140  call    ?StartElement@CSyncMLMeta@@QEAAJPEBGK0KW4SyncMLElemType@@PEAW42@PEAH@Z; CSyncMLMeta::StartElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,SyncMLElemType *,int *)
0x18000a145  mov     ebx, eax
0x18000a147  jmp     loc_18000A690
0x18000a14c  mov     r15d, 49h ; 'I'
0x18000a152  mov     [rbp+3Fh+var_9C], 1
0x18000a159  test    r12, r12
0x18000a15c  jz      loc_18000A1EE
0x18000a162  xor     eax, eax
0x18000a164  cmp     ax, [r9]
0x18000a168  jz      loc_18000A1EE
0x18000a16e  mov     esi, [rbp+3Fh+arg_20]
0x18000a171  mov     eax, 0FFFFFFFFh
0x18000a176  cmp     rsi, rax
0x18000a179  jnz     short loc_18000A1A3
0x18000a17b  mov     esi, 7FFFFFFFh
0x18000a180  mov     ecx, esi
0x18000a182  mov     rax, r12
0x18000a185  cmp     word ptr [rax], 0
0x18000a189  jz      short loc_18000A195
0x18000a18b  add     rax, 2
0x18000a18f  sub     rcx, 1
0x18000a193  jnz     short loc_18000A185
0x18000a195  sub     rsi, rcx
0x18000a198  xor     eax, eax
0x18000a19a  test    rcx, rcx
0x18000a19d  cmovz   rsi, rax
0x18000a1a1  jz      short loc_18000A1DD
0x18000a1a3  xor     ebx, ebx
0x18000a1a5  lea     rcx, ?c_rgszSyncMLElem@@3PAPEBGA; ushort const * near * c_rgszSyncMLElem
0x18000a1ac  lea     r14, [rcx+rbx*8]
0x18000a1b0  mov     r8, rsi
0x18000a1b3  mov     rdx, [r14]
0x18000a1b6  mov     rcx, r12
0x18000a1b9  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x18000a1c0  nop     dword ptr [rax+rax+00h]
0x18000a1c5  test    eax, eax
0x18000a1c7  jnz     short loc_18000A1D2
0x18000a1c9  mov     rcx, [r14]
0x18000a1cc  cmp     ax, [rcx+rsi*2]
0x18000a1d0  jz      short loc_18000A1E4
0x18000a1d2  inc     ebx
0x18000a1d4  cmp     ebx, r15d
0x18000a1d7  jl      short loc_18000A1A5
0x18000a1d9  mov     r14, [rbp+3Fh+var_88]
0x18000a1dd  mov     ebx, 80070490h
0x18000a1e2  jmp     short loc_18000A1F3
0x18000a1e4  mov     r15d, ebx
0x18000a1e7  xor     ebx, ebx
0x18000a1e9  jmp     loc_18000A26F
0x18000a1ee  mov     ebx, 80070057h
0x18000a1f3  cmp     dword ptr [rdi+70h], 0
0x18000a1f7  jbe     short loc_18000A255
0x18000a1f9  mov     rcx, rdi; this
0x18000a1fc  call    ?IsDataTypeXML@CSyncMLItem@@QEBAHXZ; CSyncMLItem::IsDataTypeXML(void)
0x18000a201  test    eax, eax
0x18000a203  jz      short loc_18000A255
0x18000a205  mov     rax, [rdi+8]
0x18000a209  mov     rsi, [rax+50h]
0x18000a20d  mov     qword ptr [rbp+3Fh+EventDescriptor.Id], rsi
0x18000a211  test    rsi, rsi
0x18000a214  jz      short loc_18000A226
0x18000a216  mov     rax, [rsi]
0x18000a219  mov     rcx, rsi
0x18000a21c  mov     rax, [rax+8]
0x18000a220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a225  nop
0x18000a226  mov     r8d, [rbp+3Fh+arg_20]; unsigned int
0x18000a22a  mov     rcx, rsi; this
0x18000a22d  call    ?SetXMLContent@CSyncMLDPU@@QEAAJPEBGKH@Z; CSyncMLDPU::SetXMLContent(ushort const *,ulong,int)
0x18000a232  mov     ebx, eax
0x18000a234  test    rsi, rsi
0x18000a237  jz      short loc_18000A249
0x18000a239  mov     rax, [rsi]
0x18000a23c  mov     rcx, rsi
0x18000a23f  mov     rax, [rax+10h]
0x18000a243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a248  nop
0x18000a249  mov     dword ptr [r14], 1
0x18000a250  jmp     loc_18000A4E6
0x18000a255  cmp     ebx, 80070490h
0x18000a25b  jnz     short loc_18000A267
0x18000a25d  mov     ebx, 82AA0001h
0x18000a262  jmp     loc_18000A4FC
0x18000a267  test    ebx, ebx
0x18000a269  js      loc_18000A4FC
0x18000a26f  cmp     r15d, 16h
0x18000a273  jz      loc_18000A4E6
0x18000a279  cmp     r15d, 0Ah
0x18000a27d  jz      loc_18000A608
0x18000a283  cmp     r15d, 0Fh
0x18000a287  jz      loc_18000A5A2
0x18000a28d  cmp     r15d, 11h
0x18000a291  jz      loc_18000A48C
0x18000a297  cmp     r15d, 15h
0x18000a29b  jz      loc_18000A3C8
0x18000a2a1  cmp     r15d, 17h
0x18000a2a5  jz      short loc_18000A2B1
0x18000a2a7  mov     ebx, 82AA0001h
0x18000a2ac  jmp     loc_18000A4FC
0x18000a2b1  cmp     [rbp+3Fh+arg_28], 16h
0x18000a2b5  jz      short loc_18000A2C1
0x18000a2b7  mov     ebx, 82AA0001h
0x18000a2bc  jmp     loc_18000A4FC
0x18000a2c1  cmp     qword ptr [rdi+10h], 0
0x18000a2c6  jz      loc_18000A373
0x18000a2cc  mov     eax, cs:dword_18003E048
0x18000a2d2  cmp     eax, 2
0x18000a2d5  jbe     loc_18000A369
0x18000a2db  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], 0B000000h
0x18000a2e2  movzx   eax, cs:word_1800363C4
0x18000a2e9  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x18000a2ec  mov     [rbp+3Fh+EventDescriptor.Keyword], 0
0x18000a2f4  mov     rax, cs:off_18003E050
0x18000a2fb  mov     [rbp+3Fh+var_80.Ptr], rax
0x18000a2ff  movzx   eax, word ptr [rax]
0x18000a302  mov     [rbp+3Fh+var_80.Size], eax
0x18000a305  mov     dword ptr [rbp+3Fh+var_80.0Ch], 2
0x18000a30c  lea     rax, word_1800363CE
0x18000a313  mov     [rbp+3Fh+var_70], rax
0x18000a317  mov     [rbp+3Fh+var_68], 17h
0x18000a31e  mov     [rbp+3Fh+var_64], 1
0x18000a325  lea     rax, _TraceLoggingMetadataEnd
0x18000a32c  lea     rcx, _TraceLoggingMetadata
0x18000a333  sub     eax, ecx
0x18000a335  mov     [rbp+3Fh+var_9C], eax
0x18000a338  mov     eax, [rbp+3Fh+var_9C]
0x18000a33b  lea     rax, [rbp+3Fh+var_80]
0x18000a33f  mov     [rsp+0E0h+UserData], rax; UserData
0x18000a344  mov     [rsp+0E0h+UserDataCount], 2; UserDataCount
0x18000a34c  xor     r9d, r9d; RelatedActivityId
0x18000a34f  xor     r8d, r8d; ActivityId
0x18000a352  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x18000a356  mov     rcx, cs:RegHandle; RegHandle
0x18000a35d  call    cs:__imp_EventWriteTransfer
0x18000a364  nop     dword ptr [rax+rax+00h]
0x18000a369  mov     ebx, 82AA0001h
0x18000a36e  jmp     loc_18000A4FC
0x18000a373  lea     rcx, [rdi+10h]; struct CSyncMLMeta **
0x18000a377  call    ?CreateMeta@CSyncMLMeta@@SAJPEAPEAV1@@Z; CSyncMLMeta::CreateMeta(CSyncMLMeta * *)
0x18000a37c  mov     ebx, eax
0x18000a37e  test    eax, eax
0x18000a380  js      loc_18000A4FC
0x18000a386  mov     [rsp+0E0h+var_B0], r13
0x18000a38b  mov     dword ptr [rsp+0E0h+UserData], 16h
0x18000a393  mov     eax, [rbp+3Fh+arg_20]
0x18000a396  mov     [rsp+0E0h+UserDataCount], eax
0x18000a39a  mov     r9, r12
0x18000a39d  mov     r8d, [rbp+3Fh+var_A0]
0x18000a3a1  mov     rdx, qword ptr [rbp+3Fh+EventDescriptor.Id]
0x18000a3a5  mov     rcx, [rdi+10h]
0x18000a3a9  call    ?StartElement@CSyncMLMeta@@QEAAJPEBGK0KW4SyncMLElemType@@PEAW42@PEAH@Z; CSyncMLMeta::StartElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,SyncMLElemType *,int *)
0x18000a3ae  mov     ebx, eax
0x18000a3b0  test    eax, eax
0x18000a3b2  js      loc_18000A682
0x18000a3b8  mov     [rbp+3Fh+var_9C], 0
0x18000a3bf  or      dword ptr [rdi+18h], 1
0x18000a3c3  jmp     loc_18000A4E6
0x18000a3c8  cmp     [rbp+3Fh+arg_28], 16h
0x18000a3cc  jz      short loc_18000A3D8
0x18000a3ce  mov     ebx, 82AA0001h
0x18000a3d3  jmp     loc_18000A4FC
0x18000a3d8  cmp     qword ptr [rdi+50h], 0
0x18000a3dd  jz      loc_18000A487
0x18000a3e3  mov     eax, cs:dword_18003E048
0x18000a3e9  cmp     eax, 2
0x18000a3ec  jbe     loc_18000A369
0x18000a3f2  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], 0B000000h
0x18000a3f9  movzx   eax, cs:word_1800362AB
0x18000a400  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x18000a403  mov     [rbp+3Fh+EventDescriptor.Keyword], 0
0x18000a40b  mov     rax, cs:off_18003E050
0x18000a412  mov     [rbp+3Fh+var_80.Ptr], rax
0x18000a416  movzx   eax, word ptr [rax]
0x18000a419  mov     [rbp+3Fh+var_80.Size], eax
0x18000a41c  lea     rax, byte_1800362B5
0x18000a423  mov     [rbp+3Fh+var_68], 17h
0x18000a42a  mov     dword ptr [rbp+3Fh+var_80.0Ch], 2
0x18000a431  mov     [rbp+3Fh+var_70], rax
0x18000a435  mov     [rbp+3Fh+var_64], 1
0x18000a43c  lea     rax, _TraceLoggingMetadataEnd
0x18000a443  lea     rcx, _TraceLoggingMetadata
0x18000a44a  sub     eax, ecx
0x18000a44c  mov     [rbp+3Fh+var_A0], eax
0x18000a44f  mov     eax, [rbp+3Fh+var_A0]
0x18000a452  lea     rax, [rbp+3Fh+var_80]
0x18000a456  mov     [rsp+0E0h+UserData], rax; UserData
0x18000a45b  mov     [rsp+0E0h+UserDataCount], 2; UserDataCount
0x18000a463  xor     r9d, r9d; RelatedActivityId
0x18000a466  xor     r8d, r8d; ActivityId
0x18000a469  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x18000a46d  mov     rcx, cs:RegHandle; RegHandle
0x18000a474  call    cs:__imp_EventWriteTransfer
0x18000a47b  nop     dword ptr [rax+rax+00h]
0x18000a480  mov     ebx, 82AA0001h
0x18000a485  jmp     short loc_18000A4FC
0x18000a487  inc     dword ptr [rdi+70h]
0x18000a48a  jmp     short loc_18000A4E6
0x18000a48c  mov     ecx, [rdi+18h]
0x18000a48f  test    cl, 4
0x18000a492  jz      short loc_18000A4E0
0x18000a494  mov     eax, cs:dword_18003E048
0x18000a49a  cmp     eax, 2
0x18000a49d  jbe     loc_18000A369
0x18000a4a3  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], 0B000000h
0x18000a4aa  movzx   eax, cs:word_180036413
0x18000a4b1  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x18000a4b4  mov     [rbp+3Fh+EventDescriptor.Keyword], 0
0x18000a4bc  mov     rax, cs:off_18003E050
0x18000a4c3  mov     [rbp+3Fh+var_80.Ptr], rax
0x18000a4c7  movzx   eax, word ptr [rax]
0x18000a4ca  mov     [rbp+3Fh+var_80.Size], eax
0x18000a4cd  lea     rax, byte_18003641D
0x18000a4d4  mov     [rbp+3Fh+var_68], 19h
0x18000a4db  jmp     loc_18000A42A
0x18000a4e0  or      ecx, 4
0x18000a4e3  mov     [rdi+18h], ecx
0x18000a4e6  mov     [r13+0], r15d
0x18000a4ea  test    ebx, ebx
0x18000a4ec  jns     loc_18000A682
0x18000a4f2  cmp     [rbp+3Fh+var_9C], 0
0x18000a4f6  jz      loc_18000A682
0x18000a4fc  mov     eax, cs:dword_18003E048
0x18000a502  cmp     eax, 2
0x18000a505  jbe     loc_18000A623
0x18000a50b  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], 0B000000h
0x18000a512  movzx   eax, cs:word_180036491
0x18000a519  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x18000a51c  mov     [rbp+3Fh+EventDescriptor.Keyword], 0
0x18000a524  mov     rax, cs:off_18003E050
0x18000a52b  mov     [rbp+3Fh+var_80.Ptr], rax
0x18000a52f  movzx   eax, word ptr [rax]
0x18000a532  mov     [rbp+3Fh+var_80.Size], eax
0x18000a535  mov     dword ptr [rbp+3Fh+var_80.0Ch], 2
0x18000a53c  lea     rax, byte_18003649B
0x18000a543  mov     [rbp+3Fh+var_70], rax
0x18000a547  mov     [rbp+3Fh+var_68], 1Bh
0x18000a54e  mov     [rbp+3Fh+var_64], 1
0x18000a555  lea     rsi, _TraceLoggingMetadataEnd
0x18000a55c  mov     rax, rsi
0x18000a55f  lea     r15, _TraceLoggingMetadata
0x18000a566  sub     eax, r15d
0x18000a569  mov     [rbp+3Fh+var_A0], eax
0x18000a56c  mov     eax, [rbp+3Fh+var_A0]
0x18000a56f  lea     rax, [rbp+3Fh+var_80]
0x18000a573  mov     [rsp+0E0h+UserData], rax; UserData
0x18000a578  mov     [rsp+0E0h+UserDataCount], 2; UserDataCount
0x18000a580  xor     r9d, r9d; RelatedActivityId
0x18000a583  xor     r8d, r8d; ActivityId
0x18000a586  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x18000a58a  mov     rcx, cs:RegHandle; RegHandle
0x18000a591  call    cs:__imp_EventWriteTransfer
0x18000a598  nop     dword ptr [rax+rax+00h]
0x18000a59d  jmp     loc_18000A631
0x18000a5a2  cmp     [rbp+3Fh+arg_28], 16h
0x18000a5a6  jnz     loc_18000A369
0x18000a5ac  mov     ecx, [rdi+18h]
0x18000a5af  test    cl, 2
0x18000a5b2  jz      short loc_18000A600
0x18000a5b4  mov     eax, cs:dword_18003E048
0x18000a5ba  cmp     eax, 2
0x18000a5bd  jbe     loc_18000A369
0x18000a5c3  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], 0B000000h
0x18000a5ca  movzx   eax, cs:word_1800364B8
0x18000a5d1  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x18000a5d4  mov     [rbp+3Fh+EventDescriptor.Keyword], 0
0x18000a5dc  mov     rax, cs:off_18003E050
0x18000a5e3  mov     [rbp+3Fh+var_80.Ptr], rax
0x18000a5e7  movzx   eax, word ptr [rax]
0x18000a5ea  mov     [rbp+3Fh+var_80.Size], eax
  ... truncated ...
```
