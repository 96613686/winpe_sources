# ProvOperations::RemoveAllPackageMetadata(ushort * *)

- ea: `0x180015f60`
- end: `0x1800161dd`
- name: `?RemoveAllPackageMetadata@ProvOperations@@UEAAJPEAPEAG@Z`
- size: `637`
- prototype: `__int64 __fastcall(ProvOperations *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007674`
- `0x18000de84`
- `0x180015f60`
- `0x18001af18`
- `0x18001b388`
- `0x180028df4`
- `0x180028e74`
- `0x180028f28`
- `0x1800296a0`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180016132`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016187`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016132`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016187`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800160d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800160d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProvOperations::RemoveAllPackageMetadata(ProvOperations *this, unsigned __int16 **a2)
{
  __int64 result; // rax
  _QWORD *v5; // rbx
  _QWORD *v6; // rdi
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned __int16 **v9; // rdx
  int v10; // r13d
  const unsigned __int16 *v11; // r14
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // r12
  unsigned __int16 *v14; // rdi
  signed int v15; // ebx
  unsigned __int16 **v16; // [rsp+20h] [rbp-B8h]
  unsigned __int64 *v17; // [rsp+28h] [rbp-B0h]
  unsigned int v18; // [rsp+30h] [rbp-A8h]
  _QWORD *v19; // [rsp+48h] [rbp-90h] BYREF
  _QWORD *v20; // [rsp+50h] [rbp-88h]
  _BYTE v21[40]; // [rsp+60h] [rbp-78h] BYREF
  unsigned __int16 *v22[3]; // [rsp+88h] [rbp-50h] BYREF
  unsigned __int64 v23; // [rsp+A0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  if ( a2 )
  {
    *a2 = 0;
    PackageCollector::PackageCollector((PackageCollector *)v21);
    try
    {
      PackageCollector::AddDefaultSearchPaths((PackageCollector *)v21);
      PackageCollector::Search((__int64)v21, &v19);
      v5 = v19;
      v6 = v20;
      if ( v19 == v20 )
      {
        std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>((__int64)&v19);
        PackageCollector::~PackageCollector((PackageCollector *)v21);
        result = 1;
      }
      else
      {
        while ( 1 )
        {
          (*(void (__fastcall **)(_QWORD, unsigned __int16 **))(*(_QWORD *)*v5 + 16LL))(*v5, v22);
          v9 = v22;
          if ( v23 >= 8 )
            v9 = (unsigned __int16 **)v22[0];
          v10 = (*(__int64 (__fastcall **)(ProvOperations *, unsigned __int16 **))(*(_QWORD *)this + 40LL))(this, v9);
          if ( v10 < 0 )
            break;
          if ( v23 >= 8 )
            operator delete(v22[0]);
          if ( ++v5 == v6 )
          {
            std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>((__int64)&v19);
            PackageCollector::~PackageCollector((PackageCollector *)v21);
            result = 0;
            goto LABEL_32;
          }
        }
        v11 = (const unsigned __int16 *)v22;
        if ( v23 >= 8 )
          v11 = v22[0];
        v12 = -1;
        do
          ++v12;
        while ( v11[v12] );
        v13 = v12 + 1;
        if ( v12 + 1 >= v12 && is_mul_ok(v13, 2u) )
        {
          v14 = (unsigned __int16 *)CoTaskMemAlloc(2 * v13);
          v15 = v14 == 0 ? 0x8007000E : 0;
          if ( v14 )
            StringCchCopyNExW(v14, v12 + 1, v11, v12, v16, v17, v18);
        }
        else
        {
          v15 = -2147024362;
          v14 = 0;
        }
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x261,
            (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
            (const char *)(unsigned int)v15,
            (int)v16);
        *a2 = v14;
        if ( v23 >= 8 )
          operator delete(v22[0]);
        v23 = 7;
        v22[2] = 0;
        LOWORD(v22[0]) = 0;
        std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>((__int64)&v19);
        PackageCollector::~PackageCollector((PackageCollector *)v21);
        result = (unsigned int)v10;
      }
    }
    catch ( ... )
    {
      result = (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x268, v7, v8);
    }
LABEL_32:
    ;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24C,
      (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
      (const char *)0x80004003LL,
      (int)v16);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x180015f60  mov     [rsp+arg_10], rbx
0x180015f65  mov     [rsp+arg_18], rsi
0x180015f6a  push    rdi
0x180015f6b  push    r12
0x180015f6d  push    r13
0x180015f6f  push    r14
0x180015f71  push    r15
0x180015f73  sub     rsp, 0B0h
0x180015f7a  mov     rax, cs:__security_cookie
0x180015f81  xor     rax, rsp
0x180015f84  mov     [rsp+0D8h+var_30], rax
0x180015f8c  mov     r15, rdx
0x180015f8f  mov     rsi, rcx
0x180015f92  xor     eax, eax
0x180015f94  test    rdx, rdx
0x180015f97  jnz     short loc_180015FC1
0x180015f99  mov     rcx, [rsp+0D8h]; this
0x180015fa1  mov     ebx, 80004003h
0x180015fa6  mov     r9d, ebx; char *
0x180015fa9  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x180015fb0  mov     edx, 24Ch; void *
0x180015fb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015fba  mov     eax, ebx
0x180015fbc  jmp     loc_18001619A
0x180015fc1  mov     [rdx], rax
0x180015fc4  lea     rcx, [rsp+0D8h+var_78]; this
0x180015fc9  call    ??0PackageCollector@@QEAA@XZ; PackageCollector::PackageCollector(void)
0x180015fce  nop
0x180015fcf  lea     rcx, [rsp+0D8h+var_78]; this
0x180015fd4  call    ?AddDefaultSearchPaths@PackageCollector@@QEAAXXZ; PackageCollector::AddDefaultSearchPaths(void)
0x180015fd9  lea     rdx, [rsp+0D8h+var_90]
0x180015fde  lea     rcx, [rsp+0D8h+var_78]
0x180015fe3  call    ?Search@PackageCollector@@QEAA?AV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@XZ; PackageCollector::Search(void)
0x180015fe8  nop
0x180015fe9  mov     rbx, [rsp+0D8h+var_90]
0x180015fee  mov     rdi, [rsp+0D8h+var_88]
0x180015ff3  cmp     rbx, rdi
0x180015ff6  jnz     short loc_180016038
0x180015ff8  lea     rcx, [rsp+0D8h+var_90]
0x180015ffd  call    ??1?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(void)
0x180016002  nop
0x180016003  lea     rcx, [rsp+0D8h+var_78]; this
0x180016008  call    ??1PackageCollector@@UEAA@XZ; PackageCollector::~PackageCollector(void)
0x18001600d  mov     eax, 1
0x180016012  jmp     loc_18001619A
0x180016017  cmp     rbx, rdi
0x18001601a  jnz     short loc_180016038
0x18001601c  lea     rcx, [rsp+0D8h+var_90]
0x180016021  call    ??1?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(void)
0x180016026  nop
0x180016027  lea     rcx, [rsp+0D8h+var_78]; this
0x18001602c  call    ??1PackageCollector@@UEAA@XZ; PackageCollector::~PackageCollector(void)
0x180016031  xor     eax, eax
0x180016033  jmp     loc_18001619A
0x180016038  mov     rcx, [rbx]
0x18001603b  mov     rax, [rcx]
0x18001603e  lea     rdx, [rsp+0D8h+var_50]
0x180016046  mov     rax, [rax+10h]
0x18001604a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001604f  nop
0x180016050  mov     rax, [rsi]
0x180016053  lea     rdx, [rsp+0D8h+var_50]
0x18001605b  cmp     [rsp+0D8h+var_38], 8
0x180016064  cmovnb  rdx, [rsp+0D8h+var_50]
0x18001606d  mov     rcx, rsi
0x180016070  mov     rax, [rax+28h]
0x180016074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016079  mov     r13d, eax
0x18001607c  xor     ecx, ecx
0x18001607e  test    eax, eax
0x180016080  jns     loc_180016174
0x180016086  lea     r14, [rsp+0D8h+var_50]
0x18001608e  cmp     [rsp+0D8h+var_38], 8
0x180016097  cmovnb  r14, [rsp+0D8h+var_50]
0x1800160a0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800160a4  inc     rsi
0x1800160a7  cmp     [r14+rsi*2], cx
0x1800160ac  jnz     short loc_1800160A4
0x1800160ae  mov     [rsp+0D8h+var_98], rcx
0x1800160b3  lea     r12, [rsi+1]
0x1800160b7  cmp     r12, rsi
0x1800160ba  jb      short loc_180016104
0x1800160bc  mov     [rsp+0D8h+var_98], rcx
0x1800160c1  mov     eax, 2
0x1800160c6  mul     r12
0x1800160c9  test    rdx, rdx
0x1800160cc  jnz     short loc_180016104
0x1800160ce  mov     rcx, rax; cb
0x1800160d1  call    cs:__imp_CoTaskMemAlloc
0x1800160d7  mov     rdi, rax
0x1800160da  mov     [rsp+0D8h+var_98], rax
0x1800160df  neg     rax
0x1800160e2  sbb     ebx, ebx
0x1800160e4  not     ebx
0x1800160e6  and     ebx, 8007000Eh
0x1800160ec  test    rdi, rdi
0x1800160ef  jz      short loc_18001610C
0x1800160f1  mov     r9, rsi; unsigned __int64
0x1800160f4  mov     r8, r14; unsigned __int16 *
0x1800160f7  mov     rdx, r12; unsigned __int64
0x1800160fa  mov     rcx, rdi; unsigned __int16 *
0x1800160fd  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180016102  jmp     short loc_18001610C
0x180016104  mov     ebx, 80070216h
0x180016109  mov     rdi, rcx
0x18001610c  mov     rcx, [rsp+0D8h]; this
0x180016114  test    ebx, ebx
0x180016116  js      loc_1800161C7
0x18001611c  mov     [r15], rdi
0x18001611f  cmp     [rsp+0D8h+var_38], 8
0x180016128  jb      short loc_180016138
0x18001612a  mov     rcx, [rsp+0D8h+var_50]
0x180016132  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180016138  mov     [rsp+0D8h+var_38], 7
0x180016144  mov     [rsp+0D8h+var_40], 0
0x180016150  xor     eax, eax
0x180016152  mov     word ptr [rsp+0D8h+var_50], ax
0x18001615a  lea     rcx, [rsp+0D8h+var_90]
0x18001615f  call    ??1?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(void)
0x180016164  nop
0x180016165  lea     rcx, [rsp+0D8h+var_78]; this
0x18001616a  call    ??1PackageCollector@@UEAA@XZ; PackageCollector::~PackageCollector(void)
0x18001616f  mov     eax, r13d
0x180016172  jmp     short loc_18001619A
0x180016174  cmp     [rsp+0D8h+var_38], 8
0x18001617d  jb      short loc_18001618D
0x18001617f  mov     rcx, [rsp+0D8h+var_50]
0x180016187  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001618d  add     rbx, 8
0x180016191  jmp     loc_180016017
0x180016196  mov     eax, dword ptr [rsp+0D8h+var_98]
0x18001619a  mov     rcx, [rsp+0D8h+var_30]
0x1800161a2  xor     rcx, rsp; StackCookie
0x1800161a5  call    __security_check_cookie
0x1800161aa  lea     r11, [rsp+0D8h+var_28]
0x1800161b2  mov     rbx, [r11+40h]
0x1800161b6  mov     rsi, [r11+48h]
0x1800161ba  mov     rsp, r11
0x1800161bd  pop     r15
0x1800161bf  pop     r14
0x1800161c1  pop     r13
0x1800161c3  pop     r12
0x1800161c5  pop     rdi
0x1800161c6  retn
0x1800161c7  mov     r9d, ebx; char *
0x1800161ca  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x1800161d1  mov     edx, 261h; void *
0x1800161d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
