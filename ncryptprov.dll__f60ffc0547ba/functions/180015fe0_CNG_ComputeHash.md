# CNG_ComputeHash

- ea: `0x180015fe0`
- end: `0x180016210`
- name: `CNG_ComputeHash`
- size: `560`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, ULONG, PUCHAR pbOutput)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800140b4`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000bf20`
- `0x180015fe0`
- `0x180038970`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1800160a6`
- `bcrypt!BCryptCreateHash` at `0x1800160a6`
- `bcrypt!BCryptHashData` at `0x1800160ca`
- `bcrypt!BCryptHashData` at `0x1800160ca`
- `bcrypt!BCryptDestroyHash` at `0x180016198`
- `bcrypt!BCryptDestroyHash` at `0x180016198`
- `bcrypt!BCryptFinishHash` at `0x1800160ee`
- `bcrypt!BCryptFinishHash` at `0x1800160ee`
- `bcrypt!BCryptGetProperty` at `0x180016066`
- `bcrypt!BCryptGetProperty` at `0x180016066`

## string_xrefs

- `0x180016106`: `onecore\ds\security\cryptoapi\ncrypt\common\provider.c`
- `0x180016182`: `onecore\ds\security\cryptoapi\ncrypt\common\provider.c`
- `0x1800161d5`: `onecore\ds\security\cryptoapi\ncrypt\common\provider.c`

## pseudocode

```c
__int64 __fastcall CNG_ComputeHash(
        PUCHAR pbInput,
        ULONG cbInput,
        __int64 a3,
        void *a4,
        ULONG pcbResult,
        ULONG *pbOutput)
{
  unsigned int Property; // ebx
  unsigned int BCryptHandle; // eax
  ULONG *v12; // rdi
  int v13; // edx
  __int64 v14; // r9
  _QWORD *v15; // rcx
  char v17; // [rsp+30h] [rbp-38h]
  BCRYPT_HANDLE hObject[2]; // [rsp+40h] [rbp-28h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+70h] [rbp+8h] BYREF

  Property = 0;
  hObject[0] = 0;
  phHash = 0;
  pcbResult = 0;
  memset_0(a4, 0, 0x40u);
  if ( !pbInput )
    return Property;
  BCryptHandle = CNG_GetBCryptHandle(a3, hObject);
  Property = BCryptHandle;
  if ( BCryptHandle )
  {
    v14 = 178;
    goto LABEL_9;
  }
  v12 = pbOutput;
  Property = BCryptGetProperty(hObject[0], L"HashDigestLength", (PUCHAR)pbOutput, 4u, &pcbResult, 0);
  if ( !Property )
  {
    if ( *v12 > 0x40 )
    {
      Property = -2146893784;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\provider.c",
          (unsigned int)"Status",
          40,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\provider.c",
          199);
      goto LABEL_12;
    }
    BCryptHandle = BCryptCreateHash(hObject[0], &phHash, 0, 0, 0, 0, 0);
    Property = BCryptHandle;
    if ( !BCryptHandle )
    {
      Property = BCryptHashData(phHash, pbInput, cbInput, 0);
      if ( !Property )
      {
        BCryptHandle = BCryptFinishHash(phHash, (PUCHAR)a4, *v12, 0);
        Property = BCryptHandle;
        if ( !BCryptHandle )
          goto LABEL_12;
        v14 = 236;
        goto LABEL_9;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v17 = -32;
LABEL_22:
        WPP_SF_sDsd(
          v15[2],
          v13,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\provider.c",
          (unsigned int)"Status",
          Property,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\provider.c",
          v17);
        goto LABEL_12;
      }
      goto LABEL_12;
    }
    v14 = 213;
LABEL_9:
    DebugTraceError(BCryptHandle, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\provider.c", v14);
    goto LABEL_12;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v17 = -64;
    goto LABEL_22;
  }
LABEL_12:
  if ( phHash )
    BCryptDestroyHash(phHash);
  return Property;
}

