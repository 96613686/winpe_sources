# StringReadFromStream(IStream *,char *,uint)

- ea: `0x18000aef4`
- end: `0x18000af48`
- name: `?StringReadFromStream@@YAJPEAUIStream@@PEADI@Z`
- size: `84`
- prototype: `__int64 __fastcall(struct IStream *, char *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800074e0`
- `0x180008c8c`

## callees

- `0x18000aef4`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall StringReadFromStream(struct IStream *a1, char *a2, unsigned int a3)
{
  int v3; // edi

  v3 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      *a2 = 0;
      ((void (__fastcall *)(struct IStream *, char *, __int64))a1->lpVtbl->Read)(a1, a2, 1);
      if ( !*a2 )
        break;
      ++a2;
      if ( ++v3 >= a3 )
        goto LABEL_4;
    }
  }
  else
  {
LABEL_4:
    *(a2 - 1) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000aef4  push    rbx
0x18000aef6  push    rsi
0x18000aef7  push    rdi
0x18000aef8  push    r14
0x18000aefa  sub     rsp, 38h
0x18000aefe  xor     edi, edi
0x18000af00  mov     esi, r8d
0x18000af03  mov     rbx, rdx
0x18000af06  mov     r14, rcx
0x18000af09  test    r8d, r8d
0x18000af0c  jz      short loc_18000AF38
0x18000af0e  mov     byte ptr [rbx], 0
0x18000af11  xor     r9d, r9d
0x18000af14  mov     rax, [r14]
0x18000af17  mov     rdx, rbx
0x18000af1a  mov     rcx, r14
0x18000af1d  lea     r8d, [r9+1]
0x18000af21  mov     rax, [rax+18h]
0x18000af25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af2a  cmp     byte ptr [rbx], 0
0x18000af2d  jz      short loc_18000AF3C
0x18000af2f  inc     rbx
0x18000af32  inc     edi
0x18000af34  cmp     edi, esi
0x18000af36  jb      short loc_18000AF0E
0x18000af38  mov     byte ptr [rbx-1], 0
0x18000af3c  xor     eax, eax
0x18000af3e  add     rsp, 38h
0x18000af42  pop     r14
0x18000af44  pop     rdi
0x18000af45  pop     rsi
0x18000af46  pop     rbx
0x18000af47  retn
```
