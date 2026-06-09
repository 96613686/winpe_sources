# CClfsLogFcbVirtual::Cleanup(_FILE_OBJECT *)

- ea: `0x1400689f0`
- end: `0x140068d22`
- name: `?Cleanup@CClfsLogFcbVirtual@@UEAAJPEAU_FILE_OBJECT@@@Z`
- size: `818`
- prototype: `__int64 __fastcall(CClfsLogFcbVirtual *__hidden this, PFILE_OBJECT FileObject)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005840`
- `0x140017f20`
- `0x140067428`
- `0x1400689f0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140068a8a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140068a8a`
- `ntoskrnl!KeBugCheckEx` at `0x140068a72`
- `ntoskrnl!KeBugCheckEx` at `0x140068a72`
- `ntoskrnl!IoRemoveShareAccess` at `0x140068c50`
- `ntoskrnl!IoRemoveShareAccess` at `0x140068c50`
- `ntoskrnl!CcPurgeCacheSection` at `0x140068c87`
- `ntoskrnl!CcPurgeCacheSection` at `0x140068c87`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbVirtual::Cleanup(CClfsLogFcbVirtual *this, PFILE_OBJECT FileObject)
{
  CLFS_LSN v4; // rbx
  unsigned int v5; // r14d
  __int64 v6; // rdx
  __int64 v7; // r8
  BOOLEAN v8; // r12
  _QWORD *v9; // r15
  __int64 v10; // rcx
  SECTION_OBJECT_POINTERS *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  ULONG_PTR BugCheckParameter3; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v16[72]; // [rsp+40h] [rbp-48h] BYREF
  int v17; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v18; // [rsp+A8h] [rbp+20h] BYREF

  v4 = CLFS_LSN_INVALID;
  BugCheckParameter3 = 0;
  v18 = 0;
  v17 = 0;
  v5 = (*(__int64 (__fastcall **)(CClfsLogFcbVirtual *, ULONG_PTR *, _QWORD, __int64, int *))(*(_QWORD *)this + 192LL))(
         this,
         &BugCheckParameter3,
         0,
         2,
         &v17);
  if ( v5 == 259 )
    KeBugCheckEx(0xC1F5u, 0x22u, 0x103u, HIDWORD(BugCheckParameter3), (unsigned int)BugCheckParameter3);
  v8 = ExAcquireResourceExclusiveLite((PERESOURCE)((char *)this + 200), 1u);
  v9 = (_QWORD *)((char *)this + 488);
  if ( this == (CClfsLogFcbVirtual *)-488LL || CLFS_LSN_INVALID.ullOffset != *v9 )
  {
    LOBYTE(v7) = *((_BYTE *)this + 616);
    v4 = *(CLFS_LSN *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))(**((_QWORD **)this + 80) + 288LL))(
                        *((_QWORD *)this + 80),
                        v16,
                        v7);
  }
  if ( (FileObject->Flags & 2) == 0 )
    (*(void (__fastcall **)(_QWORD, PFILE_OBJECT))(**((_QWORD **)this + 80) + 280LL))(
      *((_QWORD *)this + 80),
      FileObject);
  if ( FileObject->WriteAccess )
  {
    LOBYTE(v6) = *((_BYTE *)this + 616);
    (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)this + 80) + 328LL))(
      *((_QWORD *)this + 80),
      v6,
      &v18);
    v10 = v18;
    if ( !v18 )
    {
      v5 = -1072037875;
      goto LABEL_16;
    }
    *(_WORD *)(v18 + 10) = *((_WORD *)this + 188);
    *(_QWORD *)(v18 + 32) = *((_QWORD *)this + 54);
    *(_QWORD *)(v18 + 40) = *((_QWORD *)this + 55);
    *(_QWORD *)(v18 + 48) = *((_QWORD *)this + 56);
    *(_QWORD *)(v18 + 24) = *((_QWORD *)this + 59);
    *(_QWORD *)(v18 + 64) = *((_QWORD *)this + 62);
    *(CLFS_LSN *)(v18 + 56) = CLFS_LSN_INVALID;
    *(_QWORD *)(v18 + 72) = *v9;
    *(_QWORD *)(v18 + 80) = *((_QWORD *)this + 63);
    *(_QWORD *)(v18 + 88) = *((_QWORD *)this + 64);
    *(CLFS_LSN *)(v18 + 96) = v4;
    *(_DWORD *)(v18 + 16) = *((_DWORD *)this + 95);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 80) + 136LL))(*((_QWORD *)this + 80));
    (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 80) + 336LL))(*((_QWORD *)this + 80), &v18);
  }
  IoRemoveShareAccess(FileObject, (PSHARE_ACCESS)this + 12);
  FileObject->Flags |= 0x4000u;
  if ( !CClfsLogFcbCommon::ReleaseHandleRef(this) )
  {
    v11 = (SECTION_OBJECT_POINTERS *)(*(__int64 (__fastcall **)(CClfsLogFcbVirtual *))(*(_QWORD *)this + 48LL))(this);
    CcPurgeCacheSection(v11, 0, 0, 0);
    if ( (*((_DWORD *)this + 91) & 0x10) != 0 )
    {
      LOBYTE(v13) = 1;
      LOBYTE(v12) = *((_BYTE *)this + 616);
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 80) + 312LL))(
        *((_QWORD *)this + 80),
        v12,
        v13);
    }
  }
  (*(void (__fastcall **)(CClfsLogFcbVirtual *, PFILE_OBJECT))(*(_QWORD *)this + 8LL))(this, FileObject);
  v10 = v18;
