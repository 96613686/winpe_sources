# DllRegisterServer$catch$0

- ea: `0x18000b5b1`
- end: `0x18000b611`
- name: `DllRegisterServer$catch$0`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a360`
- `0x18000b5b1`

## pseudocode

```c
__int64 __fastcall DllRegisterServer_catch_0(__int64 a1, __int64 a2)
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
      24,
      WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids,
      (unsigned int)*v3);
  }
  *(_DWORD *)(a2 + 64) = *v3;
  return 0;
}

```

## disassembly

```asm
0x18000b5b1  mov     [rsp+arg_8], rdx
0x18000b5b6  push    rbx
0x18000b5b7  push    rbp
0x18000b5b8  sub     rsp, 28h
0x18000b5bc  mov     rbp, rdx
0x18000b5bf  lea     rax, WPP_GLOBAL_Control
0x18000b5c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5cd  cmp     rcx, rax
0x18000b5d0  jz      short loc_18000B5F6
0x18000b5d2  test    byte ptr [rcx+1Ch], 2
0x18000b5d6  jz      short loc_18000B5F6
0x18000b5d8  mov     edx, 18h
0x18000b5dd  mov     rbx, [rbp+20h]
0x18000b5e1  mov     r9d, [rbx]
0x18000b5e4  lea     r8, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids
0x18000b5eb  mov     rcx, [rcx+10h]
0x18000b5ef  call    WPP_SF_D
0x18000b5f4  jmp     short loc_18000B5FA
0x18000b5f6  mov     rbx, [rbp+20h]
0x18000b5fa  mov     eax, [rbx]
0x18000b5fc  mov     [rbp+40h], eax
0x18000b5ff  mov     rax, 0
0x18000b609  add     rsp, 28h
0x18000b60d  pop     rbp
0x18000b60e  pop     rbx
0x18000b60f  retn
```
