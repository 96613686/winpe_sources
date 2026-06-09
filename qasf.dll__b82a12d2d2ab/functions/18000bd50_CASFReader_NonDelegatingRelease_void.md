# CASFReader::NonDelegatingRelease(void)

- ea: `0x18000bd50`
- end: `0x18000bdc8`
- name: `?NonDelegatingRelease@CASFReader@@UEAAKXZ`
- size: `120`
- prototype: `unsigned int __fastcall(CASFReader *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006ed0`
- `0x18000bd50`
- `0x18001f010`

## pseudocode

```c
unsigned int __fastcall CASFReader::NonDelegatingRelease(CASFReader *this)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // edi
  __int64 v5; // rcx
  int i; // eax

  v2 = *((_QWORD *)this + 60);
  if ( !v2 )
    return CUnknown::NonDelegatingRelease(this);
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v4 = v3;
  if ( *((_DWORD *)this + 123) && !v3 )
  {
    v5 = *(_QWORD *)this;
    *((_DWORD *)this + 123) = 0;
    *((_QWORD *)this + 60) = 0;
    for ( i = (*(__int64 (__fastcall **)(CASFReader *))(v5 + 16))(this);
          i;
          i = (*(__int64 (__fastcall **)(CASFReader *))(*(_QWORD *)this + 16LL))(this) )
    {
      ;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000bd50  mov     [rsp+arg_0], rbx
0x18000bd55  push    rdi
0x18000bd56  sub     rsp, 20h
0x18000bd5a  mov     rbx, rcx
0x18000bd5d  mov     rcx, [rcx+1E0h]
0x18000bd64  test    rcx, rcx
0x18000bd67  jz      short loc_18000BDB5
0x18000bd69  mov     rax, [rcx]
0x18000bd6c  mov     rax, [rax+10h]
0x18000bd70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd75  cmp     dword ptr [rbx+1ECh], 0
0x18000bd7c  mov     edi, eax
0x18000bd7e  jz      short loc_18000BDB1
0x18000bd80  test    eax, eax
0x18000bd82  jnz     short loc_18000BDB1
0x18000bd84  mov     rcx, [rbx]
0x18000bd87  mov     [rbx+1ECh], eax
0x18000bd8d  mov     qword ptr [rbx+1E0h], 0
0x18000bd98  mov     rax, [rcx+10h]
0x18000bd9c  jmp     short loc_18000BDA5
0x18000bd9e  mov     rax, [rbx]
0x18000bda1  mov     rax, [rax+10h]
0x18000bda5  mov     rcx, rbx
0x18000bda8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdad  test    eax, eax
0x18000bdaf  jnz     short loc_18000BD9E
0x18000bdb1  mov     eax, edi
0x18000bdb3  jmp     short loc_18000BDBD
0x18000bdb5  mov     rcx, rbx; this
0x18000bdb8  call    ?NonDelegatingRelease@CUnknown@@UEAAKXZ; CUnknown::NonDelegatingRelease(void)
0x18000bdbd  mov     rbx, [rsp+28h+arg_0]
0x18000bdc2  add     rsp, 20h
0x18000bdc6  pop     rdi
0x18000bdc7  retn
```
