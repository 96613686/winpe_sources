# CNamespaceRecord::Delete(void)

- ea: `0x180007f98`
- end: `0x180008013`
- name: `?Delete@CNamespaceRecord@@QEAAJXZ`
- size: `123`
- prototype: `__int64 __fastcall(CNamespaceRecord *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180010914`
- `0x180010de8`
- `0x180018778`

## callees

- `0x180007f98`
- `0x18000935c`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CNamespaceRecord::Delete(CNamespaceRecord *this)
{
  int v2; // edi

  v2 = 0;
  if ( *((_DWORD *)this + 4) != -1 )
  {
    v2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 128LL))(*(_QWORD *)this);
    if ( v2 >= 0 )
    {
      *((_DWORD *)this + 4) = -1;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids,
        *((unsigned int *)this + 4),
        v2);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180007f98  mov     [rsp+arg_0], rbx
0x180007f9d  push    rdi
0x180007f9e  sub     rsp, 30h
0x180007fa2  mov     rbx, rcx
0x180007fa5  xor     edi, edi
0x180007fa7  mov     edx, [rcx+10h]
0x180007faa  cmp     edx, 0FFFFFFFFh
0x180007fad  jz      short loc_180008006
0x180007faf  mov     rcx, [rcx]
0x180007fb2  mov     rax, [rcx]
0x180007fb5  mov     rax, [rax+80h]
0x180007fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fc1  mov     edi, eax
0x180007fc3  test    eax, eax
0x180007fc5  jns     short loc_180007FFF
0x180007fc7  lea     rax, WPP_GLOBAL_Control
0x180007fce  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fd5  cmp     rcx, rax
0x180007fd8  jz      short loc_180008006
0x180007fda  test    byte ptr [rcx+1Ch], 1
0x180007fde  jz      short loc_180008006
0x180007fe0  mov     edx, 1Ah
0x180007fe5  mov     [rsp+38h+var_18], edi
0x180007fe9  mov     r9d, [rbx+10h]
0x180007fed  lea     r8, WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids
0x180007ff4  mov     rcx, [rcx+10h]
0x180007ff8  call    WPP_SF_dd
0x180007ffd  jmp     short loc_180008006
0x180007fff  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x180008006  mov     eax, edi
0x180008008  mov     rbx, [rsp+38h+arg_0]
0x18000800d  add     rsp, 30h
0x180008011  pop     rdi
0x180008012  retn
```
