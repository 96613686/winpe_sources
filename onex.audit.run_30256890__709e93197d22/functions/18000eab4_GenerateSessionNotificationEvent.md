# GenerateSessionNotificationEvent

- ea: `0x18000eab4`
- end: `0x18000ecc2`
- name: `GenerateSessionNotificationEvent`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180004fa0`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000d500`
- `0x18000eab4`
- `0x180010d40`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x18000eb51`
- `MobileNetworking!AllocateMemory` at `0x18000eb51`

## string_xrefs

- `0x18000eb3e`: `OneXCreateEvent`

## pseudocode

```c
__int64 __fastcall GenerateSessionNotificationEvent(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v3; // ebp
  __int64 v5; // r15
  _QWORD *v7; // rcx
  unsigned int v8; // esi
  unsigned int v9; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  unsigned int v12; // eax
  __int64 v14; // [rsp+80h] [rbp+8h] BYREF

  v3 = *(_DWORD *)(a1 + 20);
  v5 = a2;
  v14 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 55, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  v8 = *(_DWORD *)(a1 + 20);
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
    WPP_SF_(v7[7], 10, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  v9 = AllocateMemory(72, &v14, "OneXCreateEvent", 67);
  v10 = v9;
  if ( !v9 )
  {
    *(_DWORD *)(v14 + 16) = 4;
    *(_DWORD *)(v14 + 32) = 2;
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
      WPP_SF_dd(v11[7], 56, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v3, v10);
    goto LABEL_24;
  }
  *(_DWORD *)(v14 + 40) = 2;
  *(_QWORD *)(v14 + 48) = v5;
  *(_DWORD *)(v14 + 56) = 2;
  *(_QWORD *)(v14 + 64) = *(unsigned int *)(a3 + 4);
  v12 = QueueGlobalEvent(v14);
  v10 = v12;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 57, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v3, v12);
    goto LABEL_24;
  }
