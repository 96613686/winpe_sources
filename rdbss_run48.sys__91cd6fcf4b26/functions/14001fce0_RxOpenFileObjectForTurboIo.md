# RxOpenFileObjectForTurboIo

- ea: `0x14001fce0`
- end: `0x14001feb6`
- name: `RxOpenFileObjectForTurboIo`
- size: `470`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14001b178`
- `0x14001fce0`
- `0x1400202f8`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14001fdeb`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14001fdeb`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001fd17`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001fd17`

## pseudocode

```c
__int64 __fastcall RxOpenFileObjectForTurboIo(signed __int64 a1, __int64 a2, struct _SLIST_ENTRY *a3)
{
  unsigned int v3; // edi
  __int64 v7; // rbx
  PSLIST_ENTRY v8; // rbx
  int v9; // r8d

  v3 = 0;
  v7 = *(_QWORD *)(*(_QWORD *)(a2 + 304) + 328LL);
  if ( v7 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)v7, a1, 0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qqZ(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)&WPP_d414fc76462934e262300deaf9706329_Traceguids,
          a2,
          a1,
          a1 + 88);
      }
      return (unsigned int)-1073740761;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqqZ(WPP_GLOBAL_Control->AttachedDevice, 14, (_DWORD)a3, a1, a2, v7, a1 + 88);
    }
    *(_QWORD *)(v7 + 16) = a3;
    *(_BYTE *)(v7 + 24) = 0;
    *(_DWORD *)(v7 + 28) = 0;
  }
  else
  {
    v8 = ExpInterlockedPopEntrySList(&TurboIoEntryFreeList);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqZ(WPP_GLOBAL_Control->AttachedDevice, 12, v9, a1, a2, (char)v8, a1 + 88);
      }
      v8->Next = (struct _SLIST_ENTRY *)a1;
      *((_BYTE *)&v8[1].Next + 8) = 0;
      *((_DWORD *)&v8[1].Next + 3) = 0;
      v8[1].Next = a3;
      if ( _InterlockedCompareExchange64(
             (volatile signed __int64 *)(*(_QWORD *)(a2 + 304) + 328LL),
             (signed __int64)v8,
             0) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qqZ(
            WPP_GLOBAL_Control->AttachedDevice,
            13,
            (unsigned int)&WPP_d414fc76462934e262300deaf9706329_Traceguids,
            a1,
            a2,
            a1 + 88);
        }
        v8->Next = 0;
        v8[1].Next = 0;
        ExpInterlockedPushEntrySList(&TurboIoEntryFreeList, v8);
        return (unsigned int)-1073740761;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14001fce0  push    rbx
