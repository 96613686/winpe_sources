# AddSharePermission(ushort *,uchar,ushort *,ushort *,ulong,ulong *,ulong *,uchar *,CNfsTaskContext *)

- ea: `0x18001d024`
- end: `0x18001d2cf`
- name: `?AddSharePermission@@YAKPEAGE00KPEAK1PEAEPEAVCNfsTaskContext@@@Z`
- size: `683`
- prototype: `unsigned int __usercall@<eax>(wchar_t *String2@<rcx>, unsigned __int8@<dl>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned int, unsigned int *, unsigned int *, unsigned __int8 *, struct CNfsTaskContext *)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, installer_update`

## callers

- `0x18000b72c`
- `0x18000b9d8`

## callees

- `0x180009670`
- `0x18001cda0`
- `0x18001d024`
- `0x18001d4c8`
- `0x18001dcec`
- `0x18001e230`
- `0x18001e358`
- `0x18001e418`
- `0x18001ee48`
- `0x180020d94`
- `0x180021120`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001d149`
- `msvcrt!_wcsicmp` at `0x18001d149`
- `msvcrt!free` at `0x18001d175`
- `msvcrt!free` at `0x18001d200`
- `msvcrt!free` at `0x18001d175`
- `msvcrt!free` at `0x18001d200`
- `KERNEL32!HeapFree` at `0x18001d2a4`
- `KERNEL32!HeapFree` at `0x18001d2a4`
- `KERNEL32!GetProcessHeap` at `0x18001d296`
- `KERNEL32!GetProcessHeap` at `0x18001d296`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AddSharePermission(
        wchar_t *String2,
        unsigned __int8 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned int *a7,
        unsigned __int8 *a8,
        struct CNfsTaskContext *a9)
{
  unsigned int v12; // r13d
  struct _NFS_EXPORT *v13; // rdi
  unsigned __int16 *v14; // rsi
  unsigned int NfsShareList; // ebx
  _QWORD *v16; // r12
  struct _NFS_EXPORT_FENCING *v17; // r14
  const wchar_t **v18; // rax
  int v19; // r13d
  bool v20; // bl
  const char **v21; // rax
  struct _NFS_EXPORT **v22; // rdx
  char *v23; // rax
  HANDLE ProcessHeap; // rax
  int v26; // [rsp+40h] [rbp-C0h]
  unsigned int v27; // [rsp+44h] [rbp-BCh] BYREF
  struct _NFS_EXPORT_FENCING *v28; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v29; // [rsp+50h] [rbp-B0h] BYREF
  struct _NFS_EXPORT *v30; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *String2a; // [rsp+60h] [rbp-A0h]
  struct CNfsTaskContext *v32; // [rsp+68h] [rbp-98h]
  struct _LIST_ENTRY v33; // [rsp+70h] [rbp-90h] BYREF
  void *v34; // [rsp+80h] [rbp-80h] BYREF
  char v35; // [rsp+88h] [rbp-78h] BYREF
  void *Block; // [rsp+110h] [rbp+10h] BYREF
  char v37; // [rsp+118h] [rbp+18h] BYREF

  String2a = a4;
  v32 = a9;
  v12 = 0;
  v33 = 0;
  v13 = 0;
  v30 = 0;
  v14 = 0;
  v29 = 0;
  v27 = 0;
  v26 = 0;
  v28 = 0;
  NfsShareList = GetNfsShareList(&v33);
  if ( !NfsShareList )
  {
    v26 = 1;
    NfsShareList = FindShareRecord(String2, a2, a3, &v33, &v30);
    v13 = v30;
  }
  if ( NfsShareList == 1168 )
  {
    (*(void (__fastcall **)(struct CNfsTaskContext *, __int64, __int64, wchar_t *))(*(_QWORD *)v32 + 40LL))(
      v32,
      1168,
      3221229578LL,
      String2);
  }
  else if ( !NfsShareList )
  {
    if ( *((_DWORD *)v13 + 273) )
    {
      v16 = (_QWORD *)*((_QWORD *)v13 + 205);
      while ( v16 != (_QWORD *)((char *)v13 + 1640) )
      {
        v17 = (struct _NFS_EXPORT_FENCING *)(v16 - 12);
        v28 = v17;
        v16 = (_QWORD *)*v16;
        v18 = (const wchar_t **)ATL::CA2WEX<128>::CA2WEX<128>(&Block, *((_QWORD *)v17 + 1));
        v19 = v12 | 1;
        v20 = !_wcsicmp(*v18, String2a) && a5 == *(_DWORD *)v17;
        v12 = v19 & 0xFFFFFFFE;
        if ( Block != &v37 )
          free(Block);
        if ( v20 )
        {
          UpdatePermissionEntry(v17, a6, a7, a8);
          goto LABEL_23;
        }
      }
    }
    v21 = (const char **)ATL::CW2AEX<128>::CW2AEX<128>(&v34, String2a);
    NfsShareList = CreatePermissionEntry(*v21, a5, a6, a7, a8, 0, 1u, &v28);
    if ( v34 != &v35 )
      free(v34);
    if ( !NfsShareList )
    {
      v22 = (struct _NFS_EXPORT **)*((_QWORD *)v13 + 206);
      if ( *v22 != (struct _NFS_EXPORT *)((char *)v13 + 1640) )
        __fastfail(3u);
      v23 = (char *)v28 + 96;
      *((_QWORD *)v28 + 12) = (char *)v13 + 1640;
      *((_QWORD *)v23 + 1) = v22;
      *v22 = (struct _NFS_EXPORT *)v23;
      *((_QWORD *)v13 + 206) = v23;
      ++*((_DWORD *)v13 + 273);
LABEL_23:
      SortPermissionsList((char *)v13 + 1640, 0, 0);
      NfsShareList = CreateSharePermissionString((struct _LIST_ENTRY *)((char *)v13 + 1640), &v29, &v27);
      v14 = v29;
      if ( !NfsShareList )
        NfsShareList = ModifyShareOnServer(v13);
    }
  }
  if ( v26 )
    FreeNfsExportList(&v33);
  if ( v14 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v14);
  }
  return NfsShareList;
}

```

