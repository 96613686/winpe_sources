# RTOpenInternalCertStore

- ea: `0x180010f00`
- end: `0x180011040`
- name: `RTOpenInternalCertStore`
- size: `320`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180010b10`
- `0x1800114c0`
- `0x1800120b0`

## callees

- `0x1800087f8`
- `0x18000a33c`
- `0x180010f00`
- `0x180013c74`
- `0x180014458`
- `0x180026010`

## import_xrefs

- `CRYPT32!CertEnumCertificatesInStore` at `0x180010ff4`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180010ff4`
- `mqsec!MQSigOpenUserCertStore` at `0x180010f7a`
- `mqsec!MQSigOpenUserCertStore` at `0x180010f7a`

## pseudocode

```c
__int64 __fastcall RTOpenInternalCertStore(_QWORD *a1, _DWORD *a2, int a3, int a4, __int64 a5)
{
  int v9; // ebx
  unsigned __int16 v10; // r8
  int v12; // eax
  __int64 v13; // rbx
  const CERT_CONTEXT *v14; // rdx
  void *i; // rcx
  PCCERT_CONTEXT v16; // rax
  __int128 v17; // [rsp+20h] [rbp-38h] BYREF

  v9 = RtpOneTimeThreadInit();
  if ( v9 < 0 )
  {
    v10 = 1102;
LABEL_3:
    LogMsgHR(v9, (wchar_t *)L"rt/rtcert", v10);
    return (unsigned int)v9;
  }
  v17 = 0;
  if ( a3 )
    WORD4(v17) = 257;
  else
    BYTE8(v17) = 0;
  *(_QWORD *)&v17 = a5;
  BYTE10(v17) = a4 != 0;
  v12 = MQSigOpenUserCertStore(a1, "Software\\Microsoft\\MSMQ\\CertStore", &v17);
  v9 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        10,
        WPP_6ef86d4a7ad93db02f9a9cc581b2f9e2_Traceguids,
        (unsigned int)v12);
    v10 = 1103;
    goto LABEL_3;
  }
  if ( a2 )
  {
    v13 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 8LL))(*a1);
    *a2 = 0;
    v14 = 0;
    for ( i = (void *)v13; ; i = (void *)v13 )
    {
      v16 = CertEnumCertificatesInStore(i, v14);
      if ( !v16 )
        break;
      ++*a2;
      v14 = v16;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 11, WPP_6ef86d4a7ad93db02f9a9cc581b2f9e2_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180010f00  push    rbx
0x180010f02  push    rbp
0x180010f03  push    rsi
0x180010f04  push    rdi
0x180010f05  push    r14
0x180010f07  sub     rsp, 30h
0x180010f0b  mov     ebp, r9d
0x180010f0e  mov     esi, r8d
0x180010f11  mov     rdi, rdx
0x180010f14  mov     r14, rcx
0x180010f17  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x180010f1c  mov     ebx, eax
0x180010f1e  test    eax, eax
0x180010f20  jns     short loc_180010F3D
0x180010f22  mov     r8d, 44Eh; unsigned __int16
0x180010f28  lea     rdx, aRtRtcert; "rt/rtcert"
0x180010f2f  mov     ecx, ebx; int
0x180010f31  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180010f36  mov     eax, ebx
0x180010f38  jmp     loc_180011035
0x180010f3d  xorps   xmm0, xmm0
0x180010f40  movups  [rsp+58h+var_38], xmm0
0x180010f45  test    esi, esi
0x180010f47  jz      short loc_180010F52
0x180010f49  mov     word ptr [rsp+58h+var_38+8], 101h
0x180010f50  jmp     short loc_180010F57
0x180010f52  mov     byte ptr [rsp+58h+var_38+8], 0
0x180010f57  mov     rax, [rsp+58h+arg_20]
0x180010f5f  lea     r8, [rsp+58h+var_38]
0x180010f64  test    ebp, ebp
0x180010f66  mov     qword ptr [rsp+58h+var_38], rax
0x180010f6b  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MSMQ\\CertStore"
0x180010f72  mov     rcx, r14
0x180010f75  setnz   byte ptr [rsp+58h+var_38+0Ah]
0x180010f7a  call    cs:__imp_MQSigOpenUserCertStore
0x180010f80  mov     ebx, eax
0x180010f82  test    eax, eax
0x180010f84  jns     short loc_180010FC8
0x180010f86  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f8d  lea     rdx, WPP_GLOBAL_Control
0x180010f94  cmp     rcx, rdx
0x180010f97  jz      short loc_180010FBD
0x180010f99  test    byte ptr [rcx+10Ch], 1
0x180010fa0  jz      short loc_180010FBD
0x180010fa2  mov     rcx, [rcx+100h]
0x180010fa9  lea     r8, WPP_6ef86d4a7ad93db02f9a9cc581b2f9e2_Traceguids
0x180010fb0  mov     edx, 0Ah
0x180010fb5  mov     r9d, eax
0x180010fb8  call    WPP_SF_d
0x180010fbd  mov     r8d, 44Fh
0x180010fc3  jmp     loc_180010F28
0x180010fc8  test    rdi, rdi
0x180010fcb  jz      short loc_180010FFF
0x180010fcd  mov     rcx, [r14]
0x180010fd0  mov     rax, [rcx]
0x180010fd3  mov     rax, [rax+8]
0x180010fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fdc  mov     rbx, rax
0x180010fdf  mov     dword ptr [rdi], 0
0x180010fe5  xor     edx, edx
0x180010fe7  mov     rcx, rax
0x180010fea  jmp     short loc_180010FF4
0x180010fec  inc     dword ptr [rdi]
0x180010fee  mov     rdx, rax; pPrevCertContext
0x180010ff1  mov     rcx, rbx; hCertStore
0x180010ff4  call    cs:__imp_CertEnumCertificatesInStore
0x180010ffa  test    rax, rax
0x180010ffd  jnz     short loc_180010FEC
0x180010fff  mov     rcx, cs:WPP_GLOBAL_Control
0x180011006  lea     rdx, WPP_GLOBAL_Control
0x18001100d  cmp     rcx, rdx
0x180011010  jz      short loc_180011033
0x180011012  test    byte ptr [rcx+10Ch], 4
0x180011019  jz      short loc_180011033
0x18001101b  mov     rcx, [rcx+100h]
0x180011022  lea     r8, WPP_6ef86d4a7ad93db02f9a9cc581b2f9e2_Traceguids
0x180011029  mov     edx, 0Bh
0x18001102e  call    WPP_SF_
0x180011033  xor     eax, eax
0x180011035  add     rsp, 30h
0x180011039  pop     r14
0x18001103b  pop     rdi
0x18001103c  pop     rsi
0x18001103d  pop     rbp
0x18001103e  pop     rbx
0x18001103f  retn
```
