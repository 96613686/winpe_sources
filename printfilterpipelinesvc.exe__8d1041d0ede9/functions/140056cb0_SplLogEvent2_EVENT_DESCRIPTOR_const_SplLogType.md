# SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)

- ea: `0x140056cb0`
- end: `0x140056e36`
- name: `?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ`
- size: `390`
- prototype: `void(const struct _EVENT_DESCRIPTOR *, struct SplLogType *, ...)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400073cc`
- `0x140011af8`
- `0x140056264`

## callees

- `0x140002070`
- `0x140002c68`
- `0x140056cb0`
- `0x140056f40`
- `0x140057384`
- `0x1400573a8`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x140056d08`
- `ntdll!EtwEventEnabled` at `0x140056d08`
- `ntdll!EtwEventWrite` at `0x140056df9`
- `ntdll!EtwEventWrite` at `0x140056df9`

## string_xrefs

- `0x140056e02`: `Event: %u, EventWrite: %d`

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
  __int64 v12; // [rsp+28h] [rbp-E0h]
  void *Value; // [rsp+38h] [rbp-D0h] BYREF
  _DWORD v14[58]; // [rsp+40h] [rbp-C8h]
  _QWORD v15[28]; // [rsp+44h] [rbp-C4h]
  SplLogType *v16; // [rsp+180h] [rbp+78h]
  va_list va; // [rsp+188h] [rbp+80h] BYREF

  va_start(va, a2);
  if ( a1 )
  {
    v16 = a2;
    if ( g_bTracingEnabled )
    {
      Id = a1->Id;
      if ( (unsigned __int8)EtwEventEnabled(g_splRegistrationHandle, a1) )
      {
        memset_0(&Value, 0, 0xF0u);
        PerfLibTelemetry::WriteDbgTraceInfo("SplLogEvent2", L"Event: %u, to be written...", Id);
        if ( v16 )
        {
          v4 = 1;
          v12 = 0;
          SplLogType::TraceValue(v16, Id, 1u);
          Value = SplLogType::GetValue(v16);
          va_copy(v5, va);
          v14[0] = v6;
          LODWORD(v15[0]) = 0;
          do
          {
            v5 += 8;
            v7 = (SplLogType *)*((_QWORD *)v5 - 1);
            if ( !v7 )
              break;
            SplLogType::TraceValue(*((SplLogType **)v5 - 1), Id, v4 + 1);
            v8 = SplLogType::GetValue(v7);
            *(_QWORD *)&v14[2 * v9 - 2] = v8;
            ++v4;
            v14[2 * v9] = v10;
            LODWORD(v15[v9]) = 0;
          }
          while ( v4 < 0xF );
        }
        else
        {
          v4 = 0;
        }
        v11 = EtwEventWrite(g_splRegistrationHandle, a1, v4, (unsigned __int64)&Value & -(__int64)(v4 != 0), v12);
        PerfLibTelemetry::WriteDbgTraceInfo("SplLogEvent2", L"Event: %u, EventWrite: %d", Id, v11);
      }
    }
  }
}

```

## disassembly

