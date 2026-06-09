# ProvisioningPaths::~ProvisioningPaths(void)

- ea: `0x180033128`
- end: `0x1800332c0`
- name: `??1ProvisioningPaths@@QEAA@XZ`
- size: `408`
- prototype: `void __fastcall(ProvisioningPaths *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180037b50`

## callees

- `0x180033128`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180033247`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003326e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180033294`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180033247`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003326e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180033294`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033152`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033172`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033191`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800331b1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800331d0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800331f0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003320f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003322f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033256`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003327d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800332a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033152`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033172`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033191`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800331b1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800331d0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800331f0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003320f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003322f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033256`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003327d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800332a3`

## pseudocode

```c
void __fastcall ProvisioningPaths::~ProvisioningPaths(ProvisioningPaths *this)
{
  __int64 v1; // rdi
  __int64 v3; // rdi
  __int64 v4; // rdi
  __int64 v5; // rdi
  void **v6; // rdi
  void **v7; // rdi
  void **v8; // rbx

  v1 = *((_QWORD *)this + 6);
  if ( v1 )
  {
    if ( *(_QWORD *)(v1 + 24) >= 8u )
      operator delete(*(void **)v1);
    *(_QWORD *)(v1 + 24) = 7;
    *(_QWORD *)(v1 + 16) = 0;
    *(_WORD *)v1 = 0;
    operator delete((void *)v1);
  }
  v3 = *((_QWORD *)this + 5);
  if ( v3 )
  {
    if ( *(_QWORD *)(v3 + 24) >= 8u )
      operator delete(*(void **)v3);
    *(_QWORD *)(v3 + 24) = 7;
    *(_QWORD *)(v3 + 16) = 0;
    *(_WORD *)v3 = 0;
    operator delete((void *)v3);
  }
  v4 = *((_QWORD *)this + 4);
  if ( v4 )
  {
    if ( *(_QWORD *)(v4 + 24) >= 8u )
      operator delete(*(void **)v4);
    *(_QWORD *)(v4 + 24) = 7;
    *(_QWORD *)(v4 + 16) = 0;
    *(_WORD *)v4 = 0;
    operator delete((void *)v4);
  }
  v5 = *((_QWORD *)this + 3);
  if ( v5 )
  {
    if ( *(_QWORD *)(v5 + 24) >= 8u )
      operator delete(*(void **)v5);
    *(_QWORD *)(v5 + 24) = 7;
    *(_QWORD *)(v5 + 16) = 0;
    *(_WORD *)v5 = 0;
    operator delete((void *)v5);
  }
  v6 = (void **)*((_QWORD *)this + 2);
  if ( v6 )
  {
    operator delete[](*v6);
    operator delete(v6);
  }
  v7 = (void **)*((_QWORD *)this + 1);
  if ( v7 )
  {
    operator delete[](*v7);
    operator delete(v7);
  }
  v8 = *(void ***)this;
  if ( v8 )
  {
    operator delete[](*v8);
    operator delete(v8);
  }
}

```

## disassembly

```asm
0x180033128  mov     [rsp+arg_0], rbx
0x18003312d  mov     [rsp+arg_8], rbp
0x180033132  push    rdi
0x180033133  sub     rsp, 20h
0x180033137  mov     rdi, [rcx+30h]
0x18003313b  mov     rbx, rcx
0x18003313e  mov     ebp, 7
0x180033143  test    rdi, rdi
0x180033146  jz      short loc_18003317E
0x180033148  cmp     qword ptr [rdi+18h], 8
0x18003314d  jb      short loc_18003315E
0x18003314f  mov     rcx, [rdi]
0x180033152  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033159  nop     dword ptr [rax+rax+00h]
0x18003315e  xor     eax, eax
0x180033160  mov     [rdi+18h], rbp
0x180033164  mov     qword ptr [rdi+10h], 0
0x18003316c  mov     rcx, rdi
0x18003316f  mov     [rdi], ax
0x180033172  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033179  nop     dword ptr [rax+rax+00h]
0x18003317e  mov     rdi, [rbx+28h]
0x180033182  test    rdi, rdi
0x180033185  jz      short loc_1800331BD
0x180033187  cmp     qword ptr [rdi+18h], 8
0x18003318c  jb      short loc_18003319D
0x18003318e  mov     rcx, [rdi]
0x180033191  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033198  nop     dword ptr [rax+rax+00h]
0x18003319d  xor     eax, eax
0x18003319f  mov     [rdi+18h], rbp
0x1800331a3  mov     qword ptr [rdi+10h], 0
0x1800331ab  mov     rcx, rdi
0x1800331ae  mov     [rdi], ax
0x1800331b1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800331b8  nop     dword ptr [rax+rax+00h]
0x1800331bd  mov     rdi, [rbx+20h]
0x1800331c1  test    rdi, rdi
0x1800331c4  jz      short loc_1800331FC
0x1800331c6  cmp     qword ptr [rdi+18h], 8
0x1800331cb  jb      short loc_1800331DC
0x1800331cd  mov     rcx, [rdi]
0x1800331d0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800331d7  nop     dword ptr [rax+rax+00h]
0x1800331dc  xor     eax, eax
0x1800331de  mov     [rdi+18h], rbp
0x1800331e2  mov     qword ptr [rdi+10h], 0
0x1800331ea  mov     rcx, rdi
0x1800331ed  mov     [rdi], ax
0x1800331f0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800331f7  nop     dword ptr [rax+rax+00h]
0x1800331fc  mov     rdi, [rbx+18h]
0x180033200  test    rdi, rdi
0x180033203  jz      short loc_18003323B
0x180033205  cmp     qword ptr [rdi+18h], 8
0x18003320a  jb      short loc_18003321B
0x18003320c  mov     rcx, [rdi]
0x18003320f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033216  nop     dword ptr [rax+rax+00h]
0x18003321b  xor     eax, eax
0x18003321d  mov     [rdi+18h], rbp
0x180033221  mov     qword ptr [rdi+10h], 0
0x180033229  mov     rcx, rdi
0x18003322c  mov     [rdi], ax
0x18003322f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033236  nop     dword ptr [rax+rax+00h]
0x18003323b  mov     rdi, [rbx+10h]
0x18003323f  test    rdi, rdi
0x180033242  jz      short loc_180033262
0x180033244  mov     rcx, [rdi]
0x180033247  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003324e  nop     dword ptr [rax+rax+00h]
0x180033253  mov     rcx, rdi
0x180033256  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003325d  nop     dword ptr [rax+rax+00h]
0x180033262  mov     rdi, [rbx+8]
0x180033266  test    rdi, rdi
0x180033269  jz      short loc_180033289
0x18003326b  mov     rcx, [rdi]
0x18003326e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180033275  nop     dword ptr [rax+rax+00h]
0x18003327a  mov     rcx, rdi
0x18003327d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033284  nop     dword ptr [rax+rax+00h]
0x180033289  mov     rbx, [rbx]
0x18003328c  test    rbx, rbx
0x18003328f  jz      short loc_1800332AF
0x180033291  mov     rcx, [rbx]
0x180033294  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003329b  nop     dword ptr [rax+rax+00h]
0x1800332a0  mov     rcx, rbx
0x1800332a3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800332aa  nop     dword ptr [rax+rax+00h]
0x1800332af  mov     rbx, [rsp+28h+arg_0]
0x1800332b4  mov     rbp, [rsp+28h+arg_8]
0x1800332b9  add     rsp, 20h
0x1800332bd  pop     rdi
0x1800332be  retn
```
