# FDITruncateCabinet

- ea: `0x1800159f0`
- end: `0x180015bc2`
- name: `FDITruncateCabinet`
- size: `466`
- prototype: `BOOL __cdecl(HFDI hfdi, LPSTR pszCabinetName, USHORT iFolderToDelete)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180014dc0`
- `0x1800159f0`
- `0x18001c010`

## pseudocode

```c
BOOL __cdecl FDITruncateCabinet(HFDI hfdi, LPSTR pszCabinetName, USHORT iFolderToDelete)
{
  BOOL v3; // esi
  int v4; // r12d
  __int64 v7; // rax
  __int64 v8; // rdi
  __int16 v9; // ax
  unsigned int v10; // r14d
  unsigned int (__fastcall *v11)(__int64, _QWORD, _QWORD); // rax
  int v12; // [rsp+20h] [rbp-40h] BYREF
  __int64 v13; // [rsp+28h] [rbp-38h] BYREF
  __int128 v14; // [rsp+30h] [rbp-30h] BYREF
  __int128 v15; // [rsp+40h] [rbp-20h]
  int v16; // [rsp+50h] [rbp-10h]

  v3 = 0;
  v4 = iFolderToDelete;
  v12 = 0;
  v13 = 0;
  v16 = 0;
  v14 = 0;
  v15 = 0;
  if ( !hfdi )
    return 0;
  v7 = (*((__int64 (__fastcall **)(LPSTR, __int64, _QWORD))hfdi + 3))(pszCabinetName, 32770, 0);
  v8 = v7;
  if ( v7 != -1 )
  {
    if ( (*((unsigned int (__fastcall **)(__int64, __int128 *, __int64))hfdi + 4))(v7, &v14, 36) == 36
      && (_DWORD)v14 == 1178817357
      && WORD4(v15) == 259
      && WORD5(v15) >= (unsigned __int16)v4 )
    {
      v9 = *((_WORD *)hfdi + 91);
      if ( (v9 & 3) == 0 )
      {
        v10 = 8 * v4 + 36;
        if ( (v9 & 4) == 0 )
        {
LABEL_12:
          if ( (*((unsigned int (__fastcall **)(__int64, _QWORD, _QWORD))hfdi + 7))(v8, v10, 0) != -1
            && (*((unsigned int (__fastcall **)(__int64, __int64 *, __int64))hfdi + 4))(v8, &v13, 8) == 8 )
          {
            DWORD2(v14) = v13;
            v11 = (unsigned int (__fastcall *)(__int64, _QWORD, _QWORD))*((_QWORD *)hfdi + 7);
            WORD5(v15) = v4;
            if ( v11(v8, 0, 0) != -1
              && (*((unsigned int (__fastcall **)(__int64, __int128 *, __int64))hfdi + 5))(v8, &v14, 36) == 36
              && (*((unsigned int (__fastcall **)(__int64, _QWORD, _QWORD))hfdi + 7))(v8, (unsigned int)v13, 0) != -1
              && (*((unsigned int (__fastcall **)(__int64, __int128 *, _QWORD))hfdi + 5))(v8, &v14, 0) != -1 )
            {
              v3 = 1;
            }
          }
          goto LABEL_19;
        }
        if ( (*((unsigned int (__fastcall **)(__int64, int *, __int64))hfdi + 4))(v8, &v12, 4) == 4 )
        {
          v10 = v4 * BYTE2(v12) + 8 * v4 + 40;
          goto LABEL_12;
        }
      }
    }
LABEL_19:
    (*((void (__fastcall **)(__int64))hfdi + 6))(v8);
  }
  return v3;
}

```

## disassembly

