# KdcPwReadRegistry(_KDCPW_REG *)

- ea: `0x180005978`
- end: `0x180005be6`
- name: `?KdcPwReadRegistry@@YAXPEAU_KDCPW_REG@@@Z`
- size: `622`
- prototype: `void __fastcall(struct _KDCPW_REG *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004390`
- `0x180007620`

## callees

- `0x180001630`
- `0x180005978`
- `0x180009384`
- `0x1800093c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005a6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005a6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005ad1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005ad1`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180005b14`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180005b14`

## string_xrefs

- `0x180005a60`: `System\CurrentControlSet\Services\Kdc`

## pseudocode

```c
void __fastcall KdcPwReadRegistry(struct _KDCPW_REG *a1)
{
  _DWORD *v2; // rsi
  HKEY v3; // rdx
  unsigned int v4; // eax
  unsigned int v5; // edi
  _BYTE *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  _QWORD *v12; // rcx
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  const wchar_t *v18; // [rsp+60h] [rbp-A0h]
  struct _KDCPW_REG *v19; // [rsp+68h] [rbp-98h]
  int v20; // [rsp+70h] [rbp-90h]
  int *v21; // [rsp+78h] [rbp-88h]
  int v22; // [rsp+80h] [rbp-80h]
  __int64 v23; // [rsp+88h] [rbp-78h]
  int v24; // [rsp+90h] [rbp-70h]
  const wchar_t *v25; // [rsp+98h] [rbp-68h]
  char *v26; // [rsp+A0h] [rbp-60h]
  int v27; // [rsp+A8h] [rbp-58h]
  int *v28; // [rsp+B0h] [rbp-50h]
  int v29; // [rsp+B8h] [rbp-48h]
  __int128 v30; // [rsp+C0h] [rbp-40h]
  __int128 v31; // [rsp+D0h] [rbp-30h]
  __int128 v32; // [rsp+E0h] [rbp-20h]
  __int64 v33; // [rsp+F0h] [rbp-10h]

  v13 = 4096;
  v14 = 0;
  v16 = 0;
  v17 = 32;
  v18 = L"IterationCount";
  v2 = (_DWORD *)((char *)a1 + 4);
  v19 = a1;
  v20 = 4;
  v21 = &v13;
  v22 = 4;
  v25 = L"AESKeyFailureNotContinueable";
  v27 = 4;
  v28 = &v14;
  *(_QWORD *)a1 = 0;
  v29 = 4;
  v3 = KdcPwGlobalRootKey;
  v23 = 0;
  v24 = 32;
  v26 = (char *)a1 + 4;
  v33 = 0;
  hKey = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  if ( KdcPwGlobalRootKey )
    goto LABEL_16;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Kdc", 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_7d4a502f09a63302b64cc8824afd6777_Traceguids, v4);
  }
  else if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&KdcPwGlobalRootKey, (signed __int64)hKey, 0) )
  {
    hKey = 0;
  }
  v6 = WPP_GLOBAL_Control;
LABEL_9:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || (v6[28] & 2) == 0 )
      goto LABEL_21;
    v7 = 11;
    v8 = v5;
LABEL_20:
    WPP_SF_D(*((_QWORD *)v6 + 2), v7, &WPP_7d4a502f09a63302b64cc8824afd6777_Traceguids, v8);
LABEL_21:
    *(_DWORD *)a1 = v13;
    *v2 = v14;
LABEL_26:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  v3 = KdcPwGlobalRootKey;
LABEL_16:
  v9 = RtlQueryRegistryValuesEx(0x40000000, v3, &v16, 0, 0);
  if ( v9 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_21;
    v7 = 12;
    v8 = v9;
    goto LABEL_20;
  }
  if ( *(_DWORD *)a1 )
    goto LABEL_26;
  *(_DWORD *)a1 = 1;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, 1);
    goto LABEL_26;
  }
LABEL_27:
  if ( v12 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v12 + 28) & 4) != 0 )
    {
      WPP_SF_D(v12[2], 14, &WPP_7d4a502f09a63302b64cc8824afd6777_Traceguids, *(unsigned int *)a1);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 )
      WPP_SF_D(v12[2], 15, &WPP_7d4a502f09a63302b64cc8824afd6777_Traceguids, (unsigned int)*v2);
  }
}

```

