# SetSharePermission(ushort *,uchar,ushort *,ushort *,ushort *,CNfsTaskContext *)

- ea: `0x180020b64`
- end: `0x180020d8d`
- name: `?SetSharePermission@@YAKPEAGE000PEAVCNfsTaskContext@@@Z`
- size: `553`
- prototype: `unsigned int __usercall@<eax>(wchar_t *String2@<rcx>, unsigned __int8@<dl>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, struct CNfsTaskContext *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000d66c`

## callees

- `0x18000e74c`
- `0x18001cf20`
- `0x18001dcec`
- `0x18001e230`
- `0x18001e2d4`
- `0x18001e358`
- `0x18001e418`
- `0x18001ee48`
- `0x180020b64`
- `0x180020d94`
- `0x18002115c`
- `0x180021384`
- `0x180027a2c`
- `0x180027c5c`
- `0x180037010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180020d60`
- `KERNEL32!HeapFree` at `0x180020d60`
- `KERNEL32!GetProcessHeap` at `0x180020d52`
- `KERNEL32!GetProcessHeap` at `0x180020d52`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SetSharePermission(
        wchar_t *String2,
        bool a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct CNfsTaskContext *a6)
{
  struct _NFS_EXPORT *v8; // r14
  unsigned __int16 *v9; // rsi
  int v10; // r12d
  unsigned int NfsShareList; // ebx
  int v12; // ecx
  HANDLE ProcessHeap; // rax
  unsigned int v15; // [rsp+58h] [rbp-69h] BYREF
  unsigned __int16 *v16; // [rsp+60h] [rbp-61h] BYREF
  __int64 v17; // [rsp+68h] [rbp-59h] BYREF
  struct _LIST_ENTRY v18; // [rsp+70h] [rbp-51h] BYREF
  __int64 v19; // [rsp+88h] [rbp-39h] BYREF
  __int64 v20; // [rsp+90h] [rbp-31h]
  __int128 v21; // [rsp+98h] [rbp-29h]
  __int64 v22; // [rsp+A8h] [rbp-19h]
  int v23; // [rsp+C0h] [rbp-1h]
  __int64 *v24; // [rsp+C8h] [rbp+7h]
  bool v25; // [rsp+120h] [rbp+5Fh] BYREF
  struct _NFS_EXPORT *v26; // [rsp+128h] [rbp+67h] BYREF

  v25 = a2;
  v8 = 0;
  v26 = 0;
  v9 = 0;
  v16 = 0;
  v10 = 0;
  v15 = 0;
  v18 = 0;
  v17 = 0;
  v24 = &v19;
  v19 = 0;
  v20 = 0;
  v19 = std::_List_alloc<0,std::_List_base_types<std::pair<std::wstring const,std::vector<CNfsXmlSharePermission *>>>>::_Buynode0(
          String2,
          0,
          0);
  v21 = 0;
  v22 = 0;
  v23 = 1065353216;
  std::_Hash<stdext::_Hmap_traits<std::wstring,std::vector<CNfsXmlSharePermission *>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<CNfsXmlSharePermission *>>>,0>>::_Init(
    &v19,
    8);
  NfsShareList = GetNfsShareList(&v18);
  if ( !NfsShareList )
  {
    v10 = 1;
    NfsShareList = FindShareRecord(String2, 1u, 0, &v18, &v26);
    v8 = v26;
  }
  if ( NfsShareList == 1168 )
  {
    (*(void (__fastcall **)(struct CNfsTaskContext *, __int64, __int64, wchar_t *))(*(_QWORD *)a6 + 40LL))(
      a6,
      1168,
      3221229578LL,
      String2);
  }
  else if ( !NfsShareList )
  {
    FreeNfsExportFencingList((struct _LIST_ENTRY *)((char *)v8 + 1640));
    *((_DWORD *)v8 + 273) = 0;
    *((_QWORD *)v8 + 206) = (char *)v8 + 1640;
    *((_QWORD *)v8 + 205) = (char *)v8 + 1640;
    NfsShareList = CNfsXmlParser::NfsXmlReadDocument((CNfsXmlParser *)&v19, a4, a5);
    if ( !NfsShareList )
    {
      if ( v20 )
      {
        NfsShareList = CNfsXmlParser::NfsXmlGetPermissionsList(
                         (CNfsXmlParser *)&v19,
                         (struct _LIST_ENTRY *)((char *)v8 + 1640));
        if ( !NfsShareList )
        {
          SortPermissionsList((char *)v8 + 1640, &v17, (char *)v8 + 1092);
          if ( v17 )
          {
            v12 = *(_DWORD *)(v17 + 84);
            v25 = (v12 & 8) != 0;
            LODWORD(v26) = v12 & 7;
            UpdateShareProperties((_DWORD)v8, 0, 0, 0, 0, (__int64)&v25, v17 + 88, 0, (__int64)&v26);
          }
          NfsShareList = CreateSharePermissionString((struct _LIST_ENTRY *)((char *)v8 + 1640), &v16, &v15);
          v9 = v16;
          if ( !NfsShareList )
            NfsShareList = ModifyShareOnServer(v8);
        }
      }
      else
      {
        NfsShareList = 87;
      }
    }
  }
  if ( v10 )
    FreeNfsExportList(&v18);
  if ( v9 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
  }
  CNfsXmlParser::~CNfsXmlParser((CNfsXmlParser *)&v19);
  return NfsShareList;
}

