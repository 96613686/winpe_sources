# VmPerfCreateInstance

- ea: `0x180007b7c`
- end: `0x180007d62`
- name: `VmPerfCreateInstance`
- size: `486`
- prototype: `_QWORD *__fastcall(_QWORD *, void *, const GUID *, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180006da8`

## callees

- `0x180001950`
- `0x180002100`
- `0x180002bd0`
- `0x180005a80`
- `0x1800069f4`
- `0x180006d5c`
- `0x180007a48`
- `0x180007b7c`
- `0x180007d68`
- `0x180007f3c`
- `0x180007fd4`
- `0x180008044`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180007c38`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180007c38`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180007c8a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180007c8a`

## pseudocode

```c
_QWORD *__fastcall VmPerfCreateInstance(_QWORD *a1, void *a2, const GUID *a3, __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // r9
  _WORD *v10; // rcx
  __int64 v11; // rsi
  size_t v12; // rsi
  __int64 v13; // rbx
  PCWSTR *v14; // rcx
  _OWORD *v15; // rax
  __int64 v16; // r8
  const WCHAR *v17; // r8
  PPERF_COUNTERSET_INSTANCE Instance; // rsi
  const char *v19; // r9
  __int64 v20; // rbx
  unsigned __int16 *v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // eax
  void *v25; // rdx
  unsigned int v26; // r8d
  PCWSTR Name[2]; // [rsp+40h] [rbp-49h] BYREF
  __int128 v28; // [rsp+50h] [rbp-39h]
  _QWORD v29[2]; // [rsp+60h] [rbp-29h] BYREF
  __int64 v30; // [rsp+70h] [rbp-19h]
  unsigned __int64 v31; // [rsp+78h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+4Fh]

  std::wstring::wstring(v29);
  v30 = 0;
  v10 = v29;
  if ( v31 > 7 )
    v10 = (_WORD *)v29[0];
  *v10 = 0;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(v9 + 2 * v11) );
  v12 = v11 + 1;
  v13 = v30;
  if ( v30 )
    v12 += v30 + 1;
  else
    v13 = 0;
  *(_OWORD *)Name = 0;
  v28 = 0u;
  std::wstring::_Construct<0,unsigned short>(Name, v8, v12);
  if ( v13 )
  {
    std::wstring::c_str(v29);
    v22 = (unsigned __int16 *)std::wstring::c_str(Name);
    v23 = StringCchPrintfW(v22, v12, L"%s:%s");
    v24 = wil::verify_hresult<long>(v23);
    wil::details::in1diag3::Throw_Hr(retaddr, v25, v26, (const char *)v24, a4);
  }
  v14 = Name;
  if ( *((_QWORD *)&v28 + 1) > 7u )
    v14 = (PCWSTR *)Name[0];
  _o_wcscpy_s(v14, v12, a4);
  VmPerfpCleanNameString(Name);
  v15 = operator new(0x30u);
  *v15 = 0;
  v15[1] = 0;
  v15[2] = 0;
  std::wstring::wstring((char *)v15 + 8);
  *a1 = v16;
  v17 = (const WCHAR *)Name;
  if ( *((_QWORD *)&v28 + 1) > 7u )
    v17 = Name[0];
  Instance = PerfCreateInstance(a2, a3, v17, 0);
  if ( !Instance )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xC1,
      (int)"onecore\\hv\\hvhostsvc\\lib\\hvstatspanel.cpp",
      v19);
  v20 = *a1 + 8LL;
  if ( (PCWSTR *)v20 != Name )
  {
    std::wstring::_Tidy_deallocate(*a1 + 8LL);
    *(_OWORD *)v20 = *(_OWORD *)Name;
    *(_OWORD *)(v20 + 16) = v28;
    *(_QWORD *)&v28 = 0;
    *((_QWORD *)&v28 + 1) = 7;
    LOWORD(Name[0]) = 0;
  }
  *(_QWORD *)*a1 = Instance;
  std::wstring::_Tidy_deallocate((__int64)Name);
  std::wstring::_Tidy_deallocate((__int64)v29);
  return a1;
}

