# MsQuicListenerOpen

- ea: `0x140026770`
- end: `0x140026973`
- name: `MsQuicListenerOpen`
- size: `515`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140026770`
- `0x14003ce00`
- `0x14003eca4`
- `0x14003ed00`
- `0x140040c2c`
- `0x140040de8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002689e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002689e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400268d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400268d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026900`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026900`
- `ntoskrnl!KeInitializeEvent` at `0x14002684f`
- `ntoskrnl!KeInitializeEvent` at `0x14002684f`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140026878`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140026878`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14002688e`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14002688e`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14002685b`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14002685b`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400268ec`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400268ec`
- `ntoskrnl!ExAllocatePool2` at `0x1400267e7`
- `ntoskrnl!ExAllocatePool2` at `0x1400267e7`

## pseudocode

```c
__int64 __fastcall MsQuicListenerOpen(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  unsigned int v8; // ebx
  _QWORD *Pool2; // rax
  __int64 v10; // rdx
  _QWORD *v11; // rdi
  void *CurrentServerSilo; // rax
  KIRQL v13; // al
  char v14; // bp
  char v15; // bp
  _QWORD *v16; // rax

  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 8, a1);
  v8 = 0;
  if ( a1 && !*(_DWORD *)a1 && a4 && a2 )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(66, 200, 1110467409);
    v11 = Pool2;
    if ( Pool2 )
    {
      memset(Pool2, 0, 0xC8u);
      *(_DWORD *)v11 = 2;
      v11[6] = a1;
      v11[19] = a2;
      v11[1] = a3;
      *((_BYTE *)v11 + 18) = 1;
      *((_BYTE *)v11 + 20) = 0;
      KeInitializeEvent((PRKEVENT)(v11 + 11), NotificationEvent, 1u);
      CurrentServerSilo = (void *)PsGetCurrentServerSilo();
      v11[9] = CurrentServerSilo;
      if ( CurrentServerSilo )
        ObfReferenceObjectWithTag(CurrentServerSilo, 0x30306351u);
      ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 128));
      v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 80));
      v14 = *(_BYTE *)(a1 + 16);
      *(_BYTE *)(a1 + 88) = v13;
      v15 = v14 & 4;
      if ( !v15 )
      {
        v16 = *(_QWORD **)(a1 + 120);
        v11[7] = a1 + 112;
        v11[8] = v16;
        *v16 = v11 + 7;
        *(_QWORD *)(a1 + 120) = v11 + 7;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 80), *(_BYTE *)(a1 + 88));
      if ( v15 )
      {
        ExReleaseRundownProtection((PEX_RUNDOWN_REF)(a1 + 128));
        ExFreePoolWithTag(v11, 0x42306351u);
        v8 = -1073741436;
      }
      else
      {
        if ( (byte_14005C489 & 0x10) != 0 )
          McTemplateU0pp_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)QuicListenerCreated, v11, v11[6]);
        *a4 = v11;
      }
    }
    else
    {
      if ( (Microsoft_QuicEnableBits & 2) != 0 )
        McTemplateU0sx_EtwWriteTransfer(a1, v10, "listener", 200);
      v8 = -1073741801;
    }
  }
  else
  {
    v8 = -1073741811;
  }
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)QuicApiExitStatus, v8);
  return v8;
}

```

## disassembly

