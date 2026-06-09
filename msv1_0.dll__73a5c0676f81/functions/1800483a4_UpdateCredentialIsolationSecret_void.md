# UpdateCredentialIsolationSecret(void)

- ea: `0x1800483a4`
- end: `0x1800486a5`
- name: `?UpdateCredentialIsolationSecret@@YAJXZ`
- size: `769`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180049da8`

## callees

- `0x18000164c`
- `0x180024bd0`
- `0x180046b0c`
- `0x1800483a4`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048539`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048602`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048681`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048690`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048539`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048602`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048681`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048690`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004855d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004855d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180048419`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180048595`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180048419`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180048595`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180048661`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180048661`

## pseudocode

```c
__int64 UpdateCredentialIsolationSecret(void)
{
  const WCHAR *v0; // rsi
  LSTATUS v1; // r12d
  LSTATUS v2; // r15d
  LSTATUS NewRootSecret; // eax
  LSTATUS v4; // edi
  LSTATUS v5; // r14d
  signed int v6; // ebx
  HLOCAL v7; // rcx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  HLOCAL lpData; // rax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  HLOCAL hMem; // [rsp+70h] [rbp-29h] BYREF
  int v16; // [rsp+78h] [rbp-21h] BYREF
  HLOCAL v17; // [rsp+80h] [rbp-19h] BYREF
  signed int v18; // [rsp+88h] [rbp-11h] BYREF
  LSTATUS v19; // [rsp+8Ch] [rbp-Dh] BYREF
  LSTATUS v20; // [rsp+90h] [rbp-9h] BYREF
  int v21; // [rsp+94h] [rbp-5h] BYREF
  LSTATUS v22; // [rsp+98h] [rbp-1h] BYREF
  DWORD v23; // [rsp+9Ch] [rbp+3h] BYREF
  LSTATUS v24; // [rsp+A0h] [rbp+7h] BYREF
  BOOL v25[19]; // [rsp+A4h] [rbp+Bh] BYREF
  bool v26; // [rsp+100h] [rbp+67h] BYREF
  DWORD cbData; // [rsp+108h] [rbp+6Fh] BYREF
  DWORD Type; // [rsp+110h] [rbp+77h] BYREF
  DWORD v29; // [rsp+118h] [rbp+7Fh] BYREF

  v0 = L"IsolatedCredentialsRootSecret";
  v1 = 0;
  Type = 0;
  if ( dword_180087A84 < 0 )
    v0 = L"IsolatedCredentialsRootSecretD";
  hMem = 0;
  cbData = 0;
  v2 = 0;
  v16 = 0;
  v29 = 0;
  v17 = 0;
  NewRootSecret = RegQueryValueExW(NtLmGlobalLsaMsv1_0Key, v0, 0, &Type, 0, &cbData);
  v4 = NewRootSecret;
  if ( NewRootSecret == 2 )
  {
    NewRootSecret = MakeNewRootSecret(v0, &cbData, (unsigned __int8 **)&hMem);
    v5 = NewRootSecret;
LABEL_5:
    v6 = NewRootSecret;
    goto LABEL_9;
  }
  v5 = 0;
  if ( !NewRootSecret )
  {
    lpData = LocalAlloc(0x40u, cbData);
    hMem = lpData;
    if ( !lpData )
    {
      v6 = -1073741801;
      goto LABEL_12;
    }
    v13 = RegQueryValueExW(NtLmGlobalLsaMsv1_0Key, v0, 0, &Type, (LPBYTE)lpData, &cbData);
    v4 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
      {
        v6 = (unsigned __int16)v13 | 0xC0070000;
        goto LABEL_12;
      }
    }
    else if ( Type != 3
           || (v13 = (*(__int64 (__fastcall **)(struct NtlmCredIsoApi *, _QWORD, HLOCAL, int *, DWORD *, HLOCAL *))(*(_QWORD *)LocalhostNtLmCredIsoObj::IsoObj + 112LL))(
                       LocalhostNtLmCredIsoObj::IsoObj,
                       cbData,
                       hMem,
                       &v16,
                       &v29,
                       &v17),
               v1 = v13,
               v13 >= 0) )
    {
      v6 = 0;
      if ( v16 )
      {
        if ( !v29 || !v17 )
          goto LABEL_10;
        v14 = RegSetValueExW(NtLmGlobalLsaMsv1_0Key, v0, 0, 3u, (const BYTE *)v17, v29);
        v2 = v14;
        if ( !v14 )
        {
          LocalFree(hMem);
          v7 = v17;
          cbData = v29;
          goto LABEL_11;
        }
        if ( v14 > 0 )
          v6 = (unsigned __int16)v14 | 0xC0070000;
        else
          v6 = v14;
        LocalFree(v17);
        goto LABEL_12;
      }
      LocalFree(hMem);
      hMem = 0;
      cbData = 0;
      v13 = MakeNewRootSecret(v0, &cbData, (unsigned __int8 **)&hMem);
      v5 = v13;
      if ( v13 >= 0 )
        goto LABEL_10;
    }
    v6 = v13;
    goto LABEL_12;
  }
  if ( NewRootSecret <= 0 )
    goto LABEL_5;
  v6 = (unsigned __int16)NewRootSecret | 0xC0070000;
