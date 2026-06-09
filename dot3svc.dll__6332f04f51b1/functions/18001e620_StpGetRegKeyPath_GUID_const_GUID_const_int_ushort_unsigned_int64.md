# StpGetRegKeyPath(_GUID const *,_GUID const *,int,ushort *,unsigned __int64)

- ea: `0x18001e620`
- end: `0x18001e801`
- name: `?StpGetRegKeyPath@@YAKPEBU_GUID@@0HPEAG_K@Z`
- size: `481`
- prototype: `__int64 __fastcall(GUID *rguid, GUID *, int, unsigned __int16 *, unsigned __int64)`
- caller_count: `11`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c438`
- `0x18001c530`
- `0x18001c900`
- `0x18001ca7c`
- `0x18001cce8`
- `0x18001cfd8`
- `0x18001d168`
- `0x18001d6cc`
- `0x18001d91c`
- `0x18001dbcc`
- `0x18001dd30`

## callees

- `0x1800025f0`
- `0x180008c38`
- `0x180008c7c`
- `0x18001bffc`
- `0x18001e620`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e6d2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e78d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e6d2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e78d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StpGetRegKeyPath(GUID *rguid, GUID *a2, int a3, unsigned __int16 *a4, unsigned __int64 a5)
{
  unsigned int Dot3ServiceRootRegistryLocation; // ecx
  int v10; // eax
  __int64 v11; // rbx
  __int64 v12; // rdi
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  int v16; // eax
  OLECHAR sz[40]; // [rsp+30h] [rbp-4E8h] BYREF
  OLECHAR v19[40]; // [rsp+80h] [rbp-498h] BYREF
  unsigned __int16 v20[512]; // [rsp+D0h] [rbp-448h] BYREF

  Dot3ServiceRootRegistryLocation = GetDot3ServiceRootRegistryLocation((unsigned int)rguid, v20);
  if ( Dot3ServiceRootRegistryLocation )
    return Dot3ServiceRootRegistryLocation;
  v10 = StringCchCopyW(a4, a5, v20);
  Dot3ServiceRootRegistryLocation = v10;
  if ( v10 < 0 )
  {
    if ( (v10 & 0x1FFF0000) == 0x70000 )
      Dot3ServiceRootRegistryLocation = (unsigned __int16)v10;
    if ( Dot3ServiceRootRegistryLocation )
      return Dot3ServiceRootRegistryLocation;
  }
  else
  {
    Dot3ServiceRootRegistryLocation = 0;
  }
  v11 = -1;
  if ( rguid )
  {
    v12 = -1;
    do
      ++v12;
    while ( a4[v12] );
    StringFromGUID2(rguid, sz, 39);
    v13 = StringCchPrintfW(&a4[v12], a5 - v12, L"\\%s\\%s", L"Interfaces", sz);
    Dot3ServiceRootRegistryLocation = v13;
    if ( v13 < 0 )
    {
      if ( (v13 & 0x1FFF0000) == 0x70000 )
        Dot3ServiceRootRegistryLocation = (unsigned __int16)v13;
      if ( Dot3ServiceRootRegistryLocation )
        return Dot3ServiceRootRegistryLocation;
    }
    else
    {
      Dot3ServiceRootRegistryLocation = 0;
    }
  }
  if ( !a3 )
    goto LABEL_23;
  v14 = -1;
  do
    ++v14;
  while ( a4[v14] );
  v15 = StringCchPrintfW(&a4[v14], a5 - v14, L"\\%s", L"UserData");
  Dot3ServiceRootRegistryLocation = v15;
  if ( v15 >= 0 )
  {
    Dot3ServiceRootRegistryLocation = 0;
LABEL_23:
    if ( a2 )
    {
      do
        ++v11;
      while ( a4[v11] );
      StringFromGUID2(a2, v19, 39);
      v16 = StringCchPrintfW(&a4[v11], a5 - v11, L"\\%s\\%s", L"Profiles", v19);
      Dot3ServiceRootRegistryLocation = v16;
      if ( v16 < 0 )
      {
        if ( (v16 & 0x1FFF0000) == 0x70000 )
          return (unsigned __int16)v16;
      }
      else
      {
        return 0;
      }
    }
    return Dot3ServiceRootRegistryLocation;
  }
  if ( (v15 & 0x1FFF0000) == 0x70000 )
    Dot3ServiceRootRegistryLocation = (unsigned __int16)v15;
  if ( !Dot3ServiceRootRegistryLocation )
    goto LABEL_23;
  return Dot3ServiceRootRegistryLocation;
}

```

