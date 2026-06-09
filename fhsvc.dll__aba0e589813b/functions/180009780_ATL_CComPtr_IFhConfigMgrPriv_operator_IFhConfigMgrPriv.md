# ATL::CComPtr<IFhConfigMgrPriv>::operator=(IFhConfigMgrPriv *)

- ea: `0x180009780`
- end: `0x1800097ac`
- name: `??4?$CComPtr@UIFhConfigMgrPriv@@@ATL@@QEAAPEAUIFhConfigMgrPriv@@PEAU2@@Z`
- size: `44`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010894`

## callees

- `0x180009780`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IFhConfigMgrPriv>::operator=(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *a1 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180009780  push    rbx
0x180009782  sub     rsp, 20h
0x180009786  mov     rbx, rcx
0x180009789  mov     rcx, [rcx]
0x18000978c  test    rcx, rcx
0x18000978f  jz      short loc_1800097A4
0x180009791  mov     rax, [rcx]
0x180009794  mov     rax, [rax+10h]
0x180009798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000979d  mov     qword ptr [rbx], 0
0x1800097a4  xor     eax, eax
0x1800097a6  add     rsp, 20h
0x1800097aa  pop     rbx
0x1800097ab  retn
```
