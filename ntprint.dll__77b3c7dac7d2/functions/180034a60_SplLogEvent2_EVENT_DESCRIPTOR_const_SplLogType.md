# SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)

- ea: `0x180034a60`
- end: `0x180034be6`
- name: `?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ`
- size: `390`
- prototype: `void(const struct _EVENT_DESCRIPTOR *, struct SplLogType *, ...)`
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180020820`
- `0x180031a74`
- `0x1800324ac`
- `0x180032a34`
- `0x180032ea4`
- `0x180033398`
- `0x1800340b4`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180034a60`
- `0x1800353e4`
- `0x180035600`
- `0x180035624`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180034ab8`
- `ntdll!EtwEventEnabled` at `0x180034ab8`
- `ntdll!EtwEventWrite` at `0x180034ba9`
- `ntdll!EtwEventWrite` at `0x180034ba9`

## string_xrefs

- `0x180034bb2`: `Event: %u, EventWrite: %d`

## pseudocode

```c
void SplLogEvent2(const struct _EVENT_DESCRIPTOR *a1, struct SplLogType *a2, ...)
{
  unsigned int Id; // ebx
  unsigned int v4; // r14d
  va_list v5; // r15
  int v6; // r9d
  SplLogType *v7; // r13
  void *v8; // rax
  __int64 v9; // r10
  int v10; // r9d
  unsigned int v11; // eax
  void *Value; // [rsp+38h] [rbp-D0h] BYREF
  _DWORD v13[58]; // [rsp+40h] [rbp-C8h]
  _QWORD v14[28]; // [rsp+44h] [rbp-C4h]
  SplLogType *v15; // [rsp+180h] [rbp+78h]
  va_list va; // [rsp+188h] [rbp+80h] BYREF

  va_start(va, a2);
  if ( a1 )
  {
    v15 = a2;
    if ( g_bTracingEnabled )
    {
      Id = a1->Id;
      if ( (unsigned __int8)EtwEventEnabled(g_splRegistrationHandle, a1) )
      {
        memset_0(&Value, 0, 0xF0u);
        PerfLibTelemetry::WriteDbgTraceInfo("SplLogEvent2", L"Event: %u, to be written...", Id);
        if ( v15 )
        {
          v4 = 1;
          SplLogType::TraceValue(v15, Id, 1u);
          Value = SplLogType::GetValue(v15);
          va_copy(v5, va);
          v13[0] = v6;
          LODWORD(v14[0]) = 0;
          do
          {
            v5 += 8;
            v7 = (SplLogType *)*((_QWORD *)v5 - 1);
            if ( !v7 )
              break;
            SplLogType::TraceValue(*((SplLogType **)v5 - 1), Id, v4 + 1);
            v8 = SplLogType::GetValue(v7);
            *(_QWORD *)&v13[2 * v9 - 2] = v8;
            ++v4;
            v13[2 * v9] = v10;
            LODWORD(v14[v9]) = 0;
          }
          while ( v4 < 0xF );
        }
        else
        {
          v4 = 0;
        }
        v11 = EtwEventWrite(g_splRegistrationHandle, a1, v4, (unsigned __int64)&Value & -(__int64)(v4 != 0));
        PerfLibTelemetry::WriteDbgTraceInfo("SplLogEvent2", L"Event: %u, EventWrite: %d", Id, v11);
      }
    }
  }
}

