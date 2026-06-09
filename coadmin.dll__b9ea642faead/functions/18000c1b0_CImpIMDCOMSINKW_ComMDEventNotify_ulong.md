# CImpIMDCOMSINKW::ComMDEventNotify(ulong)

- ea: `0x18000c1b0`
- end: `0x18000c263`
- name: `?ComMDEventNotify@CImpIMDCOMSINKW@@UEAAJK@Z`
- size: `179`
- prototype: `__int64 __fastcall(CImpIMDCOMSINKW *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007a50`
- `0x18000c1b0`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c20d`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c20d`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c252`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c252`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c1e3`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c1e3`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c1ca`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c1ca`

## pseudocode

```c
__int64 __fastcall CImpIMDCOMSINKW::ComMDEventNotify(CImpIMDCOMSINKW *this, int a2)
{
  unsigned int v2; // edi
  __int64 v4; // rbx
  __int64 i; // rdx
  __int64 *j; // rax
  CADMCOMW *v7; // rcx
  _MD_CHANGE_OBJECT_W v9; // [rsp+30h] [rbp-48h] BYREF

  v2 = 0;
  if ( !a2 )
  {
    CReaderWriterLock3::ReadLock((CImpIMDCOMSINKW *)((char *)this + 20));
    v4 = *((_QWORD *)this + 1);
    if ( v4 )
    {
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v4 + 800));
      for ( i = 0; i != 5; ++i )
      {
        for ( j = *(__int64 **)(v4 + 8 * i + 48); j; j = (__int64 *)*j )
          *((_DWORD *)j + 2) = -1;
      }
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v4 + 800));
      v7 = (CADMCOMW *)*((_QWORD *)this + 1);
      v9.pszMDPath = L"/";
      *(_QWORD *)&v9.dwMDChangeType = 32;
      v9.pdwMDDataIDs = 0;
      v2 = CADMCOMW::NotifySinks(v7, 0, 1u, &v9, 1);
    }
    CReaderWriterLock3::ReadUnlock((CImpIMDCOMSINKW *)((char *)this + 20));
  }
  return v2;
}

```

## disassembly

```asm
0x18000c1b0  push    rbx
0x18000c1b2  push    rbp
0x18000c1b3  push    rsi
0x18000c1b4  push    rdi
0x18000c1b5  sub     rsp, 58h
0x18000c1b9  xor     edi, edi
0x18000c1bb  mov     rsi, rcx
0x18000c1be  test    edx, edx
0x18000c1c0  jnz     loc_18000C258
0x18000c1c6  add     rcx, 14h
0x18000c1ca  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000c1d0  mov     rbx, [rsi+8]
0x18000c1d4  test    rbx, rbx
0x18000c1d7  jz      short loc_18000C24E
0x18000c1d9  lea     rdi, [rbx+320h]
0x18000c1e0  mov     rcx, rdi
0x18000c1e3  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000c1e9  xor     edx, edx
0x18000c1eb  mov     rax, [rbx+rdx*8+30h]
0x18000c1f0  jmp     short loc_18000C1FC
0x18000c1f2  mov     dword ptr [rax+8], 0FFFFFFFFh
0x18000c1f9  mov     rax, [rax]
0x18000c1fc  test    rax, rax
0x18000c1ff  jnz     short loc_18000C1F2
0x18000c201  inc     rdx
0x18000c204  cmp     rdx, 5
0x18000c208  jnz     short loc_18000C1EB
0x18000c20a  mov     rcx, rdi
0x18000c20d  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000c213  mov     rcx, [rsi+8]; this
0x18000c217  lea     rax, asc_180011C70; "/"
0x18000c21e  mov     r8d, 1; unsigned int
0x18000c224  mov     [rsp+78h+var_48.pszMDPath], rax
0x18000c229  lea     r9, [rsp+78h+var_48]; struct _MD_CHANGE_OBJECT_W *
0x18000c22e  mov     [rsp+78h+var_58], r8d; int
0x18000c233  xor     edx, edx; unsigned int
0x18000c235  mov     qword ptr [rsp+78h+var_48.dwMDChangeType], 20h ; ' '
0x18000c23e  mov     [rsp+78h+var_48.pdwMDDataIDs], 0
0x18000c247  call    ?NotifySinks@CADMCOMW@@QEAAJKKQEAU_MD_CHANGE_OBJECT_W@@H@Z; CADMCOMW::NotifySinks(ulong,ulong,_MD_CHANGE_OBJECT_W * const,int)
0x18000c24c  mov     edi, eax
0x18000c24e  lea     rcx, [rsi+14h]
0x18000c252  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000c258  mov     eax, edi
0x18000c25a  add     rsp, 58h
0x18000c25e  pop     rdi
0x18000c25f  pop     rsi
0x18000c260  pop     rbp
0x18000c261  pop     rbx
0x18000c262  retn
```
