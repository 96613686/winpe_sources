# FveTransform

- ea: `0x1400cfd14`
- end: `0x1400d0161`
- name: `FveTransform`
- size: `1101`
- prototype: `__int64 __usercall@<rax>(ULONG_PTR BugCheckParameter2@<rcx>, char, int)`
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140077394`
- `0x1400a2d94`
- `0x1400a3788`
- `0x1400e02d8`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14002bac0`
- `0x1400cfd14`
- `0x1400d0168`
- `0x1400d0800`
- `0x1400d1820`
- `0x1400dfbe0`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x1400cff26`
- `ntoskrnl!KeReadStateEvent` at `0x1400cff40`
- `ntoskrnl!KeReadStateEvent` at `0x1400cff26`
- `ntoskrnl!KeReadStateEvent` at `0x1400cff40`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400cfeb8`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400cfeb8`
- `ntoskrnl!KeClearEvent` at `0x1400cfdbc`
- `ntoskrnl!KeClearEvent` at `0x1400cfe1a`
- `ntoskrnl!KeClearEvent` at `0x1400cfe2a`
- `ntoskrnl!KeClearEvent` at `0x1400cfdbc`
- `ntoskrnl!KeClearEvent` at `0x1400cfe1a`
- `ntoskrnl!KeClearEvent` at `0x1400cfe2a`
- `ntoskrnl!KeSetEvent` at `0x1400d0063`
- `ntoskrnl!KeSetEvent` at `0x1400d0063`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d014d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d014d`
- `ntoskrnl!KeBugCheckEx` at `0x1400d012b`
- `ntoskrnl!KeBugCheckEx` at `0x1400d012b`

## pseudocode

