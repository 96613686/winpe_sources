# CmCreateVc

- ea: `0x1400259b0`
- end: `0x140025a51`
- name: `CmCreateVc`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000a290`
- `0x1400259b0`
- `0x14002c01c`

## pseudocode

```c
__int64 __fastcall CmCreateVc(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *CmVcCB; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids);
  }
  CmVcCB = NdisWanAllocateCmVcCB(a1, a2);
  if ( !CmVcCB )
    return 3221225626LL;
  *a3 = CmVcCB;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x1400259b0  push    rbx
0x1400259b2  push    rsi
0x1400259b3  push    rdi
0x1400259b4  push    r14
0x1400259b6  sub     rsp, 28h
0x1400259ba  mov     rbx, r8
0x1400259bd  mov     rdi, rdx
0x1400259c0  mov     rsi, rcx
0x1400259c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400259ca  lea     r14, WPP_GLOBAL_Control
0x1400259d1  cmp     rcx, r14
0x1400259d4  jz      short loc_1400259FA
0x1400259d6  test    dword ptr [rcx+2Ch], 10000h
0x1400259dd  jz      short loc_1400259FA
0x1400259df  cmp     byte ptr [rcx+29h], 5
0x1400259e3  jb      short loc_1400259FA
0x1400259e5  mov     rcx, [rcx+18h]
0x1400259e9  lea     r8, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids
0x1400259f0  mov     edx, 0Ah
0x1400259f5  call    WPP_SF_
0x1400259fa  mov     rdx, rdi
0x1400259fd  mov     rcx, rsi
0x140025a00  call    NdisWanAllocateCmVcCB
0x140025a05  test    rax, rax
0x140025a08  jnz     short loc_140025A11
0x140025a0a  mov     eax, 0C000009Ah
0x140025a0f  jmp     short loc_140025A46
0x140025a11  mov     [rbx], rax
0x140025a14  mov     rcx, cs:WPP_GLOBAL_Control
0x140025a1b  cmp     rcx, r14
0x140025a1e  jz      short loc_140025A44
0x140025a20  test    dword ptr [rcx+2Ch], 10000h
0x140025a27  jz      short loc_140025A44
0x140025a29  cmp     byte ptr [rcx+29h], 5
0x140025a2d  jb      short loc_140025A44
0x140025a2f  mov     rcx, [rcx+18h]
0x140025a33  lea     r8, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids
0x140025a3a  mov     edx, 0Bh
0x140025a3f  call    WPP_SF_
0x140025a44  xor     eax, eax
0x140025a46  add     rsp, 28h
0x140025a4a  pop     r14
0x140025a4c  pop     rdi
0x140025a4d  pop     rsi
0x140025a4e  pop     rbx
0x140025a4f  retn
```
