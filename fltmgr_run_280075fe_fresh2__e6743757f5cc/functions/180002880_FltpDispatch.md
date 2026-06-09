# FltpDispatch

- ea: `0x180002880`
- end: `0x180002a2f`
- name: `FltpDispatch`
- size: `431`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002880`
- `0x180002a40`
- `0x180003380`
- `0x180007500`
- `0x180019030`
- `0x1800547d4`
- `0x180060110`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180002909`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180002909`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000293a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000299a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000293a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000299a`
- `ntoskrnl!IofCompleteRequest` at `0x1800029ec`
- `ntoskrnl!IofCompleteRequest` at `0x1800029ec`

## pseudocode

```c
__int64 __fastcall FltpDispatch(PDEVICE_OBJECT DeviceObject, __int64 a2, __int64 a3, __int64 a4)
{
  __int128 Irp; // rax
  IRP *v5; // rsi
  unsigned int v7; // edi
  __int128 v9; // [rsp+20h] [rbp-38h] BYREF
  __m128i si128; // [rsp+30h] [rbp-28h]
  __int128 v11; // [rsp+40h] [rbp-18h]

  *((_QWORD *)&Irp + 1) = a2;
  v9 = 0;
  v5 = (IRP *)*((_QWORD *)&Irp + 1);
  si128 = 0;
  v11 = 0;
  if ( DeviceObject == ::DeviceObject )
    return FltpControlDispatch(DeviceObject, *((_QWORD *)&Irp + 1), a3, a4, v9, *((_QWORD *)&v9 + 1));
  if ( DeviceObject == qword_18003E9B8 )
    return FltpMsgDispatch((__int64)DeviceObject, *((IRP **)&Irp + 1));
  *(_QWORD *)&Irp = DeviceObject->DeviceExtension;
  if ( (_QWORD)Irp && *(_WORD *)Irp == 0xF106 )
  {
    if ( **(_BYTE **)(*((_QWORD *)&Irp + 1) + 184LL) == 16 )
      FltpProcessShutdownRequest(DeviceObject);
    ++v5->CurrentLocation;
    ++v5->Tail.Overlay.CurrentStackLocation;
    return FltpCallDriver(*((PDEVICE_OBJECT *)DeviceObject->DeviceExtension + 1), v5);
  }
  else
  {
    *(_QWORD *)&Irp = *(_QWORD *)(Irp + 80);
    v9 = Irp;
    *(_QWORD *)&v11 = 0;
    DWORD2(v11) = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffff0000000000000000);
    if ( (_QWORD)Irp )
    {
      if ( (*(_DWORD *)(Irp + 56) & 0x40) != 0 || *(_QWORD *)(v9 + 88) && *(_DWORD *)(*(_QWORD *)(v9 + 88) + 2032LL) )
      {
        KeEnterCriticalRegion();
        v7 = FltpPassThrough((LARGE_INTEGER **)&v9);
        if ( (BYTE8(v11) & 4) != 0 )
        {
          v7 = FltpLegacyProcessingAfterPreCallbacksCompleted((__int64)&v9, v7, 0);
        }
        else if ( (BYTE8(v11) & 8) != 0 )
        {
          KeLeaveCriticalRegion();
          ++v5->CurrentLocation;
          ++v5->Tail.Overlay.CurrentStackLocation;
          return FltpCallDriver(*((PDEVICE_OBJECT *)DeviceObject->DeviceExtension + 1), v5);
        }
        KeLeaveCriticalRegion();
        return v7;
      }
      ++*(_BYTE *)(*((_QWORD *)&Irp + 1) + 67LL);
      *(_QWORD *)(*((_QWORD *)&Irp + 1) + 184LL) += 72LL;
      return FltpCallDriver(*((PDEVICE_OBJECT *)DeviceObject->DeviceExtension + 1), *((PIRP *)&Irp + 1));
    }
    else
    {
      *(_QWORD *)(*((_QWORD *)&Irp + 1) + 56LL) = 0;
      *(_DWORD *)(*((_QWORD *)&Irp + 1) + 48LL) = -1073741436;
      IofCompleteRequest(*((PIRP *)&Irp + 1), 0);
      return 3221225860LL;
    }
  }
}

```

## disassembly

