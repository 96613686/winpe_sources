# LuafvLogVirtualRename

- ea: `0x1400162cc`
- end: `0x1400163a7`
- name: `LuafvLogVirtualRename`
- size: `219`
- prototype: `__int64 __fastcall(__int64, __int64 *, char, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400164f0`
- `0x140018f20`

## callees

- `0x140005bb0`
- `0x1400162cc`
- `0x14001892c`

## pseudocode

```c
__int64 __fastcall LuafvLogVirtualRename(__int64 a1, __int64 *a2, char a3, char a4)
{
  int v4; // r11d
  __int64 v6; // rdx
  int v7; // ecx
  __int64 v8; // rdx
  __int16 v10; // [rsp+40h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+50h] [rbp-A8h] BYREF
  __int16 *v12; // [rsp+C0h] [rbp-38h]
  __int64 v13; // [rsp+C8h] [rbp-30h]
  __int64 v14; // [rsp+D0h] [rbp-28h]
  int v15; // [rsp+D8h] [rbp-20h]
  int v16; // [rsp+DCh] [rbp-1Ch]

  v4 = a1;
  v10 = 0;
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 56LL);
  v10 = *(_WORD *)(v6 + 16) >> 1;
  v13 = 2;
  v12 = &v10;
  v15 = *(_DWORD *)(v6 + 16);
  v14 = v6 + 20;
  v16 = 0;
  v7 = (a3 != 0 ? 0x100 : 0) | 0x200;
  if ( !a4 )
    v7 = a3 != 0 ? 0x100 : 0;
  if ( a2 )
    v8 = *a2;
  else
    LODWORD(v8) = 0;
  return LuafvLogFileEvent(v4, v8, (int)a2, v7, &LuafvVirtualRenameEvent, &v11, 9u);
}

```

## disassembly

```asm
0x1400162cc  sub     rsp, 0F8h
0x1400162d3  mov     rax, cs:__security_cookie
0x1400162da  xor     rax, rsp
0x1400162dd  mov     [rsp+0F8h+var_18], rax
0x1400162e5  xor     eax, eax
0x1400162e7  mov     r11, rcx
0x1400162ea  mov     [rsp+0F8h+var_B8], ax
0x1400162ef  mov     r10, rdx
0x1400162f2  mov     rax, [rcx+10h]
0x1400162f6  mov     rdx, [rax+38h]
0x1400162fa  movzx   eax, word ptr [rdx+10h]
0x1400162fe  shr     ax, 1
0x140016301  mov     [rsp+0F8h+var_B8], ax
0x140016306  neg     r8b
0x140016309  lea     rax, [rsp+0F8h+var_B8]
0x14001630e  mov     [rsp+0F8h+var_30], 2
0x14001631a  mov     [rsp+0F8h+var_38], rax
0x140016322  lea     rax, [rdx+14h]
0x140016326  mov     ecx, [rdx+10h]
0x140016329  mov     [rsp+0F8h+var_20], ecx
0x140016330  mov     [rsp+0F8h+var_28], rax
0x140016338  sbb     eax, eax
0x14001633a  and     eax, 100h
0x14001633f  mov     [rsp+0F8h+var_1C], 0
0x14001634a  mov     ecx, eax
0x14001634c  bts     ecx, 9
0x140016350  test    r9b, r9b
0x140016353  cmovz   ecx, eax
0x140016356  test    r10, r10
0x140016359  jz      short loc_140016360
0x14001635b  mov     rdx, [r10]
0x14001635e  jmp     short loc_140016362
0x140016360  xor     edx, edx; int
0x140016362  lea     rax, [rsp+0F8h+var_A8]
0x140016367  mov     [rsp+0F8h+UserDataCount], 9; UserDataCount
0x14001636f  mov     [rsp+0F8h+var_D0], rax; PEVENT_DATA_DESCRIPTOR
0x140016374  mov     r9d, ecx; int
0x140016377  lea     rax, LuafvVirtualRenameEvent
0x14001637e  mov     r8, r10; int
0x140016381  mov     rcx, r11; int
0x140016384  mov     [rsp+0F8h+EventDescriptor], rax; EventDescriptor
0x140016389  call    LuafvLogFileEvent
0x14001638e  mov     rcx, [rsp+0F8h+var_18]
0x140016396  xor     rcx, rsp; StackCookie
0x140016399  call    __security_check_cookie
0x14001639e  add     rsp, 0F8h
0x1400163a5  retn
```
