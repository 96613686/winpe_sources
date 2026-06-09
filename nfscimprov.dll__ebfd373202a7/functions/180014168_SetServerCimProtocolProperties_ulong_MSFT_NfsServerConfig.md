# SetServerCimProtocolProperties(ulong,_MSFT_NfsServerConfig *)

- ea: `0x180014168`
- end: `0x180014460`
- name: `?SetServerCimProtocolProperties@@YAXKPEAU_MSFT_NfsServerConfig@@@Z`
- size: `760`
- prototype: `void __fastcall(unsigned int, MI_Instance *self)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010f28`

## callees

- `0x180009704`
- `0x180009744`
- `0x1800097d0`
- `0x18000994c`
- `0x18000eae4`
- `0x18000fc34`
- `0x18000fd28`
- `0x180014168`
- `0x180035b40`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800143e7`
- `msvcrt!_wcsicmp` at `0x1800143e7`

## string_xrefs

- `0x180014314`: `MapsvrProtocol`
- `0x180014248`: `MountProtocol`
- `0x18001427b`: `NfsProtocol`
- `0x180014347`: `NisProtocol`
- `0x1800143e0`: `NisProtocol`
- `0x1800142ae`: `NlmProtocol`
- `0x1800142e1`: `NsmProtocol`
- `0x180014215`: `PortmapProtocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SetServerCimProtocolProperties(unsigned int a1, MI_Instance *self)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 v9; // rdx
  MI_Uint32 v10; // ebx
  __int64 v11; // rdx
  unsigned int v12; // ebx
  __int64 v13; // rdx
  unsigned int v14; // ebx
  __int64 v15; // rdx
  unsigned int v16; // ebx
  __int64 v17; // rdx
  __int64 *v18; // rax
  __int64 *v19; // rbx
  __int64 v20; // rdi
  const wchar_t *v21; // rdx
  const MI_Char *v22; // rdx
  MI_Uint32 flags; // [rsp+20h] [rbp-E0h]
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v25; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v26; // [rsp+48h] [rbp-B8h] BYREF
  MI_Uint32 v27; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v28; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v29; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v30; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v31[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-60h]
  _OWORD v33[2]; // [rsp+B0h] [rbp-50h] BYREF
  MI_Value value; // [rsp+D0h] [rbp-30h] BYREF

  stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>(v31);
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  GetProtocolSettings(a1, &v24, &v25, &v26, &v27, &v28, &v29, &v30);
  v4 = v24;
  std::wstring::wstring(v33, L"PortmapProtocol");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v31,
               v33) = v4;
  LOBYTE(v5) = 1;
  std::wstring::_Tidy(v33, v5, 0);
  v6 = v25;
  std::wstring::wstring(v33, L"MountProtocol");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v31,
               v33) = v6;
  LOBYTE(v7) = 1;
  std::wstring::_Tidy(v33, v7, 0);
  v8 = v26;
  std::wstring::wstring(v33, L"NfsProtocol");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v31,
               v33) = v8;
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(v33, v9, 0);
  v10 = v27;
  std::wstring::wstring(v33, L"NlmProtocol");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v31,
               v33) = v10;
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(v33, v11, 0);
  v12 = v28;
  std::wstring::wstring(v33, L"NsmProtocol");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v31,
               v33) = v12;
  LOBYTE(v13) = 1;
  std::wstring::_Tidy(v33, v13, 0);
  v14 = v29;
  std::wstring::wstring(v33, L"MapsvrProtocol");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v31,
               v33) = v14;
  LOBYTE(v15) = 1;
  std::wstring::_Tidy(v33, v15, 0);
  v16 = v30;
  std::wstring::wstring(v33, L"NisProtocol");
  *(_DWORD *)stdext::hash_map<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>>::operator[](
               v31,
               v33) = v16;
  LOBYTE(v17) = 1;
  std::wstring::_Tidy(v33, v17, 0);
  v18 = (__int64 *)v31[0];
  v19 = *(__int64 **)v31[0];
  while ( v19 != v18 )
  {
    memset(v33, 0, sizeof(v33));
    v32 = 0;
    memset(&value, 0, sizeof(value));
    v20 = v19[6] & 1;
    if ( (v19[6] & 1) != 0 )
      *(_QWORD *)&v33[0] = L"TCP";
    if ( (v19[6] & 2) != 0 )
    {
      *((_QWORD *)v33 + v20) = L"UDP";
      LODWORD(v20) = v20 + 1;
    }
    if ( !(_DWORD)v20 )
    {
      v21 = (const wchar_t *)(v19 + 2);
      if ( (unsigned __int64)v19[5] >= 8 )
        v21 = *(const wchar_t **)v21;
      if ( !_wcsicmp(L"NisProtocol", v21) )
      {
        *(_QWORD *)&v33[0] = L"TCP";
        *((_QWORD *)&v33[0] + 1) = L"UDP";
        LODWORD(v20) = 2;
      }
    }
    value.uint64 = (MI_Uint64)v33;
    *(&value.uint64 + 1) = __PAIR64__(HIDWORD(v32), v20);
    v22 = (const MI_Char *)(v19 + 2);
    if ( (unsigned __int64)v19[5] >= 8 )
      v22 = *(const MI_Char **)v22;
    MI_Instance_SetElement(self, v22, &value, MI_STRINGA, flags);
    v19 = (__int64 *)*v19;
    v18 = (__int64 *)v31[0];
  }
  std::_Hash<stdext::_Hmap_traits<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Hash<stdext::_Hmap_traits<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v31);
}

