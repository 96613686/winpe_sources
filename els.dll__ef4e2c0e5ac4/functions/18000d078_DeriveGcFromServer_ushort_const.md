# DeriveGcFromServer(ushort const *)

- ea: `0x18000d078`
- end: `0x18000d43c`
- name: `?DeriveGcFromServer@@YAPEAUIDirectorySearch@@PEBG@Z`
- size: `964`
- prototype: `struct IDirectorySearch *__fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000e208`

## callees

- `0x1800017e0`
- `0x180001910`
- `0x180001a70`
- `0x180001dd0`
- `0x1800028e0`
- `0x180002904`
- `0x18000513c`
- `0x180007060`
- `0x18000c7e8`
- `0x18000d078`
- `0x18000f7b8`
- `0x18000f7e8`
- `0x1800222d0`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x18000d163`
- `netutils!NetApiBufferFree` at `0x18000d242`
- `netutils!NetApiBufferFree` at `0x18000d367`
- `netutils!NetApiBufferFree` at `0x18000d402`
- `netutils!NetApiBufferFree` at `0x18000d163`
- `netutils!NetApiBufferFree` at `0x18000d242`
- `netutils!NetApiBufferFree` at `0x18000d367`
- `netutils!NetApiBufferFree` at `0x18000d402`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18000d0be`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18000d0be`
- `DSROLE!DsRoleFreeMemory` at `0x18000d411`
- `DSROLE!DsRoleFreeMemory` at `0x18000d411`
- `logoncli!DsGetDcNameW` at `0x18000d115`
- `logoncli!DsGetDcNameW` at `0x18000d151`
- `logoncli!DsGetDcNameW` at `0x18000d290`
- `logoncli!DsGetDcNameW` at `0x18000d115`
- `logoncli!DsGetDcNameW` at `0x18000d151`
- `logoncli!DsGetDcNameW` at `0x18000d290`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct IDirectorySearch *__fastcall DeriveGcFromServer(const unsigned __int16 *a1)
{
  PBYTE v1; // rcx
  const WCHAR *v2; // rax
  const WCHAR *v3; // rdi
  ULONG v4; // ebx
  LPWSTR DomainName; // rdx
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  LPCWSTR v8; // r10
  __int64 v9; // rdx
  LPWSTR i; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r10
  unsigned __int16 **v14; // rax
  unsigned __int16 *v15; // r11
  unsigned __int64 v16; // rbx
  char *j; // r9
  unsigned __int16 **v18; // rax
  unsigned __int16 **v19; // rax
  __int64 v20; // r9
  __int64 v21; // rax
  const unsigned __int16 *v22; // rdx
  const unsigned __int16 *v23; // r8
  unsigned int v24; // r9d
  const unsigned __int16 *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rdx
  const struct _GUID *Flags; // [rsp+20h] [rbp-89h]
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+30h] [rbp-79h] BYREF
  __int16 v31; // [rsp+38h] [rbp-71h] BYREF
  PBYTE Buffer; // [rsp+40h] [rbp-69h] BYREF
  PDOMAIN_CONTROLLER_INFOW v33; // [rsp+48h] [rbp-61h] BYREF
  void *v34; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v35[8]; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v36[8]; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int16 *v37[2]; // [rsp+68h] [rbp-41h] BYREF
  __int64 v38; // [rsp+78h] [rbp-31h]
  unsigned __int64 v39; // [rsp+80h] [rbp-29h]
  _QWORD v40[3]; // [rsp+88h] [rbp-21h] BYREF
  _BYTE v41[16]; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v42; // [rsp+B8h] [rbp+Fh]
  unsigned __int16 v43[20]; // [rsp+C8h] [rbp+1Fh] BYREF

  Buffer = 0;
  DomainControllerInfo = 0;
  v34 = 0;
  if ( !DsRoleGetPrimaryDomainInformation(a1, DsRolePrimaryDomainInfoBasic, &Buffer) )
  {
    v1 = Buffer;
    if ( (*(_DWORD *)Buffer & 0xFFFFFFFD) == 0 )
      goto LABEL_44;
    v2 = (const WCHAR *)*((_QWORD *)Buffer + 2);
    v3 = v2;
    if ( !v2 )
      v3 = (const WCHAR *)*((_QWORD *)Buffer + 1);
    v4 = v2 != 0 ? 131088 : 65552;
    if ( !DsGetDcNameW(0, v3, 0, 0, v4, &DomainControllerInfo) )
    {
      if ( (DomainControllerInfo->Flags & 0x10) == 0 )
        goto LABEL_9;
      v33 = 0;
      if ( !DsGetDcNameW(0, v3, 0, 0, v4 | 0x40000000, &v33) )
      {
        NetApiBufferFree(DomainControllerInfo);
        DomainControllerInfo = v33;
LABEL_9:
        std::wstring::wstring(v41);
        std::wstring::wstring(v40);
        DomainName = (LPWSTR)*((_QWORD *)Buffer + 2);
        if ( DomainName || (DomainName = DomainControllerInfo->DomainName) != 0 )
          std::wstring::assign(v41, DomainName);
        while ( v42 && *(_WORD *)(*(_QWORD *)std::wstring::end(v41, &v33) - 2LL) == 46 )
        {
          v6 = (_QWORD *)std::wstring::end(v41, v35);
          std::wstring::erase(v41, v36, *v6 - 2LL);
        }
        std::wstring::assign(v40, DomainControllerInfo->DnsForestName);
        while ( v40[2] && *(_WORD *)(*(_QWORD *)std::wstring::end(v40, v36) - 2LL) == 46 )
        {
          v7 = (_QWORD *)std::wstring::end(v40, v35);
          std::wstring::erase(v40, &v33, *v7 - 2LL);
        }
        NetApiBufferFree(DomainControllerInfo);
        DomainControllerInfo = 0;
        std::wstring::wstring(v37);
        if ( !DsGetDcNameW(0, v8, 0, 0, 0x40u, &DomainControllerInfo) )
        {
          std::wstring::assign(v37, L"GC://");
          for ( i = DomainControllerInfo->DomainName; *i == 92; ++i )
            ;
          v11 = std::char_traits<unsigned short>::length(i);
          std::wstring::append(v37, v12, v11);
          v31 = 46;
          v13 = v38;
          if ( v38 )
          {
            v14 = v37;
            v15 = v37[0];
            v16 = v39;
            if ( v39 >= 8 )
              v14 = (unsigned __int16 **)v37[0];
            for ( j = (char *)v14 + 2 * v38 - 2;
                  *(_WORD *)j != 46 || (unsigned int)std::char_traits<unsigned short>::compare(j, &v31, 1);
                  j -= 2 )
            {
              v18 = v37;
              if ( v16 >= 8 )
                v18 = (unsigned __int16 **)v15;
              if ( j == (char *)v18 )
                goto LABEL_36;
            }
            v19 = v37;
            if ( v16 >= 8 )
              v19 = (unsigned __int16 **)v15;
            v20 = (j - (char *)v19) >> 1;
          }
          else
          {
LABEL_36:
            v20 = -1;
          }
          if ( v20 == v13 - 1 )
            std::wstring::erase(v37, v13 - 1, 1);
          NetApiBufferFree(DomainControllerInfo);
          DomainControllerInfo = 0;
          StringCchPrintfW(v43, 0x14u, L":%u", 3268);
          v21 = std::char_traits<unsigned short>::length(v43);
          std::wstring::append(v37, v43, v21);
          v25 = (const unsigned __int16 *)v37;
          if ( v39 >= 8 )
            v25 = v37[0];
          AdminToolsOpenObject(v25, v22, v23, v24, Flags, &v34);
        }
        LOBYTE(v9) = 1;
        std::wstring::_Tidy(v37, v9, 0);
        LOBYTE(v26) = 1;
        std::wstring::_Tidy(v40, v26, 0);
        LOBYTE(v27) = 1;
        std::wstring::_Tidy(v41, v27, 0);
      }
    }
  }
  v1 = Buffer;
LABEL_44:
  if ( DomainControllerInfo )
  {
    NetApiBufferFree(DomainControllerInfo);
    v1 = Buffer;
  }
  if ( v1 )
    DsRoleFreeMemory(v1);
  return (struct IDirectorySearch *)v34;
}

```

