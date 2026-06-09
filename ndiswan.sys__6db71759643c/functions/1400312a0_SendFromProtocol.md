# SendFromProtocol

- ea: `0x1400312a0`
- end: `0x1400318ac`
- name: `SendFromProtocol`
- size: `1548`
- prototype: `__int64 __usercall@<rax>(PVOID Entry@<rcx>, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140030e70`

## callees

- `0x140003970`
- `0x14000550c`
- `0x14000a290`
- `0x1400312a0`
- `0x140031b80`
- `0x1400353d0`
- `0x140035750`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003146e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400316d9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003173c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003146e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400316d9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003173c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400314d1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14003170b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14003176e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400314d1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14003170b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14003176e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003133a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003140f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400315ef`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003133a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003140f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400315ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031385`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400313ed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031615`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031875`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031385`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400313ed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031615`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031875`

## pseudocode

```c
__int64 __fastcall SendFromProtocol(char *Entry, __int64 a2, _DWORD *a3, _DWORD *a4, _BYTE *a5)
{
  __int64 v5; // rsi
  __int64 v10; // r14
  unsigned __int8 v11; // di
  __int64 *v12; // rbx
  __int64 *v13; // rax
  bool v14; // zf
  __int64 *v15; // rbx
  KIRQL v16; // al
  __int64 *v17; // rbx
  __int64 v18; // rax
  int v19; // eax
  char *v20; // rcx
  char *v21; // r13
  __int64 ***v22; // rdx
  char **v23; // rcx
  char *v24; // rdx
  struct _NET_BUFFER_LIST *v25; // rdx
  ULONGLONG Alignment; // rax
  PNET_BUFFER_LIST_CONTEXT Context; // rcx
  char *v28; // r13
  int v29; // ecx
  _QWORD *Scratch; // rdi
  NDIS_STATUS v31; // r12d
  __int64 ***v32; // rdx
  __int64 ***v33; // rdx
  unsigned int v34; // eax
  __int64 v36; // [rsp+20h] [rbp-20h]
  __int64 *v37; // [rsp+30h] [rbp-10h] BYREF
  __int64 ***v38; // [rsp+38h] [rbp-8h]
  char *v39; // [rsp+88h] [rbp+48h]
  struct _NET_BUFFER_LIST *v40; // [rsp+88h] [rbp+48h]
  char *v41; // [rsp+90h] [rbp+50h]
  int v42; // [rsp+A0h] [rbp+60h]

  v5 = *(int *)(a2 + 208);
  v38 = (__int64 ***)&v37;
  *a3 = v5;
  v37 = (__int64 *)&v37;
  *a4 &= ~*(_DWORD *)(a2 + 108);
  v10 = a2 + 48 * v5;
  *a5 = 0;
  if ( !*(_QWORD *)(v10 + 112) )
    goto LABEL_2;
  v19 = *((_DWORD *)Entry + 4) & 0x400;
  if ( v19 )
  {
    if ( (int)v5 < 1 && *(_DWORD *)(v10 + 152) )
      goto LABEL_2;
  }
  else if ( !*((_DWORD *)Entry + 39) )
  {
    goto LABEL_2;
  }
  v20 = (char *)*((_QWORD *)Entry + 11);
  v39 = v20;
  if ( !v20 )
    goto LABEL_45;
  v42 = 0;
  v21 = v20;
  v41 = v20;
  if ( (_DWORD)v5 == 1 )
  {
    do
    {
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v21 + 92);
      if ( *((_DWORD *)v21 + 5) == 2 && v21[200] && v21[201] )
      {
        v32 = v38;
        if ( *v38 != &v37 )
          goto LABEL_82;
        v39 = v21;
        *((_QWORD *)v21 + 31) = v38;
        *((_QWORD *)v21 + 30) = &v37;
        *v32 = (__int64 **)(v21 + 240);
        v38 = (__int64 ***)(v21 + 240);
        ++*((_DWORD *)v21 + 7);
        ++v42;
      }
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v21 + 92);
      v23 = (char **)(Entry + 48);
      v21 = *(char **)v21;
      if ( v21 == Entry + 48 )
        v21 = *v23;
    }
    while ( v21 != v41 );
  }
  else if ( v19 )
  {
    do
    {
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v21 + 92);
      if ( *((_DWORD *)v21 + 5) == 2 && v21[200] && *((_DWORD *)v21 + 51) )
      {
        v33 = v38;
        if ( *v38 != &v37 )
          goto LABEL_82;
        v39 = v21;
        *((_QWORD *)v21 + 31) = v38;
        *((_QWORD *)v21 + 30) = &v37;
        *v33 = (__int64 **)(v21 + 240);
        v38 = (__int64 ***)(v21 + 240);
        ++*((_DWORD *)v21 + 7);
        ++v42;
      }
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v21 + 92);
      v23 = (char **)(Entry + 48);
      v21 = *(char **)v21;
      if ( v21 == Entry + 48 )
        v21 = *v23;
    }
    while ( v21 != v41 );
  }
  else
  {
    do
    {
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v21 + 92);
      if ( *((_DWORD *)v21 + 5) == 2 && v21[200] && v21[201] )
      {
        v22 = v38;
        if ( *v38 != &v37 )
          goto LABEL_82;
        v39 = v21;
        *((_QWORD *)v21 + 31) = v38;
        *((_QWORD *)v21 + 30) = &v37;
        *v22 = (__int64 **)(v21 + 240);
        v38 = (__int64 ***)(v21 + 240);
        ++*((_DWORD *)v21 + 7);
        ++v42;
      }
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v21 + 92);
      v21 = *(char **)v21;
      v23 = (char **)(Entry + 48);
      if ( v21 == Entry + 48 )
        v21 = *v23;
    }
    while ( v21 != v41 );
  }
  v24 = *(char **)v39;
  if ( *(char ***)v39 == v23 )
    v24 = *v23;
  *((_QWORD *)Entry + 11) = v24;
  if ( !v42 )
  {
LABEL_45:
    v11 = 0;
    goto LABEL_4;
  }
  v25 = *(struct _NET_BUFFER_LIST **)(v10 + 112);
  v40 = v25;
  Alignment = v25->Link.Alignment;
  if ( !v25->Link.Alignment )
    *(_QWORD *)(v10 + 120) = 0;
  v25->Link.Alignment = 0;
  *(_QWORD *)(v10 + 112) = Alignment;
  Context = v25->Context;
  *a5 = 1;
  *(_DWORD *)(v10 + 128) -= *(_DWORD *)&Context->ContextData[Context->Offset + 100];
  --*(_DWORD *)(v10 + 136);
  v28 = (char *)v25->Context + v25->Context->Offset;
  v29 = *((_DWORD *)Entry + 4);
  if ( (v29 & 0x400) == 0 )
    *a4 |= *(_DWORD *)(a2 + 108);
  if ( (v29 & 0x100000) != 0 )
  {
    *((_DWORD *)v28 + 11) |= 8u;
    ++*((_DWORD *)Entry + 6);
    ++*((_DWORD *)Entry + 42);
    _InterlockedDecrement((volatile signed __int32 *)v28 + 10);
    FramePacketFast((__int64)Entry, a2, v25, &v37, v36, v5);
    goto LABEL_2;
  }
  Scratch = v25->Scratch;
  v31 = 0;
  if ( Scratch == (_QWORD *)v25->FirstNetBuffer )
  {
    *((_DWORD *)v28 + 11) |= 4u;
    *((_QWORD *)v28 + 12) = v25;
    *((_QWORD *)v28 + 9) = Entry;
  }
  while ( 1 )
  {
    if ( !Scratch )
      goto LABEL_43;
    if ( v37 == (__int64 *)&v37 )
      break;
LABEL_41:
    if ( (unsigned int)FramePacket(Entry, a2, (__int64)v25, &v37, v42, v5) == -1 )
    {
      v31 = -1073741823;
LABEL_43:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v28 + 10, 0xFFFFFFFF) == 1 )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)Entry + 221, Entry[1776]);
        CompleteNetBufferList(*(_QWORD *)(a2 + 56), a2, v40, v31);
        Entry[1776] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry + 221);
      }
      goto LABEL_2;
    }
    v25 = v40;
    Scratch = (_QWORD *)*Scratch;
    v40->Scratch = Scratch;
  }
  if ( (unsigned int)GetSendingLinks(Entry, (unsigned int)v5, &v37) )
  {
    v25 = v40;
    goto LABEL_41;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids);
  }
  if ( *((_DWORD *)Entry + 5) != 2 )
    goto LABEL_43;
  v40->Link.Alignment = *(_QWORD *)(v10 + 112);
  if ( !*(_QWORD *)(v10 + 112) )
    *(_QWORD *)(v10 + 120) = v40;
  *(_QWORD *)(v10 + 112) = v40;
  *(_DWORD *)(v10 + 128) += *((_DWORD *)v28 + 29);
  v34 = ++*(_DWORD *)(v10 + 136);
  if ( v34 > *(_DWORD *)(v10 + 140) )
    *(_DWORD *)(v10 + 140) = v34;
