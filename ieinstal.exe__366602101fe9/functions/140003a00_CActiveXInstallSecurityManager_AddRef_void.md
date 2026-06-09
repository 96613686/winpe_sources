# CActiveXInstallSecurityManager::AddRef(void)

- ea: `0x140003a00`
- end: `0x140003a08`
- name: `?AddRef@CActiveXInstallSecurityManager@@UEAAKXZ`
- size: `8`
- prototype: `unsigned int __fastcall(CActiveXInstallSecurityManager *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CActiveXInstallSecurityManager::AddRef(CActiveXInstallSecurityManager *this)
{
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  return *((unsigned int *)this + 2);
}

```

## disassembly

```asm
0x140003a00  lock inc dword ptr [rcx+8]
0x140003a04  mov     eax, [rcx+8]
0x140003a07  retn
```
