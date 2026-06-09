# CipHvciFindImageLoadConfig

- ea: `0x18000f03c`
- end: `0x18000f11b`
- name: `CipHvciFindImageLoadConfig`
- size: `223`
- prototype: `__int64 __fastcall(PVOID BaseAddress, ULONGLONG Size)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800d2040`

## callees

- `0x18000f03c`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x18000f085`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x18000f085`
- `ntoskrnl!RtlImageDirectoryEntryToData` at `0x18000f0b7`
- `ntoskrnl!RtlImageDirectoryEntryToData` at `0x18000f0b7`

## pseudocode

```c
NTSTATUS __fastcall CipHvciFindImageLoadConfig(char *BaseAddress, ULONGLONG Size, char **a3, ULONG *a4)
{
  __int64 v7; // r15
  NTSTATUS result; // eax
  NTSTATUS v9; // ebx
  char *v10; // rax
  ULONG v11; // edx
  char *v12; // r8
  ULONG Sizea; // [rsp+60h] [rbp+18h] BYREF
  PIMAGE_NT_HEADERS v14; // [rsp+68h] [rbp+20h] BYREF

  Sizea = 0;
  v14 = 0;
  *a3 = 0;
  *a4 = 0;
  v7 = (unsigned int)Size;
  result = RtlImageNtHeaderEx(0, BaseAddress, (unsigned int)Size, &v14);
  v9 = result;
  if ( result >= 0 )
  {
    if ( v14->OptionalHeader.Magic == 523 )
    {
      v10 = (char *)RtlImageDirectoryEntryToData(BaseAddress, 1u, 0xAu, &Sizea);
      if ( v10 )
      {
        v11 = Sizea;
        v12 = &v10[Sizea];
        if ( v12 >= v10 && v12 <= &BaseAddress[v7] && *(_DWORD *)v10 == Sizea )
        {
          *a3 = v10;
          *a4 = v11;
          return 0;
        }
        else
        {
          return -1073741701;
        }
      }
      else
      {
        return v9;
      }
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f03c  mov     rax, rsp
0x18000f03f  mov     [rax+8], rbx
0x18000f043  mov     [rax+10h], rsi
0x18000f047  push    rdi
0x18000f048  push    r14
0x18000f04a  push    r15
0x18000f04c  sub     rsp, 30h
0x18000f050  mov     rsi, r9
0x18000f053  mov     r14, r8
0x18000f056  mov     rdi, rcx
0x18000f059  mov     dword ptr [rax+18h], 0
0x18000f060  mov     qword ptr [rax+20h], 0
0x18000f068  mov     qword ptr [r8], 0
0x18000f06f  mov     dword ptr [r9], 0
0x18000f076  mov     r15d, edx
0x18000f079  lea     r9, [rax+20h]; NtHeader
0x18000f07d  mov     r8d, edx; Size
0x18000f080  mov     rdx, rcx; BaseAddress
0x18000f083  xor     ecx, ecx; Flags
0x18000f085  call    cs:__imp_RtlImageNtHeaderEx
0x18000f08c  nop     dword ptr [rax+rax+00h]
0x18000f091  mov     ebx, eax
0x18000f093  test    eax, eax
0x18000f095  js      short loc_18000F0EC
0x18000f097  mov     ecx, 20Bh
0x18000f09c  mov     rax, [rsp+48h+arg_18]
0x18000f0a1  cmp     [rax+18h], cx
0x18000f0a5  jnz     short loc_18000F0EE
0x18000f0a7  mov     r8d, 0Ah; Directory
0x18000f0ad  lea     r9, [rsp+48h+Size]; Size
0x18000f0b2  mov     dl, 1; MappedAsImage
0x18000f0b4  mov     rcx, rdi; BaseAddress
0x18000f0b7  call    cs:__imp_RtlImageDirectoryEntryToData
0x18000f0be  nop     dword ptr [rax+rax+00h]
0x18000f0c3  mov     rcx, rax
0x18000f0c6  mov     [rsp+48h+var_28], rax
0x18000f0cb  test    rax, rax
0x18000f0ce  jz      short loc_18000F0F2
0x18000f0d0  mov     edx, [rsp+48h+Size]
0x18000f0d4  lea     r8, [rax+rdx]
0x18000f0d8  cmp     r8, rax
0x18000f0db  jb      short loc_18000F0F6
0x18000f0dd  lea     rax, [r15+rdi]
0x18000f0e1  cmp     r8, rax
0x18000f0e4  ja      short loc_18000F0F6
0x18000f0e6  cmp     [rcx], edx
0x18000f0e8  jnz     short loc_18000F0F6
0x18000f0ea  jmp     short loc_18000F0FF
0x18000f0ec  jmp     short loc_18000F106
0x18000f0ee  xor     eax, eax
0x18000f0f0  jmp     short loc_18000F106
0x18000f0f2  mov     eax, ebx
0x18000f0f4  jmp     short loc_18000F106
0x18000f0f6  mov     eax, 0C000007Bh
0x18000f0fb  jmp     short loc_18000F106
0x18000f0fd  jmp     short loc_18000F106
0x18000f0ff  mov     [r14], rcx
0x18000f102  mov     [rsi], edx
0x18000f104  xor     eax, eax
0x18000f106  mov     rbx, [rsp+48h+arg_0]
0x18000f10b  mov     rsi, [rsp+48h+arg_8]
0x18000f110  add     rsp, 30h
0x18000f114  pop     r15
0x18000f116  pop     r14
0x18000f118  pop     rdi
0x18000f119  retn
```
