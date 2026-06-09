# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140002500`
- end: `0x140002577`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `119`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140006cf8`

## callees

- `0x1400022f8`
- `0x140002500`
- `0x1400043c8`
- `0x140004940`

## string_xrefs

- `0x140002517`: `onecoreuap\net\dusm\task\dusmtask.cpp`
- `0x140002545`: `onecoreuap\net\dusm\task\dusmtask.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<0>(
        wil::details *a1,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // ebx
  int v7; // edi
  signed int LastErrorFail; // eax
  __int64 v9; // rax
  __int64 v10; // xmm0_8
  int v11; // r9d
  const char *v12; // [rsp+20h] [rbp-58h]
  int v13; // [rsp+20h] [rbp-58h]
  void *v14; // [rsp+30h] [rbp-48h]
  __int64 v15; // [rsp+50h] [rbp-28h] BYREF
  int v16; // [rsp+58h] [rbp-20h]
  _BYTE v17[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecoreuap\\net\\dusm\\task\\dusmtask.cpp",
                    a4,
                    v12,
                    a6,
                    v14);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v9 = wil::details::ResultStatus::FromResult(v17, (unsigned int)LastErrorFail);
  v10 = *(_QWORD *)v9;
  v16 = *(_DWORD *)(v9 + 8);
  v15 = v10;
  wil::details::ReportFailure_Base<0,0>(
    v7,
    v6,
    (int)"onecoreuap\\net\\dusm\\task\\dusmtask.cpp",
    v11,
    v13,
    (__int64)a6,
    (__int64)&v15);
}

```

## disassembly

```asm
0x140002500  mov     [rsp+arg_0], rbx
0x140002505  mov     [rsp+arg_8], rsi
0x14000250a  push    rdi
0x14000250b  sub     rsp, 70h
0x14000250f  mov     rsi, [rsp+78h+arg_28]
0x140002517  lea     r8, aOnecoreuapNetD; "onecoreuap\\net\\dusm\\task\\dusmtask.c"...
0x14000251e  mov     [rsp+78h+var_50], rsi; char *
0x140002523  mov     ebx, edx
0x140002525  mov     rdi, rcx
0x140002528  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x14000252d  test    eax, eax
0x14000252f  jle     short loc_140002539
0x140002531  movzx   eax, ax
0x140002534  or      eax, 80070000h
0x140002539  mov     edx, eax
0x14000253b  lea     rcx, [rsp+78h+var_18]
0x140002540  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x140002545  lea     r8, aOnecoreuapNetD; "onecoreuap\\net\\dusm\\task\\dusmtask.c"...
0x14000254c  mov     edx, ebx
0x14000254e  mov     rcx, rdi
0x140002551  movsd   xmm0, qword ptr [rax]
0x140002555  mov     eax, [rax+8]
0x140002558  mov     [rsp+78h+var_20], eax
0x14000255c  lea     rax, [rsp+78h+var_28]
0x140002561  mov     [rsp+78h+var_48], rax
0x140002566  mov     [rsp+78h+var_50], rsi
0x14000256b  movsd   [rsp+78h+var_28], xmm0
0x140002571  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
