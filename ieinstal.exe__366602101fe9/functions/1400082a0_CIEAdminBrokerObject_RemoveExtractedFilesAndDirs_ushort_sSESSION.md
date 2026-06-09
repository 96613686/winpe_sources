# CIEAdminBrokerObject::RemoveExtractedFilesAndDirs(ushort *,sSESSION *)

- ea: `0x1400082a0`
- end: `0x1400082bd`
- name: `?RemoveExtractedFilesAndDirs@CIEAdminBrokerObject@@UEAAJPEAGPEAUsSESSION@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, struct sSESSION *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140005924`
- `0x1400082a0`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::RemoveExtractedFilesAndDirs(
        CIEAdminBrokerObject *this,
        unsigned __int16 *a2,
        struct sSESSION *a3)
{
  CActiveXInstallBroker *v3; // rcx
  __int64 result; // rax

  v3 = (CActiveXInstallBroker *)*((_QWORD *)this + 2);
  result = 2147500037LL;
  if ( v3 )
    return CActiveXInstallBroker::RemoveExtractedFilesAndDirs(v3, a2, a3);
  return result;
}

```

## disassembly

```asm
0x1400082a0  sub     rsp, 28h
0x1400082a4  mov     rcx, [rcx+10h]; this
0x1400082a8  mov     eax, 80004005h
0x1400082ad  test    rcx, rcx
0x1400082b0  jz      short loc_1400082B7
0x1400082b2  call    ?RemoveExtractedFilesAndDirs@CActiveXInstallBroker@@QEAAJPEAGPEAUsSESSION@@@Z; CActiveXInstallBroker::RemoveExtractedFilesAndDirs(ushort *,sSESSION *)
0x1400082b7  add     rsp, 28h
0x1400082bb  retn
```
