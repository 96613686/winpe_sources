# CONFIG_ELEMENT::InitializeFromExtension(void)

- ea: `0x180031df8`
- end: `0x180031f9c`
- name: `?InitializeFromExtension@CONFIG_ELEMENT@@AEAAJXZ`
- size: `420`
- prototype: `__int64 __fastcall(CONFIG_ELEMENT *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180030ac0`
- `0x180031100`
- `0x1800357d0`
- `0x180035860`
- `0x180035d80`

## callees

- `0x18001bcb8`
- `0x18002dbd0`
- `0x180030044`
- `0x180030078`
- `0x180031df8`
- `0x180053c0c`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031e3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031eb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031e3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031eb2`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180031e61`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180031e61`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180031e87`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180031e87`

## pseudocode

```c
__int64 __fastcall CONFIG_ELEMENT::InitializeFromExtension(CONFIG_ELEMENT *this)
{
  bool v1; // zf
  int FieldMemory; // esi
  __int64 v4; // rbp
  int v5; // ebx
  const unsigned __int16 *Extension; // rax
  EXTENSION_TABLE *v7; // rcx
  struct IUnknown *v9; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  v1 = (*((_BYTE *)this + 36) & 8) == 0;
  v10 = 0;
  if ( v1 )
  {
    return 0;
  }
  else
  {
    FieldMemory = CONFIG_ELEMENT::AllocateFieldMemory(this, 2);
    if ( FieldMemory >= 0 )
    {
      v4 = *((_QWORD *)this + 15);
      if ( *(_DWORD *)(v4 + 8) )
      {
        v5 = *(_DWORD *)(v4 + 8);
        if ( v5 != GetCurrentThreadId() )
        {
          if ( v4 || (int)CONFIG_ELEMENT::AllocateFieldMemory(this, 2) >= 0 )
            CReaderWriterLock3::ReadLock(*((CReaderWriterLock3 **)this + 15));
          if ( *((_QWORD *)this + 15) || (int)CONFIG_ELEMENT::AllocateFieldMemory(this, 2) >= 0 )
            CReaderWriterLock3::ReadUnlock(*((CReaderWriterLock3 **)this + 15));
        }
      }
      else
      {
        CONFIG_ELEMENT::ElementWriteLock(this);
        if ( (*((_BYTE *)this + 36) & 8) != 0 && !*(_DWORD *)(*((_QWORD *)this + 15) + 8LL) )
        {
          *(_DWORD *)(*((_QWORD *)this + 15) + 8LL) = GetCurrentThreadId();
          if ( SCHEMA_ELEMENT::QueryExtension(*((SCHEMA_ELEMENT **)this + 10)) )
          {
            if ( (*((_BYTE *)this + 36) & 4) != 0 )
            {
              FieldMemory = -2147024846;
            }
            else
            {
              Extension = SCHEMA_ELEMENT::QueryExtension(*((SCHEMA_ELEMENT **)this + 10));
              v9 = 0;
              FieldMemory = EXTENSION_TABLE::GetExtension(v7, Extension, &v9);
              if ( FieldMemory >= 0 )
                FieldMemory = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v9->lpVtbl->QueryInterface)(
                                v9,
                                &IID_IAppHostElementExtension,
                                &v10);
              if ( v9 )
                ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->Release)(v9);
              if ( FieldMemory >= 0 )
                FieldMemory = (*(__int64 (__fastcall **)(__int64, CONFIG_ELEMENT *))(*(_QWORD *)v10 + 24LL))(v10, this);
            }
          }
          else
          {
            FieldMemory = -2147024883;
          }
        }
        *((_WORD *)this + 18) &= ~8u;
        *(_DWORD *)(*((_QWORD *)this + 15) + 8LL) = 0;
        CONFIG_ELEMENT::ElementWriteUnlock(this);
      }
    }
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return (unsigned int)FieldMemory;
}

