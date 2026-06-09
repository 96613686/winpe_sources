# OneXGenerateEapWaitForPktEvent

- ea: `0x18000dad0`
- end: `0x18000dd30`
- name: `OneXGenerateEapWaitForPktEvent`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800067e0`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000cf70`
- `0x18000dad0`
- `0x180010d40`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x18000db97`
- `MobileNetworking!AllocateMemory` at `0x18000db97`

## string_xrefs

- `0x18000db86`: `OneXCreateEvent`

## pseudocode

```c
__int64 __fastcall OneXGenerateEapWaitForPktEvent(__int64 a1)
{
  unsigned int v1; // r14d
  _QWORD *v3; // rcx
  unsigned int v4; // ebp
  unsigned int v5; // esi
  unsigned int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  unsigned int v9; // eax
  _QWORD *v10; // rcx
  __int64 v12; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_DWORD *)(a1 + 20);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 76, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  v4 = *(_DWORD *)(a1 + 20);
  v12 = 0;
  if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 17) & 0x800) != 0 )
  {
    WPP_SF_(v3[7], 18, WPP_c98c90d098d532f46181864aabb10d65_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  v5 = *(_DWORD *)(a1 + 20);
  if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 17) & 0x800) != 0 )
    WPP_SF_(v3[7], 10, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  v6 = AllocateMemory(56, &v12, "OneXCreateEvent", 67);
  v7 = v6;
  if ( !v6 )
  {
    *(_DWORD *)(v12 + 16) = 38;
    *(_DWORD *)(v12 + 32) = 0;
    *(_QWORD *)(v12 + 24) = a1;
    goto LABEL_15;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
LABEL_27:
    OneXDeleteEvent(v12);
    goto LABEL_28;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v5, v6);
LABEL_15:
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v8[7], 12, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v7);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 68) & 1) != 0 )
      WPP_SF_dd(v8[7], 19, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v4, v7);
    goto LABEL_27;
  }
  v9 = QueueSupplicantEvent(v12);
  v7 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v4, v9);
    goto LABEL_27;
  }
