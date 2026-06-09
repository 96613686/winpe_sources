# OpenProgramsAndFeaturesCPL(void)

- ea: `0x14000e0ec`
- end: `0x14000e155`
- name: `?OpenProgramsAndFeaturesCPL@@YAXXZ`
- size: `105`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007cf0`
- `0x14000de50`

## callees

- `0x14000e0ec`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000e117`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000e117`

## pseudocode

```c
void OpenProgramsAndFeaturesCPL(void)
{
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = 0;
  if ( CoCreateInstance(&CLSID_OpenControlPanel, 0, 1u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, &ppv) >= 0 )
  {
    (*(void (__fastcall **)(LPVOID, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
      ppv,
      L"Microsoft.ProgramsAndFeatures",
      0,
      0);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
}

```

## disassembly

```asm
0x14000e0ec  sub     rsp, 38h
0x14000e0f0  xor     edx, edx; pUnkOuter
0x14000e0f2  mov     [rsp+38h+arg_0], 0
0x14000e0fb  lea     rax, [rsp+38h+arg_0]
0x14000e100  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x14000e107  mov     [rsp+38h+ppv], rax; ppv
0x14000e10c  lea     rcx, CLSID_OpenControlPanel; rclsid
0x14000e113  lea     r8d, [rdx+1]; dwClsContext
0x14000e117  call    cs:__imp_CoCreateInstance
0x14000e11d  test    eax, eax
0x14000e11f  js      short loc_14000E150
0x14000e121  mov     rcx, [rsp+38h+arg_0]
0x14000e126  lea     rdx, aMicrosoftProgr; "Microsoft.ProgramsAndFeatures"
0x14000e12d  xor     r9d, r9d
0x14000e130  xor     r8d, r8d
0x14000e133  mov     rax, [rcx]
0x14000e136  mov     rax, [rax+18h]
0x14000e13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e13f  mov     rcx, [rsp+38h+arg_0]
0x14000e144  mov     rax, [rcx]
0x14000e147  mov     rax, [rax+10h]
0x14000e14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e150  add     rsp, 38h
0x14000e154  retn
```
