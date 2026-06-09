# DeleteRegTree(HKEY__ *,ushort const *)

- ea: `0x18018f5e4`
- end: `0x18018f88f`
- name: `?DeleteRegTree@@YAIPEAUHKEY__@@PEBG@Z`
- size: `683`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18015b6c0`
- `0x18018f5e4`

## callees

- `0x180019bb4`
- `0x180025688`
- `0x180025a18`
- `0x18004ceb0`
- `0x18018e798`
- `0x18018f5e4`
- `0x18019228c`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18018f6e9`
- `ADVAPI32!RegEnumKeyExW` at `0x18018f6e9`
- `ADVAPI32!RegCloseKey` at `0x18018f77e`
- `ADVAPI32!RegCloseKey` at `0x18018f7e5`
- `ADVAPI32!RegCloseKey` at `0x18018f85a`
- `ADVAPI32!RegCloseKey` at `0x18018f77e`
- `ADVAPI32!RegCloseKey` at `0x18018f7e5`
- `ADVAPI32!RegCloseKey` at `0x18018f85a`
- `ADVAPI32!RegDeleteKeyW` at `0x18018f78e`
- `ADVAPI32!RegDeleteKeyW` at `0x18018f7f5`
- `ADVAPI32!RegDeleteKeyW` at `0x18018f78e`
- `ADVAPI32!RegDeleteKeyW` at `0x18018f7f5`

## string_xrefs

- `0x18018f687`: `Failed to delete registry key. RegOpenKeyEx returned %08x.`
- `0x18018f71e`: `DeleteRegTree: returning %08x.`
- `0x18018f750`: `Failed to delete registry key. RegEnumKeyEx returned %08x.`
- `0x18018f81b`: `Failed to delete registry key with the error %08x`

## pseudocode

