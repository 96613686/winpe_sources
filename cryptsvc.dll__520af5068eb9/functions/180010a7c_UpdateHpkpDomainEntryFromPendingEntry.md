# _UpdateHpkpDomainEntryFromPendingEntry

- ea: `0x180010a7c`
- end: `0x180010b9c`
- name: `_UpdateHpkpDomainEntryFromPendingEntry`
- size: `288`
- prototype: `__int64 __fastcall(__int64, __int64, FILETIME)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001868`

## callees

- `0x180010a7c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010ae2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010b12`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010ae2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010b12`

## pseudocode

```c
__int64 __fastcall UpdateHpkpDomainEntryFromPendingEntry(__int64 a1, __int64 a2, FILETIME a3)
{
  __int64 v3; // r14
  __int64 i; // rsi
  __int64 v7; // rdi
  __int64 v8; // rax
  __int64 v10; // rdx
  FILETIME FileTime2; // [rsp+50h] [rbp+18h] BYREF

  FileTime2 = a3;
  v3 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 3 )
    {
      v10 = 6 * v3;
      *(_OWORD *)(a1 + 8 * v10 + 16) = 0;
      *(_OWORD *)(a1 + 8 * v10 + 32) = 0;
      *(_OWORD *)(a1 + 8 * v10 + 48) = 0;
      *(_QWORD *)(a1 + 8 * v10 + 16) = *(_QWORD *)(a2 + 8);
      *(_QWORD *)(a1 + 8 * v10 + 24) = *(_QWORD *)(a2 + 16);
      *(_DWORD *)(a1 + 8 * v10 + 32) = *(_DWORD *)(a2 + 24);
      *(_DWORD *)(a1 + 8 * v10 + 36) = *(_DWORD *)(*(_QWORD *)(a2 + 40) + 8LL);
      *(_DWORD *)(a1 + 8 * v10 + 40) = *(_DWORD *)(*(_QWORD *)(a2 + 40) + 12LL);
      *(_OWORD *)(a1 + 8 * v10 + 48) = *(_OWORD *)(a2 + 48);
      return 1;
    }
    v7 = 48 * i;
    v8 = *(_QWORD *)(48 * i + a1 + 48) - *(_QWORD *)(a2 + 48);
    if ( !v8 )
      v8 = *(_QWORD *)(v7 + a1 + 56) - *(_QWORD *)(a2 + 56);
    if ( !v8 )
      break;
    if ( (_DWORD)i )
    {
      if ( CompareFileTime((const FILETIME *)(v7 + a1 + 24), (const FILETIME *)(a1 + 48 * v3 + 24)) < 0 )
        v3 = (unsigned int)i;
    }
  }
  FileTime2 = (FILETIME)(*(_QWORD *)(v7 + a1 + 24) + 10000000LL * (unsigned int)dword_18002033C);
  if ( CompareFileTime((const FILETIME *)(a2 + 16), &FileTime2) <= 0 )
    return 0;
  *(_QWORD *)(v7 + a1 + 24) = *(_QWORD *)(a2 + 16);
  *(_DWORD *)(v7 + a1 + 32) += *(_DWORD *)(a2 + 24);
  return 1;
}

