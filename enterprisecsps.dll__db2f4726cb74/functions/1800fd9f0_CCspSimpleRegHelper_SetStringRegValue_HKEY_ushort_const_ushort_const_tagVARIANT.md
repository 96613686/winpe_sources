# CCspSimpleRegHelper::SetStringRegValue(HKEY__ *,ushort const *,ushort const *,tagVARIANT)

- ea: `0x1800fd9f0`
- end: `0x1800fdb74`
- name: `?SetStringRegValue@CCspSimpleRegHelper@@CAJPEAUHKEY__@@PEBG1UtagVARIANT@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, VARIANTARG *pvarSrc)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800fdb7c`

## callees

- `0x180015e90`
- `0x18003a05c`
- `0x1800fd9f0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800fda2e`
- `OLEAUT32!__imp_VariantInit` at `0x1800fda2e`
- `OLEAUT32!__imp_VariantClear` at `0x1800fdb57`
- `OLEAUT32!__imp_VariantClear` at `0x1800fdb57`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800fdab7`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800fdab7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fdb21`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fdb21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fdb47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fdb47`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fda71`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fda71`

## pseudocode

```c
__int64 __fastcall CCspSimpleRegHelper::SetStringRegValue(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        VARIANTARG *pvarSrc)
{
  LSTATUS v8; // eax
  int v9; // ebx
  bool v10; // cc
  const BYTE *v11; // r11
  unsigned int v13; // [rsp+50h] [rbp-30h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v15; // [rsp+60h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-18h] BYREF

  hKeya = 0;
  v15 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v8 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKeya, 0);
  v9 = v8;
  v10 = v8 <= 0;
  if ( v8 )
    goto LABEL_2;
  if ( !pvarSrc->vt )
  {
    v9 = -2147024809;
    goto LABEL_13;
  }
  v13 = 4;
  v9 = VariantChangeType(&pvarg, pvarSrc, 0, 8u);
  if ( v9 >= 0 )
  {
    v9 = StringCbLengthW(pvarg.bstrVal, 0xFFFFFFFE, &v15);
    if ( v9 >= 0 )
    {
      v9 = ULongLongToULong(v15, &v13);
      if ( v9 >= 0 )
      {
        if ( v13 + 2 < v13 )
        {
          v9 = -2147024362;
          goto LABEL_13;
        }
        v8 = RegSetValueExW(hKeya, lpValueName, 0, 1u, v11, v13 + 2);
        v9 = v8;
        v10 = v8 <= 0;
        if ( v8 )
        {
LABEL_2:
          if ( !v10 )
            v9 = (unsigned __int16)v8 | 0x80070000;
        }
      }
    }
  }
LABEL_13:
  if ( hKeya )
    RegCloseKey(hKeya);
  VariantClear(&pvarg);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800fd9f0  push    rbp
