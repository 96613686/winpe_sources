# RefreshDevices

- ea: `0x180014bc0`
- end: `0x180014c96`
- name: `RefreshDevices`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000212c`
- `0x18000d92c`
- `0x18000de88`
- `0x180014bc0`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c49`

## string_xrefs

- `0x180014c70`: `RefreshDevices: dwCreateTapiPortsPerLine Failed. 0x%x`

## pseudocode

```c
__int64 RefreshDevices()
{
  unsigned int v0; // edi
  unsigned int v1; // ebx
  unsigned int v2; // edx
  int v3; // ecx
  HLOCAL hMem; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v6; // [rsp+28h] [rbp-20h] BYREF

  v0 = 0;
  v6 = 0;
  hMem = 0;
  RasTapiTrace("RefreshDevices");
  v1 = 0;
  v2 = g_dwNumNDProxyLines;
  if ( g_dwNumNDProxyLines + g_dwNumTapiLines )
  {
    while ( 1 )
    {
      v3 = v1;
      if ( v1 >= v2 )
        v3 = v1 - v2;
      v0 = dwCreateTapiPortsPerLine(v3, v1 < v2, &v6, &hMem);
      if ( v0 )
        break;
      RasTapiTrace("RefreshDevices: cNewPorts = %d");
      AddNewPortsPerLine((__int64)hMem, v6);
      LocalFree(hMem);
      ++v1;
      v2 = g_dwNumNDProxyLines;
      hMem = 0;
      if ( v1 >= g_dwNumNDProxyLines + g_dwNumTapiLines )
        return v0;
    }
    RasTapiTrace("RefreshDevices: dwCreateTapiPortsPerLine Failed. 0x%x");
  }
  return v0;
}

```

## disassembly

```asm
0x180014bc0  mov     [rsp+arg_0], rbx
0x180014bc5  push    rdi
0x180014bc6  sub     rsp, 40h
0x180014bca  mov     rax, cs:__security_cookie
0x180014bd1  xor     rax, rsp
0x180014bd4  mov     [rsp+48h+var_18], rax
0x180014bd9  xor     edi, edi
0x180014bdb  lea     rcx, aRefreshdevices_2; "RefreshDevices"
0x180014be2  mov     [rsp+48h+var_20], edi
0x180014be6  mov     [rsp+48h+hMem], rdi
0x180014beb  call    RasTapiTrace
0x180014bf0  mov     ecx, cs:g_dwNumTapiLines
0x180014bf6  xor     ebx, ebx
0x180014bf8  mov     edx, cs:g_dwNumNDProxyLines
0x180014bfe  add     ecx, edx
0x180014c00  jz      short loc_180014C7C
0x180014c02  xor     eax, eax
0x180014c04  mov     ecx, ebx
0x180014c06  cmp     ebx, edx
0x180014c08  setb    al
0x180014c0b  jb      short loc_180014C0F
0x180014c0d  sub     ecx, edx
0x180014c0f  lea     r9, [rsp+48h+hMem]
0x180014c14  mov     edx, eax
0x180014c16  lea     r8, [rsp+48h+var_20]
0x180014c1b  call    dwCreateTapiPortsPerLine
0x180014c20  mov     edi, eax
0x180014c22  test    eax, eax
0x180014c24  jnz     short loc_180014C6E
0x180014c26  mov     edx, [rsp+48h+var_20]
0x180014c2a  lea     rcx, aRefreshdevices_1; "RefreshDevices: cNewPorts = %d"
0x180014c31  call    RasTapiTrace
0x180014c36  mov     edx, [rsp+48h+var_20]
0x180014c3a  mov     rcx, [rsp+48h+hMem]
0x180014c3f  call    AddNewPortsPerLine
0x180014c44  mov     rcx, [rsp+48h+hMem]; hMem
0x180014c49  call    cs:__imp_LocalFree
0x180014c4f  mov     ecx, cs:g_dwNumTapiLines
0x180014c55  inc     ebx
0x180014c57  mov     edx, cs:g_dwNumNDProxyLines
0x180014c5d  add     ecx, edx
0x180014c5f  mov     [rsp+48h+hMem], 0
0x180014c68  cmp     ebx, ecx
0x180014c6a  jb      short loc_180014C02
0x180014c6c  jmp     short loc_180014C7C
0x180014c6e  mov     edx, eax
0x180014c70  lea     rcx, aRefreshdevices_0; "RefreshDevices: dwCreateTapiPortsPerLin"...
0x180014c77  call    RasTapiTrace
0x180014c7c  mov     eax, edi
0x180014c7e  mov     rcx, [rsp+48h+var_18]
0x180014c83  xor     rcx, rsp; StackCookie
0x180014c86  call    __security_check_cookie
0x180014c8b  mov     rbx, [rsp+48h+arg_0]
0x180014c90  add     rsp, 40h
0x180014c94  pop     rdi
0x180014c95  retn
```
