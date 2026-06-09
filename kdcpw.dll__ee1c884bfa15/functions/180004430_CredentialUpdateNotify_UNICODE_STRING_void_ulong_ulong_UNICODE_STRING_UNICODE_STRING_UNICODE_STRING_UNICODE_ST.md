# CredentialUpdateNotify(_UNICODE_STRING *,void *,ulong,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void * *,ulong *)

- ea: `0x180004430`
- end: `0x180004463`
- name: `?CredentialUpdateNotify@@YAJPEAU_UNICODE_STRING@@PEAXKK0000PEAPEAXPEAK@Z`
- size: `51`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void *, __int64, __int64, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180007944`

## pseudocode

```c
__int64 __fastcall CredentialUpdateNotify(
        struct _UNICODE_STRING *a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        struct _UNICODE_STRING *a5,
        struct _UNICODE_STRING *a6,
        struct _UNICODE_STRING *a7,
        struct _UNICODE_STRING *a8,
        void **a9,
        unsigned int *a10)
{
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DropLegacyKerberosKeyStorage>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DropLegacyKerberosKeyStorage>::GetImpl'::`2'::impl,
    a2);
  *a9 = 0;
  *a10 = 0;
  return 3221226353LL;
}

```

## disassembly

```asm
0x180004430  sub     rsp, 28h
0x180004434  mov     dl, 1
0x180004436  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DropLegacyKerberosKeyStorage@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DropLegacyKerberosKeyStorage@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DropLegacyKerberosKeyStorage> `wil::Feature<__WilFeatureTraits_Feature_DropLegacyKerberosKeyStorage>::GetImpl(void)'::`2'::impl
0x18000443d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DropLegacyKerberosKeyStorage@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DropLegacyKerberosKeyStorage>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180004442  mov     rax, [rsp+28h+arg_40]
0x180004447  mov     qword ptr [rax], 0
0x18000444e  mov     rax, [rsp+28h+arg_48]
0x180004453  mov     dword ptr [rax], 0
0x180004459  mov     eax, 0C0000371h
0x18000445e  add     rsp, 28h
0x180004462  retn
```
