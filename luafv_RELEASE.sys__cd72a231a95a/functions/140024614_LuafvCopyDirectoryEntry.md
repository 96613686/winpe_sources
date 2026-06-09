# LuafvCopyDirectoryEntry

- ea: `0x140024614`
- end: `0x140024787`
- name: `LuafvCopyDirectoryEntry`
- size: `371`
- prototype: `char *__fastcall(__int64, int, unsigned int, char, char *, unsigned __int64, char, char, _QWORD *, char *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140024050`

## callees

- `0x140001b34`
- `0x140005be0`
- `0x140005c00`
- `0x140005d00`
- `0x140006000`
- `0x140014b8c`
- `0x140014c2c`
- `0x140014c8c`
- `0x140024614`

## pseudocode

```c
char *__fastcall LuafvCopyDirectoryEntry(
        __int64 a1,
        int a2,
        unsigned int a3,
        char a4,
        char *a5,
        unsigned __int64 a6,
        char a7,
        char a8,
        _QWORD *a9,
        char *a10)
{
  char v11; // bl
  unsigned int *v12; // r14
  unsigned int v15; // r15d
  __int64 v16; // r13
  unsigned int v17; // edi
  int IsEnabledDeviceUsageNoInline; // eax
  size_t v19; // r8
  char *result; // rax
  char *v21; // [rsp+90h] [rbp+28h]

  v11 = 0;
  v12 = *(unsigned int **)(a1 + 24);
  v15 = a2 + *(unsigned int *)((char *)v12 + a3);
  v21 = &a5[v15];
  if ( (unsigned __int64)v21 < a6 )
  {
    v16 = *v12;
    if ( a8 )
    {
      v17 = a2 + *(unsigned int *)((char *)v12 + a3);
    }
    else if ( (unsigned __int64)&a5[(v15 + 7) & 0xFFFFFFF8] < a6 )
    {
      v17 = (v15 + 7) & 0xFFFFFFF8;
    }
    else
    {
      v17 = a6 - (_DWORD)a5 - 1;
    }
    if ( a7 )
      goto LABEL_19;
    if ( (unsigned int)Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( a4 )
        RtlCopyToUser(a5, v12, v15);
      else
        RtlCopyVolatileMemory(a5, v12, v15);
      if ( a4 )
      {
        RtlSetUserMemory(v21);
        RtlWriteULongToUser(a5, v17);
        goto LABEL_17;
      }
      RtlSetVolatileMemory(v21, 0, v17 - v15);
    }
    else
    {
      memmove(a5, v12, v15);
      memset(v21, 0, v17 - v15);
    }
    *(_DWORD *)a5 = v17;
LABEL_17:
    if ( a9 )
      *a9 = &a5[v17];
LABEL_19:
    if ( (_DWORD)v16 )
      *(_QWORD *)(a1 + 24) += v16;
    else
      *(_QWORD *)(a1 + 24) = *(_QWORD *)(a1 + 16) + *(unsigned int *)(a1 + 12);
    goto LABEL_29;
  }
  if ( !a7 )
  {
    IsEnabledDeviceUsageNoInline = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline();
    v19 = (unsigned int)(a6 - (_DWORD)a5 - 1);
    if ( IsEnabledDeviceUsageNoInline )
    {
      if ( a4 )
        RtlCopyToUser(a5, v12, v19);
      else
        RtlCopyVolatileMemory(a5, v12, v19);
    }
    else
    {
      memmove(a5, v12, v19);
    }
  }
  v11 = 1;
LABEL_29:
  result = a10;
  *a10 = v11;
  return result;
}

```

## disassembly

