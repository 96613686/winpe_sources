# devCommitDeviceInfo

- ea: `0x180027ae4`
- end: `0x180027b63`
- name: `devCommitDeviceInfo`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027a78`
- `0x180027e84`

## callees

- `0x180026710`
- `0x180027ae4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027b2d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027b2d`
- `rasman!RasSetDeviceConfigInfo` at `0x180027b0b`
- `rasman!RasSetDeviceConfigInfo` at `0x180027b0b`

## string_xrefs

- `0x180027b45`: `devCommDevInfo: can't commit %S, 0x%08x`
- `0x180027b1c`: `devCommDevInfo: 0x%08x from RasSetDevCfgInfo (try again)`

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
0x180027ae4  mov     [rsp+arg_0], rbx
0x180027ae9  mov     [rsp+arg_8], rsi
0x180027aee  push    rdi
0x180027aef  sub     rsp, 20h
0x180027af3  mov     rdi, rcx
0x180027af6  mov     esi, 0Ah
0x180027afb  mov     r9, rdi
0x180027afe  mov     edx, 1
0x180027b03  xor     ecx, ecx
0x180027b05  mov     r8d, 1D8h
0x180027b0b  call    cs:__imp_RasSetDeviceConfigInfo
0x180027b11  mov     ebx, eax
0x180027b13  cmp     eax, 3EBh
0x180027b18  jnz     short loc_180027B3A
0x180027b1a  mov     edx, eax
0x180027b1c  lea     rcx, aDevcommdevinfo; "devCommDevInfo: 0x%08x from RasSetDevCf"...
0x180027b23  call    DbgOutputTrace
0x180027b28  mov     ecx, 12Ch; dwMilliseconds
0x180027b2d  call    cs:__imp_Sleep
0x180027b33  add     esi, 0FFFFFFFFh
0x180027b36  jnz     short loc_180027AFB
0x180027b38  jmp     short loc_180027B51
0x180027b3a  test    ebx, ebx
0x180027b3c  jz      short loc_180027B51
0x180027b3e  lea     rdx, [rdi+55h]
0x180027b42  mov     r8d, ebx
0x180027b45  lea     rcx, aDevcommdevinfo_0; "devCommDevInfo: can't commit %S, 0x%08x"
0x180027b4c  call    DbgOutputTrace
0x180027b51  mov     rsi, [rsp+28h+arg_8]
0x180027b56  mov     eax, ebx
0x180027b58  mov     rbx, [rsp+28h+arg_0]
0x180027b5d  add     rsp, 20h
0x180027b61  pop     rdi
0x180027b62  retn
```
