# CIEAdminBrokerObject::InitializeAdminInstaller(ushort *,ulong,ushort * *)

- ea: `0x140007e20`
- end: `0x140007ebf`
- name: `?InitializeAdminInstaller@CIEAdminBrokerObject@@UEAAJPEAGKPEAPEAG@Z`
- size: `159`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x140003978`
- `0x1400039bc`
- `0x1400043d8`
- `0x14000447c`
- `0x140004aa0`
- `0x140007e20`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::InitializeAdminInstaller(
        CIEAdminBrokerObject *this,
        unsigned __int16 *a2,
        int a3,
        unsigned __int16 **a4)
{
  CActiveXInstallBroker *v9; // rdi
  CActiveXInstallBroker *v10; // rax
  CActiveXInstallBroker *v11; // rax

  if ( *((_DWORD *)this + 11) )
    return 2147500037LL;
  v9 = (CActiveXInstallBroker *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 5) = 1;
  if ( v9 )
  {
    CActiveXInstallBroker::~CActiveXInstallBroker(v9);
    operator delete(v9);
  }
  v10 = (CActiveXInstallBroker *)operator new(0x1A8u);
  if ( v10 )
  {
    v11 = CActiveXInstallBroker::CActiveXInstallBroker(v10);
    *((_QWORD *)this + 4) = v11;
    if ( v11 )
      return CActiveXInstallBroker::InitializeAxInstaller(v11, *((_DWORD *)this + 11), a2, a3, 0, a4);
  }
  else
  {
    *((_QWORD *)this + 4) = 0;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x140007e20  push    rbx
0x140007e22  push    rbp
0x140007e23  push    rsi
0x140007e24  push    rdi
0x140007e25  push    r14
0x140007e27  sub     rsp, 30h
0x140007e2b  cmp     dword ptr [rcx+2Ch], 0
0x140007e2f  mov     rsi, r9
0x140007e32  mov     ebp, r8d
0x140007e35  mov     r14, rdx
0x140007e38  mov     rbx, rcx
0x140007e3b  jz      short loc_140007E44
0x140007e3d  mov     eax, 80004005h
0x140007e42  jmp     short loc_140007EB3
0x140007e44  mov     rdi, [rcx+20h]
0x140007e48  mov     qword ptr [rcx+28h], 1
0x140007e50  test    rdi, rdi
0x140007e53  jz      short loc_140007E65
0x140007e55  mov     rcx, rdi; this
0x140007e58  call    ??1CActiveXInstallBroker@@QEAA@XZ; CActiveXInstallBroker::~CActiveXInstallBroker(void)
0x140007e5d  mov     rcx, rdi; lpMem
0x140007e60  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140007e65  mov     ecx, 1A8h; dwBytes
0x140007e6a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007e6f  test    rax, rax
0x140007e72  jz      short loc_140007EA6
0x140007e74  mov     rcx, rax; this
0x140007e77  call    ??0CActiveXInstallBroker@@QEAA@XZ; CActiveXInstallBroker::CActiveXInstallBroker(void)
0x140007e7c  mov     [rbx+20h], rax
0x140007e80  test    rax, rax
0x140007e83  jz      short loc_140007EAE
0x140007e85  mov     edx, [rbx+2Ch]; int
0x140007e88  mov     r9d, ebp; unsigned int
0x140007e8b  mov     [rsp+58h+var_30], rsi; unsigned __int16 **
0x140007e90  mov     r8, r14; unsigned __int16 *
0x140007e93  mov     rcx, rax; this
0x140007e96  mov     [rsp+58h+var_38], 0; struct IUnknown *
0x140007e9f  call    ?InitializeAxInstaller@CActiveXInstallBroker@@QEAAJHPEAGKPEAUIUnknown@@PEAPEAG@Z; CActiveXInstallBroker::InitializeAxInstaller(int,ushort *,ulong,IUnknown *,ushort * *)
0x140007ea4  jmp     short loc_140007EB3
0x140007ea6  mov     qword ptr [rbx+20h], 0
0x140007eae  mov     eax, 8007000Eh
0x140007eb3  add     rsp, 30h
0x140007eb7  pop     r14
0x140007eb9  pop     rdi
0x140007eba  pop     rsi
0x140007ebb  pop     rbp
0x140007ebc  pop     rbx
0x140007ebd  retn
```
