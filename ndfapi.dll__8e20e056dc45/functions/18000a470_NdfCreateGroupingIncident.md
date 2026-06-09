# NdfCreateGroupingIncident

- ea: `0x18000a470`
- end: `0x18000a725`
- name: `NdfCreateGroupingIncident`
- size: `693`
- prototype: `HRESULT __stdcall(LPCWSTR CloudName, LPCWSTR GroupName, LPCWSTR Identity, LPCWSTR Invitation, SOCKET_ADDRESS_LIST *Addresses, LPCWSTR appId, NDFHANDLE *handle)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000721c`
- `0x180007ee4`
- `0x1800098b0`
- `0x18000a470`
- `0x18000a9e0`
- `0x18001f652`
- `0x18001f690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a6f5`
- `KERNEL32!GetLastError` at `0x18000a6f5`
- `KERNEL32!GetModuleFileNameW` at `0x18000a630`
- `KERNEL32!GetModuleFileNameW` at `0x18000a630`
- `wdi!WdiCancel` at `0x18000a4e5`
- `wdi!WdiCancel` at `0x18000a4e5`

## string_xrefs

- `0x18000a4c8`: `NdfCreateGroupingIncident`

## pseudocode

```c
HRESULT __stdcall NdfCreateGroupingIncident(
        LPCWSTR CloudName,
        LPCWSTR GroupName,
        LPCWSTR Identity,
        LPCWSTR Invitation,
        SOCKET_ADDRESS_LIST *Addresses,
        LPCWSTR appId,
        NDFHANDLE *handle)
{
  unsigned __int16 v7; // bx
  HRESULT result; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rsi
  __int64 v16; // rcx
  int v17; // eax
  void *v18; // rdx
  __int64 v19; // r8
  LPCWSTR i; // rax
  __int64 v21; // rax
  unsigned __int16 v22; // bx
  INT v23; // edx
  __int64 v24; // r8
  unsigned int v25; // ecx
  unsigned int v26; // r9d
  size_t v27[4]; // [rsp+20h] [rbp-E0h] BYREF
  HELPER_ATTRIBUTE attributes[6]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Filename[264]; // [rsp+3A0h] [rbp+2A0h] BYREF

  v7 = 0;
  v27[3] = 15;
  v27[2] = 0;
  LOBYTE(v27[0]) = 0;
  std::string::assign(v27, "NdfCreateGroupingIncident", 0x19u);
  TelemeterAPICall(v27);
  if ( (unsigned int)WdiCancel(0) == -2147023611 )
    return -2147467260;
  if ( !handle || Addresses && Addresses->iAddressCount <= 0 )
    return -2146895611;
  if ( CloudName )
  {
    attributes[0].Int64 = (LONGLONG)CloudName;
    attributes[0].pwszName = L"cloudname";
    v7 = 1;
    attributes[0].type = AT_STRING;
  }
  if ( GroupName )
  {
    v13 = v7++;
    attributes[v13].pwszName = L"groupname";
    attributes[v13].type = AT_STRING;
    *((_QWORD *)&attributes[0].Boolean + v13 * 18) = GroupName;
  }
  if ( Identity )
  {
    v14 = v7++;
    attributes[v14].pwszName = L"identity";
    attributes[v14].type = AT_STRING;
    *((_QWORD *)&attributes[0].Boolean + v14 * 18) = Identity;
  }
  if ( Invitation )
  {
    v15 = v7;
    v16 = -1;
    attributes[v15].pwszName = L"invitation";
    attributes[v15].type = AT_OCTET_STRING;
    do
      ++v16;
    while ( Invitation[v16] );
    v17 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v16 + 1);
    *(&attributes[0].Int64 + 18 * v7 + 1) = (LONGLONG)Invitation;
    *(&attributes[0].Boolean + 36 * v7++) = 2 * v17;
  }
  memset_0(Filename, 0, 0x208u);
  v18 = (void *)appId;
  v19 = 260;
  if ( appId )
  {
    for ( i = appId; *i; ++i )
    {
      if ( !--v19 )
        return -2147024809;
    }
  }
  else
  {
    if ( !GetModuleFileNameW(0, Filename, 0x104u) )
      return GetLastError();
    v18 = Filename;
  }
  v21 = v7;
  v22 = v7 + 1;
  v21 *= 144;
  *(LPWSTR *)((char *)&attributes[0].pwszName + v21) = L"appid";
  *(ATTRIBUTE_TYPE *)((char *)&attributes[0].type + v21) = AT_STRING;
  *(_QWORD *)((char *)&attributes[0].Boolean + v21) = v18;
  if ( Addresses && Addresses->iAddressCount > 0 )
  {
    v23 = 0;
    v24 = v22;
    v25 = 16 * Addresses->iAddressCount + 8;
    v26 = v25;
    attributes[v24].pwszName = L"connectaddress";
    attributes[v24].type = AT_OCTET_STRING;
    while ( 1 )
    {
      v25 += Addresses->Address[v23].iSockaddrLength;
      if ( v25 < v26 )
        return -2146895611;
      ++v23;
      v26 = v25;
      if ( v23 >= Addresses->iAddressCount )
      {
        *(&attributes[0].Boolean + 36 * v22++) = v25;
        *(&attributes[0].Int64 + v24 * 18 + 1) = (LONGLONG)Addresses;
        break;
      }
    }
  }
  result = NdfCreateIncident(L"GroupingHelperClass", v22, attributes, handle);
  if ( result >= 0 )
  {
    if ( *handle )
      *((_DWORD *)*handle + 4) = 9;
  }
  return result;
}

```

