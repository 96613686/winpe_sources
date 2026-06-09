# MlLogOpenLog

- ea: `0x1c004cb00`
- end: `0x1c004cedd`
- name: `MlLogOpenLog`
- size: `989`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1c0053e1c`

## callees

- `0x1c004cb00`
- `0x1c004ed9c`
- `0x1c004f0dc`
- `0x1c004f32c`
- `0x1c006ac80`
- `0x1c006acc0`
- `0x1c006af80`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c004cbcd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c004cd82`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c004cbcd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c004cd82`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c004cea7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00867f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c008680c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c008681d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c004cea7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00867f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c008680c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c008681d`
- `ntoskrnl!KeInitializeEvent` at `0x1c004cd07`
- `ntoskrnl!KeInitializeEvent` at `0x1c004cd07`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c004ccdc`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c004ccef`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c004ccdc`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c004ccef`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1c004ccc9`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1c004ccc9`
- `ntoskrnl!ExUuidCreate` at `0x1c008677e`
- `ntoskrnl!ExUuidCreate` at `0x1c008677e`

## pseudocode

```c
__int64 __fastcall MlLogOpenLog(
        __int64 a1,
        char a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        char a9,
        __int64 a10,
        int a11,
        __int64 a12,
        int a13,
        _DWORD *a14,
        _QWORD *a15)
{
  bool v15; // zf
  PVOID v18; // rsi
  char *v19; // rbx
  char *PoolWithTag; // rax
  int v21; // eax
  int v22; // ebp
  int v23; // ecx
  int v24; // eax
  PVOID v25; // rax
  NTSTATUS ControlArea; // edi
  int v27; // eax
  int v28; // ebp
  __int64 v30; // rax
  void *v31; // rcx
  void *v32; // rcx

  v15 = AA_FAIL_LOG_OPEN == 0;
  v18 = 0;
  v19 = 0;
  *a15 = 0;
  if ( !v15 && !a14 && !a2 )
    return (unsigned int)-1073741670;
  if ( a5 <= 0x2000 )
  {
    ControlArea = -1073741811;
    goto LABEL_34;
  }
  if ( a5 % 4096 || a6 % 4096 )
    return (unsigned int)-1073741811;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x2F50u, 0x6C6C534Du);
  v19 = PoolWithTag;
  if ( !PoolWithTag )
    return (unsigned int)-1073741670;
  memset(PoolWithTag, 0, 0x2F50u);
  v21 = a13;
  *((_DWORD *)v19 + 914) = 1;
  if ( !a13 )
    v21 = 4096;
  *((_DWORD *)v19 + 2997) = v21;
  if ( (a9 & 1) != 0 )
    *((_DWORD *)v19 + 15) |= 1u;
  v22 = 4;
  if ( (a9 & 4) != 0 )
  {
    *((_DWORD *)v19 + 2994) = 8;
    v23 = 24;
  }
  else
  {
    v23 = 16;
  }
  *((_DWORD *)v19 + 917) = 1;
  v24 = *((_DWORD *)v19 + 2994);
  if ( (a9 & 0x10) != 0 )
    v24 = v23;
  *((_DWORD *)v19 + 2995) = 1735347277;
  *((_DWORD *)v19 + 2994) = v24;
  *((_DWORD *)v19 + 2996) = a11;
  *((_QWORD *)v19 + 459) = a7 / 4096;
  *((_QWORD *)v19 + 460) = a8 / 4096;
  *((_QWORD *)v19 + 1) = a6 / 4096;
  *((_DWORD *)v19 + 916) = 4096;
  *((_QWORD *)v19 + 2) = (a5 + a6) / 4096;
  *((_DWORD *)v19 + 924) = a5 / 4096;
  *((_QWORD *)v19 + 463) = RefsLargeEof;
  *((_QWORD *)v19 + 461) = 0;
  *((_DWORD *)v19 + 925) = 0;
  KeInitializeGuardedMutex((PKGUARDED_MUTEX)(v19 + 3720));
  KeInitializeSpinLock((PKSPIN_LOCK)v19 + 472);
  KeInitializeSpinLock((PKSPIN_LOCK)v19 + 1499);
  KeInitializeEvent((PRKEVENT)v19 + 500, NotificationEvent, 0);
  *((_DWORD *)v19 + 3022) = 1;
  if ( *((_QWORD *)&xmmword_1C0137130 + 1) )
    (*((void (__fastcall **)(__int64, char *))&xmmword_1C0137130 + 1))(a1, v19 + 12088);
  if ( !*((_QWORD *)&xmmword_1C0137120 + 1) || !(_QWORD)xmmword_1C0137130 )
    *((_DWORD *)v19 + 3022) = 1;
  *((_QWORD *)v19 + 1512) = a1;
  if ( a2 )
  {
    if ( a14 )
    {
      *((_DWORD *)v19 + 7) = a14[1] + 1;
      *((_DWORD *)v19 + 6) = *a14;
      ++a14[1];
      *((_DWORD *)v19 + 15) |= 2u;
    }
    else
    {
      *((_QWORD *)v19 + 3) = 1;
    }
    v30 = *((_QWORD *)v19 + 3);
    *((_DWORD *)v19 + 14) = 1;
    *((_DWORD *)v19 + 16) = 1;
    *((_QWORD *)v19 + 4) = v30;
    *(_QWORD *)v19 = 0;
    ControlArea = ExUuidCreate((UUID *)(v19 + 40));
    if ( ControlArea >= 0 )
    {
      v22 = (a14 != 0) + 6;
      goto LABEL_28;
    }
  }
  else
  {
    *((_DWORD *)v19 + 914) = 2;
    v25 = ExAllocatePoolWithTag((POOL_TYPE)512, 0xE48u, 0x6C6C534Du);
    v18 = v25;
    if ( v25 )
    {
      memset(v25, 0, 0xE48u);
      ControlArea = LogCoreReadControlArea(v19, a1, v18);
      if ( ControlArea < 0 )
      {
        *((_DWORD *)v19 + 914) = 3;
      }
      else
      {
        if ( *((_DWORD *)v18 + 16) == 1
          && *((_QWORD *)v19 + 1) == *((_QWORD *)v18 + 1)
          && *((_QWORD *)v19 + 2) == *((_QWORD *)v18 + 2)
          && ((*((_DWORD *)v19 + 15) & 1) == 0 || (*((_DWORD *)v18 + 15) & 1) != 0) )
        {
          memmove(v19, v18, 0xE48u);
          v27 = *((_DWORD *)v19 + 9);
          ++*((_DWORD *)v19 + 14);
          *((_DWORD *)v19 + 923) = v27;
          *((_DWORD *)v19 + 925) = v27;
          if ( (*((_DWORD *)v19 + 15) & 2) != 0 )
            v22 = 7;
LABEL_28:
          *((_DWORD *)v19 + 914) = v22;
          *((_QWORD *)v19 + 475) = *((_QWORD *)v19 + 3);
          *((_QWORD *)v19 + 464) = ML_LSN_NULL;
          ControlArea = LogInitializeFlushWindows(v19);
          if ( ControlArea >= 0 )
          {
            if ( (*((_DWORD *)v19 + 2994) & 0x10) != 0 )
            {
LABEL_33:
              *a15 = v19;
              v19 = 0;
            }
            else
            {
              v28 = 0;
              while ( 1 )
              {
                memmove(v19 + 7912, v19, 0xE48u);
                ControlArea = LogCoreWriteControlArea(v19, a1);
                if ( ControlArea < 0 )
                  break;
                if ( (unsigned int)++v28 >= 2 )
                  goto LABEL_33;
              }
            }
          }
          goto LABEL_34;
        }
        ControlArea = -1073741774;
      }
LABEL_34:
      if ( v18 )
        ExFreePoolWithTag(v18, 0);
      goto LABEL_36;
    }
    ControlArea = -1073741670;
  }
LABEL_36:
  if ( v19 )
  {
    v31 = (void *)*((_QWORD *)v19 + 1496);
    if ( v31 )
      ExFreePoolWithTag(v31, 0);
    v32 = (void *)*((_QWORD *)v19 + 473);
    if ( v32 )
      ExFreePoolWithTag(v32, 0);
    ExFreePoolWithTag(v19, 0);
  }
  return (unsigned int)ControlArea;
}

```

