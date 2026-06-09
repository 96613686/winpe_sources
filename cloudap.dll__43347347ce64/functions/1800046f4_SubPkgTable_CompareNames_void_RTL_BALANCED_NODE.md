# SubPkgTable_CompareNames(void *,_RTL_BALANCED_NODE *)

- ea: `0x1800046f4`
- end: `0x180004776`
- name: `?SubPkgTable_CompareNames@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z`
- size: `130`
- prototype: `__int64 __fastcall(PCWSTR SourceString, struct _RTL_BALANCED_NODE *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003ef4`
- `0x180004460`
- `0x180004634`
- `0x18000498c`
- `0x180008060`
- `0x180011960`
- `0x180018a20`
- `0x180022f80`

## callees

- `0x1800046f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000471b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000471b`
- `ntdll!RtlInitUnicodeString` at `0x180004746`
- `ntdll!RtlInitUnicodeString` at `0x180004754`
- `ntdll!RtlInitUnicodeString` at `0x180004746`
- `ntdll!RtlInitUnicodeString` at `0x180004754`
- `ntdll!RtlCompareUnicodeString` at `0x18000476a`
- `ntdll!RtlCompareUnicodeString` at `0x18000476a`

## pseudocode

```c
LONG __fastcall SubPkgTable_CompareNames(PCWSTR SourceString, struct _RTL_BALANCED_NODE *a2)
{
  const WCHAR *v2; // rbx
  UNICODE_STRING String2; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  v2 = (const WCHAR *)&a2[2];
  DestinationString = 0;
  String2 = 0;
  if ( (g_ulTestFlags & 2) != 0 )
    return _o__wcsicmp(SourceString, &a2[2]);
  if ( !SourceString )
    return -(v2 != 0);
  if ( a2 == (struct _RTL_BALANCED_NODE *)-48LL )
    return 1;
  RtlInitUnicodeString(&DestinationString, SourceString);
  RtlInitUnicodeString(&String2, v2);
  return RtlCompareUnicodeString(&DestinationString, &String2, 1u);
}

```

## disassembly

```asm
0x1800046f4  push    rbx
0x1800046f6  sub     rsp, 40h
0x1800046fa  mov     eax, cs:?g_ulTestFlags@@3KA; ulong g_ulTestFlags
0x180004700  lea     rbx, [rdx+30h]
0x180004704  xorps   xmm0, xmm0
0x180004707  xorps   xmm1, xmm1
0x18000470a  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18000470f  movups  xmmword ptr [rsp+48h+String2.Length], xmm1
0x180004714  test    al, 2
0x180004716  jz      short loc_180004723
0x180004718  mov     rdx, rbx
0x18000471b  call    cs:__imp__o__wcsicmp
0x180004721  jmp     short loc_180004770
0x180004723  test    rcx, rcx
0x180004726  jnz     short loc_180004734
0x180004728  xor     eax, eax
0x18000472a  sub     rax, rbx
0x18000472d  neg     rax
0x180004730  sbb     eax, eax
0x180004732  jmp     short loc_180004770
0x180004734  test    rbx, rbx
0x180004737  jnz     short loc_18000473E
0x180004739  lea     eax, [rbx+1]
0x18000473c  jmp     short loc_180004770
0x18000473e  mov     rdx, rcx; SourceString
0x180004741  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180004746  call    cs:__imp_RtlInitUnicodeString
0x18000474c  mov     rdx, rbx; SourceString
0x18000474f  lea     rcx, [rsp+48h+String2]; DestinationString
0x180004754  call    cs:__imp_RtlInitUnicodeString
0x18000475a  mov     r8d, 1; CaseInsensitive
0x180004760  lea     rdx, [rsp+48h+String2]; String2
0x180004765  lea     rcx, [rsp+48h+DestinationString]; String1
0x18000476a  call    cs:__imp_RtlCompareUnicodeString
0x180004770  add     rsp, 40h
0x180004774  pop     rbx
0x180004775  retn
```