## disassembly

```asm
0x180005978  push    rbp
0x18000597a  push    rbx
0x18000597b  push    rsi
0x18000597c  push    rdi
0x18000597d  push    r12
0x18000597f  push    r15
0x180005981  lea     rbp, [rsp-18h]
0x180005986  sub     rsp, 118h
0x18000598d  mov     rax, cs:__security_cookie
0x180005994  xor     rax, rsp
0x180005997  mov     [rbp+40h+var_40], rax
0x18000599b  mov     rbx, rcx
0x18000599e  mov     [rsp+140h+var_110], 1000h
0x1800059a6  mov     ecx, 20h ; ' '
0x1800059ab  mov     [rsp+140h+var_10C], 0
0x1800059b3  xorps   xmm0, xmm0
0x1800059b6  mov     [rsp+140h+var_F0], 0
0x1800059bf  lea     rax, aIterationcount; "IterationCount"
0x1800059c6  mov     [rsp+140h+var_E8], ecx
0x1800059ca  mov     [rsp+140h+var_E0], rax
0x1800059cf  lea     rsi, [rbx+4]
0x1800059d3  lea     edx, [rcx-1Ch]
0x1800059d6  mov     [rsp+140h+var_D8], rbx
0x1800059db  lea     rax, [rsp+140h+var_110]
0x1800059e0  mov     [rsp+140h+var_D0], edx
0x1800059e4  mov     [rsp+140h+var_C8], rax
0x1800059e9  lea     r15, WPP_GLOBAL_Control
0x1800059f0  lea     rax, aAeskeyfailuren; "AESKeyFailureNotContinueable"
0x1800059f7  mov     [rbp+40h+var_C0], edx
0x1800059fa  mov     [rbp+40h+var_A8], rax
0x1800059fe  lea     r12, WPP_7d4a502f09a63302b64cc8824afd6777_Traceguids
0x180005a05  lea     rax, [rsp+140h+var_10C]
0x180005a0a  mov     [rbp+40h+var_98], edx
0x180005a0d  mov     [rbp+40h+var_90], rax
0x180005a11  xor     eax, eax
0x180005a13  mov     [rbx], rax
0x180005a16  mov     [rbp+40h+var_88], edx
0x180005a19  mov     rdx, cs:?KdcPwGlobalRootKey@@3PEAUHKEY__@@EA; HKEY__ * KdcPwGlobalRootKey
0x180005a20  mov     [rbp+40h+var_B8], 0
0x180005a28  mov     [rbp+40h+var_B0], ecx
0x180005a2b  mov     [rbp+40h+var_A0], rsi
0x180005a2f  mov     [rbp+40h+var_50], rax
0x180005a33  mov     [rsp+140h+hKey], rax
0x180005a38  movups  [rbp+40h+var_80], xmm0
0x180005a3c  movups  [rbp+40h+var_70], xmm0
0x180005a40  movups  [rbp+40h+var_60], xmm0
0x180005a44  test    rdx, rdx
0x180005a47  jnz     loc_180005AFE
0x180005a4d  lea     rax, [rsp+140h+hKey]
0x180005a52  mov     r9d, 20019h; samDesired
0x180005a58  xor     r8d, r8d; ulOptions
0x180005a5b  mov     [rsp+140h+phkResult], rax; phkResult
0x180005a60  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Kd"...
0x180005a67  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005a6e  call    cs:__imp_RegOpenKeyExW
0x180005a74  mov     edi, eax
0x180005a76  test    eax, eax
0x180005a78  jz      short loc_180005AA2
0x180005a7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a81  cmp     rcx, r15
0x180005a84  jz      short loc_180005AC4
0x180005a86  test    byte ptr [rcx+1Ch], 1
0x180005a8a  jz      short loc_180005AC4
0x180005a8c  mov     rcx, [rcx+10h]
0x180005a90  mov     edx, 0Ah
0x180005a95  mov     r9d, eax
0x180005a98  mov     r8, r12
0x180005a9b  call    WPP_SF_D
0x180005aa0  jmp     short loc_180005ABD
0x180005aa2  mov     rcx, [rsp+140h+hKey]
0x180005aa7  xor     eax, eax
0x180005aa9  lock cmpxchg cs:?KdcPwGlobalRootKey@@3PEAUHKEY__@@EA, rcx; HKEY__ * KdcPwGlobalRootKey
0x180005ab2  jnz     short loc_180005ABD
0x180005ab4  mov     [rsp+140h+hKey], 0
0x180005abd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ac4  mov     rax, [rsp+140h+hKey]
0x180005ac9  test    rax, rax
0x180005acc  jz      short loc_180005ADE
0x180005ace  mov     rcx, rax; hKey
0x180005ad1  call    cs:__imp_RegCloseKey
0x180005ad7  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ade  test    edi, edi
0x180005ae0  jz      short loc_180005AF7
0x180005ae2  cmp     rcx, r15
0x180005ae5  jz      short loc_180005B44
0x180005ae7  test    byte ptr [rcx+1Ch], 2
0x180005aeb  jz      short loc_180005B44
0x180005aed  mov     edx, 0Bh
0x180005af2  mov     r9d, edi
0x180005af5  jmp     short loc_180005B38
0x180005af7  mov     rdx, cs:?KdcPwGlobalRootKey@@3PEAUHKEY__@@EA; HKEY__ * KdcPwGlobalRootKey
0x180005afe  xor     r9d, r9d
0x180005b01  mov     [rsp+140h+phkResult], 0
0x180005b0a  lea     r8, [rsp+140h+var_F0]
0x180005b0f  mov     ecx, 40000000h
0x180005b14  call    cs:__imp_RtlQueryRegistryValuesEx
0x180005b1a  test    eax, eax
0x180005b1c  jz      short loc_180005B52
0x180005b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b25  cmp     rcx, r15
0x180005b28  jz      short loc_180005B44
0x180005b2a  test    byte ptr [rcx+1Ch], 2
0x180005b2e  jz      short loc_180005B44
0x180005b30  mov     edx, 0Ch
0x180005b35  mov     r9d, eax
0x180005b38  mov     rcx, [rcx+10h]
0x180005b3c  mov     r8, r12
0x180005b3f  call    WPP_SF_D
0x180005b44  mov     eax, [rsp+140h+var_110]
0x180005b48  mov     [rbx], eax
0x180005b4a  mov     eax, [rsp+140h+var_10C]
0x180005b4e  mov     [rsi], eax
0x180005b50  jmp     short loc_180005B7E
0x180005b52  cmp     dword ptr [rbx], 0
0x180005b55  jnz     short loc_180005B7E
0x180005b57  mov     dword ptr [rbx], 1
0x180005b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b64  cmp     rcx, r15
0x180005b67  jz      short loc_180005BCA
0x180005b69  test    byte ptr [rcx+1Ch], 2
0x180005b6d  jz      short loc_180005B85
0x180005b6f  mov     rcx, [rcx+10h]
0x180005b73  mov     r9d, 1
0x180005b79  call    WPP_SF_d
0x180005b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b85  cmp     rcx, r15
0x180005b88  jz      short loc_180005BCA
0x180005b8a  test    byte ptr [rcx+1Ch], 4
0x180005b8e  jz      short loc_180005BAB
0x180005b90  mov     r9d, [rbx]
0x180005b93  mov     edx, 0Eh
0x180005b98  mov     rcx, [rcx+10h]
0x180005b9c  mov     r8, r12
0x180005b9f  call    WPP_SF_D
0x180005ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bab  cmp     rcx, r15
0x180005bae  jz      short loc_180005BCA
0x180005bb0  test    byte ptr [rcx+1Ch], 4
0x180005bb4  jz      short loc_180005BCA
0x180005bb6  mov     r9d, [rsi]
0x180005bb9  mov     edx, 0Fh
0x180005bbe  mov     rcx, [rcx+10h]
0x180005bc2  mov     r8, r12
0x180005bc5  call    WPP_SF_D
0x180005bca  mov     rcx, [rbp+40h+var_40]
0x180005bce  xor     rcx, rsp; StackCookie
0x180005bd1  call    __security_check_cookie
0x180005bd6  add     rsp, 118h
0x180005bdd  pop     r15
0x180005bdf  pop     r12
0x180005be1  pop     rdi
0x180005be2  pop     rsi
0x180005be3  pop     rbx
0x180005be4  pop     rbp
0x180005be5  retn
```
