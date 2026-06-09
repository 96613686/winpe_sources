# CASFOutput::CASFOutput(CASFReader *,ulong,_WMMediaType *,long *,ushort const *)

- ea: `0x18000784c`
- end: `0x180007baa`
- name: `??0CASFOutput@@QEAA@PEAVCASFReader@@KPEAU_WMMediaType@@PEAJPEBG@Z`
- size: `862`
- prototype: `CASFOutput *__fastcall(CASFOutput *this, struct CASFReader *, int, struct _WMMediaType *, int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ab04`

## callees

- `0x1800033c0`
- `0x18000784c`
- `0x18001c958`
- `0x18001e5c5`
- `0x18001f010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800078a6`
- `KERNEL32!InitializeCriticalSection` at `0x1800078a6`
- `ole32!CoTaskMemAlloc` at `0x180007b11`
- `ole32!CoTaskMemAlloc` at `0x180007b11`
- `ole32!CoTaskMemFree` at `0x180007b50`
- `ole32!CoTaskMemFree` at `0x180007b50`

## pseudocode

```c
CASFOutput *__fastcall CASFOutput::CASFOutput(
        CASFOutput *this,
        struct CASFReader *a2,
        int a3,
        struct _WMMediaType *a4,
        int *a5,
        unsigned __int16 *a6)
{
  char *v10; // rax
  int v11; // eax
  BYTE *pbFormat; // rcx
  size_t cbFormat; // rsi
  BYTE *v14; // r15
  void *v15; // rbp
  unsigned int v16; // eax
  LPVOID *v17; // r14
  __int64 v18; // rax
  __int64 v19; // rdx
  int *v21; // [rsp+20h] [rbp-68h]
  _BYTE v22[72]; // [rsp+40h] [rbp-48h] BYREF

  CBasePin::CBasePin(
    this,
    (const unsigned __int16 *)a2,
    a2,
    (struct CASFReader *)((char *)a2 + 160),
    v21,
    a6,
    PINDIR_OUTPUT);
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  *((_DWORD *)this + 73) = 0;
  *(_QWORD *)this = &CASFOutput::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 37) = a2;
  *((_QWORD *)this + 3) = &CASFOutput::`vftable'{for `IPin'};
  *((_QWORD *)this + 4) = &CASFOutput::`vftable'{for `IQualityControl'};
  *((_QWORD *)this + 29) = &CASFOutput::`vftable'{for `IAMVideoAcceleratorNotify'};
  *((_QWORD *)this + 30) = &CASFOutput::`vftable'{for `IAMWMBufferPass'};
  v10 = (char *)*((_QWORD *)this + 1);
  *((_DWORD *)this + 76) = a3;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  _InterlockedAdd(&CBaseObject::m_cObjects, 1u);
  *((_QWORD *)this + 46) = a2;
  *((_QWORD *)this + 47) = this;
  if ( !v10 )
    v10 = (char *)this + 336;
  *((_QWORD *)this + 43) = v10;
  *((_QWORD *)this + 42) = &CImplSeeking::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 45) = &CImplSeeking::`vftable'{for `IMediaSeeking'};
  *((_DWORD *)this + 88) = 0;
  if ( *((_DWORD *)a2 + 98) )
    v11 = 55;
  else
    v11 = *((_QWORD *)a2 + 48) != 0 ? 0x20 : 0;
  *((_DWORD *)this + 96) = v11;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_WORD *)this + 208) = 257;
  *(GUID *)((char *)this + 104) = a4->majortype;
  *(GUID *)((char *)this + 120) = a4->subtype;
  if ( *((_QWORD *)this + 13) != *(_QWORD *)&MEDIATYPE_Video.Data1
    || *((_QWORD *)this + 14) != *(_QWORD *)MEDIATYPE_Video.Data4 )
  {
    if ( *((_QWORD *)this + 13) != *(_QWORD *)&MEDIATYPE_Audio.Data1
      || *((_QWORD *)this + 14) != *(_QWORD *)MEDIATYPE_Audio.Data4 )
    {
      if ( *(_QWORD *)&WMMEDIATYPE_FileTransfer.Data1 == *((_QWORD *)this + 13)
        && *(_QWORD *)WMMEDIATYPE_FileTransfer.Data4 == *((_QWORD *)this + 14)
        || *(_QWORD *)&MEDIATYPE_ScriptCommand.Data1 == *((_QWORD *)this + 13)
        && *(_QWORD *)MEDIATYPE_ScriptCommand.Data4 == *((_QWORD *)this + 14) )
      {
        *((_DWORD *)this + 81) = 1;
      }
      goto LABEL_26;
    }
    if ( *(_QWORD *)&a4->subtype.Data1 == *(_QWORD *)&MEDIASUBTYPE_DOLBY_AC3.Data1
      && *(_QWORD *)a4->subtype.Data4 == *(_QWORD *)MEDIASUBTYPE_DOLBY_AC3.Data4 )
    {
      *(GUID *)((char *)this + 120) = a4->subtype;
    }
    else
    {
      if ( a4->cbFormat < 0x12 )
        goto LABEL_20;
      pbFormat = a4->pbFormat;
      *((_DWORD *)this + 30) = *(unsigned __int16 *)pbFormat;
      *((_DWORD *)this + 36) = *((unsigned __int16 *)pbFormat + 6);
    }
LABEL_26:
    *((_DWORD *)this + 34) = a4->bFixedSizeSamples;
    *((_DWORD *)this + 35) = a4->bTemporalCompression;
    *((_DWORD *)this + 36) = a4->lSampleSize;
    *(GUID *)((char *)this + 148) = a4->formattype;
    cbFormat = a4->cbFormat;
    if ( (_DWORD)cbFormat )
    {
      v14 = a4->pbFormat;
      if ( *((_DWORD *)this + 44) == (_DWORD)cbFormat )
        goto LABEL_40;
      v15 = CoTaskMemAlloc((unsigned int)cbFormat);
      v16 = *((_DWORD *)this + 44);
      if ( v15 )
      {
        v17 = (LPVOID *)((char *)this + 184);
        if ( v16 )
          CoTaskMemFree(*v17);
        *((_DWORD *)this + 44) = cbFormat;
        *v17 = v15;
        goto LABEL_35;
      }
      if ( (unsigned int)cbFormat <= v16 )
      {
LABEL_40:
        if ( *((_QWORD *)this + 23) )
        {
          v15 = (void *)*((_QWORD *)this + 23);
LABEL_35:
          memcpy_0(v15, v14, cbFormat);
        }
      }
    }
    v18 = *((_QWORD *)this + 37);
    v19 = *((unsigned __int16 *)this + 152);
    *((_DWORD *)this + 77) = 0;
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v18 + 352) + 72LL))(*(_QWORD *)(v18 + 352), v19);
    return this;
  }
  if ( *(_QWORD *)&a4->formattype.Data1 == *(_QWORD *)&FORMAT_MPEG2_VIDEO.Data1
    && *(_QWORD *)a4->formattype.Data4 == *(_QWORD *)FORMAT_MPEG2_VIDEO.Data4 )
  {
    goto LABEL_26;
  }
  if ( a4->cbFormat >= 0x58 )
  {
    *(_OWORD *)((char *)this + 120) = *(_OWORD *)GetBitmapSubtype(v22, a4->pbFormat + 48);
    if ( !*((_DWORD *)a4->pbFormat + 17) )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 37) + 352LL) + 168LL))(
        *(_QWORD *)(*((_QWORD *)this + 37) + 352LL),
        (unsigned __int16)a3);
    goto LABEL_26;
  }
