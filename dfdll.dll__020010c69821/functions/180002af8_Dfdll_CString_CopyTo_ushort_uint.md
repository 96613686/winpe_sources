# Dfdll::CString::CopyTo(ushort *,uint &)

- ea: `0x180002af8`
- end: `0x180002b80`
- name: `?CopyTo@CString@Dfdll@@QEAAJPEAGAEAI@Z`
- size: `136`
- prototype: `int(Dfdll::CString *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006180`
- `0x180006e60`
- `0x180007130`
- `0x1800073d0`
- `0x18000dadc`

## callees

- `0x180002af8`
- `0x1800043d8`

## pseudocode

```c
__int64 __fastcall Dfdll::CString::CopyTo(Dfdll::CString *this, unsigned __int16 *a2, unsigned int *a3)
{
  __int64 result; // rax
  unsigned int v6; // eax
  int v7; // eax

  if ( !a2 )
    return 2147942487LL;
  v6 = *((_DWORD *)this + 8);
  if ( v6 < *a3 )
  {
    if ( v6 || !*a3 )
    {
      result = StringCchCopyNW(a2, *a3, *((const unsigned __int16 **)this + 2), *((unsigned int *)this + 8));
      if ( (int)result < 0 )
        return result;
    }
    else
    {
      *a2 = 0;
    }
    v7 = *((_DWORD *)this + 8);
    if ( v7 == -1 )
      return 2147942934LL;
    *a3 = v7 + 1;
    return 0;
  }
  else
  {
    if ( v6 == -1 )
      return 2147942934LL;
    *a3 = v6 + 1;
    return 2147942522LL;
  }
}

```

## disassembly

```asm
0x180002af8  mov     [rsp+arg_0], rbx
0x180002afd  mov     [rsp+arg_8], rsi
0x180002b02  push    rdi
0x180002b03  sub     rsp, 20h
0x180002b07  xor     esi, esi
0x180002b09  mov     rbx, r8
0x180002b0c  mov     r10, rdx
0x180002b0f  mov     rdi, rcx
0x180002b12  test    rdx, rdx
0x180002b15  jnz     short loc_180002B1E
0x180002b17  mov     eax, 80070057h
0x180002b1c  jmp     short loc_180002B70
0x180002b1e  mov     eax, [rcx+20h]
0x180002b21  cmp     eax, [r8]
0x180002b24  jb      short loc_180002B3E
0x180002b26  cmp     eax, 0FFFFFFFEh
0x180002b29  jbe     short loc_180002B32
0x180002b2b  mov     eax, 80070216h
0x180002b30  jmp     short loc_180002B70
0x180002b32  inc     eax
0x180002b34  mov     [r8], eax
0x180002b37  mov     eax, 8007007Ah
0x180002b3c  jmp     short loc_180002B70
0x180002b3e  test    eax, eax
0x180002b40  jnz     short loc_180002B4C
0x180002b42  cmp     [r8], esi
0x180002b45  jbe     short loc_180002B4C
0x180002b47  mov     [rdx], si
0x180002b4a  jmp     short loc_180002B62
0x180002b4c  mov     edx, [r8]; unsigned __int64
0x180002b4f  mov     r9, rax; unsigned __int64
0x180002b52  mov     r8, [rcx+10h]; unsigned __int16 *
0x180002b56  mov     rcx, r10; unsigned __int16 *
0x180002b59  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180002b5e  test    eax, eax
0x180002b60  js      short loc_180002B70
0x180002b62  mov     eax, [rdi+20h]
0x180002b65  cmp     eax, 0FFFFFFFEh
0x180002b68  ja      short loc_180002B2B
0x180002b6a  inc     eax
0x180002b6c  mov     [rbx], eax
0x180002b6e  mov     eax, esi
0x180002b70  mov     rbx, [rsp+28h+arg_0]
0x180002b75  mov     rsi, [rsp+28h+arg_8]
0x180002b7a  add     rsp, 20h
0x180002b7e  pop     rdi
0x180002b7f  retn
```