LABEL_28:
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v7);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    if ( v10 == &WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)v10 + 68) & 1) != 0 )
    {
      WPP_SF_dd(v10[7], 77, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v1, v7);
      v10 = WPP_GLOBAL_Control;
    }
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x800) != 0 )
    WPP_SF_D(v10[7], 78, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18000dad0  mov     [rsp+arg_8], rbx
0x18000dad5  mov     [rsp+arg_10], rbp
0x18000dada  push    rsi
0x18000dadb  push    rdi
0x18000dadc  push    r12
0x18000dade  push    r14
0x18000dae0  push    r15
0x18000dae2  sub     rsp, 30h
0x18000dae6  mov     r14d, [rcx+14h]
0x18000daea  mov     rdi, rcx
0x18000daed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000daf4  lea     r15, WPP_GLOBAL_Control
0x18000dafb  cmp     rcx, r15
0x18000dafe  jz      short loc_18000DB25
0x18000db00  test    dword ptr [rcx+44h], 800h
0x18000db07  jz      short loc_18000DB25
0x18000db09  mov     rcx, [rcx+38h]
0x18000db0d  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000db14  mov     edx, 4Ch ; 'L'
0x18000db19  call    WPP_SF_
0x18000db1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db25  mov     ebp, [rdi+14h]
0x18000db28  xor     r12d, r12d
0x18000db2b  mov     [rsp+58h+arg_0], r12
0x18000db30  cmp     rcx, r15
0x18000db33  jz      short loc_18000DB5A
0x18000db35  test    dword ptr [rcx+44h], 800h
0x18000db3c  jz      short loc_18000DB5A
0x18000db3e  mov     rcx, [rcx+38h]
0x18000db42  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000db49  mov     edx, 12h
0x18000db4e  call    WPP_SF_
0x18000db53  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db5a  mov     esi, [rdi+14h]
0x18000db5d  cmp     rcx, r15
0x18000db60  jz      short loc_18000DB80
0x18000db62  test    dword ptr [rcx+44h], 800h
0x18000db69  jz      short loc_18000DB80
0x18000db6b  mov     rcx, [rcx+38h]
0x18000db6f  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000db76  mov     edx, 0Ah
0x18000db7b  call    WPP_SF_
0x18000db80  mov     r9d, 43h ; 'C'
0x18000db86  lea     r8, aOnexcreateeven; "OneXCreateEvent"
0x18000db8d  lea     rdx, [rsp+58h+arg_0]
0x18000db92  mov     ecx, 38h ; '8'
0x18000db97  call    cs:__imp_AllocateMemory
0x18000db9d  mov     ebx, eax
0x18000db9f  test    eax, eax
0x18000dba1  jz      short loc_18000DBD7
0x18000dba3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbaa  cmp     rcx, r15
0x18000dbad  jz      loc_18000DC81
0x18000dbb3  test    byte ptr [rcx+44h], 1
0x18000dbb7  jz      short loc_18000DBFC
0x18000dbb9  mov     rcx, [rcx+38h]
0x18000dbbd  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000dbc4  mov     edx, 0Bh
0x18000dbc9  mov     [rsp+58h+var_38], eax
0x18000dbcd  mov     r9d, esi
0x18000dbd0  call    WPP_SF_dd
0x18000dbd5  jmp     short loc_18000DBF5
0x18000dbd7  mov     rax, [rsp+58h+arg_0]
0x18000dbdc  mov     dword ptr [rax+10h], 26h ; '&'
0x18000dbe3  mov     rax, [rsp+58h+arg_0]
0x18000dbe8  mov     [rax+20h], r12d
0x18000dbec  mov     rax, [rsp+58h+arg_0]
0x18000dbf1  mov     [rax+18h], rdi
0x18000dbf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbfc  cmp     rcx, r15
0x18000dbff  jz      short loc_18000DC29
0x18000dc01  test    dword ptr [rcx+44h], 800h
0x18000dc08  jz      short loc_18000DC29
0x18000dc0a  mov     rcx, [rcx+38h]
0x18000dc0e  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000dc15  mov     edx, 0Ch
0x18000dc1a  mov     r9d, ebx
0x18000dc1d  call    WPP_SF_D
0x18000dc22  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc29  test    ebx, ebx
0x18000dc2b  jz      short loc_18000DC43
0x18000dc2d  cmp     rcx, r15
0x18000dc30  jz      short loc_18000DC81
0x18000dc32  test    byte ptr [rcx+44h], 1
0x18000dc36  jz      short loc_18000DC81
0x18000dc38  mov     edx, 13h
0x18000dc3d  mov     [rsp+58h+var_38], ebx
0x18000dc41  jmp     short loc_18000DC6E
0x18000dc43  mov     rcx, [rsp+58h+arg_0]
0x18000dc48  call    QueueSupplicantEvent
0x18000dc4d  mov     ebx, eax
0x18000dc4f  test    eax, eax
0x18000dc51  jz      short loc_18000DC8B
0x18000dc53  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc5a  cmp     rcx, r15
0x18000dc5d  jz      short loc_18000DC81
0x18000dc5f  test    byte ptr [rcx+44h], 1
0x18000dc63  jz      short loc_18000DC81
0x18000dc65  mov     edx, 14h
0x18000dc6a  mov     [rsp+58h+var_38], eax
0x18000dc6e  mov     rcx, [rcx+38h]
0x18000dc72  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000dc79  mov     r9d, ebp
0x18000dc7c  call    WPP_SF_dd
0x18000dc81  mov     rcx, [rsp+58h+arg_0]
0x18000dc86  call    OneXDeleteEvent
0x18000dc8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc92  cmp     rcx, r15
0x18000dc95  jz      short loc_18000DCBF
0x18000dc97  test    dword ptr [rcx+44h], 800h
0x18000dc9e  jz      short loc_18000DCBF
0x18000dca0  mov     rcx, [rcx+38h]
0x18000dca4  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000dcab  mov     edx, 15h
0x18000dcb0  mov     r9d, ebx
0x18000dcb3  call    WPP_SF_D
0x18000dcb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcbf  test    ebx, ebx
0x18000dcc1  jz      short loc_18000DCF1
0x18000dcc3  cmp     rcx, r15
0x18000dcc6  jz      short loc_18000DD17
0x18000dcc8  test    byte ptr [rcx+44h], 1
0x18000dccc  jz      short loc_18000DCF1
0x18000dcce  mov     rcx, [rcx+38h]
0x18000dcd2  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000dcd9  mov     edx, 4Dh ; 'M'
0x18000dcde  mov     [rsp+58h+var_38], ebx
0x18000dce2  mov     r9d, r14d
0x18000dce5  call    WPP_SF_dd
0x18000dcea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcf1  cmp     rcx, r15
0x18000dcf4  jz      short loc_18000DD17
0x18000dcf6  test    dword ptr [rcx+44h], 800h
0x18000dcfd  jz      short loc_18000DD17
0x18000dcff  mov     rcx, [rcx+38h]
0x18000dd03  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000dd0a  mov     edx, 4Eh ; 'N'
0x18000dd0f  mov     r9d, ebx
0x18000dd12  call    WPP_SF_D
0x18000dd17  mov     rbp, [rsp+58h+arg_10]
0x18000dd1c  mov     eax, ebx
0x18000dd1e  mov     rbx, [rsp+58h+arg_8]
0x18000dd23  add     rsp, 30h
0x18000dd27  pop     r15
0x18000dd29  pop     r14
0x18000dd2b  pop     r12
0x18000dd2d  pop     rdi
0x18000dd2e  pop     rsi
0x18000dd2f  retn
```
