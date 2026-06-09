# CConnectionList::HrInsert(CConFoldEntry const &)

- ea: `0x180042294`
- end: `0x180042411`
- name: `?HrInsert@CConnectionList@@QEAAJAEBVCConFoldEntry@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(CConnectionList *__hidden this, const struct CConFoldEntry *)`
- caller_count: `4`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180003770`
- `0x180016470`
- `0x180042418`
- `0x18004abf0`

## callees

- `0x180002010`
- `0x180002460`
- `0x1800025a0`
- `0x180002898`
- `0x1800032b0`
- `0x1800057a0`
- `0x18001e1e0`
- `0x1800419e0`
- `0x1800420e8`
- `0x180042294`
- `0x1800428c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800423cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800423cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042328`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042328`
- `ole32!CoTaskMemFree` at `0x1800422f4`
- `ole32!CoTaskMemFree` at `0x180042302`
- `ole32!CoTaskMemFree` at `0x1800422f4`
- `ole32!CoTaskMemFree` at `0x180042302`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CConnectionList::HrInsert(CConnectionList *this, const struct CConFoldEntry *a2)
{
  unsigned int v4; // r14d
  CConnectionList *v5; // rcx
  __int64 *v6; // rbx
  __int64 *v7; // rax
  _QWORD *v8; // rax
  _BYTE v10[16]; // [rsp+20h] [rbp-E0h] BYREF
  int v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[40]; // [rsp+38h] [rbp-C8h] BYREF
  struct _GUID v13; // [rsp+60h] [rbp-A0h]
  char v14; // [rsp+70h] [rbp-90h]
  LPVOID *v15; // [rsp+C8h] [rbp-38h]
  struct _GUID v16; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v17[176]; // [rsp+F0h] [rbp-10h] BYREF

  v4 = 0;
  ConnListEntry::ConnListEntry((ConnListEntry *)&v11);
  v11 = 0;
  CConFoldEntry::operator=((CConFoldEntry *)v12);
  v5 = (CConnectionList *)v15;
  if ( v15 )
  {
    CoTaskMemFree(*v15);
    CoTaskMemFree(v15[1]);
  }
  v15 = 0;
  if ( v14 < 0 )
    CConnectionList::HrGetBrandingInfo(v5, (struct ConnListEntry *)&v11);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  ConnListEntry::ConnListEntry((ConnListEntry *)v17);
  v16 = *(struct _GUID *)((char *)a2 + 40);
  if ( (unsigned int)CConnectionList::HrFindConnectionByGuid((__int64 **)this, &v16, (struct ConnListEntry *)v17) == 1 )
  {
    v6 = *(__int64 **)this;
    if ( *(_QWORD *)this )
      goto LABEL_12;
    v7 = (__int64 *)MemAlloc(0x10u);
    v6 = v7;
    *(_QWORD *)&v16.Data1 = v7;
    if ( v7 )
    {
      *v7 = 0;
      v7[1] = 0;
      std::_Tree<std::_Tmap_traits<_GUID const,ConnListEntry,std::less<_GUID const>,std::allocator<std::pair<_GUID const,ConnListEntry>>,0>>::_Alloc_sentinel_and_proxy(v7);
    }
    else
    {
      v6 = 0;
    }
    *(_QWORD *)this = v6;
    if ( v6 )
    {
LABEL_12:
      v16 = v13;
      v8 = (_QWORD *)std::map<_GUID const,ConnListEntry>::_Try_emplace<_GUID const,>(v6, v10, &v16);
      ConnListEntry::operator=(*v8 + 48LL, (__int64)&v11);
    }
    else
    {
      v4 = -2147024882;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  ConnListEntry::~ConnListEntry((ConnListEntry *)v17);
  ConnListEntry::~ConnListEntry((ConnListEntry *)&v11);
  return v4;
}

```

## disassembly

```asm
0x180042294  mov     [rsp-8+arg_10], rbx
0x180042299  mov     [rsp-8+arg_18], rsi
0x18004229e  push    rbp
0x18004229f  push    rdi
0x1800422a0  push    r14
0x1800422a2  lea     rbp, [rsp-0B0h]
0x1800422aa  sub     rsp, 1B0h
0x1800422b1  mov     rax, cs:__security_cookie
0x1800422b8  xor     rax, rsp
0x1800422bb  mov     [rbp+0C0h+var_20], rax
0x1800422c2  mov     rbx, rdx
0x1800422c5  mov     rsi, rcx
0x1800422c8  xor     r14d, r14d
0x1800422cb  lea     rcx, [rsp+1C0h+var_190]; this
0x1800422d0  call    ??0ConnListEntry@@QEAA@XZ; ConnListEntry::ConnListEntry(void)
0x1800422d5  nop
0x1800422d6  mov     [rsp+1C0h+var_190], r14d
0x1800422db  mov     rdx, rbx
0x1800422de  lea     rcx, [rsp+1C0h+var_188]; this
0x1800422e3  call    ??4CConFoldEntry@@QEAAAEAV0@AEBV0@@Z; CConFoldEntry::operator=(CConFoldEntry const &)
0x1800422e8  mov     rcx, [rbp+0C0h+var_F8]
0x1800422ec  test    rcx, rcx
0x1800422ef  jz      short loc_180042308
0x1800422f1  mov     rcx, [rcx]; pv
0x1800422f4  call    cs:__imp_CoTaskMemFree
0x1800422fa  mov     rcx, [rbp+0C0h+var_F8]
0x1800422fe  mov     rcx, [rcx+8]; pv
0x180042302  call    cs:__imp_CoTaskMemFree
0x180042308  mov     [rbp+0C0h+var_F8], 0
0x180042310  test    [rsp+1C0h+var_150], 80h
0x180042315  jz      short loc_180042321
0x180042317  lea     rdx, [rsp+1C0h+var_190]; struct ConnListEntry *
0x18004231c  call    ?HrGetBrandingInfo@CConnectionList@@QEAAJAEAVConnListEntry@@@Z; CConnectionList::HrGetBrandingInfo(ConnListEntry &)
0x180042321  lea     rdi, [rsi+10h]
0x180042325  mov     rcx, rdi; lpCriticalSection
0x180042328  call    cs:__imp_EnterCriticalSection
0x18004232e  lea     rcx, [rbp+0C0h+var_D0]; this
0x180042332  call    ??0ConnListEntry@@QEAA@XZ; ConnListEntry::ConnListEntry(void)
0x180042337  nop
0x180042338  movups  xmm0, xmmword ptr [rbx+28h]
0x18004233c  movdqu  xmmword ptr [rbp+0C0h+var_E0.Data1], xmm0
0x180042341  lea     r8, [rbp+0C0h+var_D0]; struct ConnListEntry *
0x180042345  lea     rdx, [rbp+0C0h+var_E0]; struct _GUID *
0x180042349  mov     rcx, rsi; this
0x18004234c  call    ?HrFindConnectionByGuid@CConnectionList@@QEAAJPEFBU_GUID@@AEAVConnListEntry@@@Z; CConnectionList::HrFindConnectionByGuid(_GUID const *,ConnListEntry &)
0x180042351  cmp     eax, 1
0x180042354  jnz     short loc_1800423C9
0x180042356  mov     rbx, [rsi]
0x180042359  test    rbx, rbx
0x18004235c  jnz     short loc_18004239D
0x18004235e  lea     ecx, [rax+0Fh]; unsigned __int64
0x180042361  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180042366  mov     rbx, rax
0x180042369  mov     qword ptr [rbp+0C0h+var_E0.Data1], rax
0x18004236d  test    rax, rax
0x180042370  jz      short loc_18004238B
0x180042372  mov     qword ptr [rax], 0
0x180042379  mov     qword ptr [rax+8], 0
0x180042381  mov     rcx, rax
0x180042384  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@$$CBU_GUID@@VConnListEntry@@U?$less@$$CBU_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VConnListEntry@@@std@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID const,ConnListEntry,std::less<_GUID const>,std::allocator<std::pair<_GUID const,ConnListEntry>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180042389  jmp     short loc_18004238D
0x18004238b  xor     ebx, ebx
0x18004238d  mov     [rsi], rbx
0x180042390  test    rbx, rbx
0x180042393  jnz     short loc_18004239D
0x180042395  mov     r14d, 8007000Eh
0x18004239b  jmp     short loc_1800423C9
0x18004239d  movaps  xmm0, [rsp+1C0h+var_160]
0x1800423a2  movdqu  xmmword ptr [rbp+0C0h+var_E0.Data1], xmm0
0x1800423a7  lea     r8, [rbp+0C0h+var_E0]
0x1800423ab  lea     rdx, [rsp+1C0h+var_1A0]
0x1800423b0  mov     rcx, rbx
0x1800423b3  call    ??$_Try_emplace@$$CBU_GUID@@$$V@?$map@$$CBU_GUID@@VConnListEntry@@U?$less@$$CBU_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VConnListEntry@@@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@VConnListEntry@@@std@@PEAX@std@@_N@1@$$QEBU_GUID@@@Z; std::map<_GUID const,ConnListEntry>::_Try_emplace<_GUID const,>(_GUID const &&)
0x1800423b8  mov     rcx, [rax]
0x1800423bb  add     rcx, 30h ; '0'
0x1800423bf  lea     rdx, [rsp+1C0h+var_190]
0x1800423c4  call    ??4ConnListEntry@@QEAAAEAV0@AEBV0@@Z; ConnListEntry::operator=(ConnListEntry const &)
0x1800423c9  mov     rcx, rdi; lpCriticalSection
0x1800423cc  call    cs:__imp_LeaveCriticalSection
0x1800423d2  nop
0x1800423d3  lea     rcx, [rbp+0C0h+var_D0]; this
0x1800423d7  call    ??1ConnListEntry@@QEAA@XZ; ConnListEntry::~ConnListEntry(void)
0x1800423dc  nop
0x1800423dd  lea     rcx, [rsp+1C0h+var_190]; this
0x1800423e2  call    ??1ConnListEntry@@QEAA@XZ; ConnListEntry::~ConnListEntry(void)
0x1800423e7  mov     eax, r14d
0x1800423ea  mov     rcx, [rbp+0C0h+var_20]
0x1800423f1  xor     rcx, rsp; StackCookie
0x1800423f4  call    __security_check_cookie
0x1800423f9  lea     r11, [rsp+1C0h+var_10]
0x180042401  mov     rbx, [r11+30h]
0x180042405  mov     rsi, [r11+38h]
0x180042409  mov     rsp, r11
0x18004240c  pop     r14
0x18004240e  pop     rdi
0x18004240f  pop     rbp
0x180042410  retn
```
