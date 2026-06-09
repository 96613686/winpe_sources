# SPSslCreateClientAuthHash

- ea: `0x1800097f0`
- end: `0x180009c94`
- name: `SPSslCreateClientAuthHash`
- size: `1188`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *, unsigned int, int, wchar_t *String1, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001acc`
- `0x180003ef0`
- `0x1800097f0`
- `0x18000b594`
- `0x18000b654`
- `0x1800183d0`
- `0x180025660`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180009a4f`
- `bcrypt!BCryptCreateHash` at `0x180009a4f`
- `ntdll!RtlAllocateHeap` at `0x1800099ea`
- `ntdll!RtlAllocateHeap` at `0x1800099ea`

## string_xrefs

- `0x180009914`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180009994`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180009a98`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180009af9`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180009b89`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180009bc2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180009c09`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180009c33`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180009c3f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180009c72`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslCreateClientAuthHash(_DWORD *a1, _DWORD *a2, unsigned int a3, int a4, wchar_t *String1, int a6)
{
  unsigned int v7; // r15d
  _QWORD *v8; // r12
  __int64 i; // rcx
  int v11; // r9d
  __int64 j; // rax
  __int64 k; // rdi
  const wchar_t **v14; // rax
  int v15; // edx
  int v16; // r8d
  unsigned int Hash; // ebx
  int HashEntry; // esi
  __int64 v20; // rsi
  BCRYPT_ALG_HANDLE *v21; // r14
  unsigned int v22; // edi
  PVOID Heap; // rax
  int v24; // edx
  int v25; // r8d
  PVOID v26; // rsi
  int v27; // edx
  int v28; // r8d
  int v29; // edx
  int v30; // r8d

  v7 = a3;
  v8 = a2;
  if ( a3 < 0x303 || a3 == 65279 )
  {
    Hash = -2146893783;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        41,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        22);
  }
  else if ( String1 && *String1 )
  {
    if ( a6 )
    {
      Hash = -2146893815;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          a3,
          (unsigned int)"Status",
          9,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          36);
    }
    else
    {
      for ( i = 0; (unsigned int)i < 7; i = (unsigned int)(i + 1) )
      {
        a2 = (_DWORD *)(8 * i);
        if ( (unsigned __int16)ProtocolVersionList[4 * i] == a3 )
        {
          v11 = *(int *)((char *)&dword_180031A24 + (_QWORD)a2);
          if ( v11 )
          {
            a3 = g_dwCipherSuiteInfoTotalCount;
            for ( j = 0; (unsigned int)j < g_dwCipherSuiteInfoTotalCount; j = (unsigned int)(j + 1) )
            {
              a2 = (_DWORD *)g_pCipherSuiteInfo[j];
              if ( a2 && a2[1] == a4 && (v11 & *a2) != 0 )
              {
                for ( k = 0; (unsigned int)k < g_dwHashInfoTotalCount; k = (unsigned int)(k + 1) )
                {
                  v14 = (const wchar_t **)g_pHashInfo[k];
                  if ( v14 && *v14 && !wcsnicmp(String1, *v14, 0x40u) )
                  {
                    if ( a1 && *a1 >= 0x310u && a1[1] == 1936944177 )
                    {
                      if ( !v8 )
                      {
                        Hash = -2146893785;
                        HashEntry = -2146893785;
                        DebugTraceError(
                          2148073511LL,
                          "Status",
                          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                          1337);
                        goto LABEL_47;
                      }
                      v20 = 8LL * (unsigned int)k;
                      v21 = (BCRYPT_ALG_HANDLE *)&a1[v20 + 68];
                      if ( *((_DWORD *)v21 + 7)
                        || (HashEntry = I_GetHashEntry((unsigned int)k, (unsigned int)a1[3], &a1[v20 + 68]),
                            HashEntry >= 0) )
                      {
                        v22 = *((_DWORD *)v21 + 4) + 48;
                        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
                        v26 = Heap;
                        if ( Heap )
                        {
                          memset(Heap, 0, v22);
                          *(_DWORD *)v26 = v22;
                          *((_DWORD *)v26 + 1) = 1936944178;
                          *((_DWORD *)v26 + 2) = v7;
                          *((_DWORD *)v26 + 3) = a4;
                          *((_DWORD *)v26 + 6) = *((_DWORD *)v21 + 4);
                          *((_DWORD *)v26 + 7) = *((_DWORD *)v21 + 6);
                          Hash = BCryptCreateHash(
                                   *v21,
                                   (BCRYPT_HASH_HANDLE *)v26 + 2,
                                   (PUCHAR)v26 + 48,
                                   *((_DWORD *)v21 + 4),
                                   0,
                                   0,
                                   0);
                          if ( (Hash & 0x80000000) == 0 )
                          {
                            *v8 = v26;
                            return 0;
                          }
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                          {
                            WPP_SF_sDsd(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              v27,
                              v28,
                              (unsigned int)"Status",
                              Hash,
                              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                              115);
                          }
                          MSCryptFree(v26);
                          HashEntry = Hash;
                        }
                        else
                        {
                          Hash = -2146893810;
                          HashEntry = -2146893810;
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                          {
                            WPP_SF_sDsd(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              v24,
                              v25,
                              (unsigned int)"Status",
                              14,
                              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                              92);
                          }
                        }
                        goto LABEL_47;
                      }
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        WPP_SF_sDsd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          v29,
                          v30,
                          (unsigned int)"Status",
                          HashEntry,
                          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                          71);
                        Hash = HashEntry;
                        goto LABEL_47;
                      }
                    }
                    else
                    {
                      Hash = -2146893786;
                      HashEntry = -2146893786;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        WPP_SF_sDsd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          v15,
                          v16,
                          (unsigned int)"Status",
                          38,
                          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                          50);
LABEL_47:
                        DebugTraceError(
                          (unsigned int)HashEntry,
                          "Status",
                          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                          1604);
                        return Hash;
                      }
                    }
                    Hash = HashEntry;
                    goto LABEL_47;
                  }
                }
                Hash = -2146893783;
                DebugTraceError(
                  2148073513LL,
                  "Status",
                  "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                  1591);
                return Hash;
              }
            }
          }
          break;
        }
      }
      Hash = -2146893783;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          a3,
          (unsigned int)"Status",
          41,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          45);
    }
  }
  else
  {
    Hash = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 1565);
  }
  return Hash;
}

```