LABEL_25:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 58, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18000eab4  mov     rax, rsp
0x18000eab7  push    rbx
0x18000eab8  push    rbp
0x18000eab9  push    rsi
0x18000eaba  push    rdi
0x18000eabb  push    r12
0x18000eabd  push    r13
0x18000eabf  push    r14
0x18000eac1  push    r15
0x18000eac3  sub     rsp, 38h
0x18000eac7  mov     ebp, [rcx+14h]
0x18000eaca  mov     r14, r8
0x18000eacd  mov     r15d, edx
0x18000ead0  mov     rdi, rcx
0x18000ead3  mov     qword ptr [rax+8], 0
0x18000eadb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eae2  lea     r12, WPP_GLOBAL_Control
0x18000eae9  lea     r13, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000eaf0  cmp     rcx, r12
0x18000eaf3  jz      short loc_18000EB16
0x18000eaf5  test    dword ptr [rcx+44h], 800h
0x18000eafc  jz      short loc_18000EB16
0x18000eafe  mov     rcx, [rcx+38h]
0x18000eb02  mov     edx, 37h ; '7'
0x18000eb07  mov     r8, r13
0x18000eb0a  call    WPP_SF_
0x18000eb0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb16  mov     esi, [rdi+14h]
0x18000eb19  cmp     rcx, r12
0x18000eb1c  jz      short loc_18000EB38
0x18000eb1e  test    dword ptr [rcx+44h], 800h
0x18000eb25  jz      short loc_18000EB38
0x18000eb27  mov     rcx, [rcx+38h]
0x18000eb2b  mov     edx, 0Ah
0x18000eb30  mov     r8, r13
0x18000eb33  call    WPP_SF_
0x18000eb38  mov     r9d, 43h ; 'C'
0x18000eb3e  lea     r8, aOnexcreateeven; "OneXCreateEvent"
0x18000eb45  lea     rdx, [rsp+78h+arg_0]
0x18000eb4d  lea     ecx, [r9+5]
0x18000eb51  call    cs:__imp_AllocateMemory
0x18000eb57  mov     ebx, eax
0x18000eb59  test    eax, eax
0x18000eb5b  jz      short loc_18000EB8D
0x18000eb5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb64  cmp     rcx, r12
0x18000eb67  jz      loc_18000EC79
0x18000eb6d  test    byte ptr [rcx+44h], 1
0x18000eb71  jz      short loc_18000EBBE
0x18000eb73  mov     rcx, [rcx+38h]
0x18000eb77  mov     edx, 0Bh
0x18000eb7c  mov     r9d, esi
0x18000eb7f  mov     [rsp+78h+var_58], eax
0x18000eb83  mov     r8, r13
0x18000eb86  call    WPP_SF_dd
0x18000eb8b  jmp     short loc_18000EBB7
0x18000eb8d  mov     rax, [rsp+78h+arg_0]
0x18000eb95  mov     dword ptr [rax+10h], 4
0x18000eb9c  mov     rax, [rsp+78h+arg_0]
0x18000eba4  mov     dword ptr [rax+20h], 2
0x18000ebab  mov     rax, [rsp+78h+arg_0]
0x18000ebb3  mov     [rax+18h], rdi
0x18000ebb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebbe  cmp     rcx, r12
0x18000ebc1  jz      short loc_18000EBE7
0x18000ebc3  test    dword ptr [rcx+44h], 800h
0x18000ebca  jz      short loc_18000EBE7
0x18000ebcc  mov     rcx, [rcx+38h]
0x18000ebd0  mov     edx, 0Ch
0x18000ebd5  mov     r9d, ebx
0x18000ebd8  mov     r8, r13
0x18000ebdb  call    WPP_SF_D
0x18000ebe0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebe7  test    ebx, ebx
0x18000ebe9  jz      short loc_18000EC05
0x18000ebeb  cmp     rcx, r12
0x18000ebee  jz      loc_18000EC79
0x18000ebf4  test    byte ptr [rcx+44h], 1
0x18000ebf8  jz      short loc_18000EC79
0x18000ebfa  mov     edx, 38h ; '8'
0x18000ebff  mov     [rsp+78h+var_58], ebx
0x18000ec03  jmp     short loc_18000EC6A
0x18000ec05  mov     rax, [rsp+78h+arg_0]
0x18000ec0d  mov     edx, 2
0x18000ec12  mov     [rax+28h], edx
0x18000ec15  mov     rax, [rsp+78h+arg_0]
0x18000ec1d  mov     [rax+30h], r15
0x18000ec21  mov     rax, [rsp+78h+arg_0]
0x18000ec29  mov     [rax+38h], edx
0x18000ec2c  mov     ecx, [r14+4]
0x18000ec30  mov     rax, [rsp+78h+arg_0]
0x18000ec38  mov     [rax+40h], rcx
0x18000ec3c  mov     rcx, [rsp+78h+arg_0]
0x18000ec44  call    QueueGlobalEvent
0x18000ec49  mov     ebx, eax
0x18000ec4b  test    eax, eax
0x18000ec4d  jz      short loc_18000EC86
0x18000ec4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec56  cmp     rcx, r12
0x18000ec59  jz      short loc_18000EC79
0x18000ec5b  test    byte ptr [rcx+44h], 1
0x18000ec5f  jz      short loc_18000EC79
0x18000ec61  mov     edx, 39h ; '9'
0x18000ec66  mov     [rsp+78h+var_58], eax
0x18000ec6a  mov     rcx, [rcx+38h]
0x18000ec6e  mov     r9d, ebp
0x18000ec71  mov     r8, r13
0x18000ec74  call    WPP_SF_dd
0x18000ec79  mov     rcx, [rsp+78h+arg_0]
0x18000ec81  call    OneXDeleteEvent
0x18000ec86  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec8d  cmp     rcx, r12
0x18000ec90  jz      short loc_18000ECAF
0x18000ec92  test    dword ptr [rcx+44h], 800h
0x18000ec99  jz      short loc_18000ECAF
0x18000ec9b  mov     rcx, [rcx+38h]
0x18000ec9f  mov     edx, 3Ah ; ':'
0x18000eca4  mov     r9d, ebx
0x18000eca7  mov     r8, r13
0x18000ecaa  call    WPP_SF_D
0x18000ecaf  mov     eax, ebx
0x18000ecb1  add     rsp, 38h
0x18000ecb5  pop     r15
0x18000ecb7  pop     r14
0x18000ecb9  pop     r13
0x18000ecbb  pop     r12
0x18000ecbd  pop     rdi
0x18000ecbe  pop     rsi
0x18000ecbf  pop     rbp
0x18000ecc0  pop     rbx
0x18000ecc1  retn
```
