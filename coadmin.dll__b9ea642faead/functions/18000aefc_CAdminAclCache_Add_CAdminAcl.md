# CAdminAclCache::Add(CAdminAcl *)

- ea: `0x18000aefc`
- end: `0x18000b083`
- name: `?Add@CAdminAclCache@@QEAAJPEAVCAdminAcl@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(CAdminAclCache *__hidden this, struct CAdminAcl *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000b988`

## callees

- `0x18000aefc`
- `0x18000bddc`
- `0x18000be64`
- `0x18000c0d0`
- `0x18000fb12`

## import_xrefs

- `IisRTL!?TryWriteLock@CReaderWriterLock3@@QEAA_NXZ` at `0x18000af69`
- `IisRTL!?TryWriteLock@CReaderWriterLock3@@QEAA_NXZ` at `0x18000af69`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b045`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b045`

## pseudocode

```c
__int64 __fastcall CAdminAclCache::Add(CAdminAclCache *this, struct CAdminAcl *a2)
{
  CAdminAcl *v2; // rcx
  unsigned int v4; // ebx
  CAdminAcl *v5; // rsi
  void *v6; // rbp
  unsigned int v7; // r14d
  const unsigned __int16 *v8; // rbx
  CAdminAclCache *v9; // rcx
  CAdminAclCache *v10; // rcx
  int v11; // eax
  unsigned int v13; // [rsp+50h] [rbp+8h] BYREF
  int v14; // [rsp+54h] [rbp+Ch]
  struct CAdminAcl *v15; // [rsp+58h] [rbp+10h] BYREF

  v14 = HIDWORD(this);
  v2 = 0;
  v13 = 0;
  v15 = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v5 = 0;
  if ( g_AclCache[0] <= 0 )
  {
    v4 = 1;
    goto LABEL_20;
  }
  v6 = (void *)*((_QWORD *)a2 + 69);
  v7 = *((_DWORD *)a2 + 132);
  v8 = &byte_1800127D8;
  if ( a2 != (struct CAdminAcl *)-4LL )
    v8 = (const unsigned __int16 *)((char *)a2 + 4);
  if ( !CReaderWriterLock3::TryWriteLock((CReaderWriterLock3 *)&qword_1800168F8) )
    return 1;
  v4 = CAdminAclCache::_Find(v9, v6, v7, v8, &v15, &v13);
  if ( v4 )
  {
    if ( dword_1800160F4 == 256 )
    {
      _InterlockedDecrement(&dword_1800160F4);
      v5 = *(CAdminAcl **)&g_AclCache[2 * dword_1800160F4 + 2];
      *(_QWORD *)&g_AclCache[2 * dword_1800160F4 + 2] = 0;
    }
    if ( dword_1800160F4 )
    {
      if ( (unsigned int)dword_1800160F4 >= 0xFF )
      {
        v11 = -2147024809;
LABEL_17:
        v4 = v11;
        goto LABEL_18;
      }
      memmove_0(qword_180016100, &qword_1800160F8, 8LL * (unsigned int)dword_1800160F4);
    }
    v11 = 0;
    qword_1800160F8 = (__int64)a2;
    _InterlockedAdd((volatile signed __int32 *)a2 + 142, 1u);
    _InterlockedAdd(&dword_1800160F4, 1u);
    goto LABEL_17;
  }
  CAdminAclCache::_MoveFirst(v10, v13);
LABEL_18:
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&qword_1800168F8);
  v2 = v15;
LABEL_20:
  if ( v2 )
    CAdminAcl::Release(v2);
  if ( v5 )
    CAdminAcl::Release(v5);
  return v4;
}

```

## disassembly

