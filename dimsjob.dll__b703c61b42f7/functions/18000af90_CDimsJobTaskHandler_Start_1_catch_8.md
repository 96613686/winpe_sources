# _CDimsJobTaskHandler::Start_::_1_::catch$8

- ea: `0x18000af90`
- end: `0x18000aff0`
- name: `_CDimsJobTaskHandler::Start_::_1_::catch$8`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000a360`
- `0x18000af90`

## pseudocode

```c
__int64 __fastcall CDimsJobTaskHandler::Start_::_1_::catch_8(__int64 a1, __int64 a2)
{
  _DWORD *v3; // rbx

  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
  {
    v3 = *(_DWORD **)(a2 + 64);
  }
  else
  {
    v3 = *(_DWORD **)(a2 + 64);
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids,
      (unsigned int)*v3);
  }
  *(_DWORD *)(a2 + 48) = *v3;
  return 0;
}

```

## disassembly

```asm
0x18000af90  mov     [rsp+arg_8], rdx
0x18000af95  push    rbx
0x18000af96  push    rbp
0x18000af97  sub     rsp, 38h
0x18000af9b  mov     rbp, rdx
0x18000af9e  lea     rax, WPP_GLOBAL_Control
0x18000afa5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afac  cmp     rcx, rax
0x18000afaf  jz      short loc_18000AFD5
0x18000afb1  test    byte ptr [rcx+1Ch], 2
0x18000afb5  jz      short loc_18000AFD5
0x18000afb7  mov     edx, 12h
0x18000afbc  mov     rbx, [rbp+40h]
0x18000afc0  mov     r9d, [rbx]
0x18000afc3  lea     r8, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids
0x18000afca  mov     rcx, [rcx+10h]
0x18000afce  call    WPP_SF_D
0x18000afd3  jmp     short loc_18000AFD9
0x18000afd5  mov     rbx, [rbp+40h]
0x18000afd9  mov     eax, [rbx]
0x18000afdb  mov     [rbp+30h], eax
0x18000afde  mov     rax, 0
0x18000afe8  add     rsp, 38h
0x18000afec  pop     rbp
0x18000afed  pop     rbx
0x18000afee  retn
```
