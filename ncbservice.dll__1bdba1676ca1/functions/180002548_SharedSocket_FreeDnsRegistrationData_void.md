# SharedSocket::FreeDnsRegistrationData(void)

- ea: `0x180002548`
- end: `0x1800025b9`
- name: `?FreeDnsRegistrationData@SharedSocket@@AEAAXXZ`
- size: `113`
- prototype: `void __fastcall(SharedSocket *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800022e4`

## callees

- `0x180002548`
- `0x180003ed0`
- `0x180027d70`

## import_xrefs

- `DNSAPI!DnsServiceFreeInstance` at `0x18000258c`
- `DNSAPI!DnsServiceFreeInstance` at `0x18000258c`

## pseudocode

```c
void __fastcall SharedSocket::FreeDnsRegistrationData(SharedSocket *this)
{
  SharedSocket *v2; // rcx
  unsigned int v3; // ebx
  struct _DNS_SERVICE_INSTANCE *v4; // rdx

  v2 = (SharedSocket *)*((_QWORD *)this + 15);
  if ( v2 )
  {
    if ( *(_DWORD *)v2 )
    {
      v3 = 0;
      do
      {
        v4 = (struct _DNS_SERVICE_INSTANCE *)*((_QWORD *)v2 + 2 * v3 + 1);
        if ( v4 )
        {
          SharedSocket::DnsServiceDeregistration(v2, v4, *((_BYTE *)v2 + 16 * v3 + 16));
          DnsServiceFreeInstance(*(_QWORD *)(*((_QWORD *)this + 15) + 16LL * v3 + 8));
        }
        v2 = (SharedSocket *)*((_QWORD *)this + 15);
        ++v3;
      }
      while ( v3 < *(_DWORD *)v2 );
    }
    VpnFree(v2);
    *((_QWORD *)this + 15) = 0;
  }
}

```

## disassembly

```asm
0x180002548  mov     [rsp+arg_0], rbx
0x18000254d  mov     [rsp+arg_8], rsi
0x180002552  push    rdi
0x180002553  sub     rsp, 20h
0x180002557  mov     rdi, rcx
0x18000255a  mov     rcx, [rcx+78h]; this
0x18000255e  test    rcx, rcx
0x180002561  jz      short loc_1800025A9
0x180002563  cmp     dword ptr [rcx], 0
0x180002566  jbe     short loc_18000259C
0x180002568  xor     ebx, ebx
0x18000256a  mov     esi, ebx
0x18000256c  add     rsi, rsi
0x18000256f  mov     rdx, [rcx+rsi*8+8]; struct _DNS_SERVICE_INSTANCE *
0x180002574  test    rdx, rdx
0x180002577  jz      short loc_180002592
0x180002579  mov     r8b, [rcx+rsi*8+10h]; unsigned __int8
0x18000257e  call    ?DnsServiceDeregistration@SharedSocket@@AEAAKPEAU_DNS_SERVICE_INSTANCE@@E@Z; SharedSocket::DnsServiceDeregistration(_DNS_SERVICE_INSTANCE *,uchar)
0x180002583  mov     rcx, [rdi+78h]
0x180002587  mov     rcx, [rcx+rsi*8+8]
0x18000258c  call    cs:__imp_DnsServiceFreeInstance
0x180002592  mov     rcx, [rdi+78h]; lpMem
0x180002596  inc     ebx
0x180002598  cmp     ebx, [rcx]
0x18000259a  jb      short loc_18000256A
0x18000259c  call    VpnFree
0x1800025a1  mov     qword ptr [rdi+78h], 0
0x1800025a9  mov     rbx, [rsp+28h+arg_0]
0x1800025ae  mov     rsi, [rsp+28h+arg_8]
0x1800025b3  add     rsp, 20h
0x1800025b7  pop     rdi
0x1800025b8  retn
```
