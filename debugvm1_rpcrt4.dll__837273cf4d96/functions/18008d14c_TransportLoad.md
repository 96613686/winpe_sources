# TransportLoad

- ea: `0x18008d14c`
- end: `0x18008d2b6`
- name: `TransportLoad`
- size: `362`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008d064`

## callees

- `0x180021e70`
- `0x18008d14c`
- `0x18008d2bc`
- `0x18008d424`
- `0x18008d4e0`
- `0x1800a73a8`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18008d296`
- `ntdll!RtlDeleteCriticalSection` at `0x18008d296`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18008d1e4`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18008d1fb`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18008d1e4`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18008d1fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008d1c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008d1c2`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x18008d29e`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x18008d29e`

## pseudocode

```c
__int64 __fastcall TransportLoad(wchar_t *String1, const struct RPC_CONNECTION_TRANSPORT **a2)
{
  bool v2; // zf
  struct TransportProtocol *v5; // rax
  struct TransportProtocol *v6; // rbx
  TransportProtocol *v7; // rdi
  __int64 v8; // rsi
  int v9; // eax
  const struct RPC_CONNECTION_TRANSPORT *v11; // rax

  v2 = dword_1800FA4D0 == 0;
  *a2 = 0;
  if ( !v2 )
    goto LABEL_11;
  v5 = (struct TransportProtocol *)AllocWrapper(0x480u);
  v6 = v5;
  if ( v5 )
  {
    v7 = v5;
    v8 = 16;
    do
    {
      TransportProtocol::TransportProtocol(v7);
      v7 = (TransportProtocol *)((char *)v7 + 72);
      --v8;
    }
    while ( v8 );
    TransportProtocolArray = v6;
    gdwComputerNameLength = 16;
    if ( GetComputerNameExW(ComputerNameNetBIOS, &gpstrComputerName, &gdwComputerNameLength) )
    {
      ++gdwComputerNameLength;
      if ( RtlInitializeCriticalSectionAndSpinCount(&AddressListLock, 0x80000000) >= 0 )
      {
        if ( RtlInitializeCriticalSectionAndSpinCount(&PNPNotificationsLock, 0x80000000) >= 0 )
        {
          if ( (_DWORD)gBCacheMode == 1 )
            gPostSize = 16;
          dword_1800FA4D0 = 1;
LABEL_11:
          v9 = MapProtseq(String1);
          if ( v9 )
          {
            if ( v9 != 1 )
            {
              if ( v9 == 3 )
              {
                if ( (unsigned __int8)IsGetLocalVmAliasNamePresent() && (unsigned int)RemoteWinRTActivation() == 1 )
                  off_1800F9468 = 0;
                v11 = (const struct RPC_CONNECTION_TRANSPORT *)&NMP_TransportInterface;
                goto LABEL_18;
              }
              if ( v9 != 6 && v9 != 15 )
                return 1703;
            }
            v11 = WS_TransportLoad(v9);
            if ( v11 )
            {
LABEL_18:
              *a2 = v11;
              return 0;
            }
          }
          return 1703;
        }
        RtlDeleteCriticalSection(&AddressListLock);
      }
    }
  }
  else
  {
    TransportProtocolArray = 0;
  }
  return 14;
}

```

## disassembly

