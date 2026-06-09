# TdiAssociateAddress

- ea: `0x140006470`
- end: `0x140006749`
- name: `TdiAssociateAddress`
- size: `729`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003330`
- `0x140003bf4`
- `0x140003cb4`
- `0x140004e58`
- `0x140006470`
- `0x14000b808`
- `0x14001e74c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006539`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000654c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006539`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000654c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006618`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000662b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006618`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000662b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400066ec`
- `ntoskrnl!ObfDereferenceObject` at `0x1400066ec`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400064f7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400064f7`
- `ntoskrnl!IoFileObjectType` at `0x1400064c8`

## string_xrefs

- `0x140006575`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140006590`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140006691`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiAssociateAddress(__int64 a1, __int64 a2, __int64 a3, void **a4)
{
  KPROCESSOR_MODE v8; // r9
  void *v9; // rcx
  int v10; // edx
  NTSTATUS v11; // edi
  PVOID v12; // rcx
  __int64 v13; // rbx
  int v14; // edx
  _QWORD *v15; // rdx
  int v16; // edx
  __int64 v17; // r9
  signed __int32 v19[8]; // [rsp+0h] [rbp-68h] BYREF
  PVOID Object; // [rsp+78h] [rbp+10h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      102,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
  v8 = *(_BYTE *)(a2 + 64);
  v9 = *a4;
  Object = 0;
  v11 = ObReferenceObjectByHandle(v9, 0, (POBJECT_TYPE)IoFileObjectType, v8, &Object, 0);
  if ( v11 >= 0 )
  {
    v12 = Object;
    if ( *((_QWORD *)Object + 4) == 1 )
    {
      v13 = ValidateAndReferenceAddr(a1, *((_QWORD *)Object + 3));
      if ( v13 )
      {
        *(_BYTE *)(a3 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 48));
        *(_BYTE *)(v13 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v13 + 48));
        if ( *(_QWORD *)(a3 + 104) )
        {
          v11 = -1073741256;
        }
        else
        {
          RefObj_AddRefEx(a3 + 24, 1380205633, 2937, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
          RefObj_AddRefEx(v13 + 24, 1313754947, 2938, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_qq(
              WPP_GLOBAL_Control->DeviceExtension,
              v14,
              15,
              103,
              (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
              a3,
              v13);
          *(_QWORD *)(a3 + 104) = v13;
          v15 = *(_QWORD **)(v13 + 128);
          if ( *v15 != v13 + 120 )
            __fastfail(3u);
          v11 = 0;
          *(_QWORD *)(a3 + 296) = v13 + 120;
          *(_QWORD *)(a3 + 304) = v15;
          *v15 = a3 + 296;
          *(_QWORD *)(v13 + 128) = a3 + 296;
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(v13 + 48), *(_BYTE *)(v13 + 56));
        KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 48), *(_BYTE *)(a3 + 56));
        if ( v11 >= 0 )
        {
          _InterlockedOr(v19, 0);
          if ( *(_BYTE *)(v13 + 136) )
          {
            if ( *(_DWORD *)(v13 + 216) )
            {
              if ( _InterlockedIncrement((volatile signed __int32 *)(v13 + 224)) == 1 )
              {
                LOBYTE(v17) = 1;
                v11 = RfcommSetPageScanForAddress(a1, v13, a2, v17);
              }
              else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                WPP_RECORDER_SF_(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v16,
                  15,
                  104,
                  (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
              }
            }
          }
        }
        RefObj_ReleaseEx(v13 + 24, 542134857, 2973, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
        v12 = Object;
        goto LABEL_23;
      }
      v12 = Object;
    }
    v11 = -1073741816;
LABEL_23:
    ObfDereferenceObject(v12);
    Object = 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      15,
      105,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140006470  mov     [rsp+arg_0], rbx
0x140006475  mov     [rsp+arg_10], rbp
0x14000647a  push    rsi
0x14000647b  push    rdi
0x14000647c  push    r12
0x14000647e  push    r14
0x140006480  push    r15
0x140006482  sub     rsp, 40h
0x140006486  mov     rbx, r9
0x140006489  mov     rsi, r8
0x14000648c  mov     r14, rdx
0x14000648f  mov     rbp, rcx
0x140006492  lea     r15, WPP_RECORDER_INITIALIZED
0x140006499  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400064a0  lea     r12, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x1400064a7  jz      short loc_1400064C8
0x1400064a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400064b0  mov     r9d, 66h ; 'f'
0x1400064b6  mov     [rsp+68h+Object], r12
0x1400064bb  mov     rcx, [rcx+40h]
0x1400064bf  lea     r8d, [r9-57h]
0x1400064c3  call    WPP_RECORDER_SF_
0x1400064c8  mov     r8, cs:__imp_IoFileObjectType
0x1400064cf  lea     rax, [rsp+68h+arg_8]
0x1400064d4  mov     r9b, [r14+40h]; AccessMode
0x1400064d8  xor     edx, edx; DesiredAccess
0x1400064da  mov     rcx, [rbx]; Handle
0x1400064dd  mov     [rsp+68h+arg_8], 0
0x1400064e6  mov     r8, [r8]; ObjectType
0x1400064e9  mov     [rsp+68h+HandleInformation], 0; HandleInformation
0x1400064f2  mov     [rsp+68h+Object], rax; Object
0x1400064f7  call    cs:__imp_ObReferenceObjectByHandle
0x1400064fe  nop     dword ptr [rax+rax+00h]
0x140006503  mov     edi, eax
0x140006505  test    eax, eax
0x140006507  js      loc_140006701
0x14000650d  mov     rcx, [rsp+68h+arg_8]
0x140006512  cmp     qword ptr [rcx+20h], 1
0x140006517  jnz     loc_1400066E7
0x14000651d  mov     rdx, [rcx+18h]
0x140006521  mov     rcx, rbp
0x140006524  call    ValidateAndReferenceAddr
0x140006529  mov     rbx, rax
0x14000652c  test    rax, rax
0x14000652f  jz      loc_1400066E2
0x140006535  lea     rcx, [rsi+30h]; SpinLock
0x140006539  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006540  nop     dword ptr [rax+rax+00h]
0x140006545  lea     rcx, [rbx+30h]; SpinLock
0x140006549  mov     [rsi+38h], al
0x14000654c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006553  nop     dword ptr [rax+rax+00h]
0x140006558  mov     [rbx+38h], al
0x14000655b  cmp     qword ptr [rsi+68h], 0
0x140006560  jz      short loc_14000656C
0x140006562  mov     edi, 0C0000238h
0x140006567  jmp     loc_140006611
0x14000656c  lea     rcx, [rsi+18h]
0x140006570  mov     edx, 52444441h
0x140006575  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000657c  mov     r8d, 0B79h
0x140006582  call    RefObj_AddRefEx
0x140006587  lea     rcx, [rbx+18h]
0x14000658b  mov     edx, 4E4E4F43h
0x140006590  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140006597  mov     r8d, 0B7Ah
0x14000659d  call    RefObj_AddRefEx
0x1400065a2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400065a9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400065b0  jz      short loc_1400065E2
0x1400065b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400065b9  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x1400065c0  mov     r9d, 67h ; 'g'
0x1400065c6  mov     [rsp+68h+var_38], rbx
0x1400065cb  mov     [rsp+68h+HandleInformation], rsi
0x1400065d0  mov     [rsp+68h+Object], rax
0x1400065d5  mov     rcx, [rcx+40h]
0x1400065d9  lea     r8d, [r9-58h]
0x1400065dd  call    WPP_RECORDER_SF_qq
0x1400065e2  lea     rcx, [rbx+78h]
0x1400065e6  mov     [rsi+68h], rbx
0x1400065ea  mov     rdx, [rcx+8]
0x1400065ee  cmp     [rdx], rcx
0x1400065f1  jz      short loc_1400065FA
0x1400065f3  mov     ecx, 3
0x1400065f8  int     29h; Win8: RtlFailFast(ecx)
0x1400065fa  lea     rax, [rsi+128h]
0x140006601  xor     edi, edi
0x140006603  mov     [rax], rcx
0x140006606  mov     [rax+8], rdx
0x14000660a  mov     [rdx], rax
0x14000660d  mov     [rcx+8], rax
0x140006611  mov     dl, [rbx+38h]; NewIrql
0x140006614  lea     rcx, [rbx+30h]; SpinLock
0x140006618  call    cs:__imp_KeReleaseSpinLock
0x14000661f  nop     dword ptr [rax+rax+00h]
0x140006624  mov     dl, [rsi+38h]; NewIrql
0x140006627  lea     rcx, [rsi+30h]; SpinLock
0x14000662b  call    cs:__imp_KeReleaseSpinLock
0x140006632  nop     dword ptr [rax+rax+00h]
0x140006637  test    edi, edi
0x140006639  js      short loc_14000667A
0x14000663b  lock or [rsp+68h+var_68], 0
0x140006640  cmp     byte ptr [rbx+88h], 0
0x140006647  jz      short loc_14000667A
0x140006649  mov     eax, [rbx+0D8h]
0x14000664f  test    eax, eax
0x140006651  jz      short loc_14000667A
0x140006653  mov     eax, 1
0x140006658  lock xadd [rbx+0E0h], eax
0x140006660  inc     eax
0x140006662  cmp     eax, 1
0x140006665  jnz     short loc_1400066AA
0x140006667  mov     r9b, al
0x14000666a  mov     r8, r14
0x14000666d  mov     rdx, rbx
0x140006670  mov     rcx, rbp
0x140006673  call    RfcommSetPageScanForAddress
0x140006678  mov     edi, eax
0x14000667a  lea     r15, WPP_RECORDER_INITIALIZED
0x140006681  lea     r12, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140006688  lea     rcx, [rbx+18h]
0x14000668c  mov     edx, 20505249h
0x140006691  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140006698  mov     r8d, 0B9Dh
0x14000669e  call    RefObj_ReleaseEx
0x1400066a3  mov     rcx, [rsp+68h+arg_8]
0x1400066a8  jmp     short loc_1400066EC
0x1400066aa  lea     r15, WPP_RECORDER_INITIALIZED
0x1400066b1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400066b8  jz      short loc_140006681
0x1400066ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400066c1  lea     r12, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x1400066c8  mov     r9d, 68h ; 'h'
0x1400066ce  mov     [rsp+68h+Object], r12
0x1400066d3  mov     rcx, [rcx+40h]
0x1400066d7  lea     r8d, [r9-59h]
0x1400066db  call    WPP_RECORDER_SF_
0x1400066e0  jmp     short loc_140006688
0x1400066e2  mov     rcx, [rsp+68h+arg_8]; Object
0x1400066e7  mov     edi, 0C0000008h
0x1400066ec  call    cs:__imp_ObfDereferenceObject
0x1400066f3  nop     dword ptr [rax+rax+00h]
0x1400066f8  mov     [rsp+68h+arg_8], 0
0x140006701  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140006708  jz      short loc_14000672D
0x14000670a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006711  mov     r9d, 69h ; 'i'
0x140006717  mov     dword ptr [rsp+68h+HandleInformation], edi
0x14000671b  mov     [rsp+68h+Object], r12
0x140006720  mov     rcx, [rcx+40h]
0x140006724  lea     r8d, [r9-5Ah]
0x140006728  call    WPP_RECORDER_SF_d
0x14000672d  lea     r11, [rsp+68h+var_28]
0x140006732  mov     eax, edi
0x140006734  mov     rbx, [r11+30h]
0x140006738  mov     rbp, [r11+40h]
0x14000673c  mov     rsp, r11
0x14000673f  pop     r15
0x140006741  pop     r14
0x140006743  pop     r12
0x140006745  pop     rdi
0x140006746  pop     rsi
0x140006747  retn
```
