# IsModemPresent

- ea: `0x180023810`
- end: `0x18002395f`
- name: `IsModemPresent`
- size: `335`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b010`

## callees

- `0x180023810`
- `0x180026400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800238dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800238f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800238dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800238f6`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180023847`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180023847`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002391f`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002391f`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800238a0`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800238a0`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800238cb`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800238cb`
- `rtutils!TracePrintfExA` at `0x180023878`
- `rtutils!TracePrintfExA` at `0x180023916`
- `rtutils!TracePrintfExA` at `0x18002393f`
- `rtutils!TracePrintfExA` at `0x180023878`
- `rtutils!TracePrintfExA` at `0x180023916`
- `rtutils!TracePrintfExA` at `0x18002393f`

## string_xrefs

- `0x18002386e`: `IsModemPresent: DevObjCreateDeviceInfoList failed (0x%x)`

## pseudocode

```c
__int64 IsModemPresent()
{
  unsigned int v0; // esi
  __int64 DeviceInfoList; // rax
  __int64 v2; // rbp
  DWORD LastError; // eax
  DWORD v4; // eax
  DWORD v5; // eax
  _OWORD v7[2]; // [rsp+30h] [rbp-38h] BYREF

  v0 = 0;
  memset(v7, 0, sizeof(v7));
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v2 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    if ( g_dwTraceId == -1 )
      return v0;
    TracePrintfExA(g_dwTraceId, 0xCu, "IsModemPresent: DevObjCreateDeviceInfoList failed (0x%x)", LastError);
  }
  else
  {
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_MODEM, 0, 18, 0, 0) )
    {
      LODWORD(v7[0]) = 32;
      if ( (unsigned int)DevObjEnumDeviceInterfaces(v2, 0, &GUID_DEVINTERFACE_MODEM, 0, v7) )
      {
        v0 = 1;
      }
      else
      {
        v4 = GetLastError();
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "IsModemPresent: DevObjEnumDeviceInterfaces failed (0x%x)", v4);
      }
    }
    else
    {
      v5 = GetLastError();
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "IsModemPresent: DevObjGetClassDevs failed (0x%x)", v5);
    }
    DevObjDestroyDeviceInfoList(v2);
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "IsModemPresent: Returning %d", v0);
  return v0;
}

```

## disassembly

```asm
0x180023810  mov     [rsp+arg_0], rbp
0x180023815  push    rsi
0x180023816  sub     rsp, 60h
0x18002381a  mov     rax, cs:__security_cookie
0x180023821  xor     rax, rsp
0x180023824  mov     [rsp+68h+var_18], rax
0x180023829  xorps   xmm0, xmm0
0x18002382c  xor     esi, esi
0x18002382e  xor     r9d, r9d
0x180023831  mov     [rsp+68h+var_48], rsi
0x180023836  xor     r8d, r8d
0x180023839  xor     edx, edx
0x18002383b  xor     ecx, ecx
0x18002383d  movups  [rsp+68h+var_38], xmm0
0x180023842  movups  [rsp+68h+var_28], xmm0
0x180023847  call    cs:__imp_DevObjCreateDeviceInfoList
0x18002384d  mov     rbp, rax
0x180023850  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023854  jnz     short loc_180023883
0x180023856  call    cs:__imp_GetLastError
0x18002385c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180023862  cmp     ecx, 0FFFFFFFFh
0x180023865  jz      loc_180023945
0x18002386b  mov     r9d, eax
0x18002386e  lea     r8, aIsmodempresent_0; "IsModemPresent: DevObjCreateDeviceInfoL"...
0x180023875  lea     edx, [rsi+0Ch]; dwFlags
0x180023878  call    cs:__imp_TracePrintfExA
0x18002387e  jmp     loc_180023925
0x180023883  mov     [rsp+68h+var_40], rsi
0x180023888  lea     rdx, GUID_DEVINTERFACE_MODEM
0x18002388f  mov     r9d, 12h
0x180023895  mov     [rsp+68h+var_48], rsi
0x18002389a  xor     r8d, r8d
0x18002389d  mov     rcx, rbp
0x1800238a0  call    cs:__imp_DevObjGetClassDevs
0x1800238a6  test    eax, eax
0x1800238a8  jz      short loc_1800238F6
0x1800238aa  lea     rax, [rsp+68h+var_38]
0x1800238af  mov     dword ptr [rsp+68h+var_38], 20h ; ' '
0x1800238b7  xor     r9d, r9d
0x1800238ba  mov     [rsp+68h+var_48], rax
0x1800238bf  lea     r8, GUID_DEVINTERFACE_MODEM
0x1800238c6  xor     edx, edx
0x1800238c8  mov     rcx, rbp
0x1800238cb  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1800238d1  test    eax, eax
0x1800238d3  jz      short loc_1800238DC
0x1800238d5  mov     esi, 1
0x1800238da  jmp     short loc_18002391C
0x1800238dc  call    cs:__imp_GetLastError
0x1800238e2  mov     ecx, cs:g_dwTraceId
0x1800238e8  cmp     ecx, 0FFFFFFFFh
0x1800238eb  jz      short loc_18002391C
0x1800238ed  lea     r8, aIsmodempresent_1; "IsModemPresent: DevObjEnumDeviceInterfa"...
0x1800238f4  jmp     short loc_18002390E
0x1800238f6  call    cs:__imp_GetLastError
0x1800238fc  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180023902  cmp     ecx, 0FFFFFFFFh
0x180023905  jz      short loc_18002391C
0x180023907  lea     r8, aIsmodempresent; "IsModemPresent: DevObjGetClassDevs fail"...
0x18002390e  mov     r9d, eax
0x180023911  mov     edx, 0Ch; dwFlags
0x180023916  call    cs:__imp_TracePrintfExA
0x18002391c  mov     rcx, rbp
0x18002391f  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180023925  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002392b  cmp     ecx, 0FFFFFFFFh
0x18002392e  jz      short loc_180023945
0x180023930  mov     r9d, esi
0x180023933  lea     r8, aIsmodempresent_2; "IsModemPresent: Returning %d"
0x18002393a  mov     edx, 0Ch; dwFlags
0x18002393f  call    cs:__imp_TracePrintfExA
0x180023945  mov     eax, esi
0x180023947  mov     rcx, [rsp+68h+var_18]
0x18002394c  xor     rcx, rsp; StackCookie
0x18002394f  call    __security_check_cookie
0x180023954  mov     rbp, [rsp+68h+arg_0]
0x180023959  add     rsp, 60h
0x18002395d  pop     rsi
0x18002395e  retn
```
