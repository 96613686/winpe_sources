# GenerateGlobalEvent

- ea: `0x18000e6c0`
- end: `0x18000e87f`
- name: `GenerateGlobalEvent`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000e230`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000d500`
- `0x18000e6c0`
- `0x180010d40`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x18000e758`
- `MobileNetworking!AllocateMemory` at `0x18000e758`

## string_xrefs

- `0x18000e748`: `OneXCreateEvent`

## pseudocode

```c
__int64 __fastcall GenerateGlobalEvent(__int64 a1)
{
  unsigned int v1; // ebp
  _QWORD *v3; // rcx
  unsigned int v4; // esi
  unsigned int v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  unsigned int v8; // eax
  __int64 v10; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_DWORD *)(a1 + 20);
  v10 = 0;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 51, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  v4 = *(_DWORD *)(a1 + 20);
  if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 17) & 0x800) != 0 )
    WPP_SF_(v3[7], 10, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  v5 = AllocateMemory(56, &v10, "OneXCreateEvent", 67);
  v6 = v5;
  if ( !v5 )
  {
    *(_DWORD *)(v10 + 16) = 0;
    *(_DWORD *)(v10 + 32) = 0;
    *(_QWORD *)(v10 + 24) = a1;
    goto LABEL_12;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
LABEL_24:
    OneXDeleteEvent(v10);
    goto LABEL_25;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v4, v5);
LABEL_12:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v7[7], 12, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v6);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 68) & 1) != 0 )
      WPP_SF_dd(v7[7], 52, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v1, v6);
    goto LABEL_24;
  }
  v8 = QueueGlobalEvent(v10);
  v6 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 53, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v1, v8);
    goto LABEL_24;
  }
LABEL_25:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 54, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000e6c0  mov     [rsp+arg_8], rbx
0x18000e6c5  mov     [rsp+arg_10], rbp
0x18000e6ca  push    rsi
0x18000e6cb  push    rdi
0x18000e6cc  push    r13
0x18000e6ce  push    r14
0x18000e6d0  push    r15
0x18000e6d2  sub     rsp, 30h
0x18000e6d6  mov     ebp, [rcx+14h]
0x18000e6d9  mov     rdi, rcx
0x18000e6dc  mov     [rsp+58h+arg_0], 0
0x18000e6e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6ec  lea     r14, WPP_GLOBAL_Control
0x18000e6f3  lea     r15, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000e6fa  mov     r13d, 800h
0x18000e700  cmp     rcx, r14
0x18000e703  jz      short loc_18000E723
0x18000e705  test    [rcx+44h], r13d
0x18000e709  jz      short loc_18000E723
0x18000e70b  mov     rcx, [rcx+38h]
0x18000e70f  mov     edx, 33h ; '3'
0x18000e714  mov     r8, r15
0x18000e717  call    WPP_SF_
0x18000e71c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e723  mov     esi, [rdi+14h]
0x18000e726  cmp     rcx, r14
0x18000e729  jz      short loc_18000E742
0x18000e72b  test    [rcx+44h], r13d
0x18000e72f  jz      short loc_18000E742
0x18000e731  mov     rcx, [rcx+38h]
0x18000e735  mov     edx, 0Ah
0x18000e73a  mov     r8, r15
0x18000e73d  call    WPP_SF_
0x18000e742  mov     r9d, 43h ; 'C'
0x18000e748  lea     r8, aOnexcreateeven; "OneXCreateEvent"
0x18000e74f  lea     rdx, [rsp+58h+arg_0]
0x18000e754  lea     ecx, [r9-0Bh]
0x18000e758  call    cs:__imp_AllocateMemory
0x18000e75e  mov     ebx, eax
0x18000e760  test    eax, eax
0x18000e762  jz      short loc_18000E794
0x18000e764  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e76b  cmp     rcx, r14
0x18000e76e  jz      loc_18000E836
0x18000e774  test    byte ptr [rcx+44h], 1
0x18000e778  jz      short loc_18000E7BC
0x18000e77a  mov     rcx, [rcx+38h]
0x18000e77e  mov     edx, 0Bh
0x18000e783  mov     r9d, esi
0x18000e786  mov     [rsp+58h+var_38], eax
0x18000e78a  mov     r8, r15
0x18000e78d  call    WPP_SF_dd
0x18000e792  jmp     short loc_18000E7B5
0x18000e794  mov     rax, [rsp+58h+arg_0]
0x18000e799  mov     dword ptr [rax+10h], 0
0x18000e7a0  mov     rax, [rsp+58h+arg_0]
0x18000e7a5  mov     dword ptr [rax+20h], 0
0x18000e7ac  mov     rax, [rsp+58h+arg_0]
0x18000e7b1  mov     [rax+18h], rdi
0x18000e7b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7bc  cmp     rcx, r14
0x18000e7bf  jz      short loc_18000E7E2
0x18000e7c1  test    [rcx+44h], r13d
0x18000e7c5  jz      short loc_18000E7E2
0x18000e7c7  mov     rcx, [rcx+38h]
0x18000e7cb  mov     edx, 0Ch
0x18000e7d0  mov     r9d, ebx
0x18000e7d3  mov     r8, r15
0x18000e7d6  call    WPP_SF_D
0x18000e7db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7e2  test    ebx, ebx
0x18000e7e4  jz      short loc_18000E7FC
0x18000e7e6  cmp     rcx, r14
0x18000e7e9  jz      short loc_18000E836
0x18000e7eb  test    byte ptr [rcx+44h], 1
0x18000e7ef  jz      short loc_18000E836
0x18000e7f1  mov     edx, 34h ; '4'
0x18000e7f6  mov     [rsp+58h+var_38], ebx
0x18000e7fa  jmp     short loc_18000E827
0x18000e7fc  mov     rcx, [rsp+58h+arg_0]
0x18000e801  call    QueueGlobalEvent
0x18000e806  mov     ebx, eax
0x18000e808  test    eax, eax
0x18000e80a  jz      short loc_18000E840
0x18000e80c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e813  cmp     rcx, r14
0x18000e816  jz      short loc_18000E836
0x18000e818  test    byte ptr [rcx+44h], 1
0x18000e81c  jz      short loc_18000E836
0x18000e81e  mov     edx, 35h ; '5'
0x18000e823  mov     [rsp+58h+var_38], eax
0x18000e827  mov     rcx, [rcx+38h]
0x18000e82b  mov     r9d, ebp
0x18000e82e  mov     r8, r15
0x18000e831  call    WPP_SF_dd
0x18000e836  mov     rcx, [rsp+58h+arg_0]
0x18000e83b  call    OneXDeleteEvent
0x18000e840  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e847  cmp     rcx, r14
0x18000e84a  jz      short loc_18000E866
0x18000e84c  test    [rcx+44h], r13d
0x18000e850  jz      short loc_18000E866
0x18000e852  mov     rcx, [rcx+38h]
0x18000e856  mov     edx, 36h ; '6'
0x18000e85b  mov     r9d, ebx
0x18000e85e  mov     r8, r15
0x18000e861  call    WPP_SF_D
0x18000e866  mov     rbp, [rsp+58h+arg_10]
0x18000e86b  mov     eax, ebx
0x18000e86d  mov     rbx, [rsp+58h+arg_8]
0x18000e872  add     rsp, 30h
0x18000e876  pop     r15
0x18000e878  pop     r14
0x18000e87a  pop     r13
0x18000e87c  pop     rdi
0x18000e87d  pop     rsi
0x18000e87e  retn
```
