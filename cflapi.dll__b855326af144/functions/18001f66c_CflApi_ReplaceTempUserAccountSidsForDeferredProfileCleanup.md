# CflApi::ReplaceTempUserAccountSidsForDeferredProfileCleanup

- ea: `0x18001f66c`
- end: `0x18001f891`
- name: `CflApi::ReplaceTempUserAccountSidsForDeferredProfileCleanup`
- size: `549`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001c500`

## callees

- `0x1800067c4`
- `0x1800071b4`
- `0x18001b128`
- `0x18001f66c`
- `0x18001f948`
- `0x18002222c`
- `0x180025cb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f6cd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f6cd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f810`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f810`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001f71b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001f71b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f6fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f870`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f6fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f870`

## string_xrefs

- `0x18001f710`: `TempUserAccountSids`
- `0x18001f805`: `TempUserAccountSids`
- `0x18001f6de`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001f744`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001f821`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001f83d`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CflApi::ReplaceTempUserAccountSidsForDeferredProfileCleanup(_QWORD *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  _QWORD *v5; // rcx
  int v6; // eax
  bool v7; // dl
  unsigned int v8; // esi
  __int64 v9; // r13
  unsigned __int16 *v10; // rdi
  unsigned int v11; // r14d
  _QWORD *v12; // r11
  _QWORD *v13; // r15
  const unsigned __int16 *v14; // r8
  int v15; // eax
  __int64 v16; // r11
  unsigned int v17; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-50h]
  BYTE *lpData[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v21; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  HKEY hKey; // [rsp+A8h] [rbp+38h] BYREF

  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ProfileCleanupData",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  if ( v2 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x424,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
           (const char *)v2,
           dwOptions);
LABEL_3:
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
  v5 = (_QWORD *)*a1;
  if ( *a1 == a1[1] )
  {
    v6 = RegDeleteValueW(hKey, L"TempUserAccountSids");
    v7 = (v6 & 0xFFFFFFFD) != 0;
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    if ( v7 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x42B,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)(unsigned int)v6,
        dwOptions);
    goto LABEL_25;
  }
  *(_OWORD *)lpData = 0;
  v21 = 0;
  v8 = 1;
  do
  {
    v9 = v8 + *((_DWORD *)v5 + 4);
    v8 = v9 + 1;
    v5 += 4;
  }
  while ( v5 != (_QWORD *)a1[1] );
  std::vector<unsigned short>::resize(lpData, v8);
  v10 = (unsigned __int16 *)lpData[0];
  v11 = v9 + 1;
  v12 = (_QWORD *)*a1;
  v13 = (_QWORD *)a1[1];
  if ( (_QWORD *)*a1 != v13 )
  {
    while ( 1 )
    {
      v14 = v12[3] <= 7u ? (const unsigned __int16 *)v12 : (const unsigned __int16 *)*v12;
      v15 = StringCchCopyW(v10, v11, v14);
      v3 = v15;
      if ( v15 < 0 )
        break;
      v10 += *(_QWORD *)(v16 + 16) + 1;
      v11 += -1 - *(_DWORD *)(v16 + 16);
      v12 = (_QWORD *)(v16 + 32);
      if ( v12 == v13 )
      {
        v10 = (unsigned __int16 *)lpData[0];
        goto LABEL_20;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x442,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)v15,
      dwOptions);
    goto LABEL_23;
  }
LABEL_20:
  v10[v9] = 0;
  v17 = RegSetValueExW(hKey, L"TempUserAccountSids", 0, 7u, lpData[0], 2 * v8);
  if ( v17 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x453,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
           (const char *)v17,
           dwOptionsa);
LABEL_23:
    std::vector<unsigned short>::~vector<unsigned short>(lpData);
    goto LABEL_3;
  }
  std::vector<unsigned short>::~vector<unsigned short>(lpData);
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18001f66c  mov     r11, rsp
0x18001f66f  mov     [r11+8], rbx
0x18001f673  mov     [r11+18h], rsi
0x18001f677  push    rbp
0x18001f678  push    rdi
0x18001f679  push    r13
0x18001f67b  push    r14
0x18001f67d  push    r15
0x18001f67f  mov     rbp, rsp
0x18001f682  sub     rsp, 70h
0x18001f686  mov     rbx, rcx
0x18001f689  mov     [rbp+hKey], 0
0x18001f691  mov     qword ptr [r11-58h], 0
0x18001f699  lea     rax, [rbp+hKey]
0x18001f69d  mov     [r11-60h], rax
0x18001f6a1  mov     qword ptr [r11-68h], 0
0x18001f6a9  mov     [rsp+70h+samDesired], 2; samDesired
0x18001f6b1  mov     [rsp+70h+dwOptions], 0; int
0x18001f6b9  xor     r9d, r9d; lpClass
0x18001f6bc  xor     r8d, r8d; Reserved
0x18001f6bf  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001f6c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f6cd  call    cs:__imp_RegCreateKeyExW
0x18001f6d3  test    eax, eax
0x18001f6d5  jz      short loc_18001F707
0x18001f6d7  mov     rcx, [rbp+28h]; this
0x18001f6db  mov     r9d, eax; char *
0x18001f6de  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001f6e5  mov     edx, 424h; void *
0x18001f6ea  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001f6ef  mov     ebx, eax
0x18001f6f1  mov     rcx, [rbp+hKey]; hKey
0x18001f6f5  test    rcx, rcx
0x18001f6f8  jz      short loc_18001F700
0x18001f6fa  call    cs:__imp_RegCloseKey
0x18001f700  mov     eax, ebx
0x18001f702  jmp     loc_18001F878
0x18001f707  mov     rcx, [rbx]
0x18001f70a  cmp     rcx, [rbx+8]
0x18001f70e  jnz     short loc_18001F75A
0x18001f710  lea     rdx, ValueName; "TempUserAccountSids"
0x18001f717  mov     rcx, [rbp+hKey]; hKey
0x18001f71b  call    cs:__imp_RegDeleteValueW
0x18001f721  test    eax, 0FFFFFFFDh
0x18001f726  setnz   dl
0x18001f729  test    eax, eax
0x18001f72b  jle     short loc_18001F735
0x18001f72d  movzx   eax, ax
0x18001f730  or      eax, 80070000h
0x18001f735  mov     rcx, [rbp+28h]; this
0x18001f739  test    dl, dl
0x18001f73b  jz      loc_18001F867
0x18001f741  mov     r9d, eax; char *
0x18001f744  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001f74b  mov     edx, 42Bh; void *
0x18001f750  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f755  jmp     loc_18001F867
0x18001f75a  xorps   xmm0, xmm0
0x18001f75d  movdqu  xmmword ptr [rbp+lpData], xmm0
0x18001f762  mov     [rbp+var_10], 0
0x18001f76a  mov     esi, 1
0x18001f76f  mov     r13d, [rcx+10h]
0x18001f773  add     r13d, esi
0x18001f776  lea     esi, [r13+1]
0x18001f77a  add     rcx, 20h ; ' '
0x18001f77e  cmp     rcx, [rbx+8]
0x18001f782  jnz     short loc_18001F76F
0x18001f784  mov     edx, esi
0x18001f786  lea     rcx, [rbp+lpData]
0x18001f78a  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18001f78f  mov     rdi, [rbp+lpData]
0x18001f793  mov     r14d, esi
0x18001f796  mov     r11, [rbx]
0x18001f799  mov     r15, [rbx+8]
0x18001f79d  cmp     r11, r15
0x18001f7a0  jz      short loc_18001F7E5
0x18001f7a2  cmp     qword ptr [r11+18h], 7
0x18001f7a7  jbe     short loc_18001F7AE
0x18001f7a9  mov     r8, [r11]
0x18001f7ac  jmp     short loc_18001F7B1
0x18001f7ae  mov     r8, r11; unsigned __int16 *
0x18001f7b1  mov     edx, r14d; unsigned __int64
0x18001f7b4  mov     rcx, rdi; unsigned __int16 *
0x18001f7b7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f7bc  mov     ebx, eax
0x18001f7be  test    eax, eax
0x18001f7c0  js      short loc_18001F836
0x18001f7c2  mov     rax, [r11+10h]
0x18001f7c6  lea     rdi, [rdi+rax*2]
0x18001f7ca  add     rdi, 2
0x18001f7ce  or      eax, 0FFFFFFFFh
0x18001f7d1  sub     eax, [r11+10h]
0x18001f7d5  add     r14d, eax
0x18001f7d8  add     r11, 20h ; ' '
0x18001f7dc  cmp     r11, r15
0x18001f7df  jnz     short loc_18001F7A2
0x18001f7e1  mov     rdi, [rbp+lpData]
0x18001f7e5  xor     eax, eax
0x18001f7e7  mov     [rdi+r13*2], ax
0x18001f7ec  mov     rdx, [rbp+lpData]
0x18001f7f0  lea     eax, [rsi+rsi]
0x18001f7f3  mov     [rsp+70h+samDesired], eax; cbData
0x18001f7f7  mov     qword ptr [rsp+70h+dwOptions], rdx; unsigned int
0x18001f7fc  mov     r9d, 7; dwType
0x18001f802  xor     r8d, r8d; Reserved
0x18001f805  lea     rdx, ValueName; "TempUserAccountSids"
0x18001f80c  mov     rcx, [rbp+hKey]; hKey
0x18001f810  call    cs:__imp_RegSetValueExW
0x18001f816  test    eax, eax
0x18001f818  jz      short loc_18001F85D
0x18001f81a  mov     rcx, [rbp+28h]; this
0x18001f81e  mov     r9d, eax; char *
0x18001f821  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001f828  mov     edx, 453h; void *
0x18001f82d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001f832  mov     ebx, eax
0x18001f834  jmp     short loc_18001F84F
0x18001f836  mov     rcx, [rbp+28h]; this
0x18001f83a  mov     r9d, ebx; char *
0x18001f83d  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001f844  mov     edx, 442h; void *
0x18001f849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f84e  nop
0x18001f84f  lea     rcx, [rbp+lpData]
0x18001f853  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18001f858  jmp     loc_18001F6F1
0x18001f85d  lea     rcx, [rbp+lpData]
0x18001f861  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18001f866  nop
0x18001f867  mov     rcx, [rbp+hKey]; hKey
0x18001f86b  test    rcx, rcx
0x18001f86e  jz      short loc_18001F876
0x18001f870  call    cs:__imp_RegCloseKey
0x18001f876  xor     eax, eax
0x18001f878  lea     r11, [rsp+70h+var_s0]
0x18001f87d  mov     rbx, [r11+30h]
0x18001f881  mov     rsi, [r11+40h]
0x18001f885  mov     rsp, r11
0x18001f888  pop     r15
0x18001f88a  pop     r14
0x18001f88c  pop     r13
0x18001f88e  pop     rdi
0x18001f88f  pop     rbp
0x18001f890  retn
```