```

## disassembly

```asm
0x180007b7c  push    rbp
0x180007b7e  push    rbx
0x180007b7f  push    rsi
0x180007b80  push    rdi
0x180007b81  push    r12
0x180007b83  push    r13
0x180007b85  push    r14
0x180007b87  push    r15
0x180007b89  lea     rbp, [rsp-0Fh]
0x180007b8e  sub     rsp, 98h
0x180007b95  mov     rax, cs:__security_cookie
0x180007b9c  xor     rax, rsp
0x180007b9f  mov     [rbp+47h+var_50], rax
0x180007ba3  mov     r14, r9
0x180007ba6  mov     r12, r8
0x180007ba9  mov     r15, rdx
0x180007bac  mov     rdi, rcx
0x180007baf  mov     [rbp+47h+var_98], rcx
0x180007bb3  xor     r13d, r13d
0x180007bb6  mov     [rbp+47h+var_A0], r13d
0x180007bba  lea     rcx, [rbp+47h+var_70]
0x180007bbe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180007bc3  nop
0x180007bc4  mov     [rbp+47h+var_60], r13
0x180007bc8  lea     rcx, [rbp+47h+var_70]
0x180007bcc  cmp     [rbp+47h+var_58], 7
0x180007bd1  cmova   rcx, [rbp+47h+var_70]
0x180007bd6  mov     [rcx], r13w
0x180007bda  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007bde  inc     rsi
0x180007be1  cmp     [r9+rsi*2], r13w
0x180007be6  jnz     short loc_180007BDE
0x180007be8  inc     rsi
0x180007beb  mov     rbx, [rbp+47h+var_60]
0x180007bef  test    rbx, rbx
0x180007bf2  jnz     short loc_180007BF9
0x180007bf4  mov     rbx, r13
0x180007bf7  jmp     short loc_180007BFF
0x180007bf9  inc     rsi
0x180007bfc  add     rsi, rbx
0x180007bff  xorps   xmm0, xmm0
0x180007c02  movups  xmmword ptr [rbp+47h+Name], xmm0
0x180007c06  mov     qword ptr [rbp+47h+var_80], r13
0x180007c0a  mov     qword ptr [rbp+47h+var_80+8], r13
0x180007c0e  mov     r8, rsi
0x180007c11  lea     rcx, [rbp+47h+Name]
0x180007c15  call    ??$_Construct@$0A@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXG_K@Z; std::wstring::_Construct<0,ushort>(ushort,unsigned __int64)
0x180007c1a  nop
0x180007c1b  test    rbx, rbx
0x180007c1e  jnz     loc_180007D22
0x180007c24  lea     rcx, [rbp+47h+Name]
0x180007c28  cmp     qword ptr [rbp+47h+var_80+8], 7
0x180007c2d  cmova   rcx, [rbp+47h+Name]
0x180007c32  mov     r8, r14
0x180007c35  mov     rdx, rsi
0x180007c38  call    cs:__imp__o_wcscpy_s
0x180007c3e  lea     rcx, [rbp+47h+Name]
0x180007c42  call    VmPerfpCleanNameString
0x180007c47  lea     ecx, [rbx+30h]; Size
0x180007c4a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007c4f  mov     r8, rax
0x180007c52  xorps   xmm0, xmm0
0x180007c55  movups  xmmword ptr [rax], xmm0
0x180007c58  movups  xmmword ptr [rax+10h], xmm0
0x180007c5c  movups  xmmword ptr [rax+20h], xmm0
0x180007c60  lea     rcx, [rax+8]
0x180007c64  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180007c69  mov     [rdi], r8
0x180007c6c  mov     [rbp+47h+var_A0], 3
0x180007c73  lea     r8, [rbp+47h+Name]
0x180007c77  cmp     qword ptr [rbp+47h+var_80+8], 7
0x180007c7c  cmova   r8, [rbp+47h+Name]; Name
0x180007c81  xor     r9d, r9d; Id
0x180007c84  mov     rdx, r12; CounterSetGuid
0x180007c87  mov     rcx, r15; ProviderHandle
0x180007c8a  call    cs:__imp_PerfCreateInstance
0x180007c90  mov     rsi, rax
0x180007c93  mov     rcx, [rbp+4Fh]; this
0x180007c97  test    rax, rax
0x180007c9a  jz      short loc_180007D10
0x180007c9c  mov     rbx, [rdi]
0x180007c9f  add     rbx, 8
0x180007ca3  lea     rax, [rbp+47h+Name]
0x180007ca7  cmp     rbx, rax
0x180007caa  jz      short loc_180007CD4
0x180007cac  mov     rcx, rbx
0x180007caf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180007cb4  movups  xmm0, xmmword ptr [rbp+47h+Name]
0x180007cb8  movups  xmmword ptr [rbx], xmm0
0x180007cbb  movups  xmm1, [rbp+47h+var_80]
0x180007cbf  movups  xmmword ptr [rbx+10h], xmm1
0x180007cc3  mov     qword ptr [rbp+47h+var_80], r13
0x180007cc7  mov     qword ptr [rbp+47h+var_80+8], 7
0x180007ccf  mov     word ptr [rbp+47h+Name], r13w
0x180007cd4  mov     rcx, [rdi]
0x180007cd7  mov     [rcx], rsi
0x180007cda  lea     rcx, [rbp+47h+Name]
0x180007cde  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180007ce3  nop
0x180007ce4  lea     rcx, [rbp+47h+var_70]
0x180007ce8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180007ced  mov     rax, rdi
0x180007cf0  mov     rcx, [rbp+47h+var_50]
0x180007cf4  xor     rcx, rsp; StackCookie
0x180007cf7  call    __security_check_cookie
0x180007cfc  add     rsp, 98h
0x180007d03  pop     r15
0x180007d05  pop     r14
0x180007d07  pop     r13
0x180007d09  pop     r12
0x180007d0b  pop     rdi
0x180007d0c  pop     rsi
0x180007d0d  pop     rbx
0x180007d0e  pop     rbp
0x180007d0f  retn
0x180007d10  lea     r8, aOnecoreHvHvhos; "onecore\\hv\\hvhostsvc\\lib\\hvstatspan"...
0x180007d17  mov     edx, 0C1h; void *
0x180007d1c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180007d22  lea     rcx, [rbp+47h+var_70]
0x180007d26  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180007d2b  mov     r9, rax
0x180007d2e  lea     rcx, [rbp+47h+Name]
0x180007d32  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180007d37  mov     qword ptr [rsp+0D0h+var_B0], r14; int
0x180007d3c  lea     r8, aSS; "%s:%s"
0x180007d43  mov     rdx, rsi; unsigned __int64
0x180007d46  mov     rcx, rax; unsigned __int16 *
0x180007d49  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007d4e  mov     ecx, eax
0x180007d50  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180007d55  mov     r9d, eax; char *
0x180007d58  mov     rcx, [rbp+4Fh]; this
0x180007d5c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
