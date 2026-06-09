# CIEAdminBrokerObject::ExtractFiles(ushort *,char const *,sSESSION *)

- ea: `0x140007df0`
- end: `0x140007e0d`
- name: `?ExtractFiles@CIEAdminBrokerObject@@UEAAJPEAGPEBDPEAUsSESSION@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, const char *, struct sSESSION *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400048c0`
- `0x140007df0`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::ExtractFiles(
        CIEAdminBrokerObject *this,
        unsigned __int16 *a2,
        const char *a3,
        struct sSESSION *a4)
{
  CActiveXInstallBroker *v4; // rcx
  __int64 result; // rax

  v4 = (CActiveXInstallBroker *)*((_QWORD *)this + 2);
  result = 2147500037LL;
  if ( v4 )
    return CActiveXInstallBroker::ExtractFiles(v4, a2, a3, a4);
  return result;
}

```

## disassembly

```asm
0x140007df0  sub     rsp, 28h
0x140007df4  mov     rcx, [rcx+10h]; this
0x140007df8  mov     eax, 80004005h
0x140007dfd  test    rcx, rcx
0x140007e00  jz      short loc_140007E07
0x140007e02  call    ?ExtractFiles@CActiveXInstallBroker@@QEAAJPEAGPEBDPEAUsSESSION@@@Z; CActiveXInstallBroker::ExtractFiles(ushort *,char const *,sSESSION *)
0x140007e07  add     rsp, 28h
0x140007e0b  retn
```
