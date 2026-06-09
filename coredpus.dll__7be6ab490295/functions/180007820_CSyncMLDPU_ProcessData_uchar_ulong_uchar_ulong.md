# CSyncMLDPU::ProcessData(uchar *,ulong,uchar * *,ulong *)

- ea: `0x180007820`
- end: `0x180007e76`
- name: `?ProcessData@CSyncMLDPU@@UEAAJPEAEKPEAPEAEPEAK@Z`
- size: `1622`
- prototype: `__int64 __fastcall(CSyncMLDPU *this, const BYTE **, int, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004f00`
- `0x180005370`
- `0x180007820`
- `0x180007e80`
- `0x180008620`
- `0x180014330`
- `0x1800194e4`
- `0x18001d8e4`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180007971`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180007989`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180007971`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180007989`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007956`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007c6f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007e0d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007956`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007c6f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007e0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000785d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000785d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c83`
- `XmlLite!CreateXmlReader` at `0x180007a3d`
- `XmlLite!CreateXmlReader` at `0x180007a3d`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x180007a98`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x180007a98`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800079c4`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800079c4`

## pseudocode

```c
__int64 __fastcall CSyncMLDPU::ProcessData(CSyncMLDPU *this, const BYTE **a2, int a3, unsigned __int8 **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r13
  IUnknown *v8; // r12
  const BYTE *v9; // rbx
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  HRESULT XmlReader; // ebx
  _QWORD *v13; // rsi
  int v14; // eax
  int started; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v19; // r14d
  CSyncMLDPU *v20; // rcx
  int v21; // [rsp+30h] [rbp-61h] BYREF
  int v22; // [rsp+34h] [rbp-5Dh] BYREF
  unsigned int v23; // [rsp+38h] [rbp-59h] BYREF
  __int64 v24; // [rsp+40h] [rbp-51h] BYREF
  int v25; // [rsp+48h] [rbp-49h] BYREF
  int v26; // [rsp+4Ch] [rbp-45h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-41h] BYREF
  unsigned __int16 *v28; // [rsp+60h] [rbp-31h] BYREF
  unsigned __int16 *v29; // [rsp+68h] [rbp-29h] BYREF
  unsigned __int16 *v30; // [rsp+70h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp-19h] BYREF
  char *v32; // [rsp+88h] [rbp-9h]
  int v33; // [rsp+90h] [rbp-1h]
  int v34; // [rsp+94h] [rbp+3h]
  unsigned int *v35; // [rsp+98h] [rbp+7h]
  __int64 v36; // [rsp+A0h] [rbp+Fh]

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 472);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 472));
  v8 = 0;
  v25 = 0;
  v29 = 0;
  v22 = 0;
  v28 = 0;
  v21 = 0;
  v30 = 0;
  v26 = 0;
  if ( !a2 || a3 != 48 )
    goto LABEL_52;
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v23 = 48;
    v35 = &v23;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v36 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v32 = (char *)&dword_18003614C;
    UserData.Reserved = 2;
    v33 = 26;
    v34 = 1;
    LODWORD(v24) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  v9 = *a2;
  if ( !*a2 )
  {
LABEL_52:
    XmlReader = -2147024809;
    goto LABEL_29;
  }
  if ( (unsigned int)_o_iswspace(*(unsigned __int16 *)v9) )
  {
    do
    {
      v10 = *((unsigned __int16 *)v9 + 1);
      v9 += 2;
    }
    while ( (unsigned int)_o_iswspace(v10) );
  }
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)&v9[2 * v11] );
  v24 = 0;
  if ( !is_mul_ok(v11, 2u) )
  {
    XmlReader = -2147024362;
    goto LABEL_29;
  }
  v8 = (IUnknown *)SHCreateMemStream(v9, 2 * (int)v11);
  if ( !v8 )
  {
    XmlReader = -2147024882;
    goto LABEL_29;
  }
  if ( !*((_DWORD *)this + 6) )
  {
    XmlReader = -2102788096;
    goto LABEL_29;
  }
  XmlReader = CSyncMLDPU::BeginPkgProcessing(this, (struct tagSyncMLDPUParams *)a2);
  if ( XmlReader >= 0 )
  {
    v13 = (_QWORD *)((char *)this + 272);
    *((_DWORD *)this + 9) = *((_DWORD *)a2 + 4);
    *((_DWORD *)this + 12) = *((_DWORD *)a2 + 9);
    *((_DWORD *)this + 110) = *((_DWORD *)a2 + 10);
    CSyncMLDPU::s_dwCurrServerMsgID = *((_DWORD *)a2 + 2);
    XmlReader = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, (void **)this + 34, 0);
    if ( XmlReader >= 0 )
    {
      XmlReader = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v13 + 40LL))(*v13, 4, 0);
      if ( XmlReader >= 0 )
      {
        XmlReader = CreateXmlReaderInputWithEncodingName(v8, 0, L"UTF-16", 0, 0, (IXmlReaderInput **)this + 35);
        if ( XmlReader >= 0 )
        {
          XmlReader = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v13 + 24LL))(*v13, *((_QWORD *)this + 35));
          if ( XmlReader >= 0 )
          {
            while ( 1 )
            {
              while ( 1 )
              {
                v14 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v13 + 48LL))(*v13, &v25);
                XmlReader = v14;
                if ( v14 )
                {
                  if ( *((_DWORD *)this + 7) )
                  {
                    if ( (unsigned int)dword_18003E048 > 2 )
                    {
                      *(_DWORD *)&EventDescriptor.Level = 2;
                      UserData.Ptr = (ULONGLONG)off_18003E050;
                      *(_DWORD *)&EventDescriptor.Id = 184549376;
                      EventDescriptor.Keyword = 0;
                      UserData.Size = (unsigned __int16)*off_18003E050;
                      v32 = byte_180035C95;
                      UserData.Reserved = 2;
                      v33 = 26;
                      v34 = 1;
                      LODWORD(v24) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
                    }
LABEL_49:
                    XmlReader = CSyncMLDPU::ExecuteAllCommands(this, (struct tagSyncMLDPUParams *const)a2);
                    if ( XmlReader >= 0 )
                      XmlReader = CSyncMLDPU::EndPkgProcessing(v20);
                  }
                  else if ( v14 >= 0 )
                  {
                    goto LABEL_49;
                  }
                  goto LABEL_29;
                }
                if ( v25 != 1 )
                  break;
                v19 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 160LL))(*v13);
                XmlReader = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **, int *))(*(_QWORD *)*v13 + 104LL))(
                              *v13,
                              &v29,
                              &v22);
                if ( XmlReader < 0 )
                  goto LABEL_29;
                XmlReader = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **, int *))(*(_QWORD *)*v13 + 112LL))(
                              *v13,
                              &v28,
                              &v21);
                if ( XmlReader < 0 )
                  goto LABEL_29;
                started = CSyncMLDPU::startElement(this, v29, v22, v28, v21, v19);
