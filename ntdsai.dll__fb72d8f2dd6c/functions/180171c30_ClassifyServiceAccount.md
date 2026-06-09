# ClassifyServiceAccount

- ea: `0x180171c30`
- end: `0x1801720f8`
- name: `ClassifyServiceAccount`
- size: `1224`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, void *, int, __int64, int)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f0728`
- `0x18015c66c`
- `0x180296f98`
- `0x18037cc18`

## callees

- `0x18001e090`
- `0x18001e0d0`
- `0x180021aa3`
- `0x180171c30`
- `0x180172a08`
- `0x180172b30`
- `0x180172edc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180171d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180171d16`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180171f38`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180171f38`
- `ntdll!RtlGetNtProductType` at `0x180171d0c`
- `ntdll!RtlGetNtProductType` at `0x180171d0c`
- `ntdll!RtlEqualSid` at `0x18017203e`
- `ntdll!RtlEqualSid` at `0x18017203e`
- `ntdll!RtlCopySid` at `0x180171d86`
- `ntdll!RtlCopySid` at `0x180171d86`
- `ntdll!RtlNtStatusToDosError` at `0x1801720c4`
- `ntdll!RtlNtStatusToDosError` at `0x1801720c4`
- `ntdll!RtlLengthSid` at `0x180171d6a`
- `ntdll!RtlLengthSid` at `0x180171d6a`
- `ADVAPI32!LsaOpenPolicy` at `0x180171d53`
- `ADVAPI32!LsaOpenPolicy` at `0x180171d53`
- `ADVAPI32!LsaLookupSids` at `0x180171db7`
- `ADVAPI32!LsaLookupSids` at `0x180171db7`
- `ADVAPI32!LsaClose` at `0x1801720b8`
- `ADVAPI32!LsaClose` at `0x1801720b8`
- `ADVAPI32!LsaFreeMemory` at `0x180171f7d`
- `ADVAPI32!LsaFreeMemory` at `0x180172058`
- `ADVAPI32!LsaFreeMemory` at `0x180172068`
- `ADVAPI32!LsaFreeMemory` at `0x180172078`
- `ADVAPI32!LsaFreeMemory` at `0x180172088`
- `ADVAPI32!LsaFreeMemory` at `0x180172098`
- `ADVAPI32!LsaFreeMemory` at `0x1801720a8`
- `ADVAPI32!LsaFreeMemory` at `0x180171f7d`
- `ADVAPI32!LsaFreeMemory` at `0x180172058`
- `ADVAPI32!LsaFreeMemory` at `0x180172068`
- `ADVAPI32!LsaFreeMemory` at `0x180172078`
- `ADVAPI32!LsaFreeMemory` at `0x180172088`
- `ADVAPI32!LsaFreeMemory` at `0x180172098`
- `ADVAPI32!LsaFreeMemory` at `0x1801720a8`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x180171e23`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x180171e54`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x180171e91`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x180171e23`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x180171e54`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x180171e91`
- `ADVAPI32!LsaLookupNames` at `0x180171fbc`
- `ADVAPI32!LsaLookupNames` at `0x180171fbc`

## pseudocode

```c
__int64 __fastcall ClassifyServiceAccount(
        void *a1,
        __int64 a2,
        _DWORD *a3,
        _DWORD *a4,
        int *a5,
        __int64 a6,
        _OWORD *a7,
        void *a8,
        unsigned int a9,
        void *a10,
        unsigned int a11)
{
  int v11; // ebx
  DWORD LastError; // edi
  PSID v15; // rbx
  PLSA_TRANSLATED_NAME v16; // rsi
  NTSTATUS v17; // eax
  int v18; // ecx
  _WORD *v19; // r13
  const void **v20; // rsi
  DWORD v21; // edx
  __int64 v22; // rdx
  DWORD nSize; // [rsp+30h] [rbp-D0h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+38h] [rbp-C8h] BYREF
  PVOID PolicyHandle; // [rsp+40h] [rbp-C0h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+48h] [rbp-B8h] BYREF
  PLSA_TRANSLATED_NAME Names; // [rsp+50h] [rbp-B0h] BYREF
  PVOID Buffer; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v30; // [rsp+60h] [rbp-A0h] BYREF
  BOOL v31; // [rsp+68h] [rbp-98h]
  PVOID v32; // [rsp+70h] [rbp-90h] BYREF
  PLSA_TRANSLATED_SID v33; // [rsp+78h] [rbp-88h] BYREF
  PSID Sid; // [rsp+80h] [rbp-80h]
  PSID Sids; // [rsp+88h] [rbp-78h] BYREF
  struct _LSA_UNICODE_STRING v36; // [rsp+90h] [rbp-70h] BYREF
  void *v37; // [rsp+A0h] [rbp-60h]
  _OWORD *v38; // [rsp+A8h] [rbp-58h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v40[264]; // [rsp+E0h] [rbp-20h] BYREF

  v11 = 0;
  *a3 = 0;
  Sid = a1;
  *a5 = 0;
  *(_OWORD *)a6 = 0;
  v38 = a7;
  *(_OWORD *)(a6 + 16) = 0;
  v37 = a10;
  *(_OWORD *)(a6 + 32) = 0;
  PolicyHandle = 0;
  *(_OWORD *)(a6 + 44) = 0;
  *(_DWORD *)a6 = 58;
  *a7 = 0;
  Buffer = 0;
  a7[1] = 0;
  v30 = 0;
  a7[2] = 0;
  v32 = 0;
  *(_OWORD *)((char *)a7 + 44) = 0;
  *(_DWORD *)a7 = 58;
  ReferencedDomains = 0;
  memset(&ObjectAttributes, 0, 44);
  Names = 0;
  nSize = 0;
  v36 = 0;
  v33 = 0;
  ProductType = 0;
  Sids = 0;
  if ( !RtlGetNtProductType(&ProductType) )
    goto LABEL_2;
  LastError = 0;
  v31 = ProductType == NtProductLanManNt;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v11 = LsaOpenPolicy(0, &ObjectAttributes, 0x801u, &PolicyHandle);
  if ( v11 >= 0 )
  {
    v15 = Sid;
    *(_DWORD *)(a6 + 4) = RtlLengthSid(Sid);
    Sid = (PSID)(a6 + 24);
    v11 = RtlCopySid(0x1Cu, (PSID)(a6 + 24), v15);
    if ( v11 >= 0 )
    {
      Sids = (PSID)(a6 + 24);
      v11 = LsaLookupSids(PolicyHandle, 1u, &Sids, &ReferencedDomains, &Names);
      if ( v11 >= 0 )
      {
        if ( a8 )
        {
          v16 = Names;
          if ( ((unsigned __int64)Names->Name.Length >> 1) + 1 > a9 )
          {
LABEL_8:
            LastError = 122;
            goto LABEL_38;
          }
          memcpy_0(a8, Names->Name.Buffer, Names->Name.Length);
          *((_WORD *)a8 + ((unsigned __int64)v16->Name.Length >> 1)) = 0;
        }
        v17 = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, &Buffer);
        v11 = v17;
        if ( v17 == -1073741772 )
          goto LABEL_15;
        if ( v17 < 0 )
          goto LABEL_38;
        if ( !*((_QWORD *)Buffer + 2) )
        {
LABEL_15:
          v18 = 0;
        }
        else
        {
          v11 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &v32);
          if ( v11 < 0 )
            goto LABEL_38;
          v18 = 2 - ((unsigned int)fNullUuid((char *)v32 + 48) != 0);
        }
        *a5 = v18;
        v11 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &v30);
        if ( v11 >= 0 )
        {
          v19 = v37;
          if ( v37 )
          {
            v20 = (const void **)Buffer;
            if ( !*a5 )
              v20 = (const void **)v30;
            if ( ((unsigned __int64)*(unsigned __int16 *)v20 >> 1) + 1 > a11 )
              goto LABEL_8;
            memcpy_0(v37, v20[1], *(unsigned __int16 *)v20);
            v19[(unsigned __int64)*(unsigned __int16 *)v20 >> 1] = 0;
          }
          if ( (unsigned int)IsNetworkServiceOrSystemSid(Sid) )
          {
            *a3 = (*a5 == 2) + 1;
            if ( a4 )
              *a4 = 1;
            if ( *a3 == 2 )
            {
              nSize = 261;
              if ( !GetComputerNameExW(ComputerNameNetBIOS, v40, &nSize) )
              {
LABEL_2:
                LastError = GetLastError();
                goto LABEL_38;
              }
              v21 = nSize;
              v40[nSize] = 36;
              v22 = v21 + 1;
              nSize = v22;
              if ( (unsigned __int64)(2 * v22) >= 0x20C )
                _report_rangecheckfailure();
              v40[v22] = 0;
              if ( ReferencedDomains )
              {
                LsaFreeMemory(ReferencedDomains);
                LOWORD(v22) = nSize;
                ReferencedDomains = 0;
              }
              v36.Buffer = v40;
              v36.Length = 2 * v22;
              v36.MaximumLength = 524;
              v11 = LsaLookupNames(PolicyHandle, 1u, &v36, &ReferencedDomains, &v33);
              if ( v11 >= 0 )
                MakeSid(ReferencedDomains->Domains[v33->DomainIndex].Sid);
            }
          }
          else
          {
            if ( a4 )
              *a4 = 0;
            if ( v31 )
              *a3 = 2;
            else
              *a3 = 2 - (RtlEqualSid(ReferencedDomains->Domains[Names->DomainIndex].Sid, *((PSID *)v30 + 2)) != 0);
          }
        }
      }
    }
  }
