# CMVEngine::GetUIStatus(IMVUIStatus * *)

- ea: `0x180013f30`
- end: `0x1800141e3`
- name: `?GetUIStatus@CMVEngine@@UEAAJPEAPEAUIMVUIStatus@@@Z`
- size: `691`
- prototype: `__int64 __fastcall(CMVEngine *this, LPVOID *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800098dc`
- `0x18000adec`
- `0x180013f30`
- `0x180033630`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001405d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800140c1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014159`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001418c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001405d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800140c1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014159`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001418c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001412b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001412b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180014093`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180014093`

## string_xrefs

- `0x180013f9c`: `UIStatusClsid`
- `0x180014029`: `UIStatusClsid`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMVEngine::GetUIStatus(CMVEngine *this, LPVOID *a2)
{
  int Configuration; // eax
  unsigned int v5; // edi
  OLECHAR *v6; // rdi
  int v7; // eax
  unsigned int v8; // esi
  HRESULT v9; // eax
  unsigned int v10; // esi
  HRESULT v11; // eax
  unsigned int v12; // esi
  LPVOID v13; // rcx
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  LPVOID v16; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v17; // [rsp+38h] [rbp-40h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v19; // [rsp+50h] [rbp-28h]
  GUID pclsid; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( a2 )
  {
    *a2 = 0;
    v16 = 0;
    v17 = 0;
    Configuration = MvGetConfiguration((char *)L"UIStatusClsid", 0, &v17);
    v5 = Configuration;
    if ( Configuration >= 0 )
    {
      pclsid = 0;
      *(_OWORD *)lpsz = 0;
      v19 = 0;
      if ( (unsigned __int64)v17 >> 1 )
        std::vector<unsigned short>::_Reallocate(lpsz, (unsigned __int64)v17 >> 1);
      v6 = (OLECHAR *)lpsz[0];
      v7 = MvGetConfiguration((char *)L"UIStatusClsid", (PVOID)lpsz[0], &v17);
      v8 = v7;
      if ( v7 >= 0 )
      {
        v9 = CLSIDFromString(v6, &pclsid);
        v10 = v9;
        if ( v9 >= 0 )
        {
          v11 = CoCreateInstance(&pclsid, 0, 1u, &GUID_58754514_926f_4982_b685_ffee82d95cbb, &v16);
          v12 = v11;
          if ( v11 >= 0 )
          {
            if ( v6 )
              operator delete(v6);
            *a2 = v16;
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC82,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
              (const char *)(unsigned int)v11,
              ppva);
            if ( v6 )
              operator delete(v6);
            v13 = v16;
            if ( v16 )
            {
              v16 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
            }
            return v12;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC81,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
            (const char *)(unsigned int)v9,
            ppv);
          if ( v6 )
            operator delete(v6);
          return v10;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC80,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
          (const char *)(unsigned int)v7,
          ppv);
        if ( v6 )
          operator delete(v6);
        return v8;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC79,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
        (const char *)(unsigned int)Configuration,
        ppv);
      return v5;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC72,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)0x80004003LL,
      ppv);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180013f30  mov     [rsp+arg_0], rsi