```

## disassembly

```asm
0x180010a7c  mov     [rsp+arg_0], rbx
0x180010a81  mov     [rsp+arg_8], rbp
0x180010a86  mov     qword ptr [rsp+FileTime2.dwLowDateTime], r8
0x180010a8b  push    rsi
0x180010a8c  push    rdi
0x180010a8d  push    r14
0x180010a8f  sub     rsp, 20h
0x180010a93  xor     r14d, r14d
0x180010a96  mov     rbp, rdx
0x180010a99  xor     esi, esi
0x180010a9b  mov     rbx, rcx
0x180010a9e  cmp     esi, 3
0x180010aa1  jnb     loc_180010B32
0x180010aa7  lea     rdi, [rsi+rsi*2]
0x180010aab  shl     rdi, 4
0x180010aaf  mov     rax, [rdi+rbx+30h]
0x180010ab4  sub     rax, [rbp+30h]
0x180010ab8  jnz     short loc_180010AC3
0x180010aba  mov     rax, [rdi+rbx+38h]
0x180010abf  sub     rax, [rbp+38h]
0x180010ac3  test    rax, rax
0x180010ac6  jz      short loc_180010AF2
0x180010ac8  test    esi, esi
0x180010aca  jz      short loc_180010AEE
0x180010acc  lea     rdx, [r14+r14*2]
0x180010ad0  shl     rdx, 4
0x180010ad4  lea     rcx, [rbx+18h]
0x180010ad8  add     rdx, 18h
0x180010adc  add     rcx, rdi; lpFileTime1
0x180010adf  add     rdx, rbx; lpFileTime2
0x180010ae2  call    cs:__imp_CompareFileTime
0x180010ae8  test    eax, eax
0x180010aea  cmovs   r14d, esi
0x180010aee  inc     esi
0x180010af0  jmp     short loc_180010A9E
0x180010af2  mov     eax, cs:dword_18002033C
0x180010af8  lea     rdx, [rsp+38h+FileTime2]; lpFileTime2
0x180010afd  imul    rcx, rax, 989680h
0x180010b04  add     rcx, [rdi+rbx+18h]
0x180010b09  mov     qword ptr [rsp+38h+FileTime2.dwLowDateTime], rcx
0x180010b0e  lea     rcx, [rbp+10h]; lpFileTime1
0x180010b12  call    cs:__imp_CompareFileTime
0x180010b18  test    eax, eax
0x180010b1a  jle     short loc_180010B2E
0x180010b1c  mov     rcx, [rbp+10h]
0x180010b20  mov     [rdi+rbx+18h], rcx
0x180010b25  mov     ecx, [rbp+18h]
0x180010b28  add     [rdi+rbx+20h], ecx
0x180010b2c  jmp     short loc_180010B84
0x180010b2e  xor     eax, eax
0x180010b30  jmp     short loc_180010B89
0x180010b32  xorps   xmm0, xmm0
0x180010b35  lea     rdx, [r14+r14*2]
0x180010b39  add     rdx, rdx
0x180010b3c  movups  xmmword ptr [rbx+rdx*8+10h], xmm0
0x180010b41  movups  xmmword ptr [rbx+rdx*8+20h], xmm0
0x180010b46  movups  xmmword ptr [rbx+rdx*8+30h], xmm0
0x180010b4b  mov     rax, [rbp+8]
0x180010b4f  mov     [rbx+rdx*8+10h], rax
0x180010b54  mov     rax, [rbp+10h]
0x180010b58  mov     [rbx+rdx*8+18h], rax
0x180010b5d  mov     eax, [rbp+18h]
0x180010b60  mov     [rbx+rdx*8+20h], eax
0x180010b64  mov     rax, [rbp+28h]
0x180010b68  mov     ecx, [rax+8]
0x180010b6b  mov     [rbx+rdx*8+24h], ecx
0x180010b6f  mov     rax, [rbp+28h]
0x180010b73  mov     ecx, [rax+0Ch]
0x180010b76  mov     [rbx+rdx*8+28h], ecx
0x180010b7a  movups  xmm0, xmmword ptr [rbp+30h]
0x180010b7e  movdqu  xmmword ptr [rbx+rdx*8+30h], xmm0
0x180010b84  mov     eax, 1
0x180010b89  mov     rbx, [rsp+38h+arg_0]
0x180010b8e  mov     rbp, [rsp+38h+arg_8]
0x180010b93  add     rsp, 20h
0x180010b97  pop     r14
0x180010b99  pop     rdi
0x180010b9a  pop     rsi
0x180010b9b  retn
```
