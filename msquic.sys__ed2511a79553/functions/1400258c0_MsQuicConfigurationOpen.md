# MsQuicConfigurationOpen

- ea: `0x1400258c0`
- end: `0x140025d64`
- name: `MsQuicConfigurationOpen`
- size: `1188`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140005f0c`
- `0x1400258c0`
- `0x140025d70`
- `0x14002cb4c`
- `0x1400337e4`
- `0x140033984`
- `0x140033bfc`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ce00`
- `0x14003ead8`
- `0x14003eca4`
- `0x14003ed00`
- `0x140040c2c`
- `0x140040de8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140025aec`
- `ntoskrnl!_snprintf_s` at `0x140025bc0`
- `ntoskrnl!_snprintf_s` at `0x140025aec`
- `ntoskrnl!_snprintf_s` at `0x140025bc0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140025c7d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140025c7d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140025c8f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140025c8f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140025cbb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140025cbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025d13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025d13`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025cc7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025cc7`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140025a8c`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140025b27`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140025a8c`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140025b27`
- `ntoskrnl!IoGetCurrentProcess` at `0x140025b0a`
- `ntoskrnl!IoGetCurrentProcess` at `0x140025b0a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140025c53`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140025c53`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x140025cff`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x140025cff`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140025a6f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140025a6f`
- `ntoskrnl!ExAllocatePool2` at `0x1400259b7`
- `ntoskrnl!ExAllocatePool2` at `0x1400259b7`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140025a60`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140025a60`

## string_xrefs

- `0x1400259da`: `QUIC_CONFIGURATION`
- `0x140025ad6`: `[cnfg][%p] Failed to open settings, 0x%x`
- `0x140025baa`: `[cnfg][%p] Failed to open app specific settings, 0x%x`
- `0x140025c6f`: `C:\__w\1\s\msquic\src\core\configuration.c`

## pseudocode

```c
__int64 __fastcall MsQuicConfigurationOpen(
        __int64 a1,
        unsigned int *a2,
        unsigned int a3,
        _QWORD *a4,
        unsigned int a5,
        __int64 a6,
        char **a7)
{
  __int64 v8; // r12
  int v11; // esi
  __int64 v12; // rdx
  _DWORD *v13; // rcx
  unsigned int v14; // r15d
  unsigned int v15; // edx
  char *Pool2; // rax
  __int64 v17; // rdx
  char *v18; // rdi
  char *v19; // r15
  char *v20; // r15
  __int64 v21; // rax
  void *CurrentServerSilo; // rax
  int v23; // r9d
  int v24; // eax
  __int64 v25; // rcx
  PEPROCESS CurrentProcess; // rax
  __int64 v27; // rcx
  unsigned int v28; // ebx
  int v29; // r9d
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  _QWORD *v34; // rax
  void *v35; // rcx
  char v37[144]; // [rsp+40h] [rbp-C0h] BYREF
  char DstBuf[128]; // [rsp+D0h] [rbp-30h] BYREF
  char v39[272]; // [rsp+150h] [rbp+50h] BYREF

  v8 = a3;
  v11 = -1073741811;
  memset(v37, 0, sizeof(v37));
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(v13, v12, 5, a1);
  if ( a1 && !*(_DWORD *)a1 && a2 && (_DWORD)v8 && a7 )
  {
    v14 = 0;
    v15 = 0;
    v13 = a2;
    do
    {
      if ( (unsigned int)(*v13 - 1) > 0xFE )
        goto LABEL_46;
      ++v15;
      v14 += *v13 + 1;
      v13 += 4;
    }
    while ( v15 < (unsigned int)v8 );
    if ( v14 > 0xFFFF )
      goto LABEL_46;
    Pool2 = (char *)ExAllocatePool2(66, v14 + 248LL, 909206353);
    v18 = Pool2;
    if ( !Pool2 )
    {
      if ( (Microsoft_QuicEnableBits & 2) != 0 )
        McTemplateU0sx_EtwWriteTransfer(v13, v17, "QUIC_CONFIGURATION", 248);
      v11 = -1073741801;
      goto LABEL_46;
    }
    memset(Pool2, 0, 0xF8u);
    *((_WORD *)v18 + 120) = v14;
    v19 = v18 + 242;
    *((_QWORD *)v18 + 1) = a6;
    *(_DWORD *)v18 = 1;
    *((_QWORD *)v18 + 2) = a1;
    *((_QWORD *)v18 + 5) = 1;
    do
    {
      *v19 = *(_BYTE *)a2;
      v20 = v19 + 1;
      memmove(v20, *((const void **)a2 + 1), *a2);
      v21 = *a2;
      a2 += 4;
      v19 = &v20[v21];
      --v8;
    }
    while ( v8 );
    *((_DWORD *)v18 + 14) = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
    CurrentServerSilo = (void *)PsGetCurrentServerSilo();
    *((_QWORD *)v18 + 8) = CurrentServerSilo;
    if ( CurrentServerSilo )
      ObfReferenceObjectWithTag(CurrentServerSilo, 0x30306351u);
    if ( *((_QWORD *)v18 + 8) )
    {
      v24 = CxPlatStorageOpen(0, (unsigned int)QuicConfigurationSettingsChanged, (_DWORD)v18, v23, (__int64)(v18 + 72));
      v11 = v24;
      if ( v24 < 0 )
      {
        if ( (byte_14005C48E & 0x20) != 0 )
        {
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[cnfg][%p] Failed to open settings, 0x%x", v18, v24);
          McTemplateU0s_EtwWriteTransfer(v25, QuicLogWarning, DstBuf);
        }
        v11 = 0;
      }
    }
    CurrentProcess = IoGetCurrentProcess();
    *((_QWORD *)v18 + 10) = CurrentProcess;
    if ( CurrentProcess )
      ObfReferenceObjectWithTag(CurrentProcess, 0x33346351u);
    v28 = *(unsigned __int8 *)(a1 + 144);
    if ( (_BYTE)v28 )
    {
      strcpy(v39, "Apps\\");
      memset(&v39[6], 0, 0xFFu);
      memmove(&v39[5], (const void *)(a1 + 145), v28);
      v30 = CxPlatStorageOpen(
              (unsigned int)v39,
              (unsigned int)QuicConfigurationSettingsChanged,
              (_DWORD)v18,
              v29,
              (__int64)(v18 + 88));
      v11 = v30;
      if ( v30 < 0 )
      {
        if ( (byte_14005C48E & 0x20) != 0 )
        {
          _snprintf_s(
            DstBuf,
            0x80u,
            0xFFFFFFFFFFFFFFFFuLL,
            "[cnfg][%p] Failed to open app specific settings, 0x%x",
            v18,
            v30);
          McTemplateU0s_EtwWriteTransfer(v31, QuicLogWarning, DstBuf);
        }
        v11 = 0;
      }
    }
    if ( a4 && *a4 )
    {
      v11 = QuicSettingsSettingsToInternal(a5, a4, v37);
      if ( v11 < 0 )
      {
LABEL_43:
        CxPlatStorageClose(*((PVOID *)v18 + 11));
        CxPlatStorageClose(*((PVOID *)v18 + 9));
        v35 = (void *)*((_QWORD *)v18 + 8);
        if ( v35 )
          ObfDereferenceObjectWithTag(v35, 0x30306351u);
        ExFreePoolWithTag(v18, 0x36316351u);
        goto LABEL_46;
      }
      LOBYTE(v33) = 1;
      LOBYTE(v32) = 1;
      if ( !(unsigned __int8)QuicSettingApply(v18 + 96, v32, v33, v37) )
      {
        v11 = -1073741811;
        goto LABEL_43;
      }
    }
    if ( (byte_14005C489 & 4) != 0 )
      McTemplateU0pp_EtwWriteTransfer(v27, QuicConfigurationCreated, v18);
    QuicConfigurationSettingsChanged(v18);
    if ( !ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 128)) )
    {
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\configuration.c", 200, "Result");
      __int2c();
    }
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a1 + 56, 0);
    v34 = *(_QWORD **)(a1 + 72);
    *((_QWORD *)v18 + 3) = a1 + 64;
    *((_QWORD *)v18 + 4) = v34;
    *v34 = v18 + 24;
    *(_QWORD *)(a1 + 72) = v18 + 24;
    ExReleasePushLockExclusiveEx(a1 + 56, 0);
    KeLeaveCriticalRegion();
    *a7 = v18;
    if ( v11 < 0 )
      goto LABEL_43;
  }
