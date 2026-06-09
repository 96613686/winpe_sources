# CMSMQTriggersConfig::SetComClassError(long)

- ea: `0x18000c720`
- end: `0x18000c7a5`
- name: `?SetComClassError@CMSMQTriggersConfig@@AEAAXJ@Z`
- size: `133`
- prototype: `void __fastcall(CMSMQTriggersConfig *this, DWORD)`
- caller_count: `10`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000c7b0`
- `0x18000c830`
- `0x18000c8c0`
- `0x18000c940`
- `0x18000c9c0`
- `0x18000ca90`
- `0x18000cb50`
- `0x18000cc10`
- `0x18000ccd0`
- `0x18001ffa4`

## callees

- `0x18000e89c`
- `0x18001e35a`
- `0x18001e380`

## import_xrefs

- `ATL!__imp_AtlSetErrorInfo` at `0x18000c786`
- `ATL!__imp_AtlSetErrorInfo` at `0x18000c786`

## pseudocode

```c
void __fastcall CMSMQTriggersConfig::SetComClassError(CMSMQTriggersConfig *this, DWORD a2)
{
  unsigned int v3; // r8d
  WCHAR Buffer[256]; // [rsp+40h] [rbp-218h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  GetErrorDescription(a2, Buffer, v3);
  AtlSetErrorInfo(&CLSID_MSMQTriggersConfig, Buffer, 0, 0, &GUID_NULL, a2, 0);
}

```

## disassembly

```asm
0x18000c720  push    rbx
0x18000c722  sub     rsp, 250h
0x18000c729  mov     rax, cs:__security_cookie
0x18000c730  xor     rax, rsp
0x18000c733  mov     [rsp+258h+var_18], rax
0x18000c73b  mov     ebx, edx
0x18000c73d  lea     rcx, [rsp+258h+Buffer]; void *
0x18000c742  xor     edx, edx; Val
0x18000c744  mov     r8d, 200h; Size
0x18000c74a  call    memset_0
0x18000c74f  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x18000c754  mov     ecx, ebx; dwMessageId
0x18000c756  call    ?GetErrorDescription@@YAXJPEA_WK@Z; GetErrorDescription(long,wchar_t *,ulong)
0x18000c75b  lea     rax, GUID_NULL
0x18000c762  mov     [rsp+258h+var_228], 0
0x18000c76b  mov     [rsp+258h+var_230], ebx
0x18000c76f  lea     rdx, [rsp+258h+Buffer]
0x18000c774  xor     r9d, r9d
0x18000c777  mov     [rsp+258h+var_238], rax
0x18000c77c  xor     r8d, r8d
0x18000c77f  lea     rcx, CLSID_MSMQTriggersConfig
0x18000c786  call    cs:__imp_AtlSetErrorInfo
0x18000c78c  mov     rcx, [rsp+258h+var_18]
0x18000c794  xor     rcx, rsp; StackCookie
0x18000c797  call    __security_check_cookie
0x18000c79c  add     rsp, 250h
0x18000c7a3  pop     rbx
0x18000c7a4  retn
```
