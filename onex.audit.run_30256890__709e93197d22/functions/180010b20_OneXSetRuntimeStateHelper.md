# OneXSetRuntimeStateHelper

- ea: `0x180010b20`
- end: `0x180010d2c`
- name: `OneXSetRuntimeStateHelper`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800170c0`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000d500`
- `0x180010b20`
- `0x180010d40`
- `0x18001a198`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x180010bb5`
- `MobileNetworking!AllocateMemory` at `0x180010bb5`

## string_xrefs

- `0x180010ba4`: `OneXCreateEvent`

## pseudocode

```c
__int64 __fastcall OneXSetRuntimeStateHelper(__int64 a1, __int64 a2)
{
  unsigned int v2; // r14d
  _QWORD *v5; // rcx
  unsigned int v6; // esi
  unsigned int v7; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  unsigned int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v14; // [rsp+70h] [rbp+8h] BYREF

  v2 = *(_DWORD *)(a1 + 20);
  v14 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 78, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = *(_DWORD *)(a1 + 20);
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x800) != 0 )
    WPP_SF_(v5[7], 10, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  v7 = AllocateMemory(56, &v14, "OneXCreateEvent", 67);
  v8 = v7;
  if ( !v7 )
  {
    *(_DWORD *)(v14 + 16) = 10;
    *(_DWORD *)(v14 + 32) = 1;
    *(_QWORD *)(v14 + 24) = a1;
    goto LABEL_12;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
LABEL_29:
    OneXDeleteEvent(v14);
    goto LABEL_30;
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
      WPP_SF_dd(v9[7], 79, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, v2, v8);
    goto LABEL_29;
  }
  *(_DWORD *)(v14 + 40) = 8;
  v10 = OneXDuplicateRuntimeState(a2, (_QWORD *)(v14 + 48));
  v8 = v10;
  if ( v10 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_29;
    v12 = 80;
    goto LABEL_28;
  }
  v10 = QueueGlobalEvent(v14);
  v8 = v10;
  if ( v10 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_29;
    v12 = 81;
LABEL_28:
    WPP_SF_dd(v11[7], v12, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, v2, v10);
    goto LABEL_29;
  }
LABEL_30:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 82, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180010b20  push    rbx
0x180010b22  push    rbp
0x180010b23  push    rsi
0x180010b24  push    rdi
0x180010b25  push    r14
0x180010b27  push    r15
0x180010b29  sub     rsp, 38h
0x180010b2d  mov     r14d, [rcx+14h]
0x180010b31  mov     rbp, rdx
0x180010b34  mov     rdi, rcx
0x180010b37  mov     [rsp+68h+arg_0], 0
0x180010b40  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b47  lea     r15, WPP_GLOBAL_Control
0x180010b4e  cmp     rcx, r15
0x180010b51  jz      short loc_180010B78
0x180010b53  test    dword ptr [rcx+44h], 800h
0x180010b5a  jz      short loc_180010B78
0x180010b5c  mov     rcx, [rcx+38h]
0x180010b60  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x180010b67  mov     edx, 4Eh ; 'N'
0x180010b6c  call    WPP_SF_
0x180010b71  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b78  mov     esi, [rdi+14h]
0x180010b7b  cmp     rcx, r15
0x180010b7e  jz      short loc_180010B9E
0x180010b80  test    dword ptr [rcx+44h], 800h
0x180010b87  jz      short loc_180010B9E
0x180010b89  mov     rcx, [rcx+38h]
0x180010b8d  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180010b94  mov     edx, 0Ah
0x180010b99  call    WPP_SF_
0x180010b9e  mov     r9d, 43h ; 'C'
0x180010ba4  lea     r8, aOnexcreateeven; "OneXCreateEvent"
0x180010bab  lea     rdx, [rsp+68h+arg_0]
0x180010bb0  mov     ecx, 38h ; '8'
0x180010bb5  call    cs:__imp_AllocateMemory
0x180010bbb  mov     ebx, eax
0x180010bbd  test    eax, eax
0x180010bbf  jz      short loc_180010BF5
0x180010bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180010bc8  cmp     rcx, r15
0x180010bcb  jz      loc_180010CE6
0x180010bd1  test    byte ptr [rcx+44h], 1
0x180010bd5  jz      short loc_180010C1D
0x180010bd7  mov     rcx, [rcx+38h]
0x180010bdb  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180010be2  mov     edx, 0Bh
0x180010be7  mov     [rsp+68h+var_48], eax
0x180010beb  mov     r9d, esi
0x180010bee  call    WPP_SF_dd
0x180010bf3  jmp     short loc_180010C16
0x180010bf5  mov     rax, [rsp+68h+arg_0]
0x180010bfa  mov     dword ptr [rax+10h], 0Ah
0x180010c01  mov     rax, [rsp+68h+arg_0]
0x180010c06  mov     dword ptr [rax+20h], 1
0x180010c0d  mov     rax, [rsp+68h+arg_0]
0x180010c12  mov     [rax+18h], rdi
0x180010c16  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c1d  cmp     rcx, r15
0x180010c20  jz      short loc_180010C4A
0x180010c22  test    dword ptr [rcx+44h], 800h
0x180010c29  jz      short loc_180010C4A
0x180010c2b  mov     rcx, [rcx+38h]
0x180010c2f  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180010c36  mov     edx, 0Ch
0x180010c3b  mov     r9d, ebx
0x180010c3e  call    WPP_SF_D
0x180010c43  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c4a  test    ebx, ebx
0x180010c4c  jz      short loc_180010C6C
0x180010c4e  cmp     rcx, r15
0x180010c51  jz      loc_180010CE6
0x180010c57  test    byte ptr [rcx+44h], 1
0x180010c5b  jz      loc_180010CE6
0x180010c61  mov     edx, 4Fh ; 'O'
0x180010c66  mov     [rsp+68h+var_48], ebx
0x180010c6a  jmp     short loc_180010CD3
0x180010c6c  mov     rax, [rsp+68h+arg_0]
0x180010c71  mov     rcx, rbp
0x180010c74  mov     dword ptr [rax+28h], 8
0x180010c7b  mov     rdx, [rsp+68h+arg_0]
0x180010c80  add     rdx, 30h ; '0'
0x180010c84  call    OneXDuplicateRuntimeState
0x180010c89  mov     ebx, eax
0x180010c8b  test    eax, eax
0x180010c8d  jz      short loc_180010CA8
0x180010c8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c96  cmp     rcx, r15
0x180010c99  jz      short loc_180010CE6
0x180010c9b  test    byte ptr [rcx+44h], 1
0x180010c9f  jz      short loc_180010CE6
0x180010ca1  mov     edx, 50h ; 'P'
0x180010ca6  jmp     short loc_180010CCF
0x180010ca8  mov     rcx, [rsp+68h+arg_0]
0x180010cad  call    QueueGlobalEvent
0x180010cb2  mov     ebx, eax
0x180010cb4  test    eax, eax
0x180010cb6  jz      short loc_180010CF0
0x180010cb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cbf  cmp     rcx, r15
0x180010cc2  jz      short loc_180010CE6
0x180010cc4  test    byte ptr [rcx+44h], 1
0x180010cc8  jz      short loc_180010CE6
0x180010cca  mov     edx, 51h ; 'Q'
0x180010ccf  mov     [rsp+68h+var_48], eax
0x180010cd3  mov     rcx, [rcx+38h]
0x180010cd7  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x180010cde  mov     r9d, r14d
0x180010ce1  call    WPP_SF_dd
0x180010ce6  mov     rcx, [rsp+68h+arg_0]
0x180010ceb  call    OneXDeleteEvent
0x180010cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cf7  cmp     rcx, r15
0x180010cfa  jz      short loc_180010D1D
0x180010cfc  test    dword ptr [rcx+44h], 800h
0x180010d03  jz      short loc_180010D1D
0x180010d05  mov     rcx, [rcx+38h]
0x180010d09  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x180010d10  mov     edx, 52h ; 'R'
0x180010d15  mov     r9d, ebx
0x180010d18  call    WPP_SF_D
0x180010d1d  mov     eax, ebx
0x180010d1f  add     rsp, 38h
0x180010d23  pop     r15
0x180010d25  pop     r14
0x180010d27  pop     rdi
0x180010d28  pop     rsi
0x180010d29  pop     rbp
0x180010d2a  pop     rbx
0x180010d2b  retn
```
