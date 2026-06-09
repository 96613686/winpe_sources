# OneXGeneratePortCookieEvent

- ea: `0x18000d8d0`
- end: `0x18000dabf`
- name: `OneXGeneratePortCookieEvent`
- size: `495`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180004780`
- `0x180014e50`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000d500`
- `0x18000d8d0`
- `0x180010d40`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x18000d971`
- `MobileNetworking!AllocateMemory` at `0x18000d971`

## string_xrefs

- `0x18000d960`: `OneXCreateEvent`

## pseudocode

```c
__int64 __fastcall OneXGeneratePortCookieEvent(__int64 a1, int a2, __int64 a3)
{
  unsigned int v3; // r15d
  _QWORD *v7; // rcx
  unsigned int v8; // r14d
  unsigned int v9; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  unsigned int v12; // eax
  __int64 v14; // [rsp+60h] [rbp+8h] BYREF

  v3 = *(_DWORD *)(a1 + 20);
  v14 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 79, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  v8 = *(_DWORD *)(a1 + 20);
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
    WPP_SF_(v7[7], 10, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  v9 = AllocateMemory(56, &v14, "OneXCreateEvent", 67);
  v10 = v9;
  if ( !v9 )
  {
    *(_DWORD *)(v14 + 16) = a2;
    *(_DWORD *)(v14 + 32) = 1;
    *(_QWORD *)(v14 + 24) = a1;
    goto LABEL_12;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
LABEL_24:
    OneXDeleteEvent(v14);
    goto LABEL_25;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v8, v9);
LABEL_12:
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v11[7], 12, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v10);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v10 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 1) != 0 )
      WPP_SF_dd(v11[7], 80, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v3, v10);
    goto LABEL_24;
  }
  *(_DWORD *)(v14 + 40) = 2;
  *(_QWORD *)(v14 + 48) = a3;
  v12 = QueueGlobalEvent(v14);
  v10 = v12;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 81, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v3, v12);
    goto LABEL_24;
  }
