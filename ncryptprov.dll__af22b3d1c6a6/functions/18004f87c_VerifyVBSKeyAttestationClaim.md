# VerifyVBSKeyAttestationClaim

- ea: `0x18004f87c`
- end: `0x18004fb40`
- name: `VerifyVBSKeyAttestationClaim`
- size: `708`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE, NCRYPT_HANDLE, NCRYPT_HANDLE, int, __int64, __int64, size_t Size, __int64, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046230`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x180038970`
- `0x18004f5c4`
- `0x18004f87c`
- `0x18004fb48`
- `0x18004ff08`
- `0x1800602a4`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x18004fafa`
- `bcrypt!BCryptDestroyKey` at `0x18004fb0f`
- `bcrypt!BCryptDestroyKey` at `0x18004fafa`
- `bcrypt!BCryptDestroyKey` at `0x18004fb0f`

## string_xrefs

- `0x18004f9b4`: `onecore\ds\security\cryptoapi\ncrypt\storage\verifyclaim.c`
- `0x18004fa96`: `onecore\ds\security\cryptoapi\ncrypt\storage\verifyclaim.c`
- `0x18004fade`: `onecore\ds\security\cryptoapi\ncrypt\storage\verifyclaim.c`

## pseudocode

```c
__int64 __fastcall VerifyVBSKeyAttestationClaim(
        NCRYPT_HANDLE a1,
        NCRYPT_HANDLE a2,
        NCRYPT_HANDLE a3,
        int a4,
        __int64 a5,
        __int64 a6,
        size_t Size,
        __int64 a8,
        int a9)
{
  __int64 v12; // r9
  int v13; // ebx
  size_t v14; // r12
  UCHAR *v15; // rax
  UCHAR *v16; // rsi
  int v17; // ebx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // r9
  __int64 v21; // rcx
  int v22; // ebx
  _OWORD *v23; // rdi
  __int64 v24; // r14
  _OWORD *v25; // rax
  int v26; // eax
  __int64 v27; // r9
  __int64 v28; // rcx
  __int64 v29; // rcx
  BCRYPT_KEY_HANDLE hKey; // [rsp+30h] [rbp-10h] BYREF
  BCRYPT_KEY_HANDLE v32; // [rsp+38h] [rbp-8h] BYREF
  int v34; // [rsp+98h] [rbp+58h] BYREF

  hKey = 0;
  v32 = 0;
  if ( (unsigned int)(a4 - 5) > 1 )
  {
    v12 = 1298;
LABEL_43:
    v17 = -1073741811;
    v18 = 3221225485LL;
    goto LABEL_44;
  }
  if ( !a2 || !a3 && a4 != 5 || (v13 = a6, !a6) || (v14 = (unsigned int)Size, !(_DWORD)Size) || a5 )
  {
    v12 = 1310;
    goto LABEL_43;
  }
  v34 = Size;
  v15 = (UCHAR *)SafeAllocaAllocateFromHeap((unsigned int)Size);
  v16 = v15;
  if ( v15 )
  {
    memset_0(v15, 0, v14);
    v19 = VBSAttestationDeserializeAttestationStatement(v13, v14, a4, (_DWORD)v16, (__int64)&v34);
    v17 = v19;
    if ( v19 < 0 )
    {
      v20 = 1354;
LABEL_13:
      v21 = (unsigned int)v19;
LABEL_19:
      DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\verifyclaim.c", v20);
LABEL_41:
      MSCryptFree(v16);
      goto LABEL_45;
    }
    v19 = VBSAttestationPrepareHandles(a1, a2, a3, &hKey, &v32);
    v17 = v19;
    if ( v19 < 0 )
    {
      v20 = 1368;
      goto LABEL_13;
    }
    v22 = a9;
    v23 = 0;
    v24 = a8;
    if ( a9 )
    {
      if ( a9 != 0x100000 )
      {
        v17 = -2146893815;
        v20 = 1379;
        v21 = 2148073481LL;
        goto LABEL_19;
      }
      if ( !a8 )
      {
        v17 = -1073741811;
        v20 = 1387;
        v21 = 3221225485LL;
        goto LABEL_19;
      }
      v25 = (_OWORD *)SafeAllocaAllocateFromHeap(16);
      v23 = v25;
      if ( !v25 )
      {
        v17 = -1073741801;
        v20 = 1396;
        v21 = 3221225495LL;
        goto LABEL_19;
      }
      *v25 = 0;
    }
    if ( a4 == 5 )
    {
      v26 = VerifyVBSKeyAttestationRootClaim(v16 + 12, hKey, v32, (unsigned int)v14, v23, v22);
      v17 = v26;
      if ( v26 < 0 )
      {
        v27 = 1415;
LABEL_28:
        v28 = (unsigned int)v26;
LABEL_36:
        DebugTraceError(v28, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\verifyclaim.c", v27);
LABEL_37:
        if ( v23 )
        {
          v29 = *((_QWORD *)v23 + 1);
          if ( v29 )
            MSCryptFree(v29);
          MSCryptFree(v23);
        }
        goto LABEL_41;
      }
    }
    else
    {
      if ( a4 != 6 )
      {
        v17 = -1073741811;
        v27 = 1437;
        v28 = 3221225485LL;
        goto LABEL_36;
      }
      v26 = VerifyVBSKeyAttestationIdentityClaim(v16 + 12, v22);
      v17 = v26;
      if ( v26 < 0 )
      {
        v27 = 1430;
        goto LABEL_28;
      }
    }
    if ( !v17 )
    {
      if ( v23 )
      {
        *(_DWORD *)v24 = 0;
        *(_DWORD *)(v24 + 4) = 1;
        *(_QWORD *)(v24 + 8) = v23;
      }
      goto LABEL_41;
    }
    goto LABEL_37;
  }
  v17 = -1073741801;
  v12 = 1326;
  v18 = 3221225495LL;
LABEL_44:
  DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\verifyclaim.c", v12);
LABEL_45:
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( v32 )
    BCryptDestroyKey(v32);
  return (v17 | 0x10000000) & (unsigned int)-(v17 != 0);
}

```

## disassembly

```asm
0x18004f87c  mov     [rsp-38h+arg_8], rbx
0x18004f881  mov     [rsp-38h+hObject], rcx
0x18004f886  push    rbp
0x18004f887  push    rsi
0x18004f888  push    rdi
0x18004f889  push    r12
0x18004f88b  push    r13
0x18004f88d  push    r14
0x18004f88f  push    r15
0x18004f891  mov     rbp, rsp
0x18004f894  sub     rsp, 40h
0x18004f898  lea     eax, [r9-5]
0x18004f89c  mov     [rbp+hKey], 0
0x18004f8a4  mov     [rbp+var_8], 0
0x18004f8ac  mov     r15d, r9d
0x18004f8af  mov     r14, r8
0x18004f8b2  mov     rdi, rdx
0x18004f8b5  cmp     eax, 1
0x18004f8b8  jbe     short loc_18004F8C5
0x18004f8ba  mov     r9d, 512h
0x18004f8c0  jmp     loc_18004FAD4
0x18004f8c5  test    rdi, rdi
0x18004f8c8  jz      loc_18004FACE
0x18004f8ce  test    r14, r14
0x18004f8d1  jnz     short loc_18004F8DD
0x18004f8d3  cmp     r15d, 5
0x18004f8d7  jnz     loc_18004FACE
0x18004f8dd  mov     rbx, [rbp+arg_28]
0x18004f8e1  test    rbx, rbx
0x18004f8e4  jz      loc_18004FACE
0x18004f8ea  mov     r12d, dword ptr [rbp+Size]
0x18004f8ee  test    r12d, r12d
0x18004f8f1  jz      loc_18004FACE
0x18004f8f7  cmp     [rbp+arg_20], 0
0x18004f8fc  jnz     loc_18004FACE
0x18004f902  mov     ecx, r12d
0x18004f905  mov     [rbp+arg_18], r12d
0x18004f909  call    SafeAllocaAllocateFromHeap
0x18004f90e  mov     rsi, rax
0x18004f911  test    rax, rax
0x18004f914  jnz     short loc_18004F92B
0x18004f916  mov     ebx, 0C0000017h
0x18004f91b  mov     r9d, 52Eh
0x18004f921  mov     ecx, 0C0000017h
0x18004f926  jmp     loc_18004FADE
0x18004f92b  mov     r8, r12; Size
0x18004f92e  xor     edx, edx; Val
0x18004f930  mov     rcx, rsi; void *
0x18004f933  call    memset_0
0x18004f938  lea     rax, [rbp+arg_18]
0x18004f93c  mov     r9, rsi
0x18004f93f  mov     r8d, r15d
0x18004f942  mov     [rsp+40h+var_20], rax
0x18004f947  mov     edx, r12d
0x18004f94a  mov     rcx, rbx
0x18004f94d  call    VBSAttestationDeserializeAttestationStatement
0x18004f952  mov     ebx, eax
0x18004f954  test    eax, eax
0x18004f956  jns     short loc_18004F962
0x18004f958  mov     r9d, 54Ah
0x18004f95e  mov     ecx, eax
0x18004f960  jmp     short loc_18004F9B4
0x18004f962  mov     rcx, [rbp+hObject]; hObject
0x18004f966  lea     rax, [rbp+var_8]
0x18004f96a  lea     r9, [rbp+hKey]; phKey
0x18004f96e  mov     [rsp+40h+var_20], rax; BCRYPT_KEY_HANDLE *
0x18004f973  mov     r8, r14; NCRYPT_HANDLE
0x18004f976  mov     rdx, rdi; NCRYPT_HANDLE
0x18004f979  call    VBSAttestationPrepareHandles
0x18004f97e  mov     ebx, eax
0x18004f980  test    eax, eax
0x18004f982  jns     short loc_18004F98C
0x18004f984  mov     r9d, 558h
0x18004f98a  jmp     short loc_18004F95E
0x18004f98c  mov     ebx, [rbp+arg_40]
0x18004f992  xor     edi, edi
0x18004f994  mov     r14, [rbp+arg_38]
0x18004f998  test    ebx, ebx
0x18004f99a  jz      short loc_18004FA0D
0x18004f99c  cmp     ebx, 100000h
0x18004f9a2  jz      short loc_18004F9CC
0x18004f9a4  mov     ebx, 80090009h
0x18004f9a9  mov     r9d, 563h
0x18004f9af  mov     ecx, 80090009h
0x18004f9b4  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004f9bb  lea     rdx, aStatus; "Status"
0x18004f9c2  call    DebugTraceError
0x18004f9c7  jmp     loc_18004FAC4
0x18004f9cc  test    r14, r14
0x18004f9cf  jnz     short loc_18004F9E3
0x18004f9d1  mov     ebx, 0C000000Dh
0x18004f9d6  mov     r9d, 56Bh
0x18004f9dc  mov     ecx, 0C000000Dh
0x18004f9e1  jmp     short loc_18004F9B4
0x18004f9e3  mov     ecx, 10h
0x18004f9e8  call    SafeAllocaAllocateFromHeap
0x18004f9ed  mov     rdi, rax
0x18004f9f0  test    rax, rax
0x18004f9f3  jnz     short loc_18004FA07
0x18004f9f5  mov     ebx, 0C0000017h
0x18004f9fa  mov     r9d, 574h
0x18004fa00  mov     ecx, 0C0000017h
0x18004fa05  jmp     short loc_18004F9B4
0x18004fa07  xorps   xmm0, xmm0
0x18004fa0a  movups  xmmword ptr [rax], xmm0
0x18004fa0d  cmp     r15d, 5
0x18004fa11  jnz     short loc_18004FA40
0x18004fa13  mov     r8, [rbp+var_8]
0x18004fa17  lea     rcx, [rsi+0Ch]
0x18004fa1b  mov     rdx, [rbp+hKey]
0x18004fa1f  mov     r9d, r12d
0x18004fa22  mov     [rsp+40h+var_18], ebx
0x18004fa26  mov     [rsp+40h+var_20], rdi
0x18004fa2b  call    VerifyVBSKeyAttestationRootClaim
0x18004fa30  mov     ebx, eax
0x18004fa32  test    eax, eax
0x18004fa34  jns     short loc_18004FA6C
0x18004fa36  mov     r9d, 587h
0x18004fa3c  mov     ecx, eax
0x18004fa3e  jmp     short loc_18004FA96
0x18004fa40  cmp     r15d, 6
0x18004fa44  jnz     short loc_18004FA86
0x18004fa46  mov     r8, [rbp+var_8]
0x18004fa4a  lea     rcx, [rsi+0Ch]; pbInput
0x18004fa4e  mov     rdx, [rbp+hKey]
0x18004fa52  mov     r9, rdi
0x18004fa55  mov     dword ptr [rsp+40h+var_20], ebx; int
0x18004fa59  call    VerifyVBSKeyAttestationIdentityClaim
0x18004fa5e  mov     ebx, eax
0x18004fa60  test    eax, eax
0x18004fa62  jns     short loc_18004FA6C
0x18004fa64  mov     r9d, 596h
0x18004fa6a  jmp     short loc_18004FA3C
0x18004fa6c  test    ebx, ebx
0x18004fa6e  jnz     short loc_18004FAA9
0x18004fa70  test    rdi, rdi
0x18004fa73  jz      short loc_18004FAC4
0x18004fa75  mov     [r14], ebx
0x18004fa78  mov     dword ptr [r14+4], 1
0x18004fa80  mov     [r14+8], rdi
0x18004fa84  jmp     short loc_18004FAC4
0x18004fa86  mov     ebx, 0C000000Dh
0x18004fa8b  mov     r9d, 59Dh
0x18004fa91  mov     ecx, 0C000000Dh
0x18004fa96  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004fa9d  lea     rdx, aStatus; "Status"
0x18004faa4  call    DebugTraceError
0x18004faa9  test    rdi, rdi
0x18004faac  jz      short loc_18004FAC4
0x18004faae  mov     rcx, [rdi+8]
0x18004fab2  test    rcx, rcx
0x18004fab5  jz      short loc_18004FABC
0x18004fab7  call    MSCryptFree
0x18004fabc  mov     rcx, rdi
0x18004fabf  call    MSCryptFree
0x18004fac4  mov     rcx, rsi
0x18004fac7  call    MSCryptFree
0x18004facc  jmp     short loc_18004FAF1
0x18004face  mov     r9d, 51Eh
0x18004fad4  mov     ebx, 0C000000Dh
0x18004fad9  mov     ecx, 0C000000Dh
0x18004fade  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004fae5  lea     rdx, aStatus; "Status"
0x18004faec  call    DebugTraceError
0x18004faf1  mov     rcx, [rbp+hKey]; hKey
0x18004faf5  test    rcx, rcx
0x18004faf8  jz      short loc_18004FB06
0x18004fafa  call    cs:__imp_BCryptDestroyKey
0x18004fb01  nop     dword ptr [rax+rax+00h]
0x18004fb06  mov     rcx, [rbp+var_8]; hKey
0x18004fb0a  test    rcx, rcx
0x18004fb0d  jz      short loc_18004FB1B
0x18004fb0f  call    cs:__imp_BCryptDestroyKey
0x18004fb16  nop     dword ptr [rax+rax+00h]
0x18004fb1b  mov     ecx, ebx
0x18004fb1d  bts     ecx, 1Ch
0x18004fb21  neg     ebx
0x18004fb23  mov     rbx, [rsp+40h+arg_8]
0x18004fb2b  sbb     eax, eax
0x18004fb2d  and     eax, ecx
0x18004fb2f  add     rsp, 40h
0x18004fb33  pop     r15
0x18004fb35  pop     r14
0x18004fb37  pop     r13
0x18004fb39  pop     r12
0x18004fb3b  pop     rdi
0x18004fb3c  pop     rsi
0x18004fb3d  pop     rbp
0x18004fb3e  retn
```
