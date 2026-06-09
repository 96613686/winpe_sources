# RestoreRecipientJob(ushort const *)

- ea: `0x14003d010`
- end: `0x14003d45f`
- name: `?RestoreRecipientJob@@YAHPEBG@Z`
- size: `1103`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x14003d468`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x1400362a0`
- `0x140037f80`
- `0x14003a754`
- `0x14003d010`
- `0x14003ec74`
- `0x140065dbc`
- `0x140067168`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003d0a1`
- `KERNEL32!GetLastError` at `0x14003d159`
- `KERNEL32!GetLastError` at `0x14003d1fd`
- `KERNEL32!GetLastError` at `0x14003d376`
- `KERNEL32!GetLastError` at `0x14003d3d3`
- `KERNEL32!GetLastError` at `0x14003d0a1`
- `KERNEL32!GetLastError` at `0x14003d159`
- `KERNEL32!GetLastError` at `0x14003d1fd`
- `KERNEL32!GetLastError` at `0x14003d376`
- `KERNEL32!GetLastError` at `0x14003d3d3`
- `KERNEL32!DeleteFileW` at `0x14003d137`
- `KERNEL32!DeleteFileW` at `0x14003d137`

## pseudocode

```c
__int64 __fastcall RestoreRecipientJob(WCHAR *lpFileName, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // eax
  struct _JOB_QUEUE_FILE *v6; // rdi
  DWORD LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  struct _LIST_ENTRY *Flink; // rdx
  char v11; // al
  int v12; // edx
  unsigned int v13; // esi
  unsigned int v15; // eax
  struct _JOB_QUEUE *v16; // rax
  struct _JOB_QUEUE *v17; // rbx
  _WORD *v18; // rcx
  __int64 v19; // r10
  _WORD *v20; // r8
  __int64 v21; // rax
  __int64 v22; // rdx
  _WORD *v23; // rcx
  __int64 v24; // r9
  CMapDeviceId *v25; // rcx
  __int64 v26; // rdx
  _WORD *v27; // rax
  __int64 v28; // rdx
  _WORD *v29; // r8
  _WORD *v30; // rcx
  __int64 v31; // rax
  void *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  struct _JOB_QUEUE_FILE *v35; // [rsp+68h] [rbp+10h] BYREF

  v35 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  v5 = ReadJobQueueFile(lpFileName, &v35, a3, a4);
  v6 = v35;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    LastError = GetLastError();
    v8 = 67;
    goto LABEL_10;
  }
  if ( !(unsigned int)FixupJobQueueFile(v35) )
    goto LABEL_25;
  Flink = g_QueueListHead.Flink;
  if ( g_QueueListHead.Flink == &g_QueueListHead )
    goto LABEL_15;
  while ( Flink[1].Flink != (struct _LIST_ENTRY *)*((_QWORD *)v6 + 68) )
  {
    Flink = Flink->Flink;
    if ( Flink == &g_QueueListHead )
      goto LABEL_15;
  }
  if ( !Flink )
  {
LABEL_15:
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ii(*((_QWORD *)WPP_GLOBAL_Control + 2), Flink, v9, *((_QWORD *)v6 + 68), *((_QWORD *)v6 + 1));
    }
    if ( DeleteFileW(lpFileName)
      || WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    v11 = GetLastError();
    v12 = 69;
LABEL_24:
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      (_DWORD)lpFileName,
      v11);
    goto LABEL_25;
  }
  v15 = *((_DWORD *)v6 + 10);
  v13 = 1;
  if ( v15 == 2 )
  {
    v15 = 1;
    if ( *((_DWORD *)v6 + 138) )
      v15 = 64;
  }
  v16 = AddRecipientJob(
          &g_QueueListHead,
          (struct _JOB_QUEUE *)Flink,
          (struct _JOB_QUEUE_FILE *)((char *)v6 + 408),
          0,
          v15);
  v17 = v16;
  if ( !v16 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    v11 = GetLastError();
    v12 = 70;
    goto LABEL_24;
  }
  v18 = (_WORD *)((char *)v6 + 1136);
  v19 = 2147483646;
  *((_DWORD *)v16 + 422) = *((_DWORD *)v6 + 412);
  v20 = (_WORD *)((char *)v16 + 1176);
  v21 = 2147483646;
  v22 = 256;
  do
  {
    if ( !v21 )
      break;
    if ( !*v18 )
      break;
    *v20++ = *v18++;
    --v21;
    --v22;
  }
  while ( v22 );
  v23 = v20 - 1;
  v24 = v22 == 0 ? 0x8007007A : 0;
  if ( v22 )
    v23 = v20;
  *v23 = 0;
  if ( !v22 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    v26 = 71;
    goto LABEL_47;
  }
  v27 = (_WORD *)((char *)v6 + 556);
  v28 = 256;
  v29 = (_WORD *)((char *)v17 + 648);
  do
  {
    if ( !v19 )
      break;
    if ( !*v27 )
      break;
    *v29++ = *v27++;
    --v19;
    --v28;
  }
  while ( v28 );
  v30 = v29 - 1;
  v24 = v28 == 0 ? 0x8007007A : 0;
  if ( v28 )
    v30 = v29;
  *v30 = 0;
  if ( !v28 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    v26 = 72;
LABEL_47:
    WPP_SF_d(*((_QWORD *)v25 + 2), v26, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v24);
    goto LABEL_25;
  }
  v31 = StringDup(lpFileName);
  *((_QWORD *)v17 + 7) = v31;
  if ( lpFileName && !v31 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    LastError = GetLastError();
    v8 = 73;
    goto LABEL_10;
  }
  v32 = (void *)*((_QWORD *)v17 + 9);
  *((_QWORD *)v17 + 2) = *((_QWORD *)v6 + 1);
  pMemFree(v32);
  v33 = StringDup(*((unsigned __int16 **)v6 + 6));
  *((_QWORD *)v17 + 9) = v33;
  if ( *((_QWORD *)v6 + 6) && !v33 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    LastError = GetLastError();
    v8 = 74;
LABEL_10:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, LastError);
LABEL_25:
    v13 = 0;
    goto LABEL_26;
  }
  *((_DWORD *)v17 + 148) = *((_DWORD *)v6 + 138);
  v34 = *((_DWORD *)v17 + 461);
  if ( (v34 & 0x200) != 0 )
  {
    ++*(_DWORD *)(*((_QWORD *)v17 + 73) + 380LL);
  }
  else if ( (v34 & 0x100) != 0 )
  {
    ++*(_DWORD *)(*((_QWORD *)v17 + 73) + 376LL);
  }
  else if ( (v34 & 0x80u) != 0 )
  {
    ++*(_DWORD *)(*((_QWORD *)v17 + 73) + 384LL);
  }
  *((_QWORD *)v17 + 145) = *((_QWORD *)v6 + 140);
  *((_QWORD *)v17 + 146) = *((_QWORD *)v6 + 141);
  *((_DWORD *)v17 + 21) = *((_DWORD *)v6 + 15);
  *((_QWORD *)v17 + 3) = *((_QWORD *)v6 + 2);
