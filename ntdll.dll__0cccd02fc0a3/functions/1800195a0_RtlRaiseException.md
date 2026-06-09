# RtlRaiseException

- ea: `0x1800195a0`
- end: `0x180019836`
- name: `RtlRaiseException`
- size: `662`
- prototype: `void __stdcall(PEXCEPTION_RECORD ExceptionRecord)`
- caller_count: `25`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180018640`
- `0x180018bc0`
- `0x18001a0d0`
- `0x18001a420`
- `0x180022aa0`
- `0x180030c98`
- `0x180041df0`
- `0x180042050`
- `0x1800432a0`
- `0x180047428`
- `0x18004a010`
- `0x18004b870`
- `0x18004c44c`
- `0x1800794d0`
- `0x18009c110`
- `0x18009da10`
- `0x18009e348`
- `0x18009f140`
- `0x1800dae28`
- `0x18010e750`
- `0x1801104d4`
- `0x18012f780`
- `0x18012fd20`
- `0x1801623a0`
- `0x180162920`

## callees

- `0x1800195a0`
- `0x180051520`
- `0x180053990`
- `0x1800b6a60`
- `0x1800b6b70`
- `0x1800b7190`
- `0x1801146d0`
- `0x180125c20`
- `0x180125da0`
- `0x180126370`
- `0x180146bcc`
- `0x180161140`
- `0x180162000`
- `0x180162980`
- `0x18016f030`

## pseudocode

```c
void __stdcall RtlRaiseException(PEXCEPTION_RECORD ExceptionRecord)
{
  unsigned int v2; // r14d
  unsigned __int64 v3; // rbx
  __int64 XStateConfiguration2; // rax
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rcx
  void *v7; // rsp
  void *v8; // rsp
  unsigned int v9; // ebx
  ULONG64 v10; // r14
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *v11; // rax
  __int64 v12; // r8
  PEXCEPTION_RECORD v13; // rcx
  unsigned __int64 v14; // rbx
  ULONG64 v15; // rbx
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *v16; // rax
  unsigned __int64 ImageBase; // [rsp+40h] [rbp+0h] BYREF
  unsigned int v18; // [rsp+48h] [rbp+8h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+50h] [rbp+10h] BYREF
  PVOID HandlerData; // [rsp+58h] [rbp+18h] BYREF
  struct _UNWIND_HISTORY_TABLE HistoryTable; // [rsp+60h] [rbp+20h] BYREF
  ULONG64 v22; // [rsp+138h] [rbp+F8h]

  v18 = 0;
  EstablisherFrame = 0;
  HandlerData = 0;
  ImageBase = 0;
  memset_thunk_772440563353939046(HistoryTable.Entry, 0, 0xC0u);
  ExceptionRecord->ExceptionFlags |= 0x80u;
  v2 = 1048587;
  v3 = 0;
  if ( !NtCurrentPeb()->BeingDebugged || (((unsigned __int64)qword_1801E3508 >> 60) & 3) == 1 )
  {
    if ( MEMORY[0x7FFE03D8] )
    {
      v2 = 1048651;
      if ( (MEMORY[0x7FFE03EC] & 2) != 0 )
      {
        v14 = MEMORY[0x7FFE0708] | MEMORY[0x7FFE03D8] | 0x8000000000000000uLL;
        if ( ((MEMORY[0x7FFE0708] | MEMORY[0x7FFE03D8]) & 0x800LL) != 0
          && (((unsigned __int64)qword_1801E3508 >> 60) & 3) != 1 )
        {
          v14 = (MEMORY[0x7FFE0708] | MEMORY[0x7FFE03D8]) & 0x7FFFFFFFFFFFF7FFLL | 0x8000000000000000uLL;
        }
        v3 = v14 & 0xFFFFFFFFFFF9FFFFuLL;
      }
    }
  }
  XStateConfiguration2 = RtlpGetXStateConfiguration2(v2);
  RtlGetExtendedContextLength3(v2, &v18, v3, XStateConfiguration2);
  v5 = v18 + 15LL;
  if ( v5 <= v18 )
    v5 = 0xFFFFFFFFFFFFFF0LL;
  v6 = v5 & 0xFFFFFFFFFFFFFFF0uLL;
  v7 = alloca(v6);
  v8 = alloca(v6);
  v9 = RtlInitializeExtendedContext2(&ImageBase, v2, &v18, v3);
  RtlpCaptureContext2(&ImageBase);
  v10 = v22;
  HistoryTable.Count = 0;
  *(_DWORD *)&HistoryTable.LocalHint = 0x1000000;
  HistoryTable.LowAddress = -1;
  HistoryTable.HighAddress = 0;
  v11 = RtlLookupFunctionEntry(v22, &ImageBase, &HistoryTable);
  if ( !v11 )
LABEL_6:
    RtlRaiseStatus(v9);
  RtlVirtualUnwind(0, ImageBase, v10, v11, (PCONTEXT)&ImageBase, &HandlerData, &EstablisherFrame, 0);
  if ( ExceptionRecord->ExceptionCode == -2147483597 )
  {
    v15 = v22;
    v16 = RtlLookupFunctionEntry(v22, &ImageBase, &HistoryTable);
    if ( v16 )
      RtlVirtualUnwind(0, ImageBase, v15, v16, (PCONTEXT)&ImageBase, &HandlerData, &EstablisherFrame, 0);
  }
  ExceptionRecord->ExceptionAddress = (void *)v22;
  RtlpGuardSynchronizeRestorePc(v22);
  v13 = ExceptionRecord;
  if ( NtCurrentPeb()->BeingDebugged )
  {
    LOBYTE(v12) = 1;
LABEL_17:
    v9 = ZwRaiseException(v13, &ImageBase, v12);
    goto LABEL_6;
  }
  if ( !(unsigned __int8)RtlDispatchException(ExceptionRecord, &ImageBase) )
  {
    v12 = 0;
    v13 = ExceptionRecord;
    goto LABEL_17;
  }
  RtlRestoreContext((PCONTEXT)&ImageBase, ExceptionRecord);
}

