# WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)

- ea: `0x18000bcbc`
- end: `0x18000bd4c`
- name: `?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z`
- size: `144`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, unsigned int, void *, unsigned int)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c19c`
- `0x18000c54c`
- `0x18000c67c`
- `0x18000d228`
- `0x18000dc78`
- `0x18000df34`
- `0x18000e11c`
- `0x18000e438`
- `0x18000e660`
- `0x18000e6cc`
- `0x18000e798`
- `0x18000e898`
- `0x18000ea58`
- `0x18000eb24`
- `0x18000ec70`
- `0x18000eefc`
- `0x18000efb4`
- `0x18000f180`
- `0x18000f2b8`

## callees

- `0x18000bcbc`
- `0x18002c010`

## string_xrefs

- `0x18000bcf3`: `WriteAtOffset.Seek(0x%x) failed, 0x%08x`
- `0x18000bd36`: `WriteAtOffset.Write(0x%x) failed, 0x%08x`

## pseudocode

```c
__int64 __fastcall WriteAtOffset(struct _MINIDUMP_STATE *a1, unsigned int a2, void *a3, unsigned int a4)
{
  unsigned int v8; // ebx
  __int64 v9; // r9
  const char *v10; // r8

  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)a1 + 3) + 24LL))(
         *((_QWORD *)a1 + 3),
         0,
         a2,
         0);
  if ( v8 )
  {
    v9 = a2;
    v10 = "WriteAtOffset.Seek(0x%x) failed, 0x%08x";
LABEL_3:
    (*(void (__fastcall **)(_QWORD, __int64, const char *, __int64, unsigned int))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      4,
      v10,
      v9,
      v8);
    return v8;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, void *, _QWORD))(**((_QWORD **)a1 + 3) + 32LL))(*((_QWORD *)a1 + 3), a3, a4);
  if ( v8 )
  {
    v9 = a4;
    v10 = "WriteAtOffset.Write(0x%x) failed, 0x%08x";
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000bcbc  push    rbx
0x18000bcbe  push    rbp
0x18000bcbf  push    rsi
0x18000bcc0  push    rdi
0x18000bcc1  push    r14
0x18000bcc3  sub     rsp, 30h
0x18000bcc7  mov     rdi, rcx
0x18000bcca  mov     ebp, edx
0x18000bccc  mov     rcx, [rcx+18h]
0x18000bcd0  mov     r14, r8
0x18000bcd3  mov     esi, r9d
0x18000bcd6  mov     r8d, edx
0x18000bcd9  xor     r9d, r9d
0x18000bcdc  xor     edx, edx
0x18000bcde  mov     rax, [rcx]
0x18000bce1  mov     rax, [rax+18h]
0x18000bce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcea  mov     ebx, eax
0x18000bcec  test    eax, eax
0x18000bcee  jz      short loc_18000BD17
0x18000bcf0  mov     r9d, ebp
0x18000bcf3  lea     r8, aWriteatoffsetS; "WriteAtOffset.Seek(0x%x) failed, 0x%08x"
0x18000bcfa  mov     rcx, [rdi+28h]
0x18000bcfe  mov     [rsp+58h+var_38], ebx
0x18000bd02  mov     rdx, [rcx]
0x18000bd05  mov     rax, [rdx+8]
0x18000bd09  mov     edx, 4
0x18000bd0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd13  mov     eax, ebx
0x18000bd15  jmp     short loc_18000BD41
0x18000bd17  mov     rcx, [rdi+18h]
0x18000bd1b  mov     r8d, esi
0x18000bd1e  mov     rdx, r14
0x18000bd21  mov     rax, [rcx]
0x18000bd24  mov     rax, [rax+20h]
0x18000bd28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd2d  mov     ebx, eax
0x18000bd2f  test    eax, eax
0x18000bd31  jz      short loc_18000BD3F
0x18000bd33  mov     r9d, esi
0x18000bd36  lea     r8, aWriteatoffsetW; "WriteAtOffset.Write(0x%x) failed, 0x%08"...
0x18000bd3d  jmp     short loc_18000BCFA
0x18000bd3f  xor     eax, eax
0x18000bd41  add     rsp, 30h
0x18000bd45  pop     r14
0x18000bd47  pop     rdi
0x18000bd48  pop     rsi
0x18000bd49  pop     rbp
0x18000bd4a  pop     rbx
0x18000bd4b  retn
```
