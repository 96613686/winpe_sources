# CMSMQRuleHandler::SetComClassError(long)

- ea: `0x18000995c`
- end: `0x1800099e1`
- name: `?SetComClassError@CMSMQRuleHandler@@AEAAXJ@Z`
- size: `133`
- prototype: `void __fastcall(CMSMQRuleHandler *this, DWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005930`
- `0x180006a50`
- `0x18001ee86`
- `0x18001efb1`

## callees

- `0x18000e89c`
- `0x18001e35a`
- `0x18001e380`

## import_xrefs

- `ATL!__imp_AtlSetErrorInfo` at `0x1800099c2`
- `ATL!__imp_AtlSetErrorInfo` at `0x1800099c2`

## pseudocode

```c
void __fastcall CMSMQRuleHandler::SetComClassError(CMSMQRuleHandler *this, DWORD a2)
{
  unsigned int v3; // r8d
  WCHAR Buffer[256]; // [rsp+40h] [rbp-218h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  GetErrorDescription(a2, Buffer, v3);
  AtlSetErrorInfo(&CLSID_MSMQRuleHandler, Buffer, 0, 0, &GUID_NULL, a2, 0);
}

```

## disassembly

```asm
0x18000995c  push    rbx
0x18000995e  sub     rsp, 250h
0x180009965  mov     rax, cs:__security_cookie
0x18000996c  xor     rax, rsp
0x18000996f  mov     [rsp+258h+var_18], rax
0x180009977  mov     ebx, edx
0x180009979  lea     rcx, [rsp+258h+Buffer]; void *
0x18000997e  xor     edx, edx; Val
0x180009980  mov     r8d, 200h; Size
0x180009986  call    memset_0
0x18000998b  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x180009990  mov     ecx, ebx; dwMessageId
0x180009992  call    ?GetErrorDescription@@YAXJPEA_WK@Z; GetErrorDescription(long,wchar_t *,ulong)
0x180009997  lea     rax, GUID_NULL
0x18000999e  mov     [rsp+258h+var_228], 0
0x1800099a7  mov     [rsp+258h+var_230], ebx
0x1800099ab  lea     rdx, [rsp+258h+Buffer]
0x1800099b0  xor     r9d, r9d
0x1800099b3  mov     [rsp+258h+var_238], rax
0x1800099b8  xor     r8d, r8d
0x1800099bb  lea     rcx, CLSID_MSMQRuleHandler
0x1800099c2  call    cs:__imp_AtlSetErrorInfo
0x1800099c8  mov     rcx, [rsp+258h+var_18]
0x1800099d0  xor     rcx, rsp; StackCookie
0x1800099d3  call    __security_check_cookie
0x1800099d8  add     rsp, 250h
0x1800099df  pop     rbx
0x1800099e0  retn
```