0x1800fd9f2  push    rbx
0x1800fd9f3  push    rsi
0x1800fd9f4  push    rdi
0x1800fd9f5  push    r14
0x1800fd9f7  mov     rbp, rsp
0x1800fd9fa  sub     rsp, 80h
0x1800fda01  mov     rdi, rcx
0x1800fda04  mov     [rbp+hKey], 0
0x1800fda0c  xorps   xmm0, xmm0
0x1800fda0f  mov     [rbp+var_20], 0
0x1800fda17  xor     eax, eax
0x1800fda19  lea     rcx, [rbp+pvarg]; pvarg
0x1800fda1d  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800fda21  mov     qword ptr [rbp+pvarg+10h], rax
0x1800fda25  mov     rsi, r9
0x1800fda28  mov     r14, r8
0x1800fda2b  mov     rbx, rdx
0x1800fda2e  call    cs:__imp_VariantInit
0x1800fda35  nop     dword ptr [rax+rax+00h]
0x1800fda3a  mov     [rsp+80h+lpdwDisposition], 0; lpdwDisposition
0x1800fda43  lea     rax, [rbp+hKey]
0x1800fda47  mov     [rsp+80h+phkResult], rax; phkResult
0x1800fda4c  xor     r9d, r9d; lpClass
0x1800fda4f  mov     [rsp+80h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800fda58  xor     r8d, r8d; Reserved
0x1800fda5b  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x1800fda63  mov     rdx, rbx; lpSubKey
0x1800fda66  mov     rcx, rdi; hKey
0x1800fda69  mov     [rsp+80h+dwOptions], 0; dwOptions
0x1800fda71  call    cs:__imp_RegCreateKeyExW
0x1800fda78  nop     dword ptr [rax+rax+00h]
0x1800fda7d  mov     ebx, eax
0x1800fda7f  test    eax, eax
0x1800fda81  jz      short loc_1800FDA97
0x1800fda83  jle     loc_1800FDB3E
0x1800fda89  movzx   ebx, ax
0x1800fda8c  or      ebx, 80070000h
0x1800fda92  jmp     loc_1800FDB3E
0x1800fda97  xor     eax, eax
0x1800fda99  cmp     ax, [rsi]
0x1800fda9c  jz      loc_1800FDB39
0x1800fdaa2  lea     r9d, [rax+8]; vt
0x1800fdaa6  mov     [rbp+var_30], 4
0x1800fdaad  xor     r8d, r8d; wFlags
0x1800fdab0  lea     rcx, [rbp+pvarg]; pvargDest
0x1800fdab4  mov     rdx, rsi; pvarSrc
0x1800fdab7  call    cs:__imp_VariantChangeType
0x1800fdabe  nop     dword ptr [rax+rax+00h]
0x1800fdac3  mov     ebx, eax
0x1800fdac5  test    eax, eax
0x1800fdac7  js      short loc_1800FDB3E
0x1800fdac9  mov     r11, qword ptr [rbp+pvarg+8]
0x1800fdacd  lea     r8, [rbp+var_20]; unsigned __int64 *
0x1800fdad1  mov     rcx, r11; unsigned __int16 *
0x1800fdad4  mov     edx, 0FFFFFFFEh; unsigned __int64
0x1800fdad9  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800fdade  mov     ebx, eax
0x1800fdae0  test    eax, eax
0x1800fdae2  js      short loc_1800FDB3E
0x1800fdae4  mov     rcx, [rbp+var_20]; unsigned __int64
0x1800fdae8  lea     rdx, [rbp+var_30]; unsigned int *
0x1800fdaec  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800fdaf1  mov     ebx, eax
0x1800fdaf3  test    eax, eax
0x1800fdaf5  js      short loc_1800FDB3E
0x1800fdaf7  mov     eax, [rbp+var_30]
0x1800fdafa  lea     ecx, [rax+2]
0x1800fdafd  cmp     ecx, eax
0x1800fdaff  jnb     short loc_1800FDB08
0x1800fdb01  mov     ebx, 80070216h
0x1800fdb06  jmp     short loc_1800FDB3E
0x1800fdb08  mov     [rsp+80h+samDesired], ecx; cbData
0x1800fdb0c  mov     r9d, 1; dwType
0x1800fdb12  mov     rcx, [rbp+hKey]; hKey
0x1800fdb16  xor     r8d, r8d; Reserved
0x1800fdb19  mov     rdx, r14; lpValueName
0x1800fdb1c  mov     qword ptr [rsp+80h+dwOptions], r11; lpData
0x1800fdb21  call    cs:__imp_RegSetValueExW
0x1800fdb28  nop     dword ptr [rax+rax+00h]
0x1800fdb2d  mov     ebx, eax
0x1800fdb2f  test    eax, eax
0x1800fdb31  jnz     loc_1800FDA83
0x1800fdb37  jmp     short loc_1800FDB3E
0x1800fdb39  mov     ebx, 80070057h
0x1800fdb3e  mov     rcx, [rbp+hKey]; hKey
0x1800fdb42  test    rcx, rcx
0x1800fdb45  jz      short loc_1800FDB53
0x1800fdb47  call    cs:__imp_RegCloseKey
0x1800fdb4e  nop     dword ptr [rax+rax+00h]
0x1800fdb53  lea     rcx, [rbp+pvarg]; pvarg
0x1800fdb57  call    cs:__imp_VariantClear
0x1800fdb5e  nop     dword ptr [rax+rax+00h]
0x1800fdb63  mov     eax, ebx
0x1800fdb65  add     rsp, 80h
0x1800fdb6c  pop     r14
0x1800fdb6e  pop     rdi
0x1800fdb6f  pop     rsi
0x1800fdb70  pop     rbx
0x1800fdb71  pop     rbp
0x1800fdb72  retn
```
