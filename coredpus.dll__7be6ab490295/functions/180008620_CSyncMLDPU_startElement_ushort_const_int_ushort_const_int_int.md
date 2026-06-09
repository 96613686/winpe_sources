# CSyncMLDPU::startElement(ushort const *,int,ushort const *,int,int)

- ea: `0x180008620`
- end: `0x180008d29`
- name: `?startElement@CSyncMLDPU@@AEAAJPEBGH0HH@Z`
- size: `1801`
- prototype: `__int64 __fastcall(CSyncMLDPU *__hidden this, const unsigned __int16 *, int, const unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180007820`

## callees

- `0x180003260`
- `0x180008620`
- `0x18000f220`
- `0x180010e04`
- `0x180014330`
- `0x18001fa3c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000880e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008971`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008ae7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008cdc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000880e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008971`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008ae7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008cdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000869d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000869d`
- `DMCmnUtils!InvStrCmpNIW` at `0x1800089f6`
- `DMCmnUtils!InvStrCmpNIW` at `0x1800089f6`

## pseudocode

```c
__int64 __fastcall CSyncMLDPU::startElement(
        CSyncMLDPU *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int a6)
{
  __int64 v6; // r10
  __int64 *v7; // r13
  void *v11; // rcx
  CSyncMLItem *v12; // r10
  __int64 v13; // r10
  unsigned int v14; // r11d
  __int64 v15; // rax
  __int64 v16; // rcx
  bool v17; // zf
  int v18; // ecx
  int v19; // eax
  int Cmd; // esi
  unsigned int v21; // r15d
  const OLECHAR *v22; // rdx
  __int64 v23; // rax
  const OLECHAR *v24; // r8
  __int64 v25; // rcx
  int v26; // ecx
  int v27; // eax
  unsigned __int64 v28; // rsi
  const unsigned __int16 *v29; // rax
  __int64 v30; // rcx
  unsigned int v31; // edi
  int v32; // r10d
  unsigned int v34; // [rsp+40h] [rbp-99h] BYREF
  unsigned int v35; // [rsp+44h] [rbp-95h] BYREF
  unsigned int v36; // [rsp+48h] [rbp-91h] BYREF
  int v37; // [rsp+4Ch] [rbp-8Dh] BYREF
  int v38; // [rsp+50h] [rbp-89h] BYREF
  unsigned int v39; // [rsp+54h] [rbp-85h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-81h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-69h] BYREF
  char *v42; // [rsp+80h] [rbp-59h]
  int v43; // [rsp+88h] [rbp-51h]
  int v44; // [rsp+8Ch] [rbp-4Dh]
  unsigned int *v45; // [rsp+90h] [rbp-49h]
  __int64 v46; // [rsp+98h] [rbp-41h]
  const unsigned __int16 *v47; // [rsp+A0h] [rbp-39h]
  int v48; // [rsp+A8h] [rbp-31h]
  int v49; // [rsp+ACh] [rbp-2Dh]
  unsigned int *v50; // [rsp+B0h] [rbp-29h]
  __int64 v51; // [rsp+B8h] [rbp-21h]
  const unsigned __int16 *v52; // [rsp+C0h] [rbp-19h]
  int v53; // [rsp+C8h] [rbp-11h]
  int v54; // [rsp+CCh] [rbp-Dh]

  v6 = *((_QWORD *)this + 8);
  v7 = (__int64 *)((char *)this + 64);
  v35 = a3;
  v37 = 73;
  v38 = 0;
  if ( !v6 || (v12 = *(CSyncMLItem **)(v6 + 120)) == 0 )
  {
    v11 = (void *)*((_QWORD *)this + 42);
LABEL_7:
    LocalFree(v11);
    v14 = v35;
    *((_QWORD *)this + 42) = 0;
    goto LABEL_8;
  }
  if ( !(unsigned int)CSyncMLItem::IsDataTypeXML(v12) || !*(_DWORD *)(v13 + 112) )
  {
    v11 = (void *)*((_QWORD *)this + 42);
    goto LABEL_7;
  }
LABEL_8:
  if ( !*((_DWORD *)this + 60) )
  {
    Cmd = 0;
    if ( (unsigned int)dword_18003E048 <= 5 )
    {
      v21 = a5;
    }
    else
    {
      v21 = a5;
      v22 = &word_180032B28;
      v34 = a5;
      v23 = -1;
      v39 = v14;
      if ( a4 )
      {
        v24 = a4;
        v25 = -1;
        do
          v17 = a4[++v25] == 0;
        while ( !v17 );
        v26 = 2 * v25 + 2;
      }
      else
      {
        v24 = &word_180032B28;
        v26 = 2;
      }
      v53 = v26;
      v50 = &v34;
      v52 = v24;
      v54 = 0;
      v51 = 4;
      if ( a2 )
      {
        v22 = a2;
        do
          v17 = a2[++v23] == 0;
        while ( !v17 );
        v27 = 2 * v23 + 2;
      }
      else
      {
        v27 = 2;
      }
      v48 = v27;
      v47 = v22;
      v45 = &v39;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_18003E050;
      v49 = 0;
      v46 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = (unsigned __int16)*off_18003E050;
      v42 = byte_18003604B;
      UserData.Reserved = 2;
      v43 = 84;
      v44 = 1;
      v36 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
    }
    if ( !*v7 )
    {
      if ( !a4 || !*a4 )
        goto LABEL_72;
      v28 = v21;
      if ( v21 == 0xFFFFFFFFLL )
      {
        v29 = a4;
        v30 = 0x7FFFFFFF;
        do
        {
          if ( !*v29 )
            break;
          ++v29;
          --v30;
        }
        while ( v30 );
        v28 = 0x7FFFFFFF - v30;
        if ( !v30 )
        {
LABEL_50:
          if ( *((_DWORD *)this + (unsigned int)(*((_DWORD *)this + 56) - 1) + 24) != 2 )
          {
            Cmd = -2102788095;
            if ( (unsigned int)dword_18003E048 > 5 )
            {
              v36 = -2102788095;
              v45 = &v36;
              *(_DWORD *)&EventDescriptor.Level = 5;
              UserData.Ptr = (ULONGLONG)off_18003E050;
              v46 = 4;
              *(_DWORD *)&EventDescriptor.Id = 184549376;
              EventDescriptor.Keyword = 0;
              UserData.Size = (unsigned __int16)*off_18003E050;
              v42 = (char *)qword_180035F60;
              UserData.Reserved = 2;
              v43 = 27;
              v44 = 1;
              v34 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
            }
            goto LABEL_75;
          }
          Cmd = CSyncMLCmd::CreateCmd(73, 0, this, a4, v21, v7);
          if ( Cmd < 0 )
            goto LABEL_75;
          goto LABEL_65;
        }
      }
      v31 = 0;
      while ( InvStrCmpNIW(a4, (&c_rgszSyncMLElem)[v31], v28) || (&c_rgszSyncMLElem)[v31][v28] )
      {
        if ( (int)++v31 >= 73 )
        {
          v21 = a5;
          goto LABEL_50;
        }
      }
      v37 = v31;
      if ( (unsigned int)CSyncMLCmd::IsCmdType(v31) )
      {
        Cmd = CSyncMLCmd::CreateCmd(v31, 0, this, 0, v32, v7);
        if ( Cmd < 0 )
          goto LABEL_75;
        if ( *((_DWORD *)this + 9) && v37 != 25 && *(int *)(*v7 + 56) >= 0 )
          *(_DWORD *)(*v7 + 56) = *((_DWORD *)this + 12);
LABEL_65:
        *((_DWORD *)this + 57) = *((_DWORD *)this + 56);
        goto LABEL_66;
      }
      Cmd = v32;
      if ( v31 && v31 != 2 )
      {
        if ( v31 != 8 )
        {
          Cmd = -2102788095;
          goto LABEL_75;
        }
        *((_DWORD *)this + 111) |= 1u;
      }
    }
LABEL_66:
    if ( !*v7
      || (Cmd = CSyncMLCmd::StartElement(
                  *v7,
                  a2,
                  v35,
                  a4,
                  a5,
                  *((_DWORD *)this + (unsigned int)(*((_DWORD *)this + 56) - 1) + 24),
                  &v37,
                  &v38),
          Cmd >= 0) )
    {
      if ( !*((_DWORD *)this + 60) && !a6 && !v38 )
      {
        if ( *((_DWORD *)this + 56) >= 0x20u )
        {
LABEL_72:
          Cmd = -2147024809;
          goto LABEL_75;
        }
        *((_DWORD *)this + (unsigned int)(*((_DWORD *)this + 56))++ + 24) = v37;
      }
      v38 = 0;
      if ( Cmd >= 0 )
        return 0;
    }
LABEL_75:
    if ( (unsigned int)dword_18003E048 > 2 )
    {
      v36 = Cmd;
      v45 = &v36;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_18003E050;
      v46 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = (unsigned __int16)*off_18003E050;
      v42 = (char *)&word_180035DE6;
      UserData.Reserved = 2;
      v43 = 40;
      v44 = 1;
      v34 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    goto LABEL_77;
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v35 = a5;
    v15 = -1;
    v39 = v14;
    if ( a4 )
    {
      v16 = -1;
      do
        v17 = a4[++v16] == 0;
      while ( !v17 );
      v18 = 2 * v16 + 2;
    }
    else
    {
      a4 = &word_180032B28;
      v18 = 2;
    }
    v53 = v18;
    v50 = &v35;
    v52 = a4;
    v54 = 0;
    v51 = 4;
    if ( a2 )
    {
      do
        v17 = a2[++v15] == 0;
      while ( !v17 );
      v19 = 2 * v15 + 2;
    }
    else
    {
      a2 = &word_180032B28;
      v19 = 2;
    }
    v48 = v19;
    v47 = a2;
    v45 = &v39;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v49 = 0;
    v46 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v42 = byte_180035CBB;
    UserData.Reserved = 2;
    v43 = 83;
    v44 = 1;
    v34 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
  }
  if ( !a6 )
    ++*((_DWORD *)this + 60);
  if ( v38 )
LABEL_77:
    *((_DWORD *)this + 60) = 1;
  return 0;
}

```

