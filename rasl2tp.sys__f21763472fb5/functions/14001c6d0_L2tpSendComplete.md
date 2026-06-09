# L2tpSendComplete

- ea: `0x14001c6d0`
- end: `0x14001c859`
- name: `L2tpSendComplete`
- size: `393`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003050`
- `0x140003080`
- `0x140004830`
- `0x1400171e0`
- `0x1400174b0`
- `0x140017af0`
- `0x140019810`
- `0x14001c6d0`

## pseudocode

```c
__int64 __fastcall L2tpSendComplete(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5, unsigned int a6)
{
  __int64 v10; // rbx
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      result = WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_58e8a5e2f2e139b3b973e872e086012f_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        result = WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_58e8a5e2f2e139b3b973e872e086012f_Traceguids, a4);
    }
  }
  v10 = a4 - 1;
  if ( (unsigned int)v10 > 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        return WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_58e8a5e2f2e139b3b973e872e086012f_Traceguids, a4);
    }
  }
  else
  {
    if ( a6
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_58e8a5e2f2e139b3b973e872e086012f_Traceguids, a6);
    }
    result = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))gL2tpSendCompleteHandlers[v10])(
               a1,
               a2,
               a3,
               a5);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_58e8a5e2f2e139b3b973e872e086012f_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001c6d0  push    rbx
0x14001c6d2  push    rbp
0x14001c6d3  push    rsi
0x14001c6d4  push    rdi
0x14001c6d5  push    r14
0x14001c6d7  push    r15
0x14001c6d9  sub     rsp, 38h
0x14001c6dd  mov     edi, r9d
0x14001c6e0  mov     rsi, r8
0x14001c6e3  mov     rbp, rdx
0x14001c6e6  mov     r14, rcx
0x14001c6e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c6f0  lea     r15, WPP_GLOBAL_Control
0x14001c6f7  cmp     rcx, r15
0x14001c6fa  jnz     short loc_14001C75F
0x14001c6fc  lea     ebx, [rdi-1]
0x14001c6ff  cmp     ebx, 3
0x14001c702  ja      loc_14001C7A0
0x14001c708  mov     r9d, [rsp+68h+arg_28]
0x14001c710  test    r9d, r9d
0x14001c713  jnz     loc_14001C7F6
0x14001c719  mov     r9, [rsp+68h+arg_20]
0x14001c721  lea     rcx, gL2tpSendCompleteHandlers
0x14001c728  mov     rax, ds:(gL2tpSendCompleteHandlers - 1400070D0h)[rcx+rbx*8]
0x14001c72c  mov     r8, rsi
0x14001c72f  mov     rcx, r14
0x14001c732  mov     rdx, rbp
0x14001c735  call    _guard_dispatch_icall
0x14001c73a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c741  cmp     rcx, r15
0x14001c744  jz      short loc_14001C751
0x14001c746  mov     eax, [rcx+2Ch]
0x14001c749  test    al, 40h
0x14001c74b  jnz     loc_14001C835
0x14001c751  add     rsp, 38h
0x14001c755  pop     r15
0x14001c757  pop     r14
0x14001c759  pop     rdi
0x14001c75a  pop     rsi
0x14001c75b  pop     rbp
0x14001c75c  pop     rbx
0x14001c75d  retn
0x14001c75f  mov     eax, [rcx+2Ch]
0x14001c762  test    al, 40h
0x14001c764  jnz     short loc_14001C7D6
0x14001c766  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c76d  cmp     rcx, r15
0x14001c770  jz      short loc_14001C6FC
0x14001c772  mov     eax, [rcx+2Ch]
0x14001c775  test    al, 40h
0x14001c777  jz      short loc_14001C6FC
0x14001c779  cmp     byte ptr [rcx+29h], 4
0x14001c77d  jb      loc_14001C6FC
0x14001c783  mov     rcx, [rcx+18h]
0x14001c787  lea     r8, WPP_58e8a5e2f2e139b3b973e872e086012f_Traceguids
0x14001c78e  mov     edx, 0Dh
0x14001c793  mov     r9d, edi
0x14001c796  call    WPP_SF_d
0x14001c79b  jmp     loc_14001C6FC
0x14001c7a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c7a7  cmp     rcx, r15
0x14001c7aa  jz      short loc_14001C751
0x14001c7ac  mov     eax, [rcx+2Ch]
0x14001c7af  test    al, 40h
0x14001c7b1  jz      short loc_14001C751
0x14001c7b3  cmp     byte ptr [rcx+29h], 4
0x14001c7b7  jb      short loc_14001C751
0x14001c7b9  mov     rcx, [rcx+18h]
0x14001c7bd  lea     r8, WPP_58e8a5e2f2e139b3b973e872e086012f_Traceguids
0x14001c7c4  mov     edx, 0Eh
0x14001c7c9  mov     r9d, edi
0x14001c7cc  call    WPP_SF_d
0x14001c7d1  jmp     loc_14001C751
0x14001c7d6  cmp     byte ptr [rcx+29h], 2
0x14001c7da  jb      short loc_14001C766
0x14001c7dc  mov     rcx, [rcx+18h]
0x14001c7e0  lea     r8, WPP_58e8a5e2f2e139b3b973e872e086012f_Traceguids
0x14001c7e7  mov     edx, 0Ch
0x14001c7ec  call    WPP_SF_
0x14001c7f1  jmp     loc_14001C766
0x14001c7f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c7fd  cmp     rcx, r15
0x14001c800  jz      loc_14001C719
0x14001c806  mov     eax, [rcx+2Ch]
0x14001c809  test    al, 40h
0x14001c80b  jz      loc_14001C719
0x14001c811  cmp     byte ptr [rcx+29h], 4
0x14001c815  jb      loc_14001C719
0x14001c81b  mov     rcx, [rcx+18h]
0x14001c81f  lea     r8, WPP_58e8a5e2f2e139b3b973e872e086012f_Traceguids
0x14001c826  mov     edx, 0Fh
0x14001c82b  call    WPP_SF_d
0x14001c830  jmp     loc_14001C719
0x14001c835  cmp     byte ptr [rcx+29h], 2
0x14001c839  jb      loc_14001C751
0x14001c83f  mov     rcx, [rcx+18h]
0x14001c843  lea     r8, WPP_58e8a5e2f2e139b3b973e872e086012f_Traceguids
0x14001c84a  mov     edx, 10h
0x14001c84f  call    WPP_SF_
0x14001c854  jmp     loc_14001C751
```
