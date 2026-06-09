# CallSetLinkInfo

- ea: `0x140010c14`
- end: `0x140010ded`
- name: `CallSetLinkInfo`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400018c0`

## callees

- `0x140003d58`
- `0x140003e08`
- `0x140004374`
- `0x1400076d0`
- `0x140007ac0`
- `0x140010c14`
- `0x140011b90`
- `0x140013164`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140010ca1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d05`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010ca1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d05`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010c82`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010c82`

## pseudocode

```c
__int64 __fastcall CallSetLinkInfo(__int64 a1, _OWORD *a2)
{
  KIRQL v4; // al
  bool v5; // zf
  KSPIN_LOCK *v6; // rcx
  unsigned int v7; // ebx
  __int128 v8; // xmm1
  __int64 v9; // rsi
  __int64 v10; // rdi
  struct _DEVICE_OBJECT *AttachedDevice; // rbx
  __int64 StringFromSockAddr; // rax
  _BYTE v14[80]; // [rsp+20h] [rbp-88h] BYREF

  memset(v14, 0, 0x41u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 89, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
  }
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  v5 = *(_DWORD *)(a1 + 112) == 9;
  v6 = (KSPIN_LOCK *)(a1 + 96);
  *(_BYTE *)(a1 + 104) = v4;
  if ( v5 )
  {
    *(_OWORD *)(a1 + 240) = *a2;
    v8 = a2[1];
    v9 = *(_QWORD *)(a1 + 80);
    *(_OWORD *)(a1 + 256) = v8;
    KeReleaseSpinLock(v6, v4);
    v10 = CtlAllocPacket(v9, 15);
    if ( v10 )
    {
      *(_WORD *)(v10 + 12) = __ROR2__(*(_WORD *)(a1 + 316), 8);
      *(_DWORD *)(v10 + 16) = _byteswap_ulong(*(_DWORD *)(a1 + 264));
      *(_DWORD *)(v10 + 20) = _byteswap_ulong(*(_DWORD *)(a1 + 268));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
        StringFromSockAddr = GetStringFromSockAddr(v9 + 368, v14);
        WPP_SF_s(AttachedDevice, 92, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids, StringFromSockAddr);
      }
      return (unsigned int)CtlSend(v9, v10);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
      }
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    v7 = -1073741823;
    KeReleaseSpinLock(v6, v4);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 90, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140010c14  push    rbx
0x140010c16  push    rsi
0x140010c17  push    rdi
0x140010c18  push    r14
0x140010c1a  sub     rsp, 88h
0x140010c21  mov     rax, cs:__security_cookie
0x140010c28  xor     rax, rsp
0x140010c2b  mov     [rsp+0A8h+var_38], rax
0x140010c30  mov     rsi, rdx
0x140010c33  mov     rbx, rcx
0x140010c36  xor     edx, edx; Val
0x140010c38  lea     rcx, [rsp+0A8h+var_88]; void *
0x140010c3d  lea     r8d, [rdx+41h]; Size
0x140010c41  call    memset
0x140010c46  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c4d  lea     r14, WPP_GLOBAL_Control
0x140010c54  cmp     rcx, r14
0x140010c57  jz      short loc_140010C7B
0x140010c59  mov     eax, [rcx+2Ch]
0x140010c5c  test    al, 10h
0x140010c5e  jz      short loc_140010C7B
0x140010c60  cmp     byte ptr [rcx+29h], 2
0x140010c64  jb      short loc_140010C7B
0x140010c66  mov     rcx, [rcx+18h]
0x140010c6a  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140010c71  mov     edx, 59h ; 'Y'
0x140010c76  call    WPP_SF_
0x140010c7b  lea     rdi, [rbx+60h]
0x140010c7f  mov     rcx, rdi; SpinLock
0x140010c82  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010c89  nop     dword ptr [rax+rax+00h]
0x140010c8e  cmp     dword ptr [rbx+70h], 9
0x140010c92  mov     rcx, rdi; SpinLock
0x140010c95  mov     [rbx+68h], al
0x140010c98  mov     dl, al; NewIrql
0x140010c9a  jz      short loc_140010CEC
0x140010c9c  mov     ebx, 0C0000001h
0x140010ca1  call    cs:__imp_KeReleaseSpinLock
0x140010ca8  nop     dword ptr [rax+rax+00h]
0x140010cad  mov     rcx, cs:WPP_GLOBAL_Control
0x140010cb4  cmp     rcx, r14
0x140010cb7  jz      loc_140010DD0
0x140010cbd  mov     eax, [rcx+2Ch]
0x140010cc0  test    al, 10h
0x140010cc2  jz      loc_140010DD0
0x140010cc8  cmp     byte ptr [rcx+29h], 1
0x140010ccc  jb      loc_140010DD0
0x140010cd2  mov     rcx, [rcx+18h]
0x140010cd6  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140010cdd  mov     edx, 5Ah ; 'Z'
0x140010ce2  call    WPP_SF_
0x140010ce7  jmp     loc_140010DD0
0x140010cec  movups  xmm0, xmmword ptr [rsi]
0x140010cef  movups  xmmword ptr [rbx+0F0h], xmm0
0x140010cf6  movups  xmm1, xmmword ptr [rsi+10h]
0x140010cfa  mov     rsi, [rbx+50h]
0x140010cfe  movups  xmmword ptr [rbx+100h], xmm1
0x140010d05  call    cs:__imp_KeReleaseSpinLock
0x140010d0c  nop     dword ptr [rax+rax+00h]
0x140010d11  mov     edx, 0Fh
0x140010d16  mov     rcx, rsi
0x140010d19  call    CtlAllocPacket
0x140010d1e  mov     rdi, rax
0x140010d21  test    rax, rax
0x140010d24  jnz     short loc_140010D59
0x140010d26  mov     rcx, cs:WPP_GLOBAL_Control
0x140010d2d  cmp     rcx, r14
0x140010d30  jz      short loc_140010D52
0x140010d32  mov     eax, [rcx+2Ch]
0x140010d35  test    al, 1
0x140010d37  jz      short loc_140010D52
0x140010d39  cmp     byte ptr [rcx+29h], 1
0x140010d3d  jb      short loc_140010D52
0x140010d3f  mov     rcx, [rcx+18h]
0x140010d43  lea     edx, [rdi+5Bh]
0x140010d46  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140010d4d  call    WPP_SF_
0x140010d52  mov     ebx, 0C000009Ah
0x140010d57  jmp     short loc_140010DD0
0x140010d59  movzx   eax, word ptr [rbx+13Ch]
0x140010d60  ror     ax, 8
0x140010d64  mov     [rdi+0Ch], ax
0x140010d68  mov     eax, [rbx+108h]
0x140010d6e  bswap   eax
0x140010d70  mov     [rdi+10h], eax
0x140010d73  mov     eax, [rbx+10Ch]
0x140010d79  bswap   eax
0x140010d7b  mov     [rdi+14h], eax
0x140010d7e  mov     rbx, cs:WPP_GLOBAL_Control
0x140010d85  cmp     rbx, r14
0x140010d88  jz      short loc_140010DC3
0x140010d8a  mov     eax, [rbx+2Ch]
0x140010d8d  test    al, 8
0x140010d8f  jz      short loc_140010DC3
0x140010d91  cmp     byte ptr [rbx+29h], 2
0x140010d95  jb      short loc_140010DC3
0x140010d97  mov     rbx, [rbx+18h]
0x140010d9b  lea     rcx, [rsi+170h]
0x140010da2  lea     rdx, [rsp+0A8h+var_88]
0x140010da7  call    GetStringFromSockAddr
0x140010dac  mov     r9, rax
0x140010daf  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140010db6  mov     edx, 5Ch ; '\'
0x140010dbb  mov     rcx, rbx
0x140010dbe  call    WPP_SF_s
0x140010dc3  mov     rdx, rdi
0x140010dc6  mov     rcx, rsi
0x140010dc9  call    CtlSend
0x140010dce  mov     ebx, eax
0x140010dd0  mov     eax, ebx
0x140010dd2  mov     rcx, [rsp+0A8h+var_38]
0x140010dd7  xor     rcx, rsp; StackCookie
0x140010dda  call    __security_check_cookie
0x140010ddf  add     rsp, 88h
0x140010de6  pop     r14
0x140010de8  pop     rdi
0x140010de9  pop     rsi
0x140010dea  pop     rbx
0x140010deb  retn
```
