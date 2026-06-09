# CConfigDescriptor::RefreshPoliciesInEngine(int,int)

- ea: `0x180007f50`
- end: `0x1800080d5`
- name: `?RefreshPoliciesInEngine@CConfigDescriptor@@QEAAXHH@Z`
- size: `389`
- prototype: `void __fastcall(CConfigDescriptor *__hidden this, int, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180003190`
- `0x180003f00`
- `0x1800065c0`

## callees

- `0x180007f50`
- `0x18000d910`
- `0x1800103d4`
- `0x180010de8`
- `0x180013010`

## pseudocode

```c
void __fastcall CConfigDescriptor::RefreshPoliciesInEngine(CConfigDescriptor *this, int a2, int a3)
{
  __int64 *v5; // rax
  __int64 v6; // rdi
  int v7; // esi
  __int64 v8; // rax
  __int64 v9; // rbp
  const wchar_t *v10; // rdx
  int v11; // r8d
  __int64 v12; // rdi
  __int64 v13; // rax
  unsigned int v14; // ebx
  const wchar_t *v15; // r9

  v5 = (__int64 *)*((_QWORD *)this + 17);
  if ( v5 )
  {
    v6 = *v5;
    if ( *v5 )
    {
      if ( a2 )
      {
        v7 = a3 != 0 ? 2 : 0;
        v8 = 112;
        if ( !a3 )
          v8 = 104;
      }
      else if ( a3 )
      {
        v7 = 3;
        v8 = 128;
      }
      else
      {
        v7 = 1;
        v8 = 120;
      }
      v9 = *(_QWORD *)((char *)this + v8);
      if ( v9 == -1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            45,
            &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
            *(_QWORD *)(v6 + 24));
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_Si(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          (unsigned int)&WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
          *(_QWORD *)(v6 + 24),
          (unsigned __int64)(v9 + 0xFFFFF) >> 20);
      }
      *(_DWORD *)(v6 + 72) = v7;
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v6 + 16) + 48LL))(*(_QWORD *)(v6 + 16), v9);
      v12 = **((_QWORD **)this + 17);
      v13 = 96;
      if ( a2 )
        v13 = 92;
      v14 = *(_DWORD *)((char *)this + v13);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        if ( v14 == 2 )
        {
          v15 = L"IoPriorityHintNormal";
        }
        else
        {
          v15 = L"IoPriorityHintLow";
          v10 = L"IoPriorityHintVeryLow";
          if ( v14 != 1 )
            v15 = L"IoPriorityHintVeryLow";
        }
        WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)v10, v11, (_DWORD)v15, *(_QWORD *)(v12 + 24));
      }
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v12 + 16) + 40LL))(*(_QWORD *)(v12 + 16), v14);
    }
  }
}

```

## disassembly

