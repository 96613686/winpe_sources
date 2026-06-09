# EtwpStartLogger(_WMI_LOGGER_INFORMATION *,ulong,_EVENT_FILTER_DESCRIPTOR *)

- ea: `0x1800137e4`
- end: `0x1800138c7`
- name: `?EtwpStartLogger@@YAKPEAU_WMI_LOGGER_INFORMATION@@KPEAU_EVENT_FILTER_DESCRIPTOR@@@Z`
- size: `227`
- prototype: `unsigned int __fastcall(struct _WMI_LOGGER_INFORMATION *, unsigned int, struct _EVENT_FILTER_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c4a0`
- `0x18000cca0`

## callees

- `0x180001eca`
- `0x180001ee2`
- `0x18001356c`
- `0x1800137e4`
- `0x180014468`

## pseudocode

```c
__int64 __fastcall EtwpStartLogger(
        struct _WMI_LOGGER_INFORMATION *a1,
        unsigned int a2,
        struct _EVENT_FILTER_DESCRIPTOR *a3)
{
  unsigned int v4; // eax
  int v5; // esi
  ULONG v6; // edi
  NTSTATUS v7; // eax
  __int64 v8; // rdx
  int v10; // [rsp+40h] [rbp+8h] BYREF

  v4 = *((_DWORD *)a1 + 10) - 1;
  v10 = 0;
  if ( v4 > 3 )
    *((_DWORD *)a1 + 10) = 1;
  v5 = *((_DWORD *)a1 + 16);
  if ( (v5 & 0x800) != 0 )
    return (unsigned int)EtwpSendUmLogRequest(1, (__int64)a1, a2, (__int64)a3);
  v7 = NtTraceControl_0(1, a1, *(unsigned int *)a1, a1, *(_DWORD *)a1, &v10);
  if ( v7 )
  {
    v6 = RtlNtStatusToDosError_0(v7);
    if ( v6 )
      return v6;
  }
  else
  {
    v6 = 0;
  }
  if ( (v5 & 0x400) != 0 )
    return v6;
  if ( *((_QWORD *)a1 + 3) == HeapGuid && *((_QWORD *)a1 + 4) == 0x4AA2F2756B3425A8LL )
  {
    v8 = 0;
LABEL_15:
    EtwpHeapRundown(*((unsigned __int16 *)a1 + 4), v8);
    return v6;
  }
  if ( *((_QWORD *)a1 + 3) == HeapSummaryGuid && *((_QWORD *)a1 + 4) == 0x9614DB2B7DE147A1uLL )
  {
    v8 = 1;
    goto LABEL_15;
  }
  return v6;
}

```

## disassembly

```asm
0x1800137e4  mov     [rsp+arg_8], rbx
0x1800137e9  mov     [rsp+arg_10], rsi
0x1800137ee  push    rdi
0x1800137ef  sub     rsp, 30h
0x1800137f3  mov     eax, [rcx+28h]
0x1800137f6  mov     rbx, rcx
0x1800137f9  dec     eax
0x1800137fb  mov     [rsp+38h+arg_0], 0
0x180013803  cmp     eax, 3
0x180013806  jbe     short loc_18001380F
0x180013808  mov     dword ptr [rcx+28h], 1
0x18001380f  mov     esi, [rcx+40h]
0x180013812  bt      esi, 0Bh
0x180013816  jnb     short loc_180013832
0x180013818  mov     r9, r8
0x18001381b  mov     ecx, 1
0x180013820  mov     r8d, edx
0x180013823  mov     rdx, rbx
0x180013826  call    ?EtwpSendUmLogRequest@@YAKW4ETWTRACECONTROLCODE@@PEAU_WMI_LOGGER_INFORMATION@@KPEAU_EVENT_FILTER_DESCRIPTOR@@@Z; EtwpSendUmLogRequest(ETWTRACECONTROLCODE,_WMI_LOGGER_INFORMATION *,ulong,_EVENT_FILTER_DESCRIPTOR *)
0x18001382b  mov     edi, eax
0x18001382d  jmp     loc_1800138B5
0x180013832  mov     r8d, [rcx]
0x180013835  lea     rax, [rsp+38h+arg_0]
0x18001383a  mov     [rsp+38h+var_10], rax
0x18001383f  mov     r9, rbx
0x180013842  mov     rdx, rbx
0x180013845  mov     [rsp+38h+var_18], r8d
0x18001384a  mov     ecx, 1
0x18001384f  call    NtTraceControl_0
0x180013854  test    eax, eax
0x180013856  jnz     short loc_18001385C
0x180013858  xor     edi, edi
0x18001385a  jmp     short loc_180013869
0x18001385c  mov     ecx, eax; Status
0x18001385e  call    RtlNtStatusToDosError_0
0x180013863  mov     edi, eax
0x180013865  test    eax, eax
0x180013867  jnz     short loc_1800138B5
0x180013869  bt      esi, 0Ah
0x18001386d  jb      short loc_1800138B5
0x18001386f  mov     rax, [rbx+18h]
0x180013873  cmp     rax, cs:HeapGuid
0x18001387a  jnz     short loc_18001388D
0x18001387c  mov     rax, [rbx+20h]
0x180013880  cmp     rax, cs:qword_180017F10
0x180013887  jnz     short loc_18001388D
0x180013889  xor     edx, edx
0x18001388b  jmp     short loc_1800138AC
0x18001388d  mov     rax, [rbx+18h]
0x180013891  cmp     rax, cs:HeapSummaryGuid
0x180013898  jnz     short loc_1800138B5
0x18001389a  mov     rax, [rbx+20h]
0x18001389e  cmp     rax, cs:qword_180017ED0
0x1800138a5  jnz     short loc_1800138B5
0x1800138a7  mov     edx, 1
0x1800138ac  movzx   ecx, word ptr [rbx+8]
0x1800138b0  call    ?EtwpHeapRundown@@YAJKW4_HEAP_RUNDOWN_CLASS@@@Z; EtwpHeapRundown(ulong,_HEAP_RUNDOWN_CLASS)
0x1800138b5  mov     rbx, [rsp+38h+arg_8]
0x1800138ba  mov     eax, edi
0x1800138bc  mov     rsi, [rsp+38h+arg_10]
0x1800138c1  add     rsp, 30h
0x1800138c5  pop     rdi
0x1800138c6  retn
```
