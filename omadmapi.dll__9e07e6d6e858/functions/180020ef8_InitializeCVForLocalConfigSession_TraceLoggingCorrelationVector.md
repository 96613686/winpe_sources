# InitializeCVForLocalConfigSession(TraceLoggingCorrelationVector *)

- ea: `0x180020ef8`
- end: `0x180021101`
- name: `?InitializeCVForLocalConfigSession@@YAJPEAVTraceLoggingCorrelationVector@@@Z`
- size: `521`
- prototype: `__int64 __fastcall(struct TraceLoggingCorrelationVector *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020df4`

## callees

- `0x180004bfc`
- `0x180004c64`
- `0x180020c74`
- `0x180020ef8`
- `0x1800221d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall InitializeCVForLocalConfigSession(struct TraceLoggingCorrelationVector *a1)
{
  __int64 v2; // rdi
  const unsigned __int16 *v4; // rcx
  const unsigned __int16 *v5; // rcx
  const unsigned __int16 *v6; // rcx
  const unsigned __int16 *v7; // rcx

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_180032DB4 > *(_DWORD *)(v2 + 4) )
  {
    Init_thread_header(&dword_180032DB4);
    if ( dword_180032DB4 == -1 )
    {
      dword_180032660 = 1;
      off_180032668 = &qword_1800321E8;
      byte_180032670 = 0;
      GetCorrelationVectorForDmSession(v5, &byte_180032670);
      Init_thread_footer(&dword_180032DB4);
    }
  }
  Microsoft::Windows::TelemetryLogger::SetCorrelationVector((Microsoft::Windows::TelemetryLogger *)&dword_180032660, a1);
  if ( dword_180032DAC > *(_DWORD *)(v2 + 4) )
  {
    Init_thread_header(&dword_180032DAC);
    if ( dword_180032DAC == -1 )
    {
      dword_180032520 = 1;
      off_180032528 = &qword_1800321B0;
      byte_180032530 = 0;
      GetCorrelationVectorForDmSession(v6, &byte_180032530);
      Init_thread_footer(&dword_180032DAC);
    }
  }
  Microsoft::Windows::TelemetryLogger::SetCorrelationVector((Microsoft::Windows::TelemetryLogger *)&dword_180032520, a1);
  if ( dword_180032DB0 > *(_DWORD *)(v2 + 4) )
  {
    Init_thread_header(&dword_180032DB0);
    if ( dword_180032DB0 == -1 )
    {
      dword_1800325C0 = 1;
      off_1800325C8 = &qword_180032178;
      byte_1800325D0 = 0;
      GetCorrelationVectorForDmSession(v7, &byte_1800325D0);
      Init_thread_footer(&dword_180032DB0);
    }
  }
  Microsoft::Windows::TelemetryLogger::SetCorrelationVector((Microsoft::Windows::TelemetryLogger *)&dword_1800325C0, a1);
  if ( dword_180032DA8 > *(_DWORD *)(v2 + 4) )
  {
    Init_thread_header(&dword_180032DA8);
    if ( dword_180032DA8 == -1 )
    {
      dword_180032480 = 1;
      off_180032488 = &qword_180032140;
      byte_180032490 = 0;
      GetCorrelationVectorForDmSession(v4, &byte_180032490);
      Init_thread_footer(&dword_180032DA8);
    }
  }
  Microsoft::Windows::TelemetryLogger::SetCorrelationVector((Microsoft::Windows::TelemetryLogger *)&dword_180032480, a1);
  return 0;
}

```

## disassembly

