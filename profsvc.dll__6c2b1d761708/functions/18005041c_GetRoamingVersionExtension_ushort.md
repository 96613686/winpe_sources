# GetRoamingVersionExtension(ushort * *)

- ea: `0x18005041c`
- end: `0x180050514`
- name: `?GetRoamingVersionExtension@@YAJPEAPEAG@Z`
- size: `248`
- prototype: `int(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e380`
- `0x18004fcbc`

## callees

- `0x18001e690`
- `0x180022440`
- `0x180030ad0`
- `0x18004f7fc`
- `0x18005041c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800504cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800504cd`

## string_xrefs

- `0x1800504f1`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180050451`: `System\CurrentControlSet\Services\ProfSvc\Parameters`
- `0x18005049a`: `System\CurrentControlSet\Services\ProfSvc\Parameters`
- `0x18005044a`: `UseProfilePathMinorExtensionVersion`
- `0x180050493`: `UseProfilePathExtensionVersion`

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
0x18005041c  push    rbp
0x18005041e  push    rbx
0x18005041f  push    rdi; int
0x180050420  mov     rbp, rsp
0x180050423  sub     rsp, 20h
0x180050427  mov     rdi, rcx
0x18005042a  mov     qword ptr [rcx], 0
0x180050431  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180050438  mov     [rbp+arg_8], 0
0x18005043f  lea     r9, [rbp+arg_0]; unsigned int *
0x180050443  mov     [rbp+arg_0], 0
0x18005044a  lea     r8, aUseprofilepath; "UseProfilePathMinorExtensionVersion"
0x180050451  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Pr"...
0x180050458  lea     rbx, aV6; ".V6"
0x18005045f  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180050464  test    eax, eax
0x180050466  js      short loc_180050488
0x180050468  cmp     [rbp+arg_0], 0
0x18005046c  lea     rbx, aV611; ".V6.11"
0x180050473  lea     rax, aV2; ".V2"
0x18005047a  cmovz   rbx, rax
0x18005047e  lea     rdx, [rbp+arg_0]
0x180050482  mov     [rbp+arg_10], rbx
0x180050486  jmp     short loc_1800504C4
0x180050488  lea     r9, [rbp+arg_8]; unsigned int *
0x18005048c  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180050493  lea     r8, aUseprofilepath_0; "UseProfilePathExtensionVersion"
0x18005049a  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Pr"...
0x1800504a1  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800504a6  test    eax, eax
0x1800504a8  js      short loc_1800504CD
0x1800504aa  cmp     [rbp+arg_8], 0
0x1800504ae  lea     rax, aV2; ".V2"
0x1800504b5  lea     rdx, [rbp+arg_8]
0x1800504b9  cmovnz  rax, rbx
0x1800504bd  mov     rbx, rax
0x1800504c0  mov     [rbp+arg_10], rax
0x1800504c4  lea     rcx, [rbp+arg_10]
0x1800504c8  call    ??$RoamingVersionKeyFound@AEAPEBGAEAK@ProfileTelemetry@@SAXAEAPEBGAEAK@Z; ProfileTelemetry::RoamingVersionKeyFound<ushort const * &,ulong &>(ushort const * &,ulong &)
0x1800504cd  call    cs:__imp_GetProcessHeap
0x1800504d4  nop     dword ptr [rax+rax+00h]
0x1800504d9  mov     r9, rdi
0x1800504dc  mov     r8, rbx
0x1800504df  mov     rcx, rax
0x1800504e2  call    ??$_AllocString@VCTHeapAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTHeapAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800504e7  mov     ebx, eax
0x1800504e9  test    eax, eax
0x1800504eb  jns     short loc_180050509
0x1800504ed  mov     rcx, [rbp+18h]; this
0x1800504f1  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800504f8  mov     r9d, eax; char *
0x1800504fb  mov     edx, 521h; void *
0x180050500  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050505  mov     eax, ebx
0x180050507  jmp     short loc_18005050B
0x180050509  xor     eax, eax
0x18005050b  add     rsp, 20h
0x18005050f  pop     rdi
0x180050510  pop     rbx
0x180050511  pop     rbp
0x180050512  retn
```
