# ForEachRegValue__lambda_04eec936f710298a39cbd82ae29f8689_

- ea: `0x180033418`
- end: `0x180033686`
- name: `ForEachRegValue__lambda_04eec936f710298a39cbd82ae29f8689___`
- size: `622`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180035074`

## callees

- `0x180012390`
- `0x180012d80`
- `0x1800248c4`
- `0x18002b358`
- `0x18002c1fc`
- `0x180032f9c`
- `0x180033418`
- `0x1800366b8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180033603`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033614`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033603`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033614`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003347e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003347e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003356d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003356d`

## string_xrefs

- `0x18003363b`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x18003364d`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x180033662`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x180033674`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ForEachRegValue__lambda_04eec936f710298a39cbd82ae29f8689_(HKEY hKey, __int64 a2)
{
  unsigned int v4; // eax
  DWORD v5; // edx
  DWORD v6; // eax
  __int64 v7; // r8
  const char *v8; // r9
  DWORD v9; // esi
  BYTE *i; // r14
  unsigned __int64 v11; // rdi
  DWORD v12; // eax
  unsigned int v13; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  int v17; // r8d
  unsigned int lpcSubKeys; // [rsp+28h] [rbp-59h]
  DWORD cValues; // [rsp+68h] [rbp-19h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-15h] BYREF
  int v22; // [rsp+70h] [rbp-11h] BYREF
  DWORD cchValueName; // [rsp+74h] [rbp-Dh] BYREF
  LPBYTE lpData[2]; // [rsp+78h] [rbp-9h] BYREF
  __int64 v25; // [rsp+88h] [rbp+7h]
  LPWSTR lpValueName[2]; // [rsp+90h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+A0h] [rbp+1Fh]
  char v28; // [rsp+A8h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]
  DWORD cbMaxValueNameLen; // [rsp+F8h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+100h] [rbp+7Fh] BYREF

  cValues = 0;
  cbMaxValueNameLen = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
      (const char *)v4,
      lpcSubKeys);
  v5 = cbMaxValueNameLen;
  v6 = cbMaxValueNameLen + 1;
  v7 = 0xFFFFFFFFLL;
  if ( cbMaxValueNameLen + 1 >= cbMaxValueNameLen )
    v7 = v6;
  v8 = v6 < cbMaxValueNameLen ? (const char *)0x80070216LL : 0LL;
  cbMaxValueNameLen = v7;
  if ( v6 < v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
      v8,
      lpcSubKeys);
  *(_OWORD *)lpValueName = 0;
  v27 = 0;
  if ( (_DWORD)v7 )
    std::vector<unsigned short>::_Reallocate((__int64)lpValueName, (unsigned int)v7);
  *(_OWORD *)lpData = 0;
  v25 = 0;
  std::vector<unsigned char>::_Reallocate(lpData, 260, v7, v8);
  cbData = 0;
  v9 = 0;
  for ( i = lpData[0]; v9 < cValues; ++v9 )
  {
    cchValueName = cbMaxValueNameLen;
    Type = 0;
    v11 = v25 - (_QWORD)i;
    v12 = v25 - (_DWORD)i;
    if ( (unsigned __int64)(v25 - (_QWORD)i) > 0xFFFFFFFF )
      v12 = -1;
    cbData = v12;
    if ( v11 > 0xFFFFFFFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F,
        (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
        v11 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
        lpcSubKeys);
    v13 = RegEnumValueW(hKey, v9, lpValueName[0], &cchValueName, 0, &Type, i, &cbData);
    if ( v13 == 234 )
    {
      if ( v11 < cbData )
      {
        std::vector<unsigned char>::_Reallocate(lpData, cbData, v14, v15);
        i = lpData[0];
      }
      --v9;
    }
    else
    {
      if ( v13 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2E,
          (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
          (const char *)v13,
          lpcSubKeys);
      v22 = 0;
      if ( Type == 4
        && cbData == 4
        && (int)GetProvisionStateFromString(lpValueName[0], (enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 *)&v22) >= 0 )
      {
        v16 = std::_Tree_buy<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>::_Buynode<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 &,long &>(
                a2 + 48,
                &v22,
                i);
        std::_Tree<std::_Tmap_traits<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>::_Insert_nohint<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long> &,std::_Tree_node<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>,void *> *>(
          a2 + 48,
          (unsigned int)&v28,
          v17,
          v16 + 28,
          v16);
      }
    }
  }
  if ( i )
    operator delete(i);
  if ( lpValueName[0] )
    operator delete(lpValueName[0]);
  return v9;
}

```

## disassembly

```asm
0x180033418  mov     rax, rsp
0x18003341b  mov     [rax+8], rbx
0x18003341f  mov     [rax+10h], rsi
0x180033423  push    rbp
0x180033424  push    rdi
0x180033425  push    r12
0x180033427  push    r13
0x180033429  push    r14
0x18003342b  lea     rbp, [rax-5Fh]
0x18003342f  sub     rsp, 0B0h
0x180033436  mov     rbx, rdx
0x180033439  mov     r12, rcx
0x18003343c  xor     r13d, r13d
0x18003343f  mov     [rbp+57h+cValues], r13d
0x180033443  mov     [rbp+57h+cbMaxValueNameLen], r13d
0x180033447  mov     [rax-80h], r13
0x18003344b  mov     [rsp+0D0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180033450  mov     [rsp+0D0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180033455  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x180033459  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18003345e  lea     rax, [rbp+57h+cValues]
0x180033462  mov     [rsp+0D0h+lpcValues], rax; lpcValues
0x180033467  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18003346c  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180033471  mov     [rsp+0D0h+lpcSubKeys], r13; int
0x180033476  xor     r9d, r9d; lpReserved
0x180033479  xor     r8d, r8d; lpcchClass
0x18003347c  xor     edx, edx; lpClass
0x18003347e  call    cs:__imp_RegQueryInfoKeyW
0x180033484  mov     rcx, [rbp+5Fh]; this
0x180033488  test    eax, eax
0x18003348a  jnz     loc_18003365F
0x180033490  mov     edx, [rbp+57h+cbMaxValueNameLen]
0x180033493  lea     eax, [rdx+1]
0x180033496  mov     r8d, 0FFFFFFFFh
0x18003349c  cmp     eax, edx
0x18003349e  cmovnb  r8d, eax
0x1800334a2  sbb     r9d, r9d
0x1800334a5  and     r9d, 80070216h; char *
0x1800334ac  mov     [rbp+57h+cbMaxValueNameLen], r8d
0x1800334b0  mov     rcx, [rbp+5Fh]; this
0x1800334b4  cmp     eax, edx
0x1800334b6  jb      loc_180033674
0x1800334bc  xorps   xmm0, xmm0
0x1800334bf  movdqu  xmmword ptr [rbp+57h+lpValueName], xmm0
0x1800334c4  mov     [rbp+57h+var_38], r13
0x1800334c8  mov     edx, r8d
0x1800334cb  test    r8d, r8d
0x1800334ce  jz      short loc_1800334D9
0x1800334d0  lea     rcx, [rbp+57h+lpValueName]
0x1800334d4  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x1800334d9  xorps   xmm0, xmm0
0x1800334dc  movdqu  xmmword ptr [rbp+57h+lpData], xmm0
0x1800334e1  mov     [rbp+57h+var_50], r13
0x1800334e5  mov     edx, 104h
0x1800334ea  lea     rcx, [rbp+57h+lpData]
0x1800334ee  call    ?_Reallocate@?$vector@EV?$allocator@E@std@@@std@@IEAAX_K@Z; std::vector<uchar>::_Reallocate(unsigned __int64)
0x1800334f3  mov     [rbp+57h+cbData], r13d
0x1800334f7  mov     esi, r13d
0x1800334fa  mov     r14, [rbp+57h+lpData]
0x1800334fe  cmp     [rbp+57h+cValues], r13d
0x180033502  jbe     loc_1800335FB
0x180033508  mov     edx, 0FFFFFFFFh
0x18003350d  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x180033510  mov     [rbp+57h+cchValueName], eax
0x180033513  mov     [rbp+57h+Type], r13d
0x180033517  mov     rdi, [rbp+57h+var_50]
0x18003351b  sub     rdi, r14
0x18003351e  cmp     rdi, rdx
0x180033521  mov     eax, edi
0x180033523  jbe     short loc_180033527
0x180033525  mov     eax, edx
0x180033527  cmp     rdx, rdi
0x18003352a  sbb     r9d, r9d
0x18003352d  and     r9d, 80070216h; char *
0x180033534  mov     [rbp+57h+cbData], eax
0x180033537  mov     rcx, [rbp+5Fh]; this
0x18003353b  cmp     rdi, rdx
0x18003353e  ja      loc_18003364D
0x180033544  lea     rax, [rbp+57h+cbData]
0x180033548  mov     [rsp+0D0h+lpcValues], rax; lpcbData
0x18003354d  mov     [rsp+0D0h+lpcbMaxClassLen], r14; lpData
0x180033552  lea     rax, [rbp+57h+Type]
0x180033556  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpType
0x18003355b  mov     [rsp+0D0h+lpcSubKeys], r13; unsigned int
0x180033560  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180033564  mov     r8, [rbp+57h+lpValueName]; lpValueName
0x180033568  mov     edx, esi; dwIndex
0x18003356a  mov     rcx, r12; hKey
0x18003356d  call    cs:__imp_RegEnumValueW
0x180033573  cmp     eax, 0EAh
0x180033578  jnz     short loc_180033598
0x18003357a  mov     edx, [rbp+57h+cbData]
0x18003357d  cmp     rdi, rdx
0x180033580  jnb     short loc_18003358F
0x180033582  lea     rcx, [rbp+57h+lpData]
0x180033586  call    ?_Reallocate@?$vector@EV?$allocator@E@std@@@std@@IEAAX_K@Z; std::vector<uchar>::_Reallocate(unsigned __int64)
0x18003358b  mov     r14, [rbp+57h+lpData]
0x18003358f  mov     edx, 0FFFFFFFFh
0x180033594  add     esi, edx
0x180033596  jmp     short loc_1800335F0
0x180033598  mov     rcx, [rbp+5Fh]; this
0x18003359c  test    eax, eax
0x18003359e  jnz     loc_180033638
0x1800335a4  mov     [rbp+57h+var_68], r13d
0x1800335a8  cmp     [rbp+57h+Type], 4
0x1800335ac  jnz     short loc_1800335EB
0x1800335ae  cmp     [rbp+57h+cbData], 4
0x1800335b2  jnz     short loc_1800335EB
0x1800335b4  lea     rdx, [rbp+57h+var_68]; enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 *
0x1800335b8  mov     rcx, [rbp+57h+lpValueName]; String1
0x1800335bc  call    ?GetProvisionStateFromString@@YAJPEBGPEAW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@@Z; GetProvisionStateFromString(ushort const *,__MIDL___MIDL_itf_mvengine_0000_0000_0001 *)
0x1800335c1  test    eax, eax
0x1800335c3  js      short loc_1800335EB
0x1800335c5  mov     r8, r14
0x1800335c8  lea     rdx, [rbp+57h+var_68]
0x1800335cc  lea     rcx, [rbx+30h]
0x1800335d0  call    ??$_Buynode@AEAW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@AEAJ@?$_Tree_buy@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@PEAX@1@AEAW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@AEAJ@Z; std::_Tree_buy<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>::_Buynode<__MIDL___MIDL_itf_mvengine_0000_0000_0001 &,long &>(__MIDL___MIDL_itf_mvengine_0000_0000_0001 &,long &)
0x1800335d5  lea     r9, [rax+1Ch]
0x1800335d9  mov     [rsp+0D0h+lpcSubKeys], rax
0x1800335de  lea     rdx, [rbp+57h+var_30]
0x1800335e2  lea     rcx, [rbx+30h]
0x1800335e6  call    ??$_Insert_nohint@AEAU?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@PEAU?$_Tree_node@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@W4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@JU?$less@W4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@@std@@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@1@PEAU?$_Tree_node@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<__MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<__MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>::_Insert_nohint<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long> &,std::_Tree_node<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>,void *> *>(bool,std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long> &,std::_Tree_node<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>,void *> *)
0x1800335eb  mov     edx, 0FFFFFFFFh
0x1800335f0  inc     esi
0x1800335f2  cmp     esi, [rbp+57h+cValues]
0x1800335f5  jb      loc_18003350D
0x1800335fb  test    r14, r14
0x1800335fe  jz      short loc_18003360A
0x180033600  mov     rcx, r14
0x180033603  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033609  nop
0x18003360a  cmp     [rbp+57h+lpValueName], r13
0x18003360e  jz      short loc_18003361A
0x180033610  mov     rcx, [rbp+57h+lpValueName]
0x180033614  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003361a  mov     eax, esi
0x18003361c  lea     r11, [rsp+0D0h+var_20]
0x180033624  mov     rbx, [r11+30h]
0x180033628  mov     rsi, [r11+38h]
0x18003362c  mov     rsp, r11
0x18003362f  pop     r14
0x180033631  pop     r13
0x180033633  pop     r12
0x180033635  pop     rdi
0x180033636  pop     rbp
0x180033637  retn
0x180033638  mov     r9d, eax; char *
0x18003363b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x180033642  mov     edx, 2Eh ; '.'; void *
0x180033647  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003364d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x180033654  mov     edx, 1Fh; void *
0x180033659  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003365f  mov     r9d, eax; char *
0x180033662  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x180033669  mov     edx, 10h; void *
0x18003366e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180033674  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x18003367b  mov     edx, 13h; void *
0x180033680  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
