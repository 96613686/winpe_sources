# CiGetFileResourceInformation

- ea: `0x1800e412c`
- end: `0x1800e4255`
- name: `CiGetFileResourceInformation`
- size: `297`
- prototype: `__int64 __fastcall(PVOID BaseAddress, ULONGLONG Size)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000eda0`

## callees

- `0x18000cf38`
- `0x18005a294`
- `0x1800e412c`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800e41dc`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800e41dc`
- `ntoskrnl!LdrResFindResource` at `0x1800e4197`
- `ntoskrnl!LdrResFindResource` at `0x1800e4197`

## pseudocode

```c
NTSTATUS __fastcall CiGetFileResourceInformation(__int64 BaseAddress, ULONGLONG Size, __int64 a3)
{
  ULONGLONG v4; // rsi
  NTSTATUS result; // eax
  int v7; // r9d
  PIMAGE_NT_HEADERS NtHeader; // [rsp+68h] [rbp-10h] BYREF
  ULONG pulResult; // [rsp+98h] [rbp+20h] BYREF

  v4 = (unsigned int)Size;
  NtHeader = 0;
  pulResult = 0;
  result = LdrResFindResource(BaseAddress, 16, 1);
  if ( result >= 0 )
  {
    result = RtlImageNtHeaderEx(0, (PVOID)BaseAddress, v4, &NtHeader);
    if ( result >= 0 )
    {
      if ( (unsigned __int64)-BaseAddress > 0xFFFFFFFF )
      {
        return -1073741675;
      }
      else
      {
        result = RtlULongLongToULong(0, &pulResult);
        if ( result >= 0 )
          return CiCopyRvaAndSizeToPageHashVerifyBuffer((_DWORD)NtHeader, BaseAddress, v7, pulResult, a3);
      }
    }
  }
  else if ( (unsigned int)(result + 1073741687) <= 2 || result == -1073741308 )
  {
    result = 0;
    *(_OWORD *)a3 = 0;
    *(_QWORD *)(a3 + 16) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800e412c  mov     r11, rsp
0x1800e412f  mov     [r11+8], rbx
0x1800e4133  mov     [r11+10h], rsi
0x1800e4137  push    rdi
0x1800e4138  sub     rsp, 70h
0x1800e413c  mov     rdi, r8
0x1800e413f  mov     esi, edx
0x1800e4141  mov     rbx, rcx
0x1800e4144  mov     qword ptr [r11-10h], 0
0x1800e414c  mov     qword ptr [r11-20h], 0
0x1800e4154  mov     qword ptr [r11-18h], 0
0x1800e415c  mov     dword ptr [r11+20h], 0
0x1800e4164  mov     [rsp+78h+var_38], 0
0x1800e416c  mov     qword ptr [r11-40h], 0
0x1800e4174  mov     qword ptr [r11-48h], 0
0x1800e417c  lea     rax, [r11-18h]
0x1800e4180  mov     [r11-50h], rax
0x1800e4184  lea     rax, [r11-20h]
0x1800e4188  mov     [r11-58h], rax
0x1800e418c  xor     r9d, r9d
0x1800e418f  lea     edx, [r9+10h]
0x1800e4193  lea     r8d, [r9+1]
0x1800e4197  call    cs:__imp_LdrResFindResource
0x1800e419e  nop     dword ptr [rax+rax+00h]
0x1800e41a3  mov     [rsp+78h+var_28], eax
0x1800e41a7  test    eax, eax
0x1800e41a9  jns     short loc_1800E41CF
0x1800e41ab  lea     ecx, [rax+3FFFFF77h]
0x1800e41b1  cmp     ecx, 2
0x1800e41b4  jbe     short loc_1800E41BD
0x1800e41b6  cmp     eax, 0C0000204h
0x1800e41bb  jnz     short loc_1800E41CD
0x1800e41bd  xorps   xmm0, xmm0
0x1800e41c0  xor     eax, eax
0x1800e41c2  movups  xmmword ptr [rdi], xmm0
0x1800e41c5  mov     [rdi+10h], rax
0x1800e41c9  mov     [rsp+78h+var_28], eax
0x1800e41cd  jmp     short loc_1800E4242
0x1800e41cf  mov     r8, rsi; Size
0x1800e41d2  lea     r9, [rsp+78h+NtHeader]; NtHeader
0x1800e41d7  mov     rdx, rbx; BaseAddress
0x1800e41da  xor     ecx, ecx; Flags
0x1800e41dc  call    cs:__imp_RtlImageNtHeaderEx
0x1800e41e3  nop     dword ptr [rax+rax+00h]
0x1800e41e8  mov     [rsp+78h+var_28], eax
0x1800e41ec  test    eax, eax
0x1800e41ee  js      short loc_1800E4242
0x1800e41f0  mov     r9, [rsp+78h+var_20]
0x1800e41f5  sub     r9, rbx
0x1800e41f8  mov     eax, 0FFFFFFFFh
0x1800e41fd  cmp     r9, rax
0x1800e4200  ja      short loc_1800E4237
0x1800e4202  lea     rdx, [rsp+78h+pulResult]; pulResult
0x1800e420a  mov     rcx, [rsp+78h+ullOperand]; ullOperand
0x1800e420f  call    RtlULongLongToULong
0x1800e4214  test    eax, eax
0x1800e4216  js      short loc_1800E4242
0x1800e4218  mov     r8d, r9d
0x1800e421b  mov     [rsp+78h+var_58], rdi
0x1800e4220  mov     r9d, [rsp+78h+pulResult]
0x1800e4228  mov     rdx, rbx
0x1800e422b  mov     rcx, [rsp+78h+NtHeader]
0x1800e4230  call    CiCopyRvaAndSizeToPageHashVerifyBuffer
0x1800e4235  jmp     short loc_1800E4242
0x1800e4237  mov     eax, 0C0000095h
0x1800e423c  jmp     short loc_1800E4242
0x1800e423e  mov     [rsp+78h+var_28], eax
0x1800e4242  lea     r11, [rsp+78h+var_8]
0x1800e4247  mov     rbx, [r11+10h]
0x1800e424b  mov     rsi, [r11+18h]
0x1800e424f  mov     rsp, r11
0x1800e4252  pop     rdi
0x1800e4253  retn
```
