# NatMappingDetachDirector

- ea: `0x140001e78`
- end: `0x140001f77`
- name: `NatMappingDetachDirector`
- size: `255`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140001030`
- `0x140001710`
- `0x14000d66c`
- `0x14000d8b0`

## callees

- `0x140001e78`
- `0x14000218c`
- `0x14002c710`

## pseudocode

```c
__int64 __fastcall NatMappingDetachDirector(__int64 a1, __int64 a2, _QWORD *a3, unsigned int a4)
{
  __int64 result; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x2Bu,
      (__int64)WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
  }
  result = *(_QWORD *)(a1 + 80);
  if ( a3 )
  {
    if ( result )
      ((void (__fastcall *)(_QWORD *, _QWORD, _QWORD, _QWORD))result)(a3, *(_QWORD *)(a1 + 56), a3[27], a4);
    result = (__int64)(a3 + 28);
    v9 = a3[28];
    if ( *(_QWORD **)(v9 + 8) != a3 + 28 || (v10 = (_QWORD *)a3[29], *v10 != result) )
      __fastfail(3u);
    *v10 = v9;
    *(_QWORD *)(v9 + 8) = v10;
    a3[26] = 0;
    a3[27] = 0;
  }
  else if ( result )
  {
    result = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD))result)(0, *(_QWORD *)(a1 + 56), a2, a4);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      return WPP_SF_(
               (__int64)WPP_GLOBAL_Control->AttachedDevice,
               0x2Cu,
               (__int64)WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140001e78  push    rbx
0x140001e7a  push    rbp
0x140001e7b  push    rsi
0x140001e7c  push    rdi
0x140001e7d  push    r14
0x140001e7f  sub     rsp, 30h
0x140001e83  mov     esi, r9d
0x140001e86  mov     rbx, r8
0x140001e89  mov     rbp, rdx
0x140001e8c  mov     rdi, rcx
0x140001e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e96  lea     r14, WPP_GLOBAL_Control
0x140001e9d  cmp     rcx, r14
0x140001ea0  jz      short loc_140001EC4
0x140001ea2  mov     eax, [rcx+2Ch]
0x140001ea5  test    al, 1
0x140001ea7  jz      short loc_140001EC4
0x140001ea9  cmp     byte ptr [rcx+29h], 6
0x140001ead  jb      short loc_140001EC4
0x140001eaf  mov     rcx, [rcx+18h]
0x140001eb3  lea     r8, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids
0x140001eba  mov     edx, 2Bh ; '+'
0x140001ebf  call    WPP_SF_
0x140001ec4  mov     rax, [rdi+50h]
0x140001ec8  test    rbx, rbx
0x140001ecb  jnz     short loc_140001EE5
0x140001ecd  test    rax, rax
0x140001ed0  jz      short loc_140001F36
0x140001ed2  mov     rdx, [rdi+38h]
0x140001ed6  mov     r9d, esi
0x140001ed9  mov     r8, rbp
0x140001edc  xor     ecx, ecx
0x140001ede  call    _guard_dispatch_icall
0x140001ee3  jmp     short loc_140001F36
0x140001ee5  test    rax, rax
0x140001ee8  jz      short loc_140001F00
0x140001eea  mov     r8, [rbx+0D8h]
0x140001ef1  mov     r9d, esi
0x140001ef4  mov     rdx, [rdi+38h]
0x140001ef8  mov     rcx, rbx
0x140001efb  call    _guard_dispatch_icall
0x140001f00  lea     rax, [rbx+0E0h]
0x140001f07  mov     rcx, [rax]
0x140001f0a  cmp     [rcx+8], rax
0x140001f0e  jnz     short loc_140001F70
0x140001f10  mov     rdx, [rax+8]
0x140001f14  cmp     [rdx], rax
0x140001f17  jnz     short loc_140001F70
0x140001f19  mov     [rdx], rcx
0x140001f1c  mov     [rcx+8], rdx
0x140001f20  mov     qword ptr [rbx+0D0h], 0
0x140001f2b  mov     qword ptr [rbx+0D8h], 0
0x140001f36  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f3d  cmp     rcx, r14
0x140001f40  jz      short loc_140001F64
0x140001f42  mov     eax, [rcx+2Ch]
0x140001f45  test    al, 1
0x140001f47  jz      short loc_140001F64
0x140001f49  cmp     byte ptr [rcx+29h], 6
0x140001f4d  jb      short loc_140001F64
0x140001f4f  mov     rcx, [rcx+18h]
0x140001f53  lea     r8, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids
0x140001f5a  mov     edx, 2Ch ; ','
0x140001f5f  call    WPP_SF_
0x140001f64  add     rsp, 30h
0x140001f68  pop     r14
0x140001f6a  pop     rdi
0x140001f6b  pop     rsi
0x140001f6c  pop     rbp
0x140001f6d  pop     rbx
0x140001f6e  retn
0x140001f70  mov     ecx, 3
0x140001f75  int     29h; Win8: RtlFailFast(ecx)
```
