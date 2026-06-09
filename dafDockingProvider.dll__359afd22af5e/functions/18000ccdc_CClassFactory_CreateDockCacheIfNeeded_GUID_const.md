# CClassFactory::CreateDockCacheIfNeeded(_GUID const &)

- ea: `0x18000ccdc`
- end: `0x18000ce10`
- name: `?CreateDockCacheIfNeeded@CClassFactory@@AEAAJAEBU_GUID@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000ce20`

## callees

- `0x1800014d0`
- `0x180001ef4`
- `0x18000ccdc`
- `0x1800110a4`
- `0x18001134c`
- `0x180016a30`
- `0x180016e2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cd25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cd25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdf1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdf1`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateDockCacheIfNeeded(CClassFactory *this, const struct _GUID *a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // r14
  DockCache *v4; // rax
  DockCache *v5; // rsi
  volatile signed __int32 *v6; // rbp
  unsigned int v7; // edi
  __int64 v8; // rsi
  volatile signed __int32 *v9; // rbx
  DockingProviders *v10; // rcx

  if ( *(_OWORD *)&GUID_aac08705_d1db_4f7d_9bde_7bb253ed0bef == *(_OWORD *)a2 || *((_QWORD *)this + 9) )
    return 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( *((_QWORD *)this + 9) )
  {
    v7 = 0;
  }
  else
  {
    v4 = (DockCache *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v4 )
      v5 = DockCache::DockCache(v4);
    else
      v5 = 0;
    v6 = (volatile signed __int32 *)*((_QWORD *)this + 9);
    v7 = 1;
    if ( v6 != (volatile signed __int32 *)v5 )
    {
      if ( v6 && _InterlockedExchangeAdd(v6 + 24, 0xFFFFFFFF) == 1 )
      {
        DockCache::~DockCache((DockCache *)v6);
        operator delete((void *)v6);
      }
      *((_QWORD *)this + 9) = v5;
      if ( v5 )
        _InterlockedAdd((volatile signed __int32 *)v5 + 24, 1u);
    }
    v8 = *((_QWORD *)this + 9);
    if ( v8 )
    {
      v9 = (volatile signed __int32 *)*((_QWORD *)this + 8);
      if ( v9 )
      {
        v10 = *(DockingProviders **)(v8 + 112);
        if ( v10 != (DockingProviders *)v9 )
        {
          if ( v10 )
            DockingProviders::Release(v10);
          *(_QWORD *)(v8 + 112) = v9;
          _InterlockedAdd(v9 + 2, 1u);
        }
        v7 = DockingProviders::RegisterConnectionListener(
               *(DockingProviders **)(v8 + 112),
               (void *)v8,
               (void (__high *)(unsigned __int64, void *, enum _ConnectionKind, unsigned int, struct _DOCK_PROFILE *))&ConnectionListenerCallback,
               (unsigned __int64 *)(v8 + 120));
      }
    }
    else
    {
      v7 = -2147024882;
    }
  }
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x18000ccdc  mov     [rsp+arg_0], rbx
0x18000cce1  mov     [rsp+arg_8], rbp
0x18000cce6  push    rsi
0x18000cce7  push    rdi
0x18000cce8  push    r14
0x18000ccea  sub     rsp, 20h
0x18000ccee  mov     rbx, rcx
0x18000ccf1  mov     rax, qword ptr cs:_GUID_aac08705_d1db_4f7d_9bde_7bb253ed0bef.Data1
0x18000ccf8  cmp     rax, [rdx]
0x18000ccfb  jnz     short loc_18000CD0E
0x18000ccfd  mov     rax, qword ptr cs:_GUID_aac08705_d1db_4f7d_9bde_7bb253ed0bef.Data4
0x18000cd04  cmp     rax, [rdx+8]
0x18000cd08  jz      loc_18000CDFB
0x18000cd0e  cmp     qword ptr [rcx+48h], 0
0x18000cd13  jnz     loc_18000CDFB
0x18000cd19  lea     r14, [rcx+18h]
0x18000cd1d  mov     [rsp+38h+arg_18], r14
0x18000cd22  mov     rcx, r14; lpCriticalSection
0x18000cd25  call    cs:__imp_EnterCriticalSection
0x18000cd2b  nop
0x18000cd2c  cmp     qword ptr [rbx+48h], 0
0x18000cd31  jnz     loc_18000CDEC
0x18000cd37  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cd3e  mov     ecx, 80h; unsigned __int64
0x18000cd43  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000cd48  mov     [rsp+38h+arg_10], rax
0x18000cd4d  test    rax, rax
0x18000cd50  jz      short loc_18000CD5F
0x18000cd52  mov     rcx, rax; this
0x18000cd55  call    ??0DockCache@@QEAA@XZ; DockCache::DockCache(void)
0x18000cd5a  mov     rsi, rax
0x18000cd5d  jmp     short loc_18000CD61
0x18000cd5f  xor     esi, esi
0x18000cd61  mov     rbp, [rbx+48h]
0x18000cd65  mov     edi, 1
0x18000cd6a  cmp     rbp, rsi
0x18000cd6d  jz      short loc_18000CD9D
0x18000cd6f  test    rbp, rbp
0x18000cd72  jz      short loc_18000CD90
0x18000cd74  or      eax, 0FFFFFFFFh
0x18000cd77  lock xadd [rbp+60h], eax
0x18000cd7c  cmp     eax, edi
0x18000cd7e  jnz     short loc_18000CD90
0x18000cd80  mov     rcx, rbp; this
0x18000cd83  call    ??1DockCache@@AEAA@XZ; DockCache::~DockCache(void)
0x18000cd88  mov     rcx, rbp; Block
0x18000cd8b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cd90  mov     [rbx+48h], rsi
0x18000cd94  test    rsi, rsi
0x18000cd97  jz      short loc_18000CD9D
0x18000cd99  lock add [rsi+60h], edi
0x18000cd9d  mov     rsi, [rbx+48h]
0x18000cda1  test    rsi, rsi
0x18000cda4  jnz     short loc_18000CDAD
0x18000cda6  mov     edi, 8007000Eh
0x18000cdab  jmp     short loc_18000CDEE
0x18000cdad  mov     rbx, [rbx+40h]
0x18000cdb1  test    rbx, rbx
0x18000cdb4  jz      short loc_18000CDEE
0x18000cdb6  mov     rcx, [rsi+70h]; this
0x18000cdba  cmp     rcx, rbx
0x18000cdbd  jz      short loc_18000CDD1
0x18000cdbf  test    rcx, rcx
0x18000cdc2  jz      short loc_18000CDC9
0x18000cdc4  call    ?Release@DockingProviders@@QEAAKXZ; DockingProviders::Release(void)
0x18000cdc9  mov     [rsi+70h], rbx
0x18000cdcd  lock add [rbx+8], edi
0x18000cdd1  lea     r9, [rsi+78h]; unsigned __int64 *
0x18000cdd5  lea     r8, ConnectionListenerCallback; void (__high *)(unsigned __int64, void *, enum _ConnectionKind, unsigned int, struct _DOCK_PROFILE *)
0x18000cddc  mov     rdx, rsi; void *
0x18000cddf  mov     rcx, [rsi+70h]; this
0x18000cde3  call    ?RegisterConnectionListener@DockingProviders@@QEAAJPEAXP6AX_K0W4_ConnectionKind@@KPEAU_DOCK_PROFILE@@@ZPEA_K@Z; DockingProviders::RegisterConnectionListener(void *,void (*)(unsigned __int64,void *,_ConnectionKind,ulong,_DOCK_PROFILE *),unsigned __int64 *)
0x18000cde8  mov     edi, eax
0x18000cdea  jmp     short loc_18000CDEE
0x18000cdec  xor     edi, edi
0x18000cdee  mov     rcx, r14; lpCriticalSection
0x18000cdf1  call    cs:__imp_LeaveCriticalSection
0x18000cdf7  mov     eax, edi
0x18000cdf9  jmp     short loc_18000CDFD
0x18000cdfb  xor     eax, eax
0x18000cdfd  mov     rbx, [rsp+38h+arg_0]
0x18000ce02  mov     rbp, [rsp+38h+arg_8]
0x18000ce07  add     rsp, 20h
0x18000ce0b  pop     r14
0x18000ce0d  pop     rdi
0x18000ce0e  pop     rsi
0x18000ce0f  retn
```
