# RegisterInterfaceWorker

- ea: `0x180038220`
- end: `0x18003839d`
- name: `RegisterInterfaceWorker`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180038078`

## callees

- `0x180038220`
- `0x1800383a4`
- `0x180038470`
- `0x1800384ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038383`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038383`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038302`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003830c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038302`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003830c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800382da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800382da`

## pseudocode

```c
__int64 __fastcall RegisterInterfaceWorker(HKEY a1, __int64 a2, REGSAM a3)
{
  unsigned int v5; // edi
  unsigned int v6; // r8d
  const unsigned __int16 *v7; // rdx
  unsigned __int16 *v8; // r8
  HKEY v9; // r14
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  HKEY phkResult; // [rsp+78h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  phkResult = 0;
  v5 = -2147319780;
  if ( !FastRegCreateKey(a1, *(LPCWSTR *)a2, &hKey, a3) )
  {
    if ( !(unsigned int)FastRegSetValueEx(hKey, 0, v6, *(const unsigned __int16 **)(a2 + 8), *(_DWORD *)(a2 + 16)) )
    {
      v8 = *(unsigned __int16 **)(a2 + 24);
      if ( v8 && *(_QWORD *)(a2 + 40) && *(_QWORD *)(a2 + 56) )
      {
        if ( FastRegCreateSubKey(hKey, v7, v8, *(_DWORD *)(a2 + 32), a3) >= 0 )
        {
          v9 = hKey;
          if ( !RegOpenKeyExW(hKey, L"TypeLib", 0, a3, &phkResult)
            || !RegCreateKeyExW(v9, L"TypeLib", 0, 0, 0, a3, 0, &phkResult, 0) )
          {
            if ( !(unsigned int)FastRegSetValueEx(
                                  phkResult,
                                  0,
                                  v10,
                                  *(const unsigned __int16 **)(a2 + 40),
                                  *(_DWORD *)(a2 + 48)) )
              v5 = (unsigned int)FastRegSetValueEx(
                                   phkResult,
                                   L"Version",
                                   v11,
                                   *(const unsigned __int16 **)(a2 + 56),
                                   *(_DWORD *)(a2 + 64)) != 0
                 ? 0x8002801C
                 : 0;
            RegCloseKey(phkResult);
          }
        }
      }
      else
      {
        v5 = 0;
      }
    }
    RegCloseKey(hKey);
  }
  return v5;
}

