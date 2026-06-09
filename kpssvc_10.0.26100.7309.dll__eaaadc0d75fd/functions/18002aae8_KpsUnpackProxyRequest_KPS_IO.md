# KpsUnpackProxyRequest(_KPS_IO *)

- ea: `0x18002aae8`
- end: `0x18002b033`
- name: `?KpsUnpackProxyRequest@@YAKPEAU_KPS_IO@@@Z`
- size: `1355`
- prototype: `__int64 __fastcall(struct _KPS_IO *, __int64, int, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800222f0`

## callees

- `0x18001ae38`
- `0x1800268f0`
- `0x180026a08`
- `0x180026d9c`
- `0x1800284ec`
- `0x1800288c4`
- `0x180028c08`
- `0x18002aae8`
- `0x18002b24c`
- `0x18002b4e0`
- `0x18002bb28`
- `0x18002c358`
- `0x18002c930`
- `0x18002fe08`
- `0x18003012c`

## import_xrefs

- `WS2_32!__imp_ntohl` at `0x18002ac38`
- `WS2_32!__imp_ntohl` at `0x18002ac38`
- `ntdll!RtlInitUnicodeString` at `0x18002aebe`
- `ntdll!RtlInitUnicodeString` at `0x18002aebe`

## string_xrefs

- `0x18002abea`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`
- `0x18002ad43`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`
- `0x18002ae33`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`
- `0x18002b008`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
__int64 __fastcall KpsUnpackProxyRequest(struct _KPS_IO *a1, __int64 a2, int a3, int a4)
{
  unsigned int *v4; // rdi
  void *v5; // r14
  unsigned int v6; // r12d
  int v7; // r15d
  WCHAR *v8; // r13
  _QWORD *v10; // rcx
  void *v11; // rdx
  unsigned int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // rcx
  u_long *v15; // rcx
  u_long v16; // eax
  int v17; // r9d
  __int64 v18; // r8
  _BYTE *v19; // rbx
  unsigned int v20; // eax
  __int64 v21; // rcx
  int v22; // r8d
  int v23; // r9d
  const wchar_t *v24; // r8
  int v25; // r8d
  int v26; // r9d
  int v27; // r8d
  int v28; // r9d
  int v29; // eax
  unsigned int v30; // eax
  void *v32; // [rsp+80h] [rbp+40h] BYREF
  void *v33; // [rsp+88h] [rbp+48h] BYREF
  PCWSTR SourceString; // [rsp+90h] [rbp+50h] BYREF

  v4 = 0;
  v5 = 0;
  v6 = 0;
  v32 = 0;
  v7 = 0;
  v33 = 0;
  v8 = 0;
  SourceString = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, a1);
    v10 = WPP_GLOBAL_Control;
  }
  v11 = (void *)*((_QWORD *)a1 + 11);
  if ( !v11 )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
      WPP_SF_sd(v10[2], 133, a3, a4, 62);
    v12 = 11;
    goto LABEL_67;
  }
  v13 = KpsDerUnpack(0x28u, v11, *((_DWORD *)a1 + 24), &v32);
  v12 = v13;
  if ( v13 )
  {
    if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 2) != 0 )
      McTemplateU0zq_EventWriteTransfer(v14, Asn1UnpackFailure, L"KDC_PROXY_MESSAGE_PDU", v13);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        134,
        (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
        v12,
        (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
        77);
    v4 = (unsigned int *)v32;
    goto LABEL_67;
  }
  v4 = (unsigned int *)v32;
  v15 = (u_long *)*((_QWORD *)v32 + 2);
  if ( !v15 || *((_DWORD *)v32 + 2) < 5u )
  {
    v12 = 11;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        135,
        (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
        11,
        (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
        85);
    goto LABEL_67;
  }
  v16 = ntohl(*v15);
  v18 = v4[2];
  if ( v16 + 4LL != v18 )
  {
    v12 = 11;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DDDsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, v18, v17, v16, v18);
    goto LABEL_67;
  }
  v19 = (_BYTE *)(*((_QWORD *)v4 + 2) + 4LL);
  if ( *v19 == 106 )
  {
    v6 = 78;
    v7 = 1;
  }
  else
  {
    if ( *v19 != 108 )
    {
      if ( KpsValidateKpasswdMessage((unsigned __int8 *)(*((_QWORD *)v4 + 2) + 4LL), v16) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, v25, v26, 126);
        goto LABEL_42;
      }
      v7 = 3;
      LODWORD(v32) = 3;
      KpsPerfUpdate(3u);
      v5 = v19;
      goto LABEL_44;
    }
    v6 = 79;
    v7 = 2;
  }
  LODWORD(v32) = v7;
  v20 = KpsDerUnpack(v6, v19, v16, &v33);
  v12 = v20;
  if ( v20 )
  {
    if ( v6 == 78 )
    {
      if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 2) == 0 )
        goto LABEL_33;
      v24 = L"KERB_AS_REQUEST_PDU";
    }
    else
    {
      if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 2) == 0 )
        goto LABEL_33;
      v24 = L"KERB_TGS_REQUEST_PDU";
    }
    McTemplateU0zq_EventWriteTransfer(v21, Asn1UnpackFailure, v24, v20);
LABEL_33:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        138,
        (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
        v12,
        (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
        164);
    v5 = v33;
    goto LABEL_67;
  }
  v5 = v33;
LABEL_44:
  if ( *(char *)v4 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, v22, v23, 171);
LABEL_42:
    v12 = 11;
    goto LABEL_67;
  }
  v12 = KpsUtf8String2UnicodeString(*((LPCCH *)v4 + 3), (unsigned __int16 **)&SourceString);
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        140,
        (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
        v12,
        (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
        183);
    v8 = (WCHAR *)SourceString;
  }
  else
  {
    v8 = (WCHAR *)SourceString;
    if ( !SourceString )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, v27, v28, 189);
      goto LABEL_42;
    }
    if ( (*(_BYTE *)v4 & 0x40) != 0 )
      *((_DWORD *)a1 + 32) = v4[8];
    *((_QWORD *)a1 + 13) = v4;
    v4 = 0;
    RtlInitUnicodeString((PUNICODE_STRING)a1 + 7, v8);
    v29 = (int)v32;
    *((_QWORD *)a1 + 17) = v5;
    v8 = 0;
    *((_DWORD *)a1 + 33) = v29;
    v5 = 0;
    v30 = KpsCheckKerbRequest(a1);
    v12 = v30;
    if ( v30 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v30);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_dZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        143,
        (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
        *((_DWORD *)a1 + 33),
        (__int64)a1 + 112);
    }
    v7 = (int)v32;
  }
LABEL_67:
  KpsFreeMem(v8);
  if ( v5 && (unsigned int)(v7 - 1) <= 1 )
    KpsDerFree(v6, v5);
  if ( v4 )
    KpsDerFree(0x28u, v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x18002aae8  mov     [rsp-38h+arg_18], rbx
0x18002aaed  push    rbp
0x18002aaee  push    rsi
0x18002aaef  push    rdi
0x18002aaf0  push    r12
0x18002aaf2  push    r13
0x18002aaf4  push    r14
0x18002aaf6  push    r15
0x18002aaf8  mov     rbp, rsp
0x18002aafb  sub     rsp, 40h
0x18002aaff  xor     edi, edi
0x18002ab01  xor     r14d, r14d
0x18002ab04  xor     r12d, r12d
0x18002ab07  mov     [rbp+arg_0], rdi
0x18002ab0b  xor     r15d, r15d
0x18002ab0e  mov     [rbp+arg_8], r14
0x18002ab12  xor     r13d, r13d
0x18002ab15  mov     rsi, rcx
0x18002ab18  mov     [rbp+SourceString], r13
0x18002ab1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab23  lea     rax, WPP_GLOBAL_Control
0x18002ab2a  cmp     rcx, rax
0x18002ab2d  jz      short loc_18002AB5B
0x18002ab2f  test    byte ptr [rcx+1Ch], 20h
0x18002ab33  jz      short loc_18002AB5B
0x18002ab35  mov     rcx, [rcx+10h]
0x18002ab39  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002ab40  mov     edx, 84h
0x18002ab45  mov     r9, rsi
0x18002ab48  call    WPP_SF_q
0x18002ab4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab54  lea     rax, WPP_GLOBAL_Control
0x18002ab5b  mov     rdx, [rsi+58h]; void *
0x18002ab5f  test    rdx, rdx
0x18002ab62  jnz     short loc_18002AB96
0x18002ab64  cmp     rcx, rax
0x18002ab67  jz      short loc_18002AB85
0x18002ab69  test    byte ptr [rcx+1Ch], 1
0x18002ab6d  jz      short loc_18002AB85
0x18002ab6f  mov     rcx, [rcx+10h]
0x18002ab73  mov     edx, 85h
0x18002ab78  mov     dword ptr [rsp+40h+var_20], 93Eh
0x18002ab80  call    WPP_SF_sd
0x18002ab85  mov     ebx, 0Bh
0x18002ab8a  lea     rsi, WPP_GLOBAL_Control
0x18002ab91  jmp     loc_18002AF66
0x18002ab96  mov     r8d, [rsi+60h]; unsigned int
0x18002ab9a  lea     r9, [rbp+arg_0]; void **
0x18002ab9e  mov     ecx, 28h ; '('; unsigned int
0x18002aba3  call    ?KpsDerUnpack@@YAKKPEAXKPEAPEAX@Z; KpsDerUnpack(ulong,void *,ulong,void * *)
0x18002aba8  mov     ebx, eax
0x18002abaa  test    eax, eax
0x18002abac  jz      short loc_18002AC1B
0x18002abae  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 2
0x18002abb5  jz      short loc_18002ABCD
0x18002abb7  mov     r9d, eax
0x18002abba  lea     r8, aKdcProxyMessag; "KDC_PROXY_MESSAGE_PDU"
0x18002abc1  lea     rdx, Asn1UnpackFailure
0x18002abc8  call    McTemplateU0zq_EventWriteTransfer
0x18002abcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002abd4  lea     rsi, WPP_GLOBAL_Control
0x18002abdb  cmp     rcx, rsi
0x18002abde  jz      short loc_18002AC12
0x18002abe0  test    byte ptr [rcx+1Ch], 1
0x18002abe4  jz      short loc_18002AC12
0x18002abe6  mov     rcx, [rcx+10h]
0x18002abea  lea     rax, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002abf1  mov     edx, 86h
0x18002abf6  mov     [rsp+40h+var_18], 94Dh
0x18002abfe  mov     r9d, ebx
0x18002ac01  mov     [rsp+40h+var_20], rax
0x18002ac06  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002ac0d  call    WPP_SF_Dsd
0x18002ac12  mov     rdi, [rbp+arg_0]
0x18002ac16  jmp     loc_18002AF66
0x18002ac1b  mov     rdi, [rbp+arg_0]
0x18002ac1f  mov     rcx, [rdi+10h]
0x18002ac23  test    rcx, rcx
0x18002ac26  jz      loc_18002AFDE
0x18002ac2c  cmp     dword ptr [rdi+8], 5
0x18002ac30  jb      loc_18002AFDE
0x18002ac36  mov     ecx, [rcx]; netlong
0x18002ac38  call    cs:__imp_ntohl
0x18002ac3f  nop     dword ptr [rax+rax+00h]
0x18002ac44  mov     r8d, [rdi+8]
0x18002ac48  mov     ecx, eax
0x18002ac4a  add     rcx, 4
0x18002ac4e  cmp     rcx, r8
0x18002ac51  jz      short loc_18002AC9B
0x18002ac53  mov     ebx, 0Bh
0x18002ac58  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac5f  lea     rsi, WPP_GLOBAL_Control
0x18002ac66  cmp     rcx, rsi
0x18002ac69  jz      loc_18002AF66
0x18002ac6f  test    byte ptr [rcx+1Ch], 1
0x18002ac73  jz      loc_18002AF66
0x18002ac79  mov     rcx, [rcx+10h]
0x18002ac7d  lea     edx, [rbx+7Dh]
0x18002ac80  mov     [rsp+40h+var_8], 965h
0x18002ac88  mov     [rsp+40h+var_18], r8d
0x18002ac8d  mov     dword ptr [rsp+40h+var_20], eax
0x18002ac91  call    WPP_SF_DDDsd
0x18002ac96  jmp     loc_18002AF66
0x18002ac9b  mov     rbx, [rdi+10h]
0x18002ac9f  add     rbx, 4
0x18002aca3  cmp     byte ptr [rbx], 6Ah ; 'j'
0x18002aca6  jnz     short loc_18002ACB5
0x18002aca8  mov     r12d, 4Eh ; 'N'
0x18002acae  lea     r15d, [r12-4Dh]
0x18002acb3  jmp     short loc_18002ACC9
0x18002acb5  cmp     byte ptr [rbx], 6Ch ; 'l'
0x18002acb8  jnz     loc_18002AD7A
0x18002acbe  mov     r12d, 4Fh ; 'O'
0x18002acc4  lea     r15d, [r12-4Dh]
0x18002acc9  lea     r9, [rbp+arg_8]; void **
0x18002accd  mov     dword ptr [rbp+arg_0], r15d
0x18002acd1  mov     r8d, eax; unsigned int
0x18002acd4  mov     rdx, rbx; void *
0x18002acd7  mov     ecx, r12d; unsigned int
0x18002acda  call    ?KpsDerUnpack@@YAKKPEAXKPEAPEAX@Z; KpsDerUnpack(ulong,void *,ulong,void * *)
0x18002acdf  mov     ebx, eax
0x18002ace1  test    eax, eax
0x18002ace3  jz      loc_18002AD74
0x18002ace9  cmp     r12d, 4Eh ; 'N'
0x18002aced  jnz     short loc_18002AD01
0x18002acef  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 2
0x18002acf6  jz      short loc_18002AD26
0x18002acf8  lea     r8, aKerbAsRequestP; "KERB_AS_REQUEST_PDU"
0x18002acff  jmp     short loc_18002AD17
0x18002ad01  cmp     r12d, 4Fh ; 'O'
0x18002ad05  jnz     short loc_18002AD26
0x18002ad07  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 2
0x18002ad0e  jz      short loc_18002AD26
0x18002ad10  lea     r8, aKerbTgsRequest; "KERB_TGS_REQUEST_PDU"
0x18002ad17  mov     r9d, ebx
0x18002ad1a  lea     rdx, Asn1UnpackFailure
0x18002ad21  call    McTemplateU0zq_EventWriteTransfer
0x18002ad26  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad2d  lea     rsi, WPP_GLOBAL_Control
0x18002ad34  cmp     rcx, rsi
0x18002ad37  jz      short loc_18002AD6B
0x18002ad39  test    byte ptr [rcx+1Ch], 1
0x18002ad3d  jz      short loc_18002AD6B
0x18002ad3f  mov     rcx, [rcx+10h]
0x18002ad43  lea     rax, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002ad4a  mov     edx, 8Ah
0x18002ad4f  mov     [rsp+40h+var_18], 9A4h
0x18002ad57  mov     r9d, ebx
0x18002ad5a  mov     [rsp+40h+var_20], rax
0x18002ad5f  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002ad66  call    WPP_SF_Dsd
0x18002ad6b  mov     r14, [rbp+arg_8]
0x18002ad6f  jmp     loc_18002AF66
0x18002ad74  mov     r14, [rbp+arg_8]
0x18002ad78  jmp     short loc_18002ADD6
0x18002ad7a  mov     edx, eax; unsigned int
0x18002ad7c  mov     rcx, rbx; unsigned __int8 *
0x18002ad7f  call    ?KpsValidateKpasswdMessage@@YAKPEAEK@Z; KpsValidateKpasswdMessage(uchar *,ulong)
0x18002ad84  test    eax, eax
0x18002ad86  jz      short loc_18002ADC1
0x18002ad88  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad8f  lea     rsi, WPP_GLOBAL_Control
0x18002ad96  cmp     rcx, rsi
0x18002ad99  jz      short loc_18002ADB7
0x18002ad9b  test    byte ptr [rcx+1Ch], 1
0x18002ad9f  jz      short loc_18002ADB7
0x18002ada1  mov     edx, 89h
0x18002ada6  mov     dword ptr [rsp+40h+var_20], 97Eh
0x18002adae  mov     rcx, [rcx+10h]
0x18002adb2  call    WPP_SF_sd
0x18002adb7  mov     ebx, 0Bh
0x18002adbc  jmp     loc_18002AF66
0x18002adc1  mov     r15d, 3
0x18002adc7  mov     ecx, r15d; unsigned int
0x18002adca  mov     dword ptr [rbp+arg_0], r15d
0x18002adce  call    ?KpsPerfUpdate@@YAXK@Z; KpsPerfUpdate(ulong)
0x18002add3  mov     r14, rbx
0x18002add6  test    byte ptr [rdi], 80h
0x18002add9  jnz     short loc_18002AE03
0x18002addb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ade2  lea     rsi, WPP_GLOBAL_Control
0x18002ade9  cmp     rcx, rsi
0x18002adec  jz      short loc_18002ADB7
0x18002adee  test    byte ptr [rcx+1Ch], 1
0x18002adf2  jz      short loc_18002ADB7
0x18002adf4  mov     edx, 8Bh
0x18002adf9  mov     dword ptr [rsp+40h+var_20], 9ABh
0x18002ae01  jmp     short loc_18002ADAE
0x18002ae03  mov     rcx, [rdi+18h]; lpMultiByteStr
0x18002ae07  lea     rdx, [rbp+SourceString]; unsigned __int16 **
0x18002ae0b  call    ?KpsUtf8String2UnicodeString@@YAKPEADPEAPEAG@Z; KpsUtf8String2UnicodeString(char *,ushort * *)
0x18002ae10  mov     ebx, eax
0x18002ae12  test    eax, eax
0x18002ae14  jz      short loc_18002AE64
0x18002ae16  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae1d  lea     rsi, WPP_GLOBAL_Control
0x18002ae24  cmp     rcx, rsi
0x18002ae27  jz      short loc_18002AE5B
0x18002ae29  test    byte ptr [rcx+1Ch], 1
0x18002ae2d  jz      short loc_18002AE5B
0x18002ae2f  mov     rcx, [rcx+10h]
0x18002ae33  lea     rax, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002ae3a  mov     edx, 8Ch
0x18002ae3f  mov     [rsp+40h+var_18], 9B7h
0x18002ae47  mov     r9d, ebx
0x18002ae4a  mov     [rsp+40h+var_20], rax
0x18002ae4f  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002ae56  call    WPP_SF_Dsd
0x18002ae5b  mov     r13, [rbp+SourceString]
0x18002ae5f  jmp     loc_18002AF66
0x18002ae64  mov     r13, [rbp+SourceString]
0x18002ae68  test    r13, r13
0x18002ae6b  jnz     short loc_18002AEA0
0x18002ae6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae74  lea     rsi, WPP_GLOBAL_Control
0x18002ae7b  cmp     rcx, rsi
0x18002ae7e  jz      loc_18002ADB7
0x18002ae84  test    byte ptr [rcx+1Ch], 1
0x18002ae88  jz      loc_18002ADB7
0x18002ae8e  mov     edx, 8Dh
0x18002ae93  mov     dword ptr [rsp+40h+var_20], 9BDh
0x18002ae9b  jmp     loc_18002ADAE
0x18002aea0  test    byte ptr [rdi], 40h
0x18002aea3  jz      short loc_18002AEAE
0x18002aea5  mov     eax, [rdi+20h]
0x18002aea8  mov     [rsi+80h], eax
0x18002aeae  mov     [rsi+68h], rdi
0x18002aeb2  lea     r15, [rsi+70h]
0x18002aeb6  mov     rcx, r15; DestinationString
0x18002aeb9  mov     rdx, r13; SourceString
0x18002aebc  xor     edi, edi
0x18002aebe  call    cs:__imp_RtlInitUnicodeString
0x18002aec5  nop     dword ptr [rax+rax+00h]
0x18002aeca  mov     eax, dword ptr [rbp+arg_0]
0x18002aecd  mov     rcx, rsi; struct _KPS_IO *
0x18002aed0  mov     [rsi+88h], r14
0x18002aed7  xor     r13d, r13d
0x18002aeda  mov     [rsi+84h], eax
0x18002aee0  xor     r14d, r14d
0x18002aee3  call    ?KpsCheckKerbRequest@@YAKPEAU_KPS_IO@@@Z; KpsCheckKerbRequest(_KPS_IO *)
0x18002aee8  mov     ebx, eax
0x18002aeea  test    eax, eax
0x18002aeec  jz      short loc_18002AF21
0x18002aeee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aef5  lea     rsi, WPP_GLOBAL_Control
0x18002aefc  cmp     rcx, rsi
0x18002aeff  jz      short loc_18002AF62
0x18002af01  test    byte ptr [rcx+1Ch], 1
0x18002af05  jz      short loc_18002AF62
0x18002af07  mov     rcx, [rcx+10h]
0x18002af0b  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002af12  mov     edx, 8Eh
0x18002af17  mov     r9d, eax
0x18002af1a  call    WPP_SF_D
0x18002af1f  jmp     short loc_18002AF62
0x18002af21  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af28  lea     rax, WPP_GLOBAL_Control
0x18002af2f  cmp     rcx, rax
0x18002af32  jz      short loc_18002AF5B
0x18002af34  test    byte ptr [rcx+1Ch], 4
0x18002af38  jz      short loc_18002AF5B
0x18002af3a  mov     r9d, [rsi+84h]
0x18002af41  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002af48  mov     rcx, [rcx+10h]
0x18002af4c  mov     edx, 8Fh
0x18002af51  mov     [rsp+40h+var_20], r15
0x18002af56  call    WPP_SF_dZ
0x18002af5b  lea     rsi, WPP_GLOBAL_Control
0x18002af62  mov     r15d, dword ptr [rbp+arg_0]
0x18002af66  mov     rcx, r13; lpMem
0x18002af69  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x18002af6e  test    r14, r14
0x18002af71  jz      short loc_18002AF87
0x18002af73  lea     eax, [r15-1]
0x18002af77  cmp     eax, 1
0x18002af7a  ja      short loc_18002AF87
0x18002af7c  mov     rdx, r14; void *
0x18002af7f  mov     ecx, r12d; unsigned int
0x18002af82  call    ?KpsDerFree@@YAXKPEAX@Z; KpsDerFree(ulong,void *)
0x18002af87  test    rdi, rdi
0x18002af8a  jz      short loc_18002AF99
0x18002af8c  mov     rdx, rdi; void *
0x18002af8f  mov     ecx, 28h ; '('; unsigned int
0x18002af94  call    ?KpsDerFree@@YAXKPEAX@Z; KpsDerFree(ulong,void *)
0x18002af99  mov     rcx, cs:WPP_GLOBAL_Control
0x18002afa0  cmp     rcx, rsi
0x18002afa3  jz      short loc_18002AFC3
0x18002afa5  test    byte ptr [rcx+1Ch], 20h
0x18002afa9  jz      short loc_18002AFC3
0x18002afab  mov     rcx, [rcx+10h]
0x18002afaf  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002afb6  mov     edx, 90h
0x18002afbb  mov     r9d, ebx
0x18002afbe  call    WPP_SF_D
0x18002afc3  mov     eax, ebx
0x18002afc5  mov     rbx, [rsp+40h+arg_18]
0x18002afcd  add     rsp, 40h
0x18002afd1  pop     r15
0x18002afd3  pop     r14
0x18002afd5  pop     r13
  ... truncated ...
```
