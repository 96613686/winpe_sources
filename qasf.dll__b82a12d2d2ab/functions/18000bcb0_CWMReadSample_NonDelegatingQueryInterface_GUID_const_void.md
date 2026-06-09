# CWMReadSample::NonDelegatingQueryInterface(_GUID const &,void * *)

- ea: `0x18000bcb0`
- end: `0x18000bd32`
- name: `?NonDelegatingQueryInterface@CWMReadSample@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `130`
- prototype: `__int64 __fastcall(CWMReadSample *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006e78`
- `0x18000bcb0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMReadSample::NonDelegatingQueryInterface(CWMReadSample *this, const struct _GUID *a2, void **a3)
{
  unsigned int v3; // ebx
  char *v4; // rcx
  void (*v5)(void); // rax
  char *v7; // rcx

  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_INSSBuffer.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_INSSBuffer.Data4 )
  {
    v3 = 0;
    if ( !a3 )
      return (unsigned int)-2147467261;
    v4 = (char *)this - 8;
    *a3 = v4;
    v5 = *(void (**)(void))(*(_QWORD *)v4 + 8LL);
LABEL_6:
    v5();
    return v3;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_INSSBuffer3.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_INSSBuffer3.Data4 )
  {
    v3 = 0;
    if ( !a3 )
      return (unsigned int)-2147467261;
    v7 = (char *)this - 8;
    *a3 = v7;
    v5 = *(void (**)(void))(*(_QWORD *)v7 + 8LL);
    goto LABEL_6;
  }
  return CUnknown::NonDelegatingQueryInterface(this, a2, a3);
}

```

## disassembly

```asm
0x18000bcb0  push    rbx
0x18000bcb2  sub     rsp, 20h
0x18000bcb6  mov     rax, [rdx]
0x18000bcb9  cmp     rax, qword ptr cs:IID_INSSBuffer.Data1
0x18000bcc0  jnz     short loc_18000BCF8
0x18000bcc2  mov     rax, [rdx+8]
0x18000bcc6  cmp     rax, qword ptr cs:IID_INSSBuffer.Data4
0x18000bccd  jnz     short loc_18000BCF8
0x18000bccf  xor     ebx, ebx
0x18000bcd1  test    r8, r8
0x18000bcd4  jnz     short loc_18000BCDD
0x18000bcd6  mov     ebx, 80004003h
0x18000bcdb  jmp     short loc_18000BCF0
0x18000bcdd  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18000bce1  mov     [r8], rcx
0x18000bce4  mov     rdx, [rcx]
0x18000bce7  mov     rax, [rdx+8]
0x18000bceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcf0  mov     eax, ebx
0x18000bcf2  add     rsp, 20h
0x18000bcf6  pop     rbx
0x18000bcf7  retn
0x18000bcf8  mov     rax, [rdx]
0x18000bcfb  cmp     rax, qword ptr cs:IID_INSSBuffer3.Data1
0x18000bd02  jnz     short loc_18000BD28
0x18000bd04  mov     rax, [rdx+8]
0x18000bd08  cmp     rax, qword ptr cs:IID_INSSBuffer3.Data4
0x18000bd0f  jnz     short loc_18000BD28
0x18000bd11  xor     ebx, ebx
0x18000bd13  test    r8, r8
0x18000bd16  jz      short loc_18000BCD6
0x18000bd18  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x18000bd1c  mov     [r8], rcx
0x18000bd1f  mov     rax, [rcx]
0x18000bd22  mov     rax, [rax+8]
0x18000bd26  jmp     short loc_18000BCEB
0x18000bd28  add     rsp, 20h
0x18000bd2c  pop     rbx
0x18000bd2d  jmp     ?NonDelegatingQueryInterface@CUnknown@@UEAAJAEBU_GUID@@PEAPEAX@Z; CUnknown::NonDelegatingQueryInterface(_GUID const &,void * *)
```
