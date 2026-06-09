# DDMTransportCreate

- ea: `0x18000bcc0`
- end: `0x18000c0a8`
- name: `DDMTransportCreate`
- size: `1000`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180007c0c`
- `0x18000bcc0`
- `0x18000c638`
- `0x180018d8c`
- `0x180052b74`
- `0x180057830`
- `0x180057bf4`
- `0x180058bd4`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `ADVAPI32!RegOpenKeyW` at `0x18000bdb6`
- `ADVAPI32!RegOpenKeyW` at `0x18000bdb6`
- `ADVAPI32!RegCloseKey` at `0x18000be05`
- `ADVAPI32!RegCloseKey` at `0x18000be16`
- `ADVAPI32!RegCloseKey` at `0x18000be05`
- `ADVAPI32!RegCloseKey` at `0x18000be16`
- `rtutils!RouterLogEventStringW` at `0x18000bee5`
- `rtutils!RouterLogEventStringW` at `0x18000c011`
- `rtutils!RouterLogEventStringW` at `0x18000bee5`
- `rtutils!RouterLogEventStringW` at `0x18000c011`

## string_xrefs

- `0x18000bf7d`: `RasIpv6SrvrStart completes with return code %d`
- `0x18000bd3a`: `DDMTransportCreate called for Transport Id = %d`
- `0x18000bdaf`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`

## pseudocode

```c
LSTATUS __fastcall DDMTransportCreate(unsigned int a1)
{
  __int64 v2; // rsi
  __int64 v3; // r8
  __int64 v4; // rax
  LSTATUS result; // eax
  int v6; // r8d
  int v7; // r9d
  DWORD dwErrorCode; // ebx
  unsigned int v9; // eax
  _QWORD *v10; // rdx
  unsigned int v11; // ecx
  __int64 *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // esi
  int *v17; // rdi
  __int64 v18; // [rsp+48h] [rbp-C0h] BYREF
  HKEY phkResult[3]; // [rsp+50h] [rbp-B8h] BYREF
  int *v20; // [rsp+68h] [rbp-A0h]
  int v21; // [rsp+70h] [rbp-98h]
  int v22; // [rsp+74h] [rbp-94h]
  int v23; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v24[2044]; // [rsp+7Ch] [rbp-8Ch] BYREF

  LODWORD(v18) = 0;
  phkResult[0] = 0;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v2 = -1;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"DDMTransportCreate called for Transport Id = %d", a1);
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v4 = -1;
      do
        ++v4;
      while ( *(_WORD *)&v24[2 * v4 - 4] );
      v22 = 0;
      v21 = 2 * v4 + 2;
      v20 = &v23;
      McGenEventWrite_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasDdmTraceInfo,
        v3,
        2,
        &phkResult[1]);
    }
  }
  result = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters", phkResult);
  if ( !result )
  {
    if ( (dword_1800CF64C & 4) != 0 || (v7 = 0, (dword_1800CF64C & 0x20) != 0) )
      v7 = 1;
    dwErrorCode = lProtocolEnabled(phkResult[0], a1, v6, v7, (__int64)&v18);
    if ( dwErrorCode )
    {
      RegCloseKey(phkResult[0]);
      return dwErrorCode;
    }
    RegCloseKey(phkResult[0]);
    if ( !(_DWORD)v18 )
      return 0;
    if ( a1 != 33 )
    {
      if ( a1 == 87 )
      {
        if ( !dword_1800CF51C )
        {
          v11 = 0;
          if ( dword_1800CF568 )
          {
            v12 = (__int64 *)((char *)qword_1800CF560 + 40);
            while ( !*(v12 - 1) || !*v12 )
            {
              ++v11;
              v12 += 21;
              if ( v11 >= dword_1800CF568 )
                goto LABEL_36;
            }
            v13 = *((unsigned __int8 *)v12 - 32);
            v14 = *v12;
            v15 = *(v12 - 1);
          }
          else
          {
LABEL_36:
            v13 = 0;
            v14 = 0;
            v15 = 0;
          }
          dwErrorCode = RasSrvrIpv6Initialize(v15, v14, v13);
          if ( !dwErrorCode )
          {
            *(GUID *)&phkResult[1] = GUID_NULL;
            dwErrorCode = RasIpv6SrvrStart((struct _GUID *)&phkResult[1]);
          }
          if ( (byte_1800CF404 & 0x10) != 0 )
          {
            LOWORD(v23) = 0;
            FormatRRASErrorString(&v23, L"RasIpv6SrvrStart completes with return code %d", dwErrorCode);
            if ( (byte_1800CF404 & 0x10) != 0 )
            {
              do
                ++v2;
              while ( *(_WORD *)&v24[2 * v2 - 4] );
              v22 = 0;
              v21 = 2 * v2 + 2;
              v20 = &v23;
              McGenEventWrite_EventWriteTransfer(
                &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                RasDdmTraceInfo,
                &v23,
                2,
                &phkResult[1]);
            }
          }
          if ( dwErrorCode )
          {
            if ( dword_1800CF4E4 )
              RouterLogEventStringW(hLogHandle, 1u, 0x4EB1u, 0, 0, dwErrorCode, 0);
          }
          else
          {
            dword_1800CF51C = 1;
          }
        }
        dword_1800CF4EC |= 0x8000000u;
      }
      goto LABEL_49;
    }
    if ( dword_1800CF518 )
    {
LABEL_28:
      dword_1800CF4EC |= 8u;
LABEL_49:
      v16 = 0;
      v17 = &dword_1800CE49C;
      do
      {
        if ( !*(v17 - 1) )
        {
          if ( *v17 )
            ProtocolDdmChangeNotification((unsigned int)dword_1800CF4EC, (unsigned int)dword_1800CF4E4, v16);
        }
        ++v16;
        v17 += 20;
      }
      while ( v16 < 3 );
      return dwErrorCode;
    }
    v9 = 0;
    if ( dword_1800CF568 )
    {
      v10 = qword_1800CF560;
      while ( !v10[2] )
      {
        ++v9;
        v10 += 21;
        if ( v9 >= dword_1800CF568 )
          goto LABEL_20;
      }
      dwErrorCode = RasSrvrIpv4Initialize(v10[2], v10[3], *((unsigned __int8 *)v10 + 8));
      if ( dwErrorCode )
      {
LABEL_22:
        if ( !dwErrorCode )
        {
          dword_1800CF518 = 1;
          goto LABEL_28;
        }
LABEL_26:
        if ( dword_1800CF4E4 )
          RouterLogEventStringW(hLogHandle, 1u, 0x4EB1u, 0, 0, dwErrorCode, 0);
        goto LABEL_28;
      }
    }
    else
    {
LABEL_20:
      dwErrorCode = RasSrvrIpv4Initialize(0, 0, 0);
      if ( dwErrorCode )
        goto LABEL_26;
    }
    *(GUID *)&phkResult[1] = GUID_NULL;
    dwErrorCode = RasSrvrStart(&phkResult[1]);
    goto LABEL_22;
  }
  return result;
}

```

