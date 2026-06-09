# SockIsMswsockCatalogEntry

- ea: `0x18000f3e0`
- end: `0x18000f4c0`
- name: `SockIsMswsockCatalogEntry`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f068`

## callees

- `0x18000f3e0`
- `0x1800222f0`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f459`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f459`
- `WS2_32!WSCGetProviderPath` at `0x18000f42b`
- `WS2_32!WSCGetProviderPath` at `0x18000f42b`

## pseudocode

```c
__int64 __fastcall SockIsMswsockCatalogEntry(__int64 a1, char *a2)
{
  bool v2; // zf
  char *v4; // rdx
  int v5; // eax
  int v6; // ecx
  int Errno; // [rsp+20h] [rbp-448h] BYREF
  int ProviderDllPathLen[3]; // [rsp+24h] [rbp-444h] BYREF
  WCHAR szProviderDllPath[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR Dst[264]; // [rsp+240h] [rbp-228h] BYREF

  v2 = *(_DWORD *)(a1 + 40) == 1;
  Errno = 0;
  if ( !v2 )
    return 0;
  ProviderDllPathLen[0] = 261;
  if ( WSCGetProviderPath((LPGUID)(a1 + 20), szProviderDllPath, ProviderDllPathLen, &Errno) == -1 )
    return 0xFFFFFFFFLL;
  szProviderDllPath[261] = 0;
  if ( ExpandEnvironmentStringsW(szProviderDllPath, Dst, 0x105u) - 1 > 0x104 )
    return 0xFFFFFFFFLL;
  Dst[261] = 0;
  v4 = (char *)((char *)Dst - a2);
  do
  {
    v5 = *(unsigned __int16 *)&v4[(_QWORD)a2];
    v6 = *(unsigned __int16 *)a2 - v5;
    if ( v6 )
      break;
    a2 += 2;
  }
  while ( v5 );
  return v6 == 0;
}

```

## disassembly

```asm
0x18000f3e0  push    rbx
0x18000f3e2  sub     rsp, 460h
0x18000f3e9  mov     rax, cs:__security_cookie
0x18000f3f0  xor     rax, rsp
0x18000f3f3  mov     [rsp+468h+var_18], rax
0x18000f3fb  cmp     dword ptr [rcx+28h], 1
0x18000f3ff  mov     rbx, rdx
0x18000f402  mov     [rsp+468h+Errno], 0
0x18000f40a  jnz     loc_18000F4B7
0x18000f410  add     rcx, 14h; lpProviderId
0x18000f414  mov     [rsp+468h+ProviderDllPathLen], 105h
0x18000f41c  lea     r9, [rsp+468h+Errno]; lpErrno
0x18000f421  lea     r8, [rsp+468h+ProviderDllPathLen]; lpProviderDllPathLen
0x18000f426  lea     rdx, [rsp+468h+szProviderDllPath]; lpszProviderDllPath
0x18000f42b  call    cs:__imp_WSCGetProviderPath
0x18000f432  nop     dword ptr [rax+rax+00h]
0x18000f437  cmp     eax, 0FFFFFFFFh
0x18000f43a  jz      short loc_18000F4BB
0x18000f43c  xor     eax, eax
0x18000f43e  lea     rdx, [rsp+468h+Dst]; lpDst
0x18000f446  mov     r8d, 105h; nSize
0x18000f44c  mov     [rsp+468h+var_22E], ax
0x18000f454  lea     rcx, [rsp+468h+szProviderDllPath]; lpSrc
0x18000f459  call    cs:__imp_ExpandEnvironmentStringsW
0x18000f460  nop     dword ptr [rax+rax+00h]
0x18000f465  dec     eax
0x18000f467  cmp     eax, 104h
0x18000f46c  ja      short loc_18000F4BB
0x18000f46e  xor     eax, eax
0x18000f470  lea     rdx, [rsp+468h+Dst]
0x18000f478  mov     [rsp+468h+var_1E], ax
0x18000f480  sub     rdx, rbx
0x18000f483  movzx   ecx, word ptr [rbx]
0x18000f486  movzx   eax, word ptr [rbx+rdx]
0x18000f48a  sub     ecx, eax
0x18000f48c  jnz     short loc_18000F496
0x18000f48e  add     rbx, 2
0x18000f492  test    eax, eax
0x18000f494  jnz     short loc_18000F483
0x18000f496  xor     eax, eax
0x18000f498  test    ecx, ecx
0x18000f49a  setz    al
0x18000f49d  mov     rcx, [rsp+468h+var_18]
0x18000f4a5  xor     rcx, rsp; StackCookie
0x18000f4a8  call    __security_check_cookie
0x18000f4ad  add     rsp, 460h
0x18000f4b4  pop     rbx
0x18000f4b5  retn
0x18000f4b7  xor     eax, eax
0x18000f4b9  jmp     short loc_18000F49D
0x18000f4bb  or      eax, 0FFFFFFFFh
0x18000f4be  jmp     short loc_18000F49D
```
