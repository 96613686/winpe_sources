# SrvRundownKeyList

- ea: `0x180007088`
- end: `0x180007137`
- name: `SrvRundownKeyList`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a5c0`

## callees

- `0x180003cf0`
- `0x180007088`
- `0x180007140`
- `0x18000ba3c`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18000709a`
- `ntdll!RtlEnterCriticalSection` at `0x18000709a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800070bd`

## string_xrefs

- `0x1800070fb`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`

## pseudocode

```c
NTSTATUS __fastcall SrvRundownKeyList(__int64 a1)
{
  __int64 v2; // r8
  _QWORD *v3; // rbx
  __int64 v5; // rsi
  int v6; // eax

  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
  v3 = *(_QWORD **)(a1 + 144);
  while ( v3 != (_QWORD *)(a1 + 144) )
  {
    v5 = (__int64)(v3 - 2);
    v3 = (_QWORD *)*v3;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v2, v5, *(_QWORD *)(v5 + 8) - 1LL);
    *(_QWORD *)(v5 + 8) = 1;
    v6 = SrvRemoveKeyFromList(a1, v5);
    if ( v6 < 0 )
      DebugTraceError(
        (unsigned int)v6,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c",
        597);
  }
  return RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
}

```

## disassembly

```asm
0x180007088  push    rbx
0x18000708a  push    rbp
0x18000708b  push    rsi
0x18000708c  push    rdi
0x18000708d  push    r14
0x18000708f  sub     rsp, 30h
0x180007093  mov     rbp, rcx
0x180007096  add     rcx, 68h ; 'h'; CriticalSection
0x18000709a  call    cs:__imp_RtlEnterCriticalSection
0x1800070a0  lea     rdi, [rbp+90h]
0x1800070a7  mov     rbx, [rdi]
0x1800070aa  cmp     rbx, rdi
0x1800070ad  jnz     short loc_1800070C4
0x1800070af  lea     rcx, [rbp+68h]
0x1800070b3  add     rsp, 30h
0x1800070b7  pop     r14
0x1800070b9  pop     rdi
0x1800070ba  pop     rsi
0x1800070bb  pop     rbp
0x1800070bc  pop     rbx
0x1800070bd  jmp     cs:__imp_RtlLeaveCriticalSection
0x1800070c4  lea     rsi, [rbx-10h]
0x1800070c8  mov     rbx, [rbx]
0x1800070cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070d2  lea     rax, WPP_GLOBAL_Control
0x1800070d9  cmp     rcx, rax
0x1800070dc  jnz     short loc_180007112
0x1800070de  mov     rdx, rsi
0x1800070e1  mov     qword ptr [rsi+8], 1
0x1800070e9  mov     rcx, rbp
0x1800070ec  call    SrvRemoveKeyFromList
0x1800070f1  test    eax, eax
0x1800070f3  jns     short loc_1800070AA
0x1800070f5  mov     r9d, 255h
0x1800070fb  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007102  lea     rdx, aStatus; "Status"
0x180007109  mov     ecx, eax
0x18000710b  call    DebugTraceError
0x180007110  jmp     short loc_1800070AA
0x180007112  test    byte ptr [rcx+1Ch], 20h
0x180007116  jz      short loc_1800070DE
0x180007118  mov     rax, [rsi+8]
0x18000711c  mov     edx, 11h
0x180007121  mov     rcx, [rcx+10h]
0x180007125  dec     rax
0x180007128  mov     r9, rsi
0x18000712b  mov     [rsp+58h+var_38], rax
0x180007130  call    WPP_SF_qq
0x180007135  jmp     short loc_1800070DE
```
