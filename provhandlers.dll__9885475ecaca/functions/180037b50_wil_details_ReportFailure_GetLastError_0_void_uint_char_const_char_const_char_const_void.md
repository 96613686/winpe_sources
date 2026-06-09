# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180037b50`
- end: `0x180037bc7`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `119`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003ac98`

## callees

- `0x180005b68`
- `0x1800061b0`
- `0x18000f044`
- `0x180037b50`

## string_xrefs

- `0x180037b67`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x180037b95`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`

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
                    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
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
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
    v11,
    v13,
    (__int64)a6,
    (__int64)&v15);
}

```

## disassembly

```asm
0x180037b50  mov     [rsp+arg_0], rbx
0x180037b55  mov     [rsp+arg_8], rsi
0x180037b5a  push    rdi
0x180037b5b  sub     rsp, 70h
0x180037b5f  mov     rsi, [rsp+78h+arg_28]
0x180037b67  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180037b6e  mov     [rsp+78h+var_50], rsi; char *
0x180037b73  mov     ebx, edx
0x180037b75  mov     rdi, rcx
0x180037b78  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180037b7d  test    eax, eax
0x180037b7f  jle     short loc_180037B89
0x180037b81  movzx   eax, ax
0x180037b84  or      eax, 80070000h
0x180037b89  mov     edx, eax
0x180037b8b  lea     rcx, [rsp+78h+var_18]
0x180037b90  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180037b95  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180037b9c  mov     edx, ebx
0x180037b9e  mov     rcx, rdi
0x180037ba1  movsd   xmm0, qword ptr [rax]
0x180037ba5  mov     eax, [rax+8]
0x180037ba8  mov     [rsp+78h+var_20], eax
0x180037bac  lea     rax, [rsp+78h+var_28]
0x180037bb1  mov     [rsp+78h+var_48], rax
0x180037bb6  mov     [rsp+78h+var_50], rsi
0x180037bbb  movsd   [rsp+78h+var_28], xmm0
0x180037bc1  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
