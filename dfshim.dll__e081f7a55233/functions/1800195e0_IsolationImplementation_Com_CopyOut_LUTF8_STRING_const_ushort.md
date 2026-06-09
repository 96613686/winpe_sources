# IsolationImplementation::Com::CopyOut(_LUTF8_STRING const *,ushort * *)

- ea: `0x1800195e0`
- end: `0x1800197ac`
- name: `?CopyOut@Com@IsolationImplementation@@YAJPEBU_LUTF8_STRING@@PEAPEAG@Z`
- size: `460`
- prototype: `__int64 __fastcall(IsolationImplementation::Com *__hidden this, const struct _LUTF8_STRING *, unsigned __int16 **)`
- caller_count: `22`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a678`
- `0x18005c584`
- `0x18005d270`
- `0x18005d438`
- `0x18005d89c`
- `0x180073a80`
- `0x180078640`
- `0x180078d30`
- `0x180079420`
- `0x180079b10`
- `0x18007a6e0`
- `0x18007add0`
- `0x18007b4c0`
- `0x18007c090`
- `0x18007c780`
- `0x18007ce70`
- `0x18007dd90`
- `0x18007e480`
- `0x180097970`
- `0x18009e350`
- `0x18009e5a0`
- `0x18009e7f0`

## callees

- `0x180012910`
- `0x180012b1c`
- `0x180012b38`
- `0x180014410`
- `0x1800187f0`
- `0x180018940`
- `0x1800195e0`
- `0x1800493d4`
- `0x180049880`
- `0x18004b204`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001965e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800196ca`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180019769`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001965e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800196ca`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180019769`

## string_xrefs

- `0x1800195f7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\copyout.cpp`
- `0x180019702`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\ntos\rtl\lutf8_string.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CopyOut(
        IsolationImplementation::Com *this,
        const struct _LUTF8_STRING *a2,
        unsigned __int16 **a3)
{
  unsigned int v5; // ebx
  int v6; // eax
  unsigned int v7; // edx
  unsigned int v8; // ebx
  int v9; // edx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  _WORD *v12; // r14
  int v13; // edx
  int v14; // edi
  int v15; // eax
  unsigned int v17; // [rsp+20h] [rbp-48h]
  const char *v18; // [rsp+30h] [rbp-38h] BYREF
  int v19; // [rsp+38h] [rbp-30h]
  int v20; // [rsp+40h] [rbp-28h]
  _QWORD v21[2]; // [rsp+48h] [rbp-20h] BYREF
  _WORD *v22; // [rsp+58h] [rbp-10h]
  unsigned __int64 v23; // [rsp+A0h] [rbp+38h] BYREF

  v20 = -2147023537;
  v18 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\copyout.cpp";
  v23 = 0;
  if ( a2 )
    *(_QWORD *)a2 = 0;
  if ( !this )
  {
    v19 = 466;
LABEL_5:
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v18);
    return (unsigned int)v20;
  }
  if ( !a2 )
  {
    v19 = 467;
    goto LABEL_5;
  }
  v6 = RtlCalculateUtf16StringLengthFromLUtf8String(this, &v23, a3);
  v8 = v6;
  if ( v6 < 0 )
  {
    if ( v6 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\copyout.cpp",
      (const char *)0x1D5,
      v8,
      v17);
    v10 = v8;
    return (unsigned int)Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v10, v9);
  }
  v11 = v23;
  if ( (v23 & 1) != 0 )
  {
    v19 = 470;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v18,
      &v18);
    return (unsigned int)v20;
  }
  v22 = IsolationImplementation::Com::CoTaskMemAlloc((IsolationImplementation::Com *)(unsigned int)(v23 + 2), v7);
  v12 = v22;
  if ( v22 )
  {
    v20 = -1073741595;
    v21[1] = v11 + 2;
    v21[0] = 0;
    v18 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\ntos\\rtl\\lutf8_string.cpp";
    if ( (unsigned __int8)RtlIsLUtf8StringValid(this) )
    {
      v15 = RtlTranscodeLBlobs(0, v13, 106, (_DWORD)this, 1014, (__int64)v21);
      v12 = v22;
      v14 = 0;
      if ( v15 < 0 )
        v14 = v15;
    }
    else
    {
      v19 = 297;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v18);
      v14 = v20;
    }
    if ( v14 >= 0 )
    {
      v12[v11 >> 1] = 0;
      v5 = 0;
      *(_QWORD *)a2 = v12;
      return v5;
    }
    if ( v14 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\copyout.cpp",
      (const char *)0x1DC,
      v14,
      v17);
    v10 = (unsigned int)v14;
    return (unsigned int)Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v10, v9);
  }
  v5 = -2147024882;
  if ( g_HRESULT_to_break_on == -2147024882 )
    DebugBreak();
  Windows::ErrorHandling::COM::ReportError(
    (Windows::ErrorHandling::COM *)"HR originated",
    "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\copyout.cpp",
    (const char *)0x1D8,
    -2147024882,
    v17);
  return v5;
}

```

## disassembly

