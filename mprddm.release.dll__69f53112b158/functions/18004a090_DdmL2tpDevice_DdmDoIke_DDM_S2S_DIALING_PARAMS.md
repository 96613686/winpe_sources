# DdmL2tpDevice::DdmDoIke(_DDM_S2S_DIALING_PARAMS &)

- ea: `0x18004a090`
- end: `0x18004a3fb`
- name: `?DdmDoIke@DdmL2tpDevice@@AEAAKAEAU_DDM_S2S_DIALING_PARAMS@@@Z`
- size: `875`
- prototype: `unsigned int __fastcall(DdmL2tpDevice *__hidden this, struct _DDM_S2S_DIALING_PARAMS *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18004af30`

## callees

- `0x180007c0c`
- `0x18004a090`
- `0x18004a404`
- `0x18004a61c`
- `0x18004ab2c`
- `0x1800755b8`
- `0x180084f24`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18004a2dc`
- `KERNEL32!CloseHandle` at `0x18004a2dc`
- `KERNEL32!GetLastError` at `0x18004a1df`
- `KERNEL32!GetLastError` at `0x18004a1df`
- `KERNEL32!CreateEventW` at `0x18004a1cb`
- `KERNEL32!CreateEventW` at `0x18004a1cb`
- `KERNEL32!WaitForSingleObject` at `0x18004a2a3`
- `KERNEL32!WaitForSingleObject` at `0x18004a2a3`

## string_xrefs

- `0x18004a202`: `DdmL2tpDevice::DdmDoIke: CreateEvent failed. 0x%x`

## pseudocode

```c
__int64 __fastcall DdmL2tpDevice::DdmDoIke(DdmL2tpDevice *this, struct _DDM_S2S_DIALING_PARAMS *a2)
{
  DdmL2tpDevice *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rsi
  __int64 v7; // rax
  unsigned int IkeStatus; // ebx
  unsigned int v9; // eax
  __int64 v10; // r8
  __int64 v11; // rax
  HANDLE EventW; // rax
  void *v13; // r14
  DWORD LastError; // eax
  __int128 v15; // xmm0
  unsigned int v16; // eax
  DdmL2tpDevice *v17; // rcx
  DWORD v18; // eax
  unsigned int v20[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v21; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+60h] [rbp-A0h]
  __int128 v23; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v24; // [rsp+80h] [rbp-80h]
  int v25; // [rsp+88h] [rbp-78h]
  int v26; // [rsp+8Ch] [rbp-74h]
  int v27; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v28[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v20[0] = 0;
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v6 = -1;
  if ( g_dwProhibitIpsec )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( aDdml2tpdeviceD_4[v7] );
      v24 = L"DdmL2tpDevice::DdmDoIke:  ProhibitIpSec=1. Not Doing Ike";
      v25 = 2 * v7 + 2;
      v26 = 0;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v5, 2, &v23);
    }
    IkeStatus = 0;
    goto LABEL_33;
  }
  v9 = DdmL2tpDevice::DdmIsIKESecureCheckDisabled(v4, a2, (int *)v20);
  IkeStatus = v9;
  if ( v9 )
  {
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_33;
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"DwDdmL2tpDevice::DdmDoIke:  IsIKESecureCheckEnabled failed with %d", v9);
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_33;
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&v28[2 * v11 - 4] );
    goto LABEL_32;
  }
  if ( !*((_DWORD *)a2 + 2236) || !*((_DWORD *)a2 + 2241) )
  {
    IkeStatus = 769;
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_33;
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"DdmL2tpDevice::DdmDoIke:  failed to get ipaddress. 0x%x", 769);
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_33;
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&v28[2 * v11 - 4] );
LABEL_32:
    v26 = 0;
    v25 = 2 * v11 + 2;
    v24 = (const wchar_t *)&v27;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v10, 2, &v23);
    goto LABEL_33;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v13 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    IkeStatus = LastError;
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_33;
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"DdmL2tpDevice::DdmDoIke: CreateEvent failed. 0x%x", LastError);
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_33;
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&v28[2 * v11 - 4] );
    goto LABEL_32;
  }
  v15 = *((_OWORD *)a2 + 559);
  v22 = *((_DWORD *)a2 + 2240);
  LODWORD(v24) = *((_DWORD *)a2 + 2245);
  v21 = v15;
  v23 = *(_OWORD *)((char *)a2 + 8964);
  v16 = DwDoIke((_DWORD)EventW, (int)a2 + 58, v20[0], (unsigned int)&v23, (__int64)&v21);
  IkeStatus = v16;
  if ( v16 )
    IkeStatus = DdmL2tpDevice::DdmMapOakleyErrorToRasError(v17, v16, a2);
  do
    v18 = WaitForSingleObject(v13, 0x1F4u);
  while ( v18 == 258 );
  if ( !v18 )
  {
    v20[0] = 0;
    IkeStatus = DdmL2tpDevice::DdmDwQueryIkeStatus(this, a2, v20);
    if ( !IkeStatus )
      IkeStatus = v20[0];
  }
  CloseHandle(v13);
