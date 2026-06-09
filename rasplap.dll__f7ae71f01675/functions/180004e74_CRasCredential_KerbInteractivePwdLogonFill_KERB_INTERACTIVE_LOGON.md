# CRasCredential::_KerbInteractivePwdLogonFill(_KERB_INTERACTIVE_LOGON *)

- ea: `0x180004e74`
- end: `0x180004f54`
- name: `?_KerbInteractivePwdLogonFill@CRasCredential@@AEAAJPEAU_KERB_INTERACTIVE_LOGON@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(CRasCredential *__hidden this, struct _KERB_INTERACTIVE_LOGON *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180004bd8`

## callees

- `0x180004e74`
- `0x18000542c`
- `0x1800054ac`
- `0x180005648`
- `0x1800086d4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180004f42`
- `ole32!CoTaskMemFree` at `0x180004f42`
- `rtutils!TracePrintfExA` at `0x180004ed5`
- `rtutils!TracePrintfExA` at `0x180004ed5`

## pseudocode

```c
__int64 __fastcall CRasCredential::_KerbInteractivePwdLogonFill(
        CRasCredential *this,
        struct _KERB_INTERACTIVE_LOGON *a2)
{
  int v4; // edi
  const wchar_t *v5; // rbx
  void *v6; // rcx
  void *v8; // [rsp+68h] [rbp+10h] BYREF

  v8 = 0;
  a2->MessageType = KerbInteractiveLogon;
  v4 = CRasCredential::_UnformatUsername(this);
  if ( v4 >= 0 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "CRasCredential::Logon called for [%S]: Username:[%S], Domain:[%S]",
        (const wchar_t *)this + 10,
        (const wchar_t *)this + 278,
        (const wchar_t *)this + 792);
    v4 = UnicodeStringStringHijack((char *)this + 1584, &a2->LogonDomainName);
    if ( v4 >= 0 )
    {
      v4 = UnicodeStringStringHijack((char *)this + 556, &a2->UserName);
      if ( v4 >= 0 )
      {
        v5 = (const wchar_t *)((char *)this + 1070);
        EncodePasswordW(v5);
        v4 = StringStringCoAllocCopy(v5, &v8);
        EncodePasswordW(v5);
        v6 = v8;
        if ( v4 < 0 || (v4 = UnicodeStringStringHijack(v8, &a2->Password), v4 < 0) )
        {
          if ( v6 )
            CoTaskMemFree(v6);
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180004e74  push    rbx
0x180004e76  push    rsi
0x180004e77  push    rdi
0x180004e78  push    r14
0x180004e7a  sub     rsp, 38h
0x180004e7e  mov     r14, rdx
0x180004e81  mov     [rsp+58h+arg_8], 0
0x180004e8a  mov     rbx, rcx
0x180004e8d  mov     dword ptr [rdx], 2
0x180004e93  call    ?_UnformatUsername@CRasCredential@@AEAAJXZ; CRasCredential::_UnformatUsername(void)
0x180004e98  mov     edi, eax
0x180004e9a  test    eax, eax
0x180004e9c  js      loc_180004F48
0x180004ea2  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180004ea8  lea     rdi, [rbx+630h]
0x180004eaf  lea     rsi, [rbx+22Ch]
0x180004eb6  cmp     ecx, 0FFFFFFFFh
0x180004eb9  jz      short loc_180004EDB
0x180004ebb  lea     r9, [rbx+14h]
0x180004ebf  mov     [rsp+58h+var_30], rdi
0x180004ec4  lea     r8, aCrascredential_2; "CRasCredential::Logon called for [%S]: "...
0x180004ecb  mov     [rsp+58h+var_38], rsi
0x180004ed0  mov     edx, 0Ch; dwFlags
0x180004ed5  call    cs:__imp_TracePrintfExA
0x180004edb  lea     rdx, [r14+8]
0x180004edf  mov     rcx, rdi
0x180004ee2  call    _UnicodeStringStringHijack
0x180004ee7  mov     edi, eax
0x180004ee9  test    eax, eax
0x180004eeb  js      short loc_180004F48
0x180004eed  lea     rdx, [r14+18h]
0x180004ef1  mov     rcx, rsi
0x180004ef4  call    _UnicodeStringStringHijack
0x180004ef9  mov     edi, eax
0x180004efb  test    eax, eax
0x180004efd  js      short loc_180004F48
0x180004eff  add     rbx, 42Eh
0x180004f06  mov     rcx, rbx
0x180004f09  call    EncodePasswordW
0x180004f0e  lea     rdx, [rsp+58h+arg_8]
0x180004f13  mov     rcx, rbx; pszSrc
0x180004f16  call    _StringStringCoAllocCopy
0x180004f1b  mov     rcx, rbx
0x180004f1e  mov     edi, eax
0x180004f20  call    EncodePasswordW
0x180004f25  mov     rcx, [rsp+58h+arg_8]
0x180004f2a  test    edi, edi
0x180004f2c  js      short loc_180004F3D
0x180004f2e  lea     rdx, [r14+28h]
0x180004f32  call    _UnicodeStringStringHijack
0x180004f37  mov     edi, eax
0x180004f39  test    eax, eax
0x180004f3b  jns     short loc_180004F48
0x180004f3d  test    rcx, rcx
0x180004f40  jz      short loc_180004F48
0x180004f42  call    cs:__imp_CoTaskMemFree
0x180004f48  mov     eax, edi
0x180004f4a  add     rsp, 38h
0x180004f4e  pop     r14
0x180004f50  pop     rdi
0x180004f51  pop     rsi
0x180004f52  pop     rbx
0x180004f53  retn
```
