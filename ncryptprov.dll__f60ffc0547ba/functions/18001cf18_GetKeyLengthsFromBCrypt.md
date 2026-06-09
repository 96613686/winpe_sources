# GetKeyLengthsFromBCrypt

- ea: `0x18001cf18`
- end: `0x18001d2e2`
- name: `GetKeyLengthsFromBCrypt`
- size: `970`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001cdbc`
- `0x180032c10`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000def0`
- `0x18001cf18`
- `0x180063010`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001d09b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001d09b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001d2ca`
- `bcrypt!BCryptSetProperty` at `0x18001cff3`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001cfc3`
- `bcrypt!BCryptGetProperty` at `0x18001d060`
- `bcrypt!BCryptGetProperty` at `0x18001d208`
- `bcrypt!BCryptGetProperty` at `0x18001d274`
- `bcrypt!BCryptGetProperty` at `0x18001d060`
- `bcrypt!BCryptGetProperty` at `0x18001d208`
- `bcrypt!BCryptGetProperty` at `0x18001d274`

## string_xrefs

- `0x18001cf61`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18001d155`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`

## pseudocode

```c
__int64 __fastcall GetKeyLengthsFromBCrypt(__int64 a1, __int64 a2, ULONG a3)
{
  BCRYPT_HANDLE v4; // r12
  UCHAR *v5; // r14
  ULONG v6; // eax
  _QWORD *v7; // rdx
  int v8; // eax
  int v9; // edx
  int v10; // r8d
  unsigned int v11; // eax
  void *v12; // rcx
  NTSTATUS v13; // eax
  int v14; // edx
  int v15; // r8d
  unsigned int v16; // ebx
  _DWORD *v17; // rax
  void *v19; // rcx
  unsigned int Property; // eax
  __int64 v21; // r9
  __int64 v22; // rcx
  unsigned int v23; // eax
  ULONG v24; // [rsp+40h] [rbp-20h]
  int v25; // [rsp+44h] [rbp-1Ch]
  ULONG pcbResult; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_HANDLE hObject[2]; // [rsp+50h] [rbp-10h] BYREF
  ULONG v30; // [rsp+B8h] [rbp+58h] BYREF

  v30 = 0;
  pcbResult = 0;
  if ( a2 && a3 >= 0x10 )
  {
    v4 = 0;
    v5 = 0;
    v25 = 0;
    if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 64) + 32LL) - 196618) > 1 )
      goto LABEL_21;
    if ( *(_QWORD *)(a1 + 552) )
    {
      v5 = *(UCHAR **)(a1 + 552);
      v6 = *(_DWORD *)(a1 + 560);
      v30 = v6;
      goto LABEL_6;
    }
    v19 = *(void **)(a1 + 104);
    if ( !v19 )
      goto LABEL_21;
    Property = BCryptGetProperty(v19, L"ECCParameters", 0, 0, &v30, 0);
    v16 = Property;
    if ( Property )
    {
      v21 = 163;
      v22 = Property;
    }
    else
    {
      v5 = (UCHAR *)SafeAllocaAllocateFromHeap(v30);
      if ( v5 )
      {
        v23 = BCryptGetProperty(*(BCRYPT_HANDLE *)(a1 + 104), L"ECCParameters", v5, v30, &v30, 0);
        v16 = v23;
        if ( v23 )
        {
          DebugTraceError(v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", 180);
LABEL_23:
          MSCryptFree(v5);
LABEL_17:
          if ( v4 )
            BCryptCloseAlgorithmProvider(v4, 0);
          return v16;
        }
        v6 = v30;
        v25 = 1;
LABEL_6:
        v7 = *(_QWORD **)(a1 + 64);
        v24 = v6;
        hObject[0] = 0;
        v8 = ((__int64 (__fastcall *)(BCRYPT_HANDLE *, _QWORD, const wchar_t *, _QWORD))BCryptOpenAlgorithmProvider)(
               hObject,
               *v7,
               L"Microsoft Primitive Provider",
               0);
        if ( v8 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v9,
              v10,
              (unsigned int)"Status",
              v8,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
              98);
        }
        else
        {
          v11 = ((__int64 (__fastcall *)(BCRYPT_HANDLE, const wchar_t *, UCHAR *, _QWORD, _DWORD))BCryptSetProperty)(
                  hObject[0],
                  L"ECCParameters",
                  v5,
                  v24,
                  0);
          if ( v11 )
          {
            DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", 105);
          }
          else
          {
            v4 = hObject[0];
            hObject[0] = 0;
          }
        }
        if ( hObject[0] )
          ((void (__fastcall *)(BCRYPT_HANDLE, _QWORD))BCryptCloseAlgorithmProvider)(hObject[0], 0);
        v12 = v4;
        if ( v4 )
        {
LABEL_12:
          v13 = BCryptGetProperty(v12, L"KeyLengths", (PUCHAR)a2, a3, &pcbResult, 0);
          v16 = v13;
          if ( v13 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v14,
                v15,
                (unsigned int)"Status",
                v13,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
                207);
          }
          else
          {
            if ( v4 )
              v17 = (_DWORD *)a2;
            else
              v17 = (_DWORD *)(*(_QWORD *)(a1 + 64) + 60LL);
            *(_DWORD *)(a2 + 12) = *v17;
          }
          if ( !v5 || !v25 )
            goto LABEL_17;
          goto LABEL_23;
        }
LABEL_21:
        v12 = *(void **)(a1 + 88);
        goto LABEL_12;
      }
      v16 = -2146893810;
      v21 = 171;
      v22 = 2148073486LL;
    }
    DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", v21);
    return v16;
  }
  v16 = -2146893785;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
      140);
  return v16;
}

```

