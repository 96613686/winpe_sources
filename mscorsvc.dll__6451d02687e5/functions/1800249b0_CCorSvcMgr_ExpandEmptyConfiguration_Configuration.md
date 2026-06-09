# CCorSvcMgr::ExpandEmptyConfiguration(Configuration *)

- ea: `0x1800249b0`
- end: `0x180024bf2`
- name: `?ExpandEmptyConfiguration@CCorSvcMgr@@AEAAXPEAVConfiguration@@@Z`
- size: `578`
- prototype: `void __fastcall(CCorSvcMgr *__hidden this, struct Configuration *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callees

- `0x1800093d8`
- `0x18000c8a8`
- `0x1800249b0`
- `0x18002587c`
- `0x18002c5a0`
- `0x18002d3c0`
- `0x18002db88`
- `0x1800304ec`
- `0x180030568`
- `0x180030ab8`
- `0x180030d84`
- `0x180034fd4`
- `0x18003dc50`
- `0x18003f280`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180024ab2`
- `OLEAUT32!__imp_SysAllocString` at `0x180024ab2`
- `OLEAUT32!__imp_SysFreeString` at `0x180024b03`
- `OLEAUT32!__imp_SysFreeString` at `0x180024b03`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
void __fastcall CCorSvcMgr::ExpandEmptyConfiguration(CCorSvcMgr *this, struct Configuration *a2)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  int v6; // r12d
  const unsigned __int16 *v7; // rdi
  _DWORD *v8; // rax
  void *v9; // rbx
  struct LogicalImage *LogicalImage; // r13
  struct CCorSvcMgr::WorkerPoolItem *SvcWorkerForConfiguration; // r14
  __int64 v12; // rdi
  unsigned int *v13; // rbx
  const OLECHAR *RootPath; // rax
  OLECHAR *v15; // rcx
  struct ICorSvcDependencies *v16; // rbx
  void *v17; // rbx
  void *v18; // [rsp+30h] [rbp-30h] BYREF
  BOOL v19; // [rsp+38h] [rbp-28h]
  BSTR bstrString; // [rsp+40h] [rbp-20h]
  BOOL v21; // [rsp+48h] [rbp-18h]
  struct CCorSvcMgr::WorkerPoolItem *v22; // [rsp+50h] [rbp-10h]
  BOOL v23; // [rsp+58h] [rbp-8h]
  struct ICorSvcDependencies *v24; // [rsp+B0h] [rbp+50h] BYREF

  v4 = *((_QWORD *)a2 + 1);
  v5 = *(_QWORD *)(v4 + 24);
  v6 = 0;
  if ( v5 )
  {
    SString::ConvertToUnicode(*(SString **)(v4 + 24));
    v7 = *(const unsigned __int16 **)(v5 + 16);
  }
  else
  {
    v7 = 0;
  }
  v8 = operator new(0x18u);
  v9 = v8;
  if ( v8 )
  {
    v24 = (struct ICorSvcDependencies *)v8;
    *v8 = 2;
    v8[1] = 2;
    v8[2] = 16;
    *((_QWORD *)v8 + 2) = &SString::s_EmptyBuffer;
    if ( !v7 )
      ThrowHR(-2147024736);
    SString::Set((SString *)v8, v7);
  }
  else
  {
    v9 = 0;
  }
  v18 = v9;
  v19 = v9 != 0;
  LogicalImage = (struct LogicalImage *)Configuration::CreateLogicalImage(a2, (__int64 *)&v18);
  SvcWorkerForConfiguration = CCorSvcMgr::GetSvcWorkerForConfiguration(this, a2, v7, 0, 0);
  v22 = SvcWorkerForConfiguration;
  v23 = SvcWorkerForConfiguration != 0;
  v12 = *((_QWORD *)SvcWorkerForConfiguration + 3);
  v13 = (unsigned int *)*((_QWORD *)LogicalImage + 1);
  v24 = 0;
  RootPath = Configuration::GetRootPath((Configuration *)v13);
  v15 = SysAllocString(RootPath);
  bstrString = v15;
  v21 = 0;
  if ( v15 )
    v6 = 1;
  v21 = v6;
  if ( (*(int (__fastcall **)(__int64, OLECHAR *, _QWORD, struct ICorSvcDependencies **))(*(_QWORD *)v12 + 56LL))(
         v12,
         v15,
         v13[6],
         &v24) < 0 )
    ThrowHR(-2146230528);
  v16 = v24;
  if ( v6 )
  {
    SysFreeString(bstrString);
    v21 = 0;
  }
  bstrString = (BSTR)v16;
  v21 = v16 != 0;
  CCorSvcMgr::ExpandLogicalImage(this, LogicalImage, v16);
  if ( (*((_DWORD *)LogicalImage + 4) & 0xFFFFFFFB) == 0 )
    Node::SetStatus(a2, 0);
  if ( v16 )
  {
    (*(void (__fastcall **)(struct ICorSvcDependencies *))(*(_QWORD *)v16 + 16LL))(v16);
    v21 = 0;
  }
  if ( SvcWorkerForConfiguration )
  {
    CCorSvcMgr::WorkerPoolItem::~WorkerPoolItem(SvcWorkerForConfiguration);
    operator delete(SvcWorkerForConfiguration);
    v23 = 0;
  }
  if ( v19 )
  {
    v17 = v18;
    if ( v18 )
    {
      if ( (*((_BYTE *)v18 + 8) & 8) != 0 )
        operator delete(*((void **)v18 + 2));
      operator delete(v17);
    }
    v19 = 0;
  }
}