```

## disassembly

```asm
0x180038220  mov     [rsp-18h+arg_0], rbx
0x180038225  mov     [rsp-18h+arg_10], rsi
0x18003822a  push    rbp
0x18003822b  push    rdi
0x18003822c  push    r14
0x18003822e  mov     rbp, rsp
0x180038231  sub     rsp, 50h
0x180038235  mov     esi, r8d
0x180038238  mov     [rbp+hKey], 0
0x180038240  mov     rbx, rdx
0x180038243  mov     [rbp+arg_8], 0
0x18003824b  mov     rdx, [rdx]; lpSubKey
0x18003824e  mov     r9d, r8d; samDesired
0x180038251  lea     r8, [rbp+hKey]; phkResult
0x180038255  mov     edi, 8002801Ch
0x18003825a  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@K@Z; FastRegCreateKey(HKEY__ *,ushort const *,HKEY__ * *,ulong)
0x18003825f  test    eax, eax
0x180038261  jnz     loc_180038312
0x180038267  mov     eax, [rbx+10h]
0x18003826a  xor     edx, edx; lpValueName
0x18003826c  mov     r9, [rbx+8]; unsigned __int16 *
0x180038270  mov     rcx, [rbp+hKey]; hKey
0x180038274  mov     dword ptr [rsp+50h+phkResult], eax; unsigned int
0x180038278  call    ?FastRegSetValueEx@@YAJPEAUHKEY__@@PEBGK1K@Z; FastRegSetValueEx(HKEY__ *,ushort const *,ulong,ushort const *,ulong)
0x18003827d  test    eax, eax
0x18003827f  jnz     loc_180038308
0x180038285  mov     r8, [rbx+18h]; unsigned __int16 *
0x180038289  test    r8, r8
0x18003828c  jz      loc_180038396
0x180038292  cmp     qword ptr [rbx+28h], 0
0x180038297  jz      loc_180038396
0x18003829d  cmp     qword ptr [rbx+38h], 0
0x1800382a2  jz      loc_180038396
0x1800382a8  mov     r9d, [rbx+20h]; int
0x1800382ac  mov     rcx, [rbp+hKey]; HKEY
0x1800382b0  mov     dword ptr [rsp+50h+phkResult], esi; unsigned int
0x1800382b4  call    ?FastRegCreateSubKey@@YAJPEAUHKEY__@@PEBGPEAGHK@Z; FastRegCreateSubKey(HKEY__ *,ushort const *,ushort *,int,ulong)
0x1800382b9  test    eax, eax
0x1800382bb  js      short loc_180038308
0x1800382bd  mov     r14, [rbp+hKey]
0x1800382c1  lea     rax, [rbp+arg_8]
0x1800382c5  mov     rcx, r14; hKey
0x1800382c8  mov     [rsp+50h+phkResult], rax; phkResult
0x1800382cd  mov     r9d, esi; samDesired
0x1800382d0  lea     rdx, ?TypeLib@Constants@Catalog@Com@@3QBGB; "TypeLib"
0x1800382d7  xor     r8d, r8d; ulOptions
0x1800382da  call    cs:__imp_RegOpenKeyExW
0x1800382e0  test    eax, eax
0x1800382e2  jnz     short loc_18003834C
0x1800382e4  mov     eax, [rbx+30h]
0x1800382e7  xor     edx, edx; lpValueName
0x1800382e9  mov     r9, [rbx+28h]; unsigned __int16 *
0x1800382ed  mov     rcx, [rbp+arg_8]; hKey
0x1800382f1  mov     dword ptr [rsp+50h+phkResult], eax; unsigned int
0x1800382f5  call    ?FastRegSetValueEx@@YAJPEAUHKEY__@@PEBGK1K@Z; FastRegSetValueEx(HKEY__ *,ushort const *,ulong,ushort const *,ulong)
0x1800382fa  test    eax, eax
0x1800382fc  jz      short loc_180038329
0x1800382fe  mov     rcx, [rbp+arg_8]; hKey
0x180038302  call    cs:__imp_RegCloseKey
0x180038308  mov     rcx, [rbp+hKey]; hKey
0x18003830c  call    cs:__imp_RegCloseKey
0x180038312  lea     r11, [rsp+50h+var_s0]
0x180038317  mov     eax, edi
0x180038319  mov     rbx, [r11+20h]
0x18003831d  mov     rsi, [r11+30h]
0x180038321  mov     rsp, r11
0x180038324  pop     r14
0x180038326  pop     rdi
0x180038327  pop     rbp
0x180038328  retn
0x180038329  mov     eax, [rbx+40h]
0x18003832c  lea     rdx, ?Version@Constants@Catalog@Com@@3QBGB; "Version"
0x180038333  mov     r9, [rbx+38h]; unsigned __int16 *
0x180038337  mov     rcx, [rbp+arg_8]; hKey
0x18003833b  mov     dword ptr [rsp+50h+phkResult], eax; unsigned int
0x18003833f  call    ?FastRegSetValueEx@@YAJPEAUHKEY__@@PEBGK1K@Z; FastRegSetValueEx(HKEY__ *,ushort const *,ulong,ushort const *,ulong)
0x180038344  neg     eax
0x180038346  sbb     ecx, ecx
0x180038348  and     edi, ecx
0x18003834a  jmp     short loc_1800382FE
0x18003834c  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x180038355  lea     rax, [rbp+arg_8]
0x180038359  mov     [rsp+50h+var_18], rax; phkResult
0x18003835e  lea     rdx, ?TypeLib@Constants@Catalog@Com@@3QBGB; "TypeLib"
0x180038365  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003836e  xor     r9d, r9d; lpClass
0x180038371  mov     [rsp+50h+samDesired], esi; samDesired
0x180038375  xor     r8d, r8d; Reserved
0x180038378  mov     rcx, r14; hKey
0x18003837b  mov     dword ptr [rsp+50h+phkResult], 0; dwOptions
0x180038383  call    cs:__imp_RegCreateKeyExW
0x180038389  test    eax, eax
0x18003838b  jz      loc_1800382E4
0x180038391  jmp     loc_180038308
0x180038396  xor     edi, edi
0x180038398  jmp     loc_180038308
```
