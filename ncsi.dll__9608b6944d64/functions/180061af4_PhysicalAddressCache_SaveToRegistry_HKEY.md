# PhysicalAddressCache::SaveToRegistry(HKEY__ *)

- ea: `0x180061af4`
- end: `0x180061e54`
- name: `?SaveToRegistry@PhysicalAddressCache@@QEAAXPEAUHKEY__@@@Z`
- size: `864`
- prototype: `void __fastcall(PhysicalAddressCache *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180044460`

## callees

- `0x18000e59c`
- `0x180011a58`
- `0x18001a1b4`
- `0x180021bec`
- `0x18002f920`
- `0x18004269c`
- `0x180047240`
- `0x180047f60`
- `0x1800612d0`
- `0x180061320`
- `0x180061af4`
- `0x180061e8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180061c68`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180061c68`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061d92`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061d92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061e24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061e24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061b6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061b6d`

## pseudocode

```c
void __fastcall PhysicalAddressCache::SaveToRegistry(PhysicalAddressCache *this, HKEY a2)
{
  PhysicalAddressCache *v2; // r15
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  DateTime *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // esi
  __int64 v7; // r8
  __int64 v8; // r9
  DWORD cbData; // r12d
  __int64 **v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rax
  unsigned int v13; // r14d
  int v14; // esi
  __int64 v15; // rdx
  LSTATUS v16; // eax
  __int64 v17; // r8
  LSTATUS v18; // ebx
  __int64 v19; // rcx
  unsigned int v20; // esi
  unsigned int v21; // r14d
  int v22; // edi
  __int64 v23; // rdx
  int v24; // edi
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r9
  __int64 v28; // rbx
  LSTATUS v29; // eax
  __int64 v30; // r8
  wil *v31; // rcx
  __int64 i; // [rsp+30h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-70h]
  struct _RTL_CRITICAL_SECTION *v34; // [rsp+40h] [rbp-68h]
  PhysicalAddressCache *v35; // [rsp+48h] [rbp-60h]
  char *v36; // [rsp+50h] [rbp-58h]
  _BYTE v37[8]; // [rsp+58h] [rbp-50h] BYREF
  BYTE *lpData[2]; // [rsp+60h] [rbp-48h] BYREF
  __int64 v39; // [rsp+70h] [rbp-38h]

  hKey = a2;
  v2 = this;
  v35 = this;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      16,
      WPP_d942c27652103f52e6f09fbc2ef6f378_Traceguids,
      *(unsigned int *)this);
  }
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)v2 + 24);
  v34 = (struct _RTL_CRITICAL_SECTION *)((char *)v2 + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 24));
  v36 = (char *)v2 + 24;
  v6 = DateTime::AbsoluteDayCount(v4);
  cbData = 0;
  v10 = (__int64 **)((char *)v2 + 64);
  v11 = **((_QWORD **)v2 + 8);
