# _GetPublicKey

- ea: `0x18000d8a8`
- end: `0x18000daa9`
- name: `_GetPublicKey`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d3f4`

## callees

- `0x18000b250`
- `0x18000d3d0`
- `0x18000d8a8`
- `0x18000def0`

## import_xrefs

- `bcrypt!BCryptExportKey` at `0x18000d8fa`
- `bcrypt!BCryptExportKey` at `0x18000d953`
- `bcrypt!BCryptExportKey` at `0x18000d8fa`
- `bcrypt!BCryptExportKey` at `0x18000d953`

## string_xrefs

- `0x18000d9cc`: `onecore\ds\security\cryptoapi\ncrypt\storage\keycache.c`
- `0x18000da0c`: `onecore\ds\security\cryptoapi\ncrypt\storage\keycache.c`
- `0x18000da39`: `onecore\ds\security\cryptoapi\ncrypt\storage\keycache.c`
- `0x18000da90`: `onecore\ds\security\cryptoapi\ncrypt\storage\keycache.c`

## pseudocode

```c
__int64 __fastcall GetPublicKey(__int64 a1, UCHAR **a2, ULONG *pcbResult)
{
  int v6; // edx
  NTSTATUS v7; // ebx
  int v8; // r8d
  int v9; // edx
  UCHAR *v10; // rdi
  int v11; // r8d
  int v12; // edx
  int v13; // r8d

  if ( pcbResult && a1 )
  {
    *pcbResult = 0;
    v7 = BCryptExportKey(*(BCRYPT_KEY_HANDLE *)(a1 + 104), 0, L"PUBLICBLOB", 0, 0, pcbResult, 0);
    if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2146893784 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v6,
          v8,
          (unsigned int)"Status",
          v7,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\keycache.c",
          164);
      return (unsigned int)v7;
    }
    if ( !a2 )
      return 0;
    v10 = (UCHAR *)SafeAllocaAllocateFromHeap(*pcbResult);
    if ( v10 )
    {
      v7 = BCryptExportKey(*(BCRYPT_KEY_HANDLE *)(a1 + 104), 0, L"PUBLICBLOB", v10, *pcbResult, pcbResult, 0);
      if ( v7 >= 0 )
      {
        *a2 = v10;
        return 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v12,
          v13,
          (unsigned int)"Status",
          v7,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\keycache.c",
          192);
      MSCryptFree(v10);
    }
    else
    {
      v7 = -2146893810;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v9,
          v11,
          (unsigned int)"Status",
          14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\keycache.c",
          179);
    }
  }
  else
  {
    v7 = -2146893785;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)pcbResult,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\keycache.c",
        149);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d8a8  push    rbx
