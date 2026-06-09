# SymCrypt802_11SaeCustomCommitProcessGeneric

- ea: `0x14001aec4`
- end: `0x14001b3d1`
- name: `SymCrypt802_11SaeCustomCommitProcessGeneric`
- size: `1293`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400952e4`

## callees

- `0x1400044a4`
- `0x140004b1c`
- `0x140004b50`
- `0x140004ba8`
- `0x140004dcc`
- `0x140004f50`
- `0x1400072b0`
- `0x140007d24`
- `0x14000bc04`
- `0x14001aec4`
- `0x14001b3d8`
- `0x14001d0c0`
- `0x14001d0dc`
- `0x14002071c`
- `0x140020e74`
- `0x140020ec8`
- `0x14002c550`
- `0x14005ad6c`
- `0x14005aea8`
- `0x14009bbf0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b32c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b3a0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b32c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b3a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b33d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b3b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b33d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b3b1`

## pseudocode

```c
__int64 __fastcall SymCrypt802_11SaeCustomCommitProcessGeneric(
        _QWORD *a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v9; // rbx
  _DWORD *v10; // rbp
  unsigned int v11; // eax
  unsigned int v12; // r10d
  unsigned int v13; // edx
  unsigned int v14; // r8d
  unsigned int v15; // r11d
  unsigned int v16; // r9d
  unsigned int v17; // eax
  unsigned int v18; // r10d
  __int64 v19; // r15
  __int64 v20; // rax
  __int64 v21; // rsi
  char *v22; // rdi
  char *v23; // r14
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  unsigned int v27; // ecx
  __int64 v28; // r13
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r12
  unsigned int v32; // r8d
  unsigned int v33; // esi
  unsigned int v34; // eax
  int v35; // r8d
  _DWORD *v36; // rax
  unsigned int Value; // esi
  __int64 v38; // r8
  __int64 v39; // rdx
  int v40; // r9d
  int v41; // r9d
  int v42; // r8d
  PNPAGED_LOOKASIDE_LIST *v43; // r14
  PNPAGED_LOOKASIDE_LIST *v44; // rdi
  int v46; // [rsp+30h] [rbp-78h]
  unsigned int v47; // [rsp+50h] [rbp-58h]
  struct NETMON_VELAN *v48; // [rsp+58h] [rbp-50h]

  v9 = *a1;
  v10 = 0;
  v11 = *(_DWORD *)(*a1 + 12LL);
  if ( v11 )
  {
    if ( v11 <= 0x100000 )
      v12 = (*(_DWORD *)(*a1 + 12LL) >> 9) + (((*(_DWORD *)(*a1 + 12LL) & 0x1FFu) + 511) >> 9);
    else
      v12 = 0;
  }
  else
  {
    v12 = 1;
  }
  v13 = *(_DWORD *)(v9 + 56);
  v14 = *(_DWORD *)(v9 + 44);
  v15 = v14;
  if ( v14 <= v13 )
    v15 = *(_DWORD *)(v9 + 56);
  v16 = *(_DWORD *)(v9 + 48) + *(_DWORD *)(v9 + 52);
  if ( v16 <= v15 )
  {
    v17 = *(_DWORD *)(v9 + 56);
    if ( v14 > v13 )
      v17 = *(_DWORD *)(v9 + 44);
  }
  else
  {
    v17 = *(_DWORD *)(v9 + 48) + *(_DWORD *)(v9 + 52);
  }
  v18 = (v12 << 8) + 64;
  if ( v18 <= v17 )
  {
    if ( v16 <= v15 )
    {
      v18 = *(_DWORD *)(v9 + 56);
      if ( v14 > v13 )
        v18 = *(_DWORD *)(v9 + 44);
    }
    else
    {
      v18 = *(_DWORD *)(v9 + 48) + *(_DWORD *)(v9 + 52);
    }
  }
  v19 = v18;
  v20 = SymCryptCallbackAlloc(v18);
  v21 = *(_QWORD *)(v9 + 624);
  v22 = (char *)v20;
  v23 = 0;
  v24 = SymCryptCallbackAlloc(*(unsigned int *)(v21 + 16));
  if ( v24 )
  {
    v23 = (char *)v24;
    v27 = (*(_DWORD *)(v21 + 4) << 6) - 64;
    *(_QWORD *)(v27 + v24) = 0;
    *(_QWORD *)(v27 + v24 + 8) = 0;
    *(_QWORD *)(v27 + v24 + 16) = 0;
    *(_QWORD *)(v27 + v24 + 24) = 0;
    *(_QWORD *)(v27 + v24 + 32) = 0;
    *(_QWORD *)(v27 + v24 + 40) = 0;
    *(_QWORD *)(v27 + v24 + 48) = 0;
    *(_QWORD *)(v27 + v24 + 56) = 0;
  }
  v28 = SymCryptEcpointAllocate(v9, v25, v26);
  v31 = SymCryptEcpointAllocate(v9, v29, v30);
  v32 = *(_DWORD *)(v9 + 24) + *(_DWORD *)(v9 + 64);
  if ( v32 )
  {
    if ( v32 <= 0x100000 )
      v33 = (v32 >> 9) + (((v32 & 0x1FF) + 511) >> 9);
    else
      v33 = 0;
  }
  else
  {
    v33 = 1;
  }
  v34 = SymCryptFdefSizeofIntFromDigits(v33);
  v47 = v34;
  if ( v34 )
  {
    v36 = (_DWORD *)SymCryptCallbackAlloc(v34);
    if ( v36 )
    {
      v36[2] = v47;
      *v36 = 1732837376;
      v36[1] = v33;
      v10 = v36;
    }
  }
  if ( !v22 || !v23 || !v28 || !v31 || !v10 )
  {
    Value = 32783;
    if ( !v23 )
      goto LABEL_49;
    goto LABEL_45;
  }
  Value = SymCryptFdefRawSetValue(a2, a3, v35, (int)v10 + 32, v10[1]);
  if ( !Value )
  {
    v48 = *(struct NETMON_VELAN **)(v9 + 624);
    if ( (unsigned int)SymCryptFdefIntIsLessThan(v10, (char *)v48 + 96, v38)
      && !(unsigned int)SymCryptFdefRawIsEqualUint32(v10 + 8, (unsigned int)v10[1], 0)
      && !(unsigned int)SymCryptFdefRawIsEqualUint32(v10 + 8, v39, 1) )
    {
      SymCryptFdefRawDivMod(v10 + 8, v23, (__int64)v22);
      (*(void (__fastcall **)(struct NETMON_VELAN *, int, void *, unsigned int))((char *)&off_14009E030
                                                                               + (*(_DWORD *)v48 & 0x380)))(
        v48,
        (int)v23,
        v22,
        v19);
      SymCryptModAdd(*(_QWORD *)(v9 + 624), (_DWORD)v23, a1[2], (_DWORD)v23, (__int64)v22, v19);
      SymCryptModAdd(*(_QWORD *)(v9 + 624), (_DWORD)v23, a1[3], (_DWORD)v23, (__int64)v22, v19);
      Value = SymCryptEcpointSetValue(v9, a4, a5);
      if ( Value )
        goto LABEL_45;
      if ( ((unsigned int (__fastcall *)(__int64, __int64, char *, __int64))qword_14009E420[16
                                                                                          * (unsigned __int64)(*(_DWORD *)(v9 + 4) & 7)
                                                                                          + 1])(
             v9,
             v28,
             v22,
             v19)
        && !(unsigned int)SymCryptEcpointIsZero(v9, v28, v22, v19) )
      {
        Value = SymCryptEcpointScalarMul(v9, (_DWORD)v10, a1[4], v40, v31, (__int64)v22, v19);
        if ( !Value )
        {
          SymCryptEcpointAdd(v9, v31, v28, v31, 0, (__int64)v22, v19);
          SymCryptModElementToInt(*(_QWORD *)(v9 + 624), a1[2], (_DWORD)v10, (_DWORD)v22, v19);
          Value = SymCryptEcpointScalarMul(v9, (_DWORD)v10, v31, v41, v31, (__int64)v22, v19);
          if ( !Value )
          {
            Value = SymCryptEcpointGetValue(v9, v31, v42, 1, a6, a7, v46, (__int64)v22, v19);
            if ( !Value )
              Value = SymCryptFdefModElementGetValue(*(_QWORD *)(v9 + 624), v23, a8, a9);
          }
        }
        goto LABEL_45;
      }
    }
    Value = 32782;
  }
LABEL_45:
  SymCryptWipeAsm(v23, *(unsigned int *)(*(_QWORD *)(v9 + 624) + 16LL));
  v43 = (PNPAGED_LOOKASIDE_LIST *)&v23[-*((unsigned int *)v23 - 1)];
  if ( v43 )
  {
    if ( *(v43 - 2) )
      ExFreeToNPagedLookasideList(*(v43 - 2), v43 - 2);
    else
      ExFreePoolWithTag(v43 - 2, *((_DWORD *)v43 - 2));
  }
LABEL_49:
  if ( v28 )
    SymCryptEcpointFree(v9, v28);
  if ( v31 )
    SymCryptEcpointFree(v9, v31);
  if ( v10 )
    SymCryptIntFree(v10);
  if ( v22 )
  {
    SymCryptWipeAsm(v22, v19);
    v44 = (PNPAGED_LOOKASIDE_LIST *)&v22[-*((unsigned int *)v22 - 1)];
    if ( v44 )
    {
      if ( *(v44 - 2) )
        ExFreeToNPagedLookasideList(*(v44 - 2), v44 - 2);
      else
        ExFreePoolWithTag(v44 - 2, *((_DWORD *)v44 - 2));
    }
  }
  return Value;
}