```asm
0x140056cb0  test    rcx, rcx
0x140056cb3  jz      locret_140056E35
0x140056cb9  mov     rax, rsp
0x140056cbc  mov     [rax+10h], rdx
0x140056cc0  mov     [rax+18h], r8
0x140056cc4  mov     [rax+20h], r9
0x140056cc8  push    rbp
0x140056cc9  push    rbx
0x140056cca  push    rsi
0x140056ccb  push    rdi
0x140056ccc  push    r13
0x140056cce  push    r14
0x140056cd0  push    r15
0x140056cd2  lea     rbp, [rax-68h]
0x140056cd6  sub     rsp, 130h
0x140056cdd  mov     rax, cs:__security_cookie
0x140056ce4  xor     rax, rsp
0x140056ce7  mov     [rbp+60h+var_40], rax
0x140056ceb  cmp     cs:?g_bTracingEnabled@@3HA, 0; int g_bTracingEnabled
0x140056cf2  mov     rsi, rcx
0x140056cf5  jz      loc_140056E18
0x140056cfb  movzx   ebx, word ptr [rcx]
0x140056cfe  mov     rdx, rcx
0x140056d01  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x140056d08  call    cs:__imp_EtwEventEnabled
0x140056d0e  test    al, al
0x140056d10  jz      loc_140056E18
0x140056d16  xor     edx, edx; Val
0x140056d18  lea     rcx, [rsp+160h+var_130]; void *
0x140056d1d  mov     r8d, 0F0h; Size
0x140056d23  mov     edi, ebx
0x140056d25  call    memset_0
0x140056d2a  mov     r8d, ebx
0x140056d2d  lea     rdx, aEventUToBeWrit; "Event: %u, to be written..."
0x140056d34  lea     rcx, aSpllogevent2; "SplLogEvent2"
0x140056d3b  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140056d40  mov     rcx, [rbp+60h+arg_8]; this
0x140056d44  test    rcx, rcx
0x140056d47  jz      loc_140056DD9
0x140056d4d  mov     r14d, 1
0x140056d53  mov     qword ptr [rsp+20h], 0
0x140056d5c  mov     r8d, r14d; unsigned int
0x140056d5f  mov     edx, ebx; unsigned int
0x140056d61  call    ?TraceValue@SplLogType@@QEAAXII@Z; SplLogType::TraceValue(uint,uint)
0x140056d66  mov     rcx, [rbp+60h+arg_8]; this
0x140056d6a  mov     r9d, [rcx+8]
0x140056d6e  call    ?GetValue@SplLogType@@QEAAPEAXXZ; SplLogType::GetValue(void)
0x140056d73  mov     qword ptr [rsp+160h+var_130], rax
0x140056d78  lea     r15, [rbp+60h+arg_10]
0x140056d7f  mov     [rsp+160h+var_128], r9d
0x140056d84  mov     [rsp+160h+var_128+4], 0
0x140056d8c  lea     r15, [r15+8]
0x140056d90  mov     r13, [r15-8]
0x140056d94  test    r13, r13
0x140056d97  jz      short loc_140056DDC
0x140056d99  lea     ebx, [r14+1]
0x140056d9d  mov     edx, edi; unsigned int
0x140056d9f  mov     r8d, ebx; unsigned int
0x140056da2  mov     rcx, r13; this
0x140056da5  call    ?TraceValue@SplLogType@@QEAAXII@Z; SplLogType::TraceValue(uint,uint)
0x140056daa  mov     r9d, [r13+8]
0x140056dae  mov     rcx, r13; this
0x140056db1  mov     r10d, r14d
0x140056db4  add     r10, r10
0x140056db7  call    ?GetValue@SplLogType@@QEAAPEAXXZ; SplLogType::GetValue(void)
0x140056dbc  mov     qword ptr [rsp+r10*8+160h+var_130], rax
0x140056dc1  mov     r14d, ebx
0x140056dc4  mov     [rsp+r10*8+160h+var_128], r9d
0x140056dc9  mov     [rsp+r10*8+160h+var_128+4], 0
0x140056dd2  cmp     ebx, 0Fh
0x140056dd5  jb      short loc_140056D8C
0x140056dd7  jmp     short loc_140056DDC
0x140056dd9  xor     r14d, r14d
0x140056ddc  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x140056de3  mov     eax, r14d
0x140056de6  neg     eax
0x140056de8  mov     r8d, r14d
0x140056deb  lea     rax, [rsp+160h+var_130]
0x140056df0  mov     rdx, rsi
0x140056df3  sbb     r9, r9
0x140056df6  and     r9, rax
0x140056df9  call    cs:__imp_EtwEventWrite
0x140056dff  mov     r8d, edi
0x140056e02  lea     rdx, aEventUEventwri; "Event: %u, EventWrite: %d"
0x140056e09  mov     r9d, eax
0x140056e0c  lea     rcx, aSpllogevent2; "SplLogEvent2"
0x140056e13  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140056e18  mov     rcx, [rbp+60h+var_40]
0x140056e1c  xor     rcx, rsp; StackCookie
0x140056e1f  call    __security_check_cookie
0x140056e24  add     rsp, 130h
0x140056e2b  pop     r15
0x140056e2d  pop     r14
0x140056e2f  pop     r13
0x140056e31  pop     rdi
0x140056e32  pop     rsi
0x140056e33  pop     rbx
0x140056e34  pop     rbp
0x140056e35  retn
```
