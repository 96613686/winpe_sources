# CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)

- ea: `0x180006e54`
- end: `0x18000703b`
- name: `?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z`
- size: `487`
- prototype: `static void(unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `15`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004d30`
- `0x1800051e0`
- `0x1800056f0`
- `0x180007320`
- `0x1800076b0`
- `0x18001df9c`
- `0x18001e1d4`
- `0x18001e308`
- `0x18001e39c`
- `0x18001e494`
- `0x18001e5e0`
- `0x18001e890`
- `0x18001ea80`
- `0x18001eb28`
- `0x18001ecdc`

## callees

- `0x1800041ec`
- `0x180005640`
- `0x180006e54`
- `0x18000be40`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006edc`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006edc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ef0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006f3a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ef0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006f3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007003`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007011`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007003`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007011`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x180006fea`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x180006fea`
- `ntdll!EtwEventRegister` at `0x180006faa`
- `ntdll!EtwEventRegister` at `0x180006faa`
- `ntdll!EtwEventUnregister` at `0x180006ff4`
- `ntdll!EtwEventUnregister` at `0x180006ff4`

## pseudocode

```c
void __fastcall CSystemWriter::LogSystemErrorEvent(int a1, const unsigned __int16 *a2, DWORD a3)
{
  __int64 v3; // rsi
  unsigned __int16 *v7; // rbx
  int v8; // edi
  __int64 v9; // rdi
  const unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rax
  SIZE_T v12; // rdx
  unsigned __int64 v13; // rdi
  unsigned __int16 *v14; // rax
  int Arguments; // [rsp+30h] [rbp-40h]
  WCHAR Buffer[4]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v17; // [rsp+58h] [rbp-18h] BYREF
  const WCHAR *v18; // [rsp+60h] [rbp-10h] BYREF

  v3 = -1;
  v17 = 0;
  *(_QWORD *)Buffer = 0;
  v18 = &LocaleName;
  v7 = 0;
  v8 = 0;
  if ( a2 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    v8 = v9 + 11;
  }
  if ( a3 )
  {
    v8 += 16;
    FormatMessageW(0x1300u, 0, a3, 0, Buffer, 0, 0);
    v10 = *(const unsigned __int16 **)Buffer;
    if ( *(_QWORD *)Buffer
      || (v11 = (unsigned __int16 *)LocalAlloc(0, 0x40u), (*(_QWORD *)Buffer = v11) != 0)
      && (StringCchPrintfW(v11, 0x20u, L"0x%08X (unresolvable)", a3), (v10 = *(const unsigned __int16 **)Buffer) != 0) )
    {
      do
        ++v3;
      while ( v10[v3] );
      v8 += v3;
    }
  }
  if ( v8 )
  {
    v12 = 2LL * (unsigned int)(v8 + 1);
    v13 = (unsigned int)(v8 + 1);
    v14 = (unsigned __int16 *)LocalAlloc(0, v12);
    v7 = v14;
    if ( v14 )
    {
      *v14 = 0;
      if ( a2 )
      {
        StringCchCatW(v14, (unsigned int)v13, L"\n\nDetails:\n");
        StringCchCatW(v7, (unsigned int)v13, a2);
      }
      if ( *(_QWORD *)Buffer )
      {
        StringCchCatW(v7, v13, L"\n\nSystem Error:\n");
        StringCchCatW(v7, v13, *(const unsigned __int16 **)Buffer);
      }
      v18 = v7;
    }
  }
  if ( !(unsigned int)EtwEventRegister(CAPI2_PROVIDER, 0, 0, &v17) )
  {
    LOWORD(Arguments) = 1;
    EvtIntReportEventAndSourceAsync(v17, L"Microsoft-Windows-CAPI2", 1, 0, a1, 0, Arguments, 0, &v18, 0);
    EtwEventUnregister(v17);
  }
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  if ( v7 )
    LocalFree(v7);
}

