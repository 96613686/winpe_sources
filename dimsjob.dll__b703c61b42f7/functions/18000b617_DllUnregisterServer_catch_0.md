# DllUnregisterServer$catch$0

- ea: `0x18000b617`
- end: `0x18000b677`
- name: `DllUnregisterServer$catch$0`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a360`
- `0x18000b617`

## pseudocode

```c
__int64 __fastcall DllUnregisterServer_catch_0(__int64 a1, __int64 a2)
{
  _DWORD *v3; // rbx

  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
  {
    v3 = *(_DWORD **)(a2 + 32);
  }
  else
  {
    v3 = *(_DWORD **)(a2 + 32);
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids,
      (unsigned int)*v3);
  }
  *(_DWORD *)(a2 + 64) = *v3;
  return 0;
}

```

## disassembly

```asm
0x18000b617  mov     [rsp+arg_8], rdx
0x18000b61c  push    rbx
0x18000b61d  push    rbp
0x18000b61e  sub     rsp, 28h
0x18000b622  mov     rbp, rdx
0x18000b625  lea     rax, WPP_GLOBAL_Control
0x18000b62c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b633  cmp     rcx, rax
0x18000b636  jz      short loc_18000B65C
0x18000b638  test    byte ptr [rcx+1Ch], 2
0x18000b63c  jz      short loc_18000B65C
0x18000b63e  mov     edx, 19h
0x18000b643  mov     rbx, [rbp+20h]
0x18000b647  mov     r9d, [rbx]
0x18000b64a  lea     r8, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids
0x18000b651  mov     rcx, [rcx+10h]
0x18000b655  call    WPP_SF_D
0x18000b65a  jmp     short loc_18000B660
0x18000b65c  mov     rbx, [rbp+20h]
0x18000b660  mov     eax, [rbx]
0x18000b662  mov     [rbp+40h], eax
0x18000b665  mov     rax, 0
0x18000b66f  add     rsp, 28h
0x18000b673  pop     rbp
0x18000b674  pop     rbx
0x18000b675  retn
```