0x180013f35  mov     [rsp+arg_10], rdi
0x180013f3a  push    r14
0x180013f3c  sub     rsp, 70h
0x180013f40  mov     rax, cs:__security_cookie
0x180013f47  xor     rax, rsp
0x180013f4a  mov     [rsp+78h+var_10], rax
0x180013f4f  mov     r14, rdx
0x180013f52  test    rdx, rdx
0x180013f55  jnz     short loc_180013F7D
0x180013f57  mov     rcx, [rsp+78h]; this
0x180013f5c  mov     r9d, 80004003h; char *
0x180013f62  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180013f69  mov     edx, 0C72h; void *
0x180013f6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013f73  mov     eax, 80004003h
0x180013f78  jmp     loc_1800141C3
0x180013f7d  mov     qword ptr [rdx], 0
0x180013f84  mov     [rsp+78h+var_48], 0
0x180013f8d  mov     [rsp+78h+var_40], 0
0x180013f95  lea     r8, [rsp+78h+var_40]; unsigned int *
0x180013f9a  xor     edx, edx; pvData
0x180013f9c  lea     rcx, ?gc_wszUIStatusClsid@@3QBGB; "UIStatusClsid"
0x180013fa3  call    ?MvGetConfiguration@@YAJPEBGPEAEPEAK@Z; MvGetConfiguration(ushort const *,uchar *,ulong *)
0x180013fa8  mov     edi, eax
0x180013faa  test    eax, eax
0x180013fac  jns     short loc_180013FEF
0x180013fae  mov     rcx, [rsp+78h]; this
0x180013fb3  mov     r9d, eax; char *
0x180013fb6  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180013fbd  mov     edx, 0C79h; void *
0x180013fc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013fc7  nop
0x180013fc8  mov     rcx, [rsp+78h+var_48]
0x180013fcd  test    rcx, rcx
0x180013fd0  jz      short loc_180013FE8
0x180013fd2  mov     [rsp+78h+var_48], 0
0x180013fdb  mov     rax, [rcx]
0x180013fde  mov     rax, [rax+10h]
0x180013fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fe7  nop
0x180013fe8  mov     eax, edi
0x180013fea  jmp     loc_1800141C3
0x180013fef  xorps   xmm0, xmm0
0x180013ff2  movups  xmmword ptr [rsp+78h+pclsid.Data1], xmm0
0x180013ff7  xorps   xmm1, xmm1
0x180013ffa  movdqu  xmmword ptr [rsp+78h+lpsz], xmm1
0x180014000  mov     [rsp+78h+var_28], 0
0x180014009  mov     edx, [rsp+78h+var_40]
0x18001400d  shr     rdx, 1
0x180014010  jz      short loc_18001401C
0x180014012  lea     rcx, [rsp+78h+lpsz]
0x180014017  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18001401c  lea     r8, [rsp+78h+var_40]; unsigned int *
0x180014021  mov     rdi, [rsp+78h+lpsz]
0x180014026  mov     rdx, rdi; pvData
0x180014029  lea     rcx, ?gc_wszUIStatusClsid@@3QBGB; "UIStatusClsid"
0x180014030  call    ?MvGetConfiguration@@YAJPEBGPEAEPEAK@Z; MvGetConfiguration(ushort const *,uchar *,ulong *)
0x180014035  mov     esi, eax
0x180014037  test    eax, eax
0x180014039  jns     short loc_18001408B
0x18001403b  mov     rcx, [rsp+78h]; this
0x180014040  mov     r9d, eax; char *
0x180014043  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001404a  mov     edx, 0C80h; void *
0x18001404f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014054  nop
0x180014055  test    rdi, rdi
0x180014058  jz      short loc_180014064
0x18001405a  mov     rcx, rdi
0x18001405d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014063  nop
0x180014064  mov     rcx, [rsp+78h+var_48]
0x180014069  test    rcx, rcx
0x18001406c  jz      short loc_180014084
0x18001406e  mov     [rsp+78h+var_48], 0
0x180014077  mov     rax, [rcx]
0x18001407a  mov     rax, [rax+10h]
0x18001407e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014083  nop
0x180014084  mov     eax, esi
0x180014086  jmp     loc_1800141C3
0x18001408b  lea     rdx, [rsp+78h+pclsid]; pclsid
0x180014090  mov     rcx, rdi; lpsz
0x180014093  call    cs:__imp_CLSIDFromString
0x180014099  mov     esi, eax
0x18001409b  test    eax, eax
0x18001409d  jns     short loc_1800140EF
0x18001409f  mov     rcx, [rsp+78h]; this
0x1800140a4  mov     r9d, eax; char *
0x1800140a7  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800140ae  mov     edx, 0C81h; void *
0x1800140b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800140b8  nop
0x1800140b9  test    rdi, rdi
0x1800140bc  jz      short loc_1800140C8
0x1800140be  mov     rcx, rdi
0x1800140c1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800140c7  nop
0x1800140c8  mov     rcx, [rsp+78h+var_48]
0x1800140cd  test    rcx, rcx
0x1800140d0  jz      short loc_1800140E8
0x1800140d2  mov     [rsp+78h+var_48], 0
0x1800140db  mov     rax, [rcx]
0x1800140de  mov     rax, [rax+10h]
0x1800140e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140e7  nop
0x1800140e8  mov     eax, esi
0x1800140ea  jmp     loc_1800141C3
0x1800140ef  mov     rcx, [rsp+78h+var_48]
0x1800140f4  test    rcx, rcx
0x1800140f7  jz      short loc_18001410F
0x1800140f9  mov     [rsp+78h+var_48], 0
0x180014102  mov     rax, [rcx]
0x180014105  mov     rax, [rax+10h]
0x180014109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001410e  nop
0x18001410f  lea     rax, [rsp+78h+var_48]
0x180014114  mov     qword ptr [rsp+78h+ppv], rax; int
0x180014119  lea     r9, _GUID_58754514_926f_4982_b685_ffee82d95cbb; riid
0x180014120  xor     edx, edx; pUnkOuter
0x180014122  lea     r8d, [rdx+1]; dwClsContext
0x180014126  lea     rcx, [rsp+78h+pclsid]; rclsid
0x18001412b  call    cs:__imp_CoCreateInstance
0x180014131  mov     esi, eax
0x180014133  test    eax, eax
0x180014135  jns     short loc_180014184
0x180014137  mov     rcx, [rsp+78h]; this
0x18001413c  mov     r9d, eax; char *
0x18001413f  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180014146  mov     edx, 0C82h; void *
0x18001414b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014150  nop
0x180014151  test    rdi, rdi
0x180014154  jz      short loc_180014160
0x180014156  mov     rcx, rdi
0x180014159  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001415f  nop
0x180014160  mov     rcx, [rsp+78h+var_48]
0x180014165  test    rcx, rcx
0x180014168  jz      short loc_180014180
0x18001416a  mov     [rsp+78h+var_48], 0
0x180014173  mov     rax, [rcx]
0x180014176  mov     rax, [rax+10h]
0x18001417a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001417f  nop
0x180014180  mov     eax, esi
0x180014182  jmp     short loc_1800141C3
0x180014184  test    rdi, rdi
0x180014187  jz      short loc_180014193
0x180014189  mov     rcx, rdi
0x18001418c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014192  nop
0x180014193  mov     rax, [rsp+78h+var_48]
0x180014198  mov     [r14], rax
0x18001419b  xor     eax, eax
0x18001419d  jmp     short loc_1800141C3
0x18001419f  mov     rcx, [rsp+78h+var_48]
0x1800141a4  test    rcx, rcx
0x1800141a7  jz      short loc_1800141BF
0x1800141a9  mov     [rsp+78h+var_48], 0
0x1800141b2  mov     rax, [rcx]
0x1800141b5  mov     rax, [rax+10h]
0x1800141b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141be  nop
0x1800141bf  mov     eax, [rsp+78h+var_40]
0x1800141c3  mov     rcx, [rsp+78h+var_10]
0x1800141c8  xor     rcx, rsp; StackCookie
0x1800141cb  call    __security_check_cookie
0x1800141d0  lea     r11, [rsp+78h+var_8]
0x1800141d5  mov     rsi, [r11+10h]
0x1800141d9  mov     rdi, [r11+20h]
0x1800141dd  mov     rsp, r11
0x1800141e0  pop     r14
0x1800141e2  retn
```
