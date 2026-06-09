# DataSharingServiceTelemetry::GetAuthorizedSharingTokenEDPCheckFailed(void)

- ea: `0x18000dd00`
- end: `0x18000dd8d`
- name: `?GetAuthorizedSharingTokenEDPCheckFailed@DataSharingServiceTelemetry@@SAXXZ`
- size: `141`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000da68`

## callees

- `0x1800017ec`
- `0x180001818`
- `0x180005c54`
- `0x18000dd00`
- `0x18001b340`

## pseudocode

```c
void DataSharingServiceTelemetry::GetAuthorizedSharingTokenEDPCheckFailed(void)
{
  const struct _tlgProvider_t *v0; // rax
  __int64 v1; // r8
  __int64 v2; // r9
  __int64 v3; // r10
  __int64 v4; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v5[32]; // [rsp+38h] [rbp-40h] BYREF
  __int64 *v6; // [rsp+58h] [rbp-20h]
  __int64 v7; // [rsp+60h] [rbp-18h]

  v0 = DataSharingServiceProvider::Provider();
  if ( *(_DWORD *)v0 > 5u )
  {
    if ( (unsigned __int8)tlgKeywordOn(v0, 0x200000000000LL, v1, v2) )
    {
      v4 = 0x1000000;
      v6 = &v4;
      v7 = 8;
      tlgWriteTransfer_EventWriteTransfer(v3, word_180025A92, 0, 0, 3, v5);
    }
  }
}

```

## disassembly

```asm
0x18000dd00  sub     rsp, 78h
0x18000dd04  mov     rax, cs:__security_cookie
0x18000dd0b  xor     rax, rsp
0x18000dd0e  mov     [rsp+78h+var_10], rax
0x18000dd13  call    ?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ; DataSharingServiceProvider::Provider(void)
0x18000dd18  mov     r10, rax
0x18000dd1b  mov     ecx, [rax]
0x18000dd1d  cmp     ecx, 5
0x18000dd20  jbe     short loc_18000DD7B
0x18000dd22  mov     rdx, 200000000000h
0x18000dd2c  mov     rcx, rax
0x18000dd2f  call    _tlgKeywordOn
0x18000dd34  test    al, al
0x18000dd36  jz      short loc_18000DD7B
0x18000dd38  lea     rax, [rsp+78h+var_48]
0x18000dd3d  mov     [rsp+78h+var_48], 1000000h
0x18000dd46  mov     [rsp+78h+var_20], rax
0x18000dd4b  lea     rdx, word_180025A92
0x18000dd52  lea     rax, [rsp+78h+var_40]
0x18000dd57  mov     [rsp+78h+var_18], 8
0x18000dd60  mov     [rsp+78h+var_50], rax
0x18000dd65  xor     r9d, r9d
0x18000dd68  xor     r8d, r8d
0x18000dd6b  mov     [rsp+78h+var_58], 3
0x18000dd73  mov     rcx, r10
0x18000dd76  call    _tlgWriteTransfer_EventWriteTransfer
0x18000dd7b  mov     rcx, [rsp+78h+var_10]
0x18000dd80  xor     rcx, rsp; StackCookie
0x18000dd83  call    __security_check_cookie
0x18000dd88  add     rsp, 78h
0x18000dd8c  retn
```
