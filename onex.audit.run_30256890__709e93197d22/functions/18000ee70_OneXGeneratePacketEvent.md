# OneXGeneratePacketEvent

- ea: `0x18000ee70`
- end: `0x18000f1c7`
- name: `OneXGeneratePacketEvent`
- size: `855`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180006160`
- `0x180026e54`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000cf70`
- `0x18000d500`
- `0x18000ee70`
- `0x180010d40`
- `0x180013440`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!SetBufferAndLength` at `0x18000f092`
- `MobileNetworking!SetBufferAndLength` at `0x18000f092`
- `MobileNetworking!AllocateMemory` at `0x18000ef4a`
- `MobileNetworking!AllocateMemory` at `0x18000ef4a`

## string_xrefs

- `0x18000ef39`: `OneXCreateEvent`

## pseudocode

```c
__int64 __fastcall OneXGeneratePacketEvent(
        unsigned __int16 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        int a6)
{
  unsigned int v8; // ebp
  __int64 v9; // r14
  __int64 v10; // r15
  unsigned int v11; // r13d
  _QWORD *v12; // rcx
  unsigned int v13; // ebp
  unsigned int Memory; // eax
  unsigned int v15; // ebx
  _QWORD *v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v20[2]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v21; // [rsp+90h] [rbp+28h]

  v8 = *(_DWORD *)(a5 + 20);
  v21 = v8;
  v9 = a4;
  v10 = a3;
  v11 = a1;
  v20[0] = 0;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 83, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
  if ( !a6 )
  {
    v17 = OneXCreateEvent((__int64)v20, 35, 3, a5);
    v15 = v17;
    if ( v17 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_42;
      v18 = 85;
      goto LABEL_40;
    }
LABEL_27:
    *(_DWORD *)(v20[0] + 40) = 6;
    v17 = SetBufferAndLength(v20[0] + 48, v20[0] + 44, a2, v11);
    v15 = v17;
    if ( v17 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_42;
      v18 = 86;
      goto LABEL_40;
    }
    *(_DWORD *)(v20[0] + 56) = 2;
    *(_QWORD *)(v20[0] + 64) = v10;
    *(_DWORD *)(v20[0] + 72) = 2;
    *(_QWORD *)(v20[0] + 80) = v9;
    if ( a6 )
    {
      v17 = QueueGlobalEvent(v20[0]);
      v15 = v17;
      if ( v17 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_42;
        v18 = 87;
        goto LABEL_40;
      }
LABEL_44:
      v16 = WPP_GLOBAL_Control;
      goto LABEL_45;
    }
    v17 = QueueSupplicantEvent(v20[0]);
    v15 = v17;
    if ( !v17 )
      goto LABEL_44;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_42;
    v18 = 88;
LABEL_40:
    WPP_SF_dd(v16[7], v18, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v8, v17);
    goto LABEL_41;
  }
  v13 = *(_DWORD *)(a5 + 20);
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x800) != 0 )
    WPP_SF_(v12[7], 10, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  Memory = AllocateMemory(88, v20, "OneXCreateEvent", 67);
  v15 = Memory;
  if ( !Memory )
  {
    *(_DWORD *)(v20[0] + 16) = 6;
    *(_DWORD *)(v20[0] + 32) = 3;
    *(_QWORD *)(v20[0] + 24) = a5;
    goto LABEL_13;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_42;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v13, Memory);
LABEL_13:
    v16 = WPP_GLOBAL_Control;
  }
  if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v16[7], 12, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v15);
    v16 = WPP_GLOBAL_Control;
  }
  if ( !v15 )
  {
    v8 = v21;
    goto LABEL_27;
  }
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 68) & 1) != 0 )
  {
    WPP_SF_dd(v16[7], 84, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v21, v15);
LABEL_41:
    v16 = WPP_GLOBAL_Control;
  }
LABEL_42:
  if ( v20[0] )
  {
    OneXDeleteEvent(v20[0]);
    goto LABEL_44;
  }
