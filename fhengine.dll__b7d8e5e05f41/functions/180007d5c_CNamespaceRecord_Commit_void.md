# CNamespaceRecord::Commit(void)

- ea: `0x180007d5c`
- end: `0x180007e95`
- name: `?Commit@CNamespaceRecord@@QEAAJXZ`
- size: `313`
- prototype: `__int64 __fastcall(CNamespaceRecord *__hidden this)`
- caller_count: `12`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bcd8`
- `0x18000d4f4`
- `0x18000de68`
- `0x18000fde8`
- `0x180010914`
- `0x180010de8`
- `0x180013e14`
- `0x18001afe4`
- `0x18001baf8`
- `0x18001cb74`
- `0x18001eaf0`
- `0x180021f70`

## callees

- `0x180007d5c`
- `0x180009258`
- `0x18000935c`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CNamespaceRecord::Commit(CNamespaceRecord *this)
{
  _DWORD *v2; // rsi
  __int64 *v3; // rcx
  __int64 v4; // rax
  int v5; // edx
  int v6; // r11d
  int v7; // edi
  __int64 v8; // rbp
  __int64 v9; // r9
  __int64 v10; // r10
  unsigned int v11; // r14d
  __int64 v12; // r8
  __int64 v13; // r15
  int v14; // eax
  unsigned int v15; // edi
  int v16; // eax

  v2 = (_DWORD *)((char *)this + 16);
  v3 = *(__int64 **)this;
  v4 = *v3;
  v5 = *((_DWORD *)this + 21);
  v6 = *((_DWORD *)this + 20);
  v7 = *((_DWORD *)this + 19);
  v8 = *((_QWORD *)this + 6);
  v9 = *(_QWORD *)((char *)this + 68);
  v10 = *(_QWORD *)((char *)this + 60);
  v11 = *((_DWORD *)this + 14);
  v12 = *((unsigned __int16 *)this + 20);
  v13 = *((_QWORD *)this + 3);
  if ( *v2 == -1 )
  {
    v16 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, _QWORD, __int64, __int64, __int64, int, int, int, _DWORD *))(v4 + 104))(
            v3,
            v13,
            v12,
            v11,
            v10,
            v9,
            v8,
            v7,
            v6,
            v5,
            v2);
    v15 = v16;
    if ( v16 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids,
        *((_QWORD *)this + 3),
        v16);
  }
  else
  {
    v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD, unsigned int, __int64, __int64, __int64, int, int, int))(v4 + 112))(
            v3,
            (unsigned int)*v2,
            v13,
            (unsigned __int16)v12,
            v11,
            v10,
            v9,
            v8,
            v7,
            v6,
            v5);
    v15 = v14;
    if ( v14 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids,
        (unsigned int)*v2,
        v14);
  }
  return v15;
}

```

## disassembly

```asm
0x180007d5c  push    rbx
0x180007d5e  push    rbp
0x180007d5f  push    rsi
0x180007d60  push    rdi
0x180007d61  push    r14
0x180007d63  push    r15
0x180007d65  sub     rsp, 68h
0x180007d69  mov     rbx, rcx
0x180007d6c  lea     rsi, [rcx+10h]
0x180007d70  mov     rcx, [rcx]
0x180007d73  mov     rax, [rcx]
0x180007d76  mov     edx, [rbx+54h]
0x180007d79  mov     r11d, [rbx+50h]
0x180007d7d  mov     edi, [rbx+4Ch]
0x180007d80  mov     rbp, [rbx+30h]
0x180007d84  mov     r9, [rbx+44h]
0x180007d88  mov     r10, [rbx+3Ch]
0x180007d8c  mov     r14d, [rbx+38h]
0x180007d90  movzx   r8d, word ptr [rbx+28h]
0x180007d95  mov     r15, [rbx+18h]
0x180007d99  cmp     dword ptr [rsi], 0FFFFFFFFh
0x180007d9c  jz      short loc_180007E1A
0x180007d9e  mov     dword ptr [rsp+98h+var_48], edx
0x180007da2  mov     [rsp+98h+var_50], r11d
0x180007da7  mov     [rsp+98h+var_58], edi
0x180007dab  mov     [rsp+98h+var_60], rbp
0x180007db0  mov     [rsp+98h+var_68], r9
0x180007db5  mov     [rsp+98h+var_70], r10
0x180007dba  mov     dword ptr [rsp+98h+var_78], r14d
0x180007dbf  movzx   r9d, r8w
0x180007dc3  mov     r8, r15
0x180007dc6  mov     edx, [rsi]
0x180007dc8  mov     rax, [rax+70h]
0x180007dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dd1  mov     edi, eax
0x180007dd3  test    eax, eax
0x180007dd5  jns     loc_180007E86
0x180007ddb  lea     rdx, WPP_GLOBAL_Control
0x180007de2  mov     rcx, cs:WPP_GLOBAL_Control
0x180007de9  cmp     rcx, rdx
0x180007dec  jz      loc_180007E86
0x180007df2  test    byte ptr [rcx+1Ch], 1
0x180007df6  jz      loc_180007E86
0x180007dfc  mov     edx, 18h
0x180007e01  mov     dword ptr [rsp+98h+var_78], eax
0x180007e05  mov     r9d, [rsi]
0x180007e08  lea     r8, WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids
0x180007e0f  mov     rcx, [rcx+10h]
0x180007e13  call    WPP_SF_dd
0x180007e18  jmp     short loc_180007E86
0x180007e1a  mov     [rsp+98h+var_48], rsi
0x180007e1f  mov     [rsp+98h+var_50], edx
0x180007e23  mov     [rsp+98h+var_58], r11d
0x180007e28  mov     dword ptr [rsp+98h+var_60], edi
0x180007e2c  mov     [rsp+98h+var_68], rbp
0x180007e31  mov     [rsp+98h+var_70], r9
0x180007e36  mov     [rsp+98h+var_78], r10
0x180007e3b  mov     r9d, r14d
0x180007e3e  mov     rdx, r15
0x180007e41  mov     rax, [rax+68h]
0x180007e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e4a  mov     edi, eax
0x180007e4c  test    eax, eax
0x180007e4e  jns     short loc_180007E86
0x180007e50  lea     rdx, WPP_GLOBAL_Control
0x180007e57  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e5e  cmp     rcx, rdx
0x180007e61  jz      short loc_180007E86
0x180007e63  test    byte ptr [rcx+1Ch], 1
0x180007e67  jz      short loc_180007E86
0x180007e69  mov     edx, 19h
0x180007e6e  mov     dword ptr [rsp+98h+var_78], eax
0x180007e72  mov     r9, [rbx+18h]
0x180007e76  lea     r8, WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids
0x180007e7d  mov     rcx, [rcx+10h]
0x180007e81  call    WPP_SF_Sd
0x180007e86  mov     eax, edi
0x180007e88  add     rsp, 68h
0x180007e8c  pop     r15
0x180007e8e  pop     r14
0x180007e90  pop     rdi
0x180007e91  pop     rsi
0x180007e92  pop     rbp
0x180007e93  pop     rbx
0x180007e94  retn
```
