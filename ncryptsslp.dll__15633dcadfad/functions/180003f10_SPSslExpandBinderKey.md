# SPSslExpandBinderKey

- ea: `0x180003f10`
- end: `0x180004560`
- name: `SPSslExpandBinderKey`
- size: `1616`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001acc`
- `0x1800037a0`
- `0x180003f10`
- `0x180005860`
- `0x18000b594`
- `0x18000b654`
- `0x1800183d0`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18000410b`
- `bcrypt!BCryptHashData` at `0x18000410b`
- `bcrypt!BCryptCreateHash` at `0x1800040ee`
- `bcrypt!BCryptCreateHash` at `0x1800040ee`
- `bcrypt!BCryptFinishHash` at `0x180004139`
- `bcrypt!BCryptFinishHash` at `0x180004139`
- `bcrypt!BCryptDestroyHash` at `0x18000422d`
- `bcrypt!BCryptDestroyHash` at `0x18000422d`
- `ntdll!RtlFreeHeap` at `0x18000424a`
- `ntdll!RtlFreeHeap` at `0x180004293`
- `ntdll!RtlFreeHeap` at `0x18000424a`
- `ntdll!RtlFreeHeap` at `0x180004293`
- `ntdll!RtlAllocateHeap` at `0x18000400f`
- `ntdll!RtlAllocateHeap` at `0x1800040b1`
- `ntdll!RtlAllocateHeap` at `0x18000400f`
- `ntdll!RtlAllocateHeap` at `0x1800040b1`

## string_xrefs

