# DDMTransportCreate

- ea: `0x18000b9f0`
- end: `0x18000bdc1`
- name: `DDMTransportCreate`
- size: `977`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180007b7c`
- `0x18000b9f0`
- `0x18000c320`
- `0x18001846c`
- `0x1800511bc`
- `0x180055a2c`
- `0x180055d98`
- `0x180056d88`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `ADVAPI32!RegOpenKeyW` at `0x18000badd`
- `ADVAPI32!RegOpenKeyW` at `0x18000badd`
- `ADVAPI32!RegCloseKey` at `0x18000bb26`
- `ADVAPI32!RegCloseKey` at `0x18000bb31`
- `ADVAPI32!RegCloseKey` at `0x18000bb26`
- `ADVAPI32!RegCloseKey` at `0x18000bb31`
- `rtutils!RouterLogEventStringW` at `0x18000bc02`
- `rtutils!RouterLogEventStringW` at `0x18000bd33`
- `rtutils!RouterLogEventStringW` at `0x18000bc02`
- `rtutils!RouterLogEventStringW` at `0x18000bd33`

## string_xrefs

- `0x18000bc9f`: `RasIpv6SrvrStart completes with return code %d`
- `0x18000ba61`: `DDMTransportCreate called for Transport Id = %d`
- `0x18000bad6`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`

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
  unsigned int v9; // ecx
  __int64 v10; // r9
  unsigned int v11; // ecx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int i; // edi
  __int64 v17; // [rsp+48h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B8h] BYREF
  struct _GUID phkResult_8; // [rsp+58h] [rbp-B0h] BYREF
  int *v20; // [rsp+68h] [rbp-A0h]
  int v21; // [rsp+70h] [rbp-98h]
  int v22; // [rsp+74h] [rbp-94h]
  int v23; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v24[2044]; // [rsp+7Ch] [rbp-8Ch] BYREF

  LODWORD(v17) = 0;
  phkResult = 0;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v2 = -1;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"DDMTransportCreate called for Transport Id = %d", a1);
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v4 = -1;
      do
        ++v4;
      while ( *(_WORD *)&v24[2 * v4 - 4] );
      v22 = 0;
      v21 = 2 * v4 + 2;
      v20 = &v23;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v3, 2, &phkResult_8);
    }
  }
  result = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters", &phkResult);
  if ( !result )
  {
    if ( (dword_1800C864C & 4) != 0 || (v7 = 0, (dword_1800C864C & 0x20) != 0) )
      v7 = 1;
    dwErrorCode = lProtocolEnabled((_DWORD)phkResult, a1, v6, v7, (__int64)&v17);
    if ( dwErrorCode )
    {
      RegCloseKey(phkResult);
      return dwErrorCode;
    }
    RegCloseKey(phkResult);
    if ( !(_DWORD)v17 )
      return 0;
    if ( a1 != 33 )
    {
      if ( a1 == 87 )
      {
        if ( !dword_1800C851C )
        {
          v11 = 0;
          if ( dword_1800C8568 )
          {
            while ( 1 )
            {
              v12 = 168LL * v11;
              if ( *(_QWORD *)((char *)qword_1800C8560 + v12 + 32) )
              {
                if ( *(_QWORD *)((char *)qword_1800C8560 + v12 + 40) )
                  break;
              }
              if ( ++v11 >= dword_1800C8568 )
                goto LABEL_34;
            }
            v13 = *((unsigned __int8 *)qword_1800C8560 + v12 + 8);
            v15 = *(_QWORD *)((char *)qword_1800C8560 + v12 + 32);
            v14 = *(_QWORD *)((char *)qword_1800C8560 + v12 + 40);
          }
          else
          {
LABEL_34:
            v13 = 0;
            v14 = 0;
            v15 = 0;
          }
          dwErrorCode = RasSrvrIpv6Initialize(v15, v14, v13);
          if ( !dwErrorCode )
          {
            phkResult_8 = GUID_NULL;
            dwErrorCode = RasIpv6SrvrStart(&phkResult_8);
          }
          if ( (byte_1800C8404 & 0x10) != 0 )
          {
            LOWORD(v23) = 0;
            FormatRRASErrorString(&v23, L"RasIpv6SrvrStart completes with return code %d", dwErrorCode);
            if ( (byte_1800C8404 & 0x10) != 0 )
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
                &phkResult_8);
            }
          }
          if ( dwErrorCode )
          {
            if ( dword_1800C84E4 )
              RouterLogEventStringW(hLogHandle, 1u, 0x4EB1u, 0, 0, dwErrorCode, 0);
          }
          else
          {
            dword_1800C851C = 1;
          }
        }
        dword_1800C84EC |= 0x8000000u;
      }
      goto LABEL_47;
    }
    if ( dword_1800C8518 )
    {
LABEL_27:
      dword_1800C84EC |= 8u;
LABEL_47:
      for ( i = 0; i < 3; ++i )
      {
        if ( !LODWORD(protocolEngineParams[10 * i + 3]) )
        {
          if ( HIDWORD(protocolEngineParams[10 * i + 3]) )
            ProtocolDdmChangeNotification((unsigned int)dword_1800C84EC, (unsigned int)dword_1800C84E4, i);
        }
      }
      return dwErrorCode;
    }
    v9 = 0;
    if ( dword_1800C8568 )
    {
      while ( 1 )
      {
        v10 = 168LL * v9;
        if ( *(_QWORD *)((char *)qword_1800C8560 + v10 + 16) )
          break;
        if ( ++v9 >= dword_1800C8568 )
          goto LABEL_19;
      }
      dwErrorCode = RasSrvrIpv4Initialize(
                      *(_QWORD *)((char *)qword_1800C8560 + v10 + 16),
                      *(_QWORD *)((char *)qword_1800C8560 + v10 + 24),
                      *((unsigned __int8 *)qword_1800C8560 + v10 + 8));
      if ( dwErrorCode )
      {
LABEL_21:
        if ( !dwErrorCode )
        {
          dword_1800C8518 = 1;
          goto LABEL_27;
        }
LABEL_25:
        if ( dword_1800C84E4 )
          RouterLogEventStringW(hLogHandle, 1u, 0x4EB1u, 0, 0, dwErrorCode, 0);
        goto LABEL_27;
      }
    }
    else
    {
LABEL_19:
      dwErrorCode = RasSrvrIpv4Initialize(0, 0, 0);
      if ( dwErrorCode )
        goto LABEL_25;
    }
    phkResult_8 = GUID_NULL;
    dwErrorCode = RasSrvrStart(&phkResult_8);
    goto LABEL_21;
  }
  return result;
}

