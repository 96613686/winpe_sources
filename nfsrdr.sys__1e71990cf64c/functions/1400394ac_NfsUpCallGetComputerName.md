# NfsUpCallGetComputerName

- ea: `0x1400394ac`
- end: `0x1400395cf`
- name: `NfsUpCallGetComputerName`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140017b68`

## callees

- `0x14000bc80`
- `0x1400394ac`

## import_xrefs

- `ntoskrnl!RtlCopyString` at `0x14003957d`
- `ntoskrnl!RtlCopyString` at `0x14003957d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400395b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400395b0`
- `ntoskrnl!ExAllocatePool2` at `0x1400394e0`
- `ntoskrnl!ExAllocatePool2` at `0x1400394e0`

## pseudocode

```c
__int64 __fastcall NfsUpCallGetComputerName(__int64 a1, struct _STRING *a2)
{
  int v4; // ebx
  __int64 Pool2; // rax
  __int64 v6; // rdi
  unsigned int v7; // ecx
  STRING SourceString; // [rsp+20h] [rbp-18h] BYREF

  if ( a2 )
  {
    Pool2 = ExAllocatePool2(258, 448, 1433626190);
    v6 = Pool2;
    if ( Pool2 )
    {
      *(_QWORD *)Pool2 = 0;
      *(_DWORD *)(Pool2 + 8) = 15;
      *(_DWORD *)(Pool2 + 12) = 16;
      v4 = NfsUpCallSendRequestAndWait(a1, Pool2, Pool2, 448);
      if ( v4 >= 0 )
      {
        if ( (unsigned __int64)(*(_QWORD *)(v6 + 24) - 56LL) > 0x188
          || (v7 = *(_DWORD *)(v6 + 44), a2->MaximumLength < v7) )
        {
          v4 = -1073741789;
        }
        else
        {
          if ( v7 <= 0xFFFF && *(_DWORD *)(v6 + 52) <= 0xFFFFu )
          {
            SourceString.Length = *(_DWORD *)(v6 + 44);
            SourceString.MaximumLength = v7;
            *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
            SourceString.Buffer = (PCHAR)(v6 + *(unsigned int *)(v6 + 40));
            RtlCopyString(a2, &SourceString);
            goto LABEL_14;
          }
          v4 = -1073741534;
        }
      }
    }
    else
    {
      v4 = -1073741670;
    }
    *a2->Buffer = 0;
    a2->Length = 0;
    if ( !v6 )
      return (unsigned int)v4;
LABEL_14:
    ExFreePoolWithTag((PVOID)v6, 0x5573664Eu);
    return (unsigned int)v4;
  }
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x1400394ac  mov     [rsp+arg_0], rbx
0x1400394b1  mov     [rsp+arg_8], rsi
0x1400394b6  push    rdi
0x1400394b7  sub     rsp, 30h
0x1400394bb  mov     rsi, rdx
0x1400394be  mov     rbx, rcx
0x1400394c1  test    rdx, rdx
0x1400394c4  jnz     short loc_1400394D0
0x1400394c6  mov     ebx, 0C000000Dh
0x1400394cb  jmp     loc_1400395BC
0x1400394d0  mov     edx, 1C0h
0x1400394d5  mov     ecx, 102h
0x1400394da  mov     r8d, 5573664Eh
0x1400394e0  call    cs:__imp_ExAllocatePool2
0x1400394e7  nop     dword ptr [rax+rax+00h]
0x1400394ec  mov     rdi, rax
0x1400394ef  test    rax, rax
0x1400394f2  jnz     short loc_1400394FE
0x1400394f4  mov     ebx, 0C000009Ah
0x1400394f9  jmp     loc_140039597
0x1400394fe  mov     qword ptr [rax], 0
0x140039505  mov     r9d, 1C0h
0x14003950b  mov     r8, rdi
0x14003950e  mov     dword ptr [rax+8], 0Fh
0x140039515  mov     rdx, rdi
0x140039518  mov     dword ptr [rax+0Ch], 10h
0x14003951f  mov     rcx, rbx
0x140039522  call    NfsUpCallSendRequestAndWait
0x140039527  mov     ebx, eax
0x140039529  test    eax, eax
0x14003952b  js      short loc_140039597
0x14003952d  mov     rcx, [rdi+18h]
0x140039531  sub     rcx, 38h ; '8'
0x140039535  cmp     rcx, 188h
0x14003953c  ja      short loc_140039592
0x14003953e  movzx   eax, word ptr [rsi+2]
0x140039542  mov     ecx, [rdi+2Ch]
0x140039545  cmp     eax, ecx
0x140039547  jb      short loc_140039592
0x140039549  mov     eax, 0FFFFh
0x14003954e  cmp     ecx, eax
0x140039550  ja      short loc_14003958B
0x140039552  cmp     [rdi+34h], eax
0x140039555  ja      short loc_14003958B
0x140039557  movzx   eax, cx
0x14003955a  mov     [rsp+38h+SourceString.Length], cx
0x14003955f  xor     eax, eax
0x140039561  mov     [rsp+38h+SourceString.MaximumLength], cx
0x140039566  mov     dword ptr [rsp+38h+SourceString+4], eax
0x14003956a  lea     rdx, [rsp+38h+SourceString]; SourceString
0x14003956f  mov     eax, [rdi+28h]
0x140039572  mov     rcx, rsi; DestinationString
0x140039575  add     rax, rdi
0x140039578  mov     [rsp+38h+SourceString.Buffer], rax
0x14003957d  call    cs:__imp_RtlCopyString
0x140039584  nop     dword ptr [rax+rax+00h]
0x140039589  jmp     short loc_1400395A8
0x14003958b  mov     ebx, 0C0000122h
0x140039590  jmp     short loc_140039597
0x140039592  mov     ebx, 0C0000023h
0x140039597  mov     rax, [rsi+8]
0x14003959b  mov     byte ptr [rax], 0
0x14003959e  xor     eax, eax
0x1400395a0  mov     [rsi], ax
0x1400395a3  test    rdi, rdi
0x1400395a6  jz      short loc_1400395BC
0x1400395a8  mov     edx, 5573664Eh; Tag
0x1400395ad  mov     rcx, rdi; P
0x1400395b0  call    cs:__imp_ExFreePoolWithTag
0x1400395b7  nop     dword ptr [rax+rax+00h]
0x1400395bc  mov     rsi, [rsp+38h+arg_8]
0x1400395c1  mov     eax, ebx
0x1400395c3  mov     rbx, [rsp+38h+arg_0]
0x1400395c8  add     rsp, 30h
0x1400395cc  pop     rdi
0x1400395cd  retn
```