```asm
0x180002880  mov     [rsp+arg_8], rbx
0x180002885  push    rsi
0x180002886  sub     rsp, 50h
0x18000288a  cmp     rcx, cs:DeviceObject
0x180002891  xorps   xmm0, xmm0
0x180002894  movups  [rsp+58h+var_38], xmm0
0x180002899  mov     rsi, rdx
0x18000289c  mov     rbx, rcx
0x18000289f  movups  [rsp+58h+var_28], xmm0
0x1800028a4  movups  [rsp+58h+var_18], xmm0
0x1800028a9  jz      loc_1800029D2
0x1800028af  cmp     rcx, cs:qword_18003E9B8
0x1800028b6  jz      loc_180002985
0x1800028bc  mov     rax, [rcx+40h]
0x1800028c0  test    rax, rax
0x1800028c3  jnz     loc_180002959
0x1800028c9  mov     rax, [rax+50h]
0x1800028cd  xor     ecx, ecx
0x1800028cf  movdqa  xmm0, cs:__xmm@ffffffffffffffff0000000000000000
0x1800028d7  mov     qword ptr [rsp+58h+var_38], rax
0x1800028dc  mov     qword ptr [rsp+58h+var_38+8], rsi
0x1800028e1  mov     qword ptr [rsp+58h+var_18], rcx
0x1800028e6  mov     dword ptr [rsp+58h+var_18+8], ecx
0x1800028ea  movdqu  [rsp+58h+var_28], xmm0
0x1800028f0  test    rax, rax
0x1800028f3  jz      loc_1800029DC
0x1800028f9  mov     eax, [rax+38h]
0x1800028fc  test    al, 40h
0x1800028fe  jz      loc_180002A02
0x180002904  mov     [rsp+58h+arg_0], rdi
0x180002909  call    cs:__imp_KeEnterCriticalRegion
0x180002910  nop     dword ptr [rax+rax+00h]
0x180002915  lea     rcx, [rsp+58h+var_38]
0x18000291a  call    FltpPassThrough
0x18000291f  mov     edi, eax
0x180002921  mov     eax, dword ptr [rsp+58h+var_18+8]
0x180002925  test    al, 4
0x180002927  jz      short loc_180002996
0x180002929  xor     r8d, r8d
0x18000292c  lea     rcx, [rsp+58h+var_38]
0x180002931  mov     edx, edi
0x180002933  call    FltpLegacyProcessingAfterPreCallbacksCompleted
0x180002938  mov     edi, eax
0x18000293a  call    cs:__imp_KeLeaveCriticalRegion
0x180002941  nop     dword ptr [rax+rax+00h]
0x180002946  mov     eax, edi
0x180002948  mov     rdi, [rsp+58h+arg_0]
0x18000294d  mov     rbx, [rsp+58h+arg_8]
0x180002952  add     rsp, 50h
0x180002956  pop     rsi
0x180002957  retn
0x180002959  mov     ecx, 0F106h
0x18000295e  cmp     [rax], cx
0x180002961  jnz     loc_1800028C9
0x180002967  mov     rax, [rdx+0B8h]
0x18000296e  cmp     byte ptr [rax], 10h
0x180002971  jnz     loc_1800251FE
0x180002977  mov     rcx, rbx; DeviceObject
0x18000297a  call    FltpProcessShutdownRequest
0x18000297f  nop
0x180002980  jmp     loc_1800251FE
0x180002985  call    FltpMsgDispatch
0x18000298a  mov     rbx, [rsp+58h+arg_8]
0x18000298f  add     rsp, 50h
0x180002993  pop     rsi
0x180002994  retn
0x180002996  test    al, 8
0x180002998  jz      short loc_18000293A
0x18000299a  call    cs:__imp_KeLeaveCriticalRegion
0x1800029a1  nop     dword ptr [rax+rax+00h]
0x1800029a6  inc     byte ptr [rsi+43h]
0x1800029a9  mov     rdx, rsi; Irp
0x1800029ac  add     qword ptr [rsi+0B8h], 48h ; 'H'
0x1800029b4  mov     rcx, [rbx+40h]
0x1800029b8  mov     rcx, [rcx+8]; DeviceObject
0x1800029bc  call    FltpCallDriver
0x1800029c1  mov     rdi, [rsp+58h+arg_0]
0x1800029c6  mov     rbx, [rsp+58h+arg_8]
0x1800029cb  add     rsp, 50h
0x1800029cf  pop     rsi
0x1800029d0  retn
0x1800029d2  call    FltpControlDispatch
0x1800029d7  jmp     loc_18000294D
0x1800029dc  mov     [rdx+38h], rcx
0x1800029e0  mov     rcx, rsi; Irp
0x1800029e3  mov     dword ptr [rdx+30h], 0C0000184h
0x1800029ea  xor     edx, edx; PriorityBoost
0x1800029ec  call    cs:__imp_IofCompleteRequest
0x1800029f3  nop     dword ptr [rax+rax+00h]
0x1800029f8  mov     eax, 0C0000184h
0x1800029fd  jmp     loc_18000294D
0x180002a02  mov     rax, qword ptr [rsp+58h+var_38]
0x180002a07  mov     rcx, [rax+58h]
0x180002a0b  test    rcx, rcx
0x180002a0e  jz      loc_18002521F
0x180002a14  mov     rax, qword ptr [rsp+58h+var_38]
0x180002a19  mov     rcx, [rax+58h]
0x180002a1d  cmp     dword ptr [rcx+7F0h], 0
0x180002a24  jnz     loc_180002904
0x180002a2a  jmp     loc_18002521F
0x1800251fe  inc     byte ptr [rsi+43h]
0x180025201  mov     rdx, rsi; Irp
0x180025204  add     qword ptr [rsi+0B8h], 48h ; 'H'
0x18002520c  mov     rcx, [rbx+40h]
0x180025210  mov     rcx, [rcx+8]; DeviceObject
0x180025214  call    FltpCallDriver
0x180025219  nop
0x18002521a  jmp     loc_18000294D
0x18002521f  inc     byte ptr [rdx+43h]
0x180025222  add     qword ptr [rdx+0B8h], 48h ; 'H'
0x18002522a  mov     rcx, [rbx+40h]
0x18002522e  mov     rcx, [rcx+8]; DeviceObject
0x180025232  call    FltpCallDriver
0x180025237  nop
0x180025238  jmp     loc_18000294D
```
