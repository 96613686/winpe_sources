# CActiveXInstallSecurityManager::Release(void)

- ea: `0x14000bfe0`
- end: `0x14000c023`
- name: `?Release@CActiveXInstallSecurityManager@@UEAAKXZ`
- size: `67`
- prototype: `unsigned int __fastcall(CActiveXInstallSecurityManager *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1400039bc`
- `0x14000bddc`
- `0x14000bfe0`

## pseudocode

```c
__int64 __fastcall CActiveXInstallSecurityManager::Release(CActiveXInstallSecurityManager *this)
{
  int v1; // edi
  unsigned int v3; // edi

  v1 = *((_DWORD *)this + 2);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
  {
    v3 = 0;
    if ( this )
    {
      CActiveXInstallSecurityManager::~CActiveXInstallSecurityManager(this);
      operator delete(this);
    }
  }
  else
  {
    return (unsigned int)(v1 - 1);
  }
  return v3;
}

```

## disassembly

```asm
0x14000bfe0  mov     [rsp+arg_0], rbx
0x14000bfe5  push    rdi
0x14000bfe6  sub     rsp, 20h
0x14000bfea  mov     edi, [rcx+8]
0x14000bfed  mov     rbx, rcx
0x14000bff0  or      eax, 0FFFFFFFFh
0x14000bff3  lock xadd [rcx+8], eax
0x14000bff8  cmp     eax, 1
0x14000bffb  jnz     short loc_14000C013
0x14000bffd  xor     edi, edi
0x14000bfff  test    rcx, rcx
0x14000c002  jz      short loc_14000C015
0x14000c004  call    ??1CActiveXInstallSecurityManager@@QEAA@XZ; CActiveXInstallSecurityManager::~CActiveXInstallSecurityManager(void)
0x14000c009  mov     rcx, rbx; lpMem
0x14000c00c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c011  jmp     short loc_14000C015
0x14000c013  dec     edi
0x14000c015  mov     rbx, [rsp+28h+arg_0]
0x14000c01a  mov     eax, edi
0x14000c01c  add     rsp, 20h
0x14000c020  pop     rdi
0x14000c021  retn
```
