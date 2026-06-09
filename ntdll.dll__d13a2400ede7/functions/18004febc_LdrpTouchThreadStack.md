# LdrpTouchThreadStack

- ea: `0x18004febc`
- end: `0x18004ff70`
- name: `LdrpTouchThreadStack`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004ff78`

## callees

- `0x18004febc`
- `0x18015b7c8`
- `0x18015ef40`

## string_xrefs

- `0x1801665eb`: `LdrpTouchThreadStack`

## pseudocode

```c
__int64 __fastcall LdrpTouchThreadStack(unsigned __int64 a1)
{
  struct _TEB *v2; // rdi
  __int64 result; // rax
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rdx
  _QWORD v6[8]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v7; // [rsp+88h] [rbp+10h] BYREF

  memset(v6, 0, 48);
  v7 = 0;
  v2 = NtCurrentTeb();
  result = ZwQueryVirtualMemory(-1, v2->NtTib.StackLimit, 0, v6, 48, &v7);
  if ( (int)result >= 0 )
  {
    v4 = (unsigned __int64)v2->NtTib.StackBase - 4096;
    if ( v4 > a1 )
    {
      v5 = v4 - a1;
      if ( v4 - a1 <= v6[1] + 12288LL )
        v5 = v6[1] + 12288LL;
    }
    else
    {
      v5 = v6[1] + 12288LL;
    }
    while ( v4 >= v5 )
      v4 -= 4096LL;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18004febc  mov     rax, rsp
0x18004febf  mov     [rax+8], rbx
0x18004fec3  push    rdi
0x18004fec4  sub     rsp, 70h
0x18004fec8  mov     rbx, rcx
0x18004fecb  xorps   xmm0, xmm0
0x18004fece  movups  xmmword ptr [rax-40h], xmm0
0x18004fed2  movups  xmmword ptr [rax-30h], xmm0
0x18004fed6  movups  xmmword ptr [rax-20h], xmm0
0x18004feda  mov     qword ptr [rax+10h], 0
0x18004fee2  mov     rdi, gs:30h
0x18004feeb  lea     rax, [rax+10h]
0x18004feef  mov     [rsp+78h+var_50], rax
0x18004fef4  mov     [rsp+78h+var_58], 30h ; '0'
0x18004fefd  lea     r9, [rsp+78h+var_40]
0x18004ff02  xor     r8d, r8d
0x18004ff05  mov     rdx, [rdi+10h]
0x18004ff09  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004ff0d  call    ZwQueryVirtualMemory
0x18004ff12  test    eax, eax
0x18004ff14  js      short loc_18004FF52
0x18004ff16  mov     rax, [rsp+78h+var_38]
0x18004ff1b  add     rax, 3000h
0x18004ff21  mov     rcx, [rdi+8]
0x18004ff25  mov     r8d, 1000h
0x18004ff2b  sub     rcx, r8
0x18004ff2e  cmp     rcx, rbx
0x18004ff31  ja      short loc_18004FF61
0x18004ff33  mov     rdx, rax
0x18004ff36  cmp     rcx, rdx
0x18004ff39  jb      short loc_18004FF47
0x18004ff3b  mov     eax, [rcx]
0x18004ff3d  sub     rcx, r8
0x18004ff40  mov     [rsp+78h+var_48], rcx
0x18004ff45  jmp     short loc_18004FF36
0x18004ff47  jmp     short loc_18004FF50
0x18004ff49  mov     eax, 0C0000017h
0x18004ff4e  jmp     short loc_18004FF52
0x18004ff50  xor     eax, eax
0x18004ff52  mov     rbx, [rsp+78h+arg_0]
0x18004ff5a  add     rsp, 70h
0x18004ff5e  pop     rdi
0x18004ff5f  retn
0x18004ff61  mov     rdx, rcx
0x18004ff64  sub     rdx, rbx
0x18004ff67  cmp     rdx, rax
0x18004ff6a  cmovbe  rdx, rax
0x18004ff6e  jmp     short loc_18004FF36
0x1801665e2  push    rbp
0x1801665e4  sub     rsp, 30h
0x1801665e8  mov     rbp, rdx
0x1801665eb  lea     rdx, aLdrptouchthrea; "LdrpTouchThreadStack"
0x1801665f2  call    LdrpGenericExceptionFilter
0x1801665f7  nop
0x1801665f8  add     rsp, 30h
0x1801665fc  pop     rbp
0x1801665fd  retn
```
