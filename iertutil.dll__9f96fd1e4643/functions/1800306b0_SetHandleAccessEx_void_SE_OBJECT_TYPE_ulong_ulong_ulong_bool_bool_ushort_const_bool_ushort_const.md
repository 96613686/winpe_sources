# _SetHandleAccessEx(void *,_SE_OBJECT_TYPE,ulong,ulong,ulong,bool,bool,ushort const *,bool *,ushort const *)

- ea: `0x1800306b0`
- end: `0x180030a41`
- name: `?_SetHandleAccessEx@@YAJPEAXW4_SE_OBJECT_TYPE@@KKK_N2PEBGPEA_N3@Z`
- size: `913`
- prototype: `__int64 __usercall@<rax>(HANDLE Handle@<rcx>, enum _SE_OBJECT_TYPE@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, bool, bool, const unsigned __int16 *, bool *, const unsigned __int16 *)`
- caller_count: `10`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002fd10`
- `0x18002fdd8`
- `0x180030620`
- `0x180031c10`
- `0x18005ed10`
- `0x18005ed80`
- `0x18005ee20`
- `0x18005ee90`
- `0x180065e10`
- `0x180065e9c`

## callees

- `0x1800306b0`
- `0x180030a48`
- `0x180030b00`
- `0x180030b64`
- `0x1800321a0`
- `0x180032348`
- `0x18004ae00`
- `0x180050060`
- `0x1800655c0`
- `0x180065694`
- `0x180065714`
- `0x180065794`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030763`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003084e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030862`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030918`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003084e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030862`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030918`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003072b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003072b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800308b1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800308b1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18003094f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18003094f`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800306f6`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180030755`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800306f6`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180030755`

## pseudocode

```c
__int64 __fastcall _SetHandleAccessEx(
        HANDLE Handle,
        enum _SE_OBJECT_TYPE a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        bool a6,
        bool a7,
        const unsigned __int16 *a8,
        bool *a9,
        unsigned __int16 *a10)
{
  int v10; // r12d
  signed int v14; // ebx
  signed int LastError; // eax
  __int64 v16; // rcx
  HLOCAL v17; // r15
  bool v18; // cc
  unsigned int v19; // edi
  unsigned int CurrentUserSid; // eax
  struct _ACL *v21; // rcx
  bool v22; // r14
  struct _ACL *v23; // rsi
  unsigned int v24; // r12d
  bool HasSIDCheckAndSetAccess; // al
  bool v26; // al
  struct _ACL *v27; // rdx
  struct _ACL *v29; // rcx
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int lpnLengthNeeded; // [rsp+20h] [rbp-40h]
  bool v33; // [rsp+30h] [rbp-30h] BYREF
  char v34; // [rsp+31h] [rbp-2Fh]
  char v35; // [rsp+32h] [rbp-2Eh]
  PSID pSid; // [rsp+38h] [rbp-28h] BYREF
  SIZE_T uBytes; // [rsp+40h] [rbp-20h] BYREF
  PACL pDacl; // [rsp+48h] [rbp-18h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+50h] [rbp-10h] BYREF
  WINBOOL bDaclPresent; // [rsp+54h] [rbp-Ch] BYREF
  struct _ACL *v41; // [rsp+58h] [rbp-8h] BYREF

  v10 = 0;
  pDacl = 0;
  LODWORD(uBytes) = 0;
  if ( GetKernelObjectSecurity(Handle, 4u, 0, 0, (LPDWORD)&uBytes) )
    return (unsigned int)-2147418113;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  LastError = GetLastError();
  v14 = LastError;
  if ( LastError == 122 || (v18 = LastError <= 0, !LastError) )
  {
    v17 = LocalAlloc(0x40u, (unsigned int)uBytes);
    if ( !v17 )
      return (unsigned int)-2147024882;
    if ( GetKernelObjectSecurity(Handle, 4u, v17, uBytes, (LPDWORD)&uBytes) )
    {
      v14 = 0;
      if ( GetSecurityDescriptorDacl(v17, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        goto LABEL_10;
    }
    LastError = GetLastError();
    v18 = LastError <= 0;
    v14 = LastError;
  }
  else
  {
    v17 = 0;
  }
  if ( !v18 )
    v14 = (unsigned __int16)LastError | 0x80070000;
  v19 = 0;
  if ( v14 )
    goto LABEL_28;
LABEL_10:
  v35 = 1;
  v34 = 0;
  pSid = 0;
  if ( a5 )
  {
    if ( a5 == 1 )
    {
      CurrentUserSid = GetCurrentUserSid(&pSid);
LABEL_13:
      v19 = CurrentUserSid;
      v34 = 1;
      goto LABEL_14;
    }
    if ( a5 == 2 )
    {
      CurrentUserSid = CreateSpecificAppRID(a10, &pSid);
      goto LABEL_13;
    }
    if ( a5 == 3 )
    {
      LOBYTE(v16) = a6;
      v19 = SetTrustedACSid(v16, a8, &pSid);
      v35 = 0;
    }
    else
    {
      if ( a5 == 4 )
      {
        LOBYTE(v16) = a6;
        v31 = CreateDynamicBrowserCapabilitySid(v16, a8, &pSid);
      }
      else
      {
        if ( a5 != 5 )
        {
          v19 = 50;
          goto LABEL_28;
        }
        v31 = CreateAllApplicationPackagesSID(&pSid);
      }
      v19 = v31;
    }
  }
  else if ( a6 )
  {
    LOBYTE(v16) = a6;
    v19 = CreateDynamicBrowserCapabilitySid(v16, a8, &pSid);
    v10 = 786464;
    if ( a2 != SE_REGISTRY_KEY )
      v10 = 0;
  }
  else
  {
    v19 = CreateIESpecificSid(&pSid);
    if ( a2 == SE_REGISTRY_KEY && (a3 == 131103 || a3 == 131097) )
      v10 = 786464;
  }
LABEL_14:
  if ( !v19 )
  {
    v21 = pDacl;
    v22 = 0;
    v23 = 0;
    v33 = 0;
    v41 = 0;
    if ( pDacl )
    {
      lpnLengthNeeded = v10;
      v24 = a3;
      HasSIDCheckAndSetAccess = AclHasSIDCheckAndSetAccess(pDacl, pSid, a3, a4, lpnLengthNeeded, &v33);
      v22 = v33;
      if ( HasSIDCheckAndSetAccess )
      {
LABEL_17:
        v26 = 0;
        if ( a7 && !a6 && !a5 )
        {
          if ( v22 )
          {
            v29 = pDacl;
          }
          else
          {
            if ( !v23 )
              goto LABEL_18;
            v29 = v23;
          }
          v26 = CheckOrRemoveACSIDFromAcl(v29);
        }
LABEL_18:
        if ( !v19 )
        {
          if ( v22 )
          {
            v27 = pDacl;
LABEL_22:
            v14 = SetDacl(Handle, v27);
            if ( v14 >= 0 && a9 )
              *a9 = 1;
            if ( v23 )
              LocalFree(v23);
            goto LABEL_27;
          }
          if ( v23 || v26 )
          {
            v27 = v23;
            goto LABEL_22;
          }
        }
LABEL_27:
        if ( v35 )
        {
          if ( v34 )
            LocalFree(pSid);
          else
            FreeSid(pSid);
        }
        goto LABEL_28;
      }
      v21 = pDacl;
    }
    else
    {
      v24 = a3;
    }
    v30 = CreateSIDAcl(v21, &v41, pSid, v24, a4);
    v23 = v41;
    v19 = v30;
    goto LABEL_17;
  }
LABEL_28:
  if ( v17 )
    LocalFree(v17);
  if ( v19 )
    return (unsigned int)HRESULTFromWin32ErrorError(v19);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800306b0  mov     r11, rsp
0x1800306b3  mov     [r11+20h], r9d
0x1800306b7  mov     [r11+18h], r8d
0x1800306bb  mov     [r11+8], rcx
0x1800306bf  push    rbp
0x1800306c0  push    rbx
0x1800306c1  push    rsi
0x1800306c2  push    rdi
0x1800306c3  push    r12
0x1800306c5  push    r14
0x1800306c7  push    r15
0x1800306c9  mov     rbp, rsp
0x1800306cc  sub     rsp, 60h
0x1800306d0  xor     r12d, r12d
0x1800306d3  lea     rax, [rbp+uBytes]
0x1800306d7  mov     r14d, r8d
0x1800306da  mov     [rbp+pDacl], r12
0x1800306de  mov     esi, edx
0x1800306e0  mov     dword ptr [rbp+uBytes], r12d
0x1800306e4  xor     r9d, r9d; nLength
0x1800306e7  mov     [r11-78h], rax
0x1800306eb  lea     edx, [r12+4]; RequestedInformation
0x1800306f0  xor     r8d, r8d; pSecurityDescriptor
0x1800306f3  mov     rdi, rcx
0x1800306f6  call    cs:__imp_GetKernelObjectSecurity
0x1800306fc  test    eax, eax
0x1800306fe  jz      short loc_18003070A
0x180030700  mov     ebx, 8000FFFFh
0x180030705  jmp     loc_180030870
0x18003070a  mov     [rbp+bDaclPresent], r12d
0x18003070e  mov     [rbp+bDaclDefaulted], r12d
0x180030712  call    cs:__imp_GetLastError
0x180030718  mov     ebx, eax
0x18003071a  cmp     eax, 7Ah ; 'z'
0x18003071d  jnz     loc_180030923
0x180030723  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180030726  mov     ecx, 40h ; '@'; uFlags
0x18003072b  call    cs:__imp_LocalAlloc
0x180030731  mov     r15, rax
0x180030734  test    rax, rax
0x180030737  jz      loc_180030933
0x18003073d  mov     r9d, dword ptr [rbp+uBytes]; nLength
0x180030741  lea     rax, [rbp+uBytes]
0x180030745  mov     r8, r15; pSecurityDescriptor
0x180030748  mov     [rsp+60h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18003074d  mov     edx, 4; RequestedInformation
0x180030752  mov     rcx, rdi; Handle
0x180030755  call    cs:__imp_GetKernelObjectSecurity
0x18003075b  test    eax, eax
0x18003075d  jnz     loc_18003093D
0x180030763  call    cs:__imp_GetLastError
0x180030769  test    eax, eax
0x18003076b  mov     ebx, eax
0x18003076d  jle     short loc_180030778
0x18003076f  movzx   ebx, ax
0x180030772  or      ebx, 80070000h
0x180030778  mov     edi, r12d
0x18003077b  test    ebx, ebx
0x18003077d  jnz     loc_18003085A
0x180030783  mov     eax, [rbp+arg_20]
0x180030786  mov     [rbp+var_2E], 1
0x18003078a  mov     [rbp+var_2F], r12b
0x18003078e  mov     [rbp+pSid], r12
0x180030792  test    eax, eax
0x180030794  jz      loc_1800308E8
0x18003079a  sub     eax, 1
0x18003079d  jnz     loc_180030962
0x1800307a3  lea     rcx, [rbp+pSid]; void **
0x1800307a7  call    ?GetCurrentUserSid@@YAKPEAPEAX@Z; GetCurrentUserSid(void * *)
0x1800307ac  mov     edi, eax
0x1800307ae  mov     [rbp+var_2F], 1
0x1800307b2  test    edi, edi
0x1800307b4  jnz     loc_18003085A
0x1800307ba  mov     rcx, [rbp+pDacl]; pAcl
0x1800307be  xor     r14b, r14b
0x1800307c1  xor     esi, esi
0x1800307c3  mov     [rbp+var_30], r14b
0x1800307c7  mov     [rbp+var_8], rsi
0x1800307cb  test    rcx, rcx
0x1800307ce  jz      loc_1800308C2
0x1800307d4  mov     r9d, [rbp+arg_18]; unsigned int
0x1800307d8  lea     rax, [rbp+var_30]
0x1800307dc  mov     rdx, [rbp+pSid]; pSid2
0x1800307e0  mov     [rsp+60h+var_38], rax; bool *
0x1800307e5  mov     dword ptr [rsp+60h+lpnLengthNeeded], r12d; unsigned int
0x1800307ea  mov     r12d, [rbp+arg_10]
0x1800307ee  mov     r8d, r12d; unsigned int
0x1800307f1  call    ?AclHasSIDCheckAndSetAccess@@YA_NPEAU_ACL@@PEAXKKKPEA_N@Z; AclHasSIDCheckAndSetAccess(_ACL *,void *,ulong,ulong,ulong,bool *)
0x1800307f6  mov     r14b, [rbp+var_30]
0x1800307fa  test    al, al
0x1800307fc  jz      loc_180030A07
0x180030802  xor     r12d, r12d
0x180030805  mov     al, r12b
0x180030808  cmp     [rbp+arg_30], r12b
0x18003080c  jnz     short loc_180030881
0x18003080e  test    edi, edi
0x180030810  jnz     short loc_180030854
0x180030812  test    r14b, r14b
0x180030815  jnz     loc_1800308B9
0x18003081b  test    rsi, rsi
0x18003081e  jz      loc_180030A1E
0x180030824  mov     rdx, rsi; Source
0x180030827  mov     rcx, [rbp+Handle]; Handle
0x18003082b  call    ?SetDacl@@YAJPEAXPEAU_ACL@@@Z; SetDacl(void *,_ACL *)
0x180030830  mov     ebx, eax
0x180030832  test    eax, eax
0x180030834  js      short loc_180030846
0x180030836  mov     rax, [rbp+arg_40]
0x18003083d  test    rax, rax
0x180030840  jnz     loc_180030A2B
0x180030846  test    rsi, rsi
0x180030849  jz      short loc_180030854
0x18003084b  mov     rcx, rsi; hMem
0x18003084e  call    cs:__imp_LocalFree
0x180030854  cmp     [rbp+var_2E], r12b
0x180030858  jnz     short loc_1800308A7
0x18003085a  test    r15, r15
0x18003085d  jz      short loc_180030868
0x18003085f  mov     rcx, r15; hMem
0x180030862  call    cs:__imp_LocalFree
0x180030868  test    edi, edi
0x18003086a  jnz     loc_180030A33
0x180030870  mov     eax, ebx
0x180030872  add     rsp, 60h
0x180030876  pop     r15
0x180030878  pop     r14
0x18003087a  pop     r12
0x18003087c  pop     rdi
0x18003087d  pop     rsi
0x18003087e  pop     rbx
0x18003087f  pop     rbp
0x180030880  retn
0x180030881  cmp     [rbp+arg_28], r12b
0x180030885  jnz     short loc_18003080E
0x180030887  cmp     [rbp+arg_20], r12d
0x18003088b  jnz     short loc_18003080E
0x18003088d  test    r14b, r14b
0x180030890  jnz     loc_180030A10
0x180030896  test    rsi, rsi
0x180030899  jz      loc_18003080E
0x18003089f  mov     rcx, rsi
0x1800308a2  jmp     loc_180030A14
0x1800308a7  mov     rcx, [rbp+pSid]; hMem
0x1800308ab  cmp     [rbp+var_2F], r12b
0x1800308af  jnz     short loc_180030918
0x1800308b1  call    cs:__imp_FreeSid
0x1800308b7  jmp     short loc_18003085A
0x1800308b9  mov     rdx, [rbp+pDacl]
0x1800308bd  jmp     loc_180030827
0x1800308c2  mov     r12d, [rbp+arg_10]
0x1800308c6  mov     eax, [rbp+arg_18]
0x1800308c9  lea     rdx, [rbp+var_8]; struct _ACL **
0x1800308cd  mov     r8, [rbp+pSid]; void *
0x1800308d1  mov     r9d, r12d; unsigned int
0x1800308d4  mov     dword ptr [rsp+60h+lpnLengthNeeded], eax; unsigned int
0x1800308d8  call    ?CreateSIDAcl@@YAKPEAU_ACL@@PEAPEAU1@PEAXKK@Z; CreateSIDAcl(_ACL *,_ACL * *,void *,ulong,ulong)
0x1800308dd  mov     rsi, [rbp+var_8]
0x1800308e1  mov     edi, eax
0x1800308e3  jmp     loc_180030802
0x1800308e8  cmp     [rbp+arg_28], r12b
0x1800308ec  jz      loc_1800309D2
0x1800308f2  mov     rdx, [rbp+arg_38]
0x1800308f6  lea     r8, [rbp+pSid]
0x1800308fa  mov     cl, [rbp+arg_28]
0x1800308fd  call    _CreateDynamicBrowserCapabilitySid
0x180030902  mov     edi, eax
0x180030904  mov     r12d, 0C0020h
0x18003090a  xor     eax, eax
0x18003090c  cmp     esi, 4
0x18003090f  cmovnz  r12d, eax
0x180030913  jmp     loc_1800307B2
0x180030918  call    cs:__imp_LocalFree
0x18003091e  jmp     loc_18003085A
0x180030923  test    eax, eax
0x180030925  jz      loc_180030723
0x18003092b  mov     r15, r12
0x18003092e  jmp     loc_18003076D
0x180030933  mov     ebx, 8007000Eh
0x180030938  jmp     loc_180030870
0x18003093d  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180030941  mov     rcx, r15; pSecurityDescriptor
0x180030944  lea     r8, [rbp+pDacl]; pDacl
0x180030948  mov     ebx, r12d
0x18003094b  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18003094f  call    cs:__imp_GetSecurityDescriptorDacl
0x180030955  test    eax, eax
0x180030957  jnz     loc_180030783
0x18003095d  jmp     loc_180030763
0x180030962  sub     eax, 1
0x180030965  jz      short loc_1800309BD
0x180030967  sub     eax, 1
0x18003096a  jz      short loc_1800309A2
0x18003096c  sub     eax, 1
0x18003096f  jz      short loc_18003098B
0x180030971  cmp     eax, 1
0x180030974  jz      short loc_180030980
0x180030976  mov     edi, 32h ; '2'
0x18003097b  jmp     loc_18003085A
0x180030980  lea     rcx, [rbp+pSid]; pSid
0x180030984  call    ?CreateAllApplicationPackagesSID@@YAKPEAPEAX@Z; CreateAllApplicationPackagesSID(void * *)
0x180030989  jmp     short loc_18003099B
0x18003098b  mov     rdx, [rbp+arg_38]
0x18003098f  lea     r8, [rbp+pSid]
0x180030993  mov     cl, [rbp+arg_28]
0x180030996  call    _CreateDynamicBrowserCapabilitySid
0x18003099b  mov     edi, eax
0x18003099d  jmp     loc_1800307B2
0x1800309a2  mov     rdx, [rbp+arg_38]
0x1800309a6  lea     r8, [rbp+pSid]
0x1800309aa  mov     cl, [rbp+arg_28]
0x1800309ad  call    _SetTrustedACSid
0x1800309b2  mov     edi, eax
0x1800309b4  mov     [rbp+var_2E], r12b
0x1800309b8  jmp     loc_1800307B2
0x1800309bd  mov     rcx, [rbp+arg_48]; unsigned __int16 *
0x1800309c4  lea     rdx, [rbp+pSid]; void **
0x1800309c8  call    ?CreateSpecificAppRID@@YAKPEBGPEAPEAX@Z; CreateSpecificAppRID(ushort const *,void * *)
0x1800309cd  jmp     loc_1800307AC
0x1800309d2  lea     rcx, [rbp+pSid]; pSid
0x1800309d6  call    ?CreateIESpecificSid@@YAKPEAPEAX@Z; CreateIESpecificSid(void * *)
0x1800309db  mov     edi, eax
0x1800309dd  cmp     esi, 4
0x1800309e0  jnz     loc_1800307B2
0x1800309e6  cmp     r14d, 2001Fh
0x1800309ed  jz      short loc_1800309FC
0x1800309ef  cmp     r14d, 20019h
0x1800309f6  jnz     loc_1800307B2
0x1800309fc  mov     r12d, 0C0020h
0x180030a02  jmp     loc_1800307B2
0x180030a07  mov     rcx, [rbp+pDacl]
0x180030a0b  jmp     loc_1800308C6
0x180030a10  mov     rcx, [rbp+pDacl]; pAcl
0x180030a14  call    ?CheckOrRemoveACSIDFromAcl@@YA_NPEAU_ACL@@@Z; CheckOrRemoveACSIDFromAcl(_ACL *)
0x180030a19  jmp     loc_18003080E
0x180030a1e  test    al, al
0x180030a20  jz      loc_180030854
0x180030a26  jmp     loc_180030824
0x180030a2b  mov     byte ptr [rax], 1
0x180030a2e  jmp     loc_180030846
0x180030a33  mov     ecx, edi; unsigned int
0x180030a35  call    ?HRESULTFromWin32ErrorError@@YAJK@Z; HRESULTFromWin32ErrorError(ulong)
0x180030a3a  mov     ebx, eax
0x180030a3c  jmp     loc_180030870
```