0x14001fce2  push    rsi
0x14001fce3  push    rdi
0x14001fce4  push    r12
0x14001fce6  push    r14
0x14001fce8  push    r15
0x14001fcea  sub     rsp, 48h
0x14001fcee  mov     rax, [rdx+130h]
0x14001fcf5  xor     edi, edi
0x14001fcf7  mov     r12, r8
0x14001fcfa  mov     r15, rdx
0x14001fcfd  mov     rsi, rcx
0x14001fd00  mov     rbx, [rax+148h]
0x14001fd07  test    rbx, rbx
0x14001fd0a  jnz     loc_14001FDFC
0x14001fd10  lea     rcx, TurboIoEntryFreeList; ListHead
0x14001fd17  call    cs:__imp_ExpInterlockedPopEntrySList
0x14001fd1e  nop     dword ptr [rax+rax+00h]
0x14001fd23  mov     rbx, rax
0x14001fd26  test    rax, rax
0x14001fd29  jz      loc_14001FEA5
0x14001fd2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fd36  lea     r14, WPP_GLOBAL_Control
0x14001fd3d  cmp     rcx, r14
0x14001fd40  jz      short loc_14001FD73
0x14001fd42  test    dword ptr [rcx+2Ch], 4000h
0x14001fd49  jz      short loc_14001FD73
0x14001fd4b  cmp     byte ptr [rcx+29h], 2
0x14001fd4f  jb      short loc_14001FD73
0x14001fd51  mov     rcx, [rcx+18h]
0x14001fd55  lea     rax, [rsi+58h]
0x14001fd59  mov     [rsp+78h+var_48], rax
0x14001fd5e  lea     edx, [rdi+0Ch]
0x14001fd61  mov     [rsp+78h+var_50], rbx
0x14001fd66  mov     r9, rsi
0x14001fd69  mov     [rsp+78h+var_58], r15
0x14001fd6e  call    WPP_SF_qqqZ
0x14001fd73  mov     [rbx], rsi
0x14001fd76  xor     eax, eax
0x14001fd78  mov     [rbx+18h], dil
0x14001fd7c  mov     [rbx+1Ch], edi
0x14001fd7f  mov     [rbx+10h], r12
0x14001fd83  mov     rcx, [r15+130h]
0x14001fd8a  lock cmpxchg [rcx+148h], rbx
0x14001fd93  jz      loc_14001FEA5
0x14001fd99  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fda0  cmp     rcx, r14
0x14001fda3  jz      short loc_14001FDDA
0x14001fda5  test    dword ptr [rcx+2Ch], 4000h
0x14001fdac  jz      short loc_14001FDDA
0x14001fdae  cmp     byte ptr [rcx+29h], 1
0x14001fdb2  jb      short loc_14001FDDA
0x14001fdb4  mov     rcx, [rcx+18h]
0x14001fdb8  lea     rax, [rsi+58h]
0x14001fdbc  mov     [rsp+78h+var_50], rax
0x14001fdc1  lea     r8, WPP_d414fc76462934e262300deaf9706329_Traceguids
0x14001fdc8  mov     edx, 0Dh
0x14001fdcd  mov     [rsp+78h+var_58], r15
0x14001fdd2  mov     r9, rsi
0x14001fdd5  call    WPP_SF_qqZ
0x14001fdda  mov     rdx, rbx; ListEntry
0x14001fddd  mov     [rbx], rdi
0x14001fde0  lea     rcx, TurboIoEntryFreeList; ListHead
0x14001fde7  mov     [rbx+10h], rdi
0x14001fdeb  call    cs:__imp_ExpInterlockedPushEntrySList
0x14001fdf2  nop     dword ptr [rax+rax+00h]
0x14001fdf7  jmp     loc_14001FEA0
0x14001fdfc  xor     eax, eax
0x14001fdfe  lock cmpxchg [rbx], rsi
0x14001fe03  jnz     short loc_14001FE58
0x14001fe05  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fe0c  lea     r14, WPP_GLOBAL_Control
0x14001fe13  cmp     rcx, r14
0x14001fe16  jz      short loc_14001FE4B
0x14001fe18  test    dword ptr [rcx+2Ch], 4000h
0x14001fe1f  jz      short loc_14001FE4B
0x14001fe21  cmp     byte ptr [rcx+29h], 2
0x14001fe25  jb      short loc_14001FE4B
0x14001fe27  mov     rcx, [rcx+18h]
0x14001fe2b  lea     rax, [rsi+58h]
0x14001fe2f  mov     [rsp+78h+var_48], rax
0x14001fe34  mov     edx, 0Eh
0x14001fe39  mov     [rsp+78h+var_50], rbx
0x14001fe3e  mov     r9, rsi
0x14001fe41  mov     [rsp+78h+var_58], r15
0x14001fe46  call    WPP_SF_qqqZ
0x14001fe4b  mov     [rbx+10h], r12
0x14001fe4f  mov     [rbx+18h], dil
0x14001fe53  mov     [rbx+1Ch], edi
0x14001fe56  jmp     short loc_14001FEA5
0x14001fe58  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fe5f  lea     r14, WPP_GLOBAL_Control
0x14001fe66  cmp     rcx, r14
0x14001fe69  jz      short loc_14001FEA0
0x14001fe6b  test    dword ptr [rcx+2Ch], 4000h
0x14001fe72  jz      short loc_14001FEA0
0x14001fe74  cmp     byte ptr [rcx+29h], 1
0x14001fe78  jb      short loc_14001FEA0
0x14001fe7a  mov     rcx, [rcx+18h]
0x14001fe7e  lea     rax, [rsi+58h]
0x14001fe82  mov     [rsp+78h+var_50], rax
0x14001fe87  lea     r8, WPP_d414fc76462934e262300deaf9706329_Traceguids
0x14001fe8e  mov     edx, 0Fh
0x14001fe93  mov     [rsp+78h+var_58], rsi
0x14001fe98  mov     r9, r15
0x14001fe9b  call    WPP_SF_qqZ
0x14001fea0  mov     edi, 0C0000427h
0x14001fea5  mov     eax, edi
0x14001fea7  add     rsp, 48h
0x14001feab  pop     r15
0x14001fead  pop     r14
0x14001feaf  pop     r12
0x14001feb1  pop     rdi
0x14001feb2  pop     rsi
0x14001feb3  pop     rbx
0x14001feb4  retn
```
