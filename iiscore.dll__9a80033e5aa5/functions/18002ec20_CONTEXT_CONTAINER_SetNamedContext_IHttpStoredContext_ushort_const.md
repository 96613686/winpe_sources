# CONTEXT_CONTAINER::SetNamedContext(IHttpStoredContext *,ushort const *)

- ea: `0x18002ec20`
- end: `0x18002ed43`
- name: `?SetNamedContext@CONTEXT_CONTAINER@@UEAAJPEAVIHttpStoredContext@@PEBG@Z`
- size: `291`
- prototype: `int(CONTEXT_CONTAINER *__hidden this, struct IHttpStoredContext *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180019558`
- `0x18002eaac`
- `0x18002ec20`
- `0x180034382`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002ec65`
- `msvcrt!_wcsicmp` at `0x18002ec65`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ec96`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ec96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ecc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ecc0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002ece2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002ece2`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002ec42`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002ec42`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ec59`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ec59`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002ed21`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002ed21`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002ecf2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002ecf2`

## pseudocode

```c
__int64 __fastcall CONTEXT_CONTAINER::SetNamedContext(
        CONTEXT_CONTAINER *this,
        struct IHttpStoredContext *a2,
        const unsigned __int16 *a3)
{
  STRU *v3; // rdi
  __int64 i; // rsi
  unsigned int v8; // eax
  const wchar_t *Str; // rax
  __int64 v10; // rdx
  int v11; // esi
  int v12; // ecx
  int v13; // ebp
  HLOCAL v14; // rax
  HLOCAL v15; // rsi
  const void **v16; // rdx
  STRU *v17; // rax

  v3 = 0;
  if ( *((_BYTE *)this + 36) )
    CReaderWriterLock3::WriteLock((CONTEXT_CONTAINER *)((char *)this + 8));
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v8 = *((_DWORD *)this + 7);
    if ( (unsigned int)i >= v8 )
      break;
    Str = STRU::QueryStr(*(STRU **)(*((_QWORD *)this + 7) + 8 * i));
    if ( !_wcsicmp(Str, a3) )
    {
      v11 = -2147024811;
      goto LABEL_18;
    }
  }
  v12 = 8 * v8;
  if ( 8 * v8 + 8 > *((_DWORD *)this + 8) )
  {
    v13 = v12 + 40;
    v14 = LocalAlloc(0x40u, (unsigned int)(v12 + 40));
    v15 = v14;
    if ( !v14 )
    {
LABEL_17:
      v11 = -2147024882;
      goto LABEL_18;
    }
    v16 = (const void **)*((_QWORD *)this + 7);
    if ( v16 )
    {
      memcpy_0(v14, *v16, *((unsigned int *)this + 8));
      LocalFree(*((HLOCAL *)this + 7));
    }
    *((_QWORD *)this + 7) = v15;
    *((_DWORD *)this + 8) = v13;
  }
  v17 = (STRU *)operator new(0x40u);
  v3 = v17;
  if ( !v17 )
  {
    v3 = 0;
    goto LABEL_17;
  }
  STRU::STRU(v17);
  *((_QWORD *)v3 + 7) = a2;
  v11 = STRU::Copy(v3, a3);
  if ( v11 >= 0 )
  {
    v10 = *((unsigned int *)this + 7);
    *(_QWORD *)(*((_QWORD *)this + 7) + 8 * v10) = v3;
    v3 = 0;
    ++*((_DWORD *)this + 7);
  }
LABEL_18:
  if ( *((_BYTE *)this + 36) )
    CReaderWriterLock3::WriteUnlock((CONTEXT_CONTAINER *)((char *)this + 8));
  if ( v3 )
    NAMED_CONTEXT_RECORD::`scalar deleting destructor'(v3, v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002ec20  push    rbx