```

## disassembly

```asm
0x180034a60  test    rcx, rcx
0x180034a63  jz      locret_180034BE5
0x180034a69  mov     rax, rsp
0x180034a6c  mov     [rax+10h], rdx
0x180034a70  mov     [rax+18h], r8
0x180034a74  mov     [rax+20h], r9
0x180034a78  push    rbp
0x180034a79  push    rbx
0x180034a7a  push    rsi
0x180034a7b  push    rdi
0x180034a7c  push    r13
0x180034a7e  push    r14
0x180034a80  push    r15
0x180034a82  lea     rbp, [rax-68h]
0x180034a86  sub     rsp, 130h
0x180034a8d  mov     rax, cs:__security_cookie
0x180034a94  xor     rax, rsp
0x180034a97  mov     [rbp+60h+var_40], rax
0x180034a9b  cmp     cs:?g_bTracingEnabled@@3HA, 0; int g_bTracingEnabled
0x180034aa2  mov     rsi, rcx
0x180034aa5  jz      loc_180034BC8
0x180034aab  movzx   ebx, word ptr [rcx]
0x180034aae  mov     rdx, rcx
0x180034ab1  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x180034ab8  call    cs:__imp_EtwEventEnabled
0x180034abe  test    al, al
0x180034ac0  jz      loc_180034BC8
0x180034ac6  xor     edx, edx; Val
0x180034ac8  lea     rcx, [rsp+160h+var_130]; void *
0x180034acd  mov     r8d, 0F0h; Size
0x180034ad3  mov     edi, ebx
0x180034ad5  call    memset_0
0x180034ada  mov     r8d, ebx
0x180034add  lea     rdx, aEventUToBeWrit; "Event: %u, to be written..."
0x180034ae4  lea     rcx, aSpllogevent2; "SplLogEvent2"
0x180034aeb  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180034af0  mov     rcx, [rbp+60h+arg_8]; this
0x180034af4  test    rcx, rcx
0x180034af7  jz      loc_180034B89
0x180034afd  mov     r14d, 1
0x180034b03  mov     qword ptr [rsp+20h], 0
0x180034b0c  mov     r8d, r14d; unsigned int
0x180034b0f  mov     edx, ebx; unsigned int
0x180034b11  call    ?TraceValue@SplLogType@@QEAAXII@Z; SplLogType::TraceValue(uint,uint)
0x180034b16  mov     rcx, [rbp+60h+arg_8]; this
0x180034b1a  mov     r9d, [rcx+8]
0x180034b1e  call    ?GetValue@SplLogType@@QEAAPEAXXZ; SplLogType::GetValue(void)
0x180034b23  mov     qword ptr [rsp+160h+var_130], rax
0x180034b28  lea     r15, [rbp+60h+arg_10]
0x180034b2f  mov     [rsp+160h+var_128], r9d
0x180034b34  mov     [rsp+160h+var_128+4], 0
0x180034b3c  lea     r15, [r15+8]
0x180034b40  mov     r13, [r15-8]
0x180034b44  test    r13, r13
0x180034b47  jz      short loc_180034B8C
0x180034b49  lea     ebx, [r14+1]
0x180034b4d  mov     edx, edi; unsigned int
0x180034b4f  mov     r8d, ebx; unsigned int
0x180034b52  mov     rcx, r13; this
0x180034b55  call    ?TraceValue@SplLogType@@QEAAXII@Z; SplLogType::TraceValue(uint,uint)
0x180034b5a  mov     r9d, [r13+8]
0x180034b5e  mov     rcx, r13; this
0x180034b61  mov     r10d, r14d
0x180034b64  add     r10, r10
0x180034b67  call    ?GetValue@SplLogType@@QEAAPEAXXZ; SplLogType::GetValue(void)
0x180034b6c  mov     qword ptr [rsp+r10*8+160h+var_130], rax
0x180034b71  mov     r14d, ebx
0x180034b74  mov     [rsp+r10*8+160h+var_128], r9d
0x180034b79  mov     [rsp+r10*8+160h+var_128+4], 0
0x180034b82  cmp     ebx, 0Fh
0x180034b85  jb      short loc_180034B3C
0x180034b87  jmp     short loc_180034B8C
0x180034b89  xor     r14d, r14d
0x180034b8c  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x180034b93  mov     eax, r14d
0x180034b96  neg     eax
0x180034b98  mov     r8d, r14d
0x180034b9b  lea     rax, [rsp+160h+var_130]
0x180034ba0  mov     rdx, rsi
0x180034ba3  sbb     r9, r9
0x180034ba6  and     r9, rax
0x180034ba9  call    cs:__imp_EtwEventWrite
0x180034baf  mov     r8d, edi
0x180034bb2  lea     rdx, aEventUEventwri; "Event: %u, EventWrite: %d"
0x180034bb9  mov     r9d, eax
0x180034bbc  lea     rcx, aSpllogevent2; "SplLogEvent2"
0x180034bc3  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180034bc8  mov     rcx, [rbp+60h+var_40]
0x180034bcc  xor     rcx, rsp; StackCookie
0x180034bcf  call    __security_check_cookie
0x180034bd4  add     rsp, 130h
0x180034bdb  pop     r15
0x180034bdd  pop     r14
0x180034bdf  pop     r13
0x180034be1  pop     rdi
0x180034be2  pop     rsi
0x180034be3  pop     rbx
0x180034be4  pop     rbp
0x180034be5  retn
```
