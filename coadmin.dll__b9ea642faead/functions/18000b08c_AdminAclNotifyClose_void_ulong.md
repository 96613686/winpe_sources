# AdminAclNotifyClose(void *,ulong)

- ea: `0x18000b08c`
- end: `0x18000b1dc`
- name: `?AdminAclNotifyClose@@YAHPEAXK@Z`
- size: `336`
- prototype: `__int64 __fastcall(void *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180009920`
- `0x18000be20`

## callees

- `0x18000b08c`
- `0x18000bddc`
- `0x18000fb1e`
- `0x18000fb50`

## import_xrefs

- `IisRTL!?TryReadLock@CReaderWriterLock3@@QEAA_NXZ` at `0x18000b0cd`
- `IisRTL!?TryReadLock@CReaderWriterLock3@@QEAA_NXZ` at `0x18000b0cd`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b145`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b19d`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b145`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b19d`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b119`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b119`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b12f`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b12f`
- `IisRTL!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x18000b124`
- `IisRTL!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x18000b124`

## pseudocode

```c
__int64 __fastcall AdminAclNotifyClose(void *a1, int a2)
{
  __int64 i; // rdx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 j; // rdi
  __int64 v9; // r8
  __int64 k; // rbx
  CAdminAcl *v12[256]; // [rsp+20h] [rbp-838h] BYREF

  memset_0(v12, 0, sizeof(v12));
  if ( CReaderWriterLock3::TryReadLock((CReaderWriterLock3 *)&qword_1800168F8) )
  {
    for ( i = 0; (unsigned int)i < dword_1800160F4; i = (unsigned int)(i + 1) )
    {
      v5 = *(_QWORD *)&g_AclCache[2 * i + 2];
      if ( *(void **)(v5 + 552) == a1 && *(_DWORD *)(v5 + 528) == a2 )
        break;
    }
    if ( (_DWORD)i == dword_1800160F4 )
    {
      CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&qword_1800168F8);
      return 1;
    }
    CReaderWriterLock3::ConvertSharedToExclusive((CReaderWriterLock3 *)&qword_1800168F8);
  }
  else
  {
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&qword_1800168F8);
  }
  if ( (unsigned int)dword_1800160F4 <= 0x100 )
  {
    v6 = 0;
    v7 = 0;
    for ( j = 0; (unsigned int)v6 < dword_1800160F4; v6 = (unsigned int)(v6 + 1) )
    {
      v9 = *(_QWORD *)&g_AclCache[2 * v6 + 2];
      if ( *(void **)(v9 + 552) == a1 && *(_DWORD *)(v9 + 528) == a2 )
      {
        v12[j] = (CAdminAcl *)v9;
        j = (unsigned int)(j + 1);
      }
      else
      {
        if ( (_DWORD)v7 != (_DWORD)v6 )
          *(_QWORD *)&g_AclCache[2 * v7 + 2] = v9;
        v7 = (unsigned int)(v7 + 1);
      }
    }
    _InterlockedExchange(&dword_1800160F4, v7);
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&qword_1800168F8);
    for ( k = 0; (unsigned int)k < (unsigned int)j; k = (unsigned int)(k + 1) )
      CAdminAcl::Release(v12[k]);
  }
  else
  {
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&qword_1800168F8);
  }
  return 1;
}

```

## disassembly

