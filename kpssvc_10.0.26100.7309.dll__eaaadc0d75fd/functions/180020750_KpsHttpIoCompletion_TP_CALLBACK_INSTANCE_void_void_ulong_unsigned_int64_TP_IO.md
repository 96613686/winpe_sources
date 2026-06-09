# KpsHttpIoCompletion(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *)

- ea: `0x180020750`
- end: `0x1800208d0`
- name: `?KpsHttpIoCompletion@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z`
- size: `384`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, char *Overlapped, ULONG IoResult, ULONG_PTR NumberOfBytesTransferred)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18001ae38`
- `0x18001e494`
- `0x180020610`
- `0x180020750`
- `0x1800208d8`
- `0x180020d0c`
- `0x1800210f4`
- `0x1800215c0`
- `0x1800216f4`
- `0x180024be0`
- `0x18002cc3c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800208b8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800208b8`
- `ntdll!RtlEnterCriticalSection` at `0x18002076b`
- `ntdll!RtlEnterCriticalSection` at `0x18002076b`

## pseudocode

```c
void __fastcall KpsHttpIoCompletion(
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
      case 1:
        KpsHttpReceiveRequestIoCompletion(IoResult, NumberOfBytesTransferred, (LPOVERLAPPED *)&v6);
        break;
      case 2:
        KpsHttpReceiveClientCertIoCompletion(IoResult, NumberOfBytesTransferred, (LPOVERLAPPED *)&v6);
        break;
      case 3:
        KpsHttpSendResponseIoCompletion(IoResult, NumberOfBytesTransferred, (struct KpsIoLockedRef *)&v6);
        break;
      case 4:
        KpsHttpSendPostResponseIoCompletion(IoResult, NumberOfBytesTransferred, (struct KpsIoLockedRef *)&v6);
        break;
      case 5:
        KpsHttpReceiveRequestEntityIoCompletion(IoResult, NumberOfBytesTransferred, (LPOVERLAPPED *)&v6);
        break;
      case 7:
        KpsHttpCancelRequestIoCompletion(IoResult, NumberOfBytesTransferred, (struct KpsIoLockedRef *)&v6);
        break;
      default:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            119,
            &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
            *((unsigned int *)v6 + 8));
        break;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, IoResult);
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
0x180020750  mov     [rsp-8+arg_0], rbx
0x180020755  push    rbp
0x180020756  mov     rbp, rsp
0x180020759  sub     rsp, 20h
0x18002075d  lea     rcx, [r8+120h]; CriticalSection
0x180020764  mov     [rbp+arg_10], r8
0x180020768  mov     ebx, r9d
0x18002076b  call    cs:__imp_RtlEnterCriticalSection
0x180020772  nop     dword ptr [rax+rax+00h]
0x180020777  mov     rcx, [rbp+arg_10]; struct _KPS_IO *
0x18002077b  cmp     dword ptr [rcx+150h], 0
0x180020782  jz      short loc_180020789
0x180020784  call    ?KpsCancelTimeoutTimer@@YAXPEAU_KPS_IO@@@Z; KpsCancelTimeoutTimer(_KPS_IO *)
0x180020789  call    ?KpsServiceReady@@YAEXZ; KpsServiceReady(void)
0x18002078e  test    al, al
0x180020790  jnz     short loc_1800207D0
0x180020792  mov     rcx, cs:WPP_GLOBAL_Control
0x180020799  lea     rax, WPP_GLOBAL_Control
0x1800207a0  cmp     rcx, rax
0x1800207a3  jz      loc_180020899
0x1800207a9  test    byte ptr [rcx+1Ch], 4
0x1800207ad  jz      loc_180020899
0x1800207b3  mov     rcx, [rcx+10h]
0x1800207b7  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x1800207be  mov     edx, 76h ; 'v'
0x1800207c3  mov     r9d, ebx
0x1800207c6  call    WPP_SF_D
0x1800207cb  jmp     loc_180020899
0x1800207d0  mov     rax, [rbp+arg_10]
0x1800207d4  mov     r9d, [rax+20h]
0x1800207d8  mov     ecx, r9d
0x1800207db  sub     ecx, 1
0x1800207de  jz      loc_18002088A
0x1800207e4  sub     ecx, 1
0x1800207e7  jz      loc_180020879
0x1800207ed  sub     ecx, 1
0x1800207f0  jz      short loc_180020868
0x1800207f2  sub     ecx, 1
0x1800207f5  jz      short loc_180020857
0x1800207f7  sub     ecx, 1
0x1800207fa  jz      short loc_180020846
0x1800207fc  cmp     ecx, 2
0x1800207ff  jz      short loc_180020835
0x180020801  mov     rcx, cs:WPP_GLOBAL_Control
0x180020808  lea     rax, WPP_GLOBAL_Control
0x18002080f  cmp     rcx, rax
0x180020812  jz      loc_180020899
0x180020818  test    byte ptr [rcx+1Ch], 1
0x18002081c  jz      short loc_180020899
0x18002081e  mov     rcx, [rcx+10h]
0x180020822  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180020829  mov     edx, 77h ; 'w'
0x18002082e  call    WPP_SF_D
0x180020833  jmp     short loc_180020899
0x180020835  mov     rdx, [rbp+NumberOfBytesTransferred]; unsigned __int64
0x180020839  lea     r8, [rbp+arg_10]; struct KpsIoLockedRef *
0x18002083d  mov     ecx, ebx; unsigned int
0x18002083f  call    ?KpsHttpCancelRequestIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z; KpsHttpCancelRequestIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)
0x180020844  jmp     short loc_180020899
0x180020846  mov     rdx, [rbp+NumberOfBytesTransferred]; unsigned __int64
0x18002084a  lea     r8, [rbp+arg_10]; struct KpsIoLockedRef *
0x18002084e  mov     ecx, ebx; unsigned int
0x180020850  call    ?KpsHttpReceiveRequestEntityIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z; KpsHttpReceiveRequestEntityIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)
0x180020855  jmp     short loc_180020899
0x180020857  mov     rdx, [rbp+NumberOfBytesTransferred]; unsigned __int64
0x18002085b  lea     r8, [rbp+arg_10]; struct KpsIoLockedRef *
0x18002085f  mov     ecx, ebx; unsigned int
0x180020861  call    ?KpsHttpSendPostResponseIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z; KpsHttpSendPostResponseIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)
0x180020866  jmp     short loc_180020899
0x180020868  mov     rdx, [rbp+NumberOfBytesTransferred]; unsigned __int64
0x18002086c  lea     r8, [rbp+arg_10]; struct KpsIoLockedRef *
0x180020870  mov     ecx, ebx; unsigned int
0x180020872  call    ?KpsHttpSendResponseIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z; KpsHttpSendResponseIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)
0x180020877  jmp     short loc_180020899
0x180020879  mov     rdx, [rbp+NumberOfBytesTransferred]; unsigned __int64
0x18002087d  lea     r8, [rbp+arg_10]; struct KpsIoLockedRef *
0x180020881  mov     ecx, ebx; unsigned int
0x180020883  call    ?KpsHttpReceiveClientCertIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z; KpsHttpReceiveClientCertIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)
0x180020888  jmp     short loc_180020899
0x18002088a  mov     rdx, [rbp+NumberOfBytesTransferred]; unsigned __int64
0x18002088e  lea     r8, [rbp+arg_10]; struct KpsIoLockedRef *
0x180020892  mov     ecx, ebx; unsigned int
0x180020894  call    ?KpsHttpReceiveRequestIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z; KpsHttpReceiveRequestIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)
0x180020899  cmp     [rbp+arg_10], 0
0x18002089e  jz      short loc_1800208C4
0x1800208a0  lea     rcx, [rbp+arg_10]; this
0x1800208a4  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x1800208a9  test    al, al
0x1800208ab  jnz     short loc_1800208C4
0x1800208ad  mov     rcx, [rbp+arg_10]
0x1800208b1  add     rcx, 120h; CriticalSection
0x1800208b8  call    cs:__imp_RtlLeaveCriticalSection
0x1800208bf  nop     dword ptr [rax+rax+00h]
0x1800208c4  mov     rbx, [rsp+20h+arg_0]
0x1800208c9  add     rsp, 20h
0x1800208cd  pop     rbp
0x1800208ce  retn
```
