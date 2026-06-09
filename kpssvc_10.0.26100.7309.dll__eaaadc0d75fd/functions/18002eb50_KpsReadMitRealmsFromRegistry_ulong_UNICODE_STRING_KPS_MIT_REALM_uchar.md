# KpsReadMitRealmsFromRegistry(ulong (*)(_UNICODE_STRING *,_KPS_MIT_REALM *),uchar)

- ea: `0x18002eb50`
- end: `0x18002ed1b`
- name: `?KpsReadMitRealmsFromRegistry@@YAKP6AKPEAU_UNICODE_STRING@@PEAU_KPS_MIT_REALM@@@ZE@Z`
- size: `459`
- prototype: `__int64 __fastcall(unsigned int (*)(struct _UNICODE_STRING *, struct _KPS_MIT_REALM *), unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002ea8c`

## callees

- `0x18001ae38`
- `0x180029c48`
- `0x18002dbb8`
- `0x18002eb50`
- `0x18002ed24`
- `0x18002f194`
- `0x18002f738`
- `0x18002f7d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ecd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ecd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ebe5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ebe5`
- `ntdll!RtlFreeUnicodeString` at `0x18002ec08`
- `ntdll!RtlFreeUnicodeString` at `0x18002ecbd`
- `ntdll!RtlFreeUnicodeString` at `0x18002ec08`
- `ntdll!RtlFreeUnicodeString` at `0x18002ecbd`

## pseudocode

