# CancelAllPingPongIrps

- ea: `0x180013500`
- end: `0x180013859`
- name: `CancelAllPingPongIrps`
- size: `857`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180013428`
- `0x180015b98`
- `0x180019694`
- `0x18003f2b4`

## callees

- `0x180009a78`
- `0x180013500`
- `0x180018978`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x180013725`
- `ntoskrnl!KeSetEvent` at `0x18001373d`
- `ntoskrnl!KeSetEvent` at `0x180013725`
- `ntoskrnl!KeSetEvent` at `0x18001373d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800135e9`
- `ntoskrnl!KeWaitForSingleObject` at `0x180013696`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800135e9`
- `ntoskrnl!KeWaitForSingleObject` at `0x180013696`
- `ntoskrnl!KeCancelTimer` at `0x180013544`
- `ntoskrnl!KeCancelTimer` at `0x180013544`
- `ntoskrnl!IoCancelIrp` at `0x1800135fa`
- `ntoskrnl!IoCancelIrp` at `0x1800135fa`

## pseudocode

```c
void __fastcall CancelAllPingPongIrps(__int64 a1)
{
  unsigned int v2; // esi
  __int64 v3; // r14
  __int64 v4; // rbp
  unsigned int v5; // eax
  unsigned int v6; // esi
  __int64 v7; // r14
  PDEVICE_OBJECT *v8; // rdx
  __int64 v9; // rbp
  _UNKNOWN **v10; // r8
  BOOLEAN v11; // al
  int v12; // edx
  int v13; // r8d
  unsigned int v14; // eax
  unsigned int v15; // esi
  __int64 v16; // r14
  __int64 v17; // rbp
  int v18; // edx
  int v19; // r8d

  v2 = 0;
  if ( *(_DWORD *)(a1 + 232) )
  {
    do
    {
      v3 = *(_QWORD *)(a1 + 240);
      v4 = 224LL * v2;
      _InterlockedAdd((volatile signed __int32 *)(v3 + v4 + 24), 1u);
      if ( KeCancelTimer((PKTIMER)(v4 + v3 + 88)) == 1 )
      {
        KeSetEvent((PRKEVENT)(v4 + v3 + 32), 0, 0);
        KeSetEvent((PRKEVENT)(v4 + v3 + 56), 0, 0);
      }
      v5 = *(_DWORD *)(a1 + 232);
      ++v2;
    }
    while ( v2 < v5 );
    v6 = 0;
    if ( v5 )
    {
      do
      {
        v7 = *(_QWORD *)(a1 + 240);
        v8 = &WPP_GLOBAL_Control;
        v9 = 224LL * v6;
        v10 = &WPP_RECORDER_INITIALIZED;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
          || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
        {
          LOBYTE(v8) = 0;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          || (LOBYTE(v10) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v10) = 0;
        }
        if ( (_BYTE)v8 || (_BYTE)v10 )
          WPP_RECORDER_AND_TRACE_SF_qq(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)v8,
            (_DWORD)v10,
            *(_QWORD *)(a1 + 688),
            5,
            5,
            38,
            (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
            *(_QWORD *)a1,
            *(_QWORD *)(v7 + v9 + 8));
        KeWaitForSingleObject((PVOID)(v9 + v7 + 32), Executive, 0, 0, 0);
        v11 = IoCancelIrp(*(PIRP *)(v7 + v9 + 8));
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
          || (LOBYTE(v12) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
        {
          LOBYTE(v12) = 0;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          || (LOBYTE(v13) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v13) = 0;
        }
        if ( (_BYTE)v12 || (_BYTE)v13 )
          WPP_RECORDER_AND_TRACE_SF_qdq(
            WPP_GLOBAL_Control->AttachedDevice,
            v12,
            v13,
            *(_QWORD *)(a1 + 688),
            5,
            5,
            39,
            (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
            *(_QWORD *)a1,
            v11,
            *(_QWORD *)(v7 + v9 + 8));
        v14 = *(_DWORD *)(a1 + 232);
        ++v6;
      }
      while ( v6 < v14 );
      v15 = 0;
      if ( v14 )
      {
        do
        {
          v16 = *(_QWORD *)(a1 + 240);
          v17 = 224LL * v15;
          KeWaitForSingleObject((PVOID)(v17 + v16 + 56), Executive, 0, 0, 0);
          _InterlockedDecrement((volatile signed __int32 *)(v16 + v17 + 24));
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
            || (LOBYTE(v18) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
          {
            LOBYTE(v18) = 0;
          }
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            || (LOBYTE(v19) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            LOBYTE(v19) = 0;
          }
          if ( (_BYTE)v18 || (_BYTE)v19 )
            WPP_RECORDER_AND_TRACE_SF_qq(
              WPP_GLOBAL_Control->AttachedDevice,
              v18,
              v19,
              *(_QWORD *)(a1 + 688),
              5,
              5,
              40,
              (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
              *(_QWORD *)a1,
              *(_QWORD *)(v16 + v17 + 8));
          ++v15;
        }
        while ( v15 < *(_DWORD *)(a1 + 232) );
      }
    }
  }
  _InterlockedExchange((volatile __int32 *)(a1 + 280), 1);
}

```

## disassembly

```asm
0x180013500  push    rbx
0x180013502  push    rbp
0x180013503  push    rsi
0x180013504  push    rdi
0x180013505  push    r14
0x180013507  push    r15
0x180013509  sub     rsp, 68h
0x18001350d  xor     r15d, r15d
0x180013510  mov     rdi, rcx
0x180013513  mov     esi, r15d
0x180013516  lea     ebx, [r15+1]
0x18001351a  cmp     [rcx+0E8h], r15d
0x180013521  jbe     loc_180013705
0x180013527  mov     r14, [rdi+0F0h]
0x18001352e  mov     eax, esi
0x180013530  imul    rbp, rax, 0E0h
0x180013537  lock add [r14+rbp+18h], ebx
0x18001353d  lea     rcx, [r14+58h]
0x180013541  add     rcx, rbp; PKTIMER
0x180013544  call    cs:__imp_KeCancelTimer
0x18001354b  nop     dword ptr [rax+rax+00h]
0x180013550  cmp     al, bl
0x180013552  jz      loc_180013719
0x180013558  mov     eax, [rdi+0E8h]
0x18001355e  add     esi, ebx
0x180013560  cmp     esi, eax
0x180013562  jb      short loc_180013527
0x180013564  mov     esi, r15d
0x180013567  test    eax, eax
0x180013569  jz      loc_180013705
0x18001356f  mov     r14, [rdi+0F0h]
0x180013576  lea     r10, WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids
0x18001357d  mov     eax, esi
0x18001357f  lea     rdx, WPP_GLOBAL_Control
0x180013586  imul    rbp, rax, 0E0h
0x18001358d  lea     r8, WPP_RECORDER_INITIALIZED
0x180013594  mov     rcx, cs:WPP_GLOBAL_Control
0x18001359b  cmp     rcx, rdx
0x18001359e  jz      short loc_1800135AB
0x1800135a0  mov     eax, [rcx+2Ch]
0x1800135a3  test    al, 10h
0x1800135a5  jnz     loc_18001374E
0x1800135ab  mov     dl, r15b
0x1800135ae  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x1800135b5  jz      short loc_1800135C1
0x1800135b7  mov     r8b, bl
0x1800135ba  cmp     [rcx+48h], r15w
0x1800135bf  jnz     short loc_1800135C4
0x1800135c1  mov     r8b, r15b
0x1800135c4  test    dl, dl
0x1800135c6  jnz     loc_18001375F
0x1800135cc  test    r8b, r8b
0x1800135cf  jnz     loc_18001375F
0x1800135d5  lea     rcx, [r14+20h]
0x1800135d9  mov     [rsp+98h+Timeout], r15; Timeout
0x1800135de  add     rcx, rbp; Object
0x1800135e1  xor     r9d, r9d; Alertable
0x1800135e4  xor     r8d, r8d; WaitMode
0x1800135e7  xor     edx, edx; WaitReason
0x1800135e9  call    cs:__imp_KeWaitForSingleObject
0x1800135f0  nop     dword ptr [rax+rax+00h]
0x1800135f5  mov     rcx, [r14+rbp+8]; Irp
0x1800135fa  call    cs:__imp_IoCancelIrp
0x180013601  nop     dword ptr [rax+rax+00h]
0x180013606  mov     r10, cs:WPP_GLOBAL_Control
0x18001360d  lea     rcx, WPP_GLOBAL_Control
0x180013614  cmp     r10, rcx
0x180013617  jz      short loc_180013626
0x180013619  mov     ecx, [r10+2Ch]
0x18001361d  test    cl, 10h
0x180013620  jnz     loc_18001379F
0x180013626  mov     dl, r15b
0x180013629  lea     rcx, WPP_RECORDER_INITIALIZED
0x180013630  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180013637  jz      short loc_180013643
0x180013639  mov     r8b, bl
0x18001363c  cmp     [r10+48h], r15w
0x180013641  jnz     short loc_180013646
0x180013643  mov     r8b, r15b
0x180013646  test    dl, dl
0x180013648  jnz     loc_1800137B1
0x18001364e  test    r8b, r8b
0x180013651  jnz     loc_1800137B1
0x180013657  mov     eax, [rdi+0E8h]
0x18001365d  add     esi, ebx
0x18001365f  cmp     esi, eax
0x180013661  jb      loc_18001356F
0x180013667  mov     esi, r15d
0x18001366a  test    eax, eax
0x18001366c  jz      loc_180013705
0x180013672  mov     r14, [rdi+0F0h]
0x180013679  xor     r9d, r9d; Alertable
0x18001367c  mov     eax, esi
0x18001367e  xor     r8d, r8d; WaitMode
0x180013681  imul    rbp, rax, 0E0h
0x180013688  xor     edx, edx; WaitReason
0x18001368a  mov     [rsp+98h+Timeout], r15; Timeout
0x18001368f  lea     rcx, [r14+38h]
0x180013693  add     rcx, rbp; Object
0x180013696  call    cs:__imp_KeWaitForSingleObject
0x18001369d  nop     dword ptr [rax+rax+00h]
0x1800136a2  lock dec dword ptr [r14+rbp+18h]
0x1800136a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136af  lea     rax, WPP_GLOBAL_Control
0x1800136b6  cmp     rcx, rax
0x1800136b9  jz      short loc_1800136C6
0x1800136bb  mov     eax, [rcx+2Ch]
0x1800136be  test    al, 10h
0x1800136c0  jnz     loc_180013801
0x1800136c6  mov     dl, r15b
0x1800136c9  lea     rax, WPP_RECORDER_INITIALIZED
0x1800136d0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800136d7  jz      short loc_1800136E3
0x1800136d9  mov     r8b, bl
0x1800136dc  cmp     [rcx+48h], r15w
0x1800136e1  jnz     short loc_1800136E6
0x1800136e3  mov     r8b, r15b
0x1800136e6  test    dl, dl
0x1800136e8  jnz     loc_180013812
0x1800136ee  test    r8b, r8b
0x1800136f1  jnz     loc_180013812
0x1800136f7  add     esi, ebx
0x1800136f9  cmp     esi, [rdi+0E8h]
0x1800136ff  jb      loc_180013672
0x180013705  xchg    ebx, [rdi+118h]
0x18001370b  add     rsp, 68h
0x18001370f  pop     r15
0x180013711  pop     r14
0x180013713  pop     rdi
0x180013714  pop     rsi
0x180013715  pop     rbp
0x180013716  pop     rbx
0x180013717  retn
0x180013719  lea     rcx, [r14+20h]
0x18001371d  xor     r8d, r8d; Wait
0x180013720  add     rcx, rbp; Event
0x180013723  xor     edx, edx; Increment
0x180013725  call    cs:__imp_KeSetEvent
0x18001372c  nop     dword ptr [rax+rax+00h]
0x180013731  lea     rcx, [r14+38h]
0x180013735  xor     r8d, r8d; Wait
0x180013738  add     rcx, rbp; Event
0x18001373b  xor     edx, edx; Increment
0x18001373d  call    cs:__imp_KeSetEvent
0x180013744  nop     dword ptr [rax+rax+00h]
0x180013749  jmp     loc_180013558
0x18001374e  cmp     byte ptr [rcx+29h], 5
0x180013752  mov     dl, bl
0x180013754  jnb     loc_1800135AE
0x18001375a  jmp     loc_1800135AB
0x18001375f  mov     rax, [r14+rbp+8]
0x180013764  mov     r9, [rdi+2B0h]
0x18001376b  mov     rcx, [rcx+18h]
0x18001376f  mov     [rsp+98h+var_50], rax
0x180013774  mov     rax, [rdi]
0x180013777  mov     [rsp+98h+var_58], rax
0x18001377c  mov     [rsp+98h+var_60], r10
0x180013781  mov     [rsp+98h+var_68], 26h ; '&'
0x180013788  mov     [rsp+98h+var_70], 5
0x180013790  mov     byte ptr [rsp+98h+Timeout], 5
0x180013795  call    WPP_RECORDER_AND_TRACE_SF_qq
0x18001379a  jmp     loc_1800135D5
0x18001379f  cmp     byte ptr [r10+29h], 5
0x1800137a4  mov     dl, bl
0x1800137a6  jnb     loc_180013629
0x1800137ac  jmp     loc_180013626
0x1800137b1  mov     rcx, [r10+18h]
0x1800137b5  movzx   r9d, al
0x1800137b9  mov     rax, [r14+rbp+8]
0x1800137be  mov     [rsp+98h+var_48], rax
0x1800137c3  mov     rax, [rdi]
0x1800137c6  mov     dword ptr [rsp+98h+var_50], r9d
0x1800137cb  mov     r9, [rdi+2B0h]
0x1800137d2  mov     [rsp+98h+var_58], rax
0x1800137d7  lea     rax, WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids
0x1800137de  mov     [rsp+98h+var_60], rax
0x1800137e3  mov     [rsp+98h+var_68], 27h ; '''
0x1800137ea  mov     [rsp+98h+var_70], 5
0x1800137f2  mov     byte ptr [rsp+98h+Timeout], 5
0x1800137f7  call    WPP_RECORDER_AND_TRACE_SF_qdq
0x1800137fc  jmp     loc_180013657
0x180013801  cmp     byte ptr [rcx+29h], 5
0x180013805  mov     dl, bl
0x180013807  jnb     loc_1800136C9
0x18001380d  jmp     loc_1800136C6
0x180013812  mov     rax, [r14+rbp+8]
0x180013817  mov     r9, [rdi+2B0h]
0x18001381e  mov     rcx, [rcx+18h]
0x180013822  mov     [rsp+98h+var_50], rax
0x180013827  mov     rax, [rdi]
0x18001382a  mov     [rsp+98h+var_58], rax
0x18001382f  lea     rax, WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids
0x180013836  mov     [rsp+98h+var_60], rax
0x18001383b  mov     [rsp+98h+var_68], 28h ; '('
0x180013842  mov     [rsp+98h+var_70], 5
0x18001384a  mov     byte ptr [rsp+98h+Timeout], 5
0x18001384f  call    WPP_RECORDER_AND_TRACE_SF_qq
0x180013854  jmp     loc_1800136F7
```