LABEL_2:
  ++*(_DWORD *)(a2 + 208);
  v11 = 1;
  if ( *(_DWORD *)(a2 + 208) > 1u )
    *(_DWORD *)(a2 + 208) = 0;
LABEL_4:
  if ( v37 != (__int64 *)&v37 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)Entry + 221, Entry[1776]);
    v12 = v37;
    if ( (__int64 **)v37[1] == &v37 )
    {
      v13 = (__int64 *)*v37;
      if ( *(__int64 **)(*v37 + 8) == v37 )
      {
        v37 = (__int64 *)*v37;
        v14 = v12 == (__int64 *)240;
        v15 = v12 - 30;
        v13[1] = (__int64)&v37;
        *((_QWORD *)Entry + 11) = v15;
        if ( v14 )
          goto LABEL_10;
        v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v15 + 92);
        v14 = (*((_DWORD *)v15 + 7))-- == 1;
        *((_BYTE *)v15 + 744) = v16;
        if ( !v14 )
          goto LABEL_15;
LABEL_9:
        DoDerefLinkCBWork(v15);
LABEL_10:
        while ( 1 )
        {
          v17 = v37;
          if ( v37 == (__int64 *)&v37 )
            break;
          if ( (__int64 **)v37[1] != &v37 )
            goto LABEL_82;
          v18 = *v37;
          if ( *(__int64 **)(*v37 + 8) != v37 )
            goto LABEL_82;
          v37 = (__int64 *)*v37;
          *(_QWORD *)(v18 + 8) = &v37;
          v15 = v17 - 30;
          if ( v15 )
          {
            v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v15 + 92);
            v14 = (*((_DWORD *)v15 + 7))-- == 1;
            *((_BYTE *)v15 + 744) = v16;
            if ( v14 )
              goto LABEL_9;
LABEL_15:
            KeReleaseSpinLock((PKSPIN_LOCK)v15 + 92, v16);
          }
        }
        Entry[1776] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry + 221);
        return v11;
      }
    }
