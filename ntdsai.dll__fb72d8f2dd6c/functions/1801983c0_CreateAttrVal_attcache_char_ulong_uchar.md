# CreateAttrVal(_attcache *,char *,ulong &,uchar * &)

- ea: `0x1801983c0`
- end: `0x18019889c`
- name: `?CreateAttrVal@@YAHPEAU_attcache@@PEADAEAKAEAPEAE@Z`
- size: `1244`
- prototype: `__int64 __fastcall(struct _attcache *, char *, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801981b4`
- `0x1801982b8`

## callees

- `0x18001e090`
- `0x180021aa3`
- `0x18003cf0c`
- `0x180170230`
- `0x180192394`
- `0x18019805c`
- `0x1801983c0`
- `0x180198a10`
- `0x1801991a0`
- `0x180199ed0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180198685`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180198685`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1801987e8`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1801987e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18019876a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18019876a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801984ff`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801985c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801984ff`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801985c1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1801984ea`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180198566`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1801984ea`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180198566`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180198783`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180198783`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801987d0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801987d0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801984a9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180198514`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801986e2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180198710`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18019879b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180198848`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801984a9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180198514`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801986e2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180198710`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18019879b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180198848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801986cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180198833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801986cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180198833`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019874d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180198870`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019874d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180198870`
- `ntdll!RtlFreeHeap` at `0x1801985e9`
- `ntdll!RtlFreeHeap` at `0x1801985e9`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1801986f7`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1801986f7`
- `ntdll!RtlLengthSid` at `0x18019871a`
- `ntdll!RtlLengthSid` at `0x1801987a5`
- `ntdll!RtlLengthSid` at `0x18019871a`
- `ntdll!RtlLengthSid` at `0x1801987a5`
- `ADVAPI32!ConvertStringSidToSidA` at `0x180198801`
- `ADVAPI32!ConvertStringSidToSidA` at `0x180198801`

## pseudocode

