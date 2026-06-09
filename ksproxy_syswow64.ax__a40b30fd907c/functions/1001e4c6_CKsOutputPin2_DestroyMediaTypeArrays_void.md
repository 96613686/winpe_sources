# CKsOutputPin2::DestroyMediaTypeArrays(void)

- ea: `0x1001e4c6`
- end: `0x1001e5a7`
- name: `?DestroyMediaTypeArrays@CKsOutputPin2@@QAEXXZ`
- size: `225`
- prototype: `void __thiscall(CKsOutputPin2 *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x1001a73d`
- `0x1001e1f8`

## callees

- `0x1001e4c6`
- `0x1003a6f2`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1001e53a`
- `ole32!CoTaskMemFree` at `0x1001e557`
- `ole32!CoTaskMemFree` at `0x1001e57a`
- `ole32!CoTaskMemFree` at `0x1001e591`
- `ole32!CoTaskMemFree` at `0x1001e53a`
- `ole32!CoTaskMemFree` at `0x1001e557`
- `ole32!CoTaskMemFree` at `0x1001e57a`
- `ole32!CoTaskMemFree` at `0x1001e591`

## pseudocode

```c
void __thiscall CKsOutputPin2::DestroyMediaTypeArrays(CKsOutputPin2 *this)
{
  unsigned int i; // edi
  unsigned int j; // edi
  int v4; // eax
  int v5; // eax

  if ( *((_DWORD *)this + 198) )
  {
    for ( i = 0; i < *((_DWORD *)this + 199); ++i )
      operator delete[](*(void **)(*((_DWORD *)this + 198) + 4 * i));
    if ( *((_DWORD *)this + 198) )
    {
      operator delete[](*((void **)this + 198));
      *((_DWORD *)this + 198) = 0;
    }
  }
  *((_DWORD *)this + 199) = 0;
  if ( *((_DWORD *)this + 200) )
  {
    for ( j = 0; j < *((_DWORD *)this + 202); ++j )
    {
      v4 = *((_DWORD *)this + 201);
      if ( v4 && *(_DWORD *)(v4 + 4 * j) )
      {
        CoTaskMemFree(*(LPVOID *)(v4 + 4 * j));
        *(_DWORD *)(*((_DWORD *)this + 201) + 4 * j) = 0;
      }
      v5 = *((_DWORD *)this + 200);
      if ( *(_DWORD *)(v5 + 4 * j) )
      {
        CoTaskMemFree(*(LPVOID *)(v5 + 4 * j));
        *(_DWORD *)(*((_DWORD *)this + 200) + 4 * j) = 0;
      }
    }
    if ( *((_DWORD *)this + 201) )
    {
      CoTaskMemFree(*((LPVOID *)this + 201));
      *((_DWORD *)this + 201) = 0;
    }
    if ( *((_DWORD *)this + 200) )
    {
      CoTaskMemFree(*((LPVOID *)this + 200));
      *((_DWORD *)this + 200) = 0;
    }
  }
  *((_DWORD *)this + 202) = 0;
}

```

## disassembly

```asm
0x1001e4c6  mov     edi, edi
0x1001e4c8  push    ebx
0x1001e4c9  push    esi
0x1001e4ca  mov     esi, ecx
0x1001e4cc  xor     ebx, ebx
0x1001e4ce  push    edi
0x1001e4cf  cmp     [esi+318h], ebx
0x1001e4d5  jz      short loc_1001E510
0x1001e4d7  mov     edi, ebx
0x1001e4d9  cmp     [esi+31Ch], ebx
0x1001e4df  jbe     short loc_1001E4F9
0x1001e4e1  mov     eax, [esi+318h]
0x1001e4e7  push    dword ptr [eax+edi*4]; Block
0x1001e4ea  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001e4ef  inc     edi
0x1001e4f0  pop     ecx
0x1001e4f1  cmp     edi, [esi+31Ch]
0x1001e4f7  jb      short loc_1001E4E1
0x1001e4f9  mov     eax, [esi+318h]
0x1001e4ff  test    eax, eax
0x1001e501  jz      short loc_1001E510
0x1001e503  push    eax; Block
0x1001e504  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001e509  pop     ecx
0x1001e50a  mov     [esi+318h], ebx
0x1001e510  mov     [esi+31Ch], ebx
0x1001e516  cmp     [esi+320h], ebx
0x1001e51c  jz      short loc_1001E59D
0x1001e51e  mov     edi, ebx
0x1001e520  cmp     [esi+328h], ebx
0x1001e526  jbe     short loc_1001E56F
0x1001e528  mov     eax, [esi+324h]
0x1001e52e  test    eax, eax
0x1001e530  jz      short loc_1001E549
0x1001e532  cmp     [eax+edi*4], ebx
0x1001e535  jz      short loc_1001E549
0x1001e537  push    dword ptr [eax+edi*4]; pv
0x1001e53a  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001e540  mov     eax, [esi+324h]
0x1001e546  mov     [eax+edi*4], ebx
0x1001e549  mov     eax, [esi+320h]
0x1001e54f  cmp     [eax+edi*4], ebx
0x1001e552  jz      short loc_1001E566
0x1001e554  push    dword ptr [eax+edi*4]; pv
0x1001e557  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001e55d  mov     eax, [esi+320h]
0x1001e563  mov     [eax+edi*4], ebx
0x1001e566  inc     edi
0x1001e567  cmp     edi, [esi+328h]
0x1001e56d  jb      short loc_1001E528
0x1001e56f  mov     eax, [esi+324h]
0x1001e575  test    eax, eax
0x1001e577  jz      short loc_1001E586
0x1001e579  push    eax; pv
0x1001e57a  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001e580  mov     [esi+324h], ebx
0x1001e586  mov     eax, [esi+320h]
0x1001e58c  test    eax, eax
0x1001e58e  jz      short loc_1001E59D
0x1001e590  push    eax; pv
0x1001e591  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001e597  mov     [esi+320h], ebx
0x1001e59d  pop     edi
0x1001e59e  mov     [esi+328h], ebx
0x1001e5a4  pop     esi
0x1001e5a5  pop     ebx
0x1001e5a6  retn
```