```asm
0x180020ef8  mov     [rsp+arg_0], rbx
0x180020efd  mov     [rsp+arg_8], rdi
0x180020f02  push    r14
0x180020f04  sub     rsp, 20h
0x180020f08  mov     rbx, rcx
0x180020f0b  mov     edx, cs:_tls_index
0x180020f11  mov     rax, gs:58h
0x180020f1a  mov     r14d, 4
0x180020f20  mov     rdi, [rax+rdx*8]
0x180020f24  mov     eax, [rdi+r14]
0x180020f28  cmp     cs:dword_180032DB4, eax
0x180020f2e  jg      loc_180020FFF
0x180020f34  mov     rdx, rbx; struct TraceLoggingCorrelationVector *
0x180020f37  lea     rcx, dword_180032660; this
0x180020f3e  call    ?SetCorrelationVector@TelemetryLogger@Windows@Microsoft@@QEAAJPEAVTraceLoggingCorrelationVector@@@Z; Microsoft::Windows::TelemetryLogger::SetCorrelationVector(TraceLoggingCorrelationVector *)
0x180020f43  mov     eax, [rdi+r14]
0x180020f47  cmp     cs:dword_180032DAC, eax
0x180020f4d  jg      loc_180021055
0x180020f53  mov     rdx, rbx; struct TraceLoggingCorrelationVector *
0x180020f56  lea     rcx, dword_180032520; this
0x180020f5d  call    ?SetCorrelationVector@TelemetryLogger@Windows@Microsoft@@QEAAJPEAVTraceLoggingCorrelationVector@@@Z; Microsoft::Windows::TelemetryLogger::SetCorrelationVector(TraceLoggingCorrelationVector *)
0x180020f62  mov     eax, [rdi+r14]
0x180020f66  cmp     cs:dword_180032DB0, eax
0x180020f6c  jg      loc_1800210AB
0x180020f72  mov     rdx, rbx; struct TraceLoggingCorrelationVector *
0x180020f75  lea     rcx, dword_1800325C0; this
0x180020f7c  call    ?SetCorrelationVector@TelemetryLogger@Windows@Microsoft@@QEAAJPEAVTraceLoggingCorrelationVector@@@Z; Microsoft::Windows::TelemetryLogger::SetCorrelationVector(TraceLoggingCorrelationVector *)
0x180020f81  mov     eax, [rdi+r14]
0x180020f85  cmp     cs:dword_180032DA8, eax
0x180020f8b  jg      short loc_180020FB0
0x180020f8d  mov     rdx, rbx; struct TraceLoggingCorrelationVector *
0x180020f90  lea     rcx, dword_180032480; this
0x180020f97  call    ?SetCorrelationVector@TelemetryLogger@Windows@Microsoft@@QEAAJPEAVTraceLoggingCorrelationVector@@@Z; Microsoft::Windows::TelemetryLogger::SetCorrelationVector(TraceLoggingCorrelationVector *)
0x180020f9c  xor     eax, eax
0x180020f9e  mov     rbx, [rsp+28h+arg_0]
0x180020fa3  mov     rdi, [rsp+28h+arg_8]
0x180020fa8  add     rsp, 20h
0x180020fac  pop     r14
0x180020fae  retn
0x180020fb0  lea     rcx, dword_180032DA8
0x180020fb7  call    _Init_thread_header
0x180020fbc  cmp     cs:dword_180032DA8, 0FFFFFFFFh
0x180020fc3  jnz     short loc_180020F8D
0x180020fc5  mov     cs:dword_180032480, 1
0x180020fcf  lea     rax, qword_180032140
0x180020fd6  mov     cs:off_180032488, rax
0x180020fdd  mov     cs:byte_180032490, 0
0x180020fe4  lea     rdx, byte_180032490; char *
0x180020feb  call    ?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForDmSession(ushort const *,char *)
0x180020ff0  nop
0x180020ff1  lea     rcx, dword_180032DA8
0x180020ff8  call    _Init_thread_footer
0x180020ffd  jmp     short loc_180020F8D
0x180020fff  lea     rcx, dword_180032DB4
0x180021006  call    _Init_thread_header
0x18002100b  cmp     cs:dword_180032DB4, 0FFFFFFFFh
0x180021012  jnz     loc_180020F34
0x180021018  mov     cs:dword_180032660, 1
0x180021022  lea     rax, qword_1800321E8
0x180021029  mov     cs:off_180032668, rax
0x180021030  mov     cs:byte_180032670, 0
0x180021037  lea     rdx, byte_180032670; char *
0x18002103e  call    ?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForDmSession(ushort const *,char *)
0x180021043  nop
0x180021044  lea     rcx, dword_180032DB4
0x18002104b  call    _Init_thread_footer
0x180021050  jmp     loc_180020F34
0x180021055  lea     rcx, dword_180032DAC
0x18002105c  call    _Init_thread_header
0x180021061  cmp     cs:dword_180032DAC, 0FFFFFFFFh
0x180021068  jnz     loc_180020F53
0x18002106e  mov     cs:dword_180032520, 1
0x180021078  lea     rax, qword_1800321B0
0x18002107f  mov     cs:off_180032528, rax
0x180021086  mov     cs:byte_180032530, 0
0x18002108d  lea     rdx, byte_180032530; char *
0x180021094  call    ?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForDmSession(ushort const *,char *)
0x180021099  nop
0x18002109a  lea     rcx, dword_180032DAC
0x1800210a1  call    _Init_thread_footer
0x1800210a6  jmp     loc_180020F53
0x1800210ab  lea     rcx, dword_180032DB0
0x1800210b2  call    _Init_thread_header
0x1800210b7  cmp     cs:dword_180032DB0, 0FFFFFFFFh
0x1800210be  jnz     loc_180020F72
0x1800210c4  mov     cs:dword_1800325C0, 1
0x1800210ce  lea     rax, qword_180032178
0x1800210d5  mov     cs:off_1800325C8, rax
0x1800210dc  mov     cs:byte_1800325D0, 0
0x1800210e3  lea     rdx, byte_1800325D0; char *
0x1800210ea  call    ?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForDmSession(ushort const *,char *)
0x1800210ef  nop
0x1800210f0  lea     rcx, dword_180032DB0
0x1800210f7  call    _Init_thread_footer
0x1800210fc  jmp     loc_180020F72
```
