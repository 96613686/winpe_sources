# CClfsLogFcbVirtual::Open(uchar,IFcbPhysical *,void *,_SECURITY_SUBJECT_CONTEXT &,ulong,ulong,_ACCESS_STATE *,char,_FILE_OBJECT *,CClfsLogCcb *)

- ea: `0x140074c68`
- end: `0x140074ff7`
- name: `?Open@CClfsLogFcbVirtual@@QEAAJEPEAUIFcbPhysical@@PEAXAEAU_SECURITY_SUBJECT_CONTEXT@@KKPEAU_ACCESS_STATE@@DPEAU_FILE_OBJECT@@PEAVCClfsLogCcb@@@Z`
- size: `911`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbVirtual *__hidden this@<rcx>, unsigned __int8@<dl>, struct IFcbPhysical *@<r8>, void *@<r9>, struct _SECURITY_SUBJECT_CONTEXT *, ACCESS_MASK DesiredAccess, ULONG DesiredShareAccess, struct _ACCESS_STATE *, char, struct _FILE_OBJECT *, struct CClfsLogCcb *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140007f2c`

## callees

- `0x140005840`
- `0x14000714c`
- `0x140007550`
- `0x140010568`
- `0x140017f20`
- `0x140073dd0`
- `0x140074c68`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140074cb6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140074cb6`
- `ntoskrnl!KeBugCheckEx` at `0x140074fea`
- `ntoskrnl!KeBugCheckEx` at `0x140074fea`
- `ntoskrnl!IoCheckShareAccess` at `0x140074f1c`
- `ntoskrnl!IoCheckShareAccess` at `0x140074f1c`
- `ntoskrnl!IoSetShareAccess` at `0x140074f34`
- `ntoskrnl!IoSetShareAccess` at `0x140074f34`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbVirtual::Open(
        CClfsLogFcbVirtual *this,
        unsigned __int8 a2,
        struct IFcbPhysical *a3,
        void *a4,
        struct _SECURITY_SUBJECT_CONTEXT *a5,
        ACCESS_MASK DesiredAccess,
        ULONG DesiredShareAccess,
        struct _ACCESS_STATE *a8,
        char a9,
        PFILE_OBJECT FileObject,
        struct CClfsLogCcb *a11)
{
  char *v14; // r15
  BOOLEAN v15; // r14
  struct _FILE_OBJECT *v16; // rsi
  __int64 v17; // rdx
  __int64 v18; // rcx
  NTSTATUS v19; // edi
  __int64 v20; // rdx
  __int64 v21; // rdx
  char v22; // al
  struct _SHARE_ACCESS *v23; // r9
  __int64 v25; // [rsp+98h] [rbp+20h] BYREF

