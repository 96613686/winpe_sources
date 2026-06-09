# DotConnectionCleanup

- ea: `0x180083768`
- end: `0x1800838f2`
- name: `DotConnectionCleanup`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180046a44`

## callees

- `0x18002b050`
- `0x180043180`
- `0x1800533bc`
- `0x180083768`
- `0x180083954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180083896`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180083896`
- `WINHTTP!WinHttpCloseHandle` at `0x180083803`
- `WINHTTP!WinHttpCloseHandle` at `0x180083803`
- `CRYPT32!CertFreeCertificateChain` at `0x1800838cd`
- `CRYPT32!CertFreeCertificateChain` at `0x1800838cd`
- `CRYPT32!CertFreeCertificateContext` at `0x1800838ae`
- `CRYPT32!CertFreeCertificateContext` at `0x1800838ae`

## pseudocode

```c
__int64 __fastcall DotConnectionCleanup(void **a1)
{
  char *v1; // rbx
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rcx
  const CERT_CONTEXT *v8; // rcx
  const CERT_CHAIN_CONTEXT *v9; // rcx

  v1 = (char *)*a1;
  *a1 = 0;
  if ( *((_DWORD *)v1 + 21)
    || *(char **)v1 != v1
    || *((char **)v1 + 2) != v1 + 16
    || *((char **)v1 + 6) != v1 + 48
    || *((char **)v1 + 4) != v1 + 32
    || *((_DWORD *)v1 + 22)
    || *((_DWORD *)v1 + 24) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  }
  DnsApiFree(*((LPVOID *)v1 + 17));
  v2 = (void *)*((_QWORD *)v1 + 16);
  *((_QWORD *)v1 + 17) = 0;
  DnsApiFree(v2);
  v3 = (void *)*((_QWORD *)v1 + 19);
  *((_QWORD *)v1 + 16) = 0;
  DnsApiFree(v3);
  v4 = (void *)*((_QWORD *)v1 + 18);
  *((_QWORD *)v1 + 19) = 0;
  DnsApiFree(v4);
  v5 = (void *)*((_QWORD *)v1 + 15);
  *((_QWORD *)v1 + 18) = 0;
  if ( v5 )
  {
    WinHttpCloseHandle(v5);
    *((_QWORD *)v1 + 15) = 0;
  }
  if ( *((_DWORD *)v1 + 54) || *((_QWORD *)v1 + 28) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5);
  if ( *((_DWORD *)v1 + 58) || *((_QWORD *)v1 + 30) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5);
  if ( *((_QWORD *)v1 + 23) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5);
  DeRefDnsWinhttpSession(*((LPVOID *)v1 + 20));
  v6 = (void *)*((_QWORD *)v1 + 21);
  *((_QWORD *)v1 + 20) = 0;
  DnsApiFree(v6);
  v7 = *((_QWORD *)v1 + 22);
  *((_QWORD *)v1 + 21) = 0;
  *(_QWORD *)(v1 + 108) = 0;
  if ( v7 )
  {
    ThreadPool_CloseWork(v7);
    *((_QWORD *)v1 + 22) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 248));
  v8 = (const CERT_CONTEXT *)*((_QWORD *)v1 + 24);
  if ( v8 )
  {
    CertFreeCertificateContext(v8);
    *((_QWORD *)v1 + 24) = 0;
  }
  v9 = (const CERT_CHAIN_CONTEXT *)*((_QWORD *)v1 + 40);
  if ( v9 )
  {
    CertFreeCertificateChain(v9);
    *((_QWORD *)v1 + 40) = 0;
  }
  return DnsApiFree(v1);
}

```

## disassembly

