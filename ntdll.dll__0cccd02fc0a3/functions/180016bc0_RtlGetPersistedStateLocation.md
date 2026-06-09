# RtlGetPersistedStateLocation

- ea: `0x180016bc0`
- end: `0x180016f8d`
- name: `RtlGetPersistedStateLocation`
- size: `973`
- prototype: `__int64 __usercall@<rax>(wchar_t *String@<rcx>, void *, int, __int64)`
- caller_count: `5`
- callee_count: `9`
- tags: ``

## callers

- `0x180010870`
- `0x18005b0f0`
- `0x1800c966c`
- `0x1801368a4`
- `0x180147c08`

## callees

- `0x180016bc0`
- `0x18001861c`
- `0x18001b984`
- `0x18008e720`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e5b0`
- `0x180163a80`

## string_xrefs

- `0x180016dc5`: `TargetPath`

## pseudocode

```c
__int64 __fastcall RtlGetPersistedStateLocation(
        wchar_t *String,
        const wchar_t *a2,
        _WORD *a3,
        unsigned int a4,
        void *a5,
        unsigned int a6,
        unsigned int *a7)
{
  __int64 Heap_0; // rsi
  signed int v11; // edi
  __int64 v12; // r8
  unsigned int v13; // r8d
  unsigned int v14; // eax
  unsigned int v16; // ecx
  size_t v17; // r8
  _WORD *v18; // rdx
  int v19; // eax
  size_t v20; // rax
  int v21; // eax
  unsigned __int64 v22; // r14
  size_t v23; // rax
  int v24; // eax
  unsigned int v25; // ecx
  unsigned int v26; // eax
  __int64 v27; // r8
  HANDLE Handle; // [rsp+38h] [rbp-41h] BYREF
  HANDLE v29; // [rsp+40h] [rbp-39h] BYREF
  __int64 v30; // [rsp+48h] [rbp-31h] BYREF
  __int128 v31; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v32[48]; // [rsp+60h] [rbp-19h] BYREF
  unsigned int v33; // [rsp+E0h] [rbp+67h] BYREF

  Handle = 0;
  v29 = 0;
  v33 = 0;
  v30 = 0;
  memset(v32, 0, 44);
  v31 = 0;
  if ( a4 > 1 )
    return 3221225713LL;
  Heap_0 = 0;
  if ( byte_1801C6671 )
  {
    v11 = -1073741772;
    goto LABEL_4;
  }
  *(_DWORD *)v32 = 48;
  *(_QWORD *)&v32[16] = &qword_1801702D0[2 * (int)a4];
  *(_QWORD *)&v32[8] = 0;
  *(_DWORD *)&v32[24] = 64;
  *(_OWORD *)&v32[32] = 0;
  v19 = NtOpenKey(&Handle, 131097, v32);
  v11 = v19;
  if ( v19 == -1073741772 )
  {
    byte_1801C6671 = 1;
  }
  else
  {
    if ( v19 < 0 )
      goto LABEL_9;
    *(_QWORD *)&v31 = 0;
    *((_QWORD *)&v31 + 1) = String;
    if ( String )
    {
      v20 = 2 * wcslen(String);
      if ( v20 >= 0xFFFE )
        LOWORD(v20) = -4;
      LOWORD(v31) = v20;
      WORD1(v31) = v20 + 2;
    }
    *(_QWORD *)&v32[8] = Handle;
    *(_DWORD *)v32 = 48;
    *(_QWORD *)&v32[16] = &v31;
    *(_DWORD *)&v32[24] = 64;
    *(_OWORD *)&v32[32] = 0;
    v21 = NtOpenKey(&v29, 131097, v32);
    v11 = v21;
    if ( v21 != -1073741772 )
    {
      if ( v21 < 0 )
        goto LABEL_9;
      *(_QWORD *)&v31 = 0;
      if ( !a2 )
        a2 = L"TargetPath";
      *((_QWORD *)&v31 + 1) = a2;
      v22 = a6;
      v23 = 2 * wcslen(a2);
      if ( v23 >= 0xFFFE )
        LOWORD(v23) = -4;
      LOWORD(v31) = v23;
      WORD1(v31) = v23 + 2;
      if ( a6 + 16 < a6 )
      {
        v11 = -1073741675;
        goto LABEL_9;
      }
      Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, a6 + 16);
      if ( !Heap_0 )
      {
        v11 = -1073741801;
        goto LABEL_9;
      }
      v24 = NtQueryValueKey(v29, &v31, 2, Heap_0, (int)v22 + 16, &v33);
      v11 = v24;
      if ( v24 < 0 )
      {
        if ( v24 != -2147483643 )
          goto LABEL_9;
        v25 = *(_DWORD *)(Heap_0 + 8);
        v18 = (_WORD *)(Heap_0 + 12);
        v33 = v25;
        goto LABEL_38;
      }
      if ( (unsigned int)(*(_DWORD *)(Heap_0 + 4) - 1) > 1 )
      {
        v11 = -1073741788;
        goto LABEL_9;
      }
      v18 = (_WORD *)(Heap_0 + 12);
      v33 = *(_DWORD *)(Heap_0 + 8);
      v25 = v33;
      if ( *(_WORD *)(Heap_0 + 12 + 2 * ((unsigned __int64)v33 >> 1) - 2) )
      {
        v26 = v33 + 2;
        v33 = v26;
        v25 += 2;
        if ( (unsigned int)v22 < v26 )
        {
          v11 = -2147483643;
LABEL_38:
          if ( a7 )
            *a7 = v25;
          if ( v11 < 0 )
            goto LABEL_9;
          v17 = v25;
          goto LABEL_20;
        }
        v18[((unsigned __int64)v26 >> 1) - 1] = 0;
        v25 = v33;
      }
      if ( *(_DWORD *)(Heap_0 + 4) == 2 )
      {
        v27 = -1;
        do
          ++v27;
        while ( v18[v27] );
        v11 = RtlExpandEnvironmentStrings(0, (_DWORD)v18, v27, (_DWORD)a5, v22 >> 1, (__int64)&v30);
        if ( (int)(v11 + 0x80000000) < 0 || v11 == -1073741789 )
        {
          if ( a7 )
            *a7 = 2 * v30;
          if ( v11 == -1073741789 )
            v11 = -2147483643;
        }
        goto LABEL_9;
      }
      goto LABEL_38;
    }
  }
