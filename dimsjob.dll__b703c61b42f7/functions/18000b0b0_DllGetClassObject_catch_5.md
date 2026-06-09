# DllGetClassObject$catch$5

- ea: `0x18000b0b0`
- end: `0x18000b110`
- name: `DllGetClassObject$catch$5`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a360`
- `0x18000b0b0`

## pseudocode

```c
__int64 __fastcall DllGetClassObject_catch_5(__int64 a1, __int64 a2)
{
  _DWORD *v3; // rbx

  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
  {
    v3 = *(_DWORD **)(a2 + 40);
  }
  else
  {
    v3 = *(_DWORD **)(a2 + 40);
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids,
      (unsigned int)*v3);
  }
  *(_DWORD *)(a2 + 80) = *v3;
  return 0;
}

```

## disassembly

```asm
0x18000b0b0  mov     [rsp+arg_8], rdx
0x18000b0b5  push    rbx
0x18000b0b6  push    rbp
0x18000b0b7  sub     rsp, 28h
0x18000b0bb  mov     rbp, rdx
0x18000b0be  lea     rax, WPP_GLOBAL_Control
0x18000b0c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0cc  cmp     rcx, rax
0x18000b0cf  jz      short loc_18000B0F5
0x18000b0d1  test    byte ptr [rcx+1Ch], 2
0x18000b0d5  jz      short loc_18000B0F5
0x18000b0d7  mov     edx, 17h
0x18000b0dc  mov     rbx, [rbp+28h]
0x18000b0e0  mov     r9d, [rbx]
0x18000b0e3  lea     r8, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids
0x18000b0ea  mov     rcx, [rcx+10h]
0x18000b0ee  call    WPP_SF_D
0x18000b0f3  jmp     short loc_18000B0F9
0x18000b0f5  mov     rbx, [rbp+28h]
0x18000b0f9  mov     eax, [rbx]
0x18000b0fb  mov     [rbp+50h], eax
0x18000b0fe  mov     rax, 0
0x18000b108  add     rsp, 28h
0x18000b10c  pop     rbp
0x18000b10d  pop     rbx
0x18000b10e  retn
```
