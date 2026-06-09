# HrCreateAndInitializeINetCfg

- ea: `0x1800355a4`
- end: `0x1800356c7`
- name: `HrCreateAndInitializeINetCfg`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800356d0`

## callees

- `0x1800355a4`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800355e2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800355e2`
- `rtutils!TracePrintfW` at `0x180035609`
- `rtutils!TracePrintfW` at `0x18003563f`
- `rtutils!TracePrintfW` at `0x180035667`
- `rtutils!TracePrintfW` at `0x180035697`
- `rtutils!TracePrintfW` at `0x1800356b4`
- `rtutils!TracePrintfW` at `0x180035609`
- `rtutils!TracePrintfW` at `0x18003563f`
- `rtutils!TracePrintfW` at `0x180035667`
- `rtutils!TracePrintfW` at `0x180035697`
- `rtutils!TracePrintfW` at `0x1800356b4`

## string_xrefs

- `0x1800355ee`: `HrCreateAndInitializeINetCfg - CoCreateInstance(CLSID_CNetCfg)`
- `0x18003562a`: `HrCreateAndInitializeINetCfg - Initialize`
- `0x1800356aa`: `HrCreateAndInitializeINetCfg`

## pseudocode

```c
__int64 __fastcall HrCreateAndInitializeINetCfg(__int64 a1, _QWORD *a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  LPVOID v6; // rcx
  LPVOID v8; // [rsp+40h] [rbp+8h] BYREF

  *a2 = 0;
  v8 = 0;
  v3 = CoCreateInstance(&CLSID_CNetCfg, 0, 1u, &IID_INetCfg, &v8);
  v4 = v3;
  if ( v3 < 0 )
  {
    TracePrintfW(
      g_dwTraceHandle,
      L"%hs failed : hr = %08lx",
      "HrCreateAndInitializeINetCfg - CoCreateInstance(CLSID_CNetCfg)",
      (unsigned int)v3);
    goto LABEL_11;
  }
  TracePrintfW(
    g_dwTraceHandle,
    L"%hs succeeded : hr = %08lx",
    "HrCreateAndInitializeINetCfg - CoCreateInstance(CLSID_CNetCfg)",
    (unsigned int)v3);
  v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v8 + 24LL))(v8, 0);
  v4 = v5;
  if ( v5 < 0 )
  {
    TracePrintfW(
      g_dwTraceHandle,
      L"%hs failed : hr = %08lx",
      "HrCreateAndInitializeINetCfg - Initialize",
      (unsigned int)v5);
  }
  else
  {
    TracePrintfW(
      g_dwTraceHandle,
      L"%hs succeeded : hr = %08lx",
      "HrCreateAndInitializeINetCfg - Initialize",
      (unsigned int)v5);
    v6 = v8;
    *a2 = v8;
    if ( !v6 )
      goto LABEL_8;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 8LL))(v6);
  }
  if ( v8 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
LABEL_8:
  if ( (v4 & 0x80000000) != 0 )
  {
LABEL_11:
    TracePrintfW(g_dwTraceHandle, L"%hs failed : hr = %08lx", "HrCreateAndInitializeINetCfg", v4);
    return v4;
  }
  TracePrintfW(g_dwTraceHandle, L"%hs succeeded : hr = %08lx", "HrCreateAndInitializeINetCfg", v4);
  return v4;
}

```

## disassembly

```asm
0x1800355a4  mov     r11, rsp
0x1800355a7  mov     [r11+10h], rbx
0x1800355ab  mov     [r11+8], rcx
0x1800355af  push    rdi
0x1800355b0  sub     rsp, 30h
0x1800355b4  mov     rdi, rdx
0x1800355b7  mov     qword ptr [rdx], 0
0x1800355be  xor     edx, edx; pUnkOuter
0x1800355c0  mov     qword ptr [r11+8], 0
0x1800355c8  lea     rax, [r11+8]
0x1800355cc  lea     r9, IID_INetCfg; riid
0x1800355d3  mov     [r11-18h], rax
0x1800355d7  lea     rcx, CLSID_CNetCfg; rclsid
0x1800355de  lea     r8d, [rdx+1]; dwClsContext
0x1800355e2  call    cs:__imp_CoCreateInstance
0x1800355e8  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x1800355ee  lea     r8, aHrcreateandini; "HrCreateAndInitializeINetCfg - CoCreate"...
0x1800355f5  mov     ebx, eax
0x1800355f7  mov     r9d, eax
0x1800355fa  test    eax, eax
0x1800355fc  js      loc_180035690
0x180035602  lea     rdx, szFormat; "%hs succeeded : hr = %08lx"
0x180035609  call    cs:__imp_TracePrintfW
0x18003560f  mov     rcx, [rsp+38h+arg_0]
0x180035614  xor     edx, edx
0x180035616  mov     rax, [rcx]
0x180035619  mov     rax, [rax+18h]
0x18003561d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035622  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x180035628  mov     ebx, eax
0x18003562a  lea     r8, aHrcreateandini_1; "HrCreateAndInitializeINetCfg - Initiali"...
0x180035631  mov     r9d, eax
0x180035634  test    eax, eax
0x180035636  js      short loc_180035660
0x180035638  lea     rdx, szFormat; "%hs succeeded : hr = %08lx"
0x18003563f  call    cs:__imp_TracePrintfW
0x180035645  mov     rcx, [rsp+38h+arg_0]
0x18003564a  mov     [rdi], rcx
0x18003564d  test    rcx, rcx
0x180035650  jz      short loc_180035683
0x180035652  mov     rax, [rcx]
0x180035655  mov     rax, [rax+8]
0x180035659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003565e  jmp     short loc_18003566D
0x180035660  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x180035667  call    cs:__imp_TracePrintfW
0x18003566d  mov     rcx, [rsp+38h+arg_0]
0x180035672  test    rcx, rcx
0x180035675  jz      short loc_180035683
0x180035677  mov     rax, [rcx]
0x18003567a  mov     rax, [rax+10h]
0x18003567e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035683  test    ebx, ebx
0x180035685  js      short loc_18003569D
0x180035687  lea     rdx, szFormat; "%hs succeeded : hr = %08lx"
0x18003568e  jmp     short loc_1800356A4
0x180035690  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x180035697  call    cs:__imp_TracePrintfW
0x18003569d  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x1800356a4  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x1800356aa  lea     r8, aHrcreateandini_0; "HrCreateAndInitializeINetCfg"
0x1800356b1  mov     r9d, ebx
0x1800356b4  call    cs:__imp_TracePrintfW
0x1800356ba  mov     eax, ebx
0x1800356bc  mov     rbx, [rsp+38h+arg_8]
0x1800356c1  add     rsp, 30h
0x1800356c5  pop     rdi
0x1800356c6  retn
```
