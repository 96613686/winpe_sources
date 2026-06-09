# TLSCryptGenerateNewKeys

- ea: `0x1800262ac`
- end: `0x1800267e1`
- name: `TLSCryptGenerateNewKeys`
- size: `1333`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180021cfc`

## callees

- `0x18000bb98`
- `0x18001ad48`
- `0x18001ad74`
- `0x180022910`
- `0x1800262ac`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x18002632c`
- `msvcrt!_snwprintf_s` at `0x18002632c`
- `ADVAPI32!CryptReleaseContext` at `0x18002675a`
- `ADVAPI32!CryptReleaseContext` at `0x18002675a`
- `ADVAPI32!CryptDestroyKey` at `0x18002672e`
- `ADVAPI32!CryptDestroyKey` at `0x180026743`
- `ADVAPI32!CryptDestroyKey` at `0x18002672e`
- `ADVAPI32!CryptDestroyKey` at `0x180026743`
- `ADVAPI32!CryptExportKey` at `0x180026578`
- `ADVAPI32!CryptExportKey` at `0x1800265fc`
- `ADVAPI32!CryptExportKey` at `0x180026692`
- `ADVAPI32!CryptExportKey` at `0x1800266ea`
- `ADVAPI32!CryptExportKey` at `0x180026578`
- `ADVAPI32!CryptExportKey` at `0x1800265fc`
- `ADVAPI32!CryptExportKey` at `0x180026692`
- `ADVAPI32!CryptExportKey` at `0x1800266ea`
- `ADVAPI32!CryptGenKey` at `0x180026535`
- `ADVAPI32!CryptGenKey` at `0x180026663`
- `ADVAPI32!CryptGenKey` at `0x180026535`
- `ADVAPI32!CryptGenKey` at `0x180026663`
- `ADVAPI32!CryptGetUserKey` at `0x1800264f6`
- `ADVAPI32!CryptGetUserKey` at `0x18002661d`
- `ADVAPI32!CryptGetUserKey` at `0x1800264f6`
- `ADVAPI32!CryptGetUserKey` at `0x18002661d`
- `ADVAPI32!CryptAcquireContextW` at `0x180026355`
- `ADVAPI32!CryptAcquireContextW` at `0x1800263d7`
- `ADVAPI32!CryptAcquireContextW` at `0x180026477`
- `ADVAPI32!CryptAcquireContextW` at `0x180026788`
- `ADVAPI32!CryptAcquireContextW` at `0x180026355`
- `ADVAPI32!CryptAcquireContextW` at `0x1800263d7`
- `ADVAPI32!CryptAcquireContextW` at `0x180026477`
- `ADVAPI32!CryptAcquireContextW` at `0x180026788`
- `KERNEL32!GetCurrentThreadId` at `0x180026308`
- `KERNEL32!GetCurrentThreadId` at `0x180026308`
- `KERNEL32!GetLastError` at `0x180026373`
- `KERNEL32!GetLastError` at `0x1800263e7`
- `KERNEL32!GetLastError` at `0x180026487`
- `KERNEL32!GetLastError` at `0x180026506`
- `KERNEL32!GetLastError` at `0x180026512`
- `KERNEL32!GetLastError` at `0x180026545`
- `KERNEL32!GetLastError` at `0x180026588`
- `KERNEL32!GetLastError` at `0x1800265d3`
- `KERNEL32!GetLastError` at `0x18002662d`
- `KERNEL32!GetLastError` at `0x180026639`
- `KERNEL32!GetLastError` at `0x1800266a2`
- `KERNEL32!GetLastError` at `0x1800266fa`
- `KERNEL32!GetLastError` at `0x180026373`
- `KERNEL32!GetLastError` at `0x1800263e7`
- `KERNEL32!GetLastError` at `0x180026487`
- `KERNEL32!GetLastError` at `0x180026506`
- `KERNEL32!GetLastError` at `0x180026512`
- `KERNEL32!GetLastError` at `0x180026545`
- `KERNEL32!GetLastError` at `0x180026588`
- `KERNEL32!GetLastError` at `0x1800265d3`
- `KERNEL32!GetLastError` at `0x18002662d`
- `KERNEL32!GetLastError` at `0x180026639`
- `KERNEL32!GetLastError` at `0x1800266a2`
- `KERNEL32!GetLastError` at `0x1800266fa`
- `KERNEL32!LocalAlloc` at `0x1800265a6`
- `KERNEL32!LocalAlloc` at `0x1800266bc`
- `KERNEL32!LocalAlloc` at `0x1800265a6`
- `KERNEL32!LocalAlloc` at `0x1800266bc`
- `KERNEL32!LocalFree` at `0x1800267a0`
- `KERNEL32!LocalFree` at `0x1800267b4`
- `KERNEL32!LocalFree` at `0x1800267a0`
- `KERNEL32!LocalFree` at `0x1800267b4`

