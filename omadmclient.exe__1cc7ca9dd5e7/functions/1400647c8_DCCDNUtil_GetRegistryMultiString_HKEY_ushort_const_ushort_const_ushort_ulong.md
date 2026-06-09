# DCCDNUtil_GetRegistryMultiString(HKEY__ *,ushort const *,ushort const *,ushort * *,ulong *)

- ea: `0x1400647c8`
- end: `0x1400649a2`
- name: `?DCCDNUtil_GetRegistryMultiString@@YAJPEAUHKEY__@@PEBG1PEAPEAGPEAK@Z`
- size: `474`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x14005c570`

## callees

- `0x1400036e4`
- `0x140003eb4`
- `0x140005864`
- `0x14000b0f4`
- `0x1400647c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006485a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006485a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400648a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006493a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400648a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006493a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006497a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006497a`

## pseudocode

```c
__int64 __fastcall DCCDNUtil_GetRegistryMultiString(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE **a4,
        unsigned int *a5)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  unsigned int *v10; // r14
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  unsigned __int64 v13; // rax
  BYTE *v14; // rax
  BYTE *v15; // rdi
  LSTATUS v16; // eax
  DWORD v17; // eax
  int phkResult; // [rsp+20h] [rbp-20h]
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF

  Type = 7;
  hKey = 0;
  cbData = 0;
  if ( !a1 )
  {
    v8 = 680;
LABEL_3:
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)0x80070057LL,
      phkResult);
    return v9;
  }
  if ( !a4 )
  {
    v8 = 681;
    goto LABEL_3;
  }
  v10 = a5;
  if ( !a5 )
  {
    v8 = 682;
    goto LABEL_3;
  }
  if ( a2 )
  {
    v11 = RegOpenKeyExW(a1, a2, 0, 0x20119u, &hKey);
    v9 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
LABEL_29:
      if ( hKey )
        RegCloseKey(hKey);
      return v9;
    }
    a1 = hKey;
  }
  else
  {
    hKey = a1;
  }
  v12 = RegQueryValueExW(a1, a3, 0, &Type, 0, &cbData);
  v9 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v9 = (unsigned __int16)v12 | 0x80070000;
  }
  else if ( Type == 7 )
  {
    v13 = 2LL * cbData;
    if ( !is_mul_ok(cbData, 2u) )
      v13 = -1;
    v14 = (BYTE *)operator new[](v13, (const struct std::nothrow_t *)std::nothrow);
    v15 = v14;
    if ( v14 )
    {
      memset_0(v14, 0, cbData);
      v16 = RegQueryValueExW(hKey, a3, 0, &Type, v15, &cbData);
      v9 = v16;
      if ( v16 )
      {
        if ( v16 > 0 )
          v9 = (unsigned __int16)v16 | 0x80070000;
        operator delete(v15);
      }
      else
      {
        v17 = cbData;
        v9 = 0;
        *a4 = v15;
        *v10 = v17;
      }
    }
    else
    {
      v9 = -2147024882;
    }
  }
  else
  {
    v9 = -2147418113;
  }
  if ( a2 )
    goto LABEL_29;
  return v9;
}

