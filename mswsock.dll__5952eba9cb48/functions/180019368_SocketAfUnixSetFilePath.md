# SocketAfUnixSetFilePath

- ea: `0x180019368`
- end: `0x18001988d`
- name: `SocketAfUnixSetFilePath`
- size: `1317`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180012600`
- `0x180012c10`
- `0x180026d70`

## callees

- `0x1800052a0`
- `0x180019368`
- `0x1800198a0`
- `0x180037195`
- `0x180038104`
- `0x18003ae8c`
- `0x18003aec4`
- `0x180053010`

## import_xrefs

- `ntdll!RtlUTF8ToUnicodeN` at `0x1800194a9`
- `ntdll!RtlUTF8ToUnicodeN` at `0x18001951b`
- `ntdll!RtlUTF8ToUnicodeN` at `0x1800194a9`
- `ntdll!RtlUTF8ToUnicodeN` at `0x18001951b`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180019541`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180019541`
- `ntdll!RtlAllocateHeap` at `0x1800194e3`
- `ntdll!RtlAllocateHeap` at `0x180019570`
- `ntdll!RtlAllocateHeap` at `0x1800196e8`
- `ntdll!RtlAllocateHeap` at `0x1800194e3`
- `ntdll!RtlAllocateHeap` at `0x180019570`
- `ntdll!RtlAllocateHeap` at `0x1800196e8`
- `ntdll!RtlInitUnicodeString` at `0x1800193ac`
- `ntdll!RtlInitUnicodeString` at `0x1800193ac`
- `ntdll!RtlFreeHeap` at `0x180019619`
- `ntdll!RtlFreeHeap` at `0x1800196c2`
- `ntdll!RtlFreeHeap` at `0x180019835`
- `ntdll!RtlFreeHeap` at `0x180019858`
- `ntdll!RtlFreeHeap` at `0x18001987c`
- `ntdll!RtlFreeHeap` at `0x180019619`
- `ntdll!RtlFreeHeap` at `0x1800196c2`
- `ntdll!RtlFreeHeap` at `0x180019835`
- `ntdll!RtlFreeHeap` at `0x180019858`
- `ntdll!RtlFreeHeap` at `0x18001987c`

## pseudocode

```c
__int64 __fastcall SocketAfUnixSetFilePath(_QWORD *a1, __int64 a2, unsigned int a3, int a4)
{
  char *v4; // rsi
  void *v7; // r15
  _BYTE *v10; // rdi
  __int64 v11; // r14
  _BYTE *v12; // rax
  __int64 v13; // r8
  unsigned int v14; // eax
  __int64 v15; // rcx
  unsigned __int16 v17; // ax
  PVOID Heap; // rbx
  int v19; // eax
  unsigned int v20; // r12d
  char *v21; // rax
  int v22; // edi
  unsigned int v23; // edi
  _QWORD *v24; // rax
  unsigned int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rdx
  unsigned int v29; // [rsp+60h] [rbp-19h] BYREF
  unsigned int v30; // [rsp+64h] [rbp-15h] BYREF
  int v31; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int16 v32; // [rsp+70h] [rbp-9h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int16 v34; // [rsp+F0h] [rbp+77h] BYREF

  v4 = 0;
  v31 = 0;
  v29 = 0;
  v30 = 0;
  v34 = 0;
  DestinationString = 0;
  v7 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( a3 >= 0x6E )
  {
    v10 = (_BYTE *)(a2 + 2);
    if ( !*v10 )
    {
      v29 = 0;
      goto LABEL_11;
    }
    LODWORD(v11) = 108;
    v12 = v10;
    v13 = 108;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v13;
    }
    while ( v13 );
    if ( v13 )
      v11 = (108 - v13) & -(__int64)(v13 != 0);
    v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int, int, _QWORD, unsigned __int16 *))(a1[19] + 112LL))(
            a1[20],
            a1[1],
            a1[23],
            a1[24],
            65534,
            a4,
            0,
            &v34);
    v29 = v14;
    if ( v14 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_l(v15, 21, WPP_06ddd0886b683faf63d5feb5db1037b5_Traceguids, v14);
      goto LABEL_11;
    }
    v17 = v34;
    Heap = 0;
    if ( v34 )
    {
      while ( 1 )
      {
        if ( Heap )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
          v17 = v34;
        }
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v17);
        v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int, int, PVOID, unsigned __int16 *))(a1[19] + 112LL))(
                a1[20],
                a1[1],
                a1[23],
                a1[24],
                65534,
                a4,
                Heap,
                &v34);
        v29 = v25;
        if ( v25 != 10014 )
          break;
        v17 = v34;
      }
      v7 = 0;
      if ( v25 )
      {
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_l(v26, 22, WPP_06ddd0886b683faf63d5feb5db1037b5_Traceguids, v25);
        goto LABEL_25;
      }
      v17 = v34;
      if ( v34 && (*v10 == 47 || *v10 == 92) )
      {
        ++v10;
        LODWORD(v11) = v11 - 1;
      }
    }
    v32 = v17 >> 1;
    v19 = RtlUTF8ToUnicodeN(0, 0, &v30, v10, v11);
    v20 = v19;
    if ( v19 < 0 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 23, WPP_06ddd0886b683faf63d5feb5db1037b5_Traceguids, (unsigned int)v19);
      v27 = v20;
      goto LABEL_51;
    }
    v30 += 2;
    v21 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v30 + v34);
    v4 = v21;
    if ( !v21 )
    {
LABEL_24:
      v29 = 10055;
LABEL_25:
      if ( Heap )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      if ( v4 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
      goto LABEL_11;
    }
    if ( Heap )
      memcpy_0(v21, Heap, v34);
    v22 = RtlUTF8ToUnicodeN(&v4[2 * v32], v30, &v30, v10, v11);
    if ( v22 < 0 )
    {
      if ( (xmmword_180063D60 & 2) == 0 )
        goto LABEL_50;
      v28 = 24;
    }
    else
    {
      v22 = RtlDosPathNameToNtPathName_U_WithStatus(v4, &DestinationString, 0, 0);
      if ( v22 >= 0 )
      {
        v23 = DestinationString.Length + 8;
        v24 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
        v7 = v24;
        if ( v24 )
        {
          *v24 = 0;
          memcpy_0(v24 + 1, DestinationString.Buffer, DestinationString.Length);
          if ( (unsigned int)WSPIoctl(a1[1], 2550136832LL, v7, v23, 0, 0, &v31, 0, 0, 0, &v29) == -1 )
          {
            if ( (xmmword_180063D60 & 2) != 0 )
              WPP_SF_d(1025, 26, WPP_06ddd0886b683faf63d5feb5db1037b5_Traceguids, v29);
          }
          else
          {
            v29 = 0;
          }
          goto LABEL_25;
        }
        goto LABEL_24;
      }
      if ( (xmmword_180063D60 & 2) == 0 )
        goto LABEL_50;
      v28 = 25;
    }
    WPP_SF_d(1025, v28, WPP_06ddd0886b683faf63d5feb5db1037b5_Traceguids, (unsigned int)v22);
LABEL_50:
    v27 = (unsigned int)v22;
LABEL_51:
    v29 = NtStatusToSocketError(v27);
    goto LABEL_25;
  }
  v29 = 10022;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_(1025, 20, WPP_06ddd0886b683faf63d5feb5db1037b5_Traceguids);