## disassembly

```asm
0x18001e620  mov     [rsp+arg_10], rbx
0x18001e625  push    rbp
0x18001e626  push    rsi
0x18001e627  push    rdi
0x18001e628  push    r12
0x18001e62a  push    r13
0x18001e62c  push    r14
0x18001e62e  push    r15
0x18001e630  sub     rsp, 4E0h
0x18001e637  mov     rax, cs:__security_cookie
0x18001e63e  xor     rax, rsp
0x18001e641  mov     [rsp+518h+var_48], rax
0x18001e649  mov     r12, rdx
0x18001e64c  mov     rsi, r9
0x18001e64f  lea     rdx, [rsp+518h+var_448]; unsigned __int16 *
0x18001e657  mov     r15d, r8d
0x18001e65a  mov     r14, rcx
0x18001e65d  call    ?GetDot3ServiceRootRegistryLocation@@YAKKPEAG@Z; GetDot3ServiceRootRegistryLocation(ulong,ushort *)
0x18001e662  xor     r13d, r13d
0x18001e665  mov     ecx, eax
0x18001e667  test    eax, eax
0x18001e669  jnz     loc_18001E7D4
0x18001e66f  mov     rbp, [rsp+518h+arg_20]
0x18001e677  lea     r8, [rsp+518h+var_448]; unsigned __int16 *
0x18001e67f  mov     rdx, rbp; unsigned __int64
0x18001e682  mov     rcx, rsi; unsigned __int16 *
0x18001e685  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e68a  mov     ecx, eax
0x18001e68c  mov     edi, 1FFF0000h
0x18001e691  test    eax, eax
0x18001e693  js      short loc_18001E69A
0x18001e695  mov     ecx, r13d
0x18001e698  jmp     short loc_18001E6AE
0x18001e69a  and     eax, edi
0x18001e69c  cmp     eax, 70000h
0x18001e6a1  jnz     short loc_18001E6A6
0x18001e6a3  movzx   ecx, cx
0x18001e6a6  test    ecx, ecx
0x18001e6a8  jnz     loc_18001E7D4
0x18001e6ae  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001e6b2  test    r14, r14
0x18001e6b5  jz      short loc_18001E723
0x18001e6b7  mov     rdi, rbx
0x18001e6ba  inc     rdi
0x18001e6bd  cmp     [rsi+rdi*2], r13w
0x18001e6c2  jnz     short loc_18001E6BA
0x18001e6c4  mov     r8d, 27h ; '''; cchMax
0x18001e6ca  lea     rdx, [rsp+518h+sz]; lpsz
0x18001e6cf  mov     rcx, r14; rguid
0x18001e6d2  call    cs:__imp_StringFromGUID2
0x18001e6d8  lea     rax, [rsp+518h+sz]
0x18001e6dd  mov     rdx, rbp
0x18001e6e0  sub     rdx, rdi; unsigned __int64
0x18001e6e3  mov     [rsp+518h+var_4F8], rax
0x18001e6e8  lea     rcx, [rsi+rdi*2]; unsigned __int16 *
0x18001e6ec  lea     r9, aInterfaces; "Interfaces"
0x18001e6f3  lea     r8, aSS; "\\%s\\%s"
0x18001e6fa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e6ff  mov     ecx, eax
0x18001e701  mov     edi, 1FFF0000h
0x18001e706  test    eax, eax
0x18001e708  js      short loc_18001E70F
0x18001e70a  mov     ecx, r13d
0x18001e70d  jmp     short loc_18001E723
0x18001e70f  and     eax, edi
0x18001e711  cmp     eax, 70000h
0x18001e716  jnz     short loc_18001E71B
0x18001e718  movzx   ecx, cx
0x18001e71b  test    ecx, ecx
0x18001e71d  jnz     loc_18001E7D4
0x18001e723  test    r15d, r15d
0x18001e726  jz      short loc_18001E76D
0x18001e728  mov     rax, rbx
0x18001e72b  inc     rax
0x18001e72e  cmp     [rsi+rax*2], r13w
0x18001e733  jnz     short loc_18001E72B
0x18001e735  mov     rdx, rbp
0x18001e738  lea     rcx, [rsi+rax*2]; unsigned __int16 *
0x18001e73c  sub     rdx, rax; unsigned __int64
0x18001e73f  lea     r9, aUserdata; "UserData"
0x18001e746  lea     r8, aS_0; "\\%s"
0x18001e74d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e752  mov     ecx, eax
0x18001e754  test    eax, eax
0x18001e756  js      short loc_18001E75D
0x18001e758  mov     ecx, r13d
0x18001e75b  jmp     short loc_18001E76D
0x18001e75d  and     eax, edi
0x18001e75f  cmp     eax, 70000h
0x18001e764  jnz     short loc_18001E769
0x18001e766  movzx   ecx, cx
0x18001e769  test    ecx, ecx
0x18001e76b  jnz     short loc_18001E7D4
0x18001e76d  test    r12, r12
0x18001e770  jz      short loc_18001E7D4
0x18001e772  inc     rbx
0x18001e775  cmp     [rsi+rbx*2], r13w
0x18001e77a  jnz     short loc_18001E772
0x18001e77c  mov     r8d, 27h ; '''; cchMax
0x18001e782  lea     rdx, [rsp+518h+var_498]; lpsz
0x18001e78a  mov     rcx, r12; rguid
0x18001e78d  call    cs:__imp_StringFromGUID2
0x18001e793  lea     rax, [rsp+518h+var_498]
0x18001e79b  sub     rbp, rbx
0x18001e79e  mov     rdx, rbp; unsigned __int64
0x18001e7a1  mov     [rsp+518h+var_4F8], rax
0x18001e7a6  lea     rcx, [rsi+rbx*2]; unsigned __int16 *
0x18001e7aa  lea     r9, aProfiles; "Profiles"
0x18001e7b1  lea     r8, aSS; "\\%s\\%s"
0x18001e7b8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e7bd  mov     ecx, eax
0x18001e7bf  test    eax, eax
0x18001e7c1  js      short loc_18001E7C8
0x18001e7c3  mov     ecx, r13d
0x18001e7c6  jmp     short loc_18001E7D4
0x18001e7c8  and     eax, edi
0x18001e7ca  cmp     eax, 70000h
0x18001e7cf  jnz     short loc_18001E7D4
0x18001e7d1  movzx   ecx, cx
0x18001e7d4  mov     eax, ecx
0x18001e7d6  mov     rcx, [rsp+518h+var_48]
0x18001e7de  xor     rcx, rsp; StackCookie
0x18001e7e1  call    __security_check_cookie
0x18001e7e6  mov     rbx, [rsp+518h+arg_10]
0x18001e7ee  add     rsp, 4E0h
0x18001e7f5  pop     r15
0x18001e7f7  pop     r14
0x18001e7f9  pop     r13
0x18001e7fb  pop     r12
0x18001e7fd  pop     rdi
0x18001e7fe  pop     rsi
0x18001e7ff  pop     rbp
0x18001e800  retn
```