## disassembly

```asm
0x1800097f0  push    rbx
0x1800097f2  push    rbp
0x1800097f3  push    rsi
0x1800097f4  push    rdi
0x1800097f5  push    r12
0x1800097f7  push    r13
0x1800097f9  push    r14
0x1800097fb  push    r15
0x1800097fd  sub     rsp, 48h
0x180009801  mov     ebx, r9d
0x180009804  mov     r15d, r8d
0x180009807  mov     r12, rdx
0x18000980a  mov     r13, rcx
0x18000980d  cmp     r8d, 303h
0x180009814  jb      loc_180009AB1
0x18000981a  cmp     r8d, 0FEFFh
0x180009821  jz      loc_180009AB1
0x180009827  mov     rbp, [rsp+88h+String1]
0x18000982f  test    rbp, rbp
0x180009832  jz      loc_180009C6C
0x180009838  cmp     word ptr [rbp+0], 0
0x18000983d  jz      loc_180009C6C
0x180009843  cmp     [rsp+88h+arg_28], 0
0x18000984b  jnz     loc_180009A6A
0x180009851  xor     ecx, ecx
0x180009853  lea     r14, __ImageBase
0x18000985a  cmp     ecx, 7
0x18000985d  jnb     loc_1800098EE
0x180009863  lea     rdx, ds:0[rcx*8]
0x18000986b  movzx   eax, word ptr [rdx+r14+31A20h]
0x180009874  cmp     eax, r15d
0x180009877  jz      short loc_18000987D
0x180009879  inc     ecx
0x18000987b  jmp     short loc_18000985A
0x18000987d  mov     r9d, [rdx+r14+31A24h]
0x180009885  test    r9d, r9d
0x180009888  jz      short loc_1800098EE
0x18000988a  mov     r8d, cs:g_dwCipherSuiteInfoTotalCount
0x180009891  xor     eax, eax
0x180009893  cmp     eax, r8d
0x180009896  jnb     short loc_1800098EE
0x180009898  mov     rdx, rva g_pCipherSuiteInfo[r14+rax*8]
0x1800098a0  test    rdx, rdx
0x1800098a3  jz      short loc_1800098AA
0x1800098a5  cmp     [rdx+4], ebx
0x1800098a8  jz      short loc_1800098AE
0x1800098aa  inc     eax
0x1800098ac  jmp     short loc_180009893
0x1800098ae  test    [rdx], r9d
0x1800098b1  jz      short loc_1800098AA
0x1800098b3  xor     edi, edi
0x1800098b5  cmp     edi, cs:g_dwHashInfoTotalCount
0x1800098bb  jnb     loc_180009C04
0x1800098c1  mov     rax, rva g_pHashInfo[r14+rdi*8]
0x1800098c9  mov     esi, edi
0x1800098cb  test    rax, rax
0x1800098ce  jz      short loc_1800098EA
0x1800098d0  mov     rdx, [rax]; String2
0x1800098d3  test    rdx, rdx
0x1800098d6  jz      short loc_1800098EA
0x1800098d8  mov     r8d, 40h ; '@'; MaxCount
0x1800098de  mov     rcx, rbp; String1
0x1800098e1  call    _wcsnicmp
0x1800098e6  test    eax, eax
0x1800098e8  jz      short loc_18000994B
0x1800098ea  inc     edi
0x1800098ec  jmp     short loc_1800098B5
0x1800098ee  mov     ebx, 80090029h
0x1800098f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098fa  lea     rax, WPP_GLOBAL_Control
0x180009901  cmp     rcx, rax
0x180009904  jz      short loc_180009938
0x180009906  test    byte ptr [rcx+1Ch], 1
0x18000990a  jz      short loc_180009938
0x18000990c  mov     [rsp+88h+dwFlags], 62Dh
0x180009914  lea     rdi, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000991b  mov     qword ptr [rsp+88h+cbSecret], rdi
0x180009920  mov     dword ptr [rsp+88h+pbSecret], 80090029h
0x180009928  mov     rcx, [rcx+10h]
0x18000992c  lea     r9, aStatus; "Status"
0x180009933  call    WPP_SF_sDsd
0x180009938  mov     eax, ebx
0x18000993a  add     rsp, 48h
0x18000993e  pop     r15
0x180009940  pop     r14
0x180009942  pop     r13
0x180009944  pop     r12
0x180009946  pop     rdi
0x180009947  pop     rsi
0x180009948  pop     rbp
0x180009949  pop     rbx
0x18000994a  retn
0x18000994b  test    r13, r13
0x18000994e  jz      short loc_180009964
0x180009950  cmp     dword ptr [r13+0], 310h
0x180009958  jb      short loc_180009964
0x18000995a  cmp     dword ptr [r13+4], 73736C31h
0x180009962  jz      short loc_1800099AD
0x180009964  mov     ebx, 80090026h
0x180009969  mov     esi, ebx
0x18000996b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009972  lea     rax, WPP_GLOBAL_Control
0x180009979  cmp     rcx, rax
0x18000997c  jz      loc_180009C29
0x180009982  test    byte ptr [rcx+1Ch], 1
0x180009986  jz      loc_180009C29
0x18000998c  mov     [rsp+88h+dwFlags], 532h
0x180009994  lea     rdi, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000999b  mov     qword ptr [rsp+88h+cbSecret], rdi
0x1800099a0  mov     dword ptr [rsp+88h+pbSecret], 80090026h
0x1800099a8  jmp     loc_180009B20
0x1800099ad  test    r12, r12
0x1800099b0  jz      loc_180009C3F
0x1800099b6  shl     rsi, 5
0x1800099ba  lea     r14, [r13+110h]
0x1800099c1  add     r14, rsi
0x1800099c4  cmp     dword ptr [r14+1Ch], 0
0x1800099c9  jz      loc_180009B4C
0x1800099cf  mov     rcx, gs:60h
0x1800099d8  xor     edx, edx; Flags
0x1800099da  mov     edi, [r14+10h]
0x1800099de  add     edi, 30h ; '0'
0x1800099e1  mov     r8d, edi; Size
0x1800099e4  mov     rcx, [rcx+30h]; HeapHandle
0x1800099e8  mov     ebp, edi
0x1800099ea  call    cs:__imp_RtlAllocateHeap
0x1800099f0  mov     rsi, rax
0x1800099f3  test    rax, rax
0x1800099f6  jz      loc_180009AE4
0x1800099fc  mov     r8d, ebp; Size
0x1800099ff  xor     edx, edx; Val
0x180009a01  mov     rcx, rax; void *
0x180009a04  call    memset
0x180009a09  mov     [rsi], edi
0x180009a0b  lea     r8, [rsi+30h]; pbHashObject
0x180009a0f  mov     dword ptr [rsi+4], 73736C32h
0x180009a16  lea     rdx, [rsi+10h]; phHash
0x180009a1a  mov     [rsi+8], r15d
0x180009a1e  mov     [rsi+0Ch], ebx
0x180009a21  mov     eax, [r14+10h]
0x180009a25  mov     [rsi+18h], eax
0x180009a28  mov     eax, [r14+18h]
0x180009a2c  mov     [rsi+1Ch], eax
0x180009a2f  mov     r9d, [r14+10h]; cbHashObject
0x180009a33  mov     rcx, [r14]; hAlgorithm
0x180009a36  mov     [rsp+88h+dwFlags], 0; dwFlags
0x180009a3e  mov     [rsp+88h+cbSecret], 0; cbSecret
0x180009a46  mov     [rsp+88h+pbSecret], 0; pbSecret
0x180009a4f  call    cs:__imp_BCryptCreateHash
0x180009a55  mov     ebx, eax
0x180009a57  test    eax, eax
0x180009a59  js      loc_180009BB4
0x180009a5f  mov     [r12], rsi
0x180009a63  xor     ebx, ebx
0x180009a65  jmp     loc_180009938
0x180009a6a  mov     ebx, 80090009h
0x180009a6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a76  lea     rax, WPP_GLOBAL_Control
0x180009a7d  cmp     rcx, rax
0x180009a80  jz      loc_180009938
0x180009a86  test    byte ptr [rcx+1Ch], 1
0x180009a8a  jz      loc_180009938
0x180009a90  mov     [rsp+88h+dwFlags], 624h
0x180009a98  lea     rdi, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009a9f  mov     qword ptr [rsp+88h+cbSecret], rdi
0x180009aa4  mov     dword ptr [rsp+88h+pbSecret], 80090009h
0x180009aac  jmp     loc_180009928
0x180009ab1  mov     ebx, 80090029h
0x180009ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x180009abd  lea     rax, WPP_GLOBAL_Control
0x180009ac4  cmp     rcx, rax
0x180009ac7  jz      loc_180009938
0x180009acd  test    byte ptr [rcx+1Ch], 1
0x180009ad1  jz      loc_180009938
0x180009ad7  mov     [rsp+88h+dwFlags], 616h
0x180009adf  jmp     loc_180009914
0x180009ae4  mov     ebx, 8009000Eh
0x180009ae9  mov     esi, ebx
0x180009aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180009af2  lea     rax, WPP_GLOBAL_Control
0x180009af9  lea     rdi, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009b00  cmp     rcx, rax
0x180009b03  jz      short loc_180009B30
0x180009b05  test    byte ptr [rcx+1Ch], 1
0x180009b09  jz      short loc_180009B30
0x180009b0b  mov     [rsp+88h+dwFlags], 55Ch
0x180009b13  mov     qword ptr [rsp+88h+cbSecret], rdi
0x180009b18  mov     dword ptr [rsp+88h+pbSecret], 8009000Eh
0x180009b20  mov     rcx, [rcx+10h]
0x180009b24  lea     r9, aStatus; "Status"
0x180009b2b  call    WPP_SF_sDsd
0x180009b30  mov     r9d, 644h
0x180009b36  lea     rdx, aStatus; "Status"
0x180009b3d  mov     r8, rdi
0x180009b40  mov     ecx, esi
0x180009b42  call    DebugTraceError
0x180009b47  jmp     loc_180009938
0x180009b4c  mov     edx, [r13+0Ch]
0x180009b50  mov     r8, r14
0x180009b53  mov     ecx, edi
0x180009b55  call    I_GetHashEntry
0x180009b5a  mov     esi, eax
0x180009b5c  test    eax, eax
0x180009b5e  jns     loc_1800099CF
0x180009b64  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b6b  lea     rax, WPP_GLOBAL_Control
0x180009b72  cmp     rcx, rax
0x180009b75  jz      loc_180009C29
0x180009b7b  test    byte ptr [rcx+1Ch], 1
0x180009b7f  jz      loc_180009C29
0x180009b85  mov     rcx, [rcx+10h]
0x180009b89  lea     rdi, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009b90  mov     [rsp+88h+dwFlags], 547h
0x180009b98  lea     r9, aStatus; "Status"
0x180009b9f  mov     qword ptr [rsp+88h+cbSecret], rdi
0x180009ba4  mov     dword ptr [rsp+88h+pbSecret], esi
0x180009ba8  call    WPP_SF_sDsd
0x180009bad  mov     ebx, esi
0x180009baf  jmp     loc_180009B30
0x180009bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bbb  lea     rax, WPP_GLOBAL_Control
0x180009bc2  lea     rdi, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009bc9  cmp     rcx, rax
0x180009bcc  jz      short loc_180009BF5
0x180009bce  test    byte ptr [rcx+1Ch], 1
0x180009bd2  jz      short loc_180009BF5
0x180009bd4  mov     rcx, [rcx+10h]
0x180009bd8  lea     r9, aStatus; "Status"
0x180009bdf  mov     [rsp+88h+dwFlags], 573h
0x180009be7  mov     qword ptr [rsp+88h+cbSecret], rdi
0x180009bec  mov     dword ptr [rsp+88h+pbSecret], ebx
0x180009bf0  call    WPP_SF_sDsd
0x180009bf5  mov     rcx, rsi
0x180009bf8  call    MSCryptFree
0x180009bfd  mov     esi, ebx
0x180009bff  jmp     loc_180009B30
0x180009c04  mov     ebx, 80090029h
0x180009c09  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009c10  mov     ecx, ebx
0x180009c12  lea     rdx, aStatus; "Status"
0x180009c19  mov     r9d, 637h
0x180009c1f  call    DebugTraceError
0x180009c24  jmp     loc_180009938
0x180009c29  mov     ebx, esi
0x180009c2b  test    esi, esi
0x180009c2d  jns     loc_180009938
0x180009c33  lea     rdi, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009c3a  jmp     loc_180009B30
0x180009c3f  lea     rdi, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009c46  mov     ebx, 80090027h
0x180009c4b  mov     r8, rdi
0x180009c4e  lea     rdx, aStatus; "Status"
0x180009c55  mov     r9d, 539h
0x180009c5b  mov     ecx, 80090027h
0x180009c60  mov     esi, ebx
0x180009c62  call    DebugTraceError
0x180009c67  jmp     loc_180009B30
0x180009c6c  mov     r9d, 61Dh
0x180009c72  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009c79  lea     rdx, aStatus; "Status"
0x180009c80  mov     ecx, 80090027h
0x180009c85  mov     ebx, 80090027h
0x180009c8a  call    DebugTraceError
0x180009c8f  jmp     loc_180009938
```
