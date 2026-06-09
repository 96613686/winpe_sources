# CflApi::AddTempUserAccountSidForDeferredProfileCleanup

- ea: `0x18001ba30`
- end: `0x18001bcf5`
- name: `CflApi::AddTempUserAccountSidForDeferredProfileCleanup`
- size: `709`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001c500`

## callees

- `0x1800067c4`
- `0x180012a3c`
- `0x180014ce0`
- `0x1800154ac`
- `0x18001b128`
- `0x18001ba30`
- `0x18001f948`
- `0x180025cb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001bb22`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001bbce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001bb22`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001bbce`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ba81`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ba81`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bcb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bcb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001baae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bce2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001baae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bce2`

## string_xrefs

- `0x18001bb15`: `TempUserAccountSids`
- `0x18001bbc1`: `TempUserAccountSids`
- `0x18001bca6`: `TempUserAccountSids`
- `0x18001ba92`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001bb54`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001bbfe`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
__int64 __fastcall CflApi::AddTempUserAccountSidForDeferredProfileCleanup(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  __int64 v5; // rax
  LSTATUS ValueW; // eax
  __int64 v7; // rdx
  unsigned int v8; // eax
  char *v9; // rdx
  __int64 v10; // rdx
  unsigned int dwOptions; // [rsp+28h] [rbp-29h]
  int dwOptionsa; // [rsp+28h] [rbp-29h]
  unsigned int dwOptionsb; // [rsp+28h] [rbp-29h]
  HKEY hKey; // [rsp+58h] [rbp+7h] BYREF
  PVOID pvData[2]; // [rsp+60h] [rbp+Fh] BYREF
  PVOID v16; // [rsp+70h] [rbp+1Fh]
  __int64 v17; // [rsp+78h] [rbp+27h] BYREF
  __int64 v18; // [rsp+80h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]
  DWORD pdwType; // [rsp+C0h] [rbp+6Fh] BYREF
  DWORD pcbData; // [rsp+C8h] [rbp+77h] BYREF
  DWORD v22; // [rsp+D0h] [rbp+7Fh] BYREF

  v22 = 0;
  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ProfileCleanupData",
         0,
         0,
         0,
         3u,
         0,
         &hKey,
         &v22);
  if ( v2 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x46C,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
           (const char *)v2,
           dwOptions);
LABEL_3:
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
  *(_OWORD *)pvData = 0;
  v16 = 0;
  pcbData = 0;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a1 + 2 * v5) );
  std::vector<unsigned short>::vector<unsigned short>(&v17, a1, a1 + 2 * (v5 + 1));
  if ( v22 != 2 )
  {
LABEL_26:
    v9 = (char *)pvData[1];
    goto LABEL_27;
  }
  pdwType = 0;
  ValueW = RegGetValueW(hKey, 0, L"TempUserAccountSids", 0x20u, &pdwType, 0, &pcbData);
  v3 = ValueW;
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      if ( ValueW > 0 )
        v3 = (unsigned __int16)ValueW | 0x80070000;
      if ( (v3 & 0x80000000) == 0 )
        goto LABEL_16;
      v7 = 1152;
      goto LABEL_15;
    }
    goto LABEL_26;
  }
  if ( pdwType != 7 )
  {
    v3 = -2147024809;
    v7 = 1157;
    goto LABEL_15;
  }
  if ( !pcbData || (pcbData & 1) != 0 )
  {
    v3 = -2147024872;
    v7 = 1160;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)v3,
      dwOptionsa);
LABEL_16:
    std::vector<unsigned short>::~vector<unsigned short>(&v17);
    std::vector<unsigned short>::~vector<unsigned short>(pvData);
    goto LABEL_3;
  }
  std::vector<unsigned short>::resize(pvData, (unsigned __int64)pcbData >> 1);
  v8 = RegGetValueW(hKey, 0, L"TempUserAccountSids", 0x20u, 0, pvData[0], &pcbData);
  if ( v8 )
  {
    v10 = 1171;
LABEL_23:
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v10,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
           (const char *)v8,
           dwOptionsb);
    goto LABEL_16;
  }
  std::vector<unsigned short>::resize(pvData, (unsigned __int64)pcbData >> 1);
  v9 = (char *)pvData[1] - 2;
  pvData[1] = (char *)pvData[1] - 2;
  pcbData -= 2;
