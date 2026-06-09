# SetMigrationStatus(ushort const *,ushort const *,ulong)

- ea: `0x18003d49c`
- end: `0x18003d592`
- name: `?SetMigrationStatus@@YAJPEBG0K@Z`
- size: `246`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035348`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18003d49c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d508`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d508`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d548`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d548`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003d536`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003d536`

## pseudocode

```c
__int64 __fastcall SetMigrationStatus(const unsigned __int16 *a1, unsigned __int16 *a2, int a3)
{
  LSTATUS v3; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  int Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  hKey = (HKEY)a2;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 14, WPP_12e48a9d849435eac3405c86722d7b90_Traceguids);
  }
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\dot3svc\\MigrationData", 0, 0x20006u, &hKey);
  if ( !v3 )
    v3 = RegSetValueExW(hKey, L"dot3svcMigrationDone", 0, 4u, (const BYTE *)&Data, 4u);
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x10) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 15, WPP_12e48a9d849435eac3405c86722d7b90_Traceguids, (unsigned int)v3);
  }
  if ( v3 > 0 )
    return (unsigned __int16)v3 | 0x80070000;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003d49c  mov     [rsp+arg_0], rbx
0x18003d4a1  mov     [rsp+Data], r8d
0x18003d4a6  mov     [rsp+hKey], rdx
0x18003d4ab  push    rdi
0x18003d4ac  sub     rsp, 30h
0x18003d4b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d4b7  lea     rdi, WPP_GLOBAL_Control
0x18003d4be  cmp     rcx, rdi
0x18003d4c1  jz      short loc_18003D4DE
0x18003d4c3  test    byte ptr [rcx+1Ch], 10h
0x18003d4c7  jz      short loc_18003D4DE
0x18003d4c9  mov     rcx, [rcx+10h]
0x18003d4cd  lea     r8, WPP_12e48a9d849435eac3405c86722d7b90_Traceguids
0x18003d4d4  mov     edx, 0Eh
0x18003d4d9  call    WPP_SF_
0x18003d4de  lea     rax, [rsp+38h+hKey]
0x18003d4e3  mov     [rsp+38h+hKey], 0
0x18003d4ec  mov     r9d, 20006h; samDesired
0x18003d4f2  mov     [rsp+38h+phkResult], rax; phkResult
0x18003d4f7  xor     r8d, r8d; ulOptions
0x18003d4fa  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\dot3svc\\Migration"...
0x18003d501  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d508  call    cs:__imp_RegOpenKeyExW
0x18003d50e  mov     ebx, eax
0x18003d510  test    eax, eax
0x18003d512  jnz     short loc_18003D53E
0x18003d514  mov     rcx, [rsp+38h+hKey]; hKey
0x18003d519  lea     r9d, [rax+4]; dwType
0x18003d51d  lea     rax, [rsp+38h+Data]
0x18003d522  mov     [rsp+38h+cbData], r9d; cbData
0x18003d527  xor     r8d, r8d; Reserved
0x18003d52a  mov     [rsp+38h+phkResult], rax; lpData
0x18003d52f  lea     rdx, aDot3svcmigrati; "dot3svcMigrationDone"
0x18003d536  call    cs:__imp_RegSetValueExW
0x18003d53c  mov     ebx, eax
0x18003d53e  mov     rcx, [rsp+38h+hKey]; hKey
0x18003d543  test    rcx, rcx
0x18003d546  jz      short loc_18003D54E
0x18003d548  call    cs:__imp_RegCloseKey
0x18003d54e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d555  cmp     rcx, rdi
0x18003d558  jz      short loc_18003D578
0x18003d55a  test    byte ptr [rcx+1Ch], 10h
0x18003d55e  jz      short loc_18003D578
0x18003d560  mov     rcx, [rcx+10h]
0x18003d564  lea     r8, WPP_12e48a9d849435eac3405c86722d7b90_Traceguids
0x18003d56b  mov     edx, 0Fh
0x18003d570  mov     r9d, ebx
0x18003d573  call    WPP_SF_d
0x18003d578  test    ebx, ebx
0x18003d57a  jle     short loc_18003D585
0x18003d57c  movzx   ebx, bx
0x18003d57f  or      ebx, 80070000h
0x18003d585  mov     eax, ebx
0x18003d587  mov     rbx, [rsp+38h+arg_0]
0x18003d58c  add     rsp, 30h
0x18003d590  pop     rdi
0x18003d591  retn
```
