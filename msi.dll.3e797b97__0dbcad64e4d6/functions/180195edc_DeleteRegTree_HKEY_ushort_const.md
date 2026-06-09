# DeleteRegTree(HKEY__ *,ushort const *)

- ea: `0x180195edc`
- end: `0x1801961b0`
- name: `?DeleteRegTree@@YAIPEAUHKEY__@@PEBG@Z`
- size: `724`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1801612a0`
- `0x180195edc`

## callees

- `0x18000c4bc`
- `0x180014288`
- `0x180040908`
- `0x18004a014`
- `0x180194ffc`
- `0x180195edc`
- `0x180198d20`
- `0x180265240`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180195fe1`
- `ADVAPI32!RegEnumKeyExW` at `0x180195fe1`
- `ADVAPI32!RegCloseKey` at `0x18019607c`
- `ADVAPI32!RegCloseKey` at `0x1801960f3`
- `ADVAPI32!RegCloseKey` at `0x180196174`
- `ADVAPI32!RegCloseKey` at `0x18019607c`
- `ADVAPI32!RegCloseKey` at `0x1801960f3`
- `ADVAPI32!RegCloseKey` at `0x180196174`
- `ADVAPI32!RegDeleteKeyW` at `0x180196092`
- `ADVAPI32!RegDeleteKeyW` at `0x180196109`
- `ADVAPI32!RegDeleteKeyW` at `0x180196092`
- `ADVAPI32!RegDeleteKeyW` at `0x180196109`

## string_xrefs

