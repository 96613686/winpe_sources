# DllUnregisterServer

- ea: `0x180018dd0`
- end: `0x180019019`
- name: `DllUnregisterServer`
- size: `585`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180018dd0`
- `0x18001abd8`
- `0x18001acd0`
- `0x18001adc0`
- `0x18001ae60`

## string_xrefs

- `0x180018f87`: `Extensions`
- `0x180018ebd`: `CLSID`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  const unsigned __int16 *v0; // rax
  const unsigned __int16 **v1; // rbx
  HKEY v3; // [rsp+20h] [rbp-10h] BYREF
  HKEY v4; // [rsp+28h] [rbp-8h] BYREF
  HKEY v5; // [rsp+50h] [rbp+20h] BYREF
  HKEY v6; // [rsp+58h] [rbp+28h] BYREF
  HKEY v7; // [rsp+60h] [rbp+30h] BYREF
  HKEY v8; // [rsp+68h] [rbp+38h] BYREF

  v5 = 0;
  v6 = 0;
  v3 = 0;
  v7 = 0;
  if ( (int)CSafeReg::Open((CSafeReg *)&v7, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\MMC\\SnapIns", 0x2000Eu) >= 0 )
  {
    CSafeReg::DeleteTree(&v7, L"{975797FC-4E2A-11D0-B702-00C04FD8DBF7}");
    if ( (int)CSafeReg::Open((CSafeReg *)&v5, v7, L"{394C052E-B830-11D0-9A86-00C04FD8DBF7}", 0x20006u) >= 0 )
    {
      CSafeReg::DeleteValue(&v5, L"NameString");
      CSafeReg::Close((CSafeReg *)&v5);
    }
  }
  CSafeReg::Close((CSafeReg *)&v7);
  if ( (int)CSafeReg::Open((CSafeReg *)&v3, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\MMC\\NodeTypes", 0x20006u) >= 0 )
  {
    v0 = g_aNodeGuids;
    if ( g_aNodeGuids )
    {
      v1 = (const unsigned __int16 **)&g_aNodeGuids;
      do
      {
        CSafeReg::DeleteTree(&v3, v0);
        v1 += 2;
        v0 = *v1;
      }
      while ( *v1 );
    }
  }
  if ( (int)CSafeReg::Open((CSafeReg *)&v6, HKEY_CLASSES_ROOT, L"CLSID", 0x2000Eu) >= 0 )
  {
    CSafeReg::DeleteTree(&v6, L"{975797FC-4E2A-11D0-B702-00C04FD8DBF7}");
    CSafeReg::DeleteTree(&v6, L"{F778C6B4-C08B-11D2-976C-00C04F79DB19}");
    CSafeReg::DeleteTree(&v6, L"{05238C14-A6E1-11D0-9A84-00C04FD8DBF7}");
    CSafeReg::DeleteTree(&v6, L"{394C052E-B830-11D0-9A86-00C04FD8DBF7}");
  }
  if ( (int)CSafeReg::Open((CSafeReg *)&v5, HKEY_CLASSES_ROOT, L"Interface", 0x2000Eu) >= 0 )
  {
    CSafeReg::DeleteTree(&v5, L"{05238C14-A6E1-11D0-9A84-00C04FD8DBF7}");
    CSafeReg::DeleteTree(&v5, L"{12DD72EE-A6E5-11D0-9A84-00C04FD8DBF7}");
    CSafeReg::Close((CSafeReg *)&v5);
  }
  v4 = 0;
  if ( (int)CSafeReg::Open((CSafeReg *)&v4, v3, L"{476e6448-aaff-11d0-b944-00c04fd8d5b0}", 0x20006u) >= 0 )
  {
    v7 = 0;
    if ( (int)CSafeReg::Open((CSafeReg *)&v7, v4, L"Extensions", 0x20006u) >= 0 )
    {
      v8 = 0;
      if ( (int)CSafeReg::Open((CSafeReg *)&v8, v7, L"NameSpace", 0x20006u) >= 0 )
        CSafeReg::DeleteValue(&v8, L"{394C052E-B830-11D0-9A86-00C04FD8DBF7}");
      CSafeReg::Close((CSafeReg *)&v8);
    }
    CSafeReg::Close((CSafeReg *)&v7);
  }
  CSafeReg::Close((CSafeReg *)&v4);
  CSafeReg::Close((CSafeReg *)&v3);
  CSafeReg::Close((CSafeReg *)&v6);
  CSafeReg::Close((CSafeReg *)&v5);
  return 0;
}

```

## disassembly

