# _ConvertGroupOfDaclAces

- ea: `0x180024b90`
- end: `0x180024db3`
- name: `_ConvertGroupOfDaclAces`
- size: `547`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1800247e4`

## callees

- `0x1800136f0`
- `0x18001722c`
- `0x180021b30`
- `0x180021b5c`
- `0x180021c24`
- `0x1800241c8`
- `0x180024344`
- `0x180024b90`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x180024c8f`
- `ADVAPI32!EqualSid` at `0x180024c8f`
- `ADVAPI32!GetAce` at `0x180024c23`
- `ADVAPI32!GetAce` at `0x180024c75`
- `ADVAPI32!GetAce` at `0x180024c23`
- `ADVAPI32!GetAce` at `0x180024c75`
- `KERNEL32!GetLastError` at `0x180024d2d`
- `KERNEL32!GetLastError` at `0x180024d59`
- `KERNEL32!GetLastError` at `0x180024d2d`
- `KERNEL32!GetLastError` at `0x180024d59`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConvertGroupOfDaclAces(unsigned int a1, struct _ACL *a2, DWORD a3, DWORD a4, struct _ACL *a5)
{
  struct _ACL *v7; // r14
  DWORD v8; // edi
  DWORD v9; // edi
  int v10; // esi
  struct _SID **v11; // r15
  DWORD v12; // ebx
  DWORD v13; // r14d
  __int64 v14; // rdx
  unsigned int v15; // r15d
  bool v16; // cc
  DWORD LastError; // eax
  __int64 v19; // rdx
  __int64 v20; // r9
  unsigned int v21; // [rsp+40h] [rbp-30h] BYREF
  LPVOID pAce; // [rsp+48h] [rbp-28h] BYREF
  PSID pSid1; // [rsp+50h] [rbp-20h]
  struct _SID **v24; // [rsp+58h] [rbp-18h]
  _BYTE v25[16]; // [rsp+60h] [rbp-10h] BYREF
  char v28; // [rsp+C8h] [rbp+58h]

  v7 = a2;
  v8 = a4 + 1;
  if ( a4 == -1 || v8 < a3 )
    return 2147942934LL;
  v9 = v8 - a3;
  v10 = 0;
  while ( 2 )
  {
    v11 = (struct _SID **)MmAllocate(saturated_mul(v9, 8u));
    v24 = v11;
    aPtrs<_SID>::aPtrs<_SID>(v25, v11, v9);
    v21 = 0;
    v12 = a3;
    do
    {
      pAce = 0;
      if ( !GetAce(v7, v12, &pAce) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        {
          LastError = GetLastError();
          v19 = 29;
          v20 = v12;
LABEL_26:
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            v19,
            WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
            v20,
            LastError);
        }
LABEL_27:
        aPtrs<_SID>::~aPtrs<_SID>(v25);
        return 3222146058LL;
      }
      v13 = v12 + 1;
      if ( (unsigned int)IsNewSid((char *)pAce + 8, v11, &v21) )
      {
        v28 = *(_BYTE *)pAce;
        pSid1 = (char *)pAce + 8;
        v15 = *((_DWORD *)pAce + 1);
        while ( 1 )
        {
          if ( v12 > a4 )
          {
            LOBYTE(v14) = v28;
            if ( v10 )
              BuildNt5ObjAce(a1, v28, 0, 0, pSid1, v15, a5);
            else
              BuildNt5Ace(a1, v14, (__int64)pSid1, v15, a5);
            v11 = v24;
            goto LABEL_17;
          }
          if ( !GetAce(a2, v12, &pAce) )
            break;
          if ( EqualSid(pSid1, (char *)pAce + 8) )
            v15 |= *((_DWORD *)pAce + 1);
          ++v12;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        {
          LastError = GetLastError();
          v19 = 30;
          v20 = v13;
          goto LABEL_26;
        }
        goto LABEL_27;
      }
LABEL_17:
      v12 = v13;
      v16 = v13 <= a4;
      v7 = a2;
    }
    while ( v16 );
    aPtrs<_SID>::~aPtrs<_SID>(v25);
    v10 ^= 1u;
    if ( v10 )
      continue;
    return 0;
  }
}

