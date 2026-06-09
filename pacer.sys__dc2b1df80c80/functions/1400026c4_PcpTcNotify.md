# PcpTcNotify

- ea: `0x1400026c4`
- end: `0x140002873`
- name: `PcpTcNotify`
- size: `431`
- prototype: `__int64 __fastcall(__int64, int, const void *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140002500`
- `0x140003ab0`
- `0x140005578`

## callees

- `0x1400026c4`
- `0x140013300`
- `0x140013600`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002865`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002865`
- `ntoskrnl!ExAllocatePool2` at `0x140002765`
- `ntoskrnl!ExAllocatePool2` at `0x140002765`
- `ntoskrnl!IoWMIWriteEvent` at `0x14000280e`
- `ntoskrnl!IoWMIWriteEvent` at `0x14000280e`
- `ntoskrnl!IoWMIDeviceObjectToProviderId` at `0x140002794`
- `ntoskrnl!IoWMIDeviceObjectToProviderId` at `0x140002794`

## pseudocode

```c
__int64 __fastcall PcpTcNotify(__int64 a1, int a2, const void *a3, unsigned int a4)
{
  size_t v4; // r14
  __int64 *v5; // rbx
  unsigned int i; // eax
  int v8; // ebp
  int v9; // eax
  unsigned int v10; // esi
  int v11; // ebp
  unsigned int v12; // r12d
  unsigned int v13; // r13d
  NTSTATUS v14; // ebx
  char *Pool2; // rax
  char *v16; // rdi
  __int128 v17; // xmm0
  unsigned int *v18; // rcx
  size_t v19; // r8
  void *Src; // [rsp+20h] [rbp-58h]
  unsigned __int16 v22; // [rsp+80h] [rbp+8h]

  v4 = a4;
  v5 = PcgSupportedGuids;
  for ( i = 0; ; ++i )
  {
    if ( i >= 0x18 )
      return (unsigned int)-1073741823;
    v8 = *((_DWORD *)v5 + 6);
    if ( (v8 & 2) != 0 && *((_DWORD *)v5 + 4) == a2 )
      break;
    v5 = (__int64 *)((char *)v5 + 28);
  }
  if ( (v8 & 0x20) == 0 )
    return (unsigned int)-1073741823;
  v9 = *(unsigned __int16 *)(a1 + 264);
  v10 = a4 + 4;
  v11 = v5[3] & 0x10;
  v22 = *(_WORD *)(a1 + 264);
  if ( !v11 )
    v10 = a4;
  v12 = ((v9 + 9) & 0xFFFFFFF8) + 64;
  if ( ((v9 + 9) & 0xFFFFFFF8) >= 0xFFFFFFC0 )
    return (unsigned int)-1073741675;
  v13 = v12 + v10;
  if ( v12 + v10 < v12 )
    return (unsigned int)-1073741675;
  Src = *(void **)(a1 + 272);
  Pool2 = (char *)ExAllocatePool2(64, v13, 1768781648);
  v16 = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741823;
  memset(Pool2, 0, v13);
  *(_DWORD *)v16 = v13;
  *((_DWORD *)v16 + 1) = IoWMIDeviceObjectToProviderId((PDEVICE_OBJECT)WPP_MAIN_CB.Queue.ListEntry.Blink);
  *((_DWORD *)v16 + 2) = 1;
  *((_QWORD *)v16 + 2) = MEMORY[0xFFFFF78000000014];
  v17 = *(_OWORD *)v5;
  *((_DWORD *)v16 + 11) = 10;
  *(_OWORD *)(v16 + 24) = v17;
  *((_DWORD *)v16 + 12) = 64;
  *((_DWORD *)v16 + 14) = v12;
  *((_DWORD *)v16 + 15) = v10;
  *((_WORD *)v16 + 32) = v22;
  memmove(v16 + 66, Src, v22);
  v18 = (unsigned int *)&v16[*((unsigned int *)v16 + 14)];
  if ( !v11 )
  {
    if ( !v10 )
      goto LABEL_17;
    v19 = v10;
    goto LABEL_16;
  }
  if ( a3 && (_DWORD)v4 )
  {
    v19 = v4;
    *v18++ = (unsigned int)v4 / *((_DWORD *)v5 + 5);
LABEL_16:
    memmove(v18, a3, v19);
    goto LABEL_17;
  }
  *v18 = 0;
LABEL_17:
  v14 = IoWMIWriteEvent(v16);
  if ( v14 < 0 )
    ExFreePoolWithTag(v16, 0);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400026c4  push    rbx
0x1400026c6  push    rbp
0x1400026c7  push    rsi
0x1400026c8  push    rdi
0x1400026c9  push    r12
0x1400026cb  push    r13
0x1400026cd  push    r14
0x1400026cf  push    r15
0x1400026d1  sub     rsp, 38h
0x1400026d5  mov     r14d, r9d
0x1400026d8  lea     rbx, PcgSupportedGuids
0x1400026df  mov     r15, r8
0x1400026e2  xor     eax, eax
0x1400026e4  cmp     eax, 18h
0x1400026e7  jnb     loc_140002834
0x1400026ed  mov     ebp, [rbx+18h]
0x1400026f0  test    bpl, 2
0x1400026f4  jnz     short loc_1400026FE
0x1400026f6  inc     eax
0x1400026f8  add     rbx, 1Ch
0x1400026fc  jmp     short loc_1400026E4
0x1400026fe  cmp     [rbx+10h], edx
0x140002701  jnz     short loc_1400026F6
0x140002703  test    bpl, 20h
0x140002707  jz      loc_140002834
0x14000270d  movzx   eax, word ptr [rcx+108h]
0x140002714  lea     esi, [r14+4]
0x140002718  and     ebp, 10h
0x14000271b  mov     [rsp+78h+arg_0], eax
0x140002722  cmovz   esi, r14d
0x140002726  lea     r12d, [rax+9]
0x14000272a  and     r12d, 0FFFFFFF8h
0x14000272e  add     r12d, 40h ; '@'
0x140002732  cmp     r12d, 40h ; '@'
0x140002736  jb      short loc_140002741
0x140002738  lea     r13d, [r12+rsi]
0x14000273c  cmp     r13d, r12d
0x14000273f  jnb     short loc_14000274B
0x140002741  mov     ebx, 0C0000095h
0x140002746  jmp     loc_140002820
0x14000274b  mov     rax, [rcx+110h]
0x140002752  mov     r8d, 696D7750h
0x140002758  mov     ecx, 40h ; '@'
0x14000275d  mov     edx, r13d
0x140002760  mov     [rsp+78h+Src], rax
0x140002765  call    cs:__imp_ExAllocatePool2
0x14000276c  nop     dword ptr [rax+rax+00h]
0x140002771  mov     rdi, rax
0x140002774  test    rax, rax
0x140002777  jz      loc_140002834
0x14000277d  mov     r8d, r13d; Size
0x140002780  xor     edx, edx; Val
0x140002782  mov     rcx, rax; void *
0x140002785  call    memset
0x14000278a  mov     [rdi], r13d
0x14000278d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8; DeviceObject
0x140002794  call    cs:__imp_IoWMIDeviceObjectToProviderId
0x14000279b  nop     dword ptr [rax+rax+00h]
0x1400027a0  mov     rdx, [rsp+78h+Src]; Src
0x1400027a5  lea     rcx, [rdi+42h]; void *
0x1400027a9  mov     [rdi+4], eax
0x1400027ac  mov     dword ptr [rdi+8], 1
0x1400027b3  mov     rax, ds:0FFFFF78000000014h
0x1400027bd  mov     [rdi+10h], rax
0x1400027c1  movups  xmm0, xmmword ptr [rbx]
0x1400027c4  mov     eax, [rsp+78h+arg_0]
0x1400027cb  mov     dword ptr [rdi+2Ch], 0Ah
0x1400027d2  movdqu  xmmword ptr [rdi+18h], xmm0
0x1400027d7  mov     dword ptr [rdi+30h], 40h ; '@'
0x1400027de  mov     [rdi+38h], r12d
0x1400027e2  mov     [rdi+3Ch], esi
0x1400027e5  movzx   r8d, ax; Size
0x1400027e9  mov     [rdi+40h], ax
0x1400027ed  call    memmove
0x1400027f2  mov     ecx, [rdi+38h]
0x1400027f5  add     rcx, rdi; void *
0x1400027f8  test    ebp, ebp
0x1400027fa  jnz     short loc_14000283B
0x1400027fc  test    esi, esi
0x1400027fe  jz      short loc_14000280B
0x140002800  mov     r8d, esi; Size
0x140002803  mov     rdx, r15; Src
0x140002806  call    memmove
0x14000280b  mov     rcx, rdi; WnodeEventItem
0x14000280e  call    cs:__imp_IoWMIWriteEvent
0x140002815  nop     dword ptr [rax+rax+00h]
0x14000281a  mov     ebx, eax
0x14000281c  test    eax, eax
0x14000281e  js      short loc_140002860
0x140002820  mov     eax, ebx
0x140002822  add     rsp, 38h
0x140002826  pop     r15
0x140002828  pop     r14
0x14000282a  pop     r13
0x14000282c  pop     r12
0x14000282e  pop     rdi
0x14000282f  pop     rsi
0x140002830  pop     rbp
0x140002831  pop     rbx
0x140002832  retn
0x140002834  mov     ebx, 0C0000001h
0x140002839  jmp     short loc_140002820
0x14000283b  test    r15, r15
0x14000283e  jz      short loc_140002858
0x140002840  test    r14d, r14d
0x140002843  jz      short loc_140002858
0x140002845  xor     edx, edx
0x140002847  mov     eax, r14d
0x14000284a  div     dword ptr [rbx+14h]
0x14000284d  mov     r8, r14
0x140002850  mov     [rcx], eax
0x140002852  add     rcx, 4
0x140002856  jmp     short loc_140002803
0x140002858  mov     dword ptr [rcx], 0
0x14000285e  jmp     short loc_14000280B
0x140002860  xor     edx, edx; Tag
0x140002862  mov     rcx, rdi; P
0x140002865  call    cs:__imp_ExFreePoolWithTag
0x14000286c  nop     dword ptr [rax+rax+00h]
0x140002871  jmp     short loc_140002820
```
