# CommonUtil::SetStringToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ushort const *,ulong)

- ea: `0x18007fdd8`
- end: `0x18007fece`
- name: `?SetStringToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@0K@Z`
- size: `246`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007e4f8`
- `0x18007f114`
- `0x18007f838`

## callees

- `0x18007fdd8`
- `0x180080648`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007febd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007febd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007fe1f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007fe1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007fe94`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007fe94`

## pseudocode

```c
__int64 __fastcall CommonUtil::SetStringToRegistry(
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        const unsigned __int16 *a3,
        const BYTE *a4)
{
  LSTATUS v6; // eax
  signed int v7; // ebx
  unsigned __int64 v8; // rax
  LSTATUS v9; // eax
  DWORD cbData[2]; // [rsp+50h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+18h] BYREF

  hKey = 0;
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&a4[2 * v8] );
    if ( v8 + 1 < v8 )
      goto LABEL_11;
    *(_QWORD *)cbData = v8 + 1;
    v7 = ULongLongMult(v8 + 1, 2u, (unsigned __int64 *)cbData);
    if ( v7 < 0 )
      goto LABEL_12;
    if ( *(_QWORD *)cbData > 0xFFFFFFFF )
    {
LABEL_11:
      v7 = -2147024362;
    }
    else
    {
      v9 = RegSetValueExW(hKey, lpValueName, 0, 1u, a4, cbData[0]);
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
    }
  }
LABEL_12:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007fdd8  mov     r11, rsp
0x18007fddb  mov     [r11+18h], r8
0x18007fddf  push    rbx
0x18007fde0  push    rbp
0x18007fde1  push    rsi
0x18007fde2  push    rdi
0x18007fde3  sub     rsp, 68h
0x18007fde7  xor     ebp, ebp
0x18007fde9  lea     rax, [r11+18h]
0x18007fded  mov     [r11-48h], rbp
0x18007fdf1  mov     rsi, rdx
0x18007fdf4  mov     [r11-50h], rax
0x18007fdf8  mov     rdi, r9
0x18007fdfb  mov     [r11-58h], rbp
0x18007fdff  mov     rdx, rcx; lpSubKey
0x18007fe02  mov     [rsp+88h+samDesired], 0F003Fh; samDesired
0x18007fe0a  xor     r9d, r9d; lpClass
0x18007fe0d  xor     r8d, r8d; Reserved
0x18007fe10  mov     [rsp+88h+dwOptions], ebp; dwOptions
0x18007fe14  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007fe1b  mov     [r11+18h], rbp
0x18007fe1f  call    cs:__imp_RegCreateKeyExW
0x18007fe25  mov     ebx, eax
0x18007fe27  test    eax, eax
0x18007fe29  jle     short loc_18007FE34
0x18007fe2b  movzx   ebx, ax
0x18007fe2e  or      ebx, 80070000h
0x18007fe34  test    ebx, ebx
0x18007fe36  js      short loc_18007FEB0
0x18007fe38  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007fe3c  inc     rax
0x18007fe3f  cmp     [rdi+rax*2], bp
0x18007fe43  jnz     short loc_18007FE3C
0x18007fe45  lea     rcx, [rax+1]; unsigned __int64
0x18007fe49  cmp     rcx, rax
0x18007fe4c  jb      short loc_18007FEAB
0x18007fe4e  lea     r8, [rsp+88h+cbData]; unsigned __int64 *
0x18007fe53  mov     qword ptr [rsp+88h+cbData], rcx
0x18007fe58  mov     edx, 2; unsigned __int64
0x18007fe5d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18007fe62  mov     ebx, eax
0x18007fe64  test    eax, eax
0x18007fe66  js      short loc_18007FEB0
0x18007fe68  mov     rax, qword ptr [rsp+88h+cbData]
0x18007fe6d  mov     ecx, 0FFFFFFFFh
0x18007fe72  cmp     rax, rcx
0x18007fe75  ja      short loc_18007FEAB
0x18007fe77  mov     rcx, [rsp+88h+hKey]; hKey
0x18007fe7f  mov     r9d, 1; dwType
0x18007fe85  mov     [rsp+88h+samDesired], eax; cbData
0x18007fe89  xor     r8d, r8d; Reserved
0x18007fe8c  mov     rdx, rsi; lpValueName
0x18007fe8f  mov     qword ptr [rsp+88h+dwOptions], rdi; lpData
0x18007fe94  call    cs:__imp_RegSetValueExW
0x18007fe9a  mov     ebx, eax
0x18007fe9c  test    eax, eax
0x18007fe9e  jle     short loc_18007FEB0
0x18007fea0  movzx   ebx, ax
0x18007fea3  or      ebx, 80070000h
0x18007fea9  jmp     short loc_18007FEB0
0x18007feab  mov     ebx, 80070216h
0x18007feb0  mov     rcx, [rsp+88h+hKey]; hKey
0x18007feb8  test    rcx, rcx
0x18007febb  jz      short loc_18007FEC3
0x18007febd  call    cs:__imp_RegCloseKey
0x18007fec3  mov     eax, ebx
0x18007fec5  add     rsp, 68h
0x18007fec9  pop     rdi
0x18007feca  pop     rsi
0x18007fecb  pop     rbp
0x18007fecc  pop     rbx
0x18007fecd  retn
```
