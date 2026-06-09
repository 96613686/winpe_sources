# NCryptEncapsulate

- ea: `0x18001c0b0`
- end: `0x18001c2b6`
- name: `NCryptEncapsulate`
- size: `518`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000a650`
- `0x18000a71c`
- `0x18000c8e0`
- `0x18000e120`
- `0x180010684`
- `0x18001c0b0`
- `0x180020010`

## string_xrefs

- `0x18001c23d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18001c285`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __fastcall NCryptEncapsulate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        BYTE *a5,
        DWORD *a6,
        DWORD *a7,
        int a8)
{
  __int64 v10; // r9
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  unsigned int v15; // r8d
  _QWORD *v16; // rdi
  __int64 v17; // rax
  unsigned int v18; // eax
  NCRYPT_KEY_HANDLE *v19; // rdx
  NCryptKeyName **v20; // r8
  NCryptAlgorithmName **v21; // r9
  int v22; // r9d
  unsigned int v25; // [rsp+A0h] [rbp+18h]

  v25 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_PD(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, a3, a1);
  if ( !a4 )
  {
    v10 = 4657;
LABEL_6:
    v11 = -2146893785;
    v12 = 2148073511LL;
LABEL_22:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v10);
    return NormalizeNteStatus(v11, v19, v20, v21, a5, a6, a7);
  }
  if ( !a7 )
  {
    v10 = 4663;
    goto LABEL_6;
  }
  v13 = ValidateClientKeyHandle(a1);
  v16 = (_QWORD *)v13;
  if ( !v13 )
  {
    v11 = -2146893786;
    v10 = 4672;
    v12 = 2148073510LL;
    goto LABEL_22;
  }
  v17 = *(_QWORD *)(v13 + 8);
  if ( *(_WORD *)(v17 + 16) < 4u || !*(_QWORD *)(v17 + 256) )
  {
    v11 = -2146893783;
    v10 = 4684;
    v12 = 2148073513LL;
    goto LABEL_22;
  }
  while ( 1 )
  {
    v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, __int64, BYTE *, _DWORD, DWORD *, int))(v16[1] + 256LL))(
            *(_QWORD *)(v16[1] + 272LL),
            v16[2],
            v14,
            v15,
            a4,
            a5,
            (_DWORD)a6,
            a7,
            a8);
    v11 = v18;
    if ( v18 != -2146893778 )
      break;
    if ( (a8 & 0x40) != 0 )
    {
      v11 = -2146893790;
      v10 = 4710;
      v12 = 2148073506LL;
      goto LABEL_22;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, const wchar_t *, _QWORD))(v16[1] + 192LL))(
            *(_QWORD *)(v16[1] + 272LL),
            a1,
            L"NCryptEncapsulate",
            0);
    if ( v11 )
      goto LABEL_19;
    v15 = v25;
    v14 = a2;
  }
  if ( v18 )
  {
LABEL_19:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 4728);
    EtwLogNCryptOperationFailed(18, *(_QWORD *)(v16[1] + 280LL), v16[3], v22, v11);
    return NormalizeNteStatus(v11, v19, v20, v21, a5, a6, a7);
  }
  v11 = 0;
  return NormalizeNteStatus(v11, v19, v20, v21, a5, a6, a7);
}

```

## disassembly

