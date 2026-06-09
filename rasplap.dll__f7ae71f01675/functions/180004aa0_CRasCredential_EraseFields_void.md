# CRasCredential::_EraseFields(void)

- ea: `0x180004aa0`
- end: `0x180004bd1`
- name: `?_EraseFields@CRasCredential@@AEAAXXZ`
- size: `305`
- prototype: `void __fastcall(CRasCredential *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ee0`
- `0x180003fa0`
- `0x180004480`

## callees

- `0x180004aa0`
- `0x18000c010`

## pseudocode

```c
void __fastcall CRasCredential::_EraseFields(CRasCredential *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdi
  char *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rcx
  char *v7; // rax
  __int64 v8; // rcx
  char *v9; // rax
  char *v10; // rax

  v2 = *((_QWORD *)this + 1);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, CRasCredential *, __int64, const wchar_t *))(*(_QWORD *)v2 + 40LL))(
      v2,
      this,
      4,
      &Data);
    (*(void (__fastcall **)(_QWORD, CRasCredential *, __int64, const wchar_t *))(**((_QWORD **)this + 1) + 40LL))(
      *((_QWORD *)this + 1),
      this,
      7,
      &Data);
    v3 = 514;
    v4 = (char *)this + 556;
    v5 = 514;
    do
    {
      *v4++ = 0;
      --v5;
    }
    while ( v5 );
    (*(void (__fastcall **)(_QWORD, CRasCredential *, __int64, const wchar_t *))(**((_QWORD **)this + 1) + 40LL))(
      *((_QWORD *)this + 1),
      this,
      5,
      &Data);
    (*(void (__fastcall **)(_QWORD, CRasCredential *, __int64, const wchar_t *))(**((_QWORD **)this + 1) + 40LL))(
      *((_QWORD *)this + 1),
      this,
      8,
      &Data);
    v6 = 514;
    v7 = (char *)this + 1070;
    do
    {
      *v7++ = 0;
      --v6;
    }
    while ( v6 );
    v8 = 32;
    v9 = (char *)this + 1584;
    do
    {
      *v9++ = 0;
      --v8;
    }
    while ( v8 );
    v10 = (char *)this + 1616;
    do
    {
      *v10++ = 0;
      --v3;
    }
    while ( v3 );
    (*(void (__fastcall **)(_QWORD, CRasCredential *, __int64, const wchar_t *))(**((_QWORD **)this + 1) + 40LL))(
      *((_QWORD *)this + 1),
      this,
      3,
      &Data);
    (*(void (__fastcall **)(_QWORD, CRasCredential *, __int64, const wchar_t *))(**((_QWORD **)this + 1) + 40LL))(
      *((_QWORD *)this + 1),
      this,
      6,
      &Data);
  }
}

```

## disassembly

```asm
0x180004aa0  mov     [rsp+arg_0], rbx
0x180004aa5  mov     [rsp+arg_8], rbp
0x180004aaa  push    rdi
0x180004aab  sub     rsp, 30h
0x180004aaf  mov     rbx, rcx
0x180004ab2  mov     rcx, [rcx+8]
0x180004ab6  test    rcx, rcx
0x180004ab9  jz      loc_180004BC1
0x180004abf  mov     rax, [rcx]
0x180004ac2  lea     rbp, Data
0x180004ac9  mov     r9, rbp
0x180004acc  mov     r8d, 4
0x180004ad2  mov     rdx, rbx
0x180004ad5  mov     rax, [rax+28h]
0x180004ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ade  mov     rcx, [rbx+8]
0x180004ae2  mov     r9, rbp
0x180004ae5  mov     r8d, 7
0x180004aeb  mov     rdx, rbx
0x180004aee  mov     rax, [rcx]
0x180004af1  mov     rax, [rax+28h]
0x180004af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004afa  mov     edi, 202h
0x180004aff  lea     rax, [rbx+22Ch]
0x180004b06  mov     ecx, edi
0x180004b08  mov     byte ptr [rax], 0
0x180004b0b  inc     rax
0x180004b0e  sub     rcx, 1
0x180004b12  jnz     short loc_180004B08
0x180004b14  mov     rcx, [rbx+8]
0x180004b18  mov     r9, rbp
0x180004b1b  mov     r8d, 5
0x180004b21  mov     rdx, rbx
0x180004b24  mov     rax, [rcx]
0x180004b27  mov     rax, [rax+28h]
0x180004b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b30  mov     rcx, [rbx+8]
0x180004b34  mov     r9, rbp
0x180004b37  mov     r8d, 8
0x180004b3d  mov     rdx, rbx
0x180004b40  mov     rax, [rcx]
0x180004b43  mov     rax, [rax+28h]
0x180004b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b4c  mov     rcx, rdi
0x180004b4f  lea     rax, [rbx+42Eh]
0x180004b56  mov     byte ptr [rax], 0
0x180004b59  inc     rax
0x180004b5c  sub     rcx, 1
0x180004b60  jnz     short loc_180004B56
0x180004b62  mov     ecx, 20h ; ' '
0x180004b67  lea     rax, [rbx+630h]
0x180004b6e  mov     byte ptr [rax], 0
0x180004b71  inc     rax
0x180004b74  sub     rcx, 1
0x180004b78  jnz     short loc_180004B6E
0x180004b7a  lea     rax, [rbx+650h]
0x180004b81  mov     byte ptr [rax], 0
0x180004b84  inc     rax
0x180004b87  sub     rdi, 1
0x180004b8b  jnz     short loc_180004B81
0x180004b8d  mov     rcx, [rbx+8]
0x180004b91  lea     r8d, [rdi+3]
0x180004b95  mov     r9, rbp
0x180004b98  mov     rdx, rbx
0x180004b9b  mov     rax, [rcx]
0x180004b9e  mov     rax, [rax+28h]
0x180004ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ba7  mov     rcx, [rbx+8]
0x180004bab  lea     r8d, [rdi+6]
0x180004baf  mov     r9, rbp
0x180004bb2  mov     rdx, rbx
0x180004bb5  mov     rax, [rcx]
0x180004bb8  mov     rax, [rax+28h]
0x180004bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bc1  mov     rbx, [rsp+38h+arg_0]
0x180004bc6  mov     rbp, [rsp+38h+arg_8]
0x180004bcb  add     rsp, 30h
0x180004bcf  pop     rdi
0x180004bd0  retn
```