```

## disassembly

```asm
0x180024b90  mov     [rsp-38h+arg_10], rbx
0x180024b95  mov     [rsp-38h+pAcl], rdx
0x180024b9a  mov     [rsp-38h+arg_0], ecx
0x180024b9e  push    rbp
0x180024b9f  push    rsi
0x180024ba0  push    rdi
0x180024ba1  push    r12
0x180024ba3  push    r13
0x180024ba5  push    r14
0x180024ba7  push    r15
0x180024ba9  mov     rbp, rsp
0x180024bac  sub     rsp, 70h
0x180024bb0  mov     r13d, r9d
0x180024bb3  mov     r12d, r8d
0x180024bb6  mov     r14, rdx
0x180024bb9  lea     edi, [r9+1]
0x180024bbd  cmp     edi, 1
0x180024bc0  jb      loc_180024D96
0x180024bc6  cmp     edi, r8d
0x180024bc9  jb      loc_180024D96
0x180024bcf  sub     edi, r8d
0x180024bd2  xor     esi, esi
0x180024bd4  mov     ecx, edi
0x180024bd6  mov     eax, 8
0x180024bdb  mul     rcx
0x180024bde  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180024be5  cmovb   rax, rcx
0x180024be9  mov     rcx, rax; unsigned __int64
0x180024bec  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180024bf1  mov     r15, rax
0x180024bf4  mov     [rbp+var_18], rax
0x180024bf8  mov     r8d, edi
0x180024bfb  mov     rdx, rax
0x180024bfe  lea     rcx, [rbp+var_10]
0x180024c02  call    ??0?$aPtrs@U_SID@@@@QEAA@PEAPEAU_SID@@K@Z; aPtrs<_SID>::aPtrs<_SID>(_SID * *,ulong)
0x180024c07  nop
0x180024c08  mov     [rbp+var_30], 0
0x180024c0f  mov     ebx, r12d
0x180024c12  mov     [rbp+pAce], 0
0x180024c1a  lea     r8, [rbp+pAce]; pAce
0x180024c1e  mov     edx, ebx; dwAceIndex
0x180024c20  mov     rcx, r14; pAcl
0x180024c23  call    cs:__imp_GetAce
0x180024c29  test    eax, eax
0x180024c2b  jz      loc_180024D3D
0x180024c31  lea     r14d, [rbx+1]
0x180024c35  mov     rcx, [rbp+pAce]
0x180024c39  add     rcx, 8; pSourceSid
0x180024c3d  lea     r8, [rbp+var_30]; unsigned int *
0x180024c41  mov     rdx, r15; struct _SID **
0x180024c44  call    ?IsNewSid@@YAHPEAXPEAPEAU_SID@@PEAK@Z; IsNewSid(void *,_SID * *,ulong *)
0x180024c49  test    eax, eax
0x180024c4b  jz      loc_180024CE8
0x180024c51  mov     rax, [rbp+pAce]
0x180024c55  mov     dl, [rax]
0x180024c57  mov     byte ptr [rbp+arg_18], dl
0x180024c5a  lea     rcx, [rax+8]
0x180024c5e  mov     [rbp+pSid1], rcx
0x180024c62  mov     r15d, [rax+4]
0x180024c66  cmp     ebx, r13d
0x180024c69  ja      short loc_180024CA5
0x180024c6b  lea     r8, [rbp+pAce]; pAce
0x180024c6f  mov     edx, ebx; dwAceIndex
0x180024c71  mov     rcx, [rbp+pAcl]; pAcl
0x180024c75  call    cs:__imp_GetAce
0x180024c7b  test    eax, eax
0x180024c7d  jz      loc_180024D11
0x180024c83  mov     rdx, [rbp+pAce]
0x180024c87  add     rdx, 8; pSid2
0x180024c8b  mov     rcx, [rbp+pSid1]; pSid1
0x180024c8f  call    cs:__imp_EqualSid
0x180024c95  test    eax, eax
0x180024c97  jz      short loc_180024CA1
0x180024c99  mov     rax, [rbp+pAce]
0x180024c9d  or      r15d, [rax+4]
0x180024ca1  inc     ebx
0x180024ca3  jmp     short loc_180024C66
0x180024ca5  mov     rax, [rbp+arg_20]
0x180024ca9  mov     dl, byte ptr [rbp+arg_18]; int
0x180024cac  mov     ecx, [rbp+arg_0]; int
0x180024caf  test    esi, esi
0x180024cb1  jz      short loc_180024CD3
0x180024cb3  mov     [rsp+70h+var_40], rax
0x180024cb8  mov     [rsp+70h+var_48], r15d
0x180024cbd  mov     rax, [rbp+pSid1]
0x180024cc1  mov     [rsp+70h+var_50], rax
0x180024cc6  xor     r9d, r9d
0x180024cc9  xor     r8d, r8d
0x180024ccc  call    _BuildNt5ObjAce
0x180024cd1  jmp     short loc_180024CE4
0x180024cd3  mov     [rsp+70h+var_50], rax; pAcl
0x180024cd8  mov     r9d, r15d; int
0x180024cdb  mov     r8, [rbp+pSid1]; int
0x180024cdf  call    _BuildNt5Ace
0x180024ce4  mov     r15, [rbp+var_18]
0x180024ce8  mov     ebx, r14d
0x180024ceb  cmp     r14d, r13d
0x180024cee  mov     r14, [rbp+pAcl]
0x180024cf2  jbe     loc_180024C12
0x180024cf8  lea     rcx, [rbp+var_10]
0x180024cfc  call    ??1?$aPtrs@U_SID@@@@QEAA@XZ; aPtrs<_SID>::~aPtrs<_SID>(void)
0x180024d01  xor     esi, 1
0x180024d04  jnz     loc_180024BD4
0x180024d0a  xor     eax, eax
0x180024d0c  jmp     loc_180024D9B
0x180024d11  lea     rax, WPP_GLOBAL_Control
0x180024d18  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d1f  cmp     rcx, rax
0x180024d22  jz      short loc_180024D86
0x180024d24  test    byte ptr [rcx+10Ch], 1
0x180024d2b  jz      short loc_180024D86
0x180024d2d  call    cs:__imp_GetLastError
0x180024d33  mov     edx, 1Eh
0x180024d38  mov     r9d, r14d
0x180024d3b  jmp     short loc_180024D67
0x180024d3d  lea     rax, WPP_GLOBAL_Control
0x180024d44  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d4b  cmp     rcx, rax
0x180024d4e  jz      short loc_180024D86
0x180024d50  test    byte ptr [rcx+10Ch], 1
0x180024d57  jz      short loc_180024D86
0x180024d59  call    cs:__imp_GetLastError
0x180024d5f  mov     edx, 1Dh
0x180024d64  mov     r9d, ebx
0x180024d67  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d6e  mov     dword ptr [rsp+70h+var_50], eax
0x180024d72  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x180024d79  mov     rcx, [rcx+100h]
0x180024d80  call    WPP_SF_dd
0x180024d85  nop
0x180024d86  lea     rcx, [rbp+var_10]
0x180024d8a  call    ??1?$aPtrs@U_SID@@@@QEAA@XZ; aPtrs<_SID>::~aPtrs<_SID>(void)
0x180024d8f  mov     eax, 0C00E0C0Ah
0x180024d94  jmp     short loc_180024D9B
0x180024d96  mov     eax, 80070216h
0x180024d9b  mov     rbx, [rsp+70h+arg_10]
0x180024da3  add     rsp, 70h
0x180024da7  pop     r15
0x180024da9  pop     r14
0x180024dab  pop     r13
0x180024dad  pop     r12
0x180024daf  pop     rdi
0x180024db0  pop     rsi
0x180024db1  pop     rbp
0x180024db2  retn
```