LABEL_28:
                XmlReader = started;
                if ( started < 0 )
                  goto LABEL_29;
              }
              if ( v25 == 3 || v25 == 4 )
              {
                XmlReader = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **, int *))(*(_QWORD *)*v13 + 128LL))(
                              *v13,
                              &v30,
                              &v26);
                if ( XmlReader < 0 )
                  break;
                started = CSyncMLDPU::characters(this, v30, v26);
                goto LABEL_28;
              }
              if ( v25 == 15 )
              {
                XmlReader = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **, int *))(*(_QWORD *)*v13 + 104LL))(
                              *v13,
                              &v29,
                              &v22);
                if ( XmlReader < 0 )
                  break;
                XmlReader = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **, int *))(*(_QWORD *)*v13 + 112LL))(
                              *v13,
                              &v28,
                              &v21);
                if ( XmlReader < 0 )
                  break;
                started = CSyncMLDPU::endElement(this, v29, v22, v28, v21);
                goto LABEL_28;
              }
            }
          }
        }
      }
    }
  }
LABEL_29:
  v16 = *((_QWORD *)this + 34);
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    *((_QWORD *)this + 34) = 0;
  }
  if ( v8 )
    ((void (__fastcall *)(IUnknown *))v8->lpVtbl->Release)(v8);
  v17 = *((_QWORD *)this + 35);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    *((_QWORD *)this + 35) = 0;
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    LODWORD(v24) = XmlReader;
    v35 = (unsigned int *)&v24;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v36 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v32 = byte_1800361D1;
    UserData.Reserved = 2;
    v33 = 41;
    v34 = 1;
    v23 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  if ( v4 )
    LeaveCriticalSection(v4);
  return (unsigned int)XmlReader;
}