LABEL_9:
  if ( v6 >= 0 )
  {
LABEL_10:
    v7 = hMem;
LABEL_11:
    NtLmGlobalRootSecret = cbData;
    qword_1800876B0 = (__int64)v7;
    hMem = 0;
  }
LABEL_12:
  if ( (unsigned int)dword_1800861D8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800861D8, 0x400000000000LL) )
  {
    v21 = v16;
    v26 = v17 != 0;
    v23 = Type;
    v18 = v6;
    v19 = v2;
    v25[0] = dword_180087A84 >= 0;
    v20 = v5;
    v22 = v1;
    v24 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)byte_18007A451,
      v9,
      v10,
      (__int64)v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v26,
      (__int64)&v19,
      (__int64)&v18);
  }
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800483a4  push    rbp
0x1800483a6  push    rbx
0x1800483a7  push    rsi
0x1800483a8  push    rdi
0x1800483a9  push    r12
0x1800483ab  push    r13
0x1800483ad  push    r14
0x1800483af  push    r15
0x1800483b1  lea     rbp, [rsp-1Fh]
0x1800483b6  sub     rsp, 0B8h
0x1800483bd  mov     rcx, cs:NtLmGlobalLsaMsv1_0Key; hKey
0x1800483c4  lea     rax, aIsolatedcreden_0; "IsolatedCredentialsRootSecretD"
0x1800483cb  xor     r13d, r13d
0x1800483ce  lea     rsi, aIsolatedcreden; "IsolatedCredentialsRootSecret"
0x1800483d5  test    cs:dword_180087A84, 80000000h
0x1800483df  lea     r9, [rbp+57h+Type]; lpType
0x1800483e3  mov     r12d, r13d
0x1800483e6  mov     [rbp+57h+Type], r13d
0x1800483ea  cmovnz  rsi, rax
0x1800483ee  mov     [rbp+57h+hMem], r13
0x1800483f2  lea     rax, [rbp+57h+cbData]
0x1800483f6  mov     [rbp+57h+cbData], r13d
0x1800483fa  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x1800483ff  xor     r8d, r8d; lpReserved
0x180048402  mov     rdx, rsi; lpValueName
0x180048405  mov     [rsp+0F0h+lpData], r13; lpData
0x18004840a  mov     r15d, r13d
0x18004840d  mov     [rbp+57h+var_78], r13d
0x180048411  mov     [rbp+57h+arg_18], r13d
0x180048415  mov     [rbp+57h+var_70], r13
0x180048419  call    cs:__imp_RegQueryValueExW
0x18004841f  mov     edi, eax
0x180048421  cmp     eax, 2
0x180048424  jnz     short loc_18004843D
0x180048426  lea     r8, [rbp+57h+hMem]; unsigned __int8 **
0x18004842a  mov     rcx, rsi; lpValueName
0x18004842d  lea     rdx, [rbp+57h+cbData]; unsigned int *
0x180048431  call    ?MakeNewRootSecret@@YAJPEBGPEAKPEAPEAE@Z; MakeNewRootSecret(ushort const *,ulong *,uchar * *)
0x180048436  mov     r14d, eax
0x180048439  mov     ebx, eax
0x18004843b  jmp     short loc_180048453
0x18004843d  mov     r14d, r13d
0x180048440  test    eax, eax
0x180048442  jz      loc_180048555
0x180048448  jle     short loc_180048439
0x18004844a  movzx   ebx, ax
0x18004844d  or      ebx, 0C0070000h
0x180048453  test    ebx, ebx
0x180048455  js      short loc_18004846F
0x180048457  mov     rcx, [rbp+57h+hMem]
0x18004845b  mov     eax, [rbp+57h+cbData]
0x18004845e  mov     cs:NtLmGlobalRootSecret, eax
0x180048464  mov     cs:qword_1800876B0, rcx
0x18004846b  mov     [rbp+57h+hMem], r13
0x18004846f  mov     eax, cs:dword_1800861D8
0x180048475  cmp     eax, 5
0x180048478  jbe     loc_180048530
0x18004847e  mov     rdx, 400000000000h
0x180048488  lea     rcx, dword_1800861D8
0x18004848f  call    _tlgKeywordOn
0x180048494  test    al, al
0x180048496  jz      loc_180048530
0x18004849c  mov     eax, [rbp+57h+var_78]
0x18004849f  lea     rdx, byte_18007A451
0x1800484a6  cmp     [rbp+57h+var_70], r13
0x1800484aa  mov     [rbp+57h+var_5C], eax
0x1800484ad  mov     eax, [rbp+57h+Type]
0x1800484b0  setnz   [rbp+57h+arg_0]
0x1800484b4  mov     [rbp+57h+var_54], eax
0x1800484b7  mov     eax, cs:dword_180087A84
0x1800484bd  shr     eax, 1Fh
0x1800484c0  not     eax
0x1800484c2  mov     [rbp+57h+var_68], ebx
0x1800484c5  and     eax, 1
0x1800484c8  mov     [rbp+57h+var_64], r15d
0x1800484cc  mov     [rbp+57h+var_4C], eax
0x1800484cf  lea     rax, [rbp+57h+var_68]
0x1800484d3  mov     [rsp+0F0h+var_90], rax
0x1800484d8  lea     rax, [rbp+57h+var_64]
0x1800484dc  mov     [rsp+0F0h+var_98], rax
0x1800484e1  lea     rax, [rbp+57h+arg_0]
0x1800484e5  mov     [rsp+0F0h+var_A0], rax
0x1800484ea  lea     rax, [rbp+57h+var_60]
0x1800484ee  mov     [rsp+0F0h+var_A8], rax
0x1800484f3  lea     rax, [rbp+57h+var_5C]
0x1800484f7  mov     [rsp+0F0h+var_B0], rax
0x1800484fc  lea     rax, [rbp+57h+var_58]
0x180048500  mov     [rsp+0F0h+var_B8], rax
0x180048505  lea     rax, [rbp+57h+var_54]
0x180048509  mov     [rsp+0F0h+var_C0], rax
0x18004850e  lea     rax, [rbp+57h+var_50]
0x180048512  mov     [rsp+0F0h+lpcbData], rax
0x180048517  lea     rax, [rbp+57h+var_4C]
0x18004851b  mov     [rsp+0F0h+lpData], rax
0x180048520  mov     [rbp+57h+var_60], r14d
0x180048524  mov     [rbp+57h+var_58], r12d
0x180048528  mov     [rbp+57h+var_50], edi
0x18004852b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U?$_tlgWrapperByVal@$00@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33333AEBU?$_tlgWrapperByVal@$00@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180048530  mov     rcx, [rbp+57h+hMem]; hMem
0x180048534  test    rcx, rcx
0x180048537  jz      short loc_18004853F
0x180048539  call    cs:__imp_LocalFree
0x18004853f  mov     eax, ebx
0x180048541  add     rsp, 0B8h
0x180048548  pop     r15
0x18004854a  pop     r14
0x18004854c  pop     r13
0x18004854e  pop     r12
0x180048550  pop     rdi
0x180048551  pop     rsi
0x180048552  pop     rbx
0x180048553  pop     rbp
0x180048554  retn
0x180048555  mov     edx, [rbp+57h+cbData]; uBytes
0x180048558  mov     ecx, 40h ; '@'; uFlags
0x18004855d  call    cs:__imp_LocalAlloc
0x180048563  mov     [rbp+57h+hMem], rax
0x180048567  test    rax, rax
0x18004856a  jnz     short loc_180048576
0x18004856c  mov     ebx, 0C0000017h
0x180048571  jmp     loc_18004846F
0x180048576  lea     rcx, [rbp+57h+cbData]
0x18004857a  xor     r8d, r8d; lpReserved
0x18004857d  mov     [rsp+0F0h+lpcbData], rcx; lpcbData
0x180048582  lea     r9, [rbp+57h+Type]; lpType
0x180048586  mov     rcx, cs:NtLmGlobalLsaMsv1_0Key; hKey
0x18004858d  mov     rdx, rsi; lpValueName
0x180048590  mov     [rsp+0F0h+lpData], rax; lpData
0x180048595  call    cs:__imp_RegQueryValueExW
0x18004859b  mov     edi, eax
0x18004859d  test    eax, eax
0x18004859f  jz      short loc_1800485B1
0x1800485a1  jle     short loc_1800485EE
0x1800485a3  movzx   ebx, ax
0x1800485a6  or      ebx, 0C0070000h
0x1800485ac  jmp     loc_18004846F
0x1800485b1  cmp     [rbp+57h+Type], 3
0x1800485b5  jnz     short loc_1800485F5
0x1800485b7  mov     rcx, cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x1800485be  lea     rdx, [rbp+57h+var_70]
0x1800485c2  mov     r8, [rbp+57h+hMem]
0x1800485c6  lea     r9, [rbp+57h+var_78]
0x1800485ca  mov     [rsp+0F0h+lpcbData], rdx
0x1800485cf  lea     rdx, [rbp+57h+arg_18]
0x1800485d3  mov     [rsp+0F0h+lpData], rdx
0x1800485d8  mov     rax, [rcx]
0x1800485db  mov     edx, [rbp+57h+cbData]
0x1800485de  mov     rax, [rax+70h]
0x1800485e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485e7  mov     r12d, eax
0x1800485ea  test    eax, eax
0x1800485ec  jns     short loc_1800485F5
0x1800485ee  mov     ebx, eax
0x1800485f0  jmp     loc_18004846F
0x1800485f5  mov     ebx, r13d
0x1800485f8  cmp     [rbp+57h+var_78], r13d
0x1800485fc  jnz     short loc_18004862D
0x1800485fe  mov     rcx, [rbp+57h+hMem]; hMem
0x180048602  call    cs:__imp_LocalFree
0x180048608  lea     r8, [rbp+57h+hMem]; unsigned __int8 **
0x18004860c  mov     [rbp+57h+hMem], r13
0x180048610  lea     rdx, [rbp+57h+cbData]; unsigned int *
0x180048614  mov     [rbp+57h+cbData], r13d
0x180048618  mov     rcx, rsi; lpValueName
0x18004861b  call    ?MakeNewRootSecret@@YAJPEBGPEAKPEAPEAE@Z; MakeNewRootSecret(ushort const *,ulong *,uchar * *)
0x180048620  mov     r14d, eax
0x180048623  test    eax, eax
0x180048625  jns     loc_180048457
0x18004862b  jmp     short loc_1800485EE
0x18004862d  mov     eax, [rbp+57h+arg_18]
0x180048630  test    eax, eax
0x180048632  jz      loc_180048457
0x180048638  mov     rcx, [rbp+57h+var_70]
0x18004863c  test    rcx, rcx
0x18004863f  jz      loc_180048457
0x180048645  mov     dword ptr [rsp+0F0h+lpcbData], eax; cbData
0x180048649  mov     r9d, 3; dwType
0x18004864f  mov     [rsp+0F0h+lpData], rcx; lpData
0x180048654  xor     r8d, r8d; Reserved
0x180048657  mov     rcx, cs:NtLmGlobalLsaMsv1_0Key; hKey
0x18004865e  mov     rdx, rsi; lpValueName
0x180048661  call    cs:__imp_RegSetValueExW
0x180048667  mov     r15d, eax
0x18004866a  test    eax, eax
0x18004866c  jz      short loc_18004868C
0x18004866e  jg      short loc_180048674
0x180048670  mov     ebx, eax
0x180048672  jmp     short loc_18004867D
0x180048674  movzx   ebx, ax
0x180048677  or      ebx, 0C0070000h
0x18004867d  mov     rcx, [rbp+57h+var_70]; hMem
0x180048681  call    cs:__imp_LocalFree
0x180048687  jmp     loc_18004846F
0x18004868c  mov     rcx, [rbp+57h+hMem]; hMem
0x180048690  call    cs:__imp_LocalFree
0x180048696  mov     eax, [rbp+57h+arg_18]
0x180048699  mov     rcx, [rbp+57h+var_70]
0x18004869d  mov     [rbp+57h+cbData], eax
0x1800486a0  jmp     loc_18004845B
```
