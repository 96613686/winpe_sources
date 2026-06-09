# CMsftDiscFormat2TrackAtOnce::CleanupFromPreparedMedia(uchar,uchar)

- ea: `0x1800375a8`
- end: `0x1800378b2`
- name: `?CleanupFromPreparedMedia@CMsftDiscFormat2TrackAtOnce@@AEAAXEE@Z`
- size: `778`
- prototype: `void __fastcall(CMsftDiscFormat2TrackAtOnce *__hidden this, unsigned __int8, unsigned __int8)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180037d20`
- `0x1800389f0`
- `0x180039320`

## callees

- `0x1800140f4`
- `0x18001724c`
- `0x1800375a8`
- `0x18003967c`
- `0x1800464ec`
- `0x18004984a`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800377fd`
- `ole32!CoTaskMemFree` at `0x18003781f`
- `ole32!CoTaskMemFree` at `0x1800377fd`
- `ole32!CoTaskMemFree` at `0x18003781f`

## pseudocode

```c
void __fastcall CMsftDiscFormat2TrackAtOnce::CleanupFromPreparedMedia(
        CMsftDiscFormat2TrackAtOnce *this,
        const struct _GUID *a2,
        unsigned __int8 a3,
        unsigned __int8 a4)
{
  char v5; // si
  unsigned int v7; // edi
  int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // edi
  int v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // edi
  int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  struct IUnknown *v19; // rcx
  int v20; // eax
  void *v21; // rcx
  void *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx

  v5 = (char)a2;
  v7 = 0;
  while ( v7 < 5 )
  {
    v8 = CMsftDiscFormat2TrackAtOnce::RestoreWriteParametersModePage(this);
    if ( v8 >= 0 )
      goto LABEL_15;
    if ( v7 == 4 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 2u )
      {
        v10 = 116;
LABEL_9:
        WPP_SF_d(v9[42], v10, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids, (unsigned int)v8);
      }
      ++v7;
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
      {
        v10 = 117;
        goto LABEL_9;
      }
LABEL_15:
      ++v7;
      if ( v8 >= 0 )
        break;
    }
  }
  if ( v5 )
  {
    v11 = 0;
    while ( v11 < 5 )
    {
      v12 = Imapi2Utility::PreventAllowMediumRemoval(*((Imapi2Utility **)this + 24), 0, a3, a4);
      if ( v12 >= 0 )
        goto LABEL_31;
      if ( v11 == 4 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 2u )
        {
          v14 = 118;
LABEL_25:
          WPP_SF_d(v13[42], v14, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids, (unsigned int)v12);
        }
        ++v11;
      }
      else
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
        {
          v14 = 119;
          goto LABEL_25;
        }
LABEL_31:
        ++v11;
        if ( v12 >= 0 )
          break;
      }
    }
  }
  if ( a3 )
  {
    v15 = 0;
    while ( v15 < 5 )
    {
      v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 80LL))(*((_QWORD *)this + 23));
      if ( v16 >= 0 )
        goto LABEL_47;
      if ( v15 == 4 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 2u )
        {
          v18 = 120;
LABEL_41:
          WPP_SF_d(v17[42], v18, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids, (unsigned int)v16);
        }
        ++v15;
      }
      else
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
        {
          v18 = 121;
          goto LABEL_41;
        }
LABEL_47:
        ++v15;
        if ( v16 >= 0 )
          break;
      }
    }
  }
  v19 = (struct IUnknown *)*((_QWORD *)this + 32);
  if ( v19 )
  {
    v20 = ATL::AtlUnadvise(v19, a2, *((_DWORD *)this + 23));
    *((_DWORD *)this + 23) = -16843010;
    if ( v20 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        122,
        WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
        (unsigned int)v20);
    }
  }
  v21 = (void *)*((_QWORD *)this + 28);
  *((_WORD *)this + 108) = 0;
  *((_WORD *)this + 556) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_DWORD *)this + 70) = 0;
  *((_DWORD *)this + 55) = 0;
  *((_DWORD *)this + 277) = -1;
  CoTaskMemFree(v21);
  v22 = (void *)*((_QWORD *)this + 30);
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 58) = 0;
  CoTaskMemFree(v22);
  v23 = *((_QWORD *)this + 32);
  *((_QWORD *)this + 30) = 0;
  *((_DWORD *)this + 62) = 0;
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    *((_QWORD *)this + 32) = 0;
  }
  v24 = *((_QWORD *)this + 33);
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    *((_QWORD *)this + 33) = 0;
  }
  *((_DWORD *)this + 71) = 0;
  memset_0((char *)this + 288, 0, 0x324u);
  *((_WORD *)this + 100) = 0;
}

