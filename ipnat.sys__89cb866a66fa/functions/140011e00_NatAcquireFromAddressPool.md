# NatAcquireFromAddressPool

- ea: `0x140011e00`
- end: `0x14001239f`
- name: `NatAcquireFromAddressPool`
- size: `1439`
- prototype: ``
- caller_count: `7`
- callee_count: `9`
- tags: ``

## callers

- `0x140008a54`
- `0x14001169c`
- `0x140013550`
- `0x14001d05c`
- `0x14001daa0`
- `0x14001e4e4`
- `0x14002665c`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140002200`
- `0x140010ce4`
- `0x140011e00`
- `0x14001308c`
- `0x140013b70`
- `0x140013ccc`
- `0x14002cbc0`

## import_xrefs

- `ntoskrnl!RtlGetNtProductType` at `0x140011f49`
- `ntoskrnl!RtlGetNtProductType` at `0x140011f49`
- `ntoskrnl!ExAllocatePool2` at `0x1400121d7`
- `ntoskrnl!ExAllocatePool2` at `0x1400121d7`

## pseudocode

```c
__int64 __fastcall NatAcquireFromAddressPool(__int64 a1, unsigned int a2, unsigned int a3, __int64 *a4)
{
  __int64 v5; // r14
  _QWORD **v8; // rsi
  _QWORD *i; // rdi
  _QWORD *v10; // rbx
  int AddressPoolEntry; // edi
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  _QWORD *v15; // rdi
  _QWORD *v16; // rbx
  __int64 v17; // r12
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  char *Pool2; // rax
  char *v21; // rdi
  __int64 v22; // rax
  __int64 v23; // rcx
  _QWORD *v24; // rax
  _QWORD *v25; // rcx
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+80h] [rbp+8h] BYREF
  __int64 v27; // [rsp+98h] [rbp+20h] BYREF

  v5 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, a2, a3);
  }
  v27 = 0;
  *a4 = 0;
  ProductType = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_dddd(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      WPP_96cec5cc952234920ba0014d840adb44_Traceguids,
      (unsigned __int8)v5,
      BYTE1(v5),
      BYTE2(v5),
      BYTE3(v5));
  }
  v8 = (_QWORD **)(a1 + 152);
  for ( i = *(_QWORD **)(a1 + 152); ; i = (_QWORD *)*i )
  {
    if ( i == v8 )
      goto LABEL_15;
    v10 = i - 3;
    if ( *((_DWORD *)i + 6) == (_DWORD)v5 && (!a3 || *((_DWORD *)v10 + 13) == a3) )
      break;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
  }
  if ( i != v8 )
  {
    if ( *((int *)v10 + 18) >= 0 )
      _InterlockedIncrement((volatile signed __int32 *)v10 + 19);
    *a4 = (__int64)v10;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 0;
    }
    v13 = 13;
    goto LABEL_24;
  }
LABEL_15:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
  }
  RtlGetNtProductType(&ProductType);
  AddressPoolEntry = NatCreateAddressPoolEntry(a1, v5, a3, 0, 0, a4);
  if ( AddressPoolEntry >= 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 0;
    }
    v13 = 16;
LABEL_24:
    WPP_SF_d(v12->AttachedDevice, v13, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, 0);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        WPP_96cec5cc952234920ba0014d840adb44_Traceguids,
        (unsigned int)AddressPoolEntry);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
    }
  }
  if ( a3 || (*(_DWORD *)(a1 + 56) & 2) == 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225473LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_96cec5cc952234920ba0014d840adb44_Traceguids,
        (unsigned int)AddressPoolEntry);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225473LL;
    }
    v19 = 20;
    goto LABEL_90;
  }
  v15 = *v8;
  if ( *v8 == v8 )
    goto LABEL_58;
  do
  {
    v16 = v15 - 3;
    if ( (v15[6] & 0x11) == 0
      && !NatLookupAddressPoolEntry(*(_QWORD *)(a1 + 144), (unsigned int)v5, *((unsigned int *)v16 + 13), &v27) )
    {
      break;
    }
    v15 = (_QWORD *)*v15;
  }
  while ( v15 != v8 );
  v17 = v27;
  if ( v15 == v8 )
  {
LABEL_58:
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225473LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, 3221225473LL);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225473LL;
    }
    v19 = 22;
