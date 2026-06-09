# EnableVpnPluginETWChannel

- ea: `0x1800bc4e0`
- end: `0x1800bc5ac`
- name: `EnableVpnPluginETWChannel`
- size: `204`
- prototype: `__int64 __fastcall(LPCWSTR ChannelPath, HMODULE hModule)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800bc148`

## callees

- `0x1800bc4e0`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc58e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc58e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc505`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc521`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc505`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc521`
- `wevtapi!EvtOpenChannelConfig` at `0x1800bc537`
- `wevtapi!EvtOpenChannelConfig` at `0x1800bc537`
- `wevtapi!EvtClose` at `0x1800bc599`
- `wevtapi!EvtClose` at `0x1800bc599`

## string_xrefs

- `0x1800bc517`: `EvtSaveChannelConfig`
- `0x1800bc4f4`: `EvtSetChannelConfigProperty`

## pseudocode

```c
__int64 __fastcall EnableVpnPluginETWChannel(LPCWSTR ChannelPath, HMODULE hModule)
{
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rbp
  FARPROC v6; // rsi
  EVT_HANDLE v7; // rax
  void *v8; // rdi
  __int128 v10; // [rsp+30h] [rbp-38h] BYREF

  LastError = 0;
  v10 = 0;
  ProcAddress = GetProcAddress(hModule, "EvtSetChannelConfigProperty");
  if ( ProcAddress )
  {
    v6 = GetProcAddress(hModule, "EvtSaveChannelConfig");
    if ( v6 )
    {
      v7 = EvtOpenChannelConfig(0, ChannelPath, 0);
      v8 = v7;
      if ( v7 )
      {
        *(_QWORD *)((char *)&v10 + 4) = 0;
        HIDWORD(v10) = 13;
        LODWORD(v10) = 1;
        if ( !((unsigned int (__fastcall *)(EVT_HANDLE, _QWORD, _QWORD, __int128 *))ProcAddress)(v7, 0, 0, &v10)
          || !((unsigned int (__fastcall *)(void *, _QWORD))v6)(v8, 0) )
        {
          LastError = GetLastError();
        }
        EvtClose(v8);
      }
      else
      {
        return GetLastError();
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800bc4e0  push    rbx
0x1800bc4e2  push    rbp
0x1800bc4e3  push    rsi
0x1800bc4e4  push    rdi
0x1800bc4e5  push    r14
0x1800bc4e7  sub     rsp, 40h
0x1800bc4eb  mov     rdi, rdx
0x1800bc4ee  mov     r14, rcx
0x1800bc4f1  xorps   xmm0, xmm0
0x1800bc4f4  lea     rdx, aEvtsetchannelc; "EvtSetChannelConfigProperty"
0x1800bc4fb  mov     rcx, rdi; hModule
0x1800bc4fe  xor     ebx, ebx
0x1800bc500  movups  [rsp+68h+var_38], xmm0
0x1800bc505  call    cs:__imp_GetProcAddress
0x1800bc50b  mov     rbp, rax
0x1800bc50e  test    rax, rax
0x1800bc511  jz      loc_1800BC59F
0x1800bc517  lea     rdx, aEvtsavechannel; "EvtSaveChannelConfig"
0x1800bc51e  mov     rcx, rdi; hModule
0x1800bc521  call    cs:__imp_GetProcAddress
0x1800bc527  mov     rsi, rax
0x1800bc52a  test    rax, rax
0x1800bc52d  jz      short loc_1800BC59F
0x1800bc52f  xor     r8d, r8d; Flags
0x1800bc532  mov     rdx, r14; ChannelPath
0x1800bc535  xor     ecx, ecx; Session
0x1800bc537  call    cs:__imp_EvtOpenChannelConfig
0x1800bc53d  mov     rdi, rax
0x1800bc540  test    rax, rax
0x1800bc543  jnz     short loc_1800BC54F
0x1800bc545  call    cs:__imp_GetLastError
0x1800bc54b  mov     ebx, eax
0x1800bc54d  jmp     short loc_1800BC59F
0x1800bc54f  lea     r9, [rsp+68h+var_38]
0x1800bc554  mov     qword ptr [rsp+68h+var_38+4], rbx
0x1800bc559  xor     r8d, r8d
0x1800bc55c  mov     dword ptr [rsp+68h+var_38+0Ch], 0Dh
0x1800bc564  xor     edx, edx
0x1800bc566  mov     dword ptr [rsp+68h+var_38], 1
0x1800bc56e  mov     rcx, rdi
0x1800bc571  mov     rax, rbp
0x1800bc574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc579  test    eax, eax
0x1800bc57b  jz      short loc_1800BC58E
0x1800bc57d  xor     edx, edx
0x1800bc57f  mov     rcx, rdi
0x1800bc582  mov     rax, rsi
0x1800bc585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc58a  test    eax, eax
0x1800bc58c  jnz     short loc_1800BC596
0x1800bc58e  call    cs:__imp_GetLastError
0x1800bc594  mov     ebx, eax
0x1800bc596  mov     rcx, rdi; Object
0x1800bc599  call    cs:__imp_EvtClose
0x1800bc59f  mov     eax, ebx
0x1800bc5a1  add     rsp, 40h
0x1800bc5a5  pop     r14
0x1800bc5a7  pop     rdi
0x1800bc5a8  pop     rsi
0x1800bc5a9  pop     rbp
0x1800bc5aa  pop     rbx
0x1800bc5ab  retn
```
