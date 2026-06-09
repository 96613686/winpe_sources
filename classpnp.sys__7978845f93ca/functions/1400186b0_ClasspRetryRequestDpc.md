# ClasspRetryRequestDpc

- ea: `0x1400186b0`
- end: `0x1400188ab`
- name: `ClasspRetryRequestDpc`
- size: `507`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400186b0`
- `0x14001fb58`
- `0x14001fc38`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14001880c`
- `ntoskrnl!IofCallDriver` at `0x14001880c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400186ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400186ef`
- `ntoskrnl!IoClearActivityIdThread` at `0x140018873`
- `ntoskrnl!IoClearActivityIdThread` at `0x140018873`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400187cd`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400187cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001874e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001874e`
- `ntoskrnl!IofCompleteRequest` at `0x14001885d`
- `ntoskrnl!IofCompleteRequest` at `0x14001885d`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1400187ed`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1400187ed`

## pseudocode

```c
void __fastcall ClasspRetryRequestDpc(
        struct _KDPC *Dpc,
        _QWORD *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  __int64 v4; // r14
  _QWORD *v5; // rbx
  KIRQL v6; // bp
  _QWORD *v7; // rdi
  char v8; // si
  IRP *v9; // rbx
  _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  _IO_SECURITY_CONTEXT *SecurityContext; // rax
  __int128 *v12; // [rsp+20h] [rbp-48h] BYREF
  __int128 v13; // [rsp+28h] [rbp-40h] BYREF
  __int128 v14; // [rsp+38h] [rbp-30h] BYREF

  if ( DeferredContext )
  {
    v4 = DeferredContext[8];
    v5 = *(_QWORD **)(v4 + 1144);
    v6 = KeAcquireSpinLockRaiseToDpc(v5 + 171);
    if ( MEMORY[0xFFFFF78000000320] >= v5[168] )
    {
      v7 = (_QWORD *)v5[169];
      v5[169] = 0;
      v5[167] = 0;
      v5[168] = 0;
    }
    else
    {
      ClasspRetryDpcTimer(v5);
      v7 = 0;
    }
    KeReleaseSpinLock(v5 + 171, v6);
    while ( v7 )
    {
      v12 = &v14;
      v13 = 0;
      v8 = 0;
      v9 = (IRP *)(v7 - 15);
      v14 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 192, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, v7 - 15);
      }
      v7 = (_QWORD *)*v7;
      if ( (int)IoGetActivityIdIrp(v9, &v13) >= 0 )
      {
        v8 = 1;
        IoPropagateActivityIdToThread(v9, &v13, &v12);
      }
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 108), 1, 1) )
      {
        CurrentStackLocation = v9->Tail.Overlay.CurrentStackLocation;
        --v9->CurrentLocation;
        v9->Tail.Overlay.CurrentStackLocation = CurrentStackLocation - 1;
        if ( CurrentStackLocation[-1].MajorFunction == 15 )
        {
          SecurityContext = CurrentStackLocation[-1].Parameters.Create.SecurityContext;
          if ( SecurityContext )
            BYTE3(SecurityContext->SecurityQos) = 8;
        }
        CurrentStackLocation[-1].Parameters.CreatePipe.Parameters = 0;
        v9->IoStatus.Status = -1073741810;
        v9->IoStatus.Information = 0;
        IofCompleteRequest(v9, 0);
      }
      else
      {
        IofCallDriver(*(PDEVICE_OBJECT *)(v4 + 16), v9);
      }
      if ( v8 )
        IoClearActivityIdThread(v12);
    }
  }
}

```

## disassembly

