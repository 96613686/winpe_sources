# Microsoft::Windows::MDM::OmadmClient::CertificateManager::FindAppSecurityCertificatesReference(ushort *,_CERT_CONTEXT const * *)

- ea: `0x14001ffc0`
- end: `0x140020334`
- name: `?FindAppSecurityCertificatesReference@CertificateManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEAGPEAPEBU_CERT_CONTEXT@@@Z`
- size: `884`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::CertificateManager *__hidden this, unsigned __int16 *, const struct _CERT_CONTEXT **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000b0f4`
- `0x14000e610`
- `0x140013404`
- `0x14001391c`
- `0x14001ffc0`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400200b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140020101`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140020167`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400201ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002023c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400202bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400202ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400200b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140020101`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140020167`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400201ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002023c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400202bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400202ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140020194`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140020194`
- `DMCmnUtils!HexStringToBinary` at `0x140020135`
- `DMCmnUtils!HexStringToBinary` at `0x14002020a`
- `DMCmnUtils!HexStringToBinary` at `0x140020135`
- `DMCmnUtils!HexStringToBinary` at `0x14002020a`

## string_xrefs

- `0x14001fff5`: `FindAppSecurityCertificatesReference`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::CertificateManager::FindAppSecurityCertificatesReference(
        Microsoft::Windows::MDM::OmadmClient::CertificateManager *this,
        unsigned __int16 *a2,
        const struct _CERT_CONTEXT **a3)
{
  struct COmaDmLogger *Logger; // rax
  _QWORD *v7; // rdi
  int v8; // eax
  struct COmaDmLogger *v9; // rax
  struct COmaDmLogger *v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  HLOCAL v13; // rax
  int v14; // eax
  const struct _CERT_CONTEXT *v15; // rax
  struct COmaDmLogger *v16; // rax
  HLOCAL hMem[2]; // [rsp+40h] [rbp-29h] BYREF
  HLOCAL *v19; // [rsp+50h] [rbp-19h]
  Microsoft::Windows::MDM::OmadmClient::CertificateManager *v20; // [rsp+58h] [rbp-11h]
  __int64 *v21; // [rsp+60h] [rbp-9h]
  char v22; // [rsp+68h] [rbp-1h]
  _QWORD v23[3]; // [rsp+70h] [rbp+7h] BYREF
  int v24; // [rsp+88h] [rbp+1Fh]
  int *v25; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  int v27; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v28; // [rsp+D8h] [rbp+6Fh] BYREF

  v27 = 0;
  Logger = COmaDmLogger::GetLogger();
  v23[0] = 0;
  v23[1] = "FindAppSecurityCertificatesReference";
  v23[2] = Logger;
  v24 = 2;
  v25 = &v27;
  v28 = 0;
  *(_OWORD *)hMem = 0;
  v19 = hMem;
  v20 = this;
  v21 = &v28;
  v22 = 1;
  v7 = (_QWORD *)((char *)this + 24);
  if ( !a2 )
    goto LABEL_15;
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)*v7 + 80LL))(*v7, 13, 0, 0);
  v27 = v8;
  if ( !v28 )
  {
    if ( v8 == -2147024894 )
    {
      v9 = COmaDmLogger::GetLogger();
      Microsoft::Windows::TelemetryLogger::LogMeasure(v9, 1, 12062, 0);
    }
    else
    {
      v10 = COmaDmLogger::GetLogger();
      Microsoft::Windows::TelemetryLogger::LogMeasure(v10, 1, 12063, 0);
    }
    goto LABEL_15;
  }
  v11 = HexStringToBinary(a2, 0, hMem, 1);
  v12 = v11;
  v27 = v11;
  if ( v11 >= 0 )
  {
    v13 = LocalAlloc(0, LODWORD(hMem[0]));
    hMem[1] = v13;
    if ( v13 )
    {
      v27 = 0;
      v14 = HexStringToBinary(a2, v13, hMem, 1);
      v12 = v14;
      v27 = v14;
      if ( v14 >= 0 )
      {
        v15 = (const struct _CERT_CONTEXT *)(*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, int, HLOCAL *, _QWORD))(*(_QWORD *)*v7 + 32LL))(
                                              *v7,
                                              v28,
                                              65537,
                                              0,
                                              0x10000,
                                              hMem,
                                              0);
        if ( v15 )
        {
          *a3 = v15;
LABEL_15:
          v12 = v27;
          LocalFree(hMem[1]);
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v7 + 16LL))(*v7, v28, 0);
          goto LABEL_16;
        }
        v16 = COmaDmLogger::GetLogger();
        Microsoft::Windows::TelemetryLogger::LogMeasure(v16, 1, 12064, 0);
        v12 = v27;
        LocalFree(hMem[1]);
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v7 + 16LL))(*v7, v28, 0);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x87C,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\certificatemanager.cpp",
          (const char *)(unsigned int)v14,
          688128);
        LocalFree(hMem[1]);
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v7 + 16LL))(*v7, v28, 0);
      }
    }
    else
    {
      v12 = -2147024882;
      v27 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x879,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\certificatemanager.cpp",
        (const char *)0x8007000ELL,
        688128);
      LocalFree(hMem[1]);
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v7 + 16LL))(*v7, v28, 0);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x875,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\certificatemanager.cpp",
      (const char *)(unsigned int)v11,
      688128);
    LocalFree(hMem[1]);
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v7 + 16LL))(*v7, v28, 0);
  }
LABEL_16:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v23);
  return v12;
}

```

