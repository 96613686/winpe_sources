# devCommitDeviceInfo

- ea: `0x180035d0c`
- end: `0x180035d8b`
- name: `devCommitDeviceInfo`
- size: `127`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035ca0`
- `0x1800360b8`

## callees

- `0x1800348f0`
- `0x180035d0c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180035d55`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180035d55`
- `rasman!RasSetDeviceConfigInfo` at `0x180035d33`
- `rasman!RasSetDeviceConfigInfo` at `0x180035d33`

## string_xrefs

- `0x180035d44`: `devCommDevInfo: 0x%08x from RasSetDevCfgInfo (try again)`
- `0x180035d6d`: `devCommDevInfo: can't commit %S, 0x%08x`

## pseudocode

```c
__int64 __fastcall devCommitDeviceInfo(__int64 a1)
{
  int v2; // esi
  int v3; // eax
  unsigned int v4; // ebx

  v2 = 10;
  while ( 1 )
  {
    v3 = RasSetDeviceConfigInfo(0, 1, 472, a1);
    v4 = v3;
    if ( v3 != 1003 )
      break;
    DbgOutputTrace("devCommDevInfo: 0x%08x from RasSetDevCfgInfo (try again)", 1003);
    Sleep(0x12Cu);
    if ( !--v2 )
      return v4;
  }
  if ( v3 )
    DbgOutputTrace("devCommDevInfo: can't commit %S, 0x%08x", (const wchar_t *)(a1 + 85), v3);
  return v4;
}

```

## disassembly

```asm
0x180035d0c  mov     [rsp+arg_0], rbx
0x180035d11  mov     [rsp+arg_8], rsi
0x180035d16  push    rdi
0x180035d17  sub     rsp, 20h
0x180035d1b  mov     rdi, rcx
0x180035d1e  mov     esi, 0Ah
0x180035d23  mov     r9, rdi
0x180035d26  mov     edx, 1
0x180035d2b  xor     ecx, ecx
0x180035d2d  mov     r8d, 1D8h
0x180035d33  call    cs:__imp_RasSetDeviceConfigInfo
0x180035d39  mov     ebx, eax
0x180035d3b  cmp     eax, 3EBh
0x180035d40  jnz     short loc_180035D62
0x180035d42  mov     edx, eax
0x180035d44  lea     rcx, aDevcommdevinfo; "devCommDevInfo: 0x%08x from RasSetDevCf"...
0x180035d4b  call    DbgOutputTrace
0x180035d50  mov     ecx, 12Ch; dwMilliseconds
0x180035d55  call    cs:__imp_Sleep
0x180035d5b  add     esi, 0FFFFFFFFh
0x180035d5e  jnz     short loc_180035D23
0x180035d60  jmp     short loc_180035D79
0x180035d62  test    ebx, ebx
0x180035d64  jz      short loc_180035D79
0x180035d66  lea     rdx, [rdi+55h]
0x180035d6a  mov     r8d, ebx
0x180035d6d  lea     rcx, aDevcommdevinfo_0; "devCommDevInfo: can't commit %S, 0x%08x"
0x180035d74  call    DbgOutputTrace
0x180035d79  mov     rsi, [rsp+28h+arg_8]
0x180035d7e  mov     eax, ebx
0x180035d80  mov     rbx, [rsp+28h+arg_0]
0x180035d85  add     rsp, 20h
0x180035d89  pop     rdi
0x180035d8a  retn
```