- `0x18000414f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800041f4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000431c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180004496`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180004514`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800041a4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180004377`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800043c1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180004442`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800044d3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000453e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslExpandBinderKey(_DWORD *a1, _DWORD *a2, __int64 a3, __int64 a4, int a5)
{
  _DWORD *v6; // rdi
  _DWORD *v7; // rsi
  __int64 v8; // rcx
  const char *v9; // r13
  wchar_t *v10; // r14
  __int64 HashInfoFromAlgorithmName; // rax
  int v12; // edx
  int v13; // r8d
  unsigned int v14; // ebp
  const wchar_t *v15; // rdx
  int v16; // r8d
  UCHAR *v17; // r12
  __int64 i; // rbx
  const wchar_t **v19; // rax
  BCRYPT_ALG_HANDLE *v20; // r14
  ULONG v21; // ebx
  UCHAR *Heap; // rax
  int v23; // edx
  int v24; // r8d
  NTSTATUS v25; // ebx
  NTSTATUS HashEntry; // eax
  UCHAR *v27; // rsi
  NTSTATUS v28; // eax
  _QWORD *v30; // rcx
  int v31; // eax
  __int64 v32; // r9
  __int64 v33; // rcx
  __int64 v34; // r9
  char dwFlags; // [rsp+30h] [rbp-58h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int8 v37; // [rsp+90h] [rbp+8h]
  UCHAR *pbOutput; // [rsp+98h] [rbp+10h]

  v6 = a2;
  v7 = a1;
  if ( !a1 || *a1 < 0x310u || a1[1] != 1936944177 )
    v7 = 0;
  if ( !a2 || *a2 < 0x70u || a2[1] != 1936944179 )
    v6 = 0;
  if ( v7 && v6 && (v8 = *((_QWORD *)v6 + 2)) != 0 )
  {
    if ( !a3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          0,
          (unsigned int)"NTE_INVALID_PARAMETER",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          138);
      return 2148073511LL;
    }
    if ( v6[2] != 772 || v6[27] != 1 )
    {
      DebugTraceError(
        2148073513LL,
        "NTE_NOT_SUPPORTED",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        6800);
      return 2148073513LL;
    }
    if ( a5 == 1 )
    {
      v9 = "ext binder";
LABEL_18:
      v10 = *(wchar_t **)(v8 + 136);
      if ( !v10 || !*v10 )
        v10 = L"SHA256";
      HashInfoFromAlgorithmName = I_GetHashInfoFromAlgorithmName(v10);
      if ( !HashInfoFromAlgorithmName )
      {
        v14 = 0;
        v37 = 0;
        v10 = 0;
        goto LABEL_22;
      }
      v14 = *(_DWORD *)(HashInfoFromAlgorithmName + 8);
      v37 = v14;
      if ( v14 <= 0xFF )
      {
LABEL_22:
        pbOutput = (UCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
        if ( !pbOutput )
        {
          v25 = -2146893810;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)v15,
              v16,
              (unsigned int)"Status",
              14,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              178);
          return (unsigned int)v25;
        }
        v17 = 0;
        phHash = 0;
        if ( v10 && (_BYTE)v14 )
        {
          for ( i = 0; (unsigned int)i < g_dwHashInfoTotalCount; i = (unsigned int)(i + 1) )
          {
            v19 = (const wchar_t **)g_pHashInfo[i];
            if ( v19 )
            {
              v15 = *v19;
              if ( *v19 )
              {
                if ( !wcsnicmp(v10, v15, 0x40u) )
                {
                  v20 = (BCRYPT_ALG_HANDLE *)&v7[8 * (unsigned int)i];
                  if ( !*((_DWORD *)v20 + 75) )
                  {
                    HashEntry = I_GetHashEntry((unsigned int)i, (unsigned int)v7[3], v20 + 34);
                    v25 = HashEntry;
                    if ( HashEntry < 0 )
                    {
                      v34 = 3902;
                      goto LABEL_88;
                    }
                  }
                  v21 = *((_DWORD *)v20 + 72);
                  Heap = (UCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
                  v17 = Heap;
                  if ( !Heap )
                  {
                    v25 = -2146893810;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_sDsd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v23,
                        v24,
                        (unsigned int)"Status",
                        14,
                        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                        73);
                    }
                    goto LABEL_46;
                  }
                  v25 = BCryptCreateHash(v20[34], &phHash, Heap, v21, 0, 0, 0);
                  if ( v25 >= 0 )
                  {
                    HashEntry = BCryptHashData(phHash, 0, 0, 0);
                    v25 = HashEntry;
                    if ( HashEntry >= 0 )
                    {
                      v27 = pbOutput;
                      LOBYTE(v14) = v37;
                      v28 = BCryptFinishHash(phHash, pbOutput, v37, 0);
                      v25 = v28;
                      if ( v28 < 0 )
                        DebugTraceError(
                          (unsigned int)v28,
                          "Status",
                          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                          3944);
                      goto LABEL_48;
                    }
                    v34 = 3934;
LABEL_88:
                    DebugTraceError(
                      (unsigned int)HashEntry,
                      "Status",
                      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                      v34);
LABEL_46:
                    LOBYTE(v14) = v37;
                    goto LABEL_47;
                  }
                  v30 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  {
                    goto LABEL_46;
                  }
                  dwFlags = 86;
LABEL_45:
                  WPP_SF_sDsd(
                    v30[2],
                    (_DWORD)v15,
                    v16,
                    (unsigned int)"Status",
                    v25,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                    dwFlags);
                  goto LABEL_46;
                }
              }
            }
          }
          v25 = -2146893783;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_46;
          dwFlags = 53;
          goto LABEL_45;
        }
        v25 = -2146893785;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          v27 = pbOutput;
        }
        else
        {
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v15,
            v16,
            (unsigned int)"Status",
            39,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            45);
LABEL_47:
          v27 = pbOutput;
LABEL_48:
          if ( phHash )
            BCryptDestroyHash(phHash);
          if ( v17 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
          if ( v25 >= 0 )
          {
            v31 = TlsDeriveSecret(v6, v9, v27, (unsigned __int8)v14, 8, a3);
            v25 = v31;
            if ( v31 >= 0 )
            {
LABEL_54:
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v27);
              return (unsigned int)v25;
            }
            v32 = 6857;
            v33 = (unsigned int)v31;
LABEL_84:
            DebugTraceError(v33, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v32);
            goto LABEL_54;
          }
        }
        v32 = 6840;
        v33 = (unsigned int)v25;
        goto LABEL_84;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v12,
          v13,
          (unsigned int)"NTE_INVALID_PARAMETER",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          169);
      return 2148073511LL;
    }
    if ( a5 == 2 )
    {
      v9 = "res binder";
      goto LABEL_18;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"NTE_BAD_FLAGS",
        9,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        157);
    return 2148073481LL;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"NTE_INVALID_HANDLE",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        132);
    return 2148073510LL;
  }
}

```

