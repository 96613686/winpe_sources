# CCspSimpleRegHelper::SetBinaryRegValue(HKEY__ *,ushort const *,ushort const *,tagVARIANT)

- ea: `0x1800fd780`
- end: `0x1800fd8a3`
- name: `?SetBinaryRegValue@CCspSimpleRegHelper@@CAJPEAUHKEY__@@PEBG1UtagVARIANT@@@Z`
- size: `291`
- prototype: `static int(HKEY, const unsigned __int16 *, const unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800fdb7c`

## callees

- `0x1800fd780`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800fd810`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800fd810`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800fd7f0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800fd7f0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800fd86e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800fd86e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fd84b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fd84b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fd884`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fd884`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fd7c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fd7c1`

## pseudocode

```c
__int64 __fastcall CCspSimpleRegHelper::SetBinaryRegValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct tagVARIANT *a4)
{
  int UBound; // ebx
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  void *ppvData; // [rsp+38h] [rbp-10h] BYREF
  LONG plUbound; // [rsp+68h] [rbp+20h] BYREF

  UBound = 0;
  hKey = 0;
  ppvData = 0;
  plUbound = 0;
  if ( a4->vt )
  {
    v7 = RegOpenKeyExW(a1, a2, 0, 0x2001Fu, &hKey);
    UBound = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        UBound = (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      UBound = SafeArrayAccessData(a4->parray, &ppvData);
      if ( UBound >= 0 )
      {
        UBound = SafeArrayGetUBound(a4->parray, 1u, &plUbound);
        if ( UBound >= 0 )
        {
          v8 = RegSetValueExW(hKey, a3, 0, 3u, (const BYTE *)ppvData, ++plUbound);
          if ( v8 )
          {
            if ( v8 > 0 )
              UBound = (unsigned __int16)v8 | 0x80070000;
            else
              UBound = v8;
          }
        }
        SafeArrayUnaccessData(a4->parray);
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return (unsigned int)UBound;
}

```

## disassembly

```asm
0x1800fd780  mov     r11, rsp
0x1800fd783  mov     [r11+8], rbx
0x1800fd787  mov     [r11+10h], rsi
0x1800fd78b  push    rdi
0x1800fd78c  sub     rsp, 40h
0x1800fd790  xor     ebx, ebx
0x1800fd792  xor     eax, eax
0x1800fd794  mov     rdi, r9
0x1800fd797  mov     rsi, r8
0x1800fd79a  mov     [r11-18h], rbx
0x1800fd79e  mov     [r11-10h], rbx
0x1800fd7a2  mov     [rsp+48h+plUbound], ebx
0x1800fd7a6  cmp     ax, [r9]
0x1800fd7aa  jz      loc_1800FD890
0x1800fd7b0  lea     rax, [r11-18h]
0x1800fd7b4  mov     r9d, 2001Fh; samDesired
0x1800fd7ba  xor     r8d, r8d; ulOptions
0x1800fd7bd  mov     [r11-28h], rax
0x1800fd7c1  call    cs:__imp_RegOpenKeyExW
0x1800fd7c8  nop     dword ptr [rax+rax+00h]
0x1800fd7cd  mov     ebx, eax
0x1800fd7cf  test    eax, eax
0x1800fd7d1  jz      short loc_1800FD7E7
0x1800fd7d3  jle     loc_1800FD87A
0x1800fd7d9  movzx   ebx, ax
0x1800fd7dc  or      ebx, 80070000h
0x1800fd7e2  jmp     loc_1800FD87A
0x1800fd7e7  mov     rcx, [rdi+8]; psa
0x1800fd7eb  lea     rdx, [rsp+48h+ppvData]; ppvData
0x1800fd7f0  call    cs:__imp_SafeArrayAccessData
0x1800fd7f7  nop     dword ptr [rax+rax+00h]
0x1800fd7fc  mov     ebx, eax
0x1800fd7fe  test    eax, eax
0x1800fd800  js      short loc_1800FD87A
0x1800fd802  mov     rcx, [rdi+8]; psa
0x1800fd806  lea     r8, [rsp+48h+plUbound]; plUbound
0x1800fd80b  mov     edx, 1; nDim
0x1800fd810  call    cs:__imp_SafeArrayGetUBound
0x1800fd817  nop     dword ptr [rax+rax+00h]
0x1800fd81c  mov     ebx, eax
0x1800fd81e  test    eax, eax
0x1800fd820  js      short loc_1800FD86A
0x1800fd822  mov     eax, [rsp+48h+plUbound]
0x1800fd826  mov     r9d, 3; dwType
0x1800fd82c  mov     rcx, [rsp+48h+hKey]; hKey
0x1800fd831  inc     eax
0x1800fd833  mov     [rsp+48h+cbData], eax; cbData
0x1800fd837  xor     r8d, r8d; Reserved
0x1800fd83a  mov     [rsp+48h+plUbound], eax
0x1800fd83e  mov     rdx, rsi; lpValueName
0x1800fd841  mov     rax, [rsp+48h+ppvData]
0x1800fd846  mov     [rsp+48h+lpData], rax; lpData
0x1800fd84b  call    cs:__imp_RegSetValueExW
0x1800fd852  nop     dword ptr [rax+rax+00h]
0x1800fd857  test    eax, eax
0x1800fd859  jz      short loc_1800FD86A
0x1800fd85b  jg      short loc_1800FD861
0x1800fd85d  mov     ebx, eax
0x1800fd85f  jmp     short loc_1800FD86A
0x1800fd861  movzx   ebx, ax
0x1800fd864  or      ebx, 80070000h
0x1800fd86a  mov     rcx, [rdi+8]; psa
0x1800fd86e  call    cs:__imp_SafeArrayUnaccessData
0x1800fd875  nop     dword ptr [rax+rax+00h]
0x1800fd87a  mov     rcx, [rsp+48h+hKey]; hKey
0x1800fd87f  test    rcx, rcx
0x1800fd882  jz      short loc_1800FD890
0x1800fd884  call    cs:__imp_RegCloseKey
0x1800fd88b  nop     dword ptr [rax+rax+00h]
0x1800fd890  mov     rsi, [rsp+48h+arg_8]
0x1800fd895  mov     eax, ebx
0x1800fd897  mov     rbx, [rsp+48h+arg_0]
0x1800fd89c  add     rsp, 40h
0x1800fd8a0  pop     rdi
0x1800fd8a1  retn
```
