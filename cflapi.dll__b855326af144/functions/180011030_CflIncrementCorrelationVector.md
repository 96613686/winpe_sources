# CflIncrementCorrelationVector

- ea: `0x180011030`
- end: `0x18001111d`
- name: `CflIncrementCorrelationVector`
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
- `0x180011030`
- `0x18002aee8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800110e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800110e9`

## string_xrefs

- `0x180011082`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CflIncrementCorrelationVector(_QWORD *a1)
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
  v2 = CflApiNew::IncrementCorrelationVector((CflApiNew *)&v12);
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
      (void *)0x1F2,
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
0x180011030  mov     r11, rsp
0x180011033  mov     [r11+10h], rbx
0x180011037  push    rdi
0x180011038  sub     rsp, 60h
0x18001103c  mov     rax, cs:__security_cookie
0x180011043  xor     rax, rsp
0x180011046  mov     [rsp+68h+var_18], rax
0x18001104b  mov     rdi, rcx
0x18001104e  xorps   xmm0, xmm0
0x180011051  movups  [rsp+68h+var_38], xmm0
0x180011056  mov     qword ptr [r11-28h], 0
0x18001105e  mov     qword ptr [r11-20h], 0Fh
0x180011066  mov     byte ptr [rsp+68h+var_38], 0
0x18001106b  lea     rcx, [r11-38h]; this
0x18001106f  call    ?IncrementCorrelationVector@CflApiNew@@YAJPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CflApiNew::IncrementCorrelationVector(std::string *)
0x180011074  mov     ebx, eax
0x180011076  test    eax, eax
0x180011078  jns     short loc_1800110A2
0x18001107a  mov     rcx, [rsp+68h]; this
0x18001107f  mov     r9d, eax; char *
0x180011082  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x180011089  mov     edx, 1F2h; void *
0x18001108e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011093  nop
0x180011094  lea     rcx, [rsp+68h+var_38]
0x180011099  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001109e  mov     eax, ebx
0x1800110a0  jmp     short loc_180011104
0x1800110a2  xor     ebx, ebx
0x1800110a4  mov     [rsp+68h+var_40], rbx
0x1800110a9  cmp     [rsp+68h+var_28], rbx
0x1800110ae  jz      short loc_1800110EF
0x1800110b0  lea     rdx, [rsp+68h+var_38]
0x1800110b5  cmp     [rsp+68h+var_20], 0Fh
0x1800110bb  cmova   rdx, qword ptr [rsp+68h+var_38]
0x1800110c1  lea     rcx, [rsp+68h+hMem]
0x1800110c6  call    ??$make_unique_ansistring@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@0@PEBD_K@Z; wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(char const *,unsigned __int64)
0x1800110cb  lea     rcx, [rsp+68h+var_40]
0x1800110d0  cmp     rcx, rax
0x1800110d3  jz      short loc_1800110DF
0x1800110d5  mov     rbx, [rax]
0x1800110d8  mov     qword ptr [rax], 0
0x1800110df  mov     rcx, [rsp+68h+hMem]; hMem
0x1800110e4  test    rcx, rcx
0x1800110e7  jz      short loc_1800110EF
0x1800110e9  call    cs:__imp_LocalFree
0x1800110ef  mov     [rdi], rbx
0x1800110f2  lea     rcx, [rsp+68h+var_38]
0x1800110f7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800110fc  xor     eax, eax
0x1800110fe  jmp     short loc_180011104
0x180011100  mov     eax, dword ptr [rsp+68h+hMem]
0x180011104  mov     rcx, [rsp+68h+var_18]
0x180011109  xor     rcx, rsp; StackCookie
0x18001110c  call    __security_check_cookie
0x180011111  mov     rbx, [rsp+68h+arg_8]
0x180011116  add     rsp, 60h
0x18001111a  pop     rdi
0x18001111b  retn
```
