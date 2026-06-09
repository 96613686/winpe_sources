# SaveNodeIdInRegistry(uchar *,ulong)

- ea: `0x1004689cc`
- end: `0x100468a39`
- name: `?SaveNodeIdInRegistry@@YAXPEAEK@Z`
- size: `109`
- prototype: `void __fastcall(BYTE *lpData, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x100468718`

## callees

- `0x1004689cc`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x100468a00`
- `ADVAPI32!RegSetValueExW` at `0x100468a2e`
- `ADVAPI32!RegSetValueExW` at `0x100468a00`
- `ADVAPI32!RegSetValueExW` at `0x100468a2e`

## pseudocode

```c
void __fastcall SaveNodeIdInRegistry(BYTE *lpData, int a2)
{
  int Data; // [rsp+48h] [rbp+10h] BYREF

  Data = a2;
  if ( hKey )
  {
    if ( !RegSetValueExW(hKey, lpValueName, 0, 3u, lpData, 6u) )
      RegSetValueExW(hKey, off_1005CFBD0, 0, 4u, (const BYTE *)&Data, 4u);
  }
}

```

## disassembly

```asm
0x1004689cc  mov     [rsp+Data], edx
0x1004689d0  sub     rsp, 38h
0x1004689d4  mov     rax, rcx
0x1004689d7  mov     rcx, cs:hKey; hKey
0x1004689de  test    rcx, rcx
0x1004689e1  jz      short loc_100468A34
0x1004689e3  mov     rdx, cs:lpValueName; lpValueName
0x1004689ea  mov     r9d, 3; dwType
0x1004689f0  mov     [rsp+38h+cbData], 6; cbData
0x1004689f8  xor     r8d, r8d; Reserved
0x1004689fb  mov     [rsp+38h+lpData], rax; lpData
0x100468a00  call    cs:__imp_RegSetValueExW
0x100468a06  test    eax, eax
0x100468a08  jnz     short loc_100468A34
0x100468a0a  mov     rdx, cs:off_1005CFBD0; lpValueName
0x100468a11  lea     r9d, [rax+4]; dwType
0x100468a15  mov     rcx, cs:hKey; hKey
0x100468a1c  lea     rax, [rsp+38h+Data]
0x100468a21  mov     [rsp+38h+cbData], r9d; cbData
0x100468a26  xor     r8d, r8d; Reserved
0x100468a29  mov     [rsp+38h+lpData], rax; lpData
0x100468a2e  call    cs:__imp_RegSetValueExW
0x100468a34  add     rsp, 38h
0x100468a38  retn
```
