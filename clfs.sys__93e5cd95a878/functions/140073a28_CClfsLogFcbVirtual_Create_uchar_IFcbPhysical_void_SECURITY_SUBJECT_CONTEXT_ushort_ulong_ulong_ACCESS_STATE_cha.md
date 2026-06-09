# CClfsLogFcbVirtual::Create(uchar,IFcbPhysical *,void *,_SECURITY_SUBJECT_CONTEXT &,ushort,ulong,ulong,_ACCESS_STATE *,char,_FILE_OBJECT *,CClfsLogCcb *)

- ea: `0x140073a28`
- end: `0x140073dc9`
- name: `?Create@CClfsLogFcbVirtual@@QEAAJEPEAUIFcbPhysical@@PEAXAEAU_SECURITY_SUBJECT_CONTEXT@@GKKPEAU_ACCESS_STATE@@DPEAU_FILE_OBJECT@@PEAVCClfsLogCcb@@@Z`
- size: `929`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbVirtual *__hidden this@<rcx>, unsigned __int8@<dl>, struct IFcbPhysical *@<r8>, void *@<r9>, struct _SECURITY_SUBJECT_CONTEXT *, unsigned __int16, ACCESS_MASK DesiredAccess, ULONG DesiredShareAccess, struct _ACCESS_STATE *, char, struct _FILE_OBJECT *, struct CClfsLogCcb *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400011c0`

## callees

- `0x140005840`
- `0x14000714c`
- `0x140007550`
- `0x140010568`
- `0x140017f20`
- `0x140073a28`
- `0x140073dd0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140073a65`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140073a65`
- `ntoskrnl!IoCheckShareAccess` at `0x140073cc7`
- `ntoskrnl!IoCheckShareAccess` at `0x140073cc7`
- `ntoskrnl!IoSetShareAccess` at `0x140073cf3`
- `ntoskrnl!IoSetShareAccess` at `0x140073cf3`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbVirtual::Create(
        CClfsLogFcbVirtual *this,
        char a2,
        struct IFcbPhysical *a3,
        void *a4,
        struct _SECURITY_SUBJECT_CONTEXT *a5,
        unsigned __int16 a6,
        ACCESS_MASK DesiredAccess,
        ULONG DesiredShareAccess,
        struct _ACCESS_STATE *a9,
        char a10,
        PFILE_OBJECT FileObject,
        struct CClfsLogCcb *a12)
{
  char *v15; // r15
  BOOLEAN v16; // r14
  struct _FILE_OBJECT *v17; // rsi
  __int64 v18; // rdx
  NTSTATUS v19; // edi
  unsigned __int16 v20; // cx
  __int64 v22; // [rsp+88h] [rbp+20h] BYREF

  v22 = 0;
  v15 = (char *)this + 200;
  v16 = ExAcquireResourceExclusiveLite((PERESOURCE)((char *)this + 200), 1u);
  *((_BYTE *)this + 616) = a2;
  v17 = FileObject;
  *((_QWORD *)this + 70) = FileObject->DeviceObject;
  *((_QWORD *)this + 80) = a3;
  (*(void (__fastcall **)(struct IFcbPhysical *))(*(_QWORD *)a3 + 40LL))(a3);
  (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 80) + 456LL))(*((_QWORD *)this + 80), (char *)this + 56);
  LOBYTE(v18) = *((_BYTE *)this + 616);
  (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)this + 80) + 328LL))(
    *((_QWORD *)this + 80),
    v18,
    &v22);
  if ( v22 )
  {
    v20 = a6;
    *((_WORD *)this + 188) = a6;
    *(_WORD *)(v22 + 10) = v20;
    *(_QWORD *)(v22 + 32) = 0;
    *(_QWORD *)(v22 + 40) = 0;
    *(_QWORD *)(v22 + 48) = 0;
    *(_QWORD *)(v22 + 48) = 0;
    *(CLFS_LSN *)(v22 + 56) = CLFS_LSN_INVALID;
    *(_QWORD *)(v22 + 64) = *((_QWORD *)this + 62);
    *(_QWORD *)(v22 + 72) = *((_QWORD *)this + 61);
    *(_QWORD *)(v22 + 80) = *((_QWORD *)this + 63);
    *(_QWORD *)(v22 + 88) = *((_QWORD *)this + 64);
    *(CLFS_LSN *)(v22 + 96) = CLFS_LSN_INVALID;
    *(_DWORD *)(v22 + 16) = *((_DWORD *)this + 95);
    (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 80) + 336LL))(*((_QWORD *)this + 80), &v22);
    if ( !CClfsLogFcbVirtual::IsLogSecure(this)
      || (v19 = (*(__int64 (__fastcall **)(_QWORD, struct _SECURITY_SUBJECT_CONTEXT *, _QWORD, _QWORD, struct _ACCESS_STATE *, char, char))(**((_QWORD **)this + 80) + 400LL))(
                  *((_QWORD *)this + 80),
                  a5,
                  DesiredAccess,
                  a9->PreviouslyGrantedAccess,
                  a9,
                  a10,
                  1),
          v19 >= 0) )
    {
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 80) + 56LL))(*((_QWORD *)this + 80))
        && (DesiredAccess & 0x10006) != 0 )
      {
        v19 = -1073741790;
      }
      else
      {
        if ( (*(unsigned __int8 (__fastcall **)(CClfsLogFcbVirtual *))(*(_QWORD *)this + 344LL))(this)
          && (*((_DWORD *)this + 91) & 6) != 0 )
        {
          v19 = IoCheckShareAccess(DesiredAccess, DesiredShareAccess, v17, (PSHARE_ACCESS)this + 12, 1u);
        }
        else
        {
          IoSetShareAccess(DesiredAccess, DesiredShareAccess, v17, (PSHARE_ACCESS)this + 12);
          v19 = 0;
        }
        if ( v19 >= 0 )
        {
          if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 80) + 56LL))(*((_QWORD *)this + 80))
            || (v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 80) + 136LL))(*((_QWORD *)this + 80)),
                v19 >= 0) )
          {
            *((_DWORD *)this + 91) = 2;
            CClfsLogCcb::Link(a12, (struct _LIST_ENTRY *)this + 25);
            CClfsLogFcbCommon::AddHandleRef(this);
            CClfsLogFcbCommon::SetFileObject(this, v17, a12);
          }
        }
      }
    }
  }
  else
  {
    v19 = -1072037875;
  }
  if ( v16 )
    ClfsReleaseResourceLite(v15);
  if ( v22 )
    (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 80) + 336LL))(*((_QWORD *)this + 80), &v22);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x140073a28  mov     rax, rsp