```asm
0x18000b08c  push    rbx
0x18000b08e  push    rbp
0x18000b08f  push    rsi
0x18000b090  push    rdi
0x18000b091  push    r15
0x18000b093  sub     rsp, 830h
0x18000b09a  mov     rax, cs:__security_cookie
0x18000b0a1  xor     rax, rsp
0x18000b0a4  mov     [rsp+858h+var_38], rax
0x18000b0ac  mov     ebx, edx
0x18000b0ae  mov     rsi, rcx
0x18000b0b1  xor     edx, edx; Val
0x18000b0b3  lea     rcx, [rsp+858h+var_838]; void *
0x18000b0b8  mov     r8d, 800h; Size
0x18000b0be  call    memset_0
0x18000b0c3  lea     rbp, qword_1800168F8
0x18000b0ca  mov     rcx, rbp
0x18000b0cd  call    cs:__imp_?TryReadLock@CReaderWriterLock3@@QEAA_NXZ; CReaderWriterLock3::TryReadLock(void)
0x18000b0d3  lea     r15, ?g_AclCache@@3VCAdminAclCache@@A; CAdminAclCache g_AclCache
0x18000b0da  test    al, al
0x18000b0dc  jz      short loc_18000B12C
0x18000b0de  mov     eax, cs:dword_1800160F4
0x18000b0e4  xor     edx, edx
0x18000b0e6  test    eax, eax
0x18000b0e8  jz      short loc_18000B10C
0x18000b0ea  mov     rcx, [r15+rdx*8+8]
0x18000b0ef  cmp     [rcx+228h], rsi
0x18000b0f6  jnz     short loc_18000B100
0x18000b0f8  cmp     [rcx+210h], ebx
0x18000b0fe  jz      short loc_18000B10C
0x18000b100  mov     eax, cs:dword_1800160F4
0x18000b106  inc     edx
0x18000b108  cmp     edx, eax
0x18000b10a  jb      short loc_18000B0EA
0x18000b10c  mov     eax, cs:dword_1800160F4
0x18000b112  mov     rcx, rbp
0x18000b115  cmp     edx, eax
0x18000b117  jnz     short loc_18000B124
0x18000b119  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000b11f  jmp     loc_18000B1B9
0x18000b124  call    cs:__imp_?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ConvertSharedToExclusive(void)
0x18000b12a  jmp     short loc_18000B135
0x18000b12c  mov     rcx, rbp
0x18000b12f  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000b135  mov     eax, cs:dword_1800160F4
0x18000b13b  cmp     eax, 100h
0x18000b140  jbe     short loc_18000B14D
0x18000b142  mov     rcx, rbp
0x18000b145  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b14b  jmp     short loc_18000B1B9
0x18000b14d  mov     eax, cs:dword_1800160F4
0x18000b153  xor     edx, edx
0x18000b155  xor     ecx, ecx
0x18000b157  xor     edi, edi
0x18000b159  test    eax, eax
0x18000b15b  jz      short loc_18000B194
0x18000b15d  mov     r8, [r15+rdx*8+8]
0x18000b162  cmp     [r8+228h], rsi
0x18000b169  jnz     short loc_18000B17D
0x18000b16b  cmp     [r8+210h], ebx
0x18000b172  jnz     short loc_18000B17D
0x18000b174  mov     [rsp+rdi*8+858h+var_838], r8
0x18000b179  inc     edi
0x18000b17b  jmp     short loc_18000B188
0x18000b17d  cmp     ecx, edx
0x18000b17f  jz      short loc_18000B186
0x18000b181  mov     [r15+rcx*8+8], r8
0x18000b186  inc     ecx
0x18000b188  mov     eax, cs:dword_1800160F4
0x18000b18e  inc     edx
0x18000b190  cmp     edx, eax
0x18000b192  jb      short loc_18000B15D
0x18000b194  xchg    ecx, cs:dword_1800160F4
0x18000b19a  mov     rcx, rbp
0x18000b19d  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b1a3  xor     ebx, ebx
0x18000b1a5  test    edi, edi
0x18000b1a7  jz      short loc_18000B1B9
0x18000b1a9  mov     rcx, [rsp+rbx*8+858h+var_838]; this
0x18000b1ae  call    ?Release@CAdminAcl@@QEAAKXZ; CAdminAcl::Release(void)
0x18000b1b3  inc     ebx
0x18000b1b5  cmp     ebx, edi
0x18000b1b7  jb      short loc_18000B1A9
0x18000b1b9  mov     eax, 1
0x18000b1be  mov     rcx, [rsp+858h+var_38]
0x18000b1c6  xor     rcx, rsp; StackCookie
0x18000b1c9  call    __security_check_cookie
0x18000b1ce  add     rsp, 830h
0x18000b1d5  pop     r15
0x18000b1d7  pop     rdi
0x18000b1d8  pop     rsi
0x18000b1d9  pop     rbp
0x18000b1da  pop     rbx
0x18000b1db  retn
```
