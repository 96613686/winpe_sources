# CIEAdminBrokerObject::UpdateLanguageCheck(ushort *,ushort const *,_FILETIME)

- ea: `0x140008580`
- end: `0x14000859d`
- name: `?UpdateLanguageCheck@CIEAdminBrokerObject@@UEAAJPEAGPEBGU_FILETIME@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, const unsigned __int16 *, struct _FILETIME)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140006d9c`
- `0x140008580`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::UpdateLanguageCheck(
        CIEAdminBrokerObject *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _FILETIME a4)
{
  CActiveXInstallBroker *v4; // rcx
  __int64 result; // rax

  v4 = (CActiveXInstallBroker *)*((_QWORD *)this + 2);
  result = 2147500037LL;
  if ( v4 )
    return CActiveXInstallBroker::UpdateLanguageCheck(v4, a2, a3, a4);
  return result;
}

```

## disassembly

```asm
0x140008580  sub     rsp, 28h
0x140008584  mov     rcx, [rcx+10h]; this
0x140008588  mov     eax, 80004005h
0x14000858d  test    rcx, rcx
0x140008590  jz      short loc_140008597
0x140008592  call    ?UpdateLanguageCheck@CActiveXInstallBroker@@QEAAJPEAGPEBGU_FILETIME@@@Z; CActiveXInstallBroker::UpdateLanguageCheck(ushort *,ushort const *,_FILETIME)
0x140008597  add     rsp, 28h
0x14000859b  retn
```
