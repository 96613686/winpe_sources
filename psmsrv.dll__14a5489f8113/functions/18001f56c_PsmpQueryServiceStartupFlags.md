# PsmpQueryServiceStartupFlags

- ea: `0x18001f56c`
- end: `0x18001f5fa`
- name: `PsmpQueryServiceStartupFlags`
- size: `142`
- prototype: `LSTATUS __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001cd80`

## callees

- `0x18001f56c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f5ba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f5ba`

## string_xrefs

- `0x18001f5ac`: `SYSTEM\CurrentControlSet\Services\BrokerInfrastructure\Parameters`

## pseudocode

```c
LSTATUS __fastcall PsmpQueryServiceStartupFlags(_DWORD *a1)
{
  LSTATUS result; // eax
  DWORD v3; // [rsp+58h] [rbp+10h] BYREF
  int v4; // [rsp+60h] [rbp+18h] BYREF

  v4 = 0;
  v3 = 4;
  result = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
             L"StartupFlags",
             0x18u,
             0,
             &v4,
             &v3);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0xC0070000;
  }
  else if ( v3 == 4 )
  {
    if ( (v4 & 0xFFFFFFFE) != 0 )
    {
      return -1073739509;
    }
    else
    {
      *a1 = v4;
      return 0;
    }
  }
  else
  {
    return -1073741820;
  }
  return result;
}

```

## disassembly

```asm
0x18001f56c  mov     r11, rsp
0x18001f56f  push    rbx
0x18001f570  sub     rsp, 40h
0x18001f574  lea     rax, [r11+10h]
0x18001f578  mov     [rsp+48h+arg_10], 0
0x18001f580  mov     [r11-18h], rax
0x18001f584  lea     r8, Value; "StartupFlags"
0x18001f58b  lea     rax, [r11+18h]
0x18001f58f  mov     [rsp+48h+arg_8], 4
0x18001f597  mov     rbx, rcx
0x18001f59a  mov     [r11-20h], rax
0x18001f59e  mov     r9d, 18h; dwFlags
0x18001f5a4  mov     qword ptr [r11-28h], 0
0x18001f5ac  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Br"...
0x18001f5b3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001f5ba  call    cs:__imp_RegGetValueW
0x18001f5c0  test    eax, eax
0x18001f5c2  jz      short loc_18001F5D0
0x18001f5c4  jle     short loc_18001F5F4
0x18001f5c6  movzx   eax, ax
0x18001f5c9  or      eax, 0C0070000h
0x18001f5ce  jmp     short loc_18001F5F4
0x18001f5d0  cmp     [rsp+48h+arg_8], 4
0x18001f5d5  jz      short loc_18001F5DE
0x18001f5d7  mov     eax, 0C0000004h
0x18001f5dc  jmp     short loc_18001F5F4
0x18001f5de  mov     eax, [rsp+48h+arg_10]
0x18001f5e2  test    eax, 0FFFFFFFEh
0x18001f5e7  jz      short loc_18001F5F0
0x18001f5e9  mov     eax, 0C000090Bh
0x18001f5ee  jmp     short loc_18001F5F4
0x18001f5f0  mov     [rbx], eax
0x18001f5f2  xor     eax, eax
0x18001f5f4  add     rsp, 40h
0x18001f5f8  pop     rbx
0x18001f5f9  retn
```
