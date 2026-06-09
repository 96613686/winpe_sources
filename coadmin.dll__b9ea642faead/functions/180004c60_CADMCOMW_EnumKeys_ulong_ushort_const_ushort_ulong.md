# CADMCOMW::EnumKeys(ulong,ushort const *,ushort *,ulong)

- ea: `0x180004c60`
- end: `0x180004dc1`
- name: `?EnumKeys@CADMCOMW@@UEAAJKPEBGPEAGK@Z`
- size: `353`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004c60`
- `0x18000716c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::EnumKeys(
        __int64 **this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  __int64 result; // rax
  const wchar_t *v9; // rdi
  __int64 *v10; // rcx
  int v11; // edx
  bool v12; // cf
  int v13; // eax
  unsigned int v14; // eax
  __int64 *v15; // rcx
  unsigned int v16; // ebx
  __int64 v17; // r9
  unsigned int v18; // ebx
  _DWORD v19[4]; // [rsp+60h] [rbp-28h] BYREF
  unsigned int v20; // [rsp+A8h] [rbp+20h] BYREF

  v20 = 0;
  v19[0] = 0;
  if ( !a4 )
    return 2147942487LL;
  v9 = L"/";
  if ( a3 )
    v9 = a3;
  result = CADMCOMW::LookupAndAccessCheck((CADMCOMW *)this, a2, &v20, (__int64)v9, 3u, 0, 0, 0, 0, v19, 0);
  if ( (int)result >= 0 )
  {
    v10 = this[101];
    v11 = v19[0];
    if ( v10 && v19[0] == 1 )
      return (*(__int64 (__fastcall **)(__int64 *, _QWORD, const wchar_t *, unsigned __int16 *, unsigned int))(*v10 + 40))(
               v10,
               v20,
               v9,
               a4,
               a5);
    if ( !a2 )
    {
      v12 = *v9 < 0x2Fu;
      if ( *v9 != 47 || (v12 = 0, v9[1]) )
        v13 = v12 ? -1 : 1;
      else
        v13 = 0;
      v11 = v13 != 0 ? v19[0] : 0;
    }
    if ( v10 && v11 == 2 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64 *))(*v10 + 176))(v10);
      v15 = this[101];
      v16 = a5;
      v17 = *v15;
      if ( a5 < v14 )
        return (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned __int16 *))(v17 + 184))(v15, a5, a4);
      v18 = v16 - (*(__int64 (**)(void))(v17 + 176))();
    }
    else
    {
      v18 = a5;
    }
    return (*(__int64 (__fastcall **)(__int64 *, _QWORD, const wchar_t *, unsigned __int16 *, unsigned int))(*this[4] + 104))(
             this[4],
             v20,
             v9,
             a4,
             v18);
  }
  return result;
}

```

## disassembly

```asm
0x180004c60  mov     rax, rsp
0x180004c63  mov     [rax+8], rbx
0x180004c67  mov     [rax+10h], rbp
0x180004c6b  push    rsi
0x180004c6c  push    rdi
0x180004c6d  push    r14
0x180004c6f  sub     rsp, 70h
0x180004c73  xor     r14d, r14d
0x180004c76  mov     rsi, r9
0x180004c79  mov     [rax+20h], r14d
0x180004c7d  mov     ebx, edx
0x180004c7f  mov     [rax-28h], r14d
0x180004c83  mov     rbp, rcx
0x180004c86  test    r9, r9
0x180004c89  jnz     short loc_180004C95
0x180004c8b  mov     eax, 80070057h
0x180004c90  jmp     loc_180004DAC
0x180004c95  mov     [rsp+88h+var_38], r14
0x180004c9a  lea     rax, [rsp+88h+var_28]
0x180004c9f  mov     [rsp+88h+var_40], rax
0x180004ca4  lea     rdi, asc_180011C70; "/"
0x180004cab  mov     [rsp+88h+var_48], r14
0x180004cb0  test    r8, r8
0x180004cb3  mov     [rsp+88h+var_50], r14
0x180004cb8  cmovnz  rdi, r8
0x180004cbc  mov     [rsp+88h+var_58], r14
0x180004cc1  mov     [rsp+88h+var_60], r14d
0x180004cc6  lea     r8, [rsp+88h+arg_18]
0x180004cce  mov     r9, rdi
0x180004cd1  mov     [rsp+88h+var_68], 3
0x180004cd9  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180004cde  test    eax, eax
0x180004ce0  js      loc_180004DAC
0x180004ce6  mov     rcx, [rbp+328h]
0x180004ced  mov     edx, [rsp+88h+var_28]
0x180004cf1  test    rcx, rcx
0x180004cf4  jz      short loc_180004D12
0x180004cf6  cmp     edx, 1
0x180004cf9  jnz     short loc_180004D12
0x180004cfb  mov     rax, [rcx]
0x180004cfe  mov     edx, [rsp+88h+arg_20]
0x180004d05  mov     [rsp+88h+var_68], edx
0x180004d09  mov     rax, [rax+28h]
0x180004d0d  jmp     loc_180004D9A
0x180004d12  test    ebx, ebx
0x180004d14  jnz     short loc_180004D33
0x180004d16  cmp     word ptr [rdi], 2Fh ; '/'
0x180004d1a  jnz     short loc_180004D28
0x180004d1c  cmp     [rdi+2], r14w
0x180004d21  jnz     short loc_180004D28
0x180004d23  mov     eax, r14d
0x180004d26  jmp     short loc_180004D2D
0x180004d28  sbb     eax, eax
0x180004d2a  or      eax, 1
0x180004d2d  neg     eax
0x180004d2f  sbb     eax, eax
0x180004d31  and     edx, eax
0x180004d33  test    rcx, rcx
0x180004d36  jz      short loc_180004D84
0x180004d38  cmp     edx, 2
0x180004d3b  jnz     short loc_180004D84
0x180004d3d  mov     rax, [rcx]
0x180004d40  mov     rax, [rax+0B0h]
0x180004d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d4c  mov     rcx, [rbp+328h]
0x180004d53  mov     ebx, [rsp+88h+arg_20]
0x180004d5a  mov     r9, [rcx]
0x180004d5d  cmp     ebx, eax
0x180004d5f  jnb     short loc_180004D74
0x180004d61  mov     rax, [r9+0B8h]
0x180004d68  mov     r8, rsi
0x180004d6b  mov     edx, ebx
0x180004d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d72  jmp     short loc_180004DAC
0x180004d74  mov     rax, [r9+0B0h]
0x180004d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d80  sub     ebx, eax
0x180004d82  jmp     short loc_180004D8B
0x180004d84  mov     ebx, [rsp+88h+arg_20]
0x180004d8b  mov     rcx, [rbp+20h]
0x180004d8f  mov     [rsp+88h+var_68], ebx
0x180004d93  mov     rax, [rcx]
0x180004d96  mov     rax, [rax+68h]
0x180004d9a  mov     edx, [rsp+88h+arg_18]
0x180004da1  mov     r9, rsi
0x180004da4  mov     r8, rdi
0x180004da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dac  lea     r11, [rsp+88h+var_18]
0x180004db1  mov     rbx, [r11+20h]
0x180004db5  mov     rbp, [r11+28h]
0x180004db9  mov     rsp, r11
0x180004dbc  pop     r14
0x180004dbe  pop     rdi
0x180004dbf  pop     rsi
0x180004dc0  retn
```
