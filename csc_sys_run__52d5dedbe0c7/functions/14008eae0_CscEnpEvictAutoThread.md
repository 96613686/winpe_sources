# CscEnpEvictAutoThread

- ea: `0x14008eae0`
- end: `0x14008ecf3`
- name: `CscEnpEvictAutoThread`
- size: `531`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x140018930`
- `0x1400190ec`
- `0x140019510`
- `0x14001b5bc`
- `0x14002f010`
- `0x14005888c`
- `0x14008dd14`
- `0x14008eae0`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x14008ebc3`
- `ntoskrnl!KeResetEvent` at `0x14008ec0e`
- `ntoskrnl!KeResetEvent` at `0x14008ebc3`
- `ntoskrnl!KeResetEvent` at `0x14008ec0e`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14008ec79`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14008ec79`

## pseudocode

```c
__int64 __fastcall CscEnpEvictAutoThread(__int64 a1)
{
  union _LARGE_INTEGER *Timeout; // rsi
  struct _KEVENT *v3; // rax
  unsigned int v4; // r14d
  __int64 v5; // rcx
  int v6; // eax
  int v7; // ebx
  NTSTATUS v8; // ebx
  __int64 v10; // [rsp+40h] [rbp-40h] BYREF
  union _LARGE_INTEGER *v11; // [rsp+48h] [rbp-38h] BYREF
  __int64 v12; // [rsp+50h] [rbp-30h] BYREF
  PVOID Object; // [rsp+58h] [rbp-28h] BYREF
  PRKEVENT Event; // [rsp+60h] [rbp-20h]
  PRKEVENT v15; // [rsp+68h] [rbp-18h]

  v12 = a1;
  Object = &g_CscEnEvictState;
  Timeout = 0;
  Event = *(PRKEVENT *)(a1 + 32);
  v15 = 0;
  v10 = 0;
  v11 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      34,
      WPP_2dc78ab1835d3a2b6a689c5f087f77ec_Traceguids,
      a1,
      *(_QWORD *)(a1 + 8),
      *(_DWORD *)(a1 + 24));
  v3 = *(struct _KEVENT **)(a1 + 8);
  if ( v3 )
  {
    v4 = 1;
  }
  else
  {
    Timeout = (union _LARGE_INTEGER *)&v10;
    v5 = -10000000LL * *(unsigned int *)(a1 + 24);
    v11 = (union _LARGE_INTEGER *)&v10;
    v4 = 2;
    v10 = v5;
    v3 = *(struct _KEVENT **)(a1 + 16);
  }
  v15 = v3;
  while ( 1 )
  {
    v8 = KeWaitForMultipleObjects(3u, &Object, WaitAny, Executive, 0, 0, Timeout, 0);
    if ( v8 <= 0 )
      break;
    if ( v8 == 1 )
      KeResetEvent(Event);
    if ( v4 == 1 )
    {
      v6 = CscEnpEvictAutocacheFiles(*(_QWORD *)a1, v8 == 1, (__int64 **)&v11, &v10);
      Timeout = v11;
    }
    else
    {
      v6 = CscEnpEvictManualcacheFiles(*(_QWORD *)a1, v8 == 1, Timeout);
    }
    v7 = v6;
    KeResetEvent(v15);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_2dc78ab1835d3a2b6a689c5f087f77ec_Traceguids, v4, v7);
    }
  }
  CscEnpEvictMemFree(&v12);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_2dc78ab1835d3a2b6a689c5f087f77ec_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14008eae0  mov     [rsp-18h+arg_8], rbx
0x14008eae5  mov     [rsp-18h+arg_10], rsi
0x14008eaea  push    rbp
0x14008eaeb  push    rdi
0x14008eaec  push    r14
0x14008eaee  mov     rbp, rsp
0x14008eaf1  sub     rsp, 80h
0x14008eaf8  mov     rax, cs:__security_cookie
0x14008eaff  xor     rax, rsp
0x14008eb02  mov     [rbp+var_10], rax
0x14008eb06  lea     rax, g_CscEnEvictState
0x14008eb0d  mov     [rbp+var_30], rcx
0x14008eb11  mov     [rbp+Object], rax
0x14008eb15  xor     esi, esi
0x14008eb17  mov     rax, [rcx+20h]
0x14008eb1b  mov     rdi, rcx
0x14008eb1e  mov     [rbp+Event], rax
0x14008eb22  mov     [rbp+var_18], 0
0x14008eb2a  mov     [rbp+var_40], 0
0x14008eb32  mov     [rbp+var_38], rsi
0x14008eb36  mov     rcx, cs:WPP_GLOBAL_Control
0x14008eb3d  lea     rax, WPP_GLOBAL_Control
0x14008eb44  cmp     rcx, rax
0x14008eb47  jz      short loc_14008EB78
0x14008eb49  test    dword ptr [rcx+2Ch], 20000h
0x14008eb50  jz      short loc_14008EB78
0x14008eb52  mov     eax, [rdi+18h]
0x14008eb55  lea     edx, [rsi+22h]
0x14008eb58  mov     rcx, [rcx+18h]
0x14008eb5c  lea     r8, WPP_2dc78ab1835d3a2b6a689c5f087f77ec_Traceguids
0x14008eb63  mov     dword ptr [rsp+80h+Alertable], eax
0x14008eb67  mov     r9, rdi
0x14008eb6a  mov     rax, [rdi+8]
0x14008eb6e  mov     qword ptr [rsp+80h+WaitMode], rax
0x14008eb73  call    WPP_SF_qqD
0x14008eb78  mov     rax, [rdi+8]
0x14008eb7c  test    rax, rax
0x14008eb7f  jz      short loc_14008EB89
0x14008eb81  mov     r14d, 1
0x14008eb87  jmp     short loc_14008EBA9
0x14008eb89  mov     eax, [rdi+18h]
0x14008eb8c  lea     rsi, [rbp+var_40]
0x14008eb90  imul    rcx, rax, 0FFFFFFFFFF676980h
0x14008eb97  mov     [rbp+var_38], rsi
0x14008eb9b  mov     r14d, 2
0x14008eba1  mov     [rbp+var_40], rcx
0x14008eba5  mov     rax, [rdi+10h]
0x14008eba9  mov     [rbp+var_18], rax
0x14008ebad  jmp     loc_14008EC52
0x14008ebb2  test    ebx, ebx
0x14008ebb4  js      loc_14008EC8F
0x14008ebba  cmp     ebx, 1
0x14008ebbd  jnz     short loc_14008EBCF
0x14008ebbf  mov     rcx, [rbp+Event]; Event
0x14008ebc3  call    cs:__imp_KeResetEvent
0x14008ebca  nop     dword ptr [rax+rax+00h]
0x14008ebcf  mov     ecx, r14d
0x14008ebd2  sub     ecx, 1
0x14008ebd5  jz      short loc_14008EBEE
0x14008ebd7  cmp     ecx, 1
0x14008ebda  jnz     short loc_14008EC0A
0x14008ebdc  cmp     ebx, ecx
0x14008ebde  mov     r8, rsi
0x14008ebe1  mov     rcx, [rdi]
0x14008ebe4  setz    dl
0x14008ebe7  call    CscEnpEvictManualcacheFiles
0x14008ebec  jmp     short loc_14008EC08
0x14008ebee  mov     rcx, [rdi]
0x14008ebf1  lea     r9, [rbp+var_40]
0x14008ebf5  cmp     ebx, 1
0x14008ebf8  lea     r8, [rbp+var_38]
0x14008ebfc  setz    dl
0x14008ebff  call    CscEnpEvictAutocacheFiles
0x14008ec04  mov     rsi, [rbp+var_38]
0x14008ec08  mov     ebx, eax
0x14008ec0a  mov     rcx, [rbp+var_18]; Event
0x14008ec0e  call    cs:__imp_KeResetEvent
0x14008ec15  nop     dword ptr [rax+rax+00h]
0x14008ec1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ec21  lea     rax, WPP_GLOBAL_Control
0x14008ec28  cmp     rcx, rax
0x14008ec2b  jz      short loc_14008EC52
0x14008ec2d  test    dword ptr [rcx+2Ch], 20000h
0x14008ec34  jz      short loc_14008EC52
0x14008ec36  mov     rcx, [rcx+18h]
0x14008ec3a  lea     r8, WPP_2dc78ab1835d3a2b6a689c5f087f77ec_Traceguids
0x14008ec41  mov     edx, 23h ; '#'
0x14008ec46  mov     dword ptr [rsp+80h+WaitMode], ebx
0x14008ec4a  mov     r9d, r14d
0x14008ec4d  call    WPP_SF_Dd
0x14008ec52  xor     r9d, r9d; WaitReason
0x14008ec55  mov     [rsp+80h+WaitBlockArray], 0; WaitBlockArray
0x14008ec5e  mov     [rsp+80h+Timeout], rsi; Timeout
0x14008ec63  lea     rdx, [rbp+Object]; Object
0x14008ec67  mov     [rsp+80h+Alertable], 0; Alertable
0x14008ec6c  mov     [rsp+80h+WaitMode], 0; WaitMode
0x14008ec71  lea     r8d, [r9+1]; WaitType
0x14008ec75  lea     ecx, [r9+3]; Count
0x14008ec79  call    cs:__imp_KeWaitForMultipleObjects
0x14008ec80  nop     dword ptr [rax+rax+00h]
0x14008ec85  mov     ebx, eax
0x14008ec87  test    eax, eax
0x14008ec89  jnz     loc_14008EBB2
0x14008ec8f  lea     rcx, [rbp+var_30]
0x14008ec93  call    CscEnpEvictMemFree
0x14008ec98  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ec9f  lea     rax, WPP_GLOBAL_Control
0x14008eca6  cmp     rcx, rax
0x14008eca9  jz      short loc_14008ECCC
0x14008ecab  test    dword ptr [rcx+2Ch], 20000h
0x14008ecb2  jz      short loc_14008ECCC
0x14008ecb4  mov     rcx, [rcx+18h]
0x14008ecb8  lea     r8, WPP_2dc78ab1835d3a2b6a689c5f087f77ec_Traceguids
0x14008ecbf  mov     edx, 24h ; '$'
0x14008ecc4  mov     r9d, ebx
0x14008ecc7  call    WPP_SF_d
0x14008eccc  mov     eax, ebx
0x14008ecce  mov     rcx, [rbp+var_10]
0x14008ecd2  xor     rcx, rsp; StackCookie
0x14008ecd5  call    __security_check_cookie
0x14008ecda  lea     r11, [rsp+80h+var_s0]
0x14008ece2  mov     rbx, [r11+28h]
0x14008ece6  mov     rsi, [r11+30h]
0x14008ecea  mov     rsp, r11
0x14008eced  pop     r14
0x14008ecef  pop     rdi
0x14008ecf0  pop     rbp
0x14008ecf1  retn
```
