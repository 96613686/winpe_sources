# IsModemPresent

- ea: `0x1800244b8`
- end: `0x180024644`
- name: `IsModemPresent`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b230`

## callees

- `0x1800244b8`
- `0x1800273d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800245a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800245c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800245a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800245c2`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800244ef`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800244ef`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800245f7`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800245f7`
- `DEVOBJ!DevObjGetClassDevs` at `0x18002455a`
- `DEVOBJ!DevObjGetClassDevs` at `0x18002455a`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18002458b`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18002458b`
- `rtutils!TracePrintfExA` at `0x18002452c`
- `rtutils!TracePrintfExA` at `0x1800245e8`
- `rtutils!TracePrintfExA` at `0x18002461d`
- `rtutils!TracePrintfExA` at `0x18002452c`
- `rtutils!TracePrintfExA` at `0x1800245e8`
- `rtutils!TracePrintfExA` at `0x18002461d`

## string_xrefs

- `0x180024522`: `IsModemPresent: DevObjCreateDeviceInfoList failed (0x%x)`

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
0x1800244b8  mov     [rsp+arg_0], rbp
0x1800244bd  push    rsi
0x1800244be  sub     rsp, 60h
0x1800244c2  mov     rax, cs:__security_cookie
0x1800244c9  xor     rax, rsp
0x1800244cc  mov     [rsp+68h+var_18], rax
0x1800244d1  xorps   xmm0, xmm0
0x1800244d4  xor     esi, esi
0x1800244d6  xor     r9d, r9d
0x1800244d9  mov     [rsp+68h+var_48], rsi
0x1800244de  xor     r8d, r8d
0x1800244e1  xor     edx, edx
0x1800244e3  xor     ecx, ecx
0x1800244e5  movups  [rsp+68h+var_38], xmm0
0x1800244ea  movups  [rsp+68h+var_28], xmm0
0x1800244ef  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800244f6  nop     dword ptr [rax+rax+00h]
0x1800244fb  mov     rbp, rax
0x1800244fe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024502  jnz     short loc_18002453D
0x180024504  call    cs:__imp_GetLastError
0x18002450b  nop     dword ptr [rax+rax+00h]
0x180024510  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180024516  cmp     ecx, 0FFFFFFFFh
0x180024519  jz      loc_180024629
0x18002451f  mov     r9d, eax
0x180024522  lea     r8, aIsmodempresent_0; "IsModemPresent: DevObjCreateDeviceInfoL"...
0x180024529  lea     edx, [rsi+0Ch]; dwFlags
0x18002452c  call    cs:__imp_TracePrintfExA
0x180024533  nop     dword ptr [rax+rax+00h]
0x180024538  jmp     loc_180024603
0x18002453d  mov     [rsp+68h+var_40], rsi
0x180024542  lea     rdx, GUID_DEVINTERFACE_MODEM
0x180024549  mov     r9d, 12h
0x18002454f  mov     [rsp+68h+var_48], rsi
0x180024554  xor     r8d, r8d
0x180024557  mov     rcx, rbp
0x18002455a  call    cs:__imp_DevObjGetClassDevs
0x180024561  nop     dword ptr [rax+rax+00h]
0x180024566  test    eax, eax
0x180024568  jz      short loc_1800245C2
0x18002456a  lea     rax, [rsp+68h+var_38]
0x18002456f  mov     dword ptr [rsp+68h+var_38], 20h ; ' '
0x180024577  xor     r9d, r9d
0x18002457a  mov     [rsp+68h+var_48], rax
0x18002457f  lea     r8, GUID_DEVINTERFACE_MODEM
0x180024586  xor     edx, edx
0x180024588  mov     rcx, rbp
0x18002458b  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180024592  nop     dword ptr [rax+rax+00h]
0x180024597  test    eax, eax
0x180024599  jz      short loc_1800245A2
0x18002459b  mov     esi, 1
0x1800245a0  jmp     short loc_1800245F4
0x1800245a2  call    cs:__imp_GetLastError
0x1800245a9  nop     dword ptr [rax+rax+00h]
0x1800245ae  mov     ecx, cs:g_dwTraceId
0x1800245b4  cmp     ecx, 0FFFFFFFFh
0x1800245b7  jz      short loc_1800245F4
0x1800245b9  lea     r8, aIsmodempresent_1; "IsModemPresent: DevObjEnumDeviceInterfa"...
0x1800245c0  jmp     short loc_1800245E0
0x1800245c2  call    cs:__imp_GetLastError
0x1800245c9  nop     dword ptr [rax+rax+00h]
0x1800245ce  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800245d4  cmp     ecx, 0FFFFFFFFh
0x1800245d7  jz      short loc_1800245F4
0x1800245d9  lea     r8, aIsmodempresent; "IsModemPresent: DevObjGetClassDevs fail"...
0x1800245e0  mov     r9d, eax
0x1800245e3  mov     edx, 0Ch; dwFlags
0x1800245e8  call    cs:__imp_TracePrintfExA
0x1800245ef  nop     dword ptr [rax+rax+00h]
0x1800245f4  mov     rcx, rbp
0x1800245f7  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800245fe  nop     dword ptr [rax+rax+00h]
0x180024603  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180024609  cmp     ecx, 0FFFFFFFFh
0x18002460c  jz      short loc_180024629
0x18002460e  mov     r9d, esi
0x180024611  lea     r8, aIsmodempresent_2; "IsModemPresent: Returning %d"
0x180024618  mov     edx, 0Ch; dwFlags
0x18002461d  call    cs:__imp_TracePrintfExA
0x180024624  nop     dword ptr [rax+rax+00h]
0x180024629  mov     eax, esi
0x18002462b  mov     rcx, [rsp+68h+var_18]
0x180024630  xor     rcx, rsp; StackCookie
0x180024633  call    __security_check_cookie
0x180024638  mov     rbp, [rsp+68h+arg_0]
0x18002463d  add     rsp, 60h
0x180024641  pop     rsi
0x180024642  retn
```
