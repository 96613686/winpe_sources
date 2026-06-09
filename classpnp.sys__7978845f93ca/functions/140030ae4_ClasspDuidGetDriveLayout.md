# ClasspDuidGetDriveLayout

- ea: `0x140030ae4`
- end: `0x140030bdf`
- name: `ClasspDuidGetDriveLayout`
- size: `251`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140030be8`

## callees

- `0x140030ae4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140030bc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030bc0`
- `ntoskrnl!IoReadPartitionTableEx` at `0x140030b19`
- `ntoskrnl!IoReadPartitionTableEx` at `0x140030b19`

## pseudocode

```c
__int64 __fastcall ClasspDuidGetDriveLayout(struct _DEVICE_OBJECT *a1, _QWORD *a2)
{
  bool v2; // zf
  unsigned int v4; // ebx
  __int64 v5; // rsi
  __int64 v6; // rdx
  unsigned int v7; // ecx
  __int64 v8; // r9
  __int64 v9; // r10
  __int64 v10; // rax
  PVOID P; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1->DeviceType == 7;
  P = 0;
  v4 = -1073741275;
  if ( v2 )
  {
    v5 = a2[23];
    if ( IoReadPartitionTableEx(a1, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P) >= 0 && *(_DWORD *)P < 2u )
    {
      v6 = a2[3];
      v7 = *(_DWORD *)(v5 + 8);
      v8 = *(unsigned int *)(v6 + 4);
      *(_DWORD *)(v6 + 4) = v8 + 28;
      if ( v7 >= (int)v8 + 28 )
      {
        v9 = a2[3];
        *(_DWORD *)(v8 + v6 + 4) = 28;
        *(_DWORD *)(v8 + v6) = 1;
        if ( *(_DWORD *)P )
        {
          *(_BYTE *)(v8 + v6 + 8) = 0;
          *(_OWORD *)(v8 + v6 + 12) = *(_OWORD *)((char *)P + 8);
        }
        else
        {
          *(_BYTE *)(v8 + v6 + 8) = 1;
          *(_DWORD *)(v8 + v6 + 12) = *((_DWORD *)P + 2);
        }
        v10 = *(unsigned int *)(v9 + 4);
        v4 = 0;
        *(_DWORD *)(v9 + 16) = v8;
        a2[7] = v10;
      }
      else
      {
        a2[7] = 8;
        v4 = -2147483643;
      }
    }
    if ( P )
      ExFreePoolWithTag(P, 0);
  }
  return v4;
}

```

## disassembly

```asm
0x140030ae4  mov     rax, rsp
0x140030ae7  mov     [rax+10h], rbx
0x140030aeb  mov     [rax+18h], rsi
0x140030aef  push    rdi
0x140030af0  sub     rsp, 20h
0x140030af4  cmp     dword ptr [rcx+48h], 7
0x140030af8  mov     rdi, rdx
0x140030afb  mov     qword ptr [rax+8], 0
0x140030b03  mov     ebx, 0C0000225h
0x140030b08  jnz     loc_140030BCC
0x140030b0e  mov     rsi, [rdx+0B8h]
0x140030b15  lea     rdx, [rax+8]; DriveLayout
0x140030b19  call    cs:__imp_IoReadPartitionTableEx
0x140030b20  nop     dword ptr [rax+rax+00h]
0x140030b25  test    eax, eax
0x140030b27  js      loc_140030BB4
0x140030b2d  mov     rax, [rsp+28h+P]
0x140030b32  cmp     dword ptr [rax], 2
0x140030b35  jnb     short loc_140030BB4
0x140030b37  mov     rdx, [rdi+18h]
0x140030b3b  mov     ecx, [rsi+8]
0x140030b3e  mov     r9d, [rdx+4]
0x140030b42  lea     eax, [r9+1Ch]
0x140030b46  mov     [rdx+4], eax
0x140030b49  cmp     ecx, eax
0x140030b4b  jnb     short loc_140030B5C
0x140030b4d  mov     qword ptr [rdi+38h], 8
0x140030b55  mov     ebx, 80000005h
0x140030b5a  jmp     short loc_140030BB4
0x140030b5c  mov     r10, [rdi+18h]
0x140030b60  mov     dword ptr [r9+rdx+4], 1Ch
0x140030b69  mov     dword ptr [r9+rdx], 1
0x140030b71  mov     rax, [rsp+28h+P]
0x140030b76  cmp     dword ptr [rax], 0
0x140030b79  jnz     short loc_140030B90
0x140030b7b  mov     byte ptr [r9+rdx+8], 1
0x140030b81  mov     rax, [rsp+28h+P]
0x140030b86  mov     ecx, [rax+8]
0x140030b89  mov     [r9+rdx+0Ch], ecx
0x140030b8e  jmp     short loc_140030BA6
0x140030b90  mov     byte ptr [r9+rdx+8], 0
0x140030b96  mov     rax, [rsp+28h+P]
0x140030b9b  movups  xmm0, xmmword ptr [rax+8]
0x140030b9f  movdqu  xmmword ptr [r9+rdx+0Ch], xmm0
0x140030ba6  mov     eax, [r10+4]
0x140030baa  xor     ebx, ebx
0x140030bac  mov     [r10+10h], r9d
0x140030bb0  mov     [rdi+38h], rax
0x140030bb4  mov     rcx, [rsp+28h+P]; P
0x140030bb9  test    rcx, rcx
0x140030bbc  jz      short loc_140030BCC
0x140030bbe  xor     edx, edx; Tag
0x140030bc0  call    cs:__imp_ExFreePoolWithTag
0x140030bc7  nop     dword ptr [rax+rax+00h]
0x140030bcc  mov     rsi, [rsp+28h+arg_10]
0x140030bd1  mov     eax, ebx
0x140030bd3  mov     rbx, [rsp+28h+arg_8]
0x140030bd8  add     rsp, 20h
0x140030bdc  pop     rdi
0x140030bdd  retn
```