```asm
0x18008d14c  push    rbx
0x18008d14e  push    rbp
0x18008d14f  push    rsi
0x18008d150  push    rdi
0x18008d151  push    r14
0x18008d153  sub     rsp, 20h
0x18008d157  cmp     cs:dword_1800FA4D0, 0
0x18008d15e  mov     r14, rdx
0x18008d161  mov     rbp, rcx
0x18008d164  mov     qword ptr [rdx], 0
0x18008d16b  jnz     loc_18008D226
0x18008d171  mov     ecx, 480h; dwBytes
0x18008d176  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18008d17b  mov     rbx, rax
0x18008d17e  test    rax, rax
0x18008d181  jz      loc_18008D26B
0x18008d187  mov     rdi, rax
0x18008d18a  mov     esi, 10h
0x18008d18f  mov     rcx, rdi; this
0x18008d192  call    ??0TransportProtocol@@QEAA@XZ; TransportProtocol::TransportProtocol(void)
0x18008d197  add     rdi, 48h ; 'H'
0x18008d19b  sub     rsi, 1
0x18008d19f  jnz     short loc_18008D18F
0x18008d1a1  lea     r8, ?gdwComputerNameLength@@3KA; nSize
0x18008d1a8  mov     cs:?TransportProtocolArray@@3PEAVTransportProtocol@@EA, rbx; TransportProtocol * TransportProtocolArray
0x18008d1af  lea     rdx, ?gpstrComputerName@@3PAGA; lpBuffer
0x18008d1b6  mov     cs:?gdwComputerNameLength@@3KA, 10h; ulong gdwComputerNameLength
0x18008d1c0  xor     ecx, ecx; NameType
0x18008d1c2  call    cs:__imp_GetComputerNameExW
0x18008d1c8  test    eax, eax
0x18008d1ca  jz      loc_18008D276
0x18008d1d0  inc     cs:?gdwComputerNameLength@@3KA; ulong gdwComputerNameLength
0x18008d1d6  lea     rcx, ?AddressListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18008d1dd  mov     ebx, 80000000h
0x18008d1e2  mov     edx, ebx; SpinCount
0x18008d1e4  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x18008d1ea  test    eax, eax
0x18008d1ec  js      loc_18008D276
0x18008d1f2  mov     edx, ebx; SpinCount
0x18008d1f4  lea     rcx, PNPNotificationsLock; CriticalSection
0x18008d1fb  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x18008d201  test    eax, eax
0x18008d203  js      loc_18008D28F
0x18008d209  cmp     cs:?gBCacheMode@@3W4BCacheMode@@A, 1; BCacheMode gBCacheMode
0x18008d210  jnz     short loc_18008D21C
0x18008d212  mov     cs:?gPostSize@@3IA, 10h; uint gPostSize
0x18008d21c  mov     cs:dword_1800FA4D0, 1
0x18008d226  mov     rcx, rbp; String1
0x18008d229  call    ?MapProtseq@@YAHPEBG@Z; MapProtseq(ushort const *)
0x18008d22e  test    eax, eax
0x18008d230  jz      short loc_18008D248
0x18008d232  mov     edx, eax
0x18008d234  sub     edx, 1
0x18008d237  jz      short loc_18008D24F
0x18008d239  sub     edx, 2
0x18008d23c  jz      short loc_18008D27D
0x18008d23e  sub     edx, 3
0x18008d241  jz      short loc_18008D24F
0x18008d243  cmp     edx, 9
0x18008d246  jz      short loc_18008D24F
0x18008d248  mov     eax, 6A7h
0x18008d24d  jmp     short loc_18008D260
0x18008d24f  mov     ecx, eax; int
0x18008d251  call    ?WS_TransportLoad@@YAPEBURPC_CONNECTION_TRANSPORT@@H@Z; WS_TransportLoad(int)
0x18008d256  test    rax, rax
0x18008d259  jz      short loc_18008D248
0x18008d25b  mov     [r14], rax
0x18008d25e  xor     eax, eax
0x18008d260  add     rsp, 20h
0x18008d264  pop     r14
0x18008d266  pop     rdi
0x18008d267  pop     rsi
0x18008d268  pop     rbp
0x18008d269  pop     rbx
0x18008d26a  retn
0x18008d26b  mov     cs:?TransportProtocolArray@@3PEAVTransportProtocol@@EA, 0; TransportProtocol * TransportProtocolArray
0x18008d276  mov     eax, 0Eh
0x18008d27b  jmp     short loc_18008D260
0x18008d27d  call    IsGetLocalVmAliasNamePresent
0x18008d282  test    al, al
0x18008d284  jnz     short loc_18008D29E
0x18008d286  lea     rax, ?NMP_TransportInterface@@3URPC_CONNECTION_TRANSPORT@@A; RPC_CONNECTION_TRANSPORT NMP_TransportInterface
0x18008d28d  jmp     short loc_18008D25B
0x18008d28f  lea     rcx, ?AddressListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18008d296  call    cs:__imp_RtlDeleteCriticalSection
0x18008d29c  jmp     short loc_18008D276
0x18008d29e  call    cs:__imp_RemoteWinRTActivation
0x18008d2a4  cmp     eax, 1
0x18008d2a7  jnz     short loc_18008D286
0x18008d2a9  mov     cs:off_1800F9468, 0
0x18008d2b4  jmp     short loc_18008D286
```
