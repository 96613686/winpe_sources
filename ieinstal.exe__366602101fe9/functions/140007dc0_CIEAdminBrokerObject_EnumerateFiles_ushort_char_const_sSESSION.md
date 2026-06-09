# CIEAdminBrokerObject::EnumerateFiles(ushort *,char const *,sSESSION *)

- ea: `0x140007dc0`
- end: `0x140007ddd`
- name: `?EnumerateFiles@CIEAdminBrokerObject@@UEAAJPEAGPEBDPEAUsSESSION@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, const char *, struct sSESSION *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140004738`
- `0x140007dc0`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::EnumerateFiles(
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
    return CActiveXInstallBroker::EnumerateFiles(v4, a2, a3, a4);
  return result;
}

```

## disassembly

```asm
0x140007dc0  sub     rsp, 28h
0x140007dc4  mov     rcx, [rcx+10h]; this
0x140007dc8  mov     eax, 80004005h
0x140007dcd  test    rcx, rcx
0x140007dd0  jz      short loc_140007DD7
0x140007dd2  call    ?EnumerateFiles@CActiveXInstallBroker@@QEAAJPEAGPEBDPEAUsSESSION@@@Z; CActiveXInstallBroker::EnumerateFiles(ushort *,char const *,sSESSION *)
0x140007dd7  add     rsp, 28h
0x140007ddb  retn
```
