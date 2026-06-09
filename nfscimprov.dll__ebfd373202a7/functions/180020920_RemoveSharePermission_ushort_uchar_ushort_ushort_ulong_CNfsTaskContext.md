# RemoveSharePermission(ushort *,uchar,ushort *,ushort *,ulong,CNfsTaskContext *)

- ea: `0x180020920`
- end: `0x180020b5e`
- name: `?RemoveSharePermission@@YAKPEAGE00KPEAVCNfsTaskContext@@@Z`
- size: `574`
- prototype: `unsigned int __usercall@<eax>(wchar_t *String2@<rcx>, unsigned __int8@<dl>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned int, struct CNfsTaskContext *)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x18000cfec`
- `0x18000d18c`

## callees

- `0x18001cda0`
- `0x18001dcec`
- `0x18001e230`
- `0x18001e358`
- `0x18001e3c0`
- `0x18001e418`
- `0x18001ee48`
- `0x180020920`
- `0x180020d94`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180020a31`
- `msvcrt!_wcsicmp` at `0x180020a31`
- `msvcrt!free` at `0x180020a6e`
- `msvcrt!free` at `0x180020a6e`
- `KERNEL32!HeapFree` at `0x180020b33`
- `KERNEL32!HeapFree` at `0x180020b33`
- `KERNEL32!GetProcessHeap` at `0x180020b25`
- `KERNEL32!GetProcessHeap` at `0x180020b25`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RemoveSharePermission(
        wchar_t *String2,
        unsigned __int8 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        struct CNfsTaskContext *a6)
{
  unsigned __int16 *v9; // rdi
  int v10; // r15d
  unsigned int NfsShareList; // ebx
  unsigned int ShareRecord; // eax
  wchar_t *v13; // r9
  __int64 v14; // r8
  struct _NFS_EXPORT *v15; // rsi
  char *v16; // r12
  char *v17; // r13
  char *v18; // rbx
  const wchar_t **v19; // rax
  __int64 v20; // rax
  char **v21; // rdx
  HANDLE ProcessHeap; // rax
  char v24; // [rsp+30h] [rbp-D0h]
  unsigned int v25; // [rsp+34h] [rbp-CCh]
  int v26; // [rsp+34h] [rbp-CCh]
  struct _NFS_EXPORT *v27; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v28; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v29; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *String2a; // [rsp+50h] [rbp-B0h]
  struct _LIST_ENTRY v31; // [rsp+58h] [rbp-A8h] BYREF
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  char v33; // [rsp+78h] [rbp-88h] BYREF

  String2a = a4;
  v25 = 0;
  v31 = 0;
  v27 = 0;
  v9 = 0;
  v29 = 0;
  v28 = 0;
  v10 = 0;
  NfsShareList = GetNfsShareList(&v31);
  if ( NfsShareList )
    goto LABEL_21;
  ShareRecord = FindShareRecord(String2, a2, a3, &v31, &v27);
  NfsShareList = ShareRecord;
  if ( ShareRecord != 1168 )
  {
    v10 = 1;
    if ( !ShareRecord )
    {
      v15 = v27;
      if ( *((_DWORD *)v27 + 273) )
      {
        v16 = (char *)v27 + 1640;
        v17 = (char *)*((_QWORD *)v27 + 205);
        while ( v17 != v16 )
        {
          v18 = v17;
          v27 = (struct _NFS_EXPORT *)(v17 - 96);
          v17 = *(char **)v17;
          v19 = (const wchar_t **)ATL::CA2WEX<128>::CA2WEX<128>(&Block, *((_QWORD *)v27 + 1));
          v26 = v25 | 1;
          if ( _wcsicmp(*v19, String2a) || (v24 = 1, a5 != *(_DWORD *)v27) )
            v24 = 0;
          v25 = v26 & 0xFFFFFFFE;
          if ( Block != &v33 )
            free(Block);
          if ( v24 )
          {
            v20 = *(_QWORD *)v18;
            if ( *(char **)(*(_QWORD *)v18 + 8LL) != v18 || (v21 = (char **)*((_QWORD *)v18 + 1), *v21 != v18) )
              __fastfail(3u);
            *v21 = (char *)v20;
            *(_QWORD *)(v20 + 8) = v21;
            --*((_DWORD *)v15 + 273);
            FreeNfsPermissionEntry(v27);
            SortPermissionsList((char *)v15 + 1640, 0, 0);
            NfsShareList = CreateSharePermissionString((struct _LIST_ENTRY *)((char *)v15 + 1640), &v29, &v28);
            v9 = v29;
            if ( !NfsShareList )
              NfsShareList = ModifyShareOnServer(v15);
            goto LABEL_22;
          }
        }
      }
      NfsShareList = 1168;
      v13 = String2a;
      v14 = 3221229579LL;
      goto LABEL_20;
    }
LABEL_21:
    if ( !v10 )
      goto LABEL_23;
    goto LABEL_22;
  }
  v13 = String2;
  v14 = 3221229578LL;
LABEL_20:
  (*(void (__fastcall **)(struct CNfsTaskContext *, __int64, __int64, wchar_t *))(*(_QWORD *)a6 + 40LL))(
    a6,
    1168,
    v14,
    v13);
LABEL_22:
  FreeNfsExportList(&v31);
LABEL_23:
  if ( v9 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
  }
  return NfsShareList;
}

```

