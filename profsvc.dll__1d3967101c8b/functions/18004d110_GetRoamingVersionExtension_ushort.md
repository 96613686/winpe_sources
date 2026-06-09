# GetRoamingVersionExtension(ushort * *)

- ea: `0x18004d110`
- end: `0x18004d201`
- name: `?GetRoamingVersionExtension@@YAJPEAPEAG@Z`
- size: `241`
- prototype: `int(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800168ec`
- `0x18002cba8`

## callees

- `0x180008360`
- `0x1800164e0`
- `0x18002d2d8`
- `0x18004c7e0`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d1c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d1c1`

## string_xrefs

- `0x18004d1df`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18004d145`: `System\CurrentControlSet\Services\ProfSvc\Parameters`
- `0x18004d18e`: `System\CurrentControlSet\Services\ProfSvc\Parameters`
- `0x18004d13e`: `UseProfilePathMinorExtensionVersion`
- `0x18004d187`: `UseProfilePathExtensionVersion`

## pseudocode

```c
__int64 __fastcall GetRoamingVersionExtension(unsigned __int16 **a1)
{
  const wchar_t *v2; // rbx
  unsigned int *v3; // rdx
  const wchar_t *v4; // rax
  HANDLE ProcessHeap; // rax
  __int64 v6; // rdx
  int v7; // eax
  unsigned int v8; // ebx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  unsigned int v12; // [rsp+40h] [rbp+20h] BYREF
  unsigned int v13; // [rsp+48h] [rbp+28h] BYREF
  const wchar_t *v14; // [rsp+50h] [rbp+30h] BYREF

  *a1 = 0;
  v13 = 0;
  v12 = 0;
  v2 = L".V6";
  if ( SHRegGetDWORD(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\ProfSvc\\Parameters",
         L"UseProfilePathMinorExtensionVersion",
         &v12) < 0 )
  {
    if ( SHRegGetDWORD(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\ProfSvc\\Parameters",
           L"UseProfilePathExtensionVersion",
           &v13) < 0 )
      goto LABEL_10;
    v4 = L".V2";
    v3 = &v13;
    if ( v13 )
      v4 = L".V6";
    v2 = v4;
    v14 = v4;
  }
  else
  {
    v2 = L".V6.11";
    if ( !v12 )
      v2 = L".V2";
    v3 = &v12;
    v14 = v2;
  }
  ProfileTelemetry::RoamingVersionKeyFound<unsigned short const * &,unsigned long &>(&v14, v3);
LABEL_10:
  ProcessHeap = GetProcessHeap();
  v7 = _AllocString<CTHeapAllocPolicy>(ProcessHeap, v6, v2, a1);
  v8 = v7;
  if ( v7 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x521,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
    (const char *)(unsigned int)v7,
    savedregs);
  return v8;
}

```

## disassembly

```asm
0x18004d110  push    rbp
0x18004d112  push    rbx
0x18004d113  push    rdi; int
0x18004d114  mov     rbp, rsp
0x18004d117  sub     rsp, 20h
0x18004d11b  mov     rdi, rcx
0x18004d11e  mov     qword ptr [rcx], 0
0x18004d125  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18004d12c  mov     [rbp+arg_8], 0
0x18004d133  lea     r9, [rbp+arg_0]; unsigned int *
0x18004d137  mov     [rbp+arg_0], 0
0x18004d13e  lea     r8, aUseprofilepath; "UseProfilePathMinorExtensionVersion"
0x18004d145  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Pr"...
0x18004d14c  lea     rbx, aV6; ".V6"
0x18004d153  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18004d158  test    eax, eax
0x18004d15a  js      short loc_18004D17C
0x18004d15c  cmp     [rbp+arg_0], 0
0x18004d160  lea     rbx, aV611; ".V6.11"
0x18004d167  lea     rax, aV2; ".V2"
0x18004d16e  cmovz   rbx, rax
0x18004d172  lea     rdx, [rbp+arg_0]
0x18004d176  mov     [rbp+arg_10], rbx
0x18004d17a  jmp     short loc_18004D1B8
0x18004d17c  lea     r9, [rbp+arg_8]; unsigned int *
0x18004d180  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18004d187  lea     r8, aUseprofilepath_0; "UseProfilePathExtensionVersion"
0x18004d18e  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Pr"...
0x18004d195  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18004d19a  test    eax, eax
0x18004d19c  js      short loc_18004D1C1
0x18004d19e  cmp     [rbp+arg_8], 0
0x18004d1a2  lea     rax, aV2; ".V2"
0x18004d1a9  lea     rdx, [rbp+arg_8]
0x18004d1ad  cmovnz  rax, rbx
0x18004d1b1  mov     rbx, rax
0x18004d1b4  mov     [rbp+arg_10], rax
0x18004d1b8  lea     rcx, [rbp+arg_10]
0x18004d1bc  call    ??$RoamingVersionKeyFound@AEAPEBGAEAK@ProfileTelemetry@@SAXAEAPEBGAEAK@Z; ProfileTelemetry::RoamingVersionKeyFound<ushort const * &,ulong &>(ushort const * &,ulong &)
0x18004d1c1  call    cs:__imp_GetProcessHeap
0x18004d1c7  mov     r9, rdi
0x18004d1ca  mov     r8, rbx
0x18004d1cd  mov     rcx, rax
0x18004d1d0  call    ??$_AllocString@VCTHeapAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTHeapAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18004d1d5  mov     ebx, eax
0x18004d1d7  test    eax, eax
0x18004d1d9  jns     short loc_18004D1F7
0x18004d1db  mov     rcx, [rbp+18h]; this
0x18004d1df  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004d1e6  mov     r9d, eax; char *
0x18004d1e9  mov     edx, 521h; void *
0x18004d1ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d1f3  mov     eax, ebx
0x18004d1f5  jmp     short loc_18004D1F9
0x18004d1f7  xor     eax, eax
0x18004d1f9  add     rsp, 20h
0x18004d1fd  pop     rdi
0x18004d1fe  pop     rbx
0x18004d1ff  pop     rbp
0x18004d200  retn
```