## disassembly

```asm
0x180003f10  push    rsi
0x180003f12  push    rdi
0x180003f13  push    r15
0x180003f15  sub     rsp, 70h
0x180003f19  mov     r15, r8
0x180003f1c  mov     rdi, rdx
0x180003f1f  mov     rsi, rcx
0x180003f22  test    rcx, rcx
0x180003f25  jz      short loc_180003F38
0x180003f27  cmp     dword ptr [rcx], 310h
0x180003f2d  jb      short loc_180003F38
0x180003f2f  cmp     dword ptr [rcx+4], 73736C31h
0x180003f36  jz      short loc_180003F3A
0x180003f38  xor     esi, esi
0x180003f3a  test    rdx, rdx
0x180003f3d  jz      short loc_180003F4D
0x180003f3f  cmp     dword ptr [rdx], 70h ; 'p'
0x180003f42  jb      short loc_180003F4D
0x180003f44  cmp     dword ptr [rdx+4], 73736C33h
0x180003f4b  jz      short loc_180003F4F
0x180003f4d  xor     edi, edi
0x180003f4f  test    rsi, rsi
0x180003f52  jz      loc_1800043A4
0x180003f58  test    rdi, rdi
0x180003f5b  jz      loc_1800043A4
0x180003f61  mov     rcx, [rdi+10h]
0x180003f65  test    rcx, rcx
0x180003f68  jz      loc_1800043A4
0x180003f6e  mov     [rsp+88h+arg_10], rbx
0x180003f76  mov     [rsp+88h+var_20], rbp
0x180003f7b  mov     [rsp+88h+var_30], r13
0x180003f80  mov     [rsp+88h+var_38], r14
0x180003f85  test    r15, r15
0x180003f88  jz      loc_1800043F7
0x180003f8e  cmp     dword ptr [rdi+8], 304h
0x180003f95  jnz     loc_180004538
0x180003f9b  cmp     dword ptr [rdi+6Ch], 1
0x180003f9f  jnz     loc_180004538
0x180003fa5  mov     eax, [rsp+88h+arg_20]
0x180003fac  sub     eax, 1
0x180003faf  jz      loc_180004335
0x180003fb5  cmp     eax, 1
0x180003fb8  jnz     loc_180004425
0x180003fbe  lea     r13, aResBinder; "res binder"
0x180003fc5  mov     r14, [rcx+88h]
0x180003fcc  test    r14, r14
0x180003fcf  jz      loc_180004341
0x180003fd5  cmp     word ptr [r14], 0
0x180003fda  jz      loc_180004341
0x180003fe0  mov     rcx, r14; String1
0x180003fe3  call    I_GetHashInfoFromAlgorithmName
0x180003fe8  test    rax, rax
0x180003feb  jnz     loc_180004169
0x180003ff1  xor     ebp, ebp
0x180003ff3  mov     [rsp+88h+arg_0], ebp
0x180003ffa  xor     r14d, r14d
0x180003ffd  mov     rcx, gs:60h
0x180004006  xor     edx, edx; Flags
0x180004008  mov     r8d, ebp; Size
0x18000400b  mov     rcx, [rcx+30h]; HeapHandle
0x18000400f  call    cs:__imp_RtlAllocateHeap
0x180004015  mov     [rsp+88h+pbOutput], rax
0x18000401d  test    rax, rax
0x180004020  jz      loc_18000434D
0x180004026  mov     [rsp+88h+var_28], r12
0x18000402b  xor     r12d, r12d
0x18000402e  mov     [rsp+88h+phHash], r12
0x180004033  test    r14, r14
0x180004036  jz      loc_180004474
0x18000403c  test    bpl, bpl
0x18000403f  jz      loc_180004474
0x180004045  xor     ebx, ebx
0x180004047  cmp     ebx, cs:g_dwHashInfoTotalCount
0x18000404d  lea     rax, g_pHashInfo
0x180004054  jnb     loc_1800041CE
0x18000405a  mov     rax, [rax+rbx*8]
0x18000405e  mov     ebp, ebx
0x180004060  test    rax, rax
0x180004063  jz      short loc_18000407F
0x180004065  mov     rdx, [rax]; String2
0x180004068  test    rdx, rdx
0x18000406b  jz      short loc_18000407F
0x18000406d  mov     r8d, 40h ; '@'; MaxCount
0x180004073  mov     rcx, r14; String1
0x180004076  call    _wcsnicmp
0x18000407b  test    eax, eax
0x18000407d  jz      short loc_180004083
0x18000407f  inc     ebx
0x180004081  jmp     short loc_180004047
0x180004083  shl     rbp, 5
0x180004087  lea     r14, [rsi+rbp]
0x18000408b  cmp     [r14+12Ch], r12d
0x180004092  jz      loc_1800044EB
0x180004098  mov     rcx, gs:60h
0x1800040a1  xor     edx, edx; Flags
0x1800040a3  mov     ebx, [r14+120h]
0x1800040aa  mov     r8d, ebx; Size
0x1800040ad  mov     rcx, [rcx+30h]; HeapHandle
0x1800040b1  call    cs:__imp_RtlAllocateHeap
0x1800040b7  mov     r12, rax
0x1800040ba  test    rax, rax
0x1800040bd  jz      loc_1800042EE
0x1800040c3  mov     rcx, [r14+110h]; hAlgorithm
0x1800040ca  lea     rdx, [rsp+88h+phHash]; phHash
0x1800040cf  mov     dword ptr [rsp+88h+dwFlags], 0; dwFlags
0x1800040d7  mov     r9d, ebx; cbHashObject
0x1800040da  mov     [rsp+88h+cbSecret], 0; cbSecret
0x1800040e2  mov     r8, rax; pbHashObject
0x1800040e5  mov     [rsp+88h+pbSecret], 0; pbSecret
0x1800040ee  call    cs:__imp_BCryptCreateHash
0x1800040f4  mov     ebx, eax
0x1800040f6  test    eax, eax
0x1800040f8  js      loc_1800042C0
0x1800040fe  mov     rcx, [rsp+88h+phHash]; hHash
0x180004103  xor     r9d, r9d; dwFlags
0x180004106  xor     r8d, r8d; cbInput
0x180004109  xor     edx, edx; pbInput
0x18000410b  call    cs:__imp_BCryptHashData
0x180004111  mov     ebx, eax
0x180004113  test    eax, eax
0x180004115  js      loc_18000450E
0x18000411b  mov     rsi, [rsp+88h+pbOutput]
0x180004123  xor     r9d, r9d; dwFlags
0x180004126  mov     ebp, [rsp+88h+arg_0]
0x18000412d  mov     rdx, rsi; pbOutput
0x180004130  mov     rcx, [rsp+88h+phHash]; hHash
0x180004135  movzx   r8d, bpl; cbOutput
0x180004139  call    cs:__imp_BCryptFinishHash
0x18000413f  mov     ebx, eax
0x180004141  test    eax, eax
0x180004143  jns     loc_180004223
0x180004149  mov     r9d, 0F68h
0x18000414f  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004156  lea     rdx, aStatus; "Status"
0x18000415d  mov     ecx, eax
0x18000415f  call    DebugTraceError
0x180004164  jmp     loc_180004223
0x180004169  mov     ebp, [rax+8]
0x18000416c  mov     [rsp+88h+arg_0], ebp
0x180004173  cmp     ebp, 0FFh
0x180004179  jbe     loc_180003FFD
0x18000417f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004186  lea     rax, WPP_GLOBAL_Control
0x18000418d  cmp     rcx, rax
0x180004190  jz      short loc_1800041C4
0x180004192  test    byte ptr [rcx+1Ch], 1
0x180004196  jz      short loc_1800041C4
0x180004198  mov     dword ptr [rsp+88h+dwFlags], 1AA9h
0x1800041a0  mov     rcx, [rcx+10h]
0x1800041a4  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800041ab  mov     qword ptr [rsp+88h+cbSecret], rax
0x1800041b0  lea     r9, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x1800041b7  mov     dword ptr [rsp+88h+pbSecret], 80090027h
0x1800041bf  call    WPP_SF_sDsd
0x1800041c4  mov     eax, 80090027h
0x1800041c9  jmp     loc_1800042A0
0x1800041ce  mov     ebx, 80090029h
0x1800041d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041da  lea     rax, WPP_GLOBAL_Control
0x1800041e1  cmp     rcx, rax
0x1800041e4  jz      short loc_180004214
0x1800041e6  test    byte ptr [rcx+1Ch], 1
0x1800041ea  jz      short loc_180004214
0x1800041ec  mov     dword ptr [rsp+88h+dwFlags], 0F35h
0x1800041f4  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800041fb  mov     qword ptr [rsp+88h+cbSecret], rax
0x180004200  mov     dword ptr [rsp+88h+pbSecret], ebx
0x180004204  mov     rcx, [rcx+10h]
0x180004208  lea     r9, aStatus; "Status"
0x18000420f  call    WPP_SF_sDsd
0x180004214  mov     ebp, [rsp+88h+arg_0]
0x18000421b  mov     rsi, [rsp+88h+pbOutput]
0x180004223  mov     rcx, [rsp+88h+phHash]; hHash
0x180004228  test    rcx, rcx
0x18000422b  jz      short loc_180004233
0x18000422d  call    cs:__imp_BCryptDestroyHash
0x180004233  test    r12, r12
0x180004236  jz      short loc_180004250
0x180004238  mov     rcx, gs:60h
0x180004241  mov     r8, r12; P
0x180004244  xor     edx, edx; Flags
0x180004246  mov     rcx, [rcx+30h]; HeapHandle
0x18000424a  call    cs:__imp_RtlFreeHeap
0x180004250  test    ebx, ebx
0x180004252  js      loc_1800044CB
0x180004258  mov     qword ptr [rsp+88h+cbSecret], r15
0x18000425d  movzx   r9d, bpl
0x180004261  mov     r8, rsi
0x180004264  mov     dword ptr [rsp+88h+pbSecret], 8
0x18000426c  mov     rdx, r13
0x18000426f  mov     rcx, rdi
0x180004272  call    TlsDeriveSecret
0x180004277  mov     ebx, eax
0x180004279  test    eax, eax
0x18000427b  js      loc_18000452E
0x180004281  mov     rcx, gs:60h
0x18000428a  mov     r8, rsi; P
0x18000428d  xor     edx, edx; Flags
0x18000428f  mov     rcx, [rcx+30h]; HeapHandle
0x180004293  call    cs:__imp_RtlFreeHeap
0x180004299  mov     r12, [rsp+88h+var_28]
0x18000429e  mov     eax, ebx
0x1800042a0  mov     r13, [rsp+88h+var_30]
0x1800042a5  mov     rbp, [rsp+88h+var_20]
0x1800042aa  mov     rbx, [rsp+88h+arg_10]
0x1800042b2  mov     r14, [rsp+88h+var_38]
0x1800042b7  add     rsp, 70h
0x1800042bb  pop     r15
0x1800042bd  pop     rdi
0x1800042be  pop     rsi
0x1800042bf  retn
0x1800042c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042c7  lea     rax, WPP_GLOBAL_Control
0x1800042ce  cmp     rcx, rax
0x1800042d1  jz      loc_180004214
0x1800042d7  test    byte ptr [rcx+1Ch], 1
0x1800042db  jz      loc_180004214
0x1800042e1  mov     dword ptr [rsp+88h+dwFlags], 0F56h
0x1800042e9  jmp     loc_1800041F4
0x1800042ee  mov     ebx, 8009000Eh
0x1800042f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042fa  lea     rax, WPP_GLOBAL_Control
0x180004301  cmp     rcx, rax
0x180004304  jz      loc_180004214
0x18000430a  test    byte ptr [rcx+1Ch], 1
0x18000430e  jz      loc_180004214
0x180004314  mov     dword ptr [rsp+88h+dwFlags], 0F49h
0x18000431c  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004323  mov     qword ptr [rsp+88h+cbSecret], rax
0x180004328  mov     dword ptr [rsp+88h+pbSecret], 8009000Eh
0x180004330  jmp     loc_180004204
0x180004335  lea     r13, aExtBinder; "ext binder"
0x18000433c  jmp     loc_180003FC5
0x180004341  lea     r14, aSha256; "SHA256"
0x180004348  jmp     loc_180003FE0
0x18000434d  mov     ebx, 8009000Eh
0x180004352  mov     rcx, cs:WPP_GLOBAL_Control
0x180004359  lea     rax, WPP_GLOBAL_Control
0x180004360  cmp     rcx, rax
0x180004363  jz      loc_18000429E
0x180004369  test    byte ptr [rcx+1Ch], 1
0x18000436d  jz      loc_18000429E
0x180004373  mov     rcx, [rcx+10h]
0x180004377  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000437e  mov     dword ptr [rsp+88h+dwFlags], 1AB2h
0x180004386  lea     r9, aStatus; "Status"
0x18000438d  mov     qword ptr [rsp+88h+cbSecret], rax
0x180004392  mov     dword ptr [rsp+88h+pbSecret], 8009000Eh
0x18000439a  call    WPP_SF_sDsd
0x18000439f  jmp     loc_18000429E
0x1800043a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043ab  lea     rax, WPP_GLOBAL_Control
0x1800043b2  cmp     rcx, rax
0x1800043b5  jz      short loc_1800043E9
0x1800043b7  test    byte ptr [rcx+1Ch], 1
0x1800043bb  jz      short loc_1800043E9
0x1800043bd  mov     rcx, [rcx+10h]
0x1800043c1  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800043c8  mov     dword ptr [rsp+88h+dwFlags], 1A84h
0x1800043d0  lea     r9, aNteInvalidHand; "NTE_INVALID_HANDLE"
0x1800043d7  mov     qword ptr [rsp+88h+cbSecret], rax
0x1800043dc  mov     dword ptr [rsp+88h+pbSecret], 80090026h
0x1800043e4  call    WPP_SF_sDsd
0x1800043e9  mov     eax, 80090026h
0x1800043ee  add     rsp, 70h
0x1800043f2  pop     r15
0x1800043f4  pop     rdi
0x1800043f5  pop     rsi
0x1800043f6  retn
0x1800043f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043fe  lea     rax, WPP_GLOBAL_Control
0x180004405  cmp     rcx, rax
0x180004408  jz      loc_1800041C4
0x18000440e  test    byte ptr [rcx+1Ch], 1
0x180004412  jz      loc_1800041C4
0x180004418  mov     dword ptr [rsp+88h+dwFlags], 1A8Ah
0x180004420  jmp     loc_1800041A0
0x180004425  mov     rcx, cs:WPP_GLOBAL_Control
0x18000442c  lea     rax, WPP_GLOBAL_Control
0x180004433  cmp     rcx, rax
0x180004436  jz      short loc_18000446A
0x180004438  test    byte ptr [rcx+1Ch], 1
0x18000443c  jz      short loc_18000446A
0x18000443e  mov     rcx, [rcx+10h]
0x180004442  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004449  mov     dword ptr [rsp+88h+dwFlags], 1A9Dh
0x180004451  lea     r9, aNteBadFlags; "NTE_BAD_FLAGS"
0x180004458  mov     qword ptr [rsp+88h+cbSecret], rax
0x18000445d  mov     dword ptr [rsp+88h+pbSecret], 80090009h
0x180004465  call    WPP_SF_sDsd
0x18000446a  mov     eax, 80090009h
0x18000446f  jmp     loc_1800042A0
0x180004474  mov     ebx, 80090027h
0x180004479  mov     rcx, cs:WPP_GLOBAL_Control
0x180004480  lea     rax, WPP_GLOBAL_Control
0x180004487  cmp     rcx, rax
0x18000448a  jz      short loc_1800044C3
0x18000448c  test    byte ptr [rcx+1Ch], 1
0x180004490  jz      short loc_1800044C3
0x180004492  mov     rcx, [rcx+10h]
  ... truncated ...
```