## disassembly

```asm
0x180020920  push    rbp
0x180020922  push    rbx
0x180020923  push    rsi
0x180020924  push    rdi
0x180020925  push    r12
0x180020927  push    r13
0x180020929  push    r14
0x18002092b  push    r15
0x18002092d  lea     rbp, [rsp-98h]
0x180020935  sub     rsp, 198h
0x18002093c  mov     rax, cs:__security_cookie
0x180020943  xor     rax, rsp
0x180020946  mov     [rbp+0D0h+var_50], rax
0x18002094d  mov     [rsp+1D0h+String2], r9
0x180020952  mov     r13, r8
0x180020955  mov     r12b, dl
0x180020958  mov     rsi, rcx
0x18002095b  mov     r14, [rbp+0D0h+arg_28]
0x180020962  xor     eax, eax
0x180020964  mov     [rsp+1D0h+var_19C], eax
0x180020968  xorps   xmm0, xmm0
0x18002096b  movups  xmmword ptr [rsp+1D0h+var_178.Flink], xmm0
0x180020970  mov     [rsp+1D0h+var_198], rax
0x180020975  xor     edi, edi
0x180020977  mov     [rsp+1D0h+var_188], rdi
0x18002097c  mov     [rsp+1D0h+var_190], eax
0x180020980  xor     r15d, r15d
0x180020983  lea     rcx, [rsp+1D0h+var_178]; struct _LIST_ENTRY *
0x180020988  call    ?GetNfsShareList@@YAKPEAU_LIST_ENTRY@@@Z; GetNfsShareList(_LIST_ENTRY *)
0x18002098d  mov     ebx, eax
0x18002098f  test    eax, eax
0x180020991  jnz     loc_180020B11
0x180020997  lea     rax, [rsp+1D0h+var_198]
0x18002099c  mov     [rsp+1D0h+var_1B0], rax; struct _NFS_EXPORT **
0x1800209a1  lea     r9, [rsp+1D0h+var_178]; struct _LIST_ENTRY *
0x1800209a6  mov     r8, r13; unsigned __int16 *
0x1800209a9  mov     dl, r12b; unsigned __int8
0x1800209ac  mov     rcx, rsi; String2
0x1800209af  call    ?FindShareRecord@@YAKPEAGE0PEAU_LIST_ENTRY@@PEAPEAU_NFS_EXPORT@@@Z; FindShareRecord(ushort *,uchar,ushort *,_LIST_ENTRY *,_NFS_EXPORT * *)
0x1800209b4  mov     ebx, eax
0x1800209b6  mov     ecx, 490h
0x1800209bb  cmp     eax, ecx
0x1800209bd  jnz     short loc_1800209CD
0x1800209bf  mov     r9, rsi
0x1800209c2  mov     r8d, 0C000100Ah
0x1800209c8  jmp     loc_180020AFE
0x1800209cd  mov     r15d, 1
0x1800209d3  test    eax, eax
0x1800209d5  jnz     loc_180020B11
0x1800209db  mov     rsi, [rsp+1D0h+var_198]
0x1800209e0  cmp     [rsi+444h], edi
0x1800209e6  jz      loc_180020AF1
0x1800209ec  lea     r12, [rsi+668h]
0x1800209f3  mov     r13, [r12]
0x1800209f7  cmp     r13, r12
0x1800209fa  jz      loc_180020AEC
0x180020a00  mov     rbx, r13
0x180020a03  lea     rax, [r13-60h]
0x180020a07  mov     [rsp+1D0h+var_198], rax
0x180020a0c  mov     r13, [r13+0]
0x180020a10  mov     rdx, [rax+8]
0x180020a14  lea     rcx, [rsp+1D0h+Block]
0x180020a19  call    ??0?$CA2WEX@$0IA@@ATL@@QEAA@PEBD@Z; ATL::CA2WEX<128>::CA2WEX<128>(char const *)
0x180020a1e  mov     ecx, [rsp+1D0h+var_19C]
0x180020a22  or      ecx, r15d
0x180020a25  mov     [rsp+1D0h+var_19C], ecx
0x180020a29  mov     rdx, [rsp+1D0h+String2]; String2
0x180020a2e  mov     rcx, [rax]; String1
0x180020a31  call    cs:__imp__wcsicmp
0x180020a37  test    eax, eax
0x180020a39  jnz     short loc_180020A4F
0x180020a3b  mov     rax, [rsp+1D0h+var_198]
0x180020a40  mov     ecx, [rbp+0D0h+arg_20]
0x180020a46  cmp     ecx, [rax]
0x180020a48  mov     [rsp+1D0h+var_1A0], r15b
0x180020a4d  jz      short loc_180020A54
0x180020a4f  mov     [rsp+1D0h+var_1A0], 0
0x180020a54  mov     eax, [rsp+1D0h+var_19C]
0x180020a58  and     eax, 0FFFFFFFEh
0x180020a5b  mov     [rsp+1D0h+var_19C], eax
0x180020a5f  mov     rcx, [rsp+1D0h+Block]; Block
0x180020a64  lea     rax, [rsp+1D0h+var_158]
0x180020a69  cmp     rcx, rax
0x180020a6c  jz      short loc_180020A75
0x180020a6e  call    cs:__imp_free
0x180020a74  nop
0x180020a75  cmp     [rsp+1D0h+var_1A0], 0
0x180020a7a  jz      loc_1800209F7
0x180020a80  mov     rax, [rbx]
0x180020a83  cmp     [rax+8], rbx
0x180020a87  jnz     short loc_180020AE5
0x180020a89  mov     rdx, [rbx+8]
0x180020a8d  cmp     [rdx], rbx
0x180020a90  jnz     short loc_180020AE5
0x180020a92  mov     [rdx], rax
0x180020a95  mov     [rax+8], rdx
0x180020a99  dec     dword ptr [rsi+444h]
0x180020a9f  mov     rcx, [rsp+1D0h+var_198]
0x180020aa4  call    FreeNfsPermissionEntry
0x180020aa9  xor     r8d, r8d
0x180020aac  xor     edx, edx
0x180020aae  mov     rcx, r12
0x180020ab1  call    SortPermissionsList
0x180020ab6  lea     r8, [rsp+1D0h+var_190]; unsigned int *
0x180020abb  lea     rdx, [rsp+1D0h+var_188]; unsigned __int16 **
0x180020ac0  mov     rcx, r12; struct _LIST_ENTRY *
0x180020ac3  call    ?CreateSharePermissionString@@YAKPEAU_LIST_ENTRY@@PEAPEAGPEAK@Z; CreateSharePermissionString(_LIST_ENTRY *,ushort * *,ulong *)
0x180020ac8  mov     ebx, eax
0x180020aca  mov     rdi, [rsp+1D0h+var_188]
0x180020acf  test    eax, eax
0x180020ad1  jnz     short loc_180020B16
0x180020ad3  mov     r8, r14
0x180020ad6  mov     rdx, rdi
0x180020ad9  mov     rcx, rsi; struct _NFS_EXPORT *
0x180020adc  call    ModifyShareOnServer
0x180020ae1  mov     ebx, eax
0x180020ae3  jmp     short loc_180020B16
0x180020ae5  mov     ecx, 3
0x180020aea  int     29h; Win8: RtlFailFast(ecx)
0x180020aec  mov     ecx, 490h
0x180020af1  mov     ebx, ecx
0x180020af3  mov     r9, [rsp+1D0h+String2]
0x180020af8  mov     r8d, 0C000100Bh
0x180020afe  mov     rax, [r14]
0x180020b01  mov     edx, ecx
0x180020b03  mov     rcx, r14
0x180020b06  mov     rax, [rax+28h]
0x180020b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b0f  jmp     short loc_180020B16
0x180020b11  test    r15d, r15d
0x180020b14  jz      short loc_180020B20
0x180020b16  lea     rcx, [rsp+1D0h+var_178]; struct _LIST_ENTRY *
0x180020b1b  call    ?FreeNfsExportList@@YAXPEAU_LIST_ENTRY@@@Z; FreeNfsExportList(_LIST_ENTRY *)
0x180020b20  test    rdi, rdi
0x180020b23  jz      short loc_180020B39
0x180020b25  call    cs:__imp_GetProcessHeap
0x180020b2b  mov     rcx, rax; hHeap
0x180020b2e  mov     r8, rdi; lpMem
0x180020b31  xor     edx, edx; dwFlags
0x180020b33  call    cs:__imp_HeapFree
0x180020b39  mov     eax, ebx
0x180020b3b  mov     rcx, [rbp+0D0h+var_50]
0x180020b42  xor     rcx, rsp; StackCookie
0x180020b45  call    __security_check_cookie
0x180020b4a  add     rsp, 198h
0x180020b51  pop     r15
0x180020b53  pop     r14
0x180020b55  pop     r13
0x180020b57  pop     r12
0x180020b59  pop     rdi
0x180020b5a  pop     rsi
0x180020b5b  pop     rbx
0x180020b5c  pop     rbp
0x180020b5d  retn
```
