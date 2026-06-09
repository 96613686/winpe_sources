# FveUi_CreateInstance

- ea: `0x18000355c`
- end: `0x180003621`
- name: `FveUi_CreateInstance`
- size: `197`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180003080`

## callees

- `0x180002f9c`
- `0x18000303c`
- `0x18000355c`
- `0x1800037a0`

## pseudocode

```c
__int64 __fastcall FveUi_CreateInstance(_QWORD *a1, __int64 a2)
{
  int UniqueNo; // ebx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  v5 = 0;
  if ( a1 )
  {
    *a1 = 0;
    UniqueNo = MakeUniqueNoThrow<CFveUiDispatch>(&v5);
    if ( !UniqueNo )
      goto LABEL_10;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_2cd505cd70833f31b3a2527f23c3e5f0_Traceguids,
        (unsigned int)UniqueNo);
    if ( UniqueNo >= 0 )
    {
LABEL_10:
      *a1 = v5;
      v5 = 0;
    }
  }
  else
  {
    UniqueNo = -2147467261;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2cd505cd70833f31b3a2527f23c3e5f0_Traceguids, 2147500035LL);
  }
  std::unique_ptr<CFveUiDispatch>::~unique_ptr<CFveUiDispatch>(&v5, a2);
  return (unsigned int)UniqueNo;
}

```

## disassembly

```asm
0x18000355c  mov     [rsp+arg_8], rbx
0x180003561  push    rdi
0x180003562  sub     rsp, 20h
0x180003566  mov     [rsp+28h+arg_0], 0
0x18000356f  mov     rdi, rcx
0x180003572  test    rcx, rcx
0x180003575  jnz     short loc_1800035AD
0x180003577  mov     ebx, 80004003h
0x18000357c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003583  lea     rax, WPP_GLOBAL_Control
0x18000358a  cmp     rcx, rax
0x18000358d  jz      short loc_18000360A
0x18000358f  test    byte ptr [rcx+1Ch], 40h
0x180003593  jz      short loc_18000360A
0x180003595  mov     rcx, [rcx+10h]
0x180003599  lea     edx, [rdi+0Ah]
0x18000359c  mov     r9d, ebx
0x18000359f  lea     r8, WPP_2cd505cd70833f31b3a2527f23c3e5f0_Traceguids
0x1800035a6  call    WPP_SF_d
0x1800035ab  jmp     short loc_18000360A
0x1800035ad  mov     qword ptr [rcx], 0
0x1800035b4  lea     rcx, [rsp+28h+arg_0]
0x1800035b9  call    ??$MakeUniqueNoThrow@VCFveUiDispatch@@@@YAJAEAV?$unique_ptr@VCFveUiDispatch@@U?$default_delete@VCFveUiDispatch@@@std@@@std@@@Z; MakeUniqueNoThrow<CFveUiDispatch>(std::unique_ptr<CFveUiDispatch> &)
0x1800035be  mov     ebx, eax
0x1800035c0  test    eax, eax
0x1800035c2  jz      short loc_1800035F9
0x1800035c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035cb  lea     rax, WPP_GLOBAL_Control
0x1800035d2  cmp     rcx, rax
0x1800035d5  jz      short loc_1800035F5
0x1800035d7  test    byte ptr [rcx+1Ch], 40h
0x1800035db  jz      short loc_1800035F5
0x1800035dd  mov     rcx, [rcx+10h]
0x1800035e1  lea     r8, WPP_2cd505cd70833f31b3a2527f23c3e5f0_Traceguids
0x1800035e8  mov     edx, 0Bh
0x1800035ed  mov     r9d, ebx
0x1800035f0  call    WPP_SF_d
0x1800035f5  test    ebx, ebx
0x1800035f7  js      short loc_18000360A
0x1800035f9  mov     rax, [rsp+28h+arg_0]
0x1800035fe  mov     [rdi], rax
0x180003601  mov     [rsp+28h+arg_0], 0
0x18000360a  lea     rcx, [rsp+28h+arg_0]
0x18000360f  call    ??1?$unique_ptr@VCFveUiDispatch@@U?$default_delete@VCFveUiDispatch@@@std@@@std@@QEAA@XZ; std::unique_ptr<CFveUiDispatch>::~unique_ptr<CFveUiDispatch>(void)
0x180003614  mov     eax, ebx
0x180003616  mov     rbx, [rsp+28h+arg_8]
0x18000361b  add     rsp, 20h
0x18000361f  pop     rdi
0x180003620  retn
```
