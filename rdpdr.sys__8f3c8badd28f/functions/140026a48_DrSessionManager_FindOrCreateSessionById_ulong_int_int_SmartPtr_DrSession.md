# DrSessionManager::FindOrCreateSessionById(ulong,int,int *,SmartPtr<DrSession> &)

- ea: `0x140026a48`
- end: `0x140026c0f`
- name: `?FindOrCreateSessionById@DrSessionManager@@QEAAJKHPEAHAEAV?$SmartPtr@VDrSession@@@@@Z`
- size: `455`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x14001d9d4`
- `0x140025c40`
- `0x140026380`

## callees

- `0x140001830`
- `0x140001c50`
- `0x140001e60`
- `0x140001ef0`
- `0x140002260`
- `0x14000324c`
- `0x140003940`
- `0x140005448`
- `0x14001ba10`
- `0x14001d938`
- `0x140026a48`
- `0x14002cca8`

## pseudocode

```c
__int64 __fastcall DrSessionManager::FindOrCreateSessionById(
        __int64 a1,
        unsigned int a2,
        int a3,
        _DWORD *a4,
        DrSession **a5)
{
  DoubleList *v5; // r15
  unsigned int v7; // ebx
  struct ListEntry *i; // rax
  unsigned __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rsi
  DrSession *v15; // rax
  __int64 v16; // r8
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx

  v5 = (DoubleList *)(a1 + 16);
  v7 = 0;
  *a4 = 0;
  DoubleList::LockExclusive((DoubleList *)(a1 + 16));
  for ( i = DoubleList::First(v5); i; i = DoubleList::Next(v5, i) )
  {
    v14 = *((_QWORD *)i + 2);
    if ( *(_DWORD *)(v14 + 1128) == a2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 16, v13, a2, v14);
      SmartPtr<VirtualChannel>::operator=(a5, v14);
      *a4 = 1;
      break;
    }
  }
  if ( !*a4 && a3 )
  {
    v15 = (DrSession *)TopObj::operator new(0x600u, v12);
    if ( v15 )
      v15 = DrSession::DrSession(v15);
    SmartPtr<VirtualChannel>::operator=(a5, v15);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 17, v16, a2, *a5);
    if ( !*a5 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_9f7dd5792741379be231a7352ecacb15_Traceguids);
      v7 = -1073741801;
      goto LABEL_31;
    }
    if ( (unsigned int)DrSession::Initialize(*a5) )
    {
      *((_DWORD *)*a5 + 282) = a2;
      if ( (unsigned int)DrSessionManager::AddSession(a1, a5) )
        goto LABEL_31;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
LABEL_30:
        SmartPtr<VirtualChannel>::operator=(a5, 0);
        v7 = -1073741823;
        goto LABEL_31;
      }
      v18 = 20;
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_30;
      v18 = 19;
    }
    WPP_SF_(v17->AttachedDevice, v18, WPP_9f7dd5792741379be231a7352ecacb15_Traceguids);
    goto LABEL_30;
  }
LABEL_31:
  DoubleList::Unlock(v5);
  return v7;
}

