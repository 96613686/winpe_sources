# CipHvciFindImageLoadConfig

- ea: `0x18000f04c`
- end: `0x18000f12b`
- name: `CipHvciFindImageLoadConfig`
- size: `223`
- prototype: `__int64 __fastcall(PVOID BaseAddress, ULONGLONG Size)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800d2050`

## callees

- `0x18000f04c`

## import_xrefs

- `ntoskrnl!RtlImageDirectoryEntryToData` at `0x18000f0c7`
- `ntoskrnl!RtlImageDirectoryEntryToData` at `0x18000f0c7`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x18000f095`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x18000f095`

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
0x18000f04c  mov     rax, rsp
0x18000f04f  mov     [rax+8], rbx
0x18000f053  mov     [rax+10h], rsi
0x18000f057  push    rdi
0x18000f058  push    r14
0x18000f05a  push    r15
0x18000f05c  sub     rsp, 30h
0x18000f060  mov     rsi, r9
0x18000f063  mov     r14, r8
0x18000f066  mov     rdi, rcx
0x18000f069  mov     dword ptr [rax+18h], 0
0x18000f070  mov     qword ptr [rax+20h], 0
0x18000f078  mov     qword ptr [r8], 0
0x18000f07f  mov     dword ptr [r9], 0
0x18000f086  mov     r15d, edx
0x18000f089  lea     r9, [rax+20h]; NtHeader
0x18000f08d  mov     r8d, edx; Size
0x18000f090  mov     rdx, rcx; BaseAddress
0x18000f093  xor     ecx, ecx; Flags
0x18000f095  call    cs:__imp_RtlImageNtHeaderEx
0x18000f09c  nop     dword ptr [rax+rax+00h]
0x18000f0a1  mov     ebx, eax
0x18000f0a3  test    eax, eax
0x18000f0a5  js      short loc_18000F0FC
0x18000f0a7  mov     ecx, 20Bh
0x18000f0ac  mov     rax, [rsp+48h+arg_18]
0x18000f0b1  cmp     [rax+18h], cx
0x18000f0b5  jnz     short loc_18000F0FE
0x18000f0b7  mov     r8d, 0Ah; Directory
0x18000f0bd  lea     r9, [rsp+48h+Size]; Size
0x18000f0c2  mov     dl, 1; MappedAsImage
0x18000f0c4  mov     rcx, rdi; BaseAddress
0x18000f0c7  call    cs:__imp_RtlImageDirectoryEntryToData
0x18000f0ce  nop     dword ptr [rax+rax+00h]
0x18000f0d3  mov     rcx, rax
0x18000f0d6  mov     [rsp+48h+var_28], rax
0x18000f0db  test    rax, rax
0x18000f0de  jz      short loc_18000F102
0x18000f0e0  mov     edx, [rsp+48h+Size]
0x18000f0e4  lea     r8, [rax+rdx]
0x18000f0e8  cmp     r8, rax
0x18000f0eb  jb      short loc_18000F106
0x18000f0ed  lea     rax, [r15+rdi]
0x18000f0f1  cmp     r8, rax
0x18000f0f4  ja      short loc_18000F106
0x18000f0f6  cmp     [rcx], edx
0x18000f0f8  jnz     short loc_18000F106
0x18000f0fa  jmp     short loc_18000F10F
0x18000f0fc  jmp     short loc_18000F116
0x18000f0fe  xor     eax, eax
0x18000f100  jmp     short loc_18000F116
0x18000f102  mov     eax, ebx
0x18000f104  jmp     short loc_18000F116
0x18000f106  mov     eax, 0C000007Bh
0x18000f10b  jmp     short loc_18000F116
0x18000f10d  jmp     short loc_18000F116
0x18000f10f  mov     [r14], rcx
0x18000f112  mov     [rsi], edx
0x18000f114  xor     eax, eax
0x18000f116  mov     rbx, [rsp+48h+arg_0]
0x18000f11b  mov     rsi, [rsp+48h+arg_8]
0x18000f120  add     rsp, 30h
0x18000f124  pop     r15
0x18000f126  pop     r14
0x18000f128  pop     rdi
0x18000f129  retn
```
