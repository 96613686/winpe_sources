# TlsHashContext

- ea: `0x180009ca0`
- end: `0x180009f9e`
- name: `TlsHashContext`
- size: `766`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dea0`
- `0x180020718`

## callees

- `0x180001acc`
- `0x180009ca0`
- `0x18000b594`
- `0x18000b654`
- `0x1800183d0`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x180009dd5`
- `bcrypt!BCryptHashData` at `0x180009dd5`
- `bcrypt!BCryptCreateHash` at `0x180009dae`
- `bcrypt!BCryptCreateHash` at `0x180009dae`
- `bcrypt!BCryptFinishHash` at `0x180009df6`
- `bcrypt!BCryptFinishHash` at `0x180009df6`
- `bcrypt!BCryptDestroyHash` at `0x180009e72`
- `bcrypt!BCryptDestroyHash` at `0x180009e72`
- `ntdll!RtlFreeHeap` at `0x180009e8f`
- `ntdll!RtlFreeHeap` at `0x180009e8f`
- `ntdll!RtlAllocateHeap` at `0x180009d78`
- `ntdll!RtlAllocateHeap` at `0x180009d78`

## string_xrefs

- `0x180009e08`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180009e45`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180009f03`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180009f53`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsHashContext(
        __int64 a1,
        UCHAR *a2,
        unsigned __int16 a3,
        const wchar_t *a4,
        PUCHAR pbOutput,
        unsigned __int8 a6)
{
  UCHAR *Heap; // rsi
  UCHAR *v10; // r15
  ULONG v11; // r12d
  __int64 i; // rbx
  const wchar_t **v13; // rax
  __int64 v14; // rdi
  ULONG v15; // ebx
  __int16 v16; // r8
  NTSTATUS v17; // ebx
  NTSTATUS HashEntry; // eax
  __int64 v19; // r9
  _QWORD *v20; // rcx
  char dwFlags; // [rsp+30h] [rbp-48h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+80h] [rbp+8h] BYREF
  unsigned __int16 v24; // [rsp+90h] [rbp+18h]

  v24 = a3;
  Heap = 0;
  phHash = 0;
  if ( a1 && (a2 || !a3) && a4 && (v10 = pbOutput) != 0 && (v11 = a6) != 0 )
  {
    for ( i = 0; (unsigned int)i < g_dwHashInfoTotalCount; i = (unsigned int)(i + 1) )
    {
      v13 = (const wchar_t **)g_pHashInfo[i];
      if ( v13 && *v13 && !wcsnicmp(a4, *v13, 0x40u) )
      {
        v14 = a1 + 32LL * (unsigned int)i;
        if ( !*(_DWORD *)(v14 + 300) )
        {
          HashEntry = I_GetHashEntry((unsigned int)i, *(unsigned int *)(a1 + 12), v14 + 272);
          v17 = HashEntry;
          if ( HashEntry < 0 )
          {
            v19 = 3902;
LABEL_18:
            DebugTraceError(
              (unsigned int)HashEntry,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              v19);
            goto LABEL_23;
          }
        }
        v15 = *(_DWORD *)(v14 + 288);
        Heap = (UCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
        if ( Heap )
        {
          v17 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)(v14 + 272), &phHash, Heap, v15, 0, 0, 0);
          if ( v17 >= 0 )
          {
            HashEntry = BCryptHashData(phHash, a2, v24, 0);
            v17 = HashEntry;
            if ( HashEntry < 0 )
            {
              v19 = 3934;
            }
            else
            {
              HashEntry = BCryptFinishHash(phHash, v10, v11, 0);
              v17 = HashEntry;
              if ( HashEntry >= 0 )
                goto LABEL_23;
              v19 = 3944;
            }
            goto LABEL_18;
          }
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            dwFlags = 86;
            goto LABEL_22;
          }
        }
        else
        {
          v17 = -2146893810;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned int)&WPP_GLOBAL_Control,
              v16,
              (unsigned int)"Status",
              14,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              73);
        }
        goto LABEL_23;
      }
    }
    v17 = -2146893783;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      dwFlags = 53;
LABEL_22:
      WPP_SF_sDsd(
        v20[2],
        (unsigned int)&WPP_GLOBAL_Control,
        a3,
        (unsigned int)"Status",
        v17,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        dwFlags);
    }
  }
  else
  {
    v17 = -2146893785;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v17;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      a3,
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      45);
  }
LABEL_23:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180009ca0  mov     [rsp+arg_8], rbx
0x180009ca5  mov     [rsp+arg_10], r8w
0x180009cab  push    rbp
0x180009cac  push    rsi
0x180009cad  push    rdi
0x180009cae  push    r12
0x180009cb0  push    r13
0x180009cb2  push    r14
0x180009cb4  push    r15
0x180009cb6  sub     rsp, 40h
0x180009cba  xor     esi, esi
0x180009cbc  mov     rbp, r9
0x180009cbf  mov     [rsp+78h+phHash], rsi
0x180009cc7  movzx   eax, r8w
0x180009ccb  mov     r13, rdx
0x180009cce  mov     r14, rcx
0x180009cd1  test    rcx, rcx
0x180009cd4  jz      loc_180009F25
0x180009cda  test    rdx, rdx
0x180009cdd  jz      loc_180009F1C
0x180009ce3  test    rbp, rbp
0x180009ce6  jz      loc_180009F25
0x180009cec  mov     r15, [rsp+78h+pbOutput]
0x180009cf4  test    r15, r15
0x180009cf7  jz      loc_180009F25
0x180009cfd  movzx   r12d, [rsp+78h+arg_28]
0x180009d06  test    r12b, r12b
0x180009d09  jz      loc_180009F25
0x180009d0f  xor     ebx, ebx
0x180009d11  cmp     ebx, cs:g_dwHashInfoTotalCount
0x180009d17  lea     rax, g_pHashInfo
0x180009d1e  jnb     loc_180009E1F
0x180009d24  mov     rax, [rax+rbx*8]
0x180009d28  mov     edi, ebx
0x180009d2a  test    rax, rax
0x180009d2d  jz      short loc_180009D49
0x180009d2f  mov     rdx, [rax]; String2
0x180009d32  test    rdx, rdx
0x180009d35  jz      short loc_180009D49
0x180009d37  mov     r8d, 40h ; '@'; MaxCount
0x180009d3d  mov     rcx, rbp; String1
0x180009d40  call    _wcsnicmp
0x180009d45  test    eax, eax
0x180009d47  jz      short loc_180009D4D
0x180009d49  inc     ebx
0x180009d4b  jmp     short loc_180009D11
0x180009d4d  shl     rdi, 5
0x180009d51  add     rdi, r14
0x180009d54  cmp     [rdi+12Ch], esi
0x180009d5a  jz      loc_180009F6C
0x180009d60  mov     rcx, gs:60h
0x180009d69  xor     edx, edx; Flags
0x180009d6b  mov     ebx, [rdi+120h]
0x180009d71  mov     r8d, ebx; Size
0x180009d74  mov     rcx, [rcx+30h]; HeapHandle
0x180009d78  call    cs:__imp_RtlAllocateHeap
0x180009d7e  mov     rsi, rax
0x180009d81  test    rax, rax
0x180009d84  jz      loc_180009ED5
0x180009d8a  mov     rcx, [rdi+110h]; hAlgorithm
0x180009d91  lea     rdx, [rsp+78h+phHash]; phHash
0x180009d99  xor     eax, eax
0x180009d9b  mov     r9d, ebx; cbHashObject
0x180009d9e  mov     dword ptr [rsp+78h+dwFlags], eax; dwFlags
0x180009da2  mov     r8, rsi; pbHashObject
0x180009da5  mov     [rsp+78h+cbSecret], eax; cbSecret
0x180009da9  mov     [rsp+78h+pbSecret], rax; pbSecret
0x180009dae  call    cs:__imp_BCryptCreateHash
0x180009db4  mov     ebx, eax
0x180009db6  test    eax, eax
0x180009db8  js      loc_180009EAF
0x180009dbe  movzx   r8d, [rsp+78h+arg_10]; cbInput
0x180009dc7  xor     r9d, r9d; dwFlags
0x180009dca  mov     rcx, [rsp+78h+phHash]; hHash
0x180009dd2  mov     rdx, r13; pbInput
0x180009dd5  call    cs:__imp_BCryptHashData
0x180009ddb  mov     ebx, eax
0x180009ddd  test    eax, eax
0x180009ddf  js      loc_180009F93
0x180009de5  mov     rcx, [rsp+78h+phHash]; hHash
0x180009ded  mov     r8d, r12d; cbOutput
0x180009df0  xor     r9d, r9d; dwFlags
0x180009df3  mov     rdx, r15; pbOutput
0x180009df6  call    cs:__imp_BCryptFinishHash
0x180009dfc  mov     ebx, eax
0x180009dfe  test    eax, eax
0x180009e00  jns     short loc_180009E65
0x180009e02  mov     r9d, 0F68h
0x180009e08  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009e0f  mov     ecx, eax
0x180009e11  lea     rdx, aStatus; "Status"
0x180009e18  call    DebugTraceError
0x180009e1d  jmp     short loc_180009E65
0x180009e1f  mov     ebx, 80090029h
0x180009e24  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e2b  lea     rdx, WPP_GLOBAL_Control
0x180009e32  cmp     rcx, rdx
0x180009e35  jz      short loc_180009E65
0x180009e37  test    byte ptr [rcx+1Ch], 1
0x180009e3b  jz      short loc_180009E65
0x180009e3d  mov     dword ptr [rsp+78h+dwFlags], 0F35h
0x180009e45  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009e4c  mov     qword ptr [rsp+78h+cbSecret], rax
0x180009e51  mov     dword ptr [rsp+78h+pbSecret], ebx
0x180009e55  mov     rcx, [rcx+10h]
0x180009e59  lea     r9, aStatus; "Status"
0x180009e60  call    WPP_SF_sDsd
0x180009e65  mov     rcx, [rsp+78h+phHash]; hHash
0x180009e6d  test    rcx, rcx
0x180009e70  jz      short loc_180009E78
0x180009e72  call    cs:__imp_BCryptDestroyHash
0x180009e78  test    rsi, rsi
0x180009e7b  jz      short loc_180009E95
0x180009e7d  mov     rcx, gs:60h
0x180009e86  mov     r8, rsi; P
0x180009e89  xor     edx, edx; Flags
0x180009e8b  mov     rcx, [rcx+30h]; HeapHandle
0x180009e8f  call    cs:__imp_RtlFreeHeap
0x180009e95  mov     eax, ebx
0x180009e97  mov     rbx, [rsp+78h+arg_8]
0x180009e9f  add     rsp, 40h
0x180009ea3  pop     r15
0x180009ea5  pop     r14
0x180009ea7  pop     r13
0x180009ea9  pop     r12
0x180009eab  pop     rdi
0x180009eac  pop     rsi
0x180009ead  pop     rbp
0x180009eae  retn
0x180009eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180009eb6  lea     rdx, WPP_GLOBAL_Control
0x180009ebd  cmp     rcx, rdx
0x180009ec0  jz      short loc_180009E65
0x180009ec2  test    byte ptr [rcx+1Ch], 1
0x180009ec6  jz      short loc_180009E65
0x180009ec8  mov     dword ptr [rsp+78h+dwFlags], 0F56h
0x180009ed0  jmp     loc_180009E45
0x180009ed5  mov     ebx, 8009000Eh
0x180009eda  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ee1  lea     rdx, WPP_GLOBAL_Control
0x180009ee8  cmp     rcx, rdx
0x180009eeb  jz      loc_180009E65
0x180009ef1  test    byte ptr [rcx+1Ch], 1
0x180009ef5  jz      loc_180009E65
0x180009efb  mov     dword ptr [rsp+78h+dwFlags], 0F49h
0x180009f03  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009f0a  mov     qword ptr [rsp+78h+cbSecret], rax
0x180009f0f  mov     dword ptr [rsp+78h+pbSecret], 8009000Eh
0x180009f17  jmp     loc_180009E55
0x180009f1c  test    ax, ax
0x180009f1f  jz      loc_180009CE3
0x180009f25  mov     ebx, 80090027h
0x180009f2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f31  lea     rdx, WPP_GLOBAL_Control
0x180009f38  cmp     rcx, rdx
0x180009f3b  jz      loc_180009E95
0x180009f41  test    byte ptr [rcx+1Ch], 1
0x180009f45  jz      loc_180009E95
0x180009f4b  mov     dword ptr [rsp+78h+dwFlags], 0F2Dh
0x180009f53  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009f5a  mov     qword ptr [rsp+78h+cbSecret], rax
0x180009f5f  mov     dword ptr [rsp+78h+pbSecret], 80090027h
0x180009f67  jmp     loc_180009E55
0x180009f6c  mov     edx, [r14+0Ch]
0x180009f70  lea     r8, [rdi+110h]
0x180009f77  mov     ecx, ebx
0x180009f79  call    I_GetHashEntry
0x180009f7e  mov     ebx, eax
0x180009f80  test    eax, eax
0x180009f82  jns     loc_180009D60
0x180009f88  mov     r9d, 0F3Eh
0x180009f8e  jmp     loc_180009E08
0x180009f93  mov     r9d, 0F5Eh
0x180009f99  jmp     loc_180009E08
```