```

## disassembly

```asm
0x140026a48  push    rbx
0x140026a4a  push    rbp
0x140026a4b  push    rsi
0x140026a4c  push    rdi
0x140026a4d  push    r12
0x140026a4f  push    r13
0x140026a51  push    r14
0x140026a53  push    r15
0x140026a55  sub     rsp, 38h
0x140026a59  lea     r15, [rcx+10h]
0x140026a5d  mov     r13, rcx
0x140026a60  xor     ebx, ebx
0x140026a62  mov     rcx, r15; this
0x140026a65  mov     r14, r9
0x140026a68  mov     [r9], ebx
0x140026a6b  mov     r12d, r8d
0x140026a6e  mov     ebp, edx
0x140026a70  call    ?LockExclusive@DoubleList@@QEAAXXZ; DoubleList::LockExclusive(void)
0x140026a75  mov     rcx, r15; this
0x140026a78  call    ?First@DoubleList@@QEAAPEAVListEntry@@XZ; DoubleList::First(void)
0x140026a7d  mov     rdi, [rsp+78h+arg_20]
0x140026a85  lea     rsi, WPP_GLOBAL_Control
0x140026a8c  test    rax, rax
0x140026a8f  jz      short loc_140026AF2
0x140026a91  mov     rsi, [rax+10h]
0x140026a95  cmp     [rsi+468h], ebp
0x140026a9b  jz      short loc_140026AAA
0x140026a9d  mov     rdx, rax; struct ListEntry *
0x140026aa0  mov     rcx, r15; this
0x140026aa3  call    ?Next@DoubleList@@QEAAPEAVListEntry@@PEAV2@@Z; DoubleList::Next(ListEntry *)
0x140026aa8  jmp     short loc_140026A7D
0x140026aaa  mov     rcx, cs:WPP_GLOBAL_Control
0x140026ab1  lea     rax, WPP_GLOBAL_Control
0x140026ab8  cmp     rcx, rax
0x140026abb  jz      short loc_140026AD9
0x140026abd  cmp     byte ptr [rcx+29h], 4
0x140026ac1  jb      short loc_140026AD9
0x140026ac3  mov     rcx, [rcx+18h]
0x140026ac7  mov     edx, 10h
0x140026acc  mov     r9d, ebp
0x140026acf  mov     [rsp+78h+var_58], rsi
0x140026ad4  call    WPP_SF_dq
0x140026ad9  mov     rdx, rsi
0x140026adc  mov     rcx, rdi
0x140026adf  call    ??4?$SmartPtr@VVirtualChannel@@@@QEAAAEAV0@PEAVVirtualChannel@@@Z; SmartPtr<VirtualChannel>::operator=(VirtualChannel *)
0x140026ae4  mov     dword ptr [r14], 1
0x140026aeb  lea     rsi, WPP_GLOBAL_Control
0x140026af2  cmp     [r14], ebx
0x140026af5  jnz     loc_140026BF3
0x140026afb  test    r12d, r12d
0x140026afe  jz      loc_140026BF3
0x140026b04  mov     ecx, 600h; unsigned __int64
0x140026b09  call    ??2TopObj@@SAPEAX_K0@Z; TopObj::operator new(unsigned __int64,unsigned __int64)
0x140026b0e  test    rax, rax
0x140026b11  jz      short loc_140026B1B
0x140026b13  mov     rcx, rax; this
0x140026b16  call    ??0DrSession@@QEAA@XZ; DrSession::DrSession(void)
0x140026b1b  mov     rdx, rax
0x140026b1e  mov     rcx, rdi
0x140026b21  call    ??4?$SmartPtr@VVirtualChannel@@@@QEAAAEAV0@PEAVVirtualChannel@@@Z; SmartPtr<VirtualChannel>::operator=(VirtualChannel *)
0x140026b26  mov     rcx, cs:WPP_GLOBAL_Control
0x140026b2d  cmp     rcx, rsi
0x140026b30  jz      short loc_140026B51
0x140026b32  cmp     byte ptr [rcx+29h], 4
0x140026b36  jb      short loc_140026B51
0x140026b38  mov     rax, [rdi]
0x140026b3b  mov     edx, 11h
0x140026b40  mov     rcx, [rcx+18h]
0x140026b44  mov     r9d, ebp
0x140026b47  mov     [rsp+78h+var_58], rax
0x140026b4c  call    WPP_SF_dq
0x140026b51  mov     rcx, [rdi]; this
0x140026b54  test    rcx, rcx
0x140026b57  jnz     short loc_140026B87
0x140026b59  mov     rcx, cs:WPP_GLOBAL_Control
0x140026b60  cmp     rcx, rsi
0x140026b63  jz      short loc_140026B80
0x140026b65  cmp     byte ptr [rcx+29h], 2
0x140026b69  jb      short loc_140026B80
0x140026b6b  mov     rcx, [rcx+18h]
0x140026b6f  lea     r8, WPP_9f7dd5792741379be231a7352ecacb15_Traceguids
0x140026b76  mov     edx, 12h
0x140026b7b  call    WPP_SF_
0x140026b80  mov     ebx, 0C0000017h
0x140026b85  jmp     short loc_140026BF3
0x140026b87  call    ?Initialize@DrSession@@QEAAHXZ; DrSession::Initialize(void)
0x140026b8c  test    eax, eax
0x140026b8e  jnz     short loc_140026BA7
0x140026b90  mov     rcx, cs:WPP_GLOBAL_Control
0x140026b97  cmp     rcx, rsi
0x140026b9a  jz      short loc_140026BE4
0x140026b9c  cmp     byte ptr [rcx+29h], 2
0x140026ba0  jb      short loc_140026BE4
0x140026ba2  lea     edx, [rax+13h]
0x140026ba5  jmp     short loc_140026BD4
0x140026ba7  mov     rax, [rdi]
0x140026baa  mov     rdx, rdi
0x140026bad  mov     rcx, r13
0x140026bb0  mov     [rax+468h], ebp
0x140026bb6  call    ?AddSession@DrSessionManager@@QEAAHAEAV?$SmartPtr@VDrSession@@@@@Z; DrSessionManager::AddSession(SmartPtr<DrSession> &)
0x140026bbb  test    eax, eax
0x140026bbd  jnz     short loc_140026BF3
0x140026bbf  mov     rcx, cs:WPP_GLOBAL_Control
0x140026bc6  cmp     rcx, rsi
0x140026bc9  jz      short loc_140026BE4
0x140026bcb  cmp     byte ptr [rcx+29h], 2
0x140026bcf  jb      short loc_140026BE4
0x140026bd1  lea     edx, [rax+14h]
0x140026bd4  mov     rcx, [rcx+18h]
0x140026bd8  lea     r8, WPP_9f7dd5792741379be231a7352ecacb15_Traceguids
0x140026bdf  call    WPP_SF_
0x140026be4  xor     edx, edx
0x140026be6  mov     rcx, rdi
0x140026be9  call    ??4?$SmartPtr@VVirtualChannel@@@@QEAAAEAV0@PEAVVirtualChannel@@@Z; SmartPtr<VirtualChannel>::operator=(VirtualChannel *)
0x140026bee  mov     ebx, 0C0000001h
0x140026bf3  mov     rcx, r15; this
0x140026bf6  call    ?Unlock@DoubleList@@QEAAXXZ; DoubleList::Unlock(void)
0x140026bfb  mov     eax, ebx
0x140026bfd  add     rsp, 38h
0x140026c01  pop     r15
0x140026c03  pop     r14
0x140026c05  pop     r13
0x140026c07  pop     r12
0x140026c09  pop     rdi
0x140026c0a  pop     rsi
0x140026c0b  pop     rbp
0x140026c0c  pop     rbx
0x140026c0d  retn
```
