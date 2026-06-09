# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x1400042ec`
- end: `0x1400043d8`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140004264`

## callees

- `0x1400041a0`
- `0x140004200`
- `0x1400042ec`
- `0x1400080fc`
- `0x14001a010`

## string_xrefs

- `0x14000436b`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x1400043a9`: `onecore\windows\directx\database\updater\exe\main.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<1>(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rdi
  __int64 v10; // rcx
  __int64 (__fastcall *v12)(_BYTE *, __int64, __int64, int *); // rax
  __int64 v13; // rax
  int v14; // ecx
  int v16; // r9d
  _BYTE v17[56]; // [rsp+50h] [rbp-38h] BYREF
  int v18; // [rsp+A0h] [rbp+18h] BYREF

  v18 = a3;
  v8 = a8;
  LOBYTE(v18) = 0;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(a8 + 2 * v10) );
  v12 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, int *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v12
    || (v13 = v12(v17, v8 + 2 * v10, 2048 - v10, &v18),
        v14 = *(_DWORD *)(v13 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v13,
        *(_DWORD *)(a1 + 8) = v14,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(
      a2,
      370,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
      v16);
  }
  wil::details::ReportFailure_Base<1,0>(a2, 370, "onecore\\windows\\directx\\database\\updater\\exe\\main.cpp");
  return a1;
}

```

## disassembly

```asm
0x1400042ec  mov     rax, rsp
0x1400042ef  mov     [rax+18h], r8d
0x1400042f3  push    rbx
0x1400042f4  push    rbp
0x1400042f5  push    rsi
0x1400042f6  push    rdi
0x1400042f7  sub     rsp, 68h
0x1400042fb  mov     rdi, [rsp+88h+arg_38]
0x140004303  xor     ebp, ebp
0x140004305  mov     rbx, rcx
0x140004308  mov     [rax+18h], bpl
0x14000430c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140004310  mov     rsi, rdx
0x140004313  inc     rcx
0x140004316  cmp     [rdi+rcx*2], bp
0x14000431a  jnz     short loc_140004313
0x14000431c  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x140004323  mov     [rbx], rbp
0x140004326  mov     dword ptr [rbx+8], 1
0x14000432d  test    rax, rax
0x140004330  jz      short loc_14000439A
0x140004332  lea     rdx, [rdi+rcx*2]
0x140004336  mov     r8d, 800h
0x14000433c  sub     r8, rcx
0x14000433f  lea     r9, [rsp+88h+arg_10]
0x140004347  lea     rcx, [rsp+88h+var_38]
0x14000434c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004351  movsd   xmm0, qword ptr [rax]
0x140004355  mov     ecx, [rax+8]
0x140004358  movsd   qword ptr [rbx], xmm0
0x14000435c  mov     [rbx+8], ecx
0x14000435f  cmp     [rbx], ebp
0x140004361  jge     short loc_14000439A
0x140004363  mov     rax, [rsp+88h+arg_30]
0x14000436b  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x140004372  mov     [rsp+88h+var_50], rdi
0x140004377  mov     edx, 172h
0x14000437c  mov     [rsp+88h+var_58], rbx
0x140004381  mov     rcx, rsi
0x140004384  mov     [rsp+88h+var_60], rax
0x140004389  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x14000438e  mov     rax, rbx
0x140004391  add     rsp, 68h
0x140004395  pop     rdi
0x140004396  pop     rsi
0x140004397  pop     rbp
0x140004398  pop     rbx
0x140004399  retn
0x14000439a  mov     ecx, 8007023Eh; this
0x14000439f  mov     [rbx], ecx
0x1400043a1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400043a6  mov     [rbx+4], eax
0x1400043a9  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x1400043b0  mov     rax, [rsp+88h+arg_30]
0x1400043b8  mov     edx, 172h
0x1400043bd  mov     [rsp+88h+var_50], rdi
0x1400043c2  mov     rcx, rsi
0x1400043c5  mov     [rsp+88h+var_58], rbx
0x1400043ca  mov     [rsp+88h+var_60], rax
0x1400043cf  mov     [rbx+8], ebp
0x1400043d2  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
