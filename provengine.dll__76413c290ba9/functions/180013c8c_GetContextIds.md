# GetContextIds

- ea: `0x180013c8c`
- end: `0x180013dda`
- name: `GetContextIds`
- size: `334`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a6fc`

## callees

- `0x18000b030`
- `0x180013c8c`
- `0x180021c5c`
- `0x180021cf4`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013cee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013daf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013cee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013daf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall GetContextIds(_QWORD *a1, __int64 a2)
{
  __int64 *v3; // rdx
  __int64 v4; // r14
  __int64 (__fastcall *v5)(__int64, LPVOID *, LPVOID *, __int64); // rdi
  __int64 v6; // rbx
  int v7; // eax
  unsigned int v8; // ebx
  int i; // eax
  _QWORD *v10; // r14
  _QWORD *v11; // rcx
  char *v12; // rdx
  unsigned __int64 v13; // r8
  unsigned int v14; // edi
  int v16; // [rsp+20h] [rbp-38h]
  LPVOID pv[4]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v3 = *(__int64 **)(a2 + 16);
  v4 = *v3;
  if ( *v3 )
  {
    *(_OWORD *)pv = 0;
    v5 = *(__int64 (__fastcall **)(__int64, LPVOID *, LPVOID *, __int64))(*(_QWORD *)v4 + 96LL);
    v6 = (unsigned __int64)(v3 + 5) & -(__int64)(*((_DWORD *)v3 + 11) != 0);
    CoTaskMemFree(0);
    *(_OWORD *)pv = 0;
    v7 = v5(v4, pv, &pv[1], v6);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x506,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
        (const char *)(unsigned int)v7,
        v16);
    v8 = 0;
    for ( i = (int)pv[1]; v8 < LODWORD(pv[1]); i = (int)pv[1] )
    {
      v10 = pv[0];
      if ( a1[1] == a1[2] )
        std::vector<std::wstring>::_Reserve(a1);
      v11 = (_QWORD *)a1[1];
      v12 = (char *)v10[v8];
      v11[3] = 7;
      v11[2] = 0;
      *(_WORD *)v11 = 0;
      if ( *(_WORD *)v12 )
      {
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)&v12[2 * v13] );
      }
      else
      {
        v13 = 0;
      }
      std::wstring::assign(v11, v12, v13);
      a1[1] += 32LL;
      ++v8;
    }
    v14 = 0;
    if ( i )
    {
      do
      {
        CoTaskMemFree(*((LPVOID *)pv[0] + v14));
        *((_QWORD *)pv[0] + v14++) = 0;
      }
      while ( v14 < LODWORD(pv[1]) );
    }
    CoTaskMemFree(pv[0]);
  }
  return a1;
}

```

## disassembly

```asm
0x180013c8c  mov     [rsp-30h+arg_0], rcx
0x180013c91  push    rbp
0x180013c92  push    rbx
0x180013c93  push    rsi
0x180013c94  push    rdi
0x180013c95  push    r14
0x180013c97  push    r15
0x180013c99  mov     rbp, rsp
0x180013c9c  sub     rsp, 58h
0x180013ca0  mov     rsi, rcx
0x180013ca3  xor     r15d, r15d
0x180013ca6  mov     [rbp+var_28], r15d
0x180013caa  mov     [rcx], r15
0x180013cad  mov     [rcx+8], r15
0x180013cb1  mov     [rcx+10h], r15
0x180013cb5  mov     [rbp+var_28], 1
0x180013cbc  mov     rdx, [rdx+10h]
0x180013cc0  mov     r14, [rdx]
0x180013cc3  test    r14, r14
0x180013cc6  jz      loc_180013DB5
0x180013ccc  xorps   xmm0, xmm0
0x180013ccf  movups  xmmword ptr [rbp+pv], xmm0
0x180013cd3  mov     rax, [r14]
0x180013cd6  mov     rdi, [rax+60h]
0x180013cda  mov     eax, [rdx+2Ch]
0x180013cdd  add     rdx, 28h ; '('
0x180013ce1  neg     eax
0x180013ce3  sbb     rbx, rbx
0x180013ce6  and     rbx, rdx
0x180013ce9  movq    rcx, xmm0; pv
0x180013cee  call    cs:__imp_CoTaskMemFree
0x180013cf4  xorps   xmm0, xmm0
0x180013cf7  movups  xmmword ptr [rbp+pv], xmm0
0x180013cfb  mov     r9, rbx
0x180013cfe  lea     r8, [rbp+pv+8]
0x180013d02  lea     rdx, [rbp+pv]
0x180013d06  mov     rcx, r14
0x180013d09  mov     rax, rdi
0x180013d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d11  mov     rcx, [rbp+30h]; this
0x180013d15  test    eax, eax
0x180013d17  js      loc_180013DC5
0x180013d1d  mov     ebx, r15d
0x180013d20  mov     rax, [rbp+pv+8]
0x180013d24  test    eax, eax
0x180013d26  jz      short loc_180013D85
0x180013d28  mov     edi, ebx
0x180013d2a  mov     r14, [rbp+pv]
0x180013d2e  mov     rax, [rsi+10h]
0x180013d32  cmp     [rsi+8], rax
0x180013d36  jnz     short loc_180013D40
0x180013d38  mov     rcx, rsi
0x180013d3b  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x180013d40  mov     rcx, [rsi+8]; void *
0x180013d44  mov     rdx, [r14+rdi*8]; Src
0x180013d48  mov     qword ptr [rcx+18h], 7
0x180013d50  mov     [rcx+10h], r15
0x180013d54  mov     [rcx], r15w
0x180013d58  cmp     [rdx], r15w
0x180013d5c  jnz     short loc_180013D63
0x180013d5e  mov     r8, r15
0x180013d61  jmp     short loc_180013D71
0x180013d63  or      r8, 0FFFFFFFFFFFFFFFFh
0x180013d67  inc     r8
0x180013d6a  cmp     [rdx+r8*2], r15w
0x180013d6f  jnz     short loc_180013D67
0x180013d71  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180013d76  add     qword ptr [rsi+8], 20h ; ' '
0x180013d7b  inc     ebx
0x180013d7d  mov     rax, [rbp+pv+8]
0x180013d81  cmp     ebx, eax
0x180013d83  jb      short loc_180013D28
0x180013d85  mov     edi, r15d
0x180013d88  test    eax, eax
0x180013d8a  jz      short loc_180013DAB
0x180013d8c  mov     ebx, edi
0x180013d8e  mov     rcx, [rbp+pv]
0x180013d92  mov     rcx, [rcx+rbx*8]; pv
0x180013d96  call    cs:__imp_CoTaskMemFree
0x180013d9c  mov     rax, [rbp+pv]
0x180013da0  mov     [rax+rbx*8], r15
0x180013da4  inc     edi
0x180013da6  cmp     edi, dword ptr [rbp+pv+8]
0x180013da9  jb      short loc_180013D8C
0x180013dab  mov     rcx, [rbp+pv]; pv
0x180013daf  call    cs:__imp_CoTaskMemFree
0x180013db5  mov     rax, rsi
0x180013db8  add     rsp, 58h
0x180013dbc  pop     r15
0x180013dbe  pop     r14
0x180013dc0  pop     rdi
0x180013dc1  pop     rsi
0x180013dc2  pop     rbx
0x180013dc3  pop     rbp
0x180013dc4  retn
0x180013dc5  mov     r9d, eax; char *
0x180013dc8  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180013dcf  mov     edx, 506h; void *
0x180013dd4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