LABEL_20:
  *a5 = -1072889796;
  return this;
}

```

## disassembly

```asm
0x18000784c  push    rbx
0x18000784e  push    rbp
0x18000784f  push    rsi
0x180007850  push    rdi
0x180007851  push    r12
0x180007853  push    r14
0x180007855  push    r15
0x180007857  sub     rsp, 50h
0x18000785b  mov     rax, [rsp+88h+arg_28]
0x180007863  mov     rdi, r9
0x180007866  mov     ebp, r8d
0x180007869  lea     r9, [rdx+0A0h]; struct CCritSec *
0x180007870  mov     r14d, 1
0x180007876  mov     r8, rdx; struct CBaseFilter *
0x180007879  mov     [rsp+88h+var_58], r14d; enum _PinDirection
0x18000787e  mov     rsi, rdx
0x180007881  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x180007886  mov     rbx, rcx
0x180007889  call    ??0CBasePin@@QEAA@PEBGPEAVCBaseFilter@@PEAVCCritSec@@PEAJ0W4_PinDirection@@@Z; CBasePin::CBasePin(ushort const *,CBaseFilter *,CCritSec *,long *,ushort const *,_PinDirection)
0x18000788e  xor     r12d, r12d
0x180007891  lea     rcx, [rbx+0F8h]; lpCriticalSection
0x180007898  mov     [rbx+0D8h], r12
0x18000789f  mov     [rbx+0E0h], r12
0x1800078a6  call    cs:__imp_InitializeCriticalSection
0x1800078ac  lea     rax, ??_7CASFOutput@@6BCUnknown@@@; const CASFOutput::`vftable'{for `CUnknown'}
0x1800078b3  mov     [rbx+124h], r12d
0x1800078ba  mov     [rbx], rax
0x1800078bd  lea     rcx, [rbx+150h]
0x1800078c4  lea     rax, ??_7CASFOutput@@6BIPin@@@; const CASFOutput::`vftable'{for `IPin'}
0x1800078cb  mov     [rbx+128h], rsi
0x1800078d2  mov     [rbx+18h], rax
0x1800078d6  lea     rax, ??_7CASFOutput@@6BIQualityControl@@@; const CASFOutput::`vftable'{for `IQualityControl'}
0x1800078dd  mov     [rbx+20h], rax
0x1800078e1  lea     rax, ??_7CASFOutput@@6BIAMVideoAcceleratorNotify@@@; const CASFOutput::`vftable'{for `IAMVideoAcceleratorNotify'}
0x1800078e8  mov     [rbx+0E8h], rax
0x1800078ef  lea     rax, ??_7CASFOutput@@6BIAMWMBufferPass@@@; const CASFOutput::`vftable'{for `IAMWMBufferPass'}
0x1800078f6  mov     [rbx+0F0h], rax
0x1800078fd  mov     rax, [rbx+8]
0x180007901  mov     [rbx+130h], ebp
0x180007907  mov     [rbx+140h], r12
0x18000790e  mov     [rbx+148h], r12
0x180007915  lock add cs:?m_cObjects@CBaseObject@@0JA, r14d; long CBaseObject::m_cObjects
0x18000791d  test    rax, rax
0x180007920  mov     [rcx+20h], rsi
0x180007924  mov     [rcx+28h], rbx
0x180007928  cmovz   rax, rcx
0x18000792c  mov     [rcx+8], rax
0x180007930  lea     rax, ??_7CImplSeeking@@6BCUnknown@@@; const CImplSeeking::`vftable'{for `CUnknown'}
0x180007937  mov     [rcx], rax
0x18000793a  lea     rax, ??_7CImplSeeking@@6BIMediaSeeking@@@; const CImplSeeking::`vftable'{for `IMediaSeeking'}
0x180007941  mov     [rcx+18h], rax
0x180007945  mov     [rcx+10h], r12d
0x180007949  cmp     [rsi+188h], r12d
0x180007950  jz      short loc_180007958
0x180007952  lea     eax, [r14+36h]
0x180007956  jmp     short loc_180007964
0x180007958  cmp     r12, [rsi+180h]
0x18000795f  sbb     eax, eax
0x180007961  and     eax, 20h
0x180007964  mov     [rcx+30h], eax
0x180007967  mov     [rbx+188h], r12
0x18000796e  mov     [rbx+190h], r12
0x180007975  mov     [rbx+198h], r12
0x18000797c  mov     word ptr [rbx+1A0h], 101h
0x180007985  movups  xmm0, xmmword ptr [rdi]
0x180007988  movdqu  xmmword ptr [rbx+68h], xmm0
0x18000798d  movups  xmm0, xmmword ptr [rdi+10h]
0x180007991  movdqu  xmmword ptr [rbx+78h], xmm0
0x180007996  mov     rax, [rbx+68h]
0x18000799a  cmp     rax, qword ptr cs:MEDIATYPE_Video.Data1
0x1800079a1  jnz     loc_180007A2C
0x1800079a7  mov     rax, [rbx+70h]
0x1800079ab  cmp     rax, qword ptr cs:MEDIATYPE_Video.Data4
0x1800079b2  jnz     short loc_180007A2C
0x1800079b4  mov     rax, [rdi+2Ch]
0x1800079b8  cmp     rax, qword ptr cs:FORMAT_MPEG2_VIDEO.Data1
0x1800079bf  jnz     short loc_1800079D2
0x1800079c1  mov     rax, [rdi+34h]
0x1800079c5  cmp     rax, qword ptr cs:FORMAT_MPEG2_VIDEO.Data4
0x1800079cc  jz      loc_180007AD5
0x1800079d2  cmp     dword ptr [rdi+48h], 58h ; 'X'
0x1800079d6  jb      loc_180007A87
0x1800079dc  mov     rdx, [rdi+50h]
0x1800079e0  lea     rcx, [rsp+88h+var_48]
0x1800079e5  add     rdx, 30h ; '0'
0x1800079e9  call    GetBitmapSubtype
0x1800079ee  movups  xmm1, xmmword ptr [rax]
0x1800079f1  movdqu  xmmword ptr [rbx+78h], xmm1
0x1800079f6  mov     r8, [rdi+50h]
0x1800079fa  add     r8, 44h ; 'D'
0x1800079fe  cmp     [r8], r12d
0x180007a01  jnz     loc_180007AD5
0x180007a07  mov     rax, [rbx+128h]
0x180007a0e  movzx   edx, bp
0x180007a11  mov     rcx, [rax+160h]
0x180007a18  mov     rax, [rcx]
0x180007a1b  mov     rax, [rax+0A8h]
0x180007a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a27  jmp     loc_180007AD5
0x180007a2c  mov     rax, [rbx+68h]
0x180007a30  cmp     rax, qword ptr cs:MEDIATYPE_Audio.Data1
0x180007a37  jnz     short loc_180007A9A
0x180007a39  mov     rax, [rbx+70h]
0x180007a3d  cmp     rax, qword ptr cs:MEDIATYPE_Audio.Data4
0x180007a44  jnz     short loc_180007A9A
0x180007a46  mov     rax, [rdi+10h]
0x180007a4a  cmp     rax, qword ptr cs:MEDIASUBTYPE_DOLBY_AC3.Data1
0x180007a51  jnz     short loc_180007A6B
0x180007a53  mov     rax, [rdi+18h]
0x180007a57  cmp     rax, qword ptr cs:MEDIASUBTYPE_DOLBY_AC3.Data4
0x180007a5e  jnz     short loc_180007A6B
0x180007a60  movups  xmm0, xmmword ptr [rdi+10h]
0x180007a64  movdqu  xmmword ptr [rbx+78h], xmm0
0x180007a69  jmp     short loc_180007AD5
0x180007a6b  cmp     dword ptr [rdi+48h], 12h
0x180007a6f  jb      short loc_180007A87
0x180007a71  mov     rcx, [rdi+50h]
0x180007a75  movzx   eax, word ptr [rcx]
0x180007a78  mov     [rbx+78h], eax
0x180007a7b  movzx   eax, word ptr [rcx+0Ch]
0x180007a7f  mov     [rbx+90h], eax
0x180007a85  jmp     short loc_180007AD5
0x180007a87  mov     rax, [rsp+88h+arg_20]
0x180007a8f  mov     dword ptr [rax], 0C00D003Ch
0x180007a95  jmp     loc_180007B98
0x180007a9a  mov     rax, qword ptr cs:WMMEDIATYPE_FileTransfer.Data1
0x180007aa1  cmp     rax, [rbx+68h]
0x180007aa5  jnz     short loc_180007AB4
0x180007aa7  mov     rax, qword ptr cs:WMMEDIATYPE_FileTransfer.Data4
0x180007aae  cmp     rax, [rbx+70h]
0x180007ab2  jz      short loc_180007ACE
0x180007ab4  mov     rax, qword ptr cs:MEDIATYPE_ScriptCommand.Data1
0x180007abb  cmp     rax, [rbx+68h]
0x180007abf  jnz     short loc_180007AD5
0x180007ac1  mov     rax, qword ptr cs:MEDIATYPE_ScriptCommand.Data4
0x180007ac8  cmp     rax, [rbx+70h]
0x180007acc  jnz     short loc_180007AD5
0x180007ace  mov     [rbx+144h], r14d
0x180007ad5  mov     eax, [rdi+20h]
0x180007ad8  mov     [rbx+88h], eax
0x180007ade  mov     eax, [rdi+24h]
0x180007ae1  mov     [rbx+8Ch], eax
0x180007ae7  mov     eax, [rdi+28h]
0x180007aea  mov     [rbx+90h], eax
0x180007af0  movups  xmm0, xmmword ptr [rdi+2Ch]
0x180007af4  movdqu  xmmword ptr [rbx+94h], xmm0
0x180007afc  mov     esi, [rdi+48h]
0x180007aff  test    esi, esi
0x180007b01  jz      short loc_180007B6D
0x180007b03  mov     r15, [rdi+50h]
0x180007b07  cmp     [rbx+0B0h], esi
0x180007b0d  jz      short loc_180007B29
0x180007b0f  mov     ecx, esi; cb
0x180007b11  call    cs:__imp_CoTaskMemAlloc
0x180007b17  mov     rbp, rax
0x180007b1a  mov     eax, [rbx+0B0h]
0x180007b20  test    rbp, rbp
0x180007b23  jnz     short loc_180007B42
0x180007b25  cmp     esi, eax
0x180007b27  ja      short loc_180007B6D
0x180007b29  mov     eax, 0B8h
0x180007b2e  mov     rdx, rbx
0x180007b31  mov     ecx, eax
0x180007b33  mov     rbp, rbx
0x180007b36  cmp     [rbx+rax], r12
0x180007b3a  jz      short loc_180007B6D
0x180007b3c  mov     rbp, [rax+rbx]
0x180007b40  jmp     short loc_180007B5F
0x180007b42  lea     r14, [rbx+0B8h]
0x180007b49  test    eax, eax
0x180007b4b  jz      short loc_180007B56
0x180007b4d  mov     rcx, [r14]; pv
0x180007b50  call    cs:__imp_CoTaskMemFree
0x180007b56  mov     [rbx+0B0h], esi
0x180007b5c  mov     [r14], rbp
0x180007b5f  mov     r8, rsi; Size
0x180007b62  mov     rdx, r15; Src
0x180007b65  mov     rcx, rbp; void *
0x180007b68  call    memcpy_0
0x180007b6d  mov     rax, [rbx+128h]
0x180007b74  lea     r8, [rbx+134h]
0x180007b7b  movzx   edx, word ptr [rbx+130h]
0x180007b82  mov     [r8], r12d
0x180007b85  mov     rcx, [rax+160h]
0x180007b8c  mov     rax, [rcx]
0x180007b8f  mov     rax, [rax+48h]
0x180007b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b98  mov     rax, rbx
0x180007b9b  add     rsp, 50h
0x180007b9f  pop     r15
0x180007ba1  pop     r14
0x180007ba3  pop     r12
0x180007ba5  pop     rdi
0x180007ba6  pop     rsi
0x180007ba7  pop     rbp
0x180007ba8  pop     rbx
0x180007ba9  retn
```
