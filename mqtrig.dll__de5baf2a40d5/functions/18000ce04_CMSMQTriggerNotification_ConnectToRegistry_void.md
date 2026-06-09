# CMSMQTriggerNotification::ConnectToRegistry(void)

- ea: `0x18000ce04`
- end: `0x18000ce8e`
- name: `?ConnectToRegistry@CMSMQTriggerNotification@@IEAA_NXZ`
- size: `138`
- prototype: `char __fastcall(HKEY *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ce94`

## callees

- `0x180004dfc`
- `0x18000ce04`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ce4b`
- `KERNEL32!GetLastError` at `0x18000ce4b`
- `ADVAPI32!RegConnectRegistryW` at `0x18000ce26`
- `ADVAPI32!RegConnectRegistryW` at `0x18000ce26`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CMSMQTriggerNotification::ConnectToRegistry(HKEY *this)
{
  char v1; // bl
  char LastError; // al

  v1 = 1;
  if ( !this[2] )
  {
    if ( RegConnectRegistryW(0, HKEY_LOCAL_MACHINE, this + 2) )
    {
      v1 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000ce04  mov     [rsp+arg_0], rbx
0x18000ce09  push    rdi
0x18000ce0a  sub     rsp, 30h
0x18000ce0e  lea     r8, [rcx+10h]; phkResult
0x18000ce12  mov     rdi, rcx
0x18000ce15  cmp     qword ptr [r8], 0
0x18000ce19  mov     bl, 1
0x18000ce1b  jnz     short loc_18000CE81
0x18000ce1d  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18000ce24  xor     ecx, ecx; lpMachineName
0x18000ce26  call    cs:__imp_RegConnectRegistryW
0x18000ce2c  test    eax, eax
0x18000ce2e  jz      short loc_18000CE81
0x18000ce30  xor     bl, bl
0x18000ce32  mov     rax, cs:WPP_GLOBAL_Control
0x18000ce39  lea     rcx, WPP_GLOBAL_Control
0x18000ce40  cmp     rax, rcx
0x18000ce43  jz      short loc_18000CE81
0x18000ce45  test    byte ptr [rax+1Ch], 1
0x18000ce49  jz      short loc_18000CE81
0x18000ce4b  call    cs:__imp_GetLastError
0x18000ce51  mov     rcx, [rdi]
0x18000ce54  test    rcx, rcx
0x18000ce57  jz      short loc_18000CE5E
0x18000ce59  mov     r9, [rcx]
0x18000ce5c  jmp     short loc_18000CE61
0x18000ce5e  xor     r9d, r9d
0x18000ce61  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce68  lea     r8, WPP_6d1c6f0186f431bde13e7207227cdc41_Traceguids
0x18000ce6f  mov     edx, 0Dh
0x18000ce74  mov     dword ptr [rsp+38h+var_18], eax; char
0x18000ce78  mov     rcx, [rcx+10h]; LoggerHandle
0x18000ce7c  call    WPP_SF_SD
0x18000ce81  mov     al, bl
0x18000ce83  mov     rbx, [rsp+38h+arg_0]
0x18000ce88  add     rsp, 30h
0x18000ce8c  pop     rdi
0x18000ce8d  retn
```
