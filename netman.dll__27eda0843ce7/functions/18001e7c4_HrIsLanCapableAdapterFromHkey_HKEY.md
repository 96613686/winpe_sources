# HrIsLanCapableAdapterFromHkey(HKEY__ *)

- ea: `0x18001e7c4`
- end: `0x18001eb73`
- name: `?HrIsLanCapableAdapterFromHkey@@YAJPEAUHKEY__@@@Z`
- size: `943`
- prototype: `__int64 __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eb7c`

## callees

- `0x180001710`
- `0x1800043a8`
- `0x180004640`
- `0x18000538c`
- `0x18001e340`
- `0x18001e7c4`
- `0x18001efb8`
- `0x18001efe4`
- `0x1800301b4`
- `0x180030434`
- `0x18003106c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001e863`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001e863`
- `ADVAPI32!RegCloseKey` at `0x18001eabd`
- `ADVAPI32!RegCloseKey` at `0x18001eabd`
- `KERNEL32!lstrcmpiW` at `0x18001ea67`
- `KERNEL32!lstrcmpiW` at `0x18001ea67`

## string_xrefs

- `0x18001e839`: `ComponentId`

## pseudocode

```c
__int64 __fastcall HrIsLanCapableAdapterFromHkey(HKEY a1)
{
  int v2; // eax
  unsigned int v3; // esi
  _QWORD **v4; // rcx
  _QWORD *v5; // rcx
  _QWORD *v6; // rbx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  const unsigned __int16 **v10; // r8
  unsigned int *v11; // r9
  const unsigned __int16 **v12; // r8
  unsigned int *v13; // r9
  const unsigned __int16 **v14; // r8
  unsigned int *v15; // r9
  const unsigned __int16 **v16; // r8
  unsigned int *v17; // r9
  const unsigned __int16 **v18; // r8
  unsigned int *v19; // r9
  const unsigned __int16 **v20; // r8
  unsigned int *v21; // r9
  const unsigned __int16 **v22; // r8
  unsigned int *v23; // r9
  int v24; // r14d
  int v25; // eax
  _QWORD *v26; // r8
  _QWORD *i; // rbx
  const WCHAR *v28; // rcx
  int v29; // eax
  _QWORD *j; // rbx
  void *v31; // rcx
  _QWORD **v32; // rcx
  _QWORD *v33; // rcx
  _QWORD *v34; // rbx
  unsigned int v36; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v38; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v39; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int8 v40[2]; // [rsp+60h] [rbp-A0h] BYREF

  v38 = 512;
  v39 = 0;
  std::list<CLch *>::_Alloc_sentinel_and_proxy(&v39);
  hKey = 0;
  v36 = 0;
  v2 = HrRegQueryValueEx(a1, L"ComponentId", &v36, v40, &v38);
  v3 = 1;
  if ( !v2 )
  {
    if ( v36 == 1 )
      goto LABEL_3;
LABEL_8:
    *(_WORD *)v40 = 0;
    goto LABEL_9;
  }
  if ( v2 < 0 )
    goto LABEL_8;
LABEL_3:
  if ( !(unsigned int)_o__wcsicmp(v40, L"BTH\\MS_BTHPAN") )
  {
    v4 = (_QWORD **)v39;
    **(_QWORD **)(v39 + 8) = 0;
    v5 = *v4;
    if ( v5 )
    {
      do
      {
        v6 = (_QWORD *)*v5;
        std::_Deallocate<16>(v5, 0x18u);
        v5 = v6;
      }
      while ( v6 );
    }
    goto LABEL_51;
  }
LABEL_9:
  v7 = HrRegOpenKeyEx(a1, L"Ndi\\Interfaces", 0x20019u, &hKey);
  v8 = v7;
  if ( v7 < 0 )
  {
    if ( v7 != -2147024894 )
      goto LABEL_45;
    goto LABEL_44;
  }
  v38 = 512;
  v36 = 0;
  v9 = HrRegQueryValueEx(hKey, L"UpperRange", &v36, v40, &v38);
  v8 = v9;
  if ( v9 )
  {
    if ( v9 >= 0 )
      goto LABEL_12;
LABEL_23:
    *(_WORD *)v40 = 0;
    goto LABEL_19;
  }
  if ( v36 != 1 )
    goto LABEL_23;
LABEL_12:
  if ( (unsigned int)FSubstringMatch((const unsigned __int16 *)v40, L"ndis4", v10, v11)
    || (unsigned int)FSubstringMatch((const unsigned __int16 *)v40, L"ndis5", v12, v13)
    || (unsigned int)FSubstringMatch((const unsigned __int16 *)v40, L"ndis5_ip", v14, v15)
    || (unsigned int)FSubstringMatch((const unsigned __int16 *)v40, L"flpp4", v16, v17)
    || (unsigned int)FSubstringMatch((const unsigned __int16 *)v40, L"flpp6", v18, v19)
    || (unsigned int)FSubstringMatch((const unsigned __int16 *)v40, L"ndis1394", v20, v21)
    || (unsigned int)FSubstringMatch((const unsigned __int16 *)v40, L"ndisbda", v22, v23) )
  {
    v24 = 1;
    goto LABEL_40;
  }
LABEL_19:
  v24 = 0;
  v38 = 512;
  v36 = 0;
  v25 = HrRegQueryValueEx(hKey, L"LowerRange", &v36, v40, &v38);
  v8 = v25;
  if ( v25 )
  {
    if ( v25 < 0 )
      goto LABEL_25;
  }
  else if ( v36 != 1 )
  {
    v8 = -2147023092;
LABEL_25:
    *(_WORD *)v40 = 0;
    goto LABEL_40;
  }
  ConvertStringToColString((unsigned __int16 *)v40);
  v26 = (_QWORD *)v39;
  for ( i = *(_QWORD **)v39; i != v26; i = (_QWORD *)*i )
  {
    v28 = (const WCHAR *)i[2];
    if ( *((_QWORD *)v28 + 3) > 7u )
      v28 = *(const WCHAR **)v28;
    v29 = lstrcmpiW(v28, L"LocalTalk");
    v26 = (_QWORD *)v39;
    if ( !v29 )
    {
      v24 = 1;
      break;
    }
  }
  for ( j = (_QWORD *)*v26; j != v26; j = (_QWORD *)*j )
  {
    v31 = (void *)j[2];
    if ( v31 )
    {
      std::wstring::`scalar deleting destructor'(v31);
      v26 = (_QWORD *)v39;
    }
  }
  std::list<std::wstring *>::erase(&v39, &v36, *v26, v26);
LABEL_40:
  RegCloseKey(hKey);
  if ( v8 < 0 )
    goto LABEL_45;
  if ( v24 )
  {
    v8 = 0;
    goto LABEL_45;
  }
LABEL_44:
  v8 = 1;
LABEL_45:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_35d09b3fa63b3959b71899817b9a8e52_Traceguids, (unsigned int)v8);
  v32 = (_QWORD **)v39;
  **(_QWORD **)(v39 + 8) = 0;
  v33 = *v32;
  if ( v33 )
  {
    do
    {
      v34 = (_QWORD *)*v33;
      std::_Deallocate<16>(v33, 0x18u);
      v33 = v34;
    }
    while ( v34 );
  }
  v3 = v8;
LABEL_51:
  std::_Deallocate<16>((_QWORD *)v39, 0x18u);
  return v3;
}

```

## disassembly

```asm
0x18001e7c4  mov     [rsp-8+arg_8], rbx
0x18001e7c9  mov     [rsp-8+arg_10], rsi
0x18001e7ce  push    rbp
0x18001e7cf  push    rdi
0x18001e7d0  push    r14
0x18001e7d2  lea     rbp, [rsp-170h]
0x18001e7da  sub     rsp, 270h
0x18001e7e1  mov     rax, cs:__security_cookie
0x18001e7e8  xor     rax, rsp
0x18001e7eb  mov     [rbp+180h+var_20], rax
0x18001e7f2  mov     rdi, rcx
0x18001e7f5  mov     [rsp+280h+var_240], 200h
0x18001e7fd  xorps   xmm0, xmm0
0x18001e800  movdqu  [rsp+280h+var_238], xmm0
0x18001e806  lea     rcx, [rsp+280h+var_238]
0x18001e80b  call    ?_Alloc_sentinel_and_proxy@?$list@PEAVCLch@@V?$allocator@PEAVCLch@@@std@@@std@@AEAAXXZ; std::list<CLch *>::_Alloc_sentinel_and_proxy(void)
0x18001e810  mov     [rsp+280h+hKey], 0
0x18001e819  mov     ebx, [rsp+280h+var_240]
0x18001e81d  mov     [rsp+280h+var_250], 0
0x18001e825  lea     rax, [rsp+280h+var_240]
0x18001e82a  mov     [rsp+280h+var_260], rax; unsigned int *
0x18001e82f  lea     r9, [rsp+280h+var_220]; unsigned __int8 *
0x18001e834  lea     r8, [rsp+280h+var_250]; unsigned int *
0x18001e839  lea     rdx, ?c_szRegValueComponentId@@3QBGB; "ComponentId"
0x18001e840  mov     rcx, rdi; HKEY
0x18001e843  call    ?HrRegQueryValueEx@@YAJPEAUHKEY__@@PEBGPEAKPEAE2@Z; HrRegQueryValueEx(HKEY__ *,ushort const *,ulong *,uchar *,ulong *)
0x18001e848  mov     esi, 1
0x18001e84d  test    eax, eax
0x18001e84f  jnz     short loc_18001E8A7
0x18001e851  cmp     [rsp+280h+var_250], esi
0x18001e855  jnz     short loc_18001E8A9
0x18001e857  lea     rdx, aBthMsBthpan; "BTH\\MS_BTHPAN"
0x18001e85e  lea     rcx, [rsp+280h+var_220]
0x18001e863  call    cs:__imp__o__wcsicmp
0x18001e869  test    eax, eax
0x18001e86b  jnz     short loc_18001E8B5
0x18001e86d  mov     rcx, qword ptr [rsp+280h+var_238]
0x18001e872  mov     rax, [rcx+8]
0x18001e876  mov     qword ptr [rax], 0
0x18001e87d  mov     rcx, [rcx]
0x18001e880  mov     r14d, 18h
0x18001e886  test    rcx, rcx
0x18001e889  jz      loc_18001EB3D
0x18001e88f  mov     rbx, [rcx]
0x18001e892  mov     rdx, r14
0x18001e895  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e89a  mov     rcx, rbx
0x18001e89d  test    rbx, rbx
0x18001e8a0  jnz     short loc_18001E88F
0x18001e8a2  jmp     loc_18001EB3D
0x18001e8a7  jns     short loc_18001E857
0x18001e8a9  cmp     ebx, 2
0x18001e8ac  jb      short loc_18001E8B5
0x18001e8ae  xor     eax, eax
0x18001e8b0  mov     word ptr [rsp+280h+var_220], ax
0x18001e8b5  lea     r9, [rsp+280h+hKey]; HKEY *
0x18001e8ba  mov     r8d, 20019h; unsigned int
0x18001e8c0  lea     rdx, ?c_szRegKeyInterfacesFromInstance@@3QBGB; "Ndi\\Interfaces"
0x18001e8c7  mov     rcx, rdi; HKEY
0x18001e8ca  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18001e8cf  mov     edi, eax
0x18001e8d1  test    eax, eax
0x18001e8d3  js      loc_18001EAD0
0x18001e8d9  mov     [rsp+280h+var_240], 200h
0x18001e8e1  mov     [rsp+280h+var_250], 0
0x18001e8e9  lea     rax, [rsp+280h+var_240]
0x18001e8ee  mov     [rsp+280h+var_260], rax; unsigned int *
0x18001e8f3  lea     r9, [rsp+280h+var_220]; unsigned __int8 *
0x18001e8f8  lea     r8, [rsp+280h+var_250]; unsigned int *
0x18001e8fd  lea     rdx, ?c_szRegValueUpperRange@@3QBGB; "UpperRange"
0x18001e904  mov     rcx, [rsp+280h+hKey]; HKEY
0x18001e909  call    ?HrRegQueryValueEx@@YAJPEAUHKEY__@@PEBGPEAKPEAE2@Z; HrRegQueryValueEx(HKEY__ *,ushort const *,ulong *,uchar *,ulong *)
0x18001e90e  mov     edi, eax
0x18001e910  test    eax, eax
0x18001e912  jnz     loc_18001EA19
0x18001e918  cmp     [rsp+280h+var_250], esi
0x18001e91c  jnz     loc_18001EA1F
0x18001e922  lea     rdx, ?c_szBiNdis4@@3QBGB; "ndis4"
0x18001e929  lea     rcx, [rsp+280h+var_220]; Buf1
0x18001e92e  call    ?FSubstringMatch@@YAHPEBG0PEAPEBGPEAK@Z; FSubstringMatch(ushort const *,ushort const *,ushort const * *,ulong *)
0x18001e933  test    eax, eax
0x18001e935  jnz     loc_18001EAB5
0x18001e93b  lea     rdx, ?c_szBiNdis5@@3QBGB; "ndis5"
0x18001e942  lea     rcx, [rsp+280h+var_220]; Buf1
0x18001e947  call    ?FSubstringMatch@@YAHPEBG0PEAPEBGPEAK@Z; FSubstringMatch(ushort const *,ushort const *,ushort const * *,ulong *)
0x18001e94c  test    eax, eax
0x18001e94e  jnz     loc_18001EAB5
0x18001e954  lea     rdx, ?c_szBiNdis5Ip@@3QBGB; "ndis5_ip"
0x18001e95b  lea     rcx, [rsp+280h+var_220]; Buf1
0x18001e960  call    ?FSubstringMatch@@YAHPEBG0PEAPEBGPEAK@Z; FSubstringMatch(ushort const *,ushort const *,ushort const * *,ulong *)
0x18001e965  test    eax, eax
0x18001e967  jnz     loc_18001EAB5
0x18001e96d  lea     rdx, ?c_szBiFlpp4@@3QBGB; "flpp4"
0x18001e974  lea     rcx, [rsp+280h+var_220]; Buf1
0x18001e979  call    ?FSubstringMatch@@YAHPEBG0PEAPEBGPEAK@Z; FSubstringMatch(ushort const *,ushort const *,ushort const * *,ulong *)
0x18001e97e  test    eax, eax
0x18001e980  jnz     loc_18001EAB5
0x18001e986  lea     rdx, ?c_szBiFlpp6@@3QBGB; "flpp6"
0x18001e98d  lea     rcx, [rsp+280h+var_220]; Buf1
0x18001e992  call    ?FSubstringMatch@@YAHPEBG0PEAPEBGPEAK@Z; FSubstringMatch(ushort const *,ushort const *,ushort const * *,ulong *)
0x18001e997  test    eax, eax
0x18001e999  jnz     loc_18001EAB5
0x18001e99f  lea     rdx, ?c_szBiNdis1394@@3QBGB; "ndis1394"
0x18001e9a6  lea     rcx, [rsp+280h+var_220]; Buf1
0x18001e9ab  call    ?FSubstringMatch@@YAHPEBG0PEAPEBGPEAK@Z; FSubstringMatch(ushort const *,ushort const *,ushort const * *,ulong *)
0x18001e9b0  test    eax, eax
0x18001e9b2  jnz     loc_18001EAB5
0x18001e9b8  lea     rdx, ?c_szBiNdisBda@@3QBGB; "ndisbda"
0x18001e9bf  lea     rcx, [rsp+280h+var_220]; Buf1
0x18001e9c4  call    ?FSubstringMatch@@YAHPEBG0PEAPEBGPEAK@Z; FSubstringMatch(ushort const *,ushort const *,ushort const * *,ulong *)
0x18001e9c9  test    eax, eax
0x18001e9cb  jnz     loc_18001EAB5
0x18001e9d1  xor     r14d, r14d
0x18001e9d4  mov     [rsp+280h+var_240], 200h
0x18001e9dc  mov     [rsp+280h+var_250], r14d
0x18001e9e1  lea     rax, [rsp+280h+var_240]
0x18001e9e6  mov     [rsp+280h+var_260], rax; unsigned int *
0x18001e9eb  lea     r9, [rsp+280h+var_220]; unsigned __int8 *
0x18001e9f0  lea     r8, [rsp+280h+var_250]; unsigned int *
0x18001e9f5  lea     rdx, ?c_szRegValueLowerRange@@3QBGB; "LowerRange"
0x18001e9fc  mov     rcx, [rsp+280h+hKey]; HKEY
0x18001ea01  call    ?HrRegQueryValueEx@@YAJPEAUHKEY__@@PEBGPEAKPEAE2@Z; HrRegQueryValueEx(HKEY__ *,ushort const *,ulong *,uchar *,ulong *)
0x18001ea06  mov     edi, eax
0x18001ea08  test    eax, eax
0x18001ea0a  jnz     short loc_18001EA28
0x18001ea0c  cmp     [rsp+280h+var_250], esi
0x18001ea10  jz      short loc_18001EA36
0x18001ea12  mov     edi, 8007070Ch
0x18001ea17  jmp     short loc_18001EA2A
0x18001ea19  jns     loc_18001E922
0x18001ea1f  xor     eax, eax
0x18001ea21  mov     word ptr [rsp+280h+var_220], ax
0x18001ea26  jmp     short loc_18001E9D1
0x18001ea28  jns     short loc_18001EA36
0x18001ea2a  xor     eax, eax
0x18001ea2c  mov     word ptr [rsp+280h+var_220], ax
0x18001ea31  jmp     loc_18001EAB8
0x18001ea36  lea     r8, [rsp+280h+var_238]
0x18001ea3b  lea     rcx, [rsp+280h+var_220]; unsigned __int16 *
0x18001ea40  call    ?ConvertStringToColString@@YAXPEBGGAEAV?$list@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; ConvertStringToColString(ushort const *,ushort,std::list<std::wstring *> &)
0x18001ea45  mov     r8, qword ptr [rsp+280h+var_238]
0x18001ea4a  mov     rbx, [r8]
0x18001ea4d  cmp     rbx, r8
0x18001ea50  jz      short loc_18001EA7E
0x18001ea52  mov     rcx, [rbx+10h]
0x18001ea56  cmp     qword ptr [rcx+18h], 7
0x18001ea5b  jbe     short loc_18001EA60
0x18001ea5d  mov     rcx, [rcx]; lpString1
0x18001ea60  lea     rdx, ?c_szBiLocalTalk@@3QBGB; "LocalTalk"
0x18001ea67  call    cs:__imp_lstrcmpiW
0x18001ea6d  mov     r8, qword ptr [rsp+280h+var_238]
0x18001ea72  test    eax, eax
0x18001ea74  jz      short loc_18001EA7B
0x18001ea76  mov     rbx, [rbx]
0x18001ea79  jmp     short loc_18001EA4D
0x18001ea7b  mov     r14d, esi
0x18001ea7e  mov     rbx, [r8]
0x18001ea81  cmp     rbx, r8
0x18001ea84  jz      short loc_18001EA9E
0x18001ea86  mov     rcx, [rbx+10h]; void *
0x18001ea8a  test    rcx, rcx
0x18001ea8d  jz      short loc_18001EA99
0x18001ea8f  call    ??_G?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAPEAXI@Z; std::wstring::`scalar deleting destructor'(uint)
0x18001ea94  mov     r8, qword ptr [rsp+280h+var_238]
0x18001ea99  mov     rbx, [rbx]
0x18001ea9c  jmp     short loc_18001EA81
0x18001ea9e  mov     r9, r8
0x18001eaa1  mov     r8, [r8]
0x18001eaa4  lea     rdx, [rsp+280h+var_250]
0x18001eaa9  lea     rcx, [rsp+280h+var_238]
0x18001eaae  call    ?erase@?$list@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@0@Z; std::list<std::wstring *>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::wstring *>>>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::wstring *>>>)
0x18001eab3  jmp     short loc_18001EAB8
0x18001eab5  mov     r14d, esi
0x18001eab8  mov     rcx, [rsp+280h+hKey]; hKey
0x18001eabd  call    cs:__imp_RegCloseKey
0x18001eac3  test    edi, edi
0x18001eac5  js      short loc_18001EAD9
0x18001eac7  test    r14d, r14d
0x18001eaca  jz      short loc_18001EAD7
0x18001eacc  xor     edi, edi
0x18001eace  jmp     short loc_18001EAD9
0x18001ead0  cmp     eax, 80070002h
0x18001ead5  jnz     short loc_18001EAD9
0x18001ead7  mov     edi, esi
0x18001ead9  lea     rax, WPP_GLOBAL_Control
0x18001eae0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eae7  cmp     rcx, rax
0x18001eaea  jz      short loc_18001EB0A
0x18001eaec  test    byte ptr [rcx+1Ch], 8
0x18001eaf0  jz      short loc_18001EB0A
0x18001eaf2  mov     edx, 12h
0x18001eaf7  mov     r9d, edi
0x18001eafa  lea     r8, WPP_35d09b3fa63b3959b71899817b9a8e52_Traceguids
0x18001eb01  mov     rcx, [rcx+10h]
0x18001eb05  call    WPP_SF_d
0x18001eb0a  mov     rcx, qword ptr [rsp+280h+var_238]
0x18001eb0f  mov     rax, [rcx+8]
0x18001eb13  mov     qword ptr [rax], 0
0x18001eb1a  mov     rcx, [rcx]
0x18001eb1d  mov     r14d, 18h
0x18001eb23  test    rcx, rcx
0x18001eb26  jz      short loc_18001EB3B
0x18001eb28  mov     rbx, [rcx]
0x18001eb2b  mov     rdx, r14
0x18001eb2e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001eb33  mov     rcx, rbx
0x18001eb36  test    rbx, rbx
0x18001eb39  jnz     short loc_18001EB28
0x18001eb3b  mov     esi, edi
0x18001eb3d  mov     rdx, r14
0x18001eb40  mov     rcx, qword ptr [rsp+280h+var_238]
0x18001eb45  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001eb4a  mov     eax, esi
0x18001eb4c  mov     rcx, [rbp+180h+var_20]
0x18001eb53  xor     rcx, rsp; StackCookie
0x18001eb56  call    __security_check_cookie
0x18001eb5b  lea     r11, [rsp+280h+var_10]
0x18001eb63  mov     rbx, [r11+28h]
0x18001eb67  mov     rsi, [r11+30h]
0x18001eb6b  mov     rsp, r11
0x18001eb6e  pop     r14
0x18001eb70  pop     rdi
0x18001eb71  pop     rbp
0x18001eb72  retn
```
