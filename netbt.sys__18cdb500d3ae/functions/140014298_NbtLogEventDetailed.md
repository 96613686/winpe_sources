# NbtLogEventDetailed

- ea: `0x140014298`
- end: `0x1400144f7`
- name: `NbtLogEventDetailed`
- size: `607`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x140007354`
- `0x140012694`
- `0x14001aa0c`
- `0x140021ff8`
- `0x1400232bc`
- `0x1400260f4`
- `0x140028040`
- `0x140045570`
- `0x140050ce4`
- `0x140053828`

## callees

- `0x140014298`
- `0x140031140`
- `0x140040294`

## import_xrefs

- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140014307`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140014307`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400144e4`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400144e4`

## pseudocode

```c
__int64 __fastcall NbtLogEventDetailed(
        int a1,
        int a2,
        int a3,
        const void *a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        char a7)
{
  unsigned int v11; // r10d
  unsigned __int64 v12; // rdx
  unsigned int v13; // r12d
  int v14; // ebx
  char *ErrorLogEntry; // rax
  _DWORD *v16; // rsi
  char *v18; // r8
  unsigned int i; // edx
  __int64 v20; // rcx
  __int64 v21; // r9
  int v22; // eax
  unsigned __int16 v23; // r8
  char *v24; // r15
  unsigned int v25; // ebp
  char *v26; // r14
  __int64 v27; // rdi
  _WORD *v28; // rdx
  size_t v29; // rbx

  v11 = 0;
  if ( a6 )
  {
    v18 = &a7;
    for ( i = 0; i < a6; ++i )
    {
      v18 += 8;
      v20 = -1;
      v21 = *((_QWORD *)v18 - 1);
      do
        ++v20;
      while ( *(_WORD *)(v21 + 2 * v20) );
      while ( (int)v20 > 0 && *(_WORD *)(v21 + 2LL * (unsigned int)v20 - 2) == 32 )
        LODWORD(v20) = v20 - 1;
      v11 += 2 * v20 + 2;
    }
  }
  v12 = v11 + a5 + 49LL;
  if ( v12 < 0xF0 )
  {
    if ( (unsigned int)v12 < 0x28 )
      return 3221225621LL;
  }
  else
  {
    LODWORD(v12) = 240;
  }
  v13 = v11;
  if ( (int)v12 - 40 <= v11 )
    v13 = v12 - 40;
  v14 = v11 < (int)v12 - 40 ? v12 - 40 - v11 : 0;
  ErrorLogEntry = (char *)IoAllocateErrorLogEntry(DriverObject, v12);
  v16 = ErrorLogEntry;
  if ( ErrorLogEntry )
  {
    *((_DWORD *)ErrorLogEntry + 3) = a1;
    *((_DWORD *)ErrorLogEntry + 4) = a3;
    *((_DWORD *)ErrorLogEntry + 5) = a2;
    *(_DWORD *)ErrorLogEntry = 0;
    *(_QWORD *)(ErrorLogEntry + 28) = 0;
    *((_DWORD *)ErrorLogEntry + 9) = 0;
    *((_WORD *)ErrorLogEntry + 2) = 0;
    v22 = EventLogSequenceNumber;
    v16[6] = EventLogSequenceNumber;
    EventLogSequenceNumber = v22 + 1;
    *((_WORD *)v16 + 3) = (v14 + 41) & 0xFFFE;
    if ( a4 && v14 )
    {
      if ( a5 < (unsigned __int16)v14 )
        LOWORD(v14) = a5;
      memmove(v16 + 10, a4, (unsigned __int16)v14);
      *((_WORD *)v16 + 1) = v14;
    }
    v23 = a6;
    if ( a6 )
    {
      v24 = &a7;
      v25 = 0;
      v26 = (char *)v16 + *((unsigned __int16 *)v16 + 3);
      do
      {
        v24 += 8;
        v27 = -1;
        v28 = (_WORD *)*((_QWORD *)v24 - 1);
        do
          ++v27;
        while ( v28[v27] );
        while ( (int)v27 > 0 && v28[(unsigned int)v27 - 1] == 32 )
          LODWORD(v27) = v27 - 1;
        if ( 2LL * ((int)v27 + 1) > (unsigned __int64)v13 )
          LODWORD(v27) = (v13 >> 1) - 1;
        if ( (int)v27 > 0 )
        {
          v29 = 2LL * (int)v27;
          memmove(v26, v28, v29);
          *(_WORD *)&v26[v29] = 0;
          v26 += v29 + 2;
          v13 += -2 - 2 * v27;
          ++*((_WORD *)v16 + 2);
          v23 = a6;
        }
        ++v25;
      }
      while ( v25 < v23 );
    }
    IoWriteErrorLogEntry(v16);
    return 0;
  }
  else
  {
    if ( (BYTE3(xmmword_140038420) & 2) != 0 )
      WPP_SF_(1049, 54, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140014298  mov     rax, rsp
0x14001429b  push    rbx
0x14001429c  push    rbp
0x14001429d  push    rsi
0x14001429e  push    rdi
0x14001429f  push    r12
0x1400142a1  push    r13
0x1400142a3  push    r14
0x1400142a5  push    r15
0x1400142a7  sub     rsp, 38h
0x1400142ab  movzx   eax, word ptr [rax+30h]
0x1400142af  xor     ebx, ebx
0x1400142b1  mov     rbp, r9
0x1400142b4  mov     r14d, r8d
0x1400142b7  mov     r15d, edx
0x1400142ba  mov     r13d, ecx
0x1400142bd  mov     r10d, ebx
0x1400142c0  test    ax, ax
0x1400142c3  jnz     short loc_140014343
0x1400142c5  movzx   edi, [rsp+78h+arg_20]
0x1400142cd  mov     eax, 0F0h
0x1400142d2  mov     ecx, r10d
0x1400142d5  lea     rdx, [rdi+31h]
0x1400142d9  add     rdx, rcx
0x1400142dc  cmp     rdx, rax
0x1400142df  jb      loc_140014395
0x1400142e5  mov     edx, eax; EntrySize
0x1400142e7  lea     ecx, [rdx-28h]
0x1400142ea  mov     r12d, r10d
0x1400142ed  cmp     ecx, r10d
0x1400142f0  mov     eax, ecx
0x1400142f2  cmovbe  r12d, ecx
0x1400142f6  sub     eax, r10d
0x1400142f9  cmp     r10d, ecx
0x1400142fc  mov     rcx, cs:DriverObject; IoObject
0x140014303  sbb     ebx, ebx
0x140014305  and     ebx, eax
0x140014307  call    cs:__imp_IoAllocateErrorLogEntry
0x14001430e  nop     dword ptr [rax+rax+00h]
0x140014313  mov     rsi, rax
0x140014316  test    rax, rax
0x140014319  jnz     loc_1400143B5
0x14001431f  test    byte ptr cs:xmmword_140038420+3, 2
0x140014326  jz      short loc_14001433C
0x140014328  lea     edx, [rax+36h]
0x14001432b  mov     ecx, 419h
0x140014330  lea     r8, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids
0x140014337  call    WPP_SF_
0x14001433c  mov     eax, 0C000009Ah
0x140014341  jmp     short loc_1400143A3
0x140014343  lea     r8, [rsp+78h+arg_30]
0x14001434b  mov     r11d, eax
0x14001434e  mov     edx, ebx
0x140014350  test    eax, eax
0x140014352  jz      loc_1400142C5
0x140014358  lea     r8, [r8+8]
0x14001435c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140014360  mov     r9, [r8-8]
0x140014364  inc     rcx
0x140014367  cmp     [r9+rcx*2], bx
0x14001436c  jnz     short loc_140014364
0x14001436e  test    ecx, ecx
0x140014370  jg      short loc_140014386
0x140014372  lea     r10d, [r10+rcx*2]
0x140014376  inc     edx
0x140014378  add     r10d, 2
0x14001437c  cmp     edx, r11d
0x14001437f  jb      short loc_140014358
0x140014381  jmp     loc_1400142C5
0x140014386  mov     eax, ecx
0x140014388  cmp     word ptr [r9+rax*2-2], 20h ; ' '
0x14001438f  jnz     short loc_140014372
0x140014391  dec     ecx
0x140014393  jmp     short loc_14001436E
0x140014395  cmp     edx, 28h ; '('
0x140014398  jnb     loc_1400142E7
0x14001439e  mov     eax, 0C0000095h
0x1400143a3  add     rsp, 38h
0x1400143a7  pop     r15
0x1400143a9  pop     r14
0x1400143ab  pop     r13
0x1400143ad  pop     r12
0x1400143af  pop     rdi
0x1400143b0  pop     rsi
0x1400143b1  pop     rbp
0x1400143b2  pop     rbx
0x1400143b3  retn
0x1400143b5  mov     [rax+0Ch], r13d
0x1400143b9  mov     ecx, 0FFFEh
0x1400143be  xor     r13d, r13d
0x1400143c1  mov     [rax+10h], r14d
0x1400143c5  mov     [rax+14h], r15d
0x1400143c9  mov     [rax], r13d
0x1400143cc  mov     [rax+1Ch], r13
0x1400143d0  mov     [rax+24h], r13d
0x1400143d4  lea     r9d, [r13+1]
0x1400143d8  mov     [rax+4], r13w
0x1400143dd  mov     eax, cs:EventLogSequenceNumber
0x1400143e3  mov     [rsi+18h], eax
0x1400143e6  add     eax, r9d
0x1400143e9  mov     cs:EventLogSequenceNumber, eax
0x1400143ef  lea     eax, [rbx+29h]
0x1400143f2  and     ax, cx
0x1400143f5  mov     [rsi+6], ax
0x1400143f9  test    rbp, rbp
0x1400143fc  jz      short loc_140014421
0x1400143fe  test    ebx, ebx
0x140014400  jz      short loc_140014421
0x140014402  cmp     di, bx
0x140014405  lea     rcx, [rsi+28h]; void *
0x140014409  mov     rdx, rbp; Src
0x14001440c  cmovb   bx, di
0x140014410  movzx   r8d, bx; Size
0x140014414  call    memmove
0x140014419  lea     r9d, [r13+1]
0x14001441d  mov     [rsi+2], bx
0x140014421  movzx   r8d, [rsp+78h+arg_28]
0x14001442a  cmp     r8w, r13w
0x14001442e  jz      loc_1400144E1
0x140014434  lea     r15, [rsp+78h+arg_30]
0x14001443c  jbe     loc_1400144E1
0x140014442  movzx   r14d, word ptr [rsi+6]
0x140014447  mov     ebp, r13d
0x14001444a  add     r14, rsi
0x14001444d  lea     r15, [r15+8]
0x140014451  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140014455  mov     rdx, [r15-8]; Src
0x140014459  inc     rdi
0x14001445c  cmp     [rdx+rdi*2], r13w
0x140014461  jnz     short loc_140014459
0x140014463  jmp     short loc_140014472
0x140014465  mov     eax, edi
0x140014467  cmp     word ptr [rdx+rax*2-2], 20h ; ' '
0x14001446d  jnz     short loc_140014476
0x14001446f  sub     edi, r9d
0x140014472  test    edi, edi
0x140014474  jg      short loc_140014465
0x140014476  lea     eax, [rdi+1]
0x140014479  movsxd  rcx, eax
0x14001447c  add     rcx, rcx
0x14001447f  mov     eax, r12d
0x140014482  cmp     rcx, rax
0x140014485  jbe     short loc_14001448F
0x140014487  mov     edi, r12d
0x14001448a  shr     edi, 1
0x14001448c  sub     edi, r9d
0x14001448f  test    edi, edi
0x140014491  jle     short loc_1400144D2
0x140014493  movsxd  rax, edi
0x140014496  mov     rcx, r14; void *
0x140014499  lea     rbx, [rax+rax]
0x14001449d  mov     r8, rbx; Size
0x1400144a0  call    memmove
0x1400144a5  lea     rcx, [rbx+r14]
0x1400144a9  mov     edx, 0FFFFFFFEh
0x1400144ae  mov     [rcx], r13w
0x1400144b2  lea     eax, [rdi+rdi]
0x1400144b5  sub     edx, eax
0x1400144b7  lea     r14, [rcx+2]
0x1400144bb  add     r12d, edx
0x1400144be  mov     r9d, 1
0x1400144c4  add     [rsi+4], r9w
0x1400144c9  movzx   r8d, [rsp+78h+arg_28]
0x1400144d2  add     ebp, r9d
0x1400144d5  movzx   eax, r8w
0x1400144d9  cmp     ebp, eax
0x1400144db  jb      loc_14001444D
0x1400144e1  mov     rcx, rsi; ElEntry
0x1400144e4  call    cs:__imp_IoWriteErrorLogEntry
0x1400144eb  nop     dword ptr [rax+rax+00h]
0x1400144f0  xor     eax, eax
0x1400144f2  jmp     loc_1400143A3
```
