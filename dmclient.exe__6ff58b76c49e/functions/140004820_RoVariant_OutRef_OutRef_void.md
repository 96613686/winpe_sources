# RoVariant::OutRef::~OutRef(void)

- ea: `0x140004820`
- end: `0x1400048d6`
- name: `??1OutRef@RoVariant@@QEAA@XZ`
- size: `182`
- prototype: `void __fastcall(RoVariant::OutRef *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140005b34`
- `0x140007ff8`
- `0x140018a9a`
- `0x140018b06`

## callees

- `0x140004820`
- `0x140019010`

## pseudocode

```c
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
0x140004820  push    rbx
0x140004822  push    rsi
0x140004823  push    rdi
0x140004824  push    r14
0x140004826  sub     rsp, 28h
0x14000482a  mov     r14, [rcx]
0x14000482d  mov     rbx, [rcx+8]
0x140004831  test    rbx, rbx
0x140004834  jnz     short loc_14000483C
0x140004836  xor     esi, esi
0x140004838  xor     edi, edi
0x14000483a  jmp     short loc_1400048A2
0x14000483c  mov     [rsp+48h+arg_0], 0
0x140004845  mov     rax, [rbx]
0x140004848  lea     r8, [rsp+48h+arg_0]
0x14000484d  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x140004854  mov     rcx, rbx
0x140004857  mov     rax, [rax]
0x14000485a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000485f  mov     edi, eax
0x140004861  test    eax, eax
0x140004863  js      short loc_140004880
0x140004865  mov     rsi, [rsp+48h+arg_0]
0x14000486a  mov     rax, [rbx]
0x14000486d  mov     rcx, rbx
0x140004870  mov     rax, [rax+10h]
0x140004874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004879  mov     edi, 7
0x14000487e  jmp     short loc_1400048A2
0x140004880  cmp     eax, 80004002h
0x140004885  jnz     short loc_140004891
0x140004887  mov     rsi, rbx
0x14000488a  mov     edi, 3
0x14000488f  jmp     short loc_1400048A2
0x140004891  mov     rax, [rbx]
0x140004894  mov     rcx, rbx
0x140004897  mov     rax, [rax+10h]
0x14000489b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048a0  xor     esi, esi
0x1400048a2  mov     rcx, [r14]
0x1400048a5  mov     [r14], rsi
0x1400048a8  mov     eax, [r14+8]
0x1400048ac  mov     [r14+8], edi
0x1400048b0  test    rcx, rcx
0x1400048b3  jz      short loc_1400048CC
0x1400048b5  add     eax, 0FFFFFFFDh
0x1400048b8  test    eax, 0FFFFFFFBh
0x1400048bd  jnz     short loc_1400048CC
0x1400048bf  mov     rax, [rcx]
0x1400048c2  mov     rax, [rax+10h]
0x1400048c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048cb  nop
0x1400048cc  add     rsp, 28h
0x1400048d0  pop     r14
0x1400048d2  pop     rdi
0x1400048d3  pop     rsi
0x1400048d4  pop     rbx
0x1400048d5  retn
```