```c
__int64 __fastcall FveTransform(__int64 *BugCheckParameter2, int a2, int a3, char a4, char a5, unsigned int a6)
{
  __int64 v10; // rax
  unsigned int *v11; // r13
  __int64 v12; // rax
  char v13; // r15
  int v14; // r12d
  __int64 i; // rsi
  __int64 v16; // rdi
  char v17; // al
  PVOID *__attribute__((__org_arrdim(0,0))) *v18; // r12
  PVOID *__attribute__((__org_arrdim(0,0))) *j; // r14
  __int64 v20; // rbp
  __int64 v21; // r15
  unsigned int v22; // edi
  __int64 v24; // rsi
  __int64 v25; // rdi
  __int64 v26; // rbp
  char v27; // al
  struct _KEVENT *v28; // rcx
  int v29; // edx
  int v30; // r9d
  bool v31; // zf
  int v32; // r8d
  ULONG_PTR v33; // rax
  __int64 WaitMode; // [rsp+20h] [rbp-88h]
  __int64 v35; // [rsp+B0h] [rbp+8h]
  int v36; // [rsp+C0h] [rbp+18h] BYREF
  char v37; // [rsp+C8h] [rbp+20h] BYREF

  v37 = a4;
  v36 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_838c7b85fa053f0b1c8d8005c1e1a89d_Traceguids);
  }
  v10 = BugCheckParameter2[1];
  v35 = BugCheckParameter2[7];
  v11 = *(unsigned int **)(v10 + 8);
  if ( a5 && !*(_DWORD *)(v10 + 1324) )
  {
    v12 = v11[221];
    if ( (__int64 (__fastcall *)(int, int, int, int, int, PUCHAR, PUCHAR, __int64))BugCheckParameter2[16] == FveFilteredEncrypt )
    {
      if ( v11[v12 + 343] != -1 )
        goto LABEL_6;
    }
    else if ( v11[v12 + 346] != -1 )
    {
LABEL_6:
      v13 = 1;
      goto LABEL_9;
    }
  }
  v13 = 0;
LABEL_9:
  a5 = v13;
  KeClearEvent((PRKEVENT)(BugCheckParameter2 + 2));
  v14 = a6;
  *((_DWORD *)BugCheckParameter2 + 19) = 0;
  *((_DWORD *)BugCheckParameter2 + 20) = 0;
  *((_DWORD *)BugCheckParameter2 + 103) = v14;
  *((_DWORD *)BugCheckParameter2 + 100) = a2;
  *((_DWORD *)BugCheckParameter2 + 101) = a3;
  *((_BYTE *)BugCheckParameter2 + 408) = a4;
  _InterlockedIncrement((volatile signed __int32 *)BugCheckParameter2 + 20);
  for ( i = 0; (unsigned int)i < *((_DWORD *)BugCheckParameter2 + 18); i = (unsigned int)(i + 1) )
  {
    v16 = *BugCheckParameter2 + 80 * i;
    *(_DWORD *)(*(_QWORD *)(v16 + 8) + 48LL) = v14;
    KeClearEvent((PRKEVENT)(v16 + 16));
    KeClearEvent((PRKEVENT)(v16 + 40));
    *(_BYTE *)(v16 + 64) = 0;
    if ( (unsigned int)i >= *((_DWORD *)BugCheckParameter2 + 18) - 1
      || (v17 = 0, (unsigned int)(*((_DWORD *)BugCheckParameter2 + 22) * (i + 1)) >= *((_DWORD *)BugCheckParameter2 + 23)) )
    {
      v17 = 1;
    }
    *(_BYTE *)(v16 + 65) = v17;
    _InterlockedIncrement((volatile signed __int32 *)BugCheckParameter2 + 20);
    if ( v13 )
    {
      FveCryptoWorkQueue(v11, *(_QWORD *)(v16 + 8), 0, 0);
    }
    else
    {
      if ( *(_BYTE *)(v16 + 65)
        || (v27 = FvepQueueWorkItem(v11, *(_QWORD *)(v16 + 8), v36, v37, (__int64)FveTransformWork, v16, 0, v14, 1),
            v28 = (struct _KEVENT *)(v16 + 16),
            !v27) )
      {
        v28 = (struct _KEVENT *)(v16 + 40);
      }
      KeSetEvent(v28, 0, 0);
    }
    if ( *(_BYTE *)(v16 + 65) )
      break;
  }
  v18 = (PVOID *__attribute__((__org_arrdim(0,0))) *)(BugCheckParameter2 + 5);
  for ( j = (PVOID *__attribute__((__org_arrdim(0,0))) *)(BugCheckParameter2 + 5);
        ;
        KeWaitForMultipleObjects(v20, *j, WaitAny, Executive, 0, 0, 0, (PKWAIT_BLOCK)BugCheckParameter2[6]) )
  {
    v20 = 0;
    v21 = 0;
    while ( (unsigned int)v21 < *((_DWORD *)BugCheckParameter2 + 18) )
    {
      v24 = *BugCheckParameter2;
      v25 = 80 * v21;
      if ( !KeReadStateEvent((PRKEVENT)(80 * v21 + *BugCheckParameter2 + 16)) )
      {
        if ( KeReadStateEvent((PRKEVENT)(v25 + v24 + 40)) )
        {
          if ( !*(_BYTE *)(v25 + v24 + 64) )
          {
            FveTransformWork(v11, *(_QWORD *)(v25 + v24 + 8));
            v31 = a5 == 0;
            *(_BYTE *)(v25 + v24 + 64) = 1;
            if ( !v31 )
            {
              LOBYTE(v30) = *(_BYTE *)(v25 + v24 + 72);
              v32 = *(_DWORD *)(v25 + v24 + 68);
              LOBYTE(v29) = BugCheckParameter2[16] == (_QWORD)FveFilteredEncrypt;
              v36 = 0;
              WaitMode = *(_QWORD *)(v25 + v24 + 8);
              v37 = 0;
              v33 = FveGlobalCryptoThrottleComplete(
                      (_DWORD)v11,
                      v29,
                      v32,
                      v30,
                      WaitMode,
                      0,
                      (__int64)&v36,
                      (__int64)&v37);
              if ( v33 )
                KeBugCheckEx(0x120u, 0xCu, (ULONG_PTR)BugCheckParameter2, 0, v33);
            }
          }
        }
        else
        {
          (*j)[v20] = (PVOID)(v25 + v24 + 16);
          v26 = (unsigned int)(v20 + 1);
          (*j)[v26] = (PVOID)(v25 + v24 + 40);
          v20 = (unsigned int)(v26 + 1);
        }
        v18 = (PVOID *__attribute__((__org_arrdim(0,0))) *)(BugCheckParameter2 + 5);
      }
      if ( *(_BYTE *)(v25 + v24 + 65) )
        break;
      v21 = (unsigned int)(v21 + 1);
      j = v18;
    }
    if ( !(_DWORD)v20 )
      break;
  }
  v22 = 259;
  FveTransformWorkComplete(BugCheckParameter2, a6);
  if ( !v35 )
  {
    KeWaitForSingleObject(BugCheckParameter2 + 2, Executive, 0, 0, 0);
    v22 = *((_DWORD *)BugCheckParameter2 + 19);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_838c7b85fa053f0b1c8d8005c1e1a89d_Traceguids, v22);
  }
  return v22;
}

```