```asm
0x1800159f0  push    rbp
0x1800159f2  push    rbx
0x1800159f3  push    rsi
0x1800159f4  push    rdi
0x1800159f5  push    r12
0x1800159f7  push    r14
0x1800159f9  push    r15
0x1800159fb  mov     rbp, rsp
0x1800159fe  sub     rsp, 60h
0x180015a02  mov     rax, cs:__security_cookie
0x180015a09  xor     rax, rsp
0x180015a0c  mov     [rbp+var_8], rax
0x180015a10  xor     esi, esi
0x180015a12  movzx   r12d, r8w
0x180015a16  mov     rbx, rcx
0x180015a19  mov     [rbp+var_40], esi
0x180015a1c  xor     ecx, ecx
0x180015a1e  mov     [rbp+var_38], rsi
0x180015a22  mov     [rbp+var_10], ecx
0x180015a25  xorps   xmm0, xmm0
0x180015a28  mov     rax, rdx
0x180015a2b  movups  [rbp+var_30], xmm0
0x180015a2f  movups  [rbp+var_20], xmm0
0x180015a33  test    rbx, rbx
0x180015a36  jnz     short loc_180015A3F
0x180015a38  xor     eax, eax
0x180015a3a  jmp     loc_180015BA7
0x180015a3f  mov     rcx, rax
0x180015a42  xor     r8d, r8d
0x180015a45  mov     rax, [rbx+18h]
0x180015a49  mov     edx, 8002h
0x180015a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a53  mov     rdi, rax
0x180015a56  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015a5a  jz      loc_180015BA5
0x180015a60  mov     rcx, rax
0x180015a63  lea     rdx, [rbp+var_30]
0x180015a67  mov     rax, [rbx+20h]
0x180015a6b  mov     r8d, 24h ; '$'
0x180015a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a76  cmp     eax, 24h ; '$'
0x180015a79  jnz     loc_180015B99
0x180015a7f  cmp     dword ptr [rbp+var_30], 4643534Dh
0x180015a86  jnz     loc_180015B99
0x180015a8c  mov     eax, 103h
0x180015a91  cmp     word ptr [rbp+var_20+8], ax
0x180015a95  jnz     loc_180015B99
0x180015a9b  cmp     word ptr [rbp+var_20+0Ah], r12w
0x180015aa0  jb      loc_180015B99
0x180015aa6  movzx   eax, word ptr [rbx+0B6h]
0x180015aad  test    al, 3
0x180015aaf  jnz     loc_180015B99
0x180015ab5  lea     r14d, ds:24h[r12*8]
0x180015abd  mov     r15d, r12d
0x180015ac0  test    al, 4
0x180015ac2  jz      short loc_180015AF2
0x180015ac4  mov     rax, [rbx+20h]
0x180015ac8  lea     rdx, [rbp+var_40]
0x180015acc  mov     r8d, 4
0x180015ad2  mov     rcx, rdi
0x180015ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ada  cmp     eax, 4
0x180015add  jnz     loc_180015B99
0x180015ae3  movzx   eax, byte ptr [rbp+var_40+2]
0x180015ae7  add     r14d, 4
0x180015aeb  imul    eax, r15d
0x180015aef  add     r14d, eax
0x180015af2  mov     rax, [rbx+38h]
0x180015af6  xor     r8d, r8d
0x180015af9  mov     edx, r14d
0x180015afc  mov     rcx, rdi
0x180015aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b04  cmp     eax, 0FFFFFFFFh
0x180015b07  jz      loc_180015B99
0x180015b0d  mov     rax, [rbx+20h]
0x180015b11  lea     rdx, [rbp+var_38]
0x180015b15  mov     r8d, 8
0x180015b1b  mov     rcx, rdi
0x180015b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b23  cmp     eax, 8
0x180015b26  jnz     short loc_180015B99
0x180015b28  mov     eax, dword ptr [rbp+var_38]
0x180015b2b  xor     r8d, r8d
0x180015b2e  mov     dword ptr [rbp+var_30+8], eax
0x180015b31  xor     edx, edx
0x180015b33  mov     rax, [rbx+38h]
0x180015b37  mov     rcx, rdi
0x180015b3a  mov     word ptr [rbp+var_20+0Ah], r12w
0x180015b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b44  cmp     eax, 0FFFFFFFFh
0x180015b47  jz      short loc_180015B99
0x180015b49  mov     rax, [rbx+28h]
0x180015b4d  lea     rdx, [rbp+var_30]
0x180015b51  mov     r8d, 24h ; '$'
0x180015b57  mov     rcx, rdi
0x180015b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b5f  cmp     eax, 24h ; '$'
0x180015b62  jnz     short loc_180015B99
0x180015b64  mov     edx, dword ptr [rbp+var_38]
0x180015b67  xor     r8d, r8d
0x180015b6a  mov     rax, [rbx+38h]
0x180015b6e  mov     rcx, rdi
0x180015b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b76  cmp     eax, 0FFFFFFFFh
0x180015b79  jz      short loc_180015B99
0x180015b7b  mov     rax, [rbx+28h]
0x180015b7f  lea     rdx, [rbp+var_30]
0x180015b83  xor     r8d, r8d
0x180015b86  mov     rcx, rdi
0x180015b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b8e  cmp     eax, 0FFFFFFFFh
0x180015b91  mov     ecx, 1
0x180015b96  cmovnz  esi, ecx
0x180015b99  mov     rax, [rbx+30h]
0x180015b9d  mov     rcx, rdi
0x180015ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ba5  mov     eax, esi
0x180015ba7  mov     rcx, [rbp+var_8]
0x180015bab  xor     rcx, rsp; StackCookie
0x180015bae  call    __security_check_cookie
0x180015bb3  add     rsp, 60h
0x180015bb7  pop     r15
0x180015bb9  pop     r14
0x180015bbb  pop     r12
0x180015bbd  pop     rdi
0x180015bbe  pop     rsi
0x180015bbf  pop     rbx
0x180015bc0  pop     rbp
0x180015bc1  retn
```