```

## disassembly

```asm
0x180020b64  mov     rax, rsp
0x180020b67  mov     [rax+8], rbx
0x180020b6b  mov     [rax+18h], r8
0x180020b6f  mov     [rax+10h], dl
0x180020b72  push    rbp
0x180020b73  push    rsi
0x180020b74  push    rdi
0x180020b75  push    r12
0x180020b77  push    r13
0x180020b79  push    r14
0x180020b7b  push    r15
0x180020b7d  lea     rbp, [rax-4Fh]
0x180020b81  sub     rsp, 0D0h
0x180020b88  mov     r13, r9
0x180020b8b  mov     rdi, rcx
0x180020b8e  xor     r14d, r14d
0x180020b91  mov     [rbp+47h+arg_10], r14
0x180020b95  xor     esi, esi
0x180020b97  mov     [rbp+47h+var_A8], rsi
0x180020b9b  xor     r12d, r12d
0x180020b9e  mov     [rbp+47h+var_B0], esi
0x180020ba1  xorps   xmm0, xmm0
0x180020ba4  movups  xmmword ptr [rbp+47h+var_98.Flink], xmm0
0x180020ba8  mov     [rbp+47h+var_A0], rsi
0x180020bac  lea     rax, [rbp+47h+var_80]
0x180020bb0  mov     [rbp+47h+var_40], rax
0x180020bb4  mov     [rbp+47h+var_80], rsi
0x180020bb8  mov     [rbp+47h+var_78], rsi
0x180020bbc  xor     r8d, r8d
0x180020bbf  xor     edx, edx
0x180020bc1  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@2@@std@@@2@@std@@@std@@QEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@2@@std@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<std::pair<std::wstring const,std::vector<CNfsXmlSharePermission *>>>>::_Buynode0(std::_List_node<std::pair<std::wstring const,std::vector<CNfsXmlSharePermission *>>,void *> *,std::_List_node<std::pair<std::wstring const,std::vector<CNfsXmlSharePermission *>>,void *> *)
0x180020bc6  mov     [rbp+47h+var_80], rax
0x180020bca  xorps   xmm0, xmm0
0x180020bcd  movdqa  [rbp+47h+var_70], xmm0
0x180020bd2  mov     [rbp+47h+var_60], r12
0x180020bd6  mov     [rbp+47h+var_48], 3F800000h
0x180020bdd  lea     edx, [rsi+8]
0x180020be0  lea     rcx, [rbp+47h+var_80]
0x180020be4  call    ?_Init@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@2@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@2@@std@@@2@$0A@@stdext@@@std@@IEAAX_K@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::vector<CNfsXmlSharePermission *>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<CNfsXmlSharePermission *>>>,0>>::_Init(unsigned __int64)
0x180020be9  nop
0x180020bea  lea     rcx, [rbp+47h+var_98]; struct _LIST_ENTRY *
0x180020bee  call    ?GetNfsShareList@@YAKPEAU_LIST_ENTRY@@@Z; GetNfsShareList(_LIST_ENTRY *)
0x180020bf3  mov     ebx, eax
0x180020bf5  test    eax, eax
0x180020bf7  jnz     short loc_180020C1E
0x180020bf9  lea     r12d, [r14+1]
0x180020bfd  lea     rax, [rbp+47h+arg_10]
0x180020c01  mov     [rsp+100h+var_E0], rax; struct _NFS_EXPORT **
0x180020c06  lea     r9, [rbp+47h+var_98]; struct _LIST_ENTRY *
0x180020c0a  xor     r8d, r8d; unsigned __int16 *
0x180020c0d  mov     dl, r12b; unsigned __int8
0x180020c10  mov     rcx, rdi; String2
0x180020c13  call    ?FindShareRecord@@YAKPEAGE0PEAU_LIST_ENTRY@@PEAPEAU_NFS_EXPORT@@@Z; FindShareRecord(ushort *,uchar,ushort *,_LIST_ENTRY *,_NFS_EXPORT * *)
0x180020c18  mov     ebx, eax
0x180020c1a  mov     r14, [rbp+47h+arg_10]
0x180020c1e  mov     edx, 490h
0x180020c23  cmp     ebx, edx
0x180020c25  jnz     short loc_180020C45
0x180020c27  mov     rcx, [rbp+47h+arg_28]
0x180020c2b  mov     rax, [rcx]
0x180020c2e  mov     r9, rdi
0x180020c31  mov     r8d, 0C000100Ah
0x180020c37  mov     rax, [rax+28h]
0x180020c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c40  jmp     loc_180020D3F
0x180020c45  test    ebx, ebx
0x180020c47  jnz     loc_180020D3F
0x180020c4d  lea     rdi, [r14+668h]
0x180020c54  mov     rcx, rdi; struct _LIST_ENTRY *
0x180020c57  call    ?FreeNfsExportFencingList@@YAXPEAU_LIST_ENTRY@@@Z; FreeNfsExportFencingList(_LIST_ENTRY *)
0x180020c5c  lea     r15, [r14+444h]
0x180020c63  mov     [r15], ebx
0x180020c66  mov     [rdi+8], rdi
0x180020c6a  mov     [rdi], rdi
0x180020c6d  mov     r8, [rbp+47h+arg_20]; unsigned __int16 *
0x180020c71  mov     rdx, r13; unsigned __int16 *
0x180020c74  lea     rcx, [rbp+47h+var_80]; this
0x180020c78  call    ?NfsXmlReadDocument@CNfsXmlParser@@QEAAKPEAG0@Z; CNfsXmlParser::NfsXmlReadDocument(ushort *,ushort *)
0x180020c7d  mov     ebx, eax
0x180020c7f  test    eax, eax
0x180020c81  jnz     loc_180020D3F
0x180020c87  cmp     [rbp+47h+var_78], 0
0x180020c8c  jnz     short loc_180020C96
0x180020c8e  lea     ebx, [rax+57h]
0x180020c91  jmp     loc_180020D3F
0x180020c96  mov     rdx, rdi; struct _LIST_ENTRY *
0x180020c99  lea     rcx, [rbp+47h+var_80]; this
0x180020c9d  call    ?NfsXmlGetPermissionsList@CNfsXmlParser@@QEAAKPEAU_LIST_ENTRY@@@Z; CNfsXmlParser::NfsXmlGetPermissionsList(_LIST_ENTRY *)
0x180020ca2  mov     ebx, eax
0x180020ca4  test    eax, eax
0x180020ca6  jnz     loc_180020D3F
0x180020cac  mov     r8, r15
0x180020caf  lea     rdx, [rbp+47h+var_A0]
0x180020cb3  mov     rcx, rdi
0x180020cb6  call    SortPermissionsList
0x180020cbb  mov     rdx, [rbp+47h+var_A0]
0x180020cbf  test    rdx, rdx
0x180020cc2  jz      short loc_180020D14
0x180020cc4  mov     ecx, [rdx+54h]
0x180020cc7  mov     eax, ecx
0x180020cc9  shr     eax, 3
0x180020ccc  and     al, 1
0x180020cce  mov     [rbp+47h+arg_8], al
0x180020cd1  and     ecx, 7
0x180020cd4  mov     dword ptr [rbp+47h+arg_10], ecx
0x180020cd7  lea     rax, [rdx+58h]
0x180020cdb  lea     rcx, [rbp+47h+arg_10]
0x180020cdf  mov     [rsp+40h], rcx
0x180020ce4  mov     [rsp+100h+var_C8], 0
0x180020ced  mov     [rsp+100h+var_D0], rax
0x180020cf2  lea     rax, [rbp+47h+arg_8]
0x180020cf6  mov     [rsp+100h+var_D8], rax
0x180020cfb  mov     [rsp+100h+var_E0], 0
0x180020d04  xor     r9d, r9d
0x180020d07  xor     r8d, r8d
0x180020d0a  xor     edx, edx
0x180020d0c  mov     rcx, r14
0x180020d0f  call    UpdateShareProperties
0x180020d14  lea     r8, [rbp+47h+var_B0]; unsigned int *
0x180020d18  lea     rdx, [rbp+47h+var_A8]; unsigned __int16 **
0x180020d1c  mov     rcx, rdi; struct _LIST_ENTRY *
0x180020d1f  call    ?CreateSharePermissionString@@YAKPEAU_LIST_ENTRY@@PEAPEAGPEAK@Z; CreateSharePermissionString(_LIST_ENTRY *,ushort * *,ulong *)
0x180020d24  mov     ebx, eax
0x180020d26  mov     rsi, [rbp+47h+var_A8]
0x180020d2a  test    eax, eax
0x180020d2c  jnz     short loc_180020D3F
0x180020d2e  mov     r8, [rbp+47h+arg_28]
0x180020d32  mov     rdx, rsi
0x180020d35  mov     rcx, r14; struct _NFS_EXPORT *
0x180020d38  call    ModifyShareOnServer
0x180020d3d  mov     ebx, eax
0x180020d3f  test    r12d, r12d
0x180020d42  jz      short loc_180020D4D
0x180020d44  lea     rcx, [rbp+47h+var_98]; struct _LIST_ENTRY *
0x180020d48  call    ?FreeNfsExportList@@YAXPEAU_LIST_ENTRY@@@Z; FreeNfsExportList(_LIST_ENTRY *)
0x180020d4d  test    rsi, rsi
0x180020d50  jz      short loc_180020D67
0x180020d52  call    cs:__imp_GetProcessHeap
0x180020d58  mov     rcx, rax; hHeap
0x180020d5b  mov     r8, rsi; lpMem
0x180020d5e  xor     edx, edx; dwFlags
0x180020d60  call    cs:__imp_HeapFree
0x180020d66  nop
0x180020d67  lea     rcx, [rbp+47h+var_80]; this
0x180020d6b  call    ??1CNfsXmlParser@@QEAA@XZ; CNfsXmlParser::~CNfsXmlParser(void)
0x180020d70  mov     eax, ebx
0x180020d72  mov     rbx, [rsp+100h+arg_0]
0x180020d7a  add     rsp, 0D0h
0x180020d81  pop     r15
0x180020d83  pop     r14
0x180020d85  pop     r13
0x180020d87  pop     r12
0x180020d89  pop     rdi
0x180020d8a  pop     rsi
0x180020d8b  pop     rbp
0x180020d8c  retn
```