LABEL_45:
  if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 17) & 0x800) != 0 )
    WPP_SF_D(v16[7], 89, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x18000ee70  mov     rax, rsp
0x18000ee73  sub     rsp, 68h
0x18000ee77  mov     [rax+10h], rbp
0x18000ee7b  mov     [rax+18h], rsi
0x18000ee7f  mov     [rax-8], rdi
0x18000ee83  mov     rdi, [rsp+68h+arg_20]
0x18000ee8b  mov     [rax-10h], r12
0x18000ee8f  mov     r12, rdx
0x18000ee92  mov     [rax-18h], r13
0x18000ee96  mov     [rax-20h], r14
0x18000ee9a  mov     ebp, [rdi+14h]
0x18000ee9d  mov     [rax-28h], r15
0x18000eea1  mov     dword ptr [rsp+68h+arg_20], ebp
0x18000eea8  mov     r14d, r9d
0x18000eeab  mov     r15d, r8d
0x18000eeae  movzx   r13d, cx
0x18000eeb2  mov     qword ptr [rax-38h], 0
0x18000eeba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eec1  lea     rax, WPP_GLOBAL_Control
0x18000eec8  cmp     rcx, rax
0x18000eecb  jz      short loc_18000EEF9
0x18000eecd  test    dword ptr [rcx+44h], 800h
0x18000eed4  jz      short loc_18000EEF9
0x18000eed6  mov     rcx, [rcx+38h]
0x18000eeda  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000eee1  mov     edx, 53h ; 'S'
0x18000eee6  call    WPP_SF_
0x18000eeeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eef2  lea     rax, WPP_GLOBAL_Control
0x18000eef9  mov     esi, [rsp+68h+arg_28]
0x18000ef00  mov     [rsp+68h+arg_0], rbx
0x18000ef05  test    esi, esi
0x18000ef07  jz      loc_18000F01A
0x18000ef0d  mov     ebp, [rdi+14h]
0x18000ef10  cmp     rcx, rax
0x18000ef13  jz      short loc_18000EF33
0x18000ef15  test    dword ptr [rcx+44h], 800h
0x18000ef1c  jz      short loc_18000EF33
0x18000ef1e  mov     rcx, [rcx+38h]
0x18000ef22  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000ef29  mov     edx, 0Ah
0x18000ef2e  call    WPP_SF_
0x18000ef33  mov     r9d, 43h ; 'C'
0x18000ef39  lea     r8, aOnexcreateeven; "OneXCreateEvent"
0x18000ef40  lea     rdx, [rsp+68h+var_38]
0x18000ef45  mov     ecx, 58h ; 'X'
0x18000ef4a  call    cs:__imp_AllocateMemory
0x18000ef50  mov     ebx, eax
0x18000ef52  test    eax, eax
0x18000ef54  jz      short loc_18000EF91
0x18000ef56  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef5d  lea     rdi, WPP_GLOBAL_Control
0x18000ef64  cmp     rcx, rdi
0x18000ef67  jz      loc_18000F156
0x18000ef6d  test    byte ptr [rcx+44h], 1
0x18000ef71  jz      short loc_18000EFC0
0x18000ef73  mov     rcx, [rcx+38h]
0x18000ef77  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000ef7e  mov     edx, 0Bh
0x18000ef83  mov     [rsp+68h+var_48], eax
0x18000ef87  mov     r9d, ebp
0x18000ef8a  call    WPP_SF_dd
0x18000ef8f  jmp     short loc_18000EFB9
0x18000ef91  mov     rax, [rsp+68h+var_38]
0x18000ef96  mov     dword ptr [rax+10h], 6
0x18000ef9d  mov     rax, [rsp+68h+var_38]
0x18000efa2  mov     dword ptr [rax+20h], 3
0x18000efa9  mov     rax, [rsp+68h+var_38]
0x18000efae  mov     [rax+18h], rdi
0x18000efb2  lea     rdi, WPP_GLOBAL_Control
0x18000efb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efc0  cmp     rcx, rdi
0x18000efc3  jz      short loc_18000EFED
0x18000efc5  test    dword ptr [rcx+44h], 800h
0x18000efcc  jz      short loc_18000EFED
0x18000efce  mov     rcx, [rcx+38h]
0x18000efd2  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000efd9  mov     edx, 0Ch
0x18000efde  mov     r9d, ebx
0x18000efe1  call    WPP_SF_D
0x18000efe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efed  test    ebx, ebx
0x18000efef  jz      short loc_18000F06C
0x18000eff1  cmp     rcx, rdi
0x18000eff4  jz      loc_18000F156
0x18000effa  test    byte ptr [rcx+44h], 1
0x18000effe  jz      loc_18000F156
0x18000f004  mov     r9d, dword ptr [rsp+68h+arg_20]
0x18000f00c  mov     edx, 54h ; 'T'
0x18000f011  mov     [rsp+68h+var_48], ebx
0x18000f015  jmp     loc_18000F13F
0x18000f01a  mov     r9, rdi
0x18000f01d  lea     rcx, [rsp+68h+var_38]
0x18000f022  mov     edx, 23h ; '#'
0x18000f027  mov     r8d, 3
0x18000f02d  call    OneXCreateEvent
0x18000f032  mov     ebx, eax
0x18000f034  test    eax, eax
0x18000f036  jz      short loc_18000F063
0x18000f038  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f03f  lea     rdi, WPP_GLOBAL_Control
0x18000f046  cmp     rcx, rdi
0x18000f049  jz      loc_18000F156
0x18000f04f  test    byte ptr [rcx+44h], 1
0x18000f053  jz      loc_18000F156
0x18000f059  mov     edx, 55h ; 'U'
0x18000f05e  jmp     loc_18000F138
0x18000f063  lea     rdi, WPP_GLOBAL_Control
0x18000f06a  jmp     short loc_18000F073
0x18000f06c  mov     ebp, dword ptr [rsp+68h+arg_20]
0x18000f073  mov     rax, [rsp+68h+var_38]
0x18000f078  mov     r9d, r13d
0x18000f07b  mov     r8, r12
0x18000f07e  mov     dword ptr [rax+28h], 6
0x18000f085  mov     rcx, [rsp+68h+var_38]
0x18000f08a  lea     rdx, [rcx+2Ch]
0x18000f08e  add     rcx, 30h ; '0'
0x18000f092  call    cs:__imp_SetBufferAndLength
0x18000f098  mov     ebx, eax
0x18000f09a  test    eax, eax
0x18000f09c  jz      short loc_18000F0BF
0x18000f09e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0a5  cmp     rcx, rdi
0x18000f0a8  jz      loc_18000F156
0x18000f0ae  test    byte ptr [rcx+44h], 1
0x18000f0b2  jz      loc_18000F156
0x18000f0b8  mov     edx, 56h ; 'V'
0x18000f0bd  jmp     short loc_18000F138
0x18000f0bf  mov     rax, [rsp+68h+var_38]
0x18000f0c4  mov     dword ptr [rax+38h], 2
0x18000f0cb  mov     rax, [rsp+68h+var_38]
0x18000f0d0  mov     [rax+40h], r15
0x18000f0d4  mov     rax, [rsp+68h+var_38]
0x18000f0d9  mov     dword ptr [rax+48h], 2
0x18000f0e0  mov     rax, [rsp+68h+var_38]
0x18000f0e5  mov     [rax+50h], r14
0x18000f0e9  mov     rcx, [rsp+68h+var_38]
0x18000f0ee  test    esi, esi
0x18000f0f0  jz      short loc_18000F116
0x18000f0f2  call    QueueGlobalEvent
0x18000f0f7  mov     ebx, eax
0x18000f0f9  test    eax, eax
0x18000f0fb  jz      short loc_18000F168
0x18000f0fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f104  cmp     rcx, rdi
0x18000f107  jz      short loc_18000F156
0x18000f109  test    byte ptr [rcx+44h], 1
0x18000f10d  jz      short loc_18000F156
0x18000f10f  mov     edx, 57h ; 'W'
0x18000f114  jmp     short loc_18000F138
0x18000f116  call    QueueSupplicantEvent
0x18000f11b  mov     ebx, eax
0x18000f11d  test    eax, eax
0x18000f11f  jz      short loc_18000F168
0x18000f121  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f128  cmp     rcx, rdi
0x18000f12b  jz      short loc_18000F156
0x18000f12d  test    byte ptr [rcx+44h], 1
0x18000f131  jz      short loc_18000F156
0x18000f133  mov     edx, 58h ; 'X'
0x18000f138  mov     r9d, ebp
0x18000f13b  mov     [rsp+68h+var_48], eax
0x18000f13f  mov     rcx, [rcx+38h]
0x18000f143  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000f14a  call    WPP_SF_dd
0x18000f14f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f156  mov     rax, [rsp+68h+var_38]
0x18000f15b  test    rax, rax
0x18000f15e  jz      short loc_18000F16F
0x18000f160  mov     rcx, rax
0x18000f163  call    OneXDeleteEvent
0x18000f168  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f16f  mov     r15, [rsp+68h+var_28]
0x18000f174  cmp     rcx, rdi
0x18000f177  mov     rdi, [rsp+68h+var_8]
0x18000f17c  mov     r14, [rsp+68h+var_20]
0x18000f181  mov     r13, [rsp+68h+var_18]
0x18000f186  mov     r12, [rsp+68h+var_10]
0x18000f18b  mov     rsi, [rsp+68h+arg_10]
0x18000f193  mov     rbp, [rsp+68h+arg_8]
0x18000f198  jz      short loc_18000F1BB
0x18000f19a  test    dword ptr [rcx+44h], 800h
0x18000f1a1  jz      short loc_18000F1BB
0x18000f1a3  mov     rcx, [rcx+38h]
0x18000f1a7  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000f1ae  mov     edx, 59h ; 'Y'
0x18000f1b3  mov     r9d, ebx
0x18000f1b6  call    WPP_SF_D
0x18000f1bb  mov     eax, ebx
0x18000f1bd  mov     rbx, [rsp+68h+arg_0]
0x18000f1c2  add     rsp, 68h
0x18000f1c6  retn
```
