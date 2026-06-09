# BwcCompleteNbls

- ea: `0x140011da8`
- end: `0x140011ecb`
- name: `BwcCompleteNbls`
- size: `291`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140002974`
- `0x140012570`
- `0x140013080`
- `0x140013570`

## callees

- `0x14000917c`
- `0x140011da8`
- `0x140013f48`
- `0x140014050`
- `0x140014860`
- `0x140015d84`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140011de0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140011de0`
- `NDIS!NdisReleaseRWLock` at `0x140011e3d`
- `NDIS!NdisReleaseRWLock` at `0x140011e3d`
- `NDIS!NdisAcquireRWLockWrite` at `0x140011e1f`
- `NDIS!NdisAcquireRWLockWrite` at `0x140011e1f`

## pseudocode

```c
int __fastcall BwcCompleteNbls(__int64 a1, volatile signed __int32 *a2, _QWORD *a3, _QWORD *a4)
{
  _QWORD *v8; // rax
  unsigned int v9; // r15d
  int v10; // r14d
  int v11; // r9d
  _QWORD *v12; // rdi
  __int64 v14; // [rsp+30h] [rbp-10h] BYREF
  _QWORD *v15; // [rsp+38h] [rbp-8h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+70h] [rbp+30h] BYREF
  _QWORD *v17; // [rsp+88h] [rbp+48h] BYREF

  v17 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  LODWORD(v8) = KeGetCurrentProcessorNumberEx(0);
  v9 = (unsigned int)v8;
  if ( a1 )
  {
    if ( !a2 )
      a2 = (volatile signed __int32 *)BwcVirtualLine;
    v10 = (_DWORD)a2 + 8;
    if ( (unsigned __int8)QosLineNeedSignal(a2 + 2, (unsigned int)v8) )
    {
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)a2, &LockState, 1u);
      QosLineSignalExternalEvent(a2 + 2, v9);
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)a2, &LockState);
    }
    _InterlockedAdd(a2 + 36, QosGetNblChainDataLength(a3));
    v8 = &v17;
    v15 = &v17;
    if ( a3 )
    {
      do
      {
        v12 = (_QWORD *)*a3;
        v14 = 0;
        *a3 = 0;
        LODWORD(v8) = QosTbcSendNetBufferListComplete((int)a1 + 40, v10, (_DWORD)a3, v11, (__int64)&v14);
        if ( v14 )
          LODWORD(v8) = BwcNblAppendNblsMoveLast(&v15);
        a3 = v12;
      }
      while ( v12 );
    }
    a3 = v17;
  }
  *a4 = a3;
  return (int)v8;
}

```

## disassembly

```asm
0x140011da8  mov     [rsp-28h+arg_8], rbx
0x140011dad  mov     [rsp-28h+arg_10], rsi
0x140011db2  push    rbp
0x140011db3  push    rdi
0x140011db4  push    r12
0x140011db6  push    r14
0x140011db8  push    r15
0x140011dba  mov     rbp, rsp
0x140011dbd  sub     rsp, 40h
0x140011dc1  xor     eax, eax
0x140011dc3  mov     [rbp+arg_18], 0
0x140011dcb  mov     rsi, rcx
0x140011dce  mov     word ptr [rbp+LockState.OldIrql], ax
0x140011dd2  xor     ecx, ecx; ProcNumber
0x140011dd4  mov     [rbp+LockState.Flags], al
0x140011dd7  mov     r12, r9
0x140011dda  mov     rbx, r8
0x140011ddd  mov     rdi, rdx
0x140011de0  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140011de7  nop     dword ptr [rax+rax+00h]
0x140011dec  mov     r15d, eax
0x140011def  test    rsi, rsi
0x140011df2  jz      loc_140011EAD
0x140011df8  test    rdi, rdi
0x140011dfb  mov     edx, eax
0x140011dfd  cmovz   rdi, cs:BwcVirtualLine
0x140011e05  lea     r14, [rdi+8]
0x140011e09  mov     rcx, r14
0x140011e0c  call    QosLineNeedSignal
0x140011e11  test    al, al
0x140011e13  jz      short loc_140011E49
0x140011e15  mov     rcx, [rdi]; Lock
0x140011e18  lea     rdx, [rbp+LockState]; LockState
0x140011e1c  mov     r8b, 1; Flags
0x140011e1f  call    cs:__imp_NdisAcquireRWLockWrite
0x140011e26  nop     dword ptr [rax+rax+00h]
0x140011e2b  mov     edx, r15d
0x140011e2e  mov     rcx, r14
0x140011e31  call    QosLineSignalExternalEvent
0x140011e36  mov     rcx, [rdi]; Lock
0x140011e39  lea     rdx, [rbp+LockState]; LockState
0x140011e3d  call    cs:__imp_NdisReleaseRWLock
0x140011e44  nop     dword ptr [rax+rax+00h]
0x140011e49  mov     rcx, rbx
0x140011e4c  call    QosGetNblChainDataLength
0x140011e51  lock add [rdi+90h], eax
0x140011e58  lea     rax, [rbp+arg_18]
0x140011e5c  mov     [rbp+var_8], rax
0x140011e60  test    rbx, rbx
0x140011e63  jz      short loc_140011EA9
0x140011e65  mov     rdi, [rbx]
0x140011e68  lea     rax, [rbp+var_10]
0x140011e6c  mov     r8, rbx
0x140011e6f  mov     [rsp+40h+var_20], rax
0x140011e74  mov     rdx, r14
0x140011e77  mov     [rbp+var_10], 0
0x140011e7f  lea     rcx, [rsi+28h]
0x140011e83  mov     qword ptr [rbx], 0
0x140011e8a  call    QosTbcSendNetBufferListComplete
0x140011e8f  mov     rdx, [rbp+var_10]
0x140011e93  test    rdx, rdx
0x140011e96  jz      short loc_140011EA1
0x140011e98  lea     rcx, [rbp+var_8]
0x140011e9c  call    BwcNblAppendNblsMoveLast
0x140011ea1  mov     rbx, rdi
0x140011ea4  test    rdi, rdi
0x140011ea7  jnz     short loc_140011E65
0x140011ea9  mov     rbx, [rbp+arg_18]
0x140011ead  lea     r11, [rsp+40h+var_s0]
0x140011eb2  mov     [r12], rbx
0x140011eb6  mov     rbx, [r11+38h]
0x140011eba  mov     rsi, [r11+40h]
0x140011ebe  mov     rsp, r11
0x140011ec1  pop     r15
0x140011ec3  pop     r14
0x140011ec5  pop     r12
0x140011ec7  pop     rdi
0x140011ec8  pop     rbp
0x140011ec9  retn
```
