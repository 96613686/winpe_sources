# NatReverseTcpStateCheck

- ea: `0x14002040c`
- end: `0x140020573`
- name: `NatReverseTcpStateCheck`
- size: `359`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140022d70`
- `0x140023160`
- `0x140023800`
- `0x140023940`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14002040c`

## pseudocode

```c
__int64 __fastcall NatReverseTcpStateCheck(__int64 a1, __int64 a2)
{
  unsigned __int16 v4; // cx
  int v5; // edx
  unsigned int v6; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x81u,
      (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
  }
  v4 = *(_WORD *)(a2 + 12) & 0x3F00;
  if ( DisableTcpFlagChecks )
    v4 = *(_WORD *)(a2 + 12) & 0x1700;
  v5 = *(_DWORD *)(a1 + 240);
  if ( (v5 & 0x200) != 0 )
  {
    v6 = (v4 >> 9) & 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x82u,
        (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids,
        v6);
    }
    return v6;
  }
  if ( ((v4 - 4608) & 0xF7FF) != 0 )
  {
    if ( ((v4 - 1024) & 0xEFFF) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_d(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x83u,
          (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids,
          1);
      }
      return 1;
    }
  }
  else
  {
    *(_DWORD *)(a1 + 240) = v5 | 4;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x84u,
      (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x14002040c  mov     [rsp+arg_0], rbx
0x140020411  mov     [rsp+arg_8], rdi
0x140020416  push    r14
0x140020418  sub     rsp, 20h
0x14002041c  mov     rdi, rdx
0x14002041f  mov     rbx, rcx
0x140020422  mov     rcx, cs:WPP_GLOBAL_Control
0x140020429  lea     r14, WPP_GLOBAL_Control
0x140020430  cmp     rcx, r14
0x140020433  jz      short loc_140020457
0x140020435  mov     eax, [rcx+2Ch]
0x140020438  test    al, 1
0x14002043a  jz      short loc_140020457
0x14002043c  cmp     byte ptr [rcx+29h], 6
0x140020440  jb      short loc_140020457
0x140020442  mov     rcx, [rcx+18h]
0x140020446  lea     r8, WPP_876e08a63f053efae1df392b423d899c_Traceguids
0x14002044d  mov     edx, 81h
0x140020452  call    WPP_SF_
0x140020457  mov     ecx, 3F00h
0x14002045c  and     cx, [rdi+0Ch]
0x140020460  cmp     cs:DisableTcpFlagChecks, 0
0x140020467  jz      short loc_140020471
0x140020469  mov     eax, 0D7FFh
0x14002046e  and     cx, ax
0x140020471  mov     edx, [rbx+0F0h]
0x140020477  bt      edx, 9
0x14002047b  jnb     short loc_1400204BE
0x14002047d  movzx   ebx, cx
0x140020480  shr     ebx, 9
0x140020483  and     ebx, 1
0x140020486  mov     rcx, cs:WPP_GLOBAL_Control
0x14002048d  cmp     rcx, r14
0x140020490  jz      short loc_1400204B7
0x140020492  mov     eax, [rcx+2Ch]
0x140020495  test    al, 1
0x140020497  jz      short loc_1400204B7
0x140020499  cmp     byte ptr [rcx+29h], 6
0x14002049d  jb      short loc_1400204B7
0x14002049f  mov     rcx, [rcx+18h]
0x1400204a3  lea     r8, WPP_876e08a63f053efae1df392b423d899c_Traceguids
0x1400204aa  mov     edx, 82h
0x1400204af  mov     r9d, ebx
0x1400204b2  call    WPP_SF_d
0x1400204b7  mov     eax, ebx
0x1400204b9  jmp     loc_140020561
0x1400204be  mov     r8d, 1200h
0x1400204c4  movzx   eax, cx
0x1400204c7  sub     ax, r8w
0x1400204cb  mov     r8d, 0F7FFh
0x1400204d1  test    r8w, ax
0x1400204d5  jz      short loc_140020525
0x1400204d7  mov     eax, 400h
0x1400204dc  sub     cx, ax
0x1400204df  mov     eax, 0EFFFh
0x1400204e4  test    ax, cx
0x1400204e7  jz      short loc_14002052E
0x1400204e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400204f0  cmp     rcx, r14
0x1400204f3  jz      short loc_14002051E
0x1400204f5  mov     edx, [rcx+2Ch]
0x1400204f8  test    dl, 1
0x1400204fb  jz      short loc_14002051E
0x1400204fd  cmp     byte ptr [rcx+29h], 6
0x140020501  jb      short loc_14002051E
0x140020503  mov     rcx, [rcx+18h]
0x140020507  lea     r8, WPP_876e08a63f053efae1df392b423d899c_Traceguids
0x14002050e  mov     edx, 83h
0x140020513  mov     r9d, 1
0x140020519  call    WPP_SF_d
0x14002051e  mov     eax, 1
0x140020523  jmp     short loc_140020561
0x140020525  or      edx, 4
0x140020528  mov     [rbx+0F0h], edx
0x14002052e  mov     rcx, cs:WPP_GLOBAL_Control
0x140020535  cmp     rcx, r14
0x140020538  jz      short loc_14002055F
0x14002053a  mov     eax, [rcx+2Ch]
0x14002053d  test    al, 1
0x14002053f  jz      short loc_14002055F
0x140020541  cmp     byte ptr [rcx+29h], 6
0x140020545  jb      short loc_14002055F
0x140020547  mov     rcx, [rcx+18h]
0x14002054b  lea     r8, WPP_876e08a63f053efae1df392b423d899c_Traceguids
0x140020552  mov     edx, 84h
0x140020557  xor     r9d, r9d
0x14002055a  call    WPP_SF_d
0x14002055f  xor     eax, eax
0x140020561  mov     rbx, [rsp+28h+arg_0]
0x140020566  mov     rdi, [rsp+28h+arg_8]
0x14002056b  add     rsp, 20h
0x14002056f  pop     r14
0x140020571  retn
```
