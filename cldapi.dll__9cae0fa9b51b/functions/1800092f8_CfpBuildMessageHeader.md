# CfpBuildMessageHeader

- ea: `0x1800092f8`
- end: `0x1800097cb`
- name: `CfpBuildMessageHeader`
- size: `1235`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int16)`
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008bd8`
- `0x180008e74`
- `0x1800090d4`
- `0x1800097d4`
- `0x180009d1c`
- `0x18000a004`
- `0x18000a334`
- `0x18000a9a0`

## callees

- `0x18000231e`
- `0x1800092f8`
- `0x18001d0ac`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800093b2`
- `ntdll!RtlNtStatusToDosError` at `0x18000943c`
- `ntdll!RtlNtStatusToDosError` at `0x1800094c0`
- `ntdll!RtlNtStatusToDosError` at `0x180009544`
- `ntdll!RtlNtStatusToDosError` at `0x18000964c`
- `ntdll!RtlNtStatusToDosError` at `0x1800096fc`
- `ntdll!RtlNtStatusToDosError` at `0x18000979c`
- `ntdll!RtlNtStatusToDosError` at `0x1800093b2`
- `ntdll!RtlNtStatusToDosError` at `0x18000943c`
- `ntdll!RtlNtStatusToDosError` at `0x1800094c0`
- `ntdll!RtlNtStatusToDosError` at `0x180009544`
- `ntdll!RtlNtStatusToDosError` at `0x18000964c`
- `ntdll!RtlNtStatusToDosError` at `0x1800096fc`
- `ntdll!RtlNtStatusToDosError` at `0x18000979c`

## pseudocode

```c
__int64 __fastcall CfpBuildMessageHeader(__int64 a1, unsigned int a2, __int64 a3, __int16 a4)
{
  unsigned __int64 v4; // rsi
  signed int v8; // ecx
  NTSTATUS v9; // edi
  NTSTATUS v10; // ecx
  __int64 v11; // rdx
  int v12; // ecx
  signed int v13; // eax
  NTSTATUS v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rax
  signed int v17; // eax
  NTSTATUS v18; // ecx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  signed int v22; // eax
  NTSTATUS v23; // ecx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rax
  signed int v27; // eax
  __int64 v28; // rdx
  NTSTATUS v29; // ecx
  __int64 v30; // r8
  unsigned int v31; // ecx
  __int64 v32; // r8
  signed int v33; // eax
  unsigned __int16 *v34; // rdx
  NTSTATUS v35; // ecx
  __int64 v36; // r9
  size_t v37; // r8
  __int64 v38; // rcx
  unsigned __int16 *v39; // rcx
  signed int v40; // eax
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // rax
  signed int v44; // eax

  v4 = a2;
  v8 = a2 < 0xC8 ? 0x57 : 0;
  if ( a2 < 0xC8 )
    v8 = (a2 < 0xC8 ? 0x57 : 0) | 0x80070000;
  if ( v8 < 0 )
    return (unsigned int)v8;
  *(_DWORD *)(a1 + 8) = 200;
  *(_QWORD *)a1 = 1886219331;
  *(_DWORD *)(a1 + 12) = 1507328;
  memset_0((void *)(a1 + 16), 0, 0xB8u);
  v9 = -1073741789;
  if ( (unsigned int)v4 < 0x18 )
    goto LABEL_5;
  if ( *(_WORD *)(a1 + 14) )
  {
    v11 = *(unsigned int *)(a1 + 8);
    if ( ((v11 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 > v4 )
    {
LABEL_5:
      v10 = -1073741789;
      goto LABEL_10;
    }
    v12 = (v11 + 3) & 0xFFFFFFFC;
    *(_DWORD *)(a1 + 8) = v12;
    *(_DWORD *)(a1 + 20) = v12;
    v10 = 0;
    *(_DWORD *)(a1 + 16) = 65543;
    *(_BYTE *)((((_DWORD)v11 + 3) & 0xFFFFFFFC) + a1) = 1;
    ++*(_DWORD *)(a1 + 8);
  }
  else
  {
    v10 = -1073741811;
  }
LABEL_10:
  v13 = RtlNtStatusToDosError(v10);
  v8 = v13;
  if ( v13 > 0 )
    v8 = (unsigned __int16)v13 | 0x80070000;
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( (unsigned int)v4 < 0x18 )
    goto LABEL_14;
  if ( *(_WORD *)(a1 + 14) > 1u )
  {
    if ( (unsigned int)v4 < 0x20 || (v15 = *(unsigned int *)(a1 + 8), ((v15 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 > v4) )
    {
LABEL_14:
      v14 = -1073741789;
      goto LABEL_22;
    }
    v16 = ((_DWORD)v15 + 3) & 0xFFFFFFFC;
    *(_DWORD *)(a1 + 8) = v16;
    if ( *(_WORD *)(a1 + 24) )
      *(_WORD *)(a1 + 12) |= 1u;
    *(_DWORD *)(a1 + 24) = 131080;
    v14 = 0;
    *(_DWORD *)(a1 + 28) = v16;
    *(_WORD *)(v16 + a1) = a4;
    *(_DWORD *)(a1 + 8) += 2;
  }
  else
  {
    v14 = -1073741811;
  }
LABEL_22:
  v17 = RtlNtStatusToDosError(v14);
  v8 = v17;
  if ( v17 > 0 )
    v8 = (unsigned __int16)v17 | 0x80070000;
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( (unsigned int)v4 < 0x18 )
    goto LABEL_26;
  if ( *(_WORD *)(a1 + 14) > 4u )
  {
    if ( (unsigned int)v4 < 0x38 || (v19 = *(unsigned int *)(a1 + 8), ((v19 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 > v4) )
    {
LABEL_26:
      v18 = -1073741789;
      goto LABEL_34;
    }
    v20 = *(_QWORD *)(a3 + 8);
    v21 = ((_DWORD)v19 + 3) & 0xFFFFFFFC;
    *(_DWORD *)(a1 + 8) = v21;
    if ( *(_WORD *)(a1 + 48) )
      *(_WORD *)(a1 + 12) |= 1u;
    *(_DWORD *)(a1 + 48) = 524294;
    *(_DWORD *)(a1 + 52) = v21;
    *(_QWORD *)(v21 + a1) = v20;
    v18 = 0;
    *(_DWORD *)(a1 + 8) += 8;
  }
  else
  {
    v18 = -1073741811;
  }
LABEL_34:
  v22 = RtlNtStatusToDosError(v18);
  v8 = v22;
  if ( v22 > 0 )
    v8 = (unsigned __int16)v22 | 0x80070000;
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( (unsigned int)v4 < 0x18 )
    goto LABEL_38;
  if ( *(_WORD *)(a1 + 14) > 7u )
  {
    if ( (unsigned int)v4 < 0x50 || (v24 = *(unsigned int *)(a1 + 8), ((v24 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 > v4) )
    {
LABEL_38:
      v23 = -1073741789;
      goto LABEL_46;
    }
    v25 = *(_QWORD *)(a3 + 16);
    v26 = ((_DWORD)v24 + 3) & 0xFFFFFFFC;
    *(_DWORD *)(a1 + 8) = v26;
    if ( *(_WORD *)(a1 + 72) )
      *(_WORD *)(a1 + 12) |= 1u;
    *(_DWORD *)(a1 + 72) = 524294;
    *(_DWORD *)(a1 + 76) = v26;
    *(_QWORD *)(v26 + a1) = v25;
    v23 = 0;
    *(_DWORD *)(a1 + 8) += 8;
  }
  else
  {
    v23 = -1073741811;
  }
LABEL_46:
  v27 = RtlNtStatusToDosError(v23);
  v8 = v27;
  if ( v27 > 0 )
    v8 = (unsigned __int16)v27 | 0x80070000;
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( *(_DWORD *)a3 >= 0x20u )
  {
    v28 = *(_QWORD *)(a3 + 24);
    if ( v28 )
    {
      if ( (unsigned int)v4 < 0x18 )
      {
LABEL_52:
        v29 = -1073741789;
        goto LABEL_62;
      }
      if ( *(_WORD *)(a1 + 14) > 8u )
      {
        if ( (unsigned int)v4 < 0x58 )
          goto LABEL_52;
        v30 = *(unsigned int *)(a1 + 8);
        if ( ((v30 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 130 > v4 )
          goto LABEL_52;
        if ( *(_WORD *)(a1 + 80) )
          *(_WORD *)(a1 + 12) |= 1u;
        v31 = (v30 + 3) & 0xFFFFFFFC;
        *(_DWORD *)(a1 + 8) = v31;
        *(_DWORD *)(a1 + 80) = 8519697;
        v32 = v31 + a1;
        *(_DWORD *)(a1 + 84) = v31;
        if ( v32 != v28 )
        {
          *(_OWORD *)v32 = *(_OWORD *)v28;
          *(_OWORD *)(v32 + 16) = *(_OWORD *)(v28 + 16);
          *(_OWORD *)(v32 + 32) = *(_OWORD *)(v28 + 32);
          *(_OWORD *)(v32 + 48) = *(_OWORD *)(v28 + 48);
          *(_OWORD *)(v32 + 64) = *(_OWORD *)(v28 + 64);
          *(_OWORD *)(v32 + 80) = *(_OWORD *)(v28 + 80);
          *(_OWORD *)(v32 + 96) = *(_OWORD *)(v28 + 96);
          *(_OWORD *)(v32 + 112) = *(_OWORD *)(v28 + 112);
          *(_WORD *)(v32 + 128) = *(_WORD *)(v28 + 128);
        }
        v29 = 0;
        *(_DWORD *)(a1 + 8) += *(unsigned __int16 *)(a1 + 82);
      }
      else
      {
        v29 = -1073741811;
      }
LABEL_62:
      v33 = RtlNtStatusToDosError(v29);
      v8 = v33;
      if ( v33 > 0 )
        v8 = (unsigned __int16)v33 | 0x80070000;
      if ( v8 < 0 )
        return (unsigned int)v8;
    }
  }
  if ( *(_DWORD *)a3 < 0x28u || (v34 = *(unsigned __int16 **)(a3 + 32)) == 0 )
  {
LABEL_81:
    if ( a4 == 513 )
    {
      if ( *(_DWORD *)a3 < 0x30u )
        v41 = 0;
      else
        v41 = *(_QWORD *)(a3 + 40);
      if ( (unsigned int)v4 >= 0x18 )
      {
        if ( *(_WORD *)(a1 + 14) > 0xCu )
        {
          if ( (unsigned int)v4 >= 0x78 )
          {
            v42 = *(unsigned int *)(a1 + 8);
            if ( ((v42 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= v4 )
            {
              v43 = ((_DWORD)v42 + 3) & 0xFFFFFFFC;
              *(_DWORD *)(a1 + 8) = v43;
              if ( *(_WORD *)(a1 + 112) )
                *(_WORD *)(a1 + 12) |= 1u;
              *(_DWORD *)(a1 + 112) = 524294;
              v9 = 0;
              *(_DWORD *)(a1 + 116) = v43;
              *(_QWORD *)(v43 + a1) = v41;
              *(_DWORD *)(a1 + 8) += 8;
            }
          }
        }
        else
        {
          v9 = -1073741811;
        }
      }
      v44 = RtlNtStatusToDosError(v9);
      v8 = v44;
      if ( v44 > 0 )
        return (unsigned __int16)v44 | 0x80070000;
    }
    return (unsigned int)v8;
  }
  if ( (unsigned int)v4 < 0x18 )
    goto LABEL_68;
  if ( *(_WORD *)(a1 + 14) > 9u )
  {
    if ( (unsigned int)v4 < 0x60
      || (v36 = *(unsigned int *)(a1 + 8), v37 = *v34, v37 + ((v36 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v4) )
    {
LABEL_68:
      v35 = -1073741789;
      goto LABEL_78;
    }
    if ( *(_WORD *)(a1 + 88) )
      *(_WORD *)(a1 + 12) |= 1u;
    v38 = ((_DWORD)v36 + 3) & 0xFFFFFFFC;
    *(_DWORD *)(a1 + 8) = v38;
    *(_DWORD *)(a1 + 92) = v38;
    v39 = (unsigned __int16 *)(a1 + v38);
    *(_WORD *)(a1 + 88) = 17;
    *(_WORD *)(a1 + 90) = v37;
    if ( v39 != v34 )
      memcpy_0(v39, v34, v37);
    v35 = 0;
    *(_DWORD *)(a1 + 8) += *(unsigned __int16 *)(a1 + 90);
  }
  else
  {
    v35 = -1073741811;
  }
LABEL_78:
  v40 = RtlNtStatusToDosError(v35);
  v8 = v40;
  if ( v40 > 0 )
    v8 = (unsigned __int16)v40 | 0x80070000;
  if ( v8 >= 0 )
    goto LABEL_81;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800092f8  push    rbx
0x1800092fa  push    rbp
0x1800092fb  push    rsi
0x1800092fc  push    rdi
0x1800092fd  push    r12
0x1800092ff  push    r13
0x180009301  push    r14
0x180009303  push    r15
0x180009305  sub     rsp, 28h
0x180009309  mov     esi, edx
0x18000930b  mov     rbx, rcx
0x18000930e  mov     edx, 0C8h
0x180009313  mov     r13d, 80070000h
0x180009319  cmp     esi, edx
0x18000931b  movzx   r15d, r9w
0x18000931f  mov     rbp, r8
0x180009322  sbb     ecx, ecx
0x180009324  and     ecx, 57h
0x180009327  mov     eax, ecx
0x180009329  or      eax, r13d
0x18000932c  cmp     esi, edx
0x18000932e  cmovb   ecx, eax
0x180009331  xor     r12d, r12d
0x180009334  test    ecx, ecx
0x180009336  js      loc_1800097B7
0x18000933c  mov     [rbx+8], edx
0x18000933f  lea     rcx, [rbx+10h]; void *
0x180009343  xor     edx, edx; Val
0x180009345  mov     qword ptr [rbx], 706D6C43h
0x18000934c  mov     r8d, 0B8h; Size
0x180009352  mov     dword ptr [rbx+0Ch], 170000h
0x180009359  call    memset_0
0x18000935e  lea     r9d, [r12+1]
0x180009363  mov     edi, 0C0000023h
0x180009368  cmp     esi, 18h
0x18000936b  jnb     short loc_180009371
0x18000936d  mov     ecx, edi
0x18000936f  jmp     short loc_1800093B2
0x180009371  cmp     r12w, [rbx+0Eh]
0x180009376  jb      short loc_18000937F
0x180009378  mov     ecx, 0C000000Dh
0x18000937d  jmp     short loc_1800093B2
0x18000937f  mov     edx, [rbx+8]
0x180009382  lea     rcx, [rdx+3]
0x180009386  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18000938a  add     rcx, r9
0x18000938d  cmp     rcx, rsi
0x180009390  ja      short loc_18000936D
0x180009392  lea     eax, [rdx+3]
0x180009395  and     eax, 0FFFFFFFCh
0x180009398  mov     ecx, eax
0x18000939a  mov     [rbx+8], ecx
0x18000939d  mov     [rbx+14h], ecx
0x1800093a0  mov     ecx, r12d; Status
0x1800093a3  mov     dword ptr [rbx+10h], 10007h
0x1800093aa  mov     [rax+rbx], r9b
0x1800093ae  add     [rbx+8], r9d
0x1800093b2  call    cs:__imp_RtlNtStatusToDosError
0x1800093b9  nop     dword ptr [rax+rax+00h]
0x1800093be  mov     ecx, eax
0x1800093c0  test    eax, eax
0x1800093c2  jle     short loc_1800093CA
0x1800093c4  movzx   ecx, ax
0x1800093c7  or      ecx, r13d
0x1800093ca  test    ecx, ecx
0x1800093cc  js      loc_1800097B7
0x1800093d2  mov     r13d, 8
0x1800093d8  lea     r14d, [r13-7]
0x1800093dc  cmp     esi, 18h
0x1800093df  jnb     short loc_1800093E5
0x1800093e1  mov     ecx, edi
0x1800093e3  jmp     short loc_18000943C
0x1800093e5  cmp     r14w, [rbx+0Eh]
0x1800093ea  jb      short loc_1800093F3
0x1800093ec  mov     ecx, 0C000000Dh
0x1800093f1  jmp     short loc_18000943C
0x1800093f3  cmp     esi, 20h ; ' '
0x1800093f6  jb      short loc_1800093E1
0x1800093f8  mov     edx, [rbx+8]
0x1800093fb  mov     r8d, 2
0x180009401  lea     rcx, [rdx+3]
0x180009405  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180009409  add     rcx, r8
0x18000940c  cmp     rcx, rsi
0x18000940f  ja      short loc_1800093E1
0x180009411  lea     eax, [rdx+3]
0x180009414  and     eax, 0FFFFFFFCh
0x180009417  mov     [rbx+8], eax
0x18000941a  cmp     [rbx+18h], r12w
0x18000941f  jz      short loc_180009426
0x180009421  or      [rbx+0Ch], r14w
0x180009426  mov     dword ptr [rbx+18h], 20008h
0x18000942d  mov     ecx, r12d; Status
0x180009430  mov     [rbx+1Ch], eax
0x180009433  mov     [rax+rbx], r15w
0x180009438  add     [rbx+8], r8d
0x18000943c  call    cs:__imp_RtlNtStatusToDosError
0x180009443  nop     dword ptr [rax+rax+00h]
0x180009448  mov     ecx, eax
0x18000944a  test    eax, eax
0x18000944c  jle     short loc_180009457
0x18000944e  movzx   ecx, ax
0x180009451  or      ecx, 80070000h
0x180009457  test    ecx, ecx
0x180009459  js      loc_1800097B7
0x18000945f  cmp     esi, 18h
0x180009462  jnb     short loc_180009468
0x180009464  mov     ecx, edi
0x180009466  jmp     short loc_1800094C0
0x180009468  mov     eax, 4
0x18000946d  cmp     ax, [rbx+0Eh]
0x180009471  jb      short loc_18000947A
0x180009473  mov     ecx, 0C000000Dh
0x180009478  jmp     short loc_1800094C0
0x18000947a  cmp     esi, 38h ; '8'
0x18000947d  jb      short loc_180009464
0x18000947f  mov     edx, [rbx+8]
0x180009482  lea     rcx, [rdx+3]
0x180009486  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18000948a  add     rcx, r13
0x18000948d  cmp     rcx, rsi
0x180009490  ja      short loc_180009464
0x180009492  mov     rcx, [rbp+8]
0x180009496  lea     eax, [rdx+3]
0x180009499  and     eax, 0FFFFFFFCh
0x18000949c  mov     [rbx+8], eax
0x18000949f  cmp     [rbx+30h], r12w
0x1800094a4  jz      short loc_1800094AB
0x1800094a6  or      [rbx+0Ch], r14w
0x1800094ab  mov     dword ptr [rbx+30h], 80006h
0x1800094b2  mov     [rbx+34h], eax
0x1800094b5  mov     [rax+rbx], rcx
0x1800094b9  mov     ecx, r12d; Status
0x1800094bc  add     [rbx+8], r13d
0x1800094c0  call    cs:__imp_RtlNtStatusToDosError
0x1800094c7  nop     dword ptr [rax+rax+00h]
0x1800094cc  mov     ecx, eax
0x1800094ce  test    eax, eax
0x1800094d0  jle     short loc_1800094DB
0x1800094d2  movzx   ecx, ax
0x1800094d5  or      ecx, 80070000h
0x1800094db  test    ecx, ecx
0x1800094dd  js      loc_1800097B7
0x1800094e3  cmp     esi, 18h
0x1800094e6  jnb     short loc_1800094EC
0x1800094e8  mov     ecx, edi
0x1800094ea  jmp     short loc_180009544
0x1800094ec  mov     eax, 7
0x1800094f1  cmp     ax, [rbx+0Eh]
0x1800094f5  jb      short loc_1800094FE
0x1800094f7  mov     ecx, 0C000000Dh
0x1800094fc  jmp     short loc_180009544
0x1800094fe  cmp     esi, 50h ; 'P'
0x180009501  jb      short loc_1800094E8
0x180009503  mov     edx, [rbx+8]
0x180009506  lea     rcx, [rdx+3]
0x18000950a  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18000950e  add     rcx, r13
0x180009511  cmp     rcx, rsi
0x180009514  ja      short loc_1800094E8
0x180009516  mov     rcx, [rbp+10h]
0x18000951a  lea     eax, [rdx+3]
0x18000951d  and     eax, 0FFFFFFFCh
0x180009520  mov     [rbx+8], eax
0x180009523  cmp     [rbx+48h], r12w
0x180009528  jz      short loc_18000952F
0x18000952a  or      [rbx+0Ch], r14w
0x18000952f  mov     dword ptr [rbx+48h], 80006h
0x180009536  mov     [rbx+4Ch], eax
0x180009539  mov     [rax+rbx], rcx
0x18000953d  mov     ecx, r12d; Status
0x180009540  add     [rbx+8], r13d
0x180009544  call    cs:__imp_RtlNtStatusToDosError
0x18000954b  nop     dword ptr [rax+rax+00h]
0x180009550  mov     ecx, eax
0x180009552  test    eax, eax
0x180009554  jle     short loc_18000955F
0x180009556  movzx   ecx, ax
0x180009559  or      ecx, 80070000h
0x18000955f  test    ecx, ecx
0x180009561  js      loc_1800097B7
0x180009567  cmp     dword ptr [rbp+0], 20h ; ' '
0x18000956b  mov     r14d, 11h
0x180009571  jb      loc_18000966F
0x180009577  mov     rdx, [rbp+18h]
0x18000957b  test    rdx, rdx
0x18000957e  jz      loc_18000966F
0x180009584  cmp     esi, 18h
0x180009587  jnb     short loc_180009590
0x180009589  mov     ecx, edi
0x18000958b  jmp     loc_18000964C
0x180009590  cmp     r13w, [rbx+0Eh]
0x180009595  jb      short loc_1800095A1
0x180009597  mov     ecx, 0C000000Dh
0x18000959c  jmp     loc_18000964C
0x1800095a1  cmp     esi, 58h ; 'X'
0x1800095a4  jb      short loc_180009589
0x1800095a6  mov     r8d, [rbx+8]
0x1800095aa  lea     rcx, [r8+3]
0x1800095ae  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800095b2  add     rcx, 82h
0x1800095b9  cmp     rcx, rsi
0x1800095bc  ja      short loc_180009589
0x1800095be  cmp     [rbx+50h], r12w
0x1800095c3  jz      short loc_1800095CE
0x1800095c5  mov     eax, 1
0x1800095ca  or      [rbx+0Ch], ax
0x1800095ce  lea     eax, [r8+3]
0x1800095d2  and     eax, 0FFFFFFFCh
0x1800095d5  mov     ecx, eax
0x1800095d7  mov     [rbx+8], ecx
0x1800095da  mov     dword ptr [rbx+50h], 820011h
0x1800095e1  lea     r8, [rax+rbx]
0x1800095e5  mov     [rbx+54h], ecx
0x1800095e8  cmp     r8, rdx
0x1800095eb  jz      short loc_180009642
0x1800095ed  movups  xmm0, xmmword ptr [rdx]
0x1800095f0  movups  xmmword ptr [r8], xmm0
0x1800095f4  movups  xmm1, xmmword ptr [rdx+10h]
0x1800095f8  movups  xmmword ptr [r8+10h], xmm1
0x1800095fd  movups  xmm0, xmmword ptr [rdx+20h]
0x180009601  movups  xmmword ptr [r8+20h], xmm0
0x180009606  movups  xmm1, xmmword ptr [rdx+30h]
0x18000960a  movups  xmmword ptr [r8+30h], xmm1
0x18000960f  movups  xmm0, xmmword ptr [rdx+40h]
0x180009613  movups  xmmword ptr [r8+40h], xmm0
0x180009618  movups  xmm1, xmmword ptr [rdx+50h]
0x18000961c  movups  xmmword ptr [r8+50h], xmm1
0x180009621  movups  xmm0, xmmword ptr [rdx+60h]
0x180009625  movups  xmmword ptr [r8+60h], xmm0
0x18000962a  movups  xmm1, xmmword ptr [rdx+70h]
0x18000962e  movups  xmmword ptr [r8+70h], xmm1
0x180009633  movzx   eax, word ptr [rdx+80h]
0x18000963a  mov     [r8+80h], ax
0x180009642  movzx   eax, word ptr [rbx+52h]
0x180009646  mov     ecx, r12d; Status
0x180009649  add     [rbx+8], eax
0x18000964c  call    cs:__imp_RtlNtStatusToDosError
0x180009653  nop     dword ptr [rax+rax+00h]
0x180009658  mov     ecx, eax
0x18000965a  test    eax, eax
0x18000965c  jle     short loc_180009667
0x18000965e  movzx   ecx, ax
0x180009661  or      ecx, 80070000h
0x180009667  test    ecx, ecx
0x180009669  js      loc_1800097B7
0x18000966f  cmp     dword ptr [rbp+0], 28h ; '('
0x180009673  jb      loc_18000971F
0x180009679  mov     rdx, [rbp+20h]; Src
0x18000967d  test    rdx, rdx
0x180009680  jz      loc_18000971F
0x180009686  cmp     esi, 18h
0x180009689  jnb     short loc_18000968F
0x18000968b  mov     ecx, edi
0x18000968d  jmp     short loc_1800096FC
0x18000968f  mov     eax, 9
0x180009694  cmp     ax, [rbx+0Eh]
0x180009698  jb      short loc_1800096A1
0x18000969a  mov     ecx, 0C000000Dh
0x18000969f  jmp     short loc_1800096FC
0x1800096a1  cmp     esi, 60h ; '`'
0x1800096a4  jb      short loc_18000968B
0x1800096a6  mov     r9d, [rbx+8]
0x1800096aa  movzx   r8d, word ptr [rdx]; Size
0x1800096ae  lea     rcx, [r9+3]
0x1800096b2  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800096b6  add     rcx, r8
0x1800096b9  cmp     rcx, rsi
0x1800096bc  ja      short loc_18000968B
0x1800096be  cmp     [rbx+58h], r12w
0x1800096c3  jz      short loc_1800096CE
0x1800096c5  mov     eax, 1
0x1800096ca  or      [rbx+0Ch], ax
0x1800096ce  lea     ecx, [r9+3]
0x1800096d2  and     ecx, 0FFFFFFFCh
0x1800096d5  mov     [rbx+8], ecx
0x1800096d8  mov     [rbx+5Ch], ecx
0x1800096db  add     rcx, rbx; void *
0x1800096de  mov     [rbx+58h], r14w
0x1800096e3  mov     [rbx+5Ah], r8w
0x1800096e8  cmp     rcx, rdx
0x1800096eb  jz      short loc_1800096F2
0x1800096ed  call    memcpy_0
0x1800096f2  movzx   eax, word ptr [rbx+5Ah]
0x1800096f6  mov     ecx, r12d; Status
0x1800096f9  add     [rbx+8], eax
0x1800096fc  call    cs:__imp_RtlNtStatusToDosError
0x180009703  nop     dword ptr [rax+rax+00h]
0x180009708  mov     ecx, eax
0x18000970a  test    eax, eax
0x18000970c  jle     short loc_180009717
0x18000970e  movzx   ecx, ax
0x180009711  or      ecx, 80070000h
0x180009717  test    ecx, ecx
0x180009719  js      loc_1800097B7
0x18000971f  mov     eax, 201h
0x180009724  cmp     r15w, ax
0x180009728  jnz     loc_1800097B7
0x18000972e  cmp     dword ptr [rbp+0], 30h ; '0'
0x180009732  jb      short loc_18000973A
  ... truncated ...
```