  v25 = 0;
  if ( !a2 || a2 > 0x60u )
    KeBugCheckEx(0xC1F5u, 0x1Fu, a2, (ULONG_PTR)this, 0);
  v14 = (char *)this + 200;
  v15 = ExAcquireResourceExclusiveLite((PERESOURCE)((char *)this + 200), 1u);
  v16 = FileObject;
  if ( (*((_BYTE *)this + 364) & 1) != 0 )
  {
    *((_BYTE *)this + 616) = a2;
    *((_QWORD *)this + 70) = v16->DeviceObject;
    *((_QWORD *)this + 80) = a3;
    (*(void (__fastcall **)(struct IFcbPhysical *))(*(_QWORD *)a3 + 40LL))(a3);
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 80) + 456LL))(
      *((_QWORD *)this + 80),
      (char *)this + 56);
    LOBYTE(v17) = *((_BYTE *)this + 616);
    (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)this + 80) + 328LL))(
      *((_QWORD *)this + 80),
      v17,
      &v25);
    v18 = v25;
    if ( !v25 )
    {
      v19 = -1072037875;
      goto LABEL_23;
    }
    *((_WORD *)this + 188) = *(_WORD *)(v25 + 10);
    *((_QWORD *)this + 54) = *(_QWORD *)(v18 + 32);
    *((_QWORD *)this + 55) = *(_QWORD *)(v18 + 40);
    *((_QWORD *)this + 56) = *(_QWORD *)(v18 + 48);
    *((_QWORD *)this + 62) = *(_QWORD *)(v18 + 64);
    *((_QWORD *)this + 61) = *(_QWORD *)(v18 + 72);
    *((_QWORD *)this + 63) = *(_QWORD *)(v18 + 80);
    *((_QWORD *)this + 64) = *(_QWORD *)(v18 + 88);
    *((_DWORD *)this + 95) = *(_DWORD *)(v18 + 16);
    v20 = *(_QWORD *)(v18 + 96);
    if ( (*(_BYTE *)(v18 + 120) & 0x20) != 0 )
    {
      *((CLFS_LSN *)this + 64) = CLFS_LSN_INVALID;
      *(_BYTE *)(v18 + 120) &= ~0x20u;
    }
    if ( CLFS_LSN_INVALID.ullOffset != v20 )
      *((_BYTE *)this + 648) = 1;
    (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 80) + 336LL))(*((_QWORD *)this + 80), &v25);
    LOBYTE(v21) = *((_BYTE *)this + 616);
    v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 80) + 112LL))(
            *((_QWORD *)this + 80),
            v21,
            (char *)this + 504);
    if ( v19 < 0 )
      goto LABEL_22;
    *((_DWORD *)this + 91) |= 4u;
    *((_DWORD *)this + 91) &= ~1u;
  }
  if ( CClfsLogFcbVirtual::IsLogSecure(this) )
  {
    v19 = (*(__int64 (__fastcall **)(_QWORD, struct _SECURITY_SUBJECT_CONTEXT *, _QWORD, _QWORD, struct _ACCESS_STATE *, char, char))(**((_QWORD **)this + 80) + 400LL))(
            *((_QWORD *)this + 80),
            a5,
            DesiredAccess,
            a8->PreviouslyGrantedAccess,
            a8,
            a9,
            1);
    if ( v19 < 0 )
      goto LABEL_22;
  }
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 80) + 56LL))(*((_QWORD *)this + 80))
    && (DesiredAccess & 0x10006) != 0 )
  {
    v19 = -1073741790;
  }
  else
  {
    v22 = (*(__int64 (__fastcall **)(CClfsLogFcbVirtual *))(*(_QWORD *)this + 344LL))(this);
    v23 = (struct _SHARE_ACCESS *)((char *)this + 336);
    if ( v22 )
    {
      v19 = IoCheckShareAccess(DesiredAccess, DesiredShareAccess, v16, v23, 1u);
      if ( v19 < 0 )
        goto LABEL_22;
    }
    else
    {
      IoSetShareAccess(DesiredAccess, DesiredShareAccess, v16, v23);
      v19 = 0;
    }
    CClfsLogCcb::Link(a11, (struct _LIST_ENTRY *)this + 25);
    CClfsLogFcbCommon::AddHandleRef(this);
    CClfsLogFcbCommon::SetFileObject(this, v16, a11);
  }
LABEL_22:
  v18 = v25;
LABEL_23:
  if ( v15 )
  {
    ClfsReleaseResourceLite(v14);
    v18 = v25;
  }
  if ( v18 )
    (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 80) + 336LL))(*((_QWORD *)this + 80), &v25);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x140074c68  mov     rax, rsp
