# ProvStateContext::CreatePackageContext(ProvSource const &)

- ea: `0x180035fb0`
- end: `0x1800361b0`
- name: `?CreatePackageContext@ProvStateContext@@QEAAAEAUPackageContext@@AEBVProvSource@@@Z`
- size: `512`
- prototype: `struct PackageContext *__fastcall(ProvStateContext *__hidden this, const struct ProvSource *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18001eeec`

## callees

- `0x1800021b4`
- `0x1800111d4`
- `0x1800349c4`
- `0x180035378`
- `0x180035fb0`
- `0x180036780`
- `0x18003b2b4`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800360be`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003611e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180036141`
- `msvcrt!??3@YAXPEAX@Z` at `0x180036176`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003617f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800360be`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003611e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180036141`
- `msvcrt!??3@YAXPEAX@Z` at `0x180036176`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003617f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct PackageContext *__fastcall ProvStateContext::CreatePackageContext(
        ProvStateContext *this,
        const struct ProvSource *a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rbx
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  _QWORD *v8; // rsi
  char *v9; // rax
  __int64 v10; // r8
  __int64 *v11; // rax
  __int64 v12; // rsi
  PackageEnroller **v13; // rbx
  PackageEnroller *v14; // rdi
  PackageEnroller **v16; // [rsp+30h] [rbp-50h] BYREF
  void *v17[3]; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int64 v18; // [rsp+50h] [rbp-30h]
  void *v19[3]; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v20; // [rsp+70h] [rbp-10h]

  v4 = operator new(0x20u);
  v5 = (__int64)v4;
  if ( v4 )
  {
    *v4 = 0;
    v4[2] = 0;
    v4[3] = 0;
    v4[1] = 0;
  }
  else
  {
    v5 = 0;
  }
  v16 = (PackageEnroller **)v5;
  (*(void (__fastcall **)(const struct ProvSource *, void **))(*(_QWORD *)a2 + 16LL))(a2, v19);
  *(_QWORD *)v5 = a2;
  *(_QWORD *)(v5 + 16) = this;
  v6 = operator new(0x58u);
  v7 = v6;
  v17[0] = v6;
  if ( v6 )
  {
    *v6 = 0;
    v6[1] = 0;
    (*(void (__fastcall **)(const struct ProvSource *, _QWORD *))(*(_QWORD *)a2 + 16LL))(a2, v6 + 2);
    v7[9] = 7;
    v7[8] = 0;
    *((_WORD *)v7 + 24) = 0;
    v7[10] = (*(__int64 (__fastcall **)(const struct ProvSource *))(*(_QWORD *)a2 + 40LL))(a2);
    PackageEnroller::Initalize((PackageEnroller *)v7);
  }
  else
  {
    v7 = 0;
  }
  v8 = *(_QWORD **)(v5 + 8);
  if ( v7 != v8 )
  {
    if ( v8 )
    {
      PackageEnroller::~PackageEnroller(*(PackageEnroller **)(v5 + 8));
      operator delete(v8);
    }
    *(_QWORD *)(v5 + 8) = v7;
  }
  v9 = (char *)std::_Tree_buy<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>::_Buynode<std::wstring,std::unique_ptr<PackageContext>>(
                 (__int64)this + 64,
                 (__int64)v19,
                 (__int64 *)&v16);
  std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PackageContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>,0>>::_Insert_nohint<std::pair<std::wstring const,std::unique_ptr<PackageContext>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<PackageContext>>,void *> *>(
    (_QWORD *)this + 8,
    (__int64)v17,
    v10,
    (__int64)(v9 + 32),
    v9);
  v11 = (__int64 *)(*(__int64 (__fastcall **)(const struct ProvSource *, void **))(*(_QWORD *)a2 + 16LL))(a2, v17);
  v12 = *std::map<std::wstring,std::unique_ptr<PackageContext>>::at((__int64)this + 64, v11);
  if ( v18 >= 8 )
    operator delete(v17[0]);
  v18 = 7;
  v17[2] = 0;
  LOWORD(v17[0]) = 0;
  if ( v20 >= 8 )
    operator delete(v19[0]);
  v20 = 7;
  v19[2] = 0;
  LOWORD(v19[0]) = 0;
  v13 = v16;
  if ( v16 )
  {
    v14 = v16[1];
    if ( v14 )
    {
      PackageEnroller::~PackageEnroller(v16[1]);
      operator delete(v14);
    }
    operator delete(v13);
  }
  return (struct PackageContext *)v12;
}

