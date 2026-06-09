# SIPolicyCanLoadResources

- ea: `0x1800c1c9c`
- end: `0x1800c1dc6`
- name: `SIPolicyCanLoadResources`
- size: `298`
- prototype: `__int64 __fastcall(PVOID BaseAddress, ULONGLONG Size)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800a46e0`

## callees

- `0x1800c1c9c`
- `0x1800c1dcc`
- `0x1800e42a8`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800c1cc9`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800c1cc9`

## pseudocode

```c
NTSTATUS __fastcall SIPolicyCanLoadResources(PVOID BaseAddress, ULONGLONG Size, char a3)
{
  NTSTATUS result; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int16 v9; // ax
  __int64 v10; // r8
  int v11; // r9d
  unsigned int v12; // edx
  __int64 v13; // rax
  __int64 v14; // [rsp+38h] [rbp-10h] BYREF
  PIMAGE_NT_HEADERS v15; // [rsp+68h] [rbp+20h] BYREF

  v15 = 0;
  result = RtlImageNtHeaderEx(0, BaseAddress, Size, &v15);
  if ( result >= 0 )
  {
    result = SIPolicyIsBlockWithinImage(BaseAddress, Size, v15, 26);
    if ( result >= 0 )
    {
      v9 = *(_WORD *)(v8 + 24);
      if ( v9 == 267 )
      {
        result = SIPolicyIsBlockWithinImage(BaseAddress, v7, v8, 248);
        if ( result < 0 )
          return result;
        v12 = *(_DWORD *)(v10 + 116);
        v13 = *(_QWORD *)(v10 + 136);
      }
      else
      {
        if ( v9 != 523 )
          return -1073741701;
        result = SIPolicyIsBlockWithinImage(BaseAddress, Size, v8, 264);
        if ( result < 0 )
          return result;
        v12 = *(_DWORD *)(v10 + 132);
        v13 = *(_QWORD *)(v10 + 152);
      }
      v14 = v13;
      if ( v12 > 2 && (_DWORD)v13 && HIDWORD(v13) )
      {
        LOBYTE(v11) = a3;
        return SIPolicyFindNtSection((_DWORD)BaseAddress, Size, v10, v11, v13, (__int64)&v14);
      }
      else
      {
        return -1073741275;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800c1c9c  mov     rax, rsp
0x1800c1c9f  mov     [rax+8], rbx
0x1800c1ca3  mov     [rax+10h], rsi
0x1800c1ca7  push    rdi
0x1800c1ca8  sub     rsp, 40h
0x1800c1cac  mov     sil, r8b
0x1800c1caf  mov     rbx, rdx
0x1800c1cb2  mov     rdi, rcx
0x1800c1cb5  mov     qword ptr [rax+20h], 0
0x1800c1cbd  lea     r9, [rax+20h]; NtHeader
0x1800c1cc1  mov     r8, rdx; Size
0x1800c1cc4  mov     rdx, rcx; BaseAddress
0x1800c1cc7  xor     ecx, ecx; Flags
0x1800c1cc9  call    cs:__imp_RtlImageNtHeaderEx
0x1800c1cd0  nop     dword ptr [rax+rax+00h]
0x1800c1cd5  mov     [rsp+48h+var_18], eax
0x1800c1cd9  test    eax, eax
0x1800c1cdb  js      loc_1800C1DAF
0x1800c1ce1  mov     r9d, 1Ah
0x1800c1ce7  mov     r8, [rsp+48h+arg_18]
0x1800c1cec  mov     rdx, rbx
0x1800c1cef  mov     rcx, rdi
0x1800c1cf2  call    SIPolicyIsBlockWithinImage
0x1800c1cf7  mov     [rsp+48h+var_18], eax
0x1800c1cfb  test    eax, eax
0x1800c1cfd  js      loc_1800C1DAF
0x1800c1d03  movzx   eax, word ptr [r8+18h]
0x1800c1d08  mov     ecx, 10Bh
0x1800c1d0d  cmp     ax, cx
0x1800c1d10  jnz     short loc_1800C1D37
0x1800c1d12  lea     r9d, [rcx-13h]
0x1800c1d16  mov     rcx, rdi
0x1800c1d19  call    SIPolicyIsBlockWithinImage
0x1800c1d1e  mov     [rsp+48h+var_18], eax
0x1800c1d22  test    eax, eax
0x1800c1d24  js      loc_1800C1DAF
0x1800c1d2a  mov     edx, [r8+74h]
0x1800c1d2e  mov     rax, [r8+88h]
0x1800c1d35  jmp     short loc_1800C1D68
0x1800c1d37  mov     ecx, 20Bh
0x1800c1d3c  cmp     ax, cx
0x1800c1d3f  jnz     short loc_1800C1DA6
0x1800c1d41  mov     r9d, 108h
0x1800c1d47  mov     rdx, rbx
0x1800c1d4a  mov     rcx, rdi
0x1800c1d4d  call    SIPolicyIsBlockWithinImage
0x1800c1d52  mov     [rsp+48h+var_18], eax
0x1800c1d56  test    eax, eax
0x1800c1d58  js      short loc_1800C1DAF
0x1800c1d5a  mov     edx, [r8+84h]
0x1800c1d61  mov     rax, [r8+98h]
0x1800c1d68  mov     rcx, rax
0x1800c1d6b  mov     [rsp+48h+var_10], rax
0x1800c1d70  cmp     edx, 2
0x1800c1d73  jbe     short loc_1800C1D9F
0x1800c1d75  test    eax, eax
0x1800c1d77  jz      short loc_1800C1D9F
0x1800c1d79  shr     rcx, 20h
0x1800c1d7d  test    ecx, ecx
0x1800c1d7f  jz      short loc_1800C1D9F
0x1800c1d81  lea     rcx, [rsp+48h+var_10]
0x1800c1d86  mov     [rsp+48h+var_20], rcx
0x1800c1d8b  mov     [rsp+48h+var_28], eax
0x1800c1d8f  mov     r9b, sil
0x1800c1d92  mov     rdx, rbx
0x1800c1d95  mov     rcx, rdi
0x1800c1d98  call    SIPolicyFindNtSection
0x1800c1d9d  jmp     short loc_1800C1DAB
0x1800c1d9f  mov     eax, 0C0000225h
0x1800c1da4  jmp     short loc_1800C1DAB
0x1800c1da6  mov     eax, 0C000007Bh
0x1800c1dab  mov     [rsp+48h+var_18], eax
0x1800c1daf  jmp     short loc_1800C1DB5
0x1800c1db1  mov     [rsp+48h+var_18], eax
0x1800c1db5  mov     rbx, [rsp+48h+arg_0]
0x1800c1dba  mov     rsi, [rsp+48h+arg_8]
0x1800c1dbf  add     rsp, 40h
0x1800c1dc3  pop     rdi
0x1800c1dc4  retn
```
