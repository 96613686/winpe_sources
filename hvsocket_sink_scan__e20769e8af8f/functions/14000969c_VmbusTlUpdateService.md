# VmbusTlUpdateService

- ea: `0x14000969c`
- end: `0x140009754`
- name: `VmbusTlUpdateService`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1400222b0`
- `0x140022634`

## callees

- `0x14000969c`

## import_xrefs

- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000971c`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000973d`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000971c`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000973d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400096bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400096da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400096bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400096da`

## pseudocode

```c
__int64 __fastcall VmbusTlUpdateService(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *v4; // r14
  void *v6; // rcx
  _QWORD *v8; // rdi
  void *v9; // rcx
  __int64 result; // rax
  __int64 v11; // rdx
  __int64 v12; // r9

  v4 = (_QWORD *)(a3 + 144);
  v6 = *(void **)(a3 + 144);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  v8 = (_QWORD *)(a3 + 136);
  v9 = *(void **)(a3 + 136);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  *(_BYTE *)(a3 + 128) = *(_BYTE *)(a1 + 16);
  *(_BYTE *)(a3 + 152) = *(_BYTE *)(a1 + 40);
  *v4 = 0;
  LOBYTE(a4) = 1;
  *v8 = 0;
  LOBYTE(a2) = 1;
  result = SeCaptureSecurityDescriptor(*(_QWORD *)(a1 + 32), a2, 1, a4, v4);
  if ( (int)result >= 0 )
  {
    LOBYTE(v12) = 1;
    LOBYTE(v11) = 1;
    return SeCaptureSecurityDescriptor(*(_QWORD *)(a1 + 24), v11, 1, v12, v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000969c  push    rbx
0x14000969e  push    rsi
0x14000969f  push    rdi
0x1400096a0  push    r14
0x1400096a2  sub     rsp, 38h
0x1400096a6  lea     r14, [r8+90h]
0x1400096ad  mov     rsi, rcx
0x1400096b0  mov     rcx, [r14]; P
0x1400096b3  mov     rbx, r8
0x1400096b6  test    rcx, rcx
0x1400096b9  jz      short loc_1400096C9
0x1400096bb  xor     edx, edx; Tag
0x1400096bd  call    cs:__imp_ExFreePoolWithTag
0x1400096c4  nop     dword ptr [rax+rax+00h]
0x1400096c9  lea     rdi, [rbx+88h]
0x1400096d0  mov     rcx, [rdi]; P
0x1400096d3  test    rcx, rcx
0x1400096d6  jz      short loc_1400096E6
0x1400096d8  xor     edx, edx; Tag
0x1400096da  call    cs:__imp_ExFreePoolWithTag
0x1400096e1  nop     dword ptr [rax+rax+00h]
0x1400096e6  mov     al, [rsi+10h]
0x1400096e9  mov     [rbx+80h], al
0x1400096ef  mov     al, [rsi+28h]
0x1400096f2  mov     [rbx+98h], al
0x1400096f8  mov     ebx, 1
0x1400096fd  mov     qword ptr [r14], 0
0x140009704  mov     r9b, bl
0x140009707  mov     qword ptr [rdi], 0
0x14000970e  mov     r8d, ebx
0x140009711  mov     rcx, [rsi+20h]
0x140009715  mov     dl, bl
0x140009717  mov     [rsp+58h+var_38], r14
0x14000971c  call    cs:__imp_SeCaptureSecurityDescriptor
0x140009723  nop     dword ptr [rax+rax+00h]
0x140009728  test    eax, eax
0x14000972a  js      short loc_140009749
0x14000972c  mov     rcx, [rsi+18h]
0x140009730  mov     r9b, bl
0x140009733  mov     r8d, ebx
0x140009736  mov     [rsp+58h+var_38], rdi
0x14000973b  mov     dl, bl
0x14000973d  call    cs:__imp_SeCaptureSecurityDescriptor
0x140009744  nop     dword ptr [rax+rax+00h]
0x140009749  add     rsp, 38h
0x14000974d  pop     r14
0x14000974f  pop     rdi
0x140009750  pop     rsi
0x140009751  pop     rbx
0x140009752  retn
```
