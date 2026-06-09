# NcaEvCollIPv6IsDisabled(void)

- ea: `0x180010bcc`
- end: `0x180010c5b`
- name: `?NcaEvCollIPv6IsDisabled@@YAHXZ`
- size: `143`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010aa0`

## callees

- `0x180004f34`
- `0x180010bcc`
- `0x18001a654`

## string_xrefs

- `0x180010be9`: `DisabledComponents`
- `0x180010bf8`: `SYSTEM\CurrentControlSet\Services\Tcpip6\Parameters\`

## pseudocode

```c
__int64 NcaEvCollIPv6IsDisabled(void)
{
  int DWord; // eax
  unsigned int v1; // ebx
  __int64 v3; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF

  Data = 0;
  LODWORD(v3) = 0;
  DWord = NcaRegQueryDWord(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\",
            L"DisabledComponents",
            (LPBYTE)&Data,
            (__int64)&v3);
  v1 = 1;
  if ( DWord < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_26111ec2426b3182965f58d1256f8724_Traceguids,
      (unsigned int)DWord);
  if ( !(_DWORD)v3 || !Data )
    return 0;
  return v1;
}

```

## disassembly

```asm
0x180010bcc  push    rbx
0x180010bce  sub     rsp, 30h
0x180010bd2  lea     rax, [rsp+38h+arg_0]
0x180010bd7  mov     [rsp+38h+Data], 0
0x180010bdf  lea     r9, [rsp+38h+Data]; lpData
0x180010be4  mov     [rsp+38h+var_18], rax; __int64
0x180010be9  lea     r8, aDisabledcompon; "DisabledComponents"
0x180010bf0  mov     dword ptr [rsp+38h+arg_0], 0
0x180010bf8  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x180010bff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010c06  call    NcaRegQueryDWord
0x180010c0b  mov     ebx, 1
0x180010c10  test    eax, eax
0x180010c12  jns     short loc_180010C42
0x180010c14  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c1b  lea     rdx, WPP_GLOBAL_Control
0x180010c22  cmp     rcx, rdx
0x180010c25  jz      short loc_180010C42
0x180010c27  test    [rcx+1Ch], bl
0x180010c2a  jz      short loc_180010C42
0x180010c2c  mov     rcx, [rcx+10h]
0x180010c30  lea     edx, [rbx+0Fh]
0x180010c33  mov     r9d, eax
0x180010c36  lea     r8, WPP_26111ec2426b3182965f58d1256f8724_Traceguids
0x180010c3d  call    WPP_SF_d
0x180010c42  cmp     dword ptr [rsp+38h+arg_0], 0
0x180010c47  jz      short loc_180010C50
0x180010c49  cmp     [rsp+38h+Data], 0
0x180010c4e  jnz     short loc_180010C52
0x180010c50  xor     ebx, ebx
0x180010c52  mov     eax, ebx
0x180010c54  add     rsp, 30h
0x180010c58  pop     rbx
0x180010c59  retn
```
