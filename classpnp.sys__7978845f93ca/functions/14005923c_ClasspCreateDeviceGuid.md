# ClasspCreateDeviceGuid

- ea: `0x14005923c`
- end: `0x140059400`
- name: `ClasspCreateDeviceGuid`
- size: `452`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400579b4`

## callees

- `0x140001008`
- `0x1400010f8`
- `0x14001fbf4`
- `0x14003e430`
- `0x14005923c`
- `0x140059408`
- `0x140059500`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400592f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400592f1`
- `ntoskrnl!ExUuidCreate` at `0x14005931d`
- `ntoskrnl!ExUuidCreate` at `0x14005931d`

## pseudocode

```c
__int64 __fastcall ClasspCreateDeviceGuid(PDEVICE_OBJECT a1, __int64 a2, __int64 a3)
{
  unsigned __int64 Lock; // rax
  char v4; // di
  PDEVICE_OBJECT v5; // rsi
  UUID *v6; // r14
  bool v7; // zf
  int DeviceSpecificDataForGuid; // ebx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  char v14; // [rsp+30h] [rbp-19h] BYREF
  _BYTE v15[3]; // [rsp+31h] [rbp-18h] BYREF
  ULONG cbInput; // [rsp+34h] [rbp-15h] BYREF
  PVOID P; // [rsp+38h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+40h] [rbp-9h] BYREF
  __int64 v19; // [rsp+60h] [rbp+17h]
  __int64 v20; // [rsp+68h] [rbp+1Fh]
  char *v21; // [rsp+70h] [rbp+27h]
  __int64 v22; // [rsp+78h] [rbp+2Fh]

  Lock = a1[1].DeviceQueue.Lock;
  v4 = 0;
  v5 = a1;
  v6 = (UUID *)(*(_QWORD *)&a1[3].DeviceQueue.Type + 4LL);
  P = 0;
  cbInput = 0;
  v7 = *(_DWORD *)(Lock + 28) == 16;
  v15[0] = 0;
  v14 = 0;
  if ( v7 )
  {
    if ( *(_DWORD *)(Lock + 32) == 32 )
    {
      DeviceSpecificDataForGuid = 0;
      *v6 = *(UUID *)(Lock + 52);
      goto LABEL_16;
    }
    goto LABEL_10;
  }
  DeviceSpecificDataForGuid = ClasspGetDeviceSpecificDataForGuid((__int64)a1, &P, &cbInput, v15, &v14, (__int64)v6);
  if ( DeviceSpecificDataForGuid < 0
    || !v14
    && (DeviceSpecificDataForGuid = ClasspGenerateMD5BasedGuid((PUCHAR)P, cbInput),
        ExFreePoolWithTag(P, 0),
        DeviceSpecificDataForGuid < 0) )
  {
    v4 = v15[0];
LABEL_10:
    DeviceSpecificDataForGuid = ExUuidCreate(v6);
    if ( DeviceSpecificDataForGuid < 0 )
    {
      a1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          273,
          WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
          (unsigned int)DeviceSpecificDataForGuid);
      }
    }
    else
    {
      **(_DWORD **)&v5[3].DeviceQueue.Type |= 2u;
    }
    goto LABEL_16;
  }
  v4 = v15[0];
  if ( v15[0] )
    **(_DWORD **)&v5[3].DeviceQueue.Type |= 4u;
LABEL_16:
  if ( (unsigned int)dword_14004D060 > 5 && (unsigned __int8)tlgKeywordOn(a1, 0x400000000000LL, a3) )
  {
    v12 = *(_QWORD *)&v5[3].DeviceQueue.Type;
    v20 = 16;
    v19 = v12 + 4;
    v21 = &v14;
    v14 = v4;
    v22 = 1;
    tlgWriteTransfer_EtwWriteTransfer(v9, (unsigned __int8 *)&byte_1400486E3, v10, v11, 4u, &v18);
  }
  return (unsigned int)DeviceSpecificDataForGuid;
}

```

## disassembly

