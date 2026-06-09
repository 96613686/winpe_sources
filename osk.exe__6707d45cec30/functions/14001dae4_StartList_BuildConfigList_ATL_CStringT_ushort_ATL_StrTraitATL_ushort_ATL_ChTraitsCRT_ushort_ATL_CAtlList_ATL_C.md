# StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)

- ea: `0x14001dae4`
- end: `0x14001dc47`
- name: `?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001f728`

## callees

- `0x1400045f4`
- `0x140005c04`
- `0x140005c90`
- `0x140007e90`
- `0x140009524`
- `0x140009cd8`
- `0x14000a414`
- `0x14001c508`
- `0x14001d930`
- `0x14001dab0`
- `0x14001dae4`

## string_xrefs

- `0x14001db2e`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs\`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall StartList::BuildConfigList(__int64 a1, __int64 a2)
{
  _BYTE *v4; // rdx
  _QWORD *v5; // rcx
  int *v6; // rdi
  __int64 v7; // rbx
  char *v8; // [rsp+20h] [rbp-30h] BYREF
  LPCWSTR lpSubKey; // [rsp+28h] [rbp-28h] BYREF
  __int64 v10; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v11[3]; // [rsp+38h] [rbp-18h] BYREF
  int v12; // [rsp+80h] [rbp+30h] BYREF
  int v13; // [rsp+88h] [rbp+38h] BYREF

  v12 = 0;
  v13 = 44;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
    a1,
    &v8,
    &v13,
    &v12);
  while ( (unsigned __int8)ATL::operator!=(&v8) )
  {
    if ( *((_DWORD *)v8 - 4) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &lpSubKey,
        L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATs\\");
      ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, v8, *((unsigned int *)v8 - 4));
      memset(v11, 0, sizeof(v11));
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v11, HKEY_LOCAL_MACHINE, lpSubKey, 0x20019u) )
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          a2,
          v8);
      ATL::CRegKey::Close((ATL::CRegKey *)v11);
      ATL::CStringData::Release((ATL::CStringData *)(lpSubKey - 12));
    }
    v4 = *(_BYTE **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                      a1,
                      &v10,
                      &v13,
                      &v12);
    v5 = v4 - 24;
    v6 = (int *)(v8 - 24);
    if ( v4 - 24 != v8 - 24 )
    {
      if ( v6[4] >= 0 && *v5 == *(_QWORD *)v6 )
      {
        v7 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v5);
        ATL::CStringData::Release((ATL::CStringData *)v6);
        v8 = (char *)(v7 + 24);
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v8, v4, *((_DWORD *)v4 - 4));
      }
    }
    ATL::CStringData::Release((ATL::CStringData *)(v10 - 24));
  }
  ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
}

```

## disassembly

```asm
0x14001dae4  mov     [rsp-18h+arg_0], rbx
0x14001dae9  mov     [rsp-18h+arg_8], rsi
0x14001daee  push    rbp
0x14001daef  push    rdi
0x14001daf0  push    r14
0x14001daf2  mov     rbp, rsp
0x14001daf5  sub     rsp, 50h
0x14001daf9  mov     rsi, rdx
0x14001dafc  mov     r14, rcx
0x14001daff  mov     [rbp+arg_10], 0
0x14001db06  mov     [rbp+arg_18], 2Ch ; ','
0x14001db0d  lea     r9, [rbp+arg_10]
0x14001db11  lea     r8, [rbp+arg_18]
0x14001db15  lea     rdx, [rbp+var_30]
0x14001db19  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x14001db1e  nop
0x14001db1f  jmp     loc_14001DC16
0x14001db24  mov     rax, [rbp+var_30]
0x14001db28  cmp     dword ptr [rax-10h], 0
0x14001db2c  jz      short loc_14001DBAA
0x14001db2e  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001db35  lea     rcx, [rbp+lpSubKey]
0x14001db39  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001db3e  nop
0x14001db3f  mov     rdx, [rbp+var_30]
0x14001db43  mov     r8d, [rdx-10h]
0x14001db47  lea     rcx, [rbp+lpSubKey]
0x14001db4b  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14001db50  mov     [rbp+var_18], 0
0x14001db58  mov     [rbp+var_10], 0
0x14001db60  mov     [rbp+var_8], 0
0x14001db68  mov     r9d, 20019h; unsigned int
0x14001db6e  mov     r8, [rbp+lpSubKey]; lpSubKey
0x14001db72  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14001db79  lea     rcx, [rbp+var_18]; this
0x14001db7d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001db82  test    eax, eax
0x14001db84  jnz     short loc_14001DB93
0x14001db86  mov     rdx, [rbp+var_30]
0x14001db8a  mov     rcx, rsi
0x14001db8d  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x14001db92  nop
0x14001db93  lea     rcx, [rbp+var_18]; this
0x14001db97  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001db9c  nop
0x14001db9d  mov     rcx, [rbp+lpSubKey]
0x14001dba1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001dba5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001dbaa  lea     r9, [rbp+arg_10]
0x14001dbae  lea     r8, [rbp+arg_18]
0x14001dbb2  lea     rdx, [rbp+var_20]
0x14001dbb6  mov     rcx, r14
0x14001dbb9  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x14001dbbe  nop
0x14001dbbf  mov     rdx, [rax]
0x14001dbc2  lea     rcx, [rdx-18h]
0x14001dbc6  mov     rdi, [rbp+var_30]
0x14001dbca  add     rdi, 0FFFFFFFFFFFFFFE8h
0x14001dbce  cmp     rcx, rdi
0x14001dbd1  jz      short loc_14001DC09
0x14001dbd3  cmp     dword ptr [rdi+10h], 0
0x14001dbd7  jl      short loc_14001DBFB
0x14001dbd9  mov     rax, [rdi]
0x14001dbdc  cmp     [rcx], rax
0x14001dbdf  jnz     short loc_14001DBFB
0x14001dbe1  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001dbe6  mov     rbx, rax
0x14001dbe9  mov     rcx, rdi; this
0x14001dbec  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001dbf1  lea     rax, [rbx+18h]
0x14001dbf5  mov     [rbp+var_30], rax
0x14001dbf9  jmp     short loc_14001DC09
0x14001dbfb  mov     r8d, [rdx-10h]
0x14001dbff  lea     rcx, [rbp+var_30]
0x14001dc03  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001dc08  nop
0x14001dc09  mov     rcx, [rbp+var_20]
0x14001dc0d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001dc11  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001dc16  lea     rcx, [rbp+var_30]
0x14001dc1a  call    ??9ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBD@Z; ATL::operator!=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,char const *)
0x14001dc1f  test    al, al
0x14001dc21  jnz     loc_14001DB24
0x14001dc27  mov     rcx, [rbp+var_30]
0x14001dc2b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001dc2f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001dc34  mov     rbx, [rsp+50h+arg_0]
0x14001dc39  mov     rsi, [rsp+50h+arg_8]
0x14001dc3e  add     rsp, 50h
0x14001dc42  pop     r14
0x14001dc44  pop     rdi
0x14001dc45  pop     rbp
0x14001dc46  retn
```
