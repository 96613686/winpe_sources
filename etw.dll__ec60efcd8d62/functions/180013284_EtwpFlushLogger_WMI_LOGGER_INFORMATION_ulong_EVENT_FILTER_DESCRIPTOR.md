# EtwpFlushLogger(_WMI_LOGGER_INFORMATION *,ulong,_EVENT_FILTER_DESCRIPTOR *)

- ea: `0x180013284`
- end: `0x180013494`
- name: `?EtwpFlushLogger@@YAKPEAU_WMI_LOGGER_INFORMATION@@KPEAU_EVENT_FILTER_DESCRIPTOR@@@Z`
- size: `528`
- prototype: `unsigned int __fastcall(struct _WMI_LOGGER_INFORMATION *, unsigned int, struct _EVENT_FILTER_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1800099c0`
- `0x18000a300`

## callees

- `0x180001eca`
- `0x180001ee2`
- `0x180013284`
- `0x180013504`
- `0x18001356c`
- `0x180014468`

## import_xrefs

- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800132c1`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800132f0`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180013321`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180013390`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800133cd`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180013405`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800132c1`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800132f0`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180013321`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180013390`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800133cd`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180013405`

## pseudocode

```c
NTSTATUS __fastcall EtwpFlushLogger(
        struct _WMI_LOGGER_INFORMATION *a1,
        __int64 a2,
        struct _EVENT_FILTER_DESCRIPTOR *a3)
{
  bool v3; // zf
  unsigned int v5; // r12d
  __int64 v7; // rdx
  __int64 v8; // r14
  __int64 v9; // rcx
  char v10; // r15
  __int64 v11; // rdx
  __int64 v12; // rbp
  __int64 v13; // rcx
  __int64 v14; // rsi
  __int64 v15; // rcx
  char v16; // r13
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned int v19; // ebx
  NTSTATUS result; // eax
  char v21; // [rsp+70h] [rbp+8h]
  int v22; // [rsp+88h] [rbp+20h] BYREF

  v3 = (*((_DWORD *)a1 + 16) & 0x800) == 0;
  v5 = a2;
  v22 = 0;
  if ( !v3 || (*((_BYTE *)a1 + 11) & 1) != 0 )
    return EtwpSendUmLogRequest(5, a1, (unsigned int)a2, a3);
  v8 = 2147353480;
  if ( (unsigned int)RtlGetCurrentServiceSessionId(a1, a2) )
    v9 = (__int64)NtCurrentPeb()->HotpatchInformation + 558;
  else
    v9 = 2147353480;
  v10 = *(_BYTE *)v9;
  v12 = 2147353472;
  if ( (unsigned int)RtlGetCurrentServiceSessionId(v9, v7) )
    v13 = (__int64)NtCurrentPeb()->HotpatchInformation + 550;
  else
    v13 = 2147353472;
  v21 = *(_BYTE *)v13;
  v14 = 2147353482;
  if ( (unsigned int)RtlGetCurrentServiceSessionId(v13, v11) )
    v15 = (__int64)NtCurrentPeb()->HotpatchInformation + 560;
  else
    v15 = 2147353482;
  v16 = *(_BYTE *)v15;
  if ( (v10 || v21 || v16) && (EtwpQueryLogger(a1, v5, a3) & 0x80000000) == 0 && (*((_DWORD *)a1 + 16) & 0x400) != 0 )
  {
    v19 = *((unsigned __int16 *)a1 + 4);
    if ( v10 )
    {
      if ( (unsigned int)RtlGetCurrentServiceSessionId(v18, v17) )
        v8 = (__int64)NtCurrentPeb()->HotpatchInformation + 558;
      if ( (_WORD)v19 == *(unsigned __int8 *)v8 )
        EtwpHeapRundown(v19, 2);
    }
    if ( v21 )
    {
      if ( (unsigned int)RtlGetCurrentServiceSessionId(v18, v17) )
        v12 = (__int64)NtCurrentPeb()->HotpatchInformation + 550;
      if ( (_WORD)v19 == *(unsigned __int8 *)v12 )
        EtwpHeapRundown(v19, 0);
    }
    if ( v16 )
    {
      if ( (unsigned int)RtlGetCurrentServiceSessionId(v18, v17) )
        v14 = (__int64)NtCurrentPeb()->HotpatchInformation + 560;
      if ( (_WORD)v19 == *(unsigned __int8 *)v14 )
        EtwpHeapRundown(v19, 1);
    }
  }
  result = NtTraceControl_0(5, a1, *(unsigned int *)a1, a1, *(_DWORD *)a1, &v22);
  if ( result )
    return RtlNtStatusToDosError_0(result);
  return result;
}

```

