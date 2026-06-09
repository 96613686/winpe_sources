# LdrpHandleUserCopyAttributeList

- ea: `0x18015b770`
- end: `0x18015b8ec`
- name: `LdrpHandleUserCopyAttributeList`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800d6508`

## callees

- `0x18001eb80`
- `0x18015b770`

## string_xrefs

- `0x18015b81f`: `LdrpHandleUserCopyAttributeList`
- `0x18015b854`: `LdrpHandleUserCopyAttributeList`
- `0x18015b87f`: `LdrpHandleUserCopyAttributeList`
- `0x18015b8b7`: `LdrpHandleUserCopyAttributeList`

## pseudocode

```c
__int64 LdrpHandleUserCopyAttributeList()
{
  struct _PEB *v0; // rdi
  unsigned int v1; // ebx
  _QWORD *AttributeList; // rdx
  __int64 v3; // r9
  unsigned __int64 v4; // rcx
  _BYTE *v5; // r8
  __int64 result; // rax
  char ArgList; // [rsp+28h] [rbp-20h]

  v0 = NtCurrentPeb();
  v1 = 0;
  AttributeList = v0->ProcessParameters->AttributeList;
  if ( AttributeList )
  {
    v3 = 0;
    v4 = (unsigned __int64)(*AttributeList - 8LL) >> 5;
    if ( v4 )
    {
      while ( AttributeList[4 * v3 + 1] == 655394 )
      {
        v5 = (_BYTE *)AttributeList[4 * v3 + 3];
        if ( !v5 )
        {
          LdrpLogInternal(
            (int)"minkernel\\ldr\\ldrinit.c",
            4832,
            (int)"LdrpHandleUserCopyAttributeList",
            0,
            "Received invalid NULL HeapFeatures attribute\n",
            ArgList);
          goto LABEL_12;
        }
        if ( (*v5 & 3u) > 1 || (*(_QWORD *)v5 & 3LL) != *(_QWORD *)v5 )
        {
          v1 = -1073741811;
          LdrpLogInternal(
            (int)"minkernel\\ldr\\ldrinit.c",
            4847,
            (int)"LdrpHandleUserCopyAttributeList",
            0,
            "Failed to set HeapFeatures attribute, st=0x%08lx, value=0x%I64x\n",
            13);
          goto LABEL_13;
        }
        qword_1801C6268 = *(_QWORD *)v5;
        v1 = 0;
        if ( ++v3 >= v4 )
          goto LABEL_14;
      }
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrinit.c",
        4861,
        (int)"LdrpHandleUserCopyAttributeList",
        0,
        "Unknown attribute=0x%08Ix\n",
        AttributeList[4 * v3 + 1]);
LABEL_12:
      v1 = -1073741811;
LABEL_13:
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrinit.c",
        4873,
        (int)"LdrpHandleUserCopyAttributeList",
        0,
        "Failed to parse attribute list with status=0x%08lx\n",
        13);
    }
  }
LABEL_14:
  result = v1;
  v0->ProcessParameters->AttributeList = 0;
  return result;
}

