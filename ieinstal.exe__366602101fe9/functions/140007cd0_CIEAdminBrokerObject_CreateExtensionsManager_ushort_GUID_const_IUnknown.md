# CIEAdminBrokerObject::CreateExtensionsManager(ushort *,_GUID const &,IUnknown * *)

- ea: `0x140007cd0`
- end: `0x140007ced`
- name: `?CreateExtensionsManager@CIEAdminBrokerObject@@UEAAJPEAGAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400044c0`
- `0x140007cd0`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::CreateExtensionsManager(
        CIEAdminBrokerObject *this,
        unsigned __int16 *a2,
        const struct _GUID *a3,
        LPVOID *a4)
{
  CActiveXInstallBroker *v4; // rcx
  __int64 result; // rax

  v4 = (CActiveXInstallBroker *)*((_QWORD *)this + 2);
  result = 2147500037LL;
  if ( v4 )
    return CActiveXInstallBroker::CreateExtensionsManager(v4, a2, a3, a4);
  return result;
}

```

## disassembly

```asm
0x140007cd0  sub     rsp, 28h
0x140007cd4  mov     rcx, [rcx+10h]; this
0x140007cd8  mov     eax, 80004005h
0x140007cdd  test    rcx, rcx
0x140007ce0  jz      short loc_140007CE7
0x140007ce2  call    ?CreateExtensionsManager@CActiveXInstallBroker@@QEAAJPEAGAEBU_GUID@@PEAPEAUIUnknown@@@Z; CActiveXInstallBroker::CreateExtensionsManager(ushort *,_GUID const &,IUnknown * *)
0x140007ce7  add     rsp, 28h
0x140007ceb  retn
```
