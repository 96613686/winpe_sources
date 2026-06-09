# CWMWriter::ConfigureFilterUsingProfile(IWMProfile *)

- ea: `0x18000ea00`
- end: `0x18000efe6`
- name: `?ConfigureFilterUsingProfile@CWMWriter@@UEAAJPEAUIWMProfile@@@Z`
- size: `1510`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, struct IWMProfile *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180001460`
- `0x180006f10`
- `0x180007004`
- `0x18000e444`
- `0x18000ea00`
- `0x18000f594`
- `0x18000f6ac`
- `0x180010b88`
- `0x18001187c`
- `0x18001e5b9`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000ea37`
- `KERNEL32!EnterCriticalSection` at `0x18000ea37`
- `KERNEL32!LeaveCriticalSection` at `0x18000efb7`
- `KERNEL32!LeaveCriticalSection` at `0x18000efb7`

## pseudocode

```c
__int64 __fastcall CWMWriter::ConfigureFilterUsingProfile(CWMWriter *this, struct IWMProfile *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int Pin; // edi
  struct IWMProfileVtbl *lpVtbl; // rax
  __int64 v7; // rcx
  int i; // edi
  struct IWMProfileVtbl *v9; // rax
  unsigned int v10; // r13d
  struct IWMProfileVtbl *v11; // rax
  unsigned int v12; // edx
  unsigned int v13; // r8d
  int v14; // esi
  int v15; // eax
  struct __POSITION *v16; // rsi
  __int64 v17; // rcx
  struct __POSITION *v18; // r12
  __int64 v19; // r15
  __int64 v20; // r13
  int v21; // esi
  __int64 v22; // rcx
  int v23; // eax
  struct IWMStreamConfig *v24; // rcx
  unsigned int v25; // edx
  unsigned int v26; // r8d
  void *v27; // rax
  __int64 v28; // rcx
  bool v30; // [rsp+30h] [rbp-39h] BYREF
  __int64 v31; // [rsp+38h] [rbp-31h] BYREF
  struct IWMStreamConfig *v32; // [rsp+40h] [rbp-29h] BYREF
  int v33; // [rsp+48h] [rbp-21h] BYREF
  int v34; // [rsp+4Ch] [rbp-1Dh] BYREF
  __int128 Buf2; // [rsp+50h] [rbp-19h] BYREF
  struct __POSITION *v36[2]; // [rsp+60h] [rbp-9h] BYREF
  int v37; // [rsp+70h] [rbp+7h]
  __int64 v38; // [rsp+78h] [rbp+Fh]
  __int64 v39; // [rsp+80h] [rbp+17h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( !a2 )
  {
    Pin = -2147467261;
    goto LABEL_81;
  }
  if ( !*((_QWORD *)this + 20) )
  {
    Pin = -2147467259;
    goto LABEL_81;
  }
  if ( *((_DWORD *)this - 28) )
  {
    Pin = -2147220953;
    goto LABEL_81;
  }
  v37 = 0;
  v38 = 10;
  v39 = 0;
  *(_OWORD *)v36 = 0;
  CWMWriter::PrepareForReconnect((char *)this - 152, v36);
  CWMWriter::DeleteProfile((CWMWriter *)((char *)this - 152));
  CWMWriter::DeletePins((CWMWriter *)((char *)this - 152), 1);
  Pin = (*(__int64 (__fastcall **)(_QWORD, struct IWMProfile *))(**((_QWORD **)this + 20) + 32LL))(
          *((_QWORD *)this + 20),
          a2);
  if ( Pin < 0 )
    goto LABEL_77;
  lpVtbl = a2->lpVtbl;
  v31 = 0;
  if ( ((__int64 (__fastcall *)(struct IWMProfile *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a2,
         &IID_IWMProfile2,
         &v31) >= 0 )
  {
    if ( (*(int (__fastcall **)(__int64, char *))(*(_QWORD *)v31 + 168LL))(v31, (char *)this + 212) >= 0 )
      *((_DWORD *)this + 57) = 1;
    else
      *(GUID *)((char *)this + 212) = GUID_NULL;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  *((_QWORD *)this + 24) = a2;
  ((void (__fastcall *)(struct IWMProfile *))a2->lpVtbl->AddRef)(a2);
  v7 = *((_QWORD *)this + 20);
  v33 = 0;
  Pin = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v7 + 48LL))(v7, &v33);
  if ( Pin < 0 )
    goto LABEL_77;
  if ( *((_DWORD *)this + 20) )
  {
    for ( i = 0; i < v33; ++i )
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 20) + 64LL))(
        *((_QWORD *)this + 20),
        (unsigned int)i,
        0);
  }
  v9 = a2->lpVtbl;
  v34 = 0;
  Pin = ((__int64 (__fastcall *)(struct IWMProfile *, int *))v9->GetStreamCount)(a2, &v34);
  if ( Pin < 0 )
    goto LABEL_77;
  if ( v34 == v33 )
  {
    v10 = 0;
    if ( v34 <= 0 )
      goto LABEL_39;
    while ( 1 )
    {
      v11 = a2->lpVtbl;
      v32 = 0;
      Pin = ((__int64 (__fastcall *)(struct IWMProfile *, _QWORD, struct IWMStreamConfig **))v11->GetStream)(
              a2,
              v10,
              &v32);
      if ( Pin >= 0 )
      {
        Buf2 = 0;
        Pin = ((__int64 (__fastcall *)(struct IWMStreamConfig *, __int128 *))v32->lpVtbl->GetStreamType)(v32, &Buf2);
        if ( Pin >= 0 )
        {
          if ( !memcmp_0(&MEDIATYPE_Audio, &Buf2, 0x10u) )
          {
            v13 = 1;
            goto LABEL_34;
          }
          if ( !memcmp_0(&MEDIATYPE_Video, &Buf2, 0x10u) )
          {
            v13 = 2;
            goto LABEL_34;
          }
          if ( !memcmp_0(&WMMEDIATYPE_FileTransfer, &Buf2, 0x10u) )
          {
            v13 = 3;
            goto LABEL_34;
          }
          if ( !memcmp_0(&WMMEDIATYPE_Script, &Buf2, 0x10u) )
          {
            v13 = 4;
            goto LABEL_34;
          }
          if ( !memcmp_0(&WMMEDIATYPE_Image, &Buf2, 0x10u) )
          {
            v13 = 6;
            goto LABEL_34;
          }
          if ( !memcmp_0(&WMMEDIATYPE_Text, &Buf2, 0x10u) )
          {
            v13 = 5;
LABEL_34:
            Pin = CWMWriter::AddNextPin((CWMWriter *)((char *)this - 152), v12, v13, v32);
            if ( Pin < 0 )
              goto LABEL_70;
          }
        }
      }
      if ( v32 )
        ((void (__fastcall *)(struct IWMStreamConfig *))v32->lpVtbl->Release)(v32);
      if ( (int)++v10 >= v34 )
        goto LABEL_38;
    }
  }
  v21 = 0;
  if ( v33 <= 0 )
    goto LABEL_39;
  do
  {
    v22 = *((_QWORD *)this + 20);
    v32 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct IWMStreamConfig **))(*(_QWORD *)v22 + 80LL))(
            v22,
            (unsigned int)v21,
            0,
            &v32);
    v24 = v32;
    Pin = v23;
    if ( v23 < 0 )
      goto LABEL_71;
    Buf2 = 0;
    Pin = ((__int64 (__fastcall *)(struct IWMStreamConfig *, __int128 *))v32->lpVtbl->GetStreamType)(v32, &Buf2);
    if ( Pin >= 0 )
    {
      if ( !memcmp_0(&MEDIATYPE_Audio, &Buf2, 0x10u) )
      {
        v26 = 1;
      }
      else if ( !memcmp_0(&MEDIATYPE_Video, &Buf2, 0x10u) )
      {
        v26 = 2;
      }
      else if ( !memcmp_0(&WMMEDIATYPE_FileTransfer, &Buf2, 0x10u) )
      {
        v26 = 3;
      }
      else if ( !memcmp_0(&WMMEDIATYPE_Script, &Buf2, 0x10u) )
      {
        v26 = 4;
      }
      else if ( !memcmp_0(&WMMEDIATYPE_Image, &Buf2, 0x10u) )
      {
        v26 = 6;
      }
      else
      {
        if ( memcmp_0(&WMMEDIATYPE_Text, &Buf2, 0x10u) )
          goto LABEL_66;
        v26 = 5;
      }
      Pin = CWMWriter::AddNextPin((CWMWriter *)((char *)this - 152), v25, v26, 0);
      if ( Pin < 0 )
      {
LABEL_70:
        v24 = v32;
LABEL_71:
        if ( v24 )
          ((void (__fastcall *)(struct IWMStreamConfig *))v24->lpVtbl->Release)(v24);
        goto LABEL_77;
      }
    }
LABEL_66:
    if ( v32 )
      ((void (__fastcall *)(struct IWMStreamConfig *))v32->lpVtbl->Release)(v32);
    ++v21;
  }
  while ( v21 < v33 );
LABEL_38:
  if ( Pin < 0 )
    goto LABEL_77;
LABEL_39:
  v30 = 0;
  Pin = CWMWriter::SetupDataUnitExtensions((CWMWriter *)((char *)this - 152), &v30);
  if ( Pin >= 0 )
  {
    if ( !v30 )
      goto LABEL_45;
    if ( !*((_DWORD *)this + 20) )
      goto LABEL_45;
    v14 = 0;
    if ( v33 <= 0 )
      goto LABEL_45;
    do
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 20) + 64LL))(
              *((_QWORD *)this + 20),
              (unsigned int)v14++,
              0);
      Pin = v15;
    }
    while ( v14 < v33 );
    if ( v15 >= 0 )
    {
LABEL_45:
      v16 = v36[0];
      if ( v36[0] )
      {
        do
        {
          v17 = *((_QWORD *)this + 32);
          v18 = (struct __POSITION *)*((_QWORD *)v16 + 1);
          v19 = *((_QWORD *)v16 + 2);
          if ( v17 )
          {
            while ( 1 )
            {
              v20 = *(_QWORD *)(v17 + 8);
              if ( (*(int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v19 + 24LL))(
                     v19,
                     (*(_QWORD *)(v17 + 16) + 24LL) & -(__int64)(*(_QWORD *)(v17 + 16) != 0),
                     0) >= 0 )
                break;
              v17 = v20;
              if ( !v20 )
                goto LABEL_74;
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
            CBaseList::RemoveI((CBaseList *)v36, v16);
          }
LABEL_74:
          v16 = v18;
        }
        while ( v18 );
      }
    }
  }
LABEL_77:
  while ( 1 )
  {
    v27 = CBaseList::RemoveI((CBaseList *)v36, v36[0]);
    if ( !v27 )
      break;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = *((_QWORD *)this - 6);
  if ( v28 )
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v28 + 24LL))(v28, 80, 0);
  CBaseList::~CBaseList((CBaseList *)v36);
LABEL_81:
  LeaveCriticalSection(v2);
  return (unsigned int)Pin;
}

```

