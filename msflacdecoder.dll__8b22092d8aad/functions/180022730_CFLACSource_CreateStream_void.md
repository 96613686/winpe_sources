# CFLACSource::CreateStream(void)

- ea: `0x180022730`
- end: `0x1800229d9`
- name: `?CreateStream@CFLACSource@@AEAAJXZ`
- size: `681`
- prototype: `__int64 __fastcall(CFLACSource *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180023d6c`

## callees

- `0x180020398`
- `0x180020484`
- `0x180021c70`
- `0x180022730`
- `0x18002833c`
- `0x180056010`

## import_xrefs

- `MFPlat!MFCreateStreamDescriptor` at `0x1800227d5`
- `MFPlat!MFCreateStreamDescriptor` at `0x1800227d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFLACSource::CreateStream(CFLACSource *this)
{
  struct CFLACStream *v2; // rdi
  int v4; // ecx
  __int64 v5; // rdx
  int v6; // ecx
  _QWORD v7[4]; // [rsp+30h] [rbp-20h] BYREF
  HRESULT v8; // [rsp+70h] [rbp+20h] BYREF
  IMFStreamDescriptor *ppDescriptor; // [rsp+78h] [rbp+28h] BYREF
  IMFMediaType *apMediaTypes; // [rsp+80h] [rbp+30h] BYREF
  struct CFLACStream *v11; // [rsp+88h] [rbp+38h] BYREF

  v8 = 0;
  v7[1] = this;
  v7[2] = &v8;
  apMediaTypes = 0;
  ppDescriptor = 0;
  v7[0] = 0;
  v2 = 0;
  v11 = 0;
  if ( *((_QWORD *)this + 22) )
    return 0;
  v8 = CFLACSource::CreateAudioMediaType(this, &apMediaTypes);
  if ( v8 >= 0 )
  {
    v8 = MFCreateStreamDescriptor(0, 1u, &apMediaTypes, &ppDescriptor);
    if ( v8 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_30;
      v5 = 240;
      goto LABEL_6;
    }
    v8 = ((__int64 (__fastcall *)(IMFStreamDescriptor *, _QWORD *))ppDescriptor->lpVtbl->GetMediaTypeHandler)(
           ppDescriptor,
           v7);
    if ( v8 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_30;
      v5 = 241;
      goto LABEL_6;
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaType *))(*(_QWORD *)v7[0] + 48LL))(v7[0], apMediaTypes);
    if ( v8 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_30;
      v5 = 242;
      goto LABEL_6;
    }
    v8 = ((__int64 (__fastcall *)(IMFStreamDescriptor *, __int64 *, _QWORD))ppDescriptor->lpVtbl->SetUINT32)(
           ppDescriptor,
           MF_SD_AUDIO_ENCODER_DELAY,
           0);
    if ( v8 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_30;
      v5 = 243;
      goto LABEL_6;
    }
    v8 = ((__int64 (__fastcall *)(IMFStreamDescriptor *, __int64 *, _QWORD))ppDescriptor->lpVtbl->SetUINT32)(
           ppDescriptor,
           MF_SD_AUDIO_ENCODER_PADDING,
           0);
    if ( v8 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_30;
      v5 = 244;
      goto LABEL_6;
    }
    v8 = CFLACStream::CreateInstance(this, ppDescriptor, &v11);
    if ( v8 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 245, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, this, v6);
      v2 = v11;
      goto LABEL_30;
    }
    v2 = v11;
    if ( v11 )
    {
      *((_QWORD *)this + 22) = v11;
      (*(void (__fastcall **)(struct CFLACStream *))(*(_QWORD *)v2 + 8LL))(v2);
      goto LABEL_30;
    }
    v8 = -2147024882;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v5 = 246;
      goto LABEL_6;
    }
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v5 = 239;
LABEL_6:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, this, v4);
  }
LABEL_30:
  if ( ppDescriptor )
  {
    ((void (__fastcall *)(IMFStreamDescriptor *))ppDescriptor->lpVtbl->Release)(ppDescriptor);
    ppDescriptor = 0;
  }
  if ( apMediaTypes )
  {
    ((void (__fastcall *)(IMFMediaType *))apMediaTypes->lpVtbl->Release)(apMediaTypes);
    apMediaTypes = 0;
  }
  if ( v7[0] )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v7[0] + 16LL))(v7[0]);
    v7[0] = 0;
  }
  if ( v2 )
    (*(void (__fastcall **)(struct CFLACStream *))(*(_QWORD *)v2 + 16LL))(v2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180022730  push    rbp
0x180022732  push    rbx
0x180022733  push    rdi
0x180022734  mov     rbp, rsp
0x180022737  sub     rsp, 50h
0x18002273b  mov     rbx, rcx
0x18002273e  mov     [rbp+arg_0], 0
0x180022745  mov     [rbp+var_18], rcx
0x180022749  lea     rax, [rbp+arg_0]
0x18002274d  mov     [rbp+var_10], rax
0x180022751  mov     [rbp+apMediaTypes], 0
0x180022759  mov     [rbp+ppDescriptor], 0
0x180022761  mov     [rbp+var_20], 0
0x180022769  xor     edi, edi
0x18002276b  mov     [rbp+arg_18], rdi
0x18002276f  cmp     [rcx+0B0h], rdi
0x180022776  jz      short loc_18002277F
0x180022778  xor     eax, eax
0x18002277a  jmp     loc_1800229D1
0x18002277f  lea     rdx, [rbp+apMediaTypes]; struct IMFMediaType **
0x180022783  call    ?CreateAudioMediaType@CFLACSource@@AEAAJPEAPEAUIMFMediaType@@@Z; CFLACSource::CreateAudioMediaType(IMFMediaType * *)
0x180022788  mov     ecx, eax
0x18002278a  mov     [rbp+arg_0], eax
0x18002278d  test    eax, eax
0x18002278f  jns     short loc_1800227C6
0x180022791  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180022796  cmp     al, 1
0x180022798  jb      loc_180022962
0x18002279e  mov     edx, 0EFh
0x1800227a3  mov     [rsp+50h+var_30], ecx
0x1800227a7  mov     r9, rbx
0x1800227aa  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x1800227b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227b8  mov     rcx, [rcx+10h]
0x1800227bc  call    WPP_SF_qd
0x1800227c1  jmp     loc_180022962
0x1800227c6  lea     r9, [rbp+ppDescriptor]; ppDescriptor
0x1800227ca  lea     r8, [rbp+apMediaTypes]; apMediaTypes
0x1800227ce  mov     edx, 1; cMediaTypes
0x1800227d3  xor     ecx, ecx; dwStreamIdentifier
0x1800227d5  call    cs:__imp_MFCreateStreamDescriptor
0x1800227db  mov     ecx, eax
0x1800227dd  mov     [rbp+arg_0], eax
0x1800227e0  test    eax, eax
0x1800227e2  jns     short loc_1800227F8
0x1800227e4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800227e9  cmp     al, 1
0x1800227eb  jb      loc_180022962
0x1800227f1  mov     edx, 0F0h
0x1800227f6  jmp     short loc_1800227A3
0x1800227f8  mov     rcx, [rbp+ppDescriptor]
0x1800227fc  mov     rax, [rcx]
0x1800227ff  lea     rdx, [rbp+var_20]
0x180022803  mov     rax, [rax+110h]
0x18002280a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002280f  mov     ecx, eax
0x180022811  mov     [rbp+arg_0], eax
0x180022814  test    eax, eax
0x180022816  jns     short loc_18002282F
0x180022818  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002281d  cmp     al, 1
0x18002281f  jb      loc_180022962
0x180022825  mov     edx, 0F1h
0x18002282a  jmp     loc_1800227A3
0x18002282f  mov     rcx, [rbp+var_20]
0x180022833  mov     rax, [rcx]
0x180022836  mov     rdx, [rbp+apMediaTypes]
0x18002283a  mov     rax, [rax+30h]
0x18002283e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022843  mov     ecx, eax
0x180022845  mov     [rbp+arg_0], eax
0x180022848  test    eax, eax
0x18002284a  jns     short loc_180022863
0x18002284c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180022851  cmp     al, 1
0x180022853  jb      loc_180022962
0x180022859  mov     edx, 0F2h
0x18002285e  jmp     loc_1800227A3
0x180022863  mov     rcx, [rbp+ppDescriptor]
0x180022867  mov     rax, [rcx]
0x18002286a  xor     r8d, r8d
0x18002286d  lea     rdx, MF_SD_AUDIO_ENCODER_DELAY
0x180022874  mov     rax, [rax+0A8h]
0x18002287b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022880  mov     ecx, eax
0x180022882  mov     [rbp+arg_0], eax
0x180022885  test    eax, eax
0x180022887  jns     short loc_1800228A0
0x180022889  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002288e  cmp     al, 1
0x180022890  jb      loc_180022962
0x180022896  mov     edx, 0F3h
0x18002289b  jmp     loc_1800227A3
0x1800228a0  mov     rcx, [rbp+ppDescriptor]
0x1800228a4  mov     rax, [rcx]
0x1800228a7  xor     r8d, r8d
0x1800228aa  lea     rdx, MF_SD_AUDIO_ENCODER_PADDING
0x1800228b1  mov     rax, [rax+0A8h]
0x1800228b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228bd  mov     ecx, eax
0x1800228bf  mov     [rbp+arg_0], eax
0x1800228c2  test    eax, eax
0x1800228c4  jns     short loc_1800228DD
0x1800228c6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800228cb  cmp     al, 1
0x1800228cd  jb      loc_180022962
0x1800228d3  mov     edx, 0F4h
0x1800228d8  jmp     loc_1800227A3
0x1800228dd  lea     r8, [rbp+arg_18]; struct CFLACStream **
0x1800228e1  mov     rdx, [rbp+ppDescriptor]; struct IMFStreamDescriptor *
0x1800228e5  mov     rcx, rbx; struct CFLACSource *
0x1800228e8  call    ?CreateInstance@CFLACStream@@SAJPEAVCFLACSource@@PEAUIMFStreamDescriptor@@PEAPEAV1@@Z; CFLACStream::CreateInstance(CFLACSource *,IMFStreamDescriptor *,CFLACStream * *)
0x1800228ed  mov     ecx, eax
0x1800228ef  mov     [rbp+arg_0], eax
0x1800228f2  test    eax, eax
0x1800228f4  jns     short loc_180022928
0x1800228f6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800228fb  cmp     al, 1
0x1800228fd  jb      short loc_180022922
0x1800228ff  mov     edx, 0F5h
0x180022904  mov     [rsp+50h+var_30], ecx
0x180022908  mov     r9, rbx
0x18002290b  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x180022912  mov     rcx, cs:WPP_GLOBAL_Control
0x180022919  mov     rcx, [rcx+10h]
0x18002291d  call    WPP_SF_qd
0x180022922  mov     rdi, [rbp+arg_18]
0x180022926  jmp     short loc_180022962
0x180022928  mov     rdi, [rbp+arg_18]
0x18002292c  test    rdi, rdi
0x18002292f  jnz     short loc_18002294C
0x180022931  mov     ecx, 8007000Eh
0x180022936  mov     [rbp+arg_0], ecx
0x180022939  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002293e  cmp     al, 1
0x180022940  jb      short loc_180022962
0x180022942  mov     edx, 0F6h
0x180022947  jmp     loc_1800227A3
0x18002294c  mov     [rbx+0B0h], rdi
0x180022953  mov     rax, [rdi]
0x180022956  mov     rcx, rdi
0x180022959  mov     rax, [rax+8]
0x18002295d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022962  mov     rcx, [rbp+ppDescriptor]
0x180022966  test    rcx, rcx
0x180022969  jz      short loc_18002297F
0x18002296b  mov     rax, [rcx]
0x18002296e  mov     rax, [rax+10h]
0x180022972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022977  mov     [rbp+ppDescriptor], 0
0x18002297f  mov     rcx, [rbp+apMediaTypes]
0x180022983  test    rcx, rcx
0x180022986  jz      short loc_18002299C
0x180022988  mov     rax, [rcx]
0x18002298b  mov     rax, [rax+10h]
0x18002298f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022994  mov     [rbp+apMediaTypes], 0
0x18002299c  mov     rcx, [rbp+var_20]
0x1800229a0  test    rcx, rcx
0x1800229a3  jz      short loc_1800229B9
0x1800229a5  mov     rax, [rcx]
0x1800229a8  mov     rax, [rax+10h]
0x1800229ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229b1  mov     [rbp+var_20], 0
0x1800229b9  test    rdi, rdi
0x1800229bc  jz      short loc_1800229CE
0x1800229be  mov     rax, [rdi]
0x1800229c1  mov     rcx, rdi
0x1800229c4  mov     rax, [rax+10h]
0x1800229c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229cd  nop
0x1800229ce  mov     eax, [rbp+arg_0]
0x1800229d1  add     rsp, 50h
0x1800229d5  pop     rdi
0x1800229d6  pop     rbx
0x1800229d7  pop     rbp
0x1800229d8  retn
```
