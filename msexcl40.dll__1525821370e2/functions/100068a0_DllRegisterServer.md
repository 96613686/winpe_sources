# DllRegisterServer()

- ea: `0x100068a0`
- end: `0x1000693b`
- name: `_DllRegisterServer@0`
- size: `155`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x100066d0`
- `0x100068a0`
- `0x10024d8e`
- `0x10025ab7`
- `0x10032c26`
- `0x10035510`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  int v0; // ecx
  _DWORD *v1; // ebx
  int v2; // eax
  _DWORD *v3; // ecx
  int v4; // edi
  _DWORD *v5; // esi
  WCHAR Filename[262]; // [esp+4h] [ebp-210h] BYREF

  if ( !JetGetModuleFileNameW(hModule, Filename, 0x105u) )
    return -2147467259;
  v1 = (_DWORD *)SetupConfigurationSpec(0);
  if ( !v1 )
    return -2147467259;
  v2 = ConfigRegister(v0, (int)v1, (BYTE *)Filename);
  v3 = (_DWORD *)*v1;
  v4 = v2;
  if ( *v1 )
  {
    do
    {
      v5 = (_DWORD *)*v3;
      MemFree(v3);
      v3 = v5;
    }
    while ( v5 );
  }
  MemFree(v1);
  return v4 != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x100068a0  mov     edi, edi
0x100068a2  push    ebp
0x100068a3  mov     ebp, esp
0x100068a5  sub     esp, 210h
0x100068ab  mov     eax, ___security_cookie
0x100068b0  xor     eax, ebp
0x100068b2  mov     [ebp+var_4], eax
0x100068b5  push    ebx
0x100068b6  push    105h; nSize
0x100068bb  lea     eax, [ebp+Filename]
0x100068c1  push    eax; lpFilename
0x100068c2  push    hModule; hModule
0x100068c8  call    _JetGetModuleFileNameW@12; JetGetModuleFileNameW(x,x,x)
0x100068cd  test    eax, eax
0x100068cf  jz      short loc_10006927
0x100068d1  xor     ecx, ecx
0x100068d3  call    SetupConfigurationSpec
0x100068d8  mov     ebx, eax
0x100068da  test    ebx, ebx
0x100068dc  jz      short loc_10006927
0x100068de  push    edi
0x100068df  lea     eax, [ebp+Filename]
0x100068e5  push    eax; lpData
0x100068e6  push    ebx; int
0x100068e7  push    ecx; int
0x100068e8  call    _ConfigRegister@20; ConfigRegister(x,x,x,x,x)
0x100068ed  mov     ecx, [ebx]
0x100068ef  mov     edi, eax
0x100068f1  test    ecx, ecx
0x100068f3  jz      short loc_10006904
0x100068f5  push    esi
0x100068f6  mov     esi, [ecx]
0x100068f8  call    _MemFree@4; MemFree(x)
0x100068fd  mov     ecx, esi
0x100068ff  test    esi, esi
0x10006901  jnz     short loc_100068F6
0x10006903  pop     esi
0x10006904  mov     ecx, ebx
0x10006906  call    _MemFree@4; MemFree(x)
0x1000690b  neg     edi
0x1000690d  sbb     edi, edi
0x1000690f  and     edi, 80004005h
0x10006915  mov     eax, edi
0x10006917  pop     edi
0x10006918  pop     ebx
0x10006919  mov     ecx, [ebp+var_4]
0x1000691c  xor     ecx, ebp; StackCookie
0x1000691e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10006923  mov     esp, ebp
0x10006925  pop     ebp
0x10006926  retn
0x10006927  mov     ecx, [ebp+var_4]
0x1000692a  mov     eax, 80004005h
0x1000692f  xor     ecx, ebp; StackCookie
0x10006931  pop     ebx
0x10006932  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10006937  mov     esp, ebp
0x10006939  pop     ebp
0x1000693a  retn
```
