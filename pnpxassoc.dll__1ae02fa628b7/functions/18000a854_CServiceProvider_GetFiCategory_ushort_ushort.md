# CServiceProvider::GetFiCategory(ushort * *,ushort * *)

- ea: `0x18000a854`
- end: `0x18000a9e2`
- name: `?GetFiCategory@CServiceProvider@@IEAAJPEAPEAG0@Z`
- size: `398`
- prototype: `__int64 __fastcall(CServiceProvider *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180009c10`
- `0x18000a480`
- `0x18000b5c0`

## callees

- `0x18000a854`
- `0x18000bce4`
- `0x18000bd30`
- `0x180014010`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x18000a9c8`
- `ole32!CoTaskMemRealloc` at `0x18000a9c8`

## pseudocode

```c
__int64 __fastcall CServiceProvider::GetFiCategory(CServiceProvider *this, LPVOID *a2, unsigned __int16 **a3)
{
  signed int v6; // ebx
  __int64 v7; // rdi
  unsigned int v8; // ebp
  _WORD *v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rcx
  bool v12; // cf

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  v6 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *, unsigned __int16 **))(**((_QWORD **)this + 11) + 56LL))(
         *((_QWORD *)this + 11),
         a2,
         a3);
  if ( v6 != -2147467263 )
    goto LABEL_29;
  v7 = 0;
  v8 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11), a2);
  if ( !v6 )
  {
    v9 = *a2;
    if ( *a2 )
    {
      v10 = 0x7FFFFFFF;
      do
      {
        if ( !*v9 )
          break;
        ++v9;
        --v10;
      }
      while ( v10 );
      v7 = (0x7FFFFFFF - v10) & -(__int64)(v10 != 0);
      v6 = v10 == 0 ? 0x80070057 : 0;
      if ( v10 )
        goto LABEL_14;
    }
    else
    {
      v6 = -2147024809;
    }
    v7 = 0;
  }
LABEL_14:
  if ( v6 >= 0 )
  {
    while ( v8 < (unsigned __int64)(v7 - 1) && (*((_WORD *)*a2 + v8) != 47 || *((_WORD *)*a2 + v8 + 1) != 47) )
      ++v8;
  }
  if ( v6 )
  {
    if ( v6 < 0 )
      goto LABEL_22;
  }
  else if ( v8 >= (unsigned __int64)(v7 - 1) )
  {
    v6 = -2147467259;
    goto LABEL_22;
  }
  *((_WORD *)*a2 + v8) = 0;
  *a2 = CoTaskMemRealloc(*a2, 2LL * (v8 + 1));
LABEL_29:
  if ( !v6 )
  {
    v11 = WPP_GLOBAL_Control;
    v12 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
    goto LABEL_23;
  }
LABEL_22:
  v11 = WPP_GLOBAL_Control;
  v12 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