```

## disassembly

```asm
0x180035fb0  mov     [rsp-28h+arg_10], rbx
0x180035fb5  mov     [rsp-28h+arg_18], rsi
0x180035fba  push    rbp
0x180035fbb  push    rdi
0x180035fbc  push    r13
0x180035fbe  push    r14
0x180035fc0  push    r15
0x180035fc2  mov     rbp, rsp
0x180035fc5  sub     rsp, 80h
0x180035fcc  mov     rax, cs:__security_cookie
0x180035fd3  xor     rax, rsp
0x180035fd6  mov     [rbp+var_8], rax
0x180035fda  mov     r14, rdx
0x180035fdd  mov     r15, rcx
0x180035fe0  mov     ecx, 20h ; ' '; Size
0x180035fe5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035fea  mov     rbx, rax
0x180035fed  test    rax, rax
0x180035ff0  jz      short loc_180036013
0x180035ff2  mov     qword ptr [rax], 0
0x180035ff9  mov     qword ptr [rax+10h], 0
0x180036001  mov     qword ptr [rax+18h], 0
0x180036009  mov     qword ptr [rax+8], 0
0x180036011  jmp     short loc_180036015
0x180036013  xor     ebx, ebx
0x180036015  mov     [rbp+var_50], rbx
0x180036019  mov     rax, [r14]
0x18003601c  lea     rdx, [rbp+var_28]
0x180036020  mov     rcx, r14
0x180036023  mov     rax, [rax+10h]
0x180036027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003602c  nop
0x18003602d  mov     [rbx], r14
0x180036030  mov     [rbx+10h], r15
0x180036034  mov     ecx, 58h ; 'X'; Size
0x180036039  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003603e  mov     rdi, rax
0x180036041  mov     [rbp+var_48], rax
0x180036045  mov     r13d, 7
0x18003604b  test    rax, rax
0x18003604e  jz      short loc_1800360A3
0x180036050  mov     qword ptr [rax], 0
0x180036057  mov     qword ptr [rax+8], 0
0x18003605f  mov     rcx, [r14]
0x180036062  lea     rdx, [rax+10h]
0x180036066  mov     rax, [rcx+10h]
0x18003606a  mov     rcx, r14
0x18003606d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036072  nop
0x180036073  mov     [rdi+48h], r13
0x180036077  mov     qword ptr [rdi+40h], 0
0x18003607f  xor     eax, eax
0x180036081  mov     [rdi+30h], ax
0x180036085  mov     rax, [r14]
0x180036088  mov     rcx, r14
0x18003608b  mov     rax, [rax+28h]
0x18003608f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036094  mov     [rdi+50h], rax
0x180036098  mov     rcx, rdi; this
0x18003609b  call    ?Initalize@PackageEnroller@@AEAAXXZ; PackageEnroller::Initalize(void)
0x1800360a0  nop
0x1800360a1  jmp     short loc_1800360A5
0x1800360a3  xor     edi, edi
0x1800360a5  mov     rsi, [rbx+8]
0x1800360a9  cmp     rdi, rsi
0x1800360ac  jz      short loc_1800360C8
0x1800360ae  test    rsi, rsi
0x1800360b1  jz      short loc_1800360C4
0x1800360b3  mov     rcx, rsi; this
0x1800360b6  call    ??1PackageEnroller@@QEAA@XZ; PackageEnroller::~PackageEnroller(void)
0x1800360bb  mov     rcx, rsi
0x1800360be  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800360c4  mov     [rbx+8], rdi
0x1800360c8  lea     rbx, [r15+40h]
0x1800360cc  lea     r8, [rbp+var_50]
0x1800360d0  lea     rdx, [rbp+var_28]
0x1800360d4  mov     rcx, rbx
0x1800360d7  call    ??$_Buynode@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAX@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@1@@Z; std::_Tree_buy<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>::_Buynode<std::wstring,std::unique_ptr<PackageContext>>(std::wstring &&,std::unique_ptr<PackageContext> &&)
0x1800360dc  lea     r9, [rax+20h]
0x1800360e0  mov     [rsp+80h+var_60], rax
0x1800360e5  lea     rdx, [rbp+var_48]
0x1800360e9  mov     rcx, rbx
0x1800360ec  call    ??$_Insert_nohint@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PackageContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>,0>>::_Insert_nohint<std::pair<std::wstring const,std::unique_ptr<PackageContext>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<PackageContext>>,void *> *>(bool,std::pair<std::wstring const,std::unique_ptr<PackageContext>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<PackageContext>>,void *> *)
0x1800360f1  mov     rax, [r14]
0x1800360f4  lea     rdx, [rbp+var_48]
0x1800360f8  mov     rcx, r14
0x1800360fb  mov     rax, [rax+10h]
0x1800360ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036104  nop
0x180036105  mov     rdx, rax
0x180036108  mov     rcx, rbx
0x18003610b  call    ?at@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@2@@std@@QEAAAEAV?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::map<std::wstring,std::unique_ptr<PackageContext>>::at(std::wstring const &)
0x180036110  mov     rsi, [rax]
0x180036113  cmp     [rbp+var_30], 8
0x180036118  jb      short loc_180036124
0x18003611a  mov     rcx, [rbp+var_48]
0x18003611e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180036124  mov     [rbp+var_30], r13
0x180036128  mov     [rbp+var_38], 0
0x180036130  xor     eax, eax
0x180036132  mov     word ptr [rbp+var_48], ax
0x180036136  cmp     [rbp+var_10], 8
0x18003613b  jb      short loc_180036147
0x18003613d  mov     rcx, [rbp+var_28]
0x180036141  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180036147  mov     [rbp+var_10], r13
0x18003614b  mov     [rbp+var_18], 0
0x180036153  xor     eax, eax
0x180036155  mov     word ptr [rbp+var_28], ax
0x180036159  mov     rbx, [rbp+var_50]
0x18003615d  test    rbx, rbx
0x180036160  jz      short loc_180036185
0x180036162  mov     rdi, [rbx+8]
0x180036166  test    rdi, rdi
0x180036169  jz      short loc_18003617C
0x18003616b  mov     rcx, rdi; this
0x18003616e  call    ??1PackageEnroller@@QEAA@XZ; PackageEnroller::~PackageEnroller(void)
0x180036173  mov     rcx, rdi
0x180036176  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003617c  mov     rcx, rbx
0x18003617f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180036185  mov     rax, rsi
0x180036188  mov     rcx, [rbp+var_8]
0x18003618c  xor     rcx, rsp; StackCookie
0x18003618f  call    __security_check_cookie
0x180036194  lea     r11, [rsp+80h+var_s0]
0x18003619c  mov     rbx, [r11+40h]
0x1800361a0  mov     rsi, [r11+48h]
0x1800361a4  mov     rsp, r11
0x1800361a7  pop     r15
0x1800361a9  pop     r14
0x1800361ab  pop     r13
0x1800361ad  pop     rdi
0x1800361ae  pop     rbp
0x1800361af  retn
```