```

## disassembly

```asm
0x14001aec4  mov     rax, rsp
0x14001aec7  mov     [rax+20h], r9
0x14001aecb  mov     [rax+18h], r8
0x14001aecf  mov     [rax+10h], rdx
0x14001aed3  mov     [rax+8], rcx
0x14001aed7  push    rbx
0x14001aed8  push    rbp
0x14001aed9  push    rsi
0x14001aeda  push    rdi
0x14001aedb  push    r12
0x14001aedd  push    r13
0x14001aedf  push    r14
0x14001aee1  push    r15
0x14001aee3  sub     rsp, 68h
0x14001aee7  mov     rbx, [rcx]
0x14001aeea  xor     ebp, ebp
0x14001aeec  mov     ecx, 1FFh
0x14001aef1  mov     eax, [rbx+0Ch]
0x14001aef4  test    eax, eax
0x14001aef6  jnz     short loc_14001AEFE
0x14001aef8  lea     r10d, [rax+1]
0x14001aefc  jmp     short loc_14001AF1D
0x14001aefe  cmp     eax, 100000h
0x14001af03  jbe     short loc_14001AF0A
0x14001af05  mov     r10d, ebp
0x14001af08  jmp     short loc_14001AF1D
0x14001af0a  mov     r10d, eax
0x14001af0d  shr     eax, 9
0x14001af10  and     r10d, ecx
0x14001af13  add     r10d, ecx
0x14001af16  shr     r10d, 9
0x14001af1a  add     r10d, eax
0x14001af1d  mov     edx, [rbx+38h]
0x14001af20  mov     r8d, [rbx+2Ch]
0x14001af24  mov     r11d, r8d
0x14001af27  mov     r9d, [rbx+34h]
0x14001af2b  cmp     r8d, edx
0x14001af2e  cmovbe  r11d, edx
0x14001af32  add     r9d, [rbx+30h]
0x14001af36  cmp     r9d, r11d
0x14001af39  jbe     short loc_14001AF40
0x14001af3b  mov     eax, r9d
0x14001af3e  jmp     short loc_14001AF49
0x14001af40  cmp     r8d, edx
0x14001af43  mov     eax, edx
0x14001af45  cmova   eax, r8d
0x14001af49  shl     r10d, 8
0x14001af4d  add     r10d, 40h ; '@'
0x14001af51  cmp     r10d, eax
0x14001af54  ja      short loc_14001AF6A
0x14001af56  cmp     r9d, r11d
0x14001af59  jbe     short loc_14001AF60
0x14001af5b  mov     r10d, r9d
0x14001af5e  jmp     short loc_14001AF6A
0x14001af60  cmp     r8d, edx
0x14001af63  mov     r10d, edx
0x14001af66  cmova   r10d, r8d
0x14001af6a  mov     ecx, r10d
0x14001af6d  mov     r15d, r10d
0x14001af70  call    SymCryptCallbackAlloc
0x14001af75  mov     rsi, [rbx+270h]
0x14001af7c  mov     rdi, rax
0x14001af7f  mov     r14, rbp
0x14001af82  mov     ecx, [rsi+10h]
0x14001af85  call    SymCryptCallbackAlloc
0x14001af8a  test    rax, rax
0x14001af8d  jz      short loc_14001AFC2
0x14001af8f  mov     ecx, [rsi+4]
0x14001af92  mov     r14, rax
0x14001af95  shl     ecx, 6
0x14001af98  sub     ecx, 40h ; '@'
0x14001af9b  mov     [rcx+rax], rbp
0x14001af9f  mov     [rcx+rax+8], rbp
0x14001afa4  mov     [rcx+rax+10h], rbp
0x14001afa9  mov     [rcx+rax+18h], rbp
0x14001afae  mov     [rcx+rax+20h], rbp
0x14001afb3  mov     [rcx+rax+28h], rbp
0x14001afb8  mov     [rcx+rax+30h], rbp
0x14001afbd  mov     [rcx+rax+38h], rbp
0x14001afc2  mov     rcx, rbx
0x14001afc5  call    SymCryptEcpointAllocate
0x14001afca  mov     rcx, rbx
0x14001afcd  mov     r13, rax
0x14001afd0  call    SymCryptEcpointAllocate
0x14001afd5  mov     r8d, [rbx+40h]
0x14001afd9  mov     r12, rax
0x14001afdc  add     r8d, [rbx+18h]
0x14001afe0  jnz     short loc_14001AFE8
0x14001afe2  lea     esi, [r8+1]
0x14001afe6  jmp     short loc_14001B00B
0x14001afe8  cmp     r8d, 100000h
0x14001afef  jbe     short loc_14001AFF5
0x14001aff1  mov     esi, ebp
0x14001aff3  jmp     short loc_14001B00B
0x14001aff5  mov     esi, r8d
0x14001aff8  mov     eax, 1FFh
0x14001affd  and     esi, eax
0x14001afff  shr     r8d, 9
0x14001b003  add     esi, eax
0x14001b005  shr     esi, 9
0x14001b008  add     esi, r8d
0x14001b00b  mov     ecx, esi
0x14001b00d  call    SymCryptFdefSizeofIntFromDigits
0x14001b012  mov     dword ptr [rsp+0A8h+var_58], eax
0x14001b016  test    eax, eax
0x14001b018  jz      short loc_14001B039
0x14001b01a  mov     ecx, eax
0x14001b01c  call    SymCryptCallbackAlloc
0x14001b021  test    rax, rax
0x14001b024  jz      short loc_14001B039
0x14001b026  mov     ecx, dword ptr [rsp+0A8h+var_58]
0x14001b02a  mov     [rax+8], ecx
0x14001b02d  mov     dword ptr [rax], 67490000h
0x14001b033  mov     [rax+4], esi
0x14001b036  mov     rbp, rax
0x14001b039  test    rdi, rdi
0x14001b03c  jz      loc_14001B2F5
0x14001b042  test    r14, r14
0x14001b045  jz      loc_14001B2F5
0x14001b04b  test    r13, r13
0x14001b04e  jz      loc_14001B2F5
0x14001b054  test    r12, r12
0x14001b057  jz      loc_14001B2F5
0x14001b05d  test    rbp, rbp
0x14001b060  jz      loc_14001B2F5
0x14001b066  mov     eax, [rbp+4]
0x14001b069  lea     r9, [rbp+20h]
0x14001b06d  mov     rdx, [rsp+0A8h+arg_10]
0x14001b075  mov     rcx, [rsp+0A8h+arg_8]
0x14001b07d  mov     dword ptr [rsp+0A8h+var_88], eax
0x14001b081  call    SymCryptFdefRawSetValue
0x14001b086  mov     esi, eax
0x14001b088  test    eax, eax
0x14001b08a  jnz     loc_14001B2FF
0x14001b090  mov     rax, [rbx+270h]
0x14001b097  mov     rcx, rbp
0x14001b09a  mov     [rsp+0A8h+var_50], rax
0x14001b09f  add     rax, 40h ; '@'
0x14001b0a3  mov     [rsp+0A8h+var_58], rax
0x14001b0a8  lea     rdx, [rax+20h]
0x14001b0ac  call    SymCryptFdefIntIsLessThan
0x14001b0b1  test    eax, eax
0x14001b0b3  jz      loc_14001B2EE
0x14001b0b9  mov     edx, [rbp+4]
0x14001b0bc  lea     rsi, [rbp+20h]
0x14001b0c0  mov     rcx, rsi
0x14001b0c3  xor     r8d, r8d
0x14001b0c6  call    SymCryptFdefRawIsEqualUint32
0x14001b0cb  test    eax, eax
0x14001b0cd  jnz     loc_14001B2EE
0x14001b0d3  lea     r8d, [rax+1]
0x14001b0d7  mov     rcx, rsi
0x14001b0da  call    SymCryptFdefRawIsEqualUint32
0x14001b0df  test    eax, eax
0x14001b0e1  jnz     loc_14001B2EE
0x14001b0e7  mov     r8, [rsp+0A8h+var_58]
0x14001b0ec  mov     rcx, rsi; Src
0x14001b0ef  mov     [rsp+0A8h+var_80], rdi; __int64
0x14001b0f4  mov     [rsp+0A8h+var_88], r14; void *
0x14001b0f9  call    SymCryptFdefRawDivMod
0x14001b0fe  mov     rcx, [rsp+0A8h+var_50]
0x14001b103  lea     rdx, cs:140000000h
0x14001b10a  mov     r9, r15
0x14001b10d  mov     r8, rdi
0x14001b110  mov     eax, [rcx]
0x14001b112  and     eax, 380h
0x14001b117  mov     rax, [rax+rdx+9E030h]
0x14001b11f  mov     rdx, r14
0x14001b122  call    _guard_dispatch_icall
0x14001b127  mov     rsi, [rsp+0A8h+arg_0]
0x14001b12f  mov     r9, r14
0x14001b132  mov     rcx, [rbx+270h]
0x14001b139  mov     rdx, r14
0x14001b13c  mov     [rsp+0A8h+var_80], r15
0x14001b141  mov     [rsp+0A8h+var_88], rdi
0x14001b146  mov     r8, [rsi+10h]
0x14001b14a  call    SymCryptModAdd
0x14001b14f  mov     r8, [rsi+18h]
0x14001b153  mov     r9, r14
0x14001b156  mov     rcx, [rbx+270h]
0x14001b15d  mov     rdx, r14
0x14001b160  mov     [rsp+0A8h+var_80], r15
0x14001b165  mov     [rsp+0A8h+var_88], rdi
0x14001b16a  call    SymCryptModAdd
0x14001b16f  mov     r8, [rsp+0A8h+arg_20]
0x14001b177  mov     rcx, rbx
0x14001b17a  mov     rdx, [rsp+0A8h+arg_18]
0x14001b182  mov     [rsp+0A8h+var_68], r15
0x14001b187  mov     [rsp+0A8h+var_70], rdi
0x14001b18c  mov     dword ptr [rsp+0A8h+var_78], 0
0x14001b194  mov     [rsp+0A8h+var_80], r13
0x14001b199  call    SymCryptEcpointSetValue
0x14001b19e  mov     esi, eax
0x14001b1a0  test    eax, eax
0x14001b1a2  jnz     loc_14001B2FF
0x14001b1a8  mov     eax, [rbx+4]
0x14001b1ab  lea     rcx, cs:140000000h
0x14001b1b2  and     eax, 7
0x14001b1b5  mov     r9, r15
0x14001b1b8  shl     rax, 7
0x14001b1bc  mov     r8, rdi
0x14001b1bf  mov     rdx, r13
0x14001b1c2  mov     rax, [rax+rcx+9E428h]
0x14001b1ca  mov     rcx, rbx
0x14001b1cd  call    rax
0x14001b1cf  nop     dword ptr [rax]
0x14001b1d2  test    eax, eax
0x14001b1d4  jz      loc_14001B2EE
0x14001b1da  mov     r9, r15
0x14001b1dd  mov     r8, rdi
0x14001b1e0  mov     rdx, r13
0x14001b1e3  mov     rcx, rbx
0x14001b1e6  call    SymCryptEcpointIsZero
0x14001b1eb  test    eax, eax
0x14001b1ed  jnz     loc_14001B2EE
0x14001b1f3  mov     r8, [rsp+0A8h+arg_0]
0x14001b1fb  mov     rdx, rbp
0x14001b1fe  mov     [rsp+0A8h+var_78], r15
0x14001b203  mov     rcx, rbx
0x14001b206  mov     [rsp+0A8h+var_80], rdi
0x14001b20b  mov     [rsp+0A8h+var_88], r12
0x14001b210  mov     r8, [r8+20h]
0x14001b214  call    SymCryptEcpointScalarMul
0x14001b219  mov     esi, eax
0x14001b21b  test    eax, eax
0x14001b21d  jnz     loc_14001B2FF
0x14001b223  mov     [rsp+0A8h+var_78], r15
0x14001b228  mov     r9, r12
0x14001b22b  mov     [rsp+0A8h+var_80], rdi
0x14001b230  mov     r8, r13
0x14001b233  mov     rdx, r12
0x14001b236  mov     dword ptr [rsp+0A8h+var_88], eax
0x14001b23a  mov     rcx, rbx
0x14001b23d  call    SymCryptEcpointAdd
0x14001b242  mov     rax, [rsp+0A8h+arg_0]
0x14001b24a  mov     r9, rdi
0x14001b24d  mov     rcx, [rbx+270h]
0x14001b254  mov     r8, rbp
0x14001b257  mov     [rsp+0A8h+var_88], r15
0x14001b25c  mov     rdx, [rax+10h]
0x14001b260  call    SymCryptModElementToInt
0x14001b265  mov     [rsp+0A8h+var_78], r15
0x14001b26a  mov     r8, r12
0x14001b26d  mov     [rsp+0A8h+var_80], rdi
0x14001b272  mov     rdx, rbp
0x14001b275  mov     rcx, rbx
0x14001b278  mov     [rsp+0A8h+var_88], r12
0x14001b27d  call    SymCryptEcpointScalarMul
0x14001b282  mov     esi, eax
0x14001b284  test    eax, eax
0x14001b286  jnz     short loc_14001B2FF
0x14001b288  mov     rax, [rsp+0A8h+arg_30]
0x14001b290  lea     r9d, [rsi+1]
0x14001b294  mov     [rsp+0A8h+var_68], r15
0x14001b299  mov     rdx, r12
0x14001b29c  mov     [rsp+0A8h+var_70], rdi
0x14001b2a1  mov     rcx, rbx
0x14001b2a4  mov     [rsp+0A8h+var_80], rax
0x14001b2a9  mov     rax, [rsp+0A8h+arg_28]
0x14001b2b1  mov     [rsp+0A8h+var_88], rax
0x14001b2b6  call    SymCryptEcpointGetValue
0x14001b2bb  mov     esi, eax
0x14001b2bd  test    eax, eax
0x14001b2bf  jnz     short loc_14001B2FF
0x14001b2c1  mov     r9, [rsp+0A8h+arg_40]
0x14001b2c9  mov     rdx, r14
0x14001b2cc  mov     r8, [rsp+0A8h+arg_38]
0x14001b2d4  mov     rcx, [rbx+270h]
0x14001b2db  mov     [rsp+0A8h+var_78], r15
0x14001b2e0  mov     [rsp+0A8h+var_80], rdi
0x14001b2e5  call    SymCryptFdefModElementGetValue
0x14001b2ea  mov     esi, eax
0x14001b2ec  jmp     short loc_14001B2FF
0x14001b2ee  mov     esi, 800Eh
0x14001b2f3  jmp     short loc_14001B2FF
0x14001b2f5  mov     esi, 800Fh
0x14001b2fa  test    r14, r14
0x14001b2fd  jz      short loc_14001B349
0x14001b2ff  mov     rax, [rbx+270h]
0x14001b306  mov     rcx, r14
0x14001b309  mov     edx, [rax+10h]
0x14001b30c  call    SymCryptWipeAsm
0x14001b311  mov     eax, [r14-4]
0x14001b315  sub     r14, rax
0x14001b318  jz      short loc_14001B349
0x14001b31a  lea     rcx, [r14-10h]; P
0x14001b31e  mov     rax, [rcx]
0x14001b321  test    rax, rax
0x14001b324  jz      short loc_14001B33A
0x14001b326  mov     rdx, rcx; Entry
0x14001b329  mov     rcx, rax; Lookaside
0x14001b32c  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001b333  nop     dword ptr [rax+rax+00h]
0x14001b338  jmp     short loc_14001B349
0x14001b33a  mov     edx, [rcx+8]; Tag
0x14001b33d  call    cs:__imp_ExFreePoolWithTag
0x14001b344  nop     dword ptr [rax+rax+00h]
0x14001b349  test    r13, r13
0x14001b34c  jz      short loc_14001B359
0x14001b34e  mov     rdx, r13
  ... truncated ...
```