```c
__int64 __fastcall KpsReadMitRealmsFromRegistry(
        unsigned int (*a1)(struct _UNICODE_STRING *, struct _KPS_MIT_REALM *),
        unsigned __int8 a2)
{
  int v2; // edi
  const WCHAR *v3; // rdx
  unsigned int v4; // ebx
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // r8d
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-40h] BYREF
  _OWORD v11[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v12; // [rsp+60h] [rbp-10h]
  HKEY hKey; // [rsp+90h] [rbp+20h] BYREF
  unsigned int v14; // [rsp+98h] [rbp+28h] BYREF

  hKey = 0;
  v14 = 0;
  v2 = a2;
  v12 = 0;
  UnicodeString = 0;
  memset(v11, 0, sizeof(v11));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids, a2);
  v3 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System\\Kerberos\\MITRealms";
  if ( !(_BYTE)v2 )
    v3 = L"System\\CurrentControlSet\\Control\\Lsa\\Kerberos\\Domains";
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  if ( !v4 )
  {
    while ( 1 )
    {
      KpsFreeMitRealm((struct _KPS_MIT_REALM *)v11);
      RtlFreeUnicodeString(&UnicodeString);
      UnicodeString = 0;
      if ( (_BYTE)v2 )
        v5 = KpsReadNextMitRealmFromGroupPolicy(hKey, &UnicodeString, (struct _KPS_MIT_REALM *)v11, &v14);
      else
        v5 = KpsReadNextMitRealmFromLocalPolicy(hKey, &UnicodeString, (struct _KPS_MIT_REALM *)v11, &v14);
      v4 = v5;
      if ( v5 == 259 )
      {
        v4 = 0;
        goto LABEL_20;
      }
      if ( v5 )
        break;
      v4 = KpsKerbAddMitRealm(&UnicodeString, (struct _KPS_MIT_REALM *)v11);
      if ( v4 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_DZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, v8, v4, (__int64)&UnicodeString);
        goto LABEL_20;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, v5, v2);
  }
LABEL_20:
  KpsFreeMitRealm((struct _KPS_MIT_REALM *)v11);
  RtlFreeUnicodeString(&UnicodeString);
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18002eb50  mov     [rsp-18h+arg_10], rbx
0x18002eb55  mov     [rsp-18h+hKey], rcx
0x18002eb5a  push    rbp
0x18002eb5b  push    rsi
0x18002eb5c  push    rdi
0x18002eb5d  mov     rbp, rsp
0x18002eb60  sub     rsp, 70h
0x18002eb64  and     [rbp+hKey], 0
0x18002eb69  xorps   xmm1, xmm1
0x18002eb6c  and     [rbp+arg_8], 0
0x18002eb70  xorps   xmm0, xmm0
0x18002eb73  xor     eax, eax
0x18002eb75  movzx   edi, dl
0x18002eb78  mov     [rbp+var_10], rax
0x18002eb7c  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x18002eb80  movups  [rbp+var_30], xmm1
0x18002eb84  movups  [rbp+var_20], xmm1
0x18002eb88  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb8f  lea     rsi, WPP_GLOBAL_Control
0x18002eb96  cmp     rcx, rsi
0x18002eb99  jz      short loc_18002EBB7
0x18002eb9b  test    byte ptr [rcx+1Ch], 20h
0x18002eb9f  jz      short loc_18002EBB7
0x18002eba1  mov     rcx, [rcx+10h]
0x18002eba5  lea     edx, [rax+35h]
0x18002eba8  mov     r9d, edi
0x18002ebab  lea     r8, WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids
0x18002ebb2  call    WPP_SF_D
0x18002ebb7  lea     rax, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Lsa"...
0x18002ebbe  test    dil, dil
0x18002ebc1  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002ebc8  mov     r9d, 20019h; samDesired
0x18002ebce  cmovz   rdx, rax; lpSubKey
0x18002ebd2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ebd9  lea     rax, [rbp+hKey]
0x18002ebdd  xor     r8d, r8d; ulOptions
0x18002ebe0  mov     [rsp+70h+phkResult], rax; phkResult
0x18002ebe5  call    cs:__imp_RegOpenKeyExW
0x18002ebec  nop     dword ptr [rax+rax+00h]
0x18002ebf1  mov     ebx, eax
0x18002ebf3  test    eax, eax
0x18002ebf5  jnz     loc_18002ECB0
0x18002ebfb  lea     rcx, [rbp+var_30]; struct _KPS_MIT_REALM *
0x18002ebff  call    ?KpsFreeMitRealm@@YAXPEAU_KPS_MIT_REALM@@@Z; KpsFreeMitRealm(_KPS_MIT_REALM *)
0x18002ec04  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18002ec08  call    cs:__imp_RtlFreeUnicodeString
0x18002ec0f  nop     dword ptr [rax+rax+00h]
0x18002ec14  mov     rcx, [rbp+hKey]; hKey
0x18002ec18  xorps   xmm0, xmm0
0x18002ec1b  lea     r9, [rbp+arg_8]; unsigned int *
0x18002ec1f  lea     r8, [rbp+var_30]; struct _KPS_MIT_REALM *
0x18002ec23  lea     rdx, [rbp+UnicodeString]; struct _UNICODE_STRING *
0x18002ec27  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x18002ec2b  test    dil, dil
0x18002ec2e  jz      short loc_18002EC37
0x18002ec30  call    ?KpsReadNextMitRealmFromGroupPolicy@@YAKPEAUHKEY__@@PEAU_UNICODE_STRING@@PEAU_KPS_MIT_REALM@@PEAK@Z; KpsReadNextMitRealmFromGroupPolicy(HKEY__ *,_UNICODE_STRING *,_KPS_MIT_REALM *,ulong *)
0x18002ec35  jmp     short loc_18002EC3C
0x18002ec37  call    ?KpsReadNextMitRealmFromLocalPolicy@@YAKPEAUHKEY__@@PEAU_UNICODE_STRING@@PEAU_KPS_MIT_REALM@@PEAK@Z; KpsReadNextMitRealmFromLocalPolicy(HKEY__ *,_UNICODE_STRING *,_KPS_MIT_REALM *,ulong *)
0x18002ec3c  mov     ebx, eax
0x18002ec3e  cmp     eax, 103h
0x18002ec43  jz      short loc_18002ECAE
0x18002ec45  test    eax, eax
0x18002ec47  jnz     short loc_18002EC8A
0x18002ec49  lea     rdx, [rbp+var_30]; struct _KPS_MIT_REALM *
0x18002ec4d  lea     rcx, [rbp+UnicodeString]; struct _UNICODE_STRING *
0x18002ec51  call    ?KpsKerbAddMitRealm@@YAKPEAU_UNICODE_STRING@@PEAU_KPS_MIT_REALM@@@Z; KpsKerbAddMitRealm(_UNICODE_STRING *,_KPS_MIT_REALM *)
0x18002ec56  mov     ebx, eax
0x18002ec58  test    eax, eax
0x18002ec5a  jz      short loc_18002EBFB
0x18002ec5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec63  cmp     rcx, rsi
0x18002ec66  jz      short loc_18002ECB0
0x18002ec68  test    byte ptr [rcx+1Ch], 1
0x18002ec6c  jz      short loc_18002ECB0
0x18002ec6e  mov     rcx, [rcx+10h]
0x18002ec72  lea     rax, [rbp+UnicodeString]
0x18002ec76  mov     edx, 37h ; '7'
0x18002ec7b  mov     [rsp+70h+phkResult], rax
0x18002ec80  mov     r9d, ebx
0x18002ec83  call    WPP_SF_DZ
0x18002ec88  jmp     short loc_18002ECB0
0x18002ec8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec91  cmp     rcx, rsi
0x18002ec94  jz      short loc_18002ECB0
0x18002ec96  test    byte ptr [rcx+1Ch], 1
0x18002ec9a  jz      short loc_18002ECB0
0x18002ec9c  mov     rcx, [rcx+10h]
0x18002eca0  mov     r9d, ebx
0x18002eca3  mov     dword ptr [rsp+70h+phkResult], edi
0x18002eca7  call    WPP_SF_Dd
0x18002ecac  jmp     short loc_18002ECB0
0x18002ecae  xor     ebx, ebx
0x18002ecb0  lea     rcx, [rbp+var_30]; struct _KPS_MIT_REALM *
0x18002ecb4  call    ?KpsFreeMitRealm@@YAXPEAU_KPS_MIT_REALM@@@Z; KpsFreeMitRealm(_KPS_MIT_REALM *)
0x18002ecb9  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18002ecbd  call    cs:__imp_RtlFreeUnicodeString
0x18002ecc4  nop     dword ptr [rax+rax+00h]
0x18002ecc9  mov     rcx, [rbp+hKey]; hKey
0x18002eccd  test    rcx, rcx
0x18002ecd0  jz      short loc_18002ECDE
0x18002ecd2  call    cs:__imp_RegCloseKey
0x18002ecd9  nop     dword ptr [rax+rax+00h]
0x18002ecde  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ece5  cmp     rcx, rsi
0x18002ece8  jz      short loc_18002ED08
0x18002ecea  test    byte ptr [rcx+1Ch], 20h
0x18002ecee  jz      short loc_18002ED08
0x18002ecf0  mov     rcx, [rcx+10h]
0x18002ecf4  lea     r8, WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids
0x18002ecfb  mov     edx, 38h ; '8'
0x18002ed00  mov     r9d, ebx
0x18002ed03  call    WPP_SF_D
0x18002ed08  mov     eax, ebx
0x18002ed0a  mov     rbx, [rsp+70h+arg_10]
0x18002ed12  add     rsp, 70h
0x18002ed16  pop     rdi
0x18002ed17  pop     rsi
0x18002ed18  pop     rbp
0x18002ed19  retn
```
