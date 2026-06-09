# LipsFilterCreate

- ea: `0x18004b410`
- end: `0x18004b5b2`
- name: `LipsFilterCreate`
- size: `418`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, __int64, char, __int16, __int64, _QWORD *)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x18004713c`
- `0x1800475ec`
- `0x180047a34`
- `0x18004a090`
- `0x18004a530`

## callees

- `0x180006f00`
- `0x18000e510`
- `0x18004a854`
- `0x18004b410`
- `0x18004b5b8`
- `0x18004b618`
- `0x18004b844`

## pseudocode

```c
__int64 __fastcall LipsFilterCreate(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        __int16 a7,
        __int64 a8,
        _QWORD *a9)
{
  _QWORD *v9; // rsi
  BOOL v11; // r14d
  _QWORD *v15; // rax
  _QWORD *v16; // rdi
  unsigned int v17; // ebx
  _QWORD *v18; // rcx
  __int64 v19; // rdx

  v9 = a9;
  v11 = *(_DWORD *)(a2 + 4) == 0;
  *a9 = 0;
  v15 = IpsecAllocMem(0xC8u);
  a9 = v15;
  v16 = v15;
  if ( !v15 )
  {
    v17 = 8;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_14;
    v19 = 10;
    goto LABEL_13;
  }
  v17 = LipsFilterInit(a8, v15);
  if ( v17 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_14;
    v19 = 11;
    goto LABEL_13;
  }
  LipsFilterOptionsGet(v11, a1, (_DWORD)v16 + 64, (_DWORD)v16 + 132, (__int64)(v16 + 16));
  v17 = LipsFilterCondition5TupleCreate(a1, a2, a3, a4, a5, a6, a7);
  if ( !v17 )
  {
    *((_DWORD *)v16 + 28) = 0;
    v16[15] = 0;
    *v9 = v16;
    return v17;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v19 = 12;
LABEL_13:
    WPP_SF_d(v18[2], v19, WPP_b2a5e40790a73c32bbd4ebb8c897c7db_Traceguids, v17);
  }
LABEL_14:
  LipsFilterDestroy(&a9);
  return v17;
}

```

## disassembly

```asm
0x18004b410  mov     rax, rsp
0x18004b413  push    rbx
0x18004b414  push    rbp
0x18004b415  push    rsi
0x18004b416  push    rdi
0x18004b417  push    r12
0x18004b419  push    r13
0x18004b41b  push    r14
0x18004b41d  push    r15
0x18004b41f  sub     rsp, 68h
0x18004b423  mov     rsi, [rsp+0A8h+arg_40]
0x18004b42b  xor     ebx, ebx
0x18004b42d  cmp     [rdx+4], ebx
0x18004b430  mov     r15d, ecx
0x18004b433  mov     r14d, ebx
0x18004b436  mov     [rax+10h], ebx
0x18004b439  mov     ecx, 0C8h
0x18004b43e  mov     [rax-58h], rbx
0x18004b442  setz    r14b
0x18004b446  mov     [rsi], rbx
0x18004b449  mov     r12, r9
0x18004b44c  mov     r13, r8
0x18004b44f  mov     rbp, rdx
0x18004b452  call    IpsecAllocMem
0x18004b457  mov     [rsp+0A8h+arg_40], rax
0x18004b45f  mov     rdi, rax
0x18004b462  test    rax, rax
0x18004b465  jnz     short loc_18004B493
0x18004b467  lea     ebx, [rax+8]
0x18004b46a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b471  lea     rax, WPP_GLOBAL_Control
0x18004b478  cmp     rcx, rax
0x18004b47b  jz      loc_18004B57A
0x18004b481  test    byte ptr [rcx+1Ch], 10h
0x18004b485  jz      loc_18004B57A
0x18004b48b  lea     edx, [rdi+0Ah]
0x18004b48e  jmp     loc_18004B567
0x18004b493  mov     rcx, [rsp+0A8h+arg_38]
0x18004b49b  mov     rdx, rdi
0x18004b49e  call    LipsFilterInit
0x18004b4a3  mov     ebx, eax
0x18004b4a5  test    eax, eax
0x18004b4a7  jz      short loc_18004B4D4
0x18004b4a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b4b0  lea     rax, WPP_GLOBAL_Control
0x18004b4b7  cmp     rcx, rax
0x18004b4ba  jz      loc_18004B57A
0x18004b4c0  test    byte ptr [rcx+1Ch], 10h
0x18004b4c4  jz      loc_18004B57A
0x18004b4ca  mov     edx, 0Bh
0x18004b4cf  jmp     loc_18004B567
0x18004b4d4  lea     rax, [rdi+80h]
0x18004b4db  mov     edx, r15d
0x18004b4de  lea     r9, [rdi+84h]
0x18004b4e5  mov     [rsp+0A8h+var_88], rax
0x18004b4ea  lea     r8, [rdi+40h]
0x18004b4ee  mov     ecx, r14d
0x18004b4f1  call    LipsFilterOptionsGet
0x18004b4f6  lea     rax, [rsp+0A8h+arg_8]
0x18004b4fe  mov     r9, r12
0x18004b501  mov     [rsp+0A8h+var_60], rax
0x18004b506  mov     r8, r13
0x18004b509  lea     rax, [rsp+0A8h+var_58]
0x18004b50e  mov     rdx, rbp
0x18004b511  mov     [rsp+0A8h+var_68], rax
0x18004b516  mov     ecx, r15d
0x18004b519  movzx   eax, [rsp+0A8h+arg_30]
0x18004b521  mov     [rsp+0A8h+var_78], ax
0x18004b526  mov     al, [rsp+0A8h+arg_28]
0x18004b52d  mov     [rsp+0A8h+var_80], al
0x18004b531  mov     rax, [rsp+0A8h+arg_20]
0x18004b539  mov     [rsp+0A8h+var_88], rax
0x18004b53e  call    LipsFilterCondition5TupleCreate
0x18004b543  mov     ebx, eax
0x18004b545  test    eax, eax
0x18004b547  jz      short loc_18004B589
0x18004b549  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b550  lea     rax, WPP_GLOBAL_Control
0x18004b557  cmp     rcx, rax
0x18004b55a  jz      short loc_18004B57A
0x18004b55c  test    byte ptr [rcx+1Ch], 10h
0x18004b560  jz      short loc_18004B57A
0x18004b562  mov     edx, 0Ch
0x18004b567  mov     rcx, [rcx+10h]
0x18004b56b  lea     r8, WPP_b2a5e40790a73c32bbd4ebb8c897c7db_Traceguids
0x18004b572  mov     r9d, ebx
0x18004b575  call    WPP_SF_d
0x18004b57a  lea     rcx, [rsp+0A8h+arg_40]
0x18004b582  call    LipsFilterDestroy
0x18004b587  jmp     short loc_18004B59F
0x18004b589  mov     eax, [rsp+0A8h+arg_8]
0x18004b590  mov     [rdi+70h], eax
0x18004b593  mov     rax, [rsp+0A8h+var_58]
0x18004b598  mov     [rdi+78h], rax
0x18004b59c  mov     [rsi], rdi
0x18004b59f  mov     eax, ebx
0x18004b5a1  add     rsp, 68h
0x18004b5a5  pop     r15
0x18004b5a7  pop     r14
0x18004b5a9  pop     r13
0x18004b5ab  pop     r12
0x18004b5ad  pop     rdi
0x18004b5ae  pop     rsi
0x18004b5af  pop     rbp
0x18004b5b0  pop     rbx
0x18004b5b1  retn
```