```

## disassembly

```asm
0x1800249b0  mov     [rsp-38h+arg_0], rbx
0x1800249b5  push    rbp
0x1800249b6  push    rsi
0x1800249b7  push    rdi
0x1800249b8  push    r12
0x1800249ba  push    r13
0x1800249bc  push    r14
0x1800249be  push    r15
0x1800249c0  mov     rbp, rsp
0x1800249c3  sub     rsp, 60h
0x1800249c7  mov     rsi, rdx
0x1800249ca  mov     r15, rcx
0x1800249cd  mov     rax, [rdx+8]
0x1800249d1  mov     rdi, [rax+18h]
0x1800249d5  xor     r12d, r12d
0x1800249d8  test    rdi, rdi
0x1800249db  jnz     short loc_1800249E2
0x1800249dd  mov     edi, r12d
0x1800249e0  jmp     short loc_1800249EE
0x1800249e2  mov     rcx, rdi; this
0x1800249e5  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800249ea  mov     rdi, [rdi+10h]
0x1800249ee  mov     ecx, 18h; dwBytes
0x1800249f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800249f8  mov     rbx, rax
0x1800249fb  mov     [rbp+arg_8], rax
0x1800249ff  test    rax, rax
0x180024a02  jz      short loc_180024A3B
0x180024a04  mov     [rbp+arg_10], rax
0x180024a08  mov     eax, 2
0x180024a0d  mov     [rbx], eax
0x180024a0f  mov     [rbx+4], eax
0x180024a12  mov     dword ptr [rbx+8], 10h
0x180024a19  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180024a20  mov     [rbx+10h], rax
0x180024a24  test    rdi, rdi
0x180024a27  jz      loc_180024BE7
0x180024a2d  mov     rdx, rdi; unsigned __int16 *
0x180024a30  mov     rcx, rbx; this
0x180024a33  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180024a38  nop
0x180024a39  jmp     short loc_180024A3E
0x180024a3b  mov     rbx, r12
0x180024a3e  mov     [rbp+var_30], rbx
0x180024a42  mov     [rbp+var_28], r12d
0x180024a46  mov     eax, r12d
0x180024a49  mov     ecx, 1
0x180024a4e  test    rbx, rbx
0x180024a51  cmovnz  eax, ecx
0x180024a54  mov     [rbp+var_28], eax
0x180024a57  lea     rdx, [rbp+var_30]
0x180024a5b  mov     rcx, rsi; this
0x180024a5e  call    ?CreateLogicalImage@Configuration@@QEAAPEAVLogicalImage@@AEAV?$NewHolder@VImage@@@@@Z; Configuration::CreateLogicalImage(NewHolder<Image> &)
0x180024a63  mov     r13, rax
0x180024a66  mov     [rsp+60h+var_40], r12; struct ICorSvcLogger *
0x180024a6b  xor     r9d, r9d; struct LogicalImage *
0x180024a6e  mov     r8, rdi; unsigned __int16 *
0x180024a71  mov     rdx, rsi; struct Configuration *
0x180024a74  mov     rcx, r15; this
0x180024a77  call    ?GetSvcWorkerForConfiguration@CCorSvcMgr@@AEAAPEAVWorkerPoolItem@1@PEAVConfiguration@@PEBGPEAVLogicalImage@@PEAUICorSvcLogger@@@Z; CCorSvcMgr::GetSvcWorkerForConfiguration(Configuration *,ushort const *,LogicalImage *,ICorSvcLogger *)
0x180024a7c  mov     r14, rax
0x180024a7f  mov     [rbp+var_10], rax
0x180024a83  mov     [rbp+var_8], r12d
0x180024a87  mov     eax, r12d
0x180024a8a  test    r14, r14
0x180024a8d  mov     ecx, 1
0x180024a92  cmovnz  eax, ecx
0x180024a95  mov     dword ptr [rbp+arg_8], eax
0x180024a98  mov     [rbp+var_8], eax
0x180024a9b  mov     rdi, [r14+18h]
0x180024a9f  mov     rbx, [r13+8]
0x180024aa3  mov     [rbp+arg_10], r12
0x180024aa7  mov     rcx, rbx; this
0x180024aaa  call    ?GetRootPath@Configuration@@QEAAPEBGXZ; Configuration::GetRootPath(void)
0x180024aaf  mov     rcx, rax; psz
0x180024ab2  call    cs:__imp_SysAllocString
0x180024ab8  mov     rcx, rax
0x180024abb  mov     [rbp+bstrString], rax
0x180024abf  mov     [rbp+var_18], r12d
0x180024ac3  test    rax, rax
0x180024ac6  mov     eax, 1
0x180024acb  cmovnz  r12d, eax
0x180024acf  mov     [rbp+var_18], r12d
0x180024ad3  mov     rax, [rdi]
0x180024ad6  lea     r9, [rbp+arg_10]
0x180024ada  mov     r8d, [rbx+18h]
0x180024ade  mov     rdx, rcx
0x180024ae1  mov     rcx, rdi
0x180024ae4  mov     rax, [rax+38h]
0x180024ae8  call    cs:__guard_dispatch_icall_fptr
0x180024aee  test    eax, eax
0x180024af0  js      loc_180024BDC
0x180024af6  mov     rbx, [rbp+arg_10]
0x180024afa  test    r12d, r12d
0x180024afd  jz      short loc_180024B12
0x180024aff  mov     rcx, [rbp+bstrString]; bstrString
0x180024b03  call    cs:__imp_SysFreeString
0x180024b09  xor     r12d, r12d
0x180024b0c  mov     [rbp+var_18], r12d
0x180024b10  jmp     short loc_180024B15
0x180024b12  xor     r12d, r12d
0x180024b15  mov     [rbp+bstrString], rbx
0x180024b19  mov     [rbp+var_18], r12d
0x180024b1d  mov     edi, r12d
0x180024b20  test    rbx, rbx
0x180024b23  mov     eax, 1
0x180024b28  cmovnz  edi, eax
0x180024b2b  mov     [rbp+var_18], edi
0x180024b2e  mov     r8, rbx; struct ICorSvcDependencies *
0x180024b31  mov     rdx, r13; struct LogicalImage *
0x180024b34  mov     rcx, r15; this
0x180024b37  call    ?ExpandLogicalImage@CCorSvcMgr@@AEAAXPEAVLogicalImage@@PEAUICorSvcDependencies@@@Z; CCorSvcMgr::ExpandLogicalImage(LogicalImage *,ICorSvcDependencies *)
0x180024b3c  test    dword ptr [r13+10h], 0FFFFFFFBh
0x180024b44  jnz     short loc_180024B51
0x180024b46  xor     edx, edx
0x180024b48  mov     rcx, rsi
0x180024b4b  call    ?SetStatus@Node@@QEAAXW4EntryStatus@@@Z; Node::SetStatus(EntryStatus)
0x180024b50  nop
0x180024b51  test    edi, edi
0x180024b53  jz      short loc_180024B6E
0x180024b55  test    rbx, rbx
0x180024b58  jz      short loc_180024B6A
0x180024b5a  mov     rax, [rbx]
0x180024b5d  mov     rcx, rbx
0x180024b60  mov     rax, [rax+10h]
0x180024b64  call    cs:__guard_dispatch_icall_fptr
0x180024b6a  mov     [rbp+var_18], r12d
0x180024b6e  cmp     dword ptr [rbp+arg_8], r12d
0x180024b72  jz      short loc_180024B8D
0x180024b74  mov     rcx, r14; this
0x180024b77  call    ??1WorkerPoolItem@CCorSvcMgr@@QEAA@XZ; CCorSvcMgr::WorkerPoolItem::~WorkerPoolItem(void)
0x180024b7c  mov     edx, 40h ; '@'; unsigned __int64
0x180024b81  mov     rcx, r14; void *
0x180024b84  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024b89  mov     [rbp+var_8], r12d
0x180024b8d  cmp     [rbp+var_28], r12d
0x180024b91  jz      short loc_180024BC4
0x180024b93  mov     rbx, [rbp+var_30]
0x180024b97  mov     [rbp+arg_8], rbx
0x180024b9b  test    rbx, rbx
0x180024b9e  jz      short loc_180024BC0
0x180024ba0  mov     [rbp+arg_8], rbx
0x180024ba4  test    byte ptr [rbx+8], 8
0x180024ba8  jz      short loc_180024BB3
0x180024baa  mov     rcx, [rbx+10h]; lpMem
0x180024bae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024bb3  mov     edx, 18h; unsigned __int64
0x180024bb8  mov     rcx, rbx; void *
0x180024bbb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024bc0  mov     [rbp+var_28], r12d
0x180024bc4  mov     rbx, [rsp+60h+arg_0]
0x180024bcc  add     rsp, 60h
0x180024bd0  pop     r15
0x180024bd2  pop     r14
0x180024bd4  pop     r13
0x180024bd6  pop     r12
0x180024bd8  pop     rdi
0x180024bd9  pop     rsi
0x180024bda  pop     rbp
0x180024bdb  retn
0x180024bdc  mov     ecx, 80131F00h; int
0x180024be1  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180024be7  mov     ecx, 800700A0h; int
0x180024bec  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
