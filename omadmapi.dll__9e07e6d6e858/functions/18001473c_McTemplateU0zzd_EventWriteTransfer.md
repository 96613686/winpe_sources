# McTemplateU0zzd_EventWriteTransfer

- ea: `0x18001473c`
- end: `0x1800147be`
- name: `McTemplateU0zzd_EventWriteTransfer`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180019684`

## callees

- `0x1800031b0`
- `0x180014514`

## string_xrefs

- `0x18001476f`: `Failed to update doc status`
- `0x180014755`: `DC_CheckAndUpdatePendingDocs`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzd_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-58h] BYREF
  const wchar_t *v7; // [rsp+40h] [rbp-48h]
  __int64 v8; // [rsp+48h] [rbp-40h]
  const wchar_t *v9; // [rsp+50h] [rbp-38h]
  __int64 v10; // [rsp+58h] [rbp-30h]
  __int64 *v11; // [rsp+60h] [rbp-28h]
  __int64 v12; // [rsp+68h] [rbp-20h]

  v8 = 58;
  v7 = L"DC_CheckAndUpdatePendingDocs";
  v10 = 56;
  v9 = L"Failed to update doc status";
  v11 = &a5;
  v12 = 4;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)MDM_ENTERPRISE_DIAGNOSTICS_Context,
           (const EVENT_DESCRIPTOR *)OrchestratorGenericFailure,
           a3,
           4u,
           &v6);
}

```

## disassembly

```asm
0x18001473c  mov     r11, rsp
0x18001473f  sub     rsp, 88h
0x180014746  mov     rax, cs:__security_cookie
0x18001474d  xor     rax, rsp
0x180014750  mov     [rsp+88h+var_18], rax
0x180014755  lea     rax, aDcCheckandupda; "DC_CheckAndUpdatePendingDocs"
0x18001475c  mov     qword ptr [r11-40h], 3Ah ; ':'
0x180014764  mov     [r11-48h], rax
0x180014768  lea     rdx, OrchestratorGenericFailure
0x18001476f  lea     rax, aFailedToUpdate; "Failed to update doc status"
0x180014776  mov     qword ptr [r11-30h], 38h ; '8'
0x18001477e  mov     [r11-38h], rax
0x180014782  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180014789  lea     rax, [r11+28h]
0x18001478d  mov     r9d, 4
0x180014793  mov     [r11-28h], rax
0x180014797  lea     rax, [r11-58h]
0x18001479b  mov     [r11-68h], rax
0x18001479f  mov     [r11-20h], r9
0x1800147a3  call    McGenEventWrite_EventWriteTransfer
0x1800147a8  mov     rcx, [rsp+88h+var_18]
0x1800147ad  xor     rcx, rsp; StackCookie
0x1800147b0  call    __security_check_cookie
0x1800147b5  add     rsp, 88h
0x1800147bc  retn
```