## disassembly

```asm
0x18000ea00  mov     [rsp-8+arg_10], rbx
0x18000ea05  push    rbp
0x18000ea06  push    rsi
0x18000ea07  push    rdi
0x18000ea08  push    r12
0x18000ea0a  push    r13
0x18000ea0c  push    r14
0x18000ea0e  push    r15
0x18000ea10  lea     rbp, [rsp-27h]
0x18000ea15  sub     rsp, 90h
0x18000ea1c  mov     rax, cs:__security_cookie
0x18000ea23  xor     rax, rsp
0x18000ea26  mov     [rbp+57h+var_38], rax
0x18000ea2a  lea     rbx, [rcx+58h]
0x18000ea2e  mov     r14, rcx
0x18000ea31  mov     rcx, rbx; lpCriticalSection
0x18000ea34  mov     rsi, rdx
0x18000ea37  call    cs:__imp_EnterCriticalSection
0x18000ea3d  test    rsi, rsi
0x18000ea40  jnz     short loc_18000EA4C
0x18000ea42  mov     edi, 80004003h
0x18000ea47  jmp     loc_18000EFB4
0x18000ea4c  lea     r15, [r14-98h]
0x18000ea53  cmp     qword ptr [r15+138h], 0
0x18000ea5b  jnz     short loc_18000EA67
0x18000ea5d  mov     edi, 80004005h
0x18000ea62  jmp     loc_18000EFB4
0x18000ea67  cmp     dword ptr [r14-70h], 0
0x18000ea6c  jz      short loc_18000EA78
0x18000ea6e  mov     edi, 80040227h
0x18000ea73  jmp     loc_18000EFB4
0x18000ea78  xorps   xmm0, xmm0
0x18000ea7b  mov     [rbp+57h+var_50], 0
0x18000ea82  lea     rdx, [rbp+57h+var_60]
0x18000ea86  mov     [rbp+57h+var_48], 0Ah
0x18000ea8e  mov     rcx, r15
0x18000ea91  mov     [rbp+57h+var_40], 0
0x18000ea99  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18000ea9e  call    ?PrepareForReconnect@CWMWriter@@AEAAJAEAV?$CGenericList@UIPin@@@@@Z; CWMWriter::PrepareForReconnect(CGenericList<IPin> &)
0x18000eaa3  mov     rcx, r15; this
0x18000eaa6  call    ?DeleteProfile@CWMWriter@@QEAAXXZ; CWMWriter::DeleteProfile(void)
0x18000eaab  mov     r13d, 1
0x18000eab1  mov     rcx, r15; this
0x18000eab4  mov     edx, r13d; int
0x18000eab7  call    ?DeletePins@CWMWriter@@QEAAXH@Z; CWMWriter::DeletePins(int)
0x18000eabc  mov     rcx, [r14+0A0h]
0x18000eac3  mov     rdx, rsi
0x18000eac6  mov     rax, [rcx]
0x18000eac9  mov     rax, [rax+20h]
0x18000eacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ead2  mov     edi, eax
0x18000ead4  test    eax, eax
0x18000ead6  js      loc_18000EF77
0x18000eadc  mov     rax, [rsi]
0x18000eadf  lea     r8, [rbp+57h+var_88]
0x18000eae3  lea     rdx, IID_IWMProfile2
0x18000eaea  mov     [rbp+57h+var_88], 0
0x18000eaf2  mov     rcx, rsi
0x18000eaf5  mov     rax, [rax]
0x18000eaf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eafd  test    eax, eax
0x18000eaff  js      short loc_18000EB46
0x18000eb01  mov     rcx, [rbp+57h+var_88]
0x18000eb05  lea     rdi, [r14+0D4h]
0x18000eb0c  mov     rdx, rdi
0x18000eb0f  mov     rax, [rcx]
0x18000eb12  mov     rax, [rax+0A8h]
0x18000eb19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb1e  test    eax, eax
0x18000eb20  jns     short loc_18000EB2F
0x18000eb22  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000eb29  movdqu  xmmword ptr [rdi], xmm0
0x18000eb2d  jmp     short loc_18000EB36
0x18000eb2f  mov     [r14+0E4h], r13d
0x18000eb36  mov     rcx, [rbp+57h+var_88]
0x18000eb3a  mov     rax, [rcx]
0x18000eb3d  mov     rax, [rax+10h]
0x18000eb41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb46  mov     [r14+0C0h], rsi
0x18000eb4d  mov     rcx, rsi
0x18000eb50  mov     rax, [rsi]
0x18000eb53  mov     rax, [rax+8]
0x18000eb57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb5c  mov     rcx, [r14+0A0h]
0x18000eb63  lea     rdx, [rbp+57h+var_78]
0x18000eb67  mov     [rbp+57h+var_78], 0
0x18000eb6e  mov     rax, [rcx]
0x18000eb71  mov     rax, [rax+30h]
0x18000eb75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb7a  mov     edi, eax
0x18000eb7c  test    eax, eax
0x18000eb7e  js      loc_18000EF77
0x18000eb84  cmp     dword ptr [r14+50h], 0
0x18000eb89  jz      short loc_18000EBB2
0x18000eb8b  xor     edi, edi
0x18000eb8d  cmp     [rbp+57h+var_78], edi
0x18000eb90  jle     short loc_18000EBB2
0x18000eb92  mov     rcx, [r14+0A0h]
0x18000eb99  xor     r8d, r8d
0x18000eb9c  mov     edx, edi
0x18000eb9e  mov     rax, [rcx]
0x18000eba1  mov     rax, [rax+40h]
0x18000eba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebaa  add     edi, r13d
0x18000ebad  cmp     edi, [rbp+57h+var_78]
0x18000ebb0  jl      short loc_18000EB92
0x18000ebb2  mov     rax, [rsi]
0x18000ebb5  lea     rdx, [rbp+57h+var_74]
0x18000ebb9  mov     rcx, rsi
0x18000ebbc  mov     [rbp+57h+var_74], 0
0x18000ebc3  mov     rax, [rax+40h]
0x18000ebc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebcc  mov     edi, eax
0x18000ebce  test    eax, eax
0x18000ebd0  js      loc_18000EF77
0x18000ebd6  mov     ecx, [rbp+57h+var_74]
0x18000ebd9  mov     eax, [rbp+57h+var_78]
0x18000ebdc  cmp     ecx, eax
0x18000ebde  jnz     loc_18000EDE7
0x18000ebe4  xor     r13d, r13d
0x18000ebe7  test    ecx, ecx
0x18000ebe9  jle     loc_18000ED2F
0x18000ebef  lea     r12d, [r13+10h]
0x18000ebf3  mov     rax, [rsi]
0x18000ebf6  lea     r8, [rbp+57h+var_80]
0x18000ebfa  mov     edx, r13d
0x18000ebfd  mov     [rbp+57h+var_80], 0
0x18000ec05  mov     rcx, rsi
0x18000ec08  mov     rax, [rax+48h]
0x18000ec0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec11  mov     edi, eax
0x18000ec13  test    eax, eax
0x18000ec15  js      loc_18000ED05
0x18000ec1b  mov     rcx, [rbp+57h+var_80]
0x18000ec1f  lea     rdx, [rbp+57h+Buf2]
0x18000ec23  xorps   xmm0, xmm0
0x18000ec26  movups  [rbp+57h+Buf2], xmm0
0x18000ec2a  mov     rax, [rcx]
0x18000ec2d  mov     rax, [rax+18h]
0x18000ec31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec36  mov     edi, eax
0x18000ec38  test    eax, eax
0x18000ec3a  js      loc_18000ED05
0x18000ec40  mov     r8, r12; Size
0x18000ec43  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18000ec47  lea     rcx, MEDIATYPE_Audio; Buf1
0x18000ec4e  call    memcmp_0
0x18000ec53  test    eax, eax
0x18000ec55  jnz     short loc_18000EC60
0x18000ec57  lea     r8d, [rax+1]
0x18000ec5b  jmp     loc_18000ECEF
0x18000ec60  mov     r8, r12; Size
0x18000ec63  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18000ec67  lea     rcx, MEDIATYPE_Video; Buf1
0x18000ec6e  call    memcmp_0
0x18000ec73  test    eax, eax
0x18000ec75  jnz     short loc_18000EC7D
0x18000ec77  lea     r8d, [rax+2]
0x18000ec7b  jmp     short loc_18000ECEF
0x18000ec7d  mov     r8, r12; Size
0x18000ec80  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18000ec84  lea     rcx, WMMEDIATYPE_FileTransfer; Buf1
0x18000ec8b  call    memcmp_0
0x18000ec90  test    eax, eax
0x18000ec92  jnz     short loc_18000EC9A
0x18000ec94  lea     r8d, [rax+3]
0x18000ec98  jmp     short loc_18000ECEF
0x18000ec9a  mov     r8, r12; Size
0x18000ec9d  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18000eca1  lea     rcx, WMMEDIATYPE_Script; Buf1
0x18000eca8  call    memcmp_0
0x18000ecad  test    eax, eax
0x18000ecaf  jnz     short loc_18000ECB7
0x18000ecb1  lea     r8d, [rax+4]
0x18000ecb5  jmp     short loc_18000ECEF
0x18000ecb7  mov     r8, r12; Size
0x18000ecba  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18000ecbe  lea     rcx, WMMEDIATYPE_Image; Buf1
0x18000ecc5  call    memcmp_0
0x18000ecca  test    eax, eax
0x18000eccc  jnz     short loc_18000ECD4
0x18000ecce  lea     r8d, [rax+6]
0x18000ecd2  jmp     short loc_18000ECEF
0x18000ecd4  mov     r8, r12; Size
0x18000ecd7  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18000ecdb  lea     rcx, WMMEDIATYPE_Text; Buf1
0x18000ece2  call    memcmp_0
0x18000ece7  test    eax, eax
0x18000ece9  jnz     short loc_18000ED05
0x18000eceb  lea     r8d, [rax+5]; unsigned int
0x18000ecef  mov     r9, [rbp+57h+var_80]; struct IWMStreamConfig *
0x18000ecf3  mov     rcx, r15; this
0x18000ecf6  call    ?AddNextPin@CWMWriter@@AEAAJIKPEAUIWMStreamConfig@@@Z; CWMWriter::AddNextPin(uint,ulong,IWMStreamConfig *)
0x18000ecfb  mov     edi, eax
0x18000ecfd  test    eax, eax
0x18000ecff  js      loc_18000EF2D
0x18000ed05  mov     rcx, [rbp+57h+var_80]
0x18000ed09  test    rcx, rcx
0x18000ed0c  jz      short loc_18000ED1A
0x18000ed0e  mov     rax, [rcx]
0x18000ed11  mov     rax, [rax+10h]
0x18000ed15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed1a  inc     r13d
0x18000ed1d  cmp     r13d, [rbp+57h+var_74]
0x18000ed21  jl      loc_18000EBF3
0x18000ed27  test    edi, edi
0x18000ed29  js      loc_18000EF77
0x18000ed2f  lea     rdx, [rbp+57h+var_90]; bool *
0x18000ed33  mov     [rbp+57h+var_90], 0
0x18000ed37  mov     rcx, r15; this
0x18000ed3a  call    ?SetupDataUnitExtensions@CWMWriter@@IEAAJPEA_N@Z; CWMWriter::SetupDataUnitExtensions(bool *)
0x18000ed3f  mov     edi, eax
0x18000ed41  test    eax, eax
0x18000ed43  js      loc_18000EF77
0x18000ed49  cmp     [rbp+57h+var_90], 0
0x18000ed4d  jz      short loc_18000ED86
0x18000ed4f  cmp     dword ptr [r14+50h], 0
0x18000ed54  jz      short loc_18000ED86
0x18000ed56  xor     esi, esi
0x18000ed58  cmp     [rbp+57h+var_78], esi
0x18000ed5b  jle     short loc_18000ED86
0x18000ed5d  mov     rcx, [r14+0A0h]
0x18000ed64  xor     r8d, r8d
0x18000ed67  mov     edx, esi
0x18000ed69  mov     rax, [rcx]
0x18000ed6c  mov     rax, [rax+40h]
0x18000ed70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed75  inc     esi
0x18000ed77  mov     edi, eax
0x18000ed79  cmp     esi, [rbp+57h+var_78]
0x18000ed7c  jl      short loc_18000ED5D
0x18000ed7e  test    eax, eax
0x18000ed80  js      loc_18000EF77
0x18000ed86  mov     rsi, [rbp+57h+var_60]
0x18000ed8a  test    rsi, rsi
0x18000ed8d  jz      loc_18000EF77
0x18000ed93  mov     rcx, [r14+100h]
0x18000ed9a  mov     r12, [rsi+8]
0x18000ed9e  mov     r15, [rsi+10h]
0x18000eda2  test    rcx, rcx
0x18000eda5  jz      loc_18000EF5A
0x18000edab  mov     r13, [rcx+8]
0x18000edaf  mov     rcx, [rcx+10h]
0x18000edb3  mov     r9, [r15]
0x18000edb6  lea     rax, [rcx+18h]
0x18000edba  neg     rcx
0x18000edbd  mov     rcx, r15
0x18000edc0  sbb     rdx, rdx
0x18000edc3  xor     r8d, r8d
0x18000edc6  and     rdx, rax
0x18000edc9  mov     rax, [r9+18h]
0x18000edcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edd2  test    eax, eax
0x18000edd4  jns     loc_18000EF3F
0x18000edda  mov     rcx, r13
0x18000eddd  test    r13, r13
0x18000ede0  jnz     short loc_18000EDAB
0x18000ede2  jmp     loc_18000EF5A
0x18000ede7  xor     esi, esi
0x18000ede9  test    eax, eax
0x18000edeb  jle     loc_18000ED2F
0x18000edf1  lea     r12d, [rsi+10h]
0x18000edf5  mov     rcx, [r14+0A0h]
0x18000edfc  lea     r9, [rbp+57h+var_80]
0x18000ee00  mov     [rbp+57h+var_80], 0
0x18000ee08  xor     r8d, r8d
0x18000ee0b  mov     edx, esi
0x18000ee0d  mov     rax, [rcx]
0x18000ee10  mov     rax, [rax+50h]
0x18000ee14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee19  mov     rcx, [rbp+57h+var_80]
0x18000ee1d  mov     edi, eax
0x18000ee1f  test    eax, eax
0x18000ee21  js      loc_18000EF31
0x18000ee27  xorps   xmm0, xmm0
0x18000ee2a  lea     rdx, [rbp+57h+Buf2]
0x18000ee2e  movups  [rbp+57h+Buf2], xmm0
0x18000ee32  mov     rax, [rcx]
0x18000ee35  mov     rax, [rax+18h]
0x18000ee39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee3e  mov     edi, eax
0x18000ee40  test    eax, eax
0x18000ee42  js      loc_18000EF07
0x18000ee48  mov     r8, r12; Size
0x18000ee4b  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18000ee4f  lea     rcx, MEDIATYPE_Audio; Buf1
0x18000ee56  call    memcmp_0
0x18000ee5b  test    eax, eax
0x18000ee5d  jnz     short loc_18000EE67
0x18000ee5f  mov     r8d, r13d
0x18000ee62  jmp     loc_18000EEF6
0x18000ee67  mov     r8, r12; Size
0x18000ee6a  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18000ee6e  lea     rcx, MEDIATYPE_Video; Buf1
0x18000ee75  call    memcmp_0
0x18000ee7a  test    eax, eax
0x18000ee7c  jnz     short loc_18000EE84
0x18000ee7e  lea     r8d, [rax+2]
0x18000ee82  jmp     short loc_18000EEF6
0x18000ee84  mov     r8, r12; Size
  ... truncated ...
```
