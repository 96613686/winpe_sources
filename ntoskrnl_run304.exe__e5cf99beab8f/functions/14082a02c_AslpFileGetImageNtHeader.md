# AslpFileGetImageNtHeader

- ea: `0x14082a02c`
- end: `0x14082a164`
- name: `AslpFileGetImageNtHeader`
- size: `312`
- prototype: ``
- caller_count: `9`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140826950`
- `0x140829474`
- `0x1408297ac`
- `0x14082a16c`
- `0x14082a33c`
- `0x14082ad10`
- `0x14082b468`
- `0x14082bb3c`
- `0x14082bfe8`

## callees

- `0x1404058e0`
- `0x140519f7c`
- `0x1406d9d70`
- `0x1406f4880`
- `0x14082a02c`
- `0x14097d158`

## string_xrefs

- `0x14082a082`: `AslpFileGetImageNtHeader`
- `0x14082a100`: `AslpFileGetImageNtHeader`
- `0x14082a12a`: `AslpFileGetImageNtHeader`

## pseudocode

```c
__int64 __fastcall AslpFileGetImageNtHeader(_QWORD *a1, __int64 a2)
{
  unsigned int v4; // ebx
  int *v5; // rdi
  __int64 v6; // rcx
  _BYTE v8[64]; // [rsp+40h] [rbp-58h] BYREF

  memset_0(v8, 0, sizeof(v8));
  if ( *(_DWORD *)(a2 + 64) == 6 )
  {
    v5 = *(int **)(a2 + 32);
    if ( (unsigned __int8)MmIsUserAddress(v5) )
    {
      RtlCopyFromUser(v8, v5, 0x40u);
      v5 = (int *)v8;
    }
    v6 = v5[15];
    if ( *(_QWORD *)(a2 + 24) < (unsigned __int64)(v6 + 264) || *(_QWORD *)(a2 + 40) < (unsigned __int64)(v6 + 264) )
    {
      v4 = -1073741701;
      AslLogCallPrintf(
        1,
        (unsigned int)"AslpFileGetImageNtHeader",
        3777,
        (unsigned int)"File mapping invalid [%x]",
        -1073741701);
    }
    else
    {
      *a1 = *(_QWORD *)(a2 + 32) + v6;
      return 0;
    }
  }
  else
  {
    v4 = -1073741637;
    AslLogCallPrintf(
      1,
      (unsigned int)"AslpFileGetImageNtHeader",
      3758,
      (unsigned int)"File mapping not a PE [%x]",
      -1073741637);
  }
  return v4;
}

```

## disassembly

```asm
0x14082a02c  mov     [rsp+arg_10], rbx
0x14082a031  mov     [rsp+arg_18], rsi
0x14082a036  push    rdi
0x14082a037  sub     rsp, 90h
0x14082a03e  mov     rax, cs:__security_cookie
0x14082a045  xor     rax, rsp
0x14082a048  mov     [rsp+98h+var_18], rax
0x14082a050  mov     rbx, rdx
0x14082a053  mov     rsi, rcx
0x14082a056  xor     edx, edx; Val
0x14082a058  lea     r8d, [rdx+40h]; Size
0x14082a05c  lea     rcx, [rsp+98h+var_58]; void *
0x14082a061  call    memset_0
0x14082a066  cmp     dword ptr [rbx+40h], 6
0x14082a06a  jz      short loc_14082A098
0x14082a06c  mov     ebx, 0C00000BBh
0x14082a071  mov     [rsp+98h+var_78], ebx
0x14082a075  lea     r9, aFileMappingNot; "File mapping not a PE [%x]"
0x14082a07c  mov     r8d, 0EAEh
0x14082a082  lea     rdx, aAslpfilegetima_3; "AslpFileGetImageNtHeader"
0x14082a089  mov     ecx, 1
0x14082a08e  call    AslLogCallPrintf
0x14082a093  jmp     loc_14082A13C
0x14082a098  mov     rdi, [rbx+20h]
0x14082a09c  mov     rcx, rdi
0x14082a09f  call    MmIsUserAddress
0x14082a0a4  test    al, al
0x14082a0a6  jz      short loc_14082A0C0
0x14082a0a8  mov     r8d, 40h ; '@'; Size
0x14082a0ae  mov     rdx, rdi; Src
0x14082a0b1  lea     rcx, [rsp+98h+var_58]; void *
0x14082a0b6  call    RtlCopyFromUser
0x14082a0bb  lea     rdi, [rsp+98h+var_58]
0x14082a0c0  movsxd  rcx, dword ptr [rdi+3Ch]
0x14082a0c4  lea     rax, [rcx+108h]
0x14082a0cb  cmp     [rbx+18h], rax
0x14082a0cf  jb      short loc_14082A0E6
0x14082a0d1  cmp     [rbx+28h], rax
0x14082a0d5  jb      short loc_14082A0E6
0x14082a0d7  add     rcx, [rbx+20h]
0x14082a0db  mov     [rsi], rcx
0x14082a0de  xor     ebx, ebx
0x14082a0e0  mov     [rsp+98h+var_68], ebx
0x14082a0e4  jmp     short loc_14082A111
0x14082a0e6  mov     ebx, 0C000007Bh
0x14082a0eb  mov     [rsp+98h+var_68], ebx
0x14082a0ef  mov     [rsp+98h+var_78], ebx
0x14082a0f3  lea     r9, aFileMappingInv; "File mapping invalid [%x]"
0x14082a0fa  mov     r8d, 0EC1h
0x14082a100  lea     rdx, aAslpfilegetima_3; "AslpFileGetImageNtHeader"
0x14082a107  mov     ecx, 1
0x14082a10c  call    AslLogCallPrintf
0x14082a111  jmp     short loc_14082A13C
0x14082a113  mov     ebx, eax
0x14082a115  mov     [rsp+98h+var_68], eax
0x14082a119  mov     [rsp+98h+var_78], eax
0x14082a11d  lea     r9, aExceptionEncou_0; "Exception encountered [%x]"
0x14082a124  mov     r8d, 0ECAh
0x14082a12a  lea     rdx, aAslpfilegetima_3; "AslpFileGetImageNtHeader"
0x14082a131  mov     ecx, 1
0x14082a136  call    AslLogCallPrintf
0x14082a13b  nop
0x14082a13c  mov     eax, ebx
0x14082a13e  mov     rcx, [rsp+98h+var_18]
0x14082a146  xor     rcx, rsp; StackCookie
0x14082a149  call    __security_check_cookie
0x14082a14e  lea     r11, [rsp+98h+var_8]
0x14082a156  mov     rbx, [r11+20h]
0x14082a15a  mov     rsi, [r11+28h]
0x14082a15e  mov     rsp, r11
0x14082a161  pop     rdi
0x14082a162  retn
0x140b4a7ed  push    rbp
0x140b4a7ef  sub     rsp, 30h
0x140b4a7f3  mov     rbp, rdx
0x140b4a7f6  mov     eax, 1
0x140b4a7fb  add     rsp, 30h
0x140b4a7ff  pop     rbp
0x140b4a800  retn
```
