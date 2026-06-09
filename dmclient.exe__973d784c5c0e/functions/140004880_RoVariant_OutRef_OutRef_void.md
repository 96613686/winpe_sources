# RoVariant::OutRef::~OutRef(void)

- ea: `0x140004880`
- end: `0x140004937`
- name: `??1OutRef@RoVariant@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(RoVariant::OutRef *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140005bd4`
- `0x1400081c4`
- `0x1400198cb`
- `0x140019937`

## callees

- `0x140004880`
- `0x14001a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RoVariant::OutRef::~OutRef(RoVariant::OutRef *this)
{
  __int64 *v1; // r14
  __int64 v2; // rbx
  __int64 v3; // rsi
  int v4; // edi
  int v5; // eax
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(__int64 **)this;
  v2 = *((_QWORD *)this + 1);
  if ( v2 )
  {
    v8 = 0;
    v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v2)(
           v2,
           &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
           &v8);
    v4 = v5;
    if ( v5 < 0 )
    {
      if ( v5 == -2147467262 )
      {
        v3 = v2;
        v4 = 3;
      }
      else
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
        v3 = 0;
      }
    }
    else
    {
      v3 = v8;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
      v4 = 7;
    }
  }
  else
  {
    v3 = 0;
    v4 = 0;
  }
  v6 = *v1;
  *v1 = v3;
  v7 = *((_DWORD *)v1 + 2);
  *((_DWORD *)v1 + 2) = v4;
  if ( v6 )
  {
    if ( ((v7 - 3) & 0xFFFFFFFB) == 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
}

```

## disassembly

```asm
0x140004880  push    rbx
0x140004882  push    rsi
0x140004883  push    rdi
0x140004884  push    r14
0x140004886  sub     rsp, 28h
0x14000488a  mov     r14, [rcx]
0x14000488d  mov     rbx, [rcx+8]
0x140004891  test    rbx, rbx
0x140004894  jnz     short loc_14000489C
0x140004896  xor     esi, esi
0x140004898  xor     edi, edi
0x14000489a  jmp     short loc_140004902
0x14000489c  mov     [rsp+48h+arg_0], 0
0x1400048a5  mov     rax, [rbx]
0x1400048a8  lea     r8, [rsp+48h+arg_0]
0x1400048ad  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1400048b4  mov     rcx, rbx
0x1400048b7  mov     rax, [rax]
0x1400048ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048bf  mov     edi, eax
0x1400048c1  test    eax, eax
0x1400048c3  js      short loc_1400048E0
0x1400048c5  mov     rsi, [rsp+48h+arg_0]
0x1400048ca  mov     rax, [rbx]
0x1400048cd  mov     rcx, rbx
0x1400048d0  mov     rax, [rax+10h]
0x1400048d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048d9  mov     edi, 7
0x1400048de  jmp     short loc_140004902
0x1400048e0  cmp     eax, 80004002h
0x1400048e5  jnz     short loc_1400048F1
0x1400048e7  mov     rsi, rbx
0x1400048ea  mov     edi, 3
0x1400048ef  jmp     short loc_140004902
0x1400048f1  mov     rax, [rbx]
0x1400048f4  mov     rcx, rbx
0x1400048f7  mov     rax, [rax+10h]
0x1400048fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004900  xor     esi, esi
0x140004902  mov     rcx, [r14]
0x140004905  mov     [r14], rsi
0x140004908  mov     eax, [r14+8]
0x14000490c  mov     [r14+8], edi
0x140004910  test    rcx, rcx
0x140004913  jz      short loc_14000492C
0x140004915  add     eax, 0FFFFFFFDh
0x140004918  test    eax, 0FFFFFFFBh
0x14000491d  jnz     short loc_14000492C
0x14000491f  mov     rax, [rcx]
0x140004922  mov     rax, [rax+10h]
0x140004926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000492b  nop
0x14000492c  add     rsp, 28h
0x140004930  pop     r14
0x140004932  pop     rdi
0x140004933  pop     rsi
0x140004934  pop     rbx
0x140004935  retn
```
