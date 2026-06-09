# Dfdll::CInterfacePointer<IUnknown>::Attach(IUnknown *,bool)

- ea: `0x1800093b0`
- end: `0x18000945e`
- name: `?Attach@?$CInterfacePointer@UIUnknown@@@Dfdll@@QEAAJPEAUIUnknown@@_N@Z`
- size: `174`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d9b8`
- `0x18000dadc`
- `0x180010bf4`

## callees

- `0x1800093b0`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CInterfacePointer<IUnknown>::Attach(_QWORD *a1, __int64 a2, char a3)
{
  _QWORD *v3; // rsi
  __int64 v5; // rcx
  __int64 (__fastcall **v8)(__int64, __int64, _QWORD *); // rbx
  __int64 v9; // rax
  int v10; // ebx

  v3 = a1 + 1;
  v5 = a1[1];
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  *v3 = 0;
  if ( !a2 )
    return 2147500035LL;
  v8 = *(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))a2;
  v9 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 40LL))(a1);
  v10 = (*v8)(a2, v9, v3);
  if ( v10 >= 0 )
  {
    if ( a3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
  }
  else
  {
    *v3 = 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800093b0  mov     rax, rsp
0x1800093b3  mov     [rax+8], rbx
0x1800093b7  mov     [rax+10h], rbp
0x1800093bb  mov     [rax+18h], rsi
0x1800093bf  mov     [rax+20h], rdi
0x1800093c3  push    r14
0x1800093c5  sub     rsp, 20h
0x1800093c9  lea     rsi, [rcx+8]
0x1800093cd  mov     r14, rcx
0x1800093d0  mov     rcx, [rsi]
0x1800093d3  mov     bpl, r8b
0x1800093d6  mov     rdi, rdx
0x1800093d9  test    rcx, rcx
0x1800093dc  jz      short loc_1800093EB
0x1800093de  mov     rax, [rcx]
0x1800093e1  mov     rax, [rax+10h]
0x1800093e5  call    cs:__guard_dispatch_icall_fptr
0x1800093eb  and     qword ptr [rsi], 0
0x1800093ef  test    rdi, rdi
0x1800093f2  jz      short loc_18000943E
0x1800093f4  mov     rax, [r14]
0x1800093f7  mov     rcx, r14
0x1800093fa  mov     rbx, [rdi]
0x1800093fd  mov     rax, [rax+28h]
0x180009401  call    cs:__guard_dispatch_icall_fptr
0x180009407  mov     r8, rsi
0x18000940a  mov     rcx, rdi
0x18000940d  mov     rdx, rax
0x180009410  mov     rax, [rbx]
0x180009413  call    cs:__guard_dispatch_icall_fptr
0x180009419  mov     ebx, eax
0x18000941b  test    eax, eax
0x18000941d  jns     short loc_180009425
0x18000941f  and     qword ptr [rsi], 0
0x180009423  jmp     short loc_18000943A
0x180009425  test    bpl, bpl
0x180009428  jz      short loc_18000943A
0x18000942a  mov     rax, [rdi]
0x18000942d  mov     rcx, rdi
0x180009430  mov     rax, [rax+10h]
0x180009434  call    cs:__guard_dispatch_icall_fptr
0x18000943a  mov     eax, ebx
0x18000943c  jmp     short loc_180009443
0x18000943e  mov     eax, 80004003h
0x180009443  mov     rbx, [rsp+28h+arg_0]
0x180009448  mov     rbp, [rsp+28h+arg_8]
0x18000944d  mov     rsi, [rsp+28h+arg_10]
0x180009452  mov     rdi, [rsp+28h+arg_18]
0x180009457  add     rsp, 20h
0x18000945b  pop     r14
0x18000945d  retn
```
