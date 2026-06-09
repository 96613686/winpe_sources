# SIPolicyCanLoadResources

- ea: `0x1800a31c0`
- end: `0x1800a32ea`
- name: `SIPolicyCanLoadResources`
- size: `298`
- prototype: `__int64 __fastcall(PVOID BaseAddress, ULONGLONG Size)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800a2c10`

## callees

- `0x1800a31c0`
- `0x1800a350c`
- `0x1800e3d38`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800a31ed`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800a31ed`

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
0x1800a31c0  mov     rax, rsp
0x1800a31c3  mov     [rax+8], rbx
0x1800a31c7  mov     [rax+10h], rsi
0x1800a31cb  push    rdi
0x1800a31cc  sub     rsp, 40h
0x1800a31d0  mov     sil, r8b
0x1800a31d3  mov     rbx, rdx
0x1800a31d6  mov     rdi, rcx
0x1800a31d9  mov     qword ptr [rax+20h], 0
0x1800a31e1  lea     r9, [rax+20h]; NtHeader
0x1800a31e5  mov     r8, rdx; Size
0x1800a31e8  mov     rdx, rcx; BaseAddress
0x1800a31eb  xor     ecx, ecx; Flags
0x1800a31ed  call    cs:__imp_RtlImageNtHeaderEx
0x1800a31f4  nop     dword ptr [rax+rax+00h]
0x1800a31f9  mov     [rsp+48h+var_18], eax
0x1800a31fd  test    eax, eax
0x1800a31ff  js      loc_1800A32D3
0x1800a3205  mov     r9d, 1Ah
0x1800a320b  mov     r8, [rsp+48h+arg_18]
0x1800a3210  mov     rdx, rbx
0x1800a3213  mov     rcx, rdi
0x1800a3216  call    SIPolicyIsBlockWithinImage
0x1800a321b  mov     [rsp+48h+var_18], eax
0x1800a321f  test    eax, eax
0x1800a3221  js      loc_1800A32D3
0x1800a3227  movzx   eax, word ptr [r8+18h]
0x1800a322c  mov     ecx, 10Bh
0x1800a3231  cmp     ax, cx
0x1800a3234  jnz     short loc_1800A325B
0x1800a3236  lea     r9d, [rcx-13h]
0x1800a323a  mov     rcx, rdi
0x1800a323d  call    SIPolicyIsBlockWithinImage
0x1800a3242  mov     [rsp+48h+var_18], eax
0x1800a3246  test    eax, eax
0x1800a3248  js      loc_1800A32D3
0x1800a324e  mov     edx, [r8+74h]
0x1800a3252  mov     rax, [r8+88h]
0x1800a3259  jmp     short loc_1800A328C
0x1800a325b  mov     ecx, 20Bh
0x1800a3260  cmp     ax, cx
0x1800a3263  jnz     short loc_1800A32CA
0x1800a3265  mov     r9d, 108h
0x1800a326b  mov     rdx, rbx
0x1800a326e  mov     rcx, rdi
0x1800a3271  call    SIPolicyIsBlockWithinImage
0x1800a3276  mov     [rsp+48h+var_18], eax
0x1800a327a  test    eax, eax
0x1800a327c  js      short loc_1800A32D3
0x1800a327e  mov     edx, [r8+84h]
0x1800a3285  mov     rax, [r8+98h]
0x1800a328c  mov     rcx, rax
0x1800a328f  mov     [rsp+48h+var_10], rax
0x1800a3294  cmp     edx, 2
0x1800a3297  jbe     short loc_1800A32C3
0x1800a3299  test    eax, eax
0x1800a329b  jz      short loc_1800A32C3
0x1800a329d  shr     rcx, 20h
0x1800a32a1  test    ecx, ecx
0x1800a32a3  jz      short loc_1800A32C3
0x1800a32a5  lea     rcx, [rsp+48h+var_10]
0x1800a32aa  mov     [rsp+48h+var_20], rcx
0x1800a32af  mov     [rsp+48h+var_28], eax
0x1800a32b3  mov     r9b, sil
0x1800a32b6  mov     rdx, rbx
0x1800a32b9  mov     rcx, rdi
0x1800a32bc  call    SIPolicyFindNtSection
0x1800a32c1  jmp     short loc_1800A32CF
0x1800a32c3  mov     eax, 0C0000225h
0x1800a32c8  jmp     short loc_1800A32CF
0x1800a32ca  mov     eax, 0C000007Bh
0x1800a32cf  mov     [rsp+48h+var_18], eax
0x1800a32d3  jmp     short loc_1800A32D9
0x1800a32d5  mov     [rsp+48h+var_18], eax
0x1800a32d9  mov     rbx, [rsp+48h+arg_0]
0x1800a32de  mov     rsi, [rsp+48h+arg_8]
0x1800a32e3  add     rsp, 40h
0x1800a32e7  pop     rdi
0x1800a32e8  retn
```
