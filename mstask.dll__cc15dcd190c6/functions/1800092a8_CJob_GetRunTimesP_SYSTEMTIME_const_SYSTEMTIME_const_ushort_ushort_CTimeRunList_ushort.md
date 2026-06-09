# CJob::GetRunTimesP(_SYSTEMTIME const *,_SYSTEMTIME const *,ushort *,ushort,CTimeRunList *,ushort *)

- ea: `0x1800092a8`
- end: `0x1800093e7`
- name: `?GetRunTimesP@CJob@@QEAAJPEBU_SYSTEMTIME@@0PEAGGPEAVCTimeRunList@@1@Z`
- size: `319`
- prototype: `int(CJob *__hidden this, const struct _SYSTEMTIME *, const struct _SYSTEMTIME *, unsigned __int16 *, unsigned __int16, struct CTimeRunList *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180009cd0`
- `0x18000cff4`
- `0x18000e0c0`

## callees

- `0x1800018c0`
- `0x1800092a8`

## pseudocode

```c
int __fastcall CJob::GetRunTimesP(
        CJob *this,
        const struct _SYSTEMTIME *a2,
        const struct _SYSTEMTIME *a3,
        unsigned __int16 *a4,
        unsigned __int16 a5,
        struct CTimeRunList *a6)
{
  int result; // eax
  unsigned __int16 v9; // ax
  unsigned int v10; // esi
  int v11; // edi
  int v12; // r12d
  unsigned __int16 v13; // r14
  int v14; // ebx
  unsigned __int16 v15; // [rsp+A0h] [rbp+8h]
  const struct _SYSTEMTIME *v16; // [rsp+A8h] [rbp+10h]
  const struct _SYSTEMTIME *v17; // [rsp+B0h] [rbp+18h]

  v17 = a3;
  v16 = a2;
  if ( (*((_DWORD *)this + 22) & 4) != 0 )
    return 267010;
  v9 = *((_WORD *)this + 16);
  v10 = *((_DWORD *)this + 22) & 0x7FFF;
  v11 = 0;
  v15 = v9;
  v12 = 0;
  v13 = 0;
  v14 = 267016;
  while ( v13 < v9 )
  {
    result = GetTriggerRunTimes(
               (struct _TASK_TRIGGER *)(*((_QWORD *)this + 3) + 48LL * v13),
               a2,
               a3,
               a4,
               a5,
               a6,
               0,
               v10,
               *((_DWORD *)this + 19),
               *((_WORD *)this + 34),
               *((_WORD *)this + 35));
    if ( result < 0 )
      return result;
    if ( result == 267016 )
    {
      v11 = 1;
    }
    else if ( !result )
    {
      v12 = 1;
      if ( *a4 >= a5 && !a6 )
        goto LABEL_13;
    }
    v9 = v15;
    ++v13;
    a3 = v17;
    a2 = v16;
  }
  if ( !v12 )
    return (v11 != 0) + 267015;
LABEL_13:
  if ( *a4 || !v11 )
    return 0;
  return v14;
}

```

## disassembly

