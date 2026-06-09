# W3_FILTER_CONTEXT::HandleAuthComplete(int *,int *,int *)

- ea: `0x180002a40`
- end: `0x180002c4c`
- name: `?HandleAuthComplete@W3_FILTER_CONTEXT@@QEAAJPEAH00@Z`
- size: `524`
- prototype: `__int64 __fastcall(W3_FILTER_CONTEXT *__hidden this, int *, int *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800019c0`

## callees

- `0x180002a40`
- `0x180003a20`
- `0x1800074c0`
- `0x18000c942`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall W3_FILTER_CONTEXT::HandleAuthComplete(W3_FILTER_CONTEXT *this, int *a2, int *a3, int *a4)
{
  __int64 result; // rax
  __int64 v9; // rax
  const wchar_t *v10; // rbp
  __int64 v11; // rax
  unsigned __int16 v12; // r15
  __int16 v13; // r15
  __int64 v14; // rax
  const wchar_t *v15; // rdi
  __int64 v16; // rax
  unsigned __int16 v17; // cx
  __int64 v18; // rcx
  int v19; // edi
  _QWORD v20[9]; // [rsp+40h] [rbp-48h] BYREF

  if ( (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 232LL))(*((_QWORD *)this + 3)) )
    return 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3));
  v10 = *(const wchar_t **)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9) + 88);
  v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3));
  v12 = *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11) + 68);
  v20[0] = W3_FILTER_CONTEXT::GetFilterHeader;
  v20[1] = W3_FILTER_CONTEXT::SetFilterHeader;
  v20[2] = W3_FILTER_CONTEXT::AddFilterHeader;
  v20[3] = W3_FILTER_CONTEXT::GetUserToken;
  v13 = v12 >> 1;
  v20[5] = 0;
  v20[4] = 0;
  result = W3_FILTER_CONTEXT::NotifyFilters(this, 0x4000000u, v20, a2);
  if ( (int)result >= 0 && !*a2 )
  {
    v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3));
    v15 = *(const wchar_t **)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14) + 88);
    v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3));
    v17 = *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16) + 68) >> 1;
    if ( v17 == v13 && (v15 == v10 || !wcsncmp_0(v15, v10, v17)) )
      return 0;
    v18 = *((_QWORD *)this + 3);
    *a3 = 1;
    result = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v18 + 248LL))(v18, 7, (char *)this + 32);
    if ( (int)result < 0 )
      return result;
    v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, int *))(**((_QWORD **)this + 3) + 104LL))(
            *((_QWORD *)this + 3),
            1,
            *((_QWORD *)this + 4),
            0,
            0,
            a4);
    if ( v19 >= 0 && *a4 )
    {
      return 0;
    }
    else
    {
      W3_FILTER_CONTEXT::HandleAuthCompleteCompletion(this);
      return (unsigned int)v19;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002a40  mov     [rsp+arg_18], rbx
0x180002a45  push    rsi
0x180002a46  push    rdi
0x180002a47  push    r14
0x180002a49  sub     rsp, 70h
0x180002a4d  mov     rbx, rcx
0x180002a50  mov     rsi, r9
0x180002a53  mov     rcx, [rcx+18h]
0x180002a57  mov     r14, r8
0x180002a5a  mov     rdi, rdx
0x180002a5d  mov     rax, [rcx]
0x180002a60  mov     rax, [rax+0E8h]
0x180002a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a6c  test    rax, rax
0x180002a6f  jz      short loc_180002A84
0x180002a71  xor     eax, eax
0x180002a73  mov     rbx, [rsp+88h+arg_18]
0x180002a7b  add     rsp, 70h
0x180002a7f  pop     r14
0x180002a81  pop     rdi
0x180002a82  pop     rsi
0x180002a83  retn
0x180002a84  mov     rcx, [rbx+18h]
0x180002a88  mov     [rsp+88h+arg_0], rbp
0x180002a90  mov     [rsp+88h+arg_8], r12
0x180002a98  mov     [rsp+88h+arg_10], r15
0x180002aa0  mov     rax, [rcx]
0x180002aa3  mov     rax, [rax+18h]
0x180002aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aac  mov     rdx, rax
0x180002aaf  mov     rcx, [rax]
0x180002ab2  mov     rax, [rcx+8]
0x180002ab6  mov     rcx, rdx
0x180002ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002abe  mov     rcx, [rbx+18h]
0x180002ac2  mov     rbp, [rax+58h]
0x180002ac6  mov     rax, [rcx]
0x180002ac9  mov     rax, [rax+18h]
0x180002acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ad2  mov     rdx, rax
0x180002ad5  mov     rcx, [rax]
0x180002ad8  mov     rax, [rcx+8]
0x180002adc  mov     rcx, rdx
0x180002adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ae4  xor     r12d, r12d
0x180002ae7  lea     r8, [rsp+88h+var_48]; void *
0x180002aec  mov     r9, rdi; int *
0x180002aef  mov     edx, 4000000h; unsigned int
0x180002af4  mov     rcx, rbx; this
0x180002af7  movzx   r15d, word ptr [rax+44h]
0x180002afc  lea     rax, ?GetFilterHeader@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEADPEAXPEAK@Z; W3_FILTER_CONTEXT::GetFilterHeader(_HTTP_FILTER_CONTEXT *,char *,void *,ulong *)
0x180002b03  mov     [rsp+88h+var_48], rax
0x180002b08  lea     rax, ?SetFilterHeader@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEAD1@Z; W3_FILTER_CONTEXT::SetFilterHeader(_HTTP_FILTER_CONTEXT *,char *,char *)
0x180002b0f  mov     [rsp+88h+var_40], rax
0x180002b14  lea     rax, ?AddFilterHeader@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEAD1@Z; W3_FILTER_CONTEXT::AddFilterHeader(_HTTP_FILTER_CONTEXT *,char *,char *)
0x180002b1b  mov     [rsp+88h+var_38], rax
0x180002b20  lea     rax, ?GetUserToken@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEAPEAX@Z; W3_FILTER_CONTEXT::GetUserToken(_HTTP_FILTER_CONTEXT *,void * *)
0x180002b27  mov     [rsp+88h+var_30], rax
0x180002b2c  shr     r15w, 1
0x180002b30  mov     [rsp+88h+var_20], r12
0x180002b35  mov     [rsp+88h+var_28], r12
0x180002b3a  call    ?NotifyFilters@W3_FILTER_CONTEXT@@QEAAJKPEAXPEAH@Z; W3_FILTER_CONTEXT::NotifyFilters(ulong,void *,int *)
0x180002b3f  test    eax, eax
0x180002b41  js      loc_180002C23
0x180002b47  cmp     [rdi], r12d
0x180002b4a  jnz     loc_180002C23
0x180002b50  mov     rcx, [rbx+18h]
0x180002b54  mov     rax, [rcx]
0x180002b57  mov     rax, [rax+18h]
0x180002b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b60  mov     rdx, rax
0x180002b63  mov     rcx, [rax]
0x180002b66  mov     rax, [rcx+8]
0x180002b6a  mov     rcx, rdx
0x180002b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b72  mov     rcx, [rbx+18h]
0x180002b76  mov     rdi, [rax+58h]
0x180002b7a  mov     rax, [rcx]
0x180002b7d  mov     rax, [rax+18h]
0x180002b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b86  mov     r8, rax
0x180002b89  mov     rcx, [rax]
0x180002b8c  mov     rax, [rcx+8]
0x180002b90  mov     rcx, r8
0x180002b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b98  movzx   ecx, word ptr [rax+44h]
0x180002b9c  shr     cx, 1
0x180002b9f  cmp     cx, r15w
0x180002ba3  jnz     short loc_180002BBD
0x180002ba5  cmp     rdi, rbp
0x180002ba8  jz      short loc_180002C15
0x180002baa  movzx   r8d, cx; MaxCount
0x180002bae  mov     rdx, rbp; String2
0x180002bb1  mov     rcx, rdi; String1
0x180002bb4  call    wcsncmp_0
0x180002bb9  test    eax, eax
0x180002bbb  jz      short loc_180002C15
0x180002bbd  mov     rcx, [rbx+18h]
0x180002bc1  lea     r8, [rbx+20h]
0x180002bc5  mov     edx, 7
0x180002bca  mov     dword ptr [r14], 1
0x180002bd1  mov     rax, [rcx]
0x180002bd4  mov     rax, [rax+0F8h]
0x180002bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002be0  test    eax, eax
0x180002be2  js      short loc_180002C23
0x180002be4  mov     rcx, [rbx+18h]
0x180002be8  xor     r9d, r9d
0x180002beb  mov     r8, [rbx+20h]
0x180002bef  mov     edx, 1
0x180002bf4  mov     [rsp+88h+var_60], rsi
0x180002bf9  mov     [rsp+88h+var_68], r12
0x180002bfe  mov     rax, [rcx]
0x180002c01  mov     rax, [rax+68h]
0x180002c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c0a  mov     edi, eax
0x180002c0c  test    eax, eax
0x180002c0e  js      short loc_180002C19
0x180002c10  cmp     [rsi], r12d
0x180002c13  jz      short loc_180002C19
0x180002c15  xor     eax, eax
0x180002c17  jmp     short loc_180002C23
0x180002c19  mov     rcx, rbx; this
0x180002c1c  call    ?HandleAuthCompleteCompletion@W3_FILTER_CONTEXT@@QEAAXXZ; W3_FILTER_CONTEXT::HandleAuthCompleteCompletion(void)
0x180002c21  mov     eax, edi
0x180002c23  mov     r12, [rsp+88h+arg_8]
0x180002c2b  mov     rbp, [rsp+88h+arg_0]
0x180002c33  mov     r15, [rsp+88h+arg_10]
0x180002c3b  mov     rbx, [rsp+88h+arg_18]
0x180002c43  add     rsp, 70h
0x180002c47  pop     r14
0x180002c49  pop     rdi
0x180002c4a  pop     rsi
0x180002c4b  retn
```
