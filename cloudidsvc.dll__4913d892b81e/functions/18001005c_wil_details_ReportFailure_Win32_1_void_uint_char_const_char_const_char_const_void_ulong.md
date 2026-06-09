# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18001005c`
- end: `0x1800100c7`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `107`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800105f4`

## callees

- `0x1800032fc`
- `0x180005f3c`
- `0x18001005c`

## string_xrefs

- `0x18001008c`: `onecoreuap\ds\ext\common\lib\registryhelpers\registryhelpers.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  int v8; // edx
  int v9; // r9d
  int v11; // [rsp+20h] [rbp-48h]
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  v12[0] = v7;
  v12[1] = wil::details::HrToNtStatus((wil::details *)v7, a2);
  v12[2] = 0;
  wil::details::ReportFailure_Base<1,0>(
    v9,
    v8,
    (int)"onecoreuap\\ds\\ext\\common\\lib\\registryhelpers\\registryhelpers.cpp",
    v9,
    v11,
    a6,
    (int)v12,
    0);
  return v7;
}

```

## disassembly

```asm
0x18001005c  push    rbx
0x18001005e  sub     rsp, 60h
0x180010062  mov     ebx, dword ptr [rsp+68h+arg_30]
0x180010069  mov     r9, rcx
0x18001006c  test    ebx, ebx
0x18001006e  jle     short loc_180010079
0x180010070  movzx   ebx, bx
0x180010073  or      ebx, 80070000h
0x180010079  mov     ecx, ebx; this
0x18001007b  mov     [rsp+68h+var_18], ebx
0x18001007f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180010084  mov     rcx, [rsp+68h+arg_28]
0x18001008c  lea     r8, aOnecoreuapDsEx_2; "onecoreuap\\ds\\ext\\common\\lib\\regis"...
0x180010093  mov     [rsp+68h+var_14], eax
0x180010097  lea     rax, [rsp+68h+var_18]
0x18001009c  mov     [rsp+68h+var_30], 0
0x1800100a5  mov     [rsp+68h+var_38], rax
0x1800100aa  mov     [rsp+68h+var_40], rcx
0x1800100af  mov     rcx, r9
0x1800100b2  mov     [rsp+68h+var_10], 0
0x1800100ba  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800100bf  mov     eax, ebx
0x1800100c1  add     rsp, 60h
0x1800100c5  pop     rbx
0x1800100c6  retn
```
