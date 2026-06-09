# CValidateTask::TaskRoutine(void)

- ea: `0x18009ffe0`
- end: `0x1800a0202`
- name: `?TaskRoutine@CValidateTask@@UEAAXXZ`
- size: `546`
- prototype: `void __fastcall(CValidateTask *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800063b0`
- `0x18001bda4`
- `0x18009ffe0`
- `0x1800a06b8`
- `0x1800bd010`

## string_xrefs

- `0x1800a013f`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x1800a01aa`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x1800a0043`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x1800a00a6`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x1800a00f4`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x1800a0184`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x1800a0031`: `CValidateTask::TaskRoutine`
- `0x1800a001c`: `CValidateTask::TaskRoutine - calling xa_open - DLL=%S`
- `0x1800a0086`: `CValidateTask::TaskRoutine - returned from xa_open with error=%d - DLL=%S`
- `0x1800a0164`: `CValidateTask::TaskRoutine - returned from xa_close with error=%d - DLL=%S`
- `0x1800a00d4`: `CValidateTask::TaskRoutine - calling xa_close - DLL=%S`

## pseudocode

```c
void __fastcall CValidateTask::TaskRoutine(CValidateTask *this)
{
  unsigned int v2; // edi
  unsigned int v3; // r9d
  unsigned int v4; // r9d
  int v5; // [rsp+20h] [rbp-38h]
  int v6; // [rsp+20h] [rbp-38h]
  int v7; // [rsp+28h] [rbp-30h]
  int v8; // [rsp+28h] [rbp-30h]
  __int64 v9; // [rsp+38h] [rbp-20h]

  v2 = XaRmId(*((_DWORD *)this + 20));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11));
  try
  {
    TraceStringInline(
      11,
      4,
      L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
      1915,
      L"CValidateTask::TaskRoutine",
      0,
      L"CValidateTask::TaskRoutine - calling xa_open - DLL=%S",
      *((_QWORD *)this + 8));
    **((_DWORD **)this + 15) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 12) + 40LL))(
                                 *((_QWORD *)this + 13),
                                 v2,
                                 0);
    TraceStringInline(
      11,
      4,
      L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
      1919,
      L"CValidateTask::TaskRoutine",
      0,
      L"CValidateTask::TaskRoutine - returned from xa_open with error=%d - DLL=%S");
  }
  catch ( ... )
  {
    TraceStringInline(
      11,
      1,
      L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
      1924,
      L"CValidateTask::TaskRoutine",
      -2147430319,
      L"CValidateTask::TaskRoutine - exception thrown calling xa_open - DLL=%S",
      *((_QWORD *)this + 8));
    XA_TRACE_WARNING(0x8000D051, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 1925, *((char **)this + 8), v6);
    DtcXaException("xa_open");
  }
  v3 = **((_DWORD **)this + 15);
  if ( v3 )
  {
    XA_TRACE_WARNING(0x8000D04D, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 1955, v3, *((char **)this + 8), v7);
  }
  else
  {
    v9 = *((_QWORD *)this + 8);
    try
    {
      TraceStringInline(
        11,
        4,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        1934,
        L"CValidateTask::TaskRoutine",
        0,
        L"CValidateTask::TaskRoutine - calling xa_close - DLL=%S");
      **((_DWORD **)this + 15) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 12) + 48LL))(
                                   *((_QWORD *)this + 14),
                                   v2,
                                   0);
      v4 = **((_DWORD **)this + 15);
      if ( v4 )
        XA_TRACE_WARNING(
          0x8000D05B,
          "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
          1941,
          v4,
          *((char **)this + 8),
          v8);
      LODWORD(v9) = **((_DWORD **)this + 15);
      TraceStringInline(
        11,
        4,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        1943,
        L"CValidateTask::TaskRoutine",
        0,
        L"CValidateTask::TaskRoutine - returned from xa_close with error=%d - DLL=%S",
        v9,
        *((_QWORD *)this + 8));
    }
    catch ( ... )
    {
      TraceStringInline(
        11,
        1,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        1948,
        L"CValidateTask::TaskRoutine",
        -2147430318,
        L"CValidateTask::TaskRoutine - exception thrown calling xa_close - DLL=%S",
        *((_QWORD *)this + 8));
      XA_TRACE_WARNING(0x8000D052, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 1949, *((char **)this + 8), v5);
      DtcXaException("xa_close");
    }
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 40LL))(*((_QWORD *)this + 11));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 24LL))(*((_QWORD *)this + 11));
  *((_QWORD *)this + 11) = 0;
  (*(void (__fastcall **)(CValidateTask *))(*(_QWORD *)this + 16LL))(this);
}

```