0x140073a2b  mov     [rax+10h], rbx
0x140073a2f  mov     [rax+18h], rsi
0x140073a33  mov     [rax+20h], r9
0x140073a37  mov     [rax+8], rcx
0x140073a3b  push    rdi
0x140073a3c  push    r14
0x140073a3e  push    r15
0x140073a40  sub     rsp, 50h
0x140073a44  mov     rdi, r8
0x140073a47  mov     sil, dl
0x140073a4a  mov     rbx, rcx
0x140073a4d  mov     qword ptr [rax+20h], 0
0x140073a55  mov     byte ptr [rax-28h], 0
0x140073a59  lea     r15, [rcx+0C8h]
0x140073a60  mov     dl, 1; Wait
0x140073a62  mov     rcx, r15; Resource
0x140073a65  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140073a6c  nop     dword ptr [rax+rax+00h]
0x140073a71  mov     r14b, al
0x140073a74  mov     [rsp+68h+var_28], al
0x140073a78  mov     [rbx+268h], sil
0x140073a7f  mov     rsi, [rsp+68h+FileObject]
0x140073a87  mov     rcx, [rsi+8]
0x140073a8b  mov     [rbx+230h], rcx
0x140073a92  mov     [rbx+280h], rdi
0x140073a99  mov     rcx, [rdi]
0x140073a9c  mov     rax, [rcx+28h]
0x140073aa0  mov     rcx, rdi
0x140073aa3  call    _guard_dispatch_icall
0x140073aa8  mov     rcx, [rbx+280h]
0x140073aaf  mov     rax, [rcx]
0x140073ab2  lea     rdx, [rbx+38h]
0x140073ab6  mov     rax, [rax+1C8h]
0x140073abd  call    _guard_dispatch_icall
0x140073ac2  mov     rcx, [rbx+280h]
0x140073ac9  mov     rax, [rcx]
0x140073acc  mov     rax, [rax+148h]
0x140073ad3  lea     r8, [rsp+68h+arg_18]
0x140073adb  mov     dl, [rbx+268h]
0x140073ae1  call    _guard_dispatch_icall
0x140073ae6  cmp     [rsp+68h+arg_18], 0
0x140073aef  jnz     short loc_140073AFF
0x140073af1  mov     edi, 0C01A000Dh
0x140073af6  mov     [rsp+68h+var_24], edi
0x140073afa  jmp     loc_140073D7A
0x140073aff  movzx   ecx, [rsp+68h+arg_28]
0x140073b07  mov     [rbx+178h], cx
0x140073b0e  mov     rax, [rsp+68h+arg_18]
0x140073b16  mov     [rax+0Ah], cx
0x140073b1a  mov     rax, [rsp+68h+arg_18]
0x140073b22  mov     qword ptr [rax+20h], 0
0x140073b2a  mov     rax, [rsp+68h+arg_18]
0x140073b32  mov     qword ptr [rax+28h], 0
0x140073b3a  mov     rax, [rsp+68h+arg_18]
0x140073b42  mov     qword ptr [rax+30h], 0
0x140073b4a  mov     rax, [rsp+68h+arg_18]
0x140073b52  mov     qword ptr [rax+30h], 0
0x140073b5a  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140073b61  mov     rcx, [rsp+68h+arg_18]
0x140073b69  mov     [rcx+38h], rax
0x140073b6d  mov     rcx, [rbx+1F0h]
0x140073b74  mov     rax, [rsp+68h+arg_18]
0x140073b7c  mov     [rax+40h], rcx
0x140073b80  mov     rcx, [rbx+1E8h]
0x140073b87  mov     rax, [rsp+68h+arg_18]
0x140073b8f  mov     [rax+48h], rcx
0x140073b93  mov     rcx, [rbx+1F8h]
0x140073b9a  mov     rax, [rsp+68h+arg_18]
0x140073ba2  mov     [rax+50h], rcx
0x140073ba6  mov     rcx, [rbx+200h]
0x140073bad  mov     rax, [rsp+68h+arg_18]
0x140073bb5  mov     [rax+58h], rcx
0x140073bb9  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140073bc0  mov     rcx, [rsp+68h+arg_18]
0x140073bc8  mov     [rcx+60h], rax
0x140073bcc  mov     ecx, [rbx+17Ch]
0x140073bd2  mov     rax, [rsp+68h+arg_18]
0x140073bda  mov     [rax+10h], ecx
0x140073bdd  mov     rcx, [rbx+280h]
0x140073be4  mov     rax, [rcx]
0x140073be7  mov     rax, [rax+150h]
0x140073bee  lea     rdx, [rsp+68h+arg_18]
0x140073bf6  call    _guard_dispatch_icall
0x140073bfb  mov     rcx, rbx; this
0x140073bfe  call    ?IsLogSecure@CClfsLogFcbVirtual@@QEBAEXZ; CClfsLogFcbVirtual::IsLogSecure(void)
0x140073c03  test    al, al
0x140073c05  jz      short loc_140073C5C
0x140073c07  mov     rcx, [rbx+280h]
0x140073c0e  mov     rax, [rcx]
0x140073c11  mov     rax, [rax+190h]
0x140073c18  mov     [rsp+68h+var_38], 1
0x140073c1d  mov     dl, [rsp+68h+arg_48]
0x140073c24  mov     [rsp+68h+var_40], dl
0x140073c28  mov     r9, [rsp+68h+arg_40]
0x140073c30  mov     qword ptr [rsp+68h+Update], r9
0x140073c35  mov     r9d, [r9+14h]
0x140073c39  mov     r8d, [rsp+68h+DesiredAccess]
0x140073c41  mov     rdx, [rsp+68h+arg_20]
0x140073c49  call    _guard_dispatch_icall
0x140073c4e  mov     edi, eax
0x140073c50  mov     [rsp+68h+var_24], eax
0x140073c54  test    eax, eax
0x140073c56  js      loc_140073D7A
0x140073c5c  mov     rcx, [rbx+280h]
0x140073c63  mov     rax, [rcx]
0x140073c66  mov     rax, [rax+38h]
0x140073c6a  call    _guard_dispatch_icall
0x140073c6f  test    al, al
0x140073c71  jz      short loc_140073C8A
0x140073c73  test    [rsp+68h+DesiredAccess], 10006h
0x140073c7e  jz      short loc_140073C8A
0x140073c80  mov     edi, 0C0000022h
0x140073c85  jmp     loc_140073AF6
0x140073c8a  mov     rax, [rbx]
0x140073c8d  mov     rax, [rax+158h]
0x140073c94  mov     rcx, rbx
0x140073c97  call    _guard_dispatch_icall
0x140073c9c  test    al, al
0x140073c9e  jz      short loc_140073CDB
0x140073ca0  mov     eax, [rbx+16Ch]
0x140073ca6  test    al, 6
0x140073ca8  jz      short loc_140073CDB
0x140073caa  lea     r9, [rbx+150h]; ShareAccess
0x140073cb1  mov     [rsp+68h+Update], 1; Update
0x140073cb6  mov     r8, rsi; FileObject
0x140073cb9  mov     edx, [rsp+68h+DesiredShareAccess]; DesiredShareAccess
0x140073cc0  mov     ecx, [rsp+68h+DesiredAccess]; DesiredAccess
0x140073cc7  call    cs:__imp_IoCheckShareAccess
0x140073cce  nop     dword ptr [rax+rax+00h]
0x140073cd3  mov     edi, eax
0x140073cd5  mov     [rsp+68h+var_24], eax
0x140073cd9  jmp     short loc_140073D05
0x140073cdb  lea     r9, [rbx+150h]; ShareAccess
0x140073ce2  mov     r8, rsi; FileObject
0x140073ce5  mov     edx, [rsp+68h+DesiredShareAccess]; DesiredShareAccess
0x140073cec  mov     ecx, [rsp+68h+DesiredAccess]; DesiredAccess
0x140073cf3  call    cs:__imp_IoSetShareAccess
0x140073cfa  nop     dword ptr [rax+rax+00h]
0x140073cff  xor     edi, edi
0x140073d01  mov     [rsp+68h+var_24], edi
0x140073d05  test    edi, edi
0x140073d07  js      short loc_140073D7A
0x140073d09  mov     rcx, [rbx+280h]
0x140073d10  mov     rax, [rcx]
0x140073d13  mov     rax, [rax+38h]
0x140073d17  call    _guard_dispatch_icall
0x140073d1c  test    al, al
0x140073d1e  jnz     short loc_140073D40
0x140073d20  mov     rcx, [rbx+280h]
0x140073d27  mov     rax, [rcx]
0x140073d2a  mov     rax, [rax+88h]
0x140073d31  call    _guard_dispatch_icall
0x140073d36  mov     edi, eax
0x140073d38  mov     [rsp+68h+var_24], eax
0x140073d3c  test    eax, eax
0x140073d3e  js      short loc_140073D7A
0x140073d40  mov     dword ptr [rbx+16Ch], 2
0x140073d4a  lea     rdx, [rbx+190h]; struct _LIST_ENTRY *
0x140073d51  mov     rcx, [rsp+68h+arg_58]; this
0x140073d59  call    ?Link@CClfsLogCcb@@QEAAXPEAU_LIST_ENTRY@@@Z; CClfsLogCcb::Link(_LIST_ENTRY *)
0x140073d5e  mov     rcx, rbx; this
0x140073d61  call    ?AddHandleRef@CClfsLogFcbCommon@@QEAAKXZ; CClfsLogFcbCommon::AddHandleRef(void)
0x140073d66  mov     r8, [rsp+68h+arg_58]; struct CClfsLogCcb *
0x140073d6e  mov     rdx, rsi; struct _FILE_OBJECT *
0x140073d71  mov     rcx, rbx; this
0x140073d74  call    ?SetFileObject@CClfsLogFcbCommon@@QEAAXPEAU_FILE_OBJECT@@PEAVCClfsLogCcb@@@Z; CClfsLogFcbCommon::SetFileObject(_FILE_OBJECT *,CClfsLogCcb *)
0x140073d79  nop
0x140073d7a  test    r14b, r14b
0x140073d7d  jz      short loc_140073D87
0x140073d7f  mov     rcx, r15
0x140073d82  call    ClfsReleaseResourceLite
0x140073d87  cmp     [rsp+68h+arg_18], 0
0x140073d90  jz      short loc_140073DB0
0x140073d92  mov     rcx, [rbx+280h]
0x140073d99  mov     rax, [rcx]
0x140073d9c  mov     rax, [rax+150h]
0x140073da3  lea     rdx, [rsp+68h+arg_18]
0x140073dab  call    _guard_dispatch_icall
0x140073db0  mov     eax, edi
0x140073db2  lea     r11, [rsp+68h+var_18]
0x140073db7  mov     rbx, [r11+28h]
0x140073dbb  mov     rsi, [r11+30h]
0x140073dbf  mov     rsp, r11
0x140073dc2  pop     r15
0x140073dc4  pop     r14
0x140073dc6  pop     rdi
0x140073dc7  retn
0x14007c2a2  push    rbp
0x14007c2a4  sub     rsp, 40h
0x14007c2a8  mov     rbp, rdx
0x14007c2ab  cmp     byte ptr [rbp+40h], 0
0x14007c2af  jz      short loc_14007C2C5
0x14007c2b1  mov     rcx, [rbp+70h]
0x14007c2b5  add     rcx, 0C8h
0x14007c2bc  call    ClfsReleaseResourceLite
0x14007c2c1  mov     byte ptr [rbp+40h], 0
0x14007c2c5  cmp     qword ptr [rbp+88h], 0
0x14007c2cd  jz      short loc_14007C2F1
0x14007c2cf  mov     rax, [rbp+70h]
0x14007c2d3  mov     rcx, [rax+280h]
0x14007c2da  mov     rdx, [rcx]
0x14007c2dd  mov     rax, [rdx+150h]
0x14007c2e4  lea     rdx, [rbp+88h]
0x14007c2eb  call    _guard_dispatch_icall
0x14007c2f0  nop
0x14007c2f1  add     rsp, 40h
0x14007c2f5  pop     rbp
0x14007c2f6  retn
```