## disassembly

```asm
0x18000bcc0  mov     rax, rsp
0x18000bcc3  mov     [rax+10h], rbx
0x18000bcc7  mov     [rax+18h], rsi
0x18000bccb  mov     [rax+20h], rdi
0x18000bccf  push    rbp
0x18000bcd0  push    r14
0x18000bcd2  push    r15
0x18000bcd4  lea     rbp, [rax-7A8h]
0x18000bcdb  sub     rsp, 890h
0x18000bce2  movaps  xmmword ptr [rax-28h], xmm6
0x18000bce6  mov     rax, cs:__security_cookie
0x18000bced  xor     rax, rsp
0x18000bcf0  mov     [rbp+7A0h+var_30], rax
0x18000bcf7  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18000bcfe  xor     r14d, r14d
0x18000bd01  mov     edi, ecx
0x18000bd03  lea     rcx, [rsp+8A0h+var_82C]; void *
0x18000bd08  mov     dword ptr [rsp+8A0h+var_860], r14d
0x18000bd0d  xor     edx, edx; Val
0x18000bd0f  mov     qword ptr [rsp+8A0h+phkResult], r14
0x18000bd14  mov     r8d, 7FCh; Size
0x18000bd1a  mov     [rsp+8A0h+var_830], r14d
0x18000bd1f  call    memset_0
0x18000bd24  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000bd28  test    cs:byte_1800CF404, 10h
0x18000bd2f  jz      short loc_18000BDA3
0x18000bd31  mov     r8d, edi
0x18000bd34  mov     word ptr [rsp+8A0h+var_830], r14w
0x18000bd3a  lea     rdx, aDdmtransportcr_0; "DDMTransportCreate called for Transport"...
0x18000bd41  lea     rcx, [rsp+8A0h+var_830]
0x18000bd46  call    FormatRRASErrorString
0x18000bd4b  test    cs:byte_1800CF404, 10h
0x18000bd52  jz      short loc_18000BDA3
0x18000bd54  lea     rcx, [rsp+8A0h+var_830]
0x18000bd59  mov     rax, rsi
0x18000bd5c  inc     rax
0x18000bd5f  cmp     [rcx+rax*2], r14w
0x18000bd64  jnz     short loc_18000BD5C
0x18000bd66  lea     eax, ds:2[rax*2]
0x18000bd6d  mov     [rsp+8A0h+var_834], r14d
0x18000bd72  lea     rcx, [rsp+8A0h+var_830]
0x18000bd77  mov     [rsp+8A0h+var_838], eax
0x18000bd7b  lea     rax, [rsp+8A0h+phkResult+8]
0x18000bd80  mov     [rsp+8A0h+var_840], rcx
0x18000bd85  mov     r9d, 2
0x18000bd8b  mov     [rsp+8A0h+plpszSubStringArray], rax
0x18000bd90  lea     rdx, RasDdmTraceInfo
0x18000bd97  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bd9e  call    McGenEventWrite_EventWriteTransfer
0x18000bda3  lea     r8, [rsp+8A0h+phkResult]; phkResult
0x18000bda8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bdaf  lea     rdx, aSystemCurrentc_12; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18000bdb6  call    cs:__imp_RegOpenKeyW
0x18000bdbd  nop     dword ptr [rax+rax+00h]
0x18000bdc2  test    eax, eax
0x18000bdc4  jnz     loc_18000C076
0x18000bdca  mov     eax, cs:dword_1800CF64C
0x18000bdd0  mov     r15d, 1
0x18000bdd6  test    al, 4
0x18000bdd8  jnz     short loc_18000BDE1
0x18000bdda  mov     r9d, r14d
0x18000bddd  test    al, 20h
0x18000bddf  jz      short loc_18000BDE4
0x18000bde1  mov     r9d, r15d
0x18000bde4  mov     rcx, qword ptr [rsp+8A0h+phkResult]
0x18000bde9  lea     rax, [rsp+8A0h+var_860]
0x18000bdee  mov     edx, edi
0x18000bdf0  mov     [rsp+8A0h+plpszSubStringArray], rax
0x18000bdf5  call    lProtocolEnabled
0x18000bdfa  mov     rcx, qword ptr [rsp+8A0h+phkResult]; hKey
0x18000bdff  mov     ebx, eax
0x18000be01  test    eax, eax
0x18000be03  jz      short loc_18000BE16
0x18000be05  call    cs:__imp_RegCloseKey
0x18000be0c  nop     dword ptr [rax+rax+00h]
0x18000be11  jmp     loc_18000C074
0x18000be16  call    cs:__imp_RegCloseKey
0x18000be1d  nop     dword ptr [rax+rax+00h]
0x18000be22  cmp     dword ptr [rsp+8A0h+var_860], r14d
0x18000be27  jnz     short loc_18000BE30
0x18000be29  xor     eax, eax
0x18000be2b  jmp     loc_18000C076
0x18000be30  cmp     edi, 21h ; '!'
0x18000be33  jnz     loc_18000BEFD
0x18000be39  cmp     cs:dword_1800CF518, r14d
0x18000be40  jnz     loc_18000BEF1
0x18000be46  mov     ecx, cs:dword_1800CF568
0x18000be4c  mov     eax, r14d
0x18000be4f  test    ecx, ecx
0x18000be51  jz      short loc_18000BE71
0x18000be53  mov     rdx, cs:qword_1800CF560
0x18000be5a  mov     r9, [rdx+10h]
0x18000be5e  test    r9, r9
0x18000be61  jnz     short loc_18000BEA2
0x18000be63  add     eax, r15d
0x18000be66  add     rdx, 0A8h
0x18000be6d  cmp     eax, ecx
0x18000be6f  jb      short loc_18000BE5A
0x18000be71  xor     r8d, r8d
0x18000be74  xor     edx, edx
0x18000be76  xor     ecx, ecx
0x18000be78  call    RasSrvrIpv4Initialize
0x18000be7d  mov     ebx, eax
0x18000be7f  test    eax, eax
0x18000be81  jnz     short loc_18000BEBB
0x18000be83  lea     rcx, [rsp+8A0h+phkResult+8]
0x18000be88  movdqa  xmmword ptr [rsp+8A0h+phkResult+8], xmm6
0x18000be8e  call    RasSrvrStart
0x18000be93  mov     ebx, eax
0x18000be95  test    ebx, ebx
0x18000be97  jnz     short loc_18000BEBB
0x18000be99  mov     cs:dword_1800CF518, r15d
0x18000bea0  jmp     short loc_18000BEF1
0x18000bea2  movzx   r8d, byte ptr [rdx+8]
0x18000bea7  mov     rcx, r9
0x18000beaa  mov     rdx, [rdx+18h]
0x18000beae  call    RasSrvrIpv4Initialize
0x18000beb3  mov     ebx, eax
0x18000beb5  test    eax, eax
0x18000beb7  jnz     short loc_18000BE95
0x18000beb9  jmp     short loc_18000BE83
0x18000bebb  cmp     cs:dword_1800CF4E4, r14d
0x18000bec2  jbe     short loc_18000BEF1
0x18000bec4  mov     rcx, cs:hLogHandle; hLogHandle
0x18000becb  xor     r9d, r9d; dwSubStringCount
0x18000bece  mov     [rsp+8A0h+dwErrorIndex], r14d; dwErrorIndex
0x18000bed3  mov     r8d, 4EB1h; dwMessageId
0x18000bed9  mov     [rsp+8A0h+dwErrorCode], ebx; dwErrorCode
0x18000bedd  mov     edx, r15d; dwEventType
0x18000bee0  mov     [rsp+8A0h+plpszSubStringArray], r14; plpszSubStringArray
0x18000bee5  call    cs:__imp_RouterLogEventStringW
0x18000beec  nop     dword ptr [rax+rax+00h]
0x18000bef1  or      cs:dword_1800CF4EC, 8
0x18000bef8  jmp     loc_18000C03F
0x18000befd  cmp     edi, 57h ; 'W'
0x18000bf00  jnz     loc_18000C03F
0x18000bf06  cmp     cs:dword_1800CF51C, r14d
0x18000bf0d  jnz     loc_18000C037
0x18000bf13  mov     edx, cs:dword_1800CF568
0x18000bf19  mov     ecx, r14d
0x18000bf1c  test    edx, edx
0x18000bf1e  jz      short loc_18000BF47
0x18000bf20  mov     rax, cs:qword_1800CF560
0x18000bf27  add     rax, 28h ; '('
0x18000bf2b  cmp     [rax-8], r14
0x18000bf2f  jz      short loc_18000BF3A
0x18000bf31  cmp     [rax], r14
0x18000bf34  jnz     loc_18000C01F
0x18000bf3a  add     ecx, r15d
0x18000bf3d  add     rax, 0A8h
0x18000bf43  cmp     ecx, edx
0x18000bf45  jb      short loc_18000BF2B
0x18000bf47  xor     r8d, r8d
0x18000bf4a  xor     edx, edx
0x18000bf4c  xor     ecx, ecx
0x18000bf4e  call    RasSrvrIpv6Initialize
0x18000bf53  mov     ebx, eax
0x18000bf55  test    eax, eax
0x18000bf57  jnz     short loc_18000BF6B
0x18000bf59  lea     rcx, [rsp+8A0h+phkResult+8]; struct _GUID *
0x18000bf5e  movdqa  xmmword ptr [rsp+8A0h+phkResult+8], xmm6
0x18000bf64  call    RasIpv6SrvrStart
0x18000bf69  mov     ebx, eax
0x18000bf6b  test    cs:byte_1800CF404, 10h
0x18000bf72  jz      short loc_18000BFE3
0x18000bf74  mov     r8d, ebx
0x18000bf77  mov     word ptr [rsp+8A0h+var_830], r14w
0x18000bf7d  lea     rdx, aRasipv6srvrsta_0; "RasIpv6SrvrStart completes with return "...
0x18000bf84  lea     rcx, [rsp+8A0h+var_830]
0x18000bf89  call    FormatRRASErrorString
0x18000bf8e  test    cs:byte_1800CF404, 10h
0x18000bf95  jz      short loc_18000BFE3
0x18000bf97  lea     rax, [rsp+8A0h+var_830]
0x18000bf9c  inc     rsi
0x18000bf9f  cmp     [rax+rsi*2], r14w
0x18000bfa4  jnz     short loc_18000BF9C
0x18000bfa6  lea     eax, ds:2[rsi*2]
0x18000bfad  mov     [rsp+8A0h+var_834], r14d
0x18000bfb2  mov     [rsp+8A0h+var_838], eax
0x18000bfb6  lea     r8, [rsp+8A0h+var_830]
0x18000bfbb  lea     rax, [rsp+8A0h+phkResult+8]
0x18000bfc0  mov     [rsp+8A0h+var_840], r8
0x18000bfc5  mov     r9d, 2
0x18000bfcb  mov     [rsp+8A0h+plpszSubStringArray], rax
0x18000bfd0  lea     rdx, RasDdmTraceInfo
0x18000bfd7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bfde  call    McGenEventWrite_EventWriteTransfer
0x18000bfe3  test    ebx, ebx
0x18000bfe5  jz      short loc_18000C030
0x18000bfe7  cmp     cs:dword_1800CF4E4, r14d
0x18000bfee  jbe     short loc_18000C037
0x18000bff0  mov     rcx, cs:hLogHandle; hLogHandle
0x18000bff7  xor     r9d, r9d; dwSubStringCount
0x18000bffa  mov     [rsp+8A0h+dwErrorIndex], r14d; dwErrorIndex
0x18000bfff  mov     r8d, 4EB1h; dwMessageId
0x18000c005  mov     [rsp+8A0h+dwErrorCode], ebx; dwErrorCode
0x18000c009  mov     edx, r15d; dwEventType
0x18000c00c  mov     [rsp+8A0h+plpszSubStringArray], r14; plpszSubStringArray
0x18000c011  call    cs:__imp_RouterLogEventStringW
0x18000c018  nop     dword ptr [rax+rax+00h]
0x18000c01d  jmp     short loc_18000C037
0x18000c01f  movzx   r8d, byte ptr [rax-20h]
0x18000c024  mov     rdx, [rax]
0x18000c027  mov     rcx, [rax-8]
0x18000c02b  jmp     loc_18000BF4E
0x18000c030  mov     cs:dword_1800CF51C, r15d
0x18000c037  bts     cs:dword_1800CF4EC, 1Bh
0x18000c03f  mov     esi, r14d
0x18000c042  lea     rdi, dword_1800CE49C
0x18000c049  cmp     [rdi-4], r14d
0x18000c04d  jnz     short loc_18000C068
0x18000c04f  cmp     [rdi], r14d
0x18000c052  jz      short loc_18000C068
0x18000c054  mov     edx, cs:dword_1800CF4E4
0x18000c05a  mov     r8d, esi
0x18000c05d  mov     ecx, cs:dword_1800CF4EC
0x18000c063  call    ProtocolDdmChangeNotification
0x18000c068  add     esi, r15d
0x18000c06b  add     rdi, 50h ; 'P'
0x18000c06f  cmp     esi, 3
0x18000c072  jb      short loc_18000C049
0x18000c074  mov     eax, ebx
0x18000c076  mov     rcx, [rbp+7A0h+var_30]
0x18000c07d  xor     rcx, rsp; StackCookie
0x18000c080  call    __security_check_cookie
0x18000c085  lea     r11, [rsp+8A0h+var_10]
0x18000c08d  mov     rbx, [r11+28h]
0x18000c091  mov     rsi, [r11+30h]
0x18000c095  mov     rdi, [r11+38h]
0x18000c099  movaps  xmm6, xmmword ptr [r11-10h]
0x18000c09e  mov     rsp, r11
0x18000c0a1  pop     r15
0x18000c0a3  pop     r14
0x18000c0a5  pop     rbp
0x18000c0a6  retn
```