LABEL_46:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer(v13, QuicApiExitStatus, (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400258c0  mov     [rsp-8+arg_10], rbx
0x1400258c5  push    rbp
0x1400258c6  push    rsi
0x1400258c7  push    rdi
0x1400258c8  push    r12
0x1400258ca  push    r13
0x1400258cc  push    r14
0x1400258ce  push    r15
0x1400258d0  lea     rbp, [rsp-170h]
0x1400258d8  sub     rsp, 270h
0x1400258df  mov     rax, cs:__security_cookie
0x1400258e6  xor     rax, rsp
0x1400258e9  mov     [rbp+1A0h+var_40], rax
0x1400258f0  mov     rdi, [rbp+1A0h+arg_30]
0x1400258f7  mov     rbx, rdx
0x1400258fa  mov     r12d, r8d
0x1400258fd  mov     r14, rcx
0x140025900  xor     edx, edx; Val
0x140025902  mov     [rsp+2A0h+var_270], rdi
0x140025907  mov     r8d, 90h; Size
0x14002590d  lea     rcx, [rsp+2A0h+var_260]; void *
0x140025912  mov     r13, r9
0x140025915  mov     esi, 0C000000Dh
0x14002591a  call    memset
0x14002591f  test    cs:Microsoft_QuicEnableBits, 8
0x140025926  jz      short loc_140025936
0x140025928  mov     r9, r14
0x14002592b  mov     r8d, 5
0x140025931  call    McTemplateU0qp_EtwWriteTransfer
0x140025936  test    r14, r14
0x140025939  jz      loc_140025D1F
0x14002593f  cmp     dword ptr [r14], 0
0x140025943  jnz     loc_140025D1F
0x140025949  test    rbx, rbx
0x14002594c  jz      loc_140025D1F
0x140025952  test    r12d, r12d
0x140025955  jz      loc_140025D1F
0x14002595b  test    rdi, rdi
0x14002595e  jz      loc_140025D1F
0x140025964  xor     r15d, r15d
0x140025967  xor     edx, edx
0x140025969  test    r12d, r12d
0x14002596c  jz      short loc_1400259A2
0x14002596e  mov     rcx, rbx
0x140025971  mov     r8d, [rcx]
0x140025974  lea     eax, [r8-1]
0x140025978  cmp     eax, 0FEh
0x14002597d  ja      loc_140025D1F
0x140025983  inc     r15d
0x140025986  inc     edx
0x140025988  add     r15d, r8d
0x14002598b  add     rcx, 10h
0x14002598f  mov     eax, r15d
0x140025992  cmp     edx, r12d
0x140025995  jb      short loc_140025971
0x140025997  cmp     eax, 0FFFFh
0x14002599c  ja      loc_140025D1F
0x1400259a2  mov     edx, r15d
0x1400259a5  mov     ecx, 42h ; 'B'
0x1400259aa  add     rdx, 0F8h
0x1400259b1  mov     r8d, 36316351h
0x1400259b7  call    cs:__imp_ExAllocatePool2
0x1400259be  nop     dword ptr [rax+rax+00h]
0x1400259c3  mov     rdi, rax
0x1400259c6  test    rax, rax
0x1400259c9  jnz     short loc_1400259F0
0x1400259cb  test    cs:Microsoft_QuicEnableBits, 2
0x1400259d2  jz      short loc_1400259E6
0x1400259d4  mov     r9d, 0F8h
0x1400259da  lea     r8, aQuicConfigurat; "QUIC_CONFIGURATION"
0x1400259e1  call    McTemplateU0sx_EtwWriteTransfer
0x1400259e6  mov     esi, 0C0000017h
0x1400259eb  jmp     loc_140025D1F
0x1400259f0  xor     edx, edx; Val
0x1400259f2  mov     r8d, 0F8h; Size
0x1400259f8  mov     rcx, rdi; void *
0x1400259fb  call    memset
0x140025a00  mov     rax, [rbp+1A0h+arg_28]
0x140025a07  mov     [rdi+0F0h], r15w
0x140025a0f  lea     r15, [rdi+0F2h]
0x140025a16  mov     [rdi+8], rax
0x140025a1a  mov     dword ptr [rdi], 1
0x140025a20  mov     [rdi+10h], r14
0x140025a24  mov     qword ptr [rdi+28h], 1
0x140025a2c  test    r12d, r12d
0x140025a2f  jz      short loc_140025A57
0x140025a31  mov     al, [rbx]
0x140025a33  mov     [r15], al
0x140025a36  inc     r15
0x140025a39  mov     r8d, [rbx]; Size
0x140025a3c  mov     rcx, r15; void *
0x140025a3f  mov     rdx, [rbx+8]; Src
0x140025a43  call    memmove
0x140025a48  mov     eax, [rbx]
0x140025a4a  lea     rbx, [rbx+10h]
0x140025a4e  add     r15, rax
0x140025a51  sub     r12, 1
0x140025a55  jnz     short loc_140025A31
0x140025a57  mov     rcx, gs:188h
0x140025a60  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140025a67  nop     dword ptr [rax+rax+00h]
0x140025a6c  mov     [rdi+38h], eax
0x140025a6f  call    cs:__imp_PsGetCurrentServerSilo
0x140025a76  nop     dword ptr [rax+rax+00h]
0x140025a7b  mov     [rdi+40h], rax
0x140025a7f  test    rax, rax
0x140025a82  jz      short loc_140025A98
0x140025a84  mov     edx, 30306351h; Tag
0x140025a89  mov     rcx, rax; Object
0x140025a8c  call    cs:__imp_ObfReferenceObjectWithTag
0x140025a93  nop     dword ptr [rax+rax+00h]
0x140025a98  or      r15, 0FFFFFFFFFFFFFFFFh
0x140025a9c  mov     r12d, 80h
0x140025aa2  cmp     qword ptr [rdi+40h], 0
0x140025aa7  jz      short loc_140025B0A
0x140025aa9  lea     rax, [rdi+48h]
0x140025aad  mov     r8, rdi
0x140025ab0  lea     rdx, QuicConfigurationSettingsChanged
0x140025ab7  mov     [rsp+2A0h+var_280], rax
0x140025abc  xor     ecx, ecx
0x140025abe  call    CxPlatStorageOpen
0x140025ac3  mov     esi, eax
0x140025ac5  test    eax, eax
0x140025ac7  jns     short loc_140025B0A
0x140025ac9  test    cs:byte_14005C48E, 20h
0x140025ad0  jz      short loc_140025B08
0x140025ad2  mov     [rsp+2A0h+var_278], eax
0x140025ad6  lea     r9, aCnfgPFailedToO; "[cnfg][%p] Failed to open settings, 0x%"...
0x140025add  mov     r8, r15; MaxCount
0x140025ae0  mov     [rsp+2A0h+var_280], rdi
0x140025ae5  mov     edx, r12d; SizeInBytes
0x140025ae8  lea     rcx, [rbp+1A0h+DstBuf]; DstBuf
0x140025aec  call    cs:__imp__snprintf_s
0x140025af3  nop     dword ptr [rax+rax+00h]
0x140025af8  lea     r8, [rbp+1A0h+DstBuf]
0x140025afc  lea     rdx, QuicLogWarning
0x140025b03  call    McTemplateU0s_EtwWriteTransfer
0x140025b08  xor     esi, esi
0x140025b0a  call    cs:__imp_IoGetCurrentProcess
0x140025b11  nop     dword ptr [rax+rax+00h]
0x140025b16  mov     [rdi+50h], rax
0x140025b1a  test    rax, rax
0x140025b1d  jz      short loc_140025B33
0x140025b1f  mov     edx, 33346351h; Tag
0x140025b24  mov     rcx, rax; Object
0x140025b27  call    cs:__imp_ObfReferenceObjectWithTag
0x140025b2e  nop     dword ptr [rax+rax+00h]
0x140025b33  movzx   ebx, byte ptr [r14+90h]
0x140025b3b  test    bl, bl
0x140025b3d  jz      loc_140025BDE
0x140025b43  mov     eax, dword ptr cs:aApps; "Apps\\"
0x140025b49  lea     rcx, [rbp+1A0h+var_150+6]; void *
0x140025b4d  mov     dword ptr [rbp+1A0h+var_150], eax
0x140025b50  xor     edx, edx; Val
0x140025b52  movzx   eax, word ptr cs:aApps+4; "\\"
0x140025b59  mov     r8d, 0FFh; Size
0x140025b5f  mov     word ptr [rbp+1A0h+var_150+4], ax
0x140025b63  call    memset
0x140025b68  mov     r8d, ebx; Size
0x140025b6b  lea     rdx, [r14+91h]; Src
0x140025b72  lea     rcx, [rbp+1A0h+var_150+5]; void *
0x140025b76  call    memmove
0x140025b7b  lea     rax, [rdi+58h]
0x140025b7f  mov     r8, rdi
0x140025b82  lea     rdx, QuicConfigurationSettingsChanged
0x140025b89  mov     [rsp+2A0h+var_280], rax
0x140025b8e  lea     rcx, [rbp+1A0h+var_150]
0x140025b92  call    CxPlatStorageOpen
0x140025b97  mov     esi, eax
0x140025b99  test    eax, eax
0x140025b9b  jns     short loc_140025BDE
0x140025b9d  test    cs:byte_14005C48E, 20h
0x140025ba4  jz      short loc_140025BDC
0x140025ba6  mov     [rsp+2A0h+var_278], eax
0x140025baa  lea     r9, aCnfgPFailedToO_0; "[cnfg][%p] Failed to open app specific "...
0x140025bb1  mov     r8, r15; MaxCount
0x140025bb4  mov     [rsp+2A0h+var_280], rdi
0x140025bb9  mov     rdx, r12; SizeInBytes
0x140025bbc  lea     rcx, [rbp+1A0h+DstBuf]; DstBuf
0x140025bc0  call    cs:__imp__snprintf_s
0x140025bc7  nop     dword ptr [rax+rax+00h]
0x140025bcc  lea     r8, [rbp+1A0h+DstBuf]
0x140025bd0  lea     rdx, QuicLogWarning
0x140025bd7  call    McTemplateU0s_EtwWriteTransfer
0x140025bdc  xor     esi, esi
0x140025bde  test    r13, r13
0x140025be1  jz      short loc_140025C29
0x140025be3  cmp     qword ptr [r13+0], 0
0x140025be8  jz      short loc_140025C29
0x140025bea  mov     ecx, [rbp+1A0h+arg_20]
0x140025bf0  lea     r8, [rsp+2A0h+var_260]
0x140025bf5  mov     rdx, r13
0x140025bf8  call    QuicSettingsSettingsToInternal
0x140025bfd  mov     esi, eax
0x140025bff  test    eax, eax
0x140025c01  js      loc_140025CDF
0x140025c07  mov     r8b, 1
0x140025c0a  lea     rcx, [rdi+60h]
0x140025c0e  mov     dl, r8b
0x140025c11  lea     r9, [rsp+2A0h+var_260]
0x140025c16  call    QuicSettingApply
0x140025c1b  test    al, al
0x140025c1d  jnz     short loc_140025C29
0x140025c1f  mov     esi, 0C000000Dh
0x140025c24  jmp     loc_140025CDF
0x140025c29  test    cs:byte_14005C489, 4
0x140025c30  jz      short loc_140025C44
0x140025c32  mov     r9, r14
0x140025c35  lea     rdx, QuicConfigurationCreated
0x140025c3c  mov     r8, rdi
0x140025c3f  call    McTemplateU0pp_EtwWriteTransfer
0x140025c44  mov     rcx, rdi
0x140025c47  call    QuicConfigurationSettingsChanged
0x140025c4c  lea     rcx, [r14+80h]; RunRef
0x140025c53  call    cs:__imp_ExAcquireRundownProtection
0x140025c5a  nop     dword ptr [rax+rax+00h]
0x140025c5f  test    al, al
0x140025c61  jnz     short loc_140025C7D
0x140025c63  lea     r8, aResult; "Result"
0x140025c6a  mov     edx, 0C8h
0x140025c6f  lea     rcx, aCW1SMsquicSrcC_2; "C:\\__w\\1\\s\\msquic\\src\\core\\confi"...
0x140025c76  call    CxPlatLogAssert
0x140025c7b  int     2Ch; Windows NT - assertion failure
0x140025c7d  call    cs:__imp_KeEnterCriticalRegion
0x140025c84  nop     dword ptr [rax+rax+00h]
0x140025c89  xor     edx, edx
0x140025c8b  lea     rcx, [r14+38h]
0x140025c8f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140025c96  nop     dword ptr [rax+rax+00h]
0x140025c9b  lea     rdx, [r14+40h]
0x140025c9f  mov     rax, [rdx+8]
0x140025ca3  lea     r8, [rdi+18h]
0x140025ca7  mov     [r8], rdx
0x140025caa  lea     rcx, [r14+38h]
0x140025cae  mov     [r8+8], rax
0x140025cb2  mov     [rax], r8
0x140025cb5  mov     [rdx+8], r8
0x140025cb9  xor     edx, edx
0x140025cbb  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140025cc2  nop     dword ptr [rax+rax+00h]
0x140025cc7  call    cs:__imp_KeLeaveCriticalRegion
0x140025cce  nop     dword ptr [rax+rax+00h]
0x140025cd3  mov     rax, [rsp+2A0h+var_270]
0x140025cd8  mov     [rax], rdi
0x140025cdb  test    esi, esi
0x140025cdd  jns     short loc_140025D1F
0x140025cdf  mov     rcx, [rdi+58h]; P
0x140025ce3  call    CxPlatStorageClose
0x140025ce8  mov     rcx, [rdi+48h]; P
0x140025cec  call    CxPlatStorageClose
0x140025cf1  mov     rcx, [rdi+40h]; Object
0x140025cf5  test    rcx, rcx
0x140025cf8  jz      short loc_140025D0B
0x140025cfa  mov     edx, 30306351h; Tag
0x140025cff  call    cs:__imp_ObfDereferenceObjectWithTag
0x140025d06  nop     dword ptr [rax+rax+00h]
0x140025d0b  mov     edx, 36316351h; Tag
0x140025d10  mov     rcx, rdi; P
0x140025d13  call    cs:__imp_ExFreePoolWithTag
0x140025d1a  nop     dword ptr [rax+rax+00h]
0x140025d1f  test    cs:Microsoft_QuicEnableBits, 8
0x140025d26  jz      short loc_140025D37
0x140025d28  mov     r8d, esi
0x140025d2b  lea     rdx, QuicApiExitStatus
0x140025d32  call    McTemplateU0q_EtwWriteTransfer
0x140025d37  mov     eax, esi
0x140025d39  mov     rcx, [rbp+1A0h+var_40]
0x140025d40  xor     rcx, rsp; StackCookie
0x140025d43  call    __security_check_cookie
0x140025d48  mov     rbx, [rsp+2A0h+arg_10]
0x140025d50  add     rsp, 270h
0x140025d57  pop     r15
0x140025d59  pop     r14
0x140025d5b  pop     r13
0x140025d5d  pop     r12
0x140025d5f  pop     rdi
0x140025d60  pop     rsi
0x140025d61  pop     rbp
0x140025d62  retn
```
