# HidpFdoAcquirePoFxPowerReferenceWithTag

- ea: `0x180003b70`
- end: `0x180003f38`
- name: `HidpFdoAcquirePoFxPowerReferenceWithTag`
- size: `968`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003190`
- `0x1800039c0`
- `0x180004c00`
- `0x180006ac8`
- `0x18000ce08`
- `0x180017264`
- `0x180017d70`
- `0x180018d50`

## callees

- `0x180003b70`
- `0x18000ec10`
- `0x180012e6c`
- `0x18001cabc`
- `0x18001e944`
- `0x180024e20`
- `0x180025420`

## import_xrefs

- `ntoskrnl!PoFxActivateComponent` at `0x180003f1d`
- `ntoskrnl!PoFxActivateComponent` at `0x180003f1d`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x180003bc9`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x180003cca`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x180003dd1`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x180003bc9`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x180003cca`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x180003dd1`

## string_xrefs

- `0x180003e72`: `A PoFx reference is being acquired for a reason for which there is already a reference acquired`

## pseudocode

```c
__int64 __fastcall HidpFdoAcquirePoFxPowerReferenceWithTag(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  int IsEnabledDeviceUsageNoInline; // eax
  int v5; // edx
  int v6; // r8d
  int v7; // eax
  int v8; // edx
  bool v9; // r8
  int v10; // r8d

  v2 = a2;
  if ( a2 == 8 )
  {
    IsEnabledDeviceUsageNoInline = Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline();
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 1876)) == 1 )
    {
      if ( IsEnabledDeviceUsageNoInline )
      {
        HidpFdoSleepstudyHelperComponentActiveSafe(a1, a1 + 2160);
      }
      else if ( *(_QWORD *)(a1 + 2160) )
      {
        SleepstudyHelper_ComponentActive();
      }
    }
    LOBYTE(v5) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qLDqDLlll(WPP_GLOBAL_Control->AttachedDevice, v5, v6, *(_QWORD *)(a1 + 672));
    }
  }
  else if ( a2 == 4 )
  {
    v7 = Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline();
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 1872)) == 1 )
    {
      if ( v7 )
      {
        HidpFdoSleepstudyHelperComponentActiveSafe(a1, a1 + 2152);
      }
      else if ( *(_QWORD *)(a1 + 2152) )
      {
        SleepstudyHelper_ComponentActive();
      }
    }
    LOBYTE(v8) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    v9 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType);
    if ( (_BYTE)v8 || v9 )
      WPP_RECORDER_AND_TRACE_SF_qLDDLlll(WPP_GLOBAL_Control->AttachedDevice, v8, v9, *(_QWORD *)(a1 + 672), 5);
  }
  else
  {
    if ( a2 == 16 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 1880));
    }
    else
    {
      if ( (unsigned int)Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( v2 == 1 )
          HidpFdoSleepstudyHelperComponentActiveSafe(a1, a1 + 2168);
      }
      else if ( v2 == 1 && *(_QWORD *)(a1 + 2168) )
      {
        SleepstudyHelper_ComponentActive();
      }
      LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                 && LOWORD(WPP_GLOBAL_Control->DeviceType);
      if ( (_BYTE)a2 || (_BYTE)v10 )
        WPP_RECORDER_AND_TRACE_SF_qLDD(WPP_GLOBAL_Control->AttachedDevice, a2, v10, *(_QWORD *)(a1 + 672));
      _m_prefetchw((const void *)(a1 + 1868));
      if ( (_InterlockedOr((volatile signed __int32 *)(a1 + 1868), v2) & v2) != 0 )
        HidpDbgBreak("A PoFx reference is being acquired for a reason for which there is already a reference acquired");
    }
    LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_qLDDLlll(
        WPP_GLOBAL_Control->AttachedDevice,
        a2,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *(_QWORD *)(a1 + 672),
        4);
  }
  return PoFxActivateComponent(*(_QWORD *)(a1 + 696), 0, 2);
}

