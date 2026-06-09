# VolumePropPage::CreateInstance(IUnknown *,CVolumeID const &,VolumePropPage * *)

- ea: `0x180018a68`
- end: `0x180018b57`
- name: `?CreateInstance@VolumePropPage@@SAJPEAUIUnknown@@AEBVCVolumeID@@PEAPEAV1@@Z`
- size: `239`
- prototype: `__int64 __fastcall(struct IUnknown *, const struct CVolumeID *, struct VolumePropPage **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180016120`

## callees

- `0x180006ec0`
- `0x180015f98`
- `0x180016a54`
- `0x180018a68`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VolumePropPage::CreateInstance(struct IUnknown *a1, const struct CVolumeID *a2, struct _GUID *a3)
{
  int v6; // edi
  DiskQuotaPropPage *v7; // rax
  DiskQuotaPropPage *v8; // rbx
  void *v10; // [rsp+60h] [rbp+18h] BYREF
  DiskQuotaPropPage *v11; // [rsp+68h] [rbp+20h]

  *(_QWORD *)&a3->Data1 = 0;
  v10 = 0;
  v6 = CreateQuotaController(a2, (__int64)a2, a3, &v10);
  if ( v6 >= 0 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = 0;
    v6 = -2147024882;
    v7 = (DiskQuotaPropPage *)operator new(0xB8u);
    v8 = v7;
    v11 = v7;
    if ( v7 )
    {
      DiskQuotaPropPage::DiskQuotaPropPage(v7, 0x6Bu, a1, a2);
      *(_QWORD *)v8 = &VolumePropPage::`vftable';
      *((_QWORD *)v8 + 12) = 0;
      *((_QWORD *)v8 + 13) = 0;
      *((_QWORD *)v8 + 14) = 0;
      *((_QWORD *)v8 + 15) = -1;
      *((_QWORD *)v8 + 16) = 0;
      *((_DWORD *)v8 + 34) = 0;
      *((_DWORD *)v8 + 35) = -1;
      *((_QWORD *)v8 + 19) = 0;
      *((_QWORD *)v8 + 20) = 0;
      *((_QWORD *)v8 + 21) = 0;
      *((_DWORD *)v8 + 44) = -1;
    }
    else
    {
      v8 = 0;
    }
    if ( v8 )
    {
      *(_QWORD *)&a3->Data1 = v8;
      return 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180018a68  mov     [rsp+arg_0], rbx
0x180018a6d  push    rbp
0x180018a6e  push    rsi
0x180018a6f  push    rdi
0x180018a70  push    r14
0x180018a72  push    r15
0x180018a74  sub     rsp, 20h
0x180018a78  mov     rsi, r8
0x180018a7b  mov     rbp, rdx
0x180018a7e  mov     r14, rcx
0x180018a81  xor     r15d, r15d
0x180018a84  mov     [r8], r15
0x180018a87  mov     [rsp+48h+arg_10], r15
0x180018a8c  lea     r9, [rsp+48h+arg_10]; void **
0x180018a91  mov     rcx, rdx; struct CVolumeID *
0x180018a94  call    ?CreateQuotaController@@YAJAEBVCVolumeID@@HAEBU_GUID@@PEAPEAX@Z; CreateQuotaController(CVolumeID const &,int,_GUID const &,void * *)
0x180018a99  mov     edi, eax
0x180018a9b  test    eax, eax
0x180018a9d  js      loc_180018B44
0x180018aa3  mov     rcx, [rsp+48h+arg_10]
0x180018aa8  mov     rax, [rcx]
0x180018aab  mov     rax, [rax+10h]
0x180018aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ab4  mov     [rsp+48h+arg_10], r15
0x180018ab9  mov     edi, 8007000Eh
0x180018abe  mov     ecx, 0B8h; uBytes
0x180018ac3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018ac8  mov     rbx, rax
0x180018acb  mov     [rsp+48h+arg_18], rax
0x180018ad0  test    rax, rax
0x180018ad3  jz      short loc_180018B36
0x180018ad5  mov     r9, rbp; struct CVolumeID *
0x180018ad8  mov     r8, r14; struct IUnknown *
0x180018adb  lea     edx, [r15+6Bh]; unsigned int
0x180018adf  mov     rcx, rax; this
0x180018ae2  call    ??0DiskQuotaPropPage@@QEAA@KPEAUIUnknown@@AEBVCVolumeID@@@Z; DiskQuotaPropPage::DiskQuotaPropPage(ulong,IUnknown *,CVolumeID const &)
0x180018ae7  lea     rax, ??_7VolumePropPage@@6B@; const VolumePropPage::`vftable'
0x180018aee  mov     [rbx], rax
0x180018af1  mov     [rbx+60h], r15
0x180018af5  mov     [rbx+68h], r15
0x180018af9  mov     [rbx+70h], r15
0x180018afd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018b01  mov     [rbx+78h], rax
0x180018b05  mov     [rbx+80h], r15
0x180018b0c  mov     [rbx+88h], r15d
0x180018b13  mov     [rbx+8Ch], eax
0x180018b19  mov     [rbx+98h], r15
0x180018b20  mov     [rbx+0A0h], r15
0x180018b27  mov     [rbx+0A8h], r15
0x180018b2e  mov     [rbx+0B0h], eax
0x180018b34  jmp     short loc_180018B39
0x180018b36  mov     rbx, r15
0x180018b39  test    rbx, rbx
0x180018b3c  jz      short loc_180018B44
0x180018b3e  mov     [rsi], rbx
0x180018b41  mov     edi, r15d
0x180018b44  mov     eax, edi
0x180018b46  mov     rbx, [rsp+48h+arg_0]
0x180018b4b  add     rsp, 20h
0x180018b4f  pop     r15
0x180018b51  pop     r14
0x180018b53  pop     rdi
0x180018b54  pop     rsi
0x180018b55  pop     rbp
0x180018b56  retn
```
