# CdFindPathEntry

- ea: `0x1400166ac`
- end: `0x140016990`
- name: `CdFindPathEntry`
- size: `740`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000c8b4`

## callees

- `0x140001114`
- `0x1400164dc`
- `0x1400166ac`
- `0x140016998`
- `0x140016a20`
- `0x140016dc0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140016722`
- `ntoskrnl!ExAcquireFastMutex` at `0x140016808`
- `ntoskrnl!ExAcquireFastMutex` at `0x140016903`
- `ntoskrnl!ExAcquireFastMutex` at `0x140016722`
- `ntoskrnl!ExAcquireFastMutex` at `0x140016808`
- `ntoskrnl!ExAcquireFastMutex` at `0x140016903`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001679f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140016861`
- `ntoskrnl!ExReleaseFastMutex` at `0x140016948`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001679f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140016861`
- `ntoskrnl!ExReleaseFastMutex` at `0x140016948`

## pseudocode

```c
char __fastcall CdFindPathEntry(__int64 a1, __int64 a2, __int64 a3, char a4, _DWORD *a5)
{
  unsigned int v6; // esi
  struct _KTHREAD *CurrentThread; // rbp
  __int64 v9; // rdi
  int v10; // ecx
  unsigned int *v11; // r15
  int v12; // edx
  int v13; // r14d
  bool v14; // bp
  struct _FAST_MUTEX *v15; // rcx
  __int64 v16; // r8
  unsigned int v17; // eax
  unsigned int *v18; // r9
  unsigned int v19; // ecx
  _DWORD *v20; // rdx
  struct _KTHREAD *v21; // rsi
  int v22; // ecx
  struct _FAST_MUTEX *v23; // rcx
  __int64 v24; // rcx
  struct _KTHREAD *v26; // rbp
  int v27; // ecx
  struct _FAST_MUTEX *v28; // rcx
  int v29; // [rsp+30h] [rbp-48h]

  v6 = *(_DWORD *)(a2 + 504);
  if ( v6 > 0xFFFF )
    CdRaiseStatusEx(a1, 3221225522LL, 0, 1245184, 376);
  CurrentThread = KeGetCurrentThread();
  v9 = a2 + 200;
  v10 = *(_DWORD *)(a2 + 156);
  v29 = v10;
  if ( CurrentThread == *(struct _KTHREAD **)(a2 + 184) )
  {
    v11 = (unsigned int *)(a2 + 504);
  }
  else
  {
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)v9 + 136LL));
    v10 = v29;
    v11 = (unsigned int *)(a2 + 504);
    *(_QWORD *)(a2 + 184) = CurrentThread;
  }
  v12 = *(_DWORD *)(a2 + 192);
  v13 = *(_DWORD *)(a2 + 508);
  *(_DWORD *)(a2 + 192) = v12 + 1;
  if ( v13 )
  {
    v6 = *(_DWORD *)(a2 + 512);
    v14 = 0;
  }
  else
  {
    v13 = v10;
    v14 = a2 != *(_QWORD *)(*(_QWORD *)(a2 + 120) + 80LL);
  }
  *(_DWORD *)(a2 + 192) = v12;
  if ( !v12 )
  {
    v15 = (struct _FAST_MUTEX *)(*(_QWORD *)v9 + 136LL);
    *(_QWORD *)(a2 + 184) = 0;
    ExReleaseFastMutex(v15);
  }
  CdLookupPathEntry(a1, v13, v6, 0, (__int64)a5);
  v17 = *v11;
  v18 = a5 + 8;
  v19 = a5[12];
  if ( v19 <= *v11 )
  {
    v20 = a5 + 9;
    while ( 1 )
    {
      if ( v19 == v17 )
      {
        if ( v14 )
        {
          v21 = KeGetCurrentThread();
          if ( v21 != *(struct _KTHREAD **)(a2 + 184) )
          {
            ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)v9 + 136LL));
            v20 = a5 + 9;
            *(_QWORD *)(a2 + 184) = v21;
            v18 = a5 + 8;
          }
          v22 = *(_DWORD *)(a2 + 192);
          *(_DWORD *)(a2 + 192) = v22 + 1;
          *(_DWORD *)(a2 + 508) = *v20;
          *(_DWORD *)(a2 + 512) = *v18;
          *(_DWORD *)(a2 + 192) = v22;
          if ( !v22 )
          {
            v23 = (struct _FAST_MUTEX *)(*(_QWORD *)v9 + 136LL);
            *(_QWORD *)(a2 + 184) = 0;
            ExReleaseFastMutex(v23);
            v18 = a5 + 8;
          }
          v14 = 0;
        }
        LOBYTE(v16) = a4;
        CdUpdatePathEntryName(a1, v18, v16);
        if ( (unsigned __int8)CdIsNameInExpression(v24, a5 + 26, a3) )
          return 1;
        v18 = a5 + 8;
      }
      v13 = a5[9];
      v6 = *v18;
      if ( !(unsigned __int8)CdLookupNextPathEntry(a1, a5, v18) )
        return 0;
      v17 = *(_DWORD *)(a2 + 504);
      v20 = a5 + 9;
      v19 = a5[12];
      if ( v19 > v17 )
        break;
      v18 = a5 + 8;
    }
  }
  if ( v14 )
  {
    v26 = KeGetCurrentThread();
    if ( v26 != *(struct _KTHREAD **)(a2 + 184) )
    {
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)v9 + 136LL));
      *(_QWORD *)(a2 + 184) = v26;
    }
    v27 = *(_DWORD *)(a2 + 192);
    *(_DWORD *)(a2 + 508) = v13;
    *(_DWORD *)(a2 + 512) = v6;
    *(_DWORD *)(a2 + 192) = v27;
    if ( !v27 )
    {
      v28 = (struct _FAST_MUTEX *)(*(_QWORD *)v9 + 136LL);
      *(_QWORD *)(a2 + 184) = 0;
      ExReleaseFastMutex(v28);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400166ac  mov     [rsp+arg_0], rbx
0x1400166b1  mov     [rsp+arg_18], r9b
0x1400166b6  mov     [rsp+arg_10], r8
0x1400166bb  push    rbp
0x1400166bc  push    rsi
0x1400166bd  push    rdi
0x1400166be  push    r12
0x1400166c0  push    r13
0x1400166c2  push    r14
0x1400166c4  push    r15
0x1400166c6  sub     rsp, 40h
0x1400166ca  lea     rax, [rdx+1F8h]
0x1400166d1  mov     rbx, rdx
0x1400166d4  mov     esi, [rax]
0x1400166d6  mov     r12, rcx
0x1400166d9  cmp     esi, 0FFFFh
0x1400166df  ja      loc_140016974
0x1400166e5  mov     rbp, gs:188h
0x1400166ee  lea     rdi, [rdx+0C8h]
0x1400166f5  mov     ecx, [rdx+9Ch]
0x1400166fb  mov     r13, [rsp+78h+arg_20]
0x140016703  mov     [rsp+78h+arg_8], 0
0x14001670b  mov     [rsp+78h+var_48], ecx
0x14001670f  cmp     rbp, [rdx+0B8h]
0x140016716  jz      short loc_140016742
0x140016718  mov     rcx, [rdi]
0x14001671b  add     rcx, 88h; FastMutex
0x140016722  call    cs:__imp_ExAcquireFastMutex
0x140016729  nop     dword ptr [rax+rax+00h]
0x14001672e  mov     ecx, [rsp+78h+var_48]
0x140016732  lea     r15, [rbx+1F8h]
0x140016739  mov     [rbx+0B8h], rbp
0x140016740  jmp     short loc_140016745
0x140016742  mov     r15, rax
0x140016745  mov     edx, [rbx+0C0h]
0x14001674b  mov     r14d, [rbx+1FCh]
0x140016752  lea     eax, [rdx+1]
0x140016755  mov     [rbx+0C0h], eax
0x14001675b  mov     al, 1
0x14001675d  test    r14d, r14d
0x140016760  jz      short loc_14001676D
0x140016762  mov     esi, [rbx+200h]
0x140016768  xor     bpl, bpl
0x14001676b  jmp     short loc_140016780
0x14001676d  movzx   ebp, al
0x140016770  mov     r14d, ecx
0x140016773  mov     rcx, [rbx+78h]
0x140016777  xor     eax, eax
0x140016779  cmp     rbx, [rcx+50h]
0x14001677d  cmovz   ebp, eax
0x140016780  mov     [rbx+0C0h], edx
0x140016786  test    edx, edx
0x140016788  jnz     short loc_1400167AB
0x14001678a  mov     rcx, [rdi]
0x14001678d  add     rcx, 88h; FastMutex
0x140016794  mov     qword ptr [rbx+0B8h], 0
0x14001679f  call    cs:__imp_ExReleaseFastMutex
0x1400167a6  nop     dword ptr [rax+rax+00h]
0x1400167ab  xor     r9d, r9d
0x1400167ae  mov     [rsp+78h+var_58], r13
0x1400167b3  mov     r8d, esi
0x1400167b6  mov     edx, r14d
0x1400167b9  mov     rcx, r12
0x1400167bc  call    CdLookupPathEntry
0x1400167c1  mov     eax, [r15]
0x1400167c4  lea     r9, [r13+20h]
0x1400167c8  mov     ecx, [r13+30h]
0x1400167cc  cmp     ecx, eax
0x1400167ce  ja      loc_1400168E2
0x1400167d4  lea     r15, [r13+24h]
0x1400167d8  mov     rdx, r15
0x1400167db  cmp     ecx, eax
0x1400167dd  jnz     loc_1400168A8
0x1400167e3  test    bpl, bpl
0x1400167e6  jz      loc_140016874
0x1400167ec  mov     rsi, gs:188h
0x1400167f5  cmp     rsi, [rbx+0B8h]
0x1400167fc  jz      short loc_140016822
0x1400167fe  mov     rcx, [rdi]
0x140016801  add     rcx, 88h; FastMutex
0x140016808  call    cs:__imp_ExAcquireFastMutex
0x14001680f  nop     dword ptr [rax+rax+00h]
0x140016814  mov     rdx, r15
0x140016817  mov     [rbx+0B8h], rsi
0x14001681e  lea     r9, [r13+20h]
0x140016822  mov     ecx, [rbx+0C0h]
0x140016828  lea     eax, [rcx+1]
0x14001682b  mov     [rbx+0C0h], eax
0x140016831  mov     eax, [rdx]
0x140016833  mov     [rbx+1FCh], eax
0x140016839  mov     eax, [r9]
0x14001683c  mov     [rbx+200h], eax
0x140016842  mov     [rbx+0C0h], ecx
0x140016848  test    ecx, ecx
0x14001684a  jnz     short loc_140016871
0x14001684c  mov     rcx, [rdi]
0x14001684f  add     rcx, 88h; FastMutex
0x140016856  mov     qword ptr [rbx+0B8h], 0
0x140016861  call    cs:__imp_ExReleaseFastMutex
0x140016868  nop     dword ptr [rax+rax+00h]
0x14001686d  lea     r9, [r13+20h]
0x140016871  xor     bpl, bpl
0x140016874  mov     r8b, [rsp+78h+arg_18]
0x14001687c  mov     rdx, r9
0x14001687f  mov     rcx, r12
0x140016882  call    CdUpdatePathEntryName
0x140016887  mov     r8, [rsp+78h+arg_10]
0x14001688f  lea     rdx, [r13+68h]
0x140016893  xor     r9d, r9d
0x140016896  mov     byte ptr [rsp+78h+var_58], 0
0x14001689b  call    CdIsNameInExpression
0x1400168a0  test    al, al
0x1400168a2  jnz     short loc_1400168DE
0x1400168a4  lea     r9, [r13+20h]
0x1400168a8  mov     r14d, [r15]
0x1400168ab  mov     r8, r9
0x1400168ae  mov     esi, [r9]
0x1400168b1  mov     rdx, r13
0x1400168b4  mov     rcx, r12
0x1400168b7  call    CdLookupNextPathEntry
0x1400168bc  test    al, al
0x1400168be  jz      loc_140016954
0x1400168c4  mov     eax, [rbx+1F8h]
0x1400168ca  mov     rdx, r15
0x1400168cd  mov     ecx, [r13+30h]
0x1400168d1  cmp     ecx, eax
0x1400168d3  ja      short loc_1400168E2
0x1400168d5  lea     r9, [r13+20h]
0x1400168d9  jmp     loc_1400167DB
0x1400168de  mov     al, 1
0x1400168e0  jmp     short loc_14001695B
0x1400168e2  test    bpl, bpl
0x1400168e5  jz      short loc_140016954
0x1400168e7  mov     rbp, gs:188h
0x1400168f0  cmp     rbp, [rbx+0B8h]
0x1400168f7  jz      short loc_140016916
0x1400168f9  mov     rcx, [rdi]
0x1400168fc  add     rcx, 88h; FastMutex
0x140016903  call    cs:__imp_ExAcquireFastMutex
0x14001690a  nop     dword ptr [rax+rax+00h]
0x14001690f  mov     [rbx+0B8h], rbp
0x140016916  mov     ecx, [rbx+0C0h]
0x14001691c  mov     [rbx+1FCh], r14d
0x140016923  mov     [rbx+200h], esi
0x140016929  mov     [rbx+0C0h], ecx
0x14001692f  test    ecx, ecx
0x140016931  jnz     short loc_140016954
0x140016933  mov     rcx, [rdi]
0x140016936  add     rcx, 88h; FastMutex
0x14001693d  mov     qword ptr [rbx+0B8h], 0
0x140016948  call    cs:__imp_ExReleaseFastMutex
0x14001694f  nop     dword ptr [rax+rax+00h]
0x140016954  mov     al, [rsp+78h+arg_8]
0x14001695b  mov     rbx, [rsp+78h+arg_0]
0x140016963  add     rsp, 40h
0x140016967  pop     r15
0x140016969  pop     r14
0x14001696b  pop     r13
0x14001696d  pop     r12
0x14001696f  pop     rdi
0x140016970  pop     rsi
0x140016971  pop     rbp
0x140016972  retn
0x140016974  mov     r9d, 130000h
0x14001697a  mov     dword ptr [rsp+78h+var_58], 178h
0x140016982  xor     r8d, r8d
0x140016985  mov     edx, 0C0000032h
0x14001698a  call    CdRaiseStatusEx
```
