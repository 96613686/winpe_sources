# MRxSmbStuffSMB

- ea: `0x140046380`
- end: `0x140046a3f`
- name: `MRxSmbStuffSMB`
- size: `1727`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `27`
- callee_count: `2`
- tags: ``

## callers

- `0x14002d870`
- `0x14002ddd0`
- `0x14002dee8`
- `0x14002ea60`
- `0x14002ec20`
- `0x140033fa8`
- `0x140034058`
- `0x140034470`
- `0x1400360f4`
- `0x1400361b0`
- `0x140036260`
- `0x14003630c`
- `0x14003652c`
- `0x140039b9c`
- `0x140039ee0`
- `0x14003a028`
- `0x14003a120`
- `0x14003a204`
- `0x14003a394`
- `0x14003a494`
- `0x14003b07c`
- `0x14003b4c8`
- `0x14003b980`
- `0x14003c230`
- `0x14003c2e8`
- `0x140045890`
- `0x1400495b4`

## callees

- `0x1400166c0`
- `0x140046380`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeStringToOemString` at `0x140046931`
- `ntoskrnl!RtlUpcaseUnicodeStringToOemString` at `0x140046931`
- `ntoskrnl!RtlUnicodeStringToOemString` at `0x14004693f`
- `ntoskrnl!RtlUnicodeStringToOemString` at `0x14004693f`

## pseudocode

```c
__int64 __fastcall MRxSmbStuffSMB(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r15
  int *v5; // rsi
  int v7; // r14d
  char *v8; // rbx
  char v9; // al
  _BYTE *v10; // rdx
  _WORD *v12; // rdx
  _DWORD *v13; // rdx
  char *v14; // rcx
  const UNICODE_STRING *v15; // rdx
  char *v16; // r8
  size_t Length; // r8
  PWSTR Buffer; // rdx
  _BYTE *v19; // rdx
  _BYTE *v20; // rdx
  _BYTE *v21; // rdx
  _DWORD *v22; // r8
  _DWORD *v23; // rdx
  unsigned __int64 v24; // rdx
  _WORD *v25; // rdx
  _WORD *v26; // rdx
  _BYTE *v27; // rcx
  unsigned __int64 v28; // rdx
  int v29; // ecx
  _BYTE *v30; // rdx
  _BYTE *v31; // r8
  _BYTE *v32; // rcx
  unsigned __int64 v33; // rdx
  _QWORD *v34; // rax
  _BYTE *v35; // rcx
  char *v36; // rdx
  _BYTE *v37; // r8
  char v38; // al
  _QWORD *v39; // rcx
  __int64 v40; // rdx
  char *v41; // rdx
  __int64 v42; // rax
  char *v43; // rcx
  __int64 v44; // rax
  size_t v45; // r8
  _BYTE *v46; // r8
  __int16 v47; // r8
  __int16 v48; // cx
  CHAR *v49; // rax
  NTSTATUS v50; // eax
  _BYTE *v51; // rdx
  unsigned __int16 *v52; // rdx
  char *v53; // r8
  _WORD *v54; // rdx
  __int64 v55; // r9
  char *v56; // rcx
  struct _STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF
  __int64 v59; // [rsp+88h] [rbp+50h] BYREF
  __int64 v60; // [rsp+90h] [rbp+58h]
  __int64 v61; // [rsp+98h] [rbp+60h]

  v59 = a2;
  v60 = a3;
  v61 = a4;
  v4 = *(_QWORD *)(a1 + 32);
  v5 = (int *)&v59;
  *(_QWORD *)&DestinationString.Length = 0;
  v7 = 1;
  while ( 1 )
  {
    switch ( v7 )
    {
      case 1:
LABEL_3:
        v8 = *(char **)v5;
        v5 += 2;
        while ( 1 )
        {
          v9 = *v8;
          if ( !*v8 )
            goto LABEL_27;
          if ( v9 == 119 )
            break;
          if ( v9 == 88 )
          {
            v10 = *(_BYTE **)(a1 + 80);
            if ( (unsigned __int64)v10 >= *(_QWORD *)(a1 + 40) - 4LL )
              return 2147483653LL;
            *v10 = -52;
            *(_DWORD *)++*(_QWORD *)(a1 + 80) = -555876097;
            *(_QWORD *)(a1 + 80) += 4LL;
            ++v8;
          }
          else if ( v9 == 100 )
          {
LABEL_14:
            v5 += 2;
            if ( v7 == 2 )
              goto LABEL_12;
            v13 = *(_DWORD **)(a1 + 80);
            if ( (unsigned __int64)v13 >= *(_QWORD *)(a1 + 40) - 4LL )
              return 2147483653LL;
            *v13 = *(v5 - 2);
            *(_QWORD *)(a1 + 80) += 4LL;
            ++v8;
          }
          else
          {
            switch ( *v8 )
            {
              case '!':
                if ( v7 == 2 )
                  break;
                **(_WORD **)(a1 + 96) = *(_WORD *)(a1 + 80) - *(_WORD *)(a1 + 96) - 2;
                return 0;
              case '0':
                v19 = *(_BYTE **)(a1 + 80);
                if ( (unsigned __int64)v19 >= *(_QWORD *)(a1 + 40) - 1LL )
                  return 2147483653LL;
                *v19 = -52;
                ++*(_QWORD *)(a1 + 80);
                break;
              case '1':
                v32 = *(_BYTE **)(a1 + 80);
                v33 = (unsigned __int64)(v32 + 1) & 0xFFFFFFFFFFFFFFFEuLL;
                *(_QWORD *)(a1 + 80) = v33;
                if ( v33 >= *(_QWORD *)(a1 + 40) )
                  return 2147483653LL;
                if ( v32 != (_BYTE *)v33 )
                {
                  do
                    *v32++ = -18;
                  while ( v32 != *(_BYTE **)(a1 + 80) );
                }
                break;
              case '4':
              case '>':
              case 'z':
                v5 += 2;
                if ( v7 == 2 )
                  break;
                v15 = (const UNICODE_STRING *)*((_QWORD *)v5 - 1);
                if ( v9 == 52 )
                {
                  v46 = *(_BYTE **)(a1 + 80);
                  if ( (unsigned __int64)v46 >= *(_QWORD *)(a1 + 40) - 1LL )
                    return 2147483653LL;
                  *v46 = 4;
                  ++*(_QWORD *)(a1 + 80);
                }
                else if ( v9 == 62 )
                {
                  *(_QWORD *)(a1 + 80) += -1 - (((__int64)*(__int16 *)(v4 + 10) >> 63) & 1);
                }
                v47 = *(_WORD *)(v4 + 10);
                if ( v47 >= 0 )
                {
                  v48 = ~*(_WORD *)(a1 + 80);
                  DestinationString = 0;
                  v49 = *(CHAR **)(a1 + 80);
                  DestinationString.MaximumLength = *(_WORD *)(a1 + 40) + v48;
                  DestinationString.Length = DestinationString.MaximumLength;
                  LOBYTE(v48) = *(_BYTE *)(v4 + 9) >> 3;
                  DestinationString.Buffer = v49;
                  if ( (((v47 & 1) == 0) & (unsigned __int8)v48) != 0 )
                    v50 = RtlUpcaseUnicodeStringToOemString(&DestinationString, v15, 0);
                  else
                    v50 = RtlUnicodeStringToOemString(&DestinationString, v15, 0);
                  if ( v50 < 0 )
                    return 2147483653LL;
                  v51 = (_BYTE *)(*(_QWORD *)(a1 + 80) + DestinationString.Length);
                  *(_QWORD *)(a1 + 80) = v51 + 1;
                  *v51 = 0;
                }
                else
                {
                  v14 = *(char **)(a1 + 80);
                  if ( ((unsigned __int8)v14 & 1) != 0 )
LABEL_78:
                    *(_QWORD *)(a1 + 80) = ++v14;
LABEL_22:
                  v16 = &v14[v15->Length + 2];
                  *(_QWORD *)(a1 + 80) = v16;
                  if ( (unsigned __int64)v16 >= *(_QWORD *)(a1 + 40) )
                    return 2147483653LL;
                  Length = v15->Length;
                  Buffer = v15->Buffer;
LABEL_24:
                  memmove(v14, Buffer, Length);
                  *(_WORD *)(*(_QWORD *)(a1 + 80) - 2LL) = 0;
                }
                break;
              case '5':
                **(_WORD **)(a1 + 104) = *(_WORD *)(a1 + 80) - v4;
                break;
              case '6':
                **(_WORD **)(a1 + 112) = *(_WORD *)(a1 + 80) - v4;
                break;
              case '?':
                v5 += 2;
                if ( *(v5 - 2) )
                  break;
                return 0;
              case 'A':
              case 'a':
                v41 = *(char **)v5;
                v5 += 2;
                v42 = -1;
                do
                  ++v42;
                while ( v41[v42] );
                v43 = *(char **)(a1 + 80);
                v44 = (unsigned int)(v42 + 1);
                v45 = (unsigned int)v44;
                *(_QWORD *)(a1 + 80) = &v43[v44];
                if ( (unsigned __int64)&v43[v44] >= *(_QWORD *)(a1 + 40) )
                  return 2147483653LL;
                goto LABEL_69;
              case 'B':
              case 'b':
                v24 = *(_QWORD *)(a1 + 80);
                if ( v24 >= *(_QWORD *)(a1 + 40) - 2LL )
                  return 2147483653LL;
                **(_BYTE **)(a1 + 88) = (__int64)(v24 - *(_QWORD *)(a1 + 88)) >> 1;
                **(_WORD **)(a1 + 80) = -1330;
                *(_QWORD *)(a1 + 96) = *(_QWORD *)(a1 + 80);
                *(_QWORD *)(a1 + 80) += 2LL;
                break;
              case 'D':
                goto LABEL_14;
              case 'L':
              case 'l':
                v5 += 2;
                if ( v7 == 2 )
                  break;
                v22 = *(_DWORD **)(a1 + 80);
                if ( (unsigned __int64)v22 >= *(_QWORD *)(a1 + 40) - 8LL )
                  return 2147483653LL;
                v23 = (_DWORD *)*((_QWORD *)v5 - 1);
                *v22 = *v23;
                **(_DWORD **)(a1 + 80) = v23[1];
                *(_QWORD *)(a1 + 80) += 8LL;
                break;
              case 'M':
              case 'm':
                if ( v7 == 2 )
                  break;
                v21 = *(_BYTE **)(a1 + 80);
                if ( (unsigned __int64)v21 >= *(_QWORD *)(a1 + 40) - 1LL )
                  return 2147483653LL;
                *v21 = 0;
                ++*(_QWORD *)(a1 + 80);
                break;
              case 'N':
              case 'n':
                v5 += 2;
                if ( (*(_DWORD *)(a1 + 128) & 0x8000) == 0 )
                  break;
                v54 = *(_WORD **)(a1 + 80);
                v55 = *((_QWORD *)v5 - 1);
                if ( ((unsigned __int8)v54 & 1) != 0 )
                {
                  v54 = (_WORD *)((char *)v54 + 1);
                  *(_QWORD *)(a1 + 80) = v54;
                }
                v56 = (char *)v54 + *(unsigned __int16 *)(v55 + 216) + 4;
                *(_QWORD *)(a1 + 80) = v56;
                if ( (unsigned __int64)v56 >= *(_QWORD *)(a1 + 40) )
                  return 2147483653LL;
                *v54 = 92;
                v14 = (char *)(v54 + 1);
                Length = *(unsigned __int16 *)(v55 + 216);
                Buffer = *(PWSTR *)(v55 + 224);
                goto LABEL_24;
              case 'P':
              case 'p':
                v26 = *(_WORD **)(a1 + 80);
                if ( (unsigned __int64)v26 >= *(_QWORD *)(a1 + 40) - 2LL )
                  return 2147483653LL;
                *v26 = -20225;
                *(_QWORD *)(a1 + 112) = *(_QWORD *)(a1 + 80);
                *(_QWORD *)(a1 + 80) += 2LL;
                break;
              case 'Q':
              case 'q':
                v25 = *(_WORD **)(a1 + 80);
                if ( (unsigned __int64)v25 >= *(_QWORD *)(a1 + 40) - 2LL )
                  return 2147483653LL;
                *v25 = -12033;
                *(_QWORD *)(a1 + 104) = *(_QWORD *)(a1 + 80);
                *(_QWORD *)(a1 + 80) += 2LL;
                break;
              case 'R':
              case 'r':
                v39 = v5 + 2;
                v40 = (unsigned int)v5[2];
                v5 += 4;
                *(_QWORD *)*(v39 - 1) = *(_QWORD *)(a1 + 80);
                *(_QWORD *)(a1 + 80) += v40;
                if ( *(_QWORD *)(a1 + 80) < *(_QWORD *)(a1 + 40) )
                  break;
                return 2147483653LL;
              case 'S':
                v27 = *(_BYTE **)(a1 + 80);
                v28 = (unsigned __int64)(v27 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
                *(_QWORD *)(a1 + 80) = v28;
                if ( v28 >= *(_QWORD *)(a1 + 40) )
                  return 2147483653LL;
                if ( v27 != (_BYTE *)v28 )
                {
                  do
                    *v27++ = -18;
                  while ( v27 != *(_BYTE **)(a1 + 80) );
                }
                break;
              case 'U':
              case 'u':
                v14 = *(char **)(a1 + 80);
                v5 += 2;
                v15 = (const UNICODE_STRING *)*((_QWORD *)v5 - 1);
                if ( ((unsigned __int8)v14 & 1) == 0 )
                  goto LABEL_22;
                goto LABEL_78;
              case 'V':
              case 'v':
                v43 = *(char **)(a1 + 80);
                v5 += 2;
                v52 = (unsigned __int16 *)*((_QWORD *)v5 - 1);
                if ( ((unsigned __int8)v43 & 1) != 0 )
                  *(_QWORD *)(a1 + 80) = ++v43;
                v53 = &v43[*v52];
                *(_QWORD *)(a1 + 80) = v53;
                if ( (unsigned __int64)v53 >= *(_QWORD *)(a1 + 40) )
                  return 2147483653LL;
                v45 = *v52;
                v41 = (char *)*((_QWORD *)v52 + 1);
LABEL_69:
                memmove(v43, v41, v45);
                break;
              case 'W':
                goto LABEL_9;
              case 'Y':
              case 'y':
                v5 += 2;
                if ( v7 == 2 )
                  break;
                v20 = *(_BYTE **)(a1 + 80);
                if ( (unsigned __int64)v20 >= *(_QWORD *)(a1 + 40) - 1LL )
                  return 2147483653LL;
                *v20 = *((_BYTE *)v5 - 8);
                ++*(_QWORD *)(a1 + 80);
                break;
              case 'c':
                v34 = v5 + 2;
                v5 += 4;
                if ( v7 == 2 )
                  break;
                v35 = *(_BYTE **)(a1 + 80);
                v36 = (char *)*((_QWORD *)v5 - 1);
                v37 = &v35[*((unsigned int *)v34 - 2)];
                *(_QWORD *)(a1 + 80) = v37;
                if ( (unsigned __int64)v37 >= *(_QWORD *)(a1 + 40) )
                  return 2147483653LL;
                if ( v35 != v37 )
                {
                  do
                  {
                    v38 = *v36++;
                    *v35++ = v38;
                  }
                  while ( v35 != *(_BYTE **)(a1 + 80) );
                }
                break;
              case 's':
                v29 = *v5;
                v5 += 2;
                v30 = *(_BYTE **)(a1 + 80);
                v31 = (_BYTE *)(-v29 & (unsigned __int64)&v30[v29 - 1]);
                *(_QWORD *)(a1 + 80) = v31;
                if ( (unsigned __int64)v31 >= *(_QWORD *)(a1 + 40) )
                  return 2147483653LL;
                if ( v30 != v31 )
                {
                  do
                    *v30++ = -18;
                  while ( v30 != *(_BYTE **)(a1 + 80) );
                }
                break;
              default:
                break;
            }
LABEL_12:
            ++v8;
          }
        }
LABEL_9:
        v5 += 2;
        if ( v7 != 2 )
        {
          v12 = *(_WORD **)(a1 + 80);
          if ( (unsigned __int64)v12 >= *(_QWORD *)(a1 + 40) - 2LL )
            return 2147483653LL;
          *v12 = *((_WORD *)v5 - 4);
          *(_QWORD *)(a1 + 80) += 2LL;
        }
        goto LABEL_12;
      case 0:
        return 0;
      case 2:
        goto LABEL_3;
    }
LABEL_27:
    v7 = *v5;
    v5 += 2;
  }
}

```

## disassembly

```asm
0x140046380  mov     [rsp-40h+arg_0], rcx
0x140046385  mov     [rsp-40h+arg_8], rdx
0x14004638a  mov     [rsp-40h+arg_10], r8
0x14004638f  mov     [rsp-40h+arg_18], r9
0x140046394  push    rbp
0x140046395  push    rbx
0x140046396  push    rsi
0x140046397  push    rdi
0x140046398  push    r12
0x14004639a  push    r13
0x14004639c  push    r14
0x14004639e  push    r15
0x1400463a0  mov     rbp, rsp
0x1400463a3  sub     rsp, 38h
0x1400463a7  mov     r15, [rcx+20h]
0x1400463ab  lea     rsi, [rbp+arg_8]
0x1400463af  mov     rdi, rcx
0x1400463b2  mov     qword ptr [rbp+DestinationString.Length], 0
0x1400463ba  mov     r14d, 1
0x1400463c0  lea     r12, cs:140000000h
0x1400463c7  mov     r9d, 0FACEh
0x1400463cd  mov     r8d, 0B0FFh
0x1400463d3  mov     r10d, 5Ch ; '\'
0x1400463d9  cmp     r14d, 1
0x1400463dd  jnz     loc_1400464B2
0x1400463e3  mov     rbx, [rsi]
0x1400463e6  add     rsi, 8
0x1400463ea  nop     word ptr [rax+rax+00h]
0x1400463f0  movsx   eax, byte ptr [rbx]
0x1400463f3  test    al, al
0x1400463f5  jz      loc_140046553
0x1400463fb  cmp     al, 77h ; 'w'
0x1400463fd  jz      short loc_14004642F; jumptable 00000001400464E3 case 87
0x1400463ff  cmp     al, 58h ; 'X'
0x140046401  jnz     short loc_14004645F
0x140046403  mov     rax, [rbp+arg_0]
0x140046407  mov     rdx, [rdi+50h]
0x14004640b  mov     rcx, [rax+28h]
0x14004640f  sub     rcx, 4
0x140046413  cmp     rdx, rcx
0x140046416  jb      short loc_140046494
0x140046418  mov     eax, 80000005h
0x14004641d  add     rsp, 38h
0x140046421  pop     r15
0x140046423  pop     r14
0x140046425  pop     r13
0x140046427  pop     r12
0x140046429  pop     rdi
0x14004642a  pop     rsi
0x14004642b  pop     rbx
0x14004642c  pop     rbp
0x14004642d  retn
0x14004642f  add     rsi, 8; jumptable 00000001400464E3 case 87
0x140046433  cmp     r14d, 2
0x140046437  jz      short def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x140046439  mov     rax, [rbp+arg_0]
0x14004643d  mov     rdx, [rdi+50h]
0x140046441  mov     rcx, [rax+28h]
0x140046445  sub     rcx, 2
0x140046449  cmp     rdx, rcx
0x14004644c  jnb     short loc_140046418
0x14004644e  movzx   eax, word ptr [rsi-8]
0x140046452  mov     [rdx], ax
0x140046455  add     qword ptr [rdi+50h], 2
0x14004645a  inc     rbx; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x14004645d  jmp     short loc_1400463F0
0x14004645f  cmp     al, 64h ; 'd'
0x140046461  jnz     short loc_1400464C2
0x140046463  add     rsi, 8; jumptable 00000001400464E3 case 68
0x140046467  cmp     r14d, 2
0x14004646b  jz      short def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x14004646d  mov     rax, [rbp+arg_0]
0x140046471  mov     rdx, [rdi+50h]
0x140046475  mov     rcx, [rax+28h]
0x140046479  sub     rcx, 4
0x14004647d  cmp     rdx, rcx
0x140046480  jnb     short loc_140046418
0x140046482  mov     eax, [rsi-8]
0x140046485  mov     [rdx], eax
0x140046487  add     qword ptr [rdi+50h], 4
0x14004648c  inc     rbx
0x14004648f  jmp     loc_1400463F0
0x140046494  mov     byte ptr [rdx], 0CCh
0x140046497  inc     qword ptr [rdi+50h]
0x14004649b  mov     rax, [rdi+50h]
0x14004649f  mov     dword ptr [rax], 0DEDE00FFh
0x1400464a5  add     qword ptr [rdi+50h], 4
0x1400464aa  inc     rbx
0x1400464ad  jmp     loc_1400463F0
0x1400464b2  test    r14d, r14d
0x1400464b5  jnz     loc_140046549
0x1400464bb  xor     eax, eax
0x1400464bd  jmp     loc_14004641D
0x1400464c2  mov     ecx, eax
0x1400464c4  add     ecx, 0FFFFFFDFh; switch 90 cases
0x1400464c7  cmp     ecx, 59h
0x1400464ca  ja      short def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x1400464cc  movsxd  rcx, ecx
0x1400464cf  movzx   ecx, ds:(byte_14001B2E7 - 140000000h)[r12+rcx]
0x1400464d8  mov     edx, ds:(jpt_1400464E3 - 140000000h)[r12+rcx*4]
0x1400464e0  add     rdx, r12
0x1400464e3  jmp     rdx; switch jump
0x1400464e9  mov     rcx, [rdi+50h]; jumptable 00000001400464E3 cases 85,117
0x1400464ed  add     rsi, 8
0x1400464f1  mov     rdx, [rsi-8]
0x1400464f5  test    cl, 1
0x1400464f8  jnz     loc_1400468DF
0x1400464fe  movzx   r8d, word ptr [rdx]
0x140046502  add     r8, 2
0x140046506  add     r8, rcx
0x140046509  mov     [rdi+50h], r8
0x14004650d  mov     rax, [rbp+arg_0]
0x140046511  cmp     r8, [rax+28h]
0x140046515  jnb     loc_140046418
0x14004651b  movzx   r8d, word ptr [rdx]; Size
0x14004651f  mov     rdx, [rdx+8]; Src
0x140046523  call    memmove
0x140046528  mov     rcx, [rdi+50h]
0x14004652c  xor     eax, eax
0x14004652e  mov     [rcx-2], ax
0x140046532  mov     r10d, 5Ch ; '\'
0x140046538  mov     r9d, 0FACEh
0x14004653e  mov     r8d, 0B0FFh
0x140046544  jmp     def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x140046549  cmp     r14d, 2
0x14004654d  jz      loc_1400463E3
0x140046553  mov     r14d, [rsi]
0x140046556  add     rsi, 8
0x14004655a  jmp     loc_1400463D9
0x14004655f  mov     rax, [rbp+arg_0]; jumptable 00000001400464E3 case 48
0x140046563  mov     rdx, [rdi+50h]
0x140046567  mov     rcx, [rax+28h]
0x14004656b  dec     rcx
0x14004656e  cmp     rdx, rcx
0x140046571  jnb     loc_140046418
0x140046577  mov     byte ptr [rdx], 0CCh
0x14004657a  inc     qword ptr [rdi+50h]
0x14004657e  jmp     def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x140046583  add     rsi, 8; jumptable 00000001400464E3 cases 89,121
0x140046587  cmp     r14d, 2
0x14004658b  jz      def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x140046591  mov     rax, [rbp+arg_0]
0x140046595  mov     rdx, [rdi+50h]
0x140046599  mov     rcx, [rax+28h]
0x14004659d  dec     rcx
0x1400465a0  cmp     rdx, rcx
0x1400465a3  jnb     loc_140046418
0x1400465a9  movzx   eax, byte ptr [rsi-8]
0x1400465ad  mov     [rdx], al
0x1400465af  inc     qword ptr [rdi+50h]
0x1400465b3  jmp     def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x1400465b8  cmp     r14d, 2; jumptable 00000001400464E3 cases 77,109
0x1400465bc  jz      def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x1400465c2  mov     rax, [rbp+arg_0]
0x1400465c6  mov     rdx, [rdi+50h]
0x1400465ca  mov     rcx, [rax+28h]
0x1400465ce  dec     rcx
0x1400465d1  cmp     rdx, rcx
0x1400465d4  jnb     loc_140046418
0x1400465da  mov     byte ptr [rdx], 0
0x1400465dd  inc     qword ptr [rdi+50h]
0x1400465e1  jmp     def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x1400465e6  add     rsi, 8; jumptable 00000001400464E3 cases 76,108
0x1400465ea  cmp     r14d, 2
0x1400465ee  jz      def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x1400465f4  mov     rax, [rbp+arg_0]
0x1400465f8  mov     r8, [rdi+50h]
0x1400465fc  mov     rcx, [rax+28h]
0x140046600  sub     rcx, 8
0x140046604  cmp     r8, rcx
0x140046607  jnb     loc_140046418
0x14004660d  mov     rdx, [rsi-8]
0x140046611  mov     eax, [rdx]
0x140046613  mov     [r8], eax
0x140046616  mov     rcx, [rdi+50h]
0x14004661a  mov     eax, [rdx+4]
0x14004661d  mov     [rcx], eax
0x14004661f  add     qword ptr [rdi+50h], 8
0x140046624  jmp     loc_14004653E
0x140046629  mov     rax, [rbp+arg_0]; jumptable 00000001400464E3 cases 66,98
0x14004662d  mov     rdx, [rdi+50h]
0x140046631  mov     rcx, [rax+28h]
0x140046635  sub     rcx, 2
0x140046639  cmp     rdx, rcx
0x14004663c  jnb     loc_140046418
0x140046642  mov     rax, [rdi+58h]
0x140046646  sub     rdx, rax
0x140046649  sar     rdx, 1
0x14004664c  mov     [rax], dl
0x14004664e  mov     rax, [rdi+50h]
0x140046652  mov     [rax], r9w
0x140046656  mov     rax, [rdi+50h]
0x14004665a  mov     [rdi+60h], rax
0x14004665e  add     qword ptr [rdi+50h], 2
0x140046663  jmp     def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x140046668  mov     rax, [rbp+arg_0]; jumptable 00000001400464E3 cases 81,113
0x14004666c  mov     rdx, [rdi+50h]
0x140046670  mov     rcx, [rax+28h]
0x140046674  sub     rcx, 2
0x140046678  cmp     rdx, rcx
0x14004667b  jnb     loc_140046418
0x140046681  mov     word ptr [rdx], 0D0FFh
0x140046686  mov     rax, [rdi+50h]
0x14004668a  mov     [rdi+68h], rax
0x14004668e  add     qword ptr [rdi+50h], 2
0x140046693  jmp     def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x140046698  movzx   ecx, word ptr [rdi+50h]; jumptable 00000001400464E3 case 53
0x14004669c  mov     rax, [rdi+68h]
0x1400466a0  sub     cx, r15w
0x1400466a4  mov     [rax], cx
0x1400466a7  jmp     def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x1400466ac  mov     rax, [rbp+arg_0]; jumptable 00000001400464E3 cases 80,112
0x1400466b0  mov     rdx, [rdi+50h]
0x1400466b4  mov     rcx, [rax+28h]
0x1400466b8  sub     rcx, 2
0x1400466bc  cmp     rdx, rcx
0x1400466bf  jnb     loc_140046418
0x1400466c5  mov     [rdx], r8w
0x1400466c9  mov     rax, [rdi+50h]
0x1400466cd  mov     [rdi+70h], rax
0x1400466d1  add     qword ptr [rdi+50h], 2
0x1400466d6  jmp     def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x1400466db  movzx   ecx, word ptr [rdi+50h]; jumptable 00000001400464E3 case 54
0x1400466df  mov     rax, [rdi+70h]
0x1400466e3  sub     cx, r15w
0x1400466e7  mov     [rax], cx
0x1400466ea  jmp     def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x1400466ef  mov     rcx, [rdi+50h]; jumptable 00000001400464E3 case 83
0x1400466f3  lea     rdx, [rcx+7]
0x1400466f7  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1400466fb  mov     [rdi+50h], rdx
0x1400466ff  mov     rax, [rbp+arg_0]
0x140046703  cmp     rdx, [rax+28h]
0x140046707  jnb     loc_140046418
0x14004670d  cmp     rcx, rdx
0x140046710  jz      def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x140046716  mov     byte ptr [rcx], 0EEh
0x140046719  inc     rcx
0x14004671c  cmp     rcx, [rdi+50h]
0x140046720  jnz     short loc_140046716
0x140046722  jmp     def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x140046727  mov     ecx, [rsi]; jumptable 00000001400464E3 case 115
0x140046729  add     rsi, 8
0x14004672d  mov     rdx, [rdi+50h]
0x140046731  lea     r8d, [rcx-1]
0x140046735  neg     ecx
0x140046737  movsxd  rax, ecx
0x14004673a  add     r8, rdx
0x14004673d  and     r8, rax
0x140046740  mov     [rdi+50h], r8
0x140046744  mov     rax, [rbp+arg_0]
0x140046748  cmp     r8, [rax+28h]
0x14004674c  jnb     loc_140046418
0x140046752  cmp     rdx, r8
0x140046755  jz      loc_14004653E
0x14004675b  mov     byte ptr [rdx], 0EEh
0x14004675e  inc     rdx
0x140046761  cmp     rdx, [rdi+50h]
0x140046765  jnz     short loc_14004675B
0x140046767  jmp     loc_14004653E
0x14004676c  mov     rcx, [rdi+50h]; jumptable 00000001400464E3 case 49
0x140046770  lea     rdx, [rcx+1]
0x140046774  and     rdx, 0FFFFFFFFFFFFFFFEh
0x140046778  mov     [rdi+50h], rdx
0x14004677c  mov     rax, [rbp+arg_0]
0x140046780  cmp     rdx, [rax+28h]
0x140046784  jnb     loc_140046418
0x14004678a  cmp     rcx, rdx
0x14004678d  jz      def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x140046793  mov     byte ptr [rcx], 0EEh
0x140046796  inc     rcx
0x140046799  cmp     rcx, [rdi+50h]
0x14004679d  jnz     short loc_140046793
0x14004679f  jmp     def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x1400467a4  lea     rax, [rsi+8]; jumptable 00000001400464E3 case 99
0x1400467a8  lea     rsi, [rax+8]
0x1400467ac  cmp     r14d, 2
0x1400467b0  jz      def_1400464E3; jumptable 00000001400464E3 default case, cases 34-47,50,51,55-61,64,67,69-75,79,84,88,90-96,100-107,111,116,119,120
0x1400467b6  mov     r8d, [rax-8]
0x1400467ba  mov     rcx, [rdi+50h]
0x1400467be  mov     rdx, [rsi-8]
0x1400467c2  add     r8, rcx
0x1400467c5  mov     [rdi+50h], r8
0x1400467c9  mov     rax, [rbp+arg_0]
0x1400467cd  cmp     r8, [rax+28h]
0x1400467d1  jnb     loc_140046418
0x1400467d7  cmp     rcx, r8
0x1400467da  jz      loc_14004653E
0x1400467e0  movzx   eax, byte ptr [rdx]
0x1400467e3  lea     rdx, [rdx+1]
0x1400467e7  mov     [rcx], al
0x1400467e9  inc     rcx
0x1400467ec  cmp     rcx, [rdi+50h]
0x1400467f0  jnz     short loc_1400467E0
0x1400467f2  jmp     loc_14004653E
0x1400467f7  mov     rax, [rdi+50h]; jumptable 00000001400464E3 cases 82,114
0x1400467fb  lea     rcx, [rsi+8]
0x1400467ff  mov     edx, [rcx]
0x140046801  lea     rsi, [rcx+8]
0x140046805  mov     rcx, [rcx-8]
  ... truncated ...
```
