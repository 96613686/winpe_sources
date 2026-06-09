# CMSMQRuleSet::SetComClassError(long)

- ea: `0x18000bd0c`
- end: `0x18000bd91`
- name: `?SetComClassError@CMSMQRuleSet@@AEAAXJ@Z`
- size: `133`
- prototype: `void __fastcall(CMSMQRuleSet *this, DWORD)`
- caller_count: `16`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a300`
- `0x18000aa80`
- `0x18000aea0`
- `0x18000b310`
- `0x18000b5e0`
- `0x18000bb20`
- `0x18000bda0`
- `0x18000c340`
- `0x18000c4b0`
- `0x18001f81b`
- `0x18001f92f`
- `0x18001fa21`
- `0x18001fb01`
- `0x18001fcda`
- `0x18001fdcc`
- `0x18001feac`

## callees

- `0x18000e89c`
- `0x18001e35a`
- `0x18001e380`

## import_xrefs

- `ATL!__imp_AtlSetErrorInfo` at `0x18000bd72`
- `ATL!__imp_AtlSetErrorInfo` at `0x18000bd72`

## pseudocode

```c
void __fastcall CMSMQRuleSet::SetComClassError(CMSMQRuleSet *this, DWORD a2)
{
  unsigned int v3; // r8d
  WCHAR Buffer[256]; // [rsp+40h] [rbp-218h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  GetErrorDescription(a2, Buffer, v3);
  AtlSetErrorInfo(&CLSID_MSMQRuleSet, Buffer, 0, 0, &GUID_NULL, a2, 0);
}

```

## disassembly

```asm
0x18000bd0c  push    rbx
0x18000bd0e  sub     rsp, 250h
0x18000bd15  mov     rax, cs:__security_cookie
0x18000bd1c  xor     rax, rsp
0x18000bd1f  mov     [rsp+258h+var_18], rax
0x18000bd27  mov     ebx, edx
0x18000bd29  lea     rcx, [rsp+258h+Buffer]; void *
0x18000bd2e  xor     edx, edx; Val
0x18000bd30  mov     r8d, 200h; Size
0x18000bd36  call    memset_0
0x18000bd3b  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x18000bd40  mov     ecx, ebx; dwMessageId
0x18000bd42  call    ?GetErrorDescription@@YAXJPEA_WK@Z; GetErrorDescription(long,wchar_t *,ulong)
0x18000bd47  lea     rax, GUID_NULL
0x18000bd4e  mov     [rsp+258h+var_228], 0
0x18000bd57  mov     [rsp+258h+var_230], ebx
0x18000bd5b  lea     rdx, [rsp+258h+Buffer]
0x18000bd60  xor     r9d, r9d
0x18000bd63  mov     [rsp+258h+var_238], rax
0x18000bd68  xor     r8d, r8d
0x18000bd6b  lea     rcx, CLSID_MSMQRuleSet
0x18000bd72  call    cs:__imp_AtlSetErrorInfo
0x18000bd78  mov     rcx, [rsp+258h+var_18]
0x18000bd80  xor     rcx, rsp; StackCookie
0x18000bd83  call    __security_check_cookie
0x18000bd88  add     rsp, 250h
0x18000bd8f  pop     rbx
0x18000bd90  retn
```
