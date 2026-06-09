# SignalDeletedConnection(_GUID *)

- ea: `0x18002a758`
- end: `0x18002a7cd`
- name: `?SignalDeletedConnection@@YAJPEAU_GUID@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800268c0`

## callees

- `0x18002a758`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a78d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a78d`

## pseudocode

```c
__int64 __fastcall SignalDeletedConnection(struct _GUID *a1)
{
  HRESULT v2; // ebx
  LPVOID v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v2 = CoCreateInstance(&CLSID_ConnectionManager, 0, 0x8405u, &GUID_faedcf5f_31fe_11d1_aad2_00805fc1270e, &v4);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *))(*(_QWORD *)v4 + 40LL))(v4, a1);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002a758  mov     r11, rsp
0x18002a75b  mov     [r11+8], rbx
0x18002a75f  push    rdi
0x18002a760  sub     rsp, 30h
0x18002a764  mov     rdi, rcx
0x18002a767  mov     qword ptr [r11+10h], 0
0x18002a76f  lea     rax, [r11+10h]
0x18002a773  xor     edx, edx; pUnkOuter
0x18002a775  lea     rcx, CLSID_ConnectionManager; rclsid
0x18002a77c  mov     [r11-18h], rax
0x18002a780  lea     r9, _GUID_faedcf5f_31fe_11d1_aad2_00805fc1270e; riid
0x18002a787  mov     r8d, 8405h; dwClsContext
0x18002a78d  call    cs:__imp_CoCreateInstance
0x18002a793  mov     ebx, eax
0x18002a795  test    eax, eax
0x18002a797  js      short loc_18002A7C0
0x18002a799  mov     rcx, [rsp+38h+arg_8]
0x18002a79e  mov     rdx, rdi
0x18002a7a1  mov     rax, [rcx]
0x18002a7a4  mov     rax, [rax+28h]
0x18002a7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7ad  mov     rcx, [rsp+38h+arg_8]
0x18002a7b2  mov     ebx, eax
0x18002a7b4  mov     rax, [rcx]
0x18002a7b7  mov     rax, [rax+10h]
0x18002a7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7c0  mov     eax, ebx
0x18002a7c2  mov     rbx, [rsp+38h+arg_0]
0x18002a7c7  add     rsp, 30h
0x18002a7cb  pop     rdi
0x18002a7cc  retn
```