LABEL_33:
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"DdmDoIke done. 0x%x", IkeStatus);
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      do
        ++v6;
      while ( *(_WORD *)&v28[2 * v6 - 4] );
      v26 = 0;
      v25 = 2 * v6 + 2;
      v24 = (const wchar_t *)&v27;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, &v27, 2, &v23);
    }
  }
  return IkeStatus;
}

```

## disassembly

```asm
0x18004a090  mov     [rsp-8+arg_10], rbx
0x18004a095  push    rbp
0x18004a096  push    rsi
0x18004a097  push    rdi
0x18004a098  push    r12
0x18004a09a  push    r13
0x18004a09c  push    r14
0x18004a09e  push    r15
0x18004a0a0  lea     rbp, [rsp-7A0h]
0x18004a0a8  sub     rsp, 8A0h
0x18004a0af  mov     rax, cs:__security_cookie
0x18004a0b6  xor     rax, rsp
0x18004a0b9  mov     [rbp+7D0h+var_40], rax
0x18004a0c0  mov     rdi, rdx
0x18004a0c3  mov     r15, rcx
0x18004a0c6  xor     r12d, r12d
0x18004a0c9  lea     rcx, [rbp+7D0h+var_83C]; void *
0x18004a0cd  xor     edx, edx; Val
0x18004a0cf  mov     [rsp+8D0h+var_890], r12d
0x18004a0d4  mov     r8d, 7FCh; Size
0x18004a0da  mov     [rbp+7D0h+var_840], r12d
0x18004a0de  call    memset_0
0x18004a0e3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004a0e7  lea     r13d, [r12+2]
0x18004a0ec  cmp     cs:g_dwProhibitIpsec, r12d
0x18004a0f3  jz      short loc_18004A14C
0x18004a0f5  test    cs:byte_1800CF404, 10h
0x18004a0fc  jz      short loc_18004A144
0x18004a0fe  lea     rcx, aDdml2tpdeviceD_4; "DdmL2tpDevice::DdmDoIke:  ProhibitIpSec"...
0x18004a105  mov     rax, rsi
0x18004a108  inc     rax
0x18004a10b  cmp     [rcx+rax*2], r12w
0x18004a110  jnz     short loc_18004A108
0x18004a112  lea     eax, ds:2[rax*2]
0x18004a119  mov     [rbp+7D0h+var_850], rcx
0x18004a11d  mov     [rbp+7D0h+var_848], eax
0x18004a120  lea     rdx, RasDdmTraceInfo
0x18004a127  lea     rax, [rsp+8D0h+var_860]
0x18004a12c  mov     [rbp+7D0h+var_844], r12d
0x18004a130  mov     r9d, r13d
0x18004a133  mov     [rsp+8D0h+var_8B0], rax
0x18004a138  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004a13f  call    McGenEventWrite_EventWriteTransfer
0x18004a144  mov     ebx, r12d
0x18004a147  jmp     loc_18004A360
0x18004a14c  lea     r8, [rsp+8D0h+var_890]; int *
0x18004a151  mov     rdx, rdi; struct _DDM_S2S_DIALING_PARAMS *
0x18004a154  call    ?DdmIsIKESecureCheckDisabled@DdmL2tpDevice@@AEAAKAEAU_DDM_S2S_DIALING_PARAMS@@PEAH@Z; DdmL2tpDevice::DdmIsIKESecureCheckDisabled(_DDM_S2S_DIALING_PARAMS &,int *)
0x18004a159  mov     ebx, eax
0x18004a15b  test    eax, eax
0x18004a15d  jz      short loc_18004A1A7
0x18004a15f  test    cs:byte_1800CF404, 8
0x18004a166  jz      loc_18004A360
0x18004a16c  mov     r8d, eax
0x18004a16f  mov     word ptr [rbp+7D0h+var_840], r12w
0x18004a174  lea     rdx, aDwddml2tpdevic; "DwDdmL2tpDevice::DdmDoIke:  IsIKESecure"...
0x18004a17b  lea     rcx, [rbp+7D0h+var_840]
0x18004a17f  call    FormatRRASErrorString
0x18004a184  test    cs:byte_1800CF404, 8
0x18004a18b  jz      loc_18004A360
0x18004a191  lea     rcx, [rbp+7D0h+var_840]
0x18004a195  mov     rax, rsi
0x18004a198  inc     rax
0x18004a19b  cmp     [rcx+rax*2], r12w
0x18004a1a0  jnz     short loc_18004A198
0x18004a1a2  jmp     loc_18004A32A
0x18004a1a7  cmp     [rdi+22F0h], r12d
0x18004a1ae  jz      loc_18004A2EA
0x18004a1b4  cmp     [rdi+2304h], r12d
0x18004a1bb  jz      loc_18004A2EA
0x18004a1c1  xor     r9d, r9d; lpName
0x18004a1c4  xor     r8d, r8d; bInitialState
0x18004a1c7  xor     edx, edx; bManualReset
0x18004a1c9  xor     ecx, ecx; lpEventAttributes
0x18004a1cb  call    cs:__imp_CreateEventW
0x18004a1d2  nop     dword ptr [rax+rax+00h]
0x18004a1d7  mov     r14, rax
0x18004a1da  test    rax, rax
0x18004a1dd  jnz     short loc_18004A235
0x18004a1df  call    cs:__imp_GetLastError
0x18004a1e6  nop     dword ptr [rax+rax+00h]
0x18004a1eb  test    cs:byte_1800CF404, 8
0x18004a1f2  mov     ebx, eax
0x18004a1f4  jz      loc_18004A360
0x18004a1fa  mov     r8d, eax
0x18004a1fd  mov     word ptr [rbp+7D0h+var_840], r12w
0x18004a202  lea     rdx, aDdml2tpdeviceD_2; "DdmL2tpDevice::DdmDoIke: CreateEvent fa"...
0x18004a209  lea     rcx, [rbp+7D0h+var_840]
0x18004a20d  call    FormatRRASErrorString
0x18004a212  test    cs:byte_1800CF404, 8
0x18004a219  jz      loc_18004A360
0x18004a21f  lea     rcx, [rbp+7D0h+var_840]
0x18004a223  mov     rax, rsi
0x18004a226  inc     rax
0x18004a229  cmp     [rcx+rax*2], r12w
0x18004a22e  jnz     short loc_18004A226
0x18004a230  jmp     loc_18004A32A
0x18004a235  mov     eax, [rdi+2300h]
0x18004a23b  lea     rdx, [rdi+3Ah]
0x18004a23f  movups  xmm0, xmmword ptr [rdi+22F0h]
0x18004a246  mov     r8d, [rsp+8D0h+var_890]
0x18004a24b  lea     r9, [rsp+8D0h+var_860]
0x18004a250  mov     [rsp+8D0h+var_870], eax
0x18004a254  mov     rcx, r14
0x18004a257  mov     eax, [rdi+2314h]
0x18004a25d  mov     dword ptr [rbp+7D0h+var_850], eax
0x18004a260  lea     rax, [r15+10h]
0x18004a264  mov     [rsp+8D0h+var_8A0], rax
0x18004a269  lea     rax, [rsp+8D0h+var_880]
0x18004a26e  movaps  [rsp+8D0h+var_880], xmm0
0x18004a273  movups  xmm0, xmmword ptr [rdi+2304h]
0x18004a27a  mov     [rsp+8D0h+var_8B0], rax
0x18004a27f  movaps  [rsp+8D0h+var_860], xmm0
0x18004a284  call    DwDoIke
0x18004a289  mov     ebx, eax
0x18004a28b  test    eax, eax
0x18004a28d  jz      short loc_18004A29B
0x18004a28f  mov     r8, rdi; struct _DDM_S2S_DIALING_PARAMS *
0x18004a292  mov     edx, eax; unsigned int
0x18004a294  call    ?DdmMapOakleyErrorToRasError@DdmL2tpDevice@@AEAAKKAEAU_DDM_S2S_DIALING_PARAMS@@@Z; DdmL2tpDevice::DdmMapOakleyErrorToRasError(ulong,_DDM_S2S_DIALING_PARAMS &)
0x18004a299  mov     ebx, eax
0x18004a29b  mov     edx, 1F4h; dwMilliseconds
0x18004a2a0  mov     rcx, r14; hHandle
0x18004a2a3  call    cs:__imp_WaitForSingleObject
0x18004a2aa  nop     dword ptr [rax+rax+00h]
0x18004a2af  cmp     eax, 102h
0x18004a2b4  jz      short loc_18004A29B
0x18004a2b6  test    eax, eax
0x18004a2b8  jnz     short loc_18004A2D9
0x18004a2ba  lea     r8, [rsp+8D0h+var_890]; unsigned int *
0x18004a2bf  mov     [rsp+8D0h+var_890], r12d
0x18004a2c4  mov     rdx, rdi; struct _DDM_S2S_DIALING_PARAMS *
0x18004a2c7  mov     rcx, r15; this
0x18004a2ca  call    ?DdmDwQueryIkeStatus@DdmL2tpDevice@@AEAAKAEAU_DDM_S2S_DIALING_PARAMS@@PEAK@Z; DdmL2tpDevice::DdmDwQueryIkeStatus(_DDM_S2S_DIALING_PARAMS &,ulong *)
0x18004a2cf  mov     ebx, eax
0x18004a2d1  test    eax, eax
0x18004a2d3  jnz     short loc_18004A2D9
0x18004a2d5  mov     ebx, [rsp+8D0h+var_890]
0x18004a2d9  mov     rcx, r14; hObject
0x18004a2dc  call    cs:__imp_CloseHandle
0x18004a2e3  nop     dword ptr [rax+rax+00h]
0x18004a2e8  jmp     short loc_18004A360
0x18004a2ea  test    cs:byte_1800CF404, 8
0x18004a2f1  mov     ebx, 301h
0x18004a2f6  jz      short loc_18004A360
0x18004a2f8  mov     r8d, ebx
0x18004a2fb  mov     word ptr [rbp+7D0h+var_840], r12w
0x18004a300  lea     rdx, aDdml2tpdeviceD_1; "DdmL2tpDevice::DdmDoIke:  failed to get"...
0x18004a307  lea     rcx, [rbp+7D0h+var_840]
0x18004a30b  call    FormatRRASErrorString
0x18004a310  test    cs:byte_1800CF404, 8
0x18004a317  jz      short loc_18004A360
0x18004a319  lea     rcx, [rbp+7D0h+var_840]
0x18004a31d  mov     rax, rsi
0x18004a320  inc     rax
0x18004a323  cmp     [rcx+rax*2], r12w
0x18004a328  jnz     short loc_18004A320
0x18004a32a  lea     eax, ds:2[rax*2]
0x18004a331  mov     [rbp+7D0h+var_844], r12d
0x18004a335  lea     rcx, [rbp+7D0h+var_840]
0x18004a339  mov     [rbp+7D0h+var_848], eax
0x18004a33c  lea     rax, [rsp+8D0h+var_860]
0x18004a341  mov     [rbp+7D0h+var_850], rcx
0x18004a345  mov     r9d, r13d
0x18004a348  mov     [rsp+8D0h+var_8B0], rax
0x18004a34d  lea     rdx, RasDdmTraceError
0x18004a354  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004a35b  call    McGenEventWrite_EventWriteTransfer
0x18004a360  test    cs:byte_1800CF404, 10h
0x18004a367  jz      short loc_18004A3CE
0x18004a369  mov     r8d, ebx
0x18004a36c  mov     word ptr [rbp+7D0h+var_840], r12w
0x18004a371  lea     rdx, aDdmdoikeDone0x; "DdmDoIke done. 0x%x"
0x18004a378  lea     rcx, [rbp+7D0h+var_840]
0x18004a37c  call    FormatRRASErrorString
0x18004a381  test    cs:byte_1800CF404, 10h
0x18004a388  jz      short loc_18004A3CE
0x18004a38a  lea     rax, [rbp+7D0h+var_840]
0x18004a38e  inc     rsi
0x18004a391  cmp     [rax+rsi*2], r12w
0x18004a396  jnz     short loc_18004A38E
0x18004a398  lea     eax, ds:2[rsi*2]
0x18004a39f  mov     [rbp+7D0h+var_844], r12d
0x18004a3a3  mov     [rbp+7D0h+var_848], eax
0x18004a3a6  lea     r8, [rbp+7D0h+var_840]
0x18004a3aa  lea     rax, [rsp+8D0h+var_860]
0x18004a3af  mov     [rbp+7D0h+var_850], r8
0x18004a3b3  mov     r9d, r13d
0x18004a3b6  mov     [rsp+8D0h+var_8B0], rax
0x18004a3bb  lea     rdx, RasDdmTraceInfo
0x18004a3c2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004a3c9  call    McGenEventWrite_EventWriteTransfer
0x18004a3ce  mov     eax, ebx
0x18004a3d0  mov     rcx, [rbp+7D0h+var_40]
0x18004a3d7  xor     rcx, rsp; StackCookie
0x18004a3da  call    __security_check_cookie
0x18004a3df  mov     rbx, [rsp+8D0h+arg_10]
0x18004a3e7  add     rsp, 8A0h
0x18004a3ee  pop     r15
0x18004a3f0  pop     r14
0x18004a3f2  pop     r13
0x18004a3f4  pop     r12
0x18004a3f6  pop     rdi
0x18004a3f7  pop     rsi
0x18004a3f8  pop     rbp
0x18004a3f9  retn
```
