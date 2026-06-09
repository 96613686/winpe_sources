# AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)

- ea: `0x180016930`
- end: `0x180016aec`
- name: `?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z`
- size: `444`
- prototype: `unsigned __int8(struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *, struct _INTERNAL_THREAD *, unsigned __int64, unsigned __int8, unsigned __int8)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180017890`
- `0x1800198b4`
- `0x180019c24`
- `0x180019ea4`

## callees

- `0x180005570`
- `0x1800055f0`
- `0x1800168f0`
- `0x180016930`
- `0x18001f334`
- `0x18002c010`

## pseudocode

```c
char __fastcall AddressReferenced(
        struct _MINIDUMP_STATE *a1,
        struct _INTERNAL_PROCESS *a2,
        struct _INTERNAL_THREAD *a3,
        unsigned __int64 a4,
        int a5)
{
  struct _INTERNAL_PROCESS *i; // rax
  char v10; // di
  __int64 v11; // rcx
  int v12; // edx
  struct _INTERNAL_PROCESS *j; // rax
  unsigned __int64 v15[7]; // [rsp+40h] [rbp-38h] BYREF

  if ( (unsigned int)AddressInModule(a2, a4, 0)
    || AddressInFunctionTable(a2, a4)
    || a3 && a4 >= *((_QWORD *)a3 + 17) && a4 <= *((_QWORD *)a3 + 16) )
  {
    return 1;
  }
  for ( i = (struct _INTERNAL_PROCESS *)*((_QWORD *)a2 + 13);
        i != (struct _INTERNAL_PROCESS *)((char *)a2 + 104);
        i = *(struct _INTERNAL_PROCESS **)i )
  {
    if ( a4 >= *((_QWORD *)i - 6) && a4 <= *((_QWORD *)i - 7) )
    {
      if ( i != (struct _INTERNAL_PROCESS *)184 )
        return 1;
      break;
    }
  }
  if ( AddressIsHandle(a2, a4) )
    return 1;
  v10 = 0;
  if ( a4 >= 0x1000 )
  {
    v11 = *((_QWORD *)a1 + 2);
    v12 = *((_DWORD *)a1 + 39);
    v15[0] = 0;
    a5 = 0;
    if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, unsigned __int64, unsigned __int64 *, int, int *))(*(_QWORD *)v11 + 232LL))(
            v11,
            *(_QWORD *)a1,
            a4,
            v15,
            v12,
            &a5)
      && a5 == *((_DWORD *)a1 + 39) )
    {
      if ( (unsigned int)AddressInModule(a2, v15[0], 0)
        || AddressInFunctionTable(a2, a4)
        || a3 && v15[0] >= *((_QWORD *)a3 + 17) && v15[0] <= *((_QWORD *)a3 + 16) )
      {
LABEL_29:
        v10 = 1;
        GenAddMemoryBlock(a1, (__int64)a2, 9u, 0, a4, *((_DWORD *)a1 + 39));
      }
      else
      {
        for ( j = (struct _INTERNAL_PROCESS *)*((_QWORD *)a2 + 13);
              j != (struct _INTERNAL_PROCESS *)((char *)a2 + 104);
              j = *(struct _INTERNAL_PROCESS **)j )
        {
          if ( v15[0] >= *((_QWORD *)j - 6) && v15[0] <= *((_QWORD *)j - 7) )
          {
            if ( j == (struct _INTERNAL_PROCESS *)184 )
              return v10;
            goto LABEL_29;
          }
        }
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180016930  push    rbx
0x180016932  push    rbp
0x180016933  push    rsi
0x180016934  push    rdi
0x180016935  push    r14
0x180016937  sub     rsp, 50h
0x18001693b  mov     rbp, rdx
0x18001693e  mov     rsi, r8
0x180016941  mov     r14, rcx
0x180016944  xor     r8d, r8d; unsigned __int8
0x180016947  mov     rcx, rbp; struct _INTERNAL_PROCESS *
0x18001694a  mov     rdx, r9; unsigned __int64
0x18001694d  mov     rbx, r9
0x180016950  call    ?AddressInModule@@YAHPEAU_INTERNAL_PROCESS@@_KE@Z; AddressInModule(_INTERNAL_PROCESS *,unsigned __int64,uchar)
0x180016955  test    eax, eax
0x180016957  jnz     loc_180016ADB
0x18001695d  mov     rdx, rbx; unsigned __int64
0x180016960  mov     rcx, rbp; struct _INTERNAL_PROCESS *
0x180016963  call    ?AddressInFunctionTable@@YAPEAU_INTERNAL_FUNCTION_TABLE@@PEAU_INTERNAL_PROCESS@@_K@Z; AddressInFunctionTable(_INTERNAL_PROCESS *,unsigned __int64)
0x180016968  test    rax, rax
0x18001696b  jnz     loc_180016ADB
0x180016971  test    rsi, rsi
0x180016974  jz      short loc_18001698C
0x180016976  cmp     rbx, [rsi+88h]
0x18001697d  jb      short loc_18001698C
0x18001697f  cmp     rbx, [rsi+80h]
0x180016986  jbe     loc_180016ADB
0x18001698c  lea     rdx, [rbp+68h]
0x180016990  mov     rax, [rdx]
0x180016993  jmp     short loc_1800169B1
0x180016995  lea     rcx, [rax-0B8h]
0x18001699c  cmp     rbx, [rcx+88h]
0x1800169a3  jb      short loc_1800169AE
0x1800169a5  cmp     rbx, [rcx+80h]
0x1800169ac  jbe     short loc_1800169B8
0x1800169ae  mov     rax, [rax]
0x1800169b1  cmp     rax, rdx
0x1800169b4  jnz     short loc_180016995
0x1800169b6  jmp     short loc_1800169C1
0x1800169b8  test    rcx, rcx
0x1800169bb  jnz     loc_180016ADB
0x1800169c1  mov     rdx, rbx; unsigned __int64
0x1800169c4  mov     rcx, rbp; struct _INTERNAL_PROCESS *
0x1800169c7  call    ?AddressIsHandle@@YAPEAU_MINIDUMP_HANDLE_DESCRIPTOR_2@@PEAU_INTERNAL_PROCESS@@_K@Z; AddressIsHandle(_INTERNAL_PROCESS *,unsigned __int64)
0x1800169cc  test    rax, rax
0x1800169cf  jnz     loc_180016ADB
0x1800169d5  xor     dil, dil
0x1800169d8  cmp     rbx, 1000h
0x1800169df  jb      loc_180016ADE
0x1800169e5  mov     rcx, [r14+10h]
0x1800169e9  lea     rdx, [rsp+78h+arg_20]
0x1800169f1  mov     [rsp+78h+var_50], rdx
0x1800169f6  lea     r9, [rsp+78h+var_38]
0x1800169fb  mov     edx, [r14+9Ch]
0x180016a02  mov     r8, rbx
0x180016a05  mov     [rsp+78h+var_38], rax
0x180016a0a  mov     [rsp+78h+arg_20], eax
0x180016a11  mov     rax, [rcx]
0x180016a14  mov     dword ptr [rsp+78h+var_58], edx
0x180016a18  mov     rdx, [r14]
0x180016a1b  mov     rax, [rax+0E8h]
0x180016a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a27  test    eax, eax
0x180016a29  jnz     loc_180016ADE
0x180016a2f  mov     eax, [r14+9Ch]
0x180016a36  cmp     [rsp+78h+arg_20], eax
0x180016a3d  jnz     loc_180016ADE
0x180016a43  mov     rdx, [rsp+78h+var_38]; unsigned __int64
0x180016a48  xor     r8d, r8d; unsigned __int8
0x180016a4b  mov     rcx, rbp; struct _INTERNAL_PROCESS *
0x180016a4e  call    ?AddressInModule@@YAHPEAU_INTERNAL_PROCESS@@_KE@Z; AddressInModule(_INTERNAL_PROCESS *,unsigned __int64,uchar)
0x180016a53  test    eax, eax
0x180016a55  jnz     short loc_180016AB4
0x180016a57  mov     rdx, rbx; unsigned __int64
0x180016a5a  mov     rcx, rbp; struct _INTERNAL_PROCESS *
0x180016a5d  call    ?AddressInFunctionTable@@YAPEAU_INTERNAL_FUNCTION_TABLE@@PEAU_INTERNAL_PROCESS@@_K@Z; AddressInFunctionTable(_INTERNAL_PROCESS *,unsigned __int64)
0x180016a62  test    rax, rax
0x180016a65  jnz     short loc_180016AB4
0x180016a67  mov     rcx, [rsp+78h+var_38]
0x180016a6c  test    rsi, rsi
0x180016a6f  jz      short loc_180016A83
0x180016a71  cmp     rcx, [rsi+88h]
0x180016a78  jb      short loc_180016A83
0x180016a7a  cmp     rcx, [rsi+80h]
0x180016a81  jbe     short loc_180016AB4
0x180016a83  lea     r8, [rbp+68h]
0x180016a87  mov     rax, [r8]
0x180016a8a  jmp     short loc_180016AA8
0x180016a8c  lea     rdx, [rax-0B8h]
0x180016a93  cmp     rcx, [rdx+88h]
0x180016a9a  jb      short loc_180016AA5
0x180016a9c  cmp     rcx, [rdx+80h]
0x180016aa3  jbe     short loc_180016AAF
0x180016aa5  mov     rax, [rax]
0x180016aa8  cmp     rax, r8
0x180016aab  jnz     short loc_180016A8C
0x180016aad  jmp     short loc_180016ADE
0x180016aaf  test    rdx, rdx
0x180016ab2  jz      short loc_180016ADE
0x180016ab4  mov     eax, [r14+9Ch]
0x180016abb  xor     r9d, r9d
0x180016abe  mov     dword ptr [rsp+78h+var_50], eax
0x180016ac2  mov     rdx, rbp
0x180016ac5  mov     rcx, r14
0x180016ac8  mov     [rsp+78h+var_58], rbx
0x180016acd  mov     dil, 1
0x180016ad0  lea     r8d, [r9+9]
0x180016ad4  call    ?GenAddMemoryBlock@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@W4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@_KK@Z; GenAddMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE,unsigned __int64,ulong)
0x180016ad9  jmp     short loc_180016ADE
0x180016adb  mov     dil, 1
0x180016ade  mov     al, dil
0x180016ae1  add     rsp, 50h
0x180016ae5  pop     r14
0x180016ae7  pop     rdi
0x180016ae8  pop     rsi
0x180016ae9  pop     rbp
0x180016aea  pop     rbx
0x180016aeb  retn
```
