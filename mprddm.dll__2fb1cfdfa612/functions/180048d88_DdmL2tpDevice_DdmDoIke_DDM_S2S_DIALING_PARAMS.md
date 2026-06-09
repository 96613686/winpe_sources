# DdmL2tpDevice::DdmDoIke(_DDM_S2S_DIALING_PARAMS &)

- ea: `0x180048d88`
- end: `0x1800490cd`
- name: `?DdmDoIke@DdmL2tpDevice@@AEAAKAEAU_DDM_S2S_DIALING_PARAMS@@@Z`
- size: `837`
- prototype: `unsigned int __fastcall(DdmL2tpDevice *__hidden this, struct _DDM_S2S_DIALING_PARAMS *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180049b70`

## callees

- `0x180007b7c`
- `0x180048d88`
- `0x1800490d4`
- `0x1800492cc`
- `0x1800497a8`
- `0x180071cec`
- `0x18007fbcc`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180048fae`
- `KERNEL32!CloseHandle` at `0x180048fae`
- `KERNEL32!GetLastError` at `0x180048ebd`
- `KERNEL32!GetLastError` at `0x180048ebd`
- `KERNEL32!CreateEventW` at `0x180048eaf`
- `KERNEL32!CreateEventW` at `0x180048eaf`
- `KERNEL32!WaitForSingleObject` at `0x180048f7b`
- `KERNEL32!WaitForSingleObject` at `0x180048f7b`

## string_xrefs

- `0x180048eda`: `DdmL2tpDevice::DdmDoIke: CreateEvent failed. 0x%x`

## pseudocode

```c
__int64 __fastcall DdmL2tpDevice::DdmDoIke(DdmL2tpDevice *this, struct _DDM_S2S_DIALING_PARAMS *a2)
{
  DdmL2tpDevice *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rsi
  unsigned int IkeStatus; // ebx
  unsigned int v8; // eax
  __int64 v9; // r8
  __int64 v10; // rax
  HANDLE EventW; // rax
  void *v12; // r14
  DWORD LastError; // eax
  __int128 v14; // xmm0
  unsigned int v15; // eax
  DdmL2tpDevice *v16; // rcx
  DWORD v17; // eax
  unsigned int v19[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+60h] [rbp-A0h]
  __int128 v22; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v23; // [rsp+80h] [rbp-80h]
  __int64 v24; // [rsp+88h] [rbp-78h]
  int v25; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v26[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v19[0] = 0;
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v6 = -1;
  if ( g_dwProhibitIpsec )
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v24 = 114;
      v23 = L"DdmL2tpDevice::DdmDoIke:  ProhibitIpSec=1. Not Doing Ike";
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v5, 2, &v22);
    }
    IkeStatus = 0;
    goto LABEL_31;
  }
  v8 = DdmL2tpDevice::DdmIsIKESecureCheckDisabled(v4, a2, (int *)v19);
  IkeStatus = v8;
  if ( v8 )
  {
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_31;
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, L"DwDdmL2tpDevice::DdmDoIke:  IsIKESecureCheckEnabled failed with %d", v8);
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_31;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&v26[2 * v10 - 4] );
    goto LABEL_30;
  }
  if ( !*((_DWORD *)a2 + 2236) || !*((_DWORD *)a2 + 2241) )
  {
    IkeStatus = 769;
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_31;
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, L"DdmL2tpDevice::DdmDoIke:  failed to get ipaddress. 0x%x", 769);
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_31;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&v26[2 * v10 - 4] );
LABEL_30:
    v24 = (unsigned int)(2 * v10 + 2);
    v23 = (const wchar_t *)&v25;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v9, 2, &v22);
    goto LABEL_31;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v12 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    IkeStatus = LastError;
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_31;
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, L"DdmL2tpDevice::DdmDoIke: CreateEvent failed. 0x%x", LastError);
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_31;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&v26[2 * v10 - 4] );
    goto LABEL_30;
  }
  v14 = *((_OWORD *)a2 + 559);
  v21 = *((_DWORD *)a2 + 2240);
  LODWORD(v23) = *((_DWORD *)a2 + 2245);
  v20 = v14;
  v22 = *(_OWORD *)((char *)a2 + 8964);
  v15 = DwDoIke((_DWORD)EventW, (int)a2 + 58, v19[0], (unsigned int)&v22, (__int64)&v20);
  IkeStatus = v15;
  if ( v15 )
    IkeStatus = DdmL2tpDevice::DdmMapOakleyErrorToRasError(v16, v15, a2);
  do
    v17 = WaitForSingleObject(v12, 0x1F4u);
  while ( v17 == 258 );
  if ( !v17 )
  {
    v19[0] = 0;
    IkeStatus = DdmL2tpDevice::DdmDwQueryIkeStatus(this, a2, v19);
    if ( !IkeStatus )
      IkeStatus = v19[0];
  }
  CloseHandle(v12);
