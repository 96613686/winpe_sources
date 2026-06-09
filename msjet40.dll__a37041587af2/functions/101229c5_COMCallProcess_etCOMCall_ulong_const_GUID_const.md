# COMCallProcess(etCOMCall,ulong * const,_GUID * const)

- ea: `0x101229c5`
- end: `0x101229f7`
- name: `?COMCallProcess@@YGJW4etCOMCall@@QAKQAU_GUID@@@Z`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x10122a00`
- `0x10122b8a`

## callees

- `0x101229c5`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x101229ed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x101229ed`

## pseudocode

```c
HRESULT __fastcall COMCallProcess(int a1, int a2, IID *rclsid)
{
  if ( a1 == 1 )
    return CoCreateInstance(rclsid, *(LPUNKNOWN *)(a2 + 4), *(_DWORD *)(a2 + 8), rclsid + 3, *(LPVOID **)(a2 + 16));
  else
    return -2147467259;
}

```

## disassembly

```asm
0x101229c5  mov     edi, edi
0x101229c7  push    ebp
0x101229c8  mov     ebp, esp
0x101229ca  sub     ecx, 1
0x101229cd  jz      short loc_101229DC
0x101229cf  sub     ecx, 3E7h
0x101229d5  mov     eax, 80004005h
0x101229da  jmp     short loc_101229F3
0x101229dc  mov     ecx, [ebp+rclsid]
0x101229df  push    dword ptr [edx+10h]; ppv
0x101229e2  lea     eax, [ecx+30h]
0x101229e5  push    eax; riid
0x101229e6  push    dword ptr [edx+8]; dwClsContext
0x101229e9  push    dword ptr [edx+4]; pUnkOuter
0x101229ec  push    ecx; rclsid
0x101229ed  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x101229f3  pop     ebp
0x101229f4  retn    4
```
