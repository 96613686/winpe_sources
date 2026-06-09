# _write_internal

- ea: `0x18001cb24`
- end: `0x18001cc43`
- name: `_write_internal`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001bbd4`

## callees

- `0x180014e3c`
- `0x18001bde4`
- `0x18001be14`
- `0x18001cb24`
- `0x18001cc4c`

## pseudocode

```c
__int64 __fastcall write_internal(unsigned int a1, wchar_t *a2, unsigned int a3, __int64 dwErrCode)
{
  unsigned __int64 v8; // r15
  unsigned int v9; // r14d
  __int64 v11; // [rsp+30h] [rbp-48h]

  if ( a1 == -2 )
  {
    *(_BYTE *)(dwErrCode + 56) = 1;
    *(_DWORD *)(dwErrCode + 52) = 0;
    *(_BYTE *)(dwErrCode + 48) = 1;
    *(_DWORD *)(dwErrCode + 44) = 9;
    return 0xFFFFFFFFLL;
  }
  if ( (a1 & 0x80000000) != 0
    || a1 >= nhandle
    || (v8 = (unsigned __int64)(int)a1 >> 6,
        v11 = 9LL * (a1 & 0x3F),
        (*(_BYTE *)(_pioinfo[v8] + 72LL * (a1 & 0x3F) + 56) & 1) == 0) )
  {
    *(_BYTE *)(dwErrCode + 56) = 1;
    *(_DWORD *)(dwErrCode + 52) = 0;
    *(_BYTE *)(dwErrCode + 48) = 1;
    *(_DWORD *)(dwErrCode + 44) = 9;
    invalid_parameter_internal(0, 0, 0, 0, 0, dwErrCode);
    return 0xFFFFFFFFLL;
  }
  _acrt_lowio_lock_fh(a1);
  v9 = -1;
  if ( (*(_BYTE *)(_pioinfo[v8] + 8 * v11 + 56) & 1) != 0 )
  {
    v9 = write_nolock(a1, a2, a3, dwErrCode);
  }
  else
  {
    *(_BYTE *)(dwErrCode + 48) = 1;
    *(_DWORD *)(dwErrCode + 44) = 9;
    *(_BYTE *)(dwErrCode + 56) = 1;
    *(_DWORD *)(dwErrCode + 52) = 0;
  }
  _acrt_lowio_unlock_fh(a1);
  return v9;
}

```

## disassembly

```asm
0x18001cb24  mov     [rsp+arg_0], ecx
0x18001cb28  push    rbx
0x18001cb29  push    rdi
0x18001cb2a  push    r12
0x18001cb2c  push    r13
0x18001cb2e  push    r14
0x18001cb30  push    r15
0x18001cb32  sub     rsp, 48h
0x18001cb36  mov     rbx, r9
0x18001cb39  mov     r12d, r8d
0x18001cb3c  mov     r13, rdx
0x18001cb3f  movsxd  rdi, ecx
0x18001cb42  cmp     edi, 0FFFFFFFEh
0x18001cb45  jnz     short loc_18001CB66
0x18001cb47  mov     byte ptr [r9+38h], 1
0x18001cb4c  mov     dword ptr [r9+34h], 0
0x18001cb54  mov     byte ptr [r9+30h], 1
0x18001cb59  mov     dword ptr [r9+2Ch], 9
0x18001cb61  jmp     loc_18001CC31
0x18001cb66  test    ecx, ecx
0x18001cb68  js      loc_18001CBFA
0x18001cb6e  cmp     edi, cs:_nhandle
0x18001cb74  jnb     loc_18001CBFA
0x18001cb7a  mov     r15, rdi
0x18001cb7d  shr     r15, 6
0x18001cb81  lea     rdx, __pioinfo
0x18001cb88  mov     eax, edi
0x18001cb8a  and     eax, 3Fh
0x18001cb8d  lea     rcx, [rax+rax*8]
0x18001cb91  mov     [rsp+78h+var_48], rcx
0x18001cb96  mov     rax, [rdx+r15*8]
0x18001cb9a  test    byte ptr [rax+rcx*8+38h], 1
0x18001cb9f  jz      short loc_18001CBFA
0x18001cba1  mov     ecx, edi
0x18001cba3  call    __acrt_lowio_lock_fh
0x18001cba8  or      r14d, 0FFFFFFFFh
0x18001cbac  lea     rax, __pioinfo
0x18001cbb3  mov     rax, [rax+r15*8]
0x18001cbb7  mov     rcx, [rsp+78h+var_48]
0x18001cbbc  test    byte ptr [rax+rcx*8+38h], 1
0x18001cbc1  jnz     short loc_18001CBDB
0x18001cbc3  mov     byte ptr [rbx+30h], 1
0x18001cbc7  mov     dword ptr [rbx+2Ch], 9
0x18001cbce  mov     byte ptr [rbx+38h], 1
0x18001cbd2  mov     dword ptr [rbx+34h], 0
0x18001cbd9  jmp     short loc_18001CBEE
0x18001cbdb  mov     r9, rbx
0x18001cbde  mov     r8d, r12d
0x18001cbe1  mov     rdx, r13
0x18001cbe4  mov     ecx, edi
0x18001cbe6  call    _write_nolock
0x18001cbeb  mov     r14d, eax
0x18001cbee  mov     ecx, edi
0x18001cbf0  call    __acrt_lowio_unlock_fh
0x18001cbf5  mov     eax, r14d
0x18001cbf8  jmp     short loc_18001CC34
0x18001cbfa  mov     qword ptr [rsp+78h+dwErrCode], rbx; dwErrCode
0x18001cbff  mov     byte ptr [r9+38h], 1
0x18001cc04  mov     dword ptr [r9+34h], 0
0x18001cc0c  mov     byte ptr [r9+30h], 1
0x18001cc11  mov     dword ptr [r9+2Ch], 9
0x18001cc19  mov     [rsp+78h+var_58], 0; uintptr_t
0x18001cc22  xor     r9d, r9d; LineNo
0x18001cc25  xor     r8d, r8d; FileName
0x18001cc28  xor     edx, edx; FunctionName
0x18001cc2a  xor     ecx, ecx; Expression
0x18001cc2c  call    _invalid_parameter_internal
0x18001cc31  or      eax, 0FFFFFFFFh
0x18001cc34  add     rsp, 48h
0x18001cc38  pop     r15
0x18001cc3a  pop     r14
0x18001cc3c  pop     r13
0x18001cc3e  pop     r12
0x18001cc40  pop     rdi
0x18001cc41  pop     rbx
0x18001cc42  retn
0x180025f81  push    rbp
0x180025f83  sub     rsp, 30h
0x180025f87  mov     rbp, rdx
0x180025f8a  mov     ecx, [rbp+80h]
0x180025f90  add     rsp, 30h
0x180025f94  pop     rbp
0x180025f95  jmp     __acrt_lowio_unlock_fh
```
