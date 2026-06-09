# NatLogConnectionCreation

- ea: `0x1400101b8`
- end: `0x1400103fb`
- name: `NatLogConnectionCreation`
- size: `579`
- prototype: `void __fastcall(unsigned int, unsigned int, __int16, __int16, char, char)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000d8b0`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x1400101b8`
- `0x14002c6d0`
- `0x14002cbc0`

## import_xrefs

- `ntoskrnl!IoWMIWriteEvent` at `0x140010324`
- `ntoskrnl!IoWMIWriteEvent` at `0x140010324`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400102a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400102a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001028c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001028c`

## pseudocode

```c
void __fastcall NatLogConnectionCreation(unsigned int a1, unsigned int a2, __int16 a3, __int16 a4, char a5, char a6)
{
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  KIRQL v12; // al
  __int64 v13; // rbx
  NTSTATUS v14; // eax
  _QWORD WnodeEventItem[8]; // [rsp+20h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
  }
  if ( (_DWORD)NatWmiEnabledEvents )
  {
    v12 = KeAcquireSpinLockRaiseToDpc(&NatWmiLock);
    v13 = NatWmiLogHandles;
    KeReleaseSpinLock(&NatWmiLock, v12);
    if ( v13 )
    {
      memset(WnodeEventItem, 0, sizeof(WnodeEventItem));
      LOWORD(WnodeEventItem[0]) = 64;
      WnodeEventItem[3] = ConnectionCreationEventGuid;
      HIDWORD(WnodeEventItem[0]) = 0;
      HIDWORD(WnodeEventItem[5]) = 655872;
      WnodeEventItem[1] = v13;
      WnodeEventItem[2] = MEMORY[0xFFFFF78000000014];
      BYTE4(WnodeEventItem[7]) = a5;
      BYTE5(WnodeEventItem[7]) = a6;
      WnodeEventItem[6] = __PAIR64__(a2, a1);
      LOWORD(WnodeEventItem[7]) = a3;
      WORD1(WnodeEventItem[7]) = a4;
      v14 = IoWMIWriteEvent(WnodeEventItem);
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids,
            (unsigned int)v14);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v11 = 25;
      goto LABEL_28;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v11 = 22;
LABEL_28:
      WPP_SF_(v10->AttachedDevice, v11, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x1400101b8  push    rbp
0x1400101ba  push    rbx
0x1400101bb  push    rsi
0x1400101bc  push    rdi
0x1400101bd  push    r12
0x1400101bf  push    r14
0x1400101c1  push    r15
0x1400101c3  mov     rbp, rsp
0x1400101c6  sub     rsp, 70h
0x1400101ca  mov     rax, cs:__security_cookie
0x1400101d1  xor     rax, rsp
0x1400101d4  mov     [rbp+var_10], rax
0x1400101d8  movzx   edi, r9w
0x1400101dc  movzx   esi, r8w
0x1400101e0  mov     r14d, edx
0x1400101e3  mov     r15d, ecx
0x1400101e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400101ed  lea     rbx, WPP_GLOBAL_Control
0x1400101f4  cmp     rcx, rbx
0x1400101f7  jz      short loc_14001021B
0x1400101f9  mov     eax, [rcx+2Ch]
0x1400101fc  test    al, 1
0x1400101fe  jz      short loc_14001021B
0x140010200  cmp     byte ptr [rcx+29h], 6
0x140010204  jb      short loc_14001021B
0x140010206  mov     rcx, [rcx+18h]
0x14001020a  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140010211  mov     edx, 14h
0x140010216  call    WPP_SF_
0x14001021b  cmp     dword ptr cs:NatWmiEnabledEvents, 0
0x140010222  jnz     short loc_140010285
0x140010224  mov     rcx, cs:WPP_GLOBAL_Control
0x14001022b  cmp     rcx, rbx
0x14001022e  jz      loc_1400103DF
0x140010234  mov     eax, [rcx+2Ch]
0x140010237  test    al, 1
0x140010239  jz      short loc_140010256
0x14001023b  cmp     byte ptr [rcx+29h], 2
0x14001023f  jb      short loc_140010256
0x140010241  mov     rcx, [rcx+18h]
0x140010245  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x14001024c  mov     edx, 15h
0x140010251  call    WPP_SF_
0x140010256  mov     rcx, cs:WPP_GLOBAL_Control
0x14001025d  cmp     rcx, rbx
0x140010260  jz      loc_1400103DF
0x140010266  mov     eax, [rcx+2Ch]
0x140010269  test    al, 1
0x14001026b  jz      loc_1400103DF
0x140010271  cmp     byte ptr [rcx+29h], 6
0x140010275  jb      loc_1400103DF
0x14001027b  mov     edx, 16h
0x140010280  jmp     loc_1400103CF
0x140010285  lea     rcx, NatWmiLock; SpinLock
0x14001028c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010293  nop     dword ptr [rax+rax+00h]
0x140010298  mov     rbx, qword ptr cs:NatWmiLogHandles
0x14001029f  lea     rcx, NatWmiLock; SpinLock
0x1400102a6  mov     dl, al; NewIrql
0x1400102a8  call    cs:__imp_KeReleaseSpinLock
0x1400102af  nop     dword ptr [rax+rax+00h]
0x1400102b4  test    rbx, rbx
0x1400102b7  jz      loc_140010373
0x1400102bd  mov     r12d, 40h ; '@'
0x1400102c3  lea     rcx, [rbp+WnodeEventItem]; void *
0x1400102c7  mov     r8d, r12d; Size
0x1400102ca  xor     edx, edx; Val
0x1400102cc  call    memset
0x1400102d1  lea     rax, ConnectionCreationEventGuid
0x1400102d8  mov     [rbp+WnodeEventItem], r12w
0x1400102dd  mov     [rbp+var_38], rax
0x1400102e1  lea     rcx, [rbp+WnodeEventItem]; WnodeEventItem
0x1400102e5  mov     [rbp+var_4C], 0
0x1400102ec  mov     rax, 0FFFFF78000000014h
0x1400102f6  mov     [rbp+var_24], 0A0200h
0x1400102fd  mov     [rbp+var_48], rbx
0x140010301  mov     rax, [rax]
0x140010304  mov     [rbp+var_40], rax
0x140010308  mov     al, [rbp+arg_20]
0x14001030b  mov     [rbp+var_14], al
0x14001030e  mov     al, [rbp+arg_28]
0x140010311  mov     [rbp+var_13], al
0x140010314  mov     [rbp+var_20], r15d
0x140010318  mov     [rbp+var_1C], r14d
0x14001031c  mov     [rbp+var_18], si
0x140010320  mov     [rbp+var_16], di
0x140010324  call    cs:__imp_IoWMIWriteEvent
0x14001032b  nop     dword ptr [rax+rax+00h]
0x140010330  test    eax, eax
0x140010332  jns     short loc_1400103AA
0x140010334  mov     rcx, cs:WPP_GLOBAL_Control
0x14001033b  lea     rbx, WPP_GLOBAL_Control
0x140010342  cmp     rcx, rbx
0x140010345  jz      loc_1400103DF
0x14001034b  mov     edx, [rcx+2Ch]
0x14001034e  test    dl, 1
0x140010351  jz      short loc_1400103B1
0x140010353  cmp     byte ptr [rcx+29h], 2
0x140010357  jb      short loc_1400103B1
0x140010359  mov     rcx, [rcx+18h]
0x14001035d  lea     edx, [r12-29h]
0x140010362  mov     r9d, eax
0x140010365  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x14001036c  call    WPP_SF_d
0x140010371  jmp     short loc_1400103B1
0x140010373  mov     rcx, cs:WPP_GLOBAL_Control
0x14001037a  lea     rbx, WPP_GLOBAL_Control
0x140010381  cmp     rcx, rbx
0x140010384  jz      short loc_1400103DF
0x140010386  mov     eax, [rcx+2Ch]
0x140010389  test    al, 1
0x14001038b  jz      short loc_1400103B1
0x14001038d  cmp     byte ptr [rcx+29h], 2
0x140010391  jb      short loc_1400103B1
0x140010393  mov     rcx, [rcx+18h]
0x140010397  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x14001039e  mov     edx, 18h
0x1400103a3  call    WPP_SF_
0x1400103a8  jmp     short loc_1400103B1
0x1400103aa  lea     rbx, WPP_GLOBAL_Control
0x1400103b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400103b8  cmp     rcx, rbx
0x1400103bb  jz      short loc_1400103DF
0x1400103bd  mov     eax, [rcx+2Ch]
0x1400103c0  test    al, 1
0x1400103c2  jz      short loc_1400103DF
0x1400103c4  cmp     byte ptr [rcx+29h], 6
0x1400103c8  jb      short loc_1400103DF
0x1400103ca  mov     edx, 19h
0x1400103cf  mov     rcx, [rcx+18h]
0x1400103d3  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x1400103da  call    WPP_SF_
0x1400103df  mov     rcx, [rbp+var_10]
0x1400103e3  xor     rcx, rsp; StackCookie
0x1400103e6  call    __security_check_cookie
0x1400103eb  add     rsp, 70h
0x1400103ef  pop     r15
0x1400103f1  pop     r14
0x1400103f3  pop     r12
0x1400103f5  pop     rdi
0x1400103f6  pop     rsi
0x1400103f7  pop     rbx
0x1400103f8  pop     rbp
0x1400103f9  retn
```
