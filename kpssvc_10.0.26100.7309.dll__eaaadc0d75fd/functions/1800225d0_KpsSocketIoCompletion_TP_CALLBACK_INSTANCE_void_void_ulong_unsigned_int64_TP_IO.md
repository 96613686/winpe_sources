# KpsSocketIoCompletion(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *)

- ea: `0x1800225d0`
- end: `0x1800226ff`
- name: `?KpsSocketIoCompletion@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z`
- size: `303`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, char *Overlapped, ULONG IoResult, ULONG_PTR NumberOfBytesTransferred)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18001ae38`
- `0x18001e494`
- `0x1800223fc`
- `0x1800225d0`
- `0x180022708`
- `0x180022a5c`
- `0x180024be0`
- `0x18002cc3c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800226e7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800226e7`
- `ntdll!RtlEnterCriticalSection` at `0x1800225eb`
- `ntdll!RtlEnterCriticalSection` at `0x1800225eb`

## pseudocode

```c
void __fastcall KpsSocketIoCompletion(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        char *Overlapped,
        ULONG IoResult,
        ULONG_PTR NumberOfBytesTransferred)
{
  struct _KPS_IO *v6; // [rsp+40h] [rbp+20h] BYREF

  v6 = (struct _KPS_IO *)Overlapped;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(Overlapped + 288));
  if ( *((_DWORD *)v6 + 84) )
    KpsCancelTimeoutTimer(v6);
  if ( KpsServiceReady() )
  {
    switch ( *((_DWORD *)v6 + 8) )
    {
      case 8:
        KpsSocketConnectAndSendIoCompletion(IoResult, NumberOfBytesTransferred, &v6);
        break;
      case 9:
        KpsSocketRecvDataLengthIoCompletion(IoResult, NumberOfBytesTransferred, (struct KpsIoLockedRef *)&v6);
        break;
      case 0xA:
        KpsSocketRecvDataIoCompletion(IoResult, NumberOfBytesTransferred, &v6);
        break;
      default:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            136,
            &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
            *((unsigned int *)v6 + 8));
        break;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, IoResult);
  }
  if ( v6 )
  {
    if ( !KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)&v6) )
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v6 + 288));
  }
}

```

## disassembly

```asm
0x1800225d0  mov     [rsp-8+arg_0], rbx
0x1800225d5  push    rbp
0x1800225d6  mov     rbp, rsp
0x1800225d9  sub     rsp, 20h
0x1800225dd  lea     rcx, [r8+120h]; CriticalSection
0x1800225e4  mov     [rbp+arg_10], r8
0x1800225e8  mov     ebx, r9d
0x1800225eb  call    cs:__imp_RtlEnterCriticalSection
0x1800225f2  nop     dword ptr [rax+rax+00h]
0x1800225f7  mov     rcx, [rbp+arg_10]; struct _KPS_IO *
0x1800225fb  cmp     dword ptr [rcx+150h], 0
0x180022602  jz      short loc_180022609
0x180022604  call    ?KpsCancelTimeoutTimer@@YAXPEAU_KPS_IO@@@Z; KpsCancelTimeoutTimer(_KPS_IO *)
0x180022609  call    ?KpsServiceReady@@YAEXZ; KpsServiceReady(void)
0x18002260e  test    al, al
0x180022610  jnz     short loc_18002264D
0x180022612  mov     rcx, cs:WPP_GLOBAL_Control
0x180022619  lea     rax, WPP_GLOBAL_Control
0x180022620  cmp     rcx, rax
0x180022623  jz      loc_1800226C8
0x180022629  test    byte ptr [rcx+1Ch], 4
0x18002262d  jz      loc_1800226C8
0x180022633  mov     rcx, [rcx+10h]
0x180022637  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18002263e  mov     edx, 87h
0x180022643  mov     r9d, ebx
0x180022646  call    WPP_SF_D
0x18002264b  jmp     short loc_1800226C8
0x18002264d  mov     rax, [rbp+arg_10]
0x180022651  mov     r9d, [rax+20h]
0x180022655  mov     ecx, r9d
0x180022658  sub     ecx, 8
0x18002265b  jz      short loc_1800226B9
0x18002265d  sub     ecx, 1
0x180022660  jz      short loc_1800226A8
0x180022662  cmp     ecx, 1
0x180022665  jz      short loc_180022697
0x180022667  mov     rcx, cs:WPP_GLOBAL_Control
0x18002266e  lea     rax, WPP_GLOBAL_Control
0x180022675  cmp     rcx, rax
0x180022678  jz      short loc_1800226C8
0x18002267a  test    byte ptr [rcx+1Ch], 1
0x18002267e  jz      short loc_1800226C8
0x180022680  mov     rcx, [rcx+10h]
0x180022684  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18002268b  mov     edx, 88h
0x180022690  call    WPP_SF_D
0x180022695  jmp     short loc_1800226C8
0x180022697  mov     rdx, [rbp+NumberOfBytesTransferred]; unsigned __int64
0x18002269b  lea     r8, [rbp+arg_10]; struct KpsIoLockedRef *
0x18002269f  mov     ecx, ebx; unsigned int
0x1800226a1  call    ?KpsSocketRecvDataIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z; KpsSocketRecvDataIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)
0x1800226a6  jmp     short loc_1800226C8
0x1800226a8  mov     rdx, [rbp+NumberOfBytesTransferred]; unsigned __int64
0x1800226ac  lea     r8, [rbp+arg_10]; struct KpsIoLockedRef *
0x1800226b0  mov     ecx, ebx; unsigned int
0x1800226b2  call    ?KpsSocketRecvDataLengthIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z; KpsSocketRecvDataLengthIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)
0x1800226b7  jmp     short loc_1800226C8
0x1800226b9  mov     rdx, [rbp+NumberOfBytesTransferred]; unsigned __int64
0x1800226bd  lea     r8, [rbp+arg_10]; struct KpsIoLockedRef *
0x1800226c1  mov     ecx, ebx; unsigned int
0x1800226c3  call    ?KpsSocketConnectAndSendIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z; KpsSocketConnectAndSendIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)
0x1800226c8  cmp     [rbp+arg_10], 0
0x1800226cd  jz      short loc_1800226F3
0x1800226cf  lea     rcx, [rbp+arg_10]; this
0x1800226d3  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x1800226d8  test    al, al
0x1800226da  jnz     short loc_1800226F3
0x1800226dc  mov     rcx, [rbp+arg_10]
0x1800226e0  add     rcx, 120h; CriticalSection
0x1800226e7  call    cs:__imp_RtlLeaveCriticalSection
0x1800226ee  nop     dword ptr [rax+rax+00h]
0x1800226f3  mov     rbx, [rsp+20h+arg_0]
0x1800226f8  add     rsp, 20h
0x1800226fc  pop     rbp
0x1800226fd  retn
```