```asm
0x18001c0b0  mov     [rsp+arg_0], rbx
0x18001c0b5  mov     [rsp+arg_10], r8d
0x18001c0ba  mov     [rsp+arg_8], rdx
0x18001c0bf  push    rbp
0x18001c0c0  push    rsi
0x18001c0c1  push    rdi
0x18001c0c2  push    r12
0x18001c0c4  push    r13
0x18001c0c6  push    r14
0x18001c0c8  push    r15
0x18001c0ca  sub     rsp, 50h
0x18001c0ce  mov     r15, r9
0x18001c0d1  mov     rsi, rcx
0x18001c0d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0db  lea     rax, WPP_GLOBAL_Control
0x18001c0e2  mov     ebp, [rsp+88h+arg_38]
0x18001c0e9  cmp     rcx, rax
0x18001c0ec  jz      short loc_18001C119
0x18001c0ee  test    byte ptr [rcx+1Ch], 4
0x18001c0f2  jz      short loc_18001C119
0x18001c0f4  mov     rcx, [rcx+10h]
0x18001c0f8  mov     edx, 26h ; '&'
0x18001c0fd  mov     r9, rsi
0x18001c100  mov     dword ptr [rsp+88h+var_68], ebp
0x18001c104  call    WPP_SF_PD
0x18001c109  mov     r8d, [rsp+88h+arg_10]
0x18001c111  mov     rdx, [rsp+88h+arg_8]
0x18001c119  test    r15, r15
0x18001c11c  jnz     short loc_18001C133
0x18001c11e  mov     r9d, 1231h
0x18001c124  mov     ebx, 80090027h
0x18001c129  mov     ecx, 80090027h
0x18001c12e  jmp     loc_18001C285
0x18001c133  mov     r14, [rsp+88h+arg_30]
0x18001c13b  test    r14, r14
0x18001c13e  jnz     short loc_18001C148
0x18001c140  mov     r9d, 1237h
0x18001c146  jmp     short loc_18001C124
0x18001c148  mov     rcx, rsi
0x18001c14b  call    ValidateClientKeyHandle
0x18001c150  mov     rdi, rax
0x18001c153  test    rax, rax
0x18001c156  jnz     short loc_18001C16D
0x18001c158  mov     ebx, 80090026h
0x18001c15d  mov     r9d, 1240h
0x18001c163  mov     ecx, 80090026h
0x18001c168  jmp     loc_18001C285
0x18001c16d  mov     rax, [rax+8]
0x18001c171  cmp     word ptr [rax+10h], 4
0x18001c176  jb      loc_18001C275
0x18001c17c  cmp     qword ptr [rax+100h], 0
0x18001c184  jz      loc_18001C275
0x18001c18a  mov     r12d, dword ptr [rsp+88h+arg_28]
0x18001c192  mov     r13, [rsp+88h+arg_20]
0x18001c19a  mov     rcx, [rdi+8]
0x18001c19e  mov     r9d, r8d
0x18001c1a1  mov     [rsp+88h+var_48], ebp
0x18001c1a5  mov     r8, rdx
0x18001c1a8  mov     rdx, [rdi+10h]
0x18001c1ac  mov     [rsp+88h+var_50], r14
0x18001c1b1  mov     rax, [rcx+100h]
0x18001c1b8  mov     rcx, [rcx+110h]
0x18001c1bf  mov     [rsp+88h+var_58], r12d
0x18001c1c4  mov     [rsp+88h+var_60], r13
0x18001c1c9  mov     [rsp+88h+var_68], r15
0x18001c1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1d3  mov     ebx, eax
0x18001c1d5  cmp     eax, 8009002Eh
0x18001c1da  jnz     short loc_18001C233
0x18001c1dc  test    bpl, 40h
0x18001c1e0  jnz     short loc_18001C221
0x18001c1e2  mov     rcx, [rdi+8]
0x18001c1e6  lea     r8, aNcryptencapsul_0; "NCryptEncapsulate"
0x18001c1ed  xor     r9d, r9d
0x18001c1f0  mov     rdx, rsi
0x18001c1f3  mov     rax, [rcx+0C0h]
0x18001c1fa  mov     rcx, [rcx+110h]
0x18001c201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c206  mov     ebx, eax
0x18001c208  test    eax, eax
0x18001c20a  jnz     short loc_18001C237
0x18001c20c  mov     r8d, [rsp+88h+arg_10]
0x18001c214  mov     rdx, [rsp+88h+arg_8]
0x18001c21c  jmp     loc_18001C19A
0x18001c221  mov     ebx, 80090022h
0x18001c226  mov     r9d, 1266h
0x18001c22c  mov     ecx, 80090022h
0x18001c231  jmp     short loc_18001C285
0x18001c233  test    eax, eax
0x18001c235  jz      short loc_18001C271
0x18001c237  mov     r9d, 1278h
0x18001c23d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c244  lea     rdx, aStatus; "Status"
0x18001c24b  mov     ecx, ebx
0x18001c24d  call    DebugTraceError
0x18001c252  mov     rdx, [rdi+8]
0x18001c256  mov     ecx, 12h
0x18001c25b  mov     r8, [rdi+18h]
0x18001c25f  mov     dword ptr [rsp+88h+var_68], ebx
0x18001c263  mov     rdx, [rdx+118h]
0x18001c26a  call    EtwLogNCryptOperationFailed
0x18001c26f  jmp     short loc_18001C298
0x18001c271  xor     ebx, ebx
0x18001c273  jmp     short loc_18001C298
0x18001c275  mov     ebx, 80090029h
0x18001c27a  mov     r9d, 124Ch
0x18001c280  mov     ecx, 80090029h
0x18001c285  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c28c  lea     rdx, aStatus; "Status"
0x18001c293  call    DebugTraceError
0x18001c298  mov     ecx, ebx
0x18001c29a  mov     rbx, [rsp+88h+arg_0]
0x18001c2a2  add     rsp, 50h
0x18001c2a6  pop     r15
0x18001c2a8  pop     r14
0x18001c2aa  pop     r13
0x18001c2ac  pop     r12
0x18001c2ae  pop     rdi
0x18001c2af  pop     rsi
0x18001c2b0  pop     rbp
0x18001c2b1  jmp     NormalizeNteStatus
```