## disassembly

```asm
0x18000a470  push    rbp
0x18000a472  push    rbx
0x18000a473  push    rsi
0x18000a474  push    rdi
0x18000a475  push    r12
0x18000a477  push    r13
0x18000a479  push    r14
0x18000a47b  push    r15
0x18000a47d  lea     rbp, [rsp-4C8h]
0x18000a485  sub     rsp, 5C8h
0x18000a48c  mov     rax, cs:__security_cookie
0x18000a493  xor     rax, rsp
0x18000a496  mov     [rbp+500h+var_50], rax
0x18000a49d  mov     r13, [rbp+500h+handle]
0x18000a4a4  xor     ebx, ebx
0x18000a4a6  mov     r15, r8
0x18000a4a9  mov     [rsp+600h+var_5C8], 0Fh
0x18000a4b2  mov     r14, rdx
0x18000a4b5  mov     [rsp+600h+var_5D0], rbx
0x18000a4ba  mov     rsi, rcx
0x18000a4bd  mov     [rsp+600h+var_5E0], bl
0x18000a4c1  lea     r8d, [rbx+19h]; Size
0x18000a4c5  mov     r12, r9
0x18000a4c8  lea     rdx, aNdfcreategroup_0; "NdfCreateGroupingIncident"
0x18000a4cf  lea     rcx, [rsp+600h+var_5E0]; void *
0x18000a4d4  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18000a4d9  lea     rcx, [rsp+600h+var_5E0]
0x18000a4de  call    ?TelemeterAPICall@@YAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; TelemeterAPICall(std::string)
0x18000a4e3  xor     ecx, ecx
0x18000a4e5  call    cs:__imp_WdiCancel
0x18000a4eb  cmp     eax, 80070505h
0x18000a4f0  jnz     short loc_18000A4FC
0x18000a4f2  mov     eax, 80004004h
0x18000a4f7  jmp     loc_18000A702
0x18000a4fc  test    r13, r13
0x18000a4ff  jz      loc_18000A6FD
0x18000a505  mov     rdi, [rbp+500h+Addresses]
0x18000a50c  test    rdi, rdi
0x18000a50f  jz      short loc_18000A519
0x18000a511  cmp     [rdi], ebx
0x18000a513  jle     loc_18000A6FD
0x18000a519  mov     edx, 0Ah
0x18000a51e  test    rsi, rsi
0x18000a521  jz      short loc_18000A540
0x18000a523  mov     qword ptr [rsp+600h+attributes.10h], rsi
0x18000a528  lea     rax, aCloudname; "cloudname"
0x18000a52f  lea     esi, [rdx-9]
0x18000a532  mov     [rsp+600h+attributes.pwszName], rax
0x18000a537  movzx   ebx, si
0x18000a53a  mov     [rsp+600h+attributes.type], edx
0x18000a53e  jmp     short loc_18000A545
0x18000a540  mov     esi, 1
0x18000a545  test    r14, r14
0x18000a548  jz      short loc_18000A56C
0x18000a54a  movzx   eax, bx
0x18000a54d  lea     rcx, [rax+rax*8]
0x18000a551  add     rcx, rcx
0x18000a554  lea     rax, aGroupname; "groupname"
0x18000a55b  add     bx, si
0x18000a55e  mov     [rsp+rcx*8+600h+attributes.pwszName], rax
0x18000a563  mov     [rsp+rcx*8+600h+attributes.type], edx
0x18000a567  mov     qword ptr [rsp+rcx*8+600h+attributes.10h], r14
0x18000a56c  xor     r14d, r14d
0x18000a56f  test    r15, r15
0x18000a572  jz      short loc_18000A596
0x18000a574  movzx   eax, bx
0x18000a577  lea     rcx, [rax+rax*8]
0x18000a57b  add     rcx, rcx
0x18000a57e  lea     rax, aIdentity; "identity"
0x18000a585  add     bx, si
0x18000a588  mov     [rsp+rcx*8+600h+attributes.pwszName], rax
0x18000a58d  mov     [rsp+rcx*8+600h+attributes.type], edx
0x18000a591  mov     qword ptr [rsp+rcx*8+600h+attributes.10h], r15
0x18000a596  mov     r15d, 0Eh
0x18000a59c  test    r12, r12
0x18000a59f  jz      short loc_18000A5E5
0x18000a5a1  movzx   eax, bx
0x18000a5a4  lea     rsi, [rax+rax*8]
0x18000a5a8  add     rsi, rsi
0x18000a5ab  lea     rax, aInvitation; "invitation"
0x18000a5b2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000a5b6  mov     [rsp+rsi*8+600h+attributes.pwszName], rax
0x18000a5bb  mov     [rsp+rsi*8+600h+attributes.type], r15d
0x18000a5c0  inc     rcx
0x18000a5c3  cmp     [r12+rcx*2], r14w
0x18000a5c8  jnz     short loc_18000A5C0
0x18000a5ca  inc     rcx
0x18000a5cd  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000a5d2  add     eax, eax
0x18000a5d4  mov     qword ptr [rsp+rsi*8+600h+attributes.10h+8], r12
0x18000a5d9  mov     dword ptr [rsp+rsi*8+600h+attributes.10h], eax
0x18000a5dd  mov     esi, 1
0x18000a5e2  add     bx, si
0x18000a5e5  xor     edx, edx; Val
0x18000a5e7  lea     rcx, [rbp+500h+Filename]; void *
0x18000a5ee  mov     r8d, 208h; Size
0x18000a5f4  call    memset_0
0x18000a5f9  mov     rdx, [rbp+500h+appId]
0x18000a600  mov     r8d, 104h; nSize
0x18000a606  test    rdx, rdx
0x18000a609  jz      short loc_18000A627
0x18000a60b  mov     rax, rdx
0x18000a60e  cmp     [rax], r14w
0x18000a612  jz      short loc_18000A645
0x18000a614  add     rax, 2
0x18000a618  sub     r8, rsi
0x18000a61b  jnz     short loc_18000A60E
0x18000a61d  mov     eax, 80070057h
0x18000a622  jmp     loc_18000A702
0x18000a627  lea     rdx, [rbp+500h+Filename]; lpFilename
0x18000a62e  xor     ecx, ecx; hModule
0x18000a630  call    cs:__imp_GetModuleFileNameW
0x18000a636  test    eax, eax
0x18000a638  jz      loc_18000A6F5
0x18000a63e  lea     rdx, [rbp+500h+Filename]
0x18000a645  movzx   eax, bx
0x18000a648  mov     ecx, 90h
0x18000a64d  movzx   eax, bx
0x18000a650  add     bx, si
0x18000a653  imul    rax, rcx
0x18000a657  lea     rcx, aAppid; "appid"
0x18000a65e  mov     [rsp+rax+600h+attributes.pwszName], rcx
0x18000a663  mov     [rsp+rax+600h+attributes.type], 0Ah
0x18000a66b  mov     qword ptr [rsp+rax+600h+attributes.10h], rdx
0x18000a670  test    rdi, rdi
0x18000a673  jz      short loc_18000A6C8
0x18000a675  cmp     [rdi], r14d
0x18000a678  jle     short loc_18000A6C8
0x18000a67a  mov     ecx, [rdi]
0x18000a67c  mov     edx, r14d
0x18000a67f  movzx   eax, bx
0x18000a682  shl     ecx, 4
0x18000a685  lea     r8, [rax+rax*8]
0x18000a689  add     r8, r8
0x18000a68c  lea     rax, aConnectaddress; "connectaddress"
0x18000a693  add     ecx, 8
0x18000a696  mov     r9d, ecx
0x18000a699  mov     [rsp+r8*8+600h+attributes.pwszName], rax
0x18000a69e  mov     [rsp+r8*8+600h+attributes.type], r15d
0x18000a6a3  mov     eax, edx
0x18000a6a5  shl     rax, 4
0x18000a6a9  add     ecx, [rax+rdi+10h]
0x18000a6ad  cmp     ecx, r9d
0x18000a6b0  jb      short loc_18000A6FD
0x18000a6b2  add     edx, esi
0x18000a6b4  mov     r9d, ecx
0x18000a6b7  cmp     edx, [rdi]
0x18000a6b9  jl      short loc_18000A6A3
0x18000a6bb  mov     dword ptr [rsp+r8*8+600h+attributes.10h], ecx
0x18000a6c0  add     bx, si
0x18000a6c3  mov     qword ptr [rsp+r8*8+600h+attributes.10h+8], rdi
0x18000a6c8  movzx   edx, bx; celt
0x18000a6cb  lea     r8, [rsp+600h+attributes]; attributes
0x18000a6d0  mov     r9, r13; handle
0x18000a6d3  lea     rcx, aGroupinghelper; "GroupingHelperClass"
0x18000a6da  call    NdfCreateIncident
0x18000a6df  test    eax, eax
0x18000a6e1  js      short loc_18000A702
0x18000a6e3  mov     rcx, [r13+0]
0x18000a6e7  test    rcx, rcx
0x18000a6ea  jz      short loc_18000A702
0x18000a6ec  mov     dword ptr [rcx+10h], 9
0x18000a6f3  jmp     short loc_18000A702
0x18000a6f5  call    cs:__imp_GetLastError
0x18000a6fb  jmp     short loc_18000A702
0x18000a6fd  mov     eax, 8008F905h
0x18000a702  mov     rcx, [rbp+500h+var_50]
0x18000a709  xor     rcx, rsp; StackCookie
0x18000a70c  call    __security_check_cookie
0x18000a711  add     rsp, 5C8h
0x18000a718  pop     r15
0x18000a71a  pop     r14
0x18000a71c  pop     r13
0x18000a71e  pop     r12
0x18000a720  pop     rdi
0x18000a721  pop     rsi
0x18000a722  pop     rbx
0x18000a723  pop     rbp
0x18000a724  retn
```