```asm
0x1800195e0  push    rbp
0x1800195e2  push    rbx
0x1800195e3  push    rsi
0x1800195e4  push    rdi
0x1800195e5  push    r12
0x1800195e7  push    r14
0x1800195e9  mov     rbp, rsp
0x1800195ec  sub     rsp, 68h
0x1800195f0  mov     [rbp+var_28], 8007054Fh
0x1800195f7  lea     r12, aOnecoreComNetf_19; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800195fe  mov     [rbp+var_38], r12
0x180019602  mov     rsi, rdx
0x180019605  mov     [rbp+arg_0], 0
0x18001960d  mov     rdi, rcx
0x180019610  test    rdx, rdx
0x180019613  jz      short loc_18001961C
0x180019615  mov     qword ptr [rdx], 0
0x18001961c  test    rdi, rdi
0x18001961f  jnz     short loc_180019639
0x180019621  mov     [rbp+var_30], 1D2h
0x180019628  lea     rcx, [rbp+var_38]
0x18001962c  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180019631  mov     ebx, [rbp+var_28]
0x180019634  jmp     loc_18001979D
0x180019639  test    rsi, rsi
0x18001963c  jnz     short loc_180019647
0x18001963e  mov     [rbp+var_30], 1D3h
0x180019645  jmp     short loc_180019628
0x180019647  lea     rdx, [rbp+arg_0]
0x18001964b  call    RtlCalculateUtf16StringLengthFromLUtf8String
0x180019650  mov     ebx, eax
0x180019652  test    eax, eax
0x180019654  jns     short loc_18001968A
0x180019656  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18001965c  jnz     short loc_180019664
0x18001965e  call    cs:__imp_DebugBreak
0x180019664  mov     r9d, ebx; int
0x180019667  lea     rcx, aStatusPropagat; "Status propagated"
0x18001966e  mov     r8d, 1D5h; char *
0x180019674  mov     rdx, r12; char *
0x180019677  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18001967c  mov     ecx, ebx; this
0x18001967e  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180019683  mov     ebx, eax
0x180019685  jmp     loc_18001979D
0x18001968a  mov     rbx, [rbp+arg_0]
0x18001968e  test    bl, 1
0x180019691  jz      short loc_1800196A9
0x180019693  mov     [rbp+var_30], 1D6h
0x18001969a  lea     rdx, [rbp+var_38]
0x18001969e  lea     rcx, [rbp+var_38]
0x1800196a2  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800196a7  jmp     short loc_180019631
0x1800196a9  lea     ecx, [rbx+2]; this
0x1800196ac  call    ?CoTaskMemAlloc@Com@IsolationImplementation@@YAPEAXK@Z; IsolationImplementation::Com::CoTaskMemAlloc(ulong)
0x1800196b1  mov     [rbp+var_10], rax
0x1800196b5  mov     r14, rax
0x1800196b8  test    rax, rax
0x1800196bb  jnz     short loc_1800196F0
0x1800196bd  mov     ebx, 8007000Eh
0x1800196c2  cmp     cs:?g_HRESULT_to_break_on@@3JA, ebx; long g_HRESULT_to_break_on
0x1800196c8  jnz     short loc_1800196D0
0x1800196ca  call    cs:__imp_DebugBreak
0x1800196d0  mov     r9d, 8007000Eh; int
0x1800196d6  lea     rcx, aHrOriginated; "HR originated"
0x1800196dd  mov     r8d, 1D8h; char *
0x1800196e3  mov     rdx, r12; char *
0x1800196e6  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800196eb  jmp     loc_18001979D
0x1800196f0  lea     rax, [rbx+2]
0x1800196f4  mov     [rbp+var_28], 0C00000E5h
0x1800196fb  mov     [rbp+var_18], rax
0x1800196ff  mov     rcx, rdi
0x180019702  lea     rax, aOnecoreComNetf_83; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180019709  mov     [rbp+var_20], 0
0x180019711  mov     [rbp+var_38], rax
0x180019715  call    RtlIsLUtf8StringValid
0x18001971a  test    al, al
0x18001971c  jnz     short loc_180019733
0x18001971e  mov     [rbp+var_30], 129h
0x180019725  lea     rcx, [rbp+var_38]
0x180019729  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18001972e  mov     edi, [rbp+var_28]
0x180019731  jmp     short loc_18001975D
0x180019733  xor     ecx, ecx
0x180019735  lea     rax, [rbp+var_20]
0x180019739  mov     [rsp+68h+var_40], rax
0x18001973e  mov     r9, rdi
0x180019741  mov     [rsp+68h+var_48], 3F6h; unsigned int
0x180019749  lea     r8d, [rcx+6Ah]
0x18001974d  call    RtlTranscodeLBlobs
0x180019752  mov     r14, [rbp+var_10]
0x180019756  xor     edi, edi
0x180019758  test    eax, eax
0x18001975a  cmovs   edi, eax
0x18001975d  test    edi, edi
0x18001975f  jns     short loc_18001978E
0x180019761  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x180019767  jnz     short loc_18001976F
0x180019769  call    cs:__imp_DebugBreak
0x18001976f  mov     r9d, edi; int
0x180019772  lea     rcx, aStatusPropagat; "Status propagated"
0x180019779  mov     r8d, 1DCh; char *
0x18001977f  mov     rdx, r12; char *
0x180019782  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180019787  mov     ecx, edi
0x180019789  jmp     loc_18001967E
0x18001978e  shr     rbx, 1
0x180019791  xor     eax, eax
0x180019793  mov     [r14+rbx*2], ax
0x180019798  xor     ebx, ebx
0x18001979a  mov     [rsi], r14
0x18001979d  mov     eax, ebx
0x18001979f  add     rsp, 68h
0x1800197a3  pop     r14
0x1800197a5  pop     r12
0x1800197a7  pop     rdi
0x1800197a8  pop     rsi
0x1800197a9  pop     rbx
0x1800197aa  pop     rbp
0x1800197ab  retn
```