## disassembly

```asm
0x18000d078  mov     [rsp-8+arg_8], rbx
0x18000d07d  mov     [rsp-8+arg_10], rdi
0x18000d082  push    rbp
0x18000d083  lea     rbp, [rsp-57h]
0x18000d088  sub     rsp, 100h
0x18000d08f  mov     rax, cs:__security_cookie
0x18000d096  xor     rax, rsp
0x18000d099  mov     [rbp+57h+var_10], rax
0x18000d09d  mov     [rbp+57h+Buffer], 0
0x18000d0a5  mov     [rbp+57h+var_D0], 0
0x18000d0ad  mov     [rbp+57h+var_B0], 0
0x18000d0b5  lea     r8, [rbp+57h+Buffer]; Buffer
0x18000d0b9  mov     edx, 1; InfoLevel
0x18000d0be  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x18000d0c4  test    eax, eax
0x18000d0c6  jnz     loc_18000D3F2
0x18000d0cc  mov     rcx, [rbp+57h+Buffer]
0x18000d0d0  test    dword ptr [rcx], 0FFFFFFFDh
0x18000d0d6  jz      loc_18000D3F6
0x18000d0dc  mov     rax, [rcx+10h]
0x18000d0e0  test    rax, rax
0x18000d0e3  mov     rdi, rax
0x18000d0e6  jnz     short loc_18000D0EC
0x18000d0e8  mov     rdi, [rcx+8]
0x18000d0ec  neg     rax
0x18000d0ef  sbb     ebx, ebx
0x18000d0f1  and     ebx, 10000h
0x18000d0f7  add     ebx, 10010h
0x18000d0fd  lea     rax, [rbp+57h+var_D0]
0x18000d101  mov     [rsp+100h+DomainControllerInfo], rax; DomainControllerInfo
0x18000d106  mov     dword ptr [rsp+100h+Flags], ebx; Flags
0x18000d10a  xor     r9d, r9d; SiteName
0x18000d10d  xor     r8d, r8d; DomainGuid
0x18000d110  mov     rdx, rdi; DomainName
0x18000d113  xor     ecx, ecx; ComputerName
0x18000d115  call    cs:__imp_DsGetDcNameW
0x18000d11b  test    eax, eax
0x18000d11d  jnz     loc_18000D3F2
0x18000d123  mov     rax, [rbp+57h+var_D0]
0x18000d127  test    byte ptr [rax+38h], 10h
0x18000d12b  jz      short loc_18000D171
0x18000d12d  mov     [rbp+57h+var_B8], 0
0x18000d135  bts     ebx, 1Eh
0x18000d139  lea     rax, [rbp+57h+var_B8]
0x18000d13d  mov     [rsp+100h+DomainControllerInfo], rax; DomainControllerInfo
0x18000d142  mov     dword ptr [rsp+100h+Flags], ebx; Flags
0x18000d146  xor     r9d, r9d; SiteName
0x18000d149  xor     r8d, r8d; DomainGuid
0x18000d14c  mov     rdx, rdi; DomainName
0x18000d14f  xor     ecx, ecx; ComputerName
0x18000d151  call    cs:__imp_DsGetDcNameW
0x18000d157  test    eax, eax
0x18000d159  jnz     loc_18000D3F2
0x18000d15f  mov     rcx, [rbp+57h+var_D0]; Buffer
0x18000d163  call    cs:__imp_NetApiBufferFree
0x18000d169  mov     rax, [rbp+57h+var_B8]
0x18000d16d  mov     [rbp+57h+var_D0], rax
0x18000d171  lea     rcx, [rbp+57h+var_58]
0x18000d175  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000d17a  nop
0x18000d17b  lea     rcx, [rbp+57h+var_78]
0x18000d17f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000d184  nop
0x18000d185  mov     rax, [rbp+57h+Buffer]
0x18000d189  mov     rdx, [rax+10h]
0x18000d18d  test    rdx, rdx
0x18000d190  jnz     short loc_18000D19F
0x18000d192  mov     rax, [rbp+57h+var_D0]
0x18000d196  mov     rdx, [rax+28h]
0x18000d19a  test    rdx, rdx
0x18000d19d  jz      short loc_18000D1A8
0x18000d19f  lea     rcx, [rbp+57h+var_58]
0x18000d1a3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000d1a8  mov     edi, 2Eh ; '.'
0x18000d1ad  cmp     [rbp+57h+var_48], 0
0x18000d1b2  jz      short loc_18000D1ED
0x18000d1b4  lea     rdx, [rbp+57h+var_B8]
0x18000d1b8  lea     rcx, [rbp+57h+var_58]
0x18000d1bc  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18000d1c1  mov     rcx, [rax]
0x18000d1c4  cmp     [rcx-2], di
0x18000d1c8  jnz     short loc_18000D1ED
0x18000d1ca  lea     rdx, [rbp+57h+var_A8]
0x18000d1ce  lea     rcx, [rbp+57h+var_58]
0x18000d1d2  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18000d1d7  mov     r8, [rax]
0x18000d1da  sub     r8, 2
0x18000d1de  lea     rdx, [rbp+57h+var_A0]
0x18000d1e2  lea     rcx, [rbp+57h+var_58]
0x18000d1e6  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@@Z; std::wstring::erase(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x18000d1eb  jmp     short loc_18000D1AD
0x18000d1ed  mov     rdx, [rbp+57h+var_D0]
0x18000d1f1  mov     rdx, [rdx+30h]
0x18000d1f5  lea     rcx, [rbp+57h+var_78]
0x18000d1f9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000d1fe  cmp     [rbp+57h+var_68], 0
0x18000d203  jz      short loc_18000D23E
0x18000d205  lea     rdx, [rbp+57h+var_A0]
0x18000d209  lea     rcx, [rbp+57h+var_78]
0x18000d20d  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18000d212  mov     rcx, [rax]
0x18000d215  cmp     [rcx-2], di
0x18000d219  jnz     short loc_18000D23E
0x18000d21b  lea     rdx, [rbp+57h+var_A8]
0x18000d21f  lea     rcx, [rbp+57h+var_78]
0x18000d223  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18000d228  mov     r8, [rax]
0x18000d22b  sub     r8, 2
0x18000d22f  lea     rdx, [rbp+57h+var_B8]
0x18000d233  lea     rcx, [rbp+57h+var_78]
0x18000d237  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@@Z; std::wstring::erase(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x18000d23c  jmp     short loc_18000D1FE
0x18000d23e  mov     rcx, [rbp+57h+var_D0]; Buffer
0x18000d242  call    cs:__imp_NetApiBufferFree
0x18000d248  mov     [rbp+57h+var_D0], 0
0x18000d250  lea     rcx, [rbp+57h+var_78]
0x18000d254  cmp     [rbp+57h+var_60], 8
0x18000d259  cmovnb  rcx, [rbp+57h+var_78]
0x18000d25e  movzx   eax, word ptr [rcx]
0x18000d261  neg     ax
0x18000d264  sbb     r10, r10
0x18000d267  and     r10, rcx
0x18000d26a  lea     rcx, [rbp+57h+var_98]
0x18000d26e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000d273  nop
0x18000d274  lea     rax, [rbp+57h+var_D0]
0x18000d278  mov     [rsp+100h+DomainControllerInfo], rax; DomainControllerInfo
0x18000d27d  mov     dword ptr [rsp+100h+Flags], 40h ; '@'; Flags
0x18000d285  xor     r9d, r9d; SiteName
0x18000d288  xor     r8d, r8d; DomainGuid
0x18000d28b  mov     rdx, r10; DomainName
0x18000d28e  xor     ecx, ecx; ComputerName
0x18000d290  call    cs:__imp_DsGetDcNameW
0x18000d296  test    eax, eax
0x18000d298  jnz     loc_18000D3C6
0x18000d29e  lea     rdx, aGc; "GC://"
0x18000d2a5  lea     rcx, [rbp+57h+var_98]
0x18000d2a9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000d2ae  mov     rax, [rbp+57h+var_D0]
0x18000d2b2  mov     rcx, [rax+28h]
0x18000d2b6  jmp     short loc_18000D2BC
0x18000d2b8  add     rcx, 2
0x18000d2bc  cmp     word ptr [rcx], 5Ch ; '\'
0x18000d2c0  jz      short loc_18000D2B8
0x18000d2c2  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18000d2c7  mov     r8, rax
0x18000d2ca  mov     rdx, rcx
0x18000d2cd  lea     rcx, [rbp+57h+var_98]
0x18000d2d1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000d2d6  mov     [rbp+57h+var_C8], di
0x18000d2da  mov     r10, [rbp+57h+var_88]
0x18000d2de  cmp     r10, 1
0x18000d2e2  jb      short loc_18000D347
0x18000d2e4  lea     rax, [rbp+57h+var_98]
0x18000d2e8  mov     r11, [rbp+57h+var_98]
0x18000d2ec  mov     rbx, [rbp+57h+var_80]
0x18000d2f0  cmp     rbx, 8
0x18000d2f4  cmovnb  rax, r11
0x18000d2f8  lea     r9, [r10-1]
0x18000d2fc  lea     r9, [rax+r9*2]
0x18000d300  cmp     [r9], di
0x18000d304  jnz     short loc_18000D31C
0x18000d306  mov     r8d, 1
0x18000d30c  lea     rdx, [rbp+57h+var_C8]
0x18000d310  mov     rcx, r9
0x18000d313  call    ?compare@?$char_traits@G@std@@SAHPEBG0_K@Z; std::char_traits<ushort>::compare(ushort const *,ushort const *,unsigned __int64)
0x18000d318  test    eax, eax
0x18000d31a  jz      short loc_18000D333
0x18000d31c  lea     rax, [rbp+57h+var_98]
0x18000d320  cmp     rbx, 8
0x18000d324  cmovnb  rax, r11
0x18000d328  cmp     r9, rax
0x18000d32b  jz      short loc_18000D347
0x18000d32d  sub     r9, 2
0x18000d331  jmp     short loc_18000D300
0x18000d333  lea     rax, [rbp+57h+var_98]
0x18000d337  cmp     rbx, 8
0x18000d33b  cmovnb  rax, r11
0x18000d33f  sub     r9, rax
0x18000d342  sar     r9, 1
0x18000d345  jmp     short loc_18000D34B
0x18000d347  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000d34b  lea     rdx, [r10-1]
0x18000d34f  cmp     r9, rdx
0x18000d352  jnz     short loc_18000D363
0x18000d354  mov     r8d, 1
0x18000d35a  lea     rcx, [rbp+57h+var_98]
0x18000d35e  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x18000d363  mov     rcx, [rbp+57h+var_D0]; Buffer
0x18000d367  call    cs:__imp_NetApiBufferFree
0x18000d36d  mov     [rbp+57h+var_D0], 0
0x18000d375  mov     r9d, 0CC4h
0x18000d37b  lea     r8, aU; ":%u"
0x18000d382  mov     edx, 14h; unsigned __int64
0x18000d387  lea     rcx, [rbp+57h+var_38]; unsigned __int16 *
0x18000d38b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d390  lea     rcx, [rbp+57h+var_38]
0x18000d394  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18000d399  mov     r8, rax
0x18000d39c  lea     rdx, [rbp+57h+var_38]
0x18000d3a0  lea     rcx, [rbp+57h+var_98]
0x18000d3a4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000d3a9  lea     rcx, [rbp+57h+var_98]
0x18000d3ad  cmp     [rbp+57h+var_80], 8
0x18000d3b2  cmovnb  rcx, [rbp+57h+var_98]; unsigned __int16 *
0x18000d3b7  lea     rax, [rbp+57h+var_B0]
0x18000d3bb  mov     [rsp+100h+DomainControllerInfo], rax; void **
0x18000d3c0  call    ?AdminToolsOpenObject@@YAJPEBG00KAEBU_GUID@@PEAPEAX@Z; AdminToolsOpenObject(ushort const *,ushort const *,ushort const *,ulong,_GUID const &,void * *)
0x18000d3c5  nop
0x18000d3c6  xor     r8d, r8d
0x18000d3c9  mov     dl, 1
0x18000d3cb  lea     rcx, [rbp+57h+var_98]
0x18000d3cf  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000d3d4  nop
0x18000d3d5  xor     r8d, r8d
0x18000d3d8  mov     dl, 1
0x18000d3da  lea     rcx, [rbp+57h+var_78]
0x18000d3de  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000d3e3  nop
0x18000d3e4  xor     r8d, r8d
0x18000d3e7  mov     dl, 1
0x18000d3e9  lea     rcx, [rbp+57h+var_58]
0x18000d3ed  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000d3f2  mov     rcx, [rbp+57h+Buffer]
0x18000d3f6  mov     rax, [rbp+57h+var_D0]
0x18000d3fa  test    rax, rax
0x18000d3fd  jz      short loc_18000D40C
0x18000d3ff  mov     rcx, rax; Buffer
0x18000d402  call    cs:__imp_NetApiBufferFree
0x18000d408  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18000d40c  test    rcx, rcx
0x18000d40f  jz      short loc_18000D417
0x18000d411  call    cs:__imp_DsRoleFreeMemory
0x18000d417  mov     rax, [rbp+57h+var_B0]
0x18000d41b  mov     rcx, [rbp+57h+var_10]
0x18000d41f  xor     rcx, rsp; StackCookie
0x18000d422  call    __security_check_cookie
0x18000d427  lea     r11, [rsp+100h+var_s0]
0x18000d42f  mov     rbx, [r11+18h]
0x18000d433  mov     rdi, [r11+20h]
0x18000d437  mov     rsp, r11
0x18000d43a  pop     rbp
0x18000d43b  retn
```
