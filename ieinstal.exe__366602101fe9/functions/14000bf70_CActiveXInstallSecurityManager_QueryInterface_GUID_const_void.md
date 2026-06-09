# CActiveXInstallSecurityManager::QueryInterface(_GUID const &,void * *)

- ea: `0x14000bf70`
- end: `0x14000bfce`
- name: `?QueryInterface@CActiveXInstallSecurityManager@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `94`
- prototype: `__int64 __fastcall(CActiveXInstallSecurityManager *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000bf70`
- `0x140011010`

## pseudocode

```c
__int64 __fastcall CActiveXInstallSecurityManager::QueryInterface(
        CActiveXInstallSecurityManager *this,
        const struct _GUID *a2,
        void **a3)
{
  unsigned int v3; // ebx

  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IInternetHostSecurityManager.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IInternetHostSecurityManager.Data4 )
  {
    *a3 = this;
    v3 = 0;
    (*(void (__fastcall **)(CActiveXInstallSecurityManager *))(*(_QWORD *)this + 8LL))(this);
  }
  else
  {
    *a3 = 0;
    return (unsigned int)-2147467262;
  }
  return v3;
}

```

## disassembly

```asm
0x14000bf70  push    rbx
0x14000bf72  sub     rsp, 20h
0x14000bf76  mov     rax, [rdx]
0x14000bf79  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x14000bf80  jnz     short loc_14000BF8F
0x14000bf82  mov     rax, [rdx+8]
0x14000bf86  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x14000bf8d  jz      short loc_14000BFA8
0x14000bf8f  mov     rax, [rdx]
0x14000bf92  cmp     rax, qword ptr cs:IID_IInternetHostSecurityManager.Data1
0x14000bf99  jnz     short loc_14000BFBB
0x14000bf9b  mov     rax, [rdx+8]
0x14000bf9f  cmp     rax, qword ptr cs:IID_IInternetHostSecurityManager.Data4
0x14000bfa6  jnz     short loc_14000BFBB
0x14000bfa8  mov     [r8], rcx
0x14000bfab  xor     ebx, ebx
0x14000bfad  mov     rax, [rcx]
0x14000bfb0  mov     rax, [rax+8]
0x14000bfb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bfb9  jmp     short loc_14000BFC5
0x14000bfbb  xor     ebx, ebx
0x14000bfbd  mov     [r8], rbx
0x14000bfc0  mov     ebx, 80004002h
0x14000bfc5  mov     eax, ebx
0x14000bfc7  add     rsp, 20h
0x14000bfcb  pop     rbx
0x14000bfcc  retn
```