0x140074c6b  mov     [rax+10h], rbx
0x140074c6f  mov     [rax+20h], r9
0x140074c73  mov     [rax+8], rcx
0x140074c77  push    rsi
0x140074c78  push    rdi
0x140074c79  push    r12
0x140074c7b  push    r14
0x140074c7d  push    r15
0x140074c7f  sub     rsp, 50h
0x140074c83  mov     r12, r8
0x140074c86  movzx   edi, dl
0x140074c89  mov     rbx, rcx
0x140074c8c  mov     qword ptr [rax+20h], 0
0x140074c94  test    dl, dl
0x140074c96  jz      loc_140074FD1
0x140074c9c  mov     byte ptr [rax-38h], 0
0x140074ca0  cmp     dil, 60h ; '`'
0x140074ca4  ja      loc_140074FD1
0x140074caa  lea     r15, [rcx+0C8h]
0x140074cb1  mov     dl, 1; Wait
0x140074cb3  mov     rcx, r15; Resource
0x140074cb6  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140074cbd  nop     dword ptr [rax+rax+00h]
0x140074cc2  mov     r14b, al
0x140074cc5  mov     [rsp+78h+var_38], al
0x140074cc9  mov     rsi, [rsp+78h+FileObject]
0x140074cd1  test    byte ptr [rbx+16Ch], 1
0x140074cd8  jz      loc_140074E53
0x140074cde  mov     [rbx+268h], dil
0x140074ce5  mov     rcx, [rsi+8]
0x140074ce9  mov     [rbx+230h], rcx
0x140074cf0  mov     [rbx+280h], r12
0x140074cf7  mov     rcx, [r12]
0x140074cfb  mov     rax, [rcx+28h]
0x140074cff  mov     rcx, r12
0x140074d02  call    _guard_dispatch_icall
0x140074d07  mov     rcx, [rbx+280h]
0x140074d0e  mov     rax, [rcx]
0x140074d11  lea     rdx, [rbx+38h]
0x140074d15  mov     rax, [rax+1C8h]
0x140074d1c  call    _guard_dispatch_icall
0x140074d21  mov     rcx, [rbx+280h]
0x140074d28  mov     rax, [rcx]
0x140074d2b  mov     rax, [rax+148h]
0x140074d32  lea     r8, [rsp+78h+arg_18]
0x140074d3a  mov     dl, [rbx+268h]
0x140074d40  call    _guard_dispatch_icall
0x140074d45  mov     rcx, [rsp+78h+arg_18]
0x140074d4d  test    rcx, rcx
0x140074d50  jnz     short loc_140074D60
0x140074d52  mov     edi, 0C01A000Dh
0x140074d57  mov     [rsp+78h+var_34], edi
0x140074d5b  jmp     loc_140074F81
0x140074d60  movzx   eax, word ptr [rcx+0Ah]
0x140074d64  mov     [rbx+178h], ax
0x140074d6b  mov     rax, [rcx+20h]
0x140074d6f  mov     [rbx+1B0h], rax
0x140074d76  mov     rax, [rcx+28h]
0x140074d7a  mov     [rbx+1B8h], rax
0x140074d81  mov     rax, [rcx+30h]
0x140074d85  mov     [rbx+1C0h], rax
0x140074d8c  mov     rax, [rcx+40h]
0x140074d90  mov     [rbx+1F0h], rax
0x140074d97  mov     rax, [rcx+48h]
0x140074d9b  mov     [rbx+1E8h], rax
0x140074da2  lea     rdi, [rbx+1F8h]
0x140074da9  mov     rax, [rcx+50h]
0x140074dad  mov     [rdi], rax
0x140074db0  mov     rax, [rcx+58h]
0x140074db4  mov     [rbx+200h], rax
0x140074dbb  mov     eax, [rcx+10h]
0x140074dbe  mov     [rbx+17Ch], eax
0x140074dc4  mov     rdx, [rcx+60h]
0x140074dc8  mov     [rsp+78h+var_30], rdx
0x140074dcd  test    byte ptr [rcx+78h], 20h
0x140074dd1  jz      short loc_140074DE5
0x140074dd3  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140074dda  mov     [rbx+200h], rax
0x140074de1  and     byte ptr [rcx+78h], 0DFh
0x140074de5  cmp     qword ptr cs:CLFS_LSN_INVALID, rdx
0x140074dec  jz      short loc_140074DF5
0x140074dee  mov     byte ptr [rbx+288h], 1
0x140074df5  mov     rcx, [rbx+280h]
0x140074dfc  mov     rax, [rcx]
0x140074dff  mov     rax, [rax+150h]
0x140074e06  lea     rdx, [rsp+78h+arg_18]
0x140074e0e  call    _guard_dispatch_icall
0x140074e13  mov     rcx, [rbx+280h]
0x140074e1a  mov     rax, [rcx]
0x140074e1d  mov     rax, [rax+70h]
0x140074e21  mov     r8, rdi
0x140074e24  mov     dl, [rbx+268h]
0x140074e2a  call    _guard_dispatch_icall
0x140074e2f  mov     edi, eax
0x140074e31  mov     [rsp+78h+var_34], eax
0x140074e35  test    eax, eax
0x140074e37  js      loc_140074F79
0x140074e3d  or      dword ptr [rbx+16Ch], 4
0x140074e44  mov     eax, [rbx+16Ch]
0x140074e4a  and     eax, 0FFFFFFFEh
0x140074e4d  mov     [rbx+16Ch], eax
0x140074e53  mov     rcx, rbx; this
0x140074e56  call    ?IsLogSecure@CClfsLogFcbVirtual@@QEBAEXZ; CClfsLogFcbVirtual::IsLogSecure(void)
0x140074e5b  test    al, al
0x140074e5d  jz      short loc_140074EB4
0x140074e5f  mov     rcx, [rbx+280h]
0x140074e66  mov     rax, [rcx]
0x140074e69  mov     rax, [rax+190h]
0x140074e70  mov     [rsp+78h+var_48], 1
0x140074e75  mov     dl, [rsp+78h+arg_40]
0x140074e7c  mov     [rsp+78h+var_50], dl
0x140074e80  mov     r9, [rsp+78h+arg_38]
0x140074e88  mov     qword ptr [rsp+78h+Update], r9
0x140074e8d  mov     r9d, [r9+14h]
0x140074e91  mov     r8d, [rsp+78h+DesiredAccess]
0x140074e99  mov     rdx, [rsp+78h+arg_20]
0x140074ea1  call    _guard_dispatch_icall
0x140074ea6  mov     edi, eax
0x140074ea8  mov     [rsp+78h+var_34], eax
0x140074eac  test    eax, eax
0x140074eae  js      loc_140074F79
0x140074eb4  mov     rcx, [rbx+280h]
0x140074ebb  mov     rax, [rcx]
0x140074ebe  mov     rax, [rax+38h]
0x140074ec2  call    _guard_dispatch_icall
0x140074ec7  test    al, al
0x140074ec9  jz      short loc_140074EE6
0x140074ecb  test    [rsp+78h+DesiredAccess], 10006h
0x140074ed6  jz      short loc_140074EE6
0x140074ed8  mov     edi, 0C0000022h
0x140074edd  mov     [rsp+78h+var_34], edi
0x140074ee1  jmp     loc_140074F79
0x140074ee6  lea     rdi, [rbx+150h]
0x140074eed  mov     rax, [rbx]
0x140074ef0  mov     rax, [rax+158h]
0x140074ef7  mov     rcx, rbx
0x140074efa  call    _guard_dispatch_icall
0x140074eff  mov     r9, rdi; ShareAccess
0x140074f02  mov     r8, rsi; FileObject
0x140074f05  mov     edx, [rsp+78h+DesiredShareAccess]; DesiredShareAccess
0x140074f0c  mov     ecx, [rsp+78h+DesiredAccess]; DesiredAccess
0x140074f13  test    al, al
0x140074f15  jz      short loc_140074F34
0x140074f17  mov     [rsp+78h+Update], 1; Update
0x140074f1c  call    cs:__imp_IoCheckShareAccess
0x140074f23  nop     dword ptr [rax+rax+00h]
0x140074f28  mov     edi, eax
0x140074f2a  mov     [rsp+78h+var_34], eax
0x140074f2e  test    eax, eax
0x140074f30  jns     short loc_140074F46
0x140074f32  jmp     short loc_140074F79
0x140074f34  call    cs:__imp_IoSetShareAccess
0x140074f3b  nop     dword ptr [rax+rax+00h]
0x140074f40  xor     edi, edi
0x140074f42  mov     [rsp+78h+var_34], edi
0x140074f46  test    edi, edi
0x140074f48  js      short loc_140074F79
0x140074f4a  lea     rdx, [rbx+190h]; struct _LIST_ENTRY *
0x140074f51  mov     rcx, [rsp+78h+arg_50]; this
0x140074f59  call    ?Link@CClfsLogCcb@@QEAAXPEAU_LIST_ENTRY@@@Z; CClfsLogCcb::Link(_LIST_ENTRY *)
0x140074f5e  mov     rcx, rbx; this
0x140074f61  call    ?AddHandleRef@CClfsLogFcbCommon@@QEAAKXZ; CClfsLogFcbCommon::AddHandleRef(void)
0x140074f66  mov     r8, [rsp+78h+arg_50]; struct CClfsLogCcb *
0x140074f6e  mov     rdx, rsi; struct _FILE_OBJECT *
0x140074f71  mov     rcx, rbx; this
0x140074f74  call    ?SetFileObject@CClfsLogFcbCommon@@QEAAXPEAU_FILE_OBJECT@@PEAVCClfsLogCcb@@@Z; CClfsLogFcbCommon::SetFileObject(_FILE_OBJECT *,CClfsLogCcb *)
0x140074f79  mov     rcx, [rsp+78h+arg_18]
0x140074f81  test    r14b, r14b
0x140074f84  jz      short loc_140074F96
0x140074f86  mov     rcx, r15
0x140074f89  call    ClfsReleaseResourceLite
0x140074f8e  mov     rcx, [rsp+78h+arg_18]
0x140074f96  test    rcx, rcx
0x140074f99  jz      short loc_140074FB9
0x140074f9b  mov     rcx, [rbx+280h]
0x140074fa2  mov     rax, [rcx]
0x140074fa5  mov     rax, [rax+150h]
0x140074fac  lea     rdx, [rsp+78h+arg_18]
0x140074fb4  call    _guard_dispatch_icall
0x140074fb9  mov     eax, edi
0x140074fbb  mov     rbx, [rsp+78h+arg_8]
0x140074fc3  add     rsp, 50h
0x140074fc7  pop     r15
0x140074fc9  pop     r14
0x140074fcb  pop     r12
0x140074fcd  pop     rdi
0x140074fce  pop     rsi
0x140074fcf  retn
0x140074fd1  mov     r8, rdi; BugCheckParameter2
0x140074fd4  mov     qword ptr [rsp+78h+Update], 0; BugCheckParameter4
0x140074fdd  mov     r9, rbx; BugCheckParameter3
0x140074fe0  mov     edx, 1Fh; BugCheckParameter1
0x140074fe5  mov     ecx, 0C1F5h; BugCheckCode
0x140074fea  call    cs:__imp_KeBugCheckEx
0x14007c487  push    rbp
0x14007c489  sub     rsp, 40h
0x14007c48d  mov     rbp, rdx
0x14007c490  cmp     byte ptr [rbp+40h], 0
0x14007c494  jz      short loc_14007C4AD
0x14007c496  mov     rcx, [rbp+80h]
0x14007c49d  add     rcx, 0C8h
0x14007c4a4  call    ClfsReleaseResourceLite
0x14007c4a9  mov     byte ptr [rbp+40h], 0
0x14007c4ad  cmp     qword ptr [rbp+98h], 0
0x14007c4b5  jz      short loc_14007C4DC
0x14007c4b7  mov     rax, [rbp+80h]
0x14007c4be  mov     rcx, [rax+280h]
0x14007c4c5  mov     rdx, [rcx]
0x14007c4c8  mov     rax, [rdx+150h]
0x14007c4cf  lea     rdx, [rbp+98h]
0x14007c4d6  call    _guard_dispatch_icall
0x14007c4db  nop
0x14007c4dc  add     rsp, 40h
0x14007c4e0  pop     rbp
0x14007c4e1  retn
```
