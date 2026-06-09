# HsmOsCheckAppCompatPolicy

- ea: `0x1400074b0`
- end: `0x140007834`
- name: `HsmOsCheckAppCompatPolicy`
- size: `900`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140002aec`
- `0x140049778`
- `0x14005aaf0`
- `0x14005be10`
- `0x14005c600`
- `0x14007a0d4`

## callees

- `0x1400074b0`
- `0x14000783c`
- `0x140007944`
- `0x14000c24c`
- `0x14000c284`
- `0x14001e140`

## import_xrefs

- `ntoskrnl!PsGetProcessWow64Process` at `0x14000756e`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400075c0`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400076f3`
- `ntoskrnl!PsGetProcessWow64Process` at `0x140007717`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14000773e`
- `ntoskrnl!PsGetProcessWow64Process` at `0x140007762`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14000756e`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400075c0`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400076f3`
- `ntoskrnl!PsGetProcessWow64Process` at `0x140007717`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14000773e`
- `ntoskrnl!PsGetProcessWow64Process` at `0x140007762`
- `ntoskrnl!PsGetProcessPeb` at `0x140007587`
- `ntoskrnl!PsGetProcessPeb` at `0x1400075a0`
- `ntoskrnl!PsGetProcessPeb` at `0x1400075d9`
- `ntoskrnl!PsGetProcessPeb` at `0x1400075f2`
- `ntoskrnl!PsGetProcessPeb` at `0x1400077bc`
- `ntoskrnl!PsGetProcessPeb` at `0x140007805`
- `ntoskrnl!PsGetProcessPeb` at `0x140007587`
- `ntoskrnl!PsGetProcessPeb` at `0x1400075a0`
- `ntoskrnl!PsGetProcessPeb` at `0x1400075d9`
- `ntoskrnl!PsGetProcessPeb` at `0x1400075f2`
- `ntoskrnl!PsGetProcessPeb` at `0x1400077bc`
- `ntoskrnl!PsGetProcessPeb` at `0x140007805`
- `ntoskrnl!KeStackAttachProcess` at `0x1400076ab`
- `ntoskrnl!KeStackAttachProcess` at `0x1400076ab`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000750c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000754c`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400076c0`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400076e4`
- `ntoskrnl!PsGetCurrentProcess` at `0x140007708`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000772f`
- `ntoskrnl!PsGetCurrentProcess` at `0x140007753`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400077ad`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400077cd`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400077f6`
- `ntoskrnl!PsGetCurrentProcess` at `0x140007816`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000750c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000754c`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400076c0`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400076e4`
- `ntoskrnl!PsGetCurrentProcess` at `0x140007708`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000772f`
- `ntoskrnl!PsGetCurrentProcess` at `0x140007753`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400077ad`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400077cd`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400077f6`
- `ntoskrnl!PsGetCurrentProcess` at `0x140007816`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000765b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000765b`

## pseudocode

```c
__int64 __fastcall HsmOsCheckAppCompatPolicy(__int128 *a1, __int64 a2, _BYTE *a3, __int64 a4)
{
  __int128 *v4; // rdi
  int v6; // ebp
  __int64 v7; // rax
  char v8; // si
  struct _KPROCESS *CurrentProcess; // r14
  unsigned __int8 v10; // r15
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 ProcessWow64Process; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // r14
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // r9
  unsigned int IsForegroundHydrator; // eax
  unsigned int v28; // ebx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  int v40; // ebp
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r9
  __int128 v47; // [rsp+30h] [rbp-78h] BYREF
  __int64 v48; // [rsp+40h] [rbp-68h]
  struct _KAPC_STATE ApcState; // [rsp+48h] [rbp-60h] BYREF

  v4 = &v47;
  v47 = 0;
  if ( a1 )
    v4 = a1;
  v48 = 0;
  *a3 = 0;
  v6 = a2;
  memset(&ApcState, 0, sizeof(ApcState));
  if ( !a1 )
    *((_QWORD *)v4 + 2) = PsGetCurrentProcess(0, a2, a3, a4);
  v7 = *((_QWORD *)v4 + 1);
  v8 = 0;
  if ( v7 )
  {
    v21 = v7 + 32;
    v10 = 0;
    v26 = v7 + 40;
    goto LABEL_20;
  }
  CurrentProcess = (struct _KPROCESS *)*((_QWORD *)v4 + 2);
  v10 = 1;
  if ( !CurrentProcess )
    CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(a1, a2, a3, a4);
  if ( CurrentProcess != (struct _KPROCESS *)PsGetCurrentProcess(a1, a2, a3, a4) )
  {
    KeStackAttachProcess(CurrentProcess, &ApcState);
    v8 = 1;
  }
  v14 = *((_QWORD *)v4 + 2);
  if ( !v14 )
  {
    v30 = PsGetCurrentProcess(0, v11, v12, v13);
    if ( !PsGetProcessWow64Process(v30) )
    {
      v41 = PsGetCurrentProcess(v32, v31, v33, v34);
      if ( PsGetProcessPeb(v41) )
      {
        v20 = PsGetCurrentProcess(v42, v17, v18, v19);
        goto LABEL_14;
      }
      goto LABEL_35;
    }
    v16 = PsGetCurrentProcess(v32, v31, v33, v34);
LABEL_31:
    v21 = PsGetProcessWow64Process(v16) + 472;
    goto LABEL_15;
  }
  ProcessWow64Process = PsGetProcessWow64Process(v14);
  v16 = *((_QWORD *)v4 + 2);
  if ( ProcessWow64Process )
    goto LABEL_31;
  if ( PsGetProcessPeb(v16) )
  {
    v20 = *((_QWORD *)v4 + 2);
LABEL_14:
    v21 = PsGetProcessPeb(v20) + 712;
    goto LABEL_15;
  }
LABEL_35:
  v21 = 0;
LABEL_15:
  v22 = *((_QWORD *)v4 + 2);
  if ( !v22 )
  {
    v35 = PsGetCurrentProcess(0, v17, v18, v19);
    if ( !PsGetProcessWow64Process(v35) )
    {
      v43 = PsGetCurrentProcess(v37, v36, v38, v39);
      if ( PsGetProcessPeb(v43) )
      {
        v25 = PsGetCurrentProcess(v45, v44, a3, v46);
        goto LABEL_19;
      }
      goto LABEL_39;
    }
    v24 = PsGetCurrentProcess(v37, v36, v38, v39);
LABEL_34:
    v26 = PsGetProcessWow64Process(v24) + 1120;
    goto LABEL_20;
  }
  v23 = PsGetProcessWow64Process(v22);
  v24 = *((_QWORD *)v4 + 2);
  if ( v23 )
    goto LABEL_34;
  if ( PsGetProcessPeb(v24) )
  {
    v25 = *((_QWORD *)v4 + 2);
LABEL_19:
    v26 = PsGetProcessPeb(v25) + 1960;
    goto LABEL_20;
  }
LABEL_39:
  v26 = 0;
LABEL_20:
  if ( v6 == 3 )
  {
    IsForegroundHydrator = HsmiOsIsForegroundHydrator(*((_QWORD *)v4 + 2), v10, v21, v26, (__int64)a3);
LABEL_22:
    v28 = IsForegroundHydrator;
    goto LABEL_23;
  }
  v28 = 0;
  if ( !v6 )
  {
    IsForegroundHydrator = HsmiOsIsHydrationDisallowed((_DWORD)v4, v10, v21, v26, (__int64)a3);
    goto LABEL_22;
  }
  v40 = v6 - 1;
  if ( v40 )
  {
    if ( v40 == 1 )
      *a3 = HsmiOsIsFullHydrationOnOpenEnabled(v21, v10, a3, v26);
    else
      v28 = -1073741595;
  }
  else
  {
    *a3 = HsmiOsIsFullHydrationEnabled(v21, v10, a3, v26);
  }
LABEL_23:
  if ( v8 )
    KeUnstackDetachProcess(&ApcState);
  return v28;
}

