# CTraceController::GenerateTraceFilePath(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180023880`
- end: `0x18002398a`
- name: `?GenerateTraceFilePath@CTraceController@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x18000c478`
- `0x18000ec4c`
- `0x18001bfc0`
- `0x180023a2c`

## callees

- `0x180006d58`
- `0x18000bca0`
- `0x18000bcd0`
- `0x18000c454`
- `0x180023880`
- `0x18002c802`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800238ed`
- `KERNEL32!GetLastError` at `0x1800238ed`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800238e3`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800238e3`

## string_xrefs

- `0x1800238dc`: `%windir%\system32\NDF`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CTraceController::GenerateTraceFilePath(_DWORD *a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // ebx
  signed int LastError; // eax
  __time64_t *TickCount; // rax
  __int64 v9; // rax
  __int64 v11; // [rsp+30h] [rbp-268h]
  _BYTE v12[8]; // [rsp+38h] [rbp-260h] BYREF
  const ATL::CAtlException *v13; // [rsp+40h] [rbp-258h] BYREF
  WCHAR Dst[264]; // [rsp+50h] [rbp-248h] BYREF

  v6 = -2147024809;
  if ( a2 )
    v6 = a1[6];
  memset_0(Dst, 0, 0x208u);
  if ( !v6 )
  {
    if ( ExpandEnvironmentStringsW(L"%windir%\\system32\\NDF", Dst, 0x104u) )
      goto LABEL_8;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( !v6 )
    {
LABEL_8:
      TickCount = (__time64_t *)ATL::CTime::GetTickCount(v12);
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        ATL::CTime::Format(TickCount);
        v9 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 48LL))(*(_QWORD *)a1);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          a3,
          L"%s\\%s-%s-%s.etl",
          Dst,
          v9,
          a2);
        ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v13) )
        {
          v6 = *(_DWORD *)v13;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180023965);
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180023880  push    rbx
0x180023882  push    rsi
0x180023883  push    rdi
0x180023884  push    r14
0x180023886  push    r15
0x180023888  sub     rsp, 270h
0x18002388f  mov     rax, cs:__security_cookie
0x180023896  xor     rax, rsp
0x180023899  mov     [rsp+298h+var_38], rax
0x1800238a1  mov     r15, r8
0x1800238a4  mov     r14, rdx
0x1800238a7  mov     rdi, rcx
0x1800238aa  test    rdx, rdx
0x1800238ad  mov     ebx, 80070057h
0x1800238b2  jz      short loc_1800238B7
0x1800238b4  mov     ebx, [rcx+18h]
0x1800238b7  xor     edx, edx; Val
0x1800238b9  mov     r8d, 208h; Size
0x1800238bf  lea     rcx, [rsp+298h+Dst]; void *
0x1800238c4  call    memset_0
0x1800238c9  test    ebx, ebx
0x1800238cb  jnz     loc_180023969
0x1800238d1  mov     r8d, 104h; nSize
0x1800238d7  lea     rdx, [rsp+298h+Dst]; lpDst
0x1800238dc  lea     rcx, aWindirSystem32; "%windir%\\system32\\NDF"
0x1800238e3  call    cs:__imp_ExpandEnvironmentStringsW
0x1800238e9  test    eax, eax
0x1800238eb  jnz     short loc_180023906
0x1800238ed  call    cs:__imp_GetLastError
0x1800238f3  mov     ebx, eax
0x1800238f5  test    eax, eax
0x1800238f7  jle     short loc_180023902
0x1800238f9  movzx   ebx, ax
0x1800238fc  or      ebx, 80070000h
0x180023902  test    ebx, ebx
0x180023904  jnz     short loc_180023969
0x180023906  lea     rcx, [rsp+298h+var_260]
0x18002390b  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x180023910  lea     rdx, [rsp+298h+var_268]
0x180023915  mov     rcx, rax; Time
0x180023918  call    ?Format@CTime@ATL@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@PEBG@Z; ATL::CTime::Format(ushort const *)
0x18002391d  nop
0x18002391e  mov     rsi, [rsp+298h+var_268]
0x180023923  mov     rcx, [rdi]
0x180023926  mov     rax, [rcx]
0x180023929  mov     rax, [rax+30h]
0x18002392d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023932  mov     [rsp+298h+var_270], rsi
0x180023937  mov     [rsp+298h+var_278], r14
0x18002393c  mov     r9, rax
0x18002393f  lea     r8, [rsp+298h+Dst]
0x180023944  lea     rdx, aSSSSEtl; "%s\\%s-%s-%s.etl"
0x18002394b  mov     rcx, r15
0x18002394e  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180023953  nop
0x180023954  mov     rcx, [rsp+298h+var_268]
0x180023959  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002395d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023962  nop
0x180023963  jmp     short loc_180023969
0x180023965  mov     ebx, dword ptr [rsp+298h+var_268]
0x180023969  mov     eax, ebx
0x18002396b  mov     rcx, [rsp+298h+var_38]
0x180023973  xor     rcx, rsp; StackCookie
0x180023976  call    __security_check_cookie
0x18002397b  add     rsp, 270h
0x180023982  pop     r15
0x180023984  pop     r14
0x180023986  pop     rdi
0x180023987  pop     rsi
0x180023988  pop     rbx
0x180023989  retn
```
