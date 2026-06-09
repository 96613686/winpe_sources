# LoadIconFromHGlobal

- ea: `0x180007420`
- end: `0x1800074cc`
- name: `LoadIconFromHGlobal`
- size: `172`
- prototype: `__int64 __fastcall(void *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800074d4`

## callees

- `0x180007420`
- `0x1800079e0`
- `0x180007aac`
- `0x180007b88`
- `0x18000b010`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x18000743d`
- `ole32!CreateStreamOnHGlobal` at `0x18000743d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LoadIconFromHGlobal(void *a1, _QWORD *a2)
{
  HRESULT v3; // ebx
  __int64 v5; // rax
  __int64 v6; // rbx
  LPSTREAM ppstm; // [rsp+40h] [rbp+18h] BYREF

  ppstm = 0;
  v3 = CreateStreamOnHGlobal(a1, 0, &ppstm);
  if ( v3 >= 0 )
  {
    v5 = IsolationAwareImageList_Read(ppstm);
    v6 = v5;
    if ( v5 )
    {
      *a2 = IsolationAwareImageList_GetIcon(v5);
      IsolationAwareImageList_Destroy(v6);
      if ( ppstm )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      return 0;
    }
    else
    {
      if ( ppstm )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      return 2147500037LL;
    }
  }
  else
  {
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x180007420  mov     [rsp+arg_0], rbx
0x180007425  push    rdi
0x180007426  sub     rsp, 20h
0x18000742a  mov     rdi, rdx
0x18000742d  mov     [rsp+28h+ppstm], 0
0x180007436  lea     r8, [rsp+28h+ppstm]; ppstm
0x18000743b  xor     edx, edx; fDeleteOnRelease
0x18000743d  call    cs:__imp_CreateStreamOnHGlobal
0x180007443  mov     ebx, eax
0x180007445  test    eax, eax
0x180007447  jns     short loc_180007464
0x180007449  mov     rcx, [rsp+28h+ppstm]
0x18000744e  test    rcx, rcx
0x180007451  jz      short loc_180007460
0x180007453  mov     rdx, [rcx]
0x180007456  mov     rax, [rdx+10h]
0x18000745a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000745f  nop
0x180007460  mov     eax, ebx
0x180007462  jmp     short loc_1800074C1
0x180007464  mov     rcx, [rsp+28h+ppstm]
0x180007469  call    IsolationAwareImageList_Read
0x18000746e  mov     rbx, rax
0x180007471  test    rax, rax
0x180007474  jnz     short loc_180007494
0x180007476  mov     rcx, [rsp+28h+ppstm]
0x18000747b  test    rcx, rcx
0x18000747e  jz      short loc_18000748D
0x180007480  mov     rax, [rcx]
0x180007483  mov     rax, [rax+10h]
0x180007487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000748c  nop
0x18000748d  mov     eax, 80004005h
0x180007492  jmp     short loc_1800074C1
0x180007494  mov     rcx, rbx
0x180007497  call    IsolationAwareImageList_GetIcon
0x18000749c  mov     [rdi], rax
0x18000749f  mov     rcx, rbx
0x1800074a2  call    IsolationAwareImageList_Destroy
0x1800074a7  nop
0x1800074a8  mov     rcx, [rsp+28h+ppstm]
0x1800074ad  test    rcx, rcx
0x1800074b0  jz      short loc_1800074BF
0x1800074b2  mov     rax, [rcx]
0x1800074b5  mov     rax, [rax+10h]
0x1800074b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074be  nop
0x1800074bf  xor     eax, eax
0x1800074c1  mov     rbx, [rsp+28h+arg_0]
0x1800074c6  add     rsp, 20h
0x1800074ca  pop     rdi
0x1800074cb  retn
```
