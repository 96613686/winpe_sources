# CDpSearchProtocol::CreateAccessorEx(ushort const *,_AUTHENTICATION_INFO *,_INCREMENTAL_ACCESS_INFO *,_ITEM_INFO *,tagBLOB const *,IUrlAccessor * *)

- ea: `0x180004020`
- end: `0x1800041e7`
- name: `?CreateAccessorEx@CDpSearchProtocol@@UEAAJPEBGPEAU_AUTHENTICATION_INFO@@PEAU_INCREMENTAL_ACCESS_INFO@@PEAU_ITEM_INFO@@PEBUtagBLOB@@PEAPEAUIUrlAccessor@@@Z`
- size: `455`
- prototype: `__int64 __fastcall(CDpSearchProtocol *this, unsigned __int16 *, struct _AUTHENTICATION_INFO *, struct _INCREMENTAL_ACCESS_INFO *, struct _ITEM_INFO *, struct tagBLOB *, struct IUrlAccessor **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180004020`
- `0x18000487c`
- `0x1800067b4`
- `0x180006dc0`
- `0x180007a40`
- `0x180007cc4`
- `0x1800093b4`
- `0x18000ab60`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800040d1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800040d1`
- `ADVAPI32!RegSetKeyValueW` at `0x18000410e`
- `ADVAPI32!RegSetKeyValueW` at `0x18000410e`

## pseudocode

```c
__int64 __fastcall CDpSearchProtocol::CreateAccessorEx(
        CDpSearchProtocol *this,
        unsigned __int16 *a2,
        struct _AUTHENTICATION_INFO *a3,
        struct _INCREMENTAL_ACCESS_INFO *a4,
        struct _ITEM_INFO *a5,
        struct tagBLOB *a6,
        struct IUrlAccessor **a7)
{
  __int64 result; // rax
  __int64 v9; // r8
  char IsRoot; // di
  LSTATUS v11; // eax
  signed int v12; // edi
  CDpUrlAccessor *v13; // rdi
  int v14; // esi
  CDpUrlAccessor *v15; // [rsp+30h] [rbp-D8h] BYREF
  int Data; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int16 *v17; // [rsp+40h] [rbp-C8h]
  struct IUrlAccessor **v18; // [rsp+48h] [rbp-C0h]
  void *Src[3]; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 v20; // [rsp+70h] [rbp-98h]
  LPVOID ppv[10]; // [rsp+80h] [rbp-88h] BYREF