## disassembly

```asm
0x18001cf18  mov     [rsp-38h+arg_0], rbx
0x18001cf1d  mov     [rsp-38h+cbOutput], r8d
0x18001cf22  mov     [rsp-38h+pbOutput], rdx
0x18001cf27  push    rbp
0x18001cf28  push    rsi
0x18001cf29  push    rdi
0x18001cf2a  push    r12
0x18001cf2c  push    r13
0x18001cf2e  push    r14
0x18001cf30  push    r15
0x18001cf32  mov     rbp, rsp
0x18001cf35  sub     rsp, 60h
0x18001cf39  mov     [rbp+arg_18], 0
0x18001cf40  mov     r15, rcx
0x18001cf43  mov     [rbp+var_18], 0
0x18001cf4a  test    rdx, rdx
0x18001cf4d  jz      loc_18001D12B
0x18001cf53  cmp     r8d, 10h
0x18001cf57  jb      loc_18001D12B
0x18001cf5d  mov     rax, [rcx+40h]
0x18001cf61  lea     rsi, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001cf68  xor     r12d, r12d
0x18001cf6b  lea     rdi, aStatus; "Status"
0x18001cf72  xor     r14d, r14d
0x18001cf75  mov     [rbp+var_1C], r12d
0x18001cf79  lea     r13, WPP_GLOBAL_Control
0x18001cf80  mov     ecx, [rax+20h]
0x18001cf83  sub     ecx, 3000Ah
0x18001cf89  cmp     ecx, 1
0x18001cf8c  ja      loc_18001D0CF
0x18001cf92  mov     rax, [r15+228h]
0x18001cf99  test    rax, rax
0x18001cf9c  jz      loc_18001D0C2
0x18001cfa2  mov     r14, rax
0x18001cfa5  xor     ebx, ebx
0x18001cfa7  mov     eax, [r15+230h]
0x18001cfae  mov     [rbp+arg_18], eax
0x18001cfb1  mov     rdx, [r15+40h]
0x18001cfb5  lea     r8, aMicrosoftPrimi; "Microsoft Primitive Provider"
0x18001cfbc  mov     [rbp+var_20], eax
0x18001cfbf  lea     rcx, [rbp+hObject]
0x18001cfc3  mov     rax, cs:__imp_BCryptOpenAlgorithmProvider
0x18001cfca  xor     r9d, r9d
0x18001cfcd  mov     [rbp+hObject], r12
0x18001cfd1  mov     rdx, [rdx]
0x18001cfd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfd9  test    eax, eax
0x18001cfdb  jnz     loc_18001D1B1
0x18001cfe1  mov     r9d, [rbp+var_20]
0x18001cfe5  lea     rdx, aEccparameters; "ECCParameters"
0x18001cfec  mov     rcx, [rbp+hObject]
0x18001cff0  mov     r8, r14
0x18001cff3  mov     rax, cs:__imp_BCryptSetProperty
0x18001cffa  mov     dword ptr [rsp+60h+pcbResult], r12d
0x18001cfff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d004  test    eax, eax
0x18001d006  jnz     loc_18001D2AD
0x18001d00c  mov     r12, [rbp+hObject]
0x18001d010  mov     [rbp+hObject], 0
0x18001d018  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d01f  mov     rax, [rbp+hObject]
0x18001d023  test    rax, rax
0x18001d026  jnz     loc_18001D2C5
0x18001d02c  test    ebx, ebx
0x18001d02e  jnz     loc_18001D0D8
0x18001d034  mov     rcx, r12; hObject
0x18001d037  test    r12, r12
0x18001d03a  jz      loc_18001D0CF
0x18001d040  mov     r9d, [rbp+cbOutput]; cbOutput
0x18001d044  lea     rax, [rbp+var_18]
0x18001d048  mov     r8, [rbp+pbOutput]; pbOutput
0x18001d04c  lea     rdx, aKeylengths; "KeyLengths"
0x18001d053  mov     [rsp+60h+dwFlags], 0; dwFlags
0x18001d05b  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18001d060  call    cs:__imp_BCryptGetProperty
0x18001d067  nop     dword ptr [rax+rax+00h]
0x18001d06c  mov     ebx, eax
0x18001d06e  test    eax, eax
0x18001d070  jnz     loc_18001D0F7
0x18001d076  test    r12, r12
0x18001d079  jz      loc_18001D182
0x18001d07f  mov     rax, [rbp+pbOutput]
0x18001d083  mov     rcx, [rbp+pbOutput]
0x18001d087  mov     eax, [rax]
0x18001d089  mov     [rcx+0Ch], eax
0x18001d08c  test    r14, r14
0x18001d08f  jnz     short loc_18001D0E7
0x18001d091  test    r12, r12
0x18001d094  jz      short loc_18001D0A7
0x18001d096  xor     edx, edx; dwFlags
0x18001d098  mov     rcx, r12; hAlgorithm
0x18001d09b  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001d0a2  nop     dword ptr [rax+rax+00h]
0x18001d0a7  mov     eax, ebx
0x18001d0a9  mov     rbx, [rsp+60h+arg_0]
0x18001d0b1  add     rsp, 60h
0x18001d0b5  pop     r15
0x18001d0b7  pop     r14
0x18001d0b9  pop     r13
0x18001d0bb  pop     r12
0x18001d0bd  pop     rdi
0x18001d0be  pop     rsi
0x18001d0bf  pop     rbp
0x18001d0c0  retn
0x18001d0c2  mov     rcx, [r15+68h]; hObject
0x18001d0c6  test    rcx, rcx
0x18001d0c9  jnz     loc_18001D1ED
0x18001d0cf  mov     rcx, [r15+58h]
0x18001d0d3  jmp     loc_18001D040
0x18001d0d8  cmp     rcx, r13
0x18001d0db  jz      short loc_18001D0E7
0x18001d0dd  test    byte ptr [rcx+1Ch], 1
0x18001d0e1  jnz     loc_18001D18F
0x18001d0e7  cmp     [rbp+var_1C], 0
0x18001d0eb  jz      short loc_18001D091
0x18001d0ed  mov     rcx, r14
0x18001d0f0  call    MSCryptFree
0x18001d0f5  jmp     short loc_18001D091
0x18001d0f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0fe  cmp     rcx, r13
0x18001d101  jz      short loc_18001D08C
0x18001d103  test    byte ptr [rcx+1Ch], 1
0x18001d107  jz      short loc_18001D08C
0x18001d109  mov     rcx, [rcx+10h]
0x18001d10d  mov     r9, rdi
0x18001d110  mov     [rsp+60h+var_30], 0CFh
0x18001d118  mov     qword ptr [rsp+60h+dwFlags], rsi
0x18001d11d  mov     dword ptr [rsp+60h+pcbResult], eax
0x18001d121  call    WPP_SF_sDsd
0x18001d126  jmp     loc_18001D08C
0x18001d12b  mov     ebx, 80090027h
0x18001d130  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d137  lea     r13, WPP_GLOBAL_Control
0x18001d13e  cmp     rcx, r13
0x18001d141  jz      loc_18001D0A7
0x18001d147  test    byte ptr [rcx+1Ch], 1
0x18001d14b  jz      loc_18001D0A7
0x18001d151  mov     rcx, [rcx+10h]
0x18001d155  lea     rsi, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001d15c  mov     [rsp+60h+var_30], 8Ch
0x18001d164  lea     r9, aStatus; "Status"
0x18001d16b  mov     qword ptr [rsp+60h+dwFlags], rsi
0x18001d170  mov     dword ptr [rsp+60h+pcbResult], 80090027h
0x18001d178  call    WPP_SF_sDsd
0x18001d17d  jmp     loc_18001D0A7
0x18001d182  mov     rax, [r15+40h]
0x18001d186  add     rax, 3Ch ; '<'
0x18001d18a  jmp     loc_18001D083
0x18001d18f  mov     rcx, [rcx+10h]
0x18001d193  mov     r9, rdi
0x18001d196  mov     [rsp+60h+var_30], 0C1h
0x18001d19e  mov     qword ptr [rsp+60h+dwFlags], rsi
0x18001d1a3  mov     dword ptr [rsp+60h+pcbResult], ebx
0x18001d1a7  call    WPP_SF_sDsd
0x18001d1ac  jmp     loc_18001D0E7
0x18001d1b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1b8  cmp     rcx, r13
0x18001d1bb  jz      loc_18001D01F
0x18001d1c1  test    byte ptr [rcx+1Ch], 1
0x18001d1c5  jz      loc_18001D01F
0x18001d1cb  mov     rcx, [rcx+10h]
0x18001d1cf  mov     r9, rdi
0x18001d1d2  mov     [rsp+60h+var_30], 62h ; 'b'
0x18001d1da  mov     qword ptr [rsp+60h+dwFlags], rsi
0x18001d1df  mov     dword ptr [rsp+60h+pcbResult], eax
0x18001d1e3  call    WPP_SF_sDsd
0x18001d1e8  jmp     loc_18001D018
0x18001d1ed  lea     rax, [rbp+arg_18]
0x18001d1f1  mov     [rsp+60h+dwFlags], r12d; dwFlags
0x18001d1f6  xor     r9d, r9d; cbOutput
0x18001d1f9  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18001d1fe  xor     r8d, r8d; pbOutput
0x18001d201  lea     rdx, aEccparameters; "ECCParameters"
0x18001d208  call    cs:__imp_BCryptGetProperty
0x18001d20f  nop     dword ptr [rax+rax+00h]
0x18001d214  mov     ebx, eax
0x18001d216  test    eax, eax
0x18001d218  jz      short loc_18001D244
0x18001d21a  mov     r9d, 0A3h
0x18001d220  mov     ecx, eax
0x18001d222  jmp     short loc_18001D234
0x18001d224  mov     ebx, 8009000Eh
0x18001d229  mov     r9d, 0ABh
0x18001d22f  mov     ecx, 8009000Eh
0x18001d234  mov     rdx, rdi
0x18001d237  mov     r8, rsi
0x18001d23a  call    DebugTraceError
0x18001d23f  jmp     loc_18001D0A7
0x18001d244  mov     ecx, [rbp+arg_18]
0x18001d247  call    SafeAllocaAllocateFromHeap
0x18001d24c  mov     r14, rax
0x18001d24f  test    rax, rax
0x18001d252  jz      short loc_18001D224
0x18001d254  mov     r9d, [rbp+arg_18]; cbOutput
0x18001d258  lea     rax, [rbp+arg_18]
0x18001d25c  mov     rcx, [r15+68h]; hObject
0x18001d260  lea     rdx, aEccparameters; "ECCParameters"
0x18001d267  mov     [rsp+60h+dwFlags], r12d; dwFlags
0x18001d26c  mov     r8, r14; pbOutput
0x18001d26f  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18001d274  call    cs:__imp_BCryptGetProperty
0x18001d27b  nop     dword ptr [rax+rax+00h]
0x18001d280  mov     ebx, eax
0x18001d282  test    eax, eax
0x18001d284  jz      short loc_18001D29E
0x18001d286  mov     r9d, 0B4h
0x18001d28c  mov     r8, rsi
0x18001d28f  mov     rdx, rdi
0x18001d292  mov     ecx, eax
0x18001d294  call    DebugTraceError
0x18001d299  jmp     loc_18001D0ED
0x18001d29e  mov     eax, [rbp+arg_18]
0x18001d2a1  mov     [rbp+var_1C], 1
0x18001d2a8  jmp     loc_18001CFB1
0x18001d2ad  mov     r9d, 69h ; 'i'
0x18001d2b3  mov     r8, rsi
0x18001d2b6  mov     rdx, rdi
0x18001d2b9  mov     ecx, eax
0x18001d2bb  call    DebugTraceError
0x18001d2c0  jmp     loc_18001D018
0x18001d2c5  mov     rcx, rax
0x18001d2c8  xor     edx, edx
0x18001d2ca  mov     rax, cs:__imp_BCryptCloseAlgorithmProvider
0x18001d2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2dd  jmp     loc_18001D02C
```
