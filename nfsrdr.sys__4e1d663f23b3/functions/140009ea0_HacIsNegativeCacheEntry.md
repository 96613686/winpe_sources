# HacIsNegativeCacheEntry

- ea: `0x140009ea0`
- end: `0x140009f58`
- name: `HacIsNegativeCacheEntry`
- size: `184`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140019044`
- `0x140020af4`

## callees

- `0x140009ea0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140009ec0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009ec0`
- `ntoskrnl!KeReleaseMutex` at `0x140009f3d`
- `ntoskrnl!KeReleaseMutex` at `0x140009f3d`

## pseudocode

```c
_BOOL8 __fastcall HacIsNegativeCacheEntry(__int64 a1)
{
  struct _KMUTANT *v2; // r8
  struct _LIST_ENTRY *v3; // rax
  __int64 v4; // rcx
  bool v5; // bl

  KeWaitForSingleObject(*(PVOID *)(a1 + 40), Executive, 0, 0, 0);
  v2 = *(struct _KMUTANT **)(a1 + 40);
  if ( !v2[1].MutantListEntry.Blink )
  {
    v2[1].MutantListEntry.Blink = (struct _LIST_ENTRY *)a1;
LABEL_9:
    v2[1].OwnerThread = (struct _KTHREAD *)a1;
    v2 = *(struct _KMUTANT **)(a1 + 40);
    goto LABEL_10;
  }
  if ( v2[1].OwnerThread != (struct _KTHREAD *)a1 )
  {
    v3 = *(struct _LIST_ENTRY **)(a1 + 16);
    if ( v3 )
    {
      v4 = *(_QWORD *)(a1 + 24);
      if ( v4 )
      {
        *(_QWORD *)(v4 + 16) = v3;
        *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) = *(_QWORD *)(a1 + 24);
      }
      else
      {
        v2[1].MutantListEntry.Blink = v3;
        *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) = 0;
      }
    }
    *((_QWORD *)v2[1].OwnerThread + 2) = a1;
    *(_QWORD *)(a1 + 24) = v2[1].OwnerThread;
    *(_QWORD *)(a1 + 16) = 0;
    goto LABEL_9;
  }
LABEL_10:
  v5 = (*(_BYTE *)(a1 + 48) & 8) != 0;
  KeReleaseMutex(v2, 0);
  return v5;
}

```

## disassembly

```asm
0x140009ea0  mov     [rsp+arg_0], rbx
0x140009ea5  push    rdi
0x140009ea6  sub     rsp, 30h
0x140009eaa  mov     rbx, rcx
0x140009ead  xor     edi, edi
0x140009eaf  mov     rcx, [rcx+28h]; Object
0x140009eb3  xor     r9d, r9d; Alertable
0x140009eb6  xor     r8d, r8d; WaitMode
0x140009eb9  mov     [rsp+38h+Timeout], rdi; Timeout
0x140009ebe  xor     edx, edx; WaitReason
0x140009ec0  call    cs:__imp_KeWaitForSingleObject
0x140009ec7  nop     dword ptr [rax+rax+00h]
0x140009ecc  mov     r8, [rbx+28h]
0x140009ed0  cmp     [r8+58h], rdi
0x140009ed4  jz      short loc_140009F22
0x140009ed6  cmp     [r8+60h], rbx
0x140009eda  jz      short loc_140009F2E
0x140009edc  mov     rax, [rbx+10h]
0x140009ee0  test    rax, rax
0x140009ee3  jz      short loc_140009F0C
0x140009ee5  mov     rcx, [rbx+18h]
0x140009ee9  test    rcx, rcx
0x140009eec  jz      short loc_140009F00
0x140009eee  mov     [rcx+10h], rax
0x140009ef2  mov     rcx, [rbx+10h]
0x140009ef6  mov     rax, [rbx+18h]
0x140009efa  mov     [rcx+18h], rax
0x140009efe  jmp     short loc_140009F0C
0x140009f00  mov     [r8+58h], rax
0x140009f04  mov     rax, [rbx+10h]
0x140009f08  mov     [rax+18h], rdi
0x140009f0c  mov     rax, [r8+60h]
0x140009f10  mov     [rax+10h], rbx
0x140009f14  mov     rax, [r8+60h]
0x140009f18  mov     [rbx+18h], rax
0x140009f1c  mov     [rbx+10h], rdi
0x140009f20  jmp     short loc_140009F26
0x140009f22  mov     [r8+58h], rbx
0x140009f26  mov     [r8+60h], rbx
0x140009f2a  mov     r8, [rbx+28h]
0x140009f2e  movzx   ebx, byte ptr [rbx+30h]
0x140009f32  xor     edx, edx; Wait
0x140009f34  shr     bl, 3
0x140009f37  mov     rcx, r8; Mutex
0x140009f3a  and     bl, 1
0x140009f3d  call    cs:__imp_KeReleaseMutex
0x140009f44  nop     dword ptr [rax+rax+00h]
0x140009f49  movzx   eax, bl
0x140009f4c  mov     rbx, [rsp+38h+arg_0]
0x140009f51  add     rsp, 30h
0x140009f55  pop     rdi
0x140009f56  retn
```