```

## disassembly

```asm
0x1800195a0  push    rbp
0x1800195a2  push    rbx
0x1800195a3  push    rsi
0x1800195a4  push    rdi
0x1800195a5  push    r14
0x1800195a7  push    r15
0x1800195a9  sub     rsp, 158h
0x1800195b0  lea     rbp, [rsp+40h]
0x1800195b5  mov     rax, cs:__security_cookie
0x1800195bc  xor     rax, rbp
0x1800195bf  mov     [rbp+140h+var_40], rax
0x1800195c6  xor     r15d, r15d
0x1800195c9  mov     rsi, rcx
0x1800195cc  lea     rcx, [rbp+140h+HistoryTable.Entry]; void *
0x1800195d0  mov     [rbp+140h+var_138], r15d
0x1800195d4  xor     edx, edx; Val
0x1800195d6  mov     [rbp+140h+var_130], r15
0x1800195da  mov     r8d, 0C0h; Size
0x1800195e0  mov     [rbp+140h+var_128], r15
0x1800195e4  mov     [rbp+140h+ImageBase], r15
0x1800195e8  call    memset$thunk$772440563353939046
0x1800195ed  bts     dword ptr [rsi+4], 7
0x1800195f2  mov     r14d, 10000Bh
0x1800195f8  mov     rax, gs:60h
0x180019601  mov     ebx, r15d
0x180019604  mov     rcx, cs:qword_1801E3508
0x18001960b  cmp     [rax+2], r15b
0x18001960f  jnz     loc_1800197CE
0x180019615  mov     rax, ds:7FFE03D8h
0x18001961d  test    rax, rax
0x180019620  jnz     loc_180019762
0x180019626  mov     ecx, r14d
0x180019629  call    RtlpGetXStateConfiguration2
0x18001962e  mov     r9, rax
0x180019631  lea     rdx, [rbp+140h+var_138]
0x180019635  mov     ecx, r14d
0x180019638  mov     r8, rbx
0x18001963b  call    RtlGetExtendedContextLength3
0x180019640  mov     eax, [rbp+140h+var_138]
0x180019643  lea     rcx, [rax+0Fh]
0x180019647  cmp     rcx, rax
0x18001964a  ja      short loc_180019656
0x18001964c  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180019656  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001965a  mov     rax, rcx
0x18001965d  call    _alloca_probe
0x180019662  sub     rsp, rcx
0x180019665  lea     r8, [rbp+140h+var_138]
0x180019669  mov     r9, rbx
0x18001966c  mov     edx, r14d
0x18001966f  lea     rdi, [rsp+180h+ImageBase]
0x180019674  mov     rcx, rdi
0x180019677  call    RtlInitializeExtendedContext2
0x18001967c  mov     rcx, rdi
0x18001967f  mov     ebx, eax
0x180019681  call    RtlpCaptureContext2
0x180019686  mov     r14, [rdi+0F8h]
0x18001968d  lea     r8, [rbp+140h+HistoryTable]; HistoryTable
0x180019691  mov     rcx, r14; ControlPc
0x180019694  mov     [rbp+140h+HistoryTable.Count], r15d
0x180019698  lea     rdx, [rbp+140h+ImageBase]; ImageBase
0x18001969c  mov     dword ptr [rbp+140h+HistoryTable.LocalHint], 1000000h
0x1800196a3  mov     [rbp+140h+HistoryTable.LowAddress], 0FFFFFFFFFFFFFFFFh
0x1800196ab  mov     [rbp+140h+HistoryTable.HighAddress], r15
0x1800196af  call    RtlLookupFunctionEntry
0x1800196b4  test    rax, rax
0x1800196b7  jnz     short loc_1800196C1
0x1800196b9  mov     ecx, ebx
0x1800196bb  call    RtlRaiseStatus
0x1800196c1  mov     rdx, [rbp+140h+ImageBase]; ImageBase
0x1800196c5  lea     rcx, [rbp+140h+var_130]
0x1800196c9  mov     [rsp+180h+ContextPointers], r15; ContextPointers
0x1800196ce  mov     r9, rax; FunctionEntry
0x1800196d1  mov     [rsp+180h+EstablisherFrame], rcx; EstablisherFrame
0x1800196d6  mov     r8, r14; ControlPc
0x1800196d9  lea     rcx, [rbp+140h+var_128]
0x1800196dd  mov     [rsp+180h+HandlerData], rcx; HandlerData
0x1800196e2  xor     ecx, ecx; HandlerType
0x1800196e4  mov     [rsp+180h+ContextRecord], rdi; ContextRecord
0x1800196e9  call    RtlVirtualUnwind
0x1800196ee  cmp     dword ptr [rsi], 80000033h
0x1800196f4  jz      loc_1800197E4
0x1800196fa  mov     rax, [rdi+0F8h]
0x180019701  mov     [rsi+10h], rax
0x180019705  mov     rcx, [rdi+0F8h]
0x18001970c  call    RtlpGuardSynchronizeRestorePc
0x180019711  mov     rax, gs:60h
0x18001971a  mov     rdx, rdi
0x18001971d  mov     rcx, rsi
0x180019720  cmp     [rax+2], r15b
0x180019724  jnz     loc_1800197B4
0x18001972a  call    RtlDispatchException
0x18001972f  test    al, al
0x180019731  jz      loc_1800197C3
0x180019737  mov     rdx, rsi; ExceptionRecord
0x18001973a  mov     rcx, rdi; ContextRecord
0x18001973d  call    RtlRestoreContext
0x180019742  mov     rcx, [rbp+140h+var_40]
0x180019749  xor     rcx, rbp; StackCookie
0x18001974c  call    __security_check_cookie
0x180019751  lea     rsp, [rbp+118h]
0x180019758  pop     r15
0x18001975a  pop     r14
0x18001975c  pop     rdi
0x18001975d  pop     rsi
0x18001975e  pop     rbx
0x18001975f  pop     rbp
0x180019760  retn
0x180019762  test    byte ptr ds:7FFE03ECh, 2
0x18001976a  mov     r14d, 10004Bh
0x180019770  jz      loc_180019626
0x180019776  mov     rbx, rax
0x180019779  mov     rax, 8000000000000000h
0x180019783  or      rbx, ds:7FFE0708h
0x18001978b  or      rbx, rax
0x18001978e  bt      rbx, 0Bh
0x180019793  jb      short loc_1800197A1
0x180019795  and     rbx, 0FFFFFFFFFFF9FFFFh
0x18001979c  jmp     loc_180019626
0x1800197a1  shr     rcx, 3Ch
0x1800197a5  and     cl, 3
0x1800197a8  cmp     cl, 1
0x1800197ab  jz      short loc_180019795
0x1800197ad  btr     rbx, 0Bh
0x1800197b2  jmp     short loc_180019795
0x1800197b4  mov     r8b, 1
0x1800197b7  call    ZwRaiseException
0x1800197bc  mov     ebx, eax
0x1800197be  jmp     loc_1800196B9
0x1800197c3  xor     r8d, r8d
0x1800197c6  mov     rdx, rdi
0x1800197c9  mov     rcx, rsi
0x1800197cc  jmp     short loc_1800197B7
0x1800197ce  mov     rax, rcx
0x1800197d1  shr     rax, 3Ch
0x1800197d5  and     al, 3
0x1800197d7  cmp     al, 1
0x1800197d9  jnz     loc_180019626
0x1800197df  jmp     loc_180019615
0x1800197e4  mov     rbx, [rdi+0F8h]
0x1800197eb  lea     r8, [rbp+140h+HistoryTable]; HistoryTable
0x1800197ef  mov     rcx, rbx; ControlPc
0x1800197f2  lea     rdx, [rbp+140h+ImageBase]; ImageBase
0x1800197f6  call    RtlLookupFunctionEntry
0x1800197fb  test    rax, rax
0x1800197fe  jz      loc_1800196FA
0x180019804  mov     rdx, [rbp+140h+ImageBase]; ImageBase
0x180019808  lea     rcx, [rbp+140h+var_130]
0x18001980c  mov     [rsp+180h+ContextPointers], r15; ContextPointers
0x180019811  mov     r9, rax; FunctionEntry
0x180019814  mov     [rsp+180h+EstablisherFrame], rcx; EstablisherFrame
0x180019819  mov     r8, rbx; ControlPc
0x18001981c  lea     rcx, [rbp+140h+var_128]
0x180019820  mov     [rsp+180h+HandlerData], rcx; HandlerData
0x180019825  xor     ecx, ecx; HandlerType
0x180019827  mov     [rsp+180h+ContextRecord], rdi; ContextRecord
0x18001982c  call    RtlVirtualUnwind
0x180019831  jmp     loc_1800196FA
```