## pseudocode

```c
__int64 __fastcall TLSCryptGenerateNewKeys(BYTE **a1, DWORD *a2, BYTE **a3, DWORD *a4)
{
  DWORD LastError; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  DWORD v11; // eax
  unsigned int v12; // edx
  BYTE *v13; // rax
  BYTE *v14; // rax
  DWORD dwFlags; // [rsp+20h] [rbp-59h]
  HCRYPTPROV phProv; // [rsp+30h] [rbp-49h] BYREF
  HCRYPTKEY phUserKey; // [rsp+38h] [rbp-41h] BYREF
  HCRYPTKEY phKey[2]; // [rsp+40h] [rbp-39h] BYREF
  struct _EVENT_DESCRIPTOR v20; // [rsp+50h] [rbp-29h] BYREF
  wchar_t Buffer[8]; // [rsp+60h] [rbp-19h] BYREF
  __int128 v22; // [rsp+70h] [rbp-9h]
  __int128 v23; // [rsp+80h] [rbp+7h]
  int v24; // [rsp+90h] [rbp+17h]

  *a1 = 0;
  phProv = 0;
  phUserKey = 0;
  phKey[0] = 0;
  *a3 = 0;
  *(_OWORD *)Buffer = 0;
  v24 = 0;
  v22 = 0;
  v23 = 0;
  dwFlags = GetCurrentThreadId();
  _snwprintf_s(Buffer, 0x1Au, 0x19u, L"TlsContainer%d", dwFlags);
  if ( CryptAcquireContextW(&phProv, Buffer, L"Microsoft Strong Cryptographic Provider", 1u, 0x28u) )
    goto LABEL_19;
  LastError = GetLastError();
  if ( LastError != -2146893809 )
    goto LABEL_39;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_08690fd55cba3683604b251810567528_Traceguids);
  if ( !CryptAcquireContextW(&phProv, Buffer, L"Microsoft Strong Cryptographic Provider", 1u, 0x30u) )
  {
    LastError = GetLastError();
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v10 = 11;
LABEL_10:
      WPP_SF_D(v9[2], v10, WPP_08690fd55cba3683604b251810567528_Traceguids, LastError);
      goto LABEL_39;
    }
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_08690fd55cba3683604b251810567528_Traceguids);
  if ( CryptAcquireContextW(&phProv, Buffer, L"Microsoft Strong Cryptographic Provider", 1u, 0x28u) )
  {
LABEL_19:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_08690fd55cba3683604b251810567528_Traceguids);
    if ( !CryptGetUserKey(phProv, 2u, &phUserKey) )
    {
      GetLastError();
      if ( GetLastError() != -2146893811 || !CryptGenKey(phProv, 2u, 0x8000001u, &phUserKey) )
        goto LABEL_24;
    }
    if ( CryptExportKey(phUserKey, 0, 7u, 0, *a1, a2) || GetLastError() == 234 )
    {
      v13 = (BYTE *)LocalAlloc(0x40u, *a2);
      *a1 = v13;
      if ( !v13 )
      {
LABEL_28:
        CrimsonHelper::RaiseEventInternal((CrimsonHelper *)CrimsonHelper::s_instance, &TLS_E_ALLOCATE_MEMORY, 0, 0);
        LastError = GetLastError();
        goto LABEL_39;
      }
      if ( CryptExportKey(phUserKey, 0, 7u, 0, v13, a2) )
      {
        if ( !CryptGetUserKey(phProv, 1u, phKey) )
        {
          GetLastError();
          if ( GetLastError() != -2146893811 || !CryptGenKey(phProv, 1u, 0x8000001u, phKey) )
          {
LABEL_24:
            v11 = GetLastError();
            v12 = -1072627709;
LABEL_38:
            LastError = v11;
            v20 = (struct _EVENT_DESCRIPTOR)TLS_E_GENERATEKEYS;
            TLSLogEvent(&v20, v12, v11);
            goto LABEL_39;
          }
        }
        LastError = 0;
        if ( CryptExportKey(phKey[0], 0, 7u, 0, *a3, a4) || GetLastError() == 234 )
        {
          v14 = (BYTE *)LocalAlloc(0x40u, *a4);
          *a3 = v14;
          if ( !v14 )
            goto LABEL_28;
          if ( CryptExportKey(phKey[0], 0, 7u, 0, v14, a4) )
            goto LABEL_39;
        }
      }
    }
    v11 = GetLastError();
    v12 = -1072627707;
    goto LABEL_38;
  }
  LastError = GetLastError();
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    v10 = 13;
    goto LABEL_10;
  }
LABEL_39:
  if ( phUserKey )
    CryptDestroyKey(phUserKey);
  if ( phKey[0] )
    CryptDestroyKey(phKey[0]);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  phProv = 0;
  CryptAcquireContextW(&phProv, Buffer, L"Microsoft Strong Cryptographic Provider", 1u, 0x30u);
  if ( LastError )
  {
    if ( *a1 )
      LocalFree(*a1);
    if ( *a3 )
      LocalFree(*a3);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800262ac  push    rbp
0x1800262ae  push    rbx
0x1800262af  push    rsi
0x1800262b0  push    rdi
0x1800262b1  push    r13
0x1800262b3  push    r14
0x1800262b5  push    r15
0x1800262b7  lea     rbp, [rsp-27h]
0x1800262bc  sub     rsp, 0A0h
0x1800262c3  mov     rax, cs:__security_cookie
0x1800262ca  xor     rax, rsp
0x1800262cd  mov     [rbp+57h+var_38], rax
0x1800262d1  and     qword ptr [rcx], 0
0x1800262d5  xorps   xmm0, xmm0
0x1800262d8  and     [rbp+57h+phProv], 0
0x1800262dd  xor     eax, eax
0x1800262df  and     [rbp+57h+phUserKey], 0
0x1800262e4  mov     rsi, r9
0x1800262e7  and     [rbp+57h+phKey], 0
0x1800262ec  mov     r14, r8
0x1800262ef  and     qword ptr [r8], 0
0x1800262f3  mov     rdi, rdx
0x1800262f6  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1800262fa  mov     [rbp+57h+var_40], eax
0x1800262fd  mov     r15, rcx
0x180026300  movups  [rbp+57h+var_60], xmm0
0x180026304  movups  [rbp+57h+var_50], xmm0
0x180026308  call    cs:__imp_GetCurrentThreadId
0x18002630f  nop     dword ptr [rax+rax+00h]
0x180026314  mov     edx, 1Ah; BufferCount
0x180026319  lea     r9, aTlscontainerD; "TlsContainer%d"
0x180026320  lea     rcx, [rbp+57h+Buffer]; Buffer
0x180026324  mov     [rsp+0D0h+dwFlags], eax
0x180026328  lea     r8d, [rdx-1]; MaxCount
0x18002632c  call    cs:__imp__snwprintf_s
0x180026333  nop     dword ptr [rax+rax+00h]
0x180026338  mov     r9d, 1; dwProvType
0x18002633e  mov     [rsp+0D0h+dwFlags], 28h ; '('; dwFlags
0x180026346  lea     r8, szProvider; "Microsoft Strong Cryptographic Provider"
0x18002634d  lea     rdx, [rbp+57h+Buffer]; szContainer
0x180026351  lea     rcx, [rbp+57h+phProv]; phProv
0x180026355  call    cs:__imp_CryptAcquireContextW
0x18002635c  nop     dword ptr [rax+rax+00h]
0x180026361  lea     rbx, WPP_GLOBAL_Control
0x180026368  mov     r13b, 20h ; ' '
0x18002636b  test    eax, eax
0x18002636d  jnz     loc_1800264C0
0x180026373  call    cs:__imp_GetLastError
0x18002637a  nop     dword ptr [rax+rax+00h]
0x18002637f  mov     ebx, eax
0x180026381  cmp     eax, 8009000Fh
0x180026386  jnz     loc_180026725
0x18002638c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026393  lea     rbx, WPP_GLOBAL_Control
0x18002639a  cmp     rcx, rbx
0x18002639d  jz      short loc_1800263BA
0x18002639f  test    [rcx+1Ch], r13b
0x1800263a3  jz      short loc_1800263BA
0x1800263a5  mov     rcx, [rcx+10h]
0x1800263a9  lea     r8, WPP_08690fd55cba3683604b251810567528_Traceguids
0x1800263b0  mov     edx, 0Ah
0x1800263b5  call    WPP_SF_
0x1800263ba  mov     r9d, 1; dwProvType
0x1800263c0  mov     [rsp+0D0h+dwFlags], 30h ; '0'; dwFlags
0x1800263c8  lea     r8, szProvider; "Microsoft Strong Cryptographic Provider"
0x1800263cf  lea     rdx, [rbp+57h+Buffer]; szContainer
0x1800263d3  lea     rcx, [rbp+57h+phProv]; phProv
0x1800263d7  call    cs:__imp_CryptAcquireContextW
0x1800263de  nop     dword ptr [rax+rax+00h]
0x1800263e3  test    eax, eax
0x1800263e5  jnz     short loc_180026433
0x1800263e7  call    cs:__imp_GetLastError
0x1800263ee  nop     dword ptr [rax+rax+00h]
0x1800263f3  mov     ebx, eax
0x1800263f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263fc  lea     rax, WPP_GLOBAL_Control
0x180026403  cmp     rcx, rax
0x180026406  jz      loc_180026725
0x18002640c  test    [rcx+1Ch], r13b
0x180026410  jz      loc_180026725
0x180026416  mov     edx, 0Bh
0x18002641b  mov     rcx, [rcx+10h]
0x18002641f  lea     r8, WPP_08690fd55cba3683604b251810567528_Traceguids
0x180026426  mov     r9d, ebx
0x180026429  call    WPP_SF_D
0x18002642e  jmp     loc_180026725
0x180026433  mov     rcx, cs:WPP_GLOBAL_Control
0x18002643a  cmp     rcx, rbx
0x18002643d  jz      short loc_18002645A
0x18002643f  test    [rcx+1Ch], r13b
0x180026443  jz      short loc_18002645A
0x180026445  mov     rcx, [rcx+10h]
0x180026449  lea     r8, WPP_08690fd55cba3683604b251810567528_Traceguids
0x180026450  mov     edx, 0Ch
0x180026455  call    WPP_SF_
0x18002645a  mov     r9d, 1; dwProvType
0x180026460  mov     [rsp+0D0h+dwFlags], 28h ; '('; dwFlags
0x180026468  lea     r8, szProvider; "Microsoft Strong Cryptographic Provider"
0x18002646f  lea     rdx, [rbp+57h+Buffer]; szContainer
0x180026473  lea     rcx, [rbp+57h+phProv]; phProv
0x180026477  call    cs:__imp_CryptAcquireContextW
0x18002647e  nop     dword ptr [rax+rax+00h]
0x180026483  test    eax, eax
0x180026485  jnz     short loc_1800264C0
0x180026487  call    cs:__imp_GetLastError
0x18002648e  nop     dword ptr [rax+rax+00h]
0x180026493  mov     ebx, eax
0x180026495  mov     rcx, cs:WPP_GLOBAL_Control
0x18002649c  lea     rax, WPP_GLOBAL_Control
0x1800264a3  cmp     rcx, rax
0x1800264a6  jz      loc_180026725
0x1800264ac  test    [rcx+1Ch], r13b
0x1800264b0  jz      loc_180026725
0x1800264b6  mov     edx, 0Dh
0x1800264bb  jmp     loc_18002641B
0x1800264c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800264c7  cmp     rcx, rbx
0x1800264ca  jz      short loc_1800264E7
0x1800264cc  test    [rcx+1Ch], r13b
0x1800264d0  jz      short loc_1800264E7
0x1800264d2  mov     rcx, [rcx+10h]
0x1800264d6  lea     r8, WPP_08690fd55cba3683604b251810567528_Traceguids
0x1800264dd  mov     edx, 0Eh
0x1800264e2  call    WPP_SF_
0x1800264e7  mov     rcx, [rbp+57h+phProv]; hProv
0x1800264eb  lea     r8, [rbp+57h+phUserKey]; phUserKey
0x1800264ef  mov     ebx, 2
0x1800264f4  mov     edx, ebx; dwKeySpec
0x1800264f6  call    cs:__imp_CryptGetUserKey
0x1800264fd  nop     dword ptr [rax+rax+00h]
0x180026502  test    eax, eax
0x180026504  jnz     short loc_18002655B
0x180026506  call    cs:__imp_GetLastError
0x18002650d  nop     dword ptr [rax+rax+00h]
0x180026512  call    cs:__imp_GetLastError
0x180026519  nop     dword ptr [rax+rax+00h]
0x18002651e  cmp     eax, 8009000Dh
0x180026523  jnz     short loc_180026545
0x180026525  mov     rcx, [rbp+57h+phProv]; hProv
0x180026529  lea     r9, [rbp+57h+phUserKey]; phKey
0x18002652d  mov     r8d, 8000001h; dwFlags
0x180026533  mov     edx, ebx; Algid
0x180026535  call    cs:__imp_CryptGenKey
0x18002653c  nop     dword ptr [rax+rax+00h]
0x180026541  test    eax, eax
0x180026543  jnz     short loc_18002655B
0x180026545  call    cs:__imp_GetLastError
0x18002654c  nop     dword ptr [rax+rax+00h]
0x180026551  mov     edx, 0C0110003h
0x180026556  jmp     loc_18002670B
0x18002655b  mov     rax, [r15]
0x18002655e  xor     r9d, r9d; dwFlags
0x180026561  mov     rcx, [rbp+57h+phUserKey]; hKey
0x180026565  xor     edx, edx; hExpKey
0x180026567  mov     [rsp+0D0h+pdwDataLen], rdi; pdwDataLen
0x18002656c  mov     qword ptr [rsp+0D0h+dwFlags], rax; pbData
0x180026571  lea     r13d, [r9+7]
0x180026575  mov     r8d, r13d; dwBlobType
0x180026578  call    cs:__imp_CryptExportKey
0x18002657f  nop     dword ptr [rax+rax+00h]
0x180026584  test    eax, eax
0x180026586  jnz     short loc_18002659F
0x180026588  call    cs:__imp_GetLastError
0x18002658f  nop     dword ptr [rax+rax+00h]
0x180026594  cmp     eax, 0EAh
0x180026599  jnz     loc_1800266FA
0x18002659f  mov     edx, [rdi]; uBytes
0x1800265a1  mov     ecx, 40h ; '@'; uFlags
0x1800265a6  call    cs:__imp_LocalAlloc
0x1800265ad  nop     dword ptr [rax+rax+00h]
0x1800265b2  mov     [r15], rax
0x1800265b5  test    rax, rax
0x1800265b8  jnz     short loc_1800265E6
0x1800265ba  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x1800265bd  lea     rdx, TLS_E_ALLOCATE_MEMORY; struct _EVENT_DESCRIPTOR *
0x1800265c4  xor     r8d, r8d; unsigned int
0x1800265c7  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x1800265ce  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x1800265d3  call    cs:__imp_GetLastError
0x1800265da  nop     dword ptr [rax+rax+00h]
0x1800265df  mov     ebx, eax
0x1800265e1  jmp     loc_180026725
0x1800265e6  mov     rcx, [rbp+57h+phUserKey]; hKey
0x1800265ea  xor     r9d, r9d; dwFlags
0x1800265ed  mov     [rsp+0D0h+pdwDataLen], rdi; pdwDataLen
0x1800265f2  mov     r8d, r13d; dwBlobType
0x1800265f5  xor     edx, edx; hExpKey
0x1800265f7  mov     qword ptr [rsp+0D0h+dwFlags], rax; pbData
0x1800265fc  call    cs:__imp_CryptExportKey
0x180026603  nop     dword ptr [rax+rax+00h]
0x180026608  test    eax, eax
0x18002660a  jz      loc_1800266FA
0x180026610  mov     rcx, [rbp+57h+phProv]; hProv
0x180026614  lea     r8, [rbp+57h+phKey]; phUserKey
0x180026618  mov     edx, 1; dwKeySpec
0x18002661d  call    cs:__imp_CryptGetUserKey
0x180026624  nop     dword ptr [rax+rax+00h]
0x180026629  test    eax, eax
0x18002662b  jnz     short loc_180026677
0x18002662d  call    cs:__imp_GetLastError
0x180026634  nop     dword ptr [rax+rax+00h]
0x180026639  call    cs:__imp_GetLastError
0x180026640  nop     dword ptr [rax+rax+00h]
0x180026645  cmp     eax, 8009000Dh
0x18002664a  jnz     loc_180026545
0x180026650  mov     rcx, [rbp+57h+phProv]; hProv
0x180026654  lea     r9, [rbp+57h+phKey]; phKey
0x180026658  mov     edx, 1; Algid
0x18002665d  mov     r8d, 8000001h; dwFlags
0x180026663  call    cs:__imp_CryptGenKey
0x18002666a  nop     dword ptr [rax+rax+00h]
0x18002666f  test    eax, eax
0x180026671  jz      loc_180026545
0x180026677  mov     rax, [r14]
0x18002667a  xor     r9d, r9d; dwFlags
0x18002667d  mov     rcx, [rbp+57h+phKey]; hKey
0x180026681  mov     r8d, r13d; dwBlobType
0x180026684  mov     [rsp+0D0h+pdwDataLen], rsi; pdwDataLen
0x180026689  xor     edx, edx; hExpKey
0x18002668b  mov     qword ptr [rsp+0D0h+dwFlags], rax; pbData
0x180026690  xor     ebx, ebx
0x180026692  call    cs:__imp_CryptExportKey
0x180026699  nop     dword ptr [rax+rax+00h]
0x18002669e  test    eax, eax
0x1800266a0  jnz     short loc_1800266B5
0x1800266a2  call    cs:__imp_GetLastError
0x1800266a9  nop     dword ptr [rax+rax+00h]
0x1800266ae  cmp     eax, 0EAh
0x1800266b3  jnz     short loc_1800266FA
0x1800266b5  mov     edx, [rsi]; uBytes
0x1800266b7  mov     ecx, 40h ; '@'; uFlags
0x1800266bc  call    cs:__imp_LocalAlloc
0x1800266c3  nop     dword ptr [rax+rax+00h]
0x1800266c8  mov     [r14], rax
0x1800266cb  test    rax, rax
0x1800266ce  jz      loc_1800265BA
0x1800266d4  mov     rcx, [rbp+57h+phKey]; hKey
0x1800266d8  xor     r9d, r9d; dwFlags
0x1800266db  mov     [rsp+0D0h+pdwDataLen], rsi; pdwDataLen
0x1800266e0  mov     r8d, r13d; dwBlobType
0x1800266e3  xor     edx, edx; hExpKey
0x1800266e5  mov     qword ptr [rsp+0D0h+dwFlags], rax; pbData
0x1800266ea  call    cs:__imp_CryptExportKey
0x1800266f1  nop     dword ptr [rax+rax+00h]
0x1800266f6  test    eax, eax
0x1800266f8  jnz     short loc_180026725
0x1800266fa  call    cs:__imp_GetLastError
0x180026701  nop     dword ptr [rax+rax+00h]
0x180026706  mov     edx, 0C0110005h; unsigned int
0x18002670b  movups  xmm0, cs:TLS_E_GENERATEKEYS
0x180026712  mov     r8d, eax
0x180026715  lea     rcx, [rbp+57h+var_80]; struct _EVENT_DESCRIPTOR
0x180026719  mov     ebx, eax
0x18002671b  movdqu  xmmword ptr [rbp+57h+var_80.Id], xmm0
0x180026720  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x180026725  mov     rcx, [rbp+57h+phUserKey]; hKey
0x180026729  test    rcx, rcx
0x18002672c  jz      short loc_18002673A
0x18002672e  call    cs:__imp_CryptDestroyKey
0x180026735  nop     dword ptr [rax+rax+00h]
0x18002673a  mov     rcx, [rbp+57h+phKey]; hKey
0x18002673e  test    rcx, rcx
0x180026741  jz      short loc_18002674F
0x180026743  call    cs:__imp_CryptDestroyKey
0x18002674a  nop     dword ptr [rax+rax+00h]
0x18002674f  mov     rcx, [rbp+57h+phProv]; hProv
0x180026753  test    rcx, rcx
0x180026756  jz      short loc_180026766
0x180026758  xor     edx, edx; dwFlags
0x18002675a  call    cs:__imp_CryptReleaseContext
0x180026761  nop     dword ptr [rax+rax+00h]
0x180026766  and     [rbp+57h+phProv], 0
0x18002676b  lea     r8, szProvider; "Microsoft Strong Cryptographic Provider"
0x180026772  mov     r9d, 1; dwProvType
0x180026778  mov     [rsp+0D0h+dwFlags], 30h ; '0'; dwFlags
0x180026780  lea     rdx, [rbp+57h+Buffer]; szContainer
0x180026784  lea     rcx, [rbp+57h+phProv]; phProv
0x180026788  call    cs:__imp_CryptAcquireContextW
0x18002678f  nop     dword ptr [rax+rax+00h]
0x180026794  test    ebx, ebx
0x180026796  jz      short loc_1800267C0
0x180026798  mov     rcx, [r15]; hMem
0x18002679b  test    rcx, rcx
0x18002679e  jz      short loc_1800267AC
0x1800267a0  call    cs:__imp_LocalFree
0x1800267a7  nop     dword ptr [rax+rax+00h]
0x1800267ac  mov     rcx, [r14]; hMem
0x1800267af  test    rcx, rcx
0x1800267b2  jz      short loc_1800267C0
0x1800267b4  call    cs:__imp_LocalFree
0x1800267bb  nop     dword ptr [rax+rax+00h]
0x1800267c0  mov     eax, ebx
0x1800267c2  mov     rcx, [rbp+57h+var_38]
0x1800267c6  xor     rcx, rsp; StackCookie
0x1800267c9  call    __security_check_cookie
0x1800267ce  add     rsp, 0A0h
0x1800267d5  pop     r15
0x1800267d7  pop     r14
0x1800267d9  pop     r13
0x1800267db  pop     rdi
  ... truncated ...
```