```asm
0x180007f50  push    rbx
0x180007f52  push    rbp
0x180007f53  push    rsi
0x180007f54  push    rdi
0x180007f55  push    r14
0x180007f57  push    r15
0x180007f59  sub     rsp, 38h
0x180007f5d  mov     r14d, edx
0x180007f60  mov     rbx, rcx
0x180007f63  mov     rax, [rcx+88h]
0x180007f6a  test    rax, rax
0x180007f6d  jz      loc_1800080C8
0x180007f73  mov     rdi, [rax]
0x180007f76  test    rdi, rdi
0x180007f79  jz      loc_1800080C8
0x180007f7f  test    edx, edx
0x180007f81  jz      short loc_180007F9F
0x180007f83  mov     eax, r8d
0x180007f86  neg     eax
0x180007f88  sbb     esi, esi
0x180007f8a  and     esi, 2
0x180007f8d  mov     eax, 70h ; 'p'
0x180007f92  mov     ecx, 68h ; 'h'
0x180007f97  test    r8d, r8d
0x180007f9a  cmovz   eax, ecx
0x180007f9d  jmp     short loc_180007FBA
0x180007f9f  test    r8d, r8d
0x180007fa2  jz      short loc_180007FB0
0x180007fa4  mov     esi, 3
0x180007fa9  mov     eax, 80h
0x180007fae  jmp     short loc_180007FBA
0x180007fb0  mov     esi, 1
0x180007fb5  mov     eax, 78h ; 'x'
0x180007fba  mov     rbp, [rax+rbx]
0x180007fbe  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180007fc2  jz      short loc_180008008
0x180007fc4  lea     r15, WPP_GLOBAL_Control
0x180007fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fd2  cmp     rcx, r15
0x180007fd5  jz      short loc_18000803A
0x180007fd7  test    byte ptr [rcx+1Ch], 8
0x180007fdb  jz      short loc_18000803A
0x180007fdd  lea     rax, [rbp+0FFFFFh]
0x180007fe4  shr     rax, 14h
0x180007fe8  mov     edx, 2Ch ; ','
0x180007fed  mov     [rsp+68h+var_48], rax
0x180007ff2  mov     r9, [rdi+18h]
0x180007ff6  lea     r8, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x180007ffd  mov     rcx, [rcx+10h]
0x180008001  call    WPP_SF_Si
0x180008006  jmp     short loc_18000803A
0x180008008  lea     r15, WPP_GLOBAL_Control
0x18000800f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008016  cmp     rcx, r15
0x180008019  jz      short loc_18000803A
0x18000801b  test    byte ptr [rcx+1Ch], 8
0x18000801f  jz      short loc_18000803A
0x180008021  mov     edx, 2Dh ; '-'
0x180008026  mov     r9, [rdi+18h]
0x18000802a  lea     r8, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x180008031  mov     rcx, [rcx+10h]
0x180008035  call    WPP_SF_S
0x18000803a  mov     [rdi+48h], esi
0x18000803d  mov     rcx, [rdi+10h]
0x180008041  mov     rax, [rcx]
0x180008044  mov     rdx, rbp
0x180008047  mov     rax, [rax+30h]
0x18000804b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008050  nop
0x180008051  mov     rax, [rbx+88h]
0x180008058  mov     rdi, [rax]
0x18000805b  mov     ecx, 5Ch ; '\'
0x180008060  mov     eax, 60h ; '`'
0x180008065  test    r14d, r14d
0x180008068  cmovnz  eax, ecx
0x18000806b  mov     ebx, [rax+rbx]
0x18000806e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008075  cmp     rcx, r15
0x180008078  jz      short loc_1800080B5
0x18000807a  test    byte ptr [rcx+1Ch], 8
0x18000807e  jz      short loc_1800080B5
0x180008080  mov     rax, [rdi+18h]
0x180008084  cmp     ebx, 2
0x180008087  jnz     short loc_180008092
0x180008089  lea     r9, aIopriorityhint_1; "IoPriorityHintNormal"
0x180008090  jmp     short loc_1800080A7
0x180008092  lea     r9, aIopriorityhint_0; "IoPriorityHintLow"
0x180008099  lea     rdx, aIopriorityhint; "IoPriorityHintVeryLow"
0x1800080a0  cmp     ebx, 1
0x1800080a3  cmovnz  r9, rdx
0x1800080a7  mov     [rsp+68h+var_48], rax
0x1800080ac  mov     rcx, [rcx+10h]
0x1800080b0  call    WPP_SF_SS
0x1800080b5  mov     rcx, [rdi+10h]
0x1800080b9  mov     rax, [rcx]
0x1800080bc  mov     edx, ebx
0x1800080be  mov     rax, [rax+28h]
0x1800080c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080c7  nop
0x1800080c8  add     rsp, 38h
0x1800080cc  pop     r15
0x1800080ce  pop     r14
0x1800080d0  pop     rdi
0x1800080d1  pop     rsi
0x1800080d2  pop     rbp
0x1800080d3  pop     rbx
0x1800080d4  retn
```
