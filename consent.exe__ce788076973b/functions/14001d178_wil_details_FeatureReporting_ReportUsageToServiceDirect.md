# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x14001d178`
- end: `0x14001d238`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `192`
- prototype: `_BOOL8 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x14001d0fc`

## callees

- `0x140018380`
- `0x14001858c`
- `0x14001d178`
- `0x14001e050`
- `0x14001f010`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  unsigned int v4; // edi
  int *v5; // rax
  _BYTE v7[24]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v8; // [rsp+48h] [rbp-30h] BYREF
  __int64 v9; // [rsp+58h] [rbp-20h]

  v3 = a2;
  v4 = a3;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v7,
         (volatile signed __int32 *)&Feature_ShadowAdmin__private_reporting,
         a3,
         SHIDWORD(a2));
  v8 = *(_OWORD *)v5;
  v9 = *((_QWORD *)v5 + 2);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(60288851, v4, 1, &Feature_ShadowAdmin__private_reporting, &v8);
  if ( (v3 & 0x400) != 0 && v4 != 254 )
    wil_RtlStagingConfig_RecordFeatureUsage(60288851, v4, (v3 >> 11) & 1);
  return (_DWORD)v9 == 0;
}

```

## disassembly

```asm
0x14001d178  mov     [rsp+arg_0], rbx
0x14001d17d  push    rdi
0x14001d17e  sub     rsp, 70h
0x14001d182  mov     rax, cs:__security_cookie
0x14001d189  xor     rax, rsp
0x14001d18c  mov     [rsp+78h+var_18], rax
0x14001d191  mov     r9, rdx
0x14001d194  lea     rcx, [rsp+78h+var_48]
0x14001d199  mov     rbx, rdx
0x14001d19c  shr     r9, 20h
0x14001d1a0  mov     rdx, cs:off_140025DE8
0x14001d1a7  mov     edi, r8d
0x14001d1aa  call    wil_details_FeatureReporting_RecordUsageInCache
0x14001d1af  movups  xmm1, xmmword ptr [rax]
0x14001d1b2  movups  [rsp+78h+var_30], xmm1
0x14001d1b7  movsd   xmm0, qword ptr [rax+10h]
0x14001d1bc  mov     rax, cs:g_wil_details_recordFeatureUsage
0x14001d1c3  movsd   [rsp+78h+var_20], xmm0
0x14001d1c9  test    rax, rax
0x14001d1cc  jz      short loc_14001D1F1
0x14001d1ce  mov     r9, cs:off_140025DE8
0x14001d1d5  lea     rcx, [rsp+78h+var_30]
0x14001d1da  mov     [rsp+78h+var_58], rcx
0x14001d1df  mov     r8d, 1
0x14001d1e5  mov     ecx, 397EF53h
0x14001d1ea  mov     edx, edi
0x14001d1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d1f1  bt      ebx, 0Ah
0x14001d1f5  jnb     short loc_14001D214
0x14001d1f7  cmp     edi, 0FEh
0x14001d1fd  jz      short loc_14001D214
0x14001d1ff  shr     ebx, 0Bh
0x14001d202  mov     edx, edi
0x14001d204  and     ebx, 1
0x14001d207  mov     ecx, 397EF53h
0x14001d20c  mov     r8d, ebx
0x14001d20f  call    wil_RtlStagingConfig_RecordFeatureUsage
0x14001d214  xor     eax, eax
0x14001d216  cmp     dword ptr [rsp+78h+var_20], eax
0x14001d21a  setz    al
0x14001d21d  mov     rcx, [rsp+78h+var_18]
0x14001d222  xor     rcx, rsp; StackCookie
0x14001d225  call    __security_check_cookie
0x14001d22a  mov     rbx, [rsp+78h+arg_0]
0x14001d232  add     rsp, 70h
0x14001d236  pop     rdi
0x14001d237  retn
```
