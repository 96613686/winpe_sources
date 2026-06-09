# CKsPin::TransferKsIrp(_IRP *,IKsTransport * *)

- ea: `0x18000f090`
- end: `0x18000f1d1`
- name: `?TransferKsIrp@CKsPin@@UEAAJPEAU_IRP@@PEAPEAUIKsTransport@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(CKsPin *__hidden this, PIRP Irp, struct IKsTransport **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007210`
- `0x1800073d0`
- `0x18000adb0`
- `0x18000b7bc`
- `0x18000da50`
- `0x18000f090`
- `0x180010310`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18000f18f`
- `ntoskrnl!IofCompleteRequest` at `0x18000f18f`

## pseudocode

```c
__int64 __fastcall CKsPin::TransferKsIrp(CKsPin *this, PIRP Irp, struct IKsTransport **a3)
{
  PIRP v4; // rdi
  __int64 result; // rax
  struct IKsTransport *m_TransportSink; // rcx
  __int64 v8; // rcx
  __int64 v9; // r8

  v4 = Irp;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(Irp) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      1,
      52,
      (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
  }
  if ( this->m_ConnectionFileObject )
  {
    if ( this->m_Flushing || this->m_State == KSSTATE_STOP || v4->IoStatus.Status < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(Irp) = 5;
          WPP_RECORDER_SF_qq(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)Irp,
            (_DWORD)a3,
            53,
            (char)WPP_9505c27395793143ec5446714e36088f_Traceguids,
            (char)this);
        }
      }
      m_TransportSink = this->m_TransportSink;
      result = 0;
    }
    else
    {
      KsAddIrpToCancelableQueue(&this->m_IrpsToSend.ListEntry, &this->m_IrpsToSend.SpinLock, v4, KsListEntryTail, 0);
      KsIncrementCountedWorker(this->m_Worker);
      result = 259;
      m_TransportSink = 0;
    }
    *a3 = m_TransportSink;
  }
  else
  {
    v4->IoStatus.Information = v4->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
    IofCompleteRequest(v4, 0);
    *a3 = 0;
    if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 2) != 0 )
      McTemplateK0p_EtwWriteTransfer(v8, (__int64)KS_StreamingRequest_Stop, v9, 0);
    CKsPin::DecrementIrpCirculation(this);
    return 259;
  }
  return result;
}

```

## disassembly

```asm
0x18000f090  push    rbx
0x18000f092  push    rbp
0x18000f093  push    rsi
0x18000f094  push    rdi
0x18000f095  push    r14
0x18000f097  push    r15
0x18000f099  sub     rsp, 48h
0x18000f09d  mov     rsi, r8
0x18000f0a0  mov     rdi, rdx
0x18000f0a3  mov     rbx, rcx
0x18000f0a6  lea     r14, WPP_RECORDER_INITIALIZED
0x18000f0ad  xor     ebp, ebp
0x18000f0af  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000f0b6  lea     r15, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x18000f0bd  jz      short loc_18000F0E4
0x18000f0bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0c6  cmp     [rcx+48h], bp
0x18000f0ca  jz      short loc_18000F0E4
0x18000f0cc  mov     rcx, [rcx+40h]
0x18000f0d0  lea     r9d, [rbp+34h]
0x18000f0d4  lea     r8d, [rbp+1]
0x18000f0d8  mov     [rsp+78h+DriverCancel], r15
0x18000f0dd  mov     dl, 5
0x18000f0df  call    WPP_RECORDER_SF_
0x18000f0e4  cmp     [rbx+358h], rbp
0x18000f0eb  jz      loc_18000F17C
0x18000f0f1  cmp     [rbx+2C8h], bpl
0x18000f0f8  jnz     short loc_18000F138
0x18000f0fa  cmp     [rbx+2CCh], ebp
0x18000f100  jz      short loc_18000F138
0x18000f102  cmp     [rdi+30h], ebp
0x18000f105  jl      short loc_18000F138
0x18000f107  lea     rcx, [rbx+300h]; QueueHead
0x18000f10e  mov     [rsp+78h+DriverCancel], rbp; DriverCancel
0x18000f113  lea     rdx, [rcx+10h]; SpinLock
0x18000f117  xor     r9d, r9d; ListLocation
0x18000f11a  mov     r8, rdi; Irp
0x18000f11d  call    KsAddIrpToCancelableQueue
0x18000f122  mov     rcx, [rbx+348h]; Worker
0x18000f129  call    KsIncrementCountedWorker
0x18000f12e  mov     eax, 103h
0x18000f133  mov     rcx, rbp
0x18000f136  jmp     short loc_18000F177
0x18000f138  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000f13f  jz      short loc_18000F16E
0x18000f141  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f148  cmp     [rcx+48h], bp
0x18000f14c  jz      short loc_18000F16E
0x18000f14e  mov     rcx, [rcx+40h]
0x18000f152  mov     r9d, 35h ; '5'
0x18000f158  mov     [rsp+78h+var_48], rdi
0x18000f15d  mov     dl, 5
0x18000f15f  mov     [rsp+78h+var_50], rbx
0x18000f164  mov     [rsp+78h+DriverCancel], r15
0x18000f169  call    WPP_RECORDER_SF_qq
0x18000f16e  mov     rcx, [rbx+2B8h]
0x18000f175  mov     eax, ebp
0x18000f177  mov     [rsi], rcx
0x18000f17a  jmp     short loc_18000F1C3
0x18000f17c  mov     rax, [rdi+0B8h]
0x18000f183  xor     edx, edx; PriorityBoost
0x18000f185  mov     ecx, [rax+8]
0x18000f188  mov     [rdi+38h], rcx
0x18000f18c  mov     rcx, rdi; Irp
0x18000f18f  call    cs:__imp_IofCompleteRequest
0x18000f196  nop     dword ptr [rax+rax+00h]
0x18000f19b  mov     [rsi], rbp
0x18000f19e  test    byte ptr cs:WPP_MAIN_CB.Dpc.SystemArgument1, 2
0x18000f1a5  jz      short loc_18000F1B6
0x18000f1a7  xor     r9d, r9d
0x18000f1aa  lea     rdx, KS_StreamingRequest_Stop
0x18000f1b1  call    McTemplateK0p_EtwWriteTransfer
0x18000f1b6  mov     rcx, rbx; this
0x18000f1b9  call    ?DecrementIrpCirculation@CKsPin@@AEAAXXZ; CKsPin::DecrementIrpCirculation(void)
0x18000f1be  mov     eax, 103h
0x18000f1c3  add     rsp, 48h
0x18000f1c7  pop     r15
0x18000f1c9  pop     r14
0x18000f1cb  pop     rdi
0x18000f1cc  pop     rsi
0x18000f1cd  pop     rbp
0x18000f1ce  pop     rbx
0x18000f1cf  retn
```
