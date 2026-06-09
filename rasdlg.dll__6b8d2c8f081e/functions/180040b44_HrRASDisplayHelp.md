# HrRASDisplayHelp

- ea: `0x180040b44`
- end: `0x180040bc2`
- name: `HrRASDisplayHelp`
- size: `126`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b07c`

## callees

- `0x180040b44`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180040bb4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180040bb4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040b7d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040b7d`
- `ole32!CoInitialize` at `0x180040b59`
- `ole32!CoInitialize` at `0x180040b59`

## pseudocode

```c
__int64 HrRASDisplayHelp()
{
  unsigned int v0; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = 0;
  CoInitialize(0);
  v0 = CoCreateInstance(
         &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
         0,
         1u,
         &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
         &ppv);
  if ( !v0 )
  {
    v0 = (*(__int64 (__fastcall **)(LPVOID, wchar_t *))(*(_QWORD *)ppv + 24LL))(ppv, c_szHelpbutton);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  CoUninitialize();
  return v0;
}

```

## disassembly

```asm
0x180040b44  mov     [rsp+arg_0], rcx
0x180040b49  push    rbx
0x180040b4a  sub     rsp, 30h
0x180040b4e  xor     ecx, ecx; pvReserved
0x180040b50  mov     [rsp+38h+arg_0], 0
0x180040b59  call    cs:__imp_CoInitialize
0x180040b5f  xor     edx, edx; pUnkOuter
0x180040b61  lea     rax, [rsp+38h+arg_0]
0x180040b66  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x180040b6d  mov     [rsp+38h+ppv], rax; ppv
0x180040b72  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x180040b79  lea     r8d, [rdx+1]; dwClsContext
0x180040b7d  call    cs:__imp_CoCreateInstance
0x180040b83  mov     ebx, eax
0x180040b85  test    eax, eax
0x180040b87  jnz     short loc_180040BB4
0x180040b89  mov     rcx, [rsp+38h+arg_0]
0x180040b8e  lea     rdx, c_szHelpbutton; "mshelp://windows/?id=c2a0e1e2-6036-49db"...
0x180040b95  mov     rax, [rcx]
0x180040b98  mov     rax, [rax+18h]
0x180040b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ba1  mov     rcx, [rsp+38h+arg_0]
0x180040ba6  mov     ebx, eax
0x180040ba8  mov     rax, [rcx]
0x180040bab  mov     rax, [rax+10h]
0x180040baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040bb4  call    cs:__imp_CoUninitialize
0x180040bba  mov     eax, ebx
0x180040bbc  add     rsp, 30h
0x180040bc0  pop     rbx
0x180040bc1  retn
```
