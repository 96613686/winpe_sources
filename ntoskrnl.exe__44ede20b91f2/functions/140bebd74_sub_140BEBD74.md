# sub_140BEBD74

- ea: `0x140bebd74`
- end: `0x140bebfc2`
- name: `sub_140BEBD74`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x1404bb69c`

## callees

- `0x1405433d0`
- `0x1406d9d70`
- `0x1406f4480`
- `0x140beb310`
- `0x140bebd74`

## string_xrefs

- `0x140bebe3a`: `KRNL: Failed to locate system dll.`
- `0x140bebe18`: `KRNL: Failed to create root directories.`
- `0x140bebddc`: `KRNL: Failed to create object types.`
- `0x140bebe52`: `KRNL: Failed to initialize (phase 1) plug and play services.`
- `0x140bebe5e`: `KRNL: Failed to initialize (phase 0) plug and play services.`
- `0x140bebde8`: `KRNL: Failed to create event.`
- `0x140bebecb`: `KRNL: Failed waiting for boot devices to delete.`

## pseudocode

```c
__int64 __fastcall sub_140BEBD74(unsigned int a1, unsigned __int16 *a2)
{
  const wchar_t *v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // r14
  __int64 v7; // rbx
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // r15
  wchar_t Dst[88]; // [rsp+30h] [rbp-108h] BYREF

  if ( a1 > 0xB )
  {
    switch ( a1 )
    {
      case 0xCu:
        v4 = L"KRNL: Failed to reassign system root.";
        goto LABEL_43;
      case 0xDu:
        v4 = L"KRNL: Failed to protect system partition.";
        goto LABEL_43;
      case 0xEu:
        v4 = L"KRNL: Failed to UnicodeToAnsi system root.";
        goto LABEL_43;
      case 0xFu:
        v4 = L"KRNL: Failed to AnsiToUnicode system root.";
        goto LABEL_43;
      case 0x10u:
        v4 = L"KRNL: Failed to find any groups.";
        goto LABEL_43;
      case 0x12u:
        v4 = L"KRNL: Failed waiting for boot devices to delete.";
        goto LABEL_43;
      case 0x13u:
        v4 = L"KRNL: Failed waiting for boot devices to start.";
        goto LABEL_43;
      case 0x14u:
        v4 = L"KRNL: Failed waiting for boot devices to reinit.";
        goto LABEL_43;
      case 0x15u:
        v4 = L"KRNL: Failed marking boot partition.";
        goto LABEL_43;
    }
  }
  else
  {
    if ( a1 == 11 )
    {
      v4 = L"KRNL: Failed to initialize system drivers.";
      goto LABEL_43;
    }
    if ( a1 > 6 )
    {
      switch ( a1 )
      {
        case 7u:
          v4 = L"KRNL: Failed to initialize (phase 0) plug and play services.";
          break;
        case 8u:
          v4 = L"KRNL: Failed to initialize (phase 1) plug and play services.";
          break;
        case 9u:
          v4 = L"KRNL: Failed to initialize boot drivers.";
          break;
        default:
          v4 = L"KRNL: Failed to locate system dll.";
          break;
      }
      goto LABEL_43;
    }
    switch ( a1 )
    {
      case 6u:
        v4 = L"KRNL: Failed to create root directories.";
        goto LABEL_43;
      case 1u:
        v4 = L"KRNL: Loading ";
        goto LABEL_43;
      case 2u:
        v4 = L"KRNL: Load succeeded.";
        goto LABEL_43;
      case 3u:
        v4 = L"KRNL: Load failed.";
        goto LABEL_43;
      case 4u:
        v4 = L"KRNL: Failed to create event.";
        goto LABEL_43;
      case 5u:
        v4 = L"KRNL: Failed to create object types.";
LABEL_43:
        wcscpy_s(Dst, 0x50u, v4);
        goto LABEL_44;
    }
  }
  v4 = 0;
  Dst[0] = 0;
LABEL_44:
  v5 = -1;
  if ( a1 == 1 && a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v4[v6] );
    v7 = *((_QWORD *)a2 + 1);
    v8 = (unsigned __int64)*a2 >> 1;
    v9 = 79 - v6;
    if ( v8 < 80 - v6 )
      v9 = (unsigned __int64)*a2 >> 1;
    memmove(&Dst[v6], *((const void **)a2 + 1), 2 * v9);
    if ( *(_WORD *)(v7 + 2 * v8 - 2) )
      Dst[v9 + v6] = 0;
  }
  do
    ++v5;
  while ( Dst[v5] );
  return sub_140BEB310(17, Dst, 2 * v5 + 2);
}