```

## disassembly

```asm
0x1400074b0  mov     r11, rsp
0x1400074b3  push    rbx
0x1400074b4  sub     rsp, 0A0h
0x1400074bb  mov     rax, cs:__security_cookie
0x1400074c2  xor     rax, rsp
0x1400074c5  mov     [rsp+0A8h+var_30], rax
0x1400074ca  mov     [r11+10h], rbp
0x1400074ce  xorps   xmm0, xmm0
0x1400074d1  xor     eax, eax
0x1400074d3  mov     [r11+20h], rsi
0x1400074d7  mov     [r11-10h], rdi
0x1400074db  test    rcx, rcx
0x1400074de  lea     rdi, [r11-78h]
0x1400074e2  mov     [r11-18h], r12
0x1400074e6  movups  [rsp+0A8h+var_78], xmm0
0x1400074eb  cmovnz  rdi, rcx
0x1400074ef  mov     [r11-68h], rax
0x1400074f3  mov     r12, r8
0x1400074f6  mov     [r8], al
0x1400074f9  mov     ebp, edx
0x1400074fb  movups  xmmword ptr [rsp+0A8h+ApcState.ApcListHead.Flink], xmm0
0x140007500  movups  xmmword ptr [rsp+0A8h+ApcState.ApcListHead.Flink+10h], xmm0
0x140007505  movups  xmmword ptr [rsp+0A8h+ApcState.Process], xmm0
0x14000750a  jnz     short loc_14000751C
0x14000750c  call    cs:__imp_PsGetCurrentProcess
0x140007513  nop     dword ptr [rax+rax+00h]
0x140007518  mov     [rdi+10h], rax
0x14000751c  mov     rax, [rdi+8]
0x140007520  xor     sil, sil
0x140007523  mov     [rsp+0A8h+var_20], r14
0x14000752b  mov     [rsp+0A8h+var_28], r15
0x140007533  test    rax, rax
0x140007536  jnz     loc_1400076D4
0x14000753c  mov     r14, [rdi+10h]
0x140007540  mov     r15b, 1
0x140007543  test    r14, r14
0x140007546  jz      loc_1400076C0
0x14000754c  call    cs:__imp_PsGetCurrentProcess
0x140007553  nop     dword ptr [rax+rax+00h]
0x140007558  cmp     r14, rax
0x14000755b  jnz     loc_1400076A3
0x140007561  mov     rcx, [rdi+10h]
0x140007565  test    rcx, rcx
0x140007568  jz      loc_1400076E4
0x14000756e  call    cs:__imp_PsGetProcessWow64Process
0x140007575  nop     dword ptr [rax+rax+00h]
0x14000757a  mov     rcx, [rdi+10h]
0x14000757e  test    rax, rax
0x140007581  jnz     loc_140007717
0x140007587  call    cs:__imp_PsGetProcessPeb
0x14000758e  nop     dword ptr [rax+rax+00h]
0x140007593  test    rax, rax
0x140007596  jz      loc_14000777A
0x14000759c  mov     rcx, [rdi+10h]
0x1400075a0  call    cs:__imp_PsGetProcessPeb
0x1400075a7  nop     dword ptr [rax+rax+00h]
0x1400075ac  lea     r14, [rax+2C8h]
0x1400075b3  mov     rcx, [rdi+10h]
0x1400075b7  test    rcx, rcx
0x1400075ba  jz      loc_14000772F
0x1400075c0  call    cs:__imp_PsGetProcessWow64Process
0x1400075c7  nop     dword ptr [rax+rax+00h]
0x1400075cc  mov     rcx, [rdi+10h]
0x1400075d0  test    rax, rax
0x1400075d3  jnz     loc_140007762
0x1400075d9  call    cs:__imp_PsGetProcessPeb
0x1400075e0  nop     dword ptr [rax+rax+00h]
0x1400075e5  test    rax, rax
0x1400075e8  jz      loc_1400077A5
0x1400075ee  mov     rcx, [rdi+10h]
0x1400075f2  call    cs:__imp_PsGetProcessPeb
0x1400075f9  nop     dword ptr [rax+rax+00h]
0x1400075fe  lea     r9, [rax+7A8h]
0x140007605  cmp     ebp, 3
0x140007608  jnz     short loc_140007680
0x14000760a  mov     rcx, [rdi+10h]
0x14000760e  mov     r8, r14
0x140007611  movzx   edx, r15b
0x140007615  mov     [rsp+0A8h+var_88], r12
0x14000761a  call    HsmiOsIsForegroundHydrator
0x14000761f  mov     ebx, eax
0x140007621  mov     r15, [rsp+0A8h+var_28]
0x140007629  test    sil, sil
0x14000762c  mov     rsi, [rsp+0A8h+arg_18]
0x140007634  mov     r14, [rsp+0A8h+var_20]
0x14000763c  mov     r12, [rsp+0A8h+var_18]
0x140007644  mov     rdi, [rsp+0A8h+var_10]
0x14000764c  mov     rbp, [rsp+0A8h+arg_8]
0x140007654  jz      short loc_140007667
0x140007656  lea     rcx, [rsp+0A8h+ApcState]; ApcState
0x14000765b  call    cs:__imp_KeUnstackDetachProcess
0x140007662  nop     dword ptr [rax+rax+00h]
0x140007667  mov     eax, ebx
0x140007669  mov     rcx, [rsp+0A8h+var_30]
0x14000766e  xor     rcx, rsp; StackCookie
0x140007671  call    __security_check_cookie
0x140007676  add     rsp, 0A0h
0x14000767d  pop     rbx
0x14000767e  retn
0x140007680  xor     ebx, ebx
0x140007682  test    ebp, ebp
0x140007684  jnz     loc_140007782
0x14000768a  mov     r8, r14
0x14000768d  mov     [rsp+0A8h+var_88], r12
0x140007692  movzx   edx, r15b
0x140007696  mov     rcx, rdi
0x140007699  call    HsmiOsIsHydrationDisallowed
0x14000769e  jmp     loc_14000761F
0x1400076a3  lea     rdx, [rsp+0A8h+ApcState]; ApcState
0x1400076a8  mov     rcx, r14; PROCESS
0x1400076ab  call    cs:__imp_KeStackAttachProcess
0x1400076b2  nop     dword ptr [rax+rax+00h]
0x1400076b7  movzx   esi, r15b
0x1400076bb  jmp     loc_140007561
0x1400076c0  call    cs:__imp_PsGetCurrentProcess
0x1400076c7  nop     dword ptr [rax+rax+00h]
0x1400076cc  mov     r14, rax
0x1400076cf  jmp     loc_14000754C
0x1400076d4  lea     r14, [rax+20h]
0x1400076d8  xor     r15b, r15b
0x1400076db  lea     r9, [rax+28h]
0x1400076df  jmp     loc_140007605
0x1400076e4  call    cs:__imp_PsGetCurrentProcess
0x1400076eb  nop     dword ptr [rax+rax+00h]
0x1400076f0  mov     rcx, rax
0x1400076f3  call    cs:__imp_PsGetProcessWow64Process
0x1400076fa  nop     dword ptr [rax+rax+00h]
0x1400076ff  test    rax, rax
0x140007702  jz      loc_1400077AD
0x140007708  call    cs:__imp_PsGetCurrentProcess
0x14000770f  nop     dword ptr [rax+rax+00h]
0x140007714  mov     rcx, rax
0x140007717  call    cs:__imp_PsGetProcessWow64Process
0x14000771e  nop     dword ptr [rax+rax+00h]
0x140007723  lea     r14, [rax+1D8h]
0x14000772a  jmp     loc_1400075B3
0x14000772f  call    cs:__imp_PsGetCurrentProcess
0x140007736  nop     dword ptr [rax+rax+00h]
0x14000773b  mov     rcx, rax
0x14000773e  call    cs:__imp_PsGetProcessWow64Process
0x140007745  nop     dword ptr [rax+rax+00h]
0x14000774a  test    rax, rax
0x14000774d  jz      loc_1400077F6
0x140007753  call    cs:__imp_PsGetCurrentProcess
0x14000775a  nop     dword ptr [rax+rax+00h]
0x14000775f  mov     rcx, rax
0x140007762  call    cs:__imp_PsGetProcessWow64Process
0x140007769  nop     dword ptr [rax+rax+00h]
0x14000776e  lea     r9, [rax+460h]
0x140007775  jmp     loc_140007605
0x14000777a  xor     r14d, r14d
0x14000777d  jmp     loc_1400075B3
0x140007782  sub     ebp, 1
0x140007785  jz      short loc_1400077E1
0x140007787  cmp     ebp, 1
0x14000778a  jnz     loc_14000782A
0x140007790  movzx   edx, r15b
0x140007794  mov     rcx, r14
0x140007797  call    HsmiOsIsFullHydrationOnOpenEnabled
0x14000779c  mov     [r12], al
0x1400077a0  jmp     loc_140007621
0x1400077a5  xor     r9d, r9d
0x1400077a8  jmp     loc_140007605
0x1400077ad  call    cs:__imp_PsGetCurrentProcess
0x1400077b4  nop     dword ptr [rax+rax+00h]
0x1400077b9  mov     rcx, rax
0x1400077bc  call    cs:__imp_PsGetProcessPeb
0x1400077c3  nop     dword ptr [rax+rax+00h]
0x1400077c8  test    rax, rax
0x1400077cb  jz      short loc_14000777A
0x1400077cd  call    cs:__imp_PsGetCurrentProcess
0x1400077d4  nop     dword ptr [rax+rax+00h]
0x1400077d9  mov     rcx, rax
0x1400077dc  jmp     loc_1400075A0
0x1400077e1  movzx   edx, r15b
0x1400077e5  mov     rcx, r14
0x1400077e8  call    HsmiOsIsFullHydrationEnabled
0x1400077ed  mov     [r12], al
0x1400077f1  jmp     loc_140007621
0x1400077f6  call    cs:__imp_PsGetCurrentProcess
0x1400077fd  nop     dword ptr [rax+rax+00h]
0x140007802  mov     rcx, rax
0x140007805  call    cs:__imp_PsGetProcessPeb
0x14000780c  nop     dword ptr [rax+rax+00h]
0x140007811  test    rax, rax
0x140007814  jz      short loc_1400077A5
0x140007816  call    cs:__imp_PsGetCurrentProcess
0x14000781d  nop     dword ptr [rax+rax+00h]
0x140007822  mov     rcx, rax
0x140007825  jmp     loc_1400075F2
0x14000782a  mov     ebx, 0C00000E5h
0x14000782f  jmp     loc_140007621
```