## disassembly

```asm
0x14001ffc0  mov     [rsp-8+arg_10], rbx
0x14001ffc5  push    rbp
0x14001ffc6  push    rsi
0x14001ffc7  push    rdi
0x14001ffc8  push    r12
0x14001ffca  push    r14
0x14001ffcc  lea     rbp, [rsp-37h]
0x14001ffd1  sub     rsp, 0A0h
0x14001ffd8  mov     r14, r8
0x14001ffdb  mov     rsi, rdx
0x14001ffde  mov     rbx, rcx
0x14001ffe1  mov     [rbp+57h+arg_0], 0
0x14001ffe8  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14001ffed  mov     [rbp+57h+var_50], 0
0x14001fff5  lea     rcx, aFindappsecurit; "FindAppSecurityCertificatesReference"
0x14001fffc  mov     [rbp+57h+var_48], rcx
0x140020000  mov     [rbp+57h+var_40], rax
0x140020004  mov     [rbp+57h+var_38], 2
0x14002000b  lea     rax, [rbp+57h+arg_0]
0x14002000f  mov     [rbp+57h+var_30], rax
0x140020013  mov     [rbp+57h+arg_8], 0
0x14002001b  xorps   xmm0, xmm0
0x14002001e  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x140020022  lea     rax, [rbp+57h+hMem]
0x140020026  mov     [rbp+57h+var_70], rax
0x14002002a  mov     [rbp+57h+var_68], rbx
0x14002002e  lea     rax, [rbp+57h+arg_8]
0x140020032  mov     [rbp+57h+var_60], rax
0x140020036  mov     r12d, 1
0x14002003c  mov     [rbp+57h+var_58], r12b
0x140020040  lea     rdi, [rbx+18h]
0x140020044  test    rsi, rsi
0x140020047  jz      loc_1400202E7
0x14002004d  mov     rcx, [rdi]
0x140020050  mov     rax, [rcx]
0x140020053  lea     rdx, [rbp+57h+arg_8]
0x140020057  mov     [rsp+0C0h+var_90], rdx
0x14002005c  lea     rdx, aMy; "MY"
0x140020063  mov     [rsp+0C0h+var_98], rdx
0x140020068  mov     [rsp+0C0h+var_A0], 0A8000h; int
0x140020070  xor     r9d, r9d
0x140020073  xor     r8d, r8d
0x140020076  lea     edx, [r12+0Ch]
0x14002007b  mov     rax, [rax+50h]
0x14002007f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020084  mov     [rbp+57h+arg_0], eax
0x140020087  cmp     [rbp+57h+arg_8], 0
0x14002008c  jnz     loc_140020129
0x140020092  cmp     eax, 80070002h
0x140020097  jnz     short loc_1400200E1
0x140020099  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14002009e  xor     r9d, r9d
0x1400200a1  mov     r8d, 2F1Eh
0x1400200a7  mov     edx, r12d
0x1400200aa  mov     rcx, rax
0x1400200ad  call    ?LogMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@KPEBGZZ; Microsoft::Windows::TelemetryLogger::LogMeasure(Microsoft::Windows::TracingLevel,ulong,ushort const *,...)
0x1400200b2  mov     ebx, [rbp+57h+arg_0]
0x1400200b5  mov     rcx, [rbp+57h+hMem+8]; hMem
0x1400200b9  call    cs:__imp_LocalFree
0x1400200c0  nop     dword ptr [rax+rax+00h]
0x1400200c5  mov     rcx, [rdi]
0x1400200c8  mov     rax, [rcx]
0x1400200cb  xor     r8d, r8d
0x1400200ce  mov     rdx, [rbp+57h+arg_8]
0x1400200d2  mov     rax, [rax+10h]
0x1400200d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400200db  nop
0x1400200dc  jmp     loc_140020311
0x1400200e1  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x1400200e6  xor     r9d, r9d
0x1400200e9  mov     r8d, 2F1Fh
0x1400200ef  mov     edx, r12d
0x1400200f2  mov     rcx, rax
0x1400200f5  call    ?LogMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@KPEBGZZ; Microsoft::Windows::TelemetryLogger::LogMeasure(Microsoft::Windows::TracingLevel,ulong,ushort const *,...)
0x1400200fa  mov     ebx, [rbp+57h+arg_0]
0x1400200fd  mov     rcx, [rbp+57h+hMem+8]; hMem
0x140020101  call    cs:__imp_LocalFree
0x140020108  nop     dword ptr [rax+rax+00h]
0x14002010d  mov     rcx, [rdi]
0x140020110  mov     rax, [rcx]
0x140020113  xor     r8d, r8d
0x140020116  mov     rdx, [rbp+57h+arg_8]
0x14002011a  mov     rax, [rax+10h]
0x14002011e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020123  nop
0x140020124  jmp     loc_140020311
0x140020129  mov     r9d, r12d
0x14002012c  lea     r8, [rbp+57h+hMem]
0x140020130  xor     edx, edx
0x140020132  mov     rcx, rsi
0x140020135  call    cs:__imp_HexStringToBinary
0x14002013c  nop     dword ptr [rax+rax+00h]
0x140020141  mov     ebx, eax
0x140020143  mov     [rbp+57h+arg_0], eax
0x140020146  test    eax, eax
0x140020148  jns     short loc_14002018F
0x14002014a  mov     rcx, [rbp+5Fh]; this
0x14002014e  mov     r9d, eax; char *
0x140020151  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140020158  mov     edx, 875h; void *
0x14002015d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140020162  nop
0x140020163  mov     rcx, [rbp+57h+hMem+8]; hMem
0x140020167  call    cs:__imp_LocalFree
0x14002016e  nop     dword ptr [rax+rax+00h]
0x140020173  mov     rcx, [rdi]
0x140020176  mov     rax, [rcx]
0x140020179  xor     r8d, r8d
0x14002017c  mov     rdx, [rbp+57h+arg_8]
0x140020180  mov     rax, [rax+10h]
0x140020184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020189  nop
0x14002018a  jmp     loc_140020311
0x14002018f  mov     edx, dword ptr [rbp+57h+hMem]; uBytes
0x140020192  xor     ecx, ecx; uFlags
0x140020194  call    cs:__imp_LocalAlloc
0x14002019b  nop     dword ptr [rax+rax+00h]
0x1400201a0  mov     [rbp+57h+hMem+8], rax
0x1400201a4  test    rax, rax
0x1400201a7  jnz     short loc_1400201F6
0x1400201a9  mov     ebx, 8007000Eh
0x1400201ae  mov     [rbp+57h+arg_0], ebx
0x1400201b1  mov     rcx, [rbp+5Fh]; this
0x1400201b5  mov     r9d, ebx; char *
0x1400201b8  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x1400201bf  mov     edx, 879h; void *
0x1400201c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400201c9  nop
0x1400201ca  mov     rcx, [rbp+57h+hMem+8]; hMem
0x1400201ce  call    cs:__imp_LocalFree
0x1400201d5  nop     dword ptr [rax+rax+00h]
0x1400201da  mov     rcx, [rdi]
0x1400201dd  mov     rax, [rcx]
0x1400201e0  xor     r8d, r8d
0x1400201e3  mov     rdx, [rbp+57h+arg_8]
0x1400201e7  mov     rax, [rax+10h]
0x1400201eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400201f0  nop
0x1400201f1  jmp     loc_140020311
0x1400201f6  mov     [rbp+57h+arg_0], 0
0x1400201fd  mov     r9d, r12d
0x140020200  lea     r8, [rbp+57h+hMem]
0x140020204  mov     rdx, rax
0x140020207  mov     rcx, rsi
0x14002020a  call    cs:__imp_HexStringToBinary
0x140020211  nop     dword ptr [rax+rax+00h]
0x140020216  mov     ebx, eax
0x140020218  mov     [rbp+57h+arg_0], eax
0x14002021b  test    eax, eax
0x14002021d  jns     short loc_140020264
0x14002021f  mov     rcx, [rbp+5Fh]; this
0x140020223  mov     r9d, eax; char *
0x140020226  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14002022d  mov     edx, 87Ch; void *
0x140020232  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140020237  nop
0x140020238  mov     rcx, [rbp+57h+hMem+8]; hMem
0x14002023c  call    cs:__imp_LocalFree
0x140020243  nop     dword ptr [rax+rax+00h]
0x140020248  mov     rcx, [rdi]
0x14002024b  mov     rax, [rcx]
0x14002024e  xor     r8d, r8d
0x140020251  mov     rdx, [rbp+57h+arg_8]
0x140020255  mov     rax, [rax+10h]
0x140020259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002025e  nop
0x14002025f  jmp     loc_140020311
0x140020264  mov     rcx, [rdi]
0x140020267  mov     rax, [rcx]
0x14002026a  mov     [rsp+0C0h+var_90], 0
0x140020273  lea     rdx, [rbp+57h+hMem]
0x140020277  mov     [rsp+0C0h+var_98], rdx
0x14002027c  mov     [rsp+0C0h+var_A0], 10000h
0x140020284  xor     r9d, r9d
0x140020287  mov     r8d, 10001h
0x14002028d  mov     rdx, [rbp+57h+arg_8]
0x140020291  mov     rax, [rax+20h]
0x140020295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002029a  test    rax, rax
0x14002029d  jnz     short loc_1400202E4
0x14002029f  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x1400202a4  xor     r9d, r9d
0x1400202a7  mov     r8d, 2F20h
0x1400202ad  mov     edx, r12d
0x1400202b0  mov     rcx, rax
0x1400202b3  call    ?LogMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@KPEBGZZ; Microsoft::Windows::TelemetryLogger::LogMeasure(Microsoft::Windows::TracingLevel,ulong,ushort const *,...)
0x1400202b8  mov     ebx, [rbp+57h+arg_0]
0x1400202bb  mov     rcx, [rbp+57h+hMem+8]; hMem
0x1400202bf  call    cs:__imp_LocalFree
0x1400202c6  nop     dword ptr [rax+rax+00h]
0x1400202cb  mov     rcx, [rdi]
0x1400202ce  mov     rax, [rcx]
0x1400202d1  xor     r8d, r8d
0x1400202d4  mov     rdx, [rbp+57h+arg_8]
0x1400202d8  mov     rax, [rax+10h]
0x1400202dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400202e1  nop
0x1400202e2  jmp     short loc_140020311
0x1400202e4  mov     [r14], rax
0x1400202e7  mov     ebx, [rbp+57h+arg_0]
0x1400202ea  mov     rcx, [rbp+57h+hMem+8]; hMem
0x1400202ee  call    cs:__imp_LocalFree
0x1400202f5  nop     dword ptr [rax+rax+00h]
0x1400202fa  mov     rcx, [rdi]
0x1400202fd  mov     rax, [rcx]
0x140020300  xor     r8d, r8d
0x140020303  mov     rdx, [rbp+57h+arg_8]
0x140020307  mov     rax, [rax+10h]
0x14002030b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020310  nop
0x140020311  lea     rcx, [rbp+57h+var_50]; this
0x140020315  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14002031a  mov     eax, ebx
0x14002031c  mov     rbx, [rsp+0C0h+arg_10]
0x140020324  add     rsp, 0A0h
0x14002032b  pop     r14
0x14002032d  pop     r12
0x14002032f  pop     rdi
0x140020330  pop     rsi
0x140020331  pop     rbp
0x140020332  retn
```