```asm
0x14005923c  mov     [rsp-8+arg_8], rbx
0x140059241  mov     [rsp-8+arg_10], rsi
0x140059246  push    rbp
0x140059247  push    rdi
0x140059248  push    r14
0x14005924a  lea     rbp, [rsp-47h]
0x14005924f  sub     rsp, 90h
0x140059256  mov     rax, cs:__security_cookie
0x14005925d  xor     rax, rsp
0x140059260  mov     [rbp+57h+var_20], rax
0x140059264  mov     rax, [rcx+208h]
0x14005926b  xor     dil, dil
0x14005926e  mov     r14, [rcx+490h]
0x140059275  mov     rsi, rcx
0x140059278  add     r14, 4
0x14005927c  mov     [rbp+57h+P], 0
0x140059284  mov     [rbp+57h+cbInput], 0
0x14005928b  cmp     dword ptr [rax+1Ch], 10h
0x14005928f  mov     [rbp+57h+var_6F], dil
0x140059293  mov     [rbp+57h+var_70], dil
0x140059297  jnz     short loc_1400592AF
0x140059299  cmp     dword ptr [rax+20h], 20h ; ' '
0x14005929d  jnz     short loc_14005931A
0x14005929f  movups  xmm0, xmmword ptr [rax+34h]
0x1400592a3  xor     ebx, ebx
0x1400592a5  movdqu  xmmword ptr [r14], xmm0
0x1400592aa  jmp     loc_140059373
0x1400592af  lea     rax, [rbp+57h+var_70]
0x1400592b3  mov     [rsp+0A0h+var_78], r14
0x1400592b8  lea     r9, [rbp+57h+var_6F]
0x1400592bc  mov     qword ptr [rsp+0A0h+var_80], rax
0x1400592c1  lea     r8, [rbp+57h+cbInput]
0x1400592c5  lea     rdx, [rbp+57h+P]
0x1400592c9  call    ClasspGetDeviceSpecificDataForGuid
0x1400592ce  mov     ebx, eax
0x1400592d0  test    eax, eax
0x1400592d2  js      short loc_140059316
0x1400592d4  cmp     [rbp+57h+var_70], dil
0x1400592d8  jnz     short loc_140059301
0x1400592da  mov     edx, [rbp+57h+cbInput]; cbInput
0x1400592dd  mov     r8, r14
0x1400592e0  mov     rcx, [rbp+57h+P]; pbInput
0x1400592e4  call    ClasspGenerateMD5BasedGuid
0x1400592e9  mov     rcx, [rbp+57h+P]; P
0x1400592ed  xor     edx, edx; Tag
0x1400592ef  mov     ebx, eax
0x1400592f1  call    cs:__imp_ExFreePoolWithTag
0x1400592f8  nop     dword ptr [rax+rax+00h]
0x1400592fd  test    ebx, ebx
0x1400592ff  js      short loc_140059316
0x140059301  mov     dil, [rbp+57h+var_6F]
0x140059305  test    dil, dil
0x140059308  jz      short loc_140059373
0x14005930a  mov     rax, [rsi+490h]
0x140059311  or      dword ptr [rax], 4
0x140059314  jmp     short loc_140059373
0x140059316  mov     dil, [rbp+57h+var_6F]
0x14005931a  mov     rcx, r14; Uuid
0x14005931d  call    cs:__imp_ExUuidCreate
0x140059324  nop     dword ptr [rax+rax+00h]
0x140059329  mov     ebx, eax
0x14005932b  test    eax, eax
0x14005932d  js      short loc_14005933B
0x14005932f  mov     rax, [rsi+490h]
0x140059336  or      dword ptr [rax], 2
0x140059339  jmp     short loc_140059373
0x14005933b  mov     rcx, cs:WPP_GLOBAL_Control
0x140059342  lea     rax, WPP_GLOBAL_Control
0x140059349  cmp     rcx, rax
0x14005934c  jz      short loc_140059373
0x14005934e  mov     eax, [rcx+2Ch]
0x140059351  test    al, 2
0x140059353  jz      short loc_140059373
0x140059355  cmp     byte ptr [rcx+29h], 2
0x140059359  jb      short loc_140059373
0x14005935b  mov     rcx, [rcx+18h]
0x14005935f  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140059366  mov     edx, 111h
0x14005936b  mov     r9d, ebx
0x14005936e  call    WPP_SF_d
0x140059373  mov     eax, cs:dword_14004D060
0x140059379  cmp     eax, 5
0x14005937c  jbe     short loc_1400593D9
0x14005937e  mov     rdx, 400000000000h
0x140059388  call    _tlgKeywordOn
0x14005938d  test    al, al
0x14005938f  jz      short loc_1400593D9
0x140059391  mov     rax, [rsi+490h]
0x140059398  lea     rdx, byte_1400486E3; int
0x14005939f  add     rax, 4
0x1400593a3  mov     [rbp+57h+var_38], 10h
0x1400593ab  mov     [rbp+57h+var_40], rax
0x1400593af  lea     rax, [rbp+57h+var_70]
0x1400593b3  mov     [rbp+57h+var_30], rax
0x1400593b7  lea     rax, [rbp+57h+var_60]
0x1400593bb  mov     [rsp+0A0h+var_78], rax; __int64
0x1400593c0  mov     [rsp+0A0h+var_80], 4; ULONG
0x1400593c8  mov     [rbp+57h+var_70], dil
0x1400593cc  mov     [rbp+57h+var_28], 1
0x1400593d4  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400593d9  mov     eax, ebx
0x1400593db  mov     rcx, [rbp+57h+var_20]
0x1400593df  xor     rcx, rsp; StackCookie
0x1400593e2  call    __security_check_cookie
0x1400593e7  lea     r11, [rsp+0A0h+var_10]
0x1400593ef  mov     rbx, [r11+28h]
0x1400593f3  mov     rsi, [r11+30h]
0x1400593f7  mov     rsp, r11
0x1400593fa  pop     r14
0x1400593fc  pop     rdi
0x1400593fd  pop     rbp
0x1400593fe  retn
```