```

## disassembly

```asm
0x180031df8  mov     [rsp+arg_10], rbx
0x180031dfd  push    rbp
0x180031dfe  push    rsi
0x180031dff  push    rdi
0x180031e00  sub     rsp, 20h
0x180031e04  test    byte ptr [rcx+24h], 8
0x180031e08  mov     rdi, rcx
0x180031e0b  mov     [rsp+38h+arg_8], 0
0x180031e14  jz      loc_180031F8B
0x180031e1a  mov     edx, 2
0x180031e1f  call    ?AllocateFieldMemory@CONFIG_ELEMENT@@QEAAJW4ALLOCATION_TYPE@@@Z; CONFIG_ELEMENT::AllocateFieldMemory(ALLOCATION_TYPE)
0x180031e24  mov     esi, eax
0x180031e26  test    eax, eax
0x180031e28  js      loc_180031F73
0x180031e2e  mov     rbp, [rdi+78h]
0x180031e32  cmp     dword ptr [rbp+8], 0
0x180031e36  jz      short loc_180031E92
0x180031e38  mov     ebx, [rbp+8]
0x180031e3b  call    cs:__imp_GetCurrentThreadId
0x180031e41  cmp     ebx, eax
0x180031e43  jz      loc_180031F73
0x180031e49  test    rbp, rbp
0x180031e4c  jnz     short loc_180031E5D
0x180031e4e  lea     edx, [rbp+2]
0x180031e51  mov     rcx, rdi
0x180031e54  call    ?AllocateFieldMemory@CONFIG_ELEMENT@@QEAAJW4ALLOCATION_TYPE@@@Z; CONFIG_ELEMENT::AllocateFieldMemory(ALLOCATION_TYPE)
0x180031e59  test    eax, eax
0x180031e5b  js      short loc_180031E67
0x180031e5d  mov     rcx, [rdi+78h]
0x180031e61  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180031e67  cmp     qword ptr [rdi+78h], 0
0x180031e6c  jnz     short loc_180031E83
0x180031e6e  mov     edx, 2
0x180031e73  mov     rcx, rdi
0x180031e76  call    ?AllocateFieldMemory@CONFIG_ELEMENT@@QEAAJW4ALLOCATION_TYPE@@@Z; CONFIG_ELEMENT::AllocateFieldMemory(ALLOCATION_TYPE)
0x180031e7b  test    eax, eax
0x180031e7d  js      loc_180031F73
0x180031e83  mov     rcx, [rdi+78h]
0x180031e87  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180031e8d  jmp     loc_180031F73
0x180031e92  mov     rcx, rdi; this
0x180031e95  call    ?ElementWriteLock@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::ElementWriteLock(void)
0x180031e9a  test    byte ptr [rdi+24h], 8
0x180031e9e  jz      loc_180031F57
0x180031ea4  mov     rax, [rdi+78h]
0x180031ea8  cmp     dword ptr [rax+8], 0
0x180031eac  jnz     loc_180031F57
0x180031eb2  call    cs:__imp_GetCurrentThreadId
0x180031eb8  mov     rcx, [rdi+78h]
0x180031ebc  mov     [rcx+8], eax
0x180031ebf  mov     rcx, [rdi+50h]; this
0x180031ec3  call    ?QueryExtension@SCHEMA_ELEMENT@@QEBAPEBGXZ; SCHEMA_ELEMENT::QueryExtension(void)
0x180031ec8  test    rax, rax
0x180031ecb  jnz     short loc_180031ED7
0x180031ecd  mov     esi, 8007000Dh
0x180031ed2  jmp     loc_180031F57
0x180031ed7  test    byte ptr [rdi+24h], 4
0x180031edb  jz      short loc_180031EE4
0x180031edd  mov     esi, 80070032h
0x180031ee2  jmp     short loc_180031F57
0x180031ee4  mov     rcx, [rdi+50h]; this
0x180031ee8  call    ?QueryExtension@SCHEMA_ELEMENT@@QEBAPEBGXZ; SCHEMA_ELEMENT::QueryExtension(void)
0x180031eed  mov     rdx, rax; unsigned __int16 *
0x180031ef0  mov     [rsp+38h+arg_0], 0
0x180031ef9  lea     r8, [rsp+38h+arg_0]; struct IUnknown **
0x180031efe  call    ?GetExtension@EXTENSION_TABLE@@AEAAJPEBGPEAPEAUIUnknown@@@Z; EXTENSION_TABLE::GetExtension(ushort const *,IUnknown * *)
0x180031f03  mov     esi, eax
0x180031f05  test    eax, eax
0x180031f07  js      short loc_180031F27
0x180031f09  mov     rcx, [rsp+38h+arg_0]
0x180031f0e  lea     r8, [rsp+38h+arg_8]
0x180031f13  lea     rdx, IID_IAppHostElementExtension
0x180031f1a  mov     rax, [rcx]
0x180031f1d  mov     rax, [rax]
0x180031f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f25  mov     esi, eax
0x180031f27  mov     rcx, [rsp+38h+arg_0]
0x180031f2c  test    rcx, rcx
0x180031f2f  jz      short loc_180031F3D
0x180031f31  mov     rax, [rcx]
0x180031f34  mov     rax, [rax+10h]
0x180031f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f3d  test    esi, esi
0x180031f3f  js      short loc_180031F57
0x180031f41  mov     rcx, [rsp+38h+arg_8]
0x180031f46  mov     rdx, rdi
0x180031f49  mov     rax, [rcx]
0x180031f4c  mov     rax, [rax+18h]
0x180031f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f55  mov     esi, eax
0x180031f57  mov     eax, 0FFF7h
0x180031f5c  mov     rcx, rdi; this
0x180031f5f  and     [rdi+24h], ax
0x180031f63  mov     rax, [rdi+78h]
0x180031f67  mov     dword ptr [rax+8], 0
0x180031f6e  call    ?ElementWriteUnlock@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::ElementWriteUnlock(void)
0x180031f73  mov     rcx, [rsp+38h+arg_8]
0x180031f78  test    rcx, rcx
0x180031f7b  jz      short loc_180031F8D
0x180031f7d  mov     rax, [rcx]
0x180031f80  mov     rax, [rax+10h]
0x180031f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f89  jmp     short loc_180031F8D
0x180031f8b  xor     esi, esi
0x180031f8d  mov     rbx, [rsp+38h+arg_10]
0x180031f92  mov     eax, esi
0x180031f94  add     rsp, 20h
0x180031f98  pop     rdi
0x180031f99  pop     rsi
0x180031f9a  pop     rbp
0x180031f9b  retn
```
