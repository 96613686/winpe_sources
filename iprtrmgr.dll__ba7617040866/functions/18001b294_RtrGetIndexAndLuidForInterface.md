# RtrGetIndexAndLuidForInterface

- ea: `0x18001b294`
- end: `0x18001b698`
- name: `RtrGetIndexAndLuidForInterface`
- size: `1028`
- prototype: `__int64 __usercall@<rax>(LPCWCH lpWideCharStr@<rcx>, PNET_LUID InterfaceLuid, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180015e5c`

## callees

- `0x180011790`
- `0x18001b294`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x18001b634`
- `KERNEL32!CompareStringA` at `0x18001b634`
- `KERNEL32!LocalFree` at `0x18001b521`
- `KERNEL32!LocalFree` at `0x18001b665`
- `KERNEL32!LocalFree` at `0x18001b521`
- `KERNEL32!LocalFree` at `0x18001b665`
- `KERNEL32!LocalAlloc` at `0x18001b4e8`
- `KERNEL32!LocalAlloc` at `0x18001b4e8`
- `KERNEL32!WideCharToMultiByte` at `0x18001b445`
- `KERNEL32!WideCharToMultiByte` at `0x18001b445`
- `KERNEL32!GetLastError` at `0x18001b44f`
- `KERNEL32!GetLastError` at `0x18001b52b`
- `KERNEL32!GetLastError` at `0x18001b44f`
- `KERNEL32!GetLastError` at `0x18001b52b`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18001b64e`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18001b64e`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18001b489`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18001b511`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18001b489`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18001b511`

## pseudocode

```c
__int64 __fastcall RtrGetIndexAndLuidForInterface(
        LPCWCH lpWideCharStr,
        __int64 *a2,
        __int64 a3,
        NET_IFINDEX *a4,
        PNET_LUID InterfaceLuid,
        int a6)
{
  unsigned int v9; // r12d
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  DWORD LastError; // eax
  DWORD v14; // ebx
  const wchar_t *v15; // rdx
  __int64 *v16; // rdx
  ULONG *v17; // r9
  __int64 v18; // r9
  ULONG AdaptersAddresses; // eax
  IP_ADAPTER_ADDRESSES_LH *v20; // rsi
  int v21; // r14d
  ULONG *v22; // r9
  ULONG *v23; // r9
  IP_ADAPTER_ADDRESSES_LH *i; // rbx
  NET_IFINDEX IfIndex; // ecx
  ULONG SizePointer; // [rsp+48h] [rbp-C0h] BYREF
  ULONG SizePointer_8[4]; // [rsp+50h] [rbp-B8h] BYREF
  int v29; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v30; // [rsp+64h] [rbp-A4h]
  __int128 v31; // [rsp+74h] [rbp-94h]
  int v32; // [rsp+84h] [rbp-84h]
  CHAR MultiByteStr[48]; // [rsp+88h] [rbp-80h] BYREF
  int v34; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v35[2044]; // [rsp+BCh] [rbp-4Ch] BYREF

  SizePointer = 0;
  v34 = 0;
  v9 = a6 != 0 ? 0xFFFFFFEB : 0;
  memset_0(v35, 0, sizeof(v35));
  v11 = *a2;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  *(_OWORD *)SizePointer_8 = 0;
  v12 = v11 - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v12 )
    v12 = a2[1] - _mm_srli_si128((__m128i)GUID_NULL, 8).m128i_u64[0];
  if ( v12 )
  {
    LastError = ((__int64 (__fastcall *)(__int64, PNET_LUID, NET_IFINDEX *))GetInfoForTenantInterface)(
                  a3,
                  InterfaceLuid,
                  a4);
    v14 = LastError;
    if ( LastError )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return v14;
      v15 = L"RtrGetIndexAndLuidForInterface: GetInfoForTenantInterface failed with error %d \n";
      goto LABEL_7;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return v14;
    v18 = *a4;
    LOWORD(v34) = 0;
    LOWORD(v29) = 0;
    FormatRRASErrorString(
      &v34,
      L"RtrGetIndexAndLuidForInterface: Interface index for multi-tenant interface %ws is %d",
      lpWideCharStr,
      v18);
LABEL_14:
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return v14;
    v16 = RasRtrmgrParamTraceInfo;
LABEL_9:
    v17 = SizePointer_8;
    if ( a2 )
      LODWORD(v17) = (_DWORD)a2;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (_DWORD)v16,
      (unsigned int)&v34,
      (_DWORD)v17,
      0,
      (__int64)&v29);
    return v14;
  }
  if ( !WideCharToMultiByte(0, 0x400u, lpWideCharStr, -1, MultiByteStr, 39, 0, 0) )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return v14;
    v15 = L"Converting the adapter index to utf7 failed with error %d\n";