LABEL_4:
  if ( a3 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
    v13 = v12 + 1;
    v14 = 2 * v13;
    v33 = 2 * v13;
    if ( 2 * v13 < v13 )
    {
      v11 = -1073741675;
      goto LABEL_9;
    }
    v16 = a6;
    v11 = a6 < v14 ? 0x80000005 : 0;
    if ( a7 )
      *a7 = v14;
    if ( v14 > v16 )
      goto LABEL_9;
    v17 = v14;
    v18 = a3;
LABEL_20:
    memmove(a5, v18, v17);
  }
LABEL_9:
  if ( Handle )
    NtClose(Handle);
  if ( v29 )
    NtClose(v29);
  if ( Heap_0 )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, Heap_0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180016bc0  mov     r11, rsp
0x180016bc3  push    rbp
0x180016bc4  push    rbx
0x180016bc5  push    r12
0x180016bc7  push    r14
0x180016bc9  push    r15
0x180016bcb  lea     rbp, [r11-47h]
0x180016bcf  sub     rsp, 90h
0x180016bd6  xor     r12d, r12d
0x180016bd9  xorps   xmm0, xmm0
0x180016bdc  xor     eax, eax
0x180016bde  mov     [rbp+3Fh+Handle], r12
0x180016be2  mov     [rbp+3Fh+var_78], r12
0x180016be6  mov     rbx, r8
0x180016be9  mov     [rbp+3Fh+arg_18], r12d
0x180016bed  mov     r15, rdx
0x180016bf0  mov     [rbp+3Fh+var_70], r12
0x180016bf4  mov     r14, rcx
0x180016bf7  movups  [rbp+3Fh+var_48], xmm0
0x180016bfb  movups  [rbp+3Fh+var_48+0Ch], xmm0
0x180016bff  movups  [rbp+3Fh+var_58], xmm0
0x180016c03  movups  [rbp+3Fh+var_68], xmm0
0x180016c07  cmp     r9d, 1
0x180016c0b  ja      loc_180016E9F
0x180016c11  cmp     cs:byte_1801C6671, al
0x180016c17  mov     [r11+8], rsi
0x180016c1b  mov     esi, r12d
0x180016c1e  mov     [r11+10h], rdi
0x180016c22  mov     [r11+18h], r13
0x180016c26  jz      loc_180016CF1
0x180016c2c  mov     edi, 0C0000034h
0x180016c31  test    rbx, rbx
0x180016c34  jz      short loc_180016C5E
0x180016c36  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180016c3d  nop     dword ptr [rax]
0x180016c40  inc     r8
0x180016c43  cmp     [rbx+r8*2], r12w
0x180016c48  jnz     short loc_180016C40
0x180016c4a  inc     r8d
0x180016c4d  lea     eax, [r8+r8]
0x180016c51  mov     [rbp+3Fh+arg_18], eax
0x180016c54  cmp     eax, r8d
0x180016c57  jnb     short loc_180016CC1
0x180016c59  mov     edi, 0C0000095h
0x180016c5e  mov     rcx, [rbp+3Fh+Handle]; Handle
0x180016c62  mov     r13, [rsp+0B0h+arg_10]
0x180016c6a  test    rcx, rcx
0x180016c6d  jz      short loc_180016C74
0x180016c6f  call    NtClose
0x180016c74  mov     rcx, [rbp+3Fh+var_78]; Handle
0x180016c78  test    rcx, rcx
0x180016c7b  jz      short loc_180016C82
0x180016c7d  call    NtClose
0x180016c82  test    rsi, rsi
0x180016c85  jz      short loc_180016C9E
0x180016c87  mov     rcx, gs:60h
0x180016c90  mov     r8, rsi
0x180016c93  xor     edx, edx
0x180016c95  mov     rcx, [rcx+30h]
0x180016c99  call    RtlFreeHeap_0
0x180016c9e  mov     rsi, [rsp+0B0h+arg_0]
0x180016ca6  mov     eax, edi
0x180016ca8  mov     rdi, [rsp+0B0h+arg_8]
0x180016cb0  add     rsp, 90h
0x180016cb7  pop     r15
0x180016cb9  pop     r14
0x180016cbb  pop     r12
0x180016cbd  pop     rbx
0x180016cbe  pop     rbp
0x180016cbf  retn
0x180016cc1  mov     ecx, [rbp+3Fh+arg_28]
0x180016cc4  cmp     ecx, eax
0x180016cc6  mov     rdx, [rbp+3Fh+arg_30]
0x180016cca  sbb     edi, edi
0x180016ccc  and     edi, 80000005h
0x180016cd2  test    rdx, rdx
0x180016cd5  jz      short loc_180016CD9
0x180016cd7  mov     [rdx], eax
0x180016cd9  cmp     eax, ecx
0x180016cdb  ja      short loc_180016C5E
0x180016cdd  mov     r8d, eax; Size
0x180016ce0  mov     rdx, rbx; Src
0x180016ce3  mov     rcx, [rbp+3Fh+arg_20]; void *
0x180016ce7  call    memmove
0x180016cec  jmp     loc_180016C5E
0x180016cf1  movsxd  rax, r9d
0x180016cf4  lea     rcx, qword_1801702D0
0x180016cfb  shl     rax, 4
0x180016cff  lea     r8, [rbp+3Fh+var_58]
0x180016d03  add     rax, rcx
0x180016d06  mov     dword ptr [rbp+3Fh+var_58], 30h ; '0'
0x180016d0d  lea     rcx, [rbp+3Fh+Handle]
0x180016d11  mov     qword ptr [rbp+3Fh+var_48], rax
0x180016d15  mov     edx, 20019h
0x180016d1a  mov     qword ptr [rbp+3Fh+var_58+8], r12
0x180016d1e  mov     dword ptr [rbp+3Fh+var_48+8], 40h ; '@'
0x180016d25  movdqu  [rbp+3Fh+var_38], xmm0
0x180016d2a  call    NtOpenKey
0x180016d2f  mov     edi, eax
0x180016d31  cmp     eax, 0C0000034h
0x180016d36  jz      loc_180016E89
0x180016d3c  test    eax, eax
0x180016d3e  js      loc_180016C5E
0x180016d44  mov     qword ptr [rbp+3Fh+var_68], r12
0x180016d48  mov     r13d, 0FFFCh
0x180016d4e  mov     qword ptr [rbp+3Fh+var_68+8], r14
0x180016d52  test    r14, r14
0x180016d55  jz      short loc_180016D78
0x180016d57  mov     rcx, r14; String
0x180016d5a  call    wcslen
0x180016d5f  add     rax, rax
0x180016d62  cmp     rax, 0FFFEh
0x180016d68  cmovnb  rax, r13
0x180016d6c  mov     word ptr [rbp+3Fh+var_68], ax
0x180016d70  add     ax, 2
0x180016d74  mov     word ptr [rbp+3Fh+var_68+2], ax
0x180016d78  mov     rax, [rbp+3Fh+Handle]
0x180016d7c  lea     r8, [rbp+3Fh+var_58]
0x180016d80  mov     qword ptr [rbp+3Fh+var_58+8], rax
0x180016d84  lea     rcx, [rbp+3Fh+var_78]
0x180016d88  lea     rax, [rbp+3Fh+var_68]
0x180016d8c  mov     dword ptr [rbp+3Fh+var_58], 30h ; '0'
0x180016d93  xorps   xmm0, xmm0
0x180016d96  mov     qword ptr [rbp+3Fh+var_48], rax
0x180016d9a  mov     edx, 20019h
0x180016d9f  mov     dword ptr [rbp+3Fh+var_48+8], 40h ; '@'
0x180016da6  movdqu  [rbp+3Fh+var_38], xmm0
0x180016dab  call    NtOpenKey
0x180016db0  mov     edi, eax
0x180016db2  cmp     eax, 0C0000034h
0x180016db7  jz      loc_180016C31
0x180016dbd  test    eax, eax
0x180016dbf  js      loc_180016C5E
0x180016dc5  lea     rax, aTargetpath; "TargetPath"
0x180016dcc  mov     qword ptr [rbp+3Fh+var_68], r12
0x180016dd0  test    r15, r15
0x180016dd3  cmovz   r15, rax
0x180016dd7  mov     rcx, r15; String
0x180016dda  mov     qword ptr [rbp+3Fh+var_68+8], r15
0x180016dde  call    wcslen
0x180016de3  mov     r14d, [rbp+3Fh+arg_28]
0x180016de7  add     rax, rax
0x180016dea  cmp     rax, 0FFFEh
0x180016df0  cmovnb  rax, r13
0x180016df4  mov     word ptr [rbp+3Fh+var_68], ax
0x180016df8  lea     ebx, [r14+10h]
0x180016dfc  add     ax, 2
0x180016e00  mov     word ptr [rbp+3Fh+var_68+2], ax
0x180016e04  cmp     ebx, r14d
0x180016e07  jb      loc_180016EB5
0x180016e0d  mov     rcx, gs:60h
0x180016e16  xor     edx, edx
0x180016e18  mov     r8d, ebx
0x180016e1b  mov     rcx, [rcx+30h]
0x180016e1f  call    RtlAllocateHeap_0
0x180016e24  mov     rsi, rax
0x180016e27  test    rax, rax
0x180016e2a  jz      short loc_180016E95
0x180016e2c  mov     rcx, [rbp+3Fh+var_78]
0x180016e30  lea     rax, [rbp+3Fh+arg_18]
0x180016e34  mov     [rsp+28h], rax
0x180016e39  lea     rdx, [rbp+3Fh+var_68]
0x180016e3d  mov     r9, rsi
0x180016e40  mov     dword ptr [rsp+0B0h+var_90], ebx
0x180016e44  mov     r8d, 2
0x180016e4a  call    NtQueryValueKey
0x180016e4f  mov     edi, eax
0x180016e51  test    eax, eax
0x180016e53  jns     loc_180016F75
0x180016e59  cmp     eax, 80000005h
0x180016e5e  jnz     loc_180016C5E
0x180016e64  mov     ecx, [rsi+8]
0x180016e67  lea     rdx, [rsi+0Ch]
0x180016e6b  mov     [rbp+3Fh+arg_18], ecx
0x180016e6e  mov     rax, [rbp+3Fh+arg_30]
0x180016e72  test    rax, rax
0x180016e75  jz      short loc_180016E79
0x180016e77  mov     [rax], ecx
0x180016e79  test    edi, edi
0x180016e7b  js      loc_180016C5E
0x180016e81  mov     r8d, ecx
0x180016e84  jmp     loc_180016CE3
0x180016e89  mov     cs:byte_1801C6671, 1
0x180016e90  jmp     loc_180016C31
0x180016e95  mov     edi, 0C0000017h
0x180016e9a  jmp     loc_180016C5E
0x180016e9f  mov     eax, 0C00000F1h
0x180016ea4  add     rsp, 90h
0x180016eab  pop     r15
0x180016ead  pop     r14
0x180016eaf  pop     r12
0x180016eb1  pop     rbx
0x180016eb2  pop     rbp
0x180016eb3  retn
0x180016eb5  mov     edi, 0C0000095h
0x180016eba  jmp     loc_180016C5E
0x180016ebf  mov     ecx, [rsi+8]
0x180016ec2  lea     rdx, [rsi+0Ch]
0x180016ec6  mov     eax, ecx
0x180016ec8  mov     [rbp+3Fh+arg_18], ecx
0x180016ecb  shr     rax, 1
0x180016ece  cmp     [rdx+rax*2-2], r12w
0x180016ed4  jz      short loc_180016EF1
0x180016ed6  lea     eax, [rcx+2]
0x180016ed9  mov     [rbp+3Fh+arg_18], eax
0x180016edc  mov     ecx, eax
0x180016ede  cmp     r14d, eax
0x180016ee1  jb      short loc_180016F5E
0x180016ee3  mov     ecx, eax
0x180016ee5  shr     rcx, 1
0x180016ee8  mov     [rdx+rcx*2-2], r12w
0x180016eee  mov     ecx, [rbp+3Fh+arg_18]
0x180016ef1  cmp     dword ptr [rsi+4], 2
0x180016ef5  jnz     loc_180016E6E
0x180016efb  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180016f02  inc     r8
0x180016f05  cmp     [rdx+r8*2], r12w
0x180016f0a  jnz     short loc_180016F02
0x180016f0c  mov     r9, [rbp+3Fh+arg_20]
0x180016f10  lea     rcx, [rbp+3Fh+var_70]
0x180016f14  mov     [rsp+28h], rcx
0x180016f19  mov     rax, r14
0x180016f1c  shr     rax, 1
0x180016f1f  xor     ecx, ecx
0x180016f21  mov     [rsp+0B0h+var_90], rax
0x180016f26  call    RtlExpandEnvironmentStrings
0x180016f2b  mov     ecx, 80000000h
0x180016f30  mov     edi, eax
0x180016f32  add     eax, ecx
0x180016f34  test    ecx, eax
0x180016f36  jz      short loc_180016F68
0x180016f38  mov     rcx, [rbp+3Fh+arg_30]
0x180016f3c  test    rcx, rcx
0x180016f3f  jz      short loc_180016F48
0x180016f41  mov     eax, dword ptr [rbp+3Fh+var_70]
0x180016f44  add     eax, eax
0x180016f46  mov     [rcx], eax
0x180016f48  cmp     edi, 0C0000023h
0x180016f4e  jnz     loc_180016C5E
0x180016f54  mov     edi, 80000005h
0x180016f59  jmp     loc_180016C5E
0x180016f5e  mov     edi, 80000005h
0x180016f63  jmp     loc_180016E6E
0x180016f68  cmp     edi, 0C0000023h
0x180016f6e  jz      short loc_180016F38
0x180016f70  jmp     loc_180016C5E
0x180016f75  mov     eax, [rsi+4]
0x180016f78  dec     eax
0x180016f7a  cmp     eax, 1
0x180016f7d  jbe     loc_180016EBF
0x180016f83  mov     edi, 0C0000024h
0x180016f88  jmp     loc_180016C5E
```