0x18002ec22  push    rbp
0x18002ec23  push    rsi
0x18002ec24  push    rdi
0x18002ec25  push    r14
0x18002ec27  push    r15
0x18002ec29  sub     rsp, 28h
0x18002ec2d  xor     edi, edi
0x18002ec2f  mov     r14, r8
0x18002ec32  mov     r15, rdx
0x18002ec35  mov     rbx, rcx
0x18002ec38  cmp     [rcx+24h], dil
0x18002ec3c  jz      short loc_18002EC48
0x18002ec3e  add     rcx, 8
0x18002ec42  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18002ec48  xor     esi, esi
0x18002ec4a  mov     eax, [rbx+1Ch]
0x18002ec4d  cmp     esi, eax
0x18002ec4f  jnb     short loc_18002EC7D
0x18002ec51  mov     rcx, [rbx+38h]
0x18002ec55  mov     rcx, [rcx+rsi*8]
0x18002ec59  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002ec5f  mov     rcx, rax; String1
0x18002ec62  mov     rdx, r14; String2
0x18002ec65  call    cs:__imp__wcsicmp
0x18002ec6b  test    eax, eax
0x18002ec6d  jz      short loc_18002EC73
0x18002ec6f  inc     esi
0x18002ec71  jmp     short loc_18002EC4A
0x18002ec73  mov     esi, 80070055h
0x18002ec78  jmp     loc_18002ED17
0x18002ec7d  lea     ecx, ds:0[rax*8]
0x18002ec84  lea     eax, [rcx+8]
0x18002ec87  cmp     eax, [rbx+20h]
0x18002ec8a  jbe     short loc_18002ECCD
0x18002ec8c  lea     ebp, [rcx+28h]
0x18002ec8f  mov     ecx, 40h ; '@'; uFlags
0x18002ec94  mov     edx, ebp; uBytes
0x18002ec96  call    cs:__imp_LocalAlloc
0x18002ec9c  mov     rsi, rax
0x18002ec9f  test    rax, rax
0x18002eca2  jz      short loc_18002ED12
0x18002eca4  mov     rdx, [rbx+38h]
0x18002eca8  test    rdx, rdx
0x18002ecab  jz      short loc_18002ECC6
0x18002ecad  mov     r8d, [rbx+20h]; Size
0x18002ecb1  mov     rcx, rax; void *
0x18002ecb4  mov     rdx, [rdx]; Src
0x18002ecb7  call    memcpy_0
0x18002ecbc  mov     rcx, [rbx+38h]; hMem
0x18002ecc0  call    cs:__imp_LocalFree
0x18002ecc6  mov     [rbx+38h], rsi
0x18002ecca  mov     [rbx+20h], ebp
0x18002eccd  mov     ecx, 40h ; '@'; Size
0x18002ecd2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ecd7  mov     rdi, rax
0x18002ecda  test    rax, rax
0x18002ecdd  jz      short loc_18002ED10
0x18002ecdf  mov     rcx, rax
0x18002ece2  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002ece8  mov     rdx, r14
0x18002eceb  mov     [rdi+38h], r15
0x18002ecef  mov     rcx, rdi
0x18002ecf2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002ecf8  mov     esi, eax
0x18002ecfa  test    eax, eax
0x18002ecfc  js      short loc_18002ED17
0x18002ecfe  mov     edx, [rbx+1Ch]
0x18002ed01  mov     rcx, [rbx+38h]
0x18002ed05  mov     [rcx+rdx*8], rdi
0x18002ed09  xor     edi, edi
0x18002ed0b  inc     dword ptr [rbx+1Ch]
0x18002ed0e  jmp     short loc_18002ED17
0x18002ed10  xor     edi, edi
0x18002ed12  mov     esi, 8007000Eh
0x18002ed17  cmp     byte ptr [rbx+24h], 0
0x18002ed1b  jz      short loc_18002ED27
0x18002ed1d  lea     rcx, [rbx+8]
0x18002ed21  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18002ed27  test    rdi, rdi
0x18002ed2a  jz      short loc_18002ED34
0x18002ed2c  mov     rcx, rdi; this
0x18002ed2f  call    ??_GNAMED_CONTEXT_RECORD@@QEAAPEAXI@Z; NAMED_CONTEXT_RECORD::`scalar deleting destructor'(uint)
0x18002ed34  mov     eax, esi
0x18002ed36  add     rsp, 28h
0x18002ed3a  pop     r15
0x18002ed3c  pop     r14
0x18002ed3e  pop     rdi
0x18002ed3f  pop     rsi
0x18002ed40  pop     rbp
0x18002ed41  pop     rbx
0x18002ed42  retn
```
