# CRedbookTracks::~CRedbookTracks(void)

- ea: `0x1800150f8`
- end: `0x18001517a`
- name: `??1CRedbookTracks@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(CRedbookTracks *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000b394`

## callees

- `0x180001144`
- `0x1800150f8`
- `0x180015810`
- `0x180019010`

## import_xrefs

- `msvcrt!_wremove` at `0x180015113`
- `msvcrt!_wremove` at `0x180015113`
- `OLEAUT32!__imp_SysFreeString` at `0x18001511d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001511d`

## pseudocode

```c
void __fastcall CRedbookTracks::~CRedbookTracks(BSTR *this)
{
  const wchar_t *v2; // rcx
  _QWORD *v3; // rdi
  bool v4; // zf
  __int64 v5; // rcx

  CRedbookTracks::CloseDisc((CRedbookTracks *)this);
  v2 = this[5];
  if ( v2 )
  {
    _wremove(v2);
    SysFreeString(this[5]);
    this[5] = 0;
  }
  while ( 1 )
  {
    v3 = *this;
    if ( !*this )
      break;
    v4 = v3 == (_QWORD *)this[1];
    *this = (BSTR)*v3;
    if ( v4 )
      this[1] = (BSTR)*v3;
    --*((_DWORD *)this + 4);
    v5 = v3[1];
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    operator delete(v3);
  }
  *((_DWORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x1800150f8  mov     [rsp+arg_0], rbx
0x1800150fd  push    rdi
0x1800150fe  sub     rsp, 20h
0x180015102  mov     rbx, rcx
0x180015105  call    ?CloseDisc@CRedbookTracks@@IEAAXXZ; CRedbookTracks::CloseDisc(void)
0x18001510a  mov     rcx, [rbx+28h]; FileName
0x18001510e  test    rcx, rcx
0x180015111  jz      short loc_18001512B
0x180015113  call    cs:__imp__wremove
0x180015119  mov     rcx, [rbx+28h]; bstrString
0x18001511d  call    cs:__imp_SysFreeString
0x180015123  mov     qword ptr [rbx+28h], 0
0x18001512b  mov     rdi, [rbx]
0x18001512e  test    rdi, rdi
0x180015131  jz      short loc_180015168
0x180015133  mov     rax, [rdi]
0x180015136  cmp     rdi, [rbx+8]
0x18001513a  mov     [rbx], rax
0x18001513d  jnz     short loc_180015146
0x18001513f  mov     rax, [rdi]
0x180015142  mov     [rbx+8], rax
0x180015146  dec     dword ptr [rbx+10h]
0x180015149  mov     rcx, [rdi+8]
0x18001514d  test    rcx, rcx
0x180015150  jz      short loc_18001515E
0x180015152  mov     rax, [rcx]
0x180015155  mov     rax, [rax+10h]
0x180015159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001515e  mov     rcx, rdi; Block
0x180015161  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015166  jmp     short loc_18001512B
0x180015168  mov     dword ptr [rbx+10h], 0
0x18001516f  mov     rbx, [rsp+28h+arg_0]
0x180015174  add     rsp, 20h
0x180015178  pop     rdi
0x180015179  retn
```
