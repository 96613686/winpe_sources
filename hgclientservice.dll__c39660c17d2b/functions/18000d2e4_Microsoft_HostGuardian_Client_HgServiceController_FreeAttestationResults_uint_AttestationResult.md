# Microsoft::HostGuardian::Client::HgServiceController::FreeAttestationResults(uint,AttestationResult *)

- ea: `0x18000d2e4`
- end: `0x18000d342`
- name: `?FreeAttestationResults@HgServiceController@Client@HostGuardian@Microsoft@@QEAAXIPEAUAttestationResult@@@Z`
- size: `94`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::HgServiceController *this, unsigned int, struct AttestationResult *)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c080`
- `0x18000c148`
- `0x18000ca70`
- `0x18000cdbc`

## callees

- `0x18000d2e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d311`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d311`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d333`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgServiceController::FreeAttestationResults(
        Microsoft::HostGuardian::Client::HgServiceController *this,
        unsigned int a2,
        struct AttestationResult *a3)
{
  unsigned __int64 v3; // rdi
  unsigned __int64 i; // rbp
  __int64 v6; // rsi
  void *v7; // rcx

  if ( a3 )
  {
    v3 = 0;
    for ( i = a2; v3 < i; *((_DWORD *)a3 + 2 * v6 + 2) = 0 )
    {
      v6 = 3 * v3;
      if ( !*((_DWORD *)a3 + 6 * v3 + 2) )
        break;
      v7 = (void *)*((_QWORD *)a3 + 3 * v3 + 2);
      if ( !v7 )
        break;
      CoTaskMemFree(v7);
      ++v3;
      *((_QWORD *)a3 + v6 + 2) = 0;
    }
    CoTaskMemFree(a3);
  }
}

```

## disassembly

```asm
0x18000d2e4  test    r8, r8
0x18000d2e7  jz      short locret_18000D341
0x18000d2e9  push    rbx
0x18000d2ea  push    rbp
0x18000d2eb  push    rsi
0x18000d2ec  push    rdi
0x18000d2ed  sub     rsp, 28h
0x18000d2f1  xor     edi, edi
0x18000d2f3  mov     ebp, edx
0x18000d2f5  mov     rbx, r8
0x18000d2f8  test    edx, edx
0x18000d2fa  jz      short loc_18000D330
0x18000d2fc  lea     rsi, [rdi+rdi*2]
0x18000d300  cmp     dword ptr [rbx+rsi*8+8], 0
0x18000d305  jbe     short loc_18000D330
0x18000d307  mov     rcx, [rbx+rsi*8+10h]; pv
0x18000d30c  test    rcx, rcx
0x18000d30f  jz      short loc_18000D330
0x18000d311  call    cs:__imp_CoTaskMemFree
0x18000d317  inc     rdi
0x18000d31a  mov     qword ptr [rbx+rsi*8+10h], 0
0x18000d323  mov     dword ptr [rbx+rsi*8+8], 0
0x18000d32b  cmp     rdi, rbp
0x18000d32e  jb      short loc_18000D2FC
0x18000d330  mov     rcx, rbx; pv
0x18000d333  call    cs:__imp_CoTaskMemFree
0x18000d339  add     rsp, 28h
0x18000d33d  pop     rdi
0x18000d33e  pop     rsi
0x18000d33f  pop     rbp
0x18000d340  pop     rbx
0x18000d341  retn
```