```asm
0x140026770  mov     rax, rsp
0x140026773  mov     [rax+8], rbx
0x140026777  mov     [rax+10h], rbp
0x14002677b  mov     [rax+18h], rsi
0x14002677f  mov     [rax+20h], rdi
0x140026783  push    r12
0x140026785  push    r14
0x140026787  push    r15
0x140026789  sub     rsp, 20h
0x14002678d  test    cs:Microsoft_QuicEnableBits, 8
0x140026794  mov     r14, r9
0x140026797  mov     r15, r8
0x14002679a  mov     rbp, rdx
0x14002679d  mov     rsi, rcx
0x1400267a0  jz      short loc_1400267B0
0x1400267a2  mov     r9, rcx
0x1400267a5  mov     r8d, 8
0x1400267ab  call    McTemplateU0qp_EtwWriteTransfer
0x1400267b0  xor     ebx, ebx
0x1400267b2  test    rsi, rsi
0x1400267b5  jz      loc_140026934
0x1400267bb  cmp     [rsi], ebx
0x1400267bd  jnz     loc_140026934
0x1400267c3  test    r14, r14
0x1400267c6  jz      loc_140026934
0x1400267cc  test    rbp, rbp
0x1400267cf  jz      loc_140026934
0x1400267d5  mov     r12d, 0C8h
0x1400267db  lea     ecx, [rbx+42h]
0x1400267de  mov     edx, r12d
0x1400267e1  mov     r8d, 42306351h
0x1400267e7  call    cs:__imp_ExAllocatePool2
0x1400267ee  nop     dword ptr [rax+rax+00h]
0x1400267f3  mov     rdi, rax
0x1400267f6  test    rax, rax
0x1400267f9  jnz     short loc_14002681D
0x1400267fb  test    cs:Microsoft_QuicEnableBits, 2
0x140026802  jz      short loc_140026813
0x140026804  mov     r9d, r12d
0x140026807  lea     r8, aListener; "listener"
0x14002680e  call    McTemplateU0sx_EtwWriteTransfer
0x140026813  mov     ebx, 0C0000017h
0x140026818  jmp     loc_140026939
0x14002681d  mov     r8, r12; Size
0x140026820  xor     edx, edx; Val
0x140026822  mov     rcx, rdi; void *
0x140026825  call    memset
0x14002682a  lea     rcx, [rdi+58h]; Event
0x14002682e  mov     dword ptr [rdi], 2
0x140026834  mov     r8b, 1; State
0x140026837  mov     [rdi+30h], rsi
0x14002683b  xor     edx, edx; Type
0x14002683d  mov     [rdi+98h], rbp
0x140026844  mov     [rdi+8], r15
0x140026848  mov     byte ptr [rdi+12h], 1
0x14002684c  mov     [rdi+14h], bl
0x14002684f  call    cs:__imp_KeInitializeEvent
0x140026856  nop     dword ptr [rax+rax+00h]
0x14002685b  call    cs:__imp_PsGetCurrentServerSilo
0x140026862  nop     dword ptr [rax+rax+00h]
0x140026867  mov     [rdi+48h], rax
0x14002686b  test    rax, rax
0x14002686e  jz      short loc_140026884
0x140026870  mov     edx, 30306351h; Tag
0x140026875  mov     rcx, rax; Object
0x140026878  call    cs:__imp_ObfReferenceObjectWithTag
0x14002687f  nop     dword ptr [rax+rax+00h]
0x140026884  lea     r15, [rsi+80h]
0x14002688b  mov     rcx, r15; RunRef
0x14002688e  call    cs:__imp_ExAcquireRundownProtection
0x140026895  nop     dword ptr [rax+rax+00h]
0x14002689a  lea     rcx, [rsi+50h]; SpinLock
0x14002689e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400268a5  nop     dword ptr [rax+rax+00h]
0x1400268aa  mov     bpl, [rsi+10h]
0x1400268ae  mov     [rsi+58h], al
0x1400268b1  and     bpl, 4
0x1400268b5  jnz     short loc_1400268D1
0x1400268b7  lea     r9, [rdi+38h]
0x1400268bb  lea     r8, [rsi+70h]
0x1400268bf  mov     rax, [r8+8]
0x1400268c3  mov     [r9], r8
0x1400268c6  mov     [r9+8], rax
0x1400268ca  mov     [rax], r9
0x1400268cd  mov     [r8+8], r9
0x1400268d1  mov     dl, [rsi+58h]; NewIrql
0x1400268d4  lea     rcx, [rsi+50h]; SpinLock
0x1400268d8  call    cs:__imp_KeReleaseSpinLock
0x1400268df  nop     dword ptr [rax+rax+00h]
0x1400268e4  test    bpl, bpl
0x1400268e7  jz      short loc_140026913
0x1400268e9  mov     rcx, r15; RunRef
0x1400268ec  call    cs:__imp_ExReleaseRundownProtection
0x1400268f3  nop     dword ptr [rax+rax+00h]
0x1400268f8  mov     edx, 42306351h; Tag
0x1400268fd  mov     rcx, rdi; P
0x140026900  call    cs:__imp_ExFreePoolWithTag
0x140026907  nop     dword ptr [rax+rax+00h]
0x14002690c  mov     ebx, 0C0000184h
0x140026911  jmp     short loc_140026939
0x140026913  test    cs:byte_14005C489, 10h
0x14002691a  jz      short loc_14002692F
0x14002691c  mov     r9, [rdi+30h]
0x140026920  lea     rdx, QuicListenerCreated
0x140026927  mov     r8, rdi
0x14002692a  call    McTemplateU0pp_EtwWriteTransfer
0x14002692f  mov     [r14], rdi
0x140026932  jmp     short loc_140026939
0x140026934  mov     ebx, 0C000000Dh
0x140026939  test    cs:Microsoft_QuicEnableBits, 8
0x140026940  jz      short loc_140026951
0x140026942  mov     r8d, ebx
0x140026945  lea     rdx, QuicApiExitStatus
0x14002694c  call    McTemplateU0q_EtwWriteTransfer
0x140026951  mov     rbp, [rsp+38h+arg_8]
0x140026956  mov     eax, ebx
0x140026958  mov     rbx, [rsp+38h+arg_0]
0x14002695d  mov     rsi, [rsp+38h+arg_10]
0x140026962  mov     rdi, [rsp+38h+arg_18]
0x140026967  add     rsp, 20h
0x14002696b  pop     r15
0x14002696d  pop     r14
0x14002696f  pop     r12
0x140026971  retn
```
