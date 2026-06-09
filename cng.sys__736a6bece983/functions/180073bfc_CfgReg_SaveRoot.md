# _CfgReg_SaveRoot

- ea: `0x180073bfc`
- end: `0x180073dd1`
- name: `_CfgReg_SaveRoot`
- size: `469`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `10`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18006a720`
- `0x18006a950`
- `0x18006accc`
- `0x18006ae80`
- `0x18006b19c`
- `0x18006b40c`
- `0x18006c46c`
- `0x18006c6a0`
- `0x18006c9b4`
- `0x18006ce40`

## callees

- `0x180018e40`
- `0x180018ec0`
- `0x1800375a0`
- `0x18004cb68`
- `0x180073a58`
- `0x180073bfc`
- `0x180073fb0`
- `0x180074100`

## string_xrefs

- `0x180073c2e`: `System\CurrentControlSet\Control\Cryptography\Configuration`
- `0x180073c51`: `System\CurrentControlSet\Control\Cryptography\Configuration`

## pseudocode

```c
__int64 __fastcall CfgReg_SaveRoot(__int64 a1)
{
  unsigned int v2; // ebx
  unsigned int v3; // r12d
  __int64 v4; // r14
  __int64 v5; // rsi
  HANDLE v6; // r15
  _QWORD **v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rax
  _QWORD **v13; // rax
  PVOID *v14; // rax
  HANDLE Handle; // [rsp+58h] [rbp+38h] BYREF
  HANDLE v17; // [rsp+60h] [rbp+40h] BYREF

  v17 = 0;
  v2 = KeRegOpenKey(-2147483646, L"System\\CurrentControlSet\\Control\\Cryptography\\Configuration", 196639, &v17);
  if ( v2 == 5 )
    v2 = KeRegOpenKey(-2147483646, L"System\\CurrentControlSet\\Control\\Cryptography\\Configuration", 131097, &v17);
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
      v7 = *(_QWORD ***)(v5 + 8 * v4);
      if ( v7 )
        break;
LABEL_27:
      v4 = (unsigned int)(v4 + 1);
    }
    Handle = 0;
    v8 = KeRegOpenKey(v6, **v7, 196639, &Handle);
    v2 = v8;
    if ( v8 == 5 )
    {
      v10 = KeRegOpenKey(v6, ***(_QWORD ***)(v5 + 8 * v4), 131097, &Handle);
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
      v10 = KeRegCreateKey(v6, **(_QWORD **)v11, v9, &Handle);
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
0x180073bfc  mov     [rsp-28h+arg_0], rbx
0x180073c01  mov     [rsp-28h+arg_18], rsi
0x180073c06  push    rbp
0x180073c07  push    rdi
0x180073c08  push    r12
0x180073c0a  push    r14
0x180073c0c  push    r15
0x180073c0e  mov     rbp, rsp
0x180073c11  sub     rsp, 20h
0x180073c15  mov     rsi, rcx
0x180073c18  mov     [rbp+arg_10], 0
0x180073c20  mov     rdi, 0FFFFFFFF80000002h
0x180073c27  lea     r9, [rbp+arg_10]
0x180073c2b  mov     rcx, rdi
0x180073c2e  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Cry"...
0x180073c35  mov     r8d, 3001Fh
0x180073c3b  call    KeRegOpenKey
0x180073c40  mov     ebx, eax
0x180073c42  cmp     eax, 5
0x180073c45  jnz     short loc_180073C62
0x180073c47  lea     r9, [rbp+arg_10]
0x180073c4b  mov     r8d, 20019h
0x180073c51  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Cry"...
0x180073c58  mov     rcx, rdi
0x180073c5b  call    KeRegOpenKey
0x180073c60  mov     ebx, eax
0x180073c62  test    ebx, ebx
0x180073c64  jnz     loc_180073DA9
0x180073c6a  mov     r12d, [rsi+68h]
0x180073c6e  xor     r14d, r14d
0x180073c71  mov     rsi, [rsi+70h]
0x180073c75  mov     r15, [rbp+arg_10]
0x180073c79  cmp     r14d, r12d
0x180073c7c  jnb     loc_180073DA9
0x180073c82  mov     rdx, [rsi+r14*8]
0x180073c86  test    rdx, rdx
0x180073c89  jz      loc_180073DA1
0x180073c8f  mov     [rbp+Handle], 0
0x180073c97  lea     r9, [rbp+Handle]
0x180073c9b  mov     rdx, [rdx]
0x180073c9e  mov     r8d, 3001Fh
0x180073ca4  mov     rcx, r15
0x180073ca7  mov     rdx, [rdx]
0x180073caa  call    KeRegOpenKey
0x180073caf  mov     ebx, eax
0x180073cb1  cmp     eax, 5
0x180073cb4  jnz     short loc_180073CD4
0x180073cb6  mov     rax, [rsi+r14*8]
0x180073cba  lea     r9, [rbp+Handle]
0x180073cbe  mov     r8d, 20019h
0x180073cc4  mov     rcx, r15
0x180073cc7  mov     rdx, [rax]
0x180073cca  mov     rdx, [rdx]
0x180073ccd  call    KeRegOpenKey
0x180073cd2  jmp     short loc_180073CFB
0x180073cd4  cmp     eax, 2
0x180073cd7  jnz     short loc_180073CFD
0x180073cd9  mov     rdx, [rsi+r14*8]
0x180073cdd  cmp     [rdx+8], eax
0x180073ce0  jnz     short loc_180073CE9
0x180073ce2  xor     ebx, ebx
0x180073ce4  jmp     loc_180073D8F
0x180073ce9  mov     rdx, [rdx]
0x180073cec  lea     r9, [rbp+Handle]
0x180073cf0  mov     rcx, r15
0x180073cf3  mov     rdx, [rdx]
0x180073cf6  call    KeRegCreateKey
0x180073cfb  mov     ebx, eax
0x180073cfd  test    ebx, ebx
0x180073cff  jnz     loc_180073D8F
0x180073d05  mov     r8, [rsi+r14*8]
0x180073d09  mov     edx, ebx
0x180073d0b  mov     rcx, [rbp+Handle]
0x180073d0f  mov     eax, [r8+8]
0x180073d13  dec     eax
0x180073d15  test    eax, 0FFFFFFFDh
0x180073d1a  setz    dl
0x180073d1d  call    _CfgReg_OnSaveTableNode
0x180073d22  mov     ebx, eax
0x180073d24  test    eax, eax
0x180073d26  jnz     short loc_180073D8F
0x180073d28  mov     rax, [rsi+r14*8]
0x180073d2c  cmp     dword ptr [rax+8], 2
0x180073d30  jnz     short loc_180073D88
0x180073d32  mov     rcx, [rbp+Handle]; Handle
0x180073d36  call    KeRegCloseKey
0x180073d3b  mov     rax, [rsi+r14*8]
0x180073d3f  lea     r8d, [rbx+40h]
0x180073d43  mov     [rbp+Handle], 0
0x180073d4b  mov     rcx, r15
0x180073d4e  mov     rdx, [rax]
0x180073d51  mov     rdx, [rdx]
0x180073d54  call    KeRegDeleteKeyRecursive
0x180073d59  mov     ebx, eax
0x180073d5b  test    eax, eax
0x180073d5d  jnz     short loc_180073D8F
0x180073d5f  mov     rax, [rsi+r14*8]
0x180073d63  test    rax, rax
0x180073d66  jz      short loc_180073D7E
0x180073d68  mov     rcx, [rax]; P
0x180073d6b  test    rcx, rcx
0x180073d6e  jz      short loc_180073D75
0x180073d70  call    DataBlock_Free
0x180073d75  mov     rcx, [rsi+r14*8]; P
0x180073d79  call    BCryptFree
0x180073d7e  mov     qword ptr [rsi+r14*8], 0
0x180073d86  jmp     short loc_180073D8F
0x180073d88  mov     dword ptr [rax+8], 0
0x180073d8f  mov     rcx, [rbp+Handle]; Handle
0x180073d93  test    rcx, rcx
0x180073d96  jz      short loc_180073D9D
0x180073d98  call    KeRegCloseKey
0x180073d9d  test    ebx, ebx
0x180073d9f  jnz     short loc_180073DA9
0x180073da1  inc     r14d
0x180073da4  jmp     loc_180073C79
0x180073da9  mov     rcx, [rbp+arg_10]; Handle
0x180073dad  test    rcx, rcx
0x180073db0  jz      short loc_180073DB7
0x180073db2  call    KeRegCloseKey
0x180073db7  mov     rsi, [rsp+20h+arg_18]
0x180073dbc  mov     eax, ebx
0x180073dbe  mov     rbx, [rsp+20h+arg_0]
0x180073dc3  add     rsp, 20h
0x180073dc7  pop     r15
0x180073dc9  pop     r14
0x180073dcb  pop     r12
0x180073dcd  pop     rdi
0x180073dce  pop     rbp
0x180073dcf  retn
```
