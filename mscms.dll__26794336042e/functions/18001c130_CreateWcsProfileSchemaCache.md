# CreateWcsProfileSchemaCache

- ea: `0x18001c130`
- end: `0x18001c1fb`
- name: `CreateWcsProfileSchemaCache`
- size: `203`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800071e4`

## callees

- `0x18001c130`
- `0x18001c204`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c15a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c15a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c18d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c18d`

## string_xrefs

- `0x18001c14a`: `mscms.dll`

## pseudocode

```c
__int64 __fastcall CreateWcsProfileSchemaCache(unsigned int a1, __int64 a2, __int64 a3, LPVOID *a4)
{
  HMODULE ModuleHandleW; // rbp
  HRESULT v9; // ebx
  __int64 v10; // rdi
  LPVOID v11; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-48h] BYREF

  ppv = 0;
  ModuleHandleW = GetModuleHandleW(L"mscms.dll");
  if ( ModuleHandleW )
  {
    v9 = CoCreateInstance(&CLSID_XMLSchemaCache60, 0, 1u, &IID_IXMLDOMSchemaCollection, &ppv);
    if ( v9 >= 0 )
    {
      v10 = 0;
      if ( a1 )
      {
        while ( 1 )
        {
          v9 = AddSchemaFromResourceToCache(
                 ModuleHandleW,
                 *(unsigned int *)(a2 + 4 * v10),
                 *(_QWORD *)(a3 + 8 * v10),
                 ppv);
          if ( v9 < 0 )
            break;
          v10 = (unsigned int)(v10 + 1);
          if ( (unsigned int)v10 >= a1 )
            goto LABEL_7;
        }
      }
      else
      {
LABEL_7:
        v11 = ppv;
        *a4 = ppv;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
  }
  else
  {
    v9 = -2147467259;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001c130  push    rbx
0x18001c132  push    rbp
0x18001c133  push    rsi
0x18001c134  push    rdi
0x18001c135  push    r12
0x18001c137  push    r14
0x18001c139  push    r15
0x18001c13b  sub     rsp, 40h
0x18001c13f  mov     esi, ecx
0x18001c141  mov     [rsp+78h+var_48], 0
0x18001c14a  lea     rcx, ModuleName; "mscms.dll"
0x18001c151  mov     r14, r9
0x18001c154  mov     r15, r8
0x18001c157  mov     r12, rdx
0x18001c15a  call    cs:__imp_GetModuleHandleW
0x18001c160  mov     rbp, rax
0x18001c163  test    rax, rax
0x18001c166  jnz     short loc_18001C16F
0x18001c168  mov     ebx, 80004005h
0x18001c16d  jmp     short loc_18001C1D4
0x18001c16f  xor     edx, edx; pUnkOuter
0x18001c171  lea     rax, [rsp+78h+var_48]
0x18001c176  lea     r9, IID_IXMLDOMSchemaCollection; riid
0x18001c17d  mov     [rsp+78h+ppv], rax; ppv
0x18001c182  lea     rcx, CLSID_XMLSchemaCache60; rclsid
0x18001c189  lea     r8d, [rdx+1]; dwClsContext
0x18001c18d  call    cs:__imp_CoCreateInstance
0x18001c193  mov     ebx, eax
0x18001c195  test    eax, eax
0x18001c197  js      short loc_18001C1D4
0x18001c199  xor     edi, edi
0x18001c19b  test    esi, esi
0x18001c19d  jz      short loc_18001C1C0
0x18001c19f  mov     r9, [rsp+78h+var_48]
0x18001c1a4  mov     rcx, rbp
0x18001c1a7  mov     r8, [r15+rdi*8]
0x18001c1ab  mov     edx, [r12+rdi*4]
0x18001c1af  call    AddSchemaFromResourceToCache
0x18001c1b4  mov     ebx, eax
0x18001c1b6  test    eax, eax
0x18001c1b8  js      short loc_18001C1D4
0x18001c1ba  inc     edi
0x18001c1bc  cmp     edi, esi
0x18001c1be  jb      short loc_18001C19F
0x18001c1c0  mov     rcx, [rsp+78h+var_48]
0x18001c1c5  mov     [r14], rcx
0x18001c1c8  mov     rax, [rcx]
0x18001c1cb  mov     rax, [rax+8]
0x18001c1cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1d4  mov     rcx, [rsp+78h+var_48]
0x18001c1d9  test    rcx, rcx
0x18001c1dc  jz      short loc_18001C1EA
0x18001c1de  mov     rax, [rcx]
0x18001c1e1  mov     rax, [rax+10h]
0x18001c1e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1ea  mov     eax, ebx
0x18001c1ec  add     rsp, 40h
0x18001c1f0  pop     r15
0x18001c1f2  pop     r14
0x18001c1f4  pop     r12
0x18001c1f6  pop     rdi
0x18001c1f7  pop     rsi
0x18001c1f8  pop     rbp
0x18001c1f9  pop     rbx
0x18001c1fa  retn
```
