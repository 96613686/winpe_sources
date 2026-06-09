# ModifyShare(ushort *,uchar,ushort *,ushort *,uchar *,uchar *,long *,long *,uchar *,ulong *,ulong *,ulong *,_LIST_ENTRY *,CNfsTaskContext *)

- ea: `0x18001eca0`
- end: `0x18001ee42`
- name: `?ModifyShare@@YAKPEAGE00PEAE1PEAJ21PEAK33PEAU_LIST_ENTRY@@PEAVCNfsTaskContext@@@Z`
- size: `418`
- prototype: `unsigned int __usercall@<eax>(wchar_t *String2@<rcx>, unsigned __int8@<dl>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int8 *, unsigned __int8 *, int *, int *, unsigned __int8 *, unsigned int *, unsigned int *, unsigned int *, struct _LIST_ENTRY *, struct CNfsTaskContext *)`
- caller_count: `5`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x18000b72c`
- `0x18000b9d8`
- `0x18000c034`
- `0x18000c328`
- `0x18000c520`

## callees

- `0x180006a54`
- `0x18001dcec`
- `0x18001e230`
- `0x18001e358`
- `0x18001e418`
- `0x18001eca0`
- `0x18001ee48`
- `0x180020d94`
- `0x18002115c`
- `0x1800219fc`
- `0x180037010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001ee28`
- `KERNEL32!HeapFree` at `0x18001ee28`
- `KERNEL32!GetProcessHeap` at `0x18001ee1a`
- `KERNEL32!GetProcessHeap` at `0x18001ee1a`

## pseudocode

```c
__int64 __fastcall ModifyShare(
        wchar_t *String2,
        unsigned __int8 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        int *a7,
        int *a8,
        unsigned __int8 *a9,
        unsigned int *a10,
        unsigned int *a11,
        unsigned int *a12,
        struct _LIST_ENTRY *a13,
        struct CNfsTaskContext *a14)
{
  unsigned __int16 *v15; // rdi
  unsigned int NfsShareList; // ebx
  unsigned int ShareRecord; // eax
  struct _NFS_EXPORT *v21; // rsi
  int v22; // eax
  struct _LIST_ENTRY *v23; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v26; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 *v27; // [rsp+58h] [rbp-28h] BYREF
  struct _NFS_EXPORT *v28; // [rsp+60h] [rbp-20h] BYREF
  struct _LIST_ENTRY v29; // [rsp+68h] [rbp-18h] BYREF

  v15 = 0;
  v29 = 0;
  v27 = 0;
  v26 = 0;
  NfsShareList = GetNfsShareList(&v29);
  if ( !NfsShareList )
  {
    v28 = 0;
    ShareRecord = FindShareRecord(String2, a2, a3, &v29, &v28);
    NfsShareList = ShareRecord;
    if ( ShareRecord == 1168 )
    {
      (*(void (__fastcall **)(struct CNfsTaskContext *, __int64, __int64, wchar_t *))(*(_QWORD *)a14 + 40LL))(
        a14,
        1168,
        3221229578LL,
        String2);
    }
    else if ( !ShareRecord )
    {
      v21 = v28;
      if ( !a4
        || (v22 = StringCchCopyW((unsigned __int16 *)v28 + 278, 0x106u, a4), (NfsShareList = NfsGetErrorFromHr(v22)) == 0) )
      {
        v23 = a13;
        if ( a13 )
          SortPermissionsList(a13, 0, (char *)v21 + 1092);
        else
          v23 = (struct _LIST_ENTRY *)((char *)v21 + 1640);
        NfsShareList = CreateSharePermissionString(v23, &v27, &v26);
        if ( NfsShareList )
        {
          v15 = v27;
        }
        else
        {
          UpdateShareProperties(
            (_DWORD)v21,
            (_DWORD)a5,
            (_DWORD)a6,
            (_DWORD)a7,
            (__int64)a8,
            (__int64)a9,
            (__int64)a10,
            (__int64)a11,
            (__int64)a12);
          v15 = v27;
          NfsShareList = ModifyShareOnServer(v21);
        }
      }
    }
    FreeNfsExportList(&v29);
    if ( v15 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v15);
    }
  }
  return NfsShareList;
}

