# CDocInfo::~CDocInfo(void)

- ea: `0x18008a1b4`
- end: `0x18008a314`
- name: `??1CDocInfo@@QEAA@XZ`
- size: `352`
- prototype: `void __fastcall(CDocInfo *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18010c83c`

## callees

- `0x180043e7c`
- `0x18008a1b4`
- `0x18008a47c`
- `0x18008a498`
- `0x18013d250`
- `0x18027f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008a1de`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008a1ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008a1fe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008a211`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008a1de`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008a1ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008a1fe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008a211`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a2aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a2aa`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18008a2df`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18008a2df`

## pseudocode

```c
void __fastcall CDocInfo::~CDocInfo(CDocInfo *this)
{
  unsigned __int16 *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  void *v8; // rdi
  _QWORD *v9; // rcx

  v2 = *(unsigned __int16 **)this;
  if ( v2 )
    CW32System::SysFreeString(v2);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
    CloseHandle(v3);
  free(*((void **)this + 4));
  free(*((void **)this + 5));
  free(*((void **)this + 6));
  free(*((void **)this + 31));
  v4 = *((_QWORD *)this + 35);
  if ( v4 && !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4) )
    *((_QWORD *)this + 35) = 0;
  v5 = (void *)*((_QWORD *)this + 12);
  if ( v5 )
    DeleteObject(v5);
  v6 = *((_QWORD *)this + 13);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  CW32System::GlobalFree(*((void **)this + 11));
  v7 = *((_QWORD *)this + 7);
  if ( v7 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 216LL))(v7, 1);
  v8 = (void *)*((_QWORD *)this + 1);
  if ( v8 )
  {
    CTxtStories::~CTxtStories(*((CTxtStories **)this + 1));
    operator delete(v8, 0x28u);
  }
  v9 = (_QWORD *)*((_QWORD *)this + 10);
  if ( v9 )
  {
    *v9 = 0;
    operator delete(v9, 0x18u);
  }
}

```

## disassembly

```asm
0x18008a1b4  mov     [rsp+arg_0], rbx
0x18008a1b9  push    rdi
0x18008a1ba  sub     rsp, 20h
0x18008a1be  mov     rbx, rcx
0x18008a1c1  mov     rcx, [rcx]; unsigned __int16 *
0x18008a1c4  test    rcx, rcx
0x18008a1c7  jnz     loc_18008A2A0
0x18008a1cd  mov     rcx, [rbx+18h]; hObject
0x18008a1d1  test    rcx, rcx
0x18008a1d4  jnz     loc_18008A2AA
0x18008a1da  mov     rcx, [rbx+20h]; Block
0x18008a1de  call    cs:__imp_free
0x18008a1e5  nop     dword ptr [rax+rax+00h]
0x18008a1ea  mov     rcx, [rbx+28h]; Block
0x18008a1ee  call    cs:__imp_free
0x18008a1f5  nop     dword ptr [rax+rax+00h]
0x18008a1fa  mov     rcx, [rbx+30h]; Block
0x18008a1fe  call    cs:__imp_free
0x18008a205  nop     dword ptr [rax+rax+00h]
0x18008a20a  mov     rcx, [rbx+0F8h]; Block
0x18008a211  call    cs:__imp_free
0x18008a218  nop     dword ptr [rax+rax+00h]
0x18008a21d  mov     rcx, [rbx+118h]
0x18008a224  test    rcx, rcx
0x18008a227  jnz     loc_18008A2BB
0x18008a22d  mov     rcx, [rbx+60h]; ho
0x18008a231  test    rcx, rcx
0x18008a234  jnz     loc_18008A2DF
0x18008a23a  mov     rcx, [rbx+68h]
0x18008a23e  test    rcx, rcx
0x18008a241  jnz     loc_18008A2F0
0x18008a247  mov     rcx, [rbx+58h]; void *
0x18008a24b  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18008a250  mov     rcx, [rbx+38h]
0x18008a254  test    rcx, rcx
0x18008a257  jz      short loc_18008A26D
0x18008a259  mov     rax, [rcx]
0x18008a25c  mov     edx, 1
0x18008a261  mov     rax, [rax+0D8h]
0x18008a268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a26d  mov     rdi, [rbx+8]
0x18008a271  test    rdi, rdi
0x18008a274  jz      short loc_18008A28B
0x18008a276  mov     rcx, rdi; this
0x18008a279  call    ??1CTxtStories@@QEAA@XZ; CTxtStories::~CTxtStories(void)
0x18008a27e  mov     edx, 28h ; '('; unsigned __int64
0x18008a283  mov     rcx, rdi; void *
0x18008a286  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18008a28b  mov     rcx, [rbx+50h]; void *
0x18008a28f  test    rcx, rcx
0x18008a292  jnz     short loc_18008A301
0x18008a294  mov     rbx, [rsp+28h+arg_0]
0x18008a299  add     rsp, 20h
0x18008a29d  pop     rdi
0x18008a29e  retn
0x18008a2a0  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x18008a2a5  jmp     loc_18008A1CD
0x18008a2aa  call    cs:__imp_CloseHandle
0x18008a2b1  nop     dword ptr [rax+rax+00h]
0x18008a2b6  jmp     loc_18008A1DA
0x18008a2bb  mov     rax, [rcx]
0x18008a2be  mov     rax, [rax+10h]
0x18008a2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a2c7  test    eax, eax
0x18008a2c9  jnz     loc_18008A22D
0x18008a2cf  mov     qword ptr [rbx+118h], 0
0x18008a2da  jmp     loc_18008A22D
0x18008a2df  call    cs:__imp_DeleteObject
0x18008a2e6  nop     dword ptr [rax+rax+00h]
0x18008a2eb  jmp     loc_18008A23A
0x18008a2f0  mov     rax, [rcx]
0x18008a2f3  mov     rax, [rax+10h]
0x18008a2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a2fc  jmp     loc_18008A247
0x18008a301  mov     edx, 18h; unsigned __int64
0x18008a306  mov     qword ptr [rcx], 0
0x18008a30d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18008a312  jmp     short loc_18008A294
```