LABEL_7:
    LOWORD(v29) = 0;
    LOWORD(v34) = 0;
    FormatRRASErrorString(&v34, v15, LastError);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return v14;
    v16 = RasRtrMgrParamTraceError;
    goto LABEL_9;
  }
  AdaptersAddresses = GetAdaptersAddresses(v9 + 23, 0x2Fu, 0, 0, &SizePointer);
  v14 = AdaptersAddresses;
  if ( AdaptersAddresses != 111 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return v14;
    LOWORD(v34) = 0;
    LOWORD(v29) = 0;
    FormatRRASErrorString(
      &v34,
      L"GetAdaptersAddresses for getting interface index returns %d for querying the buffer size",
      AdaptersAddresses);
    goto LABEL_14;
  }
  v20 = 0;
  v21 = 3;
  while ( v14 == 111 )
  {
    if ( !v21 )
      goto LABEL_34;
    v20 = (IP_ADAPTER_ADDRESSES_LH *)LocalAlloc(0x40u, SizePointer);
    if ( !v20 )
    {
      v14 = GetLastError();
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v34) = 0;
        LOWORD(v29) = 0;
        FormatRRASErrorString(&v34, L"Unable to allocate memory for the GetAdaptersAddresses buffer: %d", v14);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v22 = SizePointer_8;
          if ( a2 )
            LODWORD(v22) = (_DWORD)a2;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v34,
            (_DWORD)v22,
            0,
            (__int64)&v29);
        }
      }
      break;
    }
    --v21;
    v14 = GetAdaptersAddresses(v9 + 23, 0x2Fu, 0, v20, &SizePointer);
    if ( v14 == 111 )
    {
      LocalFree(v20);
      v20 = 0;
    }
  }
  if ( v14 )
  {
LABEL_34:
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v34) = 0;
      LOWORD(v29) = 0;
      FormatRRASErrorString(&v34, L"GetAdaptersAddresses fails with %d\n", v14);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v23 = SizePointer_8;
        if ( a2 )
          LODWORD(v23) = (_DWORD)a2;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v34,
          (_DWORD)v23,
          0,
          (__int64)&v29);
      }
    }
    goto LABEL_45;
  }
  for ( i = v20; i; i = i->Next )
  {
    if ( CompareStringA(0x7Fu, 1u, MultiByteStr, -1, i->AdapterName, -1) == 2 )
    {
      IfIndex = i->IfIndex;
      *a4 = IfIndex;
      v14 = ConvertInterfaceIndexToLuid(IfIndex, InterfaceLuid);
      goto LABEL_45;
    }
  }
  v14 = 1168;
LABEL_45:
  if ( v20 )
    LocalFree(v20);
  return v14;
}

