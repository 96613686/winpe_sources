# COMCallProcess(etCOMCall,ulong * const,_GUID * const)

- ea: `0x10122815`
- end: `0x10122847`
- name: `?COMCallProcess@@YGJW4etCOMCall@@QAKQAU_GUID@@@Z`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x10122850`
- `0x101229da`

## callees

- `0x10122815`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1012283d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1012283d`

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
0x10122815  mov     edi, edi
0x10122817  push    ebp
0x10122818  mov     ebp, esp
0x1012281a  sub     ecx, 1
0x1012281d  jz      short loc_1012282C
0x1012281f  sub     ecx, 3E7h
0x10122825  mov     eax, 80004005h
0x1012282a  jmp     short loc_10122843
0x1012282c  mov     ecx, [ebp+rclsid]
0x1012282f  push    dword ptr [edx+10h]; ppv
0x10122832  lea     eax, [ecx+30h]
0x10122835  push    eax; riid
0x10122836  push    dword ptr [edx+8]; dwClsContext
0x10122839  push    dword ptr [edx+4]; pUnkOuter
0x1012283c  push    ecx; rclsid
0x1012283d  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x10122843  pop     ebp
0x10122844  retn    4
```
