# EnableVpnPluginETWChannel

- ea: `0x1800aaa98`
- end: `0x1800aab8d`
- name: `EnableVpnPluginETWChannel`
- size: `245`
- prototype: `__int64 __fastcall(LPCWSTR ChannelPath, HMODULE hModule)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180022bd0`

## callees

- `0x1800aaa98`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aab13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aab62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aab13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aab62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aaabd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aaadf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aaabd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aaadf`
- `wevtapi!EvtOpenChannelConfig` at `0x1800aaaff`
- `wevtapi!EvtOpenChannelConfig` at `0x1800aaaff`
- `wevtapi!EvtClose` at `0x1800aab73`
- `wevtapi!EvtClose` at `0x1800aab73`

## string_xrefs

- `0x1800aaaac`: `EvtSetChannelConfigProperty`
- `0x1800aaad5`: `EvtSaveChannelConfig`

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
0x1800aaa98  push    rbx
0x1800aaa9a  push    rbp
0x1800aaa9b  push    rsi
0x1800aaa9c  push    rdi
0x1800aaa9d  push    r14
0x1800aaa9f  sub     rsp, 40h
0x1800aaaa3  mov     rdi, rdx
0x1800aaaa6  mov     r14, rcx
0x1800aaaa9  xorps   xmm0, xmm0
0x1800aaaac  lea     rdx, aEvtsetchannelc; "EvtSetChannelConfigProperty"
0x1800aaab3  mov     rcx, rdi; hModule
0x1800aaab6  xor     ebx, ebx
0x1800aaab8  movups  [rsp+68h+var_38], xmm0
0x1800aaabd  call    cs:__imp_GetProcAddress
0x1800aaac4  nop     dword ptr [rax+rax+00h]
0x1800aaac9  mov     rbp, rax
0x1800aaacc  test    rax, rax
0x1800aaacf  jz      loc_1800AAB7F
0x1800aaad5  lea     rdx, aEvtsavechannel; "EvtSaveChannelConfig"
0x1800aaadc  mov     rcx, rdi; hModule
0x1800aaadf  call    cs:__imp_GetProcAddress
0x1800aaae6  nop     dword ptr [rax+rax+00h]
0x1800aaaeb  mov     rsi, rax
0x1800aaaee  test    rax, rax
0x1800aaaf1  jz      loc_1800AAB7F
0x1800aaaf7  xor     r8d, r8d; Flags
0x1800aaafa  mov     rdx, r14; ChannelPath
0x1800aaafd  xor     ecx, ecx; Session
0x1800aaaff  call    cs:__imp_EvtOpenChannelConfig
0x1800aab06  nop     dword ptr [rax+rax+00h]
0x1800aab0b  mov     rdi, rax
0x1800aab0e  test    rax, rax
0x1800aab11  jnz     short loc_1800AAB23
0x1800aab13  call    cs:__imp_GetLastError
0x1800aab1a  nop     dword ptr [rax+rax+00h]
0x1800aab1f  mov     ebx, eax
0x1800aab21  jmp     short loc_1800AAB7F
0x1800aab23  lea     r9, [rsp+68h+var_38]
0x1800aab28  mov     qword ptr [rsp+68h+var_38+4], rbx
0x1800aab2d  xor     r8d, r8d
0x1800aab30  mov     dword ptr [rsp+68h+var_38+0Ch], 0Dh
0x1800aab38  xor     edx, edx
0x1800aab3a  mov     dword ptr [rsp+68h+var_38], 1
0x1800aab42  mov     rcx, rdi
0x1800aab45  mov     rax, rbp
0x1800aab48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aab4d  test    eax, eax
0x1800aab4f  jz      short loc_1800AAB62
0x1800aab51  xor     edx, edx
0x1800aab53  mov     rcx, rdi
0x1800aab56  mov     rax, rsi
0x1800aab59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aab5e  test    eax, eax
0x1800aab60  jnz     short loc_1800AAB70
0x1800aab62  call    cs:__imp_GetLastError
0x1800aab69  nop     dword ptr [rax+rax+00h]
0x1800aab6e  mov     ebx, eax
0x1800aab70  mov     rcx, rdi; Object
0x1800aab73  call    cs:__imp_EvtClose
0x1800aab7a  nop     dword ptr [rax+rax+00h]
0x1800aab7f  mov     eax, ebx
0x1800aab81  add     rsp, 40h
0x1800aab85  pop     r14
0x1800aab87  pop     rdi
0x1800aab88  pop     rsi
0x1800aab89  pop     rbp
0x1800aab8a  pop     rbx
0x1800aab8b  retn
```