## disassembly

```asm
0x18009ffe0  mov     [rsp+arg_8], rbx
0x18009ffe5  mov     [rsp+arg_10], rdi
0x18009ffea  mov     [rsp+arg_0], rcx
0x18009ffef  push    r13
0x18009fff1  sub     rsp, 50h
0x18009fff5  mov     rbx, rcx
0x18009fff8  mov     ecx, [rcx+50h]; unsigned int
0x18009fffb  call    ?XaRmId@@YAKI@Z; XaRmId(uint)
0x1800a0000  mov     edi, eax
0x1800a0002  mov     rcx, [rbx+58h]
0x1800a0006  mov     rdx, [rcx]
0x1800a0009  mov     rax, [rdx+20h]
0x1800a000d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0012  nop
0x1800a0013  mov     rcx, [rbx+40h]
0x1800a0017  mov     [rsp+58h+var_20], rcx
0x1800a001c  lea     rax, aCvalidatetaskT_4; "CValidateTask::TaskRoutine - calling xa"...
0x1800a0023  mov     [rsp+58h+var_28], rax
0x1800a0028  mov     qword ptr [rsp+58h+var_30], 0
0x1800a0031  lea     r13, aCvalidatetaskT; "CValidateTask::TaskRoutine"
0x1800a0038  mov     [rsp+58h+var_38], r13
0x1800a003d  mov     r9d, 77Bh
0x1800a0043  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x1800a004a  mov     edx, 4
0x1800a004f  lea     ecx, [rdx+7]
0x1800a0052  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800a0057  mov     rax, [rbx+60h]
0x1800a005b  xor     r8d, r8d
0x1800a005e  mov     edx, edi
0x1800a0060  mov     rcx, [rbx+68h]
0x1800a0064  mov     rax, [rax+28h]
0x1800a0068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a006d  mov     rcx, [rbx+78h]
0x1800a0071  mov     [rcx], eax
0x1800a0073  mov     rcx, [rbx+78h]
0x1800a0077  mov     rax, [rbx+40h]
0x1800a007b  mov     [rsp+58h+var_18], rax
0x1800a0080  mov     eax, [rcx]
0x1800a0082  mov     dword ptr [rsp+58h+var_20], eax
0x1800a0086  lea     rax, aCvalidatetaskT_2; "CValidateTask::TaskRoutine - returned f"...
0x1800a008d  mov     [rsp+58h+var_28], rax
0x1800a0092  mov     qword ptr [rsp+58h+var_30], 0; int
0x1800a009b  mov     [rsp+58h+var_38], r13
0x1800a00a0  mov     r9d, 77Fh
0x1800a00a6  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x1800a00ad  mov     edx, 4
0x1800a00b2  lea     ecx, [rdx+7]
0x1800a00b5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800a00ba  nop
0x1800a00bb  mov     rax, [rbx+78h]
0x1800a00bf  mov     r9d, [rax]; unsigned int
0x1800a00c2  test    r9d, r9d
0x1800a00c5  jnz     loc_1800A019B
0x1800a00cb  mov     rax, [rbx+40h]
0x1800a00cf  mov     [rsp+58h+var_20], rax
0x1800a00d4  lea     rax, aCvalidatetaskT_0; "CValidateTask::TaskRoutine - calling xa"...
0x1800a00db  mov     [rsp+58h+var_28], rax
0x1800a00e0  mov     qword ptr [rsp+58h+var_30], 0; int
0x1800a00e9  mov     [rsp+58h+var_38], r13
0x1800a00ee  mov     r9d, 78Eh
0x1800a00f4  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x1800a00fb  mov     edx, 4
0x1800a0100  lea     ecx, [rdx+7]
0x1800a0103  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800a0108  mov     rax, [rbx+60h]
0x1800a010c  xor     r8d, r8d
0x1800a010f  mov     edx, edi
0x1800a0111  mov     rcx, [rbx+70h]
0x1800a0115  mov     rax, [rax+30h]
0x1800a0119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a011e  mov     rcx, [rbx+78h]
0x1800a0122  mov     [rcx], eax
0x1800a0124  mov     rax, [rbx+78h]
0x1800a0128  mov     r9d, [rax]; unsigned int
0x1800a012b  test    r9d, r9d
0x1800a012e  jz      short loc_1800A0150
0x1800a0130  mov     rax, [rbx+40h]
0x1800a0134  mov     [rsp+58h+var_38], rax; char *
0x1800a0139  mov     r8d, 795h; int
0x1800a013f  lea     rdx, aComComplusDtcD_81; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x1800a0146  mov     ecx, 8000D05Bh; unsigned int
0x1800a014b  call    ?XA_TRACE_WARNING@@YAXKPEADHK0H@Z; XA_TRACE_WARNING(ulong,char *,int,ulong,char *,int)
0x1800a0150  mov     r9, [rbx+78h]
0x1800a0154  mov     rax, [rbx+40h]
0x1800a0158  mov     [rsp+58h+var_18], rax
0x1800a015d  mov     eax, [r9]
0x1800a0160  mov     dword ptr [rsp+58h+var_20], eax
0x1800a0164  lea     rax, aCvalidatetaskT_1; "CValidateTask::TaskRoutine - returned f"...
0x1800a016b  mov     [rsp+58h+var_28], rax
0x1800a0170  mov     qword ptr [rsp+58h+var_30], 0
0x1800a0179  mov     [rsp+58h+var_38], r13
0x1800a017e  mov     r9d, 797h
0x1800a0184  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x1800a018b  mov     edx, 4
0x1800a0190  lea     ecx, [rdx+7]
0x1800a0193  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800a0198  nop
0x1800a0199  jmp     short loc_1800A01BB
0x1800a019b  mov     rax, [rbx+40h]
0x1800a019f  mov     [rsp+58h+var_38], rax; char *
0x1800a01a4  mov     r8d, 7A3h; int
0x1800a01aa  lea     rdx, aComComplusDtcD_81; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x1800a01b1  mov     ecx, 8000D04Dh; unsigned int
0x1800a01b6  call    ?XA_TRACE_WARNING@@YAXKPEADHK0H@Z; XA_TRACE_WARNING(ulong,char *,int,ulong,char *,int)
0x1800a01bb  mov     rcx, [rbx+58h]
0x1800a01bf  mov     rax, [rcx]
0x1800a01c2  mov     rax, [rax+28h]
0x1800a01c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a01cb  mov     rcx, [rbx+58h]
0x1800a01cf  mov     rax, [rcx]
0x1800a01d2  mov     rax, [rax+18h]
0x1800a01d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a01db  mov     qword ptr [rbx+58h], 0
0x1800a01e3  mov     rax, [rbx]
0x1800a01e6  mov     rcx, rbx
0x1800a01e9  mov     rax, [rax+10h]
0x1800a01ed  mov     rbx, [rsp+58h+arg_8]
0x1800a01f2  mov     rdi, [rsp+58h+arg_10]
0x1800a01f7  add     rsp, 50h
0x1800a01fb  pop     r13
0x1800a01fd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
