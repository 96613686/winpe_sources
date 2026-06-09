# ReleaseMarshallData(uchar const *,ulong)

- ea: `0x180012440`
- end: `0x1800124fe`
- name: `?ReleaseMarshallData@@YAJPEBEK@Z`
- size: `190`
- prototype: `__int64 __fastcall(const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011fb0`

## callees

- `0x180012440`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800124dc`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800124dc`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180012464`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180012464`

## pseudocode

```c
HRESULT __fastcall ReleaseMarshallData(const unsigned __int8 *a1, unsigned int a2)
{
  HRESULT result; // eax
  int v5; // eax
  LPSTREAM v6; // rcx
  int v7; // ebx
  __int64 v8; // rax
  int v9; // eax
  LPSTREAM ppstm; // [rsp+50h] [rbp+18h] BYREF
  __int64 v11; // [rsp+58h] [rbp+20h]

  ppstm = 0;
  result = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( result >= 0 )
  {
    if ( ppstm )
    {
      v5 = (*(__int64 (__fastcall **)(LPSTREAM, const unsigned __int8 *, _QWORD, _QWORD))(*(_QWORD *)ppstm + 32LL))(
             ppstm,
             a1,
             a2,
             0);
      v6 = ppstm;
      v7 = v5;
      if ( v5 >= 0
        && (v8 = *(_QWORD *)ppstm,
            v11 = 0,
            v9 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(v8 + 40))(ppstm, 0, 0, 0),
            v6 = ppstm,
            v7 = v9,
            v9 >= 0) )
      {
        CoReleaseMarshalData(ppstm);
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
        return 0;
      }
      else
      {
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v6 + 16LL))(v6);
        return v7;
      }
    }
    else
    {
      return -2147467259;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012440  mov     [rsp+arg_0], rbx
0x180012445  push    rdi
0x180012446  sub     rsp, 30h
0x18001244a  mov     ebx, edx
0x18001244c  mov     [rsp+38h+ppstm], 0
0x180012455  mov     rdi, rcx
0x180012458  lea     r8, [rsp+38h+ppstm]; ppstm
0x18001245d  mov     edx, 1; fDeleteOnRelease
0x180012462  xor     ecx, ecx; hGlobal
0x180012464  call    cs:__imp_CreateStreamOnHGlobal
0x18001246a  test    eax, eax
0x18001246c  js      short loc_1800124D1
0x18001246e  mov     rcx, [rsp+38h+ppstm]
0x180012473  test    rcx, rcx
0x180012476  jz      short loc_1800124F7
0x180012478  mov     rax, [rcx]
0x18001247b  xor     r9d, r9d
0x18001247e  mov     r8d, ebx
0x180012481  mov     rdx, rdi
0x180012484  mov     rax, [rax+20h]
0x180012488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001248d  mov     rcx, [rsp+38h+ppstm]
0x180012492  mov     ebx, eax
0x180012494  test    eax, eax
0x180012496  js      short loc_1800124C3
0x180012498  mov     rax, [rcx]
0x18001249b  xor     r9d, r9d
0x18001249e  mov     [rsp+38h+arg_18], 0
0x1800124a7  xor     r8d, r8d
0x1800124aa  mov     rdx, [rsp+38h+arg_18]
0x1800124af  mov     rax, [rax+28h]
0x1800124b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124b8  mov     rcx, [rsp+38h+ppstm]; pStm
0x1800124bd  mov     ebx, eax
0x1800124bf  test    eax, eax
0x1800124c1  jns     short loc_1800124DC
0x1800124c3  mov     rdx, [rcx]
0x1800124c6  mov     rax, [rdx+10h]
0x1800124ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124cf  mov     eax, ebx
0x1800124d1  mov     rbx, [rsp+38h+arg_0]
0x1800124d6  add     rsp, 30h
0x1800124da  pop     rdi
0x1800124db  retn
0x1800124dc  call    cs:__imp_CoReleaseMarshalData
0x1800124e2  mov     rcx, [rsp+38h+ppstm]
0x1800124e7  mov     rax, [rcx]
0x1800124ea  mov     rax, [rax+10h]
0x1800124ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124f3  xor     eax, eax
0x1800124f5  jmp     short loc_1800124D1
0x1800124f7  mov     eax, 80004005h
0x1800124fc  jmp     short loc_1800124D1
```