## disassembly

```asm
0x180008620  push    rbp
0x180008622  push    rbx
0x180008623  push    r12
0x180008625  push    r13
0x180008627  push    r14
0x180008629  lea     rbp, [rsp-27h]
0x18000862e  sub     rsp, 100h
0x180008635  mov     rax, cs:__security_cookie
0x18000863c  xor     rax, rsp
0x18000863f  mov     [rbp+47h+var_50], rax
0x180008643  mov     r10, [rcx+40h]
0x180008647  lea     r13, [rcx+40h]
0x18000864b  mov     [rsp+120h+var_DC], r8d
0x180008650  mov     r14, r9
0x180008653  mov     [rsp+120h+var_D4], 49h ; 'I'
0x18000865b  mov     r11d, r8d
0x18000865e  mov     [rsp+120h+var_D0], 0
0x180008666  mov     r12, rdx
0x180008669  mov     rbx, rcx
0x18000866c  test    r10, r10
0x18000866f  jnz     short loc_18000867A
0x180008671  mov     rcx, [rcx+150h]
0x180008678  jmp     short loc_18000869D
0x18000867a  mov     r10, [r10+78h]
0x18000867e  test    r10, r10
0x180008681  jz      short loc_180008671
0x180008683  mov     rcx, r10; this
0x180008686  call    ?IsDataTypeXML@CSyncMLItem@@QEBAHXZ; CSyncMLItem::IsDataTypeXML(void)
0x18000868b  test    eax, eax
0x18000868d  jz      short loc_180008696
0x18000868f  cmp     dword ptr [r10+70h], 0
0x180008694  ja      short loc_1800086BA
0x180008696  mov     rcx, [rbx+150h]; hMem
0x18000869d  call    cs:__imp_LocalFree
0x1800086a4  nop     dword ptr [rax+rax+00h]
0x1800086a9  mov     r11d, [rsp+120h+var_DC]
0x1800086ae  xor     r10d, r10d
0x1800086b1  mov     [rbx+150h], r10
0x1800086b8  jmp     short loc_1800086BD
0x1800086ba  xor     r10d, r10d
0x1800086bd  cmp     dword ptr [rbx+0F0h], 0
0x1800086c4  mov     eax, cs:dword_18003E048
0x1800086ca  mov     [rsp+120h+var_28], rsi
0x1800086d2  mov     [rsp+120h+var_30], rdi
0x1800086da  mov     [rsp+120h+var_38], r15
0x1800086e2  jbe     loc_180008836
0x1800086e8  cmp     eax, 5
0x1800086eb  jbe     loc_18000881A
0x1800086f1  mov     eax, [rbp+47h+arg_20]
0x1800086f4  lea     rdx, word_180032B28
0x1800086fb  mov     [rsp+120h+var_DC], eax
0x1800086ff  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008706  mov     [rsp+120h+var_CC], r11d
0x18000870b  test    r14, r14
0x18000870e  jz      short loc_180008729
0x180008710  mov     rcx, rax
0x180008713  cmp     word ptr [r14+rcx*2+2], 0
0x18000871a  lea     rcx, [rcx+1]
0x18000871e  jnz     short loc_180008713
0x180008720  lea     ecx, ds:2[rcx*2]
0x180008727  jmp     short loc_180008731
0x180008729  mov     r14, rdx
0x18000872c  mov     ecx, 2
0x180008731  mov     [rbp+47h+var_58], ecx
0x180008734  lea     rcx, [rsp+120h+var_DC]
0x180008739  mov     [rbp+47h+var_70], rcx
0x18000873d  mov     [rbp+47h+var_60], r14
0x180008741  mov     [rbp+47h+var_54], r10d
0x180008745  mov     [rbp+47h+var_68], 4
0x18000874d  test    r12, r12
0x180008750  jz      short loc_180008768
0x180008752  cmp     word ptr [r12+rax*2+2], 0
0x180008759  lea     rax, [rax+1]
0x18000875d  jnz     short loc_180008752
0x18000875f  lea     eax, ds:2[rax*2]
0x180008766  jmp     short loc_180008770
0x180008768  mov     r12, rdx
0x18000876b  mov     eax, 2
0x180008770  mov     [rbp+47h+var_78], eax
0x180008773  lea     rcx, _TraceLoggingMetadata
0x18000877a  lea     rax, [rsp+120h+var_CC]
0x18000877f  mov     [rbp+47h+var_80], r12
0x180008783  mov     [rbp+47h+var_90], rax
0x180008787  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x18000878c  movzx   eax, cs:word_180035CB1
0x180008793  xor     r9d, r9d; RelatedActivityId
0x180008796  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x180008799  xor     r8d, r8d; ActivityId
0x18000879c  mov     rax, cs:off_18003E050
0x1800087a3  mov     [rbp+47h+var_B0.Ptr], rax
0x1800087a7  mov     [rbp+47h+var_74], r10d
0x1800087ab  mov     [rbp+47h+var_88], 4
0x1800087b3  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x1800087bb  mov     [rbp+47h+EventDescriptor.Keyword], r10
0x1800087bf  movzx   eax, word ptr [rax]
0x1800087c2  mov     [rbp+47h+var_B0.Size], eax
0x1800087c5  lea     rax, byte_180035CBB
0x1800087cc  mov     [rbp+47h+var_A0], rax
0x1800087d0  lea     rax, _TraceLoggingMetadataEnd
0x1800087d7  sub     eax, ecx
0x1800087d9  mov     dword ptr [rbp+47h+var_B0.0Ch], 2
0x1800087e0  mov     [rbp+47h+var_98], 53h ; 'S'
0x1800087e7  mov     [rbp+47h+var_94], 1
0x1800087ee  mov     [rsp+120h+var_E0], eax
0x1800087f2  mov     eax, [rsp+120h+var_E0]
0x1800087f6  mov     rcx, cs:RegHandle; RegHandle
0x1800087fd  lea     rax, [rbp+47h+var_B0]
0x180008801  mov     [rsp+120h+UserData], rax; UserData
0x180008806  mov     [rsp+120h+UserDataCount], 6; UserDataCount
0x18000880e  call    cs:__imp_EventWriteTransfer
0x180008815  nop     dword ptr [rax+rax+00h]
0x18000881a  cmp     [rbp+47h+arg_28], 0
0x18000881e  jnz     short loc_180008826
0x180008820  inc     dword ptr [rbx+0F0h]
0x180008826  cmp     [rsp+120h+var_D0], 0
0x18000882b  jnz     loc_180008CE8
0x180008831  jmp     loc_180008CF2
0x180008836  lea     rdi, _TraceLoggingMetadataEnd
0x18000883d  mov     esi, r10d
0x180008840  lea     r9, _TraceLoggingMetadata
0x180008847  cmp     eax, 5
0x18000884a  jbe     loc_180008982
0x180008850  mov     r15d, [rbp+47h+arg_20]
0x180008854  lea     rdx, word_180032B28
0x18000885b  mov     [rsp+120h+var_E0], r15d
0x180008860  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008867  mov     [rsp+120h+var_CC], r11d
0x18000886c  test    r14, r14
0x18000886f  jz      short loc_180008896
0x180008871  mov     r8, r14
0x180008874  mov     rcx, rax
0x180008877  nop     word ptr [rax+rax+00000000h]
0x180008880  cmp     word ptr [r14+rcx*2+2], 0
0x180008887  lea     rcx, [rcx+1]
0x18000888b  jnz     short loc_180008880
0x18000888d  lea     ecx, ds:2[rcx*2]
0x180008894  jmp     short loc_18000889E
0x180008896  mov     r8, rdx
0x180008899  mov     ecx, 2
0x18000889e  mov     [rbp+47h+var_58], ecx
0x1800088a1  lea     rcx, [rsp+120h+var_E0]
0x1800088a6  mov     [rbp+47h+var_70], rcx
0x1800088aa  mov     [rbp+47h+var_60], r8
0x1800088ae  mov     [rbp+47h+var_54], r10d
0x1800088b2  mov     [rbp+47h+var_68], 4
0x1800088ba  test    r12, r12
0x1800088bd  jz      short loc_1800088D8
0x1800088bf  mov     rdx, r12
0x1800088c2  cmp     word ptr [r12+rax*2+2], 0
0x1800088c9  lea     rax, [rax+1]
0x1800088cd  jnz     short loc_1800088C2
0x1800088cf  lea     eax, ds:2[rax*2]
0x1800088d6  jmp     short loc_1800088DD
0x1800088d8  mov     eax, 2
0x1800088dd  mov     [rbp+47h+var_78], eax
0x1800088e0  xor     r8d, r8d; ActivityId
0x1800088e3  mov     [rbp+47h+var_80], rdx
0x1800088e7  lea     rax, [rsp+120h+var_CC]
0x1800088ec  mov     [rbp+47h+var_90], rax
0x1800088f0  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x1800088f5  movzx   eax, cs:word_180036041
0x1800088fc  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x1800088ff  mov     rax, cs:off_18003E050
0x180008906  mov     [rbp+47h+var_B0.Ptr], rax
0x18000890a  mov     [rbp+47h+var_74], r10d
0x18000890e  mov     [rbp+47h+var_88], 4
0x180008916  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x18000891e  mov     [rbp+47h+EventDescriptor.Keyword], r10
0x180008922  movzx   eax, word ptr [rax]
0x180008925  mov     [rbp+47h+var_B0.Size], eax
0x180008928  lea     rax, byte_18003604B
0x18000892f  mov     [rbp+47h+var_A0], rax
0x180008933  mov     rax, rdi
0x180008936  sub     eax, r9d
0x180008939  mov     dword ptr [rbp+47h+var_B0.0Ch], 2
0x180008940  mov     [rbp+47h+var_98], 54h ; 'T'
0x180008947  xor     r9d, r9d; RelatedActivityId
0x18000894a  mov     [rbp+47h+var_94], 1
0x180008951  mov     [rsp+120h+var_D8], eax
0x180008955  mov     eax, [rsp+120h+var_D8]
0x180008959  mov     rcx, cs:RegHandle; RegHandle
0x180008960  lea     rax, [rbp+47h+var_B0]
0x180008964  mov     [rsp+120h+UserData], rax; UserData
0x180008969  mov     [rsp+120h+UserDataCount], 6; UserDataCount
0x180008971  call    cs:__imp_EventWriteTransfer
0x180008978  nop     dword ptr [rax+rax+00h]
0x18000897d  xor     r10d, r10d
0x180008980  jmp     short loc_180008986
0x180008982  mov     r15d, [rbp+47h+arg_20]
0x180008986  cmp     qword ptr [r13+0], 0
0x18000898b  jnz     loc_180008B9F
0x180008991  test    r14, r14
0x180008994  jz      loc_180008C0A
0x18000899a  cmp     r10w, [r14]
0x18000899e  jz      loc_180008C0A
0x1800089a4  mov     esi, r15d
0x1800089a7  mov     eax, 0FFFFFFFFh
0x1800089ac  cmp     rsi, rax
0x1800089af  jnz     short loc_1800089DC
0x1800089b1  mov     esi, 7FFFFFFFh
0x1800089b6  mov     rax, r14
0x1800089b9  mov     ecx, esi
0x1800089bb  nop     dword ptr [rax+rax+00h]
0x1800089c0  cmp     word ptr [rax], 0
0x1800089c4  jz      short loc_1800089D0
0x1800089c6  add     rax, 2
0x1800089ca  sub     rcx, 1
0x1800089ce  jnz     short loc_1800089C0
0x1800089d0  sub     rsi, rcx
0x1800089d3  test    rcx, rcx
0x1800089d6  cmovz   rsi, r10
0x1800089da  jz      short loc_180008A29
0x1800089dc  mov     edi, r10d
0x1800089df  mov     eax, edi
0x1800089e1  lea     rcx, ?c_rgszSyncMLElem@@3PAPEBGA; ushort const * near * c_rgszSyncMLElem
0x1800089e8  mov     rdx, [rcx+rax*8]
0x1800089ec  lea     r15, [rcx+rax*8]
0x1800089f0  mov     r8, rsi
0x1800089f3  mov     rcx, r14
0x1800089f6  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x1800089fd  nop     dword ptr [rax+rax+00h]
0x180008a02  xor     r10d, r10d
0x180008a05  test    eax, eax
0x180008a07  jnz     short loc_180008A17
0x180008a09  mov     rcx, [r15]
0x180008a0c  cmp     r10w, [rcx+rsi*2]
0x180008a11  jz      loc_180008AF8
0x180008a17  inc     edi
0x180008a19  cmp     edi, 49h ; 'I'
0x180008a1c  jl      short loc_1800089DF
0x180008a1e  mov     r15d, [rbp+47h+arg_20]
0x180008a22  lea     rdi, _TraceLoggingMetadataEnd
0x180008a29  mov     eax, [rbx+0E0h]
0x180008a2f  dec     eax
0x180008a31  cmp     dword ptr [rbx+rax*4+60h], 2
0x180008a36  jz      loc_180008B6D
0x180008a3c  mov     eax, cs:dword_18003E048
0x180008a42  mov     esi, 82AA0001h
0x180008a47  cmp     eax, 5
0x180008a4a  jbe     loc_180008C32
0x180008a50  lea     rax, [rsp+120h+var_D8]
0x180008a55  mov     [rsp+120h+var_D8], 82AA0001h
0x180008a5d  mov     [rbp+47h+var_90], rax
0x180008a61  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x180008a66  movzx   eax, cs:word_180035F56
0x180008a6d  xor     r9d, r9d; RelatedActivityId
0x180008a70  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x180008a73  xor     r8d, r8d; ActivityId
0x180008a76  mov     rax, cs:off_18003E050
0x180008a7d  mov     [rbp+47h+var_B0.Ptr], rax
0x180008a81  mov     [rbp+47h+var_88], 4
0x180008a89  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x180008a91  mov     [rbp+47h+EventDescriptor.Keyword], r10
0x180008a95  movzx   eax, word ptr [rax]
0x180008a98  mov     [rbp+47h+var_B0.Size], eax
0x180008a9b  lea     rax, qword_180035F60
0x180008aa2  mov     [rbp+47h+var_A0], rax
0x180008aa6  mov     rax, rdi
0x180008aa9  mov     dword ptr [rbp+47h+var_B0.0Ch], 2
0x180008ab0  lea     rdi, _TraceLoggingMetadata
0x180008ab7  sub     eax, edi
0x180008ab9  mov     [rbp+47h+var_98], 1Bh
0x180008ac0  mov     [rbp+47h+var_94], 1
0x180008ac7  mov     [rsp+120h+var_E0], eax
0x180008acb  mov     eax, [rsp+120h+var_E0]
0x180008acf  mov     rcx, cs:RegHandle; RegHandle
0x180008ad6  lea     rax, [rbp+47h+var_B0]
0x180008ada  mov     [rsp+120h+UserData], rax; UserData
0x180008adf  mov     [rsp+120h+UserDataCount], 3; UserDataCount
0x180008ae7  call    cs:__imp_EventWriteTransfer
0x180008aee  nop     dword ptr [rax+rax+00h]
0x180008af3  jmp     loc_180008C39
0x180008af8  mov     ecx, edi
0x180008afa  mov     [rsp+120h+var_D4], edi
0x180008afe  call    ?IsCmdType@CSyncMLCmd@@SAHW4SyncMLElemType@@@Z; CSyncMLCmd::IsCmdType(SyncMLElemType)
0x180008b03  test    eax, eax
0x180008b05  jz      short loc_180008B49
0x180008b07  mov     [rsp+120h+UserData], r13
0x180008b0c  xor     r9d, r9d
0x180008b0f  mov     r8, rbx
0x180008b12  mov     [rsp+120h+UserDataCount], r10d
0x180008b17  xor     edx, edx
0x180008b19  mov     ecx, edi
0x180008b1b  call    ?CreateCmd@CSyncMLCmd@@SAJW4SyncMLElemType@@PEAV1@PEAVCSyncMLDPU@@PEBGKPEAPEAV1@@Z; CSyncMLCmd::CreateCmd(SyncMLElemType,CSyncMLCmd *,CSyncMLDPU *,ushort const *,ulong,CSyncMLCmd * *)
0x180008b20  mov     esi, eax
0x180008b22  test    eax, eax
0x180008b24  js      loc_180008C32
0x180008b2a  cmp     dword ptr [rbx+24h], 0
0x180008b2e  jz      short loc_180008B93
0x180008b30  cmp     [rsp+120h+var_D4], 19h
0x180008b35  jz      short loc_180008B93
0x180008b37  mov     rcx, [r13+0]
0x180008b3b  cmp     dword ptr [rcx+38h], 0
0x180008b3f  jl      short loc_180008B93
0x180008b41  mov     eax, [rbx+30h]
0x180008b44  mov     [rcx+38h], eax
0x180008b47  jmp     short loc_180008B93
0x180008b49  mov     esi, r10d
0x180008b4c  test    edi, edi
0x180008b4e  jz      short loc_180008B9F
  ... truncated ...
```
