# CIEAdminBrokerObject::InitializeSystemInstaller(ushort *,ulong,IUnknown *,ushort * *)

- ea: `0x140007ed0`
- end: `0x140007f9d`
- name: `?InitializeSystemInstaller@CIEAdminBrokerObject@@UEAAJPEAGKPEAUIUnknown@@PEAPEAG@Z`
- size: `205`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, unsigned int, struct IUnknown *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x140003978`
- `0x1400039bc`
- `0x1400043d8`
- `0x14000447c`
- `0x140004aa0`
- `0x140007ed0`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::InitializeSystemInstaller(
        CIEAdminBrokerObject *this,
        unsigned __int16 *a2,
        int a3,
        struct IUnknown *a4,
        unsigned __int16 **a5)
{
  void *v10; // rdi
  CActiveXInstallBroker *v11; // rax
  CActiveXInstallBroker *v12; // rax

  if ( *((_DWORD *)this + 8) && !*((_DWORD *)this + 9) || !g_fRunningAsSystem && !g_fRunningAsAdminWithHighIL )
    return 2147500037LL;
  *((_DWORD *)this + 8) = 1;
  *((_DWORD *)this + 9) = 1;
  if ( !a4 )
    return 2147942487LL;
  v10 = (void *)*((_QWORD *)this + 3);
  if ( v10 )
  {
    CActiveXInstallBroker::~CActiveXInstallBroker(*((CActiveXInstallBroker **)this + 3));
    operator delete(v10);
  }
  v11 = (CActiveXInstallBroker *)operator new(0x1A8u);
  if ( v11 )
  {
    v12 = CActiveXInstallBroker::CActiveXInstallBroker(v11);
    *((_QWORD *)this + 3) = v12;
    if ( v12 )
      return CActiveXInstallBroker::InitializeAxInstaller(v12, *((_DWORD *)this + 9), a2, a3, a4, a5);
  }
  else
  {
    *((_QWORD *)this + 3) = 0;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x140007ed0  push    rbx
0x140007ed2  push    rbp
0x140007ed3  push    rsi
0x140007ed4  push    rdi
0x140007ed5  push    r14
0x140007ed7  sub     rsp, 30h
0x140007edb  cmp     dword ptr [rcx+20h], 0
0x140007edf  mov     rsi, r9
0x140007ee2  mov     ebp, r8d
0x140007ee5  mov     r14, rdx
0x140007ee8  mov     rbx, rcx
0x140007eeb  jz      short loc_140007EF3
0x140007eed  cmp     dword ptr [rcx+24h], 0
0x140007ef1  jz      short loc_140007F05
0x140007ef3  cmp     cs:?g_fRunningAsSystem@@3HA, 0; int g_fRunningAsSystem
0x140007efa  jnz     short loc_140007F0F
0x140007efc  cmp     cs:?g_fRunningAsAdminWithHighIL@@3HA, 0; int g_fRunningAsAdminWithHighIL
0x140007f03  jnz     short loc_140007F0F
0x140007f05  mov     eax, 80004005h
0x140007f0a  jmp     loc_140007F91
0x140007f0f  mov     ecx, 1
0x140007f14  mov     [rbx+20h], ecx
0x140007f17  mov     [rbx+24h], ecx
0x140007f1a  test    rsi, rsi
0x140007f1d  jnz     short loc_140007F26
0x140007f1f  mov     eax, 80070057h
0x140007f24  jmp     short loc_140007F91
0x140007f26  mov     rdi, [rbx+18h]
0x140007f2a  test    rdi, rdi
0x140007f2d  jz      short loc_140007F3F
0x140007f2f  mov     rcx, rdi; this
0x140007f32  call    ??1CActiveXInstallBroker@@QEAA@XZ; CActiveXInstallBroker::~CActiveXInstallBroker(void)
0x140007f37  mov     rcx, rdi; lpMem
0x140007f3a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140007f3f  mov     ecx, 1A8h; dwBytes
0x140007f44  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007f49  test    rax, rax
0x140007f4c  jz      short loc_140007F84
0x140007f4e  mov     rcx, rax; this
0x140007f51  call    ??0CActiveXInstallBroker@@QEAA@XZ; CActiveXInstallBroker::CActiveXInstallBroker(void)
0x140007f56  mov     [rbx+18h], rax
0x140007f5a  test    rax, rax
0x140007f5d  jz      short loc_140007F8C
0x140007f5f  mov     rcx, [rsp+58h+arg_20]
0x140007f67  mov     r9d, ebp; unsigned int
0x140007f6a  mov     edx, [rbx+24h]; int
0x140007f6d  mov     r8, r14; unsigned __int16 *
0x140007f70  mov     [rsp+58h+var_30], rcx; unsigned __int16 **
0x140007f75  mov     rcx, rax; this
0x140007f78  mov     [rsp+58h+var_38], rsi; struct IUnknown *
0x140007f7d  call    ?InitializeAxInstaller@CActiveXInstallBroker@@QEAAJHPEAGKPEAUIUnknown@@PEAPEAG@Z; CActiveXInstallBroker::InitializeAxInstaller(int,ushort *,ulong,IUnknown *,ushort * *)
0x140007f82  jmp     short loc_140007F91
0x140007f84  mov     qword ptr [rbx+18h], 0
0x140007f8c  mov     eax, 8007000Eh
0x140007f91  add     rsp, 30h
0x140007f95  pop     r14
0x140007f97  pop     rdi
0x140007f98  pop     rsi
0x140007f99  pop     rbp
0x140007f9a  pop     rbx
0x140007f9b  retn
```