```

## disassembly

```asm
0x18015b770  mov     [rsp+arg_8], rbx
0x18015b775  push    rdi
0x18015b776  sub     rsp, 40h
0x18015b77a  mov     rdi, gs:60h
0x18015b783  xor     ebx, ebx
0x18015b785  mov     rax, [rdi+20h]
0x18015b789  mov     rdx, [rax+448h]
0x18015b790  test    rdx, rdx
0x18015b793  jz      loc_18015B8CF
0x18015b799  mov     rcx, [rdx]
0x18015b79c  xor     r9d, r9d
0x18015b79f  sub     rcx, 8
0x18015b7a3  shr     rcx, 5
0x18015b7a7  test    rcx, rcx
0x18015b7aa  jz      loc_18015B8CF
0x18015b7b0  mov     rax, r9
0x18015b7b3  shl     rax, 5
0x18015b7b7  mov     r8, [rax+rdx+8]
0x18015b7bc  cmp     r8, 0A0022h
0x18015b7c3  jnz     loc_18015B873
0x18015b7c9  mov     r8, [rax+rdx+18h]
0x18015b7ce  test    r8, r8
0x18015b7d1  jz      short loc_18015B84A
0x18015b7d3  mov     al, [r8]
0x18015b7d6  and     al, 3
0x18015b7d8  cmp     al, 1
0x18015b7da  ja      short loc_18015B810
0x18015b7dc  mov     r10, [r8]
0x18015b7df  mov     [rsp+48h+arg_0], 0
0x18015b7e8  mov     rax, r10
0x18015b7eb  mov     byte ptr [rsp+48h+arg_0], 3
0x18015b7f0  and     rax, [rsp+48h+arg_0]
0x18015b7f5  cmp     rax, r10
0x18015b7f8  jnz     short loc_18015B810
0x18015b7fa  mov     cs:qword_1801C6268, r10
0x18015b801  xor     ebx, ebx
0x18015b803  inc     r9
0x18015b806  cmp     r9, rcx
0x18015b809  jb      short loc_18015B7B0
0x18015b80b  jmp     loc_18015B8CF
0x18015b810  mov     rax, [r8]
0x18015b813  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x18015b81a  mov     [rsp+48h+var_18], rax
0x18015b81f  lea     r8, aLdrphandleuser; "LdrpHandleUserCopyAttributeList"
0x18015b826  lea     rax, aFailedToSetHea; "Failed to set HeapFeatures attribute, s"...
0x18015b82d  mov     ebx, 0C000000Dh
0x18015b832  mov     dword ptr [rsp+48h+ArgList], ebx; ArgList
0x18015b836  xor     r9d, r9d; int
0x18015b839  mov     edx, 12EFh; int
0x18015b83e  mov     [rsp+48h+Format], rax; Format
0x18015b843  call    LdrpLogInternal
0x18015b848  jmp     short loc_18015B8A4
0x18015b84a  lea     rax, aReceivedInvali; "Received invalid NULL HeapFeatures attr"...
0x18015b851  xor     r9d, r9d; int
0x18015b854  lea     r8, aLdrphandleuser; "LdrpHandleUserCopyAttributeList"
0x18015b85b  mov     [rsp+48h+Format], rax; Format
0x18015b860  mov     edx, 12E0h; int
0x18015b865  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x18015b86c  call    LdrpLogInternal
0x18015b871  jmp     short loc_18015B89F
0x18015b873  mov     qword ptr [rsp+48h+ArgList], r8; ArgList
0x18015b878  lea     rax, aUnknownAttribu; "Unknown attribute=0x%08Ix\n"
0x18015b87f  lea     r8, aLdrphandleuser; "LdrpHandleUserCopyAttributeList"
0x18015b886  mov     [rsp+48h+Format], rax; Format
0x18015b88b  xor     r9d, r9d; int
0x18015b88e  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x18015b895  mov     edx, 12FDh; int
0x18015b89a  call    LdrpLogInternal
0x18015b89f  mov     ebx, 0C000000Dh
0x18015b8a4  lea     rax, aFailedToParseA; "Failed to parse attribute list with sta"...
0x18015b8ab  mov     dword ptr [rsp+48h+ArgList], ebx; ArgList
0x18015b8af  xor     r9d, r9d; int
0x18015b8b2  mov     [rsp+48h+Format], rax; Format
0x18015b8b7  lea     r8, aLdrphandleuser; "LdrpHandleUserCopyAttributeList"
0x18015b8be  mov     edx, 1309h; int
0x18015b8c3  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x18015b8ca  call    LdrpLogInternal
0x18015b8cf  mov     rcx, [rdi+20h]
0x18015b8d3  mov     eax, ebx
0x18015b8d5  mov     rbx, [rsp+48h+arg_8]
0x18015b8da  mov     qword ptr [rcx+448h], 0
0x18015b8e5  add     rsp, 40h
0x18015b8e9  pop     rdi
0x18015b8ea  retn
```