```asm
0x18000aefc  mov     rax, rsp
0x18000aeff  mov     [rax+18h], rbx
0x18000af03  mov     [rax+20h], rbp
0x18000af07  mov     [rax+8], rcx
0x18000af0b  push    rsi
0x18000af0c  push    rdi
0x18000af0d  push    r14
0x18000af0f  sub     rsp, 30h
0x18000af13  xor     ecx, ecx; this
0x18000af15  mov     dword ptr [rax+8], 0
0x18000af1c  mov     [rax+10h], rcx
0x18000af20  mov     rdi, rdx
0x18000af23  test    rdx, rdx
0x18000af26  jnz     short loc_18000AF32
0x18000af28  mov     ebx, 80070057h
0x18000af2d  jmp     loc_18000B06E
0x18000af32  mov     eax, cs:?g_AclCache@@3VCAdminAclCache@@A; CAdminAclCache g_AclCache
0x18000af38  xor     esi, esi
0x18000af3a  test    eax, eax
0x18000af3c  jle     loc_18000B052
0x18000af42  mov     rbp, [rdx+228h]
0x18000af49  lea     rax, [rdx+4]
0x18000af4d  mov     r14d, [rdx+210h]
0x18000af54  lea     rbx, byte_1800127D8
0x18000af5b  test    rax, rax
0x18000af5e  lea     rcx, qword_1800168F8
0x18000af65  cmovnz  rbx, rax
0x18000af69  call    cs:__imp_?TryWriteLock@CReaderWriterLock3@@QEAA_NXZ; CReaderWriterLock3::TryWriteLock(void)
0x18000af6f  test    al, al
0x18000af71  jnz     short loc_18000AF7B
0x18000af73  lea     ebx, [rsi+1]
0x18000af76  jmp     loc_18000B06E
0x18000af7b  lea     rax, [rsp+48h+arg_0]
0x18000af80  mov     r9, rbx; unsigned __int16 *
0x18000af83  mov     [rsp+48h+var_20], rax; unsigned int *
0x18000af88  mov     r8d, r14d; unsigned int
0x18000af8b  lea     rax, [rsp+48h+arg_8]
0x18000af90  mov     rdx, rbp; void *
0x18000af93  mov     [rsp+48h+var_28], rax; struct CAdminAcl **
0x18000af98  call    ?_Find@CAdminAclCache@@AEAAJPEAXKPEBGPEAPEAVCAdminAcl@@PEAK@Z; CAdminAclCache::_Find(void *,ulong,ushort const *,CAdminAcl * *,ulong *)
0x18000af9d  mov     ebx, eax
0x18000af9f  test    eax, eax
0x18000afa1  jnz     short loc_18000AFB1
0x18000afa3  mov     edx, [rsp+48h+arg_0]; unsigned int
0x18000afa7  call    ?_MoveFirst@CAdminAclCache@@AEAAJK@Z; CAdminAclCache::_MoveFirst(ulong)
0x18000afac  jmp     loc_18000B03E
0x18000afb1  mov     eax, cs:dword_1800160F4
0x18000afb7  cmp     eax, 100h
0x18000afbc  jnz     short loc_18000AFE6
0x18000afbe  lock dec cs:dword_1800160F4
0x18000afc5  lea     rdx, ?g_AclCache@@3VCAdminAclCache@@A; CAdminAclCache g_AclCache
0x18000afcc  mov     eax, cs:dword_1800160F4
0x18000afd2  mov     rsi, [rdx+rax*8+8]
0x18000afd7  mov     eax, cs:dword_1800160F4
0x18000afdd  mov     qword ptr [rdx+rax*8+8], 0
0x18000afe6  mov     eax, cs:dword_1800160F4
0x18000afec  test    eax, eax
0x18000afee  jz      short loc_18000B022
0x18000aff0  mov     eax, cs:dword_1800160F4
0x18000aff6  cmp     eax, 0FFh
0x18000affb  jb      short loc_18000B004
0x18000affd  mov     eax, 80070057h
0x18000b002  jmp     short loc_18000B03C
0x18000b004  mov     r8d, cs:dword_1800160F4
0x18000b00b  lea     rdx, qword_1800160F8; Src
0x18000b012  shl     r8, 3; Size
0x18000b016  lea     rcx, qword_180016100; void *
0x18000b01d  call    memmove_0
0x18000b022  xor     eax, eax
0x18000b024  mov     cs:qword_1800160F8, rdi
0x18000b02b  lea     ebx, [rax+1]
0x18000b02e  lock add [rdi+238h], ebx
0x18000b035  lock add cs:dword_1800160F4, ebx
0x18000b03c  mov     ebx, eax
0x18000b03e  lea     rcx, qword_1800168F8
0x18000b045  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b04b  mov     rcx, [rsp+48h+arg_8]
0x18000b050  jmp     short loc_18000B057
0x18000b052  mov     ebx, 1
0x18000b057  test    rcx, rcx
0x18000b05a  jz      short loc_18000B061
0x18000b05c  call    ?Release@CAdminAcl@@QEAAKXZ; CAdminAcl::Release(void)
0x18000b061  test    rsi, rsi
0x18000b064  jz      short loc_18000B06E
0x18000b066  mov     rcx, rsi; this
0x18000b069  call    ?Release@CAdminAcl@@QEAAKXZ; CAdminAcl::Release(void)
0x18000b06e  mov     rbp, [rsp+48h+arg_18]
0x18000b073  mov     eax, ebx
0x18000b075  mov     rbx, [rsp+48h+arg_10]
0x18000b07a  add     rsp, 30h
0x18000b07e  pop     r14
0x18000b080  pop     rdi
0x18000b081  pop     rsi
0x18000b082  retn
```
