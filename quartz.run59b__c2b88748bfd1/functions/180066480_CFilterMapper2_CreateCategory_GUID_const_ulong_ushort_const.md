# CFilterMapper2::CreateCategory(_GUID const &,ulong,ushort const *)

- ea: `0x180066480`
- end: `0x1800665f6`
- name: `?CreateCategory@CFilterMapper2@@EEAAJAEBU_GUID@@KPEBG@Z`
- size: `374`
- prototype: `int(CFilterMapper2 *__hidden this, const struct _GUID *, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800388a0`
- `0x180066480`
- `0x1800691b8`
- `0x1800691ec`
- `0x1800696b4`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800665a9`
- `ADVAPI32!RegSetValueExW` at `0x1800665a9`
- `ole32!StringFromGUID2` at `0x1800664f2`
- `ole32!StringFromGUID2` at `0x18006655b`
- `ole32!StringFromGUID2` at `0x1800664f2`
- `ole32!StringFromGUID2` at `0x18006655b`

## string_xrefs

- `0x180066567`: `CLSID`
- `0x1800664b9`: `CLSID\{DA4E3DA0-D07D-11d0-BD50-00A0C911CE86}\Instance`

## pseudocode

```c
__int64 __fastcall CFilterMapper2::CreateCategory(
        CFilterMapper2 *this,
        const struct _GUID *a2,
        int a3,
        unsigned __int16 *a4)
{
  LSTATUS v7; // ebx
  unsigned __int16 *v8; // r9
  unsigned int lpData; // [rsp+20h] [rbp-E0h]
  unsigned int lpDataa; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+28h] [rbp-D8h]
  DWORD cbDataa; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v14; // [rsp+30h] [rbp-D0h]
  struct _SECURITY_ATTRIBUTES *v15; // [rsp+30h] [rbp-D0h]
  unsigned int *v16; // [rsp+38h] [rbp-C8h]
  unsigned int *v17; // [rsp+38h] [rbp-C8h]
  BYTE Data[8]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v20[4]; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR v22[40]; // [rsp+D0h] [rbp-30h] BYREF

  memset(v20, 0, 24);
  v7 = ATL::CRegKey::Create(
         (ATL::CRegKey *)v20,
         HKEY_CLASSES_ROOT,
         L"CLSID\\{DA4E3DA0-D07D-11d0-BD50-00A0C911CE86}\\Instance",
         a4,
         lpData,
         cbData,
         v14,
         v16);
  if ( !v7 )
  {
    StringFromGUID2(a2, sz, 39);
    memset(hKey, 0, sizeof(hKey));
    v7 = ATL::CRegKey::Create((ATL::CRegKey *)hKey, v20[0], sz, v8, lpDataa, cbDataa, v15, v17);
    if ( !v7 )
    {
      v7 = ATL::CRegKey::SetValue((ATL::CRegKey *)hKey, a4, L"FriendlyName");
      if ( !v7 )
      {
        StringFromGUID2(a2, v22, 39);
        v7 = ATL::CRegKey::SetValue((ATL::CRegKey *)hKey, v22, L"CLSID");
        if ( !v7 )
        {
          *(_DWORD *)Data = a3;
          v7 = RegSetValueExW(hKey[0], L"Merit", 0, 4u, Data, 4u);
        }
      }
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v20);
  return v7 != 0 ? v7 | 0x80070000 : 0;
}

