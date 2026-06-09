# BrowserTelemetry::IEApplicationStart<int>(int &&)

- ea: `0x14000244c`
- end: `0x140002540`
- name: `??$IEApplicationStart@H@BrowserTelemetry@@SAX$$QEAH@Z`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400014e4`

## callees

- `0x1400012dc`
- `0x140001310`
- `0x14000244c`
- `0x1400059b0`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1400024ba`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1400024ba`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1400024ac`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1400024ac`

## pseudocode

```c
ULONG __fastcall BrowserTelemetry::IEApplicationStart<int>(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  ULONG result; // eax
  int *v4; // r8
  struct IE_GLOBAL_THREAD_STATE *v5; // rbx
  __int64 CLSID; // rax
  char v7; // [rsp+30h] [rbp-49h] BYREF
  int v8; // [rsp+34h] [rbp-45h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+40h] [rbp-39h] BYREF
  __int64 v10; // [rsp+60h] [rbp-19h]
  __int64 v11; // [rsp+68h] [rbp-11h]
  struct IE_GLOBAL_THREAD_STATE *v12; // [rsp+70h] [rbp-9h]
  __int64 v13; // [rsp+78h] [rbp-1h]
  char *v14; // [rsp+80h] [rbp+7h]
  __int64 v15; // [rsp+88h] [rbp+Fh]
  int *v16; // [rsp+90h] [rbp+17h]
  __int64 v17; // [rsp+98h] [rbp+1Fh]

  v2 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
  result = dword_14000A000;
  *(_BYTE *)(v2 + 1) = 1;
  if ( result > 5 )
  {
    result = tlgKeywordOn(a1, a2, a1);
    if ( (_BYTE)result )
    {
      v8 = *v4;
      v7 = 1;
      v5 = GlobalThreadState();
      CLSID = IEConfiguration_GetCLSID(268435459);
      v17 = 4;
      v16 = &v8;
      v10 = CLSID;
      v14 = &v7;
      v15 = 1;
      v12 = v5;
      v13 = 16;
      v11 = 16;
      result = tlgWriteTransfer_BrowserWriteTransfer(
                 (__int64)&dword_14000A000,
                 (unsigned __int8 *)byte_140008057,
                 0,
                 0,
                 6u,
                 &v9);
    }
  }
  *(_BYTE *)(v2 + 1) = 0;
  return result;
}

```

## disassembly

```asm
0x14000244c  push    rbp
0x14000244e  push    rbx
0x14000244f  push    rdi
0x140002450  push    r14
0x140002452  lea     rbp, [rsp-3Fh]
0x140002457  sub     rsp, 0B8h
0x14000245e  mov     rax, cs:__security_cookie
0x140002465  xor     rax, rsp
0x140002468  mov     [rbp+57h+var_30], rax
0x14000246c  mov     rax, gs:58h
0x140002475  mov     r8, rcx
0x140002478  mov     r14d, 1
0x14000247e  mov     rdi, [rax]
0x140002481  mov     eax, cs:dword_14000A000
0x140002487  mov     byte ptr [r14+rdi], 1
0x14000248c  cmp     eax, 5
0x14000248f  jbe     loc_140002522
0x140002495  call    _tlgKeywordOn
0x14000249a  test    al, al
0x14000249c  jz      loc_140002522
0x1400024a2  mov     eax, [r8]
0x1400024a5  mov     [rbp+57h+var_9C], eax
0x1400024a8  mov     [rbp+57h+var_A0], 1
0x1400024ac  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1400024b2  mov     ecx, 10000003h
0x1400024b7  mov     rbx, rax
0x1400024ba  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1400024c0  lea     rcx, [rbp+57h+var_9C]
0x1400024c4  mov     [rbp+57h+var_38], 4
0x1400024cc  mov     [rbp+57h+var_40], rcx
0x1400024d0  lea     rdx, byte_140008057
0x1400024d7  lea     rcx, [rbp+57h+var_A0]
0x1400024db  mov     [rbp+57h+var_70], rax
0x1400024df  lea     rax, [rbp+57h+var_90]
0x1400024e3  mov     [rbp+57h+var_50], rcx
0x1400024e7  mov     [rsp+0D0h+var_A8], rax
0x1400024ec  lea     rcx, dword_14000A000
0x1400024f3  xor     r9d, r9d
0x1400024f6  mov     [rbp+57h+var_48], 1
0x1400024fe  xor     r8d, r8d
0x140002501  mov     [rbp+57h+var_60], rbx
0x140002505  mov     [rbp+57h+var_58], 10h
0x14000250d  mov     [rbp+57h+var_68], 10h
0x140002515  mov     [rsp+0D0h+var_B0], 6
0x14000251d  call    _tlgWriteTransfer_BrowserWriteTransfer
0x140002522  mov     byte ptr [r14+rdi], 0
0x140002527  mov     rcx, [rbp+57h+var_30]
0x14000252b  xor     rcx, rsp; StackCookie
0x14000252e  call    __security_check_cookie
0x140002533  add     rsp, 0B8h
0x14000253a  pop     r14
0x14000253c  pop     rdi
0x14000253d  pop     rbx
0x14000253e  pop     rbp
0x14000253f  retn
```
