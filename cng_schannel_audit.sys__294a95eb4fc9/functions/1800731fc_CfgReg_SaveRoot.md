# _CfgReg_SaveRoot

- ea: `0x1800731fc`
- end: `0x1800733d1`
- name: `_CfgReg_SaveRoot`
- size: `469`
- prototype: ``
- caller_count: `10`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180069d20`
- `0x180069f50`
- `0x18006a2cc`
- `0x18006a480`
- `0x18006a79c`
- `0x18006aa0c`
- `0x18006ba6c`
- `0x18006bca0`
- `0x18006bfb4`
- `0x18006c440`

## callees

- `0x18001bd90`
- `0x18001be10`
- `0x180036aa0`
- `0x18004c328`
- `0x180073058`
- `0x1800731fc`
- `0x1800735b0`
- `0x180073700`

## string_xrefs

- `0x18007322e`: `System\CurrentControlSet\Control\Cryptography\Configuration`
- `0x180073251`: `System\CurrentControlSet\Control\Cryptography\Configuration`

## pseudocode

```c
__int64 __fastcall CfgReg_SaveRoot(__int64 a1)
{
  ULONG v2; // ebx
  unsigned int v3; // r12d
  __int64 v4; // r14
  __int64 v5; // rsi
  HANDLE v6; // r15
  const WCHAR ***v7; // rdx
  ULONG v8; // eax
  __int64 v9; // r8
  ULONG v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rax
  _QWORD **v13; // rax
  PVOID *v14; // rax
  HANDLE Handle; // [rsp+58h] [rbp+38h] BYREF
  HANDLE v17; // [rsp+60h] [rbp+40h] BYREF

  v17 = 0;
  v2 = KeRegOpenKey(
         (void *)0xFFFFFFFF80000002LL,
         L"System\\CurrentControlSet\\Control\\Cryptography\\Configuration",
         0x3001Fu,
         &v17);
  if ( v2 == 5 )
    v2 = KeRegOpenKey(
           (void *)0xFFFFFFFF80000002LL,
           L"System\\CurrentControlSet\\Control\\Cryptography\\Configuration",
           0x20019u,
           &v17);
  if ( !v2 )
  {
    v3 = *(_DWORD *)(a1 + 104);
    v4 = 0;
    v5 = *(_QWORD *)(a1 + 112);
    v6 = v17;
    while ( 1 )
    {
      if ( (unsigned int)v4 >= v3 )
        goto LABEL_28;
      v7 = *(const WCHAR ****)(v5 + 8 * v4);
      if ( v7 )
        break;
LABEL_27:
      v4 = (unsigned int)(v4 + 1);
    }
    Handle = 0;
    v8 = KeRegOpenKey(v6, **v7, 0x3001Fu, &Handle);
    v2 = v8;
    if ( v8 == 5 )
    {
      v10 = KeRegOpenKey(v6, ***(const WCHAR ****)(v5 + 8 * v4), 0x20019u, &Handle);
    }
    else
    {
      if ( v8 != 2 )
      {
LABEL_14:
        if ( !v2 )
        {
          v2 = CfgReg_OnSaveTableNode(Handle, ((*(_DWORD *)(*(_QWORD *)(v5 + 8 * v4) + 8LL) - 1) & 0xFFFFFFFD) == 0);
          if ( !v2 )
          {
            v12 = *(_QWORD *)(v5 + 8 * v4);
            if ( *(_DWORD *)(v12 + 8) == 2 )
            {
              KeRegCloseKey(Handle);
              v13 = *(_QWORD ***)(v5 + 8 * v4);
              Handle = 0;
              v2 = KeRegDeleteKeyRecursive(v6, **v13, v2 + 64);
              if ( !v2 )
              {
                v14 = *(PVOID **)(v5 + 8 * v4);
                if ( v14 )
                {
                  if ( *v14 )
                    DataBlock_Free(*v14);
                  BCryptFree(*(PVOID *)(v5 + 8 * v4));
                }
                *(_QWORD *)(v5 + 8 * v4) = 0;
              }
            }
            else
            {
              *(_DWORD *)(v12 + 8) = 0;
            }
          }
        }
LABEL_24:
        if ( Handle )
          KeRegCloseKey(Handle);
        if ( v2 )
          goto LABEL_28;
        goto LABEL_27;
      }
      v11 = *(_QWORD *)(v5 + 8 * v4);
      if ( *(_DWORD *)(v11 + 8) == 2 )
      {
        v2 = 0;
        goto LABEL_24;
      }
      v10 = KeRegCreateKey(v6, **(const WCHAR ***)v11, v9, &Handle);
    }
    v2 = v10;
    goto LABEL_14;
  }
LABEL_28:
  if ( v17 )
    KeRegCloseKey(v17);
  return v2;
}