```

## disassembly

```asm
0x18000b9f0  mov     rax, rsp
0x18000b9f3  push    rbp
0x18000b9f4  push    rbx
0x18000b9f5  push    rsi
0x18000b9f6  push    rdi
0x18000b9f7  push    r14
0x18000b9f9  push    r15
0x18000b9fb  lea     rbp, [rax-7C8h]
0x18000ba02  sub     rsp, 898h
0x18000ba09  movaps  xmmword ptr [rax-48h], xmm6
0x18000ba0d  mov     rax, cs:__security_cookie
0x18000ba14  xor     rax, rsp
0x18000ba17  mov     [rbp+7C0h+var_50], rax
0x18000ba1e  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18000ba25  xor     r14d, r14d
0x18000ba28  mov     edi, ecx
0x18000ba2a  lea     rcx, [rsp+8C0h+var_84C]; void *
0x18000ba2f  mov     dword ptr [rsp+8C0h+var_880], r14d
0x18000ba34  xor     edx, edx; Val
0x18000ba36  mov     [rsp+8C0h+phkResult], r14
0x18000ba3b  mov     r8d, 7FCh; Size
0x18000ba41  mov     [rsp+70h], r14d
0x18000ba46  call    memset_0
0x18000ba4b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000ba4f  test    cs:byte_1800C8404, 10h
0x18000ba56  jz      short loc_18000BACA
0x18000ba58  mov     r8d, edi
0x18000ba5b  mov     [rsp+70h], r14w
0x18000ba61  lea     rdx, aDdmtransportcr_0; "DDMTransportCreate called for Transport"...
0x18000ba68  lea     rcx, [rsp+70h]
0x18000ba6d  call    FormatRRASErrorString
0x18000ba72  test    cs:byte_1800C8404, 10h
0x18000ba79  jz      short loc_18000BACA
0x18000ba7b  lea     rcx, [rsp+70h]
0x18000ba80  mov     rax, rsi
0x18000ba83  inc     rax
0x18000ba86  cmp     [rcx+rax*2], r14w
0x18000ba8b  jnz     short loc_18000BA83
0x18000ba8d  lea     eax, ds:2[rax*2]
0x18000ba94  mov     [rsp+8C0h+var_854], r14d
0x18000ba99  lea     rcx, [rsp+70h]
0x18000ba9e  mov     [rsp+8C0h+var_858], eax
0x18000baa2  lea     rax, [rsp+8C0h+phkResult+8]
0x18000baa7  mov     qword ptr [rsp+8C0h+var_860], rcx
0x18000baac  mov     r9d, 2
0x18000bab2  mov     [rsp+8C0h+plpszSubStringArray], rax
0x18000bab7  lea     rdx, RasDdmTraceInfo
0x18000babe  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bac5  call    McGenEventWrite_EventWriteTransfer
0x18000baca  lea     r8, [rsp+8C0h+phkResult]; phkResult
0x18000bacf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bad6  lea     rdx, aSystemCurrentc_36; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18000badd  call    cs:__imp_RegOpenKeyW
0x18000bae3  test    eax, eax
0x18000bae5  jnz     loc_18000BD9A
0x18000baeb  mov     eax, cs:dword_1800C864C
0x18000baf1  mov     r15d, 1
0x18000baf7  test    al, 4
0x18000baf9  jnz     short loc_18000BB02
0x18000bafb  mov     r9d, r14d
0x18000bafe  test    al, 20h
0x18000bb00  jz      short loc_18000BB05
0x18000bb02  mov     r9d, r15d
0x18000bb05  mov     rcx, [rsp+8C0h+phkResult]
0x18000bb0a  lea     rax, [rsp+8C0h+var_880]
0x18000bb0f  mov     edx, edi
0x18000bb11  mov     [rsp+8C0h+plpszSubStringArray], rax
0x18000bb16  call    lProtocolEnabled
0x18000bb1b  mov     rcx, [rsp+8C0h+phkResult]; hKey
0x18000bb20  mov     ebx, eax
0x18000bb22  test    eax, eax
0x18000bb24  jz      short loc_18000BB31
0x18000bb26  call    cs:__imp_RegCloseKey
0x18000bb2c  jmp     loc_18000BD98
0x18000bb31  call    cs:__imp_RegCloseKey
0x18000bb37  cmp     dword ptr [rsp+8C0h+var_880], r14d
0x18000bb3c  jnz     short loc_18000BB45
0x18000bb3e  xor     eax, eax
0x18000bb40  jmp     loc_18000BD9A
0x18000bb45  cmp     edi, 21h ; '!'
0x18000bb48  jnz     loc_18000BC14
0x18000bb4e  cmp     cs:dword_1800C8518, r14d
0x18000bb55  jnz     loc_18000BC08
0x18000bb5b  mov     r8d, cs:dword_1800C8568
0x18000bb62  mov     ecx, r14d
0x18000bb65  test    r8d, r8d
0x18000bb68  jz      short loc_18000BB8C
0x18000bb6a  mov     rdx, cs:qword_1800C8560
0x18000bb71  mov     eax, ecx
0x18000bb73  imul    r9, rax, 0A8h
0x18000bb7a  mov     rax, [r9+rdx+10h]
0x18000bb7f  test    rax, rax
0x18000bb82  jnz     short loc_18000BBBD
0x18000bb84  add     ecx, r15d
0x18000bb87  cmp     ecx, r8d
0x18000bb8a  jb      short loc_18000BB71
0x18000bb8c  xor     r8d, r8d
0x18000bb8f  xor     edx, edx
0x18000bb91  xor     ecx, ecx
0x18000bb93  call    RasSrvrIpv4Initialize
0x18000bb98  mov     ebx, eax
0x18000bb9a  test    eax, eax
0x18000bb9c  jnz     short loc_18000BBD8
0x18000bb9e  lea     rcx, [rsp+8C0h+phkResult+8]; Buf1
0x18000bba3  movdqa  xmmword ptr [rsp+8C0h+phkResult+8], xmm6
0x18000bba9  call    RasSrvrStart
0x18000bbae  mov     ebx, eax
0x18000bbb0  test    ebx, ebx
0x18000bbb2  jnz     short loc_18000BBD8
0x18000bbb4  mov     cs:dword_1800C8518, r15d
0x18000bbbb  jmp     short loc_18000BC08
0x18000bbbd  movzx   r8d, byte ptr [r9+rdx+8]
0x18000bbc3  mov     rcx, rax
0x18000bbc6  mov     rdx, [r9+rdx+18h]
0x18000bbcb  call    RasSrvrIpv4Initialize
0x18000bbd0  mov     ebx, eax
0x18000bbd2  test    eax, eax
0x18000bbd4  jnz     short loc_18000BBB0
0x18000bbd6  jmp     short loc_18000BB9E
0x18000bbd8  cmp     cs:dword_1800C84E4, r14d
0x18000bbdf  jbe     short loc_18000BC08
0x18000bbe1  mov     rcx, cs:hLogHandle; hLogHandle
0x18000bbe8  xor     r9d, r9d; dwSubStringCount
0x18000bbeb  mov     [rsp+30h], r14d; dwErrorIndex
0x18000bbf0  mov     r8d, 4EB1h; dwMessageId
0x18000bbf6  mov     [rsp+8C0h+dwErrorCode], ebx; dwErrorCode
0x18000bbfa  mov     edx, r15d; dwEventType
0x18000bbfd  mov     [rsp+8C0h+plpszSubStringArray], r14; plpszSubStringArray
0x18000bc02  call    cs:__imp_RouterLogEventStringW
0x18000bc08  or      cs:dword_1800C84EC, 8
0x18000bc0f  jmp     loc_18000BD5B
0x18000bc14  cmp     edi, 57h ; 'W'
0x18000bc17  jnz     loc_18000BD5B
0x18000bc1d  cmp     cs:dword_1800C851C, r14d
0x18000bc24  jnz     loc_18000BD53
0x18000bc2a  mov     r9d, cs:dword_1800C8568
0x18000bc31  mov     ecx, r14d
0x18000bc34  test    r9d, r9d
0x18000bc37  jz      short loc_18000BC69
0x18000bc39  mov     r8, cs:qword_1800C8560
0x18000bc40  mov     eax, ecx
0x18000bc42  imul    rdx, rax, 0A8h
0x18000bc49  mov     r10, [rdx+r8+20h]
0x18000bc4e  test    r10, r10
0x18000bc51  jz      short loc_18000BC61
0x18000bc53  mov     rax, [rdx+r8+28h]
0x18000bc58  test    rax, rax
0x18000bc5b  jnz     loc_18000BD3B
0x18000bc61  add     ecx, r15d
0x18000bc64  cmp     ecx, r9d
0x18000bc67  jb      short loc_18000BC40
0x18000bc69  xor     r8d, r8d
0x18000bc6c  xor     edx, edx
0x18000bc6e  xor     ecx, ecx
0x18000bc70  call    RasSrvrIpv6Initialize
0x18000bc75  mov     ebx, eax
0x18000bc77  test    eax, eax
0x18000bc79  jnz     short loc_18000BC8D
0x18000bc7b  lea     rcx, [rsp+8C0h+phkResult+8]; struct _GUID *
0x18000bc80  movdqa  xmmword ptr [rsp+8C0h+phkResult+8], xmm6
0x18000bc86  call    RasIpv6SrvrStart
0x18000bc8b  mov     ebx, eax
0x18000bc8d  test    cs:byte_1800C8404, 10h
0x18000bc94  jz      short loc_18000BD05
0x18000bc96  mov     r8d, ebx
0x18000bc99  mov     [rsp+70h], r14w
0x18000bc9f  lea     rdx, aRasipv6srvrsta_0; "RasIpv6SrvrStart completes with return "...
0x18000bca6  lea     rcx, [rsp+70h]
0x18000bcab  call    FormatRRASErrorString
0x18000bcb0  test    cs:byte_1800C8404, 10h
0x18000bcb7  jz      short loc_18000BD05
0x18000bcb9  lea     rax, [rsp+70h]
0x18000bcbe  inc     rsi
0x18000bcc1  cmp     [rax+rsi*2], r14w
0x18000bcc6  jnz     short loc_18000BCBE
0x18000bcc8  lea     eax, ds:2[rsi*2]
0x18000bccf  mov     [rsp+8C0h+var_854], r14d
0x18000bcd4  mov     [rsp+8C0h+var_858], eax
0x18000bcd8  lea     r8, [rsp+70h]
0x18000bcdd  lea     rax, [rsp+8C0h+phkResult+8]
0x18000bce2  mov     qword ptr [rsp+8C0h+var_860], r8
0x18000bce7  mov     r9d, 2
0x18000bced  mov     [rsp+8C0h+plpszSubStringArray], rax
0x18000bcf2  lea     rdx, RasDdmTraceInfo
0x18000bcf9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bd00  call    McGenEventWrite_EventWriteTransfer
0x18000bd05  test    ebx, ebx
0x18000bd07  jz      short loc_18000BD4C
0x18000bd09  cmp     cs:dword_1800C84E4, r14d
0x18000bd10  jbe     short loc_18000BD53
0x18000bd12  mov     rcx, cs:hLogHandle; hLogHandle
0x18000bd19  xor     r9d, r9d; dwSubStringCount
0x18000bd1c  mov     [rsp+30h], r14d; dwErrorIndex
0x18000bd21  mov     r8d, 4EB1h; dwMessageId
0x18000bd27  mov     [rsp+8C0h+dwErrorCode], ebx; dwErrorCode
0x18000bd2b  mov     edx, r15d; dwEventType
0x18000bd2e  mov     [rsp+8C0h+plpszSubStringArray], r14; plpszSubStringArray
0x18000bd33  call    cs:__imp_RouterLogEventStringW
0x18000bd39  jmp     short loc_18000BD53
0x18000bd3b  movzx   r8d, byte ptr [rdx+r8+8]
0x18000bd41  mov     rcx, r10
0x18000bd44  mov     rdx, rax
0x18000bd47  jmp     loc_18000BC70
0x18000bd4c  mov     cs:dword_1800C851C, r15d
0x18000bd53  bts     cs:dword_1800C84EC, 1Bh
0x18000bd5b  mov     edi, r14d
0x18000bd5e  lea     rsi, protocolEngineParams
0x18000bd65  mov     eax, edi
0x18000bd67  lea     rcx, [rax+rax*4]
0x18000bd6b  add     rcx, rcx
0x18000bd6e  cmp     [rsi+rcx*8+18h], r14d
0x18000bd73  jnz     short loc_18000BD90
0x18000bd75  cmp     [rsi+rcx*8+1Ch], r14d
0x18000bd7a  jz      short loc_18000BD90
0x18000bd7c  mov     edx, cs:dword_1800C84E4
0x18000bd82  mov     r8d, edi
0x18000bd85  mov     ecx, cs:dword_1800C84EC
0x18000bd8b  call    ProtocolDdmChangeNotification
0x18000bd90  add     edi, r15d
0x18000bd93  cmp     edi, 3
0x18000bd96  jb      short loc_18000BD65
0x18000bd98  mov     eax, ebx
0x18000bd9a  mov     rcx, [rbp+7C0h+var_50]
0x18000bda1  xor     rcx, rsp; StackCookie
0x18000bda4  call    __security_check_cookie
0x18000bda9  movaps  xmm6, [rsp+8C0h+var_48+8]
0x18000bdb1  add     rsp, 898h
0x18000bdb8  pop     r15
0x18000bdba  pop     r14
0x18000bdbc  pop     rdi
0x18000bdbd  pop     rsi
0x18000bdbe  pop     rbx
0x18000bdbf  pop     rbp
0x18000bdc0  retn
```
