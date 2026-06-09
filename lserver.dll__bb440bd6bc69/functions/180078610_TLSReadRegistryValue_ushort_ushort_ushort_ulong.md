# TLSReadRegistryValue(ushort *,ushort *,ushort * *,ulong *)

- ea: `0x180078610`
- end: `0x1800787c3`
- name: `?TLSReadRegistryValue@@YAKPEAG0PEAPEAGPEAK@Z`
- size: `435`
- prototype: `unsigned int(unsigned __int16 *, unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020284`
- `0x180020790`

## callees

- `0x180005665`
- `0x180078610`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800786b1`
- `ADVAPI32!RegQueryValueExW` at `0x18007872e`
- `ADVAPI32!RegQueryValueExW` at `0x1800786b1`
- `ADVAPI32!RegQueryValueExW` at `0x18007872e`
- `ADVAPI32!RegOpenKeyExW` at `0x180078680`
- `ADVAPI32!RegOpenKeyExW` at `0x180078680`
- `ADVAPI32!RegCloseKey` at `0x180078783`
- `ADVAPI32!RegCloseKey` at `0x180078783`
- `KERNEL32!GetLastError` at `0x1800786ee`
- `KERNEL32!GetLastError` at `0x1800786ee`
- `KERNEL32!LocalAlloc` at `0x1800786da`
- `KERNEL32!LocalAlloc` at `0x1800786da`
- `KERNEL32!LocalFree` at `0x18007879b`
- `KERNEL32!LocalFree` at `0x18007879b`

## pseudocode

```c
__int64 __fastcall TLSReadRegistryValue(unsigned __int16 *a1, unsigned __int16 *a2, HLOCAL *a3, unsigned int *a4)
{
  DWORD LastError; // ebx
  LSTATUS Value; // eax
  unsigned __int16 *v9; // rax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *cbData; // [rsp+60h] [rbp+20h] BYREF

  cbData = a1;
  if ( a2 && a3 && a4 )
  {
    *a3 = 0;
    LODWORD(cbData) = 0;
    hKey = 0;
    LastError = RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\Windows NT\\CurrentVersion",
                  0,
                  0x20019u,
                  &hKey);
    if ( !LastError )
    {
      Value = RegQueryValueExW(hKey, a2, 0, 0, 0, (LPDWORD)&cbData);
      LastError = Value;
      if ( Value == 234 || !Value )
      {
        v9 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)cbData + 2LL);
        *a3 = v9;
        if ( v9 )
        {
          memset_0(v9, 0, (unsigned int)cbData + 2LL);
          LastError = RegQueryValueExW(hKey, a2, 0, 0, (LPBYTE)*a3, (LPDWORD)&cbData);
          if ( (unsigned int)cbData >= 2 )
          {
            if ( *((_WORD *)*a3 + ((unsigned __int64)(unsigned int)((_DWORD)cbData - 1) >> 1)) )
            {
              *((_WORD *)*a3 + ((unsigned __int64)(unsigned int)cbData >> 1)) = 0;
              *a4 = (_DWORD)cbData + 2;
            }
            else
            {
              *a4 = (unsigned int)cbData;
            }
          }
          else
          {
            *a4 = 2;
          }
        }
        else
        {
          LastError = GetLastError();
        }
      }
    }
  }
  else
  {
    LastError = 87;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( LastError && a3 )
    LocalFree(*a3);
  return LastError;
}

