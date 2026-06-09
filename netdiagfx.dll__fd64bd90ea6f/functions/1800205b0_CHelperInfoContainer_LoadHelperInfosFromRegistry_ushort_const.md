# CHelperInfoContainer::LoadHelperInfosFromRegistry(ushort const *)

- ea: `0x1800205b0`
- end: `0x180020690`
- name: `?LoadHelperInfosFromRegistry@CHelperInfoContainer@@QEAAJPEBG@Z`
- size: `224`
- prototype: `__int64 __fastcall(CHelperInfoContainer *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017980`

## callees

- `0x18000579c`
- `0x180006d58`
- `0x180006f04`
- `0x18001edc0`
- `0x180020024`
- `0x1800205b0`

## string_xrefs

- `0x180020608`: `\Microsoft\HostDLLs`
- `0x18002064a`: `\Microsoft.Extensions\HostDLLs`

## pseudocode

```c
__int64 __fastcall CHelperInfoContainer::LoadHelperInfosFromRegistry(CHelperInfoContainer *this, unsigned __int16 *a2)
{
  __int64 v4; // rbx
  __int64 v5; // r8
  LPCWSTR v6; // rbx
  unsigned int v7; // edi
  LPCWSTR lpSubKey; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpSubKey);
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  ATL::CSimpleStringT<unsigned short,0>::SetString((char **)&lpSubKey, a2, v5);
  ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, L"\\Microsoft\\HostDLLs", 19);
  LoadFromRegistryToList(lpSubKey);
  do
    ++v4;
  while ( a2[v4] );
  ATL::CSimpleStringT<unsigned short,0>::SetString((char **)&lpSubKey, a2, v4);
  ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, L"\\Microsoft.Extensions\\HostDLLs", 30);
  v6 = lpSubKey;
  v7 = LoadFromRegistryToList(lpSubKey);
  ATL::CStringData::Release((ATL::CStringData *)(v6 - 12));
  return v7;
}

```

## disassembly

```asm
0x1800205b0  mov     [rsp+arg_0], rbx
0x1800205b5  mov     [rsp+arg_10], rbp
0x1800205ba  push    rsi
0x1800205bb  push    rdi
0x1800205bc  push    r14
0x1800205be  sub     rsp, 20h
0x1800205c2  mov     rdi, rdx
0x1800205c5  mov     rsi, rcx
0x1800205c8  xor     r14d, r14d
0x1800205cb  test    rdx, rdx
0x1800205ce  jnz     short loc_1800205DA
0x1800205d0  mov     eax, 80070057h
0x1800205d5  jmp     loc_18002067D
0x1800205da  lea     rcx, [rsp+38h+lpSubKey]
0x1800205df  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800205e4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800205e8  mov     r8, rbx
0x1800205eb  inc     r8
0x1800205ee  cmp     [rdi+r8*2], r14w
0x1800205f3  jnz     short loc_1800205EB
0x1800205f5  mov     rdx, rdi
0x1800205f8  lea     rcx, [rsp+38h+lpSubKey]
0x1800205fd  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180020602  mov     r8d, 13h
0x180020608  lea     rdx, aMicrosoftHostd; "\\Microsoft\\HostDLLs"
0x18002060f  lea     rcx, [rsp+38h+lpSubKey]
0x180020614  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180020619  lea     r8, [rsi+20h]
0x18002061d  mov     rdx, rsi
0x180020620  mov     rcx, [rsp+38h+lpSubKey]; lpSubKey
0x180020625  call    ?LoadFromRegistryToList@@YAJPEBGPEAV?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperInfo@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperInfo@@@std@@@5@@std@@PEAV?$vector@PEAVCHostDLLInfo@@V?$allocator@PEAVCHostDLLInfo@@@std@@@2@@Z; LoadFromRegistryToList(ushort const *,std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperInfo *> *,std::vector<CHostDLLInfo *> *)
0x18002062a  inc     rbx
0x18002062d  cmp     [rdi+rbx*2], r14w
0x180020632  jnz     short loc_18002062A
0x180020634  mov     r8d, ebx
0x180020637  mov     rdx, rdi
0x18002063a  lea     rcx, [rsp+38h+lpSubKey]
0x18002063f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180020644  mov     r8d, 1Eh
0x18002064a  lea     rdx, aMicrosoftExten; "\\Microsoft.Extensions\\HostDLLs"
0x180020651  lea     rcx, [rsp+38h+lpSubKey]
0x180020656  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18002065b  lea     rdx, [rsi+10h]
0x18002065f  lea     r8, [rsi+20h]
0x180020663  mov     rbx, [rsp+38h+lpSubKey]
0x180020668  mov     rcx, rbx; lpSubKey
0x18002066b  call    ?LoadFromRegistryToList@@YAJPEBGPEAV?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperInfo@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperInfo@@@std@@@5@@std@@PEAV?$vector@PEAVCHostDLLInfo@@V?$allocator@PEAVCHostDLLInfo@@@std@@@2@@Z; LoadFromRegistryToList(ushort const *,std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperInfo *> *,std::vector<CHostDLLInfo *> *)
0x180020670  mov     edi, eax
0x180020672  lea     rcx, [rbx-18h]; this
0x180020676  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002067b  mov     eax, edi
0x18002067d  mov     rbx, [rsp+38h+arg_0]
0x180020682  mov     rbp, [rsp+38h+arg_10]
0x180020687  add     rsp, 20h
0x18002068b  pop     r14
0x18002068d  pop     rdi
0x18002068e  pop     rsi
0x18002068f  retn
```