```

## disassembly

```asm
0x180003b70  push    rbx
0x180003b72  push    rbp
0x180003b73  push    rsi
0x180003b74  push    rdi
0x180003b75  push    r14
0x180003b77  sub     rsp, 90h
0x180003b7e  mov     r14, r8
0x180003b81  mov     edi, edx
0x180003b83  mov     rbx, rcx
0x180003b86  cmp     edx, 8
0x180003b89  jnz     loc_180003C87
0x180003b8f  call    Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline
0x180003b94  mov     ecx, 1
0x180003b99  lock xadd [rbx+754h], ecx
0x180003ba1  inc     ecx
0x180003ba3  cmp     ecx, 1
0x180003ba6  jnz     short loc_180003BD5
0x180003ba8  test    eax, eax
0x180003baa  jz      short loc_180003BBD
0x180003bac  lea     rdx, [rbx+870h]
0x180003bb3  mov     rcx, rbx
0x180003bb6  call    HidpFdoSleepstudyHelperComponentActiveSafe
0x180003bbb  jmp     short loc_180003BD5
0x180003bbd  mov     rcx, [rbx+870h]
0x180003bc4  test    rcx, rcx
0x180003bc7  jz      short loc_180003BD5
0x180003bc9  call    cs:__imp_SleepstudyHelper_ComponentActive
0x180003bd0  nop     dword ptr [rax+rax+00h]
0x180003bd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bdc  lea     rsi, WPP_GLOBAL_Control
0x180003be3  cmp     rcx, rsi
0x180003be6  jz      short loc_180003BFB
0x180003be8  test    dword ptr [rcx+2Ch], 100h
0x180003bef  jz      short loc_180003BFB
0x180003bf1  cmp     byte ptr [rcx+29h], 4
0x180003bf5  jb      short loc_180003BFB
0x180003bf7  mov     dl, 1
0x180003bf9  jmp     short loc_180003BFD
0x180003bfb  xor     dl, dl
0x180003bfd  lea     rbp, WPP_RECORDER_INITIALIZED
0x180003c04  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180003c0b  setnz   r8b
0x180003c0f  test    dl, dl
0x180003c11  jnz     short loc_180003C1C
0x180003c13  test    r8b, r8b
0x180003c16  jz      loc_180003F0E
0x180003c1c  mov     eax, [rbx+758h]
0x180003c22  mov     r9d, [rbx+74Ch]
0x180003c29  mov     rcx, [rcx+18h]
0x180003c2d  mov     [rsp+0B8h+var_38], eax
0x180003c34  mov     eax, [rbx+754h]
0x180003c3a  mov     [rsp+0B8h+var_40], eax
0x180003c3e  mov     eax, [rbx+750h]
0x180003c44  mov     [rsp+0B8h+var_48], eax
0x180003c48  mov     rax, [rbx]
0x180003c4b  mov     [rsp+0B8h+var_50], r9d
0x180003c50  mov     [rsp+0B8h+var_58], r9d
0x180003c55  mov     r9, [rbx+2A0h]
0x180003c5c  mov     [rsp+0B8h+var_60], r14
0x180003c61  mov     [rsp+0B8h+var_68], 8
0x180003c69  mov     [rsp+0B8h+var_70], 8
0x180003c71  mov     [rsp+0B8h+var_78], rax
0x180003c76  mov     [rsp+0B8h+var_88], 2Eh ; '.'
0x180003c7d  call    WPP_RECORDER_AND_TRACE_SF_qLDqDLlll
0x180003c82  jmp     loc_180003F0E
0x180003c87  cmp     edi, 4
0x180003c8a  jnz     loc_180003D82
0x180003c90  call    Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline
0x180003c95  mov     ecx, 1
0x180003c9a  lock xadd [rbx+750h], ecx
0x180003ca2  inc     ecx
0x180003ca4  cmp     ecx, 1
0x180003ca7  jnz     short loc_180003CD6
0x180003ca9  test    eax, eax
0x180003cab  jz      short loc_180003CBE
0x180003cad  lea     rdx, [rbx+868h]
0x180003cb4  mov     rcx, rbx
0x180003cb7  call    HidpFdoSleepstudyHelperComponentActiveSafe
0x180003cbc  jmp     short loc_180003CD6
0x180003cbe  mov     rcx, [rbx+868h]
0x180003cc5  test    rcx, rcx
0x180003cc8  jz      short loc_180003CD6
0x180003cca  call    cs:__imp_SleepstudyHelper_ComponentActive
0x180003cd1  nop     dword ptr [rax+rax+00h]
0x180003cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cdd  lea     rsi, WPP_GLOBAL_Control
0x180003ce4  cmp     rcx, rsi
0x180003ce7  jz      short loc_180003CFC
0x180003ce9  test    dword ptr [rcx+2Ch], 100h
0x180003cf0  jz      short loc_180003CFC
0x180003cf2  cmp     byte ptr [rcx+29h], 5
0x180003cf6  jb      short loc_180003CFC
0x180003cf8  mov     dl, 1
0x180003cfa  jmp     short loc_180003CFE
0x180003cfc  xor     dl, dl
0x180003cfe  lea     rbp, WPP_RECORDER_INITIALIZED
0x180003d05  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180003d0c  jz      short loc_180003D1A
0x180003d0e  cmp     word ptr [rcx+48h], 0
0x180003d13  jz      short loc_180003D1A
0x180003d15  mov     r8b, 1
0x180003d18  jmp     short loc_180003D1D
0x180003d1a  xor     r8b, r8b
0x180003d1d  test    dl, dl
0x180003d1f  jnz     short loc_180003D2A
0x180003d21  test    r8b, r8b
0x180003d24  jz      loc_180003F0E
0x180003d2a  mov     eax, [rbx+758h]
0x180003d30  mov     r9d, [rbx+74Ch]
0x180003d37  mov     [rsp+0B8h+var_40], eax
0x180003d3b  mov     eax, [rbx+754h]
0x180003d41  mov     [rsp+0B8h+var_48], eax
0x180003d45  mov     eax, [rbx+750h]
0x180003d4b  mov     [rsp+0B8h+var_50], eax
0x180003d4f  mov     rax, [rbx]
0x180003d52  mov     [rsp+0B8h+var_58], r9d
0x180003d57  mov     dword ptr [rsp+0B8h+var_60], r9d
0x180003d5c  mov     [rsp+0B8h+var_68], 4
0x180003d64  mov     [rsp+0B8h+var_70], 4
0x180003d6c  mov     [rsp+0B8h+var_78], rax
0x180003d71  mov     [rsp+0B8h+var_88], 2Fh ; '/'
0x180003d78  mov     [rsp+0B8h+var_98], 5
0x180003d7d  jmp     loc_180003EFE
0x180003d82  lea     rsi, WPP_GLOBAL_Control
0x180003d89  lea     rbp, WPP_RECORDER_INITIALIZED
0x180003d90  cmp     edi, 10h
0x180003d93  jnz     short loc_180003DA1
0x180003d95  lock inc dword ptr [rcx+758h]
0x180003d9c  jmp     loc_180003E7E
0x180003da1  call    Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline
0x180003da6  test    eax, eax
0x180003da8  jz      short loc_180003DC0
0x180003daa  cmp     edi, 1
0x180003dad  jnz     short loc_180003DDD
0x180003daf  lea     rdx, [rbx+878h]
0x180003db6  mov     rcx, rbx
0x180003db9  call    HidpFdoSleepstudyHelperComponentActiveSafe
0x180003dbe  jmp     short loc_180003DDD
0x180003dc0  cmp     edi, 1
0x180003dc3  jnz     short loc_180003DDD
0x180003dc5  mov     rcx, [rbx+878h]
0x180003dcc  test    rcx, rcx
0x180003dcf  jz      short loc_180003DDD
0x180003dd1  call    cs:__imp_SleepstudyHelper_ComponentActive
0x180003dd8  nop     dword ptr [rax+rax+00h]
0x180003ddd  mov     rcx, cs:WPP_GLOBAL_Control
0x180003de4  cmp     rcx, rsi
0x180003de7  jz      short loc_180003DFC
0x180003de9  test    dword ptr [rcx+2Ch], 100h
0x180003df0  jz      short loc_180003DFC
0x180003df2  cmp     byte ptr [rcx+29h], 5
0x180003df6  jb      short loc_180003DFC
0x180003df8  mov     dl, 1
0x180003dfa  jmp     short loc_180003DFE
0x180003dfc  xor     dl, dl
0x180003dfe  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180003e05  jz      short loc_180003E13
0x180003e07  cmp     word ptr [rcx+48h], 0
0x180003e0c  jz      short loc_180003E13
0x180003e0e  mov     r8b, 1
0x180003e11  jmp     short loc_180003E16
0x180003e13  xor     r8b, r8b
0x180003e16  test    dl, dl
0x180003e18  jnz     short loc_180003E1F
0x180003e1a  test    r8b, r8b
0x180003e1d  jz      short loc_180003E50
0x180003e1f  mov     eax, [rbx+74Ch]
0x180003e25  mov     r9, [rbx+2A0h]
0x180003e2c  mov     rcx, [rcx+18h]
0x180003e30  mov     dword ptr [rsp+0B8h+var_60], eax
0x180003e34  mov     rax, [rbx]
0x180003e37  mov     [rsp+0B8h+var_68], edi
0x180003e3b  mov     [rsp+0B8h+var_70], edi
0x180003e3f  mov     [rsp+0B8h+var_78], rax
0x180003e44  mov     [rsp+0B8h+var_88], 2Dh ; '-'
0x180003e4b  call    WPP_RECORDER_AND_TRACE_SF_qLDD
0x180003e50  prefetchw byte ptr [rbx+74Ch]
0x180003e57  mov     eax, [rbx+74Ch]
0x180003e5d  nop     dword ptr [rax]
0x180003e60  mov     ecx, eax
0x180003e62  or      ecx, edi
0x180003e64  lock cmpxchg [rbx+74Ch], ecx
0x180003e6c  jnz     short loc_180003E60
0x180003e6e  test    edi, eax
0x180003e70  jz      short loc_180003E7E
0x180003e72  lea     rcx, aAPofxReference; "A PoFx reference is being acquired for "...
0x180003e79  call    HidpDbgBreak
0x180003e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e85  cmp     rcx, rsi
0x180003e88  jz      short loc_180003E9D
0x180003e8a  test    dword ptr [rcx+2Ch], 100h
0x180003e91  jz      short loc_180003E9D
0x180003e93  cmp     byte ptr [rcx+29h], 4
0x180003e97  jb      short loc_180003E9D
0x180003e99  mov     dl, 1
0x180003e9b  jmp     short loc_180003E9F
0x180003e9d  xor     dl, dl
0x180003e9f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180003ea6  setnz   r8b
0x180003eaa  test    dl, dl
0x180003eac  jnz     short loc_180003EB3
0x180003eae  test    r8b, r8b
0x180003eb1  jz      short loc_180003F0E
0x180003eb3  mov     eax, [rbx+758h]
0x180003eb9  mov     r9d, [rbx+74Ch]
0x180003ec0  mov     [rsp+0B8h+var_40], eax
0x180003ec4  mov     eax, [rbx+754h]
0x180003eca  mov     [rsp+0B8h+var_48], eax
0x180003ece  mov     eax, [rbx+750h]
0x180003ed4  mov     [rsp+0B8h+var_50], eax
0x180003ed8  mov     rax, [rbx]
0x180003edb  mov     [rsp+0B8h+var_58], r9d
0x180003ee0  mov     dword ptr [rsp+0B8h+var_60], r9d
0x180003ee5  mov     [rsp+0B8h+var_68], edi
0x180003ee9  mov     [rsp+0B8h+var_70], edi
0x180003eed  mov     [rsp+0B8h+var_78], rax
0x180003ef2  mov     [rsp+0B8h+var_88], 30h ; '0'
0x180003ef9  mov     [rsp+0B8h+var_98], 4
0x180003efe  mov     r9, [rbx+2A0h]
0x180003f05  mov     rcx, [rcx+18h]
0x180003f09  call    WPP_RECORDER_AND_TRACE_SF_qLDDLlll
0x180003f0e  mov     rcx, [rbx+2B8h]
0x180003f15  xor     edx, edx
0x180003f17  mov     r8d, 2
0x180003f1d  call    cs:__imp_PoFxActivateComponent
0x180003f24  nop     dword ptr [rax+rax+00h]
0x180003f29  add     rsp, 90h
0x180003f30  pop     r14
0x180003f32  pop     rdi
0x180003f33  pop     rsi
0x180003f34  pop     rbp
0x180003f35  pop     rbx
0x180003f36  retn
```
