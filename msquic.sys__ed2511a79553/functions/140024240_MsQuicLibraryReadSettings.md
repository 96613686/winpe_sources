# MsQuicLibraryReadSettings

- ea: `0x140024240`
- end: `0x140024303`
- name: `MsQuicLibraryReadSettings`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x140023f20`

## callees

- `0x140006a2c`
- `0x140024240`
- `0x14002430c`
- `0x140024548`
- `0x140024810`
- `0x140028b3c`
- `0x14003c8e0`
- `0x14003ead8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x1400242b1`
- `ntoskrnl!_snprintf_s` at `0x1400242b1`

## string_xrefs

- `0x140024297`: `[ lib] Settings %p Updated`

## pseudocode

```c
__int64 __fastcall MsQuicLibraryReadSettings(__int64 a1)
{
  int *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  char DstBuf[128]; // [rsp+30h] [rbp-98h] BYREF

  QuicSettingsSetDefault(&qword_14005C4B0);
  if ( qword_14005C580 )
  {
    QuicSettingsLoad(v2, (__int64)qword_14005C580);
    QuicLibraryLoadRetryConfig(qword_14005C580);
  }
  if ( (byte_14005C48E & 0x40) != 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ lib] Settings %p Updated", &qword_14005C4B0);
    McTemplateU0s_EtwWriteTransfer(v3, QuicLogInfo, DstBuf);
  }
  QuicSettingsDump((__int64)&qword_14005C4B0);
  LOBYTE(v4) = a1 != 0;
  return MsQuicLibraryOnSettingsChanged(v4);
}

```

## disassembly

```asm
0x140024240  mov     [rsp+arg_0], rbx
0x140024245  push    rdi
0x140024246  sub     rsp, 0C0h
0x14002424d  mov     rax, cs:__security_cookie
0x140024254  xor     rax, rsp
0x140024257  mov     [rsp+0C8h+var_18], rax
0x14002425f  lea     rdi, qword_14005C4B0
0x140024266  mov     rbx, rcx
0x140024269  mov     rcx, rdi
0x14002426c  call    QuicSettingsSetDefault
0x140024271  mov     rdx, cs:qword_14005C580
0x140024278  test    rdx, rdx
0x14002427b  jz      short loc_14002428E
0x14002427d  call    QuicSettingsLoad
0x140024282  mov     rcx, cs:qword_14005C580
0x140024289  call    QuicLibraryLoadRetryConfig
0x14002428e  test    cs:byte_14005C48E, 40h
0x140024295  jz      short loc_1400242CE
0x140024297  lea     r9, aLibSettingsPUp; "[ lib] Settings %p Updated"
0x14002429e  mov     [rsp+0C8h+var_A8], rdi
0x1400242a3  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400242a7  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x1400242ac  mov     edx, 80h; SizeInBytes
0x1400242b1  call    cs:__imp__snprintf_s
0x1400242b8  nop     dword ptr [rax+rax+00h]
0x1400242bd  lea     r8, [rsp+0C8h+DstBuf]
0x1400242c2  lea     rdx, QuicLogInfo
0x1400242c9  call    McTemplateU0s_EtwWriteTransfer
0x1400242ce  mov     rcx, rdi
0x1400242d1  call    QuicSettingsDump
0x1400242d6  test    rbx, rbx
0x1400242d9  setnz   cl
0x1400242dc  call    MsQuicLibraryOnSettingsChanged
0x1400242e1  mov     rcx, [rsp+0C8h+var_18]
0x1400242e9  xor     rcx, rsp; StackCookie
0x1400242ec  call    __security_check_cookie
0x1400242f1  mov     rbx, [rsp+0C8h+arg_0]
0x1400242f9  add     rsp, 0C0h
0x140024300  pop     rdi
0x140024301  retn
```