```c
__int64 __fastcall DeleteRegTree(HKEY a1, const unsigned __int16 *a2)
{
  unsigned int v4; // r8d
  const unsigned __int16 *v5; // rbx
  unsigned int v6; // eax
  const unsigned __int16 *v7; // r9
  unsigned int v8; // eax
  unsigned int v9; // eax
  const unsigned __int16 *v10; // r9
  LSTATUS v11; // eax
  unsigned int v12; // r8d
  unsigned __int64 lpReserved; // [rsp+20h] [rbp-29h]
  HKEY hKey; // [rsp+60h] [rbp+17h] BYREF
  DWORD cchName; // [rsp+68h] [rbp+1Fh] BYREF
  LPWSTR lpName; // [rsp+70h] [rbp+27h] BYREF
  int v18; // [rsp+78h] [rbp+2Fh]
  char v19; // [rsp+80h] [rbp+37h] BYREF

  cchName = 260;
  v18 = 1;
  hKey = 0;
  lpName = (LPWSTR)&v19;
  if ( (unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&lpName, 260, 0) )
  {
    v6 = MsiRegOpen64bitKey(a1, a2, v4, 0x20019u, &hKey);
    v5 = (const unsigned __int16 *)v6;
    if ( v6 == 2 )
    {
      LODWORD(v5) = 0;
    }
    else if ( v6 )
    {
      if ( g_dmDiagnosticMode )
      {
        v7 = L"Failed to delete registry key. RegOpenKeyEx returned %08x.";
        goto LABEL_8;
      }
    }
    else
    {
      while ( 1 )
      {
        v8 = RegEnumKeyExW(hKey, 0, lpName, &cchName, 0, 0, 0, 0);
        LODWORD(v5) = v8;
        if ( v8 )
        {
          if ( v8 == 259 )
          {
            RegCloseKey(hKey);
            hKey = 0;
            v11 = RegDeleteKeyW(a1, a2);
            LODWORD(v5) = v11;
            if ( !v11 )
              goto LABEL_26;
            if ( v11 == 5 )
            {
              if ( !MakeAdminRegKeyOwner(a1, a2) )
                goto LABEL_26;
              if ( MsiRegOpen64bitKey(a1, a2, v12, 0x60000u, &hKey) )
                goto LABEL_26;
              if ( !(unsigned int)AddAdminFullControlToRegKey(hKey) )
                goto LABEL_26;
              RegCloseKey(hKey);
              hKey = 0;
              LODWORD(v5) = RegDeleteKeyW(a1, a2);
              if ( !(_DWORD)v5 )
                goto LABEL_26;
            }
            if ( !g_dmDiagnosticMode )
              goto LABEL_26;
            v10 = L"Failed to delete registry key with the error %08x";
            lpReserved = (unsigned int)v5;
          }
          else
          {
            if ( !g_dmDiagnosticMode )
              goto LABEL_26;
            v10 = L"Failed to delete registry key. RegEnumKeyEx returned %08x.";
            lpReserved = v8;
          }
          DebugString(
            5,
            0,
            0,
            v10,
            (const unsigned __int16 *)lpReserved,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
          goto LABEL_26;
        }
        v9 = DeleteRegTree(hKey, lpName);
        v5 = (const unsigned __int16 *)v9;
        if ( v9 )
          break;
        cchName = 260;
      }
      if ( !g_dmDiagnosticMode )
        goto LABEL_26;
      v7 = L"DeleteRegTree: returning %08x.";
LABEL_8:
      DebugString(10, 0, 0, v7, v5, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
    }
  }
  else
  {
    LODWORD(v5) = 14;
  }
LABEL_26:
  if ( hKey )
    RegCloseKey(hKey);
  CAPITempBuffer<unsigned short,1>::Destroy(&lpName);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18018f5e4  mov     [rsp-8+arg_10], rbx
0x18018f5e9  mov     [rsp-8+arg_18], rsi
0x18018f5ee  push    rbp
0x18018f5ef  push    rdi
0x18018f5f0  push    r14
0x18018f5f2  lea     rbp, [rsp-47h]
0x18018f5f7  sub     rsp, 90h
0x18018f5fe  mov     rax, cs:__security_cookie
0x18018f605  xor     rax, rsp
0x18018f608  mov     [rbp+57h+var_18], rax
0x18018f60c  mov     rsi, rdx
0x18018f60f  mov     [rbp+57h+cchName], 104h
0x18018f616  mov     rdi, rcx
0x18018f619  mov     [rbp+57h+var_28], 1
0x18018f620  lea     rax, [rbp+57h+var_20]
0x18018f624  xor     r14d, r14d
0x18018f627  mov     edx, 104h
0x18018f62c  mov     [rbp+57h+hKey], r14
0x18018f630  lea     rcx, [rbp+57h+lpName]
0x18018f634  mov     [rbp+57h+lpName], rax
0x18018f638  xor     r8d, r8d
0x18018f63b  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x18018f640  test    al, al
0x18018f642  jnz     short loc_18018F64D
0x18018f644  lea     ebx, [r14+0Eh]
0x18018f648  jmp     loc_18018F851
0x18018f64d  lea     rax, [rbp+57h+hKey]
0x18018f651  mov     r9d, 20019h; unsigned int
0x18018f657  mov     rdx, rsi; unsigned __int16 *
0x18018f65a  mov     [rsp+0A0h+lpReserved], rax; HKEY *
0x18018f65f  mov     rcx, rdi; HKEY
0x18018f662  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18018f667  mov     ebx, eax
0x18018f669  cmp     eax, 2
0x18018f66c  jnz     short loc_18018F676
0x18018f66e  mov     ebx, r14d
0x18018f671  jmp     loc_18018F851
0x18018f676  test    eax, eax
0x18018f678  jz      short loc_18018F6C7
0x18018f67a  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18018f681  jz      loc_18018F851
0x18018f687  lea     r9, aFailedToDelete; "Failed to delete registry key. RegOpenK"...
0x18018f68e  mov     [rsp+0A0h+var_48], r14
0x18018f693  lea     rcx, aNull; "(NULL)"
0x18018f69a  mov     [rsp+0A0h+var_50], r14d
0x18018f69f  mov     [rsp+0A0h+var_58], rcx
0x18018f6a4  mov     [rsp+0A0h+var_60], rcx
0x18018f6a9  mov     [rsp+0A0h+lpftLastWriteTime], rcx
0x18018f6ae  mov     [rsp+0A0h+lpcchClass], rcx
0x18018f6b3  mov     [rsp+0A0h+lpClass], rcx
0x18018f6b8  mov     ecx, 0Ah
0x18018f6bd  mov     [rsp+0A0h+lpReserved], rbx
0x18018f6c2  jmp     loc_18018F847
0x18018f6c7  mov     r8, [rbp+57h+lpName]; lpName
0x18018f6cb  lea     r9, [rbp+57h+cchName]; lpcchName
0x18018f6cf  mov     rcx, [rbp+57h+hKey]; hKey
0x18018f6d3  xor     edx, edx; dwIndex
0x18018f6d5  mov     [rsp+0A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18018f6da  mov     [rsp+0A0h+lpcchClass], r14; lpcchClass
0x18018f6df  mov     [rsp+0A0h+lpClass], r14; lpClass
0x18018f6e4  mov     [rsp+0A0h+lpReserved], r14; lpReserved
0x18018f6e9  call    cs:__imp_RegEnumKeyExW
0x18018f6ef  mov     ebx, eax
0x18018f6f1  test    eax, eax
0x18018f6f3  jnz     short loc_18018F72A
0x18018f6f5  mov     rdx, [rbp+57h+lpName]; unsigned __int16 *
0x18018f6f9  mov     rcx, [rbp+57h+hKey]; HKEY
0x18018f6fd  call    ?DeleteRegTree@@YAIPEAUHKEY__@@PEBG@Z; DeleteRegTree(HKEY__ *,ushort const *)
0x18018f702  mov     ebx, eax
0x18018f704  test    eax, eax
0x18018f706  jnz     short loc_18018F711
0x18018f708  mov     [rbp+57h+cchName], 104h
0x18018f70f  jmp     short loc_18018F6C7
0x18018f711  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18018f718  jz      loc_18018F851
0x18018f71e  lea     r9, aDeleteregtreeR; "DeleteRegTree: returning %08x."
0x18018f725  jmp     loc_18018F68E
0x18018f72a  cmp     ebx, 103h
0x18018f730  jz      short loc_18018F77A
0x18018f732  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18018f739  jz      loc_18018F851
0x18018f73f  mov     [rsp+0A0h+var_48], r14
0x18018f744  lea     rcx, aNull; "(NULL)"
0x18018f74b  mov     [rsp+0A0h+var_50], r14d
0x18018f750  lea     r9, aFailedToDelete_1; "Failed to delete registry key. RegEnumK"...
0x18018f757  mov     [rsp+0A0h+var_58], rcx
0x18018f75c  mov     [rsp+0A0h+var_60], rcx
0x18018f761  mov     [rsp+0A0h+lpftLastWriteTime], rcx
0x18018f766  mov     [rsp+0A0h+lpcchClass], rcx
0x18018f76b  mov     [rsp+0A0h+lpClass], rcx
0x18018f770  mov     [rsp+0A0h+lpReserved], rbx
0x18018f775  jmp     loc_18018F842
0x18018f77a  mov     rcx, [rbp+57h+hKey]; hKey
0x18018f77e  call    cs:__imp_RegCloseKey
0x18018f784  mov     rdx, rsi; lpSubKey
0x18018f787  mov     [rbp+57h+hKey], r14
0x18018f78b  mov     rcx, rdi; hKey
0x18018f78e  call    cs:__imp_RegDeleteKeyW
0x18018f794  mov     ebx, eax
0x18018f796  test    eax, eax
0x18018f798  jz      loc_18018F851
0x18018f79e  cmp     eax, 5
0x18018f7a1  jnz     short loc_18018F801
0x18018f7a3  mov     rdx, rsi; unsigned __int16 *
0x18018f7a6  mov     rcx, rdi; HKEY
0x18018f7a9  call    ?MakeAdminRegKeyOwner@@YAHPEAUHKEY__@@PEBG@Z; MakeAdminRegKeyOwner(HKEY__ *,ushort const *)
0x18018f7ae  test    eax, eax
0x18018f7b0  jz      loc_18018F851
0x18018f7b6  lea     rax, [rbp+57h+hKey]
0x18018f7ba  mov     r9d, 60000h; unsigned int
0x18018f7c0  mov     rdx, rsi; unsigned __int16 *
0x18018f7c3  mov     [rsp+0A0h+lpReserved], rax; HKEY *
0x18018f7c8  mov     rcx, rdi; HKEY
0x18018f7cb  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18018f7d0  test    eax, eax
0x18018f7d2  jnz     short loc_18018F851
0x18018f7d4  mov     rcx, [rbp+57h+hKey]; HKEY
0x18018f7d8  call    ?AddAdminFullControlToRegKey@@YAHPEAUHKEY__@@@Z; AddAdminFullControlToRegKey(HKEY__ *)
0x18018f7dd  test    eax, eax
0x18018f7df  jz      short loc_18018F851
0x18018f7e1  mov     rcx, [rbp+57h+hKey]; hKey
0x18018f7e5  call    cs:__imp_RegCloseKey
0x18018f7eb  mov     rdx, rsi; lpSubKey
0x18018f7ee  mov     [rbp+57h+hKey], r14
0x18018f7f2  mov     rcx, rdi; hKey
0x18018f7f5  call    cs:__imp_RegDeleteKeyW
0x18018f7fb  mov     ebx, eax
0x18018f7fd  test    eax, eax
0x18018f7ff  jz      short loc_18018F851
0x18018f801  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18018f808  jz      short loc_18018F851
0x18018f80a  mov     [rsp+0A0h+var_48], r14; void *
0x18018f80f  lea     rcx, aNull; "(NULL)"
0x18018f816  mov     [rsp+0A0h+var_50], r14d; unsigned int
0x18018f81b  lea     r9, aFailedToDelete_0; "Failed to delete registry key with the "...
0x18018f822  mov     [rsp+0A0h+var_58], rcx; unsigned __int16 *
0x18018f827  mov     [rsp+0A0h+var_60], rcx; unsigned __int16 *
0x18018f82c  mov     [rsp+0A0h+lpftLastWriteTime], rcx; unsigned __int16 *
0x18018f831  mov     [rsp+0A0h+lpcchClass], rcx; unsigned __int16 *
0x18018f836  mov     eax, ebx
0x18018f838  mov     [rsp+0A0h+lpClass], rcx; unsigned __int16 *
0x18018f83d  mov     [rsp+0A0h+lpReserved], rax; unsigned __int16 *
0x18018f842  mov     ecx, 5; int
0x18018f847  xor     r8d, r8d; int
0x18018f84a  xor     edx, edx; unsigned __int16
0x18018f84c  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18018f851  mov     rcx, [rbp+57h+hKey]; hKey
0x18018f855  test    rcx, rcx
0x18018f858  jz      short loc_18018F860
0x18018f85a  call    cs:__imp_RegCloseKey
0x18018f860  lea     rcx, [rbp+57h+lpName]
0x18018f864  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18018f869  mov     eax, ebx
0x18018f86b  mov     rcx, [rbp+57h+var_18]
0x18018f86f  xor     rcx, rsp; StackCookie
0x18018f872  call    __security_check_cookie
0x18018f877  lea     r11, [rsp+0A0h+var_10]
0x18018f87f  mov     rbx, [r11+30h]
0x18018f883  mov     rsi, [r11+38h]
0x18018f887  mov     rsp, r11
0x18018f88a  pop     r14
0x18018f88c  pop     rdi
0x18018f88d  pop     rbp
0x18018f88e  retn
```
