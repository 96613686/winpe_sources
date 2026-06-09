# HsmpFileCacheFlush

- ea: `0x140006170`
- end: `0x14000635b`
- name: `HsmpFileCacheFlush`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140071fc4`

## callees

- `0x140003c50`
- `0x1400054c0`
- `0x140006170`
- `0x140009300`
- `0x14000d95c`
- `0x14001b85c`
- `0x14001ce90`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x1400061e3`
- `ntoskrnl!CcFlushCache` at `0x1400061e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000620e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ec0a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000620e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ec0a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400061c0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400061c0`

## pseudocode

```c
__int64 __fastcall HsmpFileCacheFlush(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // ebx
  __int64 v6; // r8
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  NTSTATUS Status; // [rsp+40h] [rbp-28h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+48h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, a1, 0, 0);
  }
  v5 = HsmiFileCacheValidateFileObject(a1, 0, 0, a4);
  HsmDbgBreakOnStatus((unsigned int)v5);
  if ( v5 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v9 = 55;
LABEL_20:
      WPP_SF_d(v8->AttachedDevice, v9, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, (unsigned int)v5);
    }
  }
  else
  {
    KeEnterCriticalRegion();
    IoStatus = 0;
    CcFlushCache(*(PSECTION_OBJECT_POINTERS *)(a1 + 40), 0, 0, &IoStatus);
    Status = IoStatus.Status;
    HsmDbgBreakOnStatus((unsigned int)IoStatus.Status);
    KeLeaveCriticalRegion();
    v5 = Status;
    if ( Status >= 0 )
      goto LABEL_4;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v9 = 56;
      goto LABEL_20;
    }
  }
  if ( v5 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qiDd(WPP_GLOBAL_Control->AttachedDevice, 57, v6, a1, 0, 0, v5);
  }
LABEL_4:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140006170  mov     [rsp+arg_8], rbx
0x140006175  mov     [rsp+arg_10], rsi
0x14000617a  mov     [rsp+arg_0], rcx
0x14000617f  push    rdi
0x140006180  sub     rsp, 60h
0x140006184  mov     rsi, rcx
0x140006187  lea     rdi, WPP_GLOBAL_Control
0x14000618e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006195  cmp     rcx, rdi
0x140006198  jnz     loc_14000626F
0x14000619e  xor     r8d, r8d
0x1400061a1  xor     edx, edx
0x1400061a3  mov     rcx, rsi
0x1400061a6  call    HsmiFileCacheValidateFileObject
0x1400061ab  mov     ebx, eax
0x1400061ad  mov     [rsp+68h+var_28], eax
0x1400061b1  mov     ecx, eax
0x1400061b3  call    HsmDbgBreakOnStatus
0x1400061b8  test    ebx, ebx
0x1400061ba  js      loc_1400062B2
0x1400061c0  call    cs:__imp_KeEnterCriticalRegion
0x1400061c7  nop     dword ptr [rax+rax+00h]
0x1400061cc  nop
0x1400061cd  xorps   xmm0, xmm0
0x1400061d0  movups  xmmword ptr [rsp+68h+IoStatus], xmm0
0x1400061d5  lea     r9, [rsp+68h+IoStatus]; IoStatus
0x1400061da  xor     r8d, r8d; Length
0x1400061dd  xor     edx, edx; FileOffset
0x1400061df  mov     rcx, [rsi+28h]; SectionObjectPointer
0x1400061e3  call    cs:__imp_CcFlushCache
0x1400061ea  nop     dword ptr [rax+rax+00h]
0x1400061ef  mov     eax, dword ptr [rsp+68h+IoStatus]
0x1400061f3  mov     [rsp+68h+var_28], eax
0x1400061f7  mov     ecx, [rsp+68h+var_28]
0x1400061fb  call    HsmDbgBreakOnStatus
0x140006200  jmp     short loc_14000620E
0x140006202  lea     rdi, WPP_GLOBAL_Control
0x140006209  mov     rsi, [rsp+68h+arg_0]
0x14000620e  call    cs:__imp_KeLeaveCriticalRegion
0x140006215  nop     dword ptr [rax+rax+00h]
0x14000621a  mov     ebx, [rsp+68h+var_28]
0x14000621e  test    ebx, ebx
0x140006220  js      loc_1400062D2
0x140006226  mov     rcx, cs:WPP_GLOBAL_Control
0x14000622d  cmp     rcx, rdi
0x140006230  jnz     short loc_140006247
0x140006232  mov     eax, ebx
0x140006234  lea     r11, [rsp+68h+var_8]
0x140006239  mov     rbx, [r11+18h]
0x14000623d  mov     rsi, [r11+20h]
0x140006241  mov     rsp, r11
0x140006244  pop     rdi
0x140006245  retn
0x140006247  mov     edx, [rcx+2Ch]
0x14000624a  test    dl, 8
0x14000624d  jz      short loc_140006232
0x14000624f  cmp     byte ptr [rcx+29h], 5
0x140006253  jb      short loc_140006232
0x140006255  mov     edx, 3Ah ; ':'
0x14000625a  mov     r9d, ebx
0x14000625d  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x140006264  mov     rcx, [rcx+18h]
0x140006268  call    WPP_SF_d
0x14000626d  jmp     short loc_140006232
0x14000626f  mov     eax, [rcx+2Ch]
0x140006272  test    al, 8
0x140006274  jz      loc_14000619E
0x14000627a  cmp     byte ptr [rcx+29h], 5
0x14000627e  jb      loc_14000619E
0x140006284  mov     edx, 36h ; '6'
0x140006289  mov     [rsp+68h+var_40], 0
0x140006291  mov     [rsp+68h+var_48], 0
0x14000629a  mov     r9, rsi
0x14000629d  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x1400062a4  mov     rcx, [rcx+18h]
0x1400062a8  call    WPP_SF_qqd
0x1400062ad  jmp     loc_14000619E
0x1400062b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400062b9  cmp     rcx, rdi
0x1400062bc  jz      short loc_140006303
0x1400062be  mov     eax, [rcx+2Ch]
0x1400062c1  test    al, 8
0x1400062c3  jz      short loc_140006303
0x1400062c5  cmp     byte ptr [rcx+29h], 2
0x1400062c9  jb      short loc_140006303
0x1400062cb  mov     edx, 37h ; '7'
0x1400062d0  jmp     short loc_1400062F0
0x1400062d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400062d9  cmp     rcx, rdi
0x1400062dc  jz      short loc_140006303
0x1400062de  mov     eax, [rcx+2Ch]
0x1400062e1  test    al, 8
0x1400062e3  jz      short loc_140006303
0x1400062e5  cmp     byte ptr [rcx+29h], 2
0x1400062e9  jb      short loc_140006303
0x1400062eb  mov     edx, 38h ; '8'
0x1400062f0  mov     r9d, ebx
0x1400062f3  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x1400062fa  mov     rcx, [rcx+18h]
0x1400062fe  call    WPP_SF_d
0x140006303  test    ebx, ebx
0x140006305  jns     loc_140006226
0x14000630b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006312  cmp     rcx, rdi
0x140006315  jz      loc_140006226
0x14000631b  mov     eax, [rcx+2Ch]
0x14000631e  test    al, 8
0x140006320  jz      loc_140006226
0x140006326  cmp     byte ptr [rcx+29h], 2
0x14000632a  jb      loc_140006226
0x140006330  mov     edx, 39h ; '9'
0x140006335  mov     [rsp+68h+var_38], ebx
0x140006339  mov     [rsp+68h+var_40], 0
0x140006341  mov     [rsp+68h+var_48], 0
0x14000634a  mov     r9, rsi
0x14000634d  mov     rcx, [rcx+18h]
0x140006351  call    WPP_SF_qiDd
0x140006356  jmp     loc_140006226
0x14001ebe7  push    rbp
0x14001ebe9  sub     rsp, 40h
0x14001ebed  mov     rbp, rdx
0x14001ebf0  lea     rdx, [rbp+40h]
0x14001ebf4  call    HsmFileCacheExceptionFilter
0x14001ebf9  nop
0x14001ebfa  add     rsp, 40h
0x14001ebfe  pop     rbp
0x14001ebff  retn
0x14001ec01  push    rbp
0x14001ec03  sub     rsp, 40h
0x14001ec07  mov     rbp, rdx
0x14001ec0a  call    cs:__imp_KeLeaveCriticalRegion
0x14001ec11  nop     dword ptr [rax+rax+00h]
0x14001ec16  nop
0x14001ec17  add     rsp, 40h
0x14001ec1b  pop     rbp
0x14001ec1c  retn
```
