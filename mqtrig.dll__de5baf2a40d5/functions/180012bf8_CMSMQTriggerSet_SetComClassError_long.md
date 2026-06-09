# CMSMQTriggerSet::SetComClassError(long)

- ea: `0x180012bf8`
- end: `0x180012c7d`
- name: `?SetComClassError@CMSMQTriggerSet@@AEAAXJ@Z`
- size: `133`
- prototype: `void __fastcall(CMSMQTriggerSet *this, DWORD)`
- caller_count: `26`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010590`
- `0x180010b60`
- `0x180010ea0`
- `0x180011160`
- `0x180011330`
- `0x180011b60`
- `0x180011e40`
- `0x180012100`
- `0x180012300`
- `0x1800126d0`
- `0x180012b40`
- `0x180012f40`
- `0x180013b50`
- `0x180013c00`
- `0x18002052e`
- `0x18002059d`
- `0x18002060c`
- `0x18002067b`
- `0x1800206d8`
- `0x18002078f`
- `0x1800207ec`
- `0x180020849`
- `0x1800208a6`
- `0x180020a1b`
- `0x180020a9c`
- `0x180020af9`

## callees

- `0x18000e89c`
- `0x18001e35a`
- `0x18001e380`

## import_xrefs

- `ATL!__imp_AtlSetErrorInfo` at `0x180012c5e`
- `ATL!__imp_AtlSetErrorInfo` at `0x180012c5e`

## pseudocode

```c
void __fastcall CMSMQTriggerSet::SetComClassError(CMSMQTriggerSet *this, DWORD a2)
{
  unsigned int v3; // r8d
  WCHAR Buffer[256]; // [rsp+40h] [rbp-218h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  GetErrorDescription(a2, Buffer, v3);
  AtlSetErrorInfo(&CLSID_MSMQTriggerSet, Buffer, 0, 0, &GUID_NULL, a2, 0);
}

```

## disassembly

```asm
0x180012bf8  push    rbx
0x180012bfa  sub     rsp, 250h
0x180012c01  mov     rax, cs:__security_cookie
0x180012c08  xor     rax, rsp
0x180012c0b  mov     [rsp+258h+var_18], rax
0x180012c13  mov     ebx, edx
0x180012c15  lea     rcx, [rsp+258h+Buffer]; void *
0x180012c1a  xor     edx, edx; Val
0x180012c1c  mov     r8d, 200h; Size
0x180012c22  call    memset_0
0x180012c27  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x180012c2c  mov     ecx, ebx; dwMessageId
0x180012c2e  call    ?GetErrorDescription@@YAXJPEA_WK@Z; GetErrorDescription(long,wchar_t *,ulong)
0x180012c33  lea     rax, GUID_NULL
0x180012c3a  mov     [rsp+258h+var_228], 0
0x180012c43  mov     [rsp+258h+var_230], ebx
0x180012c47  lea     rdx, [rsp+258h+Buffer]
0x180012c4c  xor     r9d, r9d
0x180012c4f  mov     [rsp+258h+var_238], rax
0x180012c54  xor     r8d, r8d
0x180012c57  lea     rcx, CLSID_MSMQTriggerSet
0x180012c5e  call    cs:__imp_AtlSetErrorInfo
0x180012c64  mov     rcx, [rsp+258h+var_18]
0x180012c6c  xor     rcx, rsp; StackCookie
0x180012c6f  call    __security_check_cookie
0x180012c74  add     rsp, 250h
0x180012c7b  pop     rbx
0x180012c7c  retn
```
