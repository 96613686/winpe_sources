# QuicConfigurationSettingsChanged

- ea: `0x140025d70`
- end: `0x140025df4`
- name: `QuicConfigurationSettingsChanged`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x14002430c`
- `0x1400258c0`

## callees

- `0x140006a2c`
- `0x140024548`
- `0x140024810`
- `0x140025d70`
- `0x140025dfc`
- `0x14003c8e0`
- `0x14003ead8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14003e82f`
- `ntoskrnl!_snprintf_s` at `0x14003e82f`

## string_xrefs

- `0x14003e815`: `[cnfg][%p] Settings %p Updated`

## pseudocode

```c
_UNKNOWN **__fastcall QuicConfigurationSettingsChanged(__int64 *a1)
{
  bool v1; // zf
  int *v2; // rbx
  __int64 *v4; // rcx
  __int64 v5; // rdx
  int *v7; // rcx
  __int64 v8; // rcx
  char DstBuf[128]; // [rsp+30h] [rbp-98h] BYREF

  v1 = a1[9] == 0;
  v2 = (int *)(a1 + 12);
  v4 = a1 + 12;
  if ( v1 )
  {
    QuicSettingsCopy(v4, &qword_14005C4B0);
  }
  else
  {
    QuicSettingsSetDefault(v4);
    QuicSettingsLoad(v7, a1[9]);
  }
  v5 = a1[11];
  if ( v5 )
    QuicSettingsLoad(v2, v5);
  if ( (byte_14005C48E & 0x40) != 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[cnfg][%p] Settings %p Updated", a1, v2);
    McTemplateU0s_EtwWriteTransfer(v8, QuicLogInfo, DstBuf);
  }
  return QuicSettingsDump((__int64)v2);
}

```

## disassembly

```asm
0x140025d70  mov     [rsp+arg_8], rbx
0x140025d75  push    rdi
0x140025d76  sub     rsp, 0C0h
0x140025d7d  mov     rax, cs:__security_cookie
0x140025d84  xor     rax, rsp
0x140025d87  mov     [rsp+0C8h+var_18], rax
0x140025d8f  cmp     qword ptr [rcx+48h], 0
0x140025d94  lea     rbx, [rcx+60h]
0x140025d98  mov     rdi, rcx
0x140025d9b  mov     rcx, rbx
0x140025d9e  jnz     loc_14003E7EE
0x140025da4  lea     rdx, qword_14005C4B0
0x140025dab  call    QuicSettingsCopy
0x140025db0  mov     rdx, [rdi+58h]
0x140025db4  test    rdx, rdx
0x140025db7  jnz     loc_14003E802
0x140025dbd  test    cs:byte_14005C48E, 40h
0x140025dc4  jnz     loc_14003E810
0x140025dca  mov     rcx, rbx
0x140025dcd  call    QuicSettingsDump
0x140025dd2  mov     rcx, [rsp+0C8h+var_18]
0x140025dda  xor     rcx, rsp; StackCookie
0x140025ddd  call    __security_check_cookie
0x140025de2  mov     rbx, [rsp+0C8h+arg_8]
0x140025dea  add     rsp, 0C0h
0x140025df1  pop     rdi
0x140025df2  retn
0x14003e7ee  call    QuicSettingsSetDefault
0x14003e7f3  mov     rdx, [rdi+48h]
0x14003e7f7  call    QuicSettingsLoad
0x14003e7fc  nop
0x14003e7fd  jmp     loc_140025DB0
0x14003e802  mov     rcx, rbx
0x14003e805  call    QuicSettingsLoad
0x14003e80a  nop
0x14003e80b  jmp     loc_140025DBD
0x14003e810  mov     [rsp+0C8h+var_A0], rbx
0x14003e815  lea     r9, aCnfgPSettingsP; "[cnfg][%p] Settings %p Updated"
0x14003e81c  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003e820  mov     [rsp+0C8h+var_A8], rdi
0x14003e825  mov     edx, 80h; SizeInBytes
0x14003e82a  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x14003e82f  call    cs:__imp__snprintf_s
0x14003e836  nop     dword ptr [rax+rax+00h]
0x14003e83b  lea     r8, [rsp+0C8h+DstBuf]
0x14003e840  lea     rdx, QuicLogInfo
0x14003e847  call    McTemplateU0s_EtwWriteTransfer
0x14003e84c  nop
0x14003e84d  jmp     loc_140025DCA
```