LABEL_27:
  std::vector<unsigned short>::_Insert_counted_range<unsigned short *>(pvData, v9, v17, (v18 - v17) >> 1);
  LOWORD(pdwType) = 0;
  if ( pvData[1] == v16 )
  {
    std::vector<unsigned short>::_Emplace_reallocate<unsigned short>(pvData, pvData[1], &pdwType);
  }
  else
  {
    *(_WORD *)pvData[1] = 0;
    pvData[1] = (char *)pvData[1] + 2;
  }
  pcbData += 2 * (((v18 - v17) >> 1) + 1);
  v8 = RegSetValueExW(hKey, L"TempUserAccountSids", 0, 7u, (const BYTE *)pvData[0], pcbData);
  if ( v8 )
  {
    v10 = 1194;
    goto LABEL_23;
  }
  std::vector<unsigned short>::~vector<unsigned short>(&v17);
  std::vector<unsigned short>::~vector<unsigned short>(pvData);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18001ba30  mov     r11, rsp
0x18001ba33  push    rbp
0x18001ba34  push    rbx
0x18001ba35  push    rdi
0x18001ba36  lea     rbp, [r11-5Fh]
0x18001ba3a  sub     rsp, 90h
0x18001ba41  mov     rbx, rcx
0x18001ba44  xor     edi, edi
0x18001ba46  mov     [rbp+57h+arg_18], edi
0x18001ba49  mov     [rbp+57h+hKey], rdi
0x18001ba4d  lea     rax, [rbp+57h+arg_18]
0x18001ba51  mov     [r11-68h], rax
0x18001ba55  lea     rax, [rbp+57h+hKey]
0x18001ba59  mov     [r11-70h], rax
0x18001ba5d  mov     [r11-78h], rdi
0x18001ba61  mov     [rsp+0A0h+samDesired], 3; samDesired
0x18001ba69  mov     [rsp+0A0h+dwOptions], edi; unsigned int
0x18001ba6d  xor     r9d, r9d; lpClass
0x18001ba70  xor     r8d, r8d; Reserved
0x18001ba73  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001ba7a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ba81  call    cs:__imp_RegCreateKeyExW
0x18001ba87  test    eax, eax
0x18001ba89  jz      short loc_18001BABB
0x18001ba8b  mov     rcx, [rbp+5Fh]; this
0x18001ba8f  mov     r9d, eax; char *
0x18001ba92  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001ba99  mov     edx, 46Ch; void *
0x18001ba9e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001baa3  mov     ebx, eax
0x18001baa5  mov     rcx, [rbp+57h+hKey]; hKey
0x18001baa9  test    rcx, rcx
0x18001baac  jz      short loc_18001BAB4
0x18001baae  call    cs:__imp_RegCloseKey
0x18001bab4  mov     eax, ebx
0x18001bab6  jmp     loc_18001BCEA
0x18001babb  xorps   xmm0, xmm0
0x18001babe  movdqu  xmmword ptr [rbp+57h+pvData], xmm0
0x18001bac3  mov     [rbp+57h+var_38], rdi
0x18001bac7  mov     [rbp+57h+pcbData], edi
0x18001baca  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001bace  inc     rax
0x18001bad1  cmp     [rbx+rax*2], di
0x18001bad5  jnz     short loc_18001BACE
0x18001bad7  inc     rax
0x18001bada  lea     r8, [rbx+rax*2]
0x18001bade  mov     rdx, rbx
0x18001bae1  lea     rcx, [rbp+57h+var_30]
0x18001bae5  call    ??$?0PEBG$0A@@?$vector@GV?$allocator@G@std@@@std@@QEAA@PEBG0AEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(ushort const *,ushort const *,std::allocator<ushort> const &)
0x18001baea  nop
0x18001baeb  cmp     [rbp+57h+arg_18], 2
0x18001baef  jnz     loc_18001BC36
0x18001baf5  mov     [rbp+57h+pdwType], edi
0x18001baf8  lea     rax, [rbp+57h+pcbData]
0x18001bafc  mov     [rsp+30h], rax; pcbData
0x18001bb01  mov     qword ptr [rsp+0A0h+samDesired], rdi; pvData
0x18001bb06  lea     rax, [rbp+57h+pdwType]
0x18001bb0a  mov     qword ptr [rsp+0A0h+dwOptions], rax; int
0x18001bb0f  mov     r9d, 20h ; ' '; dwFlags
0x18001bb15  lea     r8, ValueName; "TempUserAccountSids"
0x18001bb1c  xor     edx, edx; lpSubKey
0x18001bb1e  mov     rcx, [rbp+57h+hKey]; hkey
0x18001bb22  call    cs:__imp_RegGetValueW
0x18001bb28  mov     ebx, eax
0x18001bb2a  test    eax, eax
0x18001bb2c  jz      short loc_18001BB79
0x18001bb2e  cmp     eax, 2
0x18001bb31  jz      loc_18001BC36
0x18001bb37  test    eax, eax
0x18001bb39  jle     short loc_18001BB44
0x18001bb3b  movzx   ebx, ax
0x18001bb3e  or      ebx, 80070000h
0x18001bb44  test    ebx, ebx
0x18001bb46  jns     short loc_18001BB61
0x18001bb48  mov     edx, 480h; void *
0x18001bb4d  mov     rcx, [rbp+5Fh]; this
0x18001bb51  mov     r9d, ebx; char *
0x18001bb54  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001bb5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bb60  nop
0x18001bb61  lea     rcx, [rbp+57h+var_30]
0x18001bb65  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18001bb6a  nop
0x18001bb6b  lea     rcx, [rbp+57h+pvData]
0x18001bb6f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18001bb74  jmp     loc_18001BAA5
0x18001bb79  cmp     [rbp+57h+pdwType], 7
0x18001bb7d  jnz     loc_18001BC27
0x18001bb83  mov     eax, [rbp+57h+pcbData]
0x18001bb86  test    eax, eax
0x18001bb88  jz      loc_18001BC18
0x18001bb8e  test    al, 1
0x18001bb90  jnz     loc_18001BC18
0x18001bb96  mov     edx, eax
0x18001bb98  shr     rdx, 1
0x18001bb9b  lea     rcx, [rbp+57h+pvData]
0x18001bb9f  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18001bba4  mov     rax, [rbp+57h+pvData]
0x18001bba8  lea     rcx, [rbp+57h+pcbData]
0x18001bbac  mov     [rsp+30h], rcx; pcbData
0x18001bbb1  mov     qword ptr [rsp+0A0h+samDesired], rax; pvData
0x18001bbb6  mov     qword ptr [rsp+0A0h+dwOptions], rdi; unsigned int
0x18001bbbb  mov     r9d, 20h ; ' '; dwFlags
0x18001bbc1  lea     r8, ValueName; "TempUserAccountSids"
0x18001bbc8  xor     edx, edx; lpSubKey
0x18001bbca  mov     rcx, [rbp+57h+hKey]; hkey
0x18001bbce  call    cs:__imp_RegGetValueW
0x18001bbd4  test    eax, eax
0x18001bbd6  jnz     short loc_18001BBF9
0x18001bbd8  mov     edx, [rbp+57h+pcbData]
0x18001bbdb  shr     rdx, 1
0x18001bbde  lea     rcx, [rbp+57h+pvData]
0x18001bbe2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18001bbe7  mov     rdx, [rbp+57h+pvData+8]
0x18001bbeb  sub     rdx, 2
0x18001bbef  mov     [rbp+57h+pvData+8], rdx
0x18001bbf3  add     [rbp+57h+pcbData], 0FFFFFFFEh
0x18001bbf7  jmp     short loc_18001BC3A
0x18001bbf9  mov     edx, 493h; void *
0x18001bbfe  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001bc05  mov     r9d, eax; char *
0x18001bc08  mov     rcx, [rbp+5Fh]; this
0x18001bc0c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001bc11  mov     ebx, eax
0x18001bc13  jmp     loc_18001BB61
0x18001bc18  mov     ebx, 80070018h
0x18001bc1d  mov     edx, 488h
0x18001bc22  jmp     loc_18001BB4D
0x18001bc27  mov     ebx, 80070057h
0x18001bc2c  mov     edx, 485h
0x18001bc31  jmp     loc_18001BB4D
0x18001bc36  mov     rdx, [rbp+57h+pvData+8]
0x18001bc3a  mov     r8, [rbp+57h+var_30]
0x18001bc3e  mov     r9, [rbp+57h+var_28]
0x18001bc42  sub     r9, r8
0x18001bc45  sar     r9, 1
0x18001bc48  lea     rcx, [rbp+57h+pvData]
0x18001bc4c  call    ??$_Insert_counted_range@PEAG@?$vector@GV?$allocator@G@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@1@PEAG_K@Z; std::vector<ushort>::_Insert_counted_range<ushort *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,ushort *,unsigned __int64)
0x18001bc51  mov     word ptr [rbp+57h+pdwType], di
0x18001bc55  mov     rdx, [rbp+57h+pvData+8]
0x18001bc59  cmp     rdx, [rbp+57h+var_38]
0x18001bc5d  jz      short loc_18001BC69
0x18001bc5f  mov     [rdx], di
0x18001bc62  add     [rbp+57h+pvData+8], 2
0x18001bc67  jmp     short loc_18001BC76
0x18001bc69  lea     r8, [rbp+57h+pdwType]
0x18001bc6d  lea     rcx, [rbp+57h+pvData]
0x18001bc71  call    ??$_Emplace_reallocate@G@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAG$$QEAG@Z; std::vector<ushort>::_Emplace_reallocate<ushort>(ushort * const,ushort &&)
0x18001bc76  mov     rcx, [rbp+57h+var_28]
0x18001bc7a  sub     rcx, [rbp+57h+var_30]
0x18001bc7e  sar     rcx, 1
0x18001bc81  mov     eax, [rbp+57h+pcbData]
0x18001bc84  lea     ecx, [rcx+1]
0x18001bc87  lea     r8d, [rax+rcx*2]
0x18001bc8b  mov     [rbp+57h+pcbData], r8d
0x18001bc8f  mov     rax, [rbp+57h+pvData]
0x18001bc93  mov     [rsp+0A0h+samDesired], r8d; cbData
0x18001bc98  mov     qword ptr [rsp+0A0h+dwOptions], rax; lpData
0x18001bc9d  mov     r9d, 7; dwType
0x18001bca3  xor     r8d, r8d; Reserved
0x18001bca6  lea     rdx, ValueName; "TempUserAccountSids"
0x18001bcad  mov     rcx, [rbp+57h+hKey]; hKey
0x18001bcb1  call    cs:__imp_RegSetValueExW
0x18001bcb7  test    eax, eax
0x18001bcb9  jz      short loc_18001BCC5
0x18001bcbb  mov     edx, 4AAh
0x18001bcc0  jmp     loc_18001BBFE
0x18001bcc5  lea     rcx, [rbp+57h+var_30]
0x18001bcc9  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18001bcce  nop
0x18001bccf  lea     rcx, [rbp+57h+pvData]
0x18001bcd3  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18001bcd8  nop
0x18001bcd9  mov     rcx, [rbp+57h+hKey]; hKey
0x18001bcdd  test    rcx, rcx
0x18001bce0  jz      short loc_18001BCE8
0x18001bce2  call    cs:__imp_RegCloseKey
0x18001bce8  xor     eax, eax
0x18001bcea  add     rsp, 90h
0x18001bcf1  pop     rdi
0x18001bcf2  pop     rbx
0x18001bcf3  pop     rbp
0x18001bcf4  retn
```
