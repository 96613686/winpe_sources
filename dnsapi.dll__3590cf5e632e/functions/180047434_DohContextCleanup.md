# DohContextCleanup

- ea: `0x180047434`
- end: `0x18004755f`
- name: `DohContextCleanup`
- size: `299`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800473cc`

## callees

- `0x18002b050`
- `0x180043180`
- `0x180047434`
- `0x180083954`
- `0x1800ddfa8`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180047527`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180047527`
- `WINHTTP!WinHttpCloseHandle` at `0x1800474ba`
- `WINHTTP!WinHttpCloseHandle` at `0x1800474ba`
- `CRYPT32!CertFreeCertificateContext` at `0x18004753c`
- `CRYPT32!CertFreeCertificateContext` at `0x18004753c`

## pseudocode

```c
char __fastcall DohContextCleanup(char *lpMem)
{
  char result; // al
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  const CERT_CONTEXT *v7; // rcx

  result = BYTE1(xmmword_1801119E0);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    WPP_SF_q(1035, 16, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids, lpMem);
    result = BYTE1(xmmword_1801119E0);
  }
  if ( lpMem )
  {
    if ( *((_DWORD *)lpMem + 12) || *(_QWORD *)lpMem )
      MicrosoftTelemetryAssertTriggeredNoArgs(lpMem);
    DnsApiFree(*((LPVOID *)lpMem + 8));
    v3 = (void *)*((_QWORD *)lpMem + 19);
    *((_QWORD *)lpMem + 8) = 0;
    if ( v3 )
    {
      WinHttpCloseHandle(v3);
      *((_QWORD *)lpMem + 19) = 0;
    }
    DnsApiFree(*((LPVOID *)lpMem + 3));
    v4 = (void *)*((_QWORD *)lpMem + 16);
    *((_QWORD *)lpMem + 3) = 0;
    *((_QWORD *)lpMem + 9) = 0;
    DeRefDnsWinhttpSession(v4);
    v5 = (void *)*((_QWORD *)lpMem + 1);
    *((_QWORD *)lpMem + 16) = 0;
    DnsApiFree(v5);
    v6 = (void *)*((_QWORD *)lpMem + 2);
    *((_QWORD *)lpMem + 1) = 0;
    DnsApiFree(v6);
    *((_QWORD *)lpMem + 2) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(lpMem + 88));
    v7 = (const CERT_CONTEXT *)*((_QWORD *)lpMem + 10);
    if ( v7 )
    {
      CertFreeCertificateContext(v7);
      *((_QWORD *)lpMem + 10) = 0;
    }
    return DnsApiFree(lpMem);
  }
  else if ( (result & 8) != 0 )
  {
    return WPP_SF_(1035, 17, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180047434  push    rbx
0x180047436  sub     rsp, 20h
0x18004743a  mov     rbx, rcx
0x18004743d  mov     al, byte ptr cs:xmmword_1801119E0+1
0x180047443  test    al, 8
0x180047445  jz      short loc_180047466
0x180047447  mov     edx, 10h
0x18004744c  lea     r8, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids
0x180047453  mov     ecx, 40Bh
0x180047458  mov     r9, rbx
0x18004745b  call    WPP_SF_q
0x180047460  mov     al, byte ptr cs:xmmword_1801119E0+1
0x180047466  test    rbx, rbx
0x180047469  jnz     short loc_18004748C
0x18004746b  test    al, 8
0x18004746d  jz      loc_180047558
0x180047473  lea     edx, [rbx+11h]
0x180047476  mov     ecx, 40Bh
0x18004747b  lea     r8, WPP_2c80e66c209e3b063fd9ee6d3755b8b2_Traceguids
0x180047482  add     rsp, 20h
0x180047486  pop     rbx
0x180047487  jmp     WPP_SF_
0x18004748c  cmp     dword ptr [rbx+30h], 0
0x180047490  jnz     short loc_180047498
0x180047492  cmp     qword ptr [rbx], 0
0x180047496  jz      short loc_18004749D
0x180047498  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004749d  mov     rcx, [rbx+40h]; lpMem
0x1800474a1  call    DnsApiFree
0x1800474a6  mov     rcx, [rbx+98h]; hInternet
0x1800474ad  mov     qword ptr [rbx+40h], 0
0x1800474b5  test    rcx, rcx
0x1800474b8  jz      short loc_1800474D1
0x1800474ba  call    cs:__imp_WinHttpCloseHandle
0x1800474c1  nop     dword ptr [rax+rax+00h]
0x1800474c6  mov     qword ptr [rbx+98h], 0
0x1800474d1  mov     rcx, [rbx+18h]; lpMem
0x1800474d5  call    DnsApiFree
0x1800474da  mov     rcx, [rbx+80h]; lpMem
0x1800474e1  mov     qword ptr [rbx+18h], 0
0x1800474e9  mov     qword ptr [rbx+48h], 0
0x1800474f1  call    DeRefDnsWinhttpSession
0x1800474f6  mov     rcx, [rbx+8]; lpMem
0x1800474fa  mov     qword ptr [rbx+80h], 0
0x180047505  call    DnsApiFree
0x18004750a  mov     rcx, [rbx+10h]; lpMem
0x18004750e  mov     qword ptr [rbx+8], 0
0x180047516  call    DnsApiFree
0x18004751b  lea     rcx, [rbx+58h]; lpCriticalSection
0x18004751f  mov     qword ptr [rbx+10h], 0
0x180047527  call    cs:__imp_DeleteCriticalSection
0x18004752e  nop     dword ptr [rax+rax+00h]
0x180047533  mov     rcx, [rbx+50h]; pCertContext
0x180047537  test    rcx, rcx
0x18004753a  jz      short loc_180047550
0x18004753c  call    cs:__imp_CertFreeCertificateContext
0x180047543  nop     dword ptr [rax+rax+00h]
0x180047548  mov     qword ptr [rbx+50h], 0
0x180047550  mov     rcx, rbx; lpMem
0x180047553  call    DnsApiFree
0x180047558  add     rsp, 20h
0x18004755c  pop     rbx
0x18004755d  retn
```
