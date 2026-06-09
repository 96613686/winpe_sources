# NcbCheckApplicationCapability

- ea: `0x18000e0e8`
- end: `0x18000e1c6`
- name: `NcbCheckApplicationCapability`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000dea0`

## callees

- `0x18000e0e8`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e19c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e19c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e14c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e14c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000e119`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000e119`

## pseudocode

```c
__int64 __fastcall NcbCheckApplicationCapability(__int64 a1, bool *a2)
{
  __int64 result; // rax
  HRESULT v5; // ebx
  LPVOID v6; // rcx
  int v7; // [rsp+48h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  if ( !a2 )
    return 87;
  *a2 = 0;
  v5 = CoInitializeEx(0, 0);
  if ( v5 >= 0 )
  {
    ppv = 0;
    v5 = CoCreateInstance(&CLSID_BackgroundTaskCapability, 0, 1u, &IID_IBackgroundTaskCapability, &ppv);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64, int *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             a1,
             0,
             2,
             &v7);
      v6 = ppv;
      *a2 = v7 != 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
    }
    CoUninitialize();
  }
  result = (unsigned __int16)v5;
  if ( (v5 & 0x1FFF0000) != 0x70000 )
    return (unsigned int)v5;
  return result;
}

```

## disassembly

```asm
0x18000e0e8  mov     [rsp+arg_0], rbx
0x18000e0ed  mov     [rsp+arg_18], rsi
0x18000e0f2  push    rdi
0x18000e0f3  sub     rsp, 30h
0x18000e0f7  mov     [rsp+38h+arg_8], 0
0x18000e0ff  mov     rdi, rdx
0x18000e102  mov     rsi, rcx
0x18000e105  test    rdx, rdx
0x18000e108  jnz     short loc_18000E112
0x18000e10a  lea     eax, [rdx+57h]
0x18000e10d  jmp     loc_18000E1B6
0x18000e112  mov     byte ptr [rdx], 0
0x18000e115  xor     ecx, ecx; pvReserved
0x18000e117  xor     edx, edx; dwCoInit
0x18000e119  call    cs:__imp_CoInitializeEx
0x18000e11f  mov     ebx, eax
0x18000e121  test    eax, eax
0x18000e123  js      short loc_18000E1A2
0x18000e125  xor     edx, edx; pUnkOuter
0x18000e127  mov     [rsp+38h+arg_10], 0
0x18000e130  lea     rax, [rsp+38h+arg_10]
0x18000e135  lea     r9, IID_IBackgroundTaskCapability; riid
0x18000e13c  mov     [rsp+38h+ppv], rax; ppv
0x18000e141  lea     rcx, CLSID_BackgroundTaskCapability; rclsid
0x18000e148  lea     r8d, [rdx+1]; dwClsContext
0x18000e14c  call    cs:__imp_CoCreateInstance
0x18000e152  mov     ebx, eax
0x18000e154  test    eax, eax
0x18000e156  js      short loc_18000E19C
0x18000e158  mov     rcx, [rsp+38h+arg_10]
0x18000e15d  lea     rdx, [rsp+38h+arg_8]
0x18000e162  mov     [rsp+38h+ppv], rdx
0x18000e167  mov     r9d, 2
0x18000e16d  xor     r8d, r8d
0x18000e170  mov     rdx, rsi
0x18000e173  mov     rax, [rcx]
0x18000e176  mov     rax, [rax+18h]
0x18000e17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e17f  cmp     [rsp+38h+arg_8], 0
0x18000e184  mov     ebx, eax
0x18000e186  mov     rcx, [rsp+38h+arg_10]
0x18000e18b  setnz   al
0x18000e18e  mov     [rdi], al
0x18000e190  mov     rax, [rcx]
0x18000e193  mov     rax, [rax+10h]
0x18000e197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e19c  call    cs:__imp_CoUninitialize
0x18000e1a2  mov     ecx, ebx
0x18000e1a4  movzx   eax, bx
0x18000e1a7  and     ecx, 1FFF0000h
0x18000e1ad  cmp     ecx, 70000h
0x18000e1b3  cmovnz  eax, ebx
0x18000e1b6  mov     rbx, [rsp+38h+arg_0]
0x18000e1bb  mov     rsi, [rsp+38h+arg_18]
0x18000e1c0  add     rsp, 30h
0x18000e1c4  pop     rdi
0x18000e1c5  retn
```