```asm
0x180083768  mov     [rsp+arg_0], rbx
0x18008376d  push    rdi
0x18008376e  sub     rsp, 20h
0x180083772  mov     rbx, [rcx]
0x180083775  xor     edi, edi
0x180083777  mov     [rcx], rdi
0x18008377a  cmp     [rbx+54h], edi
0x18008377d  jnz     short loc_1800837A9
0x18008377f  cmp     [rbx], rbx
0x180083782  jnz     short loc_1800837A9
0x180083784  lea     rax, [rbx+10h]
0x180083788  cmp     [rax], rax
0x18008378b  jnz     short loc_1800837A9
0x18008378d  lea     rax, [rbx+30h]
0x180083791  cmp     [rax], rax
0x180083794  jnz     short loc_1800837A9
0x180083796  lea     rax, [rbx+20h]
0x18008379a  cmp     [rax], rax
0x18008379d  jnz     short loc_1800837A9
0x18008379f  cmp     [rbx+58h], edi
0x1800837a2  jnz     short loc_1800837A9
0x1800837a4  cmp     [rbx+60h], edi
0x1800837a7  jz      short loc_1800837AE
0x1800837a9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800837ae  mov     rcx, [rbx+88h]; lpMem
0x1800837b5  call    DnsApiFree
0x1800837ba  mov     rcx, [rbx+80h]; lpMem
0x1800837c1  mov     [rbx+88h], rdi
0x1800837c8  call    DnsApiFree
0x1800837cd  mov     rcx, [rbx+98h]; lpMem
0x1800837d4  mov     [rbx+80h], rdi
0x1800837db  call    DnsApiFree
0x1800837e0  mov     rcx, [rbx+90h]; lpMem
0x1800837e7  mov     [rbx+98h], rdi
0x1800837ee  call    DnsApiFree
0x1800837f3  mov     rcx, [rbx+78h]; hInternet
0x1800837f7  mov     [rbx+90h], rdi
0x1800837fe  test    rcx, rcx
0x180083801  jz      short loc_180083813
0x180083803  call    cs:__imp_WinHttpCloseHandle
0x18008380a  nop     dword ptr [rax+rax+00h]
0x18008380f  mov     [rbx+78h], rdi
0x180083813  cmp     [rbx+0D8h], edi
0x180083819  jnz     short loc_180083824
0x18008381b  cmp     [rbx+0E0h], rdi
0x180083822  jz      short loc_180083829
0x180083824  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180083829  cmp     [rbx+0E8h], edi
0x18008382f  jnz     short loc_18008383A
0x180083831  cmp     [rbx+0F0h], rdi
0x180083838  jz      short loc_18008383F
0x18008383a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008383f  cmp     [rbx+0B8h], rdi
0x180083846  jz      short loc_18008384D
0x180083848  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008384d  mov     rcx, [rbx+0A0h]; lpMem
0x180083854  call    DeRefDnsWinhttpSession
0x180083859  mov     rcx, [rbx+0A8h]; lpMem
0x180083860  mov     [rbx+0A0h], rdi
0x180083867  call    DnsApiFree
0x18008386c  mov     rcx, [rbx+0B0h]
0x180083873  mov     [rbx+0A8h], rdi
0x18008387a  mov     [rbx+6Ch], rdi
0x18008387e  test    rcx, rcx
0x180083881  jz      short loc_18008388F
0x180083883  call    ThreadPool_CloseWork
0x180083888  mov     [rbx+0B0h], rdi
0x18008388f  lea     rcx, [rbx+0F8h]; lpCriticalSection
0x180083896  call    cs:__imp_DeleteCriticalSection
0x18008389d  nop     dword ptr [rax+rax+00h]
0x1800838a2  mov     rcx, [rbx+0C0h]; pCertContext
0x1800838a9  test    rcx, rcx
0x1800838ac  jz      short loc_1800838C1
0x1800838ae  call    cs:__imp_CertFreeCertificateContext
0x1800838b5  nop     dword ptr [rax+rax+00h]
0x1800838ba  mov     [rbx+0C0h], rdi
0x1800838c1  mov     rcx, [rbx+140h]; pChainContext
0x1800838c8  test    rcx, rcx
0x1800838cb  jz      short loc_1800838E0
0x1800838cd  call    cs:__imp_CertFreeCertificateChain
0x1800838d4  nop     dword ptr [rax+rax+00h]
0x1800838d9  mov     [rbx+140h], rdi
0x1800838e0  mov     rcx, rbx; lpMem
0x1800838e3  mov     rbx, [rsp+28h+arg_0]
0x1800838e8  add     rsp, 20h
0x1800838ec  pop     rdi
0x1800838ed  jmp     DnsApiFree
```