LABEL_82:
    __fastfail(3u);
  }
  return v11;
}

```

## disassembly

```asm
0x1400312a0  mov     [rsp-38h+arg_0], rbx
0x1400312a5  push    rbp
0x1400312a6  push    rsi
0x1400312a7  push    rdi
0x1400312a8  push    r12
0x1400312aa  push    r13
0x1400312ac  push    r14
0x1400312ae  push    r15
0x1400312b0  mov     rbp, rsp
0x1400312b3  sub     rsp, 40h
0x1400312b7  movsxd  rsi, dword ptr [rdx+0D0h]
0x1400312be  lea     rax, [rbp+var_10]
0x1400312c2  mov     r12, qword ptr [rbp+arg_20]
0x1400312c6  mov     rdi, r9
0x1400312c9  mov     [rbp+var_8], rax
0x1400312cd  mov     rbx, rdx
0x1400312d0  lea     rax, [rbp+var_10]
0x1400312d4  mov     [r8], esi
0x1400312d7  mov     [rbp+var_10], rax
0x1400312db  lea     r14, [rsi+rsi*2]
0x1400312df  mov     eax, [rdx+6Ch]
0x1400312e2  mov     r15, rcx
0x1400312e5  shl     r14, 4
0x1400312e9  not     eax
0x1400312eb  and     [r9], eax
0x1400312ee  add     r14, rdx
0x1400312f1  mov     byte ptr [r12], 0
0x1400312f6  cmp     qword ptr [r14+70h], 0
0x1400312fb  jnz     loc_14003141D
0x140031301  inc     dword ptr [rbx+0D0h]
0x140031307  mov     dil, 1
0x14003130a  cmp     dword ptr [rbx+0D0h], 1
0x140031311  jbe     short loc_14003131D
0x140031313  mov     dword ptr [rbx+0D0h], 0
0x14003131d  lea     rax, [rbp+var_10]
0x140031321  cmp     [rbp+var_10], rax
0x140031325  jz      loc_140031888
0x14003132b  movzx   edx, byte ptr [r15+6F0h]; NewIrql
0x140031333  lea     rcx, [r15+6E8h]; SpinLock
0x14003133a  call    cs:__imp_KeReleaseSpinLock
0x140031341  nop     dword ptr [rax+rax+00h]
0x140031346  mov     rbx, [rbp+var_10]
0x14003134a  lea     rax, [rbp+var_10]
0x14003134e  cmp     [rbx+8], rax
0x140031352  jnz     loc_1400318A5
0x140031358  mov     rax, [rbx]
0x14003135b  cmp     [rax+8], rbx
0x14003135f  jnz     loc_1400318A5
0x140031365  lea     rcx, [rbp+var_10]
0x140031369  mov     [rbp+var_10], rax
0x14003136d  add     rbx, 0FFFFFFFFFFFFFF10h
0x140031374  mov     [rax+8], rcx
0x140031378  mov     [r15+58h], rbx
0x14003137c  jz      short loc_1400313A5
0x14003137e  lea     rcx, [rbx+2E0h]; SpinLock
0x140031385  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003138c  nop     dword ptr [rax+rax+00h]
0x140031391  add     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x140031395  mov     [rbx+2E8h], al
0x14003139b  jnz     short loc_140031405
0x14003139d  mov     rcx, rbx; Entry
0x1400313a0  call    DoDerefLinkCBWork
0x1400313a5  mov     rbx, [rbp+var_10]
0x1400313a9  lea     rax, [rbp+var_10]
0x1400313ad  cmp     rbx, rax
0x1400313b0  jz      loc_14003186E
0x1400313b6  lea     rax, [rbp+var_10]
0x1400313ba  cmp     [rbx+8], rax
0x1400313be  jnz     loc_1400318A5
0x1400313c4  mov     rax, [rbx]
0x1400313c7  cmp     [rax+8], rbx
0x1400313cb  jnz     loc_1400318A5
0x1400313d1  mov     [rbp+var_10], rax
0x1400313d5  lea     rcx, [rbp+var_10]
0x1400313d9  mov     [rax+8], rcx
0x1400313dd  add     rbx, 0FFFFFFFFFFFFFF10h
0x1400313e4  jz      short loc_1400313A5
0x1400313e6  lea     rcx, [rbx+2E0h]; SpinLock
0x1400313ed  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400313f4  nop     dword ptr [rax+rax+00h]
0x1400313f9  add     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x1400313fd  mov     [rbx+2E8h], al
0x140031403  jz      short loc_14003139D
0x140031405  movzx   edx, al; NewIrql
0x140031408  lea     rcx, [rbx+2E0h]; SpinLock
0x14003140f  call    cs:__imp_KeReleaseSpinLock
0x140031416  nop     dword ptr [rax+rax+00h]
0x14003141b  jmp     short loc_1400313A5
0x14003141d  mov     eax, [rcx+10h]
0x140031420  and     eax, 400h
0x140031425  jnz     loc_140031645
0x14003142b  cmp     [rcx+9Ch], eax
0x140031431  jz      loc_140031301
0x140031437  mov     rcx, [rcx+58h]
0x14003143b  mov     [rbp+arg_8], rcx
0x14003143f  test    rcx, rcx
0x140031442  jz      loc_14003162D
0x140031448  mov     [rbp+arg_20], 0
0x14003144f  mov     r13, rcx
0x140031452  mov     [rbp+arg_10], rcx
0x140031456  cmp     esi, 1
0x140031459  jz      loc_1400316D2
0x14003145f  test    eax, eax
0x140031461  jnz     loc_140031735
0x140031467  lea     rcx, [r13+2E0h]; SpinLock
0x14003146e  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140031475  nop     dword ptr [rax+rax+00h]
0x14003147a  cmp     dword ptr [r13+14h], 2
0x14003147f  jnz     short loc_1400314CA
0x140031481  cmp     byte ptr [r13+0C8h], 0
0x140031489  jz      short loc_1400314CA
0x14003148b  cmp     byte ptr [r13+0C9h], 0
0x140031493  jz      short loc_1400314CA
0x140031495  mov     rdx, [rbp+var_8]
0x140031499  lea     rax, [rbp+var_10]
0x14003149d  cmp     [rdx], rax
0x1400314a0  jnz     loc_1400318A5
0x1400314a6  lea     rax, [r13+0F0h]
0x1400314ad  mov     [rbp+arg_8], r13
0x1400314b1  mov     [rax+8], rdx
0x1400314b5  lea     rcx, [rbp+var_10]
0x1400314b9  mov     [rax], rcx
0x1400314bc  mov     [rdx], rax
0x1400314bf  mov     [rbp+var_8], rax
0x1400314c3  inc     dword ptr [r13+1Ch]
0x1400314c7  inc     [rbp+arg_20]
0x1400314ca  lea     rcx, [r13+2E0h]; SpinLock
0x1400314d1  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400314d8  nop     dword ptr [rax+rax+00h]
0x1400314dd  mov     r13, [r13+0]
0x1400314e1  lea     rcx, [r15+30h]
0x1400314e5  cmp     r13, rcx
0x1400314e8  jnz     short loc_1400314ED
0x1400314ea  mov     r13, [rcx]
0x1400314ed  cmp     r13, [rbp+arg_10]
0x1400314f1  jnz     loc_140031467
0x1400314f7  mov     rax, [rbp+arg_8]
0x1400314fb  mov     rdx, [rax]
0x1400314fe  cmp     rdx, rcx
0x140031501  jnz     short loc_140031506
0x140031503  mov     rdx, [rcx]
0x140031506  cmp     [rbp+arg_20], 0
0x14003150a  mov     [r15+58h], rdx
0x14003150e  jz      loc_14003162D
0x140031514  mov     rdx, [r14+70h]
0x140031518  mov     [rbp+arg_8], rdx
0x14003151c  mov     rax, [rdx]
0x14003151f  test    rax, rax
0x140031522  jnz     short loc_140031528
0x140031524  mov     [r14+78h], rax
0x140031528  mov     qword ptr [rdx], 0
0x14003152f  mov     [r14+70h], rax
0x140031533  mov     rcx, [rdx+10h]
0x140031537  mov     byte ptr [r12], 1
0x14003153c  movzx   eax, word ptr [rcx+0Ah]
0x140031540  mov     ecx, [rax+rcx+74h]
0x140031544  sub     [r14+80h], ecx
0x14003154b  dec     dword ptr [r14+88h]
0x140031552  mov     rcx, [rdx+10h]
0x140031556  movzx   r13d, word ptr [rcx+0Ah]
0x14003155b  add     r13, rcx
0x14003155e  mov     ecx, [r15+10h]
0x140031562  bt      ecx, 0Ah
0x140031566  jb      short loc_14003156D
0x140031568  mov     eax, [rbx+6Ch]
0x14003156b  or      [rdi], eax
0x14003156d  bt      ecx, 14h
0x140031571  jb      loc_140031798
0x140031577  mov     rdi, [rdx+70h]
0x14003157b  xor     r12d, r12d
0x14003157e  cmp     rdi, [rdx+8]
0x140031582  jnz     short loc_140031591
0x140031584  or      dword ptr [r13+2Ch], 4
0x140031589  mov     [r13+60h], rdx
0x14003158d  mov     [r13+48h], r15
0x140031591  test    rdi, rdi
0x140031594  jz      short loc_1400315CC
0x140031596  lea     rax, [rbp+var_10]
0x14003159a  cmp     [rbp+var_10], rax
0x14003159e  jz      loc_1400317C8
0x1400315a4  mov     eax, [rbp+arg_20]
0x1400315a7  lea     r9, [rbp+var_10]
0x1400315ab  mov     r8, rdx
0x1400315ae  mov     [rsp+40h+var_18], esi; ULONG
0x1400315b2  mov     rdx, rbx
0x1400315b5  mov     dword ptr [rsp+40h+var_20], eax; int
0x1400315b9  mov     rcx, r15; Entry
0x1400315bc  call    FramePacket
0x1400315c1  cmp     eax, 0FFFFFFFFh
0x1400315c4  jnz     short loc_140031635
0x1400315c6  mov     r12d, 0C0000001h
0x1400315cc  mov     eax, 0FFFFFFFFh
0x1400315d1  lock xadd [r13+28h], eax
0x1400315d7  cmp     eax, 1
0x1400315da  jnz     loc_140031301
0x1400315e0  movzx   edx, byte ptr [r15+6F0h]; NewIrql
0x1400315e8  lea     rcx, [r15+6E8h]; SpinLock
0x1400315ef  call    cs:__imp_KeReleaseSpinLock
0x1400315f6  nop     dword ptr [rax+rax+00h]
0x1400315fb  mov     r8, [rbp+arg_8]
0x1400315ff  mov     r9d, r12d
0x140031602  mov     rcx, [rbx+38h]
0x140031606  mov     rdx, rbx
0x140031609  call    CompleteNetBufferList
0x14003160e  lea     rcx, [r15+6E8h]; SpinLock
0x140031615  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003161c  nop     dword ptr [rax+rax+00h]
0x140031621  mov     [r15+6F0h], al
0x140031628  jmp     loc_140031301
0x14003162d  xor     dil, dil
0x140031630  jmp     loc_14003131D
0x140031635  mov     rdx, [rbp+arg_8]
0x140031639  mov     rdi, [rdi]
0x14003163c  mov     [rdx+70h], rdi
0x140031640  jmp     loc_140031591
0x140031645  cmp     esi, 1
0x140031648  jge     loc_140031437
0x14003164e  cmp     dword ptr [r14+98h], 0
0x140031656  jnz     loc_140031301
0x14003165c  jmp     loc_140031437
0x140031661  mov     rdx, [rbp+var_8]
0x140031665  lea     rax, [rbp+var_10]
0x140031669  cmp     [rdx], rax
0x14003166c  jnz     loc_1400318A5
0x140031672  lea     rax, [r13+0F0h]
0x140031679  mov     [rbp+arg_8], r13
0x14003167d  mov     [rax+8], rdx
0x140031681  lea     rcx, [rbp+var_10]
0x140031685  mov     [rax], rcx
0x140031688  mov     [rdx], rax
0x14003168b  mov     [rbp+var_8], rax
0x14003168f  inc     dword ptr [r13+1Ch]
0x140031693  inc     [rbp+arg_20]
0x140031696  jmp     short loc_140031704
0x140031698  mov     rdx, [rbp+var_8]
0x14003169c  lea     rax, [rbp+var_10]
0x1400316a0  cmp     [rdx], rax
0x1400316a3  jnz     loc_1400318A5
0x1400316a9  lea     rax, [r13+0F0h]
0x1400316b0  mov     [rbp+arg_8], r13
0x1400316b4  mov     [rax+8], rdx
0x1400316b8  lea     rcx, [rbp+var_10]
0x1400316bc  mov     [rax], rcx
0x1400316bf  mov     [rdx], rax
0x1400316c2  mov     [rbp+var_8], rax
0x1400316c6  inc     dword ptr [r13+1Ch]
0x1400316ca  inc     [rbp+arg_20]
0x1400316cd  jmp     loc_140031767
0x1400316d2  lea     rcx, [r13+2E0h]; SpinLock
0x1400316d9  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400316e0  nop     dword ptr [rax+rax+00h]
0x1400316e5  cmp     dword ptr [r13+14h], 2
0x1400316ea  jnz     short loc_140031704
0x1400316ec  cmp     byte ptr [r13+0C8h], 0
0x1400316f4  jz      short loc_140031704
0x1400316f6  cmp     byte ptr [r13+0C9h], 0
0x1400316fe  jnz     loc_140031661
0x140031704  lea     rcx, [r13+2E0h]; SpinLock
0x14003170b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140031712  nop     dword ptr [rax+rax+00h]
0x140031717  mov     rax, [r13+0]
0x14003171b  lea     rcx, [r15+30h]
0x14003171f  mov     r13, rax
0x140031722  cmp     rax, rcx
0x140031725  jnz     short loc_14003172A
0x140031727  mov     r13, [rcx]
0x14003172a  cmp     r13, [rbp+arg_10]
0x14003172e  jnz     short loc_1400316D2
0x140031730  jmp     loc_1400314F7
0x140031735  lea     rcx, [r13+2E0h]; SpinLock
0x14003173c  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140031743  nop     dword ptr [rax+rax+00h]
0x140031748  cmp     dword ptr [r13+14h], 2
0x14003174d  jnz     short loc_140031767
0x14003174f  cmp     byte ptr [r13+0C8h], 0
0x140031757  jz      short loc_140031767
0x140031759  cmp     dword ptr [r13+0CCh], 0
0x140031761  jnz     loc_140031698
0x140031767  lea     rcx, [r13+2E0h]; SpinLock
0x14003176e  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140031775  nop     dword ptr [rax+rax+00h]
0x14003177a  mov     rax, [r13+0]
0x14003177e  lea     rcx, [r15+30h]
0x140031782  mov     r13, rax
0x140031785  cmp     rax, rcx
0x140031788  jnz     short loc_14003178D
0x14003178a  mov     r13, [rcx]
0x14003178d  cmp     r13, [rbp+arg_10]
0x140031791  jnz     short loc_140031735
0x140031793  jmp     loc_1400314F7
0x140031798  or      dword ptr [r13+2Ch], 8
0x14003179d  lea     r9, [rbp+var_10]
0x1400317a1  inc     dword ptr [r15+18h]
0x1400317a5  mov     r8, rdx
0x1400317a8  inc     dword ptr [r15+0A8h]
0x1400317af  mov     rdx, rbx
0x1400317b2  lock dec dword ptr [r13+28h]
0x1400317b7  mov     rcx, r15
0x1400317ba  mov     [rsp+40h+var_18], esi
0x1400317be  call    FramePacketFast
  ... truncated ...
```
