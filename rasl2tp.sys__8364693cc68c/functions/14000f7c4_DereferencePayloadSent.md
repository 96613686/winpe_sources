# DereferencePayloadSent

- ea: `0x14000f7c4`
- end: `0x14000f890`
- name: `DereferencePayloadSent`
- size: `204`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000f2ec`
- `0x1400152b0`
- `0x140017af0`
- `0x140017b90`

## callees

- `0x140003050`
- `0x140003080`
- `0x14000f7c4`
- `0x14001c050`

## pseudocode

```c
__int64 __fastcall DereferencePayloadSent(__int64 a1)
{
  unsigned int v2; // ebx

  v2 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 32));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x1Eu,
      (__int64)WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids,
      v2);
  }
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x1Fu,
        (__int64)WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids);
    }
  }
  else
  {
    ScheduleTunnelWork(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 64), (__int64)CompletePayloadSent, a1, 0, 0, 0, 0, 0);
  }
  return v2;
}

```

## disassembly

```asm
0x14000f7c4  mov     [rsp+arg_0], rbx
0x14000f7c9  mov     [rsp+arg_8], rsi
0x14000f7ce  push    rdi
0x14000f7cf  sub     rsp, 50h
0x14000f7d3  mov     rdi, rcx
0x14000f7d6  or      ebx, 0FFFFFFFFh
0x14000f7d9  lock xadd [rcx+20h], ebx
0x14000f7de  dec     ebx
0x14000f7e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f7e7  lea     rsi, WPP_GLOBAL_Control
0x14000f7ee  cmp     rcx, rsi
0x14000f7f1  jz      short loc_14000F818
0x14000f7f3  mov     eax, [rcx+2Ch]
0x14000f7f6  test    al, 10h
0x14000f7f8  jz      short loc_14000F818
0x14000f7fa  cmp     byte ptr [rcx+29h], 4
0x14000f7fe  jb      short loc_14000F818
0x14000f800  mov     rcx, [rcx+18h]
0x14000f804  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x14000f80b  mov     edx, 1Eh
0x14000f810  mov     r9d, ebx
0x14000f813  call    WPP_SF_d
0x14000f818  xor     eax, eax
0x14000f81a  test    ebx, ebx
0x14000f81c  jnz     short loc_14000F84E
0x14000f81e  mov     rdx, [rdi+40h]
0x14000f822  lea     r8, CompletePayloadSent
0x14000f829  mov     rcx, [rdi+38h]
0x14000f82d  mov     r9, rdi
0x14000f830  mov     [rsp+58h+var_18], al
0x14000f834  mov     [rsp+58h+var_20], al
0x14000f838  mov     [rsp+58h+var_28], rax
0x14000f83d  mov     [rsp+58h+var_30], rax
0x14000f842  mov     [rsp+58h+var_38], rax
0x14000f847  call    ScheduleTunnelWork
0x14000f84c  jmp     short loc_14000F87D
0x14000f84e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f855  cmp     rcx, rsi
0x14000f858  jz      short loc_14000F87D
0x14000f85a  mov     edx, [rcx+2Ch]
0x14000f85d  test    dl, 10h
0x14000f860  jz      short loc_14000F87D
0x14000f862  cmp     byte ptr [rcx+29h], 4
0x14000f866  jb      short loc_14000F87D
0x14000f868  mov     rcx, [rcx+18h]
0x14000f86c  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x14000f873  mov     edx, 1Fh
0x14000f878  call    WPP_SF_
0x14000f87d  mov     rsi, [rsp+58h+arg_8]
0x14000f882  mov     eax, ebx
0x14000f884  mov     rbx, [rsp+58h+arg_0]
0x14000f889  add     rsp, 50h
0x14000f88d  pop     rdi
0x14000f88e  retn
```