LABEL_11:
  if ( DestinationString.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  return v29;
}

```

## disassembly

```asm
0x180019368  push    rbp
0x18001936a  push    rbx
0x18001936b  push    rsi
0x18001936c  push    rdi
0x18001936d  push    r12
0x18001936f  push    r13
0x180019371  push    r14
0x180019373  push    r15
0x180019375  lea     rbp, [rsp-1Fh]
0x18001937a  sub     rsp, 98h
0x180019381  xor     esi, esi
0x180019383  mov     rdi, rdx
0x180019386  mov     r13, rcx
0x180019389  mov     [rbp+57h+var_68], esi
0x18001938c  xorps   xmm0, xmm0
0x18001938f  mov     [rbp+57h+var_70], esi
0x180019392  xor     edx, edx; SourceString
0x180019394  mov     [rbp+57h+var_6C], esi
0x180019397  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001939b  mov     [rbp+57h+arg_10], si
0x18001939f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800193a3  mov     r15d, esi
0x1800193a6  mov     r12d, r9d
0x1800193a9  mov     ebx, r8d
0x1800193ac  call    cs:__imp_RtlInitUnicodeString
0x1800193b3  nop     dword ptr [rax+rax+00h]
0x1800193b8  cmp     ebx, 6Eh ; 'n'
0x1800193bb  jb      loc_18001962A
0x1800193c1  add     rdi, 2
0x1800193c5  cmp     [rdi], sil
0x1800193c8  jz      loc_18001968A
0x1800193ce  lea     r14d, [rsi+6Ch]
0x1800193d2  mov     rax, rdi
0x1800193d5  mov     r8d, r14d
0x1800193d8  cmp     [rax], sil
0x1800193db  jz      short loc_1800193E6
0x1800193dd  inc     rax
0x1800193e0  sub     r8, 1
0x1800193e4  jnz     short loc_1800193D8
0x1800193e6  mov     r9, [r13+0C0h]
0x1800193ed  mov     rax, r8
0x1800193f0  mov     rcx, r14
0x1800193f3  sub     rcx, r8
0x1800193f6  neg     rax
0x1800193f9  mov     rax, [r13+98h]
0x180019400  sbb     rdx, rdx
0x180019403  and     rdx, rcx
0x180019406  lea     rcx, [rbp+57h+arg_10]
0x18001940a  mov     [rsp+0D0h+var_98], rcx
0x18001940f  test    r8, r8
0x180019412  mov     r8, [r13+0B8h]
0x180019419  mov     rcx, [r13+0A0h]
0x180019420  cmovnz  r14, rdx
0x180019424  mov     rdx, [r13+8]
0x180019428  mov     rax, [rax+70h]
0x18001942c  mov     [rsp+0D0h+var_A0], rsi
0x180019431  mov     [rsp+0D0h+var_A8], r12d
0x180019436  mov     dword ptr [rsp+0D0h+var_B0], 0FFFEh
0x18001943e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019443  mov     [rbp+57h+var_70], eax
0x180019446  test    eax, eax
0x180019448  jz      short loc_180019482
0x18001944a  test    byte ptr cs:xmmword_180063D60, 2
0x180019451  jnz     loc_180019692
0x180019457  cmp     [rbp+57h+DestinationString.Buffer], rsi
0x18001945b  jnz     loc_180019869
0x180019461  test    r15, r15
0x180019464  jnz     loc_180019607
0x18001946a  mov     eax, [rbp+57h+var_70]
0x18001946d  add     rsp, 98h
0x180019474  pop     r15
0x180019476  pop     r14
0x180019478  pop     r13
0x18001947a  pop     r12
0x18001947c  pop     rdi
0x18001947d  pop     rsi
0x18001947e  pop     rbx
0x18001947f  pop     rbp
0x180019480  retn
0x180019482  movzx   eax, [rbp+57h+arg_10]
0x180019486  mov     rbx, rsi
0x180019489  test    ax, ax
0x18001948c  jnz     loc_1800196AB
0x180019492  shr     ax, 1
0x180019495  lea     r8, [rbp+57h+var_6C]
0x180019499  mov     r9, rdi
0x18001949c  mov     [rbp+57h+var_60], ax
0x1800194a0  xor     edx, edx
0x1800194a2  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x1800194a7  xor     ecx, ecx
0x1800194a9  call    cs:__imp_RtlUTF8ToUnicodeN
0x1800194b0  nop     dword ptr [rax+rax+00h]
0x1800194b5  mov     r12d, eax
0x1800194b8  test    eax, eax
0x1800194ba  js      loc_180019778
0x1800194c0  mov     ecx, [rbp+57h+var_6C]
0x1800194c3  mov     edx, 8; Flags
0x1800194c8  movzx   r8d, [rbp+57h+arg_10]
0x1800194cd  add     ecx, 2
0x1800194d0  mov     [rbp+57h+var_6C], ecx
0x1800194d3  add     r8d, ecx; Size
0x1800194d6  mov     rcx, gs:60h
0x1800194df  mov     rcx, [rcx+30h]; HeapHandle
0x1800194e3  call    cs:__imp_RtlAllocateHeap
0x1800194ea  nop     dword ptr [rax+rax+00h]
0x1800194ef  mov     rsi, rax
0x1800194f2  test    rax, rax
0x1800194f5  jz      loc_180019584
0x1800194fb  test    rbx, rbx
0x1800194fe  jnz     loc_1800197C7
0x180019504  movzx   eax, [rbp+57h+var_60]
0x180019508  lea     r8, [rbp+57h+var_6C]
0x18001950c  mov     edx, [rbp+57h+var_6C]
0x18001950f  mov     r9, rdi
0x180019512  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x180019517  lea     rcx, [rsi+rax*2]
0x18001951b  call    cs:__imp_RtlUTF8ToUnicodeN
0x180019522  nop     dword ptr [rax+rax+00h]
0x180019527  xor     r14d, r14d
0x18001952a  mov     edi, eax
0x18001952c  test    eax, eax
0x18001952e  js      loc_1800197DC
0x180019534  xor     r9d, r9d
0x180019537  lea     rdx, [rbp+57h+DestinationString]
0x18001953b  xor     r8d, r8d
0x18001953e  mov     rcx, rsi
0x180019541  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180019548  nop     dword ptr [rax+rax+00h]
0x18001954d  mov     edi, eax
0x18001954f  test    eax, eax
0x180019551  js      loc_1800197E7
0x180019557  mov     rcx, gs:60h
0x180019560  xor     edx, edx; Flags
0x180019562  movzx   edi, [rbp+57h+DestinationString.Length]
0x180019566  add     edi, 8
0x180019569  mov     r8d, edi; Size
0x18001956c  mov     rcx, [rcx+30h]; HeapHandle
0x180019570  call    cs:__imp_RtlAllocateHeap
0x180019577  nop     dword ptr [rax+rax+00h]
0x18001957c  mov     r15, rax
0x18001957f  test    rax, rax
0x180019582  jnz     short loc_1800195A4
0x180019584  mov     [rbp+57h+var_70], 2747h
0x18001958b  test    rbx, rbx
0x18001958e  jnz     loc_180019823
0x180019594  test    rsi, rsi
0x180019597  jnz     loc_180019846
0x18001959d  xor     esi, esi
0x18001959f  jmp     loc_180019457
0x1800195a4  mov     [rax], r14
0x1800195a7  lea     rcx, [rax+8]; void *
0x1800195ab  movzx   r8d, [rbp+57h+DestinationString.Length]; Size
0x1800195b0  mov     rdx, [rbp+57h+DestinationString.Buffer]; Src
0x1800195b4  call    memcpy_0
0x1800195b9  mov     rcx, [r13+8]
0x1800195bd  lea     rax, [rbp+57h+var_70]
0x1800195c1  mov     [rsp+0D0h+var_80], rax
0x1800195c6  mov     r9d, edi
0x1800195c9  mov     [rsp+0D0h+var_88], r14
0x1800195ce  lea     rax, [rbp+57h+var_68]
0x1800195d2  mov     [rsp+0D0h+var_90], r14
0x1800195d7  mov     r8, r15
0x1800195da  mov     [rsp+0D0h+var_98], r14
0x1800195df  mov     edx, 98000000h
0x1800195e4  mov     [rsp+0D0h+var_A0], rax
0x1800195e9  mov     [rsp+0D0h+var_A8], r14d
0x1800195ee  mov     [rsp+0D0h+var_B0], r14
0x1800195f3  call    WSPIoctl
0x1800195f8  cmp     eax, 0FFFFFFFFh
0x1800195fb  jz      loc_1800197F7
0x180019601  mov     [rbp+57h+var_70], r14d
0x180019605  jmp     short loc_18001958B
0x180019607  mov     rcx, gs:60h
0x180019610  mov     r8, r15; P
0x180019613  xor     edx, edx; Flags
0x180019615  mov     rcx, [rcx+30h]; HeapHandle
0x180019619  call    cs:__imp_RtlFreeHeap
0x180019620  nop     dword ptr [rax+rax+00h]
0x180019625  jmp     loc_18001946A
0x18001962a  mov     [rbp+57h+var_70], 2726h
0x180019631  test    byte ptr cs:xmmword_180063D60, 2
0x180019638  jz      loc_180019457
0x18001963e  mov     edx, 14h
0x180019643  lea     r8, WPP_06ddd0886b683faf63d5feb5db1037b5_Traceguids
0x18001964a  mov     ecx, 401h
0x18001964f  call    WPP_SF_
0x180019654  jmp     loc_180019457
0x180019659  mov     r15, rsi
0x18001965c  test    eax, eax
0x18001965e  jnz     loc_180019752
0x180019664  movzx   eax, [rbp+57h+arg_10]
0x180019668  test    ax, ax
0x18001966b  jz      loc_180019492
0x180019671  cmp     byte ptr [rdi], 2Fh ; '/'
0x180019674  jz      short loc_18001967F
0x180019676  cmp     byte ptr [rdi], 5Ch ; '\'
0x180019679  jnz     loc_180019492
0x18001967f  inc     rdi
0x180019682  dec     r14
0x180019685  jmp     loc_180019492
0x18001968a  mov     [rbp+57h+var_70], esi
0x18001968d  jmp     loc_180019457
0x180019692  mov     edx, 15h
0x180019697  lea     r8, WPP_06ddd0886b683faf63d5feb5db1037b5_Traceguids
0x18001969e  mov     r9d, eax
0x1800196a1  call    WPP_SF_l
0x1800196a6  jmp     loc_180019457
0x1800196ab  test    rbx, rbx
0x1800196ae  jz      short loc_1800196D2
0x1800196b0  mov     rcx, gs:60h
0x1800196b9  mov     r8, rbx; P
0x1800196bc  xor     edx, edx; Flags
0x1800196be  mov     rcx, [rcx+30h]; HeapHandle
0x1800196c2  call    cs:__imp_RtlFreeHeap
0x1800196c9  nop     dword ptr [rax+rax+00h]
0x1800196ce  movzx   eax, [rbp+57h+arg_10]
0x1800196d2  mov     rcx, gs:60h
0x1800196db  mov     edx, 8; Flags
0x1800196e0  movzx   r8d, ax; Size
0x1800196e4  mov     rcx, [rcx+30h]; HeapHandle
0x1800196e8  call    cs:__imp_RtlAllocateHeap
0x1800196ef  nop     dword ptr [rax+rax+00h]
0x1800196f4  mov     r9, [r13+0C0h]
0x1800196fb  lea     rcx, [rbp+57h+arg_10]
0x1800196ff  mov     r8, [r13+0B8h]
0x180019706  mov     rbx, rax
0x180019709  mov     rax, [r13+98h]
0x180019710  mov     rdx, [r13+8]
0x180019714  mov     [rsp+0D0h+var_98], rcx
0x180019719  mov     rcx, [r13+0A0h]
0x180019720  mov     rax, [rax+70h]
0x180019724  mov     [rsp+0D0h+var_A0], rbx
0x180019729  mov     [rsp+0D0h+var_A8], r12d
0x18001972e  mov     dword ptr [rsp+0D0h+var_B0], 0FFFEh
0x180019736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001973b  mov     [rbp+57h+var_70], eax
0x18001973e  cmp     eax, 271Eh
0x180019743  jnz     loc_180019659
0x180019749  movzx   eax, [rbp+57h+arg_10]
0x18001974d  jmp     loc_1800196AB
0x180019752  test    byte ptr cs:xmmword_180063D60, 2
0x180019759  jz      loc_18001958B
0x18001975f  mov     edx, 16h
0x180019764  lea     r8, WPP_06ddd0886b683faf63d5feb5db1037b5_Traceguids
0x18001976b  mov     r9d, eax
0x18001976e  call    WPP_SF_l
0x180019773  jmp     loc_18001958B
0x180019778  test    byte ptr cs:xmmword_180063D60, 2
0x18001977f  jz      short loc_18001979A
0x180019781  mov     edx, 17h
0x180019786  lea     r8, WPP_06ddd0886b683faf63d5feb5db1037b5_Traceguids
0x18001978d  mov     ecx, 401h
0x180019792  mov     r9d, r12d
0x180019795  call    WPP_SF_d
0x18001979a  mov     ecx, r12d
0x18001979d  jmp     short loc_1800197BA
0x18001979f  mov     edx, 18h
0x1800197a4  mov     ecx, 401h
0x1800197a9  lea     r8, WPP_06ddd0886b683faf63d5feb5db1037b5_Traceguids
0x1800197b0  mov     r9d, edi
0x1800197b3  call    WPP_SF_d
0x1800197b8  mov     ecx, edi
0x1800197ba  call    NtStatusToSocketError
0x1800197bf  mov     [rbp+57h+var_70], eax
0x1800197c2  jmp     loc_18001958B
0x1800197c7  movzx   r8d, [rbp+57h+arg_10]; Size
0x1800197cc  mov     rdx, rbx; Src
0x1800197cf  mov     rcx, rsi; void *
0x1800197d2  call    memcpy_0
0x1800197d7  jmp     loc_180019504
0x1800197dc  test    byte ptr cs:xmmword_180063D60, 2
0x1800197e3  jz      short loc_1800197B8
0x1800197e5  jmp     short loc_18001979F
0x1800197e7  test    byte ptr cs:xmmword_180063D60, 2
0x1800197ee  jz      short loc_1800197B8
0x1800197f0  mov     edx, 19h
0x1800197f5  jmp     short loc_1800197A4
0x1800197f7  test    byte ptr cs:xmmword_180063D60, 2
0x1800197fe  jz      loc_18001958B
0x180019804  mov     r9d, [rbp+57h+var_70]
0x180019808  lea     r8, WPP_06ddd0886b683faf63d5feb5db1037b5_Traceguids
0x18001980f  mov     edx, 1Ah
0x180019814  mov     ecx, 401h
0x180019819  call    WPP_SF_d
0x18001981e  jmp     loc_18001958B
0x180019823  mov     rcx, gs:60h
0x18001982c  mov     r8, rbx; P
0x18001982f  xor     edx, edx; Flags
0x180019831  mov     rcx, [rcx+30h]; HeapHandle
0x180019835  call    cs:__imp_RtlFreeHeap
0x18001983c  nop     dword ptr [rax+rax+00h]
0x180019841  jmp     loc_180019594
0x180019846  mov     rcx, gs:60h
0x18001984f  mov     r8, rsi; P
0x180019852  xor     edx, edx; Flags
0x180019854  mov     rcx, [rcx+30h]; HeapHandle
0x180019858  call    cs:__imp_RtlFreeHeap
0x18001985f  nop     dword ptr [rax+rax+00h]
0x180019864  jmp     loc_18001959D
0x180019869  mov     rcx, gs:60h
  ... truncated ...
```