```

## disassembly

```asm
0x180066480  push    rbp
0x180066482  push    rbx
0x180066483  push    rsi
0x180066484  push    rdi
0x180066485  push    r14
0x180066487  lea     rbp, [rsp-30h]
0x18006648c  sub     rsp, 130h
0x180066493  mov     rax, cs:__security_cookie
0x18006649a  xor     rax, rsp
0x18006649d  mov     [rbp+50h+var_30], rax
0x1800664a1  mov     r14d, r8d
0x1800664a4  mov     [rsp+150h+var_F0], 0
0x1800664ad  mov     rdi, rdx
0x1800664b0  mov     [rsp+150h+var_E8], 0
0x1800664b9  lea     r8, aClsidDa4e3da0D; "CLSID\\{DA4E3DA0-D07D-11d0-BD50-00A0C91"...
0x1800664c0  mov     [rsp+150h+var_E0], 0
0x1800664c9  mov     rdx, 0FFFFFFFF80000000h; hKey
0x1800664d0  lea     rcx, [rsp+150h+var_F0]; this
0x1800664d5  mov     rsi, r9
0x1800664d8  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800664dd  mov     ebx, eax
0x1800664df  test    eax, eax
0x1800664e1  jnz     loc_1800665C1
0x1800664e7  lea     r8d, [rax+27h]; cchMax
0x1800664eb  mov     rcx, rdi; rguid
0x1800664ee  lea     rdx, [rbp+50h+sz]; lpsz
0x1800664f2  call    cs:__imp_StringFromGUID2
0x1800664f9  nop     dword ptr [rax+rax+00h]
0x1800664fe  mov     rdx, [rsp+150h+var_F0]; hKey
0x180066503  lea     r8, [rbp+50h+sz]; lpSubKey
0x180066507  lea     rcx, [rsp+150h+hKey]; this
0x18006650c  mov     [rsp+150h+hKey], 0
0x180066515  mov     [rsp+150h+var_100], 0
0x18006651e  mov     [rsp+150h+var_F8], 0
0x180066527  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18006652c  mov     ebx, eax
0x18006652e  test    eax, eax
0x180066530  jnz     loc_1800665B7
0x180066536  lea     r8, aFriendlyname; "FriendlyName"
0x18006653d  mov     rdx, rsi; unsigned __int16 *
0x180066540  lea     rcx, [rsp+150h+hKey]; this
0x180066545  call    ?SetValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetValue(ushort const *,ushort const *)
0x18006654a  mov     ebx, eax
0x18006654c  test    eax, eax
0x18006654e  jnz     short loc_1800665B7
0x180066550  lea     r8d, [rax+27h]; cchMax
0x180066554  mov     rcx, rdi; rguid
0x180066557  lea     rdx, [rbp+50h+var_80]; lpsz
0x18006655b  call    cs:__imp_StringFromGUID2
0x180066562  nop     dword ptr [rax+rax+00h]
0x180066567  lea     r8, aClsid; "CLSID"
0x18006656e  lea     rdx, [rbp+50h+var_80]; unsigned __int16 *
0x180066572  lea     rcx, [rsp+150h+hKey]; this
0x180066577  call    ?SetValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetValue(ushort const *,ushort const *)
0x18006657c  mov     ebx, eax
0x18006657e  test    eax, eax
0x180066580  jnz     short loc_1800665B7
0x180066582  mov     rcx, [rsp+150h+hKey]; hKey
0x180066587  lea     r9d, [rax+4]; dwType
0x18006658b  lea     rax, [rsp+150h+Data]
0x180066590  mov     [rsp+150h+cbData], r9d; cbData
0x180066595  xor     r8d, r8d; Reserved
0x180066598  mov     [rsp+150h+lpData], rax; lpData
0x18006659d  lea     rdx, aMerit; "Merit"
0x1800665a4  mov     dword ptr [rsp+150h+Data], r14d
0x1800665a9  call    cs:__imp_RegSetValueExW
0x1800665b0  nop     dword ptr [rax+rax+00h]
0x1800665b5  mov     ebx, eax
0x1800665b7  lea     rcx, [rsp+150h+hKey]; this
0x1800665bc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800665c1  mov     ecx, ebx
0x1800665c3  or      ecx, 80070000h
0x1800665c9  neg     ebx
0x1800665cb  sbb     ebx, ebx
0x1800665cd  and     ebx, ecx
0x1800665cf  lea     rcx, [rsp+150h+var_F0]; this
0x1800665d4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800665d9  mov     eax, ebx
0x1800665db  mov     rcx, [rbp+50h+var_30]
0x1800665df  xor     rcx, rsp; StackCookie
0x1800665e2  call    __security_check_cookie
0x1800665e7  add     rsp, 130h
0x1800665ee  pop     r14
0x1800665f0  pop     rdi
0x1800665f1  pop     rsi
0x1800665f2  pop     rbx
0x1800665f3  pop     rbp
0x1800665f4  retn
```
