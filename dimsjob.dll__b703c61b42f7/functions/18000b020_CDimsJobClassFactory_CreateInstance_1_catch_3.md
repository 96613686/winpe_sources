# _CDimsJobClassFactory::CreateInstance_::_1_::catch$3

- ea: `0x18000b020`
- end: `0x18000b080`
- name: `_CDimsJobClassFactory::CreateInstance_::_1_::catch$3`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a360`
- `0x18000b020`

## pseudocode

```c
__int64 __fastcall CDimsJobClassFactory::CreateInstance_::_1_::catch_3(__int64 a1, __int64 a2)
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
      22,
      WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids,
      (unsigned int)*v3);
  }
  *(_DWORD *)(a2 + 72) = *v3;
  return 0;
}

```

## disassembly

```asm
0x18000b020  mov     [rsp+arg_8], rdx
0x18000b025  push    rbx
0x18000b026  push    rbp
0x18000b027  sub     rsp, 28h
0x18000b02b  mov     rbp, rdx
0x18000b02e  lea     rax, WPP_GLOBAL_Control
0x18000b035  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b03c  cmp     rcx, rax
0x18000b03f  jz      short loc_18000B065
0x18000b041  test    byte ptr [rcx+1Ch], 2
0x18000b045  jz      short loc_18000B065
0x18000b047  mov     edx, 16h
0x18000b04c  mov     rbx, [rbp+20h]
0x18000b050  mov     r9d, [rbx]
0x18000b053  lea     r8, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids
0x18000b05a  mov     rcx, [rcx+10h]
0x18000b05e  call    WPP_SF_D
0x18000b063  jmp     short loc_18000B069
0x18000b065  mov     rbx, [rbp+20h]
0x18000b069  mov     eax, [rbx]
0x18000b06b  mov     [rbp+48h], eax
0x18000b06e  mov     rax, 0
0x18000b078  add     rsp, 28h
0x18000b07c  pop     rbp
0x18000b07d  pop     rbx
0x18000b07e  retn
```
