# RRasRoutingDomainConfig::OpenInterfacesKey(HKEY__ * *)

- ea: `0x18003eda8`
- end: `0x18003eef6`
- name: `?OpenInterfacesKey@RRasRoutingDomainConfig@@QEAAKPEAPEAUHKEY__@@@Z`
- size: `334`
- prototype: `unsigned int(RRasRoutingDomainConfig *__hidden this, HKEY *)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18003a874`
- `0x18003b26c`
- `0x18003b930`
- `0x18003ec48`

## callees

- `0x18003eda8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18003ee31`
- `ADVAPI32!RegCreateKeyExW` at `0x18003ee31`

## string_xrefs

- `0x18003ee59`: `RRasRoutingDomainConfig::OpenInterfacesKey`
- `0x18003ee64`: `%s: RegCreateKeyEx failed %d.`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::OpenInterfacesKey(RRasRoutingDomainConfig *this, HKEY *a2)
{
  HKEY v4; // rcx
  unsigned int Key; // ebx
  const struct _GUID *v6; // r9
  GUID v8; // [rsp+50h] [rbp-B0h] BYREF
  int v9; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v10; // [rsp+64h] [rbp-9Ch]
  __int128 v11; // [rsp+74h] [rbp-8Ch]
  int v12; // [rsp+84h] [rbp-7Ch]
  int v13; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v14[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  v4 = (HKEY)*((_QWORD *)this + 103);
  v9 = 0;
  v10 = 0;
  v12 = 0;
  v11 = 0;
  Key = RegCreateKeyExW(v4, L"Interfaces", 0, 0, 0, 0xF003Fu, 0, a2, 0);
  if ( Key || !a2 )
  {
    if ( (_QWORD)xmmword_1800710A0 )
    {
      LOWORD(v13) = 0;
      LOWORD(v9) = 0;
      v8 = GUID_NULL;
      FormatRRASErrorString(&v13, L"%s: RegCreateKeyEx failed %d.", L"RRasRoutingDomainConfig::OpenInterfacesKey", Key);
      v6 = &v8;
      if ( this != (RRasRoutingDomainConfig *)-516LL )
        v6 = (const struct _GUID *)((char *)this + 516);
      gCfgStoreParamTemplateFunc(
        gCfgStoreEtwContext,
        (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
        (const unsigned __int16 *)&v13,
        v6,
        0,
        (const unsigned __int16 *)&v9);
    }
    if ( !Key )
      return 6;
  }
  return Key;
}

```

## disassembly

```asm
0x18003eda8  mov     [rsp-8+arg_10], rbx
0x18003edad  push    rbp
0x18003edae  push    rsi
0x18003edaf  push    rdi
0x18003edb0  lea     rbp, [rsp-7A0h]
0x18003edb8  sub     rsp, 8A0h
0x18003edbf  mov     rax, cs:__security_cookie
0x18003edc6  xor     rax, rsp
0x18003edc9  mov     [rbp+7B0h+var_20], rax
0x18003edd0  mov     rdi, rdx
0x18003edd3  mov     rsi, rcx
0x18003edd6  xor     eax, eax
0x18003edd8  lea     rcx, [rbp+7B0h+var_81C]; void *
0x18003eddc  xor     edx, edx; Val
0x18003edde  mov     [rbp+7B0h+var_820], eax
0x18003ede1  mov     r8d, 7FCh; Size
0x18003ede7  call    memset_0
0x18003edec  mov     rcx, [rsi+338h]; hKey
0x18003edf3  lea     rdx, aInterfaces; "Interfaces"
0x18003edfa  xor     eax, eax
0x18003edfc  xorps   xmm0, xmm0
0x18003edff  mov     [rsp+8B0h+lpdwDisposition], rax; lpdwDisposition
0x18003ee04  xor     r9d, r9d; lpClass
0x18003ee07  mov     [rsp+8B0h+phkResult], rdi; phkResult
0x18003ee0c  xor     r8d, r8d; Reserved
0x18003ee0f  mov     [rsp+8B0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18003ee14  mov     [rsp+8B0h+samDesired], 0F003Fh; samDesired
0x18003ee1c  mov     [rsp+8B0h+dwOptions], eax; dwOptions
0x18003ee20  mov     [rsp+8B0h+var_850], eax
0x18003ee24  movups  [rsp+8B0h+var_84C], xmm0
0x18003ee29  mov     [rbp+7B0h+var_82C], eax
0x18003ee2c  movups  [rsp+8B0h+var_83C], xmm0
0x18003ee31  call    cs:__imp_RegCreateKeyExW
0x18003ee37  mov     ebx, eax
0x18003ee39  test    eax, eax
0x18003ee3b  jnz     short loc_18003EE46
0x18003ee3d  test    rdi, rdi
0x18003ee40  jnz     loc_18003EED2
0x18003ee46  cmp     qword ptr cs:xmmword_1800710A0, 0
0x18003ee4e  jz      short loc_18003EEC8
0x18003ee50  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003ee57  xor     ecx, ecx
0x18003ee59  lea     r8, aRrasroutingdom_48; "RRasRoutingDomainConfig::OpenInterfaces"...
0x18003ee60  mov     word ptr [rbp+7B0h+var_820], cx
0x18003ee64  lea     rdx, aSRegcreatekeye_2; "%s: RegCreateKeyEx failed %d."
0x18003ee6b  xor     eax, eax
0x18003ee6d  lea     rcx, [rbp+7B0h+var_820]
0x18003ee71  mov     r9d, ebx
0x18003ee74  mov     word ptr [rsp+8B0h+var_850], ax
0x18003ee79  movdqu  [rsp+8B0h+var_860], xmm0
0x18003ee7f  call    FormatRRASErrorString
0x18003ee84  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003ee8b  lea     rcx, [rsi+204h]
0x18003ee92  test    rcx, rcx
0x18003ee95  lea     rax, [rsp+8B0h+var_850]
0x18003ee9a  mov     qword ptr [rsp+8B0h+samDesired], rax
0x18003ee9f  lea     r9, [rsp+8B0h+var_860]
0x18003eea4  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003eeab  lea     r8, [rbp+7B0h+var_820]
0x18003eeaf  cmovnz  r9, rcx
0x18003eeb3  mov     qword ptr [rsp+8B0h+dwOptions], 0
0x18003eebc  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003eec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eec8  test    ebx, ebx
0x18003eeca  mov     eax, 6
0x18003eecf  cmovz   ebx, eax
0x18003eed2  mov     eax, ebx
0x18003eed4  mov     rcx, [rbp+7B0h+var_20]
0x18003eedb  xor     rcx, rsp; StackCookie
0x18003eede  call    __security_check_cookie
0x18003eee3  mov     rbx, [rsp+8B0h+arg_10]
0x18003eeeb  add     rsp, 8A0h
0x18003eef2  pop     rdi
0x18003eef3  pop     rsi
0x18003eef4  pop     rbp
0x18003eef5  retn
```
