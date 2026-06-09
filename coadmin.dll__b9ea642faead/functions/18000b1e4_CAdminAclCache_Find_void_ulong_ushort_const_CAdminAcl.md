# CAdminAclCache::Find(void *,ulong,ushort const *,CAdminAcl * *)

- ea: `0x18000b1e4`
- end: `0x18000b2cb`
- name: `?Find@CAdminAclCache@@QEAAJPEAXKPEBGPEAPEAVCAdminAcl@@@Z`
- size: `231`
- prototype: `int(CAdminAclCache *__hidden this, void *, unsigned int, const unsigned __int16 *, struct CAdminAcl **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000b988`

## callees

- `0x18000b1e4`
- `0x18000be64`
- `0x18000c0d0`

## import_xrefs

- `IisRTL!?TryReadLock@CReaderWriterLock3@@QEAA_NXZ` at `0x18000b249`
- `IisRTL!?TryReadLock@CReaderWriterLock3@@QEAA_NXZ` at `0x18000b249`
- `IisRTL!?TryConvertSharedToExclusive@CReaderWriterLock3@@QEAA_NXZ` at `0x18000b282`
- `IisRTL!?TryConvertSharedToExclusive@CReaderWriterLock3@@QEAA_NXZ` at `0x18000b282`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b29c`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b29c`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b2ab`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b2ab`

## pseudocode

```c
__int64 __fastcall CAdminAclCache::Find(
        CAdminAclCache *this,
        void *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        struct CAdminAcl **a5)
{
  struct CAdminAcl **v5; // rdi
  unsigned int v8; // ebx
  int v9; // eax
  const unsigned __int16 *v10; // rbx
  CAdminAclCache *v11; // rcx
  CAdminAclCache *v12; // rcx
  struct CAdminAcl *v14; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v15; // [rsp+70h] [rbp+8h] BYREF
  int v16; // [rsp+74h] [rbp+Ch]

  v16 = HIDWORD(this);
  v5 = a5;
  v14 = 0;
  v15 = 0;
  if ( a5 )
  {
    v9 = g_AclCache[0];
    *a5 = 0;
    if ( v9 <= 0 )
      return 1;
    v10 = &byte_1800127D8;
    if ( a4 )
      v10 = a4;
    if ( CReaderWriterLock3::TryReadLock((CReaderWriterLock3 *)&qword_1800168F8) )
    {
      v8 = CAdminAclCache::_Find(v11, a2, a3, v10, &v14, &v15);
      if ( v8 || !CReaderWriterLock3::TryConvertSharedToExclusive((CReaderWriterLock3 *)&qword_1800168F8) )
      {
        CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&qword_1800168F8);
      }
      else
      {
        CAdminAclCache::_MoveFirst(v12, v15);
        CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&qword_1800168F8);
      }
      *v5 = v14;
    }
    else
    {
      return 1;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v8;
}

```

## disassembly

```asm
0x18000b1e4  mov     qword ptr [rsp+arg_0], rcx
0x18000b1e9  push    rbx
0x18000b1ea  push    rbp
0x18000b1eb  push    rsi
0x18000b1ec  push    rdi
0x18000b1ed  sub     rsp, 48h
0x18000b1f1  mov     rdi, [rsp+68h+arg_20]
0x18000b1f9  mov     esi, r8d
0x18000b1fc  mov     [rsp+68h+var_38], 0
0x18000b205  mov     rbp, rdx
0x18000b208  mov     [rsp+68h+arg_0], 0
0x18000b210  test    rdi, rdi
0x18000b213  jnz     short loc_18000B21F
0x18000b215  mov     ebx, 80070057h
0x18000b21a  jmp     loc_18000B2C0
0x18000b21f  mov     eax, cs:?g_AclCache@@3VCAdminAclCache@@A; CAdminAclCache g_AclCache
0x18000b225  mov     qword ptr [rdi], 0
0x18000b22c  test    eax, eax
0x18000b22e  jle     loc_18000B2BB
0x18000b234  test    r9, r9
0x18000b237  lea     rbx, byte_1800127D8
0x18000b23e  lea     rcx, qword_1800168F8
0x18000b245  cmovnz  rbx, r9
0x18000b249  call    cs:__imp_?TryReadLock@CReaderWriterLock3@@QEAA_NXZ; CReaderWriterLock3::TryReadLock(void)
0x18000b24f  test    al, al
0x18000b251  jz      short loc_18000B2BB
0x18000b253  lea     rax, [rsp+68h+arg_0]
0x18000b258  mov     r9, rbx; unsigned __int16 *
0x18000b25b  mov     [rsp+68h+var_40], rax; unsigned int *
0x18000b260  mov     r8d, esi; unsigned int
0x18000b263  lea     rax, [rsp+68h+var_38]
0x18000b268  mov     rdx, rbp; void *
0x18000b26b  mov     [rsp+68h+var_48], rax; struct CAdminAcl **
0x18000b270  call    ?_Find@CAdminAclCache@@AEAAJPEAXKPEBGPEAPEAVCAdminAcl@@PEAK@Z; CAdminAclCache::_Find(void *,ulong,ushort const *,CAdminAcl * *,ulong *)
0x18000b275  mov     ebx, eax
0x18000b277  test    eax, eax
0x18000b279  jnz     short loc_18000B2A4
0x18000b27b  lea     rcx, qword_1800168F8
0x18000b282  call    cs:__imp_?TryConvertSharedToExclusive@CReaderWriterLock3@@QEAA_NXZ; CReaderWriterLock3::TryConvertSharedToExclusive(void)
0x18000b288  test    al, al
0x18000b28a  jz      short loc_18000B2A4
0x18000b28c  mov     edx, [rsp+68h+arg_0]; unsigned int
0x18000b290  call    ?_MoveFirst@CAdminAclCache@@AEAAJK@Z; CAdminAclCache::_MoveFirst(ulong)
0x18000b295  lea     rcx, qword_1800168F8
0x18000b29c  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b2a2  jmp     short loc_18000B2B1
0x18000b2a4  lea     rcx, qword_1800168F8
0x18000b2ab  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000b2b1  mov     rax, [rsp+68h+var_38]
0x18000b2b6  mov     [rdi], rax
0x18000b2b9  jmp     short loc_18000B2C0
0x18000b2bb  mov     ebx, 1
0x18000b2c0  mov     eax, ebx
0x18000b2c2  add     rsp, 48h
0x18000b2c6  pop     rdi
0x18000b2c7  pop     rsi
0x18000b2c8  pop     rbp
0x18000b2c9  pop     rbx
0x18000b2ca  retn
```
