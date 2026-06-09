# RTGetInternalCert

- ea: `0x180010b10`
- end: `0x180010c66`
- name: `RTGetInternalCert`
- size: `342`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800114c0`
- `0x180016f9c`

## callees

- `0x1800087f8`
- `0x180010b10`
- `0x180010f00`
- `0x180013c74`
- `0x180014458`
- `0x180026010`

## import_xrefs

- `CRYPT32!CertEnumCertificatesInStore` at `0x180010b9d`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180010b9d`
- `mqsec!MQSigCreateCertificate` at `0x180010bbd`
- `mqsec!MQSigCreateCertificate` at `0x180010bbd`

## pseudocode

```c
__int64 __fastcall RTGetInternalCert(_QWORD *a1, _QWORD *a2, int a3, int a4, __int64 a5)
{
  int Certificate; // ebx
  unsigned __int16 v10; // r8
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  void *v14; // rax
  PCCERT_CONTEXT v15; // rax
  _DWORD v17[14]; // [rsp+30h] [rbp-38h] BYREF

  Certificate = RtpOneTimeThreadInit();
  if ( Certificate < 0 )
  {
    v10 = 1106;
LABEL_17:
    LogMsgHR(Certificate, (wchar_t *)L"rt/rtcert", v10);
    return (unsigned int)Certificate;
  }
  *a1 = 0;
  v17[0] = 0;
  *a2 = 0;
  v11 = RTOpenInternalCertStore(a2, v17, a3, a4, a5);
  if ( v11 < 0 || !v17[0] )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        12,
        WPP_6ef86d4a7ad93db02f9a9cc581b2f9e2_Traceguids,
        (unsigned int)v11);
    v10 = 1107;
    goto LABEL_16;
  }
  v14 = (void *)(*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(*(_QWORD *)*a2 + 8LL))(
                  *a2,
                  v12,
                  v13,
                  (unsigned int)v11);
  v15 = CertEnumCertificatesInStore(v14, 0);
  if ( !v15 )
  {
    v10 = 30;
LABEL_16:
    Certificate = -1072824273;
    goto LABEL_17;
  }
  Certificate = MQSigCreateCertificate(a1, v15, 0, 0);
  if ( Certificate < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        13,
        WPP_6ef86d4a7ad93db02f9a9cc581b2f9e2_Traceguids,
        (unsigned int)Certificate);
    v10 = 40;
    goto LABEL_17;
  }
  return (unsigned int)Certificate;
}

```

## disassembly

```asm
0x180010b10  push    rbx
0x180010b12  push    rbp
0x180010b13  push    rsi
0x180010b14  push    rdi
0x180010b15  push    r14
0x180010b17  sub     rsp, 40h
0x180010b1b  mov     ebp, r9d
0x180010b1e  mov     r14d, r8d
0x180010b21  mov     rdi, rdx
0x180010b24  mov     rsi, rcx
0x180010b27  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x180010b2c  mov     ebx, eax
0x180010b2e  test    eax, eax
0x180010b30  jns     short loc_180010B3D
0x180010b32  mov     r8d, 452h
0x180010b38  jmp     loc_180010C4B
0x180010b3d  mov     rax, [rsp+68h+arg_20]
0x180010b45  lea     rdx, [rsp+68h+var_38]
0x180010b4a  mov     qword ptr [rsi], 0
0x180010b51  mov     r9d, ebp
0x180010b54  mov     r8d, r14d
0x180010b57  mov     [rsp+68h+var_48], rax
0x180010b5c  mov     rcx, rdi
0x180010b5f  mov     [rsp+68h+var_38], 0
0x180010b67  mov     qword ptr [rdi], 0
0x180010b6e  call    RTOpenInternalCertStore
0x180010b73  mov     r9d, eax
0x180010b76  test    eax, eax
0x180010b78  js      loc_180010C0C
0x180010b7e  cmp     [rsp+68h+var_38], 0
0x180010b83  jz      loc_180010C0C
0x180010b89  mov     rcx, [rdi]
0x180010b8c  mov     rax, [rcx]
0x180010b8f  mov     rax, [rax+8]
0x180010b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b98  mov     rcx, rax; hCertStore
0x180010b9b  xor     edx, edx; pPrevCertContext
0x180010b9d  call    cs:__imp_CertEnumCertificatesInStore
0x180010ba3  test    rax, rax
0x180010ba6  jnz     short loc_180010BB1
0x180010ba8  lea     r8d, [rax+1Eh]
0x180010bac  jmp     loc_180010C46
0x180010bb1  xor     r9d, r9d
0x180010bb4  xor     r8d, r8d
0x180010bb7  mov     rdx, rax
0x180010bba  mov     rcx, rsi
0x180010bbd  call    cs:__imp_MQSigCreateCertificate
0x180010bc3  mov     ebx, eax
0x180010bc5  test    eax, eax
0x180010bc7  jns     loc_180010C59
0x180010bcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180010bd4  lea     rax, WPP_GLOBAL_Control
0x180010bdb  cmp     rcx, rax
0x180010bde  jz      short loc_180010C04
0x180010be0  test    byte ptr [rcx+10Ch], 1
0x180010be7  jz      short loc_180010C04
0x180010be9  mov     rcx, [rcx+100h]
0x180010bf0  lea     r8, WPP_6ef86d4a7ad93db02f9a9cc581b2f9e2_Traceguids
0x180010bf7  mov     edx, 0Dh
0x180010bfc  mov     r9d, ebx
0x180010bff  call    WPP_SF_d
0x180010c04  mov     r8d, 28h ; '('
0x180010c0a  jmp     short loc_180010C4B
0x180010c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c13  lea     rax, WPP_GLOBAL_Control
0x180010c1a  cmp     rcx, rax
0x180010c1d  jz      short loc_180010C40
0x180010c1f  test    byte ptr [rcx+10Ch], 1
0x180010c26  jz      short loc_180010C40
0x180010c28  mov     rcx, [rcx+100h]
0x180010c2f  lea     r8, WPP_6ef86d4a7ad93db02f9a9cc581b2f9e2_Traceguids
0x180010c36  mov     edx, 0Ch
0x180010c3b  call    WPP_SF_d
0x180010c40  mov     r8d, 453h; unsigned __int16
0x180010c46  mov     ebx, 0C00E002Fh
0x180010c4b  lea     rdx, aRtRtcert; "rt/rtcert"
0x180010c52  mov     ecx, ebx; int
0x180010c54  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180010c59  mov     eax, ebx
0x180010c5b  add     rsp, 40h
0x180010c5f  pop     r14
0x180010c61  pop     rdi
0x180010c62  pop     rsi
0x180010c63  pop     rbp
0x180010c64  pop     rbx
0x180010c65  retn
```
