# CKsPin::TransferKsIrp(_IRP *,IKsTransport * *)

- ea: `0x18000e9a0`
- end: `0x18000eae1`
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
- `0x18000e9a0`
- `0x180010200`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18000ea9f`
- `ntoskrnl!IofCompleteRequest` at `0x18000ea9f`

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
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
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
            (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
            (char)this,
            (char)v4);
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
      McTemplateK0p_EtwWriteTransfer(v8, KS_StreamingRequest_Stop, v9, 0);
    CKsPin::DecrementIrpCirculation(this);
    return 259;
  }
  return result;
}

```

## disassembly

```asm
0x18000e9a0  push    rbx
0x18000e9a2  push    rbp
0x18000e9a3  push    rsi
0x18000e9a4  push    rdi
0x18000e9a5  push    r14
0x18000e9a7  push    r15
0x18000e9a9  sub     rsp, 48h
0x18000e9ad  mov     rsi, r8
0x18000e9b0  mov     rdi, rdx
0x18000e9b3  mov     rbx, rcx
0x18000e9b6  lea     r14, WPP_RECORDER_INITIALIZED
0x18000e9bd  xor     ebp, ebp
0x18000e9bf  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000e9c6  lea     r15, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x18000e9cd  jz      short loc_18000E9F4
0x18000e9cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9d6  cmp     [rcx+48h], bp
0x18000e9da  jz      short loc_18000E9F4
0x18000e9dc  mov     rcx, [rcx+40h]
0x18000e9e0  lea     r9d, [rbp+34h]
0x18000e9e4  lea     r8d, [rbp+1]
0x18000e9e8  mov     [rsp+78h+DriverCancel], r15
0x18000e9ed  mov     dl, 5
0x18000e9ef  call    WPP_RECORDER_SF_
0x18000e9f4  cmp     [rbx+358h], rbp
0x18000e9fb  jz      loc_18000EA8C
0x18000ea01  cmp     [rbx+2C8h], bpl
0x18000ea08  jnz     short loc_18000EA48
0x18000ea0a  cmp     [rbx+2CCh], ebp
0x18000ea10  jz      short loc_18000EA48
0x18000ea12  cmp     [rdi+30h], ebp
0x18000ea15  jl      short loc_18000EA48
0x18000ea17  lea     rcx, [rbx+300h]; QueueHead
0x18000ea1e  mov     [rsp+78h+DriverCancel], rbp; DriverCancel
0x18000ea23  lea     rdx, [rcx+10h]; SpinLock
0x18000ea27  xor     r9d, r9d; ListLocation
0x18000ea2a  mov     r8, rdi; Irp
0x18000ea2d  call    KsAddIrpToCancelableQueue
0x18000ea32  mov     rcx, [rbx+348h]; Worker
0x18000ea39  call    KsIncrementCountedWorker
0x18000ea3e  mov     eax, 103h
0x18000ea43  mov     rcx, rbp
0x18000ea46  jmp     short loc_18000EA87
0x18000ea48  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000ea4f  jz      short loc_18000EA7E
0x18000ea51  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea58  cmp     [rcx+48h], bp
0x18000ea5c  jz      short loc_18000EA7E
0x18000ea5e  mov     rcx, [rcx+40h]
0x18000ea62  mov     r9d, 35h ; '5'
0x18000ea68  mov     [rsp+78h+var_48], rdi
0x18000ea6d  mov     dl, 5
0x18000ea6f  mov     [rsp+78h+var_50], rbx
0x18000ea74  mov     [rsp+78h+DriverCancel], r15
0x18000ea79  call    WPP_RECORDER_SF_qq
0x18000ea7e  mov     rcx, [rbx+2B8h]
0x18000ea85  mov     eax, ebp
0x18000ea87  mov     [rsi], rcx
0x18000ea8a  jmp     short loc_18000EAD3
0x18000ea8c  mov     rax, [rdi+0B8h]
0x18000ea93  xor     edx, edx; PriorityBoost
0x18000ea95  mov     ecx, [rax+8]
0x18000ea98  mov     [rdi+38h], rcx
0x18000ea9c  mov     rcx, rdi; Irp
0x18000ea9f  call    cs:__imp_IofCompleteRequest
0x18000eaa6  nop     dword ptr [rax+rax+00h]
0x18000eaab  mov     [rsi], rbp
0x18000eaae  test    byte ptr cs:WPP_MAIN_CB.Dpc.SystemArgument1, 2
0x18000eab5  jz      short loc_18000EAC6
0x18000eab7  xor     r9d, r9d
0x18000eaba  lea     rdx, KS_StreamingRequest_Stop
0x18000eac1  call    McTemplateK0p_EtwWriteTransfer
0x18000eac6  mov     rcx, rbx; this
0x18000eac9  call    ?DecrementIrpCirculation@CKsPin@@AEAAXXZ; CKsPin::DecrementIrpCirculation(void)
0x18000eace  mov     eax, 103h
0x18000ead3  add     rsp, 48h
0x18000ead7  pop     r15
0x18000ead9  pop     r14
0x18000eadb  pop     rdi
0x18000eadc  pop     rsi
0x18000eadd  pop     rbp
0x18000eade  pop     rbx
0x18000eadf  retn
```