LABEL_16:
  if ( v8 )
  {
    ClfsReleaseResourceLite((char *)this + 200);
    v10 = v18;
  }
  if ( v10 )
    (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 80) + 336LL))(*((_QWORD *)this + 80), &v18);
  return v5;
}

```

## disassembly

```asm
0x1400689f0  mov     r11, rsp
0x1400689f3  mov     [r11+8], rcx
0x1400689f7  push    rbx
0x1400689f8  push    rsi
0x1400689f9  push    rdi
0x1400689fa  push    r12
0x1400689fc  push    r13
0x1400689fe  push    r14
0x140068a00  push    r15
0x140068a02  sub     rsp, 50h
0x140068a06  mov     rsi, rdx
0x140068a09  mov     rdi, rcx
0x140068a0c  mov     rbx, qword ptr cs:CLFS_LSN_INVALID
0x140068a13  xor     eax, eax
0x140068a15  mov     [r11-50h], rax
0x140068a19  mov     [r11+20h], rax
0x140068a1d  mov     [r11+18h], eax
0x140068a21  mov     [rsp+88h+var_58], al
0x140068a25  mov     rax, [rcx]
0x140068a28  mov     rax, [rax+0C0h]
0x140068a2f  lea     rcx, [r11+18h]
0x140068a33  mov     [r11-68h], rcx
0x140068a37  mov     r9d, 2
0x140068a3d  xor     r8d, r8d
0x140068a40  lea     rdx, [r11-50h]
0x140068a44  mov     rcx, rdi
0x140068a47  call    _guard_dispatch_icall
0x140068a4c  mov     r14d, eax
0x140068a4f  mov     r8d, 103h; BugCheckParameter2
0x140068a55  cmp     eax, r8d
0x140068a58  jnz     short loc_140068A7E
0x140068a5a  mov     eax, dword ptr [rsp+88h+BugCheckParameter3]
0x140068a5e  mov     r9d, dword ptr [rsp+88h+BugCheckParameter3+4]; BugCheckParameter3
0x140068a63  mov     [rsp+88h+BugCheckParameter4], rax; BugCheckParameter4
0x140068a68  mov     edx, 22h ; '"'; BugCheckParameter1
0x140068a6d  mov     ecx, 0C1F5h; BugCheckCode
0x140068a72  call    cs:__imp_KeBugCheckEx
0x140068a7e  lea     r13, [rdi+0C8h]
0x140068a85  mov     dl, 1; Wait
0x140068a87  mov     rcx, r13; Resource
0x140068a8a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140068a91  nop     dword ptr [rax+rax+00h]
0x140068a96  mov     r12b, al
0x140068a99  mov     [rsp+88h+var_58], al
0x140068a9d  lea     r15, [rdi+1E8h]
0x140068aa4  test    r15, r15
0x140068aa7  jz      short loc_140068AB5
0x140068aa9  mov     rcx, qword ptr cs:CLFS_LSN_INVALID
0x140068ab0  cmp     rcx, [r15]
0x140068ab3  jz      short loc_140068ADA
0x140068ab5  mov     rcx, [rdi+280h]
0x140068abc  mov     rax, [rcx]
0x140068abf  mov     rax, [rax+120h]
0x140068ac6  mov     r8b, [rdi+268h]
0x140068acd  lea     rdx, [rsp+88h+var_48]
0x140068ad2  call    _guard_dispatch_icall
0x140068ad7  mov     rbx, [rax]
0x140068ada  mov     eax, [rsi+50h]
0x140068add  test    al, 2
0x140068adf  jnz     short loc_140068AFA
0x140068ae1  mov     rcx, [rdi+280h]
0x140068ae8  mov     rax, [rcx]
0x140068aeb  mov     rax, [rax+118h]
0x140068af2  mov     rdx, rsi
0x140068af5  call    _guard_dispatch_icall
0x140068afa  cmp     byte ptr [rsi+4Bh], 0
0x140068afe  jz      loc_140068C46
0x140068b04  mov     rcx, [rdi+280h]
0x140068b0b  mov     rax, [rcx]
0x140068b0e  mov     rax, [rax+148h]
0x140068b15  lea     r8, [rsp+88h+arg_18]
0x140068b1d  mov     dl, [rdi+268h]
0x140068b23  call    _guard_dispatch_icall
0x140068b28  mov     rcx, [rsp+88h+arg_18]
0x140068b30  test    rcx, rcx
0x140068b33  jnz     short loc_140068B40
0x140068b35  mov     r14d, 0C01A000Dh
0x140068b3b  jmp     loc_140068CD6
0x140068b40  movzx   eax, word ptr [rdi+178h]
0x140068b47  mov     [rcx+0Ah], ax
0x140068b4b  mov     rcx, [rdi+1B0h]
0x140068b52  mov     rax, [rsp+88h+arg_18]
0x140068b5a  mov     [rax+20h], rcx
0x140068b5e  mov     rcx, [rdi+1B8h]
0x140068b65  mov     rax, [rsp+88h+arg_18]
0x140068b6d  mov     [rax+28h], rcx
0x140068b71  mov     rcx, [rdi+1C0h]
0x140068b78  mov     rax, [rsp+88h+arg_18]
0x140068b80  mov     [rax+30h], rcx
0x140068b84  mov     rcx, [rdi+1D8h]
0x140068b8b  mov     rax, [rsp+88h+arg_18]
0x140068b93  mov     [rax+18h], rcx
0x140068b97  mov     rcx, [rdi+1F0h]
0x140068b9e  mov     rax, [rsp+88h+arg_18]
0x140068ba6  mov     [rax+40h], rcx
0x140068baa  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140068bb1  mov     rcx, [rsp+88h+arg_18]
0x140068bb9  mov     [rcx+38h], rax
0x140068bbd  mov     rcx, [r15]
0x140068bc0  mov     rax, [rsp+88h+arg_18]
0x140068bc8  mov     [rax+48h], rcx
0x140068bcc  mov     rcx, [rdi+1F8h]
0x140068bd3  mov     rax, [rsp+88h+arg_18]
0x140068bdb  mov     [rax+50h], rcx
0x140068bdf  mov     rcx, [rdi+200h]
0x140068be6  mov     rax, [rsp+88h+arg_18]
0x140068bee  mov     [rax+58h], rcx
0x140068bf2  mov     rax, [rsp+88h+arg_18]
0x140068bfa  mov     [rax+60h], rbx
0x140068bfe  mov     ecx, [rdi+17Ch]
0x140068c04  mov     rax, [rsp+88h+arg_18]
0x140068c0c  mov     [rax+10h], ecx
0x140068c0f  mov     rcx, [rdi+280h]
0x140068c16  mov     rax, [rcx]
0x140068c19  mov     rax, [rax+88h]
0x140068c20  call    _guard_dispatch_icall
0x140068c25  mov     r14d, eax
0x140068c28  mov     rcx, [rdi+280h]
0x140068c2f  mov     rax, [rcx]
0x140068c32  mov     rax, [rax+150h]
0x140068c39  lea     rdx, [rsp+88h+arg_18]
0x140068c41  call    _guard_dispatch_icall
0x140068c46  lea     rdx, [rdi+150h]; ShareAccess
0x140068c4d  mov     rcx, rsi; FileObject
0x140068c50  call    cs:__imp_IoRemoveShareAccess
0x140068c57  nop     dword ptr [rax+rax+00h]
0x140068c5c  bts     dword ptr [rsi+50h], 0Eh
0x140068c61  mov     rcx, rdi; this
0x140068c64  call    ?ReleaseHandleRef@CClfsLogFcbCommon@@QEAAKXZ; CClfsLogFcbCommon::ReleaseHandleRef(void)
0x140068c69  test    eax, eax
0x140068c6b  jnz     short loc_140068CBC
0x140068c6d  mov     rax, [rdi]
0x140068c70  mov     rax, [rax+30h]
0x140068c74  mov     rcx, rdi
0x140068c77  call    _guard_dispatch_icall
0x140068c7c  mov     rcx, rax; SectionObjectPointer
0x140068c7f  xor     r9d, r9d; Flags
0x140068c82  xor     r8d, r8d; Length
0x140068c85  xor     edx, edx; FileOffset
0x140068c87  call    cs:__imp_CcPurgeCacheSection
0x140068c8e  nop     dword ptr [rax+rax+00h]
0x140068c93  mov     eax, [rdi+16Ch]
0x140068c99  test    al, 10h
0x140068c9b  jz      short loc_140068CBC
0x140068c9d  mov     rcx, [rdi+280h]
0x140068ca4  mov     rax, [rcx]
0x140068ca7  mov     rax, [rax+138h]
0x140068cae  mov     r8b, 1
0x140068cb1  mov     dl, [rdi+268h]
0x140068cb7  call    _guard_dispatch_icall
0x140068cbc  mov     rax, [rdi]
0x140068cbf  mov     rax, [rax+8]
0x140068cc3  mov     rdx, rsi
0x140068cc6  mov     rcx, rdi
0x140068cc9  call    _guard_dispatch_icall
0x140068cce  mov     rcx, [rsp+88h+arg_18]
0x140068cd6  test    r12b, r12b
0x140068cd9  jz      short loc_140068CEB
0x140068cdb  mov     rcx, r13
0x140068cde  call    ClfsReleaseResourceLite
0x140068ce3  mov     rcx, [rsp+88h+arg_18]
0x140068ceb  test    rcx, rcx
0x140068cee  jz      short loc_140068D0E
0x140068cf0  mov     rcx, [rdi+280h]
0x140068cf7  mov     rax, [rcx]
0x140068cfa  mov     rax, [rax+150h]
0x140068d01  lea     rdx, [rsp+88h+arg_18]
0x140068d09  call    _guard_dispatch_icall
0x140068d0e  mov     eax, r14d
0x140068d11  add     rsp, 50h
0x140068d15  pop     r15
0x140068d17  pop     r14
0x140068d19  pop     r13
0x140068d1b  pop     r12
0x140068d1d  pop     rdi
0x140068d1e  pop     rsi
0x140068d1f  pop     rbx
0x140068d20  retn
0x14007b040  push    rbp
0x14007b042  sub     rsp, 30h
0x14007b046  mov     rbp, rdx
0x14007b049  cmp     byte ptr [rbp+30h], 0
0x14007b04d  jz      short loc_14007B063
0x14007b04f  mov     rcx, [rbp+90h]
0x14007b056  add     rcx, 0C8h
0x14007b05d  call    ClfsReleaseResourceLite
0x14007b062  nop
0x14007b063  cmp     qword ptr [rbp+0A8h], 0
0x14007b06b  jz      short loc_14007B092
0x14007b06d  mov     rax, [rbp+90h]
0x14007b074  mov     rcx, [rax+280h]
0x14007b07b  mov     rdx, [rcx]
0x14007b07e  mov     rax, [rdx+150h]
0x14007b085  lea     rdx, [rbp+0A8h]
0x14007b08c  call    _guard_dispatch_icall
0x14007b091  nop
0x14007b092  add     rsp, 30h
0x14007b096  pop     rbp
0x14007b097  retn
```
