# MsQuicLibraryInitialize

- ea: `0x140023f20`
- end: `0x140024237`
- name: `MsQuicLibraryInitialize`
- size: `791`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140023e4c`

## callees

- `0x140010820`
- `0x140023f20`
- `0x140024240`
- `0x140027ff8`
- `0x14002808c`
- `0x14002a478`
- `0x140033810`
- `0x140033984`
- `0x140033bfc`
- `0x14003533c`
- `0x14003c8e0`
- `0x14003ce00`
- `0x14003e884`
- `0x14003ead8`
- `0x14003eb54`
- `0x14003ed00`
- `0x140063008`
- `0x1400632c4`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140024039`
- `ntoskrnl!_snprintf_s` at `0x140024215`
- `ntoskrnl!_snprintf_s` at `0x140024039`
- `ntoskrnl!_snprintf_s` at `0x140024215`
- `ntoskrnl!MmIsVerifierEnabled` at `0x1400241c4`
- `ntoskrnl!MmIsVerifierEnabled` at `0x1400241c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400240fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400240fa`
- `ntoskrnl!ExAllocatePool2` at `0x140024097`
- `ntoskrnl!ExAllocatePool2` at `0x140024097`

## string_xrefs

- `0x140024022`: `[ lib] Failed to open global settings, 0x%x`
- `0x1400240bf`: `default compatibility list`

## pseudocode