```

## disassembly

```asm
0x1800731fc  mov     [rsp-28h+arg_0], rbx
0x180073201  mov     [rsp-28h+arg_18], rsi
0x180073206  push    rbp
0x180073207  push    rdi
0x180073208  push    r12
0x18007320a  push    r14
0x18007320c  push    r15
0x18007320e  mov     rbp, rsp
0x180073211  sub     rsp, 20h
0x180073215  mov     rsi, rcx
0x180073218  mov     [rbp+arg_10], 0
0x180073220  mov     rdi, 0FFFFFFFF80000002h
0x180073227  lea     r9, [rbp+arg_10]
0x18007322b  mov     rcx, rdi
0x18007322e  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Cry"...
0x180073235  mov     r8d, 3001Fh
0x18007323b  call    KeRegOpenKey
0x180073240  mov     ebx, eax
0x180073242  cmp     eax, 5
0x180073245  jnz     short loc_180073262
0x180073247  lea     r9, [rbp+arg_10]
0x18007324b  mov     r8d, 20019h
0x180073251  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Cry"...
0x180073258  mov     rcx, rdi
0x18007325b  call    KeRegOpenKey
0x180073260  mov     ebx, eax
0x180073262  test    ebx, ebx
0x180073264  jnz     loc_1800733A9
0x18007326a  mov     r12d, [rsi+68h]
0x18007326e  xor     r14d, r14d
0x180073271  mov     rsi, [rsi+70h]
0x180073275  mov     r15, [rbp+arg_10]
0x180073279  cmp     r14d, r12d
0x18007327c  jnb     loc_1800733A9
0x180073282  mov     rdx, [rsi+r14*8]
0x180073286  test    rdx, rdx
0x180073289  jz      loc_1800733A1
0x18007328f  mov     [rbp+Handle], 0
0x180073297  lea     r9, [rbp+Handle]
0x18007329b  mov     rdx, [rdx]
0x18007329e  mov     r8d, 3001Fh
0x1800732a4  mov     rcx, r15
0x1800732a7  mov     rdx, [rdx]
0x1800732aa  call    KeRegOpenKey
0x1800732af  mov     ebx, eax
0x1800732b1  cmp     eax, 5
0x1800732b4  jnz     short loc_1800732D4
0x1800732b6  mov     rax, [rsi+r14*8]
0x1800732ba  lea     r9, [rbp+Handle]
0x1800732be  mov     r8d, 20019h
0x1800732c4  mov     rcx, r15
0x1800732c7  mov     rdx, [rax]
0x1800732ca  mov     rdx, [rdx]
0x1800732cd  call    KeRegOpenKey
0x1800732d2  jmp     short loc_1800732FB
0x1800732d4  cmp     eax, 2
0x1800732d7  jnz     short loc_1800732FD
0x1800732d9  mov     rdx, [rsi+r14*8]
0x1800732dd  cmp     [rdx+8], eax
0x1800732e0  jnz     short loc_1800732E9
0x1800732e2  xor     ebx, ebx
0x1800732e4  jmp     loc_18007338F
0x1800732e9  mov     rdx, [rdx]
0x1800732ec  lea     r9, [rbp+Handle]
0x1800732f0  mov     rcx, r15
0x1800732f3  mov     rdx, [rdx]
0x1800732f6  call    KeRegCreateKey
0x1800732fb  mov     ebx, eax
0x1800732fd  test    ebx, ebx
0x1800732ff  jnz     loc_18007338F
0x180073305  mov     r8, [rsi+r14*8]
0x180073309  mov     edx, ebx
0x18007330b  mov     rcx, [rbp+Handle]
0x18007330f  mov     eax, [r8+8]
0x180073313  dec     eax
0x180073315  test    eax, 0FFFFFFFDh
0x18007331a  setz    dl
0x18007331d  call    _CfgReg_OnSaveTableNode
0x180073322  mov     ebx, eax
0x180073324  test    eax, eax
0x180073326  jnz     short loc_18007338F
0x180073328  mov     rax, [rsi+r14*8]
0x18007332c  cmp     dword ptr [rax+8], 2
0x180073330  jnz     short loc_180073388
0x180073332  mov     rcx, [rbp+Handle]; Handle
0x180073336  call    KeRegCloseKey
0x18007333b  mov     rax, [rsi+r14*8]
0x18007333f  lea     r8d, [rbx+40h]
0x180073343  mov     [rbp+Handle], 0
0x18007334b  mov     rcx, r15
0x18007334e  mov     rdx, [rax]
0x180073351  mov     rdx, [rdx]
0x180073354  call    KeRegDeleteKeyRecursive
0x180073359  mov     ebx, eax
0x18007335b  test    eax, eax
0x18007335d  jnz     short loc_18007338F
0x18007335f  mov     rax, [rsi+r14*8]
0x180073363  test    rax, rax
0x180073366  jz      short loc_18007337E
0x180073368  mov     rcx, [rax]; P
0x18007336b  test    rcx, rcx
0x18007336e  jz      short loc_180073375
0x180073370  call    DataBlock_Free
0x180073375  mov     rcx, [rsi+r14*8]; P
0x180073379  call    BCryptFree
0x18007337e  mov     qword ptr [rsi+r14*8], 0
0x180073386  jmp     short loc_18007338F
0x180073388  mov     dword ptr [rax+8], 0
0x18007338f  mov     rcx, [rbp+Handle]; Handle
0x180073393  test    rcx, rcx
0x180073396  jz      short loc_18007339D
0x180073398  call    KeRegCloseKey
0x18007339d  test    ebx, ebx
0x18007339f  jnz     short loc_1800733A9
0x1800733a1  inc     r14d
0x1800733a4  jmp     loc_180073279
0x1800733a9  mov     rcx, [rbp+arg_10]; Handle
0x1800733ad  test    rcx, rcx
0x1800733b0  jz      short loc_1800733B7
0x1800733b2  call    KeRegCloseKey
0x1800733b7  mov     rsi, [rsp+20h+arg_18]
0x1800733bc  mov     eax, ebx
0x1800733be  mov     rbx, [rsp+20h+arg_0]
0x1800733c3  add     rsp, 20h
0x1800733c7  pop     r15
0x1800733c9  pop     r14
0x1800733cb  pop     r12
0x1800733cd  pop     rdi
0x1800733ce  pop     rbp
0x1800733cf  retn
```
