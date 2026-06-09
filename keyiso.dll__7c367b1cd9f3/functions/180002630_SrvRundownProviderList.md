# SrvRundownProviderList

- ea: `0x180002630`
- end: `0x1800026dc`
- name: `SrvRundownProviderList`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a5c0`

## callees

- `0x180002630`
- `0x180003540`
- `0x180003cf0`
- `0x18000ba3c`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180002642`
- `ntdll!RtlEnterCriticalSection` at `0x180002642`
- `ntdll!RtlLeaveCriticalSection` at `0x1800026b0`

## string_xrefs

- `0x18000268b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`

## pseudocode

```c
NTSTATUS __fastcall SrvRundownProviderList(struct _RTL_CRITICAL_SECTION *a1)
{
  __int64 v2; // r8
  _QWORD *p_Type; // rbx
  _QWORD *v4; // rsi
  int v5; // eax

  RtlEnterCriticalSection(a1 + 1);
  p_Type = &a1[2].DebugInfo->Type;
  while ( p_Type != (_QWORD *)&a1[2] )
  {
    v4 = p_Type - 2;
    p_Type = (_QWORD *)*p_Type;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v2, v4, v4[1] - 1LL);
    v4[1] = 1;
    v5 = SrvRemoveProviderFromList(a1, v4);
    if ( v5 < 0 )
      DebugTraceError(
        (unsigned int)v5,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c",
        403);
  }
  return RtlLeaveCriticalSection(a1 + 1);
}

```

## disassembly

```asm
0x180002630  push    rbx
0x180002632  push    rbp
0x180002633  push    rsi
0x180002634  push    rdi
0x180002635  push    r14
0x180002637  sub     rsp, 30h
0x18000263b  mov     rbp, rcx
0x18000263e  add     rcx, 28h ; '('; CriticalSection
0x180002642  call    cs:__imp_RtlEnterCriticalSection
0x180002648  lea     rdi, [rbp+50h]
0x18000264c  mov     rbx, [rdi]
0x18000264f  cmp     rbx, rdi
0x180002652  jz      short loc_1800026A2
0x180002654  lea     rsi, [rbx-10h]
0x180002658  mov     rbx, [rbx]
0x18000265b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002662  lea     rax, WPP_GLOBAL_Control
0x180002669  cmp     rcx, rax
0x18000266c  jnz     short loc_1800026B7
0x18000266e  mov     rdx, rsi
0x180002671  mov     qword ptr [rsi+8], 1
0x180002679  mov     rcx, rbp
0x18000267c  call    SrvRemoveProviderFromList
0x180002681  test    eax, eax
0x180002683  jns     short loc_18000264F
0x180002685  mov     r9d, 193h
0x18000268b  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002692  lea     rdx, aStatus; "Status"
0x180002699  mov     ecx, eax
0x18000269b  call    DebugTraceError
0x1800026a0  jmp     short loc_18000264F
0x1800026a2  lea     rcx, [rbp+28h]
0x1800026a6  add     rsp, 30h
0x1800026aa  pop     r14
0x1800026ac  pop     rdi
0x1800026ad  pop     rsi
0x1800026ae  pop     rbp
0x1800026af  pop     rbx
0x1800026b0  jmp     cs:__imp_RtlLeaveCriticalSection
0x1800026b7  test    byte ptr [rcx+1Ch], 20h
0x1800026bb  jz      short loc_18000266E
0x1800026bd  mov     rax, [rsi+8]
0x1800026c1  mov     edx, 0Ch
0x1800026c6  mov     rcx, [rcx+10h]
0x1800026ca  dec     rax
0x1800026cd  mov     r9, rsi
0x1800026d0  mov     [rsp+58h+var_38], rax
0x1800026d5  call    WPP_SF_qq
0x1800026da  jmp     short loc_18000266E
```
