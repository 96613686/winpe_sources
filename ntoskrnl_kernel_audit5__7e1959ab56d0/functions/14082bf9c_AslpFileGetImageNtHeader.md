# AslpFileGetImageNtHeader

- ea: `0x14082bf9c`
- end: `0x14082c0d4`
- name: `AslpFileGetImageNtHeader`
- size: `312`
- prototype: ``
- caller_count: `9`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1408288c0`
- `0x14082b3e4`
- `0x14082b71c`
- `0x14082c0dc`
- `0x14082c2ac`
- `0x14082cc80`
- `0x14082d3d8`
- `0x14082daac`
- `0x14082df58`

## callees

- `0x14041a320`
- `0x14052039c`
- `0x1406dc8c0`
- `0x1406f7380`
- `0x14082bf9c`
- `0x1408c2f88`

## string_xrefs

- `0x14082bff2`: `AslpFileGetImageNtHeader`
- `0x14082c070`: `AslpFileGetImageNtHeader`
- `0x14082c09a`: `AslpFileGetImageNtHeader`

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
0x14082bf9c  mov     [rsp+arg_10], rbx
0x14082bfa1  mov     [rsp+arg_18], rsi
0x14082bfa6  push    rdi
0x14082bfa7  sub     rsp, 90h
0x14082bfae  mov     rax, cs:__security_cookie
0x14082bfb5  xor     rax, rsp
0x14082bfb8  mov     [rsp+98h+var_18], rax
0x14082bfc0  mov     rbx, rdx
0x14082bfc3  mov     rsi, rcx
0x14082bfc6  xor     edx, edx; Val
0x14082bfc8  lea     r8d, [rdx+40h]; Size
0x14082bfcc  lea     rcx, [rsp+98h+var_58]; void *
0x14082bfd1  call    memset_0
0x14082bfd6  cmp     dword ptr [rbx+40h], 6
0x14082bfda  jz      short loc_14082C008
0x14082bfdc  mov     ebx, 0C00000BBh
0x14082bfe1  mov     [rsp+98h+var_78], ebx
0x14082bfe5  lea     r9, aFileMappingNot; "File mapping not a PE [%x]"
0x14082bfec  mov     r8d, 0EAEh
0x14082bff2  lea     rdx, aAslpfilegetima_3; "AslpFileGetImageNtHeader"
0x14082bff9  mov     ecx, 1
0x14082bffe  call    AslLogCallPrintf
0x14082c003  jmp     loc_14082C0AC
0x14082c008  mov     rdi, [rbx+20h]
0x14082c00c  mov     rcx, rdi
0x14082c00f  call    MmIsUserAddress
0x14082c014  test    al, al
0x14082c016  jz      short loc_14082C030
0x14082c018  mov     r8d, 40h ; '@'; Size
0x14082c01e  mov     rdx, rdi; Src
0x14082c021  lea     rcx, [rsp+98h+var_58]; void *
0x14082c026  call    RtlCopyFromUser
0x14082c02b  lea     rdi, [rsp+98h+var_58]
0x14082c030  movsxd  rcx, dword ptr [rdi+3Ch]
0x14082c034  lea     rax, [rcx+108h]
0x14082c03b  cmp     [rbx+18h], rax
0x14082c03f  jb      short loc_14082C056
0x14082c041  cmp     [rbx+28h], rax
0x14082c045  jb      short loc_14082C056
0x14082c047  add     rcx, [rbx+20h]
0x14082c04b  mov     [rsi], rcx
0x14082c04e  xor     ebx, ebx
0x14082c050  mov     [rsp+98h+var_68], ebx
0x14082c054  jmp     short loc_14082C081
0x14082c056  mov     ebx, 0C000007Bh
0x14082c05b  mov     [rsp+98h+var_68], ebx
0x14082c05f  mov     [rsp+98h+var_78], ebx
0x14082c063  lea     r9, aFileMappingInv; "File mapping invalid [%x]"
0x14082c06a  mov     r8d, 0EC1h
0x14082c070  lea     rdx, aAslpfilegetima_3; "AslpFileGetImageNtHeader"
0x14082c077  mov     ecx, 1
0x14082c07c  call    AslLogCallPrintf
0x14082c081  jmp     short loc_14082C0AC
0x14082c083  mov     ebx, eax
0x14082c085  mov     [rsp+98h+var_68], eax
0x14082c089  mov     [rsp+98h+var_78], eax
0x14082c08d  lea     r9, aExceptionEncou_0; "Exception encountered [%x]"
0x14082c094  mov     r8d, 0ECAh
0x14082c09a  lea     rdx, aAslpfilegetima_3; "AslpFileGetImageNtHeader"
0x14082c0a1  mov     ecx, 1
0x14082c0a6  call    AslLogCallPrintf
0x14082c0ab  nop
0x14082c0ac  mov     eax, ebx
0x14082c0ae  mov     rcx, [rsp+98h+var_18]
0x14082c0b6  xor     rcx, rsp; StackCookie
0x14082c0b9  call    __security_check_cookie
0x14082c0be  lea     r11, [rsp+98h+var_8]
0x14082c0c6  mov     rbx, [r11+20h]
0x14082c0ca  mov     rsi, [r11+28h]
0x14082c0ce  mov     rsp, r11
0x14082c0d1  pop     rdi
0x14082c0d2  retn
0x140b4bf39  push    rbp
0x140b4bf3b  sub     rsp, 30h
0x140b4bf3f  mov     rbp, rdx
0x140b4bf42  mov     eax, 1
0x140b4bf47  add     rsp, 30h
0x140b4bf4b  pop     rbp
0x140b4bf4c  retn
```
