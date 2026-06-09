# _CfgReg_SaveRoot

- ea: `0x18007d39c`
- end: `0x18007d571`
- name: `_CfgReg_SaveRoot`
- size: `469`
- prototype: ``
- caller_count: `10`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180073ec0`
- `0x1800740f0`
- `0x18007446c`
- `0x180074620`
- `0x18007493c`
- `0x180074bac`
- `0x180075c0c`
- `0x180075e40`
- `0x180076154`
- `0x1800765e0`

## callees

- `0x180025ec0`
- `0x180025f40`
- `0x180040b10`
- `0x180056428`
- `0x18007d1f8`
- `0x18007d39c`
- `0x18007d750`
- `0x18007d8a0`

## string_xrefs

- `0x18007d3ce`: `System\CurrentControlSet\Control\Cryptography\Configuration`
- `0x18007d3f1`: `System\CurrentControlSet\Control\Cryptography\Configuration`

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
0x18007d39c  mov     [rsp-28h+arg_0], rbx
0x18007d3a1  mov     [rsp-28h+arg_18], rsi
0x18007d3a6  push    rbp
0x18007d3a7  push    rdi
0x18007d3a8  push    r12
0x18007d3aa  push    r14
0x18007d3ac  push    r15
0x18007d3ae  mov     rbp, rsp
0x18007d3b1  sub     rsp, 20h
0x18007d3b5  mov     rsi, rcx
0x18007d3b8  mov     [rbp+arg_10], 0
0x18007d3c0  mov     rdi, 0FFFFFFFF80000002h
0x18007d3c7  lea     r9, [rbp+arg_10]
0x18007d3cb  mov     rcx, rdi
0x18007d3ce  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Cry"...
0x18007d3d5  mov     r8d, 3001Fh
0x18007d3db  call    KeRegOpenKey
0x18007d3e0  mov     ebx, eax
0x18007d3e2  cmp     eax, 5
0x18007d3e5  jnz     short loc_18007D402
0x18007d3e7  lea     r9, [rbp+arg_10]
0x18007d3eb  mov     r8d, 20019h
0x18007d3f1  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Cry"...
0x18007d3f8  mov     rcx, rdi
0x18007d3fb  call    KeRegOpenKey
0x18007d400  mov     ebx, eax
0x18007d402  test    ebx, ebx
0x18007d404  jnz     loc_18007D549
0x18007d40a  mov     r12d, [rsi+68h]
0x18007d40e  xor     r14d, r14d
0x18007d411  mov     rsi, [rsi+70h]
0x18007d415  mov     r15, [rbp+arg_10]
0x18007d419  cmp     r14d, r12d
0x18007d41c  jnb     loc_18007D549
0x18007d422  mov     rdx, [rsi+r14*8]
0x18007d426  test    rdx, rdx
0x18007d429  jz      loc_18007D541
0x18007d42f  mov     [rbp+Handle], 0
0x18007d437  lea     r9, [rbp+Handle]
0x18007d43b  mov     rdx, [rdx]
0x18007d43e  mov     r8d, 3001Fh
0x18007d444  mov     rcx, r15
0x18007d447  mov     rdx, [rdx]
0x18007d44a  call    KeRegOpenKey
0x18007d44f  mov     ebx, eax
0x18007d451  cmp     eax, 5
0x18007d454  jnz     short loc_18007D474
0x18007d456  mov     rax, [rsi+r14*8]
0x18007d45a  lea     r9, [rbp+Handle]
0x18007d45e  mov     r8d, 20019h
0x18007d464  mov     rcx, r15
0x18007d467  mov     rdx, [rax]
0x18007d46a  mov     rdx, [rdx]
0x18007d46d  call    KeRegOpenKey
0x18007d472  jmp     short loc_18007D49B
0x18007d474  cmp     eax, 2
0x18007d477  jnz     short loc_18007D49D
0x18007d479  mov     rdx, [rsi+r14*8]
0x18007d47d  cmp     [rdx+8], eax
0x18007d480  jnz     short loc_18007D489
0x18007d482  xor     ebx, ebx
0x18007d484  jmp     loc_18007D52F
0x18007d489  mov     rdx, [rdx]
0x18007d48c  lea     r9, [rbp+Handle]
0x18007d490  mov     rcx, r15
0x18007d493  mov     rdx, [rdx]
0x18007d496  call    KeRegCreateKey
0x18007d49b  mov     ebx, eax
0x18007d49d  test    ebx, ebx
0x18007d49f  jnz     loc_18007D52F
0x18007d4a5  mov     r8, [rsi+r14*8]
0x18007d4a9  mov     edx, ebx
0x18007d4ab  mov     rcx, [rbp+Handle]
0x18007d4af  mov     eax, [r8+8]
0x18007d4b3  dec     eax
0x18007d4b5  test    eax, 0FFFFFFFDh
0x18007d4ba  setz    dl
0x18007d4bd  call    _CfgReg_OnSaveTableNode
0x18007d4c2  mov     ebx, eax
0x18007d4c4  test    eax, eax
0x18007d4c6  jnz     short loc_18007D52F
0x18007d4c8  mov     rax, [rsi+r14*8]
0x18007d4cc  cmp     dword ptr [rax+8], 2
0x18007d4d0  jnz     short loc_18007D528
0x18007d4d2  mov     rcx, [rbp+Handle]; Handle
0x18007d4d6  call    KeRegCloseKey
0x18007d4db  mov     rax, [rsi+r14*8]
0x18007d4df  lea     r8d, [rbx+40h]
0x18007d4e3  mov     [rbp+Handle], 0
0x18007d4eb  mov     rcx, r15
0x18007d4ee  mov     rdx, [rax]
0x18007d4f1  mov     rdx, [rdx]
0x18007d4f4  call    KeRegDeleteKeyRecursive
0x18007d4f9  mov     ebx, eax
0x18007d4fb  test    eax, eax
0x18007d4fd  jnz     short loc_18007D52F
0x18007d4ff  mov     rax, [rsi+r14*8]
0x18007d503  test    rax, rax
0x18007d506  jz      short loc_18007D51E
0x18007d508  mov     rcx, [rax]; P
0x18007d50b  test    rcx, rcx
0x18007d50e  jz      short loc_18007D515
0x18007d510  call    DataBlock_Free
0x18007d515  mov     rcx, [rsi+r14*8]; P
0x18007d519  call    BCryptFree
0x18007d51e  mov     qword ptr [rsi+r14*8], 0
0x18007d526  jmp     short loc_18007D52F
0x18007d528  mov     dword ptr [rax+8], 0
0x18007d52f  mov     rcx, [rbp+Handle]; Handle
0x18007d533  test    rcx, rcx
0x18007d536  jz      short loc_18007D53D
0x18007d538  call    KeRegCloseKey
0x18007d53d  test    ebx, ebx
0x18007d53f  jnz     short loc_18007D549
0x18007d541  inc     r14d
0x18007d544  jmp     loc_18007D419
0x18007d549  mov     rcx, [rbp+arg_10]; Handle
0x18007d54d  test    rcx, rcx
0x18007d550  jz      short loc_18007D557
0x18007d552  call    KeRegCloseKey
0x18007d557  mov     rsi, [rsp+20h+arg_18]
0x18007d55c  mov     eax, ebx
0x18007d55e  mov     rbx, [rsp+20h+arg_0]
0x18007d563  add     rsp, 20h
0x18007d567  pop     r15
0x18007d569  pop     r14
0x18007d56b  pop     r12
0x18007d56d  pop     rdi
0x18007d56e  pop     rbp
0x18007d56f  retn
```
