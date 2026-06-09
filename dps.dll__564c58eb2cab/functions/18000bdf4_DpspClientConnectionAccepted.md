# DpspClientConnectionAccepted

- ea: `0x18000bdf4`
- end: `0x18000bf50`
- name: `DpspClientConnectionAccepted`
- size: `348`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000fbb4`

## callees

- `0x1800013a0`
- `0x180008dc0`
- `0x180009090`
- `0x18000a856`
- `0x18000bdf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bf18`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bf18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bf3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bf3a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000bf0b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000bf0b`
- `RPCRT4!UuidCreate` at `0x18000be86`
- `RPCRT4!UuidCreate` at `0x18000be86`

## pseudocode

```c
__int64 __fastcall DpspClientConnectionAccepted(__int64 a1, __int64 *a2)
{
  unsigned int v4; // esi
  void *v5; // rax
  __int64 v6; // rdi

  if ( a1 )
  {
    v5 = (void *)WdipAlloc(1264);
    v6 = (__int64)v5;
    if ( v5 )
    {
      v4 = 0;
      memset_0(v5, 0, 0x4F0u);
      *(_QWORD *)(v6 + 1224) = v6 + 1248;
      UuidCreate((UUID *)(a1 + 64));
      WdipCopyGuid(v6 + 24, a1 + 64);
      *(_DWORD *)(v6 + 128) = *(_DWORD *)(a1 + 40);
      *(_QWORD *)(v6 + 784) = 0;
      *(_QWORD *)(v6 + 768) = 0;
      *(_QWORD *)(v6 + 776) = 0;
      *(_DWORD *)(v6 + 208) = 0;
      *(_QWORD *)(v6 + 212) = 1000;
      *(_DWORD *)(v6 + 220) = 250;
      *(_DWORD *)(v6 + 84) = 0;
      *(_DWORD *)(v6 + 200) = 0;
      *(_DWORD *)(v6 + 196) = *(_DWORD *)(a1 + 128);
      *(_DWORD *)(v6 + 204) = 1;
      *(_DWORD *)(v6 + 72) = 1;
      *(_QWORD *)(v6 + 96) = _InterlockedExchangeAdd64(&g_ulConnectionId, 4u) + 4;
      InitializeSRWLock((PSRWLOCK)(v6 + 16));
      AcquireSRWLockExclusive(&g_SRWInstanceList);
      *(_QWORD *)(v6 + 1232) = g_pInstanceHead;
      g_pInstanceHead = v6;
      ReleaseSRWLockExclusive(&g_SRWInstanceList);
      *a2 = v6;
    }
    else
    {
      v4 = -2147024882;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
        (int)L"DpspClientConnectionAccepted",
        4199,
        (int)L"Error = %d",
        14);
    }
  }
  else
  {
    v4 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspClientConnectionAccepted",
      4193,
      (int)L"Error = %d",
      87);
  }
  return v4;
}

```

## disassembly

```asm
0x18000bdf4  push    rbx
0x18000bdf6  push    rbp
0x18000bdf7  push    rsi
0x18000bdf8  push    rdi
0x18000bdf9  push    r14
0x18000bdfb  sub     rsp, 30h
0x18000bdff  mov     r14, rdx
0x18000be02  mov     rbp, rcx
0x18000be05  test    rcx, rcx
0x18000be08  jnz     short loc_18000BE3C
0x18000be0a  mov     esi, 80070057h
0x18000be0f  mov     dword ptr [rsp+58h+Args], 57h ; 'W'; Args
0x18000be17  mov     r8d, 1061h; int
0x18000be1d  lea     r9, aErrorD; "Error = %d"
0x18000be24  lea     rdx, aDpspclientconn; "DpspClientConnectionAccepted"
0x18000be2b  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000be32  call    WdipTraceError
0x18000be37  jmp     loc_18000BF43
0x18000be3c  mov     ebx, 4F0h
0x18000be41  mov     ecx, ebx
0x18000be43  call    WdipAlloc
0x18000be48  mov     rdi, rax
0x18000be4b  test    rax, rax
0x18000be4e  jnz     short loc_18000BE65
0x18000be50  mov     esi, 8007000Eh
0x18000be55  mov     dword ptr [rsp+58h+Args], 0Eh
0x18000be5d  mov     r8d, 1067h
0x18000be63  jmp     short loc_18000BE1D
0x18000be65  mov     r8, rbx; Size
0x18000be68  xor     edx, edx; Val
0x18000be6a  mov     rcx, rdi; void *
0x18000be6d  xor     esi, esi
0x18000be6f  call    memset_0
0x18000be74  lea     rax, [rdi+4E0h]
0x18000be7b  lea     rcx, [rbp+40h]; Uuid
0x18000be7f  mov     [rdi+4C8h], rax
0x18000be86  call    cs:__imp_UuidCreate
0x18000be8c  lea     rcx, [rdi+18h]
0x18000be90  lea     rdx, [rbp+40h]
0x18000be94  call    WdipCopyGuid
0x18000be99  mov     eax, [rbp+28h]
0x18000be9c  lea     ecx, [rsi+4]
0x18000be9f  mov     [rdi+80h], eax
0x18000bea5  mov     [rdi+310h], rsi
0x18000beac  mov     [rdi+300h], rsi
0x18000beb3  mov     [rdi+308h], rsi
0x18000beba  mov     [rdi+0D0h], esi
0x18000bec0  mov     qword ptr [rdi+0D4h], 3E8h
0x18000becb  mov     dword ptr [rdi+0DCh], 0FAh
0x18000bed5  mov     [rdi+54h], esi
0x18000bed8  mov     [rdi+0C8h], esi
0x18000bede  mov     eax, [rbp+80h]
0x18000bee4  mov     [rdi+0C4h], eax
0x18000beea  lea     eax, [rsi+1]
0x18000beed  mov     [rdi+0CCh], eax
0x18000bef3  mov     [rdi+48h], eax
0x18000bef6  lock xadd cs:g_ulConnectionId, rcx
0x18000beff  add     rcx, 4
0x18000bf03  mov     [rdi+60h], rcx
0x18000bf07  lea     rcx, [rdi+10h]; SRWLock
0x18000bf0b  call    cs:__imp_InitializeSRWLock
0x18000bf11  lea     rcx, g_SRWInstanceList; SRWLock
0x18000bf18  call    cs:__imp_AcquireSRWLockExclusive
0x18000bf1e  mov     rdx, cs:g_pInstanceHead
0x18000bf25  lea     rcx, g_SRWInstanceList; SRWLock
0x18000bf2c  mov     [rdi+4D0h], rdx
0x18000bf33  mov     cs:g_pInstanceHead, rdi
0x18000bf3a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bf40  mov     [r14], rdi
0x18000bf43  mov     eax, esi
0x18000bf45  add     rsp, 30h
0x18000bf49  pop     r14
0x18000bf4b  pop     rdi
0x18000bf4c  pop     rsi
0x18000bf4d  pop     rbp
0x18000bf4e  pop     rbx
0x18000bf4f  retn
```
