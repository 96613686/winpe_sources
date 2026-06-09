# CCspSimpleRegHelper::SetDwordRegValue(HKEY__ *,ushort const *,ushort const *,tagVARIANT)

- ea: `0x1800fd8ac`
- end: `0x1800fd9e7`
- name: `?SetDwordRegValue@CCspSimpleRegHelper@@CAJPEAUHKEY__@@PEBG1UtagVARIANT@@@Z`
- size: `315`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, VARIANTARG *pvarSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800fdb7c`

## callees

- `0x1800fd8ac`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800fd8e9`
- `OLEAUT32!__imp_VariantInit` at `0x1800fd8e9`
- `OLEAUT32!__imp_VariantClear` at `0x1800fd9ca`
- `OLEAUT32!__imp_VariantClear` at `0x1800fd9ca`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800fd960`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800fd960`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fd996`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fd996`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fd9ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fd9ba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fd92c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fd92c`

## pseudocode

```c
__int64 __fastcall CCspSimpleRegHelper::SetDwordRegValue(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        VARIANTARG *pvarSrc)
{
  LSTATUS v8; // eax
  int v9; // ebx
  BYTE Data[8]; // [rsp+50h] [rbp-30h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-20h] BYREF

  hKeya = 0;
  *(_DWORD *)Data = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v8 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKeya, 0);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 <= 0 )
      goto LABEL_10;
    goto LABEL_3;
  }
  if ( pvarSrc->vt )
  {
    v9 = VariantChangeType(&pvarg, pvarSrc, 0, 0x13u);
    if ( v9 >= 0 )
    {
      *(_DWORD *)Data = pvarg.lVal;
      v8 = RegSetValueExW(hKeya, lpValueName, 0, 4u, Data, 4u);
      if ( v8 )
      {
        if ( v8 > 0 )
        {
LABEL_3:
          v9 = (unsigned __int16)v8 | 0x80070000;
          goto LABEL_10;
        }
        v9 = v8;
      }
    }
  }
  else
  {
    v9 = -2147024809;
  }
LABEL_10:
  if ( hKeya )
    RegCloseKey(hKeya);
  VariantClear(&pvarg);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800fd8ac  push    rbp
0x1800fd8ae  push    rbx
0x1800fd8af  push    rsi
0x1800fd8b0  push    rdi
0x1800fd8b1  push    r14
0x1800fd8b3  mov     rbp, rsp
0x1800fd8b6  sub     rsp, 80h
0x1800fd8bd  mov     rdi, rcx
0x1800fd8c0  mov     [rbp+hKey], 0
0x1800fd8c8  xorps   xmm0, xmm0
0x1800fd8cb  mov     dword ptr [rbp+Data], 0
0x1800fd8d2  xor     eax, eax
0x1800fd8d4  lea     rcx, [rbp+pvarg]; pvarg
0x1800fd8d8  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800fd8dc  mov     qword ptr [rbp+pvarg+10h], rax
0x1800fd8e0  mov     rsi, r9
0x1800fd8e3  mov     r14, r8
0x1800fd8e6  mov     rbx, rdx
0x1800fd8e9  call    cs:__imp_VariantInit
0x1800fd8f0  nop     dword ptr [rax+rax+00h]
0x1800fd8f5  mov     [rsp+80h+lpdwDisposition], 0; lpdwDisposition
0x1800fd8fe  lea     rax, [rbp+hKey]
0x1800fd902  mov     [rsp+80h+phkResult], rax; phkResult
0x1800fd907  xor     r9d, r9d; lpClass
0x1800fd90a  mov     [rsp+80h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800fd913  xor     r8d, r8d; Reserved
0x1800fd916  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x1800fd91e  mov     rdx, rbx; lpSubKey
0x1800fd921  mov     rcx, rdi; hKey
0x1800fd924  mov     [rsp+80h+dwOptions], 0; dwOptions
0x1800fd92c  call    cs:__imp_RegCreateKeyExW
0x1800fd933  nop     dword ptr [rax+rax+00h]
0x1800fd938  mov     ebx, eax
0x1800fd93a  test    eax, eax
0x1800fd93c  jz      short loc_1800FD94B
0x1800fd93e  jle     short loc_1800FD9B1
0x1800fd940  movzx   ebx, ax
0x1800fd943  or      ebx, 80070000h
0x1800fd949  jmp     short loc_1800FD9B1
0x1800fd94b  xor     eax, eax
0x1800fd94d  cmp     ax, [rsi]
0x1800fd950  jz      short loc_1800FD9AC
0x1800fd952  lea     r9d, [rax+13h]; vt
0x1800fd956  xor     r8d, r8d; wFlags
0x1800fd959  mov     rdx, rsi; pvarSrc
0x1800fd95c  lea     rcx, [rbp+pvarg]; pvargDest
0x1800fd960  call    cs:__imp_VariantChangeType
0x1800fd967  nop     dword ptr [rax+rax+00h]
0x1800fd96c  mov     ebx, eax
0x1800fd96e  test    eax, eax
0x1800fd970  js      short loc_1800FD9B1
0x1800fd972  mov     ecx, dword ptr [rbp+pvarg+8]
0x1800fd975  lea     rax, [rbp+Data]
0x1800fd979  mov     r9d, 4; dwType
0x1800fd97f  mov     dword ptr [rbp+Data], ecx
0x1800fd982  mov     rcx, [rbp+hKey]; hKey
0x1800fd986  xor     r8d, r8d; Reserved
0x1800fd989  mov     [rsp+80h+samDesired], r9d; cbData
0x1800fd98e  mov     rdx, r14; lpValueName
0x1800fd991  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x1800fd996  call    cs:__imp_RegSetValueExW
0x1800fd99d  nop     dword ptr [rax+rax+00h]
0x1800fd9a2  test    eax, eax
0x1800fd9a4  jz      short loc_1800FD9B1
0x1800fd9a6  jg      short loc_1800FD940
0x1800fd9a8  mov     ebx, eax
0x1800fd9aa  jmp     short loc_1800FD9B1
0x1800fd9ac  mov     ebx, 80070057h
0x1800fd9b1  mov     rcx, [rbp+hKey]; hKey
0x1800fd9b5  test    rcx, rcx
0x1800fd9b8  jz      short loc_1800FD9C6
0x1800fd9ba  call    cs:__imp_RegCloseKey
0x1800fd9c1  nop     dword ptr [rax+rax+00h]
0x1800fd9c6  lea     rcx, [rbp+pvarg]; pvarg
0x1800fd9ca  call    cs:__imp_VariantClear
0x1800fd9d1  nop     dword ptr [rax+rax+00h]
0x1800fd9d6  mov     eax, ebx
0x1800fd9d8  add     rsp, 80h
0x1800fd9df  pop     r14
0x1800fd9e1  pop     rdi
0x1800fd9e2  pop     rsi
0x1800fd9e3  pop     rbx
0x1800fd9e4  pop     rbp
0x1800fd9e5  retn
```
