# lrIsModemRasEnabled

- ea: `0x1800167c8`
- end: `0x180016940`
- name: `lrIsModemRasEnabled`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000de88`

## callees

- `0x1800166e0`
- `0x1800167c8`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016840`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016840`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001691a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001691a`
- `rtutils!TracePrintfExA` at `0x180016861`
- `rtutils!TracePrintfExA` at `0x18001689e`
- `rtutils!TracePrintfExA` at `0x1800168b8`
- `rtutils!TracePrintfExA` at `0x1800168ed`
- `rtutils!TracePrintfExA` at `0x18001690a`
- `rtutils!TracePrintfExA` at `0x180016861`
- `rtutils!TracePrintfExA` at `0x18001689e`
- `rtutils!TracePrintfExA` at `0x1800168b8`
- `rtutils!TracePrintfExA` at `0x1800168ed`
- `rtutils!TracePrintfExA` at `0x18001690a`

## string_xrefs

- `0x180016852`: `dwFindModemPortUsage: Failed to create/open RAS key under modem class. 0x%x`

## pseudocode

```c
__int64 __fastcall lrIsModemRasEnabled(HKEY a1, unsigned int *a2, _DWORD *a3)
{
  unsigned int v3; // ebx
  LSTATUS v6; // eax
  unsigned int v7; // edi
  int v8; // eax
  unsigned int v9; // eax
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF
  DWORD v12; // [rsp+58h] [rbp-30h] BYREF

  v3 = *a2;
  *a3 = 0;
  *a2 = 0;
  hKey = 0;
  v12 = 0;
  v6 = RegCreateKeyExW(a1, L"Clients\\Ras", 0, 0, 0, 0x2001Fu, 0, &hKey, &v12);
  v7 = v6;
  if ( v6 )
  {
    TracePrintfExA(
      dwTraceId,
      0x10006u,
      "dwFindModemPortUsage: Failed to create/open RAS key under modem class. 0x%x",
      v6);
  }
  else
  {
    v8 = lrCheckValue(hKey, L"EnableForRas", a2, v3);
    if ( v8 )
      TracePrintfExA(dwTraceId, 0x10006u, "dwFindModemPortUsage: lrCheckValue failed for RasEnabled. %d", v8);
    if ( !*a2 )
      TracePrintfExA(dwTraceId, 0x10006u, "dwFindModemPortUsage: Modem is not enabled for RAS");
    v9 = lrCheckValue(hKey, L"EnableForRouting", a3, 0);
    v7 = v9;
    if ( v9 )
    {
      TracePrintfExA(dwTraceId, 0x10006u, "dwFindModemPortUsage: lrCheckValue failed for RouterEnabled. %d", v9);
      v7 = 0;
    }
    if ( !*a3 )
      TracePrintfExA(dwTraceId, 0x10006u, "dwFindModemPortUsage: Modem is not enabled for Routing");
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x1800167c8  mov     r11, rsp
0x1800167cb  mov     [r11+20h], rbx
0x1800167cf  push    rsi
0x1800167d0  push    rdi
0x1800167d1  push    r14
0x1800167d3  sub     rsp, 70h
0x1800167d7  mov     rax, cs:__security_cookie
0x1800167de  xor     rax, rsp
0x1800167e1  mov     [rsp+88h+var_28], rax
0x1800167e6  mov     ebx, [rdx]
0x1800167e8  lea     rax, [r11-30h]
0x1800167ec  mov     [r11-48h], rax
0x1800167f0  mov     r14, r8
0x1800167f3  mov     dword ptr [r8], 0
0x1800167fa  lea     rax, [r11-38h]
0x1800167fe  mov     [r11-50h], rax
0x180016802  mov     rsi, rdx
0x180016805  mov     qword ptr [r11-58h], 0
0x18001680d  xor     r9d, r9d; lpClass
0x180016810  mov     dword ptr [rdx], 0
0x180016816  xor     r8d, r8d; Reserved
0x180016819  mov     [rsp+88h+samDesired], 2001Fh; samDesired
0x180016821  lea     rdx, aClientsRas; "Clients\\Ras"
0x180016828  mov     [rsp+88h+dwOptions], 0; dwOptions
0x180016830  mov     qword ptr [r11-38h], 0
0x180016838  mov     [rsp+88h+var_30], 0
0x180016840  call    cs:__imp_RegCreateKeyExW
0x180016846  mov     edi, eax
0x180016848  test    eax, eax
0x18001684a  jz      short loc_18001686C
0x18001684c  mov     ecx, cs:dwTraceId; dwTraceID
0x180016852  lea     r8, aDwfindmodempor_0; "dwFindModemPortUsage: Failed to create/"...
0x180016859  mov     r9d, eax
0x18001685c  mov     edx, 10006h; dwFlags
0x180016861  call    cs:__imp_TracePrintfExA
0x180016867  jmp     loc_180016910
0x18001686c  mov     rcx, [rsp+88h+hKey]
0x180016871  lea     rdx, aEnableforras; "EnableForRas"
0x180016878  mov     r9d, ebx
0x18001687b  mov     r8, rsi
0x18001687e  call    lrCheckValue
0x180016883  mov     ebx, 10006h
0x180016888  test    eax, eax
0x18001688a  jz      short loc_1800168A4
0x18001688c  mov     ecx, cs:dwTraceId; dwTraceID
0x180016892  lea     r8, aDwfindmodempor; "dwFindModemPortUsage: lrCheckValue fail"...
0x180016899  mov     r9d, eax
0x18001689c  mov     edx, ebx; dwFlags
0x18001689e  call    cs:__imp_TracePrintfExA
0x1800168a4  cmp     dword ptr [rsi], 0
0x1800168a7  jnz     short loc_1800168BE
0x1800168a9  mov     ecx, cs:dwTraceId; dwTraceID
0x1800168af  lea     r8, aDwfindmodempor_1; "dwFindModemPortUsage: Modem is not enab"...
0x1800168b6  mov     edx, ebx; dwFlags
0x1800168b8  call    cs:__imp_TracePrintfExA
0x1800168be  mov     rcx, [rsp+88h+hKey]
0x1800168c3  lea     rdx, aEnableforrouti; "EnableForRouting"
0x1800168ca  xor     r9d, r9d
0x1800168cd  mov     r8, r14
0x1800168d0  call    lrCheckValue
0x1800168d5  mov     edi, eax
0x1800168d7  test    eax, eax
0x1800168d9  jz      short loc_1800168F5
0x1800168db  mov     ecx, cs:dwTraceId; dwTraceID
0x1800168e1  lea     r8, aDwfindmodempor_3; "dwFindModemPortUsage: lrCheckValue fail"...
0x1800168e8  mov     r9d, eax
0x1800168eb  mov     edx, ebx; dwFlags
0x1800168ed  call    cs:__imp_TracePrintfExA
0x1800168f3  xor     edi, edi
0x1800168f5  cmp     dword ptr [r14], 0
0x1800168f9  jnz     short loc_180016910
0x1800168fb  mov     ecx, cs:dwTraceId; dwTraceID
0x180016901  lea     r8, aDwfindmodempor_2; "dwFindModemPortUsage: Modem is not enab"...
0x180016908  mov     edx, ebx; dwFlags
0x18001690a  call    cs:__imp_TracePrintfExA
0x180016910  mov     rcx, [rsp+88h+hKey]; hKey
0x180016915  test    rcx, rcx
0x180016918  jz      short loc_180016920
0x18001691a  call    cs:__imp_RegCloseKey
0x180016920  mov     eax, edi
0x180016922  mov     rcx, [rsp+88h+var_28]
0x180016927  xor     rcx, rsp; StackCookie
0x18001692a  call    __security_check_cookie
0x18001692f  mov     rbx, [rsp+88h+arg_18]
0x180016937  add     rsp, 70h
0x18001693b  pop     r14
0x18001693d  pop     rdi
0x18001693e  pop     rsi
0x18001693f  retn
```
