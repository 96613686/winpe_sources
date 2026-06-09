# CImpIMDCOMSINKW::ComMDShutdownNotify(void)

- ea: `0x18000c270`
- end: `0x18000c2e2`
- name: `?ComMDShutdownNotify@CImpIMDCOMSINKW@@UEAAJXZ`
- size: `114`
- prototype: `__int64 __fastcall(CImpIMDCOMSINKW *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007a50`
- `0x18000c270`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c2ca`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c2ca`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c2b0`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c2b0`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c2b9`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c2b9`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c28b`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c28b`

## pseudocode

```c
__int64 __fastcall CImpIMDCOMSINKW::ComMDShutdownNotify(CImpIMDCOMSINKW *this)
{
  CReaderWriterLock3 *v1; // rbx
  unsigned int v3; // esi
  CADMCOMW *v4; // rcx

  v1 = (CImpIMDCOMSINKW *)((char *)this + 20);
  v3 = 0;
  CReaderWriterLock3::ReadLock((CImpIMDCOMSINKW *)((char *)this + 20));
  v4 = (CADMCOMW *)*((_QWORD *)this + 1);
  if ( v4 )
    v3 = CADMCOMW::NotifySinks(v4, 0, 0, 0, 0);
  CReaderWriterLock3::ReadUnlock(v1);
  CReaderWriterLock3::WriteLock(v1);
  *((_QWORD *)this + 1) = 0;
  CReaderWriterLock3::WriteUnlock(v1);
  return v3;
}

```

## disassembly

```asm
0x18000c270  mov     [rsp+arg_0], rbx
0x18000c275  mov     [rsp+arg_8], rsi
0x18000c27a  push    rdi
0x18000c27b  sub     rsp, 30h
0x18000c27f  lea     rbx, [rcx+14h]
0x18000c283  mov     rdi, rcx
0x18000c286  mov     rcx, rbx
0x18000c289  xor     esi, esi
0x18000c28b  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000c291  mov     rcx, [rdi+8]; this
0x18000c295  test    rcx, rcx
0x18000c298  jz      short loc_18000C2AD
0x18000c29a  xor     r9d, r9d; struct _MD_CHANGE_OBJECT_W *
0x18000c29d  mov     [rsp+38h+var_18], esi; int
0x18000c2a1  xor     r8d, r8d; unsigned int
0x18000c2a4  xor     edx, edx; unsigned int
0x18000c2a6  call    ?NotifySinks@CADMCOMW@@QEAAJKKQEAU_MD_CHANGE_OBJECT_W@@H@Z; CADMCOMW::NotifySinks(ulong,ulong,_MD_CHANGE_OBJECT_W * const,int)
0x18000c2ab  mov     esi, eax
0x18000c2ad  mov     rcx, rbx
0x18000c2b0  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000c2b6  mov     rcx, rbx
0x18000c2b9  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000c2bf  mov     rcx, rbx
0x18000c2c2  mov     qword ptr [rdi+8], 0
0x18000c2ca  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000c2d0  mov     rbx, [rsp+38h+arg_0]
0x18000c2d5  mov     eax, esi
0x18000c2d7  mov     rsi, [rsp+38h+arg_8]
0x18000c2dc  add     rsp, 30h
0x18000c2e0  pop     rdi
0x18000c2e1  retn
```