```

## disassembly

```asm
0x180014168  push    rbp
0x18001416a  push    rbx
0x18001416b  push    rsi
0x18001416c  push    rdi
0x18001416d  push    r12
0x18001416f  push    r15
0x180014171  lea     rbp, [rsp-8]
0x180014176  sub     rsp, 108h
0x18001417d  mov     rax, cs:__security_cookie
0x180014184  xor     rax, rsp
0x180014187  mov     [rbp+30h+var_38], rax
0x18001418b  mov     rsi, rdx
0x18001418e  mov     ebx, ecx
0x180014190  lea     rcx, [rsp+130h+var_D0]
0x180014195  call    ??0?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAA@XZ; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>(void)
0x18001419a  nop
0x18001419b  mov     [rsp+130h+var_F0], 0
0x1800141a3  mov     [rsp+130h+var_EC], 0
0x1800141ab  mov     [rsp+130h+var_E8], 0
0x1800141b3  mov     [rsp+130h+var_E4], 0
0x1800141bb  mov     [rsp+130h+var_E0], 0
0x1800141c3  mov     [rsp+130h+var_DC], 0
0x1800141cb  mov     [rsp+130h+var_D8], 0
0x1800141d3  lea     rax, [rsp+130h+var_D8]
0x1800141d8  mov     [rsp+130h+var_F8], rax; unsigned int *
0x1800141dd  lea     rax, [rsp+130h+var_DC]
0x1800141e2  mov     [rsp+130h+var_100], rax; unsigned int *
0x1800141e7  lea     rax, [rsp+130h+var_E0]
0x1800141ec  mov     [rsp+130h+var_108], rax; unsigned int *
0x1800141f1  lea     rax, [rsp+130h+var_E4]
0x1800141f6  mov     qword ptr [rsp+130h+flags], rax; unsigned int *
0x1800141fb  lea     r9, [rsp+130h+var_E8]; unsigned int *
0x180014200  lea     r8, [rsp+130h+var_EC]; unsigned int *
0x180014205  lea     rdx, [rsp+130h+var_F0]; unsigned int *
0x18001420a  mov     ecx, ebx; unsigned int
0x18001420c  call    ?GetProtocolSettings@@YAXKPEAK000000@Z; GetProtocolSettings(ulong,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x180014211  mov     ebx, [rsp+130h+var_F0]
0x180014215  lea     rdx, aPortmapprotoco; "PortmapProtocol"
0x18001421c  lea     rcx, [rbp+30h+var_80]
0x180014220  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180014225  nop
0x180014226  lea     rdx, [rbp+30h+var_80]
0x18001422a  lea     rcx, [rsp+130h+var_D0]
0x18001422f  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180014234  mov     [rax], ebx
0x180014236  xor     r8d, r8d
0x180014239  mov     dl, 1
0x18001423b  lea     rcx, [rbp+30h+var_80]
0x18001423f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014244  mov     ebx, [rsp+130h+var_EC]
0x180014248  lea     rdx, aMountprotocol; "MountProtocol"
0x18001424f  lea     rcx, [rbp+30h+var_80]
0x180014253  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180014258  nop
0x180014259  lea     rdx, [rbp+30h+var_80]
0x18001425d  lea     rcx, [rsp+130h+var_D0]
0x180014262  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180014267  mov     [rax], ebx
0x180014269  xor     r8d, r8d
0x18001426c  mov     dl, 1
0x18001426e  lea     rcx, [rbp+30h+var_80]
0x180014272  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014277  mov     ebx, [rsp+130h+var_E8]
0x18001427b  lea     rdx, aNfsprotocol; "NfsProtocol"
0x180014282  lea     rcx, [rbp+30h+var_80]
0x180014286  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001428b  nop
0x18001428c  lea     rdx, [rbp+30h+var_80]
0x180014290  lea     rcx, [rsp+130h+var_D0]
0x180014295  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x18001429a  mov     [rax], ebx
0x18001429c  xor     r8d, r8d
0x18001429f  mov     dl, 1
0x1800142a1  lea     rcx, [rbp+30h+var_80]
0x1800142a5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800142aa  mov     ebx, [rsp+130h+var_E4]
0x1800142ae  lea     rdx, aNlmprotocol; "NlmProtocol"
0x1800142b5  lea     rcx, [rbp+30h+var_80]
0x1800142b9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800142be  nop
0x1800142bf  lea     rdx, [rbp+30h+var_80]
0x1800142c3  lea     rcx, [rsp+130h+var_D0]
0x1800142c8  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x1800142cd  mov     [rax], ebx
0x1800142cf  xor     r8d, r8d
0x1800142d2  mov     dl, 1
0x1800142d4  lea     rcx, [rbp+30h+var_80]
0x1800142d8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800142dd  mov     ebx, [rsp+130h+var_E0]
0x1800142e1  lea     rdx, aNsmprotocol; "NsmProtocol"
0x1800142e8  lea     rcx, [rbp+30h+var_80]
0x1800142ec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800142f1  nop
0x1800142f2  lea     rdx, [rbp+30h+var_80]
0x1800142f6  lea     rcx, [rsp+130h+var_D0]
0x1800142fb  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180014300  mov     [rax], ebx
0x180014302  xor     r8d, r8d
0x180014305  mov     dl, 1
0x180014307  lea     rcx, [rbp+30h+var_80]
0x18001430b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014310  mov     ebx, [rsp+130h+var_DC]
0x180014314  lea     rdx, aMapsvrprotocol; "MapsvrProtocol"
0x18001431b  lea     rcx, [rbp+30h+var_80]
0x18001431f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180014324  nop
0x180014325  lea     rdx, [rbp+30h+var_80]
0x180014329  lea     rcx, [rsp+130h+var_D0]
0x18001432e  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180014333  mov     [rax], ebx
0x180014335  xor     r8d, r8d
0x180014338  mov     dl, 1
0x18001433a  lea     rcx, [rbp+30h+var_80]
0x18001433e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014343  mov     ebx, [rsp+130h+var_D8]
0x180014347  lea     rdx, aNisprotocol; "NisProtocol"
0x18001434e  lea     rcx, [rbp+30h+var_80]
0x180014352  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180014357  nop
0x180014358  lea     rdx, [rbp+30h+var_80]
0x18001435c  lea     rcx, [rsp+130h+var_D0]
0x180014361  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@stdext@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>>::operator[](std::wstring &&)
0x180014366  mov     [rax], ebx
0x180014368  xor     r8d, r8d
0x18001436b  mov     dl, 1
0x18001436d  lea     rcx, [rbp+30h+var_80]
0x180014371  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014376  mov     rax, [rsp+130h+var_D0]
0x18001437b  mov     rbx, [rax]
0x18001437e  lea     r15, aTcp; "TCP"
0x180014385  lea     r12, aUdp; "UDP"
0x18001438c  cmp     rbx, rax
0x18001438f  jz      loc_18001443A
0x180014395  xorps   xmm0, xmm0
0x180014398  movups  [rbp+30h+var_80], xmm0
0x18001439c  movups  [rbp+30h+var_70], xmm0
0x1800143a0  movups  [rbp+30h+var_90], xmm0
0x1800143a4  xorps   xmm1, xmm1
0x1800143a7  xor     eax, eax
0x1800143a9  movups  xmmword ptr [rbp+30h+value], xmm1
0x1800143ad  movups  xmmword ptr [rbp+30h+value+10h], xmm1
0x1800143b1  mov     qword ptr [rbp+30h+value+20h], rax
0x1800143b5  mov     edi, [rbx+30h]
0x1800143b8  and     edi, 1
0x1800143bb  jz      short loc_1800143C1
0x1800143bd  mov     qword ptr [rbp+30h+var_80], r15
0x1800143c1  test    byte ptr [rbx+30h], 2
0x1800143c5  jz      short loc_1800143CE
0x1800143c7  mov     qword ptr [rbp+rdi*8+30h+var_80], r12
0x1800143cc  inc     edi
0x1800143ce  test    edi, edi
0x1800143d0  jnz     short loc_1800143FC
0x1800143d2  lea     rdx, [rbx+10h]
0x1800143d6  cmp     qword ptr [rbx+28h], 8
0x1800143db  jb      short loc_1800143E0
0x1800143dd  mov     rdx, [rdx]; String2
0x1800143e0  lea     rcx, aNisprotocol; "NisProtocol"
0x1800143e7  call    cs:__imp__wcsicmp
0x1800143ed  test    eax, eax
0x1800143ef  jnz     short loc_1800143FC
0x1800143f1  mov     qword ptr [rbp+30h+var_80], r15
0x1800143f5  mov     qword ptr [rbp+30h+var_80+8], r12
0x1800143f9  lea     edi, [rax+2]
0x1800143fc  lea     rax, [rbp+30h+var_80]
0x180014400  mov     qword ptr [rbp+30h+value], rax
0x180014404  mov     dword ptr [rbp+30h+value+8], edi
0x180014407  mov     eax, dword ptr [rbp+30h+var_90+0Ch]
0x18001440a  mov     dword ptr [rbp+30h+value+0Ch], eax
0x18001440d  lea     rdx, [rbx+10h]
0x180014411  cmp     qword ptr [rbx+28h], 8
0x180014416  jb      short loc_18001441B
0x180014418  mov     rdx, [rdx]; name
0x18001441b  mov     r9d, 1Dh; type
0x180014421  lea     r8, [rbp+30h+value]; value
0x180014425  mov     rcx, rsi; self
0x180014428  call    MI_Instance_SetElement
0x18001442d  mov     rbx, [rbx]
0x180014430  mov     rax, [rsp+130h+var_D0]
0x180014435  jmp     loc_18001438C
0x18001443a  lea     rcx, [rsp+130h+var_D0]
0x18001443f  call    ??1?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hmap_traits<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::~_Hash<stdext::_Hmap_traits<std::wstring,ulong,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>(void)
0x180014444  mov     rcx, [rbp+30h+var_38]
0x180014448  xor     rcx, rsp; StackCookie
0x18001444b  call    __security_check_cookie
0x180014450  add     rsp, 108h
0x180014457  pop     r15
0x180014459  pop     r12
0x18001445b  pop     rdi
0x18001445c  pop     rsi
0x18001445d  pop     rbx
0x18001445e  pop     rbp
0x18001445f  retn
```