```

## disassembly

```asm
0x180007820  mov     [rsp-8+arg_10], rbx
0x180007825  push    rbp
0x180007826  push    rsi
0x180007827  push    rdi
0x180007828  push    r12
0x18000782a  push    r13
0x18000782c  push    r14
0x18000782e  push    r15
0x180007830  lea     rbp, [rsp-1Fh]
0x180007835  sub     rsp, 0B0h
0x18000783c  mov     rax, cs:__security_cookie
0x180007843  xor     rax, rsp
0x180007846  mov     [rbp+4Fh+var_38], rax
0x18000784a  lea     r13, [rcx+1D8h]
0x180007851  mov     rdi, rcx
0x180007854  mov     rcx, r13; lpCriticalSection
0x180007857  mov     ebx, r8d
0x18000785a  mov     r15, rdx
0x18000785d  call    cs:__imp_EnterCriticalSection
0x180007864  nop     dword ptr [rax+rax+00h]
0x180007869  xor     r12d, r12d
0x18000786c  mov     [rbp+4Fh+var_98], 0
0x180007873  mov     [rbp+4Fh+var_78], 0
0x18000787b  lea     rsi, _TraceLoggingMetadataEnd
0x180007882  mov     [rbp+4Fh+var_AC], 0
0x180007889  lea     r14, _TraceLoggingMetadata
0x180007890  mov     [rbp+4Fh+var_80], 0
0x180007898  mov     [rbp+4Fh+var_B0], 0
0x18000789f  mov     [rbp+4Fh+var_70], 0
0x1800078a7  mov     [rbp+4Fh+var_94], 0
0x1800078ae  test    r15, r15
0x1800078b1  jz      loc_180007E6C
0x1800078b7  cmp     ebx, 30h ; '0'
0x1800078ba  jnz     loc_180007E6C
0x1800078c0  mov     eax, cs:dword_18003E048
0x1800078c6  cmp     eax, 5
0x1800078c9  jbe     loc_180007962
0x1800078cf  lea     rax, [rbp+4Fh+var_A8]
0x1800078d3  mov     [rbp+4Fh+var_A8], ebx
0x1800078d6  mov     [rbp+4Fh+var_48], rax
0x1800078da  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x1800078de  movzx   eax, cs:word_180036142
0x1800078e5  xor     r9d, r9d; RelatedActivityId
0x1800078e8  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x1800078eb  xor     r8d, r8d; ActivityId
0x1800078ee  mov     rax, cs:off_18003E050
0x1800078f5  mov     [rbp+4Fh+var_68.Ptr], rax
0x1800078f9  mov     [rbp+4Fh+var_40], 4
0x180007901  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 0B000000h
0x180007908  mov     [rbp+4Fh+EventDescriptor.Keyword], r12
0x18000790c  movzx   eax, word ptr [rax]
0x18000790f  mov     [rbp+4Fh+var_68.Size], eax
0x180007912  lea     rax, dword_18003614C
0x180007919  mov     [rbp+4Fh+var_58], rax
0x18000791d  mov     rax, rsi
0x180007920  sub     eax, r14d
0x180007923  mov     dword ptr [rbp+4Fh+var_68.0Ch], 2
0x18000792a  mov     [rbp+4Fh+var_50], 1Ah
0x180007931  mov     [rbp+4Fh+var_4C], 1
0x180007938  mov     dword ptr [rbp+4Fh+var_A0], eax
0x18000793b  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x18000793e  mov     rcx, cs:RegHandle; RegHandle
0x180007945  lea     rax, [rbp+4Fh+var_68]
0x180007949  mov     [rsp+0E0h+UserData], rax; UserData
0x18000794e  mov     [rsp+0E0h+UserDataCount], 3; UserDataCount
0x180007956  call    cs:__imp_EventWriteTransfer
0x18000795d  nop     dword ptr [rax+rax+00h]
0x180007962  mov     rbx, [r15]
0x180007965  test    rbx, rbx
0x180007968  jz      loc_180007E6C
0x18000796e  movzx   ecx, word ptr [rbx]
0x180007971  call    cs:__imp__o_iswspace
0x180007978  nop     dword ptr [rax+rax+00h]
0x18000797d  test    eax, eax
0x18000797f  jz      short loc_180007999
0x180007981  movzx   ecx, word ptr [rbx+2]
0x180007985  add     rbx, 2
0x180007989  call    cs:__imp__o_iswspace
0x180007990  nop     dword ptr [rax+rax+00h]
0x180007995  test    eax, eax
0x180007997  jnz     short loc_180007981
0x180007999  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800079a0  inc     rcx
0x1800079a3  cmp     [rbx+rcx*2], r12w
0x1800079a8  jnz     short loc_1800079A0
0x1800079aa  mov     eax, 2
0x1800079af  mov     [rbp+4Fh+var_A0], r12
0x1800079b3  mul     rcx
0x1800079b6  test    rdx, rdx
0x1800079b9  jnz     loc_180007E62
0x1800079bf  mov     edx, eax; cbInit
0x1800079c1  mov     rcx, rbx; pInit
0x1800079c4  call    cs:__imp_SHCreateMemStream
0x1800079cb  nop     dword ptr [rax+rax+00h]
0x1800079d0  mov     r12, rax
0x1800079d3  test    rax, rax
0x1800079d6  jnz     short loc_1800079E2
0x1800079d8  mov     ebx, 8007000Eh
0x1800079dd  jmp     loc_180007B7D
0x1800079e2  cmp     dword ptr [rdi+18h], 0
0x1800079e6  jnz     short loc_1800079F2
0x1800079e8  mov     ebx, 82AA0000h
0x1800079ed  jmp     loc_180007B7D
0x1800079f2  mov     rdx, r15; struct tagSyncMLDPUParams *
0x1800079f5  mov     rcx, rdi; this
0x1800079f8  call    ?BeginPkgProcessing@CSyncMLDPU@@AEAAJPEAUtagSyncMLDPUParams@@@Z; CSyncMLDPU::BeginPkgProcessing(tagSyncMLDPUParams *)
0x1800079fd  mov     ebx, eax
0x1800079ff  test    eax, eax
0x180007a01  js      loc_180007B7D
0x180007a07  mov     eax, [r15+10h]
0x180007a0b  lea     rsi, [rdi+110h]
0x180007a12  mov     [rdi+24h], eax
0x180007a15  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180007a1c  mov     eax, [r15+24h]
0x180007a20  xor     r8d, r8d; pMalloc
0x180007a23  mov     [rdi+30h], eax
0x180007a26  mov     rdx, rsi; ppvObject
0x180007a29  mov     eax, [r15+28h]
0x180007a2d  mov     [rdi+1B8h], eax
0x180007a33  mov     eax, [r15+8]
0x180007a37  mov     cs:?s_dwCurrServerMsgID@CSyncMLDPU@@0KA, eax; ulong CSyncMLDPU::s_dwCurrServerMsgID
0x180007a3d  call    cs:__imp_CreateXmlReader
0x180007a44  nop     dword ptr [rax+rax+00h]
0x180007a49  mov     ebx, eax
0x180007a4b  test    eax, eax
0x180007a4d  js      loc_180007B76
0x180007a53  mov     rcx, [rsi]
0x180007a56  xor     r8d, r8d
0x180007a59  mov     edx, 4
0x180007a5e  mov     rax, [rcx]
0x180007a61  mov     rax, [rax+28h]
0x180007a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a6a  mov     ebx, eax
0x180007a6c  test    eax, eax
0x180007a6e  js      loc_180007B76
0x180007a74  lea     r14, [rdi+118h]
0x180007a7b  xor     r9d, r9d; fEncodingHint
0x180007a7e  mov     [rsp+0E0h+UserData], r14; ppInput
0x180007a83  lea     r8, pwszEncodingName; "UTF-16"
0x180007a8a  xor     edx, edx; pMalloc
0x180007a8c  mov     qword ptr [rsp+0E0h+UserDataCount], 0; pwszBaseUri
0x180007a95  mov     rcx, r12; pInputStream
0x180007a98  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x180007a9f  nop     dword ptr [rax+rax+00h]
0x180007aa4  mov     ebx, eax
0x180007aa6  test    eax, eax
0x180007aa8  js      loc_180007B6F
0x180007aae  mov     rcx, [rsi]
0x180007ab1  mov     rdx, [r14]
0x180007ab4  mov     rax, [rcx]
0x180007ab7  mov     rax, [rax+18h]
0x180007abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ac0  mov     ebx, eax
0x180007ac2  test    eax, eax
0x180007ac4  js      loc_180007B6F
0x180007aca  nop     word ptr [rax+rax+00h]
0x180007ad0  mov     rcx, [rsi]
0x180007ad3  lea     rdx, [rbp+4Fh+var_98]
0x180007ad7  mov     rax, [rcx]
0x180007ada  mov     rax, [rax+30h]
0x180007ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ae3  mov     ebx, eax
0x180007ae5  test    eax, eax
0x180007ae7  jnz     loc_180007D6E
0x180007aed  mov     ecx, [rbp+4Fh+var_98]
0x180007af0  sub     ecx, 1
0x180007af3  jz      loc_180007CF2
0x180007af9  sub     ecx, 2
0x180007afc  jz      loc_180007CB9
0x180007b02  sub     ecx, 1
0x180007b05  jz      loc_180007CB9
0x180007b0b  cmp     ecx, 0Bh
0x180007b0e  jnz     short loc_180007AD0
0x180007b10  mov     rcx, [rsi]
0x180007b13  lea     r8, [rbp+4Fh+var_AC]
0x180007b17  lea     rdx, [rbp+4Fh+var_78]
0x180007b1b  mov     rax, [rcx]
0x180007b1e  mov     rax, [rax+68h]
0x180007b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b27  mov     ebx, eax
0x180007b29  test    eax, eax
0x180007b2b  js      short loc_180007B6F
0x180007b2d  mov     rcx, [rsi]
0x180007b30  lea     r8, [rbp+4Fh+var_B0]
0x180007b34  lea     rdx, [rbp+4Fh+var_80]
0x180007b38  mov     rax, [rcx]
0x180007b3b  mov     rax, [rax+70h]
0x180007b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b44  mov     ebx, eax
0x180007b46  test    eax, eax
0x180007b48  js      short loc_180007B6F
0x180007b4a  mov     eax, [rbp+4Fh+var_B0]
0x180007b4d  mov     rcx, rdi; this
0x180007b50  mov     r9, [rbp+4Fh+var_80]; unsigned __int16 *
0x180007b54  mov     r8d, [rbp+4Fh+var_AC]; int
0x180007b58  mov     rdx, [rbp+4Fh+var_78]; unsigned __int16 *
0x180007b5c  mov     [rsp+0E0h+UserDataCount], eax; int
0x180007b60  call    ?endElement@CSyncMLDPU@@AEAAJPEBGH0H@Z; CSyncMLDPU::endElement(ushort const *,int,ushort const *,int)
0x180007b65  mov     ebx, eax
0x180007b67  test    eax, eax
0x180007b69  jns     loc_180007AD0
0x180007b6f  lea     r14, _TraceLoggingMetadata
0x180007b76  lea     rsi, _TraceLoggingMetadataEnd
0x180007b7d  mov     rcx, [rdi+110h]
0x180007b84  test    rcx, rcx
0x180007b87  jz      short loc_180007BA0
0x180007b89  mov     rax, [rcx]
0x180007b8c  mov     rax, [rax+10h]
0x180007b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b95  mov     qword ptr [rdi+110h], 0
0x180007ba0  test    r12, r12
0x180007ba3  jz      short loc_180007BB5
0x180007ba5  mov     rax, [r12]
0x180007ba9  mov     rcx, r12
0x180007bac  mov     rax, [rax+10h]
0x180007bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bb5  mov     rcx, [rdi+118h]
0x180007bbc  test    rcx, rcx
0x180007bbf  jz      short loc_180007BD8
0x180007bc1  mov     rax, [rcx]
0x180007bc4  mov     rax, [rax+10h]
0x180007bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bcd  mov     qword ptr [rdi+118h], 0
0x180007bd8  mov     eax, cs:dword_18003E048
0x180007bde  cmp     eax, 5
0x180007be1  jbe     loc_180007C7B
0x180007be7  lea     rax, [rbp+4Fh+var_A0]
0x180007beb  mov     dword ptr [rbp+4Fh+var_A0], ebx
0x180007bee  mov     [rbp+4Fh+var_48], rax
0x180007bf2  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x180007bf6  movzx   eax, cs:word_1800361C7
0x180007bfd  sub     esi, r14d
0x180007c00  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x180007c03  xor     r9d, r9d; RelatedActivityId
0x180007c06  mov     rax, cs:off_18003E050
0x180007c0d  xor     r8d, r8d; ActivityId
0x180007c10  mov     [rbp+4Fh+var_68.Ptr], rax
0x180007c14  mov     [rbp+4Fh+var_40], 4
0x180007c1c  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 0B000000h
0x180007c23  mov     [rbp+4Fh+EventDescriptor.Keyword], 0
0x180007c2b  movzx   eax, word ptr [rax]
0x180007c2e  mov     [rbp+4Fh+var_68.Size], eax
0x180007c31  lea     rax, byte_1800361D1
0x180007c38  mov     [rbp+4Fh+var_58], rax
0x180007c3c  mov     dword ptr [rbp+4Fh+var_68.0Ch], 2
0x180007c43  mov     [rbp+4Fh+var_50], 29h ; ')'
0x180007c4a  mov     [rbp+4Fh+var_4C], 1
0x180007c51  mov     [rbp+4Fh+var_A8], esi
0x180007c54  mov     eax, [rbp+4Fh+var_A8]
0x180007c57  mov     rcx, cs:RegHandle; RegHandle
0x180007c5e  lea     rax, [rbp+4Fh+var_68]
0x180007c62  mov     [rsp+0E0h+UserData], rax; UserData
0x180007c67  mov     [rsp+0E0h+UserDataCount], 3; UserDataCount
0x180007c6f  call    cs:__imp_EventWriteTransfer
0x180007c76  nop     dword ptr [rax+rax+00h]
0x180007c7b  test    r13, r13
0x180007c7e  jz      short loc_180007C8F
0x180007c80  mov     rcx, r13; lpCriticalSection
0x180007c83  call    cs:__imp_LeaveCriticalSection
0x180007c8a  nop     dword ptr [rax+rax+00h]
0x180007c8f  mov     eax, ebx
0x180007c91  mov     rcx, [rbp+4Fh+var_38]
0x180007c95  xor     rcx, rsp; StackCookie
0x180007c98  call    __security_check_cookie
0x180007c9d  mov     rbx, [rsp+0E0h+arg_10]
0x180007ca5  add     rsp, 0B0h
0x180007cac  pop     r15
0x180007cae  pop     r14
0x180007cb0  pop     r13
0x180007cb2  pop     r12
0x180007cb4  pop     rdi
0x180007cb5  pop     rsi
0x180007cb6  pop     rbp
0x180007cb7  retn
0x180007cb9  mov     rcx, [rsi]
0x180007cbc  lea     r8, [rbp+4Fh+var_94]
0x180007cc0  lea     rdx, [rbp+4Fh+var_70]
0x180007cc4  mov     rax, [rcx]
0x180007cc7  mov     rax, [rax+80h]
0x180007cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cd3  mov     ebx, eax
0x180007cd5  test    eax, eax
0x180007cd7  js      loc_180007B6F
0x180007cdd  mov     r8d, [rbp+4Fh+var_94]; int
0x180007ce1  mov     rcx, rdi; this
0x180007ce4  mov     rdx, [rbp+4Fh+var_70]; unsigned __int16 *
0x180007ce8  call    ?characters@CSyncMLDPU@@AEAAJPEBGH@Z; CSyncMLDPU::characters(ushort const *,int)
0x180007ced  jmp     loc_180007B65
0x180007cf2  mov     rcx, [rsi]
0x180007cf5  mov     rax, [rcx]
0x180007cf8  mov     rax, [rax+0A0h]
0x180007cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d04  mov     rcx, [rsi]
0x180007d07  lea     r8, [rbp+4Fh+var_AC]
0x180007d0b  mov     r14d, eax
0x180007d0e  mov     rdx, [rcx]
0x180007d11  mov     rax, [rdx+68h]
0x180007d15  lea     rdx, [rbp+4Fh+var_78]
0x180007d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d1e  mov     ebx, eax
  ... truncated ...
```
