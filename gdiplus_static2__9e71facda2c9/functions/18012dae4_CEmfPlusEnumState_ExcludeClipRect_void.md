# CEmfPlusEnumState::ExcludeClipRect(void)

- ea: `0x18012dae4`
- end: `0x18012dbc6`
- name: `?ExcludeClipRect@CEmfPlusEnumState@@QEAAXXZ`
- size: `226`
- prototype: `void __fastcall(CEmfPlusEnumState *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003720`

## callees

- `0x18000506c`
- `0x180105d40`
- `0x18012dae4`
- `0x180171428`
- `0x180172010`

## import_xrefs

- `GDI32!CombineRgn` at `0x18012db92`
- `GDI32!CombineRgn` at `0x18012db92`
- `GDI32!DeleteObject` at `0x18012dba1`
- `GDI32!DeleteObject` at `0x18012dba1`
- `GDI32!CreateRectRgn` at `0x18012db56`
- `GDI32!CreateRectRgn` at `0x18012db6b`
- `GDI32!CreateRectRgn` at `0x18012db56`
- `GDI32!CreateRectRgn` at `0x18012db6b`

## pseudocode

```c
void __fastcall CEmfPlusEnumState::ExcludeClipRect(HRGN *this)
{
  const struct tagENHMETARECORD *PartialRecord; // rax
  __int64 *v3; // rcx
  __int64 v4; // rdx
  const struct tagENHMETARECORD *v5; // rbx
  size_t v6; // r8
  int v7; // ecx
  int iType; // edx
  int nSize; // r8d
  int v10; // r9d
  HRGN RectRgn; // rax
  HRGN v12; // rbx
  __int128 v13; // [rsp+20h] [rbp-28h] BYREF
  __int64 v14; // [rsp+30h] [rbp-18h]

  PartialRecord = CEmfPlusEnumState::GetPartialRecord((CEmfPlusEnumState *)this);
  v4 = *v3;
  v5 = PartialRecord;
  v14 = 0;
  v13 = 0;
  v6 = (*(unsigned int (__fastcall **)(__int64 *))(v4 + 48))(v3);
  if ( v6 < 0x18 )
  {
    memcpy_0(&v13, v5, v6);
    v5 = (const struct tagENHMETARECORD *)&v13;
  }
  v7 = v5->dParm[0];
  iType = v5[1].iType;
  nSize = v5[1].nSize;
  v10 = v5[1].dParm[0];
  if ( this[536] )
  {
    RectRgn = CreateRectRgn(v7, iType, nSize, v10);
    v12 = RectRgn;
    if ( RectRgn )
    {
      CombineRgn(this[536], this[536], RectRgn, 2);
      DeleteObject(v12);
    }
  }
  else
  {
    this[536] = CreateRectRgn(v7, iType, nSize, v10);
  }
}

```

## disassembly

```asm
0x18012dae4  mov     [rsp+arg_8], rbx
0x18012dae9  push    rdi
0x18012daea  sub     rsp, 40h
0x18012daee  mov     rax, cs:__security_cookie
0x18012daf5  xor     rax, rsp
0x18012daf8  mov     [rsp+48h+var_10], rax
0x18012dafd  mov     rdi, rcx
0x18012db00  call    ?GetPartialRecord@CEmfPlusEnumState@@QEAAPEBUtagENHMETARECORD@@XZ; CEmfPlusEnumState::GetPartialRecord(void)
0x18012db05  mov     rdx, [rcx]
0x18012db08  mov     rbx, rax
0x18012db0b  xor     eax, eax
0x18012db0d  xorps   xmm0, xmm0
0x18012db10  mov     [rsp+48h+var_18], rax
0x18012db15  movups  [rsp+48h+var_28], xmm0
0x18012db1a  mov     rax, [rdx+30h]
0x18012db1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012db23  mov     r8d, eax; Size
0x18012db26  cmp     r8, 18h
0x18012db2a  jnb     short loc_18012DB3E
0x18012db2c  mov     rdx, rbx; Src
0x18012db2f  lea     rcx, [rsp+48h+var_28]; void *
0x18012db34  call    memcpy_0
0x18012db39  lea     rbx, [rsp+48h+var_28]
0x18012db3e  cmp     qword ptr [rdi+10C0h], 0
0x18012db46  mov     ecx, [rbx+8]; x1
0x18012db49  mov     edx, [rbx+0Ch]; y1
0x18012db4c  mov     r8d, [rbx+10h]; x2
0x18012db50  mov     r9d, [rbx+14h]; y2
0x18012db54  jnz     short loc_18012DB6B
0x18012db56  call    cs:__imp_CreateRectRgn
0x18012db5d  nop     dword ptr [rax+rax+00h]
0x18012db62  mov     [rdi+10C0h], rax
0x18012db69  jmp     short loc_18012DBAD
0x18012db6b  call    cs:__imp_CreateRectRgn
0x18012db72  nop     dword ptr [rax+rax+00h]
0x18012db77  mov     rbx, rax
0x18012db7a  test    rax, rax
0x18012db7d  jz      short loc_18012DBAD
0x18012db7f  mov     rcx, [rdi+10C0h]; hrgnDst
0x18012db86  mov     r9d, 2; iMode
0x18012db8c  mov     rdx, rcx; hrgnSrc1
0x18012db8f  mov     r8, rax; hrgnSrc2
0x18012db92  call    cs:__imp_CombineRgn
0x18012db99  nop     dword ptr [rax+rax+00h]
0x18012db9e  mov     rcx, rbx; ho
0x18012dba1  call    cs:__imp_DeleteObject
0x18012dba8  nop     dword ptr [rax+rax+00h]
0x18012dbad  mov     rcx, [rsp+48h+var_10]
0x18012dbb2  xor     rcx, rsp; StackCookie
0x18012dbb5  call    __security_check_cookie
0x18012dbba  mov     rbx, [rsp+48h+arg_8]
0x18012dbbf  add     rsp, 40h
0x18012dbc3  pop     rdi
0x18012dbc4  retn
```
