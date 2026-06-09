# RasGetDeviceConfigInfo

- ea: `0x180018a80`
- end: `0x180018b9d`
- name: `RasGetDeviceConfigInfo`
- size: `285`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180011790`
- `0x180011b40`
- `0x180018a80`
- `0x180021000`
- `0x180021488`

## pseudocode

```c
__int64 __fastcall RasGetDeviceConfigInfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int v13; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 555, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( (unsigned int)ValidateConnectionHandle(a1) )
  {
    v13 = SubmitRequest(a1, 0x5Fu, a2, a4, a5, a3);
    v9 = v13;
    if ( !v13 )
    {
LABEL_16:
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_17;
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_17;
    v11 = 557;
    v12 = v13;
LABEL_15:
    WPP_SF_d(v10[2], v11, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v12);
    goto LABEL_16;
  }
  v9 = -2147024809;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = 556;
    v12 = 2147942487LL;
    goto LABEL_15;
  }
LABEL_17:
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 558, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180018a80  push    rbx
0x180018a82  push    rbp
0x180018a83  push    rsi
0x180018a84  push    rdi
0x180018a85  push    r15
0x180018a87  sub     rsp, 30h
0x180018a8b  mov     rdi, r9
0x180018a8e  mov     rsi, r8
0x180018a91  mov     rbp, rdx
0x180018a94  mov     rbx, rcx
0x180018a97  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a9e  lea     r15, WPP_GLOBAL_Control
0x180018aa5  cmp     rcx, r15
0x180018aa8  jz      short loc_180018ACE
0x180018aaa  test    byte ptr [rcx+1Ch], 40h
0x180018aae  jz      short loc_180018ACE
0x180018ab0  cmp     byte ptr [rcx+19h], 6
0x180018ab4  jb      short loc_180018ACE
0x180018ab6  mov     rcx, [rcx+10h]
0x180018aba  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180018ac1  mov     edx, 22Bh
0x180018ac6  mov     r9, rbx
0x180018ac9  call    WPP_SF_q
0x180018ace  mov     rcx, rbx
0x180018ad1  call    ValidateConnectionHandle
0x180018ad6  test    eax, eax
0x180018ad8  jnz     short loc_180018B05
0x180018ada  mov     ebx, 80070057h
0x180018adf  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ae6  cmp     rcx, r15
0x180018ae9  jz      loc_180018B90
0x180018aef  test    byte ptr [rcx+1Ch], 40h
0x180018af3  jz      short loc_180018B67
0x180018af5  cmp     byte ptr [rcx+19h], 2
0x180018af9  jb      short loc_180018B67
0x180018afb  mov     edx, 22Ch
0x180018b00  mov     r9d, ebx
0x180018b03  jmp     short loc_180018B50
0x180018b05  mov     rax, [rsp+58h+arg_20]
0x180018b0d  mov     edx, 5Fh ; '_'
0x180018b12  mov     [rsp+58h+var_30], rsi
0x180018b17  mov     r9, rdi
0x180018b1a  mov     r8, rbp
0x180018b1d  mov     [rsp+58h+var_38], rax
0x180018b22  mov     rcx, rbx
0x180018b25  call    SubmitRequest
0x180018b2a  mov     ebx, eax
0x180018b2c  test    eax, eax
0x180018b2e  jz      short loc_180018B60
0x180018b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b37  cmp     rcx, r15
0x180018b3a  jz      short loc_180018B90
0x180018b3c  test    byte ptr [rcx+1Ch], 40h
0x180018b40  jz      short loc_180018B67
0x180018b42  cmp     byte ptr [rcx+19h], 2
0x180018b46  jb      short loc_180018B67
0x180018b48  mov     edx, 22Dh
0x180018b4d  mov     r9d, eax
0x180018b50  mov     rcx, [rcx+10h]
0x180018b54  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180018b5b  call    WPP_SF_d
0x180018b60  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b67  cmp     rcx, r15
0x180018b6a  jz      short loc_180018B90
0x180018b6c  test    byte ptr [rcx+1Ch], 40h
0x180018b70  jz      short loc_180018B90
0x180018b72  cmp     byte ptr [rcx+19h], 6
0x180018b76  jb      short loc_180018B90
0x180018b78  mov     rcx, [rcx+10h]
0x180018b7c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180018b83  mov     edx, 22Eh
0x180018b88  mov     r9d, ebx
0x180018b8b  call    WPP_SF_d
0x180018b90  mov     eax, ebx
0x180018b92  add     rsp, 30h
0x180018b96  pop     r15
0x180018b98  pop     rdi
0x180018b99  pop     rsi
0x180018b9a  pop     rbp
0x180018b9b  pop     rbx
0x180018b9c  retn
```