```

## disassembly

```asm
0x140bebd74  push    rbx
0x140bebd76  push    rbp
0x140bebd77  push    rsi
0x140bebd78  push    rdi
0x140bebd79  push    r12
0x140bebd7b  push    r13
0x140bebd7d  push    r14
0x140bebd7f  push    r15
0x140bebd81  sub     rsp, 0F8h
0x140bebd88  mov     rax, cs:__security_cookie
0x140bebd8f  xor     rax, rsp
0x140bebd92  mov     [rsp+138h+var_58], rax
0x140bebd9a  xor     r12d, r12d
0x140bebd9d  mov     r13, rdx
0x140bebda0  mov     edi, ecx
0x140bebda2  mov     ebp, 50h ; 'P'
0x140bebda7  cmp     ecx, 0Bh
0x140bebdaa  ja      loc_140BEBE76
0x140bebdb0  jz      loc_140BEBE6A
0x140bebdb6  cmp     ecx, 6
0x140bebdb9  ja      short loc_140BEBE24
0x140bebdbb  jz      short loc_140BEBE18
0x140bebdbd  mov     eax, ecx
0x140bebdbf  sub     eax, 1
0x140bebdc2  jz      short loc_140BEBE0C
0x140bebdc4  sub     eax, 1
0x140bebdc7  jz      short loc_140BEBE00
0x140bebdc9  sub     eax, 1
0x140bebdcc  jz      short loc_140BEBDF4
0x140bebdce  sub     eax, 1
0x140bebdd1  jz      short loc_140BEBDE8
0x140bebdd3  cmp     eax, 1
0x140bebdd6  jnz     loc_140BEBEA5
0x140bebddc  lea     rbx, aKrnlFailedToCr; "KRNL: Failed to create object types."
0x140bebde3  jmp     loc_140BEBEFF
0x140bebde8  lea     rbx, aKrnlFailedToCr_0; "KRNL: Failed to create event."
0x140bebdef  jmp     loc_140BEBEFF
0x140bebdf4  lea     rbx, aKrnlLoadFailed; "KRNL: Load failed."
0x140bebdfb  jmp     loc_140BEBEFF
0x140bebe00  lea     rbx, aKrnlLoadSuccee; "KRNL: Load succeeded."
0x140bebe07  jmp     loc_140BEBEFF
0x140bebe0c  lea     rbx, aKrnlLoading; "KRNL: Loading "
0x140bebe13  jmp     loc_140BEBEFF
0x140bebe18  lea     rbx, aKrnlFailedToCr_1; "KRNL: Failed to create root directories"...
0x140bebe1f  jmp     loc_140BEBEFF
0x140bebe24  mov     eax, edi
0x140bebe26  sub     eax, 7
0x140bebe29  jz      short loc_140BEBE5E
0x140bebe2b  sub     eax, 1
0x140bebe2e  jz      short loc_140BEBE52
0x140bebe30  sub     eax, 1
0x140bebe33  jz      short loc_140BEBE46
0x140bebe35  cmp     eax, 1
0x140bebe38  jnz     short loc_140BEBEA5
0x140bebe3a  lea     rbx, aKrnlFailedToLo; "KRNL: Failed to locate system dll."
0x140bebe41  jmp     loc_140BEBEFF
0x140bebe46  lea     rbx, aKrnlFailedToIn; "KRNL: Failed to initialize boot drivers"...
0x140bebe4d  jmp     loc_140BEBEFF
0x140bebe52  lea     rbx, aKrnlFailedToIn_0; "KRNL: Failed to initialize (phase 1) pl"...
0x140bebe59  jmp     loc_140BEBEFF
0x140bebe5e  lea     rbx, aKrnlFailedToIn_1; "KRNL: Failed to initialize (phase 0) pl"...
0x140bebe65  jmp     loc_140BEBEFF
0x140bebe6a  lea     rbx, aKrnlFailedToIn_2; "KRNL: Failed to initialize system drive"...
0x140bebe71  jmp     loc_140BEBEFF
0x140bebe76  mov     eax, edi
0x140bebe78  sub     eax, 0Ch
0x140bebe7b  jz      short loc_140BEBEF8
0x140bebe7d  sub     eax, 1
0x140bebe80  jz      short loc_140BEBEEF
0x140bebe82  sub     eax, 1
0x140bebe85  jz      short loc_140BEBEE6
0x140bebe87  sub     eax, 1
0x140bebe8a  jz      short loc_140BEBEDD
0x140bebe8c  sub     eax, 1
0x140bebe8f  jz      short loc_140BEBED4
0x140bebe91  sub     eax, 2
0x140bebe94  jz      short loc_140BEBECB
0x140bebe96  sub     eax, 1
0x140bebe99  jz      short loc_140BEBEC2
0x140bebe9b  sub     eax, 1
0x140bebe9e  jz      short loc_140BEBEB9
0x140bebea0  cmp     eax, 1
0x140bebea3  jz      short loc_140BEBEB0
0x140bebea5  mov     rbx, r12
0x140bebea8  mov     [rsp+138h+Dst], r12w
0x140bebeae  jmp     short loc_140BEBF0F
0x140bebeb0  lea     rbx, aKrnlFailedMark; "KRNL: Failed marking boot partition."
0x140bebeb7  jmp     short loc_140BEBEFF
0x140bebeb9  lea     rbx, aKrnlFailedWait; "KRNL: Failed waiting for boot devices t"...
0x140bebec0  jmp     short loc_140BEBEFF
0x140bebec2  lea     rbx, aKrnlFailedWait_0; "KRNL: Failed waiting for boot devices t"...
0x140bebec9  jmp     short loc_140BEBEFF
0x140bebecb  lea     rbx, aKrnlFailedWait_1; "KRNL: Failed waiting for boot devices t"...
0x140bebed2  jmp     short loc_140BEBEFF
0x140bebed4  lea     rbx, aKrnlFailedToFi; "KRNL: Failed to find any groups."
0x140bebedb  jmp     short loc_140BEBEFF
0x140bebedd  lea     rbx, aKrnlFailedToAn; "KRNL: Failed to AnsiToUnicode system ro"...
0x140bebee4  jmp     short loc_140BEBEFF
0x140bebee6  lea     rbx, aKrnlFailedToUn; "KRNL: Failed to UnicodeToAnsi system ro"...
0x140bebeed  jmp     short loc_140BEBEFF
0x140bebeef  lea     rbx, aKrnlFailedToPr; "KRNL: Failed to protect system partitio"...
0x140bebef6  jmp     short loc_140BEBEFF
0x140bebef8  lea     rbx, aKrnlFailedToRe; "KRNL: Failed to reassign system root."
0x140bebeff  mov     r8, rbx; Src
0x140bebf02  lea     rcx, [rsp+138h+Dst]; Dst
0x140bebf07  mov     rdx, rbp; SizeInWords
0x140bebf0a  call    wcscpy_s
0x140bebf0f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140bebf13  cmp     edi, 1
0x140bebf16  jnz     short loc_140BEBF70
0x140bebf18  test    r13, r13
0x140bebf1b  jz      short loc_140BEBF70
0x140bebf1d  mov     r14, rsi
0x140bebf20  inc     r14
0x140bebf23  cmp     [rbx+r14*2], r12w
0x140bebf28  jnz     short loc_140BEBF20
0x140bebf2a  movzx   edi, word ptr [r13+0]
0x140bebf2f  lea     rcx, [rsp+138h+Dst]
0x140bebf34  mov     rbx, [r13+8]
0x140bebf38  lea     rcx, [rcx+r14*2]; void *
0x140bebf3c  shr     rdi, 1
0x140bebf3f  mov     r15d, 4Fh ; 'O'
0x140bebf45  sub     r15, r14
0x140bebf48  sub     rbp, r14
0x140bebf4b  cmp     rdi, rbp
0x140bebf4e  mov     rdx, rbx; Src
0x140bebf51  cmovb   r15, rdi
0x140bebf55  lea     r8, [r15+r15]; Size
0x140bebf59  call    memmove
0x140bebf5e  cmp     [rbx+rdi*2-2], r12w
0x140bebf64  jz      short loc_140BEBF70
0x140bebf66  lea     rcx, [r15+r14]
0x140bebf6a  mov     [rsp+rcx*2+138h+Dst], r12w
0x140bebf70  lea     rax, [rsp+138h+Dst]
0x140bebf75  inc     rsi
0x140bebf78  cmp     [rax+rsi*2], r12w
0x140bebf7d  jnz     short loc_140BEBF75
0x140bebf7f  xor     r9d, r9d
0x140bebf82  mov     [rsp+138h+var_118], r12
0x140bebf87  lea     r8, ds:2[rsi*2]
0x140bebf8f  lea     rdx, [rsp+138h+Dst]
0x140bebf94  lea     ecx, [r9+11h]
0x140bebf98  call    sub_140BEB310
0x140bebf9d  mov     rcx, [rsp+138h+var_58]
0x140bebfa5  xor     rcx, rsp; StackCookie
0x140bebfa8  call    __security_check_cookie
0x140bebfad  add     rsp, 0F8h
0x140bebfb4  pop     r15
0x140bebfb6  pop     r14
0x140bebfb8  pop     r13
0x140bebfba  pop     r12
0x140bebfbc  pop     rdi
0x140bebfbd  pop     rsi
0x140bebfbe  pop     rbp
0x140bebfbf  pop     rbx
0x140bebfc0  retn
```
