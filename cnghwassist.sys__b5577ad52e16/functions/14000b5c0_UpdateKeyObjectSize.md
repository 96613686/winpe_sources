# UpdateKeyObjectSize

- ea: `0x14000b5c0`
- end: `0x14000b631`
- name: `UpdateKeyObjectSize`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000b1c0`

## callees

- `0x140003e00`
- `0x14000b5c0`

## pseudocode

```c
__int64 __fastcall UpdateKeyObjectSize(__int64 a1)
{
  __int64 (__fastcall *v1)(__int64, const wchar_t *, int *, __int64, int *, _DWORD); // rax
  __int64 result; // rax
  int v3; // [rsp+58h] [rbp+10h] BYREF
  int v4; // [rsp+60h] [rbp+18h] BYREF

  v4 = 0;
  v1 = *(__int64 (__fastcall **)(__int64, const wchar_t *, int *, __int64, int *, _DWORD))(g_pHwCipherFunctionTable + 16);
  v3 = 0;
  result = v1(a1, L"ObjectLength", &v4, 4, &v3, 0);
  if ( (int)result >= 0 && v3 == 4 )
  {
    result = (v4 + 15) & 0xFFFFFFF0;
    if ( (unsigned int)g_cbHardwareKeyObjectSize <= (unsigned int)result )
      LODWORD(g_cbHardwareKeyObjectSize) = (v4 + 15) & 0xFFFFFFF0;
  }
  return result;
}

```

## disassembly

```asm
0x14000b5c0  sub     rsp, 48h
0x14000b5c4  mov     rax, cs:g_pHwCipherFunctionTable
0x14000b5cb  lea     rdx, [rsp+48h+arg_8]
0x14000b5d0  mov     [rsp+48h+var_20], 0
0x14000b5d8  lea     r8, [rsp+48h+arg_10]
0x14000b5dd  mov     [rsp+48h+var_28], rdx
0x14000b5e2  mov     r9d, 4
0x14000b5e8  lea     rdx, aObjectlength; "ObjectLength"
0x14000b5ef  mov     [rsp+48h+arg_10], 0
0x14000b5f7  mov     rax, [rax+10h]
0x14000b5fb  mov     [rsp+48h+arg_8], 0
0x14000b603  call    _guard_dispatch_icall
0x14000b608  test    eax, eax
0x14000b60a  js      short loc_14000B62B
0x14000b60c  cmp     [rsp+48h+arg_8], 4
0x14000b611  jnz     short loc_14000B62B
0x14000b613  mov     eax, [rsp+48h+arg_10]
0x14000b617  add     eax, 0Fh
0x14000b61a  and     eax, 0FFFFFFF0h
0x14000b61d  cmp     cs:g_cbHardwareKeyObjectSize, eax
0x14000b623  ja      short loc_14000B62B
0x14000b625  mov     cs:g_cbHardwareKeyObjectSize, eax
0x14000b62b  add     rsp, 48h
0x14000b62f  retn
```
