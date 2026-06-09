# SetValue(HKEY__ *,ushort const *,ushort const *,uchar * const,ulong)

- ea: `0x180013458`
- end: `0x180013506`
- name: `?SetValue@@YAJPEAUHKEY__@@PEBG1QEAEK@Z`
- size: `174`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *const, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180012e24`

## callees

- `0x180013458`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013496`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800134f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800134f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800134ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800134ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001348c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001348c`

## pseudocode

```c
__int64 __fastcall SetValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, unsigned __int8 *const a4)
{
  int LastError; // eax
  unsigned int v7; // ebx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = a1;
  if ( a2 && RegOpenKeyExW(a1, a2, 0, 0xF003Fu, &hKey) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
LABEL_4:
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v7 = 0;
    if ( a4 )
    {
      LastError = RegSetValueExW(hKey, L"QueueId", 0, 4u, a4, 4u);
      if ( LastError )
      {
        if ( LastError <= 0 )
        {
          v7 = LastError;
          goto LABEL_5;
        }
        goto LABEL_4;
      }
    }
  }
LABEL_5:
  if ( hKey && a2 )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180013458  mov     r11, rsp
0x18001345b  mov     [r11+8], rbx
0x18001345f  mov     [r11+10h], rsi
0x180013463  mov     [r11+18h], r8
0x180013467  push    rdi
0x180013468  sub     rsp, 30h
0x18001346c  mov     [r11+18h], rcx
0x180013470  mov     rsi, r9
0x180013473  mov     rdi, rdx
0x180013476  test    rdx, rdx
0x180013479  jz      short loc_1800134D2
0x18001347b  lea     rax, [r11+18h]
0x18001347f  mov     r9d, 0F003Fh; samDesired
0x180013485  xor     r8d, r8d; ulOptions
0x180013488  mov     [r11-18h], rax
0x18001348c  call    cs:__imp_RegOpenKeyExW
0x180013492  test    eax, eax
0x180013494  jz      short loc_1800134D2
0x180013496  call    cs:__imp_GetLastError
0x18001349c  mov     ebx, eax
0x18001349e  test    eax, eax
0x1800134a0  jle     short loc_1800134AB
0x1800134a2  movzx   ebx, ax
0x1800134a5  or      ebx, 80070000h
0x1800134ab  mov     rcx, [rsp+38h+hKey]; hKey
0x1800134b0  test    rcx, rcx
0x1800134b3  jz      short loc_1800134C0
0x1800134b5  test    rdi, rdi
0x1800134b8  jz      short loc_1800134C0
0x1800134ba  call    cs:__imp_RegCloseKey
0x1800134c0  mov     rsi, [rsp+38h+arg_8]
0x1800134c5  mov     eax, ebx
0x1800134c7  mov     rbx, [rsp+38h+arg_0]
0x1800134cc  add     rsp, 30h
0x1800134d0  pop     rdi
0x1800134d1  retn
0x1800134d2  xor     ebx, ebx
0x1800134d4  test    rsi, rsi
0x1800134d7  jz      short loc_1800134AB
0x1800134d9  mov     rcx, [rsp+38h+hKey]; hKey
0x1800134de  lea     r9d, [rbx+4]; dwType
0x1800134e2  mov     [rsp+38h+cbData], r9d; cbData
0x1800134e7  lea     rdx, ?c_szQueueId@@3QBGB; "QueueId"
0x1800134ee  xor     r8d, r8d; Reserved
0x1800134f1  mov     [rsp+38h+lpData], rsi; lpData
0x1800134f6  call    cs:__imp_RegSetValueExW
0x1800134fc  test    eax, eax
0x1800134fe  jz      short loc_1800134AB
0x180013500  jg      short loc_1800134A2
0x180013502  mov     ebx, eax
0x180013504  jmp     short loc_1800134AB
```
