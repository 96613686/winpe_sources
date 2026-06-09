# HdlspKernelAddLogEntry

- ea: `0x140beed74`
- end: `0x140beefc2`
- name: `HdlspKernelAddLogEntry`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x1404cb57c`

## callees

- `0x14054aa90`
- `0x1406dc8c0`
- `0x1406f6f80`
- `0x140bee310`
- `0x140beed74`

## string_xrefs

- `0x140beeecb`: `KRNL: Failed waiting for boot devices to delete.`
- `0x140beee3a`: `KRNL: Failed to locate system dll.`
- `0x140beee5e`: `KRNL: Failed to initialize (phase 0) plug and play services.`
- `0x140beee18`: `KRNL: Failed to create root directories.`
- `0x140beee52`: `KRNL: Failed to initialize (phase 1) plug and play services.`
- `0x140beeddc`: `KRNL: Failed to create object types.`
- `0x140beede8`: `KRNL: Failed to create event.`

## pseudocode

```c
__int64 __fastcall HdlspKernelAddLogEntry(unsigned int a1, unsigned __int16 *a2)
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
  return HdlspDispatch(17, Dst, 2 * v5 + 2);
}

```

## disassembly

```asm
0x140beed74  push    rbx
0x140beed76  push    rbp
0x140beed77  push    rsi
0x140beed78  push    rdi
0x140beed79  push    r12
0x140beed7b  push    r13
0x140beed7d  push    r14
0x140beed7f  push    r15
0x140beed81  sub     rsp, 0F8h
0x140beed88  mov     rax, cs:__security_cookie
0x140beed8f  xor     rax, rsp
0x140beed92  mov     [rsp+138h+var_58], rax
0x140beed9a  xor     r12d, r12d
0x140beed9d  mov     r13, rdx
0x140beeda0  mov     edi, ecx
0x140beeda2  mov     ebp, 50h ; 'P'
0x140beeda7  cmp     ecx, 0Bh
0x140beedaa  ja      loc_140BEEE76
0x140beedb0  jz      loc_140BEEE6A
0x140beedb6  cmp     ecx, 6
0x140beedb9  ja      short loc_140BEEE24
0x140beedbb  jz      short loc_140BEEE18
0x140beedbd  mov     eax, ecx
0x140beedbf  sub     eax, 1
0x140beedc2  jz      short loc_140BEEE0C
0x140beedc4  sub     eax, 1
0x140beedc7  jz      short loc_140BEEE00
0x140beedc9  sub     eax, 1
0x140beedcc  jz      short loc_140BEEDF4
0x140beedce  sub     eax, 1
0x140beedd1  jz      short loc_140BEEDE8
0x140beedd3  cmp     eax, 1
0x140beedd6  jnz     loc_140BEEEA5
0x140beeddc  lea     rbx, aKrnlFailedToCr_1; "KRNL: Failed to create object types."
0x140beede3  jmp     loc_140BEEEFF
0x140beede8  lea     rbx, aKrnlFailedToCr_0; "KRNL: Failed to create event."
0x140beedef  jmp     loc_140BEEEFF
0x140beedf4  lea     rbx, aKrnlLoadFailed; "KRNL: Load failed."
0x140beedfb  jmp     loc_140BEEEFF
0x140beee00  lea     rbx, aKrnlLoadSuccee; "KRNL: Load succeeded."
0x140beee07  jmp     loc_140BEEEFF
0x140beee0c  lea     rbx, aKrnlLoading; "KRNL: Loading "
0x140beee13  jmp     loc_140BEEEFF
0x140beee18  lea     rbx, aKrnlFailedToCr; "KRNL: Failed to create root directories"...
0x140beee1f  jmp     loc_140BEEEFF
0x140beee24  mov     eax, edi
0x140beee26  sub     eax, 7
0x140beee29  jz      short loc_140BEEE5E
0x140beee2b  sub     eax, 1
0x140beee2e  jz      short loc_140BEEE52
0x140beee30  sub     eax, 1
0x140beee33  jz      short loc_140BEEE46
0x140beee35  cmp     eax, 1
0x140beee38  jnz     short loc_140BEEEA5
0x140beee3a  lea     rbx, aKrnlFailedToLo; "KRNL: Failed to locate system dll."
0x140beee41  jmp     loc_140BEEEFF
0x140beee46  lea     rbx, aKrnlFailedToIn_1; "KRNL: Failed to initialize boot drivers"...
0x140beee4d  jmp     loc_140BEEEFF
0x140beee52  lea     rbx, aKrnlFailedToIn_0; "KRNL: Failed to initialize (phase 1) pl"...
0x140beee59  jmp     loc_140BEEEFF
0x140beee5e  lea     rbx, aKrnlFailedToIn; "KRNL: Failed to initialize (phase 0) pl"...
0x140beee65  jmp     loc_140BEEEFF
0x140beee6a  lea     rbx, aKrnlFailedToIn_2; "KRNL: Failed to initialize system drive"...
0x140beee71  jmp     loc_140BEEEFF
0x140beee76  mov     eax, edi
0x140beee78  sub     eax, 0Ch
0x140beee7b  jz      short loc_140BEEEF8
0x140beee7d  sub     eax, 1
0x140beee80  jz      short loc_140BEEEEF
0x140beee82  sub     eax, 1
0x140beee85  jz      short loc_140BEEEE6
0x140beee87  sub     eax, 1
0x140beee8a  jz      short loc_140BEEEDD
0x140beee8c  sub     eax, 1
0x140beee8f  jz      short loc_140BEEED4
0x140beee91  sub     eax, 2
0x140beee94  jz      short loc_140BEEECB
0x140beee96  sub     eax, 1
0x140beee99  jz      short loc_140BEEEC2
0x140beee9b  sub     eax, 1
0x140beee9e  jz      short loc_140BEEEB9
0x140beeea0  cmp     eax, 1
0x140beeea3  jz      short loc_140BEEEB0
0x140beeea5  mov     rbx, r12
0x140beeea8  mov     [rsp+138h+Dst], r12w
0x140beeeae  jmp     short loc_140BEEF0F
0x140beeeb0  lea     rbx, aKrnlFailedMark; "KRNL: Failed marking boot partition."
0x140beeeb7  jmp     short loc_140BEEEFF
0x140beeeb9  lea     rbx, aKrnlFailedWait_0; "KRNL: Failed waiting for boot devices t"...
0x140beeec0  jmp     short loc_140BEEEFF
0x140beeec2  lea     rbx, aKrnlFailedWait_1; "KRNL: Failed waiting for boot devices t"...
0x140beeec9  jmp     short loc_140BEEEFF
0x140beeecb  lea     rbx, aKrnlFailedWait; "KRNL: Failed waiting for boot devices t"...
0x140beeed2  jmp     short loc_140BEEEFF
0x140beeed4  lea     rbx, aKrnlFailedToFi; "KRNL: Failed to find any groups."
0x140beeedb  jmp     short loc_140BEEEFF
0x140beeedd  lea     rbx, aKrnlFailedToAn; "KRNL: Failed to AnsiToUnicode system ro"...
0x140beeee4  jmp     short loc_140BEEEFF
0x140beeee6  lea     rbx, aKrnlFailedToUn; "KRNL: Failed to UnicodeToAnsi system ro"...
0x140beeeed  jmp     short loc_140BEEEFF
0x140beeeef  lea     rbx, aKrnlFailedToPr; "KRNL: Failed to protect system partitio"...
0x140beeef6  jmp     short loc_140BEEEFF
0x140beeef8  lea     rbx, aKrnlFailedToRe; "KRNL: Failed to reassign system root."
0x140beeeff  mov     r8, rbx; Src
0x140beef02  lea     rcx, [rsp+138h+Dst]; Dst
0x140beef07  mov     rdx, rbp; SizeInWords
0x140beef0a  call    wcscpy_s
0x140beef0f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140beef13  cmp     edi, 1
0x140beef16  jnz     short loc_140BEEF70
0x140beef18  test    r13, r13
0x140beef1b  jz      short loc_140BEEF70
0x140beef1d  mov     r14, rsi
0x140beef20  inc     r14
0x140beef23  cmp     [rbx+r14*2], r12w
0x140beef28  jnz     short loc_140BEEF20
0x140beef2a  movzx   edi, word ptr [r13+0]
0x140beef2f  lea     rcx, [rsp+138h+Dst]
0x140beef34  mov     rbx, [r13+8]
0x140beef38  lea     rcx, [rcx+r14*2]; void *
0x140beef3c  shr     rdi, 1
0x140beef3f  mov     r15d, 4Fh ; 'O'
0x140beef45  sub     r15, r14
0x140beef48  sub     rbp, r14
0x140beef4b  cmp     rdi, rbp
0x140beef4e  mov     rdx, rbx; Src
0x140beef51  cmovb   r15, rdi
0x140beef55  lea     r8, [r15+r15]; Size
0x140beef59  call    memmove
0x140beef5e  cmp     [rbx+rdi*2-2], r12w
0x140beef64  jz      short loc_140BEEF70
0x140beef66  lea     rcx, [r15+r14]
0x140beef6a  mov     [rsp+rcx*2+138h+Dst], r12w
0x140beef70  lea     rax, [rsp+138h+Dst]
0x140beef75  inc     rsi
0x140beef78  cmp     [rax+rsi*2], r12w
0x140beef7d  jnz     short loc_140BEEF75
0x140beef7f  xor     r9d, r9d
0x140beef82  mov     [rsp+138h+var_118], r12
0x140beef87  lea     r8, ds:2[rsi*2]
0x140beef8f  lea     rdx, [rsp+138h+Dst]
0x140beef94  lea     ecx, [r9+11h]
0x140beef98  call    HdlspDispatch
0x140beef9d  mov     rcx, [rsp+138h+var_58]
0x140beefa5  xor     rcx, rsp; StackCookie
0x140beefa8  call    __security_check_cookie
0x140beefad  add     rsp, 0F8h
0x140beefb4  pop     r15
0x140beefb6  pop     r14
0x140beefb8  pop     r13
0x140beefba  pop     r12
0x140beefbc  pop     rdi
0x140beefbd  pop     rsi
0x140beefbe  pop     rbp
0x140beefbf  pop     rbx
0x140beefc0  retn
```
