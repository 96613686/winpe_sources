# I_OpenProtectedMessage

- ea: `0x180007274`
- end: `0x18000740f`
- name: `I_OpenProtectedMessage`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007420`

## callees

- `0x1800053ac`
- `0x180007274`
- `0x180007ae0`
- `0x18000d02c`
- `0x1800122c4`
- `0x180020010`

## string_xrefs

- `0x180007369`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x1800073b0`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`

## pseudocode

```c
__int64 __fastcall I_OpenProtectedMessage(
        _QWORD *a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        unsigned int *a8)
{
  _QWORD *v8; // r13
  __int64 v9; // r15
  _BYTE *v12; // rsi
  unsigned int ProtectionDescriptor; // edi
  int v14; // r8d
  __int64 v15; // rbx
  int v16; // r8d
  unsigned int *v17; // rcx
  unsigned int v18; // eax
  _BYTE *v19; // rcx
  __int64 v21; // rax
  _BYTE *v22; // rdx
  __int64 v23; // [rsp+40h] [rbp-18h] BYREF
  _BYTE *v24; // [rsp+48h] [rbp-10h] BYREF
  unsigned int v25; // [rsp+A0h] [rbp+48h] BYREF

  v8 = a7;
  v9 = a5;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  *a8 = 0;
  *v8 = 0;
  *a1 = 0;
  v12 = 0;
  ProtectionDescriptor = I_GetProtectionDescriptor(a3, a4, v9, &v23);
  if ( !ProtectionDescriptor )
  {
    v15 = v23;
    if ( (a2 & 1) == 0 )
    {
      ProtectionDescriptor = I_GetContentEncryptKey(v23, a2, v9, a6, (__int64)&v24, (__int64)&v25);
      if ( ProtectionDescriptor )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned int)&WPP_GLOBAL_Control,
            v16,
            (unsigned int)"Status",
            ProtectionDescriptor,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
            170);
        v19 = v24;
        goto LABEL_6;
      }
      v12 = v24;
    }
    v17 = a8;
    v18 = v25;
    *a1 = v15;
    *v8 = v12;
    *v17 = v18;
    v19 = 0;
    v15 = 0;
LABEL_6:
    if ( v19 )
    {
      v21 = v25;
      v22 = v19;
      if ( v25 )
      {
        do
        {
          *v22++ = 0;
          --v21;
        }
        while ( v21 );
      }
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(v9 + 16))(v19, v22);
    }
    goto LABEL_7;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      v14,
      (unsigned int)"Status",
      ProtectionDescriptor,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
      155);
  v15 = v23;
LABEL_7:
  if ( v15 )
    NCryptCloseProtectionDescriptor(v15);
  return ProtectionDescriptor;
}

