# BuildTreeConnectSecurityInformation

- ea: `0x140035df8`
- end: `0x140036085`
- name: `BuildTreeConnectSecurityInformation`
- size: `653`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140041980`
- `0x140041c80`
- `0x140041e90`

## callees

- `0x14000b120`
- `0x14000dfa8`
- `0x14000e694`
- `0x14000ed10`
- `0x140035df8`
- `0x14003ce2c`
- `0x14003ceb8`
- `0x14003ee4c`

## import_xrefs

- `ntoskrnl!RtlUnicodeStringToOemString` at `0x140035f80`
- `ntoskrnl!RtlUnicodeStringToOemString` at `0x140035f80`

## pseudocode

```c
__int64 __fastcall BuildTreeConnectSecurityInformation(__int64 a1, __int64 a2, _WORD *a3, __int16 *a4)
{
  __int64 v4; // r14
  __int64 ExchangeSession; // rax
  __int64 v9; // rcx
  CHAR *v10; // r9
  __int64 v11; // r10
  int v12; // edi
  int v13; // esi
  __int128 *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rax
  const UNICODE_STRING *v18; // rdx
  __int16 v19; // ax
  int v21; // [rsp+28h] [rbp-58h]
  int v22; // [rsp+28h] [rbp-58h]
  struct _STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  __int128 v24; // [rsp+40h] [rbp-40h] BYREF
  __int128 v25; // [rsp+50h] [rbp-30h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  __int128 v27; // [rsp+70h] [rbp-10h] BYREF
  char *v28; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v29; // [rsp+C8h] [rbp+48h] BYREF

  v29 = a2;
  v4 = *(_QWORD *)(a1 + 80);
  v28 = 0;
  v27 = 0;
  v26 = 0;
  v24 = 0;
  v25 = 0;
  ExchangeSession = SmbCeGetExchangeSession(a1, a2, a3, a2);
  if ( MRxSmbRequireExtendedSecurity == (_BYTE)v11 && *(_QWORD *)(ExchangeSession + 264) == v11 )
  {
    v12 = v11;
    if ( *(_BYTE *)(v4 + 502) == (_BYTE)v11 )
    {
      v17 = *(_QWORD *)(ExchangeSession + 48);
      if ( v17 && (v18 = *(const UNICODE_STRING **)(v17 + 24)) != 0 )
      {
        if ( EnablePlainTextPassword == (_BYTE)v11 )
        {
          v13 = -1073741715;
          if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
          {
            v21 = v11;
            McTemplateK0qqq_EtwWriteTransfer(v9, (unsigned int)SessionSetupError, v9 + 340, -1073741715, 102, v21);
          }
        }
        else
        {
          v19 = *a4;
          *(&DestinationString.MaximumLength + 2) = 0;
          DestinationString.Buffer = v10;
          *(_DWORD *)&DestinationString.MaximumLength = (unsigned __int16)(v19 - 1);
          DestinationString.Length = v19 - 1;
          v13 = RtlUnicodeStringToOemString(&DestinationString, v18, 0);
          if ( v13 >= 0 )
            v12 = DestinationString.Length + 1;
        }
      }
      else
      {
        v12 = 1;
        if ( *(_DWORD *)a4 )
        {
          *v10 = v11;
          v13 = v11;
        }
        else
        {
          v13 = -2147483643;
        }
      }
      *(_DWORD *)a4 -= v12;
    }
    else
    {
      v13 = BuildNtLanmanResponsePrologue(v9, &v27, &v26, &v24, &v25, &v28);
      if ( v13 >= 0 )
      {
        if ( (*(_DWORD *)(v4 + 420) & 2) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_05397278958134d5d85e8902d6beeb26_Traceguids);
          }
          LOWORD(v12) = v24;
          v14 = &v24;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_05397278958134d5d85e8902d6beeb26_Traceguids);
          }
          LOWORD(v12) = v25;
          v14 = &v25;
        }
        v13 = SmbPutString(&v29, v14, a4);
        BuildNtLanmanResponseEpilogue(a1, &v28, v15, v16);
      }
    }
    *a3 = v12;
  }
  else
  {
    v13 = -1073741240;
    if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
    {
      v22 = v11;
      McTemplateK0qqq_EtwWriteTransfer(v9, (unsigned int)SessionSetupError, v9 + 340, -1073741240, 25, v22);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        (unsigned int)WPP_05397278958134d5d85e8902d6beeb26_Traceguids,
        v4,
        v4 + 80);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140035df8  mov     [rsp-38h+arg_10], rbx
0x140035dfd  mov     [rsp-38h+arg_8], rdx
0x140035e02  push    rbp
0x140035e03  push    rsi
0x140035e04  push    rdi
0x140035e05  push    r12
0x140035e07  push    r13
0x140035e09  push    r14
0x140035e0b  push    r15
0x140035e0d  mov     rbp, rsp
0x140035e10  sub     rsp, 80h
0x140035e17  mov     r14, [rcx+50h]
0x140035e1b  xorps   xmm0, xmm0
0x140035e1e  xorps   xmm1, xmm1
0x140035e21  xor     r10d, r10d
0x140035e24  mov     r15, r9
0x140035e27  mov     [rbp+arg_0], r10
0x140035e2b  movups  [rbp+var_10], xmm0
0x140035e2f  mov     r12, r8
0x140035e32  mov     r9, rdx
0x140035e35  movups  [rbp+var_20], xmm1
0x140035e39  mov     r13, rcx
0x140035e3c  movups  [rbp+var_40], xmm0
0x140035e40  movups  [rbp+var_30], xmm1
0x140035e44  call    SmbCeGetExchangeSession
0x140035e49  cmp     cs:MRxSmbRequireExtendedSecurity, r10b
0x140035e50  jnz     loc_140035FF2
0x140035e56  cmp     [rax+108h], r10
0x140035e5d  jnz     loc_140035FF2
0x140035e63  mov     edi, r10d
0x140035e66  cmp     [r14+1F6h], r10b
0x140035e6d  jz      loc_140035F3E
0x140035e73  lea     rax, [rbp+arg_0]
0x140035e77  mov     [rsp+80h+var_58], rax
0x140035e7c  lea     r9, [rbp+var_40]
0x140035e80  lea     rax, [rbp+var_30]
0x140035e84  lea     r8, [rbp+var_20]
0x140035e88  mov     [rsp+80h+var_60], rax
0x140035e8d  lea     rdx, [rbp+var_10]
0x140035e91  call    BuildNtLanmanResponsePrologue
0x140035e96  mov     esi, eax
0x140035e98  test    eax, eax
0x140035e9a  js      loc_140035FEB
0x140035ea0  mov     eax, [r14+1A4h]
0x140035ea7  test    al, 2
0x140035ea9  jz      short loc_140035EE6
0x140035eab  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140035eb2  lea     rax, WPP_GLOBAL_Control
0x140035eb9  cmp     rcx, rax
0x140035ebc  jz      short loc_140035EDC
0x140035ebe  test    dword ptr [rcx+2Ch], 400h
0x140035ec5  jz      short loc_140035EDC
0x140035ec7  mov     rcx, [rcx+18h]
0x140035ecb  lea     r8, WPP_05397278958134d5d85e8902d6beeb26_Traceguids
0x140035ed2  mov     edx, 15h
0x140035ed7  call    WPP_SF_
0x140035edc  movzx   edi, word ptr [rbp+var_40]
0x140035ee0  lea     rdx, [rbp+var_40]
0x140035ee4  jmp     short loc_140035F1F
0x140035ee6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140035eed  lea     rax, WPP_GLOBAL_Control
0x140035ef4  cmp     rcx, rax
0x140035ef7  jz      short loc_140035F17
0x140035ef9  test    dword ptr [rcx+2Ch], 400h
0x140035f00  jz      short loc_140035F17
0x140035f02  mov     rcx, [rcx+18h]
0x140035f06  lea     r8, WPP_05397278958134d5d85e8902d6beeb26_Traceguids
0x140035f0d  mov     edx, 16h
0x140035f12  call    WPP_SF_
0x140035f17  movzx   edi, word ptr [rbp+var_30]
0x140035f1b  lea     rdx, [rbp+var_30]
0x140035f1f  mov     r8, r15
0x140035f22  lea     rcx, [rbp+arg_8]
0x140035f26  call    SmbPutString
0x140035f2b  lea     rdx, [rbp+arg_0]
0x140035f2f  mov     rcx, r13
0x140035f32  mov     esi, eax
0x140035f34  call    BuildNtLanmanResponseEpilogue
0x140035f39  jmp     loc_140035FEB
0x140035f3e  mov     rax, [rax+30h]
0x140035f42  test    rax, rax
0x140035f45  jz      loc_140035FCF
0x140035f4b  mov     rdx, [rax+18h]; SourceString
0x140035f4f  test    rdx, rdx
0x140035f52  jz      short loc_140035FCF
0x140035f54  cmp     cs:EnablePlainTextPassword, r10b
0x140035f5b  mov     ebx, 1
0x140035f60  jz      short loc_140035F9A
0x140035f62  movzx   eax, word ptr [r15]
0x140035f66  lea     rcx, [rbp+DestinationString]; DestinationString
0x140035f6a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140035f6e  sub     ax, bx
0x140035f71  mov     [rbp+DestinationString.Buffer], r9
0x140035f75  xor     r8d, r8d; AllocateDestinationString
0x140035f78  mov     [rbp+DestinationString.MaximumLength], ax
0x140035f7c  mov     [rbp+DestinationString.Length], ax
0x140035f80  call    cs:__imp_RtlUnicodeStringToOemString
0x140035f87  nop     dword ptr [rax+rax+00h]
0x140035f8c  mov     esi, eax
0x140035f8e  test    eax, eax
0x140035f90  js      short loc_140035FE8
0x140035f92  movzx   edi, [rbp+DestinationString.Length]
0x140035f96  add     edi, ebx
0x140035f98  jmp     short loc_140035FE8
0x140035f9a  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits, bl
0x140035fa0  mov     esi, 0C000006Dh
0x140035fa5  jz      short loc_140035FE8
0x140035fa7  mov     dword ptr [rsp+80h+var_58], r10d
0x140035fac  lea     r8, [rcx+154h]
0x140035fb3  mov     r9d, 0C000006Dh
0x140035fb9  mov     dword ptr [rsp+80h+var_60], 10300266h
0x140035fc1  lea     rdx, SessionSetupError
0x140035fc8  call    McTemplateK0qqq_EtwWriteTransfer
0x140035fcd  jmp     short loc_140035FE8
0x140035fcf  mov     ebx, 1
0x140035fd4  mov     edi, ebx
0x140035fd6  cmp     [r15], ebx
0x140035fd9  jb      short loc_140035FE3
0x140035fdb  mov     [r9], r10b
0x140035fde  mov     esi, r10d
0x140035fe1  jmp     short loc_140035FE8
0x140035fe3  mov     esi, 80000005h
0x140035fe8  sub     [r15], edi
0x140035feb  mov     [r12], di
0x140035ff0  jmp     short loc_140036067
0x140035ff2  mov     ebx, 1
0x140035ff7  mov     esi, 0C0000248h
0x140035ffc  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits, bl
0x140036002  jz      short loc_14003602A
0x140036004  mov     dword ptr [rsp+80h+var_58], r10d
0x140036009  lea     r8, [rcx+154h]
0x140036010  mov     r9d, 0C0000248h
0x140036016  mov     dword ptr [rsp+80h+var_60], 10300219h
0x14003601e  lea     rdx, SessionSetupError
0x140036025  call    McTemplateK0qqq_EtwWriteTransfer
0x14003602a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140036031  lea     rax, WPP_GLOBAL_Control
0x140036038  cmp     rcx, rax
0x14003603b  jz      short loc_140036067
0x14003603d  test    dword ptr [rcx+2Ch], 100h
0x140036044  jz      short loc_140036067
0x140036046  mov     rcx, [rcx+18h]
0x14003604a  lea     rax, [r14+50h]
0x14003604e  mov     edx, 14h
0x140036053  mov     [rsp+80h+var_60], rax
0x140036058  mov     r9, r14
0x14003605b  lea     r8, WPP_05397278958134d5d85e8902d6beeb26_Traceguids
0x140036062  call    WPP_SF_qZ
0x140036067  mov     rbx, [rsp+80h+arg_10]
0x14003606f  mov     eax, esi
0x140036071  add     rsp, 80h
0x140036078  pop     r15
0x14003607a  pop     r14
0x14003607c  pop     r13
0x14003607e  pop     r12
0x140036080  pop     rdi
0x140036081  pop     rsi
0x140036082  pop     rbp
0x140036083  retn
```