```

## disassembly

```asm
0x180078610  mov     r11, rsp
0x180078613  mov     [r11+10h], rbx
0x180078617  mov     [r11+18h], rsi
0x18007861b  mov     [r11+20h], rdi
0x18007861f  mov     [r11+8], rcx
0x180078623  push    rbp
0x180078624  push    r14
0x180078626  push    r15
0x180078628  mov     rbp, rsp
0x18007862b  sub     rsp, 40h
0x18007862f  xor     r15d, r15d
0x180078632  mov     rsi, r9
0x180078635  mov     rdi, r8
0x180078638  mov     r14, rdx
0x18007863b  test    rdx, rdx
0x18007863e  jz      loc_180078775
0x180078644  test    r8, r8
0x180078647  jz      loc_180078775
0x18007864d  test    r9, r9
0x180078650  jz      loc_180078775
0x180078656  mov     [r8], r15
0x180078659  lea     rax, [rbp+hKey]
0x18007865d  xor     r8d, r8d; ulOptions
0x180078660  mov     [r11-38h], rax
0x180078664  mov     r9d, 20019h; samDesired
0x18007866a  mov     dword ptr [rbp+cbData], r15d
0x18007866e  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows NT\\Curren"...
0x180078675  mov     [rbp+hKey], r15
0x180078679  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180078680  call    cs:__imp_RegOpenKeyExW
0x180078687  nop     dword ptr [rax+rax+00h]
0x18007868c  mov     ebx, eax
0x18007868e  test    eax, eax
0x180078690  jnz     loc_18007877A
0x180078696  mov     rcx, [rbp+hKey]; hKey
0x18007869a  lea     rax, [rbp+cbData]
0x18007869e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800786a3  xor     r9d, r9d; lpType
0x1800786a6  xor     r8d, r8d; lpReserved
0x1800786a9  mov     [rsp+40h+lpData], r15; lpData
0x1800786ae  mov     rdx, r14; lpValueName
0x1800786b1  call    cs:__imp_RegQueryValueExW
0x1800786b8  nop     dword ptr [rax+rax+00h]
0x1800786bd  mov     ebx, eax
0x1800786bf  cmp     eax, 0EAh
0x1800786c4  jz      short loc_1800786CE
0x1800786c6  test    eax, eax
0x1800786c8  jnz     loc_18007877A
0x1800786ce  mov     edx, dword ptr [rbp+cbData]
0x1800786d1  mov     ecx, 40h ; '@'; uFlags
0x1800786d6  add     rdx, 2; uBytes
0x1800786da  call    cs:__imp_LocalAlloc
0x1800786e1  nop     dword ptr [rax+rax+00h]
0x1800786e6  mov     [rdi], rax
0x1800786e9  test    rax, rax
0x1800786ec  jnz     short loc_1800786FE
0x1800786ee  call    cs:__imp_GetLastError
0x1800786f5  nop     dword ptr [rax+rax+00h]
0x1800786fa  mov     ebx, eax
0x1800786fc  jmp     short loc_18007877A
0x1800786fe  mov     r8d, dword ptr [rbp+cbData]
0x180078702  xor     edx, edx; Val
0x180078704  add     r8, 2; Size
0x180078708  mov     rcx, rax; void *
0x18007870b  call    memset_0
0x180078710  mov     rcx, [rbp+hKey]; hKey
0x180078714  lea     rax, [rbp+cbData]
0x180078718  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18007871d  xor     r9d, r9d; lpType
0x180078720  mov     rax, [rdi]
0x180078723  xor     r8d, r8d; lpReserved
0x180078726  mov     rdx, r14; lpValueName
0x180078729  mov     [rsp+40h+lpData], rax; lpData
0x18007872e  call    cs:__imp_RegQueryValueExW
0x180078735  nop     dword ptr [rax+rax+00h]
0x18007873a  mov     edx, dword ptr [rbp+cbData]
0x18007873d  mov     ebx, eax
0x18007873f  cmp     edx, 2
0x180078742  jnb     short loc_18007874C
0x180078744  mov     dword ptr [rsi], 2
0x18007874a  jmp     short loc_18007877A
0x18007874c  mov     r8, [rdi]
0x18007874f  lea     ecx, [rdx-1]
0x180078752  shr     rcx, 1
0x180078755  cmp     [r8+rcx*2], r15w
0x18007875a  jz      short loc_180078771
0x18007875c  mov     rax, rdx
0x18007875f  shr     rax, 1
0x180078762  mov     [r8+rax*2], r15w
0x180078767  mov     eax, dword ptr [rbp+cbData]
0x18007876a  add     eax, 2
0x18007876d  mov     [rsi], eax
0x18007876f  jmp     short loc_18007877A
0x180078771  mov     [rsi], edx
0x180078773  jmp     short loc_18007877A
0x180078775  mov     ebx, 57h ; 'W'
0x18007877a  mov     rcx, [rbp+hKey]; hKey
0x18007877e  test    rcx, rcx
0x180078781  jz      short loc_18007878F
0x180078783  call    cs:__imp_RegCloseKey
0x18007878a  nop     dword ptr [rax+rax+00h]
0x18007878f  test    ebx, ebx
0x180078791  jz      short loc_1800787A7
0x180078793  test    rdi, rdi
0x180078796  jz      short loc_1800787A7
0x180078798  mov     rcx, [rdi]; hMem
0x18007879b  call    cs:__imp_LocalFree
0x1800787a2  nop     dword ptr [rax+rax+00h]
0x1800787a7  mov     rsi, [rsp+40h+arg_10]
0x1800787ac  mov     eax, ebx
0x1800787ae  mov     rbx, [rsp+40h+arg_8]
0x1800787b3  mov     rdi, [rsp+40h+arg_18]
0x1800787b8  add     rsp, 40h
0x1800787bc  pop     r15
0x1800787be  pop     r14
0x1800787c0  pop     rbp
0x1800787c1  retn
```