LABEL_25:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 82, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18000d8d0  mov     [rsp+arg_8], rbx
0x18000d8d5  mov     [rsp+arg_10], rbp
0x18000d8da  push    rsi
0x18000d8db  push    rdi
0x18000d8dc  push    r12
0x18000d8de  push    r14
0x18000d8e0  push    r15
0x18000d8e2  sub     rsp, 30h
0x18000d8e6  mov     r15d, [rcx+14h]
0x18000d8ea  mov     rbp, r8
0x18000d8ed  mov     esi, edx
0x18000d8ef  mov     [rsp+58h+arg_0], 0
0x18000d8f8  mov     rdi, rcx
0x18000d8fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d902  lea     r12, WPP_GLOBAL_Control
0x18000d909  cmp     rcx, r12
0x18000d90c  jz      short loc_18000D933
0x18000d90e  test    dword ptr [rcx+44h], 800h
0x18000d915  jz      short loc_18000D933
0x18000d917  mov     rcx, [rcx+38h]
0x18000d91b  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000d922  mov     edx, 4Fh ; 'O'
0x18000d927  call    WPP_SF_
0x18000d92c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d933  mov     r14d, [rdi+14h]
0x18000d937  cmp     rcx, r12
0x18000d93a  jz      short loc_18000D95A
0x18000d93c  test    dword ptr [rcx+44h], 800h
0x18000d943  jz      short loc_18000D95A
0x18000d945  mov     rcx, [rcx+38h]
0x18000d949  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000d950  mov     edx, 0Ah
0x18000d955  call    WPP_SF_
0x18000d95a  mov     r9d, 43h ; 'C'
0x18000d960  lea     r8, aOnexcreateeven; "OneXCreateEvent"
0x18000d967  lea     rdx, [rsp+58h+arg_0]
0x18000d96c  mov     ecx, 38h ; '8'
0x18000d971  call    cs:__imp_AllocateMemory
0x18000d977  mov     ebx, eax
0x18000d979  test    eax, eax
0x18000d97b  jz      short loc_18000D9B1
0x18000d97d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d984  cmp     rcx, r12
0x18000d987  jz      loc_18000DA6F
0x18000d98d  test    byte ptr [rcx+44h], 1
0x18000d991  jz      short loc_18000D9D5
0x18000d993  mov     rcx, [rcx+38h]
0x18000d997  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000d99e  mov     edx, 0Bh
0x18000d9a3  mov     [rsp+58h+var_38], eax
0x18000d9a7  mov     r9d, r14d
0x18000d9aa  call    WPP_SF_dd
0x18000d9af  jmp     short loc_18000D9CE
0x18000d9b1  mov     rax, [rsp+58h+arg_0]
0x18000d9b6  mov     [rax+10h], esi
0x18000d9b9  mov     rax, [rsp+58h+arg_0]
0x18000d9be  mov     dword ptr [rax+20h], 1
0x18000d9c5  mov     rax, [rsp+58h+arg_0]
0x18000d9ca  mov     [rax+18h], rdi
0x18000d9ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9d5  cmp     rcx, r12
0x18000d9d8  jz      short loc_18000DA02
0x18000d9da  test    dword ptr [rcx+44h], 800h
0x18000d9e1  jz      short loc_18000DA02
0x18000d9e3  mov     rcx, [rcx+38h]
0x18000d9e7  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000d9ee  mov     edx, 0Ch
0x18000d9f3  mov     r9d, ebx
0x18000d9f6  call    WPP_SF_D
0x18000d9fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da02  test    ebx, ebx
0x18000da04  jz      short loc_18000DA1C
0x18000da06  cmp     rcx, r12
0x18000da09  jz      short loc_18000DA6F
0x18000da0b  test    byte ptr [rcx+44h], 1
0x18000da0f  jz      short loc_18000DA6F
0x18000da11  mov     edx, 50h ; 'P'
0x18000da16  mov     [rsp+58h+var_38], ebx
0x18000da1a  jmp     short loc_18000DA5C
0x18000da1c  mov     rax, [rsp+58h+arg_0]
0x18000da21  mov     dword ptr [rax+28h], 2
0x18000da28  mov     rax, [rsp+58h+arg_0]
0x18000da2d  mov     [rax+30h], rbp
0x18000da31  mov     rcx, [rsp+58h+arg_0]
0x18000da36  call    QueueGlobalEvent
0x18000da3b  mov     ebx, eax
0x18000da3d  test    eax, eax
0x18000da3f  jz      short loc_18000DA79
0x18000da41  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da48  cmp     rcx, r12
0x18000da4b  jz      short loc_18000DA6F
0x18000da4d  test    byte ptr [rcx+44h], 1
0x18000da51  jz      short loc_18000DA6F
0x18000da53  mov     edx, 51h ; 'Q'
0x18000da58  mov     [rsp+58h+var_38], eax
0x18000da5c  mov     rcx, [rcx+38h]
0x18000da60  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000da67  mov     r9d, r15d
0x18000da6a  call    WPP_SF_dd
0x18000da6f  mov     rcx, [rsp+58h+arg_0]
0x18000da74  call    OneXDeleteEvent
0x18000da79  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da80  cmp     rcx, r12
0x18000da83  jz      short loc_18000DAA6
0x18000da85  test    dword ptr [rcx+44h], 800h
0x18000da8c  jz      short loc_18000DAA6
0x18000da8e  mov     rcx, [rcx+38h]
0x18000da92  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000da99  mov     edx, 52h ; 'R'
0x18000da9e  mov     r9d, ebx
0x18000daa1  call    WPP_SF_D
0x18000daa6  mov     rbp, [rsp+58h+arg_10]
0x18000daab  mov     eax, ebx
0x18000daad  mov     rbx, [rsp+58h+arg_8]
0x18000dab2  add     rsp, 30h
0x18000dab6  pop     r15
0x18000dab8  pop     r14
0x18000daba  pop     r12
0x18000dabc  pop     rdi
0x18000dabd  pop     rsi
0x18000dabe  retn
```
