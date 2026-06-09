# _lambda_fca37cefd63776a0e871ccafc44a49bc_::_lambda_fca37cefd63776a0e871ccafc44a49bc_(Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor> *,uchar &,Windows::Internal::ServiceModuleBase * &,long &)

- ea: `0x180003e64`
- end: `0x180003e7c`
- name: `??0_lambda_fca37cefd63776a0e871ccafc44a49bc_@@QEAA@PEAV?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@AEAEAEAPEAVServiceModuleBase@23@AEAJ@Z`
- size: `24`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006dc0`

## pseudocode

```c
_QWORD *__fastcall _lambda_fca37cefd63776a0e871ccafc44a49bc_::_lambda_fca37cefd63776a0e871ccafc44a49bc_(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD *result; // rax

  a1[3] = a5;
  result = a1;
  *a1 = a2;
  a1[1] = a3;
  a1[2] = a4;
  return result;
}

```

## disassembly

```asm
0x180003e64  mov     rax, [rsp+arg_20]
0x180003e69  mov     [rcx+18h], rax
0x180003e6d  mov     rax, rcx
0x180003e70  mov     [rcx], rdx
0x180003e73  mov     [rcx+8], r8
0x180003e77  mov     [rcx+10h], r9
0x180003e7b  retn
```