  v17 = a2;
  v15 = (CDpUrlAccessor *)a6;
  v18 = a7;
  if ( !a6 )
    return 2147500035LL;
  DpSearch::DpSearch(ppv);
  v20 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  std::wstring::assign(Src, a2);
  IsRoot = DpSearch::IsRoot(ppv, Src);
  if ( v20 >= 8 )
    operator delete(Src[0]);
  if ( IsRoot )
  {
    Data = 1;
    v11 = RegSetKeyValueW(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
            L"SearchRebuildRequired",
            4u,
            &Data,
            4u);
    v12 = v11;
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    DpSearch::~DpSearch((DpSearch *)ppv);
    if ( v12 >= 0 )
      return 266755;
    else
      return (unsigned int)v12;
  }
  else
  {
    DpSearch::~DpSearch((DpSearch *)ppv);
    v15 = 0;
    result = ATL::CComObject<CDpUrlAccessor>::CreateInstance(&v15);
    if ( (int)result >= 0 )
    {
      v13 = v15;
      if ( v15 )
        (*(void (__fastcall **)(CDpUrlAccessor *))(*(_QWORD *)v15 + 8LL))(v15);
      v14 = CDpUrlAccessor::Init(v13, a2, (const unsigned __int16 *)a6->pBlobData);
      if ( v14 >= 0 )
      {
        *v18 = (struct IUrlAccessor *)v13;
      }
      else if ( v13 )
      {
        (*(void (__fastcall **)(CDpUrlAccessor *))(*(_QWORD *)v13 + 16LL))(v13);
      }
      return (unsigned int)v14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004020  push    rbx
0x180004022  push    rsi
0x180004023  push    rdi
0x180004024  push    r14
0x180004026  sub     rsp, 0E8h
0x18000402d  mov     rax, cs:__security_cookie
0x180004034  xor     rax, rsp
0x180004037  mov     [rsp+108h+var_38], rax
0x18000403f  mov     rsi, rdx
0x180004042  mov     [rsp+108h+var_C8], rdx
0x180004047  mov     r14, [rsp+108h+arg_28]
0x18000404f  mov     [rsp+108h+var_D8], r14
0x180004054  mov     rax, [rsp+108h+arg_30]
0x18000405c  mov     [rsp+108h+var_C0], rax
0x180004061  xor     ebx, ebx
0x180004063  test    r14, r14
0x180004066  jnz     short loc_180004072
0x180004068  mov     eax, 80004003h
0x18000406d  jmp     loc_1800041C9
0x180004072  lea     rcx, [rsp+108h+ppv]; ppv
0x18000407a  call    ??0DpSearch@@QEAA@XZ; DpSearch::DpSearch(void)
0x18000407f  nop
0x180004080  mov     [rsp+108h+var_98], 7
0x180004089  mov     [rsp+108h+var_A0], rbx
0x18000408e  mov     word ptr [rsp+108h+Src], bx
0x180004093  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004097  inc     r8
0x18000409a  cmp     [rsi+r8*2], bx
0x18000409f  jnz     short loc_180004097
0x1800040a1  mov     rdx, rsi; void *
0x1800040a4  lea     rcx, [rsp+108h+Src]; Src
0x1800040a9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800040ae  nop
0x1800040af  lea     rdx, [rsp+108h+Src]
0x1800040b4  lea     rcx, [rsp+108h+ppv]
0x1800040bc  call    ?IsRoot@DpSearch@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DpSearch::IsRoot(std::wstring const &)
0x1800040c1  mov     dil, al
0x1800040c4  cmp     [rsp+108h+var_98], 8
0x1800040ca  jb      short loc_1800040D7
0x1800040cc  mov     rcx, [rsp+108h+Src]
0x1800040d1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800040d7  test    dil, dil
0x1800040da  jz      short loc_180004145
0x1800040dc  mov     [rsp+108h+Data], 1
0x1800040e4  mov     r9d, 4; dwType
0x1800040ea  mov     [rsp+108h+cbData], r9d; cbData
0x1800040ef  lea     rax, [rsp+108h+Data]
0x1800040f4  mov     [rsp+108h+lpData], rax; lpData
0x1800040f9  lea     r8, ValueName; "SearchRebuildRequired"
0x180004100  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180004107  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000410e  call    cs:__imp_RegSetKeyValueW
0x180004114  mov     edi, eax
0x180004116  test    eax, eax
0x180004118  jle     short loc_180004123
0x18000411a  movzx   edi, ax
0x18000411d  or      edi, 80070000h
0x180004123  lea     rcx, [rsp+108h+ppv]; this
0x18000412b  call    ??1DpSearch@@QEAA@XZ; DpSearch::~DpSearch(void)
0x180004130  test    edi, edi
0x180004132  jns     short loc_18000413B
0x180004134  mov     eax, edi
0x180004136  jmp     loc_1800041C9
0x18000413b  mov     eax, 41203h
0x180004140  jmp     loc_1800041C9
0x180004145  lea     rcx, [rsp+108h+ppv]; this
0x18000414d  call    ??1DpSearch@@QEAA@XZ; DpSearch::~DpSearch(void)
0x180004152  nop
0x180004153  jmp     short loc_180004161
0x180004155  mov     r14, [rsp+108h+var_D8]
0x18000415a  mov     rsi, [rsp+108h+var_C8]
0x18000415f  xor     ebx, ebx
0x180004161  mov     [rsp+108h+var_D8], rbx
0x180004166  lea     rcx, [rsp+108h+var_D8]
0x18000416b  call    ?CreateInstance@?$CComObject@VCDpUrlAccessor@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CDpUrlAccessor>::CreateInstance(ATL::CComObject<CDpUrlAccessor> * *)
0x180004170  test    eax, eax
0x180004172  js      short loc_1800041C9
0x180004174  mov     rdi, [rsp+108h+var_D8]
0x180004179  mov     [rsp+108h+var_D8], rdi
0x18000417e  test    rdi, rdi
0x180004181  jz      short loc_180004193
0x180004183  mov     rax, [rdi]
0x180004186  mov     rcx, rdi
0x180004189  mov     rax, [rax+8]
0x18000418d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004192  nop
0x180004193  mov     r8, [r14+8]; unsigned __int16 *
0x180004197  mov     rdx, rsi; unsigned __int16 *
0x18000419a  mov     rcx, rdi; this
0x18000419d  call    ?Init@CDpUrlAccessor@@QEAAJPEBG0@Z; CDpUrlAccessor::Init(ushort const *,ushort const *)
0x1800041a2  mov     esi, eax
0x1800041a4  test    eax, eax
0x1800041a6  jns     short loc_1800041BF
0x1800041a8  test    rdi, rdi
0x1800041ab  jz      short loc_1800041BD
0x1800041ad  mov     rdx, [rdi]
0x1800041b0  mov     rcx, rdi
0x1800041b3  mov     rax, [rdx+10h]
0x1800041b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041bc  nop
0x1800041bd  jmp     short loc_1800041C7
0x1800041bf  mov     rax, [rsp+108h+var_C0]
0x1800041c4  mov     [rax], rdi
0x1800041c7  mov     eax, esi
0x1800041c9  mov     rcx, [rsp+108h+var_38]
0x1800041d1  xor     rcx, rsp; StackCookie
0x1800041d4  call    __security_check_cookie
0x1800041d9  add     rsp, 0E8h
0x1800041e0  pop     r14
0x1800041e2  pop     rdi
0x1800041e3  pop     rsi
0x1800041e4  pop     rbx
0x1800041e5  retn
```
