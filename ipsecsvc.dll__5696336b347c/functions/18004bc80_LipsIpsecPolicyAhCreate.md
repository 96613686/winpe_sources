# LipsIpsecPolicyAhCreate

- ea: `0x18004bc80`
- end: `0x18004bd40`
- name: `LipsIpsecPolicyAhCreate`
- size: `192`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18004c3b8`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x180045f1c`
- `0x18004bc80`

## string_xrefs

- `0x18004bd28`: `LipsIpsecPolicyAhCreate`

## pseudocode

```c
__int64 __fastcall LipsIpsecPolicyAhCreate(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  _DWORD *v6; // r9
  unsigned int v7; // ebx
  _DWORD *v9; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  *a3 = 0;
  v9 = IpsecAllocMem(0x10u);
  v6 = v9;
  if ( v9 )
  {
    v7 = 0;
    if ( *(_DWORD *)(a1 + 4) == 1 )
    {
      *v9 = 0;
      *((_BYTE *)v6 + 4) = 0;
    }
    else if ( *(_DWORD *)(a1 + 4) == 2 )
    {
      *v9 = 1;
      *((_BYTE *)v6 + 4) = 1;
    }
    *a2 = 1;
    *a3 = v6;
    v9 = 0;
  }
  else
  {
    v7 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids, 8);
  }
  LipsIkePolicyProposalDestroy((void **)&v9);
  if ( v7 )
    return LipsReportError(v7, "LipsIpsecPolicyAhCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004bc80  push    rbx
0x18004bc82  push    rsi
0x18004bc83  push    rdi
0x18004bc84  push    r14
0x18004bc86  sub     rsp, 28h
0x18004bc8a  mov     rdi, rcx
0x18004bc8d  mov     dword ptr [rdx], 0
0x18004bc93  mov     ecx, 10h
0x18004bc98  mov     qword ptr [r8], 0
0x18004bc9f  mov     rsi, r8
0x18004bca2  mov     r14, rdx
0x18004bca5  call    IpsecAllocMem
0x18004bcaa  mov     [rsp+48h+arg_8], rax
0x18004bcaf  mov     r9, rax
0x18004bcb2  test    rax, rax
0x18004bcb5  jnz     short loc_18004BCEB
0x18004bcb7  lea     ebx, [rax+8]
0x18004bcba  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bcc1  lea     rax, WPP_GLOBAL_Control
0x18004bcc8  cmp     rcx, rax
0x18004bccb  jz      short loc_18004BD16
0x18004bccd  test    byte ptr [rcx+1Ch], 10h
0x18004bcd1  jz      short loc_18004BD16
0x18004bcd3  mov     rcx, [rcx+10h]
0x18004bcd7  lea     edx, [rbx+0Dh]
0x18004bcda  mov     r9d, ebx
0x18004bcdd  lea     r8, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids
0x18004bce4  call    WPP_SF_d
0x18004bce9  jmp     short loc_18004BD16
0x18004bceb  mov     ecx, [rdi+4]
0x18004bcee  xor     ebx, ebx
0x18004bcf0  lea     eax, [rbx+1]
0x18004bcf3  sub     ecx, eax
0x18004bcf5  jz      short loc_18004BD04
0x18004bcf7  cmp     ecx, eax
0x18004bcf9  jnz     short loc_18004BD0B
0x18004bcfb  mov     [r9], eax
0x18004bcfe  mov     [r9+4], al
0x18004bd02  jmp     short loc_18004BD0B
0x18004bd04  mov     [r9], ebx
0x18004bd07  mov     [r9+4], bl
0x18004bd0b  mov     [r14], eax
0x18004bd0e  mov     [rsi], r9
0x18004bd11  mov     [rsp+48h+arg_8], rbx
0x18004bd16  lea     rcx, [rsp+48h+arg_8]
0x18004bd1b  call    LipsIkePolicyProposalDestroy
0x18004bd20  test    ebx, ebx
0x18004bd22  jnz     short loc_18004BD28
0x18004bd24  xor     eax, eax
0x18004bd26  jmp     short loc_18004BD36
0x18004bd28  lea     rdx, aLipsipsecpolic; "LipsIpsecPolicyAhCreate"
0x18004bd2f  mov     ecx, ebx
0x18004bd31  call    LipsReportError
0x18004bd36  add     rsp, 28h
0x18004bd3a  pop     r14
0x18004bd3c  pop     rdi
0x18004bd3d  pop     rsi
0x18004bd3e  pop     rbx
0x18004bd3f  retn
```
