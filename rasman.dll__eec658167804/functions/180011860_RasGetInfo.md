# RasGetInfo

- ea: `0x180011860`
- end: `0x1800119bd`
- name: `RasGetInfo`
- size: `349`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18001df30`
- `0x18001e0b0`
- `0x18001e2e0`

## callees

- `0x180011790`
- `0x180011860`
- `0x1800119c4`
- `0x180011b40`
- `0x180021000`
- `0x1800219f4`

## pseudocode

```c
__int64 __fastcall RasGetInfo(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  unsigned int v7; // ebx
  PVOID *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, a3, a1, a2);
  }
  if ( !(unsigned int)ValidatePortHandle(a2) )
  {
    v7 = 601;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_6;
      v9 = 234;
LABEL_19:
      v10 = v7;
LABEL_28:
      WPP_SF_d(v8[2], v9, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v10);
      goto LABEL_5;
    }
    return v7;
  }
  if ( !(unsigned int)ValidateConnectionHandle(a1) )
  {
    v7 = -2147024809;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_6;
      v9 = 235;
      goto LABEL_19;
    }
    return v7;
  }
  result = SubmitRequest(a1, 22, a2, a3);
  v7 = result;
  if ( !(_DWORD)result )
  {
LABEL_5:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_6;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 236;
      v10 = (unsigned int)result;
      goto LABEL_28;
    }
LABEL_6:
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
      WPP_SF_d(v8[2], 237, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180011860  push    rbx
0x180011862  push    rbp
0x180011863  push    rsi
0x180011864  push    rdi
0x180011865  sub     rsp, 38h
0x180011869  mov     rsi, r8
0x18001186c  mov     rbx, rdx
0x18001186f  mov     rdi, rcx
0x180011872  mov     rcx, cs:WPP_GLOBAL_Control
0x180011879  lea     rbp, WPP_GLOBAL_Control
0x180011880  cmp     rcx, rbp
0x180011883  jnz     short loc_1800118D9
0x180011885  mov     rcx, rbx
0x180011888  call    ValidatePortHandle
0x18001188d  test    eax, eax
0x18001188f  jz      loc_180011923
0x180011895  mov     rcx, rdi
0x180011898  call    ValidateConnectionHandle
0x18001189d  test    eax, eax
0x18001189f  jz      loc_180011951
0x1800118a5  mov     edx, 16h
0x1800118aa  mov     r9, rsi
0x1800118ad  mov     r8, rbx
0x1800118b0  mov     rcx, rdi
0x1800118b3  call    SubmitRequest
0x1800118b8  mov     ebx, eax
0x1800118ba  test    eax, eax
0x1800118bc  jnz     loc_18001197C
0x1800118c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118c9  cmp     rcx, rbp
0x1800118cc  jnz     short loc_1800118FD
0x1800118ce  mov     eax, ebx
0x1800118d0  add     rsp, 38h
0x1800118d4  pop     rdi
0x1800118d5  pop     rsi
0x1800118d6  pop     rbp
0x1800118d7  pop     rbx
0x1800118d8  retn
0x1800118d9  test    byte ptr [rcx+1Ch], 40h
0x1800118dd  jz      short loc_180011885
0x1800118df  cmp     byte ptr [rcx+19h], 6
0x1800118e3  jb      short loc_180011885
0x1800118e5  mov     rcx, [rcx+10h]
0x1800118e9  mov     edx, 0E9h
0x1800118ee  mov     r9, rdi
0x1800118f1  mov     [rsp+58h+var_38], rbx
0x1800118f6  call    WPP_SF_qq
0x1800118fb  jmp     short loc_180011885
0x1800118fd  test    byte ptr [rcx+1Ch], 40h
0x180011901  jz      short loc_1800118CE
0x180011903  cmp     byte ptr [rcx+19h], 6
0x180011907  jb      short loc_1800118CE
0x180011909  mov     rcx, [rcx+10h]
0x18001190d  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180011914  mov     edx, 0EDh
0x180011919  mov     r9d, ebx
0x18001191c  call    WPP_SF_d
0x180011921  jmp     short loc_1800118CE
0x180011923  mov     ebx, 259h
0x180011928  mov     rcx, cs:WPP_GLOBAL_Control
0x18001192f  cmp     rcx, rbp
0x180011932  jz      short loc_1800118CE
0x180011934  test    byte ptr [rcx+1Ch], 40h
0x180011938  jz      short loc_1800118C9
0x18001193a  cmp     byte ptr [rcx+19h], 2
0x18001193e  jb      short loc_1800118C9
0x180011940  mov     edx, 0EAh
0x180011945  jmp     short loc_18001194C
0x180011947  mov     edx, 0EBh
0x18001194c  mov     r9d, ebx
0x18001194f  jmp     short loc_1800119A8
0x180011951  mov     ebx, 80070057h
0x180011956  mov     rcx, cs:WPP_GLOBAL_Control
0x18001195d  cmp     rcx, rbp
0x180011960  jz      loc_1800118CE
0x180011966  test    byte ptr [rcx+1Ch], 40h
0x18001196a  jz      loc_1800118C9
0x180011970  cmp     byte ptr [rcx+19h], 2
0x180011974  jb      loc_1800118C9
0x18001197a  jmp     short loc_180011947
0x18001197c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011983  cmp     rcx, rbp
0x180011986  jz      loc_1800118D0
0x18001198c  test    byte ptr [rcx+1Ch], 40h
0x180011990  jz      loc_1800118C9
0x180011996  cmp     byte ptr [rcx+19h], 2
0x18001199a  jb      loc_1800118C9
0x1800119a0  mov     edx, 0ECh
0x1800119a5  mov     r9d, eax
0x1800119a8  mov     rcx, [rcx+10h]
0x1800119ac  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800119b3  call    WPP_SF_d
0x1800119b8  jmp     loc_1800118C2
```
