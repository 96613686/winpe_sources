# CWMWriterIndexerCallback::OnStatus(WMT_STATUS,long,WMT_ATTR_DATATYPE,uchar *,void *)

- ea: `0x180010890`
- end: `0x180010942`
- name: `?OnStatus@CWMWriterIndexerCallback@@UEAAJW4WMT_STATUS@@JW4WMT_ATTR_DATATYPE@@PEAEPEAX@Z`
- size: `178`
- prototype: `__int64 __fastcall(CWMWriterIndexerCallback *__hidden this, enum WMT_STATUS, int, enum WMT_ATTR_DATATYPE, unsigned __int8 *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180010890`
- `0x18001f010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800108f5`
- `KERNEL32!SetEvent` at `0x1800108f5`

## pseudocode

```c
__int64 __fastcall CWMWriterIndexerCallback::OnStatus(
        CWMWriterIndexerCallback *this,
        enum WMT_STATUS a2,
        int a3,
        enum WMT_ATTR_DATATYPE a4,
        unsigned __int8 *a5,
        HANDLE *a6)
{
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // r8

  switch ( a2 )
  {
    case WMT_ERROR:
      *(_DWORD *)(*((_QWORD *)this + 1) + 208LL) = a3;
      return 0;
    case WMT_STARTED:
      v8 = *(_QWORD *)(*((_QWORD *)this + 1) + 104LL);
      if ( !v8 )
        return 0;
      v9 = 11;
      goto LABEL_12;
    case WMT_CLOSED:
      *(_DWORD *)(*((_QWORD *)this + 1) + 208LL) = a3;
      SetEvent(*a6);
      v8 = *(_QWORD *)(*((_QWORD *)this + 1) + 104LL);
      if ( !v8 )
        return 0;
      v9 = 13;
LABEL_12:
      (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v8 + 24LL))(v8, 593, v9, 0);
      return 0;
    case WMT_INDEX_PROGRESS:
      v7 = *(_QWORD *)(*((_QWORD *)this + 1) + 104LL);
      if ( v7 )
        (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v7 + 24LL))(
          v7,
          593,
          16,
          *(unsigned int *)a5);
      break;
  }
  return 0;
}

```

## disassembly

```asm
0x180010890  push    rbx
0x180010892  sub     rsp, 30h
0x180010896  mov     rbx, rcx
0x180010899  test    edx, edx
0x18001089b  jz      loc_18001092F
0x1800108a1  cmp     edx, 0Bh
0x1800108a4  jz      short loc_180010910
0x1800108a6  cmp     edx, 0Dh
0x1800108a9  jz      short loc_1800108E2
0x1800108ab  mov     r8d, 10h
0x1800108b1  cmp     edx, r8d
0x1800108b4  jnz     loc_18001093A
0x1800108ba  mov     rax, [rcx+8]
0x1800108be  mov     rcx, [rax+68h]
0x1800108c2  test    rcx, rcx
0x1800108c5  jz      short loc_18001093A
0x1800108c7  mov     rax, [rsp+38h+arg_20]
0x1800108cc  mov     rdx, [rcx]
0x1800108cf  mov     r9d, [rax]
0x1800108d2  mov     rax, [rdx+18h]
0x1800108d6  mov     edx, 251h
0x1800108db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108e0  jmp     short loc_18001093A
0x1800108e2  mov     rax, [rcx+8]
0x1800108e6  mov     rcx, [rsp+38h+arg_28]
0x1800108eb  mov     [rax+0D0h], r8d
0x1800108f2  mov     rcx, [rcx]; hEvent
0x1800108f5  call    cs:__imp_SetEvent
0x1800108fb  mov     rax, [rbx+8]
0x1800108ff  mov     rcx, [rax+68h]
0x180010903  test    rcx, rcx
0x180010906  jz      short loc_18001093A
0x180010908  mov     r8d, 0Dh
0x18001090e  jmp     short loc_180010923
0x180010910  mov     rax, [rcx+8]
0x180010914  mov     rcx, [rax+68h]
0x180010918  test    rcx, rcx
0x18001091b  jz      short loc_18001093A
0x18001091d  mov     r8d, 0Bh
0x180010923  mov     rax, [rcx]
0x180010926  xor     r9d, r9d
0x180010929  mov     rax, [rax+18h]
0x18001092d  jmp     short loc_1800108D6
0x18001092f  mov     rax, [rcx+8]
0x180010933  mov     [rax+0D0h], r8d
0x18001093a  xor     eax, eax
0x18001093c  add     rsp, 30h
0x180010940  pop     rbx
0x180010941  retn
```