```

## disassembly

```asm
0x18001eca0  push    rbp
0x18001eca2  push    rbx
0x18001eca3  push    rsi
0x18001eca4  push    rdi
0x18001eca5  push    r12
0x18001eca7  push    r14
0x18001eca9  push    r15
0x18001ecab  mov     rbp, rsp
0x18001ecae  sub     rsp, 80h
0x18001ecb5  mov     rsi, rcx
0x18001ecb8  xorps   xmm0, xmm0
0x18001ecbb  xor     edi, edi
0x18001ecbd  lea     rcx, [rbp+var_18]; struct _LIST_ENTRY *
0x18001ecc1  movups  xmmword ptr [rbp+var_18.Flink], xmm0
0x18001ecc5  mov     [rbp+var_28], rdi
0x18001ecc9  mov     r14, r9
0x18001eccc  mov     [rbp+var_30], edi
0x18001eccf  mov     r15, r8
0x18001ecd2  mov     r12b, dl
0x18001ecd5  call    ?GetNfsShareList@@YAKPEAU_LIST_ENTRY@@@Z; GetNfsShareList(_LIST_ENTRY *)
0x18001ecda  mov     ebx, eax
0x18001ecdc  test    eax, eax
0x18001ecde  jnz     loc_18001EE2E
0x18001ece4  lea     rax, [rbp+var_20]
0x18001ece8  mov     [rbp+var_20], rdi
0x18001ecec  lea     r9, [rbp+var_18]; struct _LIST_ENTRY *
0x18001ecf0  mov     [rsp+80h+var_60], rax; struct _NFS_EXPORT **
0x18001ecf5  mov     r8, r15; unsigned __int16 *
0x18001ecf8  mov     dl, r12b; unsigned __int8
0x18001ecfb  mov     rcx, rsi; String2
0x18001ecfe  call    ?FindShareRecord@@YAKPEAGE0PEAU_LIST_ENTRY@@PEAPEAU_NFS_EXPORT@@@Z; FindShareRecord(ushort *,uchar,ushort *,_LIST_ENTRY *,_NFS_EXPORT * *)
0x18001ed03  mov     edx, 490h
0x18001ed08  mov     ebx, eax
0x18001ed0a  cmp     eax, edx
0x18001ed0c  jnz     short loc_18001ED2F
0x18001ed0e  mov     rcx, [rbp+arg_68]
0x18001ed15  mov     r9, rsi
0x18001ed18  mov     r8d, 0C000100Ah
0x18001ed1e  mov     rax, [rcx]
0x18001ed21  mov     rax, [rax+28h]
0x18001ed25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed2a  jmp     loc_18001EE0C
0x18001ed2f  test    eax, eax
0x18001ed31  jnz     loc_18001EE0C
0x18001ed37  mov     rsi, [rbp+var_20]
0x18001ed3b  test    r14, r14
0x18001ed3e  jz      short loc_18001ED65
0x18001ed40  lea     rcx, [rsi+22Ch]; unsigned __int16 *
0x18001ed47  mov     r8, r14; unsigned __int16 *
0x18001ed4a  mov     edx, 106h; unsigned __int64
0x18001ed4f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ed54  mov     ecx, eax; int
0x18001ed56  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x18001ed5b  mov     ebx, eax
0x18001ed5d  test    eax, eax
0x18001ed5f  jnz     loc_18001EE0C
0x18001ed65  mov     rbx, [rbp+arg_60]
0x18001ed6c  test    rbx, rbx
0x18001ed6f  jz      short loc_18001ED84
0x18001ed71  lea     r8, [rsi+444h]
0x18001ed78  xor     edx, edx
0x18001ed7a  mov     rcx, rbx
0x18001ed7d  call    SortPermissionsList
0x18001ed82  jmp     short loc_18001ED8B
0x18001ed84  lea     rbx, [rsi+668h]
0x18001ed8b  lea     r8, [rbp+var_30]; unsigned int *
0x18001ed8f  mov     rcx, rbx; struct _LIST_ENTRY *
0x18001ed92  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18001ed96  call    ?CreateSharePermissionString@@YAKPEAU_LIST_ENTRY@@PEAPEAGPEAK@Z; CreateSharePermissionString(_LIST_ENTRY *,ushort * *,ulong *)
0x18001ed9b  mov     ebx, eax
0x18001ed9d  test    eax, eax
0x18001ed9f  jnz     short loc_18001EE08
0x18001eda1  mov     rax, [rbp+arg_58]
0x18001eda8  mov     rcx, rsi
0x18001edab  mov     r9, [rbp+arg_30]
0x18001edaf  mov     r8, [rbp+arg_28]
0x18001edb3  mov     rdx, [rbp+arg_20]
0x18001edb7  mov     [rsp+80h+var_40], rax
0x18001edbc  mov     rax, [rbp+arg_50]
0x18001edc3  mov     [rsp+80h+var_48], rax
0x18001edc8  mov     rax, [rbp+arg_48]
0x18001edcf  mov     [rsp+80h+var_50], rax
0x18001edd4  mov     rax, [rbp+arg_40]
0x18001eddb  mov     [rsp+80h+var_58], rax
0x18001ede0  mov     rax, [rbp+arg_38]
0x18001ede4  mov     [rsp+80h+var_60], rax
0x18001ede9  call    UpdateShareProperties
0x18001edee  mov     rdi, [rbp+var_28]
0x18001edf2  mov     rcx, rsi; struct _NFS_EXPORT *
0x18001edf5  mov     r8, [rbp+arg_68]
0x18001edfc  mov     rdx, rdi
0x18001edff  call    ModifyShareOnServer
0x18001ee04  mov     ebx, eax
0x18001ee06  jmp     short loc_18001EE0C
0x18001ee08  mov     rdi, [rbp+var_28]
0x18001ee0c  lea     rcx, [rbp+var_18]; struct _LIST_ENTRY *
0x18001ee10  call    ?FreeNfsExportList@@YAXPEAU_LIST_ENTRY@@@Z; FreeNfsExportList(_LIST_ENTRY *)
0x18001ee15  test    rdi, rdi
0x18001ee18  jz      short loc_18001EE2E
0x18001ee1a  call    cs:__imp_GetProcessHeap
0x18001ee20  mov     r8, rdi; lpMem
0x18001ee23  xor     edx, edx; dwFlags
0x18001ee25  mov     rcx, rax; hHeap
0x18001ee28  call    cs:__imp_HeapFree
0x18001ee2e  mov     eax, ebx
0x18001ee30  add     rsp, 80h
0x18001ee37  pop     r15
0x18001ee39  pop     r14
0x18001ee3b  pop     r12
0x18001ee3d  pop     rdi
0x18001ee3e  pop     rsi
0x18001ee3f  pop     rbx
0x18001ee40  pop     rbp
0x18001ee41  retn
```