LABEL_31:
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, L"DdmDoIke done. 0x%x", IkeStatus);
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      do
        ++v6;
      while ( *(_WORD *)&v26[2 * v6 - 4] );
      v24 = (unsigned int)(2 * v6 + 2);
      v23 = (const wchar_t *)&v25;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, &v25, 2, &v22);
    }
  }
  return IkeStatus;
}

```

## disassembly

```asm
0x180048d88  mov     [rsp-8+arg_10], rbx
0x180048d8d  mov     [rsp-8+arg_18], rsi
0x180048d92  push    rbp
0x180048d93  push    rdi
0x180048d94  push    r12
0x180048d96  push    r14
0x180048d98  push    r15
0x180048d9a  lea     rbp, [rsp-7A0h]
0x180048da2  sub     rsp, 8A0h
0x180048da9  mov     rax, cs:__security_cookie
0x180048db0  xor     rax, rsp
0x180048db3  mov     [rbp+7C0h+var_30], rax
0x180048dba  mov     rdi, rdx
0x180048dbd  mov     r15, rcx
0x180048dc0  xor     r12d, r12d
0x180048dc3  lea     rcx, [rbp+7C0h+var_82C]; void *
0x180048dc7  xor     edx, edx; Val
0x180048dc9  mov     [rsp+8C0h+var_880], r12d
0x180048dce  mov     r8d, 7FCh; Size
0x180048dd4  mov     [rbp+7C0h+var_830], r12d
0x180048dd8  call    memset_0
0x180048ddd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180048de1  cmp     cs:g_dwProhibitIpsec, r12d
0x180048de8  jz      short loc_180048E30
0x180048dea  test    cs:byte_1800C8404, 10h
0x180048df1  jz      short loc_180048E28
0x180048df3  lea     rax, aDdml2tpdeviceD_4; "DdmL2tpDevice::DdmDoIke:  ProhibitIpSec"...
0x180048dfa  mov     [rbp+7C0h+var_838], 72h ; 'r'
0x180048e02  mov     [rbp+7C0h+var_840], rax
0x180048e06  lea     r9d, [r12+2]
0x180048e0b  lea     rax, [rsp+8C0h+var_850]
0x180048e10  lea     rdx, RasDdmTraceInfo
0x180048e17  mov     [rsp+8C0h+var_8A0], rax
0x180048e1c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180048e23  call    McGenEventWrite_EventWriteTransfer
0x180048e28  mov     ebx, r12d
0x180048e2b  jmp     loc_18004902F
0x180048e30  lea     r8, [rsp+8C0h+var_880]; int *
0x180048e35  mov     rdx, rdi; struct _DDM_S2S_DIALING_PARAMS *
0x180048e38  call    ?DdmIsIKESecureCheckDisabled@DdmL2tpDevice@@AEAAKAEAU_DDM_S2S_DIALING_PARAMS@@PEAH@Z; DdmL2tpDevice::DdmIsIKESecureCheckDisabled(_DDM_S2S_DIALING_PARAMS &,int *)
0x180048e3d  mov     ebx, eax
0x180048e3f  test    eax, eax
0x180048e41  jz      short loc_180048E8B
0x180048e43  test    cs:byte_1800C8404, 8
0x180048e4a  jz      loc_18004902F
0x180048e50  mov     r8d, eax
0x180048e53  mov     word ptr [rbp+7C0h+var_830], r12w
0x180048e58  lea     rdx, aDwddml2tpdevic; "DwDdmL2tpDevice::DdmDoIke:  IsIKESecure"...
0x180048e5f  lea     rcx, [rbp+7C0h+var_830]
0x180048e63  call    FormatRRASErrorString
0x180048e68  test    cs:byte_1800C8404, 8
0x180048e6f  jz      loc_18004902F
0x180048e75  lea     rcx, [rbp+7C0h+var_830]
0x180048e79  mov     rax, rsi
0x180048e7c  inc     rax
0x180048e7f  cmp     [rcx+rax*2], r12w
0x180048e84  jnz     short loc_180048E7C
0x180048e86  jmp     loc_180048FF6
0x180048e8b  cmp     [rdi+22F0h], r12d
0x180048e92  jz      loc_180048FB6
0x180048e98  cmp     [rdi+2304h], r12d
0x180048e9f  jz      loc_180048FB6
0x180048ea5  xor     r9d, r9d; lpName
0x180048ea8  xor     r8d, r8d; bInitialState
0x180048eab  xor     edx, edx; bManualReset
0x180048ead  xor     ecx, ecx; lpEventAttributes
0x180048eaf  call    cs:__imp_CreateEventW
0x180048eb5  mov     r14, rax
0x180048eb8  test    rax, rax
0x180048ebb  jnz     short loc_180048F0D
0x180048ebd  call    cs:__imp_GetLastError
0x180048ec3  test    cs:byte_1800C8404, 8
0x180048eca  mov     ebx, eax
0x180048ecc  jz      loc_18004902F
0x180048ed2  mov     r8d, eax
0x180048ed5  mov     word ptr [rbp+7C0h+var_830], r12w
0x180048eda  lea     rdx, aDdml2tpdeviceD_2; "DdmL2tpDevice::DdmDoIke: CreateEvent fa"...
0x180048ee1  lea     rcx, [rbp+7C0h+var_830]
0x180048ee5  call    FormatRRASErrorString
0x180048eea  test    cs:byte_1800C8404, 8
0x180048ef1  jz      loc_18004902F
0x180048ef7  lea     rcx, [rbp+7C0h+var_830]
0x180048efb  mov     rax, rsi
0x180048efe  inc     rax
0x180048f01  cmp     [rcx+rax*2], r12w
0x180048f06  jnz     short loc_180048EFE
0x180048f08  jmp     loc_180048FF6
0x180048f0d  mov     eax, [rdi+2300h]
0x180048f13  lea     rdx, [rdi+3Ah]
0x180048f17  movups  xmm0, xmmword ptr [rdi+22F0h]
0x180048f1e  mov     r8d, [rsp+8C0h+var_880]
0x180048f23  lea     r9, [rsp+8C0h+var_850]
0x180048f28  mov     [rsp+8C0h+var_860], eax
0x180048f2c  mov     rcx, r14
0x180048f2f  mov     eax, [rdi+2314h]
0x180048f35  mov     dword ptr [rbp+7C0h+var_840], eax
0x180048f38  lea     rax, [r15+10h]
0x180048f3c  mov     [rsp+8C0h+var_890], rax
0x180048f41  lea     rax, [rsp+8C0h+var_870]
0x180048f46  movaps  [rsp+8C0h+var_870], xmm0
0x180048f4b  movups  xmm0, xmmword ptr [rdi+2304h]
0x180048f52  mov     [rsp+8C0h+var_8A0], rax
0x180048f57  movaps  [rsp+8C0h+var_850], xmm0
0x180048f5c  call    DwDoIke
0x180048f61  mov     ebx, eax
0x180048f63  test    eax, eax
0x180048f65  jz      short loc_180048F73
0x180048f67  mov     r8, rdi; struct _DDM_S2S_DIALING_PARAMS *
0x180048f6a  mov     edx, eax; unsigned int
0x180048f6c  call    ?DdmMapOakleyErrorToRasError@DdmL2tpDevice@@AEAAKKAEAU_DDM_S2S_DIALING_PARAMS@@@Z; DdmL2tpDevice::DdmMapOakleyErrorToRasError(ulong,_DDM_S2S_DIALING_PARAMS &)
0x180048f71  mov     ebx, eax
0x180048f73  mov     edx, 1F4h; dwMilliseconds
0x180048f78  mov     rcx, r14; hHandle
0x180048f7b  call    cs:__imp_WaitForSingleObject
0x180048f81  cmp     eax, 102h
0x180048f86  jz      short loc_180048F73
0x180048f88  test    eax, eax
0x180048f8a  jnz     short loc_180048FAB
0x180048f8c  lea     r8, [rsp+8C0h+var_880]; unsigned int *
0x180048f91  mov     [rsp+8C0h+var_880], r12d
0x180048f96  mov     rdx, rdi; struct _DDM_S2S_DIALING_PARAMS *
0x180048f99  mov     rcx, r15; this
0x180048f9c  call    ?DdmDwQueryIkeStatus@DdmL2tpDevice@@AEAAKAEAU_DDM_S2S_DIALING_PARAMS@@PEAK@Z; DdmL2tpDevice::DdmDwQueryIkeStatus(_DDM_S2S_DIALING_PARAMS &,ulong *)
0x180048fa1  mov     ebx, eax
0x180048fa3  test    eax, eax
0x180048fa5  jnz     short loc_180048FAB
0x180048fa7  mov     ebx, [rsp+8C0h+var_880]
0x180048fab  mov     rcx, r14; hObject
0x180048fae  call    cs:__imp_CloseHandle
0x180048fb4  jmp     short loc_18004902F
0x180048fb6  test    cs:byte_1800C8404, 8
0x180048fbd  mov     ebx, 301h
0x180048fc2  jz      short loc_18004902F
0x180048fc4  mov     r8d, ebx
0x180048fc7  mov     word ptr [rbp+7C0h+var_830], r12w
0x180048fcc  lea     rdx, aDdml2tpdeviceD_1; "DdmL2tpDevice::DdmDoIke:  failed to get"...
0x180048fd3  lea     rcx, [rbp+7C0h+var_830]
0x180048fd7  call    FormatRRASErrorString
0x180048fdc  test    cs:byte_1800C8404, 8
0x180048fe3  jz      short loc_18004902F
0x180048fe5  lea     rcx, [rbp+7C0h+var_830]
0x180048fe9  mov     rax, rsi
0x180048fec  inc     rax
0x180048fef  cmp     [rcx+rax*2], r12w
0x180048ff4  jnz     short loc_180048FEC
0x180048ff6  lea     eax, ds:2[rax*2]
0x180048ffd  mov     dword ptr [rbp+7C0h+var_838+4], r12d
0x180049001  lea     rcx, [rbp+7C0h+var_830]
0x180049005  mov     dword ptr [rbp+7C0h+var_838], eax
0x180049008  lea     rax, [rsp+8C0h+var_850]
0x18004900d  mov     [rbp+7C0h+var_840], rcx
0x180049011  mov     r9d, 2
0x180049017  mov     [rsp+8C0h+var_8A0], rax
0x18004901c  lea     rdx, RasDdmTraceError
0x180049023  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004902a  call    McGenEventWrite_EventWriteTransfer
0x18004902f  test    cs:byte_1800C8404, 10h
0x180049036  jz      short loc_1800490A0
0x180049038  mov     r8d, ebx
0x18004903b  mov     word ptr [rbp+7C0h+var_830], r12w
0x180049040  lea     rdx, aDdmdoikeDone0x; "DdmDoIke done. 0x%x"
0x180049047  lea     rcx, [rbp+7C0h+var_830]
0x18004904b  call    FormatRRASErrorString
0x180049050  test    cs:byte_1800C8404, 10h
0x180049057  jz      short loc_1800490A0
0x180049059  lea     rax, [rbp+7C0h+var_830]
0x18004905d  inc     rsi
0x180049060  cmp     [rax+rsi*2], r12w
0x180049065  jnz     short loc_18004905D
0x180049067  lea     eax, ds:2[rsi*2]
0x18004906e  mov     dword ptr [rbp+7C0h+var_838+4], r12d
0x180049072  mov     dword ptr [rbp+7C0h+var_838], eax
0x180049075  lea     r8, [rbp+7C0h+var_830]
0x180049079  lea     rax, [rsp+8C0h+var_850]
0x18004907e  mov     [rbp+7C0h+var_840], r8
0x180049082  mov     r9d, 2
0x180049088  mov     [rsp+8C0h+var_8A0], rax
0x18004908d  lea     rdx, RasDdmTraceInfo
0x180049094  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004909b  call    McGenEventWrite_EventWriteTransfer
0x1800490a0  mov     eax, ebx
0x1800490a2  mov     rcx, [rbp+7C0h+var_30]
0x1800490a9  xor     rcx, rsp; StackCookie
0x1800490ac  call    __security_check_cookie
0x1800490b1  lea     r11, [rsp+8C0h+var_20]
0x1800490b9  mov     rbx, [r11+40h]
0x1800490bd  mov     rsi, [r11+48h]
0x1800490c1  mov     rsp, r11
0x1800490c4  pop     r15
0x1800490c6  pop     r14
0x1800490c8  pop     r12
0x1800490ca  pop     rdi
0x1800490cb  pop     rbp
0x1800490cc  retn
```
