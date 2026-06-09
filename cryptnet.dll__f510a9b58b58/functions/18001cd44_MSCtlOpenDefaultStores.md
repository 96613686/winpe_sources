# MSCtlOpenDefaultStores

- ea: `0x18001cd44`
- end: `0x18001cdeb`
- name: `MSCtlOpenDefaultStores`
- size: `167`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c790`
- `0x18001cdf4`

## callees

- `0x18001cd44`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x18001cdac`
- `CRYPT32!CertOpenStore` at `0x18001cdac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cd64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cd64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cdd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cdd5`

## pseudocode

```c
void MSCtlOpenDefaultStores()
{
  __int64 v0; // rdi
  unsigned int i; // ebx
  DWORD v2; // r9d

  v0 = 0;
  if ( !dword_180032900 )
  {
    EnterCriticalSection(&MSCtlDefaultStoresCriticalSection);
    if ( !dword_180032900 )
    {
      for ( i = 0; i < 4; ++i )
      {
        v2 = dword_180028358[4 * v0] | 0x8000;
        if ( !i )
          v2 = dword_180028358[4 * v0];
        *((_QWORD *)&xmmword_1800328E0 + v0) = CertOpenStore((LPCSTR)0xA, 0, 0, v2, (&off_180028350)[2 * v0]);
        ++v0;
      }
      dword_180032900 = 1;
    }
    LeaveCriticalSection(&MSCtlDefaultStoresCriticalSection);
  }
}

```

## disassembly

```asm
0x18001cd44  mov     [rsp+arg_0], rbx
0x18001cd49  mov     [rsp+arg_8], rsi
0x18001cd4e  push    rdi
0x18001cd4f  sub     rsp, 30h
0x18001cd53  xor     edi, edi
0x18001cd55  cmp     cs:dword_180032900, edi
0x18001cd5b  jnz     short loc_18001CDDB
0x18001cd5d  lea     rcx, ?MSCtlDefaultStoresCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001cd64  call    cs:__imp_EnterCriticalSection
0x18001cd6a  cmp     cs:dword_180032900, edi
0x18001cd70  jnz     short loc_18001CDCE
0x18001cd72  mov     ebx, edi
0x18001cd74  lea     rsi, __ImageBase
0x18001cd7b  mov     rcx, rdi
0x18001cd7e  add     rcx, rcx
0x18001cd81  mov     eax, ds:rva dword_180028358[rsi+rcx*8]
0x18001cd88  mov     r9d, eax
0x18001cd8b  bts     r9d, 0Fh
0x18001cd90  cmp     ebx, 1
0x18001cd93  cmovb   r9d, eax; dwFlags
0x18001cd97  mov     rax, ds:rva off_180028350[rsi+rcx*8]; "TRUST" ...
0x18001cd9f  xor     edx, edx; dwEncodingType
0x18001cda1  mov     [rsp+38h+pvPara], rax; pvPara
0x18001cda6  xor     r8d, r8d; hCryptProv
0x18001cda9  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18001cdac  call    cs:__imp_CertOpenStore
0x18001cdb2  mov     qword ptr rva xmmword_1800328E0[rsi+rdi*8], rax
0x18001cdba  inc     ebx
0x18001cdbc  inc     rdi
0x18001cdbf  cmp     ebx, 4
0x18001cdc2  jb      short loc_18001CD7B
0x18001cdc4  mov     cs:dword_180032900, 1
0x18001cdce  lea     rcx, ?MSCtlDefaultStoresCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001cdd5  call    cs:__imp_LeaveCriticalSection
0x18001cddb  mov     rbx, [rsp+38h+arg_0]
0x18001cde0  mov     rsi, [rsp+38h+arg_8]
0x18001cde5  add     rsp, 30h
0x18001cde9  pop     rdi
0x18001cdea  retn
```