LABEL_90:
    WPP_SF_d(v18->AttachedDevice, v19, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, 3221225473LL);
    return 3221225473LL;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_dddd(
      WPP_GLOBAL_Control->AttachedDevice,
      23,
      WPP_96cec5cc952234920ba0014d840adb44_Traceguids,
      (unsigned __int8)*((_DWORD *)v16 + 13),
      BYTE1(*((_DWORD *)v16 + 13)),
      (unsigned __int8)BYTE2(*((_DWORD *)v16 + 13)),
      HIBYTE(*((_DWORD *)v16 + 13)));
  }
  Pool2 = (char *)ExAllocatePool2(64, 88, 1096114510);
  v21 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0x58u);
    *((_DWORD *)v21 + 12) = v5;
    *((_DWORD *)v21 + 18) = 16;
    v22 = *((unsigned int *)v16 + 13);
    v23 = v22 | (v5 << 32);
    *((_DWORD *)v21 + 13) = v22;
    v24 = v21 + 24;
    *((_QWORD *)v21 + 5) = v23;
    *((_QWORD *)v21 + 4) = v21 + 24;
    *((_QWORD *)v21 + 3) = v21 + 24;
    *((_DWORD *)v21 + 19) = 1;
    *(_QWORD *)v21 = v21;
    *((_QWORD *)v21 + 1) = 0;
    *((_QWORD *)v21 + 2) = 0;
    v25 = *(_QWORD **)(a1 + 160);
    if ( (_QWORD **)*v25 != v8 )
      __fastfail(3u);
    *((_QWORD *)v21 + 4) = v25;
    *v24 = v8;
    *v25 = v24;
    *(_QWORD *)(a1 + 160) = v24;
    *(_QWORD *)(a1 + 144) = NatInsertAddressPoolEntry(v17, v21);
    *((_QWORD *)v21 + 7) = v16;
    if ( *((int *)v16 + 18) >= 0 )
      _InterlockedIncrement((volatile signed __int32 *)v16 + 19);
    *a4 = (__int64)v21;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 0;
    }
    v13 = 26;
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, 3221225495LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, 3221225495LL);
    }
  }
  return 3221225495LL;
}