LABEL_6:
  i = v11;
  while ( (__int64 *)v11 != *v10 )
  {
    if ( v6 > *(_DWORD *)(v11 + 580) + *((_DWORD *)v2 + 1) )
    {
      v11 = *(_QWORD *)std::_Tree<std::_Tmap_traits<CacheEntry,unsigned long,std::less<CacheEntry>,std::allocator<std::pair<CacheEntry const,unsigned long>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<CacheEntry const,unsigned long>>>>,0>(
                         (char *)v2 + 64,
                         v37,
                         v11);
      goto LABEL_6;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<CacheEntry const,unsigned long>>>,std::_Iterator_base0>::operator++(
      &i,
      v5,
      v7,
      v8);
    v11 = i;
  }
  v12 = **v10;
  for ( i = v12; ; v12 = i )
  {
    if ( *(_BYTE *)(v12 + 25) )
    {
      if ( !cbData )
        goto LABEL_25;
      try
      {
        *(_OWORD *)lpData = 0;
        v39 = 0;
        std::vector<unsigned char>::vector<unsigned char>(lpData, cbData);
        v27 = 0;
        v28 = **v10;
        i = v28;
        while ( !*(_BYTE *)(v28 + 25) )
        {
          v20 = *(unsigned __int16 *)(v28 + 28);
          v21 = *(unsigned __int16 *)(v28 + 62);
          lpData[0][v27] = v20;
          v22 = v27 + 1;
          memcpy_0(&lpData[0][(unsigned int)(v27 + 1)], (const void *)(v28 + 30), v20);
          v23 = v22 + v20;
          *(_WORD *)&lpData[0][v23] = v21;
          v24 = v23 + 2;
          memcpy_0(&lpData[0][(unsigned int)(v23 + 2)], (const void *)(v28 + 64), v21);
          v25 = v24 + v21;
          *(_DWORD *)&lpData[0][v25] = *(_DWORD *)(v28 + 580);
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<CacheEntry const,unsigned long>>>,std::_Iterator_base0>::operator++(
            &i,
            v26,
            v25,
            (unsigned int)(v25 + 4));
          v28 = i;
        }
        if ( (_DWORD)v27 != cbData )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v29 = RegSetValueExW(hKey, *((LPCWSTR *)v2 + 1), 0, 3u, lpData[0], cbData);
        v18 = v29;
        if ( v29
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          WPP_SF_Ld(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, v30, *(unsigned int *)v2, v29);
        }
        std::vector<unsigned char>::_Tidy(lpData);
      }
      catch ( ... )
      {
        LODWORD(i) = wil::Win32ErrorFromCaughtException(v31);
        v18 = i;
        v2 = v35;
      }
      v3 = v34;
LABEL_43:
      v19 = WPP_GLOBAL_Control;
      goto LABEL_44;
    }
    v13 = *(unsigned __int16 *)(v12 + 28);
    v14 = *(unsigned __int16 *)(v12 + 62);
    if ( v13 > 0x20 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (unsigned __int16)v14 > 0x200u )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v15 = v13 + cbData + v14 + 7;
    if ( (unsigned int)v15 < cbData )
      break;
    cbData += v13 + v14 + 7;
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<CacheEntry const,unsigned long>>>,std::_Iterator_base0>::operator++(
      &i,
      v15,
      v7,
      v8);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      17,
      WPP_d942c27652103f52e6f09fbc2ef6f378_Traceguids,
      *(unsigned int *)v2);
  }
  std::_Tree<std::_Tmap_traits<CacheEntry,unsigned long,std::less<CacheEntry>,std::allocator<std::pair<CacheEntry const,unsigned long>>,0>>::clear((char *)v2 + 64);
LABEL_25:
  v16 = RegDeleteValueW(hKey, *((LPCWSTR *)v2 + 1));
  v18 = v16;
  if ( v16 == 2 )
  {
    v18 = 0;
    goto LABEL_43;
  }
  if ( !v16 )
    goto LABEL_43;
  v19 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_48;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    WPP_SF_Ld(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, v17, *(unsigned int *)v2, v16);
    goto LABEL_43;
  }
LABEL_44:
  if ( (_UNKNOWN *)v19 != &WPP_GLOBAL_Control && (*(_BYTE *)(v19 + 28) & 0x10) != 0 && *(_BYTE *)(v19 + 25) >= 5u )
    WPP_SF_Ld(*(_QWORD *)(v19 + 16), 20, v17, *(unsigned int *)v2, v18);
LABEL_48:
  if ( v3 )
    LeaveCriticalSection(v3);
}