## disassembly

```asm
0x1c004cb00  mov     [rsp+arg_0], rbx
0x1c004cb05  mov     [rsp+arg_8], rbp
0x1c004cb0a  mov     [rsp+arg_10], rsi
0x1c004cb0f  push    rdi
0x1c004cb10  push    r12
0x1c004cb12  push    r13
0x1c004cb14  push    r14
0x1c004cb16  push    r15
0x1c004cb18  sub     rsp, 40h
0x1c004cb1c  mov     rax, [rsp+68h+arg_70]
0x1c004cb24  xor     r13d, r13d
0x1c004cb27  cmp     cs:AA_FAIL_LOG_OPEN, r13d
0x1c004cb2e  mov     r12b, dl
0x1c004cb31  mov     r14, [rsp+68h+arg_68]
0x1c004cb39  mov     r15, rcx
0x1c004cb3c  mov     esi, r13d
0x1c004cb3f  mov     ebx, r13d
0x1c004cb42  mov     [rax], r13
0x1c004cb45  jnz     loc_1C008670C
0x1c004cb4b  mov     rdi, [rsp+68h+arg_20]
0x1c004cb53  cmp     rdi, 2000h
0x1c004cb5a  jle     loc_1C00867DA
0x1c004cb60  mov     rax, rdi
0x1c004cb63  mov     ebp, 1000h
0x1c004cb68  cqo
0x1c004cb6a  idiv    rbp
0x1c004cb6d  mov     [rsp+68h+var_30], rax
0x1c004cb72  test    rdx, rdx
0x1c004cb75  jnz     loc_1C00867D0
0x1c004cb7b  mov     r13, [rsp+68h+arg_28]
0x1c004cb83  mov     rax, r13
0x1c004cb86  cqo
0x1c004cb88  idiv    rbp
0x1c004cb8b  mov     [rsp+68h+var_38], rax
0x1c004cb90  test    rdx, rdx
0x1c004cb93  jnz     loc_1C00867D0
0x1c004cb99  mov     rax, [rsp+68h+arg_30]
0x1c004cba1  mov     ecx, 200h; PoolType
0x1c004cba6  cqo
0x1c004cba8  mov     r8d, 6C6C534Dh; Tag
0x1c004cbae  idiv    rbp
0x1c004cbb1  mov     [rsp+68h+var_48], rax
0x1c004cbb6  mov     rax, [rsp+68h+arg_38]
0x1c004cbbe  cqo
0x1c004cbc0  idiv    rbp
0x1c004cbc3  mov     edx, 2F50h; NumberOfBytes
0x1c004cbc8  mov     [rsp+68h+var_40], rax
0x1c004cbcd  call    cs:__imp_ExAllocatePoolWithTag
0x1c004cbd4  nop     dword ptr [rax+rax+00h]
0x1c004cbd9  mov     rbx, rax
0x1c004cbdc  test    rax, rax
0x1c004cbdf  jz      loc_1C008671E
0x1c004cbe5  xor     edx, edx; Val
0x1c004cbe7  mov     r8d, 2F50h; Size
0x1c004cbed  mov     rcx, rax; void *
0x1c004cbf0  call    memset
0x1c004cbf5  mov     eax, [rsp+68h+arg_60]
0x1c004cbfc  mov     edx, 1
0x1c004cc01  test    eax, eax
0x1c004cc03  mov     [rbx+0E48h], edx
0x1c004cc09  cmovz   eax, ebp
0x1c004cc0c  mov     [rbx+2ED4h], eax
0x1c004cc12  mov     eax, dword ptr [rsp+68h+arg_40]
0x1c004cc19  test    dl, al
0x1c004cc1b  jz      short loc_1C004CC20
0x1c004cc1d  or      [rbx+3Ch], edx
0x1c004cc20  mov     ebp, 4
0x1c004cc25  test    bpl, al
0x1c004cc28  jnz     loc_1C0086728
0x1c004cc2e  lea     ecx, [rbp+0Ch]
0x1c004cc31  test    al, 10h
0x1c004cc33  mov     [rbx+0E54h], edx
0x1c004cc39  mov     eax, [rbx+2EC8h]
0x1c004cc3f  cmovnz  eax, ecx
0x1c004cc42  mov     dword ptr [rbx+2ECCh], 676F4C4Dh
0x1c004cc4c  mov     [rbx+2EC8h], eax
0x1c004cc52  mov     ecx, 1000h
0x1c004cc57  mov     eax, [rsp+68h+arg_50]
0x1c004cc5e  mov     [rbx+2ED0h], eax
0x1c004cc64  mov     rax, [rsp+68h+var_48]
0x1c004cc69  mov     [rbx+0E58h], rax
0x1c004cc70  mov     rax, [rsp+68h+var_40]
0x1c004cc75  mov     [rbx+0E60h], rax
0x1c004cc7c  mov     rax, [rsp+68h+var_38]
0x1c004cc81  mov     [rbx+8], rax
0x1c004cc85  lea     rax, [rdi+r13]
0x1c004cc89  cqo
0x1c004cc8b  mov     [rbx+0E50h], ecx
0x1c004cc91  idiv    rcx
0x1c004cc94  xor     r13d, r13d
0x1c004cc97  lea     rcx, [rbx+0E88h]; Mutex
0x1c004cc9e  mov     [rbx+10h], rax
0x1c004cca2  mov     rax, [rsp+68h+var_30]
0x1c004cca7  mov     [rbx+0E70h], eax
0x1c004ccad  mov     rax, cs:RefsLargeEof
0x1c004ccb4  mov     [rbx+0E78h], rax
0x1c004ccbb  mov     [rbx+0E68h], r13
0x1c004ccc2  mov     [rbx+0E74h], r13d
0x1c004ccc9  call    cs:__imp_KeInitializeGuardedMutex
0x1c004ccd0  nop     dword ptr [rax+rax+00h]
0x1c004ccd5  lea     rcx, [rbx+0EC0h]; SpinLock
0x1c004ccdc  call    cs:__imp_KeInitializeSpinLock
0x1c004cce3  nop     dword ptr [rax+rax+00h]
0x1c004cce8  lea     rcx, [rbx+2ED8h]; SpinLock
0x1c004ccef  call    cs:__imp_KeInitializeSpinLock
0x1c004ccf6  nop     dword ptr [rax+rax+00h]
0x1c004ccfb  lea     rcx, [rbx+2EE0h]; Event
0x1c004cd02  xor     r8d, r8d; State
0x1c004cd05  xor     edx, edx; Type
0x1c004cd07  call    cs:__imp_KeInitializeEvent
0x1c004cd0e  nop     dword ptr [rax+rax+00h]
0x1c004cd13  lea     ecx, [r13+1]
0x1c004cd17  lea     rdi, [rbx+2F38h]
0x1c004cd1e  mov     [rdi], ecx
0x1c004cd20  mov     rax, qword ptr cs:xmmword_1C0137130+8
0x1c004cd27  test    rax, rax
0x1c004cd2a  jz      short loc_1C004CD3C
0x1c004cd2c  mov     rdx, rdi
0x1c004cd2f  mov     rcx, r15
0x1c004cd32  call    cs:__guard_dispatch_icall_fptr
0x1c004cd38  lea     ecx, [r13+1]
0x1c004cd3c  cmp     qword ptr cs:xmmword_1C0137120+8, r13
0x1c004cd43  jz      loc_1C008673C
0x1c004cd49  cmp     qword ptr cs:xmmword_1C0137130, r13
0x1c004cd50  jz      loc_1C008673C
0x1c004cd56  mov     [rbx+2F40h], r15
0x1c004cd5d  mov     edi, 0E48h
0x1c004cd62  test    r12b, r12b
0x1c004cd65  jnz     loc_1C0086743
0x1c004cd6b  mov     r8d, 6C6C534Dh; Tag
0x1c004cd71  mov     dword ptr [rbx+0E48h], 2
0x1c004cd7b  mov     edx, edi; NumberOfBytes
0x1c004cd7d  mov     ecx, 200h; PoolType
0x1c004cd82  call    cs:__imp_ExAllocatePoolWithTag
0x1c004cd89  nop     dword ptr [rax+rax+00h]
0x1c004cd8e  mov     rsi, rax
0x1c004cd91  test    rax, rax
0x1c004cd94  jz      loc_1C00867A3
0x1c004cd9a  mov     r8d, edi; Size
0x1c004cd9d  xor     edx, edx; Val
0x1c004cd9f  mov     rcx, rax; void *
0x1c004cda2  call    memset
0x1c004cda7  mov     r8, rsi
0x1c004cdaa  mov     rdx, r15
0x1c004cdad  mov     rcx, rbx
0x1c004cdb0  call    LogCoreReadControlArea
0x1c004cdb5  mov     edi, eax
0x1c004cdb7  test    eax, eax
0x1c004cdb9  js      loc_1C00867AD
0x1c004cdbf  cmp     dword ptr [rsi+40h], 1
0x1c004cdc3  jnz     loc_1C00867BC
0x1c004cdc9  mov     rax, [rsi+8]
0x1c004cdcd  cmp     [rbx+8], rax
0x1c004cdd1  jnz     loc_1C00867BC
0x1c004cdd7  mov     rax, [rsi+10h]
0x1c004cddb  cmp     [rbx+10h], rax
0x1c004cddf  jnz     loc_1C00867BC
0x1c004cde5  mov     eax, [rbx+3Ch]
0x1c004cde8  test    al, 1
0x1c004cdea  jz      short loc_1C004CDF7
0x1c004cdec  mov     eax, [rsi+3Ch]
0x1c004cdef  test    al, 1
0x1c004cdf1  jz      loc_1C00867BC
0x1c004cdf7  mov     rcx, rbx; void *
0x1c004cdfa  mov     rdx, rsi; Src
0x1c004cdfd  mov     r8d, 0E48h; Size
0x1c004ce03  call    memmove
0x1c004ce08  mov     eax, [rbx+24h]
0x1c004ce0b  inc     dword ptr [rbx+38h]
0x1c004ce0e  mov     [rbx+0E6Ch], eax
0x1c004ce14  mov     [rbx+0E74h], eax
0x1c004ce1a  mov     eax, [rbx+3Ch]
0x1c004ce1d  test    al, 2
0x1c004ce1f  jnz     loc_1C00867C6
0x1c004ce25  mov     [rbx+0E48h], ebp
0x1c004ce2b  mov     rax, rbx
0x1c004ce2e  mov     rax, [rbx+18h]
0x1c004ce32  mov     rcx, rbx
0x1c004ce35  mov     [rbx+0ED8h], rax
0x1c004ce3c  mov     rax, cs:ML_LSN_NULL
0x1c004ce43  mov     [rbx+0E80h], rax
0x1c004ce4a  call    LogInitializeFlushWindows
0x1c004ce4f  mov     edi, eax
0x1c004ce51  test    eax, eax
0x1c004ce53  js      short loc_1C004CE9D
0x1c004ce55  mov     eax, [rbx+2EC8h]
0x1c004ce5b  test    al, 10h
0x1c004ce5d  jnz     short loc_1C004CE8F
0x1c004ce5f  mov     ebp, r13d
0x1c004ce62  lea     rcx, [rbx+1EE8h]; void *
0x1c004ce69  mov     rdx, rbx; Src
0x1c004ce6c  mov     r8d, 0E48h; Size
0x1c004ce72  call    memmove
0x1c004ce77  mov     rdx, r15
0x1c004ce7a  mov     rcx, rbx
0x1c004ce7d  call    LogCoreWriteControlArea
0x1c004ce82  mov     edi, eax
0x1c004ce84  test    eax, eax
0x1c004ce86  js      short loc_1C004CE9D
0x1c004ce88  inc     ebp
0x1c004ce8a  cmp     ebp, 2
0x1c004ce8d  jb      short loc_1C004CE62
0x1c004ce8f  mov     rax, [rsp+68h+arg_70]
0x1c004ce97  mov     [rax], rbx
0x1c004ce9a  mov     rbx, r13
0x1c004ce9d  test    rsi, rsi
0x1c004cea0  jz      short loc_1C004CEB3
0x1c004cea2  xor     edx, edx; Tag
0x1c004cea4  mov     rcx, rsi; P
0x1c004cea7  call    cs:__imp_ExFreePoolWithTag
0x1c004ceae  nop     dword ptr [rax+rax+00h]
0x1c004ceb3  test    rbx, rbx
0x1c004ceb6  jnz     loc_1C00867E4
0x1c004cebc  lea     r11, [rsp+68h+var_28]
0x1c004cec1  mov     eax, edi
0x1c004cec3  mov     rbx, [r11+30h]
0x1c004cec7  mov     rbp, [r11+38h]
0x1c004cecb  mov     rsi, [r11+40h]
0x1c004cecf  mov     rsp, r11
0x1c004ced2  pop     r15
0x1c004ced4  pop     r14
0x1c004ced6  pop     r13
0x1c004ced8  pop     r12
0x1c004ceda  pop     rdi
0x1c004cedb  retn
0x1c008670c  test    r14, r14
0x1c008670f  jnz     loc_1C004CB4B
0x1c0086715  test    r12b, r12b
0x1c0086718  jnz     loc_1C004CB4B
0x1c008671e  mov     edi, 0C000009Ah
0x1c0086723  jmp     loc_1C004CEBC
0x1c0086728  mov     dword ptr [rbx+2EC8h], 8
0x1c0086732  mov     ecx, 18h
0x1c0086737  jmp     loc_1C004CC31
0x1c008673c  mov     [rdi], ecx
0x1c008673e  jmp     loc_1C004CD56
0x1c0086743  test    r14, r14
0x1c0086746  jnz     short loc_1C0086752
0x1c0086748  mov     qword ptr [rbx+18h], 1
0x1c0086750  jmp     short loc_1C0086769
0x1c0086752  mov     eax, [r14+4]
0x1c0086756  add     eax, ecx
0x1c0086758  mov     [rbx+1Ch], eax
0x1c008675b  mov     eax, [r14]
0x1c008675e  mov     [rbx+18h], eax
0x1c0086761  add     [r14+4], ecx
0x1c0086765  or      dword ptr [rbx+3Ch], 2
0x1c0086769  mov     rax, [rbx+18h]
0x1c008676d  mov     [rbx+38h], ecx
0x1c0086770  mov     [rbx+40h], ecx
0x1c0086773  lea     rcx, [rbx+28h]; Uuid
0x1c0086777  mov     [rbx+20h], rax
0x1c008677b  mov     [rbx], r13
0x1c008677e  call    cs:__imp_ExUuidCreate
0x1c0086785  nop     dword ptr [rax+rax+00h]
0x1c008678a  mov     edi, eax
0x1c008678c  test    eax, eax
0x1c008678e  js      loc_1C004CEB3
0x1c0086794  neg     r14
0x1c0086797  sbb     ebp, ebp
0x1c0086799  neg     ebp
0x1c008679b  add     ebp, 6
0x1c008679e  jmp     loc_1C004CE25
0x1c00867a3  mov     edi, 0C000009Ah
0x1c00867a8  jmp     loc_1C004CEB3
0x1c00867ad  mov     dword ptr [rbx+0E48h], 3
0x1c00867b7  jmp     loc_1C004CE9D
0x1c00867bc  mov     edi, 0C0000032h
0x1c00867c1  jmp     loc_1C004CE9D
0x1c00867c6  mov     ebp, 7
0x1c00867cb  jmp     loc_1C004CE25
0x1c00867d0  mov     edi, 0C000000Dh
0x1c00867d5  jmp     loc_1C004CEBC
0x1c00867da  mov     edi, 0C000000Dh
0x1c00867df  jmp     loc_1C004CE9D
0x1c00867e4  mov     rcx, [rbx+2EC0h]; P
0x1c00867eb  test    rcx, rcx
0x1c00867ee  jz      short loc_1C00867FE
0x1c00867f0  xor     edx, edx; Tag
0x1c00867f2  call    cs:__imp_ExFreePoolWithTag
0x1c00867f9  nop     dword ptr [rax+rax+00h]
0x1c00867fe  mov     rcx, [rbx+0EC8h]; P
0x1c0086805  test    rcx, rcx
0x1c0086808  jz      short loc_1C0086818
0x1c008680a  xor     edx, edx; Tag
0x1c008680c  call    cs:__imp_ExFreePoolWithTag
0x1c0086813  nop     dword ptr [rax+rax+00h]
0x1c0086818  xor     edx, edx; Tag
0x1c008681a  mov     rcx, rbx; P
0x1c008681d  call    cs:__imp_ExFreePoolWithTag
0x1c0086824  nop     dword ptr [rax+rax+00h]
0x1c0086829  nop
0x1c008682a  jmp     loc_1C004CEBC
```
