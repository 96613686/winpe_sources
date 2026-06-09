# _Deletegloballocale

- ea: `0x140002780`
- end: `0x1400027ea`
- name: `_Deletegloballocale`
- size: `106`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140002840`

## callees

- `0x140002298`
- `0x140002310`
- `0x140002780`
- `0x140020010`

## pseudocode

```c
void __fastcall Deletegloballocale(__int64 *a1)
{
  __int64 v1; // rbx
  __int64 v2; // rax
  void (__fastcall ***v3)(_QWORD, __int64); // rdi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v1 = *a1;
  if ( *a1 )
  {
    std::_Lockit::_Lockit((std::_Lockit *)&v4, 0);
    v2 = *(_QWORD *)(v1 + 8);
    if ( v2 && v2 != -1 )
      *(_QWORD *)(v1 + 8) = --v2;
    v3 = 0;
    if ( !v2 )
      v3 = (void (__fastcall ***)(_QWORD, __int64))v1;
    std::_Lockit::~_Lockit((std::_Lockit *)&v4);
    if ( v3 )
      (**v3)(v3, 1);
  }
}

```

## disassembly

```asm
0x140002780  mov     [rsp+arg_8], rbx
0x140002785  push    rdi
0x140002786  sub     rsp, 20h
0x14000278a  mov     rbx, [rcx]
0x14000278d  test    rbx, rbx
0x140002790  jz      short loc_1400027DF
0x140002792  xor     edx, edx; int
0x140002794  lea     rcx, [rsp+28h+arg_0]; this
0x140002799  call    ??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x14000279e  mov     rax, [rbx+8]
0x1400027a2  test    rax, rax
0x1400027a5  jz      short loc_1400027B4
0x1400027a7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400027ab  jnb     short loc_1400027B4
0x1400027ad  dec     rax
0x1400027b0  mov     [rbx+8], rax
0x1400027b4  xor     edi, edi
0x1400027b6  lea     rcx, [rsp+28h+arg_0]; this
0x1400027bb  test    rax, rax
0x1400027be  cmovz   rdi, rbx
0x1400027c2  call    ??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x1400027c7  test    rdi, rdi
0x1400027ca  jz      short loc_1400027DF
0x1400027cc  mov     rax, [rdi]
0x1400027cf  mov     edx, 1
0x1400027d4  mov     rcx, rdi
0x1400027d7  mov     rax, [rax]
0x1400027da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027df  mov     rbx, [rsp+28h+arg_8]
0x1400027e4  add     rsp, 20h
0x1400027e8  pop     rdi
0x1400027e9  retn
```
