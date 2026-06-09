# WwanProfileHistorian::LoadHistory(void)

- ea: `0x1800579ec`
- end: `0x180057c6e`
- name: `?LoadHistory@WwanProfileHistorian@@QEAAJXZ`
- size: `642`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002d880`

## callees

- `0x180002efc`
- `0x180055448`
- `0x180055470`
- `0x1800579ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057c28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057c28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057a3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057a3c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180057b1a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180057b85`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180057b1a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180057b85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057ad7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057ad7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057c1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057c1f`
- `MobileNetworking!GetPersistentRegPath` at `0x180057a86`
- `MobileNetworking!GetPersistentRegPath` at `0x180057a86`

## pseudocode

```c
__int64 __fastcall WwanProfileHistorian::LoadHistory(LPCRITICAL_SECTION lpCriticalSection)
{
  signed int v2; // r8d
  int PersistentRegPath; // eax
  LSTATUS v4; // eax
  LSTATUS ValueW; // eax
  LSTATUS v6; // eax
  int v7; // edi
  signed int v8; // r8d
  signed int OwningThread; // edx
  __int64 v10; // rax
  DWORD pcbData; // [rsp+70h] [rbp+30h] BYREF
  int v13; // [rsp+78h] [rbp+38h] BYREF
  HKEY hkey; // [rsp+80h] [rbp+40h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_59efe20e95083d54484ef368743a0c87_Traceguids);
  hkey = 0;
  pcbData = 0;
  EnterCriticalSection(lpCriticalSection);
  if ( LOBYTE(lpCriticalSection[1].DebugInfo) )
  {
    if ( WwanProfileHistorian::m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot )
      goto LABEL_10;
    v13 = 260;
    PersistentRegPath = GetPersistentRegPath(
                          0,
                          L"MobileBroadbandAccounts\\Data",
                          &v13,
                          &WwanProfileHistorian::m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot);
    v2 = PersistentRegPath;
    if ( PersistentRegPath > 0 )
      v2 = (unsigned __int16)PersistentRegPath | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_10:
      memset_0(*(void **)&lpCriticalSection[1].LockCount, 0, 0x14F0u);
      LODWORD(lpCriticalSection[1].OwningThread) = 0;
      v4 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             &WwanProfileHistorian::m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot,
             0,
             0x20019u,
             &hkey);
      v2 = v4;
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x80070000;
      if ( v2 >= 0 )
      {
        ValueW = RegGetValueW(hkey, 0, L"ProfileHistory", 8u, 0, 0, &pcbData);
        v2 = ValueW;
        if ( ValueW > 0 )
          v2 = (unsigned __int16)ValueW | 0x80070000;
        if ( v2 >= 0 )
        {
          if ( pcbData <= 0x14F0 && pcbData == 536 * (pcbData / 0x218uLL) )
          {
            if ( pcbData )
            {
              v6 = RegGetValueW(
                     hkey,
                     0,
                     L"ProfileHistory",
                     0x20000008u,
                     0,
                     *(PVOID *)&lpCriticalSection[1].LockCount,
                     &pcbData);
              v2 = v6;
              if ( v6 > 0 )
                v2 = (unsigned __int16)v6 | 0x80070000;
            }
          }
          else
          {
            v2 = -2147024883;
          }
        }
      }
    }
  }
  else
  {
    v2 = -2147019873;
  }
  v7 = 0;
  if ( v2 != -2147024894 )
    v7 = v2;
  if ( v7 < 0 )
  {
    LODWORD(lpCriticalSection[1].OwningThread) = 0;
    OwningThread = 0;
  }
  else
  {
    v8 = 0;
    OwningThread = pcbData / 0x218;
    LODWORD(lpCriticalSection[1].OwningThread) = pcbData / 0x218;
    if ( OwningThread > 0 )
    {
      do
      {
        v10 = v8++;
        *(_WORD *)(536 * v10 + *(_QWORD *)&lpCriticalSection[1].LockCount + 510) = 0;
        OwningThread = (signed int)lpCriticalSection[1].OwningThread;
      }
      while ( v8 < OwningThread );
    }
  }
  memset_0((void *)(*(_QWORD *)&lpCriticalSection[1].LockCount + 536LL * OwningThread), 0, 536LL * (10 - OwningThread));
  if ( hkey )
    RegCloseKey(hkey);
  LeaveCriticalSection(lpCriticalSection);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_59efe20e95083d54484ef368743a0c87_Traceguids,
      (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800579ec  mov     [rsp-28h+arg_18], rbx
0x1800579f1  push    rbp
0x1800579f2  push    rsi
0x1800579f3  push    rdi
0x1800579f4  push    r12
0x1800579f6  push    r15
0x1800579f8  mov     rbp, rsp
0x1800579fb  sub     rsp, 40h
0x1800579ff  mov     rbx, rcx
0x180057a02  mov     rcx, cs:WPP_GLOBAL_Control
0x180057a09  lea     r12, WPP_GLOBAL_Control
0x180057a10  cmp     rcx, r12
0x180057a13  jz      short loc_180057A30
0x180057a15  test    byte ptr [rcx+1Ch], 10h
0x180057a19  jz      short loc_180057A30
0x180057a1b  mov     rcx, [rcx+10h]
0x180057a1f  lea     r8, WPP_59efe20e95083d54484ef368743a0c87_Traceguids
0x180057a26  mov     edx, 0Fh
0x180057a2b  call    WPP_SF_
0x180057a30  xor     esi, esi
0x180057a32  mov     rcx, rbx; lpCriticalSection
0x180057a35  mov     [rbp+hkey], rsi
0x180057a39  mov     [rbp+arg_0], esi
0x180057a3c  call    cs:__imp_EnterCriticalSection
0x180057a42  mov     r15, 0F4898D5F85BB3951h
0x180057a4c  cmp     [rbx+28h], sil
0x180057a50  jnz     short loc_180057A5D
0x180057a52  mov     r8d, 8007139Fh
0x180057a58  jmp     loc_180057BA1
0x180057a5d  cmp     cs:?m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot@WwanProfileHistorian@@0PAGA, si; ushort near * WwanProfileHistorian::m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot
0x180057a64  mov     edi, 80070000h
0x180057a69  jnz     short loc_180057AA3
0x180057a6b  lea     r9, ?m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot@WwanProfileHistorian@@0PAGA; ushort near * WwanProfileHistorian::m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot
0x180057a72  mov     [rbp+arg_8], 104h
0x180057a79  lea     r8, [rbp+arg_8]
0x180057a7d  xor     ecx, ecx
0x180057a7f  lea     rdx, aMobilebroadban; "MobileBroadbandAccounts\\Data"
0x180057a86  call    cs:__imp_GetPersistentRegPath
0x180057a8c  mov     r8d, eax
0x180057a8f  test    eax, eax
0x180057a91  jle     short loc_180057A9A
0x180057a93  movzx   r8d, ax
0x180057a97  or      r8d, edi
0x180057a9a  test    r8d, r8d
0x180057a9d  js      loc_180057BA1
0x180057aa3  mov     rcx, [rbx+30h]; void *
0x180057aa7  xor     edx, edx; Val
0x180057aa9  mov     r8d, 14F0h; Size
0x180057aaf  call    memset_0
0x180057ab4  lea     rax, [rbp+hkey]
0x180057ab8  mov     [rbx+38h], esi
0x180057abb  mov     r9d, 20019h; samDesired
0x180057ac1  mov     [rsp+40h+phkResult], rax; phkResult
0x180057ac6  xor     r8d, r8d; ulOptions
0x180057ac9  lea     rdx, ?m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot@WwanProfileHistorian@@0PAGA; lpSubKey
0x180057ad0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180057ad7  call    cs:__imp_RegOpenKeyExW
0x180057add  mov     r8d, eax
0x180057ae0  test    eax, eax
0x180057ae2  jle     short loc_180057AEB
0x180057ae4  movzx   r8d, ax
0x180057ae8  or      r8d, edi
0x180057aeb  test    r8d, r8d
0x180057aee  js      loc_180057BA1
0x180057af4  mov     rcx, [rbp+hkey]; hkey
0x180057af8  lea     rax, [rbp+arg_0]
0x180057afc  mov     [rsp+40h+pcbData], rax; pcbData
0x180057b01  lea     r8, aProfilehistory; "ProfileHistory"
0x180057b08  mov     [rsp+40h+pvData], rsi; pvData
0x180057b0d  mov     r9d, 8; dwFlags
0x180057b13  xor     edx, edx; lpSubKey
0x180057b15  mov     [rsp+40h+phkResult], rsi; pdwType
0x180057b1a  call    cs:__imp_RegGetValueW
0x180057b20  mov     r8d, eax
0x180057b23  test    eax, eax
0x180057b25  jle     short loc_180057B2E
0x180057b27  movzx   r8d, ax
0x180057b2b  or      r8d, edi
0x180057b2e  test    r8d, r8d
0x180057b31  js      short loc_180057BA1
0x180057b33  mov     r9d, [rbp+arg_0]
0x180057b37  cmp     r9d, 14F0h
0x180057b3e  ja      short loc_180057B9B
0x180057b40  mov     rax, r15
0x180057b43  mul     r9
0x180057b46  shr     rdx, 9
0x180057b4a  imul    rax, rdx, 218h
0x180057b51  cmp     r9, rax
0x180057b54  jnz     short loc_180057B9B
0x180057b56  test    r9d, r9d
0x180057b59  jz      short loc_180057BA1
0x180057b5b  mov     rcx, [rbp+hkey]; hkey
0x180057b5f  lea     rax, [rbp+arg_0]
0x180057b63  mov     [rsp+40h+pcbData], rax; pcbData
0x180057b68  lea     r8, aProfilehistory; "ProfileHistory"
0x180057b6f  mov     rax, [rbx+30h]
0x180057b73  mov     r9d, 20000008h; dwFlags
0x180057b79  mov     [rsp+40h+pvData], rax; pvData
0x180057b7e  xor     edx, edx; lpSubKey
0x180057b80  mov     [rsp+40h+phkResult], rsi; pdwType
0x180057b85  call    cs:__imp_RegGetValueW
0x180057b8b  mov     r8d, eax
0x180057b8e  test    eax, eax
0x180057b90  jle     short loc_180057BA1
0x180057b92  movzx   r8d, ax
0x180057b96  or      r8d, edi
0x180057b99  jmp     short loc_180057BA1
0x180057b9b  mov     r8d, 8007000Dh
0x180057ba1  cmp     r8d, 80070002h
0x180057ba8  mov     edi, esi
0x180057baa  cmovnz  edi, r8d
0x180057bae  test    edi, edi
0x180057bb0  js      short loc_180057BEC
0x180057bb2  mov     ecx, [rbp+arg_0]
0x180057bb5  mov     rax, r15
0x180057bb8  mul     rcx
0x180057bbb  mov     r8d, esi
0x180057bbe  shr     rdx, 9
0x180057bc2  mov     [rbx+38h], edx
0x180057bc5  test    edx, edx
0x180057bc7  jle     short loc_180057BF1
0x180057bc9  mov     rcx, [rbx+30h]
0x180057bcd  movsxd  rax, r8d
0x180057bd0  inc     r8d
0x180057bd3  imul    rdx, rax, 218h
0x180057bda  mov     [rdx+rcx+1FEh], si
0x180057be2  mov     edx, [rbx+38h]
0x180057be5  cmp     r8d, edx
0x180057be8  jl      short loc_180057BC9
0x180057bea  jmp     short loc_180057BF1
0x180057bec  mov     [rbx+38h], esi
0x180057bef  mov     edx, esi
0x180057bf1  mov     eax, 0Ah
0x180057bf6  sub     eax, edx
0x180057bf8  cdqe
0x180057bfa  imul    r8, rax, 218h; Size
0x180057c01  movsxd  rax, edx
0x180057c04  xor     edx, edx; Val
0x180057c06  imul    rcx, rax, 218h
0x180057c0d  add     rcx, [rbx+30h]; void *
0x180057c11  call    memset_0
0x180057c16  mov     rcx, [rbp+hkey]; hKey
0x180057c1a  test    rcx, rcx
0x180057c1d  jz      short loc_180057C25
0x180057c1f  call    cs:__imp_RegCloseKey
0x180057c25  mov     rcx, rbx; lpCriticalSection
0x180057c28  call    cs:__imp_LeaveCriticalSection
0x180057c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180057c35  cmp     rcx, r12
0x180057c38  jz      short loc_180057C58
0x180057c3a  test    byte ptr [rcx+1Ch], 10h
0x180057c3e  jz      short loc_180057C58
0x180057c40  mov     rcx, [rcx+10h]
0x180057c44  lea     r8, WPP_59efe20e95083d54484ef368743a0c87_Traceguids
0x180057c4b  mov     edx, 10h
0x180057c50  mov     r9d, edi
0x180057c53  call    WPP_SF_d
0x180057c58  mov     rbx, [rsp+40h+arg_18]
0x180057c60  mov     eax, edi
0x180057c62  add     rsp, 40h
0x180057c66  pop     r15
0x180057c68  pop     r12
0x180057c6a  pop     rdi
0x180057c6b  pop     rsi
0x180057c6c  pop     rbp
0x180057c6d  retn
```