- `0x180195f7f`: `Failed to delete registry key. RegOpenKeyEx returned %08x.`
- `0x18019601c`: `DeleteRegTree: returning %08x.`
- `0x18019604e`: `Failed to delete registry key. RegEnumKeyEx returned %08x.`
- `0x180196135`: `Failed to delete registry key with the error %08x`

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
0x180195edc  mov     [rsp-8+arg_10], rbx
0x180195ee1  mov     [rsp-8+arg_18], rsi
0x180195ee6  push    rbp
0x180195ee7  push    rdi
0x180195ee8  push    r14
0x180195eea  lea     rbp, [rsp-47h]
0x180195eef  sub     rsp, 90h
0x180195ef6  mov     rax, cs:__security_cookie
0x180195efd  xor     rax, rsp
0x180195f00  mov     [rbp+57h+var_18], rax
0x180195f04  mov     rsi, rdx
0x180195f07  mov     [rbp+57h+cchName], 104h
0x180195f0e  mov     rdi, rcx
0x180195f11  mov     [rbp+57h+var_28], 1
0x180195f18  lea     rax, [rbp+57h+var_20]
0x180195f1c  xor     r14d, r14d
0x180195f1f  mov     edx, 104h
0x180195f24  mov     [rbp+57h+hKey], r14
0x180195f28  lea     rcx, [rbp+57h+lpName]
0x180195f2c  mov     [rbp+57h+lpName], rax
0x180195f30  xor     r8d, r8d
0x180195f33  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x180195f38  test    al, al
0x180195f3a  jnz     short loc_180195F45
0x180195f3c  lea     ebx, [r14+0Eh]
0x180195f40  jmp     loc_18019616B
0x180195f45  lea     rax, [rbp+57h+hKey]
0x180195f49  mov     r9d, 20019h; unsigned int
0x180195f4f  mov     rdx, rsi; unsigned __int16 *
0x180195f52  mov     [rsp+0A0h+lpReserved], rax; HKEY *
0x180195f57  mov     rcx, rdi; HKEY
0x180195f5a  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180195f5f  mov     ebx, eax
0x180195f61  cmp     eax, 2
0x180195f64  jnz     short loc_180195F6E
0x180195f66  mov     ebx, r14d
0x180195f69  jmp     loc_18019616B
0x180195f6e  test    eax, eax
0x180195f70  jz      short loc_180195FBF
0x180195f72  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x180195f79  jz      loc_18019616B
0x180195f7f  lea     r9, aFailedToDelete; "Failed to delete registry key. RegOpenK"...
0x180195f86  mov     [rsp+0A0h+var_48], r14
0x180195f8b  lea     rcx, aNull; "(NULL)"
0x180195f92  mov     [rsp+0A0h+var_50], r14d
0x180195f97  mov     [rsp+0A0h+var_58], rcx
0x180195f9c  mov     [rsp+0A0h+var_60], rcx
0x180195fa1  mov     [rsp+0A0h+lpftLastWriteTime], rcx
0x180195fa6  mov     [rsp+0A0h+lpcchClass], rcx
0x180195fab  mov     [rsp+0A0h+lpClass], rcx
0x180195fb0  mov     ecx, 0Ah
0x180195fb5  mov     [rsp+0A0h+lpReserved], rbx
0x180195fba  jmp     loc_180196161
0x180195fbf  mov     r8, [rbp+57h+lpName]; lpName
0x180195fc3  lea     r9, [rbp+57h+cchName]; lpcchName
0x180195fc7  mov     rcx, [rbp+57h+hKey]; hKey
0x180195fcb  xor     edx, edx; dwIndex
0x180195fcd  mov     [rsp+0A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180195fd2  mov     [rsp+0A0h+lpcchClass], r14; lpcchClass
0x180195fd7  mov     [rsp+0A0h+lpClass], r14; lpClass
0x180195fdc  mov     [rsp+0A0h+lpReserved], r14; lpReserved
0x180195fe1  call    cs:__imp_RegEnumKeyExW
0x180195fe8  nop     dword ptr [rax+rax+00h]
0x180195fed  mov     ebx, eax
0x180195fef  test    eax, eax
0x180195ff1  jnz     short loc_180196028
0x180195ff3  mov     rdx, [rbp+57h+lpName]; unsigned __int16 *
0x180195ff7  mov     rcx, [rbp+57h+hKey]; HKEY
0x180195ffb  call    ?DeleteRegTree@@YAIPEAUHKEY__@@PEBG@Z; DeleteRegTree(HKEY__ *,ushort const *)
0x180196000  mov     ebx, eax
0x180196002  test    eax, eax
0x180196004  jnz     short loc_18019600F
0x180196006  mov     [rbp+57h+cchName], 104h
0x18019600d  jmp     short loc_180195FBF
0x18019600f  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x180196016  jz      loc_18019616B
0x18019601c  lea     r9, aDeleteregtreeR; "DeleteRegTree: returning %08x."
0x180196023  jmp     loc_180195F86
0x180196028  cmp     ebx, 103h
0x18019602e  jz      short loc_180196078
0x180196030  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x180196037  jz      loc_18019616B
0x18019603d  mov     [rsp+0A0h+var_48], r14
0x180196042  lea     rcx, aNull; "(NULL)"
0x180196049  mov     [rsp+0A0h+var_50], r14d
0x18019604e  lea     r9, aFailedToDelete_1; "Failed to delete registry key. RegEnumK"...
0x180196055  mov     [rsp+0A0h+var_58], rcx
0x18019605a  mov     [rsp+0A0h+var_60], rcx
0x18019605f  mov     [rsp+0A0h+lpftLastWriteTime], rcx
0x180196064  mov     [rsp+0A0h+lpcchClass], rcx
0x180196069  mov     [rsp+0A0h+lpClass], rcx
0x18019606e  mov     [rsp+0A0h+lpReserved], rbx
0x180196073  jmp     loc_18019615C
0x180196078  mov     rcx, [rbp+57h+hKey]; hKey
0x18019607c  call    cs:__imp_RegCloseKey
0x180196083  nop     dword ptr [rax+rax+00h]
0x180196088  mov     rdx, rsi; lpSubKey
0x18019608b  mov     [rbp+57h+hKey], r14
0x18019608f  mov     rcx, rdi; hKey
0x180196092  call    cs:__imp_RegDeleteKeyW
0x180196099  nop     dword ptr [rax+rax+00h]
0x18019609e  mov     ebx, eax
0x1801960a0  test    eax, eax
0x1801960a2  jz      loc_18019616B
0x1801960a8  cmp     eax, 5
0x1801960ab  jnz     short loc_18019611B
0x1801960ad  mov     rdx, rsi; unsigned __int16 *
0x1801960b0  mov     rcx, rdi; HKEY
0x1801960b3  call    ?MakeAdminRegKeyOwner@@YAHPEAUHKEY__@@PEBG@Z; MakeAdminRegKeyOwner(HKEY__ *,ushort const *)
0x1801960b8  test    eax, eax
0x1801960ba  jz      loc_18019616B
0x1801960c0  lea     rax, [rbp+57h+hKey]
0x1801960c4  mov     r9d, 60000h; unsigned int
0x1801960ca  mov     rdx, rsi; unsigned __int16 *
0x1801960cd  mov     [rsp+0A0h+lpReserved], rax; HKEY *
0x1801960d2  mov     rcx, rdi; HKEY
0x1801960d5  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x1801960da  test    eax, eax
0x1801960dc  jnz     loc_18019616B
0x1801960e2  mov     rcx, [rbp+57h+hKey]; HKEY
0x1801960e6  call    ?AddAdminFullControlToRegKey@@YAHPEAUHKEY__@@@Z; AddAdminFullControlToRegKey(HKEY__ *)
0x1801960eb  test    eax, eax
0x1801960ed  jz      short loc_18019616B
0x1801960ef  mov     rcx, [rbp+57h+hKey]; hKey
0x1801960f3  call    cs:__imp_RegCloseKey
0x1801960fa  nop     dword ptr [rax+rax+00h]
0x1801960ff  mov     rdx, rsi; lpSubKey
0x180196102  mov     [rbp+57h+hKey], r14
0x180196106  mov     rcx, rdi; hKey
0x180196109  call    cs:__imp_RegDeleteKeyW
0x180196110  nop     dword ptr [rax+rax+00h]
0x180196115  mov     ebx, eax
0x180196117  test    eax, eax
0x180196119  jz      short loc_18019616B
0x18019611b  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x180196122  jz      short loc_18019616B
0x180196124  mov     [rsp+0A0h+var_48], r14; void *
0x180196129  lea     rcx, aNull; "(NULL)"
0x180196130  mov     [rsp+0A0h+var_50], r14d; unsigned int
0x180196135  lea     r9, aFailedToDelete_0; "Failed to delete registry key with the "...
0x18019613c  mov     [rsp+0A0h+var_58], rcx; unsigned __int16 *
0x180196141  mov     [rsp+0A0h+var_60], rcx; unsigned __int16 *
0x180196146  mov     [rsp+0A0h+lpftLastWriteTime], rcx; unsigned __int16 *
0x18019614b  mov     [rsp+0A0h+lpcchClass], rcx; unsigned __int16 *
0x180196150  mov     eax, ebx
0x180196152  mov     [rsp+0A0h+lpClass], rcx; unsigned __int16 *
0x180196157  mov     [rsp+0A0h+lpReserved], rax; unsigned __int16 *
0x18019615c  mov     ecx, 5; int
0x180196161  xor     r8d, r8d; int
0x180196164  xor     edx, edx; unsigned __int16
0x180196166  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18019616b  mov     rcx, [rbp+57h+hKey]; hKey
0x18019616f  test    rcx, rcx
0x180196172  jz      short loc_180196180
0x180196174  call    cs:__imp_RegCloseKey
0x18019617b  nop     dword ptr [rax+rax+00h]
0x180196180  lea     rcx, [rbp+57h+lpName]
0x180196184  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x180196189  mov     eax, ebx
0x18019618b  mov     rcx, [rbp+57h+var_18]
0x18019618f  xor     rcx, rsp; StackCookie
0x180196192  call    __security_check_cookie
0x180196197  lea     r11, [rsp+0A0h+var_10]
0x18019619f  mov     rbx, [r11+30h]
0x1801961a3  mov     rsi, [r11+38h]
0x1801961a7  mov     rsp, r11
0x1801961aa  pop     r14
0x1801961ac  pop     rdi
0x1801961ad  pop     rbp
0x1801961ae  retn
```