```

## disassembly

```asm
0x180061af4  mov     [rsp+arg_10], rbx
0x180061af9  mov     [rsp+arg_18], rsi
0x180061afe  push    rdi
0x180061aff  push    r12
0x180061b01  push    r13
0x180061b03  push    r14
0x180061b05  push    r15
0x180061b07  sub     rsp, 80h
0x180061b0e  mov     rax, cs:__security_cookie
0x180061b15  xor     rax, rsp
0x180061b18  mov     [rsp+0A8h+var_30], rax
0x180061b1d  mov     [rsp+0A8h+hKey], rdx
0x180061b22  mov     r15, rcx
0x180061b25  mov     [rsp+0A8h+var_60], rcx
0x180061b2a  lea     r13, WPP_GLOBAL_Control
0x180061b31  mov     rcx, cs:WPP_GLOBAL_Control
0x180061b38  cmp     rcx, r13
0x180061b3b  jz      short loc_180061B61
0x180061b3d  test    byte ptr [rcx+1Ch], 10h
0x180061b41  jz      short loc_180061B61
0x180061b43  cmp     byte ptr [rcx+19h], 5
0x180061b47  jb      short loc_180061B61
0x180061b49  mov     edx, 10h
0x180061b4e  mov     r9d, [r15]
0x180061b51  lea     r8, WPP_d942c27652103f52e6f09fbc2ef6f378_Traceguids
0x180061b58  mov     rcx, [rcx+10h]
0x180061b5c  call    WPP_SF_d
0x180061b61  lea     rdi, [r15+18h]
0x180061b65  mov     [rsp+0A8h+var_68], rdi
0x180061b6a  mov     rcx, rdi; lpCriticalSection
0x180061b6d  call    cs:__imp_EnterCriticalSection
0x180061b73  mov     [rsp+0A8h+var_58], rdi
0x180061b78  call    ?AbsoluteDayCount@DateTime@@YAKXZ; DateTime::AbsoluteDayCount(void)
0x180061b7d  mov     esi, eax
0x180061b7f  xor     r12d, r12d
0x180061b82  lea     rbx, [r15+40h]
0x180061b86  mov     rcx, [rbx]
0x180061b89  mov     rcx, [rcx]
0x180061b8c  mov     [rsp+0A8h+var_78], rcx
0x180061b91  mov     rax, [rbx]
0x180061b94  cmp     rcx, rax
0x180061b97  jz      short loc_180061BCD
0x180061b99  mov     eax, [r15+4]
0x180061b9d  add     eax, [rcx+244h]
0x180061ba3  cmp     esi, eax
0x180061ba5  jbe     short loc_180061BBC
0x180061ba7  mov     r8, rcx
0x180061baa  lea     rdx, [rsp+0A8h+var_50]
0x180061baf  mov     rcx, rbx
0x180061bb2  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUCacheEntry@@K@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@UCacheEntry@@KU?$less@UCacheEntry@@@std@@V?$allocator@U?$pair@$$CBUCacheEntry@@K@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUCacheEntry@@K@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<CacheEntry,ulong,std::less<CacheEntry>,std::allocator<std::pair<CacheEntry const,ulong>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<CacheEntry const,ulong>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<CacheEntry const,ulong>>>>)
0x180061bb7  mov     rcx, [rax]
0x180061bba  jmp     short loc_180061B8C
0x180061bbc  lea     rcx, [rsp+0A8h+var_78]
0x180061bc1  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUCacheEntry@@K@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<CacheEntry const,ulong>>>,std::_Iterator_base0>::operator++(void)
0x180061bc6  mov     rcx, [rsp+0A8h+var_78]
0x180061bcb  jmp     short loc_180061B91
0x180061bcd  mov     rax, [rax]
0x180061bd0  mov     [rsp+0A8h+var_78], rax
0x180061bd5  cmp     byte ptr [rax+19h], 0
0x180061bd9  jnz     short loc_180061C5A
0x180061bdb  movzx   r14d, word ptr [rax+1Ch]
0x180061be0  movzx   esi, word ptr [rax+3Eh]
0x180061be4  cmp     r14d, 20h ; ' '
0x180061be8  jbe     short loc_180061BEF
0x180061bea  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180061bef  mov     eax, 200h
0x180061bf4  cmp     si, ax
0x180061bf7  jbe     short loc_180061BFE
0x180061bf9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180061bfe  lea     edx, [rsi+7]
0x180061c01  add     edx, r12d
0x180061c04  add     edx, r14d
0x180061c07  cmp     edx, r12d
0x180061c0a  jb      short loc_180061C20
0x180061c0c  mov     r12d, edx
0x180061c0f  lea     rcx, [rsp+0A8h+var_78]
0x180061c14  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUCacheEntry@@K@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<CacheEntry const,ulong>>>,std::_Iterator_base0>::operator++(void)
0x180061c19  mov     rax, [rsp+0A8h+var_78]
0x180061c1e  jmp     short loc_180061BD5
0x180061c20  mov     rcx, cs:WPP_GLOBAL_Control
0x180061c27  cmp     rcx, r13
0x180061c2a  jz      short loc_180061C50
0x180061c2c  test    byte ptr [rcx+1Ch], 10h
0x180061c30  jz      short loc_180061C50
0x180061c32  cmp     byte ptr [rcx+19h], 2
0x180061c36  jb      short loc_180061C50
0x180061c38  mov     edx, 11h
0x180061c3d  mov     r9d, [r15]
0x180061c40  lea     r8, WPP_d942c27652103f52e6f09fbc2ef6f378_Traceguids
0x180061c47  mov     rcx, [rcx+10h]
0x180061c4b  call    WPP_SF_d
0x180061c50  mov     rcx, rbx
0x180061c53  call    ?clear@?$_Tree@V?$_Tmap_traits@UCacheEntry@@KU?$less@UCacheEntry@@@std@@V?$allocator@U?$pair@$$CBUCacheEntry@@K@std@@@3@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<CacheEntry,ulong,std::less<CacheEntry>,std::allocator<std::pair<CacheEntry const,ulong>>,0>>::clear(void)
0x180061c58  jmp     short loc_180061C5F
0x180061c5a  test    r12d, r12d
0x180061c5d  jnz     short loc_180061CC2
0x180061c5f  mov     rdx, [r15+8]; lpValueName
0x180061c63  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180061c68  call    cs:__imp_RegDeleteValueW
0x180061c6e  mov     ebx, eax
0x180061c70  cmp     eax, 2
0x180061c73  jnz     short loc_180061C7C
0x180061c75  xor     ebx, ebx
0x180061c77  jmp     loc_180061DEE
0x180061c7c  test    eax, eax
0x180061c7e  jz      loc_180061DEE
0x180061c84  mov     rcx, cs:WPP_GLOBAL_Control
0x180061c8b  cmp     rcx, r13
0x180061c8e  jz      loc_180061E1C
0x180061c94  test    byte ptr [rcx+1Ch], 10h
0x180061c98  jz      loc_180061DF5
0x180061c9e  cmp     byte ptr [rcx+19h], 2
0x180061ca2  jb      loc_180061DF5
0x180061ca8  mov     edx, 12h
0x180061cad  mov     dword ptr [rsp+0A8h+lpData], eax
0x180061cb1  mov     r9d, [r15]
0x180061cb4  mov     rcx, [rcx+10h]
0x180061cb8  call    WPP_SF_Ld
0x180061cbd  jmp     loc_180061DEE
0x180061cc2  xorps   xmm0, xmm0
0x180061cc5  xor     eax, eax
0x180061cc7  movups  xmmword ptr [rsp+0A8h+var_48], xmm0
0x180061ccc  mov     [rsp+0A8h+var_38], rax
0x180061cd1  mov     edx, r12d
0x180061cd4  lea     rcx, [rsp+0A8h+var_48]
0x180061cd9  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180061cde  nop
0x180061cdf  xor     r9d, r9d
0x180061ce2  mov     rbx, [rbx]
0x180061ce5  mov     rbx, [rbx]
0x180061ce8  mov     [rsp+0A8h+var_78], rbx
0x180061ced  cmp     byte ptr [rbx+19h], 0
0x180061cf1  jnz     short loc_180061D67
0x180061cf3  movzx   esi, word ptr [rbx+1Ch]
0x180061cf7  movzx   r14d, word ptr [rbx+3Eh]
0x180061cfc  mov     rax, [rsp+0A8h+var_48]
0x180061d01  mov     [r9+rax], sil
0x180061d05  lea     edi, [r9+1]
0x180061d09  mov     r8d, esi; Size
0x180061d0c  lea     rdx, [rbx+1Eh]; Src
0x180061d10  mov     ecx, edi
0x180061d12  add     rcx, [rsp+0A8h+var_48]; void *
0x180061d17  call    memcpy_0
0x180061d1c  lea     edx, [rdi+rsi]
0x180061d1f  mov     rax, [rsp+0A8h+var_48]
0x180061d24  mov     [rdx+rax], r14w
0x180061d29  lea     edi, [rdx+2]
0x180061d2c  mov     r8d, r14d; Size
0x180061d2f  lea     rdx, [rbx+40h]; Src
0x180061d33  mov     ecx, edi
0x180061d35  add     rcx, [rsp+0A8h+var_48]; void *
0x180061d3a  call    memcpy_0
0x180061d3f  lea     r8d, [rdi+r14]
0x180061d43  mov     ecx, [rbx+244h]
0x180061d49  mov     rax, [rsp+0A8h+var_48]
0x180061d4e  mov     [r8+rax], ecx
0x180061d52  lea     r9d, [r8+4]
0x180061d56  lea     rcx, [rsp+0A8h+var_78]
0x180061d5b  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUCacheEntry@@K@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<CacheEntry const,ulong>>>,std::_Iterator_base0>::operator++(void)
0x180061d60  mov     rbx, [rsp+0A8h+var_78]
0x180061d65  jmp     short loc_180061CED
0x180061d67  cmp     r9d, r12d
0x180061d6a  jz      short loc_180061D71
0x180061d6c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180061d71  mov     rax, [rsp+0A8h+var_48]
0x180061d76  mov     [rsp+0A8h+cbData], r12d; cbData
0x180061d7b  mov     [rsp+0A8h+lpData], rax; lpData
0x180061d80  mov     r9d, 3; dwType
0x180061d86  xor     r8d, r8d; Reserved
0x180061d89  mov     rdx, [r15+8]; lpValueName
0x180061d8d  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180061d92  call    cs:__imp_RegSetValueExW
0x180061d98  mov     ebx, eax
0x180061d9a  test    eax, eax
0x180061d9c  jz      short loc_180061DCC
0x180061d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180061da5  cmp     rcx, r13
0x180061da8  jz      short loc_180061DCC
0x180061daa  test    byte ptr [rcx+1Ch], 10h
0x180061dae  jz      short loc_180061DCC
0x180061db0  cmp     byte ptr [rcx+19h], 2
0x180061db4  jb      short loc_180061DCC
0x180061db6  mov     edx, 13h
0x180061dbb  mov     dword ptr [rsp+0A8h+lpData], eax
0x180061dbf  mov     r9d, [r15]
0x180061dc2  mov     rcx, [rcx+10h]
0x180061dc6  call    WPP_SF_Ld
0x180061dcb  nop
0x180061dcc  lea     rcx, [rsp+0A8h+var_48]
0x180061dd1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180061dd6  nop
0x180061dd7  jmp     short loc_180061DE9
0x180061dd9  lea     r13, WPP_GLOBAL_Control
0x180061de0  mov     ebx, dword ptr [rsp+0A8h+var_78]
0x180061de4  mov     r15, [rsp+0A8h+var_60]
0x180061de9  mov     rdi, [rsp+0A8h+var_68]
0x180061dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180061df5  cmp     rcx, r13
0x180061df8  jz      short loc_180061E1C
0x180061dfa  test    byte ptr [rcx+1Ch], 10h
0x180061dfe  jz      short loc_180061E1C
0x180061e00  cmp     byte ptr [rcx+19h], 5
0x180061e04  jb      short loc_180061E1C
0x180061e06  mov     edx, 14h
0x180061e0b  mov     dword ptr [rsp+0A8h+lpData], ebx
0x180061e0f  mov     r9d, [r15]
0x180061e12  mov     rcx, [rcx+10h]
0x180061e16  call    WPP_SF_Ld
0x180061e1b  nop
0x180061e1c  test    rdi, rdi
0x180061e1f  jz      short loc_180061E2A
0x180061e21  mov     rcx, rdi; lpCriticalSection
0x180061e24  call    cs:__imp_LeaveCriticalSection
0x180061e2a  mov     rcx, [rsp+0A8h+var_30]
0x180061e2f  xor     rcx, rsp; StackCookie
0x180061e32  call    __security_check_cookie
0x180061e37  lea     r11, [rsp+0A8h+var_28]
0x180061e3f  mov     rbx, [r11+40h]
0x180061e43  mov     rsi, [r11+48h]
0x180061e47  mov     rsp, r11
0x180061e4a  pop     r15
0x180061e4c  pop     r14
0x180061e4e  pop     r13
0x180061e50  pop     r12
0x180061e52  pop     rdi
0x180061e53  retn
```