## disassembly

```asm
0x180013284  mov     rax, rsp
0x180013287  mov     [rax+10h], rbx
0x18001328b  push    rbp
0x18001328c  push    rsi
0x18001328d  push    rdi
0x18001328e  push    r12
0x180013290  push    r13
0x180013292  push    r14
0x180013294  push    r15
0x180013296  sub     rsp, 30h
0x18001329a  test    dword ptr [rcx+40h], 800h
0x1800132a1  mov     rbx, r8
0x1800132a4  mov     r12d, edx
0x1800132a7  mov     dword ptr [rax+20h], 0
0x1800132ae  mov     rdi, rcx
0x1800132b1  jnz     loc_18001346C
0x1800132b7  test    byte ptr [rcx+0Bh], 1
0x1800132bb  jnz     loc_18001346C
0x1800132c1  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1800132c7  mov     r14d, 7FFE0388h
0x1800132cd  test    eax, eax
0x1800132cf  jz      short loc_1800132EA
0x1800132d1  mov     rax, gs:60h
0x1800132da  mov     rcx, [rax+90h]
0x1800132e1  add     rcx, 22Eh
0x1800132e8  jmp     short loc_1800132ED
0x1800132ea  mov     rcx, r14
0x1800132ed  mov     r15b, [rcx]
0x1800132f0  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1800132f6  mov     ebp, 7FFE0380h
0x1800132fb  test    eax, eax
0x1800132fd  jz      short loc_180013318
0x1800132ff  mov     rax, gs:60h
0x180013308  mov     rcx, [rax+90h]
0x18001330f  add     rcx, 226h
0x180013316  jmp     short loc_18001331B
0x180013318  mov     rcx, rbp
0x18001331b  mov     al, [rcx]
0x18001331d  mov     [rsp+68h+arg_0], al
0x180013321  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180013327  mov     esi, 7FFE038Ah
0x18001332c  test    eax, eax
0x18001332e  jz      short loc_180013349
0x180013330  mov     rax, gs:60h
0x180013339  mov     rcx, [rax+90h]
0x180013340  add     rcx, 230h
0x180013347  jmp     short loc_18001334C
0x180013349  mov     rcx, rsi
0x18001334c  mov     r13b, [rcx]
0x18001334f  test    r15b, r15b
0x180013352  jnz     short loc_180013364
0x180013354  cmp     [rsp+68h+arg_0], r15b
0x180013359  jnz     short loc_180013364
0x18001335b  test    r13b, r13b
0x18001335e  jz      loc_18001343A
0x180013364  mov     r8, rbx; struct _EVENT_FILTER_DESCRIPTOR *
0x180013367  mov     edx, r12d; unsigned int
0x18001336a  mov     rcx, rdi; struct _WMI_LOGGER_INFORMATION *
0x18001336d  call    ?EtwpQueryLogger@@YAKPEAU_WMI_LOGGER_INFORMATION@@KPEAU_EVENT_FILTER_DESCRIPTOR@@@Z; EtwpQueryLogger(_WMI_LOGGER_INFORMATION *,ulong,_EVENT_FILTER_DESCRIPTOR *)
0x180013372  test    eax, eax
0x180013374  js      loc_18001343A
0x18001337a  test    dword ptr [rdi+40h], 400h
0x180013381  jz      loc_18001343A
0x180013387  movzx   ebx, word ptr [rdi+8]
0x18001338b  test    r15b, r15b
0x18001338e  jz      short loc_1800133C6
0x180013390  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180013396  test    eax, eax
0x180013398  jz      short loc_1800133B1
0x18001339a  mov     rax, gs:60h
0x1800133a3  mov     r14, [rax+90h]
0x1800133aa  add     r14, 22Eh
0x1800133b1  movzx   eax, byte ptr [r14]
0x1800133b5  cmp     bx, ax
0x1800133b8  jnz     short loc_1800133C6
0x1800133ba  mov     ecx, ebx
0x1800133bc  mov     edx, 2
0x1800133c1  call    ?EtwpHeapRundown@@YAJKW4_HEAP_RUNDOWN_CLASS@@@Z; EtwpHeapRundown(ulong,_HEAP_RUNDOWN_CLASS)
0x1800133c6  cmp     [rsp+68h+arg_0], 0
0x1800133cb  jz      short loc_180013400
0x1800133cd  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1800133d3  test    eax, eax
0x1800133d5  jz      short loc_1800133EE
0x1800133d7  mov     rax, gs:60h
0x1800133e0  mov     rbp, [rax+90h]
0x1800133e7  add     rbp, 226h
0x1800133ee  movzx   eax, byte ptr [rbp+0]
0x1800133f2  cmp     bx, ax
0x1800133f5  jnz     short loc_180013400
0x1800133f7  mov     ecx, ebx
0x1800133f9  xor     edx, edx
0x1800133fb  call    ?EtwpHeapRundown@@YAJKW4_HEAP_RUNDOWN_CLASS@@@Z; EtwpHeapRundown(ulong,_HEAP_RUNDOWN_CLASS)
0x180013400  test    r13b, r13b
0x180013403  jz      short loc_18001343A
0x180013405  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18001340b  test    eax, eax
0x18001340d  jz      short loc_180013426
0x18001340f  mov     rax, gs:60h
0x180013418  mov     rsi, [rax+90h]
0x18001341f  add     rsi, 230h
0x180013426  movzx   eax, byte ptr [rsi]
0x180013429  cmp     bx, ax
0x18001342c  jnz     short loc_18001343A
0x18001342e  mov     ecx, ebx
0x180013430  mov     edx, 1
0x180013435  call    ?EtwpHeapRundown@@YAJKW4_HEAP_RUNDOWN_CLASS@@@Z; EtwpHeapRundown(ulong,_HEAP_RUNDOWN_CLASS)
0x18001343a  mov     r8d, [rdi]
0x18001343d  lea     rax, [rsp+68h+arg_18]
0x180013445  mov     [rsp+68h+var_40], rax
0x18001344a  mov     r9, rdi
0x18001344d  mov     rdx, rdi
0x180013450  mov     [rsp+68h+var_48], r8d
0x180013455  mov     ecx, 5
0x18001345a  call    NtTraceControl_0
0x18001345f  test    eax, eax
0x180013461  jz      short loc_18001347F
0x180013463  mov     ecx, eax; Status
0x180013465  call    RtlNtStatusToDosError_0
0x18001346a  jmp     short loc_18001347F
0x18001346c  mov     r9, rbx
0x18001346f  mov     r8d, r12d
0x180013472  mov     rdx, rdi
0x180013475  mov     ecx, 5
0x18001347a  call    ?EtwpSendUmLogRequest@@YAKW4ETWTRACECONTROLCODE@@PEAU_WMI_LOGGER_INFORMATION@@KPEAU_EVENT_FILTER_DESCRIPTOR@@@Z; EtwpSendUmLogRequest(ETWTRACECONTROLCODE,_WMI_LOGGER_INFORMATION *,ulong,_EVENT_FILTER_DESCRIPTOR *)
0x18001347f  mov     rbx, [rsp+68h+arg_8]
0x180013484  add     rsp, 30h
0x180013488  pop     r15
0x18001348a  pop     r14
0x18001348c  pop     r13
0x18001348e  pop     r12
0x180013490  pop     rdi
0x180013491  pop     rsi
0x180013492  pop     rbp
0x180013493  retn
```
