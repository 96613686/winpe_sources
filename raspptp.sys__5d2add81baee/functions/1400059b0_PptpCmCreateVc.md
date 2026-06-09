# PptpCmCreateVc

- ea: `0x1400059b0`
- end: `0x140005bea`
- name: `PptpCmCreateVc`
- size: `570`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140001a70`
- `0x14000360c`
- `0x140003e08`
- `0x140004204`
- `0x1400059b0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140005b74`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005b74`

## pseudocode

```c
__int64 __fastcall PptpCmCreateVc(_DWORD *a1, __int64 a2, __int64 *a3)
{
  __int64 v6; // rax
  __int64 v7; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
  }
  v6 = CallFindAndLock((__int64)a1, a2, (unsigned int)a3);
  v7 = v6;
  if ( v6 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      *(_BYTE *)(v6 + 194) = 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids, v6);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids, v7);
        }
      }
    }
    *(_QWORD *)(v7 + 224) = a2;
    *(_OWORD *)(v7 + 240) = 0;
    *(_OWORD *)(v7 + 256) = 0;
    *(_DWORD *)(v7 + 240) = a1[19];
    *(_DWORD *)(v7 + 244) = a1[19];
    *(_DWORD *)(v7 + 248) = a1[21];
    *(_DWORD *)(v7 + 252) = a1[21];
    *(_DWORD *)(v7 + 264) = a1[22];
    *(_DWORD *)(v7 + 268) = a1[22];
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
    }
    *(_DWORD *)(v7 + 424) |= 1u;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
    }
    _InterlockedIncrement((volatile signed __int32 *)v7);
    DereferenceRefCount(v7);
    KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 96), *(_BYTE *)(v7 + 104));
    *a3 = v7;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids, v7);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
      }
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x1400059b0  push    rbx
0x1400059b2  push    rbp
0x1400059b3  push    rsi
0x1400059b4  push    rdi
0x1400059b5  push    r12
0x1400059b7  push    r15
0x1400059b9  sub     rsp, 28h
0x1400059bd  mov     rsi, r8
0x1400059c0  mov     rbp, rdx
0x1400059c3  mov     rdi, rcx
0x1400059c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059cd  lea     r12, WPP_GLOBAL_Control
0x1400059d4  lea     r15, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x1400059db  cmp     rcx, r12
0x1400059de  jz      short loc_1400059FE
0x1400059e0  mov     eax, [rcx+2Ch]
0x1400059e3  test    al, 4
0x1400059e5  jz      short loc_1400059FE
0x1400059e7  cmp     byte ptr [rcx+29h], 2
0x1400059eb  jb      short loc_1400059FE
0x1400059ed  mov     rcx, [rcx+18h]
0x1400059f1  mov     edx, 24h ; '$'
0x1400059f6  mov     r8, r15
0x1400059f9  call    WPP_SF_
0x1400059fe  mov     rcx, rdi
0x140005a01  call    CallFindAndLock
0x140005a06  mov     rbx, rax
0x140005a09  test    rax, rax
0x140005a0c  jnz     short loc_140005A40
0x140005a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a15  cmp     rcx, r12
0x140005a18  jz      short loc_140005A36
0x140005a1a  mov     eax, [rcx+2Ch]
0x140005a1d  test    al, 4
0x140005a1f  jz      short loc_140005A36
0x140005a21  cmp     byte ptr [rcx+29h], 1
0x140005a25  jb      short loc_140005A36
0x140005a27  mov     rcx, [rcx+18h]
0x140005a2b  lea     edx, [rbx+25h]
0x140005a2e  mov     r8, r15
0x140005a31  call    WPP_SF_
0x140005a36  mov     eax, 0C000009Ah
0x140005a3b  jmp     loc_140005BDC
0x140005a40  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a47  mov     edx, 800h
0x140005a4c  test    [rcx+2Ch], edx
0x140005a4f  jz      short loc_140005AB9
0x140005a51  cmp     byte ptr [rcx+29h], 4
0x140005a55  jb      short loc_140005AB9
0x140005a57  mov     byte ptr [rax+0C2h], 1
0x140005a5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a65  cmp     rcx, r12
0x140005a68  jz      short loc_140005AB9
0x140005a6a  test    [rcx+2Ch], edx
0x140005a6d  jz      short loc_140005A8E
0x140005a6f  cmp     byte ptr [rcx+29h], 4
0x140005a73  jb      short loc_140005A8E
0x140005a75  mov     rcx, [rcx+18h]
0x140005a79  mov     edx, 26h ; '&'
0x140005a7e  mov     r9, rbx
0x140005a81  mov     r8, r15
0x140005a84  call    WPP_SF_q
0x140005a89  mov     edx, 800h
0x140005a8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a95  cmp     rcx, r12
0x140005a98  jz      short loc_140005AB9
0x140005a9a  test    [rcx+2Ch], edx
0x140005a9d  jz      short loc_140005AB9
0x140005a9f  cmp     byte ptr [rcx+29h], 4
0x140005aa3  jb      short loc_140005AB9
0x140005aa5  mov     rcx, [rcx+18h]
0x140005aa9  mov     edx, 27h ; '''
0x140005aae  mov     r9, rbx
0x140005ab1  mov     r8, r15
0x140005ab4  call    WPP_SF_q
0x140005ab9  mov     [rbx+0E0h], rbp
0x140005ac0  xorps   xmm0, xmm0
0x140005ac3  movups  xmmword ptr [rbx+0F0h], xmm0
0x140005aca  movups  xmmword ptr [rbx+100h], xmm0
0x140005ad1  mov     eax, [rdi+4Ch]
0x140005ad4  mov     [rbx+0F0h], eax
0x140005ada  mov     eax, [rdi+4Ch]
0x140005add  mov     [rbx+0F4h], eax
0x140005ae3  mov     eax, [rdi+54h]
0x140005ae6  mov     [rbx+0F8h], eax
0x140005aec  mov     eax, [rdi+54h]
0x140005aef  mov     [rbx+0FCh], eax
0x140005af5  mov     eax, [rdi+58h]
0x140005af8  mov     [rbx+108h], eax
0x140005afe  mov     eax, [rdi+58h]
0x140005b01  mov     [rbx+10Ch], eax
0x140005b07  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b0e  cmp     rcx, r12
0x140005b11  jz      short loc_140005B31
0x140005b13  mov     eax, [rcx+2Ch]
0x140005b16  test    al, 4
0x140005b18  jz      short loc_140005B31
0x140005b1a  cmp     byte ptr [rcx+29h], 2
0x140005b1e  jb      short loc_140005B31
0x140005b20  mov     rcx, [rcx+18h]
0x140005b24  mov     edx, 28h ; '('
0x140005b29  mov     r8, r15
0x140005b2c  call    WPP_SF_
0x140005b31  or      dword ptr [rbx+1A8h], 1
0x140005b38  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b3f  cmp     rcx, r12
0x140005b42  jz      short loc_140005B62
0x140005b44  mov     eax, [rcx+2Ch]
0x140005b47  test    al, 4
0x140005b49  jz      short loc_140005B62
0x140005b4b  cmp     byte ptr [rcx+29h], 2
0x140005b4f  jb      short loc_140005B62
0x140005b51  mov     rcx, [rcx+18h]
0x140005b55  mov     edx, 29h ; ')'
0x140005b5a  mov     r8, r15
0x140005b5d  call    WPP_SF_
0x140005b62  lock inc dword ptr [rbx]
0x140005b65  mov     rcx, rbx
0x140005b68  call    DereferenceRefCount
0x140005b6d  mov     dl, [rbx+68h]; NewIrql
0x140005b70  lea     rcx, [rbx+60h]; SpinLock
0x140005b74  call    cs:__imp_KeReleaseSpinLock
0x140005b7b  nop     dword ptr [rax+rax+00h]
0x140005b80  mov     [rsi], rbx
0x140005b83  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b8a  cmp     rcx, r12
0x140005b8d  jz      short loc_140005BDA
0x140005b8f  mov     eax, [rcx+2Ch]
0x140005b92  test    al, 4
0x140005b94  jz      short loc_140005BB0
0x140005b96  cmp     byte ptr [rcx+29h], 2
0x140005b9a  jb      short loc_140005BB0
0x140005b9c  mov     rcx, [rcx+18h]
0x140005ba0  mov     edx, 2Ah ; '*'
0x140005ba5  mov     r9, rbx
0x140005ba8  mov     r8, r15
0x140005bab  call    WPP_SF_q
0x140005bb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140005bb7  cmp     rcx, r12
0x140005bba  jz      short loc_140005BDA
0x140005bbc  mov     eax, [rcx+2Ch]
0x140005bbf  test    al, 4
0x140005bc1  jz      short loc_140005BDA
0x140005bc3  cmp     byte ptr [rcx+29h], 2
0x140005bc7  jb      short loc_140005BDA
0x140005bc9  mov     rcx, [rcx+18h]
0x140005bcd  mov     edx, 2Bh ; '+'
0x140005bd2  mov     r8, r15
0x140005bd5  call    WPP_SF_
0x140005bda  xor     eax, eax
0x140005bdc  add     rsp, 28h
0x140005be0  pop     r15
0x140005be2  pop     r12
0x140005be4  pop     rdi
0x140005be5  pop     rsi
0x140005be6  pop     rbp
0x140005be7  pop     rbx
0x140005be8  retn
```
