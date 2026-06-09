# CiGetFileResourceInformation

- ea: `0x1800e46ac`
- end: `0x1800e47d5`
- name: `CiGetFileResourceInformation`
- size: `297`
- prototype: `__int64 __fastcall(PVOID BaseAddress, ULONGLONG Size)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000edb0`

## callees

- `0x18000cf48`
- `0x18005a1bc`
- `0x1800e46ac`

## import_xrefs

- `ntoskrnl!LdrResFindResource` at `0x1800e4717`
- `ntoskrnl!LdrResFindResource` at `0x1800e4717`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800e475c`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800e475c`

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
0x1800e46ac  mov     r11, rsp
0x1800e46af  mov     [r11+8], rbx
0x1800e46b3  mov     [r11+10h], rsi
0x1800e46b7  push    rdi
0x1800e46b8  sub     rsp, 70h
0x1800e46bc  mov     rdi, r8
0x1800e46bf  mov     esi, edx
0x1800e46c1  mov     rbx, rcx
0x1800e46c4  mov     qword ptr [r11-10h], 0
0x1800e46cc  mov     qword ptr [r11-20h], 0
0x1800e46d4  mov     qword ptr [r11-18h], 0
0x1800e46dc  mov     dword ptr [r11+20h], 0
0x1800e46e4  mov     [rsp+78h+var_38], 0
0x1800e46ec  mov     qword ptr [r11-40h], 0
0x1800e46f4  mov     qword ptr [r11-48h], 0
0x1800e46fc  lea     rax, [r11-18h]
0x1800e4700  mov     [r11-50h], rax
0x1800e4704  lea     rax, [r11-20h]
0x1800e4708  mov     [r11-58h], rax
0x1800e470c  xor     r9d, r9d
0x1800e470f  lea     edx, [r9+10h]
0x1800e4713  lea     r8d, [r9+1]
0x1800e4717  call    cs:__imp_LdrResFindResource
0x1800e471e  nop     dword ptr [rax+rax+00h]
0x1800e4723  mov     [rsp+78h+var_28], eax
0x1800e4727  test    eax, eax
0x1800e4729  jns     short loc_1800E474F
0x1800e472b  lea     ecx, [rax+3FFFFF77h]
0x1800e4731  cmp     ecx, 2
0x1800e4734  jbe     short loc_1800E473D
0x1800e4736  cmp     eax, 0C0000204h
0x1800e473b  jnz     short loc_1800E474D
0x1800e473d  xorps   xmm0, xmm0
0x1800e4740  xor     eax, eax
0x1800e4742  movups  xmmword ptr [rdi], xmm0
0x1800e4745  mov     [rdi+10h], rax
0x1800e4749  mov     [rsp+78h+var_28], eax
0x1800e474d  jmp     short loc_1800E47C2
0x1800e474f  mov     r8, rsi; Size
0x1800e4752  lea     r9, [rsp+78h+NtHeader]; NtHeader
0x1800e4757  mov     rdx, rbx; BaseAddress
0x1800e475a  xor     ecx, ecx; Flags
0x1800e475c  call    cs:__imp_RtlImageNtHeaderEx
0x1800e4763  nop     dword ptr [rax+rax+00h]
0x1800e4768  mov     [rsp+78h+var_28], eax
0x1800e476c  test    eax, eax
0x1800e476e  js      short loc_1800E47C2
0x1800e4770  mov     r9, [rsp+78h+var_20]
0x1800e4775  sub     r9, rbx
0x1800e4778  mov     eax, 0FFFFFFFFh
0x1800e477d  cmp     r9, rax
0x1800e4780  ja      short loc_1800E47B7
0x1800e4782  lea     rdx, [rsp+78h+pulResult]; pulResult
0x1800e478a  mov     rcx, [rsp+78h+ullOperand]; ullOperand
0x1800e478f  call    RtlULongLongToULong
0x1800e4794  test    eax, eax
0x1800e4796  js      short loc_1800E47C2
0x1800e4798  mov     r8d, r9d
0x1800e479b  mov     [rsp+78h+var_58], rdi
0x1800e47a0  mov     r9d, [rsp+78h+pulResult]
0x1800e47a8  mov     rdx, rbx
0x1800e47ab  mov     rcx, [rsp+78h+NtHeader]
0x1800e47b0  call    CiCopyRvaAndSizeToPageHashVerifyBuffer
0x1800e47b5  jmp     short loc_1800E47C2
0x1800e47b7  mov     eax, 0C0000095h
0x1800e47bc  jmp     short loc_1800E47C2
0x1800e47be  mov     [rsp+78h+var_28], eax
0x1800e47c2  lea     r11, [rsp+78h+var_8]
0x1800e47c7  mov     rbx, [r11+10h]
0x1800e47cb  mov     rsi, [r11+18h]
0x1800e47cf  mov     rsp, r11
0x1800e47d2  pop     rdi
0x1800e47d3  retn
```