```

## disassembly

```asm
0x180006e54  mov     [rsp-38h+arg_18], rbx
0x180006e59  push    rbp
0x180006e5a  push    rsi
0x180006e5b  push    rdi
0x180006e5c  push    r12
0x180006e5e  push    r13
0x180006e60  push    r14
0x180006e62  push    r15
0x180006e64  mov     rbp, rsp
0x180006e67  sub     rsp, 70h
0x180006e6b  mov     rax, cs:__security_cookie
0x180006e72  xor     rax, rsp
0x180006e75  mov     [rbp+var_8], rax
0x180006e79  xor     r13d, r13d
0x180006e7c  lea     rax, LocaleName
0x180006e83  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006e87  mov     [rbp+var_18], r13
0x180006e8b  mov     qword ptr [rbp+Buffer], r13
0x180006e8f  mov     r15d, r8d
0x180006e92  mov     [rbp+var_10], rax
0x180006e96  mov     r14, rdx
0x180006e99  mov     r12d, ecx
0x180006e9c  mov     ebx, r13d
0x180006e9f  mov     edi, r13d
0x180006ea2  test    rdx, rdx
0x180006ea5  jz      short loc_180006EB7
0x180006ea7  mov     rdi, rsi
0x180006eaa  inc     rdi
0x180006ead  cmp     [rdx+rdi*2], r13w
0x180006eb2  jnz     short loc_180006EAA
0x180006eb4  add     edi, 0Bh
0x180006eb7  test    r15d, r15d
0x180006eba  jz      short loc_180006F2B
0x180006ebc  mov     [rsp+70h+Arguments], r13; Arguments
0x180006ec1  lea     rax, [rbp+Buffer]
0x180006ec5  mov     [rsp+70h+nSize], r13d; nSize
0x180006eca  xor     r9d, r9d; dwLanguageId
0x180006ecd  xor     edx, edx; lpSource
0x180006ecf  mov     [rsp+70h+lpBuffer], rax; lpBuffer
0x180006ed4  mov     ecx, 1300h; dwFlags
0x180006ed9  add     edi, 10h
0x180006edc  call    cs:__imp_FormatMessageW
0x180006ee2  mov     rax, qword ptr [rbp+Buffer]
0x180006ee6  test    rax, rax
0x180006ee9  jnz     short loc_180006F1F
0x180006eeb  lea     edx, [rax+40h]; uBytes
0x180006eee  xor     ecx, ecx; uFlags
0x180006ef0  call    cs:__imp_LocalAlloc
0x180006ef6  mov     qword ptr [rbp+Buffer], rax
0x180006efa  test    rax, rax
0x180006efd  jz      short loc_180006F2B
0x180006eff  mov     r9d, r15d
0x180006f02  lea     r8, a0x08xUnresolva; "0x%08X (unresolvable)"
0x180006f09  mov     edx, 20h ; ' '; unsigned __int64
0x180006f0e  mov     rcx, rax; unsigned __int16 *
0x180006f11  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006f16  mov     rax, qword ptr [rbp+Buffer]
0x180006f1a  test    rax, rax
0x180006f1d  jz      short loc_180006F2B
0x180006f1f  inc     rsi
0x180006f22  cmp     [rax+rsi*2], r13w
0x180006f27  jnz     short loc_180006F1F
0x180006f29  add     edi, esi
0x180006f2b  test    edi, edi
0x180006f2d  jz      short loc_180006F9A
0x180006f2f  lea     eax, [rdi+1]
0x180006f32  xor     ecx, ecx; uFlags
0x180006f34  lea     rdx, [rax+rax]; uBytes
0x180006f38  mov     edi, eax
0x180006f3a  call    cs:__imp_LocalAlloc
0x180006f40  mov     rbx, rax
0x180006f43  test    rax, rax
0x180006f46  jz      short loc_180006F9A
0x180006f48  mov     [rax], r13w
0x180006f4c  test    r14, r14
0x180006f4f  jz      short loc_180006F6F
0x180006f51  lea     r8, aDetails; "\n\nDetails:\n"
0x180006f58  mov     edx, edi; unsigned __int64
0x180006f5a  mov     rcx, rax; unsigned __int16 *
0x180006f5d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006f62  mov     r8, r14; unsigned __int16 *
0x180006f65  mov     edx, edi; unsigned __int64
0x180006f67  mov     rcx, rbx; unsigned __int16 *
0x180006f6a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006f6f  cmp     qword ptr [rbp+Buffer], r13
0x180006f73  jz      short loc_180006F96
0x180006f75  lea     r8, aSystemError; "\n\nSystem Error:\n"
0x180006f7c  mov     rdx, rdi; unsigned __int64
0x180006f7f  mov     rcx, rbx; unsigned __int16 *
0x180006f82  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006f87  mov     r8, qword ptr [rbp+Buffer]; unsigned __int16 *
0x180006f8b  mov     rdx, rdi; unsigned __int64
0x180006f8e  mov     rcx, rbx; unsigned __int16 *
0x180006f91  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006f96  mov     [rbp+var_10], rbx
0x180006f9a  lea     r9, [rbp+var_18]
0x180006f9e  xor     r8d, r8d
0x180006fa1  xor     edx, edx
0x180006fa3  lea     rcx, CAPI2_PROVIDER
0x180006faa  call    cs:__imp_EtwEventRegister
0x180006fb0  test    eax, eax
0x180006fb2  jnz     short loc_180006FFA
0x180006fb4  lea     ecx, [rax+1]
0x180006fb7  mov     [rsp+70h+var_28], r13
0x180006fbc  lea     rax, [rbp+var_10]
0x180006fc0  mov     r8d, ecx
0x180006fc3  mov     [rsp+70h+var_30], rax
0x180006fc8  lea     rdx, aMicrosoftWindo_0; "Microsoft-Windows-CAPI2"
0x180006fcf  mov     [rsp+70h+var_38], r13d
0x180006fd4  xor     r9d, r9d
0x180006fd7  mov     word ptr [rsp+70h+Arguments], cx
0x180006fdc  mov     rcx, [rbp+var_18]
0x180006fe0  mov     qword ptr [rsp+70h+nSize], r13
0x180006fe5  mov     dword ptr [rsp+70h+lpBuffer], r12d
0x180006fea  call    cs:__imp_EvtIntReportEventAndSourceAsync
0x180006ff0  mov     rcx, [rbp+var_18]
0x180006ff4  call    cs:__imp_EtwEventUnregister
0x180006ffa  mov     rcx, qword ptr [rbp+Buffer]; hMem
0x180006ffe  test    rcx, rcx
0x180007001  jz      short loc_180007009
0x180007003  call    cs:__imp_LocalFree
0x180007009  test    rbx, rbx
0x18000700c  jz      short loc_180007017
0x18000700e  mov     rcx, rbx; hMem
0x180007011  call    cs:__imp_LocalFree
0x180007017  mov     rcx, [rbp+var_8]
0x18000701b  xor     rcx, rsp; StackCookie
0x18000701e  call    __security_check_cookie
0x180007023  mov     rbx, [rsp+70h+arg_18]
0x18000702b  add     rsp, 70h
0x18000702f  pop     r15
0x180007031  pop     r14
0x180007033  pop     r13
0x180007035  pop     r12
0x180007037  pop     rdi
0x180007038  pop     rsi
0x180007039  pop     rbp
0x18000703a  retn
```
