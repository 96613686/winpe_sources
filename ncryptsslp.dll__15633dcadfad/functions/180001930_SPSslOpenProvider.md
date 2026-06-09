# SPSslOpenProvider

- ea: `0x180001930`
- end: `0x180001ac5`
- name: `SPSslOpenProvider`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001670`
- `0x180001930`
- `0x180001acc`
- `0x180007940`
- `0x18000b594`
- `0x18000b654`
- `0x180025660`

## string_xrefs

- `0x1800019f4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180001a54`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180001aa3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslOpenProvider(_QWORD *a1, int a2, unsigned int a3)
{
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  int v7; // edx
  int HashEntry; // ebx
  int v9; // r8d
  int v10; // edx
  int v11; // r8d

  if ( a1 )
  {
    if ( (a3 & 0xFFFFFFFE) != 0 )
    {
      HashEntry = -2146893815;
      DebugTraceError(2148073481LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 5110);
      return (unsigned int)HashEntry;
    }
    v5 = (_DWORD *)SafeAllocaAllocateFromHeap(784);
    v6 = v5;
    if ( !v5 )
      return (unsigned int)-2146893810;
    memset(v5, 0, 0x310u);
    *v6 = 784;
    v6[1] = 1936944177;
    v6[2] = 1;
    v6[3] = a3;
    v6[7] = 1;
    HashEntry = I_GetHashEntry(2, a3, v6 + 84);
    if ( HashEntry < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v7,
          v9,
          (unsigned int)"Status",
          HashEntry,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          27);
    }
    else
    {
      HashEntry = I_GetHashEntry(1, a3, v6 + 76);
      if ( HashEntry >= 0 )
      {
        *a1 = v6;
        return 0;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          v11,
          (unsigned int)"Status",
          HashEntry,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          38);
    }
    FreeProviderObject(v6);
    return (unsigned int)HashEntry;
  }
  HashEntry = -2146893785;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      239);
  return (unsigned int)HashEntry;
}

```

## disassembly

```asm
0x180001930  push    rbx
0x180001932  push    rbp
0x180001933  push    rdi
0x180001934  push    r14
0x180001936  sub     rsp, 48h
0x18000193a  mov     ebp, r8d
0x18000193d  mov     r14, rcx
0x180001940  test    rcx, rcx
0x180001943  jz      loc_1800019D2
0x180001949  test    r8d, 0FFFFFFFEh
0x180001950  jnz     loc_180001A9D
0x180001956  mov     ebx, 310h
0x18000195b  mov     ecx, ebx
0x18000195d  call    SafeAllocaAllocateFromHeap
0x180001962  mov     rdi, rax
0x180001965  test    rax, rax
0x180001968  jz      loc_180001A28
0x18000196e  mov     r8d, ebx; Size
0x180001971  xor     edx, edx; Val
0x180001973  mov     rcx, rax; void *
0x180001976  call    memset
0x18000197b  lea     r8, [rdi+150h]
0x180001982  mov     [rdi], ebx
0x180001984  mov     edx, ebp
0x180001986  mov     dword ptr [rdi+4], 73736C31h
0x18000198d  mov     ecx, 2
0x180001992  mov     dword ptr [rdi+8], 1
0x180001999  mov     [rdi+0Ch], ebp
0x18000199c  mov     dword ptr [rdi+1Ch], 1
0x1800019a3  call    I_GetHashEntry
0x1800019a8  mov     ebx, eax
0x1800019aa  test    eax, eax
0x1800019ac  js      loc_180001A7A
0x1800019b2  lea     r8, [rdi+130h]
0x1800019b9  mov     edx, ebp
0x1800019bb  mov     ecx, 1
0x1800019c0  call    I_GetHashEntry
0x1800019c5  mov     ebx, eax
0x1800019c7  test    eax, eax
0x1800019c9  js      short loc_180001A2F
0x1800019cb  mov     [r14], rdi
0x1800019ce  xor     ebx, ebx
0x1800019d0  jmp     short loc_180001A1C
0x1800019d2  mov     ebx, 80090027h
0x1800019d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019de  lea     rax, WPP_GLOBAL_Control
0x1800019e5  cmp     rcx, rax
0x1800019e8  jz      short loc_180001A1C
0x1800019ea  test    byte ptr [rcx+1Ch], 1
0x1800019ee  jz      short loc_180001A1C
0x1800019f0  mov     rcx, [rcx+10h]
0x1800019f4  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800019fb  mov     [rsp+68h+var_38], 13EFh
0x180001a03  lea     r9, aStatus; "Status"
0x180001a0a  mov     [rsp+68h+var_40], rax
0x180001a0f  mov     [rsp+68h+var_48], 80090027h
0x180001a17  call    WPP_SF_sDsd
0x180001a1c  mov     eax, ebx
0x180001a1e  add     rsp, 48h
0x180001a22  pop     r14
0x180001a24  pop     rdi
0x180001a25  pop     rbp
0x180001a26  pop     rbx
0x180001a27  retn
0x180001a28  mov     ebx, 8009000Eh
0x180001a2d  jmp     short loc_180001A1C
0x180001a2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a36  lea     rax, WPP_GLOBAL_Control
0x180001a3d  cmp     rcx, rax
0x180001a40  jz      short loc_180001A70
0x180001a42  test    byte ptr [rcx+1Ch], 1
0x180001a46  jz      short loc_180001A70
0x180001a48  mov     [rsp+68h+var_38], 1426h
0x180001a50  mov     rcx, [rcx+10h]
0x180001a54  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001a5b  mov     [rsp+68h+var_40], rax
0x180001a60  lea     r9, aStatus; "Status"
0x180001a67  mov     [rsp+68h+var_48], ebx
0x180001a6b  call    WPP_SF_sDsd
0x180001a70  mov     rcx, rdi
0x180001a73  call    FreeProviderObject
0x180001a78  jmp     short loc_180001A1C
0x180001a7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a81  lea     rax, WPP_GLOBAL_Control
0x180001a88  cmp     rcx, rax
0x180001a8b  jz      short loc_180001A70
0x180001a8d  test    byte ptr [rcx+1Ch], 1
0x180001a91  jz      short loc_180001A70
0x180001a93  mov     [rsp+68h+var_38], 141Bh
0x180001a9b  jmp     short loc_180001A50
0x180001a9d  mov     r9d, 13F6h
0x180001aa3  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001aaa  lea     rdx, aStatus; "Status"
0x180001ab1  mov     ecx, 80090009h
0x180001ab6  mov     ebx, 80090009h
0x180001abb  call    DebugTraceError
0x180001ac0  jmp     loc_180001A1C
```