```asm
0x1400186b0  test    rdx, rdx
0x1400186b3  jz      locret_1400188A9
0x1400186b9  mov     [rsp+arg_0], rbx
0x1400186be  mov     [rsp+arg_10], rbp
0x1400186c3  push    rsi
0x1400186c4  push    rdi
0x1400186c5  push    r14
0x1400186c7  sub     rsp, 50h
0x1400186cb  mov     rax, cs:__security_cookie
0x1400186d2  xor     rax, rsp
0x1400186d5  mov     [rsp+68h+var_20], rax
0x1400186da  mov     r14, [rdx+40h]
0x1400186de  mov     rbx, [r14+478h]
0x1400186e5  lea     rsi, [rbx+558h]
0x1400186ec  mov     rcx, rsi; SpinLock
0x1400186ef  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400186f6  nop     dword ptr [rax+rax+00h]
0x1400186fb  mov     rdx, 0FFFFF78000000320h
0x140018705  mov     bpl, al
0x140018708  mov     rdx, [rdx]
0x14001870b  cmp     rdx, [rbx+540h]
0x140018712  jge     short loc_140018720
0x140018714  mov     rcx, rbx
0x140018717  call    ClasspRetryDpcTimer
0x14001871c  xor     edi, edi
0x14001871e  jmp     short loc_140018748
0x140018720  mov     rdi, [rbx+548h]
0x140018727  mov     qword ptr [rbx+548h], 0
0x140018732  mov     qword ptr [rbx+538h], 0
0x14001873d  mov     qword ptr [rbx+540h], 0
0x140018748  mov     dl, bpl; NewIrql
0x14001874b  mov     rcx, rsi; SpinLock
0x14001874e  call    cs:__imp_KeReleaseSpinLock
0x140018755  nop     dword ptr [rax+rax+00h]
0x14001875a  test    rdi, rdi
0x14001875d  jz      loc_140018888
0x140018763  mov     ebp, 1
0x140018768  xorps   xmm0, xmm0
0x14001876b  lea     rax, [rsp+68h+var_30]
0x140018770  xorps   xmm1, xmm1
0x140018773  mov     [rsp+68h+var_48], rax
0x140018778  movups  [rsp+68h+var_40], xmm0
0x14001877d  xor     sil, sil
0x140018780  lea     rbx, [rdi-78h]
0x140018784  movups  [rsp+68h+var_30], xmm1
0x140018789  mov     rcx, cs:WPP_GLOBAL_Control
0x140018790  lea     rax, WPP_GLOBAL_Control
0x140018797  cmp     rcx, rax
0x14001879a  jz      short loc_1400187C2
0x14001879c  mov     eax, [rcx+2Ch]
0x14001879f  test    bpl, al
0x1400187a2  jz      short loc_1400187C2
0x1400187a4  cmp     byte ptr [rcx+29h], 4
0x1400187a8  jb      short loc_1400187C2
0x1400187aa  mov     rcx, [rcx+18h]
0x1400187ae  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x1400187b5  mov     edx, 0C0h
0x1400187ba  mov     r9, rbx
0x1400187bd  call    WPP_SF_q
0x1400187c2  mov     rdi, [rdi]
0x1400187c5  lea     rdx, [rsp+68h+var_40]
0x1400187ca  mov     rcx, rbx
0x1400187cd  call    cs:__imp_IoGetActivityIdIrp
0x1400187d4  nop     dword ptr [rax+rax+00h]
0x1400187d9  test    eax, eax
0x1400187db  js      short loc_1400187F9
0x1400187dd  lea     r8, [rsp+68h+var_48]
0x1400187e2  mov     rcx, rbx
0x1400187e5  lea     rdx, [rsp+68h+var_40]
0x1400187ea  mov     sil, bpl
0x1400187ed  call    cs:__imp_IoPropagateActivityIdToThread
0x1400187f4  nop     dword ptr [rax+rax+00h]
0x1400187f9  mov     eax, ebp
0x1400187fb  lock cmpxchg [r14+6Ch], ebp
0x140018801  test    eax, eax
0x140018803  jnz     short loc_14001881A
0x140018805  mov     rcx, [r14+10h]; DeviceObject
0x140018809  mov     rdx, rbx; Irp
0x14001880c  call    cs:__imp_IofCallDriver
0x140018813  nop     dword ptr [rax+rax+00h]
0x140018818  jmp     short loc_140018869
0x14001881a  mov     rcx, [rbx+0B8h]
0x140018821  dec     byte ptr [rbx+43h]
0x140018824  lea     rax, [rcx-48h]
0x140018828  mov     [rbx+0B8h], rax
0x14001882f  cmp     byte ptr [rax], 0Fh
0x140018832  jnz     short loc_140018841
0x140018834  mov     rax, [rcx-40h]
0x140018838  test    rax, rax
0x14001883b  jz      short loc_140018841
0x14001883d  mov     byte ptr [rax+3], 8
0x140018841  mov     qword ptr [rcx-28h], 0
0x140018849  xor     edx, edx; PriorityBoost
0x14001884b  mov     rcx, rbx; Irp
0x14001884e  mov     dword ptr [rbx+30h], 0C000000Eh
0x140018855  mov     qword ptr [rbx+38h], 0
0x14001885d  call    cs:__imp_IofCompleteRequest
0x140018864  nop     dword ptr [rax+rax+00h]
0x140018869  test    sil, sil
0x14001886c  jz      short loc_14001887F
0x14001886e  mov     rcx, [rsp+68h+var_48]
0x140018873  call    cs:__imp_IoClearActivityIdThread
0x14001887a  nop     dword ptr [rax+rax+00h]
0x14001887f  test    rdi, rdi
0x140018882  jnz     loc_140018768
0x140018888  mov     rcx, [rsp+68h+var_20]
0x14001888d  xor     rcx, rsp; StackCookie
0x140018890  call    __security_check_cookie
0x140018895  lea     r11, [rsp+68h+var_18]
0x14001889a  mov     rbx, [r11+20h]
0x14001889e  mov     rbp, [r11+30h]
0x1400188a2  mov     rsp, r11
0x1400188a5  pop     r14
0x1400188a7  pop     rdi
0x1400188a8  pop     rsi
0x1400188a9  retn
```
