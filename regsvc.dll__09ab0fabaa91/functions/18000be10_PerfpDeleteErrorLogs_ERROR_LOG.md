# PerfpDeleteErrorLogs(ERROR_LOG *)

- ea: `0x18000be10`
- end: `0x18000bef1`
- name: `?PerfpDeleteErrorLogs@@YAXPEAUERROR_LOG@@@Z`
- size: `225`
- prototype: `void __fastcall(struct ERROR_LOG *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000a190`
- `0x18001335c`

## callees

- `0x180008050`
- `0x18000aaa0`
- `0x18000be10`
- `0x18000c954`
- `0x18000ca0c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000beb0`
- `ntdll!RtlLeaveCriticalSection` at `0x18000beb0`
- `ntdll!RtlEnterCriticalSection` at `0x18000be5a`
- `ntdll!RtlEnterCriticalSection` at `0x18000be5a`

## pseudocode

```c
void __fastcall PerfpDeleteErrorLogs(struct ERROR_LOG *a1)
{
  struct ERROR_LOG *v1; // rdi
  __int64 v3; // rdx
  __int64 v4; // r8
  unsigned int *p_el_len; // rsi

  v1 = *(struct ERROR_LOG **)&a1->el_len;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids, a1);
  RtlEnterCriticalSection(&PerfpCritSect);
  while ( v1 != a1 )
  {
    p_el_len = &v1->el_len;
    v1 = *(struct ERROR_LOG **)&v1->el_len;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_dqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, v4, p_el_len[4], p_el_len, a1);
    operator delete(p_el_len);
  }
  *(_QWORD *)&a1->el_time = a1;
  *(_QWORD *)&a1->el_len = a1;
  RtlLeaveCriticalSection(&PerfpCritSect);
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids);
}

```

## disassembly

```asm
0x18000be10  mov     [rsp+arg_0], rbx
0x18000be15  mov     [rsp+arg_8], rsi
0x18000be1a  push    rdi
0x18000be1b  sub     rsp, 30h
0x18000be1f  mov     rdi, [rcx]
0x18000be22  mov     rbx, rcx
0x18000be25  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be2c  test    dword ptr [rcx+1Ch], 800h
0x18000be33  jz      short loc_18000BE53
0x18000be35  cmp     byte ptr [rcx+19h], 4
0x18000be39  jb      short loc_18000BE53
0x18000be3b  mov     rcx, [rcx+10h]
0x18000be3f  lea     r8, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids
0x18000be46  mov     edx, 23h ; '#'
0x18000be4b  mov     r9, rbx
0x18000be4e  call    WPP_SF_q
0x18000be53  lea     rcx, ?PerfpCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000be5a  call    cs:__imp_RtlEnterCriticalSection
0x18000be60  jmp     short loc_18000BE9D
0x18000be62  mov     rsi, rdi
0x18000be65  mov     rdi, [rdi]
0x18000be68  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be6f  test    dword ptr [rcx+1Ch], 800h
0x18000be76  jz      short loc_18000BE95
0x18000be78  cmp     byte ptr [rcx+19h], 4
0x18000be7c  jb      short loc_18000BE95
0x18000be7e  mov     r9d, [rsi+10h]
0x18000be82  mov     rcx, [rcx+10h]
0x18000be86  mov     [rsp+38h+var_10], rbx
0x18000be8b  mov     [rsp+38h+var_18], rsi
0x18000be90  call    WPP_SF_dqq
0x18000be95  mov     rcx, rsi; Block
0x18000be98  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000be9d  cmp     rdi, rbx
0x18000bea0  jnz     short loc_18000BE62
0x18000bea2  lea     rcx, ?PerfpCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000bea9  mov     [rbx+8], rbx
0x18000bead  mov     [rbx], rbx
0x18000beb0  call    cs:__imp_RtlLeaveCriticalSection
0x18000beb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bebd  test    dword ptr [rcx+1Ch], 800h
0x18000bec4  jz      short loc_18000BEE1
0x18000bec6  cmp     byte ptr [rcx+19h], 4
0x18000beca  jb      short loc_18000BEE1
0x18000becc  mov     rcx, [rcx+10h]
0x18000bed0  lea     r8, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids
0x18000bed7  mov     edx, 25h ; '%'
0x18000bedc  call    WPP_SF_
0x18000bee1  mov     rbx, [rsp+38h+arg_0]
0x18000bee6  mov     rsi, [rsp+38h+arg_8]
0x18000beeb  add     rsp, 30h
0x18000beef  pop     rdi
0x18000bef0  retn
```