```c
__int64 __fastcall CreateAttrVal(struct _attcache *a1, char *a2, unsigned int *a3, unsigned __int8 **a4)
{
  struct _attcache *v6; // rdi
  __int64 result; // rax
  const char *v9; // r15
  const WCHAR *v10; // r14
  PSID v11; // r14
  unsigned int v12; // r15d
  LSTATUS ConfigParamAllocW; // eax
  DWORD v14; // ecx
  __int64 v15; // rdi
  __int64 v16; // r9
  unsigned int v17; // eax
  unsigned int cchWideChar; // r13d
  unsigned __int16 *v19; // r15
  __int64 v20; // r9
  unsigned int v21; // r13d
  unsigned __int64 v22; // rdx
  unsigned __int16 *v23; // rcx
  __int16 v24; // cx
  __int16 v25; // dx
  __int16 v26; // ax
  __int16 v27; // cx
  __int16 v28; // ax
  __int16 v29; // dx
  __int16 v30; // ax
  unsigned __int16 *v31; // rdx
  char *v32; // rcx
  __int64 v33; // rdi
  PSECURITY_DESCRIPTOR v34; // rdi
  ULONG v35; // eax
  unsigned __int8 *v36; // rax
  PSID v37; // rdx
  BOOL v38; // eax
  ULONG v39; // eax
  unsigned __int8 *v40; // rax
  PSID v41; // rdx
  void *v42; // rbx
  PSID Owner; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int8 OwnerDefaulted[4]; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v45; // [rsp+3Ch] [rbp-2Ch] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-28h] BYREF
  char Src[8]; // [rsp+48h] [rbp-20h] BYREF

  SecurityDescriptor = a1;
  Owner = 0;
  v6 = a1;
  result = (__int64)PreProcessInifileShortcuts(a2, a1, (unsigned __int16 **)&Owner);
  v9 = (const char *)result;
  if ( result )
  {
    if ( *(_DWORD *)v6 == 131353 )
    {
      if ( !(unsigned int)CachedStringSDConverter(a2, (void **)a4, a3) )
      {
        GetLastError();
        RaiseException(0xF007u, 1u, 0, 0);
      }
      v42 = XCalloc(1u, *a3);
      memcpy_0(v42, *a4, *a3);
      LocalFree(*a4);
      *a4 = (unsigned __int8 *)v42;
      return 1;
    }
    v10 = (const WCHAR *)Owner;
    if ( *(_DWORD *)v6 != 589970 )
    {
      if ( *(_DWORD *)v6 == 589972 || *(_DWORD *)v6 == 589973 )
      {
        v24 = *((_WORD *)a2 + 4);
        v25 = *((_WORD *)a2 + 6);
        *((_WORD *)a2 + 4) = *((_WORD *)a2 + 1);
        v26 = *((_WORD *)a2 + 2);
        *((_WORD *)a2 + 1) = v24;
        v27 = *((_WORD *)a2 + 3);
        *((_WORD *)a2 + 3) = v26;
        v28 = *((_WORD *)a2 + 5);
        *((_WORD *)a2 + 5) = v25;
        v29 = *((_WORD *)a2 + 8);
        *((_WORD *)a2 + 6) = v28;
        v30 = *((_WORD *)a2 + 7);
        *((_WORD *)a2 + 7) = v29;
        v31 = 0;
        *((_WORD *)a2 + 2) = v27;
        v32 = a2;
        *((_WORD *)a2 + 8) = v30;
LABEL_30:
        StrToAttrib(v32, v31, v6, a4, a3);
        return 1;
      }
      if ( (unsigned int)(*(_DWORD *)v6 - 590606) <= 1 )
      {
        v11 = 0;
        Owner = 0;
        v45 = 0;
        if ( !gInstallHasDoneSchemaMove )
        {
          v12 = 22;
          goto LABEL_15;
        }
        ConfigParamAllocW = GetConfigParamAllocW(L"Schema DN Name", &Owner, &v45);
        if ( ConfigParamAllocW == 14 )
        {
          v14 = 61448;
        }
        else
        {
          if ( !ConfigParamAllocW )
          {
LABEL_14:
            v11 = Owner;
            v12 = (v45 >> 1) + 5;
LABEL_15:
            v15 = -1;
            v16 = -1;
            do
              ++v16;
            while ( a2[v16] );
            v17 = MultiByteToWideChar(0xFDE9u, 0, a2, v16, 0, 0);
            v45 = v17;
            if ( !v17 )
            {
              if ( v11 )
                free(v11);
              RaiseException(0xF007u, 1u, 0, 0);
              v17 = v45;
            }
            cchWideChar = v17 + v12;
            v19 = (unsigned __int16 *)XCalloc(v17 + v12, 2u);
            StringCchCopyW(v19, cchWideChar, L"CN=");
            v20 = -1;
            do
              ++v20;
            while ( a2[v20] );
            MultiByteToWideChar(0xFDE9u, 0, a2, v20, v19 + 3, cchWideChar);
            do
              ++v15;
            while ( a2[v15] );
            v21 = cchWideChar - (v15 + 3);
            StringCchCopyW(&v19[(int)v15 + 3], v21, L",");
            v22 = v21 - 1;
            v23 = &v19[(int)v15 + 4];
            if ( gInstallHasDoneSchemaMove )
            {
              StringCchCopyW(v23, v22, (const unsigned __int16 *)v11);
              free(v11);
            }
            else
            {
              StringCchCopyW(v23, v22, L"CN=Schema,O=Boot");
            }
            StrToAttrib(0, v19, (struct _attcache *)SecurityDescriptor, a4, a3);
            RtlFreeHeap(ghInstallHeap, 0, v19);
            return 1;
          }
          v14 = 61447;
        }
        RaiseException(v14, 1u, 0, 0);
        goto LABEL_14;
      }
LABEL_51:
      v31 = (unsigned __int16 *)v10;
      if ( v10 )
        v9 = 0;
      v32 = (char *)v9;
      goto LABEL_30;
    }
    v33 = -1;
    do
      ++v33;
    while ( a2[v33] );
    if ( v33 == 2 )
    {
      v34 = 0;
      Owner = 0;
      SecurityDescriptor = 0;
      v45 = 0;
      if ( (unsigned int)_o__stricmp(a2, "DO") )
      {
        OwnerDefaulted[0] = 0;
        StringCchPrintfA(Src, 5u, "O:%s", a2);
        if ( !(unsigned int)CachedStringSDConverter(Src, &SecurityDescriptor, &v45) )
        {
          GetLastError();
          RaiseException(0xF007u, 1u, 0, 0);
        }
        v34 = SecurityDescriptor;
        if ( RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, OwnerDefaulted) < 0 )
          RaiseException(0xF007u, 1u, 0, 0);
      }
      else
      {
        Owner = gpRootDomainSid;
      }
      v35 = RtlLengthSid(Owner);
      *a3 = v35;
      v36 = (unsigned __int8 *)XCalloc(1u, v35);
      v37 = Owner;
      *a4 = v36;
      memcpy_0(v36, v37, *a3);
      if ( v34 )
        LocalFree(v34);
      return 1;
    }
    if ( !Owner || (unsigned int)_o__wcsnicmp(Owner, L"S-", 2) )
    {
      if ( _strnicmp(v9, "S-", 2u) )
      {
        v6 = (struct _attcache *)SecurityDescriptor;
        goto LABEL_51;
      }
      Owner = 0;
      v38 = ConvertStringSidToSidA(v9, &Owner);
    }
    else
    {
      Owner = 0;
      v38 = ConvertStringSidToSidW(v10, &Owner);
    }
    if ( !v38 )
      RaiseException(0xF007u, 1u, 0, 0);
    v39 = RtlLengthSid(Owner);
    *a3 = v39;
    v40 = (unsigned __int8 *)XCalloc(1u, v39);
    v41 = Owner;
    *a4 = v40;
    memcpy_0(v40, v41, *a3);
    FreeSid(Owner);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1801983c0  push    rbp
0x1801983c2  push    rbx
0x1801983c3  push    rsi
0x1801983c4  push    rdi
0x1801983c5  push    r12
0x1801983c7  push    r13
0x1801983c9  push    r14
0x1801983cb  push    r15
0x1801983cd  mov     rbp, rsp
0x1801983d0  sub     rsp, 68h
0x1801983d4  mov     rax, cs:__security_cookie
0x1801983db  xor     rax, rsp
0x1801983de  mov     [rbp+var_18], rax
0x1801983e2  mov     rbx, rdx
0x1801983e5  mov     [rbp+SecurityDescriptor], rcx
0x1801983e9  mov     rdx, rcx; struct _attcache *
0x1801983ec  mov     [rbp+Owner], 0
0x1801983f4  mov     rsi, r8
0x1801983f7  mov     rdi, rcx
0x1801983fa  mov     rcx, rbx; Str2
0x1801983fd  lea     r8, [rbp+Owner]; unsigned __int16 **
0x180198401  mov     r12, r9
0x180198404  call    ?PreProcessInifileShortcuts@@YAPEADPEADPEAU_attcache@@PEAPEAG@Z; PreProcessInifileShortcuts(char *,_attcache *,ushort * *)
0x180198409  mov     r15, rax
0x18019840c  test    rax, rax
0x18019840f  jz      loc_18019887F
0x180198415  mov     ecx, [rdi]
0x180198417  sub     ecx, 20119h
0x18019841d  jz      loc_180198821
0x180198423  mov     r14, [rbp+Owner]
0x180198427  sub     ecx, 6FF79h
0x18019842d  jz      loc_18019864E
0x180198433  mov     r13d, 2
0x180198439  sub     ecx, r13d
0x18019843c  jz      loc_1801985F4
0x180198442  sub     ecx, 1
0x180198445  jz      loc_1801985F4
0x18019844b  sub     ecx, 279h
0x180198451  jz      short loc_18019845C
0x180198453  cmp     ecx, 1
0x180198456  jnz     loc_18019880D
0x18019845c  xor     r14d, r14d
0x18019845f  cmp     cs:?gInstallHasDoneSchemaMove@@3HA, r14d; int gInstallHasDoneSchemaMove
0x180198466  mov     [rbp+Owner], r14
0x18019846a  mov     [rbp+var_2C], r14d
0x18019846e  jnz     short loc_180198476
0x180198470  lea     r15d, [r14+16h]
0x180198474  jmp     short loc_1801984BE
0x180198476  lea     r8, [rbp+var_2C]
0x18019847a  lea     rdx, [rbp+Owner]
0x18019847e  lea     rcx, aSchemaDnName_0; "Schema DN Name"
0x180198485  call    GetConfigParamAllocW
0x18019848a  cmp     eax, 0Eh
0x18019848d  jnz     short loc_180198496
0x18019848f  mov     ecx, 0F008h
0x180198494  jmp     short loc_18019849F
0x180198496  test    eax, eax
0x180198498  jz      short loc_1801984AF
0x18019849a  mov     ecx, 0F007h; dwExceptionCode
0x18019849f  xor     r9d, r9d; lpArguments
0x1801984a2  xor     r8d, r8d; nNumberOfArguments
0x1801984a5  lea     edx, [r9+1]; dwExceptionFlags
0x1801984a9  call    cs:__imp_RaiseException
0x1801984af  mov     r15d, [rbp+var_2C]
0x1801984b3  mov     r14, [rbp+Owner]
0x1801984b7  shr     r15d, 1
0x1801984ba  add     r15d, 5
0x1801984be  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801984c2  mov     r9, rdi
0x1801984c5  inc     r9; cbMultiByte
0x1801984c8  cmp     byte ptr [rbx+r9], 0
0x1801984cd  jnz     short loc_1801984C5
0x1801984cf  mov     [rsp+68h+cchWideChar], 0; cchWideChar
0x1801984d7  mov     r8, rbx; lpMultiByteStr
0x1801984da  xor     edx, edx; dwFlags
0x1801984dc  mov     [rsp+68h+lpWideCharStr], 0; lpWideCharStr
0x1801984e5  mov     ecx, 0FDE9h; CodePage
0x1801984ea  call    cs:__imp_MultiByteToWideChar
0x1801984f0  mov     [rbp+var_2C], eax
0x1801984f3  test    eax, eax
0x1801984f5  jnz     short loc_18019851D
0x1801984f7  test    r14, r14
0x1801984fa  jz      short loc_180198505
0x1801984fc  mov     rcx, r14; Block
0x1801984ff  call    cs:__imp_free
0x180198505  xor     r9d, r9d; lpArguments
0x180198508  xor     r8d, r8d; nNumberOfArguments
0x18019850b  mov     ecx, 0F007h; dwExceptionCode
0x180198510  lea     edx, [r9+1]; dwExceptionFlags
0x180198514  call    cs:__imp_RaiseException
0x18019851a  mov     eax, [rbp+var_2C]
0x18019851d  mov     edx, r13d; unsigned int
0x180198520  lea     r13d, [rax+r15]
0x180198524  mov     ecx, r13d; unsigned int
0x180198527  call    ?XCalloc@@YAPEAXKK@Z; XCalloc(ulong,ulong)
0x18019852c  mov     edx, r13d; unsigned __int64
0x18019852f  lea     r8, aCn_1; "CN="
0x180198536  mov     rcx, rax; unsigned __int16 *
0x180198539  mov     r15, rax
0x18019853c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180198541  mov     r9, rdi
0x180198544  inc     r9; cbMultiByte
0x180198547  cmp     byte ptr [rbx+r9], 0
0x18019854c  jnz     short loc_180198544
0x18019854e  lea     rax, [r15+6]
0x180198552  mov     [rsp+68h+cchWideChar], r13d; cchWideChar
0x180198557  mov     r8, rbx; lpMultiByteStr
0x18019855a  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x18019855f  xor     edx, edx; dwFlags
0x180198561  mov     ecx, 0FDE9h; CodePage
0x180198566  call    cs:__imp_MultiByteToWideChar
0x18019856c  inc     rdi
0x18019856f  cmp     byte ptr [rbx+rdi], 0
0x180198573  jnz     short loc_18019856C
0x180198575  lea     ebx, [rdi+3]
0x180198578  movsxd  rax, ebx
0x18019857b  lea     r8, asc_1804ABD00; ","
0x180198582  sub     r13d, ebx
0x180198585  mov     edx, r13d; unsigned __int64
0x180198588  lea     rcx, [r15+rax*2]; unsigned __int16 *
0x18019858c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180198591  cmp     cs:?gInstallHasDoneSchemaMove@@3HA, 0; int gInstallHasDoneSchemaMove
0x180198598  lea     eax, [rbx+1]
0x18019859b  movsxd  rcx, eax
0x18019859e  lea     edx, [r13-1]; unsigned __int64
0x1801985a2  lea     rcx, [r15+rcx*2]; unsigned __int16 *
0x1801985a6  jnz     short loc_1801985B6
0x1801985a8  lea     r8, aCnSchemaOBoot; "CN=Schema,O=Boot"
0x1801985af  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801985b4  jmp     short loc_1801985C7
0x1801985b6  mov     r8, r14; unsigned __int16 *
0x1801985b9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801985be  mov     rcx, r14; Block
0x1801985c1  call    cs:__imp_free
0x1801985c7  mov     r8, [rbp+SecurityDescriptor]; struct _attcache *
0x1801985cb  mov     r9, r12; unsigned __int8 **
0x1801985ce  mov     rdx, r15; unsigned __int16 *
0x1801985d1  mov     [rsp+68h+lpWideCharStr], rsi; unsigned int *
0x1801985d6  xor     ecx, ecx; Src
0x1801985d8  call    ?StrToAttrib@@YAXPEADPEAGPEAU_attcache@@PEAPEAEAEAK@Z; StrToAttrib(char *,ushort *,_attcache *,uchar * *,ulong &)
0x1801985dd  mov     rcx, cs:?ghInstallHeap@@3PEAXEA; HeapHandle
0x1801985e4  mov     r8, r15; P
0x1801985e7  xor     edx, edx; Flags
0x1801985e9  call    cs:__imp_RtlFreeHeap
0x1801985ef  jmp     loc_18019887A
0x1801985f4  movzx   ecx, word ptr [rbx+8]
0x1801985f8  movzx   edx, word ptr [rbx+0Ch]
0x1801985fc  movzx   eax, word ptr [rbx+2]
0x180198600  mov     [rbx+8], ax
0x180198604  movzx   eax, word ptr [rbx+4]
0x180198608  mov     [rbx+2], cx
0x18019860c  movzx   ecx, word ptr [rbx+6]
0x180198610  mov     [rbx+6], ax
0x180198614  movzx   eax, word ptr [rbx+0Ah]
0x180198618  mov     [rbx+0Ah], dx
0x18019861c  movzx   edx, word ptr [rbx+10h]
0x180198620  mov     [rbx+0Ch], ax
0x180198624  movzx   eax, word ptr [rbx+0Eh]
0x180198628  mov     [rbx+0Eh], dx
0x18019862c  xor     edx, edx; unsigned __int16 *
0x18019862e  mov     [rbx+4], cx
0x180198632  mov     rcx, rbx; Src
0x180198635  mov     [rbx+10h], ax
0x180198639  mov     r8, rdi; struct _attcache *
0x18019863c  mov     [rsp+68h+lpWideCharStr], rsi; unsigned int *
0x180198641  mov     r9, r12; unsigned __int8 **
0x180198644  call    ?StrToAttrib@@YAXPEADPEAGPEAU_attcache@@PEAPEAEAEAK@Z; StrToAttrib(char *,ushort *,_attcache *,uchar * *,ulong &)
0x180198649  jmp     loc_18019887A
0x18019864e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180198652  inc     rdi
0x180198655  cmp     byte ptr [rbx+rdi], 0
0x180198659  jnz     short loc_180198652
0x18019865b  mov     r13d, 2
0x180198661  cmp     rdi, r13
0x180198664  jnz     loc_180198758
0x18019866a  xor     edi, edi
0x18019866c  mov     [rbp+Owner], 0
0x180198674  lea     rdx, aDo; "DO"
0x18019867b  mov     [rbp+SecurityDescriptor], rdi
0x18019867f  mov     rcx, rbx
0x180198682  mov     [rbp+var_2C], edi
0x180198685  call    cs:__imp__o__stricmp
0x18019868b  test    eax, eax
0x18019868d  jnz     short loc_18019869C
0x18019868f  mov     rax, cs:gpRootDomainSid
0x180198696  mov     [rbp+Owner], rax
0x18019869a  jmp     short loc_180198716
0x18019869c  mov     r9, rbx
0x18019869f  mov     [rbp+OwnerDefaulted], dil
0x1801986a3  lea     r8, aOS; "O:%s"
0x1801986aa  mov     edx, 5; unsigned __int64
0x1801986af  lea     rcx, [rbp+Src]; char *
0x1801986b3  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1801986b8  lea     r8, [rbp+var_2C]; unsigned int *
0x1801986bc  lea     rdx, [rbp+SecurityDescriptor]; void **
0x1801986c0  lea     rcx, [rbp+Src]; Src
0x1801986c4  call    ?CachedStringSDConverter@@YAHPEADPEAPEAXPEAK@Z; CachedStringSDConverter(char *,void * *,ulong *)
0x1801986c9  test    eax, eax
0x1801986cb  jnz     short loc_1801986E8
0x1801986cd  call    cs:__imp_GetLastError
0x1801986d3  xor     r9d, r9d; lpArguments
0x1801986d6  xor     r8d, r8d; nNumberOfArguments
0x1801986d9  mov     ecx, 0F007h; dwExceptionCode
0x1801986de  lea     edx, [r9+1]; dwExceptionFlags
0x1801986e2  call    cs:__imp_RaiseException
0x1801986e8  mov     rdi, [rbp+SecurityDescriptor]
0x1801986ec  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1801986f0  mov     rcx, rdi; SecurityDescriptor
0x1801986f3  lea     rdx, [rbp+Owner]; Owner
0x1801986f7  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1801986fd  test    eax, eax
0x1801986ff  jns     short loc_180198716
0x180198701  xor     r9d, r9d; lpArguments
0x180198704  xor     r8d, r8d; nNumberOfArguments
0x180198707  mov     ecx, 0F007h; dwExceptionCode
0x18019870c  lea     edx, [r9+1]; dwExceptionFlags
0x180198710  call    cs:__imp_RaiseException
0x180198716  mov     rcx, [rbp+Owner]; Sid
0x18019871a  call    cs:__imp_RtlLengthSid
0x180198720  mov     edx, eax; unsigned int
0x180198722  mov     [rsi], eax
0x180198724  mov     ecx, 1; unsigned int
0x180198729  call    ?XCalloc@@YAPEAXKK@Z; XCalloc(ulong,ulong)
0x18019872e  mov     rdx, [rbp+Owner]; Src
0x180198732  mov     rcx, rax; void *
0x180198735  mov     [r12], rax
0x180198739  mov     r8d, [rsi]; Size
0x18019873c  call    memcpy_0
0x180198741  test    rdi, rdi
0x180198744  jz      loc_18019887A
0x18019874a  mov     rcx, rdi; hMem
0x18019874d  call    cs:__imp_LocalFree
0x180198753  jmp     loc_18019887A
0x180198758  test    r14, r14
0x18019875b  jz      short loc_1801987DB
0x18019875d  mov     r8, r13
0x180198760  lea     rdx, aS_11; "S-"
0x180198767  mov     rcx, r14
0x18019876a  call    cs:__imp__o__wcsnicmp
0x180198770  test    eax, eax
0x180198772  jnz     short loc_1801987DB
0x180198774  lea     rdx, [rbp+Owner]; Sid
0x180198778  mov     [rbp+Owner], 0
0x180198780  mov     rcx, r14; StringSid
0x180198783  call    cs:__imp_ConvertStringSidToSidW
0x180198789  test    eax, eax
0x18019878b  jnz     short loc_1801987A1
0x18019878d  xor     r9d, r9d; lpArguments
0x180198790  lea     edx, [rax+1]; dwExceptionFlags
0x180198793  xor     r8d, r8d; nNumberOfArguments
0x180198796  mov     ecx, 0F007h; dwExceptionCode
0x18019879b  call    cs:__imp_RaiseException
0x1801987a1  mov     rcx, [rbp+Owner]; Sid
0x1801987a5  call    cs:__imp_RtlLengthSid
0x1801987ab  mov     edx, eax; unsigned int
0x1801987ad  mov     [rsi], eax
0x1801987af  mov     ecx, 1; unsigned int
0x1801987b4  call    ?XCalloc@@YAPEAXKK@Z; XCalloc(ulong,ulong)
0x1801987b9  mov     rdx, [rbp+Owner]; Src
0x1801987bd  mov     rcx, rax; void *
0x1801987c0  mov     [r12], rax
0x1801987c4  mov     r8d, [rsi]; Size
0x1801987c7  call    memcpy_0
0x1801987cc  mov     rcx, [rbp+Owner]; pSid
0x1801987d0  call    cs:__imp_FreeSid
0x1801987d6  jmp     loc_18019887A
0x1801987db  mov     r8, r13; MaxCount
0x1801987de  lea     rdx, aS_4; "S-"
0x1801987e5  mov     rcx, r15; String1
0x1801987e8  call    cs:__imp__strnicmp
0x1801987ee  test    eax, eax
0x1801987f0  jnz     short loc_180198809
0x1801987f2  lea     rdx, [rbp+Owner]; Sid
0x1801987f6  mov     [rbp+Owner], 0
0x1801987fe  mov     rcx, r15; StringSid
0x180198801  call    cs:__imp_ConvertStringSidToSidA
0x180198807  jmp     short loc_180198789
0x180198809  mov     rdi, [rbp+SecurityDescriptor]
0x18019880d  xor     eax, eax
0x18019880f  mov     rdx, r14
0x180198812  test    r14, r14
0x180198815  cmovnz  r15, rax
0x180198819  mov     rcx, r15
0x18019881c  jmp     loc_180198639
0x180198821  mov     r8, rsi; unsigned int *
0x180198824  mov     rdx, r12; void **
0x180198827  mov     rcx, rbx; Src
0x18019882a  call    ?CachedStringSDConverter@@YAHPEADPEAPEAXPEAK@Z; CachedStringSDConverter(char *,void * *,ulong *)
0x18019882f  test    eax, eax
0x180198831  jnz     short loc_18019884E
0x180198833  call    cs:__imp_GetLastError
0x180198839  xor     r9d, r9d; lpArguments
0x18019883c  xor     r8d, r8d; nNumberOfArguments
0x18019883f  mov     ecx, 0F007h; dwExceptionCode
0x180198844  lea     edx, [r9+1]; dwExceptionFlags
0x180198848  call    cs:__imp_RaiseException
0x18019884e  mov     edx, [rsi]; unsigned int
0x180198850  mov     ecx, 1; unsigned int
0x180198855  call    ?XCalloc@@YAPEAXKK@Z; XCalloc(ulong,ulong)
0x18019885a  mov     r8d, [rsi]; Size
  ... truncated ...
```
