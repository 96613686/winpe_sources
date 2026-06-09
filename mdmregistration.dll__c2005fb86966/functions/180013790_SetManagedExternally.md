# SetManagedExternally

- ea: `0x180013790`
- end: `0x180013824`
- name: `SetManagedExternally`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180013790`
- `0x18003cd7c`
- `0x18003d170`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001380f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001380f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800137ea`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800137ea`

## pseudocode

```c
__int64 __fastcall SetManagedExternally(int a1)
{
  const WCHAR *EnrollmentsRootKey; // rax
  int v2; // ebx
  LSTATUS v3; // eax
  BOOL Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  Data = a1 > 0;
  EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
  v2 = EEDBManager::OpenHKEY(EnrollmentsRootKey, 131078, &hKey);
  if ( v2 >= 0 )
  {
    v3 = RegSetKeyValueW(hKey, 0, L"ExternallyManaged", 4u, &Data, 4u);
    v2 = v3;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180013790  push    rbx
0x180013792  sub     rsp, 30h
0x180013796  xor     eax, eax
0x180013798  mov     [rsp+38h+hKey], 0
0x1800137a1  test    ecx, ecx
0x1800137a3  setnle  al
0x1800137a6  mov     [rsp+38h+Data], eax
0x1800137aa  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x1800137af  mov     rcx, rax; lpSubKey
0x1800137b2  lea     r8, [rsp+38h+hKey]; HKEY *
0x1800137b7  mov     edx, 20006h; unsigned int
0x1800137bc  call    ?OpenHKEY@EEDBManager@@SAJPEBGKPEAPEAUHKEY__@@@Z; EEDBManager::OpenHKEY(ushort const *,ulong,HKEY__ * *)
0x1800137c1  mov     ebx, eax
0x1800137c3  test    eax, eax
0x1800137c5  js      short loc_180013805
0x1800137c7  mov     rcx, [rsp+38h+hKey]; hKey
0x1800137cc  lea     rax, [rsp+38h+Data]
0x1800137d1  mov     r9d, 4; dwType
0x1800137d7  lea     r8, aExternallymana; "ExternallyManaged"
0x1800137de  mov     [rsp+38h+cbData], r9d; cbData
0x1800137e3  xor     edx, edx; lpSubKey
0x1800137e5  mov     [rsp+38h+lpData], rax; lpData
0x1800137ea  call    cs:__imp_RegSetKeyValueW
0x1800137f1  nop     dword ptr [rax+rax+00h]
0x1800137f6  mov     ebx, eax
0x1800137f8  test    eax, eax
0x1800137fa  jle     short loc_180013805
0x1800137fc  movzx   ebx, ax
0x1800137ff  or      ebx, 80070000h
0x180013805  mov     rcx, [rsp+38h+hKey]; hKey
0x18001380a  test    rcx, rcx
0x18001380d  jz      short loc_18001381B
0x18001380f  call    cs:__imp_RegCloseKey
0x180013816  nop     dword ptr [rax+rax+00h]
0x18001381b  mov     eax, ebx
0x18001381d  add     rsp, 30h
0x180013821  pop     rbx
0x180013822  retn
```