```

## disassembly

```asm
0x1800375a8  push    rbx
0x1800375aa  push    rbp
0x1800375ab  push    rsi
0x1800375ac  push    rdi
0x1800375ad  push    r13
0x1800375af  sub     rsp, 20h
0x1800375b3  mov     bpl, r8b
0x1800375b6  lea     r13, WPP_GLOBAL_Control
0x1800375bd  mov     sil, dl
0x1800375c0  mov     rbx, rcx
0x1800375c3  xor     edi, edi
0x1800375c5  cmp     edi, 5
0x1800375c8  jnb     short loc_180037641
0x1800375ca  mov     rcx, rbx; this
0x1800375cd  call    ?RestoreWriteParametersModePage@CMsftDiscFormat2TrackAtOnce@@AEAAJXZ; CMsftDiscFormat2TrackAtOnce::RestoreWriteParametersModePage(void)
0x1800375d2  test    eax, eax
0x1800375d4  jns     short loc_18003763B
0x1800375d6  cmp     edi, 4
0x1800375d9  jnz     short loc_180037616
0x1800375db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800375e2  cmp     rcx, r13
0x1800375e5  jz      short loc_180037612
0x1800375e7  test    [rcx+15Ch], dil
0x1800375ee  jz      short loc_180037612
0x1800375f0  cmp     byte ptr [rcx+159h], 2
0x1800375f7  jb      short loc_180037612
0x1800375f9  lea     edx, [rdi+70h]
0x1800375fc  mov     rcx, [rcx+150h]
0x180037603  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x18003760a  mov     r9d, eax
0x18003760d  call    WPP_SF_d
0x180037612  inc     edi
0x180037614  jmp     short loc_1800375C5
0x180037616  mov     rcx, cs:WPP_GLOBAL_Control
0x18003761d  cmp     rcx, r13
0x180037620  jz      short loc_18003763B
0x180037622  test    byte ptr [rcx+15Ch], 4
0x180037629  jz      short loc_18003763B
0x18003762b  cmp     byte ptr [rcx+159h], 3
0x180037632  jb      short loc_18003763B
0x180037634  mov     edx, 75h ; 'u'
0x180037639  jmp     short loc_1800375FC
0x18003763b  inc     edi
0x18003763d  test    eax, eax
0x18003763f  js      short loc_1800375C5
0x180037641  test    sil, sil
0x180037644  jz      loc_1800376D6
0x18003764a  xor     edi, edi
0x18003764c  cmp     edi, 5
0x18003764f  jnb     loc_1800376D6
0x180037655  mov     rcx, [rbx+0C0h]; this
0x18003765c  xor     edx, edx; struct IDiscRecorder2Ex *
0x18003765e  call    ?PreventAllowMediumRemoval@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@EE@Z; Imapi2Utility::PreventAllowMediumRemoval(IDiscRecorder2Ex *,uchar,uchar)
0x180037663  test    eax, eax
0x180037665  jns     short loc_1800376CC
0x180037667  cmp     edi, 4
0x18003766a  jnz     short loc_1800376A7
0x18003766c  mov     rcx, cs:WPP_GLOBAL_Control
0x180037673  cmp     rcx, r13
0x180037676  jz      short loc_1800376A3
0x180037678  test    [rcx+15Ch], dil
0x18003767f  jz      short loc_1800376A3
0x180037681  cmp     byte ptr [rcx+159h], 2
0x180037688  jb      short loc_1800376A3
0x18003768a  lea     edx, [rdi+72h]
0x18003768d  mov     rcx, [rcx+150h]
0x180037694  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x18003769b  mov     r9d, eax
0x18003769e  call    WPP_SF_d
0x1800376a3  inc     edi
0x1800376a5  jmp     short loc_18003764C
0x1800376a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800376ae  cmp     rcx, r13
0x1800376b1  jz      short loc_1800376CC
0x1800376b3  test    byte ptr [rcx+15Ch], 4
0x1800376ba  jz      short loc_1800376CC
0x1800376bc  cmp     byte ptr [rcx+159h], 3
0x1800376c3  jb      short loc_1800376CC
0x1800376c5  mov     edx, 77h ; 'w'
0x1800376ca  jmp     short loc_18003768D
0x1800376cc  inc     edi
0x1800376ce  test    eax, eax
0x1800376d0  js      loc_18003764C
0x1800376d6  test    bpl, bpl
0x1800376d9  jz      loc_180037770
0x1800376df  xor     edi, edi
0x1800376e1  cmp     edi, 5
0x1800376e4  jnb     loc_180037770
0x1800376ea  mov     rcx, [rbx+0B8h]
0x1800376f1  mov     rax, [rcx]
0x1800376f4  mov     rax, [rax+50h]
0x1800376f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376fd  test    eax, eax
0x1800376ff  jns     short loc_180037766
0x180037701  cmp     edi, 4
0x180037704  jnz     short loc_180037741
0x180037706  mov     rcx, cs:WPP_GLOBAL_Control
0x18003770d  cmp     rcx, r13
0x180037710  jz      short loc_18003773D
0x180037712  test    [rcx+15Ch], dil
0x180037719  jz      short loc_18003773D
0x18003771b  cmp     byte ptr [rcx+159h], 2
0x180037722  jb      short loc_18003773D
0x180037724  lea     edx, [rdi+74h]
0x180037727  mov     rcx, [rcx+150h]
0x18003772e  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180037735  mov     r9d, eax
0x180037738  call    WPP_SF_d
0x18003773d  inc     edi
0x18003773f  jmp     short loc_1800376E1
0x180037741  mov     rcx, cs:WPP_GLOBAL_Control
0x180037748  cmp     rcx, r13
0x18003774b  jz      short loc_180037766
0x18003774d  test    byte ptr [rcx+15Ch], 4
0x180037754  jz      short loc_180037766
0x180037756  cmp     byte ptr [rcx+159h], 3
0x18003775d  jb      short loc_180037766
0x18003775f  mov     edx, 79h ; 'y'
0x180037764  jmp     short loc_180037727
0x180037766  inc     edi
0x180037768  test    eax, eax
0x18003776a  js      loc_1800376E1
0x180037770  mov     rcx, [rbx+100h]; struct IUnknown *
0x180037777  test    rcx, rcx
0x18003777a  jz      short loc_1800377C9
0x18003777c  mov     r8d, [rbx+5Ch]; unsigned int
0x180037780  call    ?AtlUnadvise@ATL@@YAJPEAUIUnknown@@AEBU_GUID@@K@Z; ATL::AtlUnadvise(IUnknown *,_GUID const &,ulong)
0x180037785  mov     dword ptr [rbx+5Ch], 0FEFEFEFEh
0x18003778c  test    eax, eax
0x18003778e  jns     short loc_1800377C9
0x180037790  mov     rcx, cs:WPP_GLOBAL_Control
0x180037797  cmp     rcx, r13
0x18003779a  jz      short loc_1800377C9
0x18003779c  test    byte ptr [rcx+15Ch], 4
0x1800377a3  jz      short loc_1800377C9
0x1800377a5  cmp     byte ptr [rcx+159h], 3
0x1800377ac  jb      short loc_1800377C9
0x1800377ae  mov     rcx, [rcx+150h]
0x1800377b5  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x1800377bc  mov     edx, 7Ah ; 'z'
0x1800377c1  mov     r9d, eax
0x1800377c4  call    WPP_SF_d
0x1800377c9  mov     rcx, [rbx+0E0h]; pv
0x1800377d0  xor     eax, eax
0x1800377d2  mov     [rbx+0D8h], ax
0x1800377d9  mov     [rbx+458h], ax
0x1800377e0  mov     [rbx+110h], rax
0x1800377e7  mov     [rbx+118h], eax
0x1800377ed  mov     [rbx+0DCh], eax
0x1800377f3  mov     dword ptr [rbx+454h], 0FFFFFFFFh
0x1800377fd  call    cs:__imp_CoTaskMemFree
0x180037803  mov     rcx, [rbx+0F0h]; pv
0x18003780a  mov     qword ptr [rbx+0E0h], 0
0x180037815  mov     dword ptr [rbx+0E8h], 0
0x18003781f  call    cs:__imp_CoTaskMemFree
0x180037825  mov     rcx, [rbx+100h]
0x18003782c  mov     qword ptr [rbx+0F0h], 0
0x180037837  mov     dword ptr [rbx+0F8h], 0
0x180037841  test    rcx, rcx
0x180037844  jz      short loc_18003785D
0x180037846  mov     rax, [rcx]
0x180037849  mov     rax, [rax+10h]
0x18003784d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037852  mov     qword ptr [rbx+100h], 0
0x18003785d  mov     rcx, [rbx+108h]
0x180037864  test    rcx, rcx
0x180037867  jz      short loc_180037880
0x180037869  mov     rax, [rcx]
0x18003786c  mov     rax, [rax+10h]
0x180037870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037875  mov     qword ptr [rbx+108h], 0
0x180037880  lea     rcx, [rbx+120h]; void *
0x180037887  mov     dword ptr [rbx+11Ch], 0
0x180037891  xor     edx, edx; Val
0x180037893  mov     r8d, 324h; Size
0x180037899  call    memset_0
0x18003789e  xor     eax, eax
0x1800378a0  mov     [rbx+0C8h], ax
0x1800378a7  add     rsp, 20h
0x1800378ab  pop     r13
0x1800378ad  pop     rdi
0x1800378ae  pop     rsi
0x1800378af  pop     rbp
0x1800378b0  pop     rbx
0x1800378b1  retn
```
