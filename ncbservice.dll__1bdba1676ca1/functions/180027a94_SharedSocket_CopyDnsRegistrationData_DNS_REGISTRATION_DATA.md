# SharedSocket::CopyDnsRegistrationData(_DNS_REGISTRATION_DATA *)

- ea: `0x180027a94`
- end: `0x180027ba1`
- name: `?CopyDnsRegistrationData@SharedSocket@@AEAAKPEAU_DNS_REGISTRATION_DATA@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(SharedSocket *this, struct _DNS_REGISTRATION_DATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012490`

## callees

- `0x18000a0a0`
- `0x180014130`
- `0x180027a94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ad8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ad8`
- `DNSAPI!DnsServiceCopyInstance` at `0x180027b1b`
- `DNSAPI!DnsServiceCopyInstance` at `0x180027b1b`

## string_xrefs

- `0x180027b88`: `CopyDnsRegistrationData: UIntMult for allocation for dns registration data failed`
- `0x180027b6d`: `CopyDnsRegistrationData: UIntAdd for allocation for dns registration data failed`
- `0x180027af0`: `CopyDnsRegistrationData: dns registration data failed`
- `0x180027b52`: `CopyDnsRegistrationData: DnsServiceCopyInstance failed`

## pseudocode

```c
__int64 __fastcall SharedSocket::CopyDnsRegistrationData(SharedSocket *this, struct _DNS_REGISTRATION_DATA *a2)
{
  unsigned __int64 v3; // rax
  __int64 v4; // rcx
  unsigned int v6; // eax
  _DWORD *v7; // rax
  DWORD LastError; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  const wchar_t *v11; // r8
  unsigned int v12; // ebp

  v3 = 16LL * *(unsigned int *)a2;
  v4 = 0xFFFFFFFFLL;
  if ( v3 > 0xFFFFFFFF )
  {
    v10 = 534;
    v9 = 534;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      v11 = L"CopyDnsRegistrationData: UIntMult for allocation for dns registration data failed";
      goto LABEL_18;
    }
  }
  else
  {
    v6 = v3 + 24;
    if ( v6 < 0x18 )
    {
      v10 = 534;
      v9 = 534;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        v11 = L"CopyDnsRegistrationData: UIntAdd for allocation for dns registration data failed";
        goto LABEL_18;
      }
    }
    else
    {
      v7 = MALLOC(v6);
      *((_QWORD *)this + 15) = v7;
      if ( v7 )
      {
        v9 = 0;
        v12 = 0;
        *v7 = *(_DWORD *)a2;
        while ( v12 < *(_DWORD *)a2 )
        {
          if ( *((_QWORD *)a2 + 2 * v12 + 1) )
          {
            *(_QWORD *)(*((_QWORD *)this + 15) + 16LL * v12 + 8) = DnsServiceCopyInstance();
            v4 = *((_QWORD *)this + 15);
            if ( !*(_QWORD *)(v4 + 16LL * v12 + 8) )
            {
              v9 = 8;
              if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
                return v9;
              v10 = 8;
              v11 = L"CopyDnsRegistrationData: DnsServiceCopyInstance failed";
              goto LABEL_18;
            }
            *(_BYTE *)(v4 + 16LL * v12 + 16) = *((_BYTE *)a2 + 16 * v12 + 16);
          }
          ++v12;
        }
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        {
          v10 = LastError;
          v11 = L"CopyDnsRegistrationData: dns registration data failed";
LABEL_18:
          McTemplateU0zq_EventWriteTransfer(v4, a2, v11, v10);
        }
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180027a94  push    rbx
0x180027a96  push    rbp
0x180027a97  push    rsi
0x180027a98  push    rdi
0x180027a99  push    r14
0x180027a9b  sub     rsp, 20h
0x180027a9f  mov     eax, [rdx]
0x180027aa1  mov     r14, rcx
0x180027aa4  shl     rax, 4
0x180027aa8  mov     ecx, 0FFFFFFFFh
0x180027aad  mov     rsi, rdx
0x180027ab0  cmp     rax, rcx
0x180027ab3  ja      loc_180027B76
0x180027ab9  add     eax, 18h
0x180027abc  cmp     eax, 18h
0x180027abf  jb      loc_180027B5B
0x180027ac5  mov     ecx, eax; dwBytes
0x180027ac7  call    ?MALLOC@@YAPEAX_K@Z; MALLOC(unsigned __int64)
0x180027acc  mov     [r14+78h], rax
0x180027ad0  mov     rcx, rax
0x180027ad3  test    rax, rax
0x180027ad6  jnz     short loc_180027AFC
0x180027ad8  call    cs:__imp_GetLastError
0x180027ade  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027ae5  mov     ebx, eax
0x180027ae7  jz      loc_180027B94
0x180027aed  mov     r9d, eax
0x180027af0  lea     r8, aCopydnsregistr_2; "CopyDnsRegistrationData: dns registrati"...
0x180027af7  jmp     loc_180027B8F
0x180027afc  mov     eax, [rsi]
0x180027afe  xor     ebx, ebx
0x180027b00  xor     ebp, ebp
0x180027b02  mov     [rcx], eax
0x180027b04  cmp     ebp, [rsi]
0x180027b06  jnb     loc_180027B94
0x180027b0c  mov     edi, ebp
0x180027b0e  add     rdi, rdi
0x180027b11  mov     rcx, [rsi+rdi*8+8]
0x180027b16  test    rcx, rcx
0x180027b19  jz      short loc_180027B3D
0x180027b1b  call    cs:__imp_DnsServiceCopyInstance
0x180027b21  mov     rcx, [r14+78h]
0x180027b25  mov     [rcx+rdi*8+8], rax
0x180027b2a  mov     rcx, [r14+78h]
0x180027b2e  cmp     [rcx+rdi*8+8], rbx
0x180027b33  jz      short loc_180027B41
0x180027b35  mov     al, [rsi+rdi*8+10h]
0x180027b39  mov     [rcx+rdi*8+10h], al
0x180027b3d  inc     ebp
0x180027b3f  jmp     short loc_180027B04
0x180027b41  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027b48  mov     ebx, 8
0x180027b4d  jz      short loc_180027B94
0x180027b4f  mov     r9d, ebx
0x180027b52  lea     r8, aCopydnsregistr_0; "CopyDnsRegistrationData: DnsServiceCopy"...
0x180027b59  jmp     short loc_180027B8F
0x180027b5b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027b62  mov     r9d, 216h
0x180027b68  mov     ebx, r9d
0x180027b6b  jz      short loc_180027B94
0x180027b6d  lea     r8, aCopydnsregistr_1; "CopyDnsRegistrationData: UIntAdd for al"...
0x180027b74  jmp     short loc_180027B8F
0x180027b76  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027b7d  mov     r9d, 216h
0x180027b83  mov     ebx, r9d
0x180027b86  jz      short loc_180027B94
0x180027b88  lea     r8, aCopydnsregistr; "CopyDnsRegistrationData: UIntMult for a"...
0x180027b8f  call    McTemplateU0zq_EventWriteTransfer
0x180027b94  mov     eax, ebx
0x180027b96  add     rsp, 20h
0x180027b9a  pop     r14
0x180027b9c  pop     rdi
0x180027b9d  pop     rsi
0x180027b9e  pop     rbp
0x180027b9f  pop     rbx
0x180027ba0  retn
```
