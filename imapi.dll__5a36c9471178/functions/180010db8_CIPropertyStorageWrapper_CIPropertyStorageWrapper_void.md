# CIPropertyStorageWrapper::~CIPropertyStorageWrapper(void)

- ea: `0x180010db8`
- end: `0x180010e57`
- name: `??1CIPropertyStorageWrapper@@QEAA@XZ`
- size: `159`
- prototype: `void __fastcall(CIPropertyStorageWrapper *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000e958`
- `0x180010e98`
- `0x1800119b0`

## callees

- `0x180001144`
- `0x180010db8`
- `0x180019010`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x180010e3c`
- `KERNEL32!ReleaseMutex` at `0x180010e3c`
- `KERNEL32!CloseHandle` at `0x180010e46`
- `KERNEL32!CloseHandle` at `0x180010e46`
- `KERNEL32!WaitForSingleObject` at `0x180010ddb`
- `KERNEL32!WaitForSingleObject` at `0x180010ddb`

## pseudocode

```c
void __fastcall CIPropertyStorageWrapper::~CIPropertyStorageWrapper(CIPropertyStorageWrapper *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rbx

  *(_QWORD *)this = &CIPropertyStorageWrapper::`vftable';
  v2 = (void *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    WaitForSingleObject(v2, 0xFFFFFFFF);
    while ( 1 )
    {
      v5 = (void *)*((_QWORD *)this + 2);
      if ( !v5 )
        break;
      *((_QWORD *)this + 2) = *(_QWORD *)v5;
      if ( *((_WORD *)v5 + 16) >= 2u )
      {
        if ( *((_WORD *)v5 + 16) == 66 )
        {
          v3 = **((_QWORD **)v5 + 5);
          if ( v3 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        }
        operator delete(*((void **)v5 + 5));
      }
      v4 = (void *)*((_QWORD *)v5 + 3);
      if ( v4 )
        operator delete(v4);
      operator delete(v5);
    }
    ReleaseMutex(*((HANDLE *)this + 5));
    CloseHandle(*((HANDLE *)this + 5));
  }
}

```

## disassembly

```asm
0x180010db8  mov     [rsp+arg_0], rbx
0x180010dbd  push    rdi
0x180010dbe  sub     rsp, 20h
0x180010dc2  lea     rax, ??_7CIPropertyStorageWrapper@@6B@; const CIPropertyStorageWrapper::`vftable'
0x180010dc9  mov     rdi, rcx
0x180010dcc  mov     [rcx], rax
0x180010dcf  mov     rcx, [rcx+28h]; hHandle
0x180010dd3  test    rcx, rcx
0x180010dd6  jz      short loc_180010E4C
0x180010dd8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010ddb  call    cs:__imp_WaitForSingleObject
0x180010de1  jmp     short loc_180010E2F
0x180010de3  mov     rax, [rbx]
0x180010de6  mov     [rdi+10h], rax
0x180010dea  cmp     word ptr [rbx+20h], 2
0x180010def  jb      short loc_180010E19
0x180010df1  cmp     word ptr [rbx+20h], 42h ; 'B'
0x180010df6  jnz     short loc_180010E10
0x180010df8  mov     rax, [rbx+28h]
0x180010dfc  mov     rcx, [rax]
0x180010dff  test    rcx, rcx
0x180010e02  jz      short loc_180010E10
0x180010e04  mov     rax, [rcx]
0x180010e07  mov     rax, [rax+10h]
0x180010e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e10  mov     rcx, [rbx+28h]; Block
0x180010e14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010e19  mov     rcx, [rbx+18h]; Block
0x180010e1d  test    rcx, rcx
0x180010e20  jz      short loc_180010E27
0x180010e22  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010e27  mov     rcx, rbx; Block
0x180010e2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010e2f  mov     rbx, [rdi+10h]
0x180010e33  test    rbx, rbx
0x180010e36  jnz     short loc_180010DE3
0x180010e38  mov     rcx, [rdi+28h]; hMutex
0x180010e3c  call    cs:__imp_ReleaseMutex
0x180010e42  mov     rcx, [rdi+28h]; hObject
0x180010e46  call    cs:__imp_CloseHandle
0x180010e4c  mov     rbx, [rsp+28h+arg_0]
0x180010e51  add     rsp, 20h
0x180010e55  pop     rdi
0x180010e56  retn
```
