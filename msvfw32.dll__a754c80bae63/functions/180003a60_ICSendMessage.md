# ICSendMessage

- ea: `0x180003a60`
- end: `0x180003add`
- name: `ICSendMessage`
- size: `125`
- prototype: `LONG_PTR __stdcall(HIC hic, UINT msg, DWORD_PTR dw1, DWORD_PTR dw2)`
- caller_count: `28`
- callee_count: `3`
- tags: ``

## callers

- `0x180002640`
- `0x1800026e0`
- `0x180002770`
- `0x1800029b0`
- `0x180002a00`
- `0x180002a90`
- `0x180002df0`
- `0x1800033e0`
- `0x1800035d0`
- `0x180003850`
- `0x180004590`
- `0x1800047f0`
- `0x180005cf0`
- `0x1800060a0`
- `0x180006510`
- `0x1800065e0`
- `0x1800068bc`
- `0x1800072f4`
- `0x1800074a0`
- `0x1800076c4`
- `0x180008400`
- `0x180009bb0`
- `0x18000a860`
- `0x18000aeb0`
- `0x18000b200`
- `0x18000b250`
- `0x18000b2ac`
- `0x18000b5b8`

## callees

- `0x180003a60`
- `0x180003ae4`
- `0x180017010`

## pseudocode

```c
LONG_PTR __stdcall ICSendMessage(HIC hic, UINT msg, DWORD_PTR dw1, DWORD_PTR dw2)
{
  __int64 v6; // rcx
  __int64 v7; // r9
  LONG_PTR result; // rax
  __int64 (__fastcall *v9)(_QWORD, __int64, _QWORD, DWORD_PTR, __int64); // rax

  if ( !(unsigned int)ICValid(hic, msg, dw1, dw2) )
    return -8;
  v9 = *(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, DWORD_PTR, __int64))(v6 + 40);
  if ( !v9 )
    return -4;
  result = v9(*(_QWORD *)(v6 + 32), 1, msg, dw1, v7);
  if ( result != -1 )
    return result;
  if ( msg == 16426 )
  {
    *(_DWORD *)dw1 = 15;
  }
  else
  {
    if ( msg != 20510 )
      return result;
    *(_DWORD *)dw1 = 10000;
  }
  return 0;
}

```

## disassembly

```asm
0x180003a60  mov     [rsp+arg_0], rbx
0x180003a65  push    rdi
0x180003a66  sub     rsp, 30h
0x180003a6a  mov     rbx, r8
0x180003a6d  mov     edi, edx
0x180003a6f  call    ICValid
0x180003a74  test    eax, eax
0x180003a76  jnz     short loc_180003A81
0x180003a78  mov     rax, 0FFFFFFFFFFFFFFF8h
0x180003a7f  jmp     short loc_180003AD2
0x180003a81  mov     rax, [rcx+28h]
0x180003a85  test    rax, rax
0x180003a88  jz      short loc_180003ACB
0x180003a8a  mov     rcx, [rcx+20h]
0x180003a8e  mov     r8d, edi
0x180003a91  mov     [rsp+38h+var_18], r9
0x180003a96  mov     edx, 1
0x180003a9b  mov     r9, rbx
0x180003a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aa3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003aa7  jnz     short loc_180003AD2
0x180003aa9  cmp     edi, 402Ah
0x180003aaf  jz      short loc_180003AC3
0x180003ab1  cmp     edi, 501Eh
0x180003ab7  jnz     short loc_180003AD2
0x180003ab9  mov     dword ptr [rbx], 2710h
0x180003abf  xor     eax, eax
0x180003ac1  jmp     short loc_180003AD2
0x180003ac3  mov     dword ptr [rbx], 0Fh
0x180003ac9  jmp     short loc_180003ABF
0x180003acb  mov     rax, 0FFFFFFFFFFFFFFFCh
0x180003ad2  mov     rbx, [rsp+38h+arg_0]
0x180003ad7  add     rsp, 30h
0x180003adb  pop     rdi
0x180003adc  retn
```
