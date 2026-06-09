# SetCertificateProperty

- ea: `0x180035318`
- end: `0x180035492`
- name: `SetCertificateProperty`
- size: `378`
- prototype: `__int64 __fastcall(__int64, const BYTE *, DWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180033a10`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000def0`
- `0x180035318`
- `0x1800398b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800353ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800353ee`
- `CRYPT32!CertCreateCertificateContext` at `0x1800353dd`
- `CRYPT32!CertCreateCertificateContext` at `0x1800353dd`

## string_xrefs

- `0x18003535e`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x1800353a3`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x180035400`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`

## pseudocode

```c
__int64 __fastcall SetCertificateProperty(__int64 a1, const BYTE *a2, DWORD a3)
{
  size_t v3; // rsi
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rcx
  DWORD LastError; // eax
  __int64 v10; // rcx
  void *v11; // rax

  v3 = a3;
  if ( a2 )
  {
    if ( a3 - 1 <= 0xFFFFF )
    {
LABEL_3:
      if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 64) + 8LL) - 3) > 2 )
      {
        v6 = -2146893786;
        v7 = 2580;
        v8 = 2148073510LL;
LABEL_5:
        DebugTraceError(v8, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", v7);
        return v6;
      }
      if ( a2 && !CertCreateCertificateContext(0x10001u, a2, a3) )
      {
        LastError = GetLastError();
        DebugTraceError(LastError, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", 2597);
        return (unsigned int)-2146893785;
      }
      v10 = *(_QWORD *)(a1 + 512);
      if ( v10 )
      {
        MSCryptFree(v10);
        *(_DWORD *)(a1 + 520) = 0;
        *(_QWORD *)(a1 + 512) = 0;
      }
      if ( a2 )
      {
        v11 = (void *)SafeAllocaAllocateFromHeap(v3);
        *(_QWORD *)(a1 + 512) = v11;
        if ( !v11 )
        {
          v6 = -2146893810;
          v7 = 2624;
          v8 = 2148073486LL;
          goto LABEL_5;
        }
        memcpy_0(v11, a2, v3);
      }
      v6 = 0;
      *(_DWORD *)(a1 + 520) = v3;
      return v6;
    }
  }
  else if ( !a3 )
  {
    goto LABEL_3;
  }
  v6 = -2146893785;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
      (unsigned int)"status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
      11);
  return v6;
}

```

## disassembly

```asm
0x180035318  push    rbx
0x18003531a  push    rbp
0x18003531b  push    rsi
0x18003531c  push    rdi
0x18003531d  sub     rsp, 48h
0x180035321  mov     esi, r8d
0x180035324  mov     rbx, rdx
0x180035327  mov     rdi, rcx
0x18003532a  test    rdx, rdx
0x18003532d  jnz     short loc_18003536F
0x18003532f  test    r8d, r8d
0x180035332  jnz     short loc_180035379
0x180035334  mov     rax, [rcx+40h]
0x180035338  mov     ecx, [rax+8]
0x18003533b  sub     ecx, 3
0x18003533e  cmp     ecx, 2
0x180035341  jbe     loc_1800353D0
0x180035347  mov     ebx, 80090026h
0x18003534c  mov     r9d, 0A14h
0x180035352  mov     ecx, 80090026h
0x180035357  lea     rdx, aStatus_0; "status"
0x18003535e  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180035365  call    DebugTraceError
0x18003536a  jmp     loc_180035486
0x18003536f  lea     eax, [rsi-1]
0x180035372  cmp     eax, 0FFFFFh
0x180035377  jbe     short loc_180035334
0x180035379  mov     ebx, 80090027h
0x18003537e  mov     rcx, cs:WPP_GLOBAL_Control
0x180035385  lea     rax, WPP_GLOBAL_Control
0x18003538c  cmp     rcx, rax
0x18003538f  jz      loc_180035486
0x180035395  test    byte ptr [rcx+1Ch], 1
0x180035399  jz      loc_180035486
0x18003539f  mov     rcx, [rcx+10h]
0x1800353a3  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800353aa  mov     [rsp+68h+var_38], 0A0Bh
0x1800353b2  lea     r9, aStatus_0; "status"
0x1800353b9  mov     [rsp+68h+var_40], r8
0x1800353be  mov     [rsp+68h+var_48], 80090027h
0x1800353c6  call    WPP_SF_sDsd
0x1800353cb  jmp     loc_180035486
0x1800353d0  test    rbx, rbx
0x1800353d3  jz      short loc_18003541C
0x1800353d5  mov     r8d, esi; cbCertEncoded
0x1800353d8  mov     ecx, 10001h; dwCertEncodingType
0x1800353dd  call    cs:__imp_CertCreateCertificateContext
0x1800353e4  nop     dword ptr [rax+rax+00h]
0x1800353e9  test    rax, rax
0x1800353ec  jnz     short loc_18003541C
0x1800353ee  call    cs:__imp_GetLastError
0x1800353f5  nop     dword ptr [rax+rax+00h]
0x1800353fa  mov     r9d, 0A25h
0x180035400  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180035407  mov     ecx, eax
0x180035409  lea     rdx, aDwreturn; "dwReturn"
0x180035410  call    DebugTraceError
0x180035415  mov     ebx, 80090027h
0x18003541a  jmp     short loc_180035486
0x18003541c  mov     rcx, [rdi+200h]
0x180035423  test    rcx, rcx
0x180035426  jz      short loc_180035442
0x180035428  call    MSCryptFree
0x18003542d  mov     dword ptr [rdi+208h], 0
0x180035437  mov     qword ptr [rdi+200h], 0
0x180035442  test    rbx, rbx
0x180035445  jz      short loc_18003547E
0x180035447  mov     rcx, rsi
0x18003544a  call    SafeAllocaAllocateFromHeap
0x18003544f  mov     [rdi+200h], rax
0x180035456  test    rax, rax
0x180035459  jnz     short loc_180035470
0x18003545b  mov     ebx, 8009000Eh
0x180035460  mov     r9d, 0A40h
0x180035466  mov     ecx, 8009000Eh
0x18003546b  jmp     loc_180035357
0x180035470  mov     r8, rsi; Size
0x180035473  mov     rdx, rbx; Src
0x180035476  mov     rcx, rax; void *
0x180035479  call    memcpy_0
0x18003547e  xor     ebx, ebx
0x180035480  mov     [rdi+208h], esi
0x180035486  mov     eax, ebx
0x180035488  add     rsp, 48h
0x18003548c  pop     rdi
0x18003548d  pop     rsi
0x18003548e  pop     rbp
0x18003548f  pop     rbx
0x180035490  retn
```