```asm
0x180018dd0  push    rbp
0x180018dd2  push    rbx
0x180018dd3  push    rsi
0x180018dd4  mov     rbp, rsp
0x180018dd7  sub     rsp, 30h
0x180018ddb  mov     rbx, 0FFFFFFFF80000002h
0x180018de2  mov     [rbp+arg_0], 0
0x180018dea  mov     rdx, rbx; HKEY
0x180018ded  mov     [rbp+arg_8], 0
0x180018df5  mov     r9d, 2000Eh; unsigned int
0x180018dfb  mov     [rbp+var_10], 0
0x180018e03  lea     r8, SNAPINS_KEY; "Software\\Microsoft\\MMC\\SnapIns"
0x180018e0a  mov     [rbp+arg_10], 0
0x180018e12  lea     rcx, [rbp+arg_10]; this
0x180018e16  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180018e1b  mov     esi, 20006h
0x180018e20  test    eax, eax
0x180018e22  js      short loc_180018E68
0x180018e24  lea     rdx, a975797fc4e2a11; "{975797FC-4E2A-11D0-B702-00C04FD8DBF7}"
0x180018e2b  lea     rcx, [rbp+arg_10]; this
0x180018e2f  call    ?DeleteTree@CSafeReg@@QEAAJPEBG@Z; CSafeReg::DeleteTree(ushort const *)
0x180018e34  mov     rdx, [rbp+arg_10]; HKEY
0x180018e38  lea     r8, a394c052eB83011; "{394C052E-B830-11D0-9A86-00C04FD8DBF7}"
0x180018e3f  mov     r9d, esi; unsigned int
0x180018e42  lea     rcx, [rbp+arg_0]; this
0x180018e46  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180018e4b  test    eax, eax
0x180018e4d  js      short loc_180018E68
0x180018e4f  lea     rdx, g_szNameString; "NameString"
0x180018e56  lea     rcx, [rbp+arg_0]; this
0x180018e5a  call    ?DeleteValue@CSafeReg@@QEAAJPEBG@Z; CSafeReg::DeleteValue(ushort const *)
0x180018e5f  lea     rcx, [rbp+arg_0]; this
0x180018e63  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180018e68  lea     rcx, [rbp+arg_10]; this
0x180018e6c  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180018e71  mov     r9d, esi; unsigned int
0x180018e74  lea     r8, NODE_TYPES_KEY; "Software\\Microsoft\\MMC\\NodeTypes"
0x180018e7b  mov     rdx, rbx; HKEY
0x180018e7e  lea     rcx, [rbp+var_10]; this
0x180018e82  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180018e87  test    eax, eax
0x180018e89  js      short loc_180018EB6
0x180018e8b  mov     rax, cs:?g_aNodeGuids@@3PAUNODE_GUID_INFO@@A; NODE_GUID_INFO near * g_aNodeGuids
0x180018e92  test    rax, rax
0x180018e95  jz      short loc_180018EB6
0x180018e97  lea     rbx, ?g_aNodeGuids@@3PAUNODE_GUID_INFO@@A; NODE_GUID_INFO near * g_aNodeGuids
0x180018e9e  mov     rdx, rax; unsigned __int16 *
0x180018ea1  lea     rcx, [rbp+var_10]; this
0x180018ea5  call    ?DeleteTree@CSafeReg@@QEAAJPEBG@Z; CSafeReg::DeleteTree(ushort const *)
0x180018eaa  lea     rbx, [rbx+10h]
0x180018eae  mov     rax, [rbx]
0x180018eb1  test    rax, rax
0x180018eb4  jnz     short loc_180018E9E
0x180018eb6  mov     rbx, 0FFFFFFFF80000000h
0x180018ebd  lea     r8, aClsid; "CLSID"
0x180018ec4  mov     rdx, rbx; HKEY
0x180018ec7  lea     rcx, [rbp+arg_8]; this
0x180018ecb  mov     r9d, 2000Eh; unsigned int
0x180018ed1  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180018ed6  test    eax, eax
0x180018ed8  js      short loc_180018F1A
0x180018eda  lea     rdx, a975797fc4e2a11; "{975797FC-4E2A-11D0-B702-00C04FD8DBF7}"
0x180018ee1  lea     rcx, [rbp+arg_8]; this
0x180018ee5  call    ?DeleteTree@CSafeReg@@QEAAJPEBG@Z; CSafeReg::DeleteTree(ushort const *)
0x180018eea  lea     rdx, aF778c6b4C08b11; "{F778C6B4-C08B-11D2-976C-00C04F79DB19}"
0x180018ef1  lea     rcx, [rbp+arg_8]; this
0x180018ef5  call    ?DeleteTree@CSafeReg@@QEAAJPEBG@Z; CSafeReg::DeleteTree(ushort const *)
0x180018efa  lea     rdx, a05238c14A6e111; "{05238C14-A6E1-11D0-9A84-00C04FD8DBF7}"
0x180018f01  lea     rcx, [rbp+arg_8]; this
0x180018f05  call    ?DeleteTree@CSafeReg@@QEAAJPEBG@Z; CSafeReg::DeleteTree(ushort const *)
0x180018f0a  lea     rdx, a394c052eB83011; "{394C052E-B830-11D0-9A86-00C04FD8DBF7}"
0x180018f11  lea     rcx, [rbp+arg_8]; this
0x180018f15  call    ?DeleteTree@CSafeReg@@QEAAJPEBG@Z; CSafeReg::DeleteTree(ushort const *)
0x180018f1a  mov     r9d, 2000Eh; unsigned int
0x180018f20  lea     r8, aInterface; "Interface"
0x180018f27  mov     rdx, rbx; HKEY
0x180018f2a  lea     rcx, [rbp+arg_0]; this
0x180018f2e  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180018f33  test    eax, eax
0x180018f35  js      short loc_180018F60
0x180018f37  lea     rdx, a05238c14A6e111; "{05238C14-A6E1-11D0-9A84-00C04FD8DBF7}"
0x180018f3e  lea     rcx, [rbp+arg_0]; this
0x180018f42  call    ?DeleteTree@CSafeReg@@QEAAJPEBG@Z; CSafeReg::DeleteTree(ushort const *)
0x180018f47  lea     rdx, a12dd72eeA6e511; "{12DD72EE-A6E5-11D0-9A84-00C04FD8DBF7}"
0x180018f4e  lea     rcx, [rbp+arg_0]; this
0x180018f52  call    ?DeleteTree@CSafeReg@@QEAAJPEBG@Z; CSafeReg::DeleteTree(ushort const *)
0x180018f57  lea     rcx, [rbp+arg_0]; this
0x180018f5b  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180018f60  mov     rdx, [rbp+var_10]; HKEY
0x180018f64  lea     r8, a476e6448Aaff11; "{476e6448-aaff-11d0-b944-00c04fd8d5b0}"
0x180018f6b  mov     r9d, esi; unsigned int
0x180018f6e  mov     [rbp+var_8], 0
0x180018f76  lea     rcx, [rbp+var_8]; this
0x180018f7a  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180018f7f  test    eax, eax
0x180018f81  js      short loc_180018FEB
0x180018f83  mov     rdx, [rbp+var_8]; HKEY
0x180018f87  lea     r8, g_szExtensions; "Extensions"
0x180018f8e  mov     r9d, esi; unsigned int
0x180018f91  mov     [rbp+arg_10], 0
0x180018f99  lea     rcx, [rbp+arg_10]; this
0x180018f9d  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180018fa2  test    eax, eax
0x180018fa4  js      short loc_180018FE2
0x180018fa6  mov     rdx, [rbp+arg_10]; HKEY
0x180018faa  lea     r8, g_szNameSpace; "NameSpace"
0x180018fb1  mov     r9d, esi; unsigned int
0x180018fb4  mov     [rbp+arg_18], 0
0x180018fbc  lea     rcx, [rbp+arg_18]; this
0x180018fc0  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180018fc5  lea     rcx, [rbp+arg_18]; this
0x180018fc9  test    eax, eax
0x180018fcb  js      short loc_180018FDD
0x180018fcd  lea     rdx, a394c052eB83011; "{394C052E-B830-11D0-9A86-00C04FD8DBF7}"
0x180018fd4  call    ?DeleteValue@CSafeReg@@QEAAJPEBG@Z; CSafeReg::DeleteValue(ushort const *)
0x180018fd9  lea     rcx, [rbp+arg_18]; this
0x180018fdd  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180018fe2  lea     rcx, [rbp+arg_10]; this
0x180018fe6  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180018feb  lea     rcx, [rbp+var_8]; this
0x180018fef  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180018ff4  lea     rcx, [rbp+var_10]; this
0x180018ff8  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180018ffd  lea     rcx, [rbp+arg_8]; this
0x180019001  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180019006  lea     rcx, [rbp+arg_0]; this
0x18001900a  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x18001900f  xor     eax, eax
0x180019011  add     rsp, 30h
0x180019015  pop     rsi
0x180019016  pop     rbx
0x180019017  pop     rbp
0x180019018  retn
```
