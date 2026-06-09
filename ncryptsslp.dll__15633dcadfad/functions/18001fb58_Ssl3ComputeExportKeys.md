# Ssl3ComputeExportKeys

- ea: `0x18001fb58`
- end: `0x18001fd89`
- name: `Ssl3ComputeExportKeys`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180006b60`

## callees

- `0x180009160`
- `0x18000b654`
- `0x180018ac0`
- `0x18001fb58`
- `0x180024ef0`
- `0x180024fb0`
- `0x180026010`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18001fcd0`
- `bcrypt!BCryptHashData` at `0x18001fcf2`
- `bcrypt!BCryptHashData` at `0x18001fcd0`
- `bcrypt!BCryptHashData` at `0x18001fcf2`
- `bcrypt!BCryptCreateHash` at `0x18001fca5`
- `bcrypt!BCryptCreateHash` at `0x18001fca5`
- `bcrypt!BCryptFinishHash` at `0x18001fd15`
- `bcrypt!BCryptFinishHash` at `0x18001fd15`
- `bcrypt!BCryptDestroyHash` at `0x18001fd47`
- `bcrypt!BCryptDestroyHash` at `0x18001fd47`

## string_xrefs

- `0x18001fbb2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\ssl3key.c`

## pseudocode

```c
__int64 __fastcall Ssl3ComputeExportKeys(
        __int64 a1,
        UCHAR *a2,
        ULONG a3,
        UCHAR *a4,
        __int64 a5,
        void *a6,
        unsigned int Size)
{
  UCHAR *p_phHash; // rdi
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  UCHAR *v21; // rax
  NTSTATUS v22; // eax
  __int64 v24; // [rsp+0h] [rbp-40h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp+0h] BYREF
  __int64 v26; // [rsp+48h] [rbp+8h] BYREF
  UCHAR pbOutput[16]; // [rsp+50h] [rbp+10h] BYREF

  p_phHash = 0;
  phHash = 0;
  if ( Size > 0x10 )
  {
    v12 = -2146893783;
    v13 = 1318;
    v14 = 2148073513LL;
LABEL_3:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\ssl3key.c", v13);
    goto LABEL_28;
  }
  v15 = *(unsigned int *)(a1 + 320);
  if ( !*(_DWORD *)(a1 + 320) )
    goto LABEL_36;
  if ( v15 > g_ulMaxStackAllocSize )
    goto LABEL_36;
  v16 = v15 + g_ulAdditionalProbeSize + 8;
  if ( v16 < v15 || !(unsigned int)VerifyStackAvailable(v16) )
    goto LABEL_36;
  v17 = v15 + 23;
  if ( v15 + 23 <= v15 + 8 )
    v17 = 0xFFFFFFFFFFFFFF0LL;
  v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
  v19 = alloca(v18);
  v20 = alloca(v18);
  p_phHash = (UCHAR *)&phHash;
  if ( &v24 == (__int64 *)-64LL || (LODWORD(phHash) = 1801679955, (p_phHash = (UCHAR *)&v26) == 0) )
  {
LABEL_36:
    if ( v15 + 8 >= v15 )
    {
      v21 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      p_phHash = v21;
      if ( v21 )
      {
        *(_DWORD *)v21 = 1885431112;
        p_phHash = v21 + 8;
      }
    }
  }
  if ( !p_phHash )
  {
    v12 = -2146893810;
    v13 = 1334;
    v14 = 2148073486LL;
    goto LABEL_3;
  }
  v22 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)(a1 + 304), &phHash, p_phHash, *(_DWORD *)(a1 + 320), 0, 0, 0);
  v12 = v22;
  if ( v22 < 0 )
  {
    v13 = 1352;
LABEL_19:
    v14 = (unsigned int)v22;
    goto LABEL_3;
  }
  if ( a2 )
  {
    v22 = BCryptHashData(phHash, a2, a3, 0);
    v12 = v22;
    if ( v22 < 0 )
    {
      v13 = 1361;
      goto LABEL_19;
    }
  }
  v22 = BCryptHashData(phHash, a4, 0x40u, 0);
  v12 = v22;
  if ( v22 < 0 )
  {
    v13 = 1369;
    goto LABEL_19;
  }
  v22 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0);
  v12 = v22;
  if ( v22 < 0 )
  {
    v13 = 1376;
    goto LABEL_19;
  }
  memmove(a6, pbOutput, Size);
  v12 = 0;
LABEL_28:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( p_phHash && *((_DWORD *)p_phHash - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return v12;
}

```

