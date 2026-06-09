# _LocateUserCacheEntryByNameHash(_GUID *,ushort const *)

- ea: `0x18003308c`
- end: `0x180033160`
- name: `?_LocateUserCacheEntryByNameHash@@YAPEAU_USER_CACHE_ENTRY@@PEAU_GUID@@PEBG@Z`
- size: `212`
- prototype: `struct _LIST_ENTRY *__fastcall(struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032998`

## callees

- `0x18003308c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800330d9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800330d9`
- `ntdll!RtlInitUnicodeString` at `0x1800330fa`
- `ntdll!RtlInitUnicodeString` at `0x180033108`
- `ntdll!RtlInitUnicodeString` at `0x1800330fa`
- `ntdll!RtlInitUnicodeString` at `0x180033108`
- `ntdll!RtlCompareUnicodeString` at `0x18003311b`
- `ntdll!RtlCompareUnicodeString` at `0x18003311b`

## pseudocode

```c
struct _LIST_ENTRY *__fastcall _LocateUserCacheEntryByNameHash(struct _GUID *a1, const unsigned __int16 *a2)
{
  struct _LIST_ENTRY *i; // rbx
  LONG v5; // eax
  unsigned __int64 v6; // rax
  UNICODE_STRING String2; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  for ( i = g_UserCacheList.Flink; i != &g_UserCacheList; i = i->Flink )
  {
    DestinationString = 0;
    String2 = 0;
    if ( (g_ulTestFlags & 2) != 0 )
    {
      v5 = _o__wcsicmp(&i[6].Blink, a2);
      goto LABEL_10;
    }
    if ( i != (struct _LIST_ENTRY *)-104LL )
    {
      if ( !a2 )
        continue;
      RtlInitUnicodeString(&DestinationString, (PCWSTR)&i[6].Blink);
      RtlInitUnicodeString(&String2, a2);
      v5 = RtlCompareUnicodeString(&DestinationString, &String2, 1u);
LABEL_10:
      if ( v5 )
        continue;
      goto LABEL_11;
    }
    if ( a2 )
      continue;
LABEL_11:
    v6 = *(_QWORD *)&a1->Data1 - (unsigned __int64)i[15].Blink;
    if ( *(struct _LIST_ENTRY **)&a1->Data1 == i[15].Blink )
      v6 = *(_QWORD *)a1->Data4 - (unsigned __int64)i[16].Flink;
    if ( !v6 )
      return i;
  }
  return 0;
}

```

## disassembly

```asm
0x18003308c  mov     [rsp+arg_0], rbx
0x180033091  mov     [rsp+arg_8], rsi
0x180033096  push    rdi
0x180033097  sub     rsp, 40h
0x18003309b  mov     rbx, cs:?g_UserCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_UserCacheList
0x1800330a2  mov     rdi, rdx
0x1800330a5  mov     rsi, rcx
0x1800330a8  lea     rax, ?g_UserCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_UserCacheList
0x1800330af  cmp     rbx, rax
0x1800330b2  jz      loc_18003314E
0x1800330b8  mov     eax, cs:?g_ulTestFlags@@3KA; ulong g_ulTestFlags
0x1800330be  lea     rcx, [rbx+68h]
0x1800330c2  xorps   xmm0, xmm0
0x1800330c5  xorps   xmm1, xmm1
0x1800330c8  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x1800330cd  movups  xmmword ptr [rsp+48h+String2.Length], xmm1
0x1800330d2  test    al, 2
0x1800330d4  jz      short loc_1800330E1
0x1800330d6  mov     rdx, rdi
0x1800330d9  call    cs:__imp__o__wcsicmp
0x1800330df  jmp     short loc_180033121
0x1800330e1  test    rcx, rcx
0x1800330e4  jnz     short loc_1800330ED
0x1800330e6  test    rdi, rdi
0x1800330e9  jnz     short loc_180033141
0x1800330eb  jmp     short loc_180033125
0x1800330ed  test    rdi, rdi
0x1800330f0  jz      short loc_180033141
0x1800330f2  mov     rdx, rcx; SourceString
0x1800330f5  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1800330fa  call    cs:__imp_RtlInitUnicodeString
0x180033100  mov     rdx, rdi; SourceString
0x180033103  lea     rcx, [rsp+48h+String2]; DestinationString
0x180033108  call    cs:__imp_RtlInitUnicodeString
0x18003310e  mov     r8b, 1; CaseInsensitive
0x180033111  lea     rdx, [rsp+48h+String2]; String2
0x180033116  lea     rcx, [rsp+48h+DestinationString]; String1
0x18003311b  call    cs:__imp_RtlCompareUnicodeString
0x180033121  test    eax, eax
0x180033123  jnz     short loc_180033141
0x180033125  mov     rax, [rsi]
0x180033128  sub     rax, [rbx+0F8h]
0x18003312f  jnz     short loc_18003313C
0x180033131  mov     rax, [rsi+8]
0x180033135  sub     rax, [rbx+100h]
0x18003313c  test    rax, rax
0x18003313f  jz      short loc_180033149
0x180033141  mov     rbx, [rbx]
0x180033144  jmp     loc_1800330A8
0x180033149  mov     rax, rbx
0x18003314c  jmp     short loc_180033150
0x18003314e  xor     eax, eax
0x180033150  mov     rbx, [rsp+48h+arg_0]
0x180033155  mov     rsi, [rsp+48h+arg_8]
0x18003315a  add     rsp, 40h
0x18003315e  pop     rdi
0x18003315f  retn
```