```asm
0x1800092a8  mov     [rsp+arg_18], rbx
0x1800092ad  mov     [rsp+arg_10], r8
0x1800092b2  mov     [rsp+arg_8], rdx
0x1800092b7  push    rbp
0x1800092b8  push    rsi
0x1800092b9  push    rdi
0x1800092ba  push    r12
0x1800092bc  push    r13
0x1800092be  push    r14
0x1800092c0  push    r15
0x1800092c2  sub     rsp, 60h
0x1800092c6  mov     esi, [rcx+58h]
0x1800092c9  mov     r15, r9
0x1800092cc  mov     rbp, rcx
0x1800092cf  test    sil, 4
0x1800092d3  jz      short loc_1800092DF
0x1800092d5  mov     eax, 41302h
0x1800092da  jmp     loc_1800093CF
0x1800092df  movzx   eax, word ptr [rcx+20h]
0x1800092e3  and     esi, 7FFFh
0x1800092e9  mov     r13, [rsp+98h+arg_28]
0x1800092f1  xor     r9d, r9d
0x1800092f4  mov     edi, r9d
0x1800092f7  mov     [rsp+98h+arg_0], ax
0x1800092ff  mov     r12d, r9d
0x180009302  mov     r14d, r9d
0x180009305  mov     ebx, 41308h
0x18000930a  cmp     r14w, ax
0x18000930e  jnb     loc_1800093AD
0x180009314  movzx   eax, r14w
0x180009318  lea     rcx, [rax+rax*2]
0x18000931c  movzx   eax, word ptr [rbp+46h]
0x180009320  mov     [rsp+98h+var_48], ax; unsigned __int16
0x180009325  movzx   eax, word ptr [rbp+44h]
0x180009329  mov     [rsp+98h+var_50], ax; unsigned __int16
0x18000932e  mov     eax, [rbp+4Ch]
0x180009331  mov     [rsp+98h+var_58], eax; unsigned int
0x180009335  movzx   eax, [rsp+98h+arg_20]
0x18000933d  mov     [rsp+98h+var_60], esi; unsigned int
0x180009341  mov     [rsp+98h+var_68], r9; unsigned __int16 *
0x180009346  mov     r9, r15; unsigned __int16 *
0x180009349  shl     rcx, 4
0x18000934d  add     rcx, [rbp+18h]; struct _TASK_TRIGGER *
0x180009351  mov     [rsp+98h+var_70], r13; struct CTimeRunList *
0x180009356  mov     [rsp+98h+var_78], ax; unsigned __int16
0x18000935b  call    ?GetTriggerRunTimes@@YAJAEAU_TASK_TRIGGER@@PEBU_SYSTEMTIME@@1PEAGGPEAVCTimeRunList@@2KKGG@Z; GetTriggerRunTimes(_TASK_TRIGGER &,_SYSTEMTIME const *,_SYSTEMTIME const *,ushort *,ushort,CTimeRunList *,ushort *,ulong,ulong,ushort,ushort)
0x180009360  xor     r9d, r9d
0x180009363  test    eax, eax
0x180009365  js      short loc_1800093CF
0x180009367  cmp     eax, ebx
0x180009369  jnz     short loc_180009371
0x18000936b  lea     edi, [r9+1]
0x18000936f  jmp     short loc_18000938C
0x180009371  test    eax, eax
0x180009373  jnz     short loc_18000938C
0x180009375  lea     r12d, [rax+1]
0x180009379  movzx   eax, [rsp+98h+arg_20]
0x180009381  cmp     [r15], ax
0x180009385  jb      short loc_18000938C
0x180009387  test    r13, r13
0x18000938a  jz      short loc_1800093B2
0x18000938c  movzx   eax, [rsp+98h+arg_0]
0x180009394  inc     r14w
0x180009398  mov     r8, [rsp+98h+arg_10]
0x1800093a0  mov     rdx, [rsp+98h+arg_8]
0x1800093a8  jmp     loc_18000930A
0x1800093ad  test    r12d, r12d
0x1800093b0  jz      short loc_1800093C1
0x1800093b2  cmp     [r15], r9w
0x1800093b6  jnz     short loc_1800093BC
0x1800093b8  test    edi, edi
0x1800093ba  jnz     short loc_1800093CD
0x1800093bc  mov     ebx, r9d
0x1800093bf  jmp     short loc_1800093CD
0x1800093c1  neg     edi
0x1800093c3  sbb     ebx, ebx
0x1800093c5  neg     ebx
0x1800093c7  add     ebx, 41307h
0x1800093cd  mov     eax, ebx
0x1800093cf  mov     rbx, [rsp+98h+arg_18]
0x1800093d7  add     rsp, 60h
0x1800093db  pop     r15
0x1800093dd  pop     r14
0x1800093df  pop     r13
0x1800093e1  pop     r12
0x1800093e3  pop     rdi
0x1800093e4  pop     rsi
0x1800093e5  pop     rbp
0x1800093e6  retn
```
