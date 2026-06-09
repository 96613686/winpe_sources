# NatDereferenceAddressPoolEntry

- ea: `0x1400138fc`
- end: `0x140013b69`
- name: `NatDereferenceAddressPoolEntry`
- size: `621`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140008a54`
- `0x14000ce94`
- `0x14001169c`
- `0x140013550`
- `0x14001379c`
- `0x14001d05c`
- `0x14001d7ac`
- `0x14001e4e4`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x1400138fc`

## import_xrefs

- `ntoskrnl!RtlDelete` at `0x1400139e9`
- `ntoskrnl!RtlDelete` at `0x140013b02`
- `ntoskrnl!RtlDelete` at `0x1400139e9`
- `ntoskrnl!RtlDelete` at `0x140013b02`
- `ntoskrnl!RtlClearBits` at `0x140013ad6`
- `ntoskrnl!RtlClearBits` at `0x140013ad6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b1a`

## pseudocode

```c
__int64 __fastcall NatDereferenceAddressPoolEntry(__int64 a1, __int64 a2)
{
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rdx
  __int64 v8; // rdi
  unsigned int v9; // r10d
  unsigned __int32 v10; // edx
  __int64 v11; // r11
  __int64 v12; // rcx
  unsigned __int32 v13; // r8d
  __int64 v14; // rcx
  _QWORD *v15; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
  }
  if ( (*(_DWORD *)(a2 + 72) & 0x10) != 0 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 76), 0xFFFFFFFF) != 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          v5 = 99;
LABEL_45:
          WPP_SF_d(v4->AttachedDevice, v5, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, 0);
          return 0;
        }
      }
      return 0;
    }
    if ( *(int *)(a2 + 72) >= 0 )
    {
      v6 = *(_QWORD *)(a2 + 24);
      if ( *(_QWORD *)(v6 + 8) != a2 + 24 )
        goto LABEL_47;
      v7 = *(_QWORD **)(a2 + 32);
      if ( *v7 != a2 + 24 )
        goto LABEL_47;
      *v7 = v6;
      *(_QWORD *)(v6 + 8) = v7;
      *(_QWORD *)(a1 + 144) = RtlDelete((PRTL_SPLAY_LINKS)a2);
    }
    v8 = *(_QWORD *)(a2 + 56);
    ExFreePoolWithTag((PVOID)a2, 0);
  }
  else
  {
    v8 = a2;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 76), 0xFFFFFFFF) == 1 )
  {
    if ( *(int *)(v8 + 72) < 0 )
    {
LABEL_41:
      ExFreePoolWithTag((PVOID)v8, 0);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v5 = 102;
        goto LABEL_45;
      }
      return 0;
    }
    v9 = *(_DWORD *)(a1 + 132);
    v10 = _byteswap_ulong(*(_DWORD *)(v8 + 52));
    if ( v9 )
    {
      v11 = *(_QWORD *)(a1 + 136);
      v12 = 0;
      while ( 1 )
      {
        v13 = _byteswap_ulong(*(_DWORD *)(v11 + 24 * v12));
        if ( v10 >= v13 && v10 <= _byteswap_ulong(*(_DWORD *)(v11 + 24 * v12 + 4)) )
          break;
        v12 = (unsigned int)(v12 + 1);
        if ( (unsigned int)v12 >= v9 )
          goto LABEL_38;
      }
      RtlClearBits(*(PRTL_BITMAP *)(v11 + 24 * v12 + 16), v10 - v13, 1u);
    }
LABEL_38:
    v14 = *(_QWORD *)(v8 + 24);
    if ( *(_QWORD *)(v14 + 8) == v8 + 24 )
    {
      v15 = *(_QWORD **)(v8 + 32);
      if ( *v15 == v8 + 24 )
      {
        *v15 = v14;
        *(_QWORD *)(v14 + 8) = v15;
        *(_QWORD *)(a1 + 144) = RtlDelete((PRTL_SPLAY_LINKS)v8);
        goto LABEL_41;
      }
    }
LABEL_47:
    __fastfail(3u);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v5 = 101;
      goto LABEL_45;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400138fc  push    rbx
0x1400138fe  push    rsi
0x1400138ff  push    rdi
0x140013900  push    r12
0x140013902  push    r14
0x140013904  sub     rsp, 20h
0x140013908  mov     rbx, rdx
0x14001390b  mov     rsi, rcx
0x14001390e  mov     rcx, cs:WPP_GLOBAL_Control
0x140013915  lea     r14, WPP_GLOBAL_Control
0x14001391c  lea     r12, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140013923  cmp     rcx, r14
0x140013926  jz      short loc_140013946
0x140013928  mov     eax, [rcx+2Ch]
0x14001392b  test    al, 1
0x14001392d  jz      short loc_140013946
0x14001392f  cmp     byte ptr [rcx+29h], 6
0x140013933  jb      short loc_140013946
0x140013935  mov     rcx, [rcx+18h]
0x140013939  mov     edx, 61h ; 'a'
0x14001393e  mov     r8, r12
0x140013941  call    WPP_SF_
0x140013946  mov     eax, [rbx+48h]
0x140013949  test    al, 10h
0x14001394b  jz      loc_140013A13
0x140013951  or      eax, 0FFFFFFFFh
0x140013954  lock xadd [rbx+4Ch], eax
0x140013959  cmp     eax, 1
0x14001395c  jz      short loc_1400139BB
0x14001395e  mov     rcx, cs:WPP_GLOBAL_Control
0x140013965  cmp     rcx, r14
0x140013968  jz      loc_140013B53
0x14001396e  mov     eax, [rcx+2Ch]
0x140013971  test    al, 1
0x140013973  jz      short loc_14001398C
0x140013975  cmp     byte ptr [rcx+29h], 5
0x140013979  jb      short loc_14001398C
0x14001397b  mov     rcx, [rcx+18h]
0x14001397f  mov     edx, 62h ; 'b'
0x140013984  mov     r8, r12
0x140013987  call    WPP_SF_
0x14001398c  mov     rcx, cs:WPP_GLOBAL_Control
0x140013993  cmp     rcx, r14
0x140013996  jz      loc_140013B53
0x14001399c  mov     eax, [rcx+2Ch]
0x14001399f  test    al, 1
0x1400139a1  jz      loc_140013B53
0x1400139a7  cmp     byte ptr [rcx+29h], 6
0x1400139ab  jb      loc_140013B53
0x1400139b1  mov     edx, 63h ; 'c'
0x1400139b6  jmp     loc_140013B44
0x1400139bb  cmp     dword ptr [rbx+48h], 0
0x1400139bf  jl      short loc_1400139FC
0x1400139c1  lea     rax, [rbx+18h]
0x1400139c5  mov     rcx, [rax]
0x1400139c8  cmp     [rcx+8], rax
0x1400139cc  jnz     loc_140013B62
0x1400139d2  mov     rdx, [rax+8]
0x1400139d6  cmp     [rdx], rax
0x1400139d9  jnz     loc_140013B62
0x1400139df  mov     [rdx], rcx
0x1400139e2  mov     [rcx+8], rdx
0x1400139e6  mov     rcx, rbx; Links
0x1400139e9  call    cs:__imp_RtlDelete
0x1400139f0  nop     dword ptr [rax+rax+00h]
0x1400139f5  mov     [rsi+90h], rax
0x1400139fc  mov     rdi, [rbx+38h]
0x140013a00  xor     edx, edx; Tag
0x140013a02  mov     rcx, rbx; P
0x140013a05  call    cs:__imp_ExFreePoolWithTag
0x140013a0c  nop     dword ptr [rax+rax+00h]
0x140013a11  jmp     short loc_140013A16
0x140013a13  mov     rdi, rbx
0x140013a16  or      eax, 0FFFFFFFFh
0x140013a19  lock xadd [rdi+4Ch], eax
0x140013a1e  cmp     eax, 1
0x140013a21  jz      short loc_140013A80
0x140013a23  mov     rcx, cs:WPP_GLOBAL_Control
0x140013a2a  cmp     rcx, r14
0x140013a2d  jz      loc_140013B53
0x140013a33  mov     eax, [rcx+2Ch]
0x140013a36  test    al, 1
0x140013a38  jz      short loc_140013A51
0x140013a3a  cmp     byte ptr [rcx+29h], 5
0x140013a3e  jb      short loc_140013A51
0x140013a40  mov     rcx, [rcx+18h]
0x140013a44  mov     edx, 64h ; 'd'
0x140013a49  mov     r8, r12
0x140013a4c  call    WPP_SF_
0x140013a51  mov     rcx, cs:WPP_GLOBAL_Control
0x140013a58  cmp     rcx, r14
0x140013a5b  jz      loc_140013B53
0x140013a61  mov     eax, [rcx+2Ch]
0x140013a64  test    al, 1
0x140013a66  jz      loc_140013B53
0x140013a6c  cmp     byte ptr [rcx+29h], 6
0x140013a70  jb      loc_140013B53
0x140013a76  mov     edx, 65h ; 'e'
0x140013a7b  jmp     loc_140013B44
0x140013a80  cmp     dword ptr [rdi+48h], 0
0x140013a84  jl      loc_140013B15
0x140013a8a  mov     edx, [rdi+34h]
0x140013a8d  mov     r10d, [rsi+84h]
0x140013a94  bswap   edx
0x140013a96  test    r10d, r10d
0x140013a99  jz      short loc_140013AE2
0x140013a9b  mov     r11, [rsi+88h]
0x140013aa2  xor     ecx, ecx
0x140013aa4  lea     r9, [rcx+rcx*2]
0x140013aa8  mov     r8d, [r11+r9*8]
0x140013aac  bswap   r8d
0x140013aaf  cmp     edx, r8d
0x140013ab2  jb      short loc_140013ABF
0x140013ab4  mov     eax, [r11+r9*8+4]
0x140013ab9  bswap   eax
0x140013abb  cmp     edx, eax
0x140013abd  jbe     short loc_140013AC8
0x140013abf  inc     ecx
0x140013ac1  cmp     ecx, r10d
0x140013ac4  jb      short loc_140013AA4
0x140013ac6  jmp     short loc_140013AE2
0x140013ac8  mov     rcx, [r11+r9*8+10h]; BitMapHeader
0x140013acd  sub     edx, r8d; StartingIndex
0x140013ad0  mov     r8d, 1; NumberToClear
0x140013ad6  call    cs:__imp_RtlClearBits
0x140013add  nop     dword ptr [rax+rax+00h]
0x140013ae2  lea     rax, [rdi+18h]
0x140013ae6  mov     rcx, [rax]
0x140013ae9  cmp     [rcx+8], rax
0x140013aed  jnz     short loc_140013B62
0x140013aef  mov     rdx, [rax+8]
0x140013af3  cmp     [rdx], rax
0x140013af6  jnz     short loc_140013B62
0x140013af8  mov     [rdx], rcx
0x140013afb  mov     [rcx+8], rdx
0x140013aff  mov     rcx, rdi; Links
0x140013b02  call    cs:__imp_RtlDelete
0x140013b09  nop     dword ptr [rax+rax+00h]
0x140013b0e  mov     [rsi+90h], rax
0x140013b15  xor     edx, edx; Tag
0x140013b17  mov     rcx, rdi; P
0x140013b1a  call    cs:__imp_ExFreePoolWithTag
0x140013b21  nop     dword ptr [rax+rax+00h]
0x140013b26  mov     rcx, cs:WPP_GLOBAL_Control
0x140013b2d  cmp     rcx, r14
0x140013b30  jz      short loc_140013B53
0x140013b32  mov     eax, [rcx+2Ch]
0x140013b35  test    al, 1
0x140013b37  jz      short loc_140013B53
0x140013b39  cmp     byte ptr [rcx+29h], 6
0x140013b3d  jb      short loc_140013B53
0x140013b3f  mov     edx, 66h ; 'f'
0x140013b44  mov     rcx, [rcx+18h]
0x140013b48  xor     r9d, r9d
0x140013b4b  mov     r8, r12
0x140013b4e  call    WPP_SF_d
0x140013b53  xor     eax, eax
0x140013b55  add     rsp, 20h
0x140013b59  pop     r14
0x140013b5b  pop     r12
0x140013b5d  pop     rdi
0x140013b5e  pop     rsi
0x140013b5f  pop     rbx
0x140013b60  retn
0x140013b62  mov     ecx, 3
0x140013b67  int     29h; Win8: RtlFailFast(ecx)
```