```

## disassembly

```asm
0x18001b294  mov     rax, rsp
0x18001b297  push    rbp
0x18001b298  push    rbx
0x18001b299  push    rsi
0x18001b29a  push    rdi
0x18001b29b  push    r12
0x18001b29d  push    r13
0x18001b29f  push    r14
0x18001b2a1  push    r15
0x18001b2a3  lea     rbp, [rax-818h]
0x18001b2aa  sub     rsp, 8D8h
0x18001b2b1  movaps  xmmword ptr [rax-58h], xmm6
0x18001b2b5  mov     rax, cs:__security_cookie
0x18001b2bc  xor     rax, rsp
0x18001b2bf  mov     [rbp+810h+var_60], rax
0x18001b2c6  mov     r13, [rbp+810h+InterfaceLuid]
0x18001b2cd  xor     r14d, r14d
0x18001b2d0  neg     [rbp+810h+arg_28]
0x18001b2d6  mov     rbx, r8
0x18001b2d9  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18001b2e0  sbb     r12d, r12d
0x18001b2e3  mov     [rsp+910h+SizePointer], r14d
0x18001b2e8  mov     rdi, rdx
0x18001b2eb  mov     [rbp+810h+var_860], r14d
0x18001b2ef  mov     rsi, rcx
0x18001b2f2  xor     edx, edx; Val
0x18001b2f4  mov     r8d, 7FCh; Size
0x18001b2fa  lea     rcx, [rbp+810h+var_85C]; void *
0x18001b2fe  and     r12d, 0FFFFFFEBh
0x18001b302  mov     r15, r9
0x18001b305  call    memset_0
0x18001b30a  mov     rcx, [rdi]
0x18001b30d  xor     eax, eax
0x18001b30f  xorps   xmm0, xmm0
0x18001b312  mov     [rsp+910h+var_894], eax
0x18001b316  movq    rax, xmm6
0x18001b31b  mov     dword ptr [rsp+910h+var_8BC+4], r14d
0x18001b320  movups  [rsp+910h+var_8BC+8], xmm0
0x18001b325  movups  [rsp+910h+var_8AC+8], xmm0
0x18001b32a  movups  xmmword ptr [rsp+910h+SizePointer+8], xmm0
0x18001b32f  sub     rcx, rax
0x18001b332  jnz     short loc_18001B345
0x18001b334  mov     rcx, [rdi+8]
0x18001b338  psrldq  xmm6, 8
0x18001b33d  movq    rax, xmm6
0x18001b342  sub     rcx, rax
0x18001b345  test    rcx, rcx
0x18001b348  jz      loc_18001B41C
0x18001b34e  mov     rax, cs:GetInfoForTenantInterface
0x18001b355  mov     r8, r15
0x18001b358  mov     rdx, r13
0x18001b35b  mov     rcx, rbx
0x18001b35e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b363  mov     ebx, eax
0x18001b365  test    eax, eax
0x18001b367  jz      short loc_18001B3D8
0x18001b369  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001b370  jz      loc_18001B66B
0x18001b376  lea     rdx, aRtrgetindexand; "RtrGetIndexAndLuidForInterface: GetInfo"...
0x18001b37d  mov     r8d, eax
0x18001b380  mov     word ptr [rsp+910h+var_8BC+4], r14w
0x18001b386  lea     rcx, [rbp+810h+var_860]
0x18001b38a  mov     word ptr [rbp+810h+var_860], r14w
0x18001b38f  call    FormatRRASErrorString
0x18001b394  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001b39b  jz      loc_18001B66B
0x18001b3a1  lea     rdx, RasRtrMgrParamTraceError
0x18001b3a8  test    rdi, rdi
0x18001b3ab  lea     rax, [rsp+910h+var_8BC+4]
0x18001b3b0  mov     qword ptr [rsp+910h+cbMultiByte], rax
0x18001b3b5  lea     r9, [rsp+910h+SizePointer+8]
0x18001b3ba  cmovnz  r9, rdi
0x18001b3be  mov     [rsp+910h+lpMultiByteStr], r14
0x18001b3c3  lea     r8, [rbp+810h+var_860]
0x18001b3c7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001b3ce  call    McTemplateU0zjzz_EventWriteTransfer
0x18001b3d3  jmp     loc_18001B66B
0x18001b3d8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18001b3df  jge     loc_18001B66B
0x18001b3e5  mov     r9d, [r15]
0x18001b3e8  lea     rdx, aRtrgetindexand_0; "RtrGetIndexAndLuidForInterface: Interfa"...
0x18001b3ef  mov     r8, rsi
0x18001b3f2  mov     word ptr [rbp+810h+var_860], r14w
0x18001b3f7  lea     rcx, [rbp+810h+var_860]
0x18001b3fb  mov     word ptr [rsp+910h+var_8BC+4], r14w
0x18001b401  call    FormatRRASErrorString
0x18001b406  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18001b40d  jge     loc_18001B66B
0x18001b413  lea     rdx, RasRtrmgrParamTraceInfo
0x18001b41a  jmp     short loc_18001B3A8
0x18001b41c  mov     [rsp+910h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18001b421  lea     rax, [rbp+810h+MultiByteStr]
0x18001b425  mov     [rsp+910h+lpDefaultChar], r14; lpDefaultChar
0x18001b42a  or      r9d, 0FFFFFFFFh; cchWideChar
0x18001b42e  mov     [rsp+910h+cbMultiByte], 27h ; '''; cbMultiByte
0x18001b436  mov     r8, rsi; lpWideCharStr
0x18001b439  mov     edx, 400h; dwFlags
0x18001b43e  mov     [rsp+910h+lpMultiByteStr], rax; lpMultiByteStr
0x18001b443  xor     ecx, ecx; CodePage
0x18001b445  call    cs:__imp_WideCharToMultiByte
0x18001b44b  test    eax, eax
0x18001b44d  jnz     short loc_18001B470
0x18001b44f  call    cs:__imp_GetLastError
0x18001b455  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001b45c  mov     ebx, eax
0x18001b45e  jz      loc_18001B66B
0x18001b464  lea     rdx, aConvertingTheA; "Converting the adapter index to utf7 fa"...
0x18001b46b  jmp     loc_18001B37D
0x18001b470  xor     r9d, r9d; AdapterAddresses
0x18001b473  lea     rax, [rsp+910h+SizePointer]
0x18001b478  xor     r8d, r8d; Reserved
0x18001b47b  mov     [rsp+910h+lpMultiByteStr], rax; SizePointer
0x18001b480  lea     ecx, [r12+17h]; Family
0x18001b485  lea     edx, [r9+2Fh]; Flags
0x18001b489  call    cs:__imp_GetAdaptersAddresses
0x18001b48f  mov     ebx, eax
0x18001b491  cmp     eax, 6Fh ; 'o'
0x18001b494  jz      short loc_18001B4C6
0x18001b496  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18001b49d  jge     loc_18001B66B
0x18001b4a3  mov     r8d, eax
0x18001b4a6  mov     word ptr [rbp+810h+var_860], r14w
0x18001b4ab  lea     rdx, aGetadaptersadd_0; "GetAdaptersAddresses for getting interf"...
0x18001b4b2  mov     word ptr [rsp+910h+var_8BC+4], r14w
0x18001b4b8  lea     rcx, [rbp+810h+var_860]
0x18001b4bc  call    FormatRRASErrorString
0x18001b4c1  jmp     loc_18001B406
0x18001b4c6  mov     rsi, r14
0x18001b4c9  mov     r14d, 3
0x18001b4cf  cmp     ebx, 6Fh ; 'o'
0x18001b4d2  jnz     loc_18001B599
0x18001b4d8  test    r14d, r14d
0x18001b4db  jz      loc_18001B59D
0x18001b4e1  mov     edx, [rsp+910h+SizePointer]; uBytes
0x18001b4e5  lea     ecx, [rbx-2Fh]; uFlags
0x18001b4e8  call    cs:__imp_LocalAlloc
0x18001b4ee  mov     rsi, rax
0x18001b4f1  test    rax, rax
0x18001b4f4  jz      short loc_18001B52B
0x18001b4f6  lea     rax, [rsp+910h+SizePointer]
0x18001b4fb  mov     r9, rsi; AdapterAddresses
0x18001b4fe  xor     r8d, r8d; Reserved
0x18001b501  mov     [rsp+910h+lpMultiByteStr], rax; SizePointer
0x18001b506  lea     edx, [rbx-40h]; Flags
0x18001b509  dec     r14d
0x18001b50c  lea     ecx, [r12+17h]; Family
0x18001b511  call    cs:__imp_GetAdaptersAddresses
0x18001b517  mov     ebx, eax
0x18001b519  cmp     eax, 6Fh ; 'o'
0x18001b51c  jnz     short loc_18001B4CF
0x18001b51e  mov     rcx, rsi; hMem
0x18001b521  call    cs:__imp_LocalFree
0x18001b527  xor     esi, esi
0x18001b529  jmp     short loc_18001B4CF
0x18001b52b  call    cs:__imp_GetLastError
0x18001b531  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001b538  mov     ebx, eax
0x18001b53a  jz      short loc_18001B599
0x18001b53c  xor     eax, eax
0x18001b53e  lea     rdx, aUnableToAlloca; "Unable to allocate memory for the GetAd"...
0x18001b545  mov     r8d, ebx
0x18001b548  mov     word ptr [rbp+810h+var_860], ax
0x18001b54c  lea     rcx, [rbp+810h+var_860]
0x18001b550  mov     word ptr [rsp+910h+var_8BC+4], ax
0x18001b555  call    FormatRRASErrorString
0x18001b55a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001b561  jz      short loc_18001B599
0x18001b563  test    rdi, rdi
0x18001b566  lea     rax, [rsp+910h+var_8BC+4]
0x18001b56b  mov     qword ptr [rsp+910h+cbMultiByte], rax
0x18001b570  lea     r9, [rsp+910h+SizePointer+8]
0x18001b575  cmovnz  r9, rdi
0x18001b579  mov     [rsp+910h+lpMultiByteStr], 0
0x18001b582  lea     r8, [rbp+810h+var_860]
0x18001b586  lea     rdx, RasRtrMgrParamTraceError
0x18001b58d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001b594  call    McTemplateU0zjzz_EventWriteTransfer
0x18001b599  test    ebx, ebx
0x18001b59b  jz      short loc_18001B60D
0x18001b59d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001b5a4  jz      loc_18001B65D
0x18001b5aa  xor     eax, eax
0x18001b5ac  lea     rdx, aGetadaptersadd; "GetAdaptersAddresses fails with %d\n"
0x18001b5b3  mov     r8d, ebx
0x18001b5b6  mov     word ptr [rbp+810h+var_860], ax
0x18001b5ba  lea     rcx, [rbp+810h+var_860]
0x18001b5be  mov     word ptr [rsp+910h+var_8BC+4], ax
0x18001b5c3  call    FormatRRASErrorString
0x18001b5c8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001b5cf  jz      loc_18001B65D
0x18001b5d5  test    rdi, rdi
0x18001b5d8  lea     rax, [rsp+910h+var_8BC+4]
0x18001b5dd  mov     qword ptr [rsp+910h+cbMultiByte], rax
0x18001b5e2  lea     r9, [rsp+910h+SizePointer+8]
0x18001b5e7  cmovnz  r9, rdi
0x18001b5eb  mov     [rsp+910h+lpMultiByteStr], 0
0x18001b5f4  lea     r8, [rbp+810h+var_860]
0x18001b5f8  lea     rdx, RasRtrMgrParamTraceError
0x18001b5ff  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001b606  call    McTemplateU0zjzz_EventWriteTransfer
0x18001b60b  jmp     short loc_18001B65D
0x18001b60d  mov     rbx, rsi
0x18001b610  or      edi, 0FFFFFFFFh
0x18001b613  test    rbx, rbx
0x18001b616  jz      short loc_18001B658
0x18001b618  mov     rax, [rbx+10h]
0x18001b61c  lea     r8, [rbp+810h+MultiByteStr]; lpString1
0x18001b620  mov     edx, 1; dwCmpFlags
0x18001b625  mov     [rsp+910h+cbMultiByte], edi; cchCount2
0x18001b629  mov     r9d, edi; cchCount1
0x18001b62c  mov     [rsp+910h+lpMultiByteStr], rax; lpString2
0x18001b631  lea     ecx, [rdx+7Eh]; Locale
0x18001b634  call    cs:__imp_CompareStringA
0x18001b63a  cmp     eax, 2
0x18001b63d  jz      short loc_18001B645
0x18001b63f  mov     rbx, [rbx+8]
0x18001b643  jmp     short loc_18001B613
0x18001b645  mov     ecx, [rbx+4]; InterfaceIndex
0x18001b648  mov     rdx, r13; InterfaceLuid
0x18001b64b  mov     [r15], ecx
0x18001b64e  call    cs:__imp_ConvertInterfaceIndexToLuid
0x18001b654  mov     ebx, eax
0x18001b656  jmp     short loc_18001B65D
0x18001b658  mov     ebx, 490h
0x18001b65d  test    rsi, rsi
0x18001b660  jz      short loc_18001B66B
0x18001b662  mov     rcx, rsi; hMem
0x18001b665  call    cs:__imp_LocalFree
0x18001b66b  mov     eax, ebx
0x18001b66d  mov     rcx, [rbp+810h+var_60]
0x18001b674  xor     rcx, rsp; StackCookie
0x18001b677  call    __security_check_cookie
0x18001b67c  movaps  xmm6, [rsp+910h+var_58+8]
0x18001b684  add     rsp, 8D8h
0x18001b68b  pop     r15
0x18001b68d  pop     r14
0x18001b68f  pop     r13
0x18001b691  pop     r12
0x18001b693  pop     rdi
0x18001b694  pop     rsi
0x18001b695  pop     rbx
0x18001b696  pop     rbp
0x18001b697  retn
```
