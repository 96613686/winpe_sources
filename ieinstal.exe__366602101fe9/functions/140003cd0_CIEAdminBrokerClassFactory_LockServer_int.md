# CIEAdminBrokerClassFactory::LockServer(int)

- ea: `0x140003cd0`
- end: `0x140003d2c`
- name: `?LockServer@CIEAdminBrokerClassFactory@@UEAAJH@Z`
- size: `92`
- prototype: `__int64 __fastcall(CIEAdminBrokerClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140003978`
- `0x140003cd0`
- `0x140004108`
- `0x1400042c4`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerClassFactory::LockServer(CIEAdminBrokerClassFactory *this, int a2)
{
  if ( a2 == 1 )
  {
    if ( !_InterlockedIncrement(&g_LockCount) )
    {
      _InterlockedIncrement(&g_LockCount);
      RegisterClassFactory();
    }
  }
  else if ( _InterlockedExchangeAdd(&g_LockCount, 0xFFFFFFFF) == 1 )
  {
    operator new(4u);
    _InterlockedIncrement(&g_LockCount);
    if ( _InterlockedExchangeAdd(&g_LockCount, 0xFFFFFFFF) == 1 )
      RevokeClassFactory();
  }
  return 0;
}

```

## disassembly

```asm
0x140003cd0  sub     rsp, 28h
0x140003cd4  cmp     edx, 1
0x140003cd7  jnz     short loc_140003CF0
0x140003cd9  lock inc cs:?g_LockCount@@3JA; long g_LockCount
0x140003ce0  jnz     short loc_140003D24
0x140003ce2  lock inc cs:?g_LockCount@@3JA; long g_LockCount
0x140003ce9  call    ?RegisterClassFactory@@YAJXZ; RegisterClassFactory(void)
0x140003cee  jmp     short loc_140003D24
0x140003cf0  or      eax, 0FFFFFFFFh
0x140003cf3  lock xadd cs:?g_LockCount@@3JA, eax; long g_LockCount
0x140003cfb  cmp     eax, 1
0x140003cfe  jnz     short loc_140003D24
0x140003d00  lea     ecx, [rax+3]; dwBytes
0x140003d03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003d08  lock inc cs:?g_LockCount@@3JA; long g_LockCount
0x140003d0f  or      eax, 0FFFFFFFFh
0x140003d12  lock xadd cs:?g_LockCount@@3JA, eax; long g_LockCount
0x140003d1a  cmp     eax, 1
0x140003d1d  jnz     short loc_140003D24
0x140003d1f  call    ?RevokeClassFactory@@YAJXZ; RevokeClassFactory(void)
0x140003d24  xor     eax, eax
0x140003d26  add     rsp, 28h
0x140003d2a  retn
```