```

## disassembly

```asm
0x1400647c8  mov     [rsp-28h+arg_8], rbx
0x1400647cd  mov     [rsp-28h+arg_10], rsi
0x1400647d2  push    rbp
0x1400647d3  push    rdi
0x1400647d4  push    r12
0x1400647d6  push    r14
0x1400647d8  push    r15
0x1400647da  mov     rbp, rsp
0x1400647dd  sub     rsp, 40h
0x1400647e1  mov     [rbp+Type], 7
0x1400647e8  mov     r15, r9
0x1400647eb  mov     [rbp+hKey], 0
0x1400647f3  mov     r12, r8
0x1400647f6  mov     [rbp+cbData], 0
0x1400647fd  mov     rsi, rdx
0x140064800  test    rcx, rcx
0x140064803  jnz     short loc_140064827
0x140064805  mov     edx, 2A8h; void *
0x14006480a  mov     rcx, [rbp+28h]; this
0x14006480e  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x140064815  mov     ebx, 80070057h
0x14006481a  mov     r9d, ebx; char *
0x14006481d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140064822  jmp     loc_140064986
0x140064827  test    r15, r15
0x14006482a  jnz     short loc_140064833
0x14006482c  mov     edx, 2A9h
0x140064831  jmp     short loc_14006480A
0x140064833  mov     r14, [rbp+arg_20]
0x140064837  test    r14, r14
0x14006483a  jnz     short loc_140064843
0x14006483c  mov     edx, 2AAh; lpSubKey
0x140064841  jmp     short loc_14006480A
0x140064843  test    rsi, rsi
0x140064846  jz      short loc_140064886
0x140064848  lea     rax, [rbp+hKey]
0x14006484c  mov     r9d, 20119h; samDesired
0x140064852  xor     r8d, r8d; ulOptions
0x140064855  mov     [rsp+40h+phkResult], rax; phkResult
0x14006485a  call    cs:__imp_RegOpenKeyExW
0x140064861  nop     dword ptr [rax+rax+00h]
0x140064866  mov     ebx, eax
0x140064868  test    eax, eax
0x14006486a  jz      short loc_140064880
0x14006486c  jle     loc_140064971
0x140064872  movzx   ebx, ax
0x140064875  or      ebx, 80070000h
0x14006487b  jmp     loc_140064971
0x140064880  mov     rcx, [rbp+hKey]; hKey
0x140064884  jmp     short loc_14006488A
0x140064886  mov     [rbp+hKey], rcx
0x14006488a  lea     rax, [rbp+cbData]
0x14006488e  xor     r8d, r8d; lpReserved
0x140064891  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140064896  lea     r9, [rbp+Type]; lpType
0x14006489a  mov     rdx, r12; lpValueName
0x14006489d  mov     [rsp+40h+phkResult], 0; lpData
0x1400648a6  call    cs:__imp_RegQueryValueExW
0x1400648ad  nop     dword ptr [rax+rax+00h]
0x1400648b2  mov     ebx, eax
0x1400648b4  test    eax, eax
0x1400648b6  jz      short loc_1400648CC
0x1400648b8  jle     loc_14006496C
0x1400648be  movzx   ebx, ax
0x1400648c1  or      ebx, 80070000h
0x1400648c7  jmp     loc_14006496C
0x1400648cc  cmp     [rbp+Type], 7
0x1400648d0  jz      short loc_1400648DC
0x1400648d2  mov     ebx, 8000FFFFh
0x1400648d7  jmp     loc_14006496C
0x1400648dc  mov     ecx, [rbp+cbData]
0x1400648df  mov     eax, 2
0x1400648e4  mul     rcx
0x1400648e7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400648ee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400648f5  cmovb   rax, rcx
0x1400648f9  mov     rcx, rax; unsigned __int64
0x1400648fc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140064901  mov     rdi, rax
0x140064904  test    rax, rax
0x140064907  jnz     short loc_140064910
0x140064909  mov     ebx, 8007000Eh
0x14006490e  jmp     short loc_14006496C
0x140064910  mov     r8d, [rbp+cbData]; Size
0x140064914  xor     edx, edx; Val
0x140064916  mov     rcx, rdi; void *
0x140064919  call    memset_0
0x14006491e  mov     rcx, [rbp+hKey]; hKey
0x140064922  lea     rax, [rbp+cbData]
0x140064926  mov     [rsp+40h+lpcbData], rax; lpcbData
0x14006492b  lea     r9, [rbp+Type]; lpType
0x14006492f  xor     r8d, r8d; lpReserved
0x140064932  mov     [rsp+40h+phkResult], rdi; lpData
0x140064937  mov     rdx, r12; lpValueName
0x14006493a  call    cs:__imp_RegQueryValueExW
0x140064941  nop     dword ptr [rax+rax+00h]
0x140064946  mov     ebx, eax
0x140064948  test    eax, eax
0x14006494a  jz      short loc_140064961
0x14006494c  jle     short loc_140064957
0x14006494e  movzx   ebx, ax
0x140064951  or      ebx, 80070000h
0x140064957  mov     rcx, rdi; Block
0x14006495a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14006495f  jmp     short loc_14006496C
0x140064961  mov     eax, [rbp+cbData]
0x140064964  xor     ebx, ebx
0x140064966  mov     [r15], rdi
0x140064969  mov     [r14], eax
0x14006496c  test    rsi, rsi
0x14006496f  jz      short loc_140064986
0x140064971  mov     rcx, [rbp+hKey]; hKey
0x140064975  test    rcx, rcx
0x140064978  jz      short loc_140064986
0x14006497a  call    cs:__imp_RegCloseKey
0x140064981  nop     dword ptr [rax+rax+00h]
0x140064986  lea     r11, [rsp+40h+var_s0]
0x14006498b  mov     eax, ebx
0x14006498d  mov     rbx, [r11+38h]
0x140064991  mov     rsi, [r11+40h]
0x140064995  mov     rsp, r11
0x140064998  pop     r15
0x14006499a  pop     r14
0x14006499c  pop     r12
0x14006499e  pop     rdi
0x14006499f  pop     rbp
0x1400649a0  retn
```
