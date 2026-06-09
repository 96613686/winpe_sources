# RTGetUserCerts

- ea: `0x180010c70`
- end: `0x180010ef3`
- name: `RTGetUserCerts`
- size: `643`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x180010a58`
- `0x180010c70`
- `0x180013c74`
- `0x180014458`
- `0x180018164`
- `0x18001d430`
- `0x18001d560`
- `0x18001d604`
- `0x180026010`

## import_xrefs

- `msvcrt!free` at `0x180010cf4`
- `msvcrt!free` at `0x180010d5a`
- `msvcrt!free` at `0x180010d87`
- `msvcrt!free` at `0x180010e28`
- `msvcrt!free` at `0x180010e72`
- `msvcrt!free` at `0x180010ece`
- `msvcrt!free` at `0x180010cf4`
- `msvcrt!free` at `0x180010d5a`
- `msvcrt!free` at `0x180010d87`
- `msvcrt!free` at `0x180010e28`
- `msvcrt!free` at `0x180010e72`
- `msvcrt!free` at `0x180010ece`
- `ADVAPI32!GetLengthSid` at `0x180010d0a`
- `ADVAPI32!GetLengthSid` at `0x180010d0a`
- `mqsec!MQSigCreateCertificate` at `0x180010e59`
- `mqsec!MQSigCreateCertificate` at `0x180010e59`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RTGetUserCerts(__int64 a1, unsigned int *a2, void *a3)
{
  int v6; // eax
  int v7; // edi
  unsigned int v8; // r14d
  int v9; // ebx
  DWORD LengthSid; // eax
  bool v12; // dl
  bool v13; // r8
  bool v14; // r9
  int ThreadUserSid; // eax
  __int64 v16; // rbx
  unsigned int v17; // [rsp+40h] [rbp-29h] BYREF
  void *Block; // [rsp+48h] [rbp-21h] BYREF
  int v19[2]; // [rsp+50h] [rbp-19h] BYREF
  void *v20; // [rsp+58h] [rbp-11h] BYREF
  int v21; // [rsp+60h] [rbp-9h] BYREF
  struct tagPROPVARIANT v22; // [rsp+68h] [rbp-1h] BYREF
  _QWORD v23[2]; // [rsp+80h] [rbp+17h] BYREF
  _DWORD v24[2]; // [rsp+90h] [rbp+27h] BYREF
  void *v25; // [rsp+98h] [rbp+2Fh]
  unsigned int v26; // [rsp+E8h] [rbp+7Fh] BYREF

  v6 = RtpOneTimeThreadInit();
  v7 = v6;
  if ( v6 < 0 )
  {
    LogMsgHR(v6, (wchar_t *)L"rt/rtcert", 0x462u);
    return (unsigned int)v7;
  }
  Block = 0;
  v17 = 0;
  v8 = *a2;
  if ( IsWorkGroupMode() )
  {
    v9 = -1072824214;
    LogMsgHR(-1072824214, (wchar_t *)L"rt/rtcert", 0x4Bu);
    free(Block);
    return (unsigned int)v9;
  }
  if ( a3 )
  {
    LengthSid = GetLengthSid(a3);
    v17 = LengthSid;
  }
  else
  {
    v26 = 0;
    v19[0] = 0;
    ThreadUserSid = RTpGetThreadUserSid((int *)&v26, v19, (unsigned __int8 **)&Block, &v17);
    v9 = ThreadUserSid;
    if ( ThreadUserSid < 0 )
    {
      LogMsgHR(ThreadUserSid, (wchar_t *)L"rt/rtcert", 0x50u);
      free(Block);
      return (unsigned int)v9;
    }
    if ( v26 )
    {
      v9 = -1072824303;
      LogMsgHR(-1072824303, (wchar_t *)L"rt/rtcert", 0x5Au);
      free(Block);
      return (unsigned int)v9;
    }
    a3 = Block;
    LengthSid = v17;
  }
  v23[0] = 1;
  v21 = 702;
  v20 = 0;
  v23[1] = &v21;
  v24[1] = 0;
  v24[0] = LengthSid;
  v25 = a3;
  v9 = ADInit((void (*)(void))&v21, v12, v13, v14);
  if ( v9 < 0
    || (v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _DWORD *, _QWORD *, void **))(*(_QWORD *)g_pAD + 184LL))(
               g_pAD,
               0,
               0,
               v24,
               v23,
               &v20),
        v9 < 0) )
  {
    LogMsgHR(v9, (wchar_t *)L"rt/rtcert", 0x64u);
    free(Block);
    return (unsigned int)v9;
  }
  v16 = 0;
  while ( 1 )
  {
    memset(&v22, 0, sizeof(v22));
    v26 = 1;
    v22.vt = 1;
    v7 = ADQueryResults(v20, &v26, &v22);
    if ( v7 < 0 || !v26 )
      break;
    if ( (unsigned int)v16 < v8 )
    {
      *(_QWORD *)v19 = 0;
      if ( (int)MQSigCreateCertificate(v19, 0, v22.bstrblobVal.pData, v22.ulVal) < 0 )
        goto LABEL_22;
      *(_QWORD *)(a1 + 8 * v16) = *(_QWORD *)v19;
    }
    v16 = (unsigned int)(v16 + 1);
LABEL_22:
    free(v22.bstrblobVal.pData);
  }
  ADEndQuery(v20);
  *a2 = v16;
  if ( v7 < 0 )
    LogMsgHR(v7, (wchar_t *)L"rt/rtcert", 0x6Eu);
  free(Block);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180010c70  mov     [rsp-8+arg_0], rbx
0x180010c75  mov     [rsp-8+arg_8], rsi
0x180010c7a  push    rbp
0x180010c7b  push    rdi
0x180010c7c  push    r13
0x180010c7e  push    r14
0x180010c80  push    r15
0x180010c82  lea     rbp, [rsp-37h]
0x180010c87  sub     rsp, 0A0h
0x180010c8e  mov     rbx, r8
0x180010c91  mov     rsi, rdx
0x180010c94  mov     r15, rcx
0x180010c97  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x180010c9c  mov     edi, eax
0x180010c9e  test    eax, eax
0x180010ca0  jns     short loc_180010CBB
0x180010ca2  mov     r8d, 462h; unsigned __int16
0x180010ca8  lea     rdx, aRtRtcert; "rt/rtcert"
0x180010caf  mov     ecx, eax; int
0x180010cb1  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180010cb6  jmp     loc_180010ED5
0x180010cbb  mov     [rbp+57h+Block], 0
0x180010cc3  mov     [rbp+57h+var_80], 0
0x180010cca  mov     r14d, [rsi]
0x180010ccd  call    ?IsWorkGroupMode@@YA_NXZ; IsWorkGroupMode(void)
0x180010cd2  test    al, al
0x180010cd4  jz      short loc_180010D02
0x180010cd6  mov     r8d, 4Bh ; 'K'; unsigned __int16
0x180010cdc  lea     rdx, aRtRtcert; "rt/rtcert"
0x180010ce3  mov     ebx, 0C00E006Ah
0x180010ce8  mov     ecx, ebx; int
0x180010cea  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180010cef  nop
0x180010cf0  mov     rcx, [rbp+57h+Block]; Block
0x180010cf4  call    cs:__imp_free
0x180010cfa  nop
0x180010cfb  mov     eax, ebx
0x180010cfd  jmp     loc_180010ED7
0x180010d02  test    rbx, rbx
0x180010d05  jz      short loc_180010D18
0x180010d07  mov     rcx, rbx; pSid
0x180010d0a  call    cs:__imp_GetLengthSid
0x180010d10  mov     [rbp+57h+var_80], eax
0x180010d13  jmp     loc_180010D9A
0x180010d18  mov     [rbp+57h+arg_18], 0
0x180010d1f  mov     [rbp+57h+var_70], 0
0x180010d26  lea     r9, [rbp+57h+var_80]; unsigned int *
0x180010d2a  lea     r8, [rbp+57h+Block]; unsigned __int8 **
0x180010d2e  lea     rdx, [rbp+57h+var_70]; int *
0x180010d32  lea     rcx, [rbp+57h+arg_18]; int *
0x180010d36  call    ?RTpGetThreadUserSid@@YAJPEAH0PEAPEAEPEAK@Z; RTpGetThreadUserSid(int *,int *,uchar * *,ulong *)
0x180010d3b  mov     ebx, eax
0x180010d3d  test    eax, eax
0x180010d3f  jns     short loc_180010D63
0x180010d41  mov     r8d, 50h ; 'P'; unsigned __int16
0x180010d47  lea     rdx, aRtRtcert; "rt/rtcert"
0x180010d4e  mov     ecx, eax; int
0x180010d50  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180010d55  nop
0x180010d56  mov     rcx, [rbp+57h+Block]; Block
0x180010d5a  call    cs:__imp_free
0x180010d60  nop
0x180010d61  jmp     short loc_180010CFB
0x180010d63  cmp     [rbp+57h+arg_18], 0
0x180010d67  jz      short loc_180010D93
0x180010d69  mov     r8d, 5Ah ; 'Z'; unsigned __int16
0x180010d6f  lea     rdx, aRtRtcert; "rt/rtcert"
0x180010d76  mov     ebx, 0C00E0011h
0x180010d7b  mov     ecx, ebx; int
0x180010d7d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180010d82  nop
0x180010d83  mov     rcx, [rbp+57h+Block]; Block
0x180010d87  call    cs:__imp_free
0x180010d8d  nop
0x180010d8e  jmp     loc_180010CFB
0x180010d93  mov     rbx, [rbp+57h+Block]
0x180010d97  mov     eax, [rbp+57h+var_80]
0x180010d9a  mov     [rbp+57h+var_40], 1
0x180010da2  mov     [rbp+57h+var_60], 2BEh
0x180010da9  mov     [rbp+57h+var_68], 0
0x180010db1  mov     r13d, 1
0x180010db7  lea     rcx, [rbp+57h+var_60]; void (*)(void)
0x180010dbb  mov     [rbp+57h+var_38], rcx
0x180010dbf  mov     [rbp+57h+var_2C], 0
0x180010dc6  mov     [rbp+57h+var_30], eax
0x180010dc9  mov     [rbp+57h+var_28], rbx
0x180010dcd  call    ?ADInit@@YAJP6AXXZ_N11@Z; ADInit(void (*)(void),bool,bool,bool)
0x180010dd2  mov     ebx, eax
0x180010dd4  test    eax, eax
0x180010dd6  js      short loc_180010E0F
0x180010dd8  mov     rcx, cs:?g_pAD@@3V?$P@VCBaseADProvider@@@@A; P<CBaseADProvider> g_pAD
0x180010ddf  mov     rax, [rcx]
0x180010de2  lea     rdx, [rbp+57h+var_68]
0x180010de6  mov     [rsp+0C0h+var_98], rdx
0x180010deb  lea     rdx, [rbp+57h+var_40]
0x180010def  mov     [rsp+0C0h+var_A0], rdx
0x180010df4  lea     r9, [rbp+57h+var_30]
0x180010df8  xor     r8d, r8d
0x180010dfb  xor     edx, edx
0x180010dfd  mov     rax, [rax+0B8h]
0x180010e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e09  mov     ebx, eax
0x180010e0b  test    eax, eax
0x180010e0d  jns     short loc_180010E34
0x180010e0f  mov     r8d, 64h ; 'd'; unsigned __int16
0x180010e15  lea     rdx, aRtRtcert; "rt/rtcert"
0x180010e1c  mov     ecx, ebx; int
0x180010e1e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180010e23  nop
0x180010e24  mov     rcx, [rbp+57h+Block]; Block
0x180010e28  call    cs:__imp_free
0x180010e2e  nop
0x180010e2f  jmp     loc_180010CFB
0x180010e34  xor     ebx, ebx
0x180010e36  jmp     short loc_180010E79
0x180010e38  cmp     [rbp+57h+arg_18], 0
0x180010e3c  jz      short loc_180010EA6
0x180010e3e  cmp     ebx, r14d
0x180010e41  jnb     short loc_180010E6B
0x180010e43  mov     qword ptr [rbp+57h+var_70], 0
0x180010e4b  mov     r9d, dword ptr [rbp+57h+var_58+8]
0x180010e4f  mov     r8, qword ptr [rbp+57h+var_58+10h]
0x180010e53  xor     edx, edx
0x180010e55  lea     rcx, [rbp+57h+var_70]
0x180010e59  call    cs:__imp_MQSigCreateCertificate
0x180010e5f  test    eax, eax
0x180010e61  js      short loc_180010E6E
0x180010e63  mov     rax, qword ptr [rbp+57h+var_70]
0x180010e67  mov     [r15+rbx*8], rax
0x180010e6b  add     ebx, r13d
0x180010e6e  mov     rcx, qword ptr [rbp+57h+var_58+10h]; Block
0x180010e72  call    cs:__imp_free
0x180010e78  nop
0x180010e79  xorps   xmm0, xmm0
0x180010e7c  xor     eax, eax
0x180010e7e  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180010e82  mov     [rbp+57h+arg_18], r13d
0x180010e86  mov     qword ptr [rbp+57h+var_58+10h], rax
0x180010e8a  mov     word ptr [rbp+57h+var_58], r13w
0x180010e8f  lea     r8, [rbp+57h+var_58]; struct tagPROPVARIANT *
0x180010e93  lea     rdx, [rbp+57h+arg_18]; unsigned int *
0x180010e97  mov     rcx, [rbp+57h+var_68]; void *
0x180010e9b  call    ?ADQueryResults@@YAJPEAXPEAKQEAUtagPROPVARIANT@@@Z; ADQueryResults(void *,ulong *,tagPROPVARIANT * const)
0x180010ea0  test    eax, eax
0x180010ea2  mov     edi, eax
0x180010ea4  jns     short loc_180010E38
0x180010ea6  mov     rcx, [rbp+57h+var_68]; void *
0x180010eaa  call    ?ADEndQuery@@YAJPEAX@Z; ADEndQuery(void *)
0x180010eaf  mov     [rsi], ebx
0x180010eb1  test    edi, edi
0x180010eb3  jns     short loc_180010ECA
0x180010eb5  mov     r8d, 6Eh ; 'n'; unsigned __int16
0x180010ebb  lea     rdx, aRtRtcert; "rt/rtcert"
0x180010ec2  mov     ecx, edi; int
0x180010ec4  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180010ec9  nop
0x180010eca  mov     rcx, [rbp+57h+Block]; Block
0x180010ece  call    cs:__imp_free
0x180010ed4  nop
0x180010ed5  mov     eax, edi
0x180010ed7  lea     r11, [rsp+0C0h+var_20]
0x180010edf  mov     rbx, [r11+30h]
0x180010ee3  mov     rsi, [r11+38h]
0x180010ee7  mov     rsp, r11
0x180010eea  pop     r15
0x180010eec  pop     r14
0x180010eee  pop     r13
0x180010ef0  pop     rdi
0x180010ef1  pop     rbp
0x180010ef2  retn
```
