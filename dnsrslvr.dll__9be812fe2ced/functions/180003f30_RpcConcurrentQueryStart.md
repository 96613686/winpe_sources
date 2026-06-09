# RpcConcurrentQueryStart

- ea: `0x180003f30`
- end: `0x18000408b`
- name: `RpcConcurrentQueryStart`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180038980`

## callees

- `0x180003f30`
- `0x1800040a0`
- `0x180040cd4`
- `0x180086f24`

## import_xrefs

- `DNSAPI!DnsGlobals` at `0x180003f3a`
- `DNSAPI!DnsGlobals` at `0x180003fb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004042`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004014`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004042`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003f5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003f5e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180003ffd`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180003ffd`

## pseudocode

```c
void __fastcall RpcConcurrentQueryStart(__int64 a1)
{
  unsigned int v2; // edi
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // eax
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  unsigned int v10; // ecx

  v2 = DnsGlobals[91];
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_q(1035, 12, WPP_78ecab3900143121f591626d703c42fb_Traceguids, a1);
  EnterCriticalSection(&CriticalSection);
  v7 = *(_DWORD *)(a1 + 3432);
  if ( v7 != 1 )
  {
    if ( v7 != 4 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v4, v3, v5, v6);
    goto LABEL_11;
  }
  if ( (__int64 *)qword_1800ABD28 != &qword_1800ABD28 || v2 && HIDWORD(qword_1800ABD18) >= v2 )
  {
    *(_DWORD *)(a1 + 3432) = 2;
    v8 = (_QWORD *)qword_1800ABD30;
    if ( *(__int64 **)qword_1800ABD30 != &qword_1800ABD28 )
      __fastfail(3u);
    v9 = (_QWORD *)(a1 + 152);
    *v9 = &qword_1800ABD28;
    v9[1] = v8;
    *v8 = v9;
    ++dword_1800ABD20;
    qword_1800ABD30 = (__int64)v9;
    v10 = DnsGlobals[91];
    if ( (!v10 || HIDWORD(qword_1800ABD18) < v10)
      && (unsigned int)qword_1800ABD18 < 0x80
      && (__int64 *)qword_1800ABD28 != &qword_1800ABD28 )
    {
      LODWORD(qword_1800ABD18) = qword_1800ABD18 + 1;
      SubmitThreadpoolWork(pwk);
    }
LABEL_11:
    LeaveCriticalSection(&CriticalSection);
    return;
  }
  *(_DWORD *)(a1 + 3432) = 3;
  ++HIDWORD(qword_1800ABD18);
  LeaveCriticalSection(&CriticalSection);
  ResolverQuery(a1);
}

```

## disassembly

```asm
0x180003f30  mov     [rsp+arg_0], rbx
0x180003f35  push    rdi
0x180003f36  sub     rsp, 20h
0x180003f3a  mov     rax, cs:__imp_DnsGlobals
0x180003f41  mov     rbx, rcx
0x180003f44  mov     edi, [rax+16Ch]
0x180003f4a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180003f51  jnz     loc_180004066
0x180003f57  lea     rcx, CriticalSection; lpCriticalSection
0x180003f5e  call    cs:__imp_EnterCriticalSection
0x180003f64  mov     eax, [rbx+0D68h]
0x180003f6a  cmp     eax, 1
0x180003f6d  jnz     loc_18000405A
0x180003f73  lea     rdx, qword_1800ABD28
0x180003f7a  cmp     cs:qword_1800ABD28, rdx
0x180003f81  jz      loc_18000401B
0x180003f87  mov     dword ptr [rbx+0D68h], 2
0x180003f91  mov     rax, cs:qword_1800ABD30
0x180003f98  cmp     [rax], rdx
0x180003f9b  jnz     loc_180004084
0x180003fa1  add     rbx, 98h
0x180003fa8  mov     [rbx], rdx
0x180003fab  mov     [rbx+8], rax
0x180003faf  mov     [rax], rbx
0x180003fb2  inc     cs:dword_1800ABD20
0x180003fb8  mov     rax, cs:__imp_DnsGlobals
0x180003fbf  mov     cs:qword_1800ABD30, rbx
0x180003fc6  mov     ecx, [rax+16Ch]
0x180003fcc  test    ecx, ecx
0x180003fce  jz      short loc_180003FD8
0x180003fd0  cmp     dword ptr cs:qword_1800ABD18+4, ecx
0x180003fd6  jnb     short loc_180004003
0x180003fd8  mov     eax, dword ptr cs:qword_1800ABD18
0x180003fde  cmp     eax, 80h
0x180003fe3  jnb     short loc_180004003
0x180003fe5  cmp     cs:qword_1800ABD28, rdx
0x180003fec  jz      short loc_180004003
0x180003fee  mov     rcx, cs:pwk; pwk
0x180003ff5  inc     eax
0x180003ff7  mov     dword ptr cs:qword_1800ABD18, eax
0x180003ffd  call    cs:__imp_SubmitThreadpoolWork
0x180004003  lea     rcx, CriticalSection
0x18000400a  mov     rbx, [rsp+28h+arg_0]
0x18000400f  add     rsp, 20h
0x180004013  pop     rdi
0x180004014  jmp     cs:__imp_LeaveCriticalSection
0x18000401b  test    edi, edi
0x18000401d  jz      short loc_18000402B
0x18000401f  cmp     dword ptr cs:qword_1800ABD18+4, edi
0x180004025  jnb     loc_180003F87
0x18000402b  mov     dword ptr [rbx+0D68h], 3
0x180004035  lea     rcx, CriticalSection; lpCriticalSection
0x18000403c  inc     dword ptr cs:qword_1800ABD18+4
0x180004042  call    cs:__imp_LeaveCriticalSection
0x180004048  mov     rcx, rbx
0x18000404b  mov     rbx, [rsp+28h+arg_0]
0x180004050  add     rsp, 20h
0x180004054  pop     rdi
0x180004055  jmp     ResolverQuery
0x18000405a  cmp     eax, 4
0x18000405d  jz      short loc_180004003
0x18000405f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180004064  jmp     short loc_180004003
0x180004066  mov     edx, 0Ch
0x18000406b  lea     r8, WPP_78ecab3900143121f591626d703c42fb_Traceguids
0x180004072  mov     ecx, 40Bh
0x180004077  mov     r9, rbx
0x18000407a  call    WPP_SF_q
0x18000407f  jmp     loc_180003F57
0x180004084  mov     ecx, 3
0x180004089  int     29h; Win8: RtlFailFast(ecx)
```
