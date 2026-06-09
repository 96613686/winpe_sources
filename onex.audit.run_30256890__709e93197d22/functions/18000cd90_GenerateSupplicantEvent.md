# GenerateSupplicantEvent

- ea: `0x18000cd90`
- end: `0x18000cf62`
- name: `GenerateSupplicantEvent`
- size: `466`
- prototype: ``
- caller_count: `17`
- callee_count: `6`
- tags: ``

## callers

- `0x180001ac0`
- `0x180005b00`
- `0x18000ecd0`
- `0x180015f90`
- `0x180017f70`
- `0x18001d654`
- `0x180022960`
- `0x180022f70`
- `0x1800230c0`
- `0x1800232e0`
- `0x180024750`
- `0x180024860`
- `0x180024c40`
- `0x180025280`
- `0x180025430`
- `0x180026194`
- `0x180027158`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000cd90`
- `0x18000cf70`
- `0x180010d40`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x18000ce2c`
- `MobileNetworking!AllocateMemory` at `0x18000ce2c`

## string_xrefs

- `0x18000ce1b`: `OneXCreateEvent`

## pseudocode

```c
__int64 __fastcall GenerateSupplicantEvent(__int64 a1, int a2)
{
  unsigned int v2; // r14d
  _QWORD *v5; // rcx
  unsigned int v6; // ebp
  unsigned int v7; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  unsigned int v10; // eax
  __int64 v12; // [rsp+60h] [rbp+8h] BYREF

  v2 = *(_DWORD *)(a1 + 20);
  v12 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, WPP_c98c90d098d532f46181864aabb10d65_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = *(_DWORD *)(a1 + 20);
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x800) != 0 )
    WPP_SF_(v5[7], 10, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  v7 = AllocateMemory(56, &v12, "OneXCreateEvent", 67);
  v8 = v7;
  if ( !v7 )
  {
    *(_DWORD *)(v12 + 16) = a2;
    *(_DWORD *)(v12 + 32) = 0;
    *(_QWORD *)(v12 + 24) = a1;
    goto LABEL_12;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
LABEL_24:
    OneXDeleteEvent(v12);
    goto LABEL_25;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v6, v7);
LABEL_12:
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v9[7], 12, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v8);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 1) != 0 )
      WPP_SF_dd(v9[7], 19, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v2, v8);
    goto LABEL_24;
  }
  v10 = QueueSupplicantEvent(v12);
  v8 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v2, v10);
    goto LABEL_24;
  }
LABEL_25:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18000cd90  mov     [rsp+arg_8], rbx
0x18000cd95  mov     [rsp+arg_10], rbp
0x18000cd9a  push    rsi
0x18000cd9b  push    rdi
0x18000cd9c  push    r12
0x18000cd9e  push    r14
0x18000cda0  push    r15
0x18000cda2  sub     rsp, 30h
0x18000cda6  mov     r14d, [rcx+14h]
0x18000cdaa  xor     r12d, r12d
0x18000cdad  mov     [rsp+58h+arg_0], r12
0x18000cdb2  mov     esi, edx
0x18000cdb4  mov     rdi, rcx
0x18000cdb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdbe  lea     r15, WPP_GLOBAL_Control
0x18000cdc5  cmp     rcx, r15
0x18000cdc8  jz      short loc_18000CDEF
0x18000cdca  test    dword ptr [rcx+44h], 800h
0x18000cdd1  jz      short loc_18000CDEF
0x18000cdd3  mov     rcx, [rcx+38h]
0x18000cdd7  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000cdde  mov     edx, 12h
0x18000cde3  call    WPP_SF_
0x18000cde8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdef  mov     ebp, [rdi+14h]
0x18000cdf2  cmp     rcx, r15
0x18000cdf5  jz      short loc_18000CE15
0x18000cdf7  test    dword ptr [rcx+44h], 800h
0x18000cdfe  jz      short loc_18000CE15
0x18000ce00  mov     rcx, [rcx+38h]
0x18000ce04  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000ce0b  mov     edx, 0Ah
0x18000ce10  call    WPP_SF_
0x18000ce15  mov     r9d, 43h ; 'C'
0x18000ce1b  lea     r8, aOnexcreateeven; "OneXCreateEvent"
0x18000ce22  lea     rdx, [rsp+58h+arg_0]
0x18000ce27  mov     ecx, 38h ; '8'
0x18000ce2c  call    cs:__imp_AllocateMemory
0x18000ce32  mov     ebx, eax
0x18000ce34  test    eax, eax
0x18000ce36  jz      short loc_18000CE6C
0x18000ce38  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce3f  cmp     rcx, r15
0x18000ce42  jz      loc_18000CF12
0x18000ce48  test    byte ptr [rcx+44h], 1
0x18000ce4c  jz      short loc_18000CE8D
0x18000ce4e  mov     rcx, [rcx+38h]
0x18000ce52  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000ce59  mov     edx, 0Bh
0x18000ce5e  mov     [rsp+58h+var_38], eax
0x18000ce62  mov     r9d, ebp
0x18000ce65  call    WPP_SF_dd
0x18000ce6a  jmp     short loc_18000CE86
0x18000ce6c  mov     rax, [rsp+58h+arg_0]
0x18000ce71  mov     [rax+10h], esi
0x18000ce74  mov     rax, [rsp+58h+arg_0]
0x18000ce79  mov     [rax+20h], r12d
0x18000ce7d  mov     rax, [rsp+58h+arg_0]
0x18000ce82  mov     [rax+18h], rdi
0x18000ce86  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce8d  cmp     rcx, r15
0x18000ce90  jz      short loc_18000CEBA
0x18000ce92  test    dword ptr [rcx+44h], 800h
0x18000ce99  jz      short loc_18000CEBA
0x18000ce9b  mov     rcx, [rcx+38h]
0x18000ce9f  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000cea6  mov     edx, 0Ch
0x18000ceab  mov     r9d, ebx
0x18000ceae  call    WPP_SF_D
0x18000ceb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ceba  test    ebx, ebx
0x18000cebc  jz      short loc_18000CED4
0x18000cebe  cmp     rcx, r15
0x18000cec1  jz      short loc_18000CF12
0x18000cec3  test    byte ptr [rcx+44h], 1
0x18000cec7  jz      short loc_18000CF12
0x18000cec9  mov     edx, 13h
0x18000cece  mov     [rsp+58h+var_38], ebx
0x18000ced2  jmp     short loc_18000CEFF
0x18000ced4  mov     rcx, [rsp+58h+arg_0]
0x18000ced9  call    QueueSupplicantEvent
0x18000cede  mov     ebx, eax
0x18000cee0  test    eax, eax
0x18000cee2  jz      short loc_18000CF1C
0x18000cee4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ceeb  cmp     rcx, r15
0x18000ceee  jz      short loc_18000CF12
0x18000cef0  test    byte ptr [rcx+44h], 1
0x18000cef4  jz      short loc_18000CF12
0x18000cef6  mov     edx, 14h
0x18000cefb  mov     [rsp+58h+var_38], eax
0x18000ceff  mov     rcx, [rcx+38h]
0x18000cf03  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000cf0a  mov     r9d, r14d
0x18000cf0d  call    WPP_SF_dd
0x18000cf12  mov     rcx, [rsp+58h+arg_0]
0x18000cf17  call    OneXDeleteEvent
0x18000cf1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf23  cmp     rcx, r15
0x18000cf26  jz      short loc_18000CF49
0x18000cf28  test    dword ptr [rcx+44h], 800h
0x18000cf2f  jz      short loc_18000CF49
0x18000cf31  mov     rcx, [rcx+38h]
0x18000cf35  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000cf3c  mov     edx, 15h
0x18000cf41  mov     r9d, ebx
0x18000cf44  call    WPP_SF_D
0x18000cf49  mov     rbp, [rsp+58h+arg_10]
0x18000cf4e  mov     eax, ebx
0x18000cf50  mov     rbx, [rsp+58h+arg_8]
0x18000cf55  add     rsp, 30h
0x18000cf59  pop     r15
0x18000cf5b  pop     r14
0x18000cf5d  pop     r12
0x18000cf5f  pop     rdi
0x18000cf60  pop     rsi
0x18000cf61  retn
```