```c
__int64 MsQuicLibraryInitialize()
{
  char v0; // di
  int v1; // ebx
  __int64 v2; // rax
  __int64 v3; // r9
  int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // esi
  void *Pool2; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v11; // rcx
  int v12; // edx
  int v13; // ecx
  __int64 v14; // rcx
  unsigned int v15; // [rsp+30h] [rbp-A8h] BYREF
  ULONG VerifierFlags[3]; // [rsp+34h] [rbp-A4h] BYREF
  char DstBuf[128]; // [rsp+40h] [rbp-98h] BYREF

  v0 = 0;
  v1 = CxPlatInitialize();
  if ( v1 < 0 )
  {
LABEL_10:
    if ( qword_14005C580 )
    {
      CxPlatStorageClose(qword_14005C580);
      qword_14005C580 = 0;
    }
    if ( Src )
    {
      ExFreePoolWithTag(Src, 0x31346351u);
      Src = 0;
    }
    if ( v0 )
      CxPlatUninitialize();
    return (unsigned int)v1;
  }
  v0 = 1;
  byte_14005C560 = CxPlatGetTimerResolution() / 0x3E8uLL + 1;
  v2 = QuicTimePlat();
  qword_14005D938 = QuicTimePlatToUs64(v2);
  memset(&qword_14005D940, 0, 0x100u);
  CxPlatRandom(0x2Au);
  dword_14005D924 = 38;
  CxPlatToeplitzHashInitialize(qword_14005C5F8);
  dword_14005C5C8 = 0;
  memset(&qword_14005C4B0, 0, 0x90u);
  v4 = CxPlatStorageOpen(0, (__int64)MsQuicLibraryReadSettings, 1, v3, &qword_14005C580);
  v1 = v4;
  if ( v4 < 0 )
  {
    if ( (byte_14005C48E & 0x20) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ lib] Failed to open global settings, 0x%x", v4);
      McTemplateU0s_EtwWriteTransfer(v5, QuicLogWarning, DstBuf);
    }
    v1 = 0;
  }
  MsQuicLibraryReadSettings(0);
  v15 = 0;
  QuicVersionNegotiationExtGenerateCompatibleVersionsList(
    0x1000000,
    (unsigned int)DefaultSupportedVersionsList,
    4,
    0,
    (__int64)&v15);
  v6 = v15;
  Pool2 = (void *)ExAllocatePool2(66, v15, 825516881);
  Src = Pool2;
  if ( !Pool2 )
  {
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(v9, v8, "default compatibility list", v6);
    v1 = -1073741801;
    goto LABEL_10;
  }
  dword_14005D930 = v6 >> 2;
  if ( (int)QuicVersionNegotiationExtGenerateCompatibleVersionsList(
              0x1000000,
              (unsigned int)DefaultSupportedVersionsList,
              4,
              (_DWORD)Pool2,
              (__int64)&v15) >= 0 )
  {
    if ( (Microsoft_QuicEnableBits & 1) != 0 )
    {
      McTemplateU0_EtwWriteTransfer(v11, QuicLibraryInitializedV3);
      if ( (Microsoft_QuicEnableBits & 1) != 0 )
        McTemplateU0qqqq_EtwWriteTransfer(
          v13,
          v12,
          xmmword_14005C494,
          DWORD1(xmmword_14005C494),
          SBYTE8(xmmword_14005C494),
          SBYTE12(xmmword_14005C494));
    }
    VerifierFlags[0] = 0;
    MsQuicLib = (32 * (MmIsVerifierEnabled(VerifierFlags) >= 0)) | MsQuicLib & 0xDF;
    if ( (MsQuicLib & 0x20) != 0 && (byte_14005C48E & 0x40) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ lib] Verifing enabled, per-registration!");
      McTemplateU0s_EtwWriteTransfer(v14, QuicLogInfo, DstBuf);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140023f20  mov     [rsp+arg_0], rbx
0x140023f25  mov     [rsp+arg_8], rbp
0x140023f2a  mov     [rsp+arg_10], rsi
0x140023f2f  push    rdi
0x140023f30  sub     rsp, 0D0h
0x140023f37  mov     rax, cs:__security_cookie
0x140023f3e  xor     rax, rsp
0x140023f41  mov     [rsp+0D8h+var_18], rax
0x140023f49  xor     dil, dil
0x140023f4c  call    CxPlatInitialize
0x140023f51  mov     ebx, eax
0x140023f53  test    eax, eax
0x140023f55  js      loc_1400240D0
0x140023f5b  call    CxPlatGetTimerResolution
0x140023f60  mov     rcx, rax
0x140023f63  mov     edi, 1
0x140023f68  mov     rax, 624DD2F1A9FBE77h
0x140023f72  mul     rcx
0x140023f75  sub     rcx, rdx
0x140023f78  shr     rcx, 1
0x140023f7b  add     rcx, rdx
0x140023f7e  shr     rcx, 9
0x140023f82  add     cl, dil
0x140023f85  mov     cs:byte_14005C560, cl
0x140023f8b  call    QuicTimePlat
0x140023f90  mov     rcx, rax
0x140023f93  call    QuicTimePlatToUs64
0x140023f98  xor     edx, edx; Val
0x140023f9a  mov     cs:qword_14005D938, rax
0x140023fa1  mov     r8d, 100h; Size
0x140023fa7  lea     rcx, qword_14005D940; void *
0x140023fae  call    memset
0x140023fb3  lea     rdx, qword_14005D8F8
0x140023fba  lea     ecx, [rdi+29h]; cbBuffer
0x140023fbd  call    CxPlatRandom
0x140023fc2  lea     rcx, qword_14005C5F8
0x140023fc9  mov     cs:dword_14005D924, 26h ; '&'
0x140023fd3  call    CxPlatToeplitzHashInitialize
0x140023fd8  xor     edx, edx; Val
0x140023fda  mov     cs:dword_14005C5C8, 0
0x140023fe4  mov     r8d, 90h; Size
0x140023fea  lea     rcx, qword_14005C4B0; void *
0x140023ff1  call    memset
0x140023ff6  lea     rax, qword_14005C580
0x140023ffd  mov     r8d, edi
0x140024000  lea     rdx, MsQuicLibraryReadSettings
0x140024007  mov     [rsp+0D8h+var_B8], rax
0x14002400c  xor     ecx, ecx
0x14002400e  call    CxPlatStorageOpen
0x140024013  mov     ebx, eax
0x140024015  test    eax, eax
0x140024017  jns     short loc_140024058
0x140024019  test    cs:byte_14005C48E, 20h
0x140024020  jz      short loc_140024056
0x140024022  lea     r9, aLibFailedToOpe; "[ lib] Failed to open global settings, "...
0x140024029  mov     dword ptr [rsp+0D8h+var_B8], eax
0x14002402d  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140024031  lea     edx, [rdi+7Fh]; SizeInBytes
0x140024034  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x140024039  call    cs:__imp__snprintf_s
0x140024040  nop     dword ptr [rax+rax+00h]
0x140024045  lea     r8, [rsp+0D8h+DstBuf]
0x14002404a  lea     rdx, QuicLogWarning
0x140024051  call    McTemplateU0s_EtwWriteTransfer
0x140024056  xor     ebx, ebx
0x140024058  xor     ecx, ecx
0x14002405a  call    MsQuicLibraryReadSettings
0x14002405f  and     [rsp+0D8h+var_A8], 0
0x140024064  lea     rax, [rsp+0D8h+var_A8]
0x140024069  xor     r9d, r9d
0x14002406c  mov     [rsp+0D8h+var_B8], rax
0x140024071  lea     rdx, DefaultSupportedVersionsList
0x140024078  mov     ecx, 1000000h
0x14002407d  lea     r8d, [r9+4]
0x140024081  call    QuicVersionNegotiationExtGenerateCompatibleVersionsList
0x140024086  mov     esi, [rsp+0D8h+var_A8]
0x14002408a  mov     r8d, 31346351h
0x140024090  mov     edx, esi
0x140024092  mov     ecx, 42h ; 'B'
0x140024097  call    cs:__imp_ExAllocatePool2
0x14002409e  nop     dword ptr [rax+rax+00h]
0x1400240a3  mov     cs:Src, rax
0x1400240aa  test    rax, rax
0x1400240ad  jnz     loc_140024144
0x1400240b3  test    cs:Microsoft_QuicEnableBits, 2
0x1400240ba  jz      short loc_1400240CB
0x1400240bc  mov     r9d, esi
0x1400240bf  lea     r8, aDefaultCompati; "default compatibility list"
0x1400240c6  call    McTemplateU0sx_EtwWriteTransfer
0x1400240cb  mov     ebx, 0C0000017h
0x1400240d0  mov     rcx, cs:qword_14005C580; P
0x1400240d7  test    rcx, rcx
0x1400240da  jz      short loc_1400240E9
0x1400240dc  call    CxPlatStorageClose
0x1400240e1  and     cs:qword_14005C580, 0
0x1400240e9  mov     rcx, cs:Src; P
0x1400240f0  test    rcx, rcx
0x1400240f3  jz      short loc_14002410E
0x1400240f5  mov     edx, 31346351h; Tag
0x1400240fa  call    cs:__imp_ExFreePoolWithTag
0x140024101  nop     dword ptr [rax+rax+00h]
0x140024106  and     cs:Src, 0
0x14002410e  test    dil, dil
0x140024111  jz      short loc_140024118
0x140024113  call    CxPlatUninitialize
0x140024118  mov     eax, ebx
0x14002411a  mov     rcx, [rsp+0D8h+var_18]
0x140024122  xor     rcx, rsp; StackCookie
0x140024125  call    __security_check_cookie
0x14002412a  lea     r11, [rsp+0D8h+var_8]
0x140024132  mov     rbx, [r11+10h]
0x140024136  mov     rbp, [r11+18h]
0x14002413a  mov     rsi, [r11+20h]
0x14002413e  mov     rsp, r11
0x140024141  pop     rdi
0x140024142  retn
0x140024144  lea     rdx, [rsp+0D8h+var_A8]
0x140024149  shr     esi, 2
0x14002414c  mov     [rsp+0D8h+var_B8], rdx
0x140024151  mov     r9, rax
0x140024154  lea     rdx, DefaultSupportedVersionsList
0x14002415b  mov     cs:dword_14005D930, esi
0x140024161  mov     r8d, 4
0x140024167  mov     ecx, 1000000h
0x14002416c  call    QuicVersionNegotiationExtGenerateCompatibleVersionsList
0x140024171  test    eax, eax
0x140024173  js      short loc_140024118
0x140024175  test    cs:Microsoft_QuicEnableBits, dil
0x14002417c  jz      short loc_1400241BA
0x14002417e  lea     rdx, QuicLibraryInitializedV3
0x140024185  call    McTemplateU0_EtwWriteTransfer
0x14002418a  test    cs:Microsoft_QuicEnableBits, dil
0x140024191  jz      short loc_1400241BA
0x140024193  mov     eax, dword ptr cs:xmmword_14005C494+0Ch
0x140024199  mov     r9d, dword ptr cs:xmmword_14005C494+4
0x1400241a0  mov     r8d, dword ptr cs:xmmword_14005C494
0x1400241a7  mov     [rsp+0D8h+var_B0], eax
0x1400241ab  mov     eax, dword ptr cs:xmmword_14005C494+8
0x1400241b1  mov     dword ptr [rsp+0D8h+var_B8], eax
0x1400241b5  call    McTemplateU0qqqq_EtwWriteTransfer
0x1400241ba  and     [rsp+0D8h+VerifierFlags], 0
0x1400241bf  lea     rcx, [rsp+0D8h+VerifierFlags]; VerifierFlags
0x1400241c4  call    cs:__imp_MmIsVerifierEnabled
0x1400241cb  nop     dword ptr [rax+rax+00h]
0x1400241d0  mov     cl, cs:MsQuicLib
0x1400241d6  shr     eax, 1Fh
0x1400241d9  and     cl, 0DFh
0x1400241dc  xor     al, dil
0x1400241df  shl     al, 5
0x1400241e2  or      cl, al
0x1400241e4  mov     cs:MsQuicLib, cl
0x1400241ea  test    cl, 20h
0x1400241ed  jz      loc_140024118
0x1400241f3  test    cs:byte_14005C48E, 40h
0x1400241fa  jz      loc_140024118
0x140024200  lea     r9, aLibVerifingEna; "[ lib] Verifing enabled, per-registrati"...
0x140024207  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002420b  mov     edx, 80h; SizeInBytes
0x140024210  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x140024215  call    cs:__imp__snprintf_s
0x14002421c  nop     dword ptr [rax+rax+00h]
0x140024221  lea     r8, [rsp+0D8h+DstBuf]
0x140024226  lea     rdx, QuicLogInfo
0x14002422d  call    McTemplateU0s_EtwWriteTransfer
0x140024232  jmp     loc_140024118
```
