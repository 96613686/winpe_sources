# LuafvCopyDirectoryEntry

- ea: `0x140024664`
- end: `0x1400247d7`
- name: `LuafvCopyDirectoryEntry`
- size: `371`
- prototype: `char *__fastcall(__int64, int, unsigned int, char, char *, unsigned __int64, char, char, _QWORD *, char *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400240a0`

## callees

- `0x140001b34`
- `0x140005f60`
- `0x140005f80`
- `0x140006080`
- `0x140006380`
- `0x140014b8c`
- `0x140014c2c`
- `0x140014c8c`
- `0x140024664`

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
0x140024664  push    rbx
0x140024666  push    rbp
0x140024667  push    rsi
0x140024668  push    rdi
0x140024669  push    r12
0x14002466b  push    r13
0x14002466d  push    r14
0x14002466f  push    r15
0x140024671  sub     rsp, 28h
0x140024675  mov     rsi, [rsp+68h+arg_20]
0x14002467d  xor     ebx, ebx
0x14002467f  mov     r14, [rcx+18h]
0x140024683  mov     r12b, r9b
0x140024686  mov     rdi, [rsp+68h+arg_28]
0x14002468e  mov     rbp, rcx
0x140024691  mov     eax, r8d
0x140024694  mov     r15d, [rax+r14]
0x140024698  add     r15d, edx
0x14002469b  mov     eax, r15d
0x14002469e  add     rax, rsi
0x1400246a1  mov     [rsp+68h+arg_20], rax
0x1400246a9  cmp     rax, rdi
0x1400246ac  jnb     loc_140024782
0x1400246b2  mov     r13d, [r14]
0x1400246b5  cmp     [rsp+68h+arg_38], bl
0x1400246bc  jz      short loc_1400246C3
0x1400246be  mov     edi, r15d
0x1400246c1  jmp     short loc_1400246DC
0x1400246c3  lea     eax, [r15+7]
0x1400246c7  and     eax, 0FFFFFFF8h
0x1400246ca  mov     ecx, eax
0x1400246cc  add     rax, rsi
0x1400246cf  cmp     rax, rdi
0x1400246d2  jb      short loc_1400246DA
0x1400246d4  sub     edi, esi
0x1400246d6  dec     edi
0x1400246d8  jmp     short loc_1400246DC
0x1400246da  mov     edi, ecx
0x1400246dc  cmp     [rsp+68h+arg_30], bl
0x1400246e3  jnz     loc_14002476A
0x1400246e9  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x1400246ee  mov     r8d, r15d; Size
0x1400246f1  mov     rdx, r14; Src
0x1400246f4  mov     rcx, rsi; void *
0x1400246f7  test    eax, eax
0x1400246f9  jz      short loc_140024739
0x1400246fb  test    r12b, r12b
0x1400246fe  jz      short loc_140024707
0x140024700  call    RtlCopyToUser
0x140024705  jmp     short loc_14002470C
0x140024707  call    RtlCopyVolatileMemory
0x14002470c  mov     rcx, [rsp+68h+arg_20]; void *
0x140024714  mov     r8d, edi
0x140024717  sub     r8d, r15d; Size
0x14002471a  xor     edx, edx; Val
0x14002471c  test    r12b, r12b
0x14002471f  jz      short loc_140024732
0x140024721  call    RtlSetUserMemory
0x140024726  mov     edx, edi
0x140024728  mov     rcx, rsi
0x14002472b  call    RtlWriteULongToUser
0x140024730  jmp     short loc_140024755
0x140024732  call    RtlSetVolatileMemory
0x140024737  jmp     short loc_140024753
0x140024739  call    memmove
0x14002473e  mov     rcx, [rsp+68h+arg_20]; void *
0x140024746  mov     r8d, edi
0x140024749  sub     r8d, r15d; Size
0x14002474c  xor     edx, edx; Val
0x14002474e  call    memset
0x140024753  mov     [rsi], edi
0x140024755  mov     rcx, [rsp+68h+arg_40]
0x14002475d  test    rcx, rcx
0x140024760  jz      short loc_14002476A
0x140024762  mov     eax, edi
0x140024764  add     rax, rsi
0x140024767  mov     [rcx], rax
0x14002476a  test    r13d, r13d
0x14002476d  jz      short loc_140024775
0x14002476f  add     [rbp+18h], r13
0x140024773  jmp     short loc_1400247BB
0x140024775  mov     eax, [rbp+0Ch]
0x140024778  add     rax, [rbp+10h]
0x14002477c  mov     [rbp+18h], rax
0x140024780  jmp     short loc_1400247BB
0x140024782  cmp     [rsp+68h+arg_30], bl
0x140024789  jnz     short loc_1400247B9
0x14002478b  sub     edi, esi
0x14002478d  dec     edi
0x14002478f  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x140024794  mov     r8d, edi; Size
0x140024797  mov     rdx, r14; Src
0x14002479a  mov     rcx, rsi; void *
0x14002479d  test    eax, eax
0x14002479f  jz      short loc_1400247B4
0x1400247a1  test    r12b, r12b
0x1400247a4  jz      short loc_1400247AD
0x1400247a6  call    RtlCopyToUser
0x1400247ab  jmp     short loc_1400247B9
0x1400247ad  call    RtlCopyVolatileMemory
0x1400247b2  jmp     short loc_1400247B9
0x1400247b4  call    memmove
0x1400247b9  mov     bl, 1
0x1400247bb  mov     rax, [rsp+68h+arg_48]
0x1400247c3  mov     [rax], bl
0x1400247c5  add     rsp, 28h
0x1400247c9  pop     r15
0x1400247cb  pop     r14
0x1400247cd  pop     r13
0x1400247cf  pop     r12
0x1400247d1  pop     rdi
0x1400247d2  pop     rsi
0x1400247d3  pop     rbp
0x1400247d4  pop     rbx
0x1400247d5  retn
```
