# SIPolicyCanLoadResources

- ea: `0x1800a47f0`
- end: `0x1800a491a`
- name: `SIPolicyCanLoadResources`
- size: `298`
- prototype: `__int64 __fastcall(PVOID BaseAddress, ULONGLONG Size)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800a4240`

## callees

- `0x1800a47f0`
- `0x1800a4b3c`
- `0x1800e3d28`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800a481d`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800a481d`

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
0x1800a47f0  mov     rax, rsp
0x1800a47f3  mov     [rax+8], rbx
0x1800a47f7  mov     [rax+10h], rsi
0x1800a47fb  push    rdi
0x1800a47fc  sub     rsp, 40h
0x1800a4800  mov     sil, r8b
0x1800a4803  mov     rbx, rdx
0x1800a4806  mov     rdi, rcx
0x1800a4809  mov     qword ptr [rax+20h], 0
0x1800a4811  lea     r9, [rax+20h]; NtHeader
0x1800a4815  mov     r8, rdx; Size
0x1800a4818  mov     rdx, rcx; BaseAddress
0x1800a481b  xor     ecx, ecx; Flags
0x1800a481d  call    cs:__imp_RtlImageNtHeaderEx
0x1800a4824  nop     dword ptr [rax+rax+00h]
0x1800a4829  mov     [rsp+48h+var_18], eax
0x1800a482d  test    eax, eax
0x1800a482f  js      loc_1800A4903
0x1800a4835  mov     r9d, 1Ah
0x1800a483b  mov     r8, [rsp+48h+arg_18]
0x1800a4840  mov     rdx, rbx
0x1800a4843  mov     rcx, rdi
0x1800a4846  call    SIPolicyIsBlockWithinImage
0x1800a484b  mov     [rsp+48h+var_18], eax
0x1800a484f  test    eax, eax
0x1800a4851  js      loc_1800A4903
0x1800a4857  movzx   eax, word ptr [r8+18h]
0x1800a485c  mov     ecx, 10Bh
0x1800a4861  cmp     ax, cx
0x1800a4864  jnz     short loc_1800A488B
0x1800a4866  lea     r9d, [rcx-13h]
0x1800a486a  mov     rcx, rdi
0x1800a486d  call    SIPolicyIsBlockWithinImage
0x1800a4872  mov     [rsp+48h+var_18], eax
0x1800a4876  test    eax, eax
0x1800a4878  js      loc_1800A4903
0x1800a487e  mov     edx, [r8+74h]
0x1800a4882  mov     rax, [r8+88h]
0x1800a4889  jmp     short loc_1800A48BC
0x1800a488b  mov     ecx, 20Bh
0x1800a4890  cmp     ax, cx
0x1800a4893  jnz     short loc_1800A48FA
0x1800a4895  mov     r9d, 108h
0x1800a489b  mov     rdx, rbx
0x1800a489e  mov     rcx, rdi
0x1800a48a1  call    SIPolicyIsBlockWithinImage
0x1800a48a6  mov     [rsp+48h+var_18], eax
0x1800a48aa  test    eax, eax
0x1800a48ac  js      short loc_1800A4903
0x1800a48ae  mov     edx, [r8+84h]
0x1800a48b5  mov     rax, [r8+98h]
0x1800a48bc  mov     rcx, rax
0x1800a48bf  mov     [rsp+48h+var_10], rax
0x1800a48c4  cmp     edx, 2
0x1800a48c7  jbe     short loc_1800A48F3
0x1800a48c9  test    eax, eax
0x1800a48cb  jz      short loc_1800A48F3
0x1800a48cd  shr     rcx, 20h
0x1800a48d1  test    ecx, ecx
0x1800a48d3  jz      short loc_1800A48F3
0x1800a48d5  lea     rcx, [rsp+48h+var_10]
0x1800a48da  mov     [rsp+48h+var_20], rcx
0x1800a48df  mov     [rsp+48h+var_28], eax
0x1800a48e3  mov     r9b, sil
0x1800a48e6  mov     rdx, rbx
0x1800a48e9  mov     rcx, rdi
0x1800a48ec  call    SIPolicyFindNtSection
0x1800a48f1  jmp     short loc_1800A48FF
0x1800a48f3  mov     eax, 0C0000225h
0x1800a48f8  jmp     short loc_1800A48FF
0x1800a48fa  mov     eax, 0C000007Bh
0x1800a48ff  mov     [rsp+48h+var_18], eax
0x1800a4903  jmp     short loc_1800A4909
0x1800a4905  mov     [rsp+48h+var_18], eax
0x1800a4909  mov     rbx, [rsp+48h+arg_0]
0x1800a490e  mov     rsi, [rsp+48h+arg_8]
0x1800a4913  add     rsp, 40h
0x1800a4917  pop     rdi
0x1800a4918  retn
```