```

## disassembly

```asm
0x180015fe0  mov     rax, rsp
0x180015fe3  mov     [rax+10h], rbx
0x180015fe7  mov     [rax+18h], rbp
0x180015feb  push    rsi
0x180015fec  push    rdi
0x180015fed  push    r14
0x180015fef  sub     rsp, 50h
0x180015ff3  xor     ebx, ebx
0x180015ff5  mov     rdi, r8
0x180015ff8  mov     r14d, edx
0x180015ffb  mov     [rax-28h], rbx
0x180015fff  mov     rbp, rcx
0x180016002  mov     [rax+8], rbx
0x180016006  xor     edx, edx; Val
0x180016008  mov     [rax+28h], ebx
0x18001600b  lea     r8d, [rbx+40h]; Size
0x18001600f  mov     rcx, r9; void *
0x180016012  mov     rsi, r9
0x180016015  call    memset_0
0x18001601a  test    rbp, rbp
0x18001601d  jz      loc_180016144
0x180016023  lea     rdx, [rsp+68h+hObject]
0x180016028  mov     rcx, rdi
0x18001602b  call    CNG_GetBCryptHandle
0x180016030  mov     ebx, eax
0x180016032  test    eax, eax
0x180016034  jnz     loc_1800161FA
0x18001603a  mov     rdi, [rsp+68h+pbOutput]
0x180016042  lea     r9d, [rbx+4]; cbOutput
0x180016046  mov     rcx, [rsp+68h+hObject]; hObject
0x18001604b  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180016052  mov     [rsp+68h+dwFlags], eax; dwFlags
0x180016056  mov     r8, rdi; pbOutput
0x180016059  lea     rax, [rsp+68h+arg_20]
0x180016061  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180016066  call    cs:__imp_BCryptGetProperty
0x18001606d  nop     dword ptr [rax+rax+00h]
0x180016072  mov     ebx, eax
0x180016074  test    eax, eax
0x180016076  jnz     loc_18001611D
0x18001607c  cmp     dword ptr [rdi], 40h ; '@'
0x18001607f  ja      loc_18001615C
0x180016085  mov     rcx, [rsp+68h+hObject]; hAlgorithm
0x18001608a  lea     rdx, [rsp+68h+phHash]; phHash
0x18001608f  mov     dword ptr [rsp+68h+var_38], eax; dwFlags
0x180016093  xor     r9d, r9d; cbHashObject
0x180016096  mov     [rsp+68h+dwFlags], eax; cbSecret
0x18001609a  xor     r8d, r8d; pbHashObject
0x18001609d  mov     [rsp+68h+pcbResult], 0; pbSecret
0x1800160a6  call    cs:__imp_BCryptCreateHash
0x1800160ad  nop     dword ptr [rax+rax+00h]
0x1800160b2  mov     ebx, eax
0x1800160b4  test    eax, eax
0x1800160b6  jnz     loc_180016205
0x1800160bc  mov     rcx, [rsp+68h+phHash]; hHash
0x1800160c1  xor     r9d, r9d; dwFlags
0x1800160c4  mov     r8d, r14d; cbInput
0x1800160c7  mov     rdx, rbp; pbInput
0x1800160ca  call    cs:__imp_BCryptHashData
0x1800160d1  nop     dword ptr [rax+rax+00h]
0x1800160d6  mov     ebx, eax
0x1800160d8  test    eax, eax
0x1800160da  jnz     loc_1800161A6
0x1800160e0  mov     r8d, [rdi]; cbOutput
0x1800160e3  xor     r9d, r9d; dwFlags
0x1800160e6  mov     rcx, [rsp+68h+phHash]; hHash
0x1800160eb  mov     rdx, rsi; pbOutput
0x1800160ee  call    cs:__imp_BCryptFinishHash
0x1800160f5  nop     dword ptr [rax+rax+00h]
0x1800160fa  mov     ebx, eax
0x1800160fc  test    eax, eax
0x1800160fe  jz      short loc_18001613A
0x180016100  mov     r9d, 0ECh
0x180016106  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001610d  mov     ecx, eax
0x18001610f  lea     rdx, aStatus; "Status"
0x180016116  call    DebugTraceError
0x18001611b  jmp     short loc_18001613A
0x18001611d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016124  lea     rax, WPP_GLOBAL_Control
0x18001612b  cmp     rcx, rax
0x18001612e  jz      short loc_18001613A
0x180016130  test    byte ptr [rcx+1Ch], 1
0x180016134  jnz     loc_1800161CD
0x18001613a  mov     rcx, [rsp+68h+phHash]; hHash
0x18001613f  test    rcx, rcx
0x180016142  jnz     short loc_180016198
0x180016144  lea     r11, [rsp+68h+var_18]
0x180016149  mov     eax, ebx
0x18001614b  mov     rbx, [r11+28h]
0x18001614f  mov     rbp, [r11+30h]
0x180016153  mov     rsp, r11
0x180016156  pop     r14
0x180016158  pop     rdi
0x180016159  pop     rsi
0x18001615a  retn
0x18001615c  mov     ebx, 80090028h
0x180016161  mov     rcx, cs:WPP_GLOBAL_Control
0x180016168  lea     rax, WPP_GLOBAL_Control
0x18001616f  cmp     rcx, rax
0x180016172  jz      short loc_18001613A
0x180016174  test    byte ptr [rcx+1Ch], 1
0x180016178  jz      short loc_18001613A
0x18001617a  mov     dword ptr [rsp+68h+var_38], 0C7h
0x180016182  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016189  mov     qword ptr [rsp+68h+dwFlags], r8
0x18001618e  mov     dword ptr [rsp+68h+pcbResult], 80090028h
0x180016196  jmp     short loc_1800161E5
0x180016198  call    cs:__imp_BCryptDestroyHash
0x18001619f  nop     dword ptr [rax+rax+00h]
0x1800161a4  jmp     short loc_180016144
0x1800161a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800161ad  lea     rax, WPP_GLOBAL_Control
0x1800161b4  cmp     rcx, rax
0x1800161b7  jz      short loc_18001613A
0x1800161b9  test    byte ptr [rcx+1Ch], 1
0x1800161bd  jz      loc_18001613A
0x1800161c3  mov     dword ptr [rsp+68h+var_38], 0E0h
0x1800161cb  jmp     short loc_1800161D5
0x1800161cd  mov     dword ptr [rsp+68h+var_38], 0C0h
0x1800161d5  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800161dc  mov     qword ptr [rsp+68h+dwFlags], r8
0x1800161e1  mov     dword ptr [rsp+68h+pcbResult], ebx
0x1800161e5  mov     rcx, [rcx+10h]
0x1800161e9  lea     r9, aStatus; "Status"
0x1800161f0  call    WPP_SF_sDsd
0x1800161f5  jmp     loc_18001613A
0x1800161fa  mov     r9d, 0B2h
0x180016200  jmp     loc_180016106
0x180016205  mov     r9d, 0D5h
0x18001620b  jmp     loc_180016106
```
