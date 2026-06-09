# BrowserTelemetry::IESessionIDInvalidated(void)

- ea: `0x140003fec`
- end: `0x1400040bf`
- name: `?IESessionIDInvalidated@BrowserTelemetry@@SAXXZ`
- size: `211`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400014e4`

## callees

- `0x1400012dc`
- `0x140001310`
- `0x140003fec`
- `0x1400059b0`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x140004049`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x140004049`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x14000403b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x14000403b`

## pseudocode

```c
void __fastcall BrowserTelemetry::IESessionIDInvalidated(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  unsigned int v4; // eax
  struct IE_GLOBAL_THREAD_STATE *v5; // rbx
  __int64 CLSID; // rax
  char v7; // [rsp+30h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-29h] BYREF
  __int64 v9; // [rsp+60h] [rbp-9h]
  __int64 v10; // [rsp+68h] [rbp-1h]
  struct IE_GLOBAL_THREAD_STATE *v11; // [rsp+70h] [rbp+7h]
  __int64 v12; // [rsp+78h] [rbp+Fh]
  char *v13; // [rsp+80h] [rbp+17h]
  __int64 v14; // [rsp+88h] [rbp+1Fh]

  v3 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v4 = dword_14000A000;
  *(_BYTE *)(v3 + 1) = 1;
  if ( v4 > 5 && (unsigned __int8)tlgKeywordOn(a1, a2, a3) )
  {
    v7 = 1;
    v5 = GlobalThreadState();
    CLSID = IEConfiguration_GetCLSID(268435459);
    v14 = 1;
    v9 = CLSID;
    v13 = &v7;
    v11 = v5;
    v12 = 16;
    v10 = 16;
    tlgWriteTransfer_BrowserWriteTransfer((__int64)&dword_14000A000, (unsigned __int8 *)byte_14000811F, 0, 0, 5u, &v8);
  }
  *(_BYTE *)(v3 + 1) = 0;
}

```

## disassembly

```asm
0x140003fec  push    rbp
0x140003fee  push    rbx
0x140003fef  push    rdi
0x140003ff0  push    r14
0x140003ff2  lea     rbp, [rsp-3Fh]
0x140003ff7  sub     rsp, 0A8h
0x140003ffe  mov     rax, cs:__security_cookie
0x140004005  xor     rax, rsp
0x140004008  mov     [rbp+57h+var_30], rax
0x14000400c  mov     rax, gs:58h
0x140004015  mov     r14d, 1
0x14000401b  mov     rdi, [rax]
0x14000401e  mov     eax, cs:dword_14000A000
0x140004024  mov     byte ptr [r14+rdi], 1
0x140004029  cmp     eax, 5
0x14000402c  jbe     short loc_1400040A1
0x14000402e  call    _tlgKeywordOn
0x140004033  test    al, al
0x140004035  jz      short loc_1400040A1
0x140004037  mov     [rbp+57h+var_90], 1
0x14000403b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x140004041  mov     ecx, 10000003h
0x140004046  mov     rbx, rax
0x140004049  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x14000404f  lea     rcx, [rbp+57h+var_90]
0x140004053  mov     [rbp+57h+var_38], 1
0x14000405b  mov     [rbp+57h+var_60], rax
0x14000405f  lea     rdx, byte_14000811F
0x140004066  lea     rax, [rbp+57h+var_80]
0x14000406a  mov     [rbp+57h+var_40], rcx
0x14000406e  mov     [rsp+0C0h+var_98], rax
0x140004073  lea     rcx, dword_14000A000
0x14000407a  xor     r9d, r9d
0x14000407d  mov     [rsp+0C0h+var_A0], 5
0x140004085  xor     r8d, r8d
0x140004088  mov     [rbp+57h+var_50], rbx
0x14000408c  mov     [rbp+57h+var_48], 10h
0x140004094  mov     [rbp+57h+var_58], 10h
0x14000409c  call    _tlgWriteTransfer_BrowserWriteTransfer
0x1400040a1  mov     byte ptr [r14+rdi], 0
0x1400040a6  mov     rcx, [rbp+57h+var_30]
0x1400040aa  xor     rcx, rsp; StackCookie
0x1400040ad  call    __security_check_cookie
0x1400040b2  add     rsp, 0A8h
0x1400040b9  pop     r14
0x1400040bb  pop     rdi
0x1400040bc  pop     rbx
0x1400040bd  pop     rbp
0x1400040be  retn
```
