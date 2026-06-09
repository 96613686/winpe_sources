# CIEAdminBrokerObject::~CIEAdminBrokerObject(void)

- ea: `0x140007bcc`
- end: `0x140007c8d`
- name: `??1CIEAdminBrokerObject@@QEAA@XZ`
- size: `193`
- prototype: `void __fastcall(CIEAdminBrokerObject *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140008230`

## callees

- `0x140003978`
- `0x1400039bc`
- `0x1400042c4`
- `0x14000447c`
- `0x140007bcc`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140007c37`
- `KERNEL32!SetEvent` at `0x140007c37`
- `USER32!PostQuitMessage` at `0x140007c45`
- `USER32!PostQuitMessage` at `0x140007c45`

## pseudocode

```c
void __fastcall CIEAdminBrokerObject::~CIEAdminBrokerObject(CIEAdminBrokerObject *this)
{
  CActiveXInstallBroker *v1; // rdi

  v1 = (CActiveXInstallBroker *)*((_QWORD *)this + 4);
  *(_QWORD *)this = &CIEAdminBrokerObject::`vftable'{for `IeAxiAdminInstaller'};
  *((_QWORD *)this + 1) = &CIEAdminBrokerObject::`vftable'{for `IeAxiSystemInstaller'};
  *((_QWORD *)this + 2) = &CIEAdminBrokerObject::`vftable'{for `IeAxiInstaller2'};
  if ( v1 )
  {
    CActiveXInstallBroker::~CActiveXInstallBroker(v1);
    operator delete(v1);
  }
  *((_QWORD *)this + 4) = 0;
  if ( _InterlockedExchangeAdd(&g_ObjectCount, 0xFFFFFFFF) == 1 )
  {
    if ( g_hQuitEvent )
      SetEvent(g_hQuitEvent);
    PostQuitMessage(0);
  }
  if ( !_InterlockedDecrement(&g_LockCount) )
  {
    operator new(4u);
    _InterlockedIncrement(&g_LockCount);
    if ( !_InterlockedDecrement(&g_LockCount) )
      RevokeClassFactory();
  }
}

```

## disassembly

```asm
0x140007bcc  mov     [rsp+arg_8], rbx
0x140007bd1  push    rdi
0x140007bd2  sub     rsp, 20h
0x140007bd6  mov     rdi, [rcx+20h]
0x140007bda  lea     rax, ??_7CIEAdminBrokerObject@@6BIeAxiAdminInstaller@@@; const CIEAdminBrokerObject::`vftable'{for `IeAxiAdminInstaller'}
0x140007be1  mov     [rcx], rax
0x140007be4  lea     rax, ??_7CIEAdminBrokerObject@@6BIeAxiSystemInstaller@@@; const CIEAdminBrokerObject::`vftable'{for `IeAxiSystemInstaller'}
0x140007beb  mov     [rcx+8], rax
0x140007bef  lea     rax, ??_7CIEAdminBrokerObject@@6BIeAxiInstaller2@@@; const CIEAdminBrokerObject::`vftable'{for `IeAxiInstaller2'}
0x140007bf6  mov     [rcx+10h], rax
0x140007bfa  mov     rbx, rcx
0x140007bfd  test    rdi, rdi
0x140007c00  jz      short loc_140007C12
0x140007c02  mov     rcx, rdi; this
0x140007c05  call    ??1CActiveXInstallBroker@@QEAA@XZ; CActiveXInstallBroker::~CActiveXInstallBroker(void)
0x140007c0a  mov     rcx, rdi; lpMem
0x140007c0d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140007c12  mov     qword ptr [rbx+20h], 0
0x140007c1a  or      ebx, 0FFFFFFFFh
0x140007c1d  mov     eax, ebx
0x140007c1f  lock xadd cs:?g_ObjectCount@@3JA, eax; long g_ObjectCount
0x140007c27  add     eax, ebx
0x140007c29  jnz     short loc_140007C51
0x140007c2b  mov     rcx, cs:?g_hQuitEvent@@3PEAXEA; hEvent
0x140007c32  test    rcx, rcx
0x140007c35  jz      short loc_140007C43
0x140007c37  call    cs:__imp_SetEvent
0x140007c3e  nop     dword ptr [rax+rax+00h]
0x140007c43  xor     ecx, ecx; nExitCode
0x140007c45  call    cs:__imp_PostQuitMessage
0x140007c4c  nop     dword ptr [rax+rax+00h]
0x140007c51  mov     eax, ebx
0x140007c53  lock xadd cs:?g_LockCount@@3JA, eax; long g_LockCount
0x140007c5b  add     eax, ebx
0x140007c5d  jnz     short loc_140007C81
0x140007c5f  lea     ecx, [rax+4]; dwBytes
0x140007c62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007c67  lock inc cs:?g_LockCount@@3JA; long g_LockCount
0x140007c6e  mov     eax, ebx
0x140007c70  lock xadd cs:?g_LockCount@@3JA, eax; long g_LockCount
0x140007c78  add     eax, ebx
0x140007c7a  jnz     short loc_140007C81
0x140007c7c  call    ?RevokeClassFactory@@YAJXZ; RevokeClassFactory(void)
0x140007c81  mov     rbx, [rsp+28h+arg_8]
0x140007c86  add     rsp, 20h
0x140007c8a  pop     rdi
0x140007c8b  retn
```