```

## disassembly

```asm
0x180007274  push    rbp
0x180007276  push    rbx
0x180007277  push    rsi
0x180007278  push    rdi
0x180007279  push    r12
0x18000727b  push    r13
0x18000727d  push    r14
0x18000727f  push    r15
0x180007281  mov     rbp, rsp
0x180007284  sub     rsp, 58h
0x180007288  mov     r13, [rbp+arg_30]
0x18000728c  xor     ebx, ebx
0x18000728e  mov     r15, [rbp+arg_20]
0x180007292  mov     r12, rcx
0x180007295  mov     rcx, [rbp+arg_38]
0x18000729c  mov     eax, r9d
0x18000729f  mov     r10, r8
0x1800072a2  mov     [rbp+var_18], rbx
0x1800072a6  mov     r14d, edx
0x1800072a9  mov     [rbp+var_10], rbx
0x1800072ad  lea     r9, [rbp+var_18]
0x1800072b1  mov     [rbp+arg_0], ebx
0x1800072b4  mov     [rcx], ebx
0x1800072b6  mov     r8, r15
0x1800072b9  mov     rcx, r10
0x1800072bc  mov     [r13+0], rbx
0x1800072c0  mov     edx, eax
0x1800072c2  mov     [r12], rbx
0x1800072c6  mov     esi, ebx
0x1800072c8  call    I_GetProtectionDescriptor
0x1800072cd  mov     edi, eax
0x1800072cf  test    eax, eax
0x1800072d1  jnz     short loc_18000734C
0x1800072d3  mov     rbx, [rbp+var_18]
0x1800072d7  test    r14b, 1
0x1800072db  jnz     short loc_18000730F
0x1800072dd  mov     r9, [rbp+arg_28]
0x1800072e1  lea     rax, [rbp+arg_0]
0x1800072e5  mov     [rsp+58h+var_30], rax
0x1800072ea  mov     r8, r15
0x1800072ed  lea     rax, [rbp+var_10]
0x1800072f1  mov     edx, r14d
0x1800072f4  mov     rcx, rbx
0x1800072f7  mov     [rsp+58h+var_38], rax
0x1800072fc  call    I_GetContentEncryptKey
0x180007301  mov     edi, eax
0x180007303  test    eax, eax
0x180007305  jnz     loc_180007393
0x18000730b  mov     rsi, [rbp+var_10]
0x18000730f  mov     rcx, [rbp+arg_38]
0x180007316  mov     eax, [rbp+arg_0]
0x180007319  mov     [r12], rbx
0x18000731d  mov     [r13+0], rsi
0x180007321  mov     [rcx], eax
0x180007323  xor     ecx, ecx
0x180007325  xor     ebx, ebx
0x180007327  test    rcx, rcx
0x18000732a  jnz     loc_1800073DD
0x180007330  test    rbx, rbx
0x180007333  jnz     loc_180007402
0x180007339  mov     eax, edi
0x18000733b  add     rsp, 58h
0x18000733f  pop     r15
0x180007341  pop     r14
0x180007343  pop     r13
0x180007345  pop     r12
0x180007347  pop     rdi
0x180007348  pop     rsi
0x180007349  pop     rbx
0x18000734a  pop     rbp
0x18000734b  retn
0x18000734c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007353  lea     rdx, WPP_GLOBAL_Control
0x18000735a  cmp     rcx, rdx
0x18000735d  jz      short loc_18000738D
0x18000735f  test    byte ptr [rcx+1Ch], 1
0x180007363  jz      short loc_18000738D
0x180007365  mov     rcx, [rcx+10h]
0x180007369  lea     rax, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007370  mov     [rsp+58h+var_28], 69Bh
0x180007378  lea     r9, aStatus; "Status"
0x18000737f  mov     [rsp+58h+var_30], rax
0x180007384  mov     dword ptr [rsp+58h+var_38], edi
0x180007388  call    WPP_SF_sDsd
0x18000738d  mov     rbx, [rbp+var_18]
0x180007391  jmp     short loc_180007330
0x180007393  mov     rcx, cs:WPP_GLOBAL_Control
0x18000739a  lea     rdx, WPP_GLOBAL_Control
0x1800073a1  cmp     rcx, rdx
0x1800073a4  jz      short loc_1800073D4
0x1800073a6  test    byte ptr [rcx+1Ch], 1
0x1800073aa  jz      short loc_1800073D4
0x1800073ac  mov     rcx, [rcx+10h]
0x1800073b0  lea     rax, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800073b7  mov     [rsp+58h+var_28], 6AAh
0x1800073bf  lea     r9, aStatus; "Status"
0x1800073c6  mov     [rsp+58h+var_30], rax
0x1800073cb  mov     dword ptr [rsp+58h+var_38], edi
0x1800073cf  call    WPP_SF_sDsd
0x1800073d4  mov     rcx, [rbp+var_10]
0x1800073d8  jmp     loc_180007327
0x1800073dd  mov     eax, [rbp+arg_0]
0x1800073e0  mov     rdx, rcx
0x1800073e3  test    rax, rax
0x1800073e6  jz      short loc_1800073F4
0x1800073e8  mov     byte ptr [rdx], 0
0x1800073eb  inc     rdx
0x1800073ee  sub     rax, 1
0x1800073f2  jnz     short loc_1800073E8
0x1800073f4  mov     rax, [r15+10h]
0x1800073f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073fd  jmp     loc_180007330
0x180007402  mov     rcx, rbx
0x180007405  call    NCryptCloseProtectionDescriptor
0x18000740a  jmp     loc_180007339
```
