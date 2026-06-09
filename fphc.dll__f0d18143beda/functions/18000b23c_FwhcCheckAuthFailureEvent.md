# FwhcCheckAuthFailureEvent

- ea: `0x18000b23c`
- end: `0x18000b48f`
- name: `FwhcCheckAuthFailureEvent`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cff4`

## callees

- `0x18000b23c`
- `0x18000c868`
- `0x180011340`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000b424`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000b424`

## pseudocode

```c
__int64 __fastcall FwhcCheckAuthFailureEvent(__int64 a1, __int64 a2)
{
  unsigned int v2; // r14d
  int v5; // edx
  int *v6; // rax
  int v7; // r11d
  int v8; // r9d
  __int64 v9; // rsi
  int v10; // r8d
  int v11; // ecx
  int v12; // r10d
  int v13; // edi
  __int64 IsQMSaPresent; // rax
  int v15; // ecx
  __int64 v16; // rdi
  int Source2; // [rsp+20h] [rbp-38h] BYREF
  __int16 v19; // [rsp+24h] [rbp-34h]

  v2 = 0;
  *(_DWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  v5 = *(_DWORD *)(a1 + 136);
  if ( v5 )
  {
    if ( v5 != 2 )
      return v2;
    v6 = *(int **)(a1 + 144);
    v10 = 0;
    v8 = v6[5];
    v9 = *((_QWORD *)v6 + 7);
    v7 = v6[3];
    v11 = v6[4];
    v12 = v6[1];
  }
  else
  {
    v6 = *(int **)(a1 + 144);
    v7 = 0;
    v8 = v6[6];
    v9 = *((_QWORD *)v6 + 7);
    v10 = v6[4];
    v11 = v6[5];
    v12 = v6[1];
    if ( !v8 && !v11 && v10 == 4 )
    {
      *(_DWORD *)a2 = 9;
LABEL_49:
      *(_QWORD *)(a2 + 8) = v9;
      return v2;
    }
  }
  v13 = *v6;
  if ( *v6 == 13806 )
  {
    *(_DWORD *)a2 = 7;
    goto LABEL_49;
  }
  if ( v13 == 13905 )
  {
    if ( v5 == 2 && v6[28] == 1 )
      *(_BYTE *)(a2 + 44) = 1;
    return v2;
  }
  if ( (unsigned int)(v13 - 13906) <= 2 )
  {
    Source2 = 0;
    if ( v11 )
      return v2;
    if ( v12 != 2 )
      return v2;
    if ( v5 != 2 )
      return v2;
    IsQMSaPresent = FwhcIsQMSaPresent(a1, &Source2);
    v2 = IsQMSaPresent;
    if ( IsQMSaPresent || Source2 )
      return v2;
    if ( v13 != 13906 )
    {
      if ( v13 != 13908 )
      {
        v15 = 14;
        goto LABEL_44;
      }
      v16 = *(_QWORD *)(a1 + 80);
      Source2 = 0;
      v19 = 1280;
      if ( !v16 )
      {
        v15 = 13;
        goto LABEL_44;
      }
      if ( RtlCompareMemory((const void *)(v16 + 2), &Source2, 6u) == 6 && *(_BYTE *)(v16 + 1) == 1 )
      {
        v15 = (0xD00000002LL - (unsigned __int64)(unsigned int)(*(_DWORD *)(v16 + 8) - 18)) >> 32;
        goto LABEL_44;
      }
    }
    v15 = 12;
LABEL_44:
    *(_DWORD *)a2 = v15;
    goto LABEL_49;
  }
  if ( v13 == -2146893053 )
  {
    if ( v8 != 2 || v11 || (v5 || (unsigned int)(v10 - 1) > 1) && (v5 != 2 || (unsigned int)(v7 - 1) > 1) )
      return v2;
LABEL_22:
    *(_DWORD *)a2 = 8;
    goto LABEL_49;
  }
  if ( v13 == -2146893039 )
  {
    if ( v8 != 2 || v11 || (v5 || v10 != 1) && (v5 != 2 || v7 != 1) )
      return v2;
    goto LABEL_22;
  }
  if ( v13 == -2146893016 && v12 == 1 )
  {
    *(_DWORD *)a2 = 6;
    goto LABEL_49;
  }
  return v2;
}

```

## disassembly

```asm
0x18000b23c  mov     [rsp+arg_10], rbx
0x18000b241  push    rbp
0x18000b242  push    rsi
0x18000b243  push    rdi
0x18000b244  push    r12
0x18000b246  push    r14
0x18000b248  sub     rsp, 30h
0x18000b24c  mov     rax, cs:__security_cookie
0x18000b253  xor     rax, rsp
0x18000b256  mov     [rsp+58h+var_30], rax
0x18000b25b  xor     r14d, r14d
0x18000b25e  mov     rbx, rdx
0x18000b261  mov     [rdx], r14d
0x18000b264  mov     rbp, rcx
0x18000b267  mov     [rdx+8], r14
0x18000b26b  mov     edx, [rcx+88h]
0x18000b271  lea     r12d, [r14+2]
0x18000b275  test    edx, edx
0x18000b277  jnz     short loc_18000B2B0
0x18000b279  mov     rax, [rcx+90h]
0x18000b280  xor     r11d, r11d
0x18000b283  mov     r9d, [rax+18h]
0x18000b287  mov     rsi, [rax+38h]
0x18000b28b  mov     r8d, [rax+10h]
0x18000b28f  mov     ecx, [rax+14h]
0x18000b292  mov     r10d, [rax+4]
0x18000b296  test    r9d, r9d
0x18000b299  jnz     short loc_18000B2D6
0x18000b29b  test    ecx, ecx
0x18000b29d  jnz     short loc_18000B2D6
0x18000b29f  cmp     r8d, 4
0x18000b2a3  jnz     short loc_18000B2D6
0x18000b2a5  mov     dword ptr [rbx], 9
0x18000b2ab  jmp     loc_18000B46A
0x18000b2b0  cmp     edx, r12d
0x18000b2b3  jnz     loc_18000B46E
0x18000b2b9  mov     rax, [rcx+90h]
0x18000b2c0  xor     r8d, r8d
0x18000b2c3  mov     r9d, [rax+14h]
0x18000b2c7  mov     rsi, [rax+38h]
0x18000b2cb  mov     r11d, [rax+0Ch]
0x18000b2cf  mov     ecx, [rax+10h]
0x18000b2d2  mov     r10d, [rax+4]
0x18000b2d6  mov     edi, [rax]
0x18000b2d8  cmp     edi, 35EEh
0x18000b2de  jz      loc_18000B464
0x18000b2e4  cmp     edi, 3651h
0x18000b2ea  jz      loc_18000B453
0x18000b2f0  lea     eax, [rdi-3652h]
0x18000b2f6  cmp     eax, r12d
0x18000b2f9  jbe     loc_18000B39F
0x18000b2ff  cmp     edi, 80090303h
0x18000b305  jz      short loc_18000B369
0x18000b307  cmp     edi, 80090311h
0x18000b30d  jz      short loc_18000B330
0x18000b30f  cmp     edi, 80090328h
0x18000b315  jnz     loc_18000B46E
0x18000b31b  cmp     r10d, 1
0x18000b31f  jnz     loc_18000B46E
0x18000b325  mov     dword ptr [rbx], 6
0x18000b32b  jmp     loc_18000B46A
0x18000b330  cmp     r9d, r12d
0x18000b333  jnz     loc_18000B46E
0x18000b339  test    ecx, ecx
0x18000b33b  jnz     loc_18000B46E
0x18000b341  test    edx, edx
0x18000b343  jnz     short loc_18000B34B
0x18000b345  cmp     r8d, 1
0x18000b349  jz      short loc_18000B35E
0x18000b34b  cmp     edx, r12d
0x18000b34e  jnz     loc_18000B46E
0x18000b354  cmp     r11d, 1
0x18000b358  jnz     loc_18000B46E
0x18000b35e  mov     dword ptr [rbx], 8
0x18000b364  jmp     loc_18000B46A
0x18000b369  cmp     r9d, r12d
0x18000b36c  jnz     loc_18000B46E
0x18000b372  test    ecx, ecx
0x18000b374  jnz     loc_18000B46E
0x18000b37a  test    edx, edx
0x18000b37c  jnz     short loc_18000B387
0x18000b37e  lea     eax, [r8-1]
0x18000b382  cmp     eax, 1
0x18000b385  jbe     short loc_18000B35E
0x18000b387  cmp     edx, r12d
0x18000b38a  jnz     loc_18000B46E
0x18000b390  lea     eax, [r11-1]
0x18000b394  cmp     eax, 1
0x18000b397  ja      loc_18000B46E
0x18000b39d  jmp     short loc_18000B35E
0x18000b39f  mov     [rsp+58h+Source2], r14d
0x18000b3a4  test    ecx, ecx
0x18000b3a6  jnz     loc_18000B46E
0x18000b3ac  cmp     r10d, r12d
0x18000b3af  jnz     loc_18000B46E
0x18000b3b5  cmp     edx, r12d
0x18000b3b8  jnz     loc_18000B46E
0x18000b3be  lea     rdx, [rsp+58h+Source2]
0x18000b3c3  mov     rcx, rbp
0x18000b3c6  call    FwhcIsQMSaPresent
0x18000b3cb  mov     r14, rax
0x18000b3ce  test    rax, rax
0x18000b3d1  jnz     loc_18000B46E
0x18000b3d7  cmp     [rsp+58h+Source2], eax
0x18000b3db  jnz     loc_18000B46E
0x18000b3e1  cmp     edi, 3652h
0x18000b3e7  jnz     short loc_18000B3F0
0x18000b3e9  mov     ecx, 0Ch
0x18000b3ee  jmp     short loc_18000B44F
0x18000b3f0  cmp     edi, 3654h
0x18000b3f6  jnz     short loc_18000B44A
0x18000b3f8  mov     rdi, [rbp+50h]
0x18000b3fc  mov     [rsp+58h+Source2], 0
0x18000b404  mov     [rsp+58h+var_34], 500h
0x18000b40b  test    rdi, rdi
0x18000b40e  jnz     short loc_18000B415
0x18000b410  lea     ecx, [rdi+0Dh]
0x18000b413  jmp     short loc_18000B44F
0x18000b415  lea     rcx, [rdi+2]; Source1
0x18000b419  mov     r8d, 6; Length
0x18000b41f  lea     rdx, [rsp+58h+Source2]; Source2
0x18000b424  call    cs:__imp_RtlCompareMemory
0x18000b42a  cmp     rax, 6
0x18000b42e  jnz     short loc_18000B3E9
0x18000b430  cmp     byte ptr [rdi+1], 1
0x18000b434  jnz     short loc_18000B3E9
0x18000b436  mov     eax, [rdi+8]
0x18000b439  mov     ecx, 0Dh
0x18000b43e  sub     eax, 12h
0x18000b441  cmp     r12d, eax
0x18000b444  sbb     eax, eax
0x18000b446  add     ecx, eax
0x18000b448  jmp     short loc_18000B44F
0x18000b44a  mov     ecx, 0Eh
0x18000b44f  mov     [rbx], ecx
0x18000b451  jmp     short loc_18000B46A
0x18000b453  cmp     edx, r12d
0x18000b456  jnz     short loc_18000B46E
0x18000b458  cmp     dword ptr [rax+70h], 1
0x18000b45c  jnz     short loc_18000B46E
0x18000b45e  mov     byte ptr [rbx+2Ch], 1
0x18000b462  jmp     short loc_18000B46E
0x18000b464  mov     dword ptr [rbx], 7
0x18000b46a  mov     [rbx+8], rsi
0x18000b46e  mov     eax, r14d
0x18000b471  mov     rcx, [rsp+58h+var_30]
0x18000b476  xor     rcx, rsp; StackCookie
0x18000b479  call    __security_check_cookie
0x18000b47e  mov     rbx, [rsp+58h+arg_10]
0x18000b483  add     rsp, 30h
0x18000b487  pop     r14
0x18000b489  pop     r12
0x18000b48b  pop     rdi
0x18000b48c  pop     rsi
0x18000b48d  pop     rbp
0x18000b48e  retn
```