LABEL_23:
  if ( v11 != &WPP_GLOBAL_Control && !v12 )
    WPP_SF_sqd(v11[2], 38, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000a854  push    rbx
0x18000a856  push    rbp
0x18000a857  push    rsi
0x18000a858  push    rdi
0x18000a859  push    r12
0x18000a85b  push    r14
0x18000a85d  push    r15
0x18000a85f  sub     rsp, 30h
0x18000a863  mov     rbx, r8
0x18000a866  mov     rsi, rdx
0x18000a869  mov     r14, rcx
0x18000a86c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a873  lea     r12, WPP_GLOBAL_Control
0x18000a87a  cmp     rcx, r12
0x18000a87d  jz      short loc_18000A89F
0x18000a87f  cmp     byte ptr [rcx+19h], 4
0x18000a883  jb      short loc_18000A89F
0x18000a885  mov     rcx, [rcx+10h]
0x18000a889  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000a890  mov     edx, 25h ; '%'
0x18000a895  mov     [rsp+68h+var_48], r14
0x18000a89a  call    WPP_SF_sq
0x18000a89f  mov     rcx, [r14+58h]
0x18000a8a3  mov     r8, rbx
0x18000a8a6  mov     rdx, rsi
0x18000a8a9  mov     rax, [rcx]
0x18000a8ac  mov     rax, [rax+38h]
0x18000a8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8b5  xor     r15d, r15d
0x18000a8b8  mov     ebx, eax
0x18000a8ba  cmp     eax, 80004001h
0x18000a8bf  jnz     loc_18000A9D1
0x18000a8c5  mov     rcx, [r14+58h]
0x18000a8c9  mov     rdx, rsi
0x18000a8cc  mov     edi, r15d
0x18000a8cf  mov     ebp, r15d
0x18000a8d2  mov     rax, [rcx]
0x18000a8d5  mov     rax, [rax+20h]
0x18000a8d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8de  mov     ebx, eax
0x18000a8e0  test    eax, eax
0x18000a8e2  jnz     short loc_18000A931
0x18000a8e4  mov     rax, [rsi]
0x18000a8e7  test    rax, rax
0x18000a8ea  jz      short loc_18000A929
0x18000a8ec  mov     edx, 7FFFFFFFh
0x18000a8f1  mov     ecx, edx
0x18000a8f3  cmp     [rax], r15w
0x18000a8f7  jz      short loc_18000A903
0x18000a8f9  add     rax, 2
0x18000a8fd  sub     rcx, 1
0x18000a901  jnz     short loc_18000A8F3
0x18000a903  sub     rdx, rcx
0x18000a906  mov     rax, rcx
0x18000a909  neg     rax
0x18000a90c  mov     rax, rcx
0x18000a90f  sbb     rdi, rdi
0x18000a912  and     rdi, rdx
0x18000a915  neg     rax
0x18000a918  sbb     ebx, ebx
0x18000a91a  not     ebx
0x18000a91c  and     ebx, 80070057h
0x18000a922  test    rcx, rcx
0x18000a925  jz      short loc_18000A92E
0x18000a927  jmp     short loc_18000A931
0x18000a929  mov     ebx, 80070057h
0x18000a92e  mov     rdi, r15
0x18000a931  test    ebx, ebx
0x18000a933  js      short loc_18000A958
0x18000a935  lea     r9, [rdi-1]
0x18000a939  mov     eax, ebp
0x18000a93b  cmp     rax, r9
0x18000a93e  jnb     short loc_18000A958
0x18000a940  mov     rdx, [rsi]
0x18000a943  lea     ecx, [rbp+1]
0x18000a946  cmp     word ptr [rdx+rax*2], 2Fh ; '/'
0x18000a94b  jnz     short loc_18000A954
0x18000a94d  cmp     word ptr [rdx+rcx*2], 2Fh ; '/'
0x18000a952  jz      short loc_18000A958
0x18000a954  mov     ebp, ecx
0x18000a956  jmp     short loc_18000A939
0x18000a958  mov     edx, ebp
0x18000a95a  test    ebx, ebx
0x18000a95c  jnz     short loc_18000A9B5
0x18000a95e  lea     rax, [rdi-1]
0x18000a962  cmp     rdx, rax
0x18000a965  jb      short loc_18000A9B7
0x18000a967  mov     ebx, 80004005h
0x18000a96c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a973  cmp     byte ptr [rcx+19h], 2
0x18000a977  mov     eax, r15d
0x18000a97a  setnb   al
0x18000a97d  cmp     rcx, r12
0x18000a980  jz      short loc_18000A9A4
0x18000a982  test    eax, eax
0x18000a984  jz      short loc_18000A9A4
0x18000a986  mov     rcx, [rcx+10h]
0x18000a98a  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000a991  mov     edx, 26h ; '&'
0x18000a996  mov     [rsp+68h+var_40], ebx
0x18000a99a  mov     [rsp+68h+var_48], r14
0x18000a99f  call    WPP_SF_sqd
0x18000a9a4  mov     eax, ebx
0x18000a9a6  add     rsp, 30h
0x18000a9aa  pop     r15
0x18000a9ac  pop     r14
0x18000a9ae  pop     r12
0x18000a9b0  pop     rdi
0x18000a9b1  pop     rsi
0x18000a9b2  pop     rbp
0x18000a9b3  pop     rbx
0x18000a9b4  retn
0x18000a9b5  js      short loc_18000A96C
0x18000a9b7  mov     rcx, [rsi]
0x18000a9ba  mov     [rcx+rdx*2], r15w
0x18000a9bf  lea     edx, [rbp+1]
0x18000a9c2  mov     rcx, [rsi]; pv
0x18000a9c5  add     rdx, rdx; cb
0x18000a9c8  call    cs:__imp_CoTaskMemRealloc
0x18000a9ce  mov     [rsi], rax
0x18000a9d1  test    ebx, ebx
0x18000a9d3  jnz     short loc_18000A96C
0x18000a9d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9dc  cmp     byte ptr [rcx+19h], 4
0x18000a9e0  jmp     short loc_18000A977
```