## disassembly

```asm
0x18001fb58  push    rbp
0x18001fb5a  push    rbx
0x18001fb5b  push    rsi
0x18001fb5c  push    rdi
0x18001fb5d  push    r12
0x18001fb5f  push    r13
0x18001fb61  push    r14
0x18001fb63  push    r15
0x18001fb65  sub     rsp, 78h
0x18001fb69  lea     rbp, [rsp+40h]
0x18001fb6e  mov     rax, cs:__security_cookie
0x18001fb75  xor     rax, rbp
0x18001fb78  mov     [rbp+70h+var_50], rax
0x18001fb7c  mov     r15, [rbp+70h+arg_28]
0x18001fb83  xor     edi, edi
0x18001fb85  cmp     dword ptr [rbp+70h+Size], 10h
0x18001fb8c  mov     r12, r9
0x18001fb8f  mov     r13d, r8d
0x18001fb92  mov     [rbp+70h+phHash], 0
0x18001fb9a  mov     r14, rdx
0x18001fb9d  mov     rsi, rcx
0x18001fba0  jbe     short loc_18001FBCA
0x18001fba2  mov     ebx, 80090029h
0x18001fba7  mov     r9d, 526h
0x18001fbad  mov     ecx, 80090029h
0x18001fbb2  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001fbb9  lea     rdx, aStatus; "Status"
0x18001fbc0  call    DebugTraceError
0x18001fbc5  jmp     loc_18001FD3E
0x18001fbca  mov     ebx, [rcx+140h]
0x18001fbd0  test    rbx, rbx
0x18001fbd3  jz      short loc_18001FC36
0x18001fbd5  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18001fbdc  ja      short loc_18001FC36
0x18001fbde  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001fbe5  add     rcx, 8
0x18001fbe9  add     rcx, rbx
0x18001fbec  cmp     rcx, rbx
0x18001fbef  jb      short loc_18001FC36
0x18001fbf1  call    VerifyStackAvailable
0x18001fbf6  test    eax, eax
0x18001fbf8  jz      short loc_18001FC36
0x18001fbfa  lea     rax, [rbx+8]
0x18001fbfe  lea     rcx, [rax+0Fh]
0x18001fc02  cmp     rcx, rax
0x18001fc05  ja      short loc_18001FC11
0x18001fc07  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001fc11  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001fc15  mov     rax, rcx
0x18001fc18  call    _alloca_probe
0x18001fc1d  sub     rsp, rcx
0x18001fc20  lea     rdi, [rsp+0B0h+phHash]
0x18001fc25  test    rdi, rdi
0x18001fc28  jz      short loc_18001FC36
0x18001fc2a  mov     dword ptr [rdi], 6B637453h
0x18001fc30  add     rdi, 8
0x18001fc34  jnz     short loc_18001FC5D
0x18001fc36  lea     rcx, [rbx+8]
0x18001fc3a  cmp     rcx, rbx
0x18001fc3d  jb      short loc_18001FC5D
0x18001fc3f  mov     rax, cs:g_pfnAllocate
0x18001fc46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc4b  mov     rdi, rax
0x18001fc4e  test    rax, rax
0x18001fc51  jz      short loc_18001FC5D
0x18001fc53  mov     dword ptr [rax], 70616548h
0x18001fc59  add     rdi, 8
0x18001fc5d  test    rdi, rdi
0x18001fc60  jnz     short loc_18001FC77
0x18001fc62  mov     ebx, 8009000Eh
0x18001fc67  mov     r9d, 536h
0x18001fc6d  mov     ecx, 8009000Eh
0x18001fc72  jmp     loc_18001FBB2
0x18001fc77  mov     r9d, [rsi+140h]; cbHashObject
0x18001fc7e  lea     rdx, [rbp+70h+phHash]; phHash
0x18001fc82  mov     rcx, [rsi+130h]; hAlgorithm
0x18001fc89  mov     r8, rdi; pbHashObject
0x18001fc8c  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x18001fc94  mov     [rsp+0B0h+cbSecret], 0; cbSecret
0x18001fc9c  mov     [rsp+0B0h+pbSecret], 0; pbSecret
0x18001fca5  call    cs:__imp_BCryptCreateHash
0x18001fcab  mov     ebx, eax
0x18001fcad  test    eax, eax
0x18001fcaf  jns     short loc_18001FCBE
0x18001fcb1  mov     r9d, 548h
0x18001fcb7  mov     ecx, eax
0x18001fcb9  jmp     loc_18001FBB2
0x18001fcbe  test    r14, r14
0x18001fcc1  jz      short loc_18001FCE4
0x18001fcc3  mov     rcx, [rbp+70h+phHash]; hHash
0x18001fcc7  xor     r9d, r9d; dwFlags
0x18001fcca  mov     r8d, r13d; cbInput
0x18001fccd  mov     rdx, r14; pbInput
0x18001fcd0  call    cs:__imp_BCryptHashData
0x18001fcd6  mov     ebx, eax
0x18001fcd8  test    eax, eax
0x18001fcda  jns     short loc_18001FCE4
0x18001fcdc  mov     r9d, 551h
0x18001fce2  jmp     short loc_18001FCB7
0x18001fce4  mov     rcx, [rbp+70h+phHash]; hHash
0x18001fce8  xor     r9d, r9d; dwFlags
0x18001fceb  mov     rdx, r12; pbInput
0x18001fcee  lea     r8d, [r9+40h]; cbInput
0x18001fcf2  call    cs:__imp_BCryptHashData
0x18001fcf8  mov     ebx, eax
0x18001fcfa  test    eax, eax
0x18001fcfc  jns     short loc_18001FD06
0x18001fcfe  mov     r9d, 559h
0x18001fd04  jmp     short loc_18001FCB7
0x18001fd06  mov     rcx, [rbp+70h+phHash]; hHash
0x18001fd0a  lea     rdx, [rbp+70h+pbOutput]; pbOutput
0x18001fd0e  xor     r9d, r9d; dwFlags
0x18001fd11  lea     r8d, [r9+10h]; cbOutput
0x18001fd15  call    cs:__imp_BCryptFinishHash
0x18001fd1b  mov     ebx, eax
0x18001fd1d  test    eax, eax
0x18001fd1f  jns     short loc_18001FD29
0x18001fd21  mov     r9d, 560h
0x18001fd27  jmp     short loc_18001FCB7
0x18001fd29  mov     r8d, dword ptr [rbp+70h+Size]; Size
0x18001fd30  lea     rdx, [rbp+70h+pbOutput]; Src
0x18001fd34  mov     rcx, r15; void *
0x18001fd37  call    memmove
0x18001fd3c  xor     ebx, ebx
0x18001fd3e  mov     rcx, [rbp+70h+phHash]; hHash
0x18001fd42  test    rcx, rcx
0x18001fd45  jz      short loc_18001FD4D
0x18001fd47  call    cs:__imp_BCryptDestroyHash
0x18001fd4d  test    rdi, rdi
0x18001fd50  jz      short loc_18001FD6A
0x18001fd52  lea     rcx, [rdi-8]
0x18001fd56  cmp     dword ptr [rcx], 70616548h
0x18001fd5c  jnz     short loc_18001FD6A
0x18001fd5e  mov     rax, cs:g_pfnFree
0x18001fd65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd6a  mov     eax, ebx
0x18001fd6c  mov     rcx, [rbp+70h+var_50]
0x18001fd70  xor     rcx, rbp; StackCookie
0x18001fd73  call    __security_check_cookie
0x18001fd78  lea     rsp, [rbp+38h]
0x18001fd7c  pop     r15
0x18001fd7e  pop     r14
0x18001fd80  pop     r13
0x18001fd82  pop     r12
0x18001fd84  pop     rdi
0x18001fd85  pop     rsi
0x18001fd86  pop     rbx
0x18001fd87  pop     rbp
0x18001fd88  retn
```
