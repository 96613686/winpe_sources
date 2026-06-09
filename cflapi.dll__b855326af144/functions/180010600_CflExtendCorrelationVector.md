# CflExtendCorrelationVector

- ea: `0x180010600`
- end: `0x1800106ed`
- name: `CflExtendCorrelationVector`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002490`
- `0x1800067c4`
- `0x180008420`
- `0x180008a68`
- `0x180010600`
- `0x180029614`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800106b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800106b9`

## string_xrefs

- `0x180010652`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CflExtendCorrelationVector(_QWORD *a1)
{
  int v2; // eax
  __int64 v3; // r8
  const char *v4; // r9
  unsigned int v5; // ebx
  __int64 v7; // rbx
  __int128 *v8; // rdx
  __int64 *v9; // rax
  HLOCAL hMem; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+28h] [rbp-40h] BYREF
  __int128 v12; // [rsp+30h] [rbp-38h] BYREF
  __int64 v13; // [rsp+40h] [rbp-28h]
  unsigned __int64 v14; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v12 = 0;
  v13 = 0;
  v14 = 15;
  LOBYTE(v12) = 0;
  v2 = CflApiNew::ExtendCorrelationVector((CflApiNew *)&v12);
  v5 = v2;
  if ( v2 >= 0 )
  {
    v7 = 0;
    v11 = 0;
    if ( v13 )
    {
      v8 = &v12;
      if ( v14 > 0xF )
        v8 = (__int128 *)v12;
      v9 = wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
             &hMem,
             v8,
             v3,
             v4);
      if ( &v11 != v9 )
      {
        v7 = *v9;
        *v9 = 0;
      }
      if ( hMem )
        LocalFree(hMem);
    }
    *a1 = v7;
    std::string::~string(&v12);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20A,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
      (const char *)(unsigned int)v2,
      (int)hMem);
    std::string::~string(&v12);
    return v5;
  }
}

```

## disassembly

```asm
0x180010600  mov     r11, rsp
0x180010603  mov     [r11+10h], rbx
0x180010607  push    rdi
0x180010608  sub     rsp, 60h
0x18001060c  mov     rax, cs:__security_cookie
0x180010613  xor     rax, rsp
0x180010616  mov     [rsp+68h+var_18], rax
0x18001061b  mov     rdi, rcx
0x18001061e  xorps   xmm0, xmm0
0x180010621  movups  [rsp+68h+var_38], xmm0
0x180010626  mov     qword ptr [r11-28h], 0
0x18001062e  mov     qword ptr [r11-20h], 0Fh
0x180010636  mov     byte ptr [rsp+68h+var_38], 0
0x18001063b  lea     rcx, [r11-38h]; this
0x18001063f  call    ?ExtendCorrelationVector@CflApiNew@@YAJPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CflApiNew::ExtendCorrelationVector(std::string *)
0x180010644  mov     ebx, eax
0x180010646  test    eax, eax
0x180010648  jns     short loc_180010672
0x18001064a  mov     rcx, [rsp+68h]; this
0x18001064f  mov     r9d, eax; char *
0x180010652  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x180010659  mov     edx, 20Ah; void *
0x18001065e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010663  nop
0x180010664  lea     rcx, [rsp+68h+var_38]
0x180010669  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001066e  mov     eax, ebx
0x180010670  jmp     short loc_1800106D4
0x180010672  xor     ebx, ebx
0x180010674  mov     [rsp+68h+var_40], rbx
0x180010679  cmp     [rsp+68h+var_28], rbx
0x18001067e  jz      short loc_1800106BF
0x180010680  lea     rdx, [rsp+68h+var_38]
0x180010685  cmp     [rsp+68h+var_20], 0Fh
0x18001068b  cmova   rdx, qword ptr [rsp+68h+var_38]
0x180010691  lea     rcx, [rsp+68h+hMem]
0x180010696  call    ??$make_unique_ansistring@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@0@PEBD_K@Z; wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(char const *,unsigned __int64)
0x18001069b  lea     rcx, [rsp+68h+var_40]
0x1800106a0  cmp     rcx, rax
0x1800106a3  jz      short loc_1800106AF
0x1800106a5  mov     rbx, [rax]
0x1800106a8  mov     qword ptr [rax], 0
0x1800106af  mov     rcx, [rsp+68h+hMem]; hMem
0x1800106b4  test    rcx, rcx
0x1800106b7  jz      short loc_1800106BF
0x1800106b9  call    cs:__imp_LocalFree
0x1800106bf  mov     [rdi], rbx
0x1800106c2  lea     rcx, [rsp+68h+var_38]
0x1800106c7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800106cc  xor     eax, eax
0x1800106ce  jmp     short loc_1800106D4
0x1800106d0  mov     eax, dword ptr [rsp+68h+hMem]
0x1800106d4  mov     rcx, [rsp+68h+var_18]
0x1800106d9  xor     rcx, rsp; StackCookie
0x1800106dc  call    __security_check_cookie
0x1800106e1  mov     rbx, [rsp+68h+arg_8]
0x1800106e6  add     rsp, 60h
0x1800106ea  pop     rdi
0x1800106eb  retn
```