LABEL_26:
  pMemFree(v6);
  return v13;
}

```

## disassembly

```asm
0x14003d010  mov     [rsp+arg_0], rbx
0x14003d015  mov     [rsp+arg_10], rbp
0x14003d01a  push    rsi
0x14003d01b  push    rdi
0x14003d01c  push    r12
0x14003d01e  push    r13
0x14003d020  push    r14
0x14003d022  sub     rsp, 30h
0x14003d026  xor     r14d, r14d
0x14003d029  mov     rbp, rcx
0x14003d02c  mov     [rsp+58h+arg_8], r14
0x14003d031  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d038  lea     r12, WPP_GLOBAL_Control
0x14003d03f  lea     r13, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003d046  cmp     rcx, r12
0x14003d049  jz      short loc_14003D067
0x14003d04b  test    byte ptr [rcx+1Ch], 4
0x14003d04f  jz      short loc_14003D067
0x14003d051  cmp     byte ptr [rcx+19h], 5
0x14003d055  jb      short loc_14003D067
0x14003d057  mov     rcx, [rcx+10h]
0x14003d05b  lea     edx, [r14+42h]
0x14003d05f  mov     r8, r13
0x14003d062  call    WPP_SF_
0x14003d067  lea     rdx, [rsp+58h+arg_8]; struct _JOB_QUEUE_FILE **
0x14003d06c  mov     rcx, rbp; lpFileName
0x14003d06f  call    ?ReadJobQueueFile@@YAHPEBGPEAPEAU_JOB_QUEUE_FILE@@@Z; ReadJobQueueFile(ushort const *,_JOB_QUEUE_FILE * *)
0x14003d074  mov     rdi, [rsp+58h+arg_8]
0x14003d079  test    eax, eax
0x14003d07b  jnz     short loc_14003D0C7
0x14003d07d  mov     rax, cs:WPP_GLOBAL_Control
0x14003d084  cmp     rax, r12
0x14003d087  jz      loc_14003D17E
0x14003d08d  test    byte ptr [rax+1Ch], 4
0x14003d091  jz      loc_14003D17E
0x14003d097  cmp     byte ptr [rax+19h], 2
0x14003d09b  jb      loc_14003D17E
0x14003d0a1  call    cs:__imp_GetLastError
0x14003d0a7  mov     edx, 43h ; 'C'
0x14003d0ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d0b3  mov     r9d, eax
0x14003d0b6  mov     r8, r13
0x14003d0b9  mov     rcx, [rcx+10h]
0x14003d0bd  call    WPP_SF_d
0x14003d0c2  jmp     loc_14003D17E
0x14003d0c7  mov     rcx, rdi; struct _JOB_QUEUE_FILE *
0x14003d0ca  call    ?FixupJobQueueFile@@YAHPEAU_JOB_QUEUE_FILE@@@Z; FixupJobQueueFile(_JOB_QUEUE_FILE *)
0x14003d0cf  test    eax, eax
0x14003d0d1  jz      loc_14003D17E
0x14003d0d7  mov     rdx, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; struct _JOB_QUEUE *
0x14003d0de  lea     r10, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x14003d0e5  cmp     rdx, r10
0x14003d0e8  jz      short loc_14003D103
0x14003d0ea  mov     rax, [rdi+220h]
0x14003d0f1  cmp     [rdx+10h], rax
0x14003d0f5  jz      loc_14003D1A2
0x14003d0fb  mov     rdx, [rdx]
0x14003d0fe  cmp     rdx, r10
0x14003d101  jnz     short loc_14003D0F1
0x14003d103  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d10a  cmp     rcx, r12
0x14003d10d  jz      short loc_14003D134
0x14003d10f  test    byte ptr [rcx+1Ch], 4
0x14003d113  jz      short loc_14003D134
0x14003d115  cmp     byte ptr [rcx+19h], 2
0x14003d119  jb      short loc_14003D134
0x14003d11b  mov     rax, [rdi+8]
0x14003d11f  mov     r9, [rdi+220h]
0x14003d126  mov     rcx, [rcx+10h]
0x14003d12a  mov     qword ptr [rsp+58h+var_38], rax
0x14003d12f  call    WPP_SF_ii
0x14003d134  mov     rcx, rbp; lpFileName
0x14003d137  call    cs:__imp_DeleteFileW
0x14003d13d  test    eax, eax
0x14003d13f  jnz     short loc_14003D17E
0x14003d141  mov     rax, cs:WPP_GLOBAL_Control
0x14003d148  cmp     rax, r12
0x14003d14b  jz      short loc_14003D17E
0x14003d14d  test    byte ptr [rax+1Ch], 4
0x14003d151  jz      short loc_14003D17E
0x14003d153  cmp     byte ptr [rax+19h], 2
0x14003d157  jb      short loc_14003D17E
0x14003d159  call    cs:__imp_GetLastError
0x14003d15f  mov     edx, 45h ; 'E'
0x14003d164  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d16b  mov     r9, rbp
0x14003d16e  mov     r8, r13
0x14003d171  mov     [rsp+58h+var_38], eax
0x14003d175  mov     rcx, [rcx+10h]
0x14003d179  call    WPP_SF_Sd
0x14003d17e  mov     esi, r14d
0x14003d181  mov     rcx, rdi; lpMem
0x14003d184  call    pMemFree
0x14003d189  mov     rbx, [rsp+58h+arg_0]
0x14003d18e  mov     eax, esi
0x14003d190  mov     rbp, [rsp+58h+arg_10]
0x14003d195  add     rsp, 30h
0x14003d199  pop     r14
0x14003d19b  pop     r13
0x14003d19d  pop     r12
0x14003d19f  pop     rdi
0x14003d1a0  pop     rsi
0x14003d1a1  retn
0x14003d1a2  test    rdx, rdx
0x14003d1a5  jz      loc_14003D103
0x14003d1ab  mov     eax, [rdi+28h]
0x14003d1ae  mov     esi, 1
0x14003d1b3  cmp     eax, 2
0x14003d1b6  jnz     short loc_14003D1C7
0x14003d1b8  cmp     [rdi+228h], r14d
0x14003d1bf  lea     ecx, [rsi+3Fh]
0x14003d1c2  mov     eax, esi
0x14003d1c4  cmovnz  eax, ecx
0x14003d1c7  lea     r8, [rdi+198h]; struct _FAX_PERSONAL_PROFILEW *
0x14003d1ce  mov     [rsp+58h+var_38], eax; unsigned int
0x14003d1d2  xor     r9d, r9d; int
0x14003d1d5  mov     rcx, r10; struct _LIST_ENTRY *
0x14003d1d8  call    ?AddRecipientJob@@YAPEAU_JOB_QUEUE@@QEAU_LIST_ENTRY@@PEAU1@PEBU_FAX_PERSONAL_PROFILEW@@HK@Z; AddRecipientJob(_LIST_ENTRY * const,_JOB_QUEUE *,_FAX_PERSONAL_PROFILEW const *,int,ulong)
0x14003d1dd  mov     rbx, rax
0x14003d1e0  test    rax, rax
0x14003d1e3  jnz     short loc_14003D20B
0x14003d1e5  mov     rax, cs:WPP_GLOBAL_Control
0x14003d1ec  cmp     rax, r12
0x14003d1ef  jz      short loc_14003D17E
0x14003d1f1  test    byte ptr [rax+1Ch], 4
0x14003d1f5  jz      short loc_14003D17E
0x14003d1f7  cmp     byte ptr [rax+19h], 2
0x14003d1fb  jb      short loc_14003D17E
0x14003d1fd  call    cs:__imp_GetLastError
0x14003d203  lea     edx, [rbx+46h]
0x14003d206  jmp     loc_14003D164
0x14003d20b  mov     eax, [rdi+670h]
0x14003d211  lea     rcx, [rdi+470h]
0x14003d218  mov     r10d, 7FFFFFFEh
0x14003d21e  mov     [rbx+698h], eax
0x14003d224  mov     r11d, 100h
0x14003d22a  lea     r8, [rbx+498h]
0x14003d231  mov     eax, r10d
0x14003d234  mov     edx, r11d
0x14003d237  test    rax, rax
0x14003d23a  jz      short loc_14003D25A
0x14003d23c  movzx   r9d, word ptr [rcx]
0x14003d240  test    r9w, r9w
0x14003d244  jz      short loc_14003D25A
0x14003d246  mov     [r8], r9w
0x14003d24a  add     rcx, 2
0x14003d24e  add     r8, 2
0x14003d252  sub     rax, rsi
0x14003d255  sub     rdx, rsi
0x14003d258  jnz     short loc_14003D237
0x14003d25a  mov     rax, rdx
0x14003d25d  lea     rcx, [r8-2]
0x14003d261  neg     rax
0x14003d264  sbb     r9d, r9d
0x14003d267  not     r9d
0x14003d26a  and     r9d, 8007007Ah
0x14003d271  test    rdx, rdx
0x14003d274  cmovnz  rcx, r8
0x14003d278  mov     [rcx], r14w
0x14003d27c  jnz     short loc_14003D2B8
0x14003d27e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d285  cmp     rcx, r12
0x14003d288  jz      loc_14003D17E
0x14003d28e  test    byte ptr [rcx+1Ch], 4
0x14003d292  jz      loc_14003D17E
0x14003d298  cmp     byte ptr [rcx+19h], 2
0x14003d29c  jb      loc_14003D17E
0x14003d2a2  mov     edx, 47h ; 'G'
0x14003d2a7  mov     rcx, [rcx+10h]
0x14003d2ab  mov     r8, r13
0x14003d2ae  call    WPP_SF_d
0x14003d2b3  jmp     loc_14003D17E
0x14003d2b8  lea     rax, [rdi+22Ch]
0x14003d2bf  mov     rdx, r11
0x14003d2c2  lea     r8, [rbx+288h]
0x14003d2c9  test    r10, r10
0x14003d2cc  jz      short loc_14003D2EA
0x14003d2ce  movzx   ecx, word ptr [rax]
0x14003d2d1  test    cx, cx
0x14003d2d4  jz      short loc_14003D2EA
0x14003d2d6  mov     [r8], cx
0x14003d2da  add     rax, 2
0x14003d2de  add     r8, 2
0x14003d2e2  sub     r10, rsi
0x14003d2e5  sub     rdx, rsi
0x14003d2e8  jnz     short loc_14003D2C9
0x14003d2ea  mov     rax, rdx
0x14003d2ed  lea     rcx, [r8-2]
0x14003d2f1  neg     rax
0x14003d2f4  sbb     r9d, r9d
0x14003d2f7  not     r9d
0x14003d2fa  and     r9d, 8007007Ah
0x14003d301  test    rdx, rdx
0x14003d304  cmovnz  rcx, r8
0x14003d308  mov     [rcx], r14w
0x14003d30c  jnz     short loc_14003D33C
0x14003d30e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d315  cmp     rcx, r12
0x14003d318  jz      loc_14003D17E
0x14003d31e  test    byte ptr [rcx+1Ch], 4
0x14003d322  jz      loc_14003D17E
0x14003d328  cmp     byte ptr [rcx+19h], 2
0x14003d32c  jb      loc_14003D17E
0x14003d332  mov     edx, 48h ; 'H'
0x14003d337  jmp     loc_14003D2A7
0x14003d33c  mov     rcx, rbp; unsigned __int16 *
0x14003d33f  call    StringDup
0x14003d344  mov     [rbx+38h], rax
0x14003d348  test    rbp, rbp
0x14003d34b  jz      short loc_14003D386
0x14003d34d  test    rax, rax
0x14003d350  jnz     short loc_14003D386
0x14003d352  mov     rax, cs:WPP_GLOBAL_Control
0x14003d359  cmp     rax, r12
0x14003d35c  jz      loc_14003D17E
0x14003d362  test    byte ptr [rax+1Ch], 4
0x14003d366  jz      loc_14003D17E
0x14003d36c  cmp     byte ptr [rax+19h], 2
0x14003d370  jb      loc_14003D17E
0x14003d376  call    cs:__imp_GetLastError
0x14003d37c  mov     edx, 49h ; 'I'
0x14003d381  jmp     loc_14003D0AC
0x14003d386  mov     rax, [rdi+8]
0x14003d38a  mov     rcx, [rbx+48h]; lpMem
0x14003d38e  mov     [rbx+10h], rax
0x14003d392  call    pMemFree
0x14003d397  mov     rcx, [rdi+30h]; unsigned __int16 *
0x14003d39b  call    StringDup
0x14003d3a0  mov     [rbx+48h], rax
0x14003d3a4  cmp     [rdi+30h], r14
0x14003d3a8  jz      short loc_14003D3E3
0x14003d3aa  test    rax, rax
0x14003d3ad  jnz     short loc_14003D3E3
0x14003d3af  mov     rax, cs:WPP_GLOBAL_Control
0x14003d3b6  cmp     rax, r12
0x14003d3b9  jz      loc_14003D17E
0x14003d3bf  test    byte ptr [rax+1Ch], 4
0x14003d3c3  jz      loc_14003D17E
0x14003d3c9  cmp     byte ptr [rax+19h], 2
0x14003d3cd  jb      loc_14003D17E
0x14003d3d3  call    cs:__imp_GetLastError
0x14003d3d9  mov     edx, 4Ah ; 'J'
0x14003d3de  jmp     loc_14003D0AC
0x14003d3e3  mov     eax, [rdi+228h]
0x14003d3e9  mov     [rbx+250h], eax
0x14003d3ef  mov     eax, [rbx+734h]
0x14003d3f5  bt      eax, 9
0x14003d3f9  jnb     short loc_14003D40A
0x14003d3fb  mov     rax, [rbx+248h]
0x14003d402  add     [rax+17Ch], esi
0x14003d408  jmp     short loc_14003D430
0x14003d40a  bt      eax, 8
0x14003d40e  jnb     short loc_14003D41F
0x14003d410  mov     rax, [rbx+248h]
0x14003d417  add     [rax+178h], esi
0x14003d41d  jmp     short loc_14003D430
0x14003d41f  test    al, al
0x14003d421  jns     short loc_14003D430
0x14003d423  mov     rax, [rbx+248h]
0x14003d42a  add     [rax+180h], esi
0x14003d430  mov     rax, [rdi+460h]
0x14003d437  mov     [rbx+488h], rax
0x14003d43e  mov     rax, [rdi+468h]
0x14003d445  mov     [rbx+490h], rax
0x14003d44c  mov     eax, [rdi+3Ch]
0x14003d44f  mov     [rbx+54h], eax
0x14003d452  mov     rax, [rdi+10h]
0x14003d456  mov     [rbx+18h], rax
0x14003d45a  jmp     loc_14003D181
```
