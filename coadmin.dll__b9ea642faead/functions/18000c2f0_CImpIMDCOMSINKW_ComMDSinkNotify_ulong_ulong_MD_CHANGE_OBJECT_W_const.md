# CImpIMDCOMSINKW::ComMDSinkNotify(ulong,ulong,_MD_CHANGE_OBJECT_W * const)

- ea: `0x18000c2f0`
- end: `0x18000c34f`
- name: `?ComMDSinkNotify@CImpIMDCOMSINKW@@UEAAJKKQEAU_MD_CHANGE_OBJECT_W@@@Z`
- size: `95`
- prototype: `int(CImpIMDCOMSINKW *__hidden this, unsigned int, unsigned int, struct _MD_CHANGE_OBJECT_W *const)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007a50`
- `0x18000c2f0`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c33a`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c33a`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c30f`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c30f`

## pseudocode

```c
__int64 __fastcall CImpIMDCOMSINKW::ComMDSinkNotify(
        CImpIMDCOMSINKW *this,
        int a2,
        unsigned int a3,
        struct _MD_CHANGE_OBJECT_W *const a4)
{
  unsigned int v8; // edi
  CADMCOMW *v9; // rcx

  v8 = 0;
  CReaderWriterLock3::ReadLock((CImpIMDCOMSINKW *)((char *)this + 20));
  v9 = (CADMCOMW *)*((_QWORD *)this + 1);
  if ( v9 )
    v8 = CADMCOMW::NotifySinks(v9, a2, a3, a4, 1);
  CReaderWriterLock3::ReadUnlock((CImpIMDCOMSINKW *)((char *)this + 20));
  return v8;
}

```

## disassembly

```asm
0x18000c2f0  push    rbx
0x18000c2f2  push    rbp
0x18000c2f3  push    rsi
0x18000c2f4  push    rdi
0x18000c2f5  push    r14
0x18000c2f7  push    r15
0x18000c2f9  sub     rsp, 38h
0x18000c2fd  mov     rbx, rcx
0x18000c300  mov     rbp, r9
0x18000c303  add     rcx, 14h
0x18000c307  mov     r14d, r8d
0x18000c30a  mov     r15d, edx
0x18000c30d  xor     edi, edi
0x18000c30f  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000c315  mov     rcx, [rbx+8]; this
0x18000c319  test    rcx, rcx
0x18000c31c  jz      short loc_18000C336
0x18000c31e  mov     r9, rbp; struct _MD_CHANGE_OBJECT_W *
0x18000c321  mov     [rsp+68h+var_48], 1; int
0x18000c329  mov     r8d, r14d; unsigned int
0x18000c32c  mov     edx, r15d; unsigned int
0x18000c32f  call    ?NotifySinks@CADMCOMW@@QEAAJKKQEAU_MD_CHANGE_OBJECT_W@@H@Z; CADMCOMW::NotifySinks(ulong,ulong,_MD_CHANGE_OBJECT_W * const,int)
0x18000c334  mov     edi, eax
0x18000c336  lea     rcx, [rbx+14h]
0x18000c33a  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000c340  mov     eax, edi
0x18000c342  add     rsp, 38h
0x18000c346  pop     r15
0x18000c348  pop     r14
0x18000c34a  pop     rdi
0x18000c34b  pop     rsi
0x18000c34c  pop     rbp
0x18000c34d  pop     rbx
0x18000c34e  retn
```
