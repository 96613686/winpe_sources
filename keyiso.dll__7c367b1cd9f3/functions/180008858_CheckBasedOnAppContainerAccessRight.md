# CheckBasedOnAppContainerAccessRight

- ea: `0x180008858`
- end: `0x18000894d`
- name: `CheckBasedOnAppContainerAccessRight`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008954`

## callees

- `0x180008858`
- `0x180008bf0`
- `0x1800172ac`
- `0x18001739c`
- `0x1800174f0`

## string_xrefs

- `0x180008909`: `windowsHelloCredentialAccess`

## pseudocode

```c
signed int __fastcall CheckBasedOnAppContainerAccessRight(void *a1, int a2, int a3, wchar_t *a4, int a5)
{
  signed int result; // eax
  int v10; // [rsp+30h] [rbp-50h] BYREF
  int v11; // [rsp+34h] [rbp-4Ch]
  const wchar_t *v12; // [rsp+40h] [rbp-40h]
  __int64 v13; // [rsp+48h] [rbp-38h]
  const wchar_t *v14; // [rsp+50h] [rbp-30h]
  __int64 v15; // [rsp+58h] [rbp-28h]
  const wchar_t *v16; // [rsp+60h] [rbp-20h]
  int v17; // [rsp+68h] [rbp-18h]
  int v18; // [rsp+6Ch] [rbp-14h]
  const wchar_t *v19; // [rsp+70h] [rbp-10h]
  __int64 v20; // [rsp+78h] [rbp-8h]

  v10 = 1;
  v11 = 0;
  result = IsAppContainer(a1, &v10);
  if ( result >= 0 )
  {
    if ( v10 )
    {
      if ( a2 )
      {
        return CheckAppKeyStorageKeyAccessRight(a1);
      }
      else if ( (int)GetDomainRelevantKeyCharacteristics(a4) >= 0 )
      {
        v12 = L"networkingVpnProvider";
        v18 = 3932160;
        v14 = L"ID_CAP_NETWORKING_VPN_PROVIDER";
        v20 = 3932160;
        v16 = L"sharedUserCertificates";
        v13 = 0x100000;
        v19 = L"windowsHelloCredentialAccess";
        v15 = 0x100000;
        v17 = 0x20000;
        return CheckAppAccessRightBasedOnCapability((_DWORD)a1, (a3 | v11) & 0x3E0000 | 0x10000u, (_DWORD)a4, a5);
      }
      else
      {
        return -2146893808;
      }
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008858  push    rbp
0x18000885a  push    rbx
0x18000885b  push    rsi
0x18000885c  push    rdi
0x18000885d  push    r14
0x18000885f  mov     rbp, rsp
0x180008862  sub     rsp, 80h
0x180008869  mov     esi, edx
0x18000886b  mov     [rbp+var_50], 1
0x180008872  lea     rdx, [rbp+var_50]
0x180008876  mov     [rbp+var_4C], 0
0x18000887d  mov     rdi, r9
0x180008880  mov     r14d, r8d
0x180008883  mov     rbx, rcx
0x180008886  call    IsAppContainer
0x18000888b  test    eax, eax
0x18000888d  js      loc_18000893F
0x180008893  cmp     [rbp+var_50], 0
0x180008897  jnz     short loc_1800088A0
0x180008899  xor     eax, eax
0x18000889b  jmp     loc_18000893F
0x1800088a0  test    esi, esi
0x1800088a2  jz      short loc_1800088B1
0x1800088a4  mov     rcx, rbx
0x1800088a7  call    CheckAppKeyStorageKeyAccessRight
0x1800088ac  jmp     loc_18000893F
0x1800088b1  lea     rdx, [rbp+var_4C]
0x1800088b5  mov     rcx, rdi; String1
0x1800088b8  call    GetDomainRelevantKeyCharacteristics
0x1800088bd  test    eax, eax
0x1800088bf  jns     short loc_1800088C8
0x1800088c1  mov     eax, 80090010h
0x1800088c6  jmp     short loc_18000893F
0x1800088c8  mov     edx, [rbp+var_4C]
0x1800088cb  lea     rax, aNetworkingvpnp; "networkingVpnProvider"
0x1800088d2  mov     r9, [rbp+arg_20]
0x1800088d6  or      edx, r14d
0x1800088d9  mov     [rbp+var_40], rax
0x1800088dd  mov     ecx, 3C0000h
0x1800088e2  lea     rax, aIdCapNetworkin; "ID_CAP_NETWORKING_VPN_PROVIDER"
0x1800088e9  mov     [rbp+var_14], ecx
0x1800088ec  mov     [rbp+var_30], rax
0x1800088f0  and     edx, 3E0000h
0x1800088f6  lea     rax, aSharedusercert; "sharedUserCertificates"
0x1800088fd  mov     [rbp+var_8], rcx
0x180008901  mov     [rbp+var_20], rax
0x180008905  bts     edx, 10h
0x180008909  lea     rax, aWindowshellocr; "windowsHelloCredentialAccess"
0x180008910  mov     [rbp+var_38], 100000h
0x180008918  mov     [rbp+var_10], rax
0x18000891c  mov     r8, rdi
0x18000891f  lea     rax, [rbp+var_40]
0x180008923  mov     [rbp+var_28], 100000h
0x18000892b  mov     rcx, rbx
0x18000892e  mov     [rsp+80h+var_58], rax
0x180008933  mov     [rbp+var_18], 20000h
0x18000893a  call    CheckAppAccessRightBasedOnCapability
0x18000893f  add     rsp, 80h
0x180008946  pop     r14
0x180008948  pop     rdi
0x180008949  pop     rsi
0x18000894a  pop     rbx
0x18000894b  pop     rbp
0x18000894c  retn
```
