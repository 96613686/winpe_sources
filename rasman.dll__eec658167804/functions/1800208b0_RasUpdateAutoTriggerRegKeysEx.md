# RasUpdateAutoTriggerRegKeysEx

- ea: `0x1800208b0`
- end: `0x180020a38`
- name: `RasUpdateAutoTriggerRegKeysEx`
- size: `392`
- prototype: `__int64 __fastcall(__int64, const char *, __int64, int, int, const char *, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180002f80`
- `0x1800208b0`
- `0x180021000`
- `0x180021254`

## pseudocode

```c
__int64 __fastcall RasUpdateAutoTriggerRegKeysEx(
        __int64 a1,
        const char *a2,
        __int64 a3,
        int a4,
        int a5,
        const char *a6,
        int a7,
        int a8)
{
  __int64 v9; // rax
  const char *v12; // r11
  const char *v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // ebx
  PVOID *v16; // rcx
  __int64 v18; // [rsp+20h] [rbp-88h]
  __int64 v19; // [rsp+28h] [rbp-80h]
  __int64 v20; // [rsp+38h] [rbp-70h]
  __int64 v21; // [rsp+40h] [rbp-68h]

  v9 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v12 = a6;
    v13 = a2;
    if ( !a6 )
      v12 = L"<NULL>";
    if ( !a2 )
      v13 = L"<NULL>";
    WPP_SF_SScccSc(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v13, a4 != 0, a5 != 0, a8 != 0, (__int64)v12, a7 != 0);
    v9 = a3;
  }
  LODWORD(v21) = a8;
  LODWORD(v20) = a7;
  LODWORD(v19) = a5;
  LODWORD(v18) = a4;
  v14 = SubmitLocalRequest(0x9Bu, a1, a2, v9, v18, v19, a6, v20, v21);
  v15 = v14;
  if ( !v14 )
    goto LABEL_14;
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v15;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 710, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v14);
LABEL_14:
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 0x40) != 0 && *((_BYTE *)v16 + 25) >= 6u )
    WPP_SF_d(v16[2], 711, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x1800208b0  mov     [rsp+arg_10], r8
0x1800208b5  push    rbx
0x1800208b6  push    rbp
0x1800208b7  push    rsi
0x1800208b8  push    rdi
0x1800208b9  push    r12
0x1800208bb  push    r13
0x1800208bd  push    r14
0x1800208bf  push    r15
0x1800208c1  sub     rsp, 68h
0x1800208c5  mov     r14d, r9d
0x1800208c8  mov     rax, r8
0x1800208cb  mov     rdi, rdx
0x1800208ce  mov     rsi, rcx
0x1800208d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208d8  lea     rdx, WPP_GLOBAL_Control
0x1800208df  mov     r15d, [rsp+0A8h+arg_38]
0x1800208e7  mov     r12d, [rsp+0A8h+arg_30]
0x1800208ef  mov     rbp, [rsp+0A8h+arg_28]
0x1800208f7  mov     r13d, [rsp+0A8h+arg_20]
0x1800208ff  cmp     rcx, rdx
0x180020902  jz      short loc_180020983
0x180020904  test    byte ptr [rcx+1Ch], 40h
0x180020908  jz      short loc_180020983
0x18002090a  cmp     byte ptr [rcx+19h], 6
0x18002090e  jb      short loc_180020983
0x180020910  mov     rcx, [rcx+10h]; LoggerHandle
0x180020914  lea     r9, aNull_2; "<NULL>"
0x18002091b  test    r12d, r12d
0x18002091e  mov     [rsp+0A8h+var_58], r9
0x180020923  mov     r11, rbp
0x180020926  mov     rax, rdi
0x180020929  setnz   bl
0x18002092c  test    rbp, rbp
0x18002092f  mov     [rsp+0A8h+var_60], bl; char
0x180020933  cmovz   r11, r9
0x180020937  test    r15d, r15d
0x18002093a  mov     [rsp+0A8h+var_68], r11; __int64
0x18002093f  setnz   r10b
0x180020943  test    r13d, r13d
0x180020946  mov     [rsp+0A8h+var_70], r10b; char
0x18002094b  setnz   r8b
0x18002094f  test    r14d, r14d
0x180020952  mov     [rsp+0A8h+var_78], r8b; char
0x180020957  setnz   dl
0x18002095a  test    rdi, rdi
0x18002095d  mov     [rsp+0A8h+var_80], dl; char
0x180020961  cmovz   rax, r9
0x180020965  test    rsi, rsi
0x180020968  mov     r9, rsi
0x18002096b  mov     [rsp+0A8h+var_88], rax; __int64
0x180020970  cmovz   r9, [rsp+0A8h+var_58]
0x180020976  call    WPP_SF_SScccSc
0x18002097b  mov     rax, [rsp+0A8h+arg_10]
0x180020983  mov     dword ptr [rsp+0A8h+var_68], r15d
0x180020988  mov     ecx, 9Bh
0x18002098d  mov     dword ptr [rsp+0A8h+var_70], r12d
0x180020992  mov     r9, rax
0x180020995  mov     qword ptr [rsp+0A8h+var_78], rbp
0x18002099a  mov     r8, rdi
0x18002099d  mov     dword ptr [rsp+0A8h+var_80], r13d
0x1800209a2  mov     rdx, rsi
0x1800209a5  mov     dword ptr [rsp+0A8h+var_88], r14d
0x1800209aa  call    SubmitLocalRequest
0x1800209af  mov     ebx, eax
0x1800209b1  test    eax, eax
0x1800209b3  jz      short loc_1800209EE
0x1800209b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800209bc  lea     rdi, WPP_GLOBAL_Control
0x1800209c3  cmp     rcx, rdi
0x1800209c6  jz      short loc_180020A25
0x1800209c8  test    byte ptr [rcx+1Ch], 40h
0x1800209cc  jz      short loc_1800209FC
0x1800209ce  cmp     byte ptr [rcx+19h], 2
0x1800209d2  jb      short loc_1800209FC
0x1800209d4  mov     rcx, [rcx+10h]
0x1800209d8  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800209df  mov     edx, 2C6h
0x1800209e4  mov     r9d, eax
0x1800209e7  call    WPP_SF_d
0x1800209ec  jmp     short loc_1800209F5
0x1800209ee  lea     rdi, WPP_GLOBAL_Control
0x1800209f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800209fc  cmp     rcx, rdi
0x1800209ff  jz      short loc_180020A25
0x180020a01  test    byte ptr [rcx+1Ch], 40h
0x180020a05  jz      short loc_180020A25
0x180020a07  cmp     byte ptr [rcx+19h], 6
0x180020a0b  jb      short loc_180020A25
0x180020a0d  mov     rcx, [rcx+10h]
0x180020a11  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020a18  mov     edx, 2C7h
0x180020a1d  mov     r9d, ebx
0x180020a20  call    WPP_SF_d
0x180020a25  mov     eax, ebx
0x180020a27  add     rsp, 68h
0x180020a2b  pop     r15
0x180020a2d  pop     r14
0x180020a2f  pop     r13
0x180020a31  pop     r12
0x180020a33  pop     rdi
0x180020a34  pop     rsi
0x180020a35  pop     rbp
0x180020a36  pop     rbx
0x180020a37  retn
```