## disassembly

```asm
0x18001d024  push    rbp
0x18001d026  push    rbx
0x18001d027  push    rsi
0x18001d028  push    rdi
0x18001d029  push    r12
0x18001d02b  push    r13
0x18001d02d  push    r14
0x18001d02f  push    r15
0x18001d031  lea     rbp, [rsp-138h]
0x18001d039  sub     rsp, 238h
0x18001d040  mov     rax, cs:__security_cookie
0x18001d047  xor     rax, rsp
0x18001d04a  mov     [rbp+170h+var_50], rax
0x18001d051  mov     [rsp+270h+String2], r9
0x18001d056  mov     r12, r8
0x18001d059  mov     r15b, dl
0x18001d05c  mov     r14, rcx
0x18001d05f  mov     rax, [rbp+170h+arg_40]
0x18001d066  mov     [rsp+270h+var_208], rax
0x18001d06b  xor     eax, eax
0x18001d06d  mov     r13d, eax
0x18001d070  mov     [rsp+270h+var_22C], eax
0x18001d074  xorps   xmm0, xmm0
0x18001d077  movups  xmmword ptr [rsp+270h+var_200.Flink], xmm0
0x18001d07c  mov     edi, eax
0x18001d07e  mov     [rsp+270h+var_218], rax
0x18001d083  mov     esi, eax
0x18001d085  mov     [rsp+270h+var_220], rax
0x18001d08a  mov     [rsp+270h+var_22C], eax
0x18001d08e  mov     [rsp+270h+var_230], eax
0x18001d092  mov     [rsp+270h+var_228], rax
0x18001d097  lea     rcx, [rsp+270h+var_200]; struct _LIST_ENTRY *
0x18001d09c  call    ?GetNfsShareList@@YAKPEAU_LIST_ENTRY@@@Z; GetNfsShareList(_LIST_ENTRY *)
0x18001d0a1  mov     ebx, eax
0x18001d0a3  test    eax, eax
0x18001d0a5  jnz     short loc_18001D0D3
0x18001d0a7  mov     [rsp+270h+var_230], 1
0x18001d0af  lea     rax, [rsp+270h+var_218]
0x18001d0b4  mov     [rsp+270h+var_250], rax; struct _NFS_EXPORT **
0x18001d0b9  lea     r9, [rsp+270h+var_200]; struct _LIST_ENTRY *
0x18001d0be  mov     r8, r12; unsigned __int16 *
0x18001d0c1  mov     dl, r15b; unsigned __int8
0x18001d0c4  mov     rcx, r14; String2
0x18001d0c7  call    ?FindShareRecord@@YAKPEAGE0PEAU_LIST_ENTRY@@PEAPEAU_NFS_EXPORT@@@Z; FindShareRecord(ushort *,uchar,ushort *,_LIST_ENTRY *,_NFS_EXPORT * *)
0x18001d0cc  mov     ebx, eax
0x18001d0ce  mov     rdi, [rsp+270h+var_218]
0x18001d0d3  mov     edx, 490h
0x18001d0d8  cmp     ebx, edx
0x18001d0da  jnz     short loc_18001D0FB
0x18001d0dc  mov     rcx, [rsp+270h+var_208]
0x18001d0e1  mov     rax, [rcx]
0x18001d0e4  mov     r9, r14
0x18001d0e7  mov     r8d, 0C000100Ah
0x18001d0ed  mov     rax, [rax+28h]
0x18001d0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0f6  jmp     loc_18001D280
0x18001d0fb  test    ebx, ebx
0x18001d0fd  jnz     loc_18001D280
0x18001d103  cmp     [rdi+444h], esi
0x18001d109  jz      loc_18001D1A2
0x18001d10f  lea     r15, [rdi+668h]
0x18001d116  mov     r12, [r15]
0x18001d119  cmp     r12, r15
0x18001d11c  jz      loc_18001D1A2
0x18001d122  lea     r14, [r12-60h]
0x18001d127  mov     [rsp+270h+var_228], r14
0x18001d12c  mov     r12, [r12]
0x18001d130  mov     rdx, [r14+8]
0x18001d134  lea     rcx, [rbp+170h+Block]
0x18001d138  call    ??0?$CA2WEX@$0IA@@ATL@@QEAA@PEBD@Z; ATL::CA2WEX<128>::CA2WEX<128>(char const *)
0x18001d13d  or      r13d, 1
0x18001d141  mov     rdx, [rsp+270h+String2]; String2
0x18001d146  mov     rcx, [rax]; String1
0x18001d149  call    cs:__imp__wcsicmp
0x18001d14f  test    eax, eax
0x18001d151  jnz     short loc_18001D162
0x18001d153  mov     eax, [rbp+170h+arg_20]
0x18001d159  cmp     eax, [r14]
0x18001d15c  jnz     short loc_18001D162
0x18001d15e  mov     bl, 1
0x18001d160  jmp     short loc_18001D164
0x18001d162  xor     bl, bl
0x18001d164  and     r13d, 0FFFFFFFEh
0x18001d168  mov     rcx, [rbp+170h+Block]; Block
0x18001d16c  lea     rax, [rbp+170h+var_158]
0x18001d170  cmp     rcx, rax
0x18001d173  jz      short loc_18001D17C
0x18001d175  call    cs:__imp_free
0x18001d17b  nop
0x18001d17c  test    bl, bl
0x18001d17e  jz      short loc_18001D119
0x18001d180  mov     r9, [rbp+170h+arg_38]
0x18001d187  mov     r8, [rbp+170h+arg_30]
0x18001d18e  mov     rdx, [rbp+170h+arg_28]
0x18001d195  mov     rcx, r14
0x18001d198  call    UpdatePermissionEntry
0x18001d19d  jmp     loc_18001D23D
0x18001d1a2  mov     rdx, [rsp+270h+String2]
0x18001d1a7  lea     rcx, [rbp+170h+var_1F0]
0x18001d1ab  call    ??0?$CW2AEX@$0IA@@ATL@@QEAA@PEBG@Z; ATL::CW2AEX<128>::CW2AEX<128>(ushort const *)
0x18001d1b0  nop
0x18001d1b1  lea     rcx, [rsp+270h+var_228]
0x18001d1b6  mov     [rsp+270h+var_238], rcx; struct _NFS_EXPORT_FENCING **
0x18001d1bb  mov     [rsp+270h+var_240], 1; unsigned __int8
0x18001d1c0  mov     [rsp+270h+var_248], 0; char *
0x18001d1c9  mov     rcx, [rbp+170h+arg_38]
0x18001d1d0  mov     [rsp+270h+var_250], rcx; unsigned __int8 *
0x18001d1d5  mov     r9, [rbp+170h+arg_30]; unsigned int *
0x18001d1dc  mov     r8, [rbp+170h+arg_28]; unsigned int *
0x18001d1e3  mov     edx, [rbp+170h+arg_20]; unsigned int
0x18001d1e9  mov     rcx, [rax]; char *
0x18001d1ec  call    ?CreatePermissionEntry@@YAKPEBDKPEAK1PEAE0EPEAPEAU_NFS_EXPORT_FENCING@@@Z; CreatePermissionEntry(char const *,ulong,ulong *,ulong *,uchar *,char const *,uchar,_NFS_EXPORT_FENCING * *)
0x18001d1f1  mov     ebx, eax
0x18001d1f3  mov     rcx, [rbp+170h+var_1F0]; Block
0x18001d1f7  lea     rax, [rbp+170h+var_1E8]
0x18001d1fb  cmp     rcx, rax
0x18001d1fe  jz      short loc_18001D207
0x18001d200  call    cs:__imp_free
0x18001d206  nop
0x18001d207  test    ebx, ebx
0x18001d209  jnz     short loc_18001D280
0x18001d20b  lea     rcx, [rdi+668h]
0x18001d212  mov     rdx, [rcx+8]
0x18001d216  cmp     [rdx], rcx
0x18001d219  jz      short loc_18001D220
0x18001d21b  lea     ecx, [rbx+3]
0x18001d21e  int     29h; Win8: RtlFailFast(ecx)
0x18001d220  mov     rax, [rsp+270h+var_228]
0x18001d225  add     rax, 60h ; '`'
0x18001d229  mov     [rax], rcx
0x18001d22c  mov     [rax+8], rdx
0x18001d230  mov     [rdx], rax
0x18001d233  mov     [rcx+8], rax
0x18001d237  inc     dword ptr [rdi+444h]
0x18001d23d  lea     rbx, [rdi+668h]
0x18001d244  xor     r8d, r8d
0x18001d247  xor     edx, edx
0x18001d249  mov     rcx, rbx
0x18001d24c  call    SortPermissionsList
0x18001d251  lea     r8, [rsp+270h+var_22C]; unsigned int *
0x18001d256  lea     rdx, [rsp+270h+var_220]; unsigned __int16 **
0x18001d25b  mov     rcx, rbx; struct _LIST_ENTRY *
0x18001d25e  call    ?CreateSharePermissionString@@YAKPEAU_LIST_ENTRY@@PEAPEAGPEAK@Z; CreateSharePermissionString(_LIST_ENTRY *,ushort * *,ulong *)
0x18001d263  mov     ebx, eax
0x18001d265  mov     rsi, [rsp+270h+var_220]
0x18001d26a  test    eax, eax
0x18001d26c  jnz     short loc_18001D280
0x18001d26e  mov     r8, [rsp+270h+var_208]
0x18001d273  mov     rdx, rsi
0x18001d276  mov     rcx, rdi; struct _NFS_EXPORT *
0x18001d279  call    ModifyShareOnServer
0x18001d27e  mov     ebx, eax
0x18001d280  cmp     [rsp+270h+var_230], 0
0x18001d285  jz      short loc_18001D291
0x18001d287  lea     rcx, [rsp+270h+var_200]; struct _LIST_ENTRY *
0x18001d28c  call    ?FreeNfsExportList@@YAXPEAU_LIST_ENTRY@@@Z; FreeNfsExportList(_LIST_ENTRY *)
0x18001d291  test    rsi, rsi
0x18001d294  jz      short loc_18001D2AA
0x18001d296  call    cs:__imp_GetProcessHeap
0x18001d29c  mov     rcx, rax; hHeap
0x18001d29f  mov     r8, rsi; lpMem
0x18001d2a2  xor     edx, edx; dwFlags
0x18001d2a4  call    cs:__imp_HeapFree
0x18001d2aa  mov     eax, ebx
0x18001d2ac  mov     rcx, [rbp+170h+var_50]
0x18001d2b3  xor     rcx, rsp; StackCookie
0x18001d2b6  call    __security_check_cookie
0x18001d2bb  add     rsp, 238h
0x18001d2c2  pop     r15
0x18001d2c4  pop     r14
0x18001d2c6  pop     r13
0x18001d2c8  pop     r12
0x18001d2ca  pop     rdi
0x18001d2cb  pop     rsi
0x18001d2cc  pop     rbx
0x18001d2cd  pop     rbp
0x18001d2ce  retn
```