```asm
0x140024614  push    rbx
0x140024616  push    rbp
0x140024617  push    rsi
0x140024618  push    rdi
0x140024619  push    r12
0x14002461b  push    r13
0x14002461d  push    r14
0x14002461f  push    r15
0x140024621  sub     rsp, 28h
0x140024625  mov     rsi, [rsp+68h+arg_20]
0x14002462d  xor     ebx, ebx
0x14002462f  mov     r14, [rcx+18h]
0x140024633  mov     r12b, r9b
0x140024636  mov     rdi, [rsp+68h+arg_28]
0x14002463e  mov     rbp, rcx
0x140024641  mov     eax, r8d
0x140024644  mov     r15d, [rax+r14]
0x140024648  add     r15d, edx
0x14002464b  mov     eax, r15d
0x14002464e  add     rax, rsi
0x140024651  mov     [rsp+68h+arg_20], rax
0x140024659  cmp     rax, rdi
0x14002465c  jnb     loc_140024732
0x140024662  mov     r13d, [r14]
0x140024665  cmp     [rsp+68h+arg_38], bl
0x14002466c  jz      short loc_140024673
0x14002466e  mov     edi, r15d
0x140024671  jmp     short loc_14002468C
0x140024673  lea     eax, [r15+7]
0x140024677  and     eax, 0FFFFFFF8h
0x14002467a  mov     ecx, eax
0x14002467c  add     rax, rsi
0x14002467f  cmp     rax, rdi
0x140024682  jb      short loc_14002468A
0x140024684  sub     edi, esi
0x140024686  dec     edi
0x140024688  jmp     short loc_14002468C
0x14002468a  mov     edi, ecx
0x14002468c  cmp     [rsp+68h+arg_30], bl
0x140024693  jnz     loc_14002471A
0x140024699  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x14002469e  mov     r8d, r15d; Size
0x1400246a1  mov     rdx, r14; Src
0x1400246a4  mov     rcx, rsi; void *
0x1400246a7  test    eax, eax
0x1400246a9  jz      short loc_1400246E9
0x1400246ab  test    r12b, r12b
0x1400246ae  jz      short loc_1400246B7
0x1400246b0  call    RtlCopyToUser
0x1400246b5  jmp     short loc_1400246BC
0x1400246b7  call    RtlCopyVolatileMemory
0x1400246bc  mov     rcx, [rsp+68h+arg_20]; void *
0x1400246c4  mov     r8d, edi
0x1400246c7  sub     r8d, r15d; Size
0x1400246ca  xor     edx, edx; Val
0x1400246cc  test    r12b, r12b
0x1400246cf  jz      short loc_1400246E2
0x1400246d1  call    RtlSetUserMemory
0x1400246d6  mov     edx, edi
0x1400246d8  mov     rcx, rsi
0x1400246db  call    RtlWriteULongToUser
0x1400246e0  jmp     short loc_140024705
0x1400246e2  call    RtlSetVolatileMemory
0x1400246e7  jmp     short loc_140024703
0x1400246e9  call    memmove
0x1400246ee  mov     rcx, [rsp+68h+arg_20]; void *
0x1400246f6  mov     r8d, edi
0x1400246f9  sub     r8d, r15d; Size
0x1400246fc  xor     edx, edx; Val
0x1400246fe  call    memset
0x140024703  mov     [rsi], edi
0x140024705  mov     rcx, [rsp+68h+arg_40]
0x14002470d  test    rcx, rcx
0x140024710  jz      short loc_14002471A
0x140024712  mov     eax, edi
0x140024714  add     rax, rsi
0x140024717  mov     [rcx], rax
0x14002471a  test    r13d, r13d
0x14002471d  jz      short loc_140024725
0x14002471f  add     [rbp+18h], r13
0x140024723  jmp     short loc_14002476B
0x140024725  mov     eax, [rbp+0Ch]
0x140024728  add     rax, [rbp+10h]
0x14002472c  mov     [rbp+18h], rax
0x140024730  jmp     short loc_14002476B
0x140024732  cmp     [rsp+68h+arg_30], bl
0x140024739  jnz     short loc_140024769
0x14002473b  sub     edi, esi
0x14002473d  dec     edi
0x14002473f  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x140024744  mov     r8d, edi; Size
0x140024747  mov     rdx, r14; Src
0x14002474a  mov     rcx, rsi; void *
0x14002474d  test    eax, eax
0x14002474f  jz      short loc_140024764
0x140024751  test    r12b, r12b
0x140024754  jz      short loc_14002475D
0x140024756  call    RtlCopyToUser
0x14002475b  jmp     short loc_140024769
0x14002475d  call    RtlCopyVolatileMemory
0x140024762  jmp     short loc_140024769
0x140024764  call    memmove
0x140024769  mov     bl, 1
0x14002476b  mov     rax, [rsp+68h+arg_48]
0x140024773  mov     [rax], bl
0x140024775  add     rsp, 28h
0x140024779  pop     r15
0x14002477b  pop     r14
0x14002477d  pop     r13
0x14002477f  pop     r12
0x140024781  pop     rdi
0x140024782  pop     rsi
0x140024783  pop     rbp
0x140024784  pop     rbx
0x140024785  retn
```