```

## disassembly

```asm
0x140011e00  mov     [rsp+arg_8], rbx
0x140011e05  push    rbp
0x140011e06  push    rsi
0x140011e07  push    rdi
0x140011e08  push    r12
0x140011e0a  push    r13
0x140011e0c  push    r14
0x140011e0e  push    r15
0x140011e10  sub     rsp, 40h
0x140011e14  mov     r15, r9
0x140011e17  mov     r14d, edx
0x140011e1a  mov     ebp, r8d
0x140011e1d  mov     r13, rcx
0x140011e20  mov     rcx, cs:WPP_GLOBAL_Control
0x140011e27  lea     rdx, WPP_GLOBAL_Control
0x140011e2e  cmp     rcx, rdx
0x140011e31  jz      short loc_140011E64
0x140011e33  mov     eax, [rcx+2Ch]
0x140011e36  test    al, 1
0x140011e38  jz      short loc_140011E64
0x140011e3a  cmp     byte ptr [rcx+29h], 6
0x140011e3e  jb      short loc_140011E64
0x140011e40  mov     rcx, [rcx+18h]
0x140011e44  mov     edx, 0Ah
0x140011e49  mov     dword ptr [rsp+78h+var_58], r8d
0x140011e4e  mov     r9d, r14d
0x140011e51  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140011e58  call    WPP_SF_dd
0x140011e5d  lea     rdx, WPP_GLOBAL_Control
0x140011e64  xor     r12d, r12d
0x140011e67  xor     ebx, ebx
0x140011e69  mov     [rsp+78h+arg_18], r12
0x140011e71  mov     [r15], rbx
0x140011e74  mov     [rsp+78h+ProductType], r12d
0x140011e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011e83  cmp     rcx, rdx
0x140011e86  jz      short loc_140011EDD
0x140011e88  mov     eax, [rcx+2Ch]
0x140011e8b  test    al, 1
0x140011e8d  jz      short loc_140011EDD
0x140011e8f  cmp     byte ptr [rcx+29h], 5
0x140011e93  jb      short loc_140011EDD
0x140011e95  mov     rcx, [rcx+18h]
0x140011e99  lea     edx, [rbx+0Bh]
0x140011e9c  mov     eax, r14d
0x140011e9f  movzx   r9d, r14b
0x140011ea3  shr     eax, 10h
0x140011ea6  mov     r11d, r14d
0x140011ea9  movzx   r10d, al
0x140011ead  mov     eax, r14d
0x140011eb0  shr     eax, 8
0x140011eb3  movzx   r8d, al
0x140011eb7  shr     r11d, 18h
0x140011ebb  mov     [rsp+78h+var_48], r11d
0x140011ec0  mov     dword ptr [rsp+78h+var_50], r10d
0x140011ec5  mov     dword ptr [rsp+78h+var_58], r8d
0x140011eca  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140011ed1  call    WPP_SF_dddd
0x140011ed6  lea     rdx, WPP_GLOBAL_Control
0x140011edd  lea     rsi, [r13+98h]
0x140011ee4  mov     rdi, [rsi]
0x140011ee7  jmp     short loc_140011F07
0x140011ee9  lea     rbx, [rdi-18h]
0x140011eed  cmp     [rbx+30h], r14d
0x140011ef1  jnz     short loc_140011F04
0x140011ef3  test    ebp, ebp
0x140011ef5  jz      loc_140011FB9
0x140011efb  cmp     [rbx+34h], ebp
0x140011efe  jz      loc_140011FB9
0x140011f04  mov     rdi, [rdi]
0x140011f07  cmp     rdi, rsi
0x140011f0a  jnz     short loc_140011EE9
0x140011f0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011f13  lea     rax, WPP_GLOBAL_Control
0x140011f1a  cmp     rcx, rax
0x140011f1d  jz      short loc_140011F41
0x140011f1f  mov     eax, [rcx+2Ch]
0x140011f22  test    al, 1
0x140011f24  jz      short loc_140011F41
0x140011f26  cmp     byte ptr [rcx+29h], 5
0x140011f2a  jb      short loc_140011F41
0x140011f2c  mov     rcx, [rcx+18h]
0x140011f30  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140011f37  mov     edx, 0Eh
0x140011f3c  call    WPP_SF_
0x140011f41  lea     rcx, [rsp+78h+ProductType]; ProductType
0x140011f49  call    cs:__imp_RtlGetNtProductType
0x140011f50  nop     dword ptr [rax+rax+00h]
0x140011f55  xor     r9d, r9d
0x140011f58  mov     [rsp+78h+var_50], r15
0x140011f5d  mov     r8d, ebp
0x140011f60  mov     [rsp+78h+var_58], r12
0x140011f65  mov     edx, r14d
0x140011f68  mov     rcx, r13
0x140011f6b  call    NatCreateAddressPoolEntry
0x140011f70  mov     edi, eax
0x140011f72  test    eax, eax
0x140011f74  js      loc_140012027
0x140011f7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140011f81  lea     rax, WPP_GLOBAL_Control
0x140011f88  cmp     rcx, rax
0x140011f8b  jz      short loc_140011FB2
0x140011f8d  mov     eax, [rcx+2Ch]
0x140011f90  test    al, 1
0x140011f92  jz      short loc_140011FB2
0x140011f94  cmp     byte ptr [rcx+29h], 6
0x140011f98  jb      short loc_140011FB2
0x140011f9a  mov     edx, 10h
0x140011f9f  mov     rcx, [rcx+18h]
0x140011fa3  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140011faa  xor     r9d, r9d
0x140011fad  call    WPP_SF_d
0x140011fb2  xor     eax, eax
0x140011fb4  jmp     loc_140012386
0x140011fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140011fc0  cmp     rcx, rdx
0x140011fc3  jz      short loc_140011FE7
0x140011fc5  mov     eax, [rcx+2Ch]
0x140011fc8  test    al, 1
0x140011fca  jz      short loc_140011FE7
0x140011fcc  cmp     byte ptr [rcx+29h], 5
0x140011fd0  jb      short loc_140011FE7
0x140011fd2  mov     rcx, [rcx+18h]
0x140011fd6  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140011fdd  mov     edx, 0Ch
0x140011fe2  call    WPP_SF_
0x140011fe7  cmp     rdi, rsi
0x140011fea  jz      loc_140011F0C
0x140011ff0  cmp     [rbx+48h], r12d
0x140011ff4  jl      short loc_140011FFA
0x140011ff6  lock inc dword ptr [rbx+4Ch]
0x140011ffa  mov     [r15], rbx
0x140011ffd  mov     rcx, cs:WPP_GLOBAL_Control
0x140012004  lea     rax, WPP_GLOBAL_Control
0x14001200b  cmp     rcx, rax
0x14001200e  jz      short loc_140011FB2
0x140012010  mov     eax, [rcx+2Ch]
0x140012013  test    al, 1
0x140012015  jz      short loc_140011FB2
0x140012017  cmp     byte ptr [rcx+29h], 6
0x14001201b  jb      short loc_140011FB2
0x14001201d  mov     edx, 0Dh
0x140012022  jmp     loc_140011F9F
0x140012027  mov     rcx, cs:WPP_GLOBAL_Control
0x14001202e  lea     rdx, WPP_GLOBAL_Control
0x140012035  cmp     rcx, rdx
0x140012038  jz      short loc_14001209B
0x14001203a  mov     eax, [rcx+2Ch]
0x14001203d  test    al, 1
0x14001203f  jz      short loc_140012066
0x140012041  cmp     byte ptr [rcx+29h], 2
0x140012045  jb      short loc_140012066
0x140012047  mov     rcx, [rcx+18h]
0x14001204b  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140012052  mov     edx, 11h
0x140012057  mov     r9d, edi
0x14001205a  call    WPP_SF_d
0x14001205f  lea     rdx, WPP_GLOBAL_Control
0x140012066  mov     rcx, cs:WPP_GLOBAL_Control
0x14001206d  cmp     rcx, rdx
0x140012070  jz      short loc_14001209B
0x140012072  mov     eax, [rcx+2Ch]
0x140012075  test    al, 1
0x140012077  jz      short loc_14001209B
0x140012079  cmp     byte ptr [rcx+29h], 5
0x14001207d  jb      short loc_14001209B
0x14001207f  mov     rcx, [rcx+18h]
0x140012083  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x14001208a  mov     edx, 12h
0x14001208f  call    WPP_SF_
0x140012094  lea     rdx, WPP_GLOBAL_Control
0x14001209b  test    ebp, ebp
0x14001209d  jnz     loc_140012314
0x1400120a3  mov     eax, [r13+38h]
0x1400120a7  test    al, 2
0x1400120a9  jz      loc_140012314
0x1400120af  mov     rdi, [rsi]
0x1400120b2  cmp     rdi, rsi
0x1400120b5  jz      short loc_1400120F7
0x1400120b7  lea     rbx, [rdi-18h]
0x1400120bb  mov     eax, [rbx+48h]
0x1400120be  test    al, 11h
0x1400120c0  jnz     short loc_1400120E2
0x1400120c2  mov     r8d, [rbx+34h]
0x1400120c6  lea     r9, [rsp+78h+arg_18]
0x1400120ce  mov     rcx, [r13+90h]
0x1400120d5  mov     edx, r14d
0x1400120d8  call    NatLookupAddressPoolEntry
0x1400120dd  test    rax, rax
0x1400120e0  jz      short loc_1400120EA
0x1400120e2  mov     rdi, [rdi]
0x1400120e5  cmp     rdi, rsi
0x1400120e8  jnz     short loc_1400120B7
0x1400120ea  mov     r12, [rsp+78h+arg_18]
0x1400120f2  cmp     rdi, rsi
0x1400120f5  jnz     short loc_140012165
0x1400120f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400120fe  lea     rbx, WPP_GLOBAL_Control
0x140012105  cmp     rcx, rbx
0x140012108  jz      loc_140012381
0x14001210e  mov     eax, [rcx+2Ch]
0x140012111  test    al, 1
0x140012113  jz      short loc_140012136
0x140012115  cmp     byte ptr [rcx+29h], 2
0x140012119  jb      short loc_140012136
0x14001211b  mov     rcx, [rcx+18h]
0x14001211f  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140012126  mov     edx, 15h
0x14001212b  mov     r9d, 0C0000001h
0x140012131  call    WPP_SF_d
0x140012136  mov     rcx, cs:WPP_GLOBAL_Control
0x14001213d  cmp     rcx, rbx
0x140012140  jz      loc_140012381
0x140012146  mov     eax, [rcx+2Ch]
0x140012149  test    al, 1
0x14001214b  jz      loc_140012381
0x140012151  cmp     byte ptr [rcx+29h], 6
0x140012155  jb      loc_140012381
0x14001215b  mov     edx, 16h
0x140012160  jmp     loc_14001236B
0x140012165  mov     rcx, cs:WPP_GLOBAL_Control
0x14001216c  lea     rbp, WPP_GLOBAL_Control
0x140012173  cmp     rcx, rbp
0x140012176  jz      short loc_1400121C9
0x140012178  mov     eax, [rcx+2Ch]
0x14001217b  test    al, 1
0x14001217d  jz      short loc_1400121C9
0x14001217f  cmp     byte ptr [rcx+29h], 5
0x140012183  jb      short loc_1400121C9
0x140012185  mov     edx, [rbx+34h]
0x140012188  mov     r11d, edx
0x14001218b  mov     rcx, [rcx+18h]
0x14001218f  mov     eax, edx
0x140012191  shr     eax, 10h
0x140012194  movzx   r10d, al
0x140012198  mov     eax, edx
0x14001219a  shr     eax, 8
0x14001219d  movzx   r8d, al
0x1400121a1  shr     r11d, 18h
0x1400121a5  mov     [rsp+78h+var_48], r11d
0x1400121aa  mov     dword ptr [rsp+78h+var_50], r10d
0x1400121af  mov     dword ptr [rsp+78h+var_58], r8d
0x1400121b4  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x1400121bb  movzx   r9d, dl
0x1400121bf  mov     edx, 17h
0x1400121c4  call    WPP_SF_dddd
0x1400121c9  mov     edx, 58h ; 'X'
0x1400121ce  mov     r8d, 4155614Eh
0x1400121d4  lea     ecx, [rdx-18h]
0x1400121d7  call    cs:__imp_ExAllocatePool2
0x1400121de  nop     dword ptr [rax+rax+00h]
0x1400121e3  mov     rdi, rax
0x1400121e6  test    rax, rax
0x1400121e9  jnz     short loc_140012258
0x1400121eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400121f2  mov     ebx, 0C0000017h
0x1400121f7  cmp     rcx, rbp
0x1400121fa  jz      short loc_140012251
0x1400121fc  mov     eax, [rcx+2Ch]
0x1400121ff  test    al, 1
0x140012201  jz      short loc_14001221F
0x140012203  cmp     byte ptr [rcx+29h], 2
0x140012207  jb      short loc_14001221F
0x140012209  mov     rcx, [rcx+18h]
0x14001220d  lea     edx, [rdi+18h]
0x140012210  mov     r9d, ebx
0x140012213  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x14001221a  call    WPP_SF_d
0x14001221f  mov     rcx, cs:WPP_GLOBAL_Control
0x140012226  cmp     rcx, rbp
0x140012229  jz      short loc_140012251
0x14001222b  mov     edx, [rcx+2Ch]
0x14001222e  test    dl, 1
0x140012231  jz      short loc_140012251
0x140012233  cmp     byte ptr [rcx+29h], 6
0x140012237  jb      short loc_140012251
0x140012239  mov     rcx, [rcx+18h]
0x14001223d  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140012244  mov     edx, 19h
0x140012249  mov     r9d, ebx
0x14001224c  call    WPP_SF_d
0x140012251  mov     eax, ebx
0x140012253  jmp     loc_140012386
0x140012258  xor     edx, edx; Val
0x14001225a  mov     rcx, rdi; void *
0x14001225d  lea     r8d, [rdx+58h]; Size
0x140012261  call    memset
0x140012266  mov     [rdi+30h], r14d
0x14001226a  mov     rcx, r14
0x14001226d  mov     dword ptr [rdi+48h], 10h
0x140012274  xor     r14d, r14d
0x140012277  mov     eax, [rbx+34h]
0x14001227a  shl     rcx, 20h
0x14001227e  or      rcx, rax
0x140012281  mov     [rdi+34h], eax
0x140012284  lea     rax, [rdi+18h]
0x140012288  mov     [rdi+28h], rcx
0x14001228c  mov     [rax+8], rax
0x140012290  mov     [rax], rax
0x140012293  mov     dword ptr [rdi+4Ch], 1
  ... truncated ...
```