## disassembly

```asm
0x1400cfd14  mov     [rsp+arg_18], r9b
0x1400cfd19  mov     [rsp+arg_10], r8d
0x1400cfd1e  mov     [rsp+arg_8], edx
0x1400cfd22  push    rbx
0x1400cfd23  push    rbp
0x1400cfd24  push    rsi
0x1400cfd25  push    rdi
0x1400cfd26  push    r12
0x1400cfd28  push    r13
0x1400cfd2a  push    r14
0x1400cfd2c  push    r15
0x1400cfd2e  sub     rsp, 68h
0x1400cfd32  mov     dil, r9b
0x1400cfd35  mov     esi, r8d
0x1400cfd38  mov     ebp, edx
0x1400cfd3a  mov     rbx, rcx
0x1400cfd3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cfd44  lea     rax, WPP_GLOBAL_Control
0x1400cfd4b  cmp     rcx, rax
0x1400cfd4e  jnz     loc_1400CFF9E
0x1400cfd54  cmp     [rsp+0A8h+arg_20], 0
0x1400cfd5c  mov     rcx, [rbx+38h]
0x1400cfd60  mov     rax, [rbx+8]
0x1400cfd64  mov     [rsp+0A8h+arg_0], rcx
0x1400cfd6c  lea     rcx, FveFilteredEncrypt
0x1400cfd73  mov     r13, [rax+8]
0x1400cfd77  jz      short loc_1400CFDAD
0x1400cfd79  cmp     dword ptr [rax+52Ch], 0
0x1400cfd80  jnz     short loc_1400CFDAD
0x1400cfd82  mov     eax, [r13+374h]
0x1400cfd89  cmp     [rbx+80h], rcx
0x1400cfd90  jz      short loc_1400CFDA2
0x1400cfd92  cmp     dword ptr [r13+rax*4+568h], 0FFFFFFFFh
0x1400cfd9b  jz      short loc_1400CFDAD
0x1400cfd9d  mov     r15b, 1
0x1400cfda0  jmp     short loc_1400CFDB0
0x1400cfda2  cmp     dword ptr [r13+rax*4+55Ch], 0FFFFFFFFh
0x1400cfdab  jnz     short loc_1400CFD9D
0x1400cfdad  xor     r15b, r15b
0x1400cfdb0  lea     rcx, [rbx+10h]; Event
0x1400cfdb4  mov     [rsp+0A8h+arg_20], r15b
0x1400cfdbc  call    cs:__imp_KeClearEvent
0x1400cfdc3  nop     dword ptr [rax+rax+00h]
0x1400cfdc8  mov     r12d, [rsp+0A8h+arg_28]
0x1400cfdd0  mov     dword ptr [rbx+4Ch], 0
0x1400cfdd7  mov     dword ptr [rbx+50h], 0
0x1400cfdde  mov     [rbx+19Ch], r12d
0x1400cfde5  mov     [rbx+190h], ebp
0x1400cfdeb  mov     [rbx+194h], esi
0x1400cfdf1  mov     [rbx+198h], dil
0x1400cfdf8  lock inc dword ptr [rbx+50h]
0x1400cfdfc  xor     esi, esi
0x1400cfdfe  cmp     [rbx+48h], esi
0x1400cfe01  jbe     short loc_1400CFE76
0x1400cfe03  lea     rdi, [rsi+rsi*4]
0x1400cfe07  shl     rdi, 4
0x1400cfe0b  add     rdi, [rbx]
0x1400cfe0e  mov     rax, [rdi+8]
0x1400cfe12  lea     rcx, [rdi+10h]; Event
0x1400cfe16  mov     [rax+30h], r12d
0x1400cfe1a  call    cs:__imp_KeClearEvent
0x1400cfe21  nop     dword ptr [rax+rax+00h]
0x1400cfe26  lea     rcx, [rdi+28h]; Event
0x1400cfe2a  call    cs:__imp_KeClearEvent
0x1400cfe31  nop     dword ptr [rax+rax+00h]
0x1400cfe36  xor     ecx, ecx
0x1400cfe38  mov     [rdi+40h], cl
0x1400cfe3b  mov     eax, [rbx+48h]
0x1400cfe3e  dec     eax
0x1400cfe40  cmp     esi, eax
0x1400cfe42  jb      loc_1400CFF87
0x1400cfe48  mov     al, 1
0x1400cfe4a  mov     [rdi+41h], al
0x1400cfe4d  lock inc dword ptr [rbx+50h]
0x1400cfe51  test    r15b, r15b
0x1400cfe54  jz      loc_1400D0000
0x1400cfe5a  mov     rdx, [rdi+8]
0x1400cfe5e  xor     r9d, r9d
0x1400cfe61  xor     r8d, r8d
0x1400cfe64  mov     rcx, r13
0x1400cfe67  call    FveCryptoWorkQueue
0x1400cfe6c  cmp     byte ptr [rdi+41h], 0
0x1400cfe70  jz      loc_1400D0074
0x1400cfe76  lea     r12, [rbx+28h]
0x1400cfe7a  mov     r14, r12
0x1400cfe7d  xor     ebp, ebp
0x1400cfe7f  xor     r15d, r15d
0x1400cfe82  cmp     r15d, [rbx+48h]
0x1400cfe86  jb      loc_1400CFF14
0x1400cfe8c  test    ebp, ebp
0x1400cfe8e  jz      short loc_1400CFEC6
0x1400cfe90  mov     rax, [rbx+30h]
0x1400cfe94  xor     r9d, r9d; WaitReason
0x1400cfe97  mov     rdx, [r14]; Object
0x1400cfe9a  mov     ecx, ebp; Count
0x1400cfe9c  mov     [rsp+0A8h+WaitBlockArray], rax; WaitBlockArray
0x1400cfea1  mov     [rsp+0A8h+Timeout], 0; Timeout
0x1400cfeaa  lea     r8d, [r9+1]; WaitType
0x1400cfeae  mov     [rsp+0A8h+Alertable], 0; Alertable
0x1400cfeb3  mov     [rsp+0A8h+WaitMode], 0; WaitMode
0x1400cfeb8  call    cs:__imp_KeWaitForMultipleObjects
0x1400cfebf  nop     dword ptr [rax+rax+00h]
0x1400cfec4  jmp     short loc_1400CFE7D
0x1400cfec6  mov     edx, [rsp+0A8h+arg_28]
0x1400cfecd  mov     rcx, rbx
0x1400cfed0  mov     edi, 103h
0x1400cfed5  call    FveTransformWorkComplete
0x1400cfeda  cmp     [rsp+0A8h+arg_0], 0
0x1400cfee3  jz      loc_1400D0138
0x1400cfee9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cfef0  lea     rax, WPP_GLOBAL_Control
0x1400cfef7  cmp     rcx, rax
0x1400cfefa  jnz     loc_1400CFFCD
0x1400cff00  mov     eax, edi
0x1400cff02  add     rsp, 68h
0x1400cff06  pop     r15
0x1400cff08  pop     r14
0x1400cff0a  pop     r13
0x1400cff0c  pop     r12
0x1400cff0e  pop     rdi
0x1400cff0f  pop     rsi
0x1400cff10  pop     rbp
0x1400cff11  pop     rbx
0x1400cff12  retn
0x1400cff14  mov     rsi, [rbx]
0x1400cff17  lea     rdi, [r15+r15*4]
0x1400cff1b  shl     rdi, 4
0x1400cff1f  lea     rcx, [rsi+10h]
0x1400cff23  add     rcx, rdi; Event
0x1400cff26  call    cs:__imp_KeReadStateEvent
0x1400cff2d  nop     dword ptr [rax+rax+00h]
0x1400cff32  test    eax, eax
0x1400cff34  jnz     short loc_1400CFF71
0x1400cff36  lea     r12, [rsi+28h]
0x1400cff3a  add     r12, rdi
0x1400cff3d  mov     rcx, r12; Event
0x1400cff40  call    cs:__imp_KeReadStateEvent
0x1400cff47  nop     dword ptr [rax+rax+00h]
0x1400cff4c  test    eax, eax
0x1400cff4e  jnz     loc_1400D0084
0x1400cff54  mov     rax, [r14]
0x1400cff57  lea     rdx, [rsi+10h]
0x1400cff5b  add     rdx, rdi
0x1400cff5e  mov     [rax+rbp*8], rdx
0x1400cff62  inc     ebp
0x1400cff64  mov     rax, [r14]
0x1400cff67  mov     [rax+rbp*8], r12
0x1400cff6b  inc     ebp
0x1400cff6d  lea     r12, [rbx+28h]
0x1400cff71  cmp     byte ptr [rdi+rsi+41h], 0
0x1400cff76  jnz     loc_1400CFE8C
0x1400cff7c  inc     r15d
0x1400cff7f  mov     r14, r12
0x1400cff82  jmp     loc_1400CFE82
0x1400cff87  lea     eax, [rsi+1]
0x1400cff8a  imul    eax, [rbx+58h]
0x1400cff8e  cmp     eax, [rbx+5Ch]
0x1400cff91  mov     al, cl
0x1400cff93  jb      loc_1400CFE4A
0x1400cff99  jmp     loc_1400CFE48
0x1400cff9e  mov     eax, [rcx+2Ch]
0x1400cffa1  test    al, 2
0x1400cffa3  jz      loc_1400CFD54
0x1400cffa9  cmp     byte ptr [rcx+29h], 5
0x1400cffad  jb      loc_1400CFD54
0x1400cffb3  mov     rcx, [rcx+18h]
0x1400cffb7  lea     r8, WPP_838c7b85fa053f0b1c8d8005c1e1a89d_Traceguids
0x1400cffbe  mov     edx, 10h
0x1400cffc3  call    WPP_SF_
0x1400cffc8  jmp     loc_1400CFD54
0x1400cffcd  mov     edx, [rcx+2Ch]
0x1400cffd0  test    dl, 2
0x1400cffd3  jz      loc_1400CFF00
0x1400cffd9  cmp     byte ptr [rcx+29h], 5
0x1400cffdd  jb      loc_1400CFF00
0x1400cffe3  mov     rcx, [rcx+18h]
0x1400cffe7  lea     r8, WPP_838c7b85fa053f0b1c8d8005c1e1a89d_Traceguids
0x1400cffee  mov     edx, 11h
0x1400cfff3  mov     r9d, edi
0x1400cfff6  call    WPP_SF_d
0x1400cfffb  jmp     loc_1400CFF00
0x1400d0000  cmp     [rdi+41h], cl
0x1400d0003  jnz     short loc_1400D005A
0x1400d0005  mov     r9d, [rsp+0A8h+arg_8]
0x1400d000d  lea     rax, FveTransformWork
0x1400d0014  mov     rdx, [rdi+8]; BugCheckParameter2
0x1400d0018  xor     r8d, r8d
0x1400d001b  mov     [rsp+0A8h+var_58], 1; char
0x1400d0020  mov     [rsp+0A8h+var_60], r12d; int
0x1400d0025  mov     [rsp+0A8h+var_68], rcx; __int64
0x1400d002a  mov     rcx, r13; Context
0x1400d002d  mov     [rsp+0A8h+WaitBlockArray], rdi; __int64
0x1400d0032  mov     [rsp+0A8h+Timeout], rax; __int64
0x1400d0037  mov     al, [rsp+0A8h+arg_18]
0x1400d003e  mov     [rsp+0A8h+Alertable], al; char
0x1400d0042  mov     eax, [rsp+0A8h+arg_10]
0x1400d0049  mov     dword ptr [rsp+0A8h+WaitMode], eax; int
0x1400d004d  call    FvepQueueWorkItem
0x1400d0052  lea     rcx, [rdi+10h]
0x1400d0056  test    al, al
0x1400d0058  jnz     short loc_1400D005E
0x1400d005a  lea     rcx, [rdi+28h]; Event
0x1400d005e  xor     r8d, r8d; Wait
0x1400d0061  xor     edx, edx; Increment
0x1400d0063  call    cs:__imp_KeSetEvent
0x1400d006a  nop     dword ptr [rax+rax+00h]
0x1400d006f  jmp     loc_1400CFE6C
0x1400d0074  inc     esi
0x1400d0076  cmp     esi, [rbx+48h]
0x1400d0079  jb      loc_1400CFE03
0x1400d007f  jmp     loc_1400CFE76
0x1400d0084  cmp     byte ptr [rdi+rsi+40h], 0
0x1400d0089  jnz     loc_1400CFF6D
0x1400d008f  mov     rdx, [rdi+rsi+8]
0x1400d0094  mov     rcx, r13
0x1400d0097  call    FveTransformWork
0x1400d009c  cmp     [rsp+0A8h+arg_20], 0
0x1400d00a4  mov     byte ptr [rdi+rsi+40h], 1
0x1400d00a9  jz      loc_1400CFF6D
0x1400d00af  mov     r9b, [rdi+rsi+48h]
0x1400d00b4  lea     rax, FveFilteredEncrypt
0x1400d00bb  cmp     [rbx+80h], rax
0x1400d00c2  mov     rcx, r13
0x1400d00c5  mov     r8d, [rdi+rsi+44h]
0x1400d00ca  lea     rax, [rsp+0A8h+arg_18]
0x1400d00d2  mov     [rsp+0A8h+WaitBlockArray], rax
0x1400d00d7  setz    dl
0x1400d00da  lea     rax, [rsp+0A8h+arg_10]
0x1400d00e2  mov     [rsp+0A8h+arg_10], 0
0x1400d00ed  mov     [rsp+0A8h+Timeout], rax
0x1400d00f2  mov     rax, [rdi+rsi+8]
0x1400d00f7  mov     [rsp+0A8h+Alertable], 0
0x1400d00fc  mov     qword ptr [rsp+0A8h+WaitMode], rax
0x1400d0101  mov     [rsp+0A8h+arg_18], 0
0x1400d0109  call    FveGlobalCryptoThrottleComplete
0x1400d010e  test    rax, rax
0x1400d0111  jz      loc_1400CFF6D
0x1400d0117  xor     r9d, r9d; BugCheckParameter3
0x1400d011a  mov     qword ptr [rsp+0A8h+WaitMode], rax; BugCheckParameter4
0x1400d011f  mov     r8, rbx; BugCheckParameter2
0x1400d0122  mov     ecx, 120h; BugCheckCode
0x1400d0127  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400d012b  call    cs:__imp_KeBugCheckEx
0x1400d0138  xor     r9d, r9d; Alertable
0x1400d013b  mov     qword ptr [rsp+0A8h+WaitMode], 0; Timeout
0x1400d0144  xor     r8d, r8d; WaitMode
0x1400d0147  lea     rcx, [rbx+10h]; Object
0x1400d014b  xor     edx, edx; WaitReason
0x1400d014d  call    cs:__imp_KeWaitForSingleObject
0x1400d0154  nop     dword ptr [rax+rax+00h]
0x1400d0159  mov     edi, [rbx+4Ch]
0x1400d015c  jmp     loc_1400CFEE9
```