LABEL_38:
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( v30 )
    LsaFreeMemory(v30);
  if ( v32 )
    LsaFreeMemory(v32);
  if ( ReferencedDomains )
    LsaFreeMemory(ReferencedDomains);
  if ( Names )
    LsaFreeMemory(Names);
  if ( v33 )
    LsaFreeMemory(v33);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( v11 < 0 )
    return RtlNtStatusToDosError(v11);
  return LastError;
}

```

## disassembly

```asm
0x180171c30  mov     [rsp-8+arg_8], rbx
0x180171c35  push    rbp
0x180171c36  push    rsi
0x180171c37  push    rdi
0x180171c38  push    r12
0x180171c3a  push    r13
0x180171c3c  push    r14
0x180171c3e  push    r15
0x180171c40  lea     rbp, [rsp-200h]
0x180171c48  sub     rsp, 300h
0x180171c4f  mov     rax, cs:__security_cookie
0x180171c56  xor     rax, rsp
0x180171c59  mov     [rbp+230h+var_40], rax
0x180171c60  mov     rsi, [rbp+230h+arg_28]
0x180171c67  xor     ebx, ebx
0x180171c69  mov     rax, [rbp+230h+arg_48]
0x180171c70  xorps   xmm0, xmm0
0x180171c73  mov     r12, [rbp+230h+arg_20]
0x180171c7a  mov     r14, r9
0x180171c7d  mov     r13, [rbp+230h+arg_38]
0x180171c84  mov     r15, r8
0x180171c87  mov     [r8], ebx
0x180171c8a  lea     edx, [rbx+3Ah]
0x180171c8d  mov     [rbp+230h+Sid], rcx
0x180171c91  mov     rcx, [rbp+230h+arg_30]
0x180171c98  mov     [r12], ebx
0x180171c9c  movups  xmmword ptr [rsi], xmm0
0x180171c9f  mov     [rbp+230h+var_288], rcx
0x180171ca3  movups  xmmword ptr [rsi+10h], xmm0
0x180171ca7  mov     [rbp+230h+var_290], rax
0x180171cab  xor     eax, eax
0x180171cad  movups  xmmword ptr [rsi+20h], xmm0
0x180171cb1  mov     [rsp+330h+PolicyHandle], rbx
0x180171cb6  movups  xmmword ptr [rsi+2Ch], xmm0
0x180171cba  mov     [rsi], edx
0x180171cbc  movups  xmmword ptr [rcx], xmm0
0x180171cbf  mov     [rsp+330h+Buffer], rbx
0x180171cc4  movups  xmmword ptr [rcx+10h], xmm0
0x180171cc8  mov     [rsp+330h+var_2D0], rbx
0x180171ccd  movups  xmmword ptr [rcx+20h], xmm0
0x180171cd1  mov     [rsp+330h+var_2C0], rbx
0x180171cd6  movups  xmmword ptr [rcx+2Ch], xmm0
0x180171cda  mov     [rcx], edx
0x180171cdc  lea     rcx, [rsp+330h+ProductType]; ProductType
0x180171ce1  movups  xmmword ptr [rbp+230h+ObjectAttributes.ObjectName], xmm0
0x180171ce5  mov     [rsp+330h+ReferencedDomains], rbx
0x180171cea  movups  xmmword ptr [rbp+230h+ObjectAttributes.Length], xmm0
0x180171cee  mov     [rsp+330h+var_2E0], rbx
0x180171cf3  movups  xmmword ptr [rbp+230h+ObjectAttributes+1Ch], xmm0
0x180171cf7  mov     [rsp+330h+nSize], ebx
0x180171cfb  movups  xmmword ptr [rbp+230h+var_2A0.Length], xmm0
0x180171cff  mov     [rsp+330h+var_2B8], rbx
0x180171d04  mov     [rsp+330h+ProductType], ebx
0x180171d08  mov     [rbp+230h+Sids], rbx
0x180171d0c  call    cs:__imp_RtlGetNtProductType
0x180171d12  test    al, al
0x180171d14  jnz     short loc_180171D23
0x180171d16  call    cs:__imp_GetLastError
0x180171d1c  mov     edi, eax
0x180171d1e  jmp     loc_18017204E
0x180171d23  cmp     [rsp+330h+ProductType], 2
0x180171d28  lea     r9, [rsp+330h+PolicyHandle]; PolicyHandle
0x180171d2d  xorps   xmm0, xmm0
0x180171d30  lea     rdx, [rbp+230h+ObjectAttributes]; ObjectAttributes
0x180171d34  mov     eax, ebx
0x180171d36  mov     r8d, 801h; DesiredAccess
0x180171d3c  setz    al
0x180171d3f  mov     edi, ebx
0x180171d41  xor     ecx, ecx; SystemName
0x180171d43  mov     [rsp+330h+var_2C8], eax
0x180171d47  movups  xmmword ptr [rbp+230h+ObjectAttributes.Length], xmm0
0x180171d4b  movups  xmmword ptr [rbp+230h+ObjectAttributes.ObjectName], xmm0
0x180171d4f  movups  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x180171d53  call    cs:__imp_LsaOpenPolicy
0x180171d59  mov     ebx, eax
0x180171d5b  test    eax, eax
0x180171d5d  js      loc_18017204E
0x180171d63  mov     rbx, [rbp+230h+Sid]
0x180171d67  mov     rcx, rbx; Sid
0x180171d6a  call    cs:__imp_RtlLengthSid
0x180171d70  mov     [rsi+4], eax
0x180171d73  mov     r8, rbx; SourceSid
0x180171d76  add     rsi, 18h
0x180171d7a  mov     ecx, 1Ch; DestinationSidLength
0x180171d7f  mov     rdx, rsi; DestinationSid
0x180171d82  mov     [rbp+230h+Sid], rsi
0x180171d86  call    cs:__imp_RtlCopySid
0x180171d8c  mov     ebx, eax
0x180171d8e  test    eax, eax
0x180171d90  js      loc_18017204E
0x180171d96  mov     rcx, [rsp+330h+PolicyHandle]; PolicyHandle
0x180171d9b  lea     rax, [rsp+330h+var_2E0]
0x180171da0  lea     r9, [rsp+330h+ReferencedDomains]; ReferencedDomains
0x180171da5  mov     [rsp+330h+Names], rax; Names
0x180171daa  lea     r8, [rbp+230h+Sids]; Sids
0x180171dae  mov     [rbp+230h+Sids], rsi
0x180171db2  mov     edx, 1; Count
0x180171db7  call    cs:__imp_LsaLookupSids
0x180171dbd  mov     ebx, eax
0x180171dbf  test    eax, eax
0x180171dc1  js      loc_18017204E
0x180171dc7  test    r13, r13
0x180171dca  jz      short loc_180171E14
0x180171dcc  mov     rsi, [rsp+330h+var_2E0]
0x180171dd1  mov     eax, [rbp+230h+arg_40]
0x180171dd7  movzx   r8d, word ptr [rsi+8]; Size
0x180171ddc  mov     ecx, r8d
0x180171ddf  shr     rcx, 1
0x180171de2  inc     rcx
0x180171de5  cmp     rcx, rax
0x180171de8  jbe     short loc_180171DF4
0x180171dea  mov     edi, 7Ah ; 'z'
0x180171def  jmp     loc_18017204E
0x180171df4  mov     rdx, [rsp+330h+var_2E0]
0x180171df9  mov     rcx, r13; void *
0x180171dfc  mov     rdx, [rdx+10h]; Src
0x180171e00  call    memcpy_0
0x180171e05  movzx   ecx, word ptr [rsi+8]
0x180171e09  shr     rcx, 1
0x180171e0c  xor     eax, eax
0x180171e0e  mov     [r13+rcx*2+0], ax
0x180171e14  mov     rcx, [rsp+330h+PolicyHandle]; PolicyHandle
0x180171e19  lea     r8, [rsp+330h+Buffer]; Buffer
0x180171e1e  mov     edx, 3; InformationClass
0x180171e23  call    cs:__imp_LsaQueryInformationPolicy
0x180171e29  mov     ebx, eax
0x180171e2b  cmp     eax, 0C0000034h
0x180171e30  jz      short loc_180171E7B
0x180171e32  test    eax, eax
0x180171e34  js      loc_18017204E
0x180171e3a  mov     rax, [rsp+330h+Buffer]
0x180171e3f  cmp     [rax+10h], rdi
0x180171e43  jz      short loc_180171E7B
0x180171e45  mov     rcx, [rsp+330h+PolicyHandle]; PolicyHandle
0x180171e4a  lea     r8, [rsp+330h+var_2C0]; Buffer
0x180171e4f  mov     edx, 0Ch; InformationClass
0x180171e54  call    cs:__imp_LsaQueryInformationPolicy
0x180171e5a  mov     ebx, eax
0x180171e5c  test    eax, eax
0x180171e5e  js      loc_18017204E
0x180171e64  mov     rcx, [rsp+330h+var_2C0]
0x180171e69  add     rcx, 30h ; '0'
0x180171e6d  call    fNullUuid
0x180171e72  neg     eax
0x180171e74  sbb     ecx, ecx
0x180171e76  add     ecx, 2
0x180171e79  jmp     short loc_180171E7D
0x180171e7b  xor     ecx, ecx
0x180171e7d  mov     rax, r12
0x180171e80  lea     r8, [rsp+330h+var_2D0]; Buffer
0x180171e85  mov     edx, 5; InformationClass
0x180171e8a  mov     [rax], ecx
0x180171e8c  mov     rcx, [rsp+330h+PolicyHandle]; PolicyHandle
0x180171e91  call    cs:__imp_LsaQueryInformationPolicy
0x180171e97  mov     ebx, eax
0x180171e99  test    eax, eax
0x180171e9b  js      loc_18017204E
0x180171ea1  mov     r13, [rbp+230h+var_290]
0x180171ea5  test    r13, r13
0x180171ea8  jz      short loc_180171EEF
0x180171eaa  cmp     [r12], edi
0x180171eae  mov     rsi, [rsp+330h+Buffer]
0x180171eb3  cmovz   rsi, [rsp+330h+var_2D0]
0x180171eb9  mov     eax, [rbp+230h+arg_50]
0x180171ebf  movzx   r8d, word ptr [rsi]; Size
0x180171ec3  mov     ecx, r8d
0x180171ec6  shr     rcx, 1
0x180171ec9  inc     rcx
0x180171ecc  cmp     rcx, rax
0x180171ecf  ja      loc_180171DEA
0x180171ed5  mov     rdx, [rsi+8]; Src
0x180171ed9  mov     rcx, r13; void *
0x180171edc  call    memcpy_0
0x180171ee1  movzx   edx, word ptr [rsi]
0x180171ee4  shr     rdx, 1
0x180171ee7  xor     eax, eax
0x180171ee9  mov     [r13+rdx*2+0], ax
0x180171eef  mov     rcx, [rbp+230h+Sid]; Sid
0x180171ef3  call    IsNetworkServiceOrSystemSid
0x180171ef8  test    eax, eax
0x180171efa  jz      loc_180172003
0x180171f00  xor     eax, eax
0x180171f02  cmp     dword ptr [r12], 2
0x180171f07  setz    al
0x180171f0a  inc     eax
0x180171f0c  mov     [r15], eax
0x180171f0f  test    r14, r14
0x180171f12  jz      short loc_180171F1B
0x180171f14  mov     dword ptr [r14], 1
0x180171f1b  cmp     dword ptr [r15], 2
0x180171f1f  jnz     loc_18017204E
0x180171f25  lea     r8, [rsp+330h+nSize]; nSize
0x180171f2a  mov     [rsp+330h+nSize], 105h
0x180171f32  lea     rdx, [rbp+230h+var_250]; lpBuffer
0x180171f36  xor     ecx, ecx; NameType
0x180171f38  call    cs:__imp_GetComputerNameExW
0x180171f3e  test    eax, eax
0x180171f40  jz      loc_180171D16
0x180171f46  mov     edx, [rsp+330h+nSize]
0x180171f4a  mov     ecx, 24h ; '$'
0x180171f4f  mov     ebx, 20Ch
0x180171f54  mov     [rbp+rdx*2+230h+var_250], cx
0x180171f59  inc     edx
0x180171f5b  mov     [rsp+330h+nSize], edx
0x180171f5f  lea     rcx, [rdx+rdx]
0x180171f63  cmp     rcx, rbx
0x180171f66  jnb     loc_180171FFD
0x180171f6c  xor     eax, eax
0x180171f6e  mov     [rbp+rcx+230h+var_250], ax
0x180171f73  mov     rcx, [rsp+330h+ReferencedDomains]; Buffer
0x180171f78  test    rcx, rcx
0x180171f7b  jz      short loc_180171F8C
0x180171f7d  call    cs:__imp_LsaFreeMemory
0x180171f83  mov     edx, [rsp+330h+nSize]
0x180171f87  mov     [rsp+330h+ReferencedDomains], rdi
0x180171f8c  mov     rcx, [rsp+330h+PolicyHandle]; PolicyHandle
0x180171f91  lea     rax, [rbp+230h+var_250]
0x180171f95  add     dx, dx
0x180171f98  mov     [rbp+230h+var_2A0.Buffer], rax
0x180171f9c  lea     rax, [rsp+330h+var_2B8]
0x180171fa1  mov     [rbp+230h+var_2A0.Length], dx
0x180171fa5  lea     r9, [rsp+330h+ReferencedDomains]; ReferencedDomains
0x180171faa  mov     [rsp+330h+Names], rax; Sids
0x180171faf  lea     r8, [rbp+230h+var_2A0]; Names
0x180171fb3  mov     [rbp+230h+var_2A0.MaximumLength], bx
0x180171fb7  mov     edx, 1; Count
0x180171fbc  call    cs:__imp_LsaLookupNames
0x180171fc2  mov     ebx, eax
0x180171fc4  test    eax, eax
0x180171fc6  js      loc_18017204E
0x180171fcc  mov     rdx, [rsp+330h+var_2B8]
0x180171fd1  mov     r8, [rbp+230h+var_288]
0x180171fd5  movsxd  rax, dword ptr [rdx+8]
0x180171fd9  mov     edx, [rdx+4]
0x180171fdc  lea     r9, [r8+4]
0x180171fe0  add     r8, 18h
0x180171fe4  lea     r10, [rax+rax*2]
0x180171fe8  mov     rax, [rsp+330h+ReferencedDomains]
0x180171fed  mov     rcx, [rax+8]
0x180171ff1  mov     rcx, [rcx+r10*8+10h]; Src
0x180171ff6  call    MakeSid
0x180171ffb  jmp     short loc_18017204E
0x180171ffd  call    __report_rangecheckfailure
0x180172003  test    r14, r14
0x180172006  jz      short loc_18017200B
0x180172008  mov     [r14], edi
0x18017200b  cmp     [rsp+330h+var_2C8], edi
0x18017200f  jz      short loc_18017201A
0x180172011  mov     dword ptr [r15], 2
0x180172018  jmp     short loc_18017204E
0x18017201a  mov     rax, [rsp+330h+var_2E0]
0x18017201f  mov     rdx, [rsp+330h+var_2D0]
0x180172024  movsxd  rcx, dword ptr [rax+18h]
0x180172028  mov     rax, [rsp+330h+ReferencedDomains]
0x18017202d  mov     rdx, [rdx+10h]; Sid2
0x180172031  lea     r8, [rcx+rcx*2]
0x180172035  mov     rcx, [rax+8]
0x180172039  mov     rcx, [rcx+r8*8+10h]; Sid1
0x18017203e  call    cs:__imp_RtlEqualSid
0x180172044  neg     al
0x180172046  sbb     ecx, ecx
0x180172048  add     ecx, 2
0x18017204b  mov     [r15], ecx
0x18017204e  mov     rcx, [rsp+330h+Buffer]; Buffer
0x180172053  test    rcx, rcx
0x180172056  jz      short loc_18017205E
0x180172058  call    cs:__imp_LsaFreeMemory
0x18017205e  mov     rcx, [rsp+330h+var_2D0]; Buffer
0x180172063  test    rcx, rcx
0x180172066  jz      short loc_18017206E
0x180172068  call    cs:__imp_LsaFreeMemory
0x18017206e  mov     rcx, [rsp+330h+var_2C0]; Buffer
0x180172073  test    rcx, rcx
0x180172076  jz      short loc_18017207E
0x180172078  call    cs:__imp_LsaFreeMemory
0x18017207e  mov     rcx, [rsp+330h+ReferencedDomains]; Buffer
0x180172083  test    rcx, rcx
0x180172086  jz      short loc_18017208E
0x180172088  call    cs:__imp_LsaFreeMemory
0x18017208e  mov     rcx, [rsp+330h+var_2E0]; Buffer
0x180172093  test    rcx, rcx
0x180172096  jz      short loc_18017209E
0x180172098  call    cs:__imp_LsaFreeMemory
0x18017209e  mov     rcx, [rsp+330h+var_2B8]; Buffer
0x1801720a3  test    rcx, rcx
0x1801720a6  jz      short loc_1801720AE
0x1801720a8  call    cs:__imp_LsaFreeMemory
0x1801720ae  mov     rcx, [rsp+330h+PolicyHandle]; ObjectHandle
0x1801720b3  test    rcx, rcx
0x1801720b6  jz      short loc_1801720BE
0x1801720b8  call    cs:__imp_LsaClose
0x1801720be  test    ebx, ebx
0x1801720c0  jns     short loc_1801720CC
0x1801720c2  mov     ecx, ebx; Status
0x1801720c4  call    cs:__imp_RtlNtStatusToDosError
0x1801720ca  mov     edi, eax
0x1801720cc  mov     eax, edi
0x1801720ce  mov     rcx, [rbp+230h+var_40]
0x1801720d5  xor     rcx, rsp; StackCookie
0x1801720d8  call    __security_check_cookie
  ... truncated ...
```
