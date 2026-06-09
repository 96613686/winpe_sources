# DllUnregisterServer()

- ea: `0x10006840`
- end: `0x1000688f`
- name: `_DllUnregisterServer@0`
- size: `79`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x100066d0`
- `0x10006840`
- `0x100252b0`
- `0x10025ab7`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  int **v0; // eax
  int v1; // ecx
  int **v2; // ebx
  int v3; // eax
  int *v4; // ecx
  int v5; // edi
  int *v6; // esi

  v0 = (int **)SetupConfigurationSpec((void *)1);
  v2 = v0;
  if ( !v0 )
    return -2147467259;
  v3 = ConfigUnregister(v1, v0);
  v4 = *v2;
  v5 = v3;
  if ( *v2 )
  {
    do
    {
      v6 = (int *)*v4;
      MemFree(v4);
      v4 = v6;
    }
    while ( v6 );
  }
  MemFree(v2);
  return v5 != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x10006840  mov     edi, edi
0x10006842  push    ebx
0x10006843  mov     ecx, 1
0x10006848  call    SetupConfigurationSpec
0x1000684d  mov     ebx, eax
0x1000684f  test    ebx, ebx
0x10006851  jz      short loc_10006888
0x10006853  push    edi
0x10006854  push    ebx
0x10006855  push    ecx
0x10006856  call    _ConfigUnregister@16; ConfigUnregister(x,x,x,x)
0x1000685b  mov     ecx, [ebx]
0x1000685d  mov     edi, eax
0x1000685f  test    ecx, ecx
0x10006861  jz      short loc_10006872
0x10006863  push    esi
0x10006864  mov     esi, [ecx]
0x10006866  call    _MemFree@4; MemFree(x)
0x1000686b  mov     ecx, esi
0x1000686d  test    esi, esi
0x1000686f  jnz     short loc_10006864
0x10006871  pop     esi
0x10006872  mov     ecx, ebx
0x10006874  call    _MemFree@4; MemFree(x)
0x10006879  neg     edi
0x1000687b  sbb     edi, edi
0x1000687d  and     edi, 80004005h
0x10006883  mov     eax, edi
0x10006885  pop     edi
0x10006886  pop     ebx
0x10006887  retn
0x10006888  mov     eax, 80004005h
0x1000688d  pop     ebx
0x1000688e  retn
```
