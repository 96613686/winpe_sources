# CiGetFileResourceInformation

- ea: `0x1800e413c`
- end: `0x1800e4265`
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
- `0x18005957c`
- `0x1800e413c`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800e41ec`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800e41ec`
- `ntoskrnl!LdrResFindResource` at `0x1800e41a7`
- `ntoskrnl!LdrResFindResource` at `0x1800e41a7`

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
0x1800e413c  mov     r11, rsp
0x1800e413f  mov     [r11+8], rbx
0x1800e4143  mov     [r11+10h], rsi
0x1800e4147  push    rdi
0x1800e4148  sub     rsp, 70h
0x1800e414c  mov     rdi, r8
0x1800e414f  mov     esi, edx
0x1800e4151  mov     rbx, rcx
0x1800e4154  mov     qword ptr [r11-10h], 0
0x1800e415c  mov     qword ptr [r11-20h], 0
0x1800e4164  mov     qword ptr [r11-18h], 0
0x1800e416c  mov     dword ptr [r11+20h], 0
0x1800e4174  mov     [rsp+78h+var_38], 0
0x1800e417c  mov     qword ptr [r11-40h], 0
0x1800e4184  mov     qword ptr [r11-48h], 0
0x1800e418c  lea     rax, [r11-18h]
0x1800e4190  mov     [r11-50h], rax
0x1800e4194  lea     rax, [r11-20h]
0x1800e4198  mov     [r11-58h], rax
0x1800e419c  xor     r9d, r9d
0x1800e419f  lea     edx, [r9+10h]
0x1800e41a3  lea     r8d, [r9+1]
0x1800e41a7  call    cs:__imp_LdrResFindResource
0x1800e41ae  nop     dword ptr [rax+rax+00h]
0x1800e41b3  mov     [rsp+78h+var_28], eax
0x1800e41b7  test    eax, eax
0x1800e41b9  jns     short loc_1800E41DF
0x1800e41bb  lea     ecx, [rax+3FFFFF77h]
0x1800e41c1  cmp     ecx, 2
0x1800e41c4  jbe     short loc_1800E41CD
0x1800e41c6  cmp     eax, 0C0000204h
0x1800e41cb  jnz     short loc_1800E41DD
0x1800e41cd  xorps   xmm0, xmm0
0x1800e41d0  xor     eax, eax
0x1800e41d2  movups  xmmword ptr [rdi], xmm0
0x1800e41d5  mov     [rdi+10h], rax
0x1800e41d9  mov     [rsp+78h+var_28], eax
0x1800e41dd  jmp     short loc_1800E4252
0x1800e41df  mov     r8, rsi; Size
0x1800e41e2  lea     r9, [rsp+78h+NtHeader]; NtHeader
0x1800e41e7  mov     rdx, rbx; BaseAddress
0x1800e41ea  xor     ecx, ecx; Flags
0x1800e41ec  call    cs:__imp_RtlImageNtHeaderEx
0x1800e41f3  nop     dword ptr [rax+rax+00h]
0x1800e41f8  mov     [rsp+78h+var_28], eax
0x1800e41fc  test    eax, eax
0x1800e41fe  js      short loc_1800E4252
0x1800e4200  mov     r9, [rsp+78h+var_20]
0x1800e4205  sub     r9, rbx
0x1800e4208  mov     eax, 0FFFFFFFFh
0x1800e420d  cmp     r9, rax
0x1800e4210  ja      short loc_1800E4247
0x1800e4212  lea     rdx, [rsp+78h+pulResult]; pulResult
0x1800e421a  mov     rcx, [rsp+78h+ullOperand]; ullOperand
0x1800e421f  call    RtlULongLongToULong
0x1800e4224  test    eax, eax
0x1800e4226  js      short loc_1800E4252
0x1800e4228  mov     r8d, r9d
0x1800e422b  mov     [rsp+78h+var_58], rdi
0x1800e4230  mov     r9d, [rsp+78h+pulResult]
0x1800e4238  mov     rdx, rbx
0x1800e423b  mov     rcx, [rsp+78h+NtHeader]
0x1800e4240  call    CiCopyRvaAndSizeToPageHashVerifyBuffer
0x1800e4245  jmp     short loc_1800E4252
0x1800e4247  mov     eax, 0C0000095h
0x1800e424c  jmp     short loc_1800E4252
0x1800e424e  mov     [rsp+78h+var_28], eax
0x1800e4252  lea     r11, [rsp+78h+var_8]
0x1800e4257  mov     rbx, [r11+10h]
0x1800e425b  mov     rsi, [r11+18h]
0x1800e425f  mov     rsp, r11
0x1800e4262  pop     rdi
0x1800e4263  retn
```