0x18000d8aa  push    rbp
0x18000d8ab  push    rsi
0x18000d8ac  push    rdi
0x18000d8ad  push    r14
0x18000d8af  sub     rsp, 40h
0x18000d8b3  mov     rsi, r8
0x18000d8b6  mov     r14, rdx
0x18000d8b9  mov     rbp, rcx
0x18000d8bc  test    r8, r8
0x18000d8bf  jz      loc_18000D9DE
0x18000d8c5  test    rcx, rcx
0x18000d8c8  jz      loc_18000D9DE
0x18000d8ce  mov     dword ptr [r8], 0
0x18000d8d5  xor     r9d, r9d; pbOutput
0x18000d8d8  mov     rcx, [rcx+68h]; hKey
0x18000d8dc  xor     edx, edx; hExportKey
0x18000d8de  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18000d8e6  mov     [rsp+68h+pcbResult], r8; pcbResult
0x18000d8eb  lea     r8, aPublicblob; "PUBLICBLOB"
0x18000d8f2  mov     [rsp+68h+cbOutput], 0; cbOutput
0x18000d8fa  call    cs:__imp_BCryptExportKey
0x18000d901  nop     dword ptr [rax+rax+00h]
0x18000d906  mov     ebx, eax
0x18000d908  mov     eax, 80000000h
0x18000d90d  lea     ecx, [rbx+rax]
0x18000d910  test    eax, ecx
0x18000d912  jz      loc_18000D99F
0x18000d918  test    r14, r14
0x18000d91b  jz      short loc_18000D968
0x18000d91d  mov     ecx, [rsi]
0x18000d91f  call    SafeAllocaAllocateFromHeap
0x18000d924  mov     rdi, rax
0x18000d927  test    rax, rax
0x18000d92a  jz      loc_18000DA62
0x18000d930  mov     eax, [rsi]
0x18000d932  lea     r8, aPublicblob; "PUBLICBLOB"
0x18000d939  mov     rcx, [rbp+68h]; hKey
0x18000d93d  mov     r9, rdi; pbOutput
0x18000d940  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18000d948  xor     edx, edx; hExportKey
0x18000d94a  mov     [rsp+68h+pcbResult], rsi; pcbResult
0x18000d94f  mov     [rsp+68h+cbOutput], eax; cbOutput
0x18000d953  call    cs:__imp_BCryptExportKey
0x18000d95a  nop     dword ptr [rax+rax+00h]
0x18000d95f  mov     ebx, eax
0x18000d961  test    eax, eax
0x18000d963  js      short loc_18000D978
0x18000d965  mov     [r14], rdi
0x18000d968  xor     ebx, ebx
0x18000d96a  mov     eax, ebx
0x18000d96c  add     rsp, 40h
0x18000d970  pop     r14
0x18000d972  pop     rdi
0x18000d973  pop     rsi
0x18000d974  pop     rbp
0x18000d975  pop     rbx
0x18000d976  retn
0x18000d978  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d97f  lea     rax, WPP_GLOBAL_Control
0x18000d986  cmp     rcx, rax
0x18000d989  jz      short loc_18000D995
0x18000d98b  test    byte ptr [rcx+1Ch], 1
0x18000d98f  jnz     loc_18000DA35
0x18000d995  mov     rcx, rdi
0x18000d998  call    MSCryptFree
0x18000d99d  jmp     short loc_18000D96A
0x18000d99f  cmp     ebx, 80090028h
0x18000d9a5  jz      loc_18000D918
0x18000d9ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9b2  lea     rax, WPP_GLOBAL_Control
0x18000d9b9  cmp     rcx, rax
0x18000d9bc  jz      short loc_18000D96A
0x18000d9be  test    byte ptr [rcx+1Ch], 1
0x18000d9c2  jz      short loc_18000D96A
0x18000d9c4  mov     [rsp+68h+dwFlags], 0A4h
0x18000d9cc  lea     rax, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d9d3  mov     [rsp+68h+pcbResult], rax
0x18000d9d8  mov     [rsp+68h+cbOutput], ebx
0x18000d9dc  jmp     short loc_18000DA20
0x18000d9de  mov     ebx, 80090027h
0x18000d9e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9ea  lea     rax, WPP_GLOBAL_Control
0x18000d9f1  cmp     rcx, rax
0x18000d9f4  jz      loc_18000D96A
0x18000d9fa  test    byte ptr [rcx+1Ch], 1
0x18000d9fe  jz      loc_18000D96A
0x18000da04  mov     [rsp+68h+dwFlags], 95h
0x18000da0c  lea     rax, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000da13  mov     [rsp+68h+pcbResult], rax
0x18000da18  mov     [rsp+68h+cbOutput], 80090027h
0x18000da20  mov     rcx, [rcx+10h]
0x18000da24  lea     r9, aStatus; "Status"
0x18000da2b  call    WPP_SF_sDsd
0x18000da30  jmp     loc_18000D96A
0x18000da35  mov     rcx, [rcx+10h]
0x18000da39  lea     rax, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000da40  mov     [rsp+68h+dwFlags], 0C0h
0x18000da48  lea     r9, aStatus; "Status"
0x18000da4f  mov     [rsp+68h+pcbResult], rax
0x18000da54  mov     [rsp+68h+cbOutput], ebx
0x18000da58  call    WPP_SF_sDsd
0x18000da5d  jmp     loc_18000D995
0x18000da62  mov     ebx, 8009000Eh
0x18000da67  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da6e  lea     rax, WPP_GLOBAL_Control
0x18000da75  cmp     rcx, rax
0x18000da78  jz      loc_18000D96A
0x18000da7e  test    byte ptr [rcx+1Ch], 1
0x18000da82  jz      loc_18000D96A
0x18000da88  mov     [rsp+68h+dwFlags], 0B3h
0x18000da90  lea     rax, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000da97  mov     [rsp+68h+pcbResult], rax
0x18000da9c  mov     [rsp+68h+cbOutput], 8009000Eh
0x18000daa4  jmp     loc_18000DA20
```
