# CdCommonDevControl

- ea: `0x14000e844`
- end: `0x14000e96f`
- name: `CdCommonDevControl`
- size: `299`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001240`
- `0x140002250`

## callees

- `0x140001160`
- `0x14000e844`
- `0x14001a400`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000e8f7`
- `ntoskrnl!IofCallDriver` at `0x14000e8f7`

## pseudocode

```c
__int64 __fastcall CdCommonDevControl(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v4; // rbx
  __int64 v5; // rbp
  unsigned int v6; // esi
  int v8; // eax
  __int64 v9; // rbp
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned int v12; // ebx

  v2 = *(_QWORD *)(a2 + 184);
  v4 = a2;
  v5 = *(_QWORD *)(v2 + 48);
  if ( (*(_DWORD *)(v5 + 32) & 7) != 2 )
  {
    v6 = -1073741811;
LABEL_3:
    CdCompleteRequest(a1, a2, v6);
    return v6;
  }
  v8 = *(_DWORD *)(v2 + 24);
  v9 = *(_QWORD *)(v5 + 24);
  if ( v8 == 147456 )
  {
    CdVerifyVcb(a1, *(_QWORD *)(v9 + 120));
LABEL_6:
    v10 = *(_QWORD *)(v4 + 184);
    *(_OWORD *)(v10 - 72) = *(_OWORD *)v2;
    *(_OWORD *)(v10 - 56) = *(_OWORD *)(v2 + 16);
    *(_OWORD *)(v10 - 40) = *(_OWORD *)(v2 + 32);
    *(_OWORD *)(v10 - 24) = *(_OWORD *)(v2 + 48);
    *(_QWORD *)(v10 - 8) = *(_QWORD *)(v2 + 64);
    v11 = *(_QWORD *)(v4 + 184);
    *(_QWORD *)(v11 - 16) = CdDevCtrlCompletionRoutine;
    *(_QWORD *)(v11 - 8) = 0;
    *(_BYTE *)(v11 - 69) = -32;
    v12 = IofCallDriver(*(PDEVICE_OBJECT *)(*(_QWORD *)(a1 + 16) + 16LL), (PIRP)v4);
    CdCompleteRequest(a1, 0, 0);
    return v12;
  }
  if ( v8 != 131136 )
    goto LABEL_6;
  CdVerifyVcb(a1, *(_QWORD *)(v9 + 120));
  a2 = v4;
  if ( *(_DWORD *)(v2 + 8) < 4u )
  {
    v6 = -1073741789;
    goto LABEL_3;
  }
  **(_DWORD **)(v4 + 24) = *(_DWORD *)(*(_QWORD *)(v9 + 120) + 536LL);
  *(_QWORD *)(v4 + 56) = 4;
  CdCompleteRequest(a1, v4, 0);
  return 0;
}

```

## disassembly

```asm
0x14000e844  push    rbx
0x14000e846  push    rbp
0x14000e847  push    rsi
0x14000e848  push    rdi
0x14000e849  sub     rsp, 28h
0x14000e84d  mov     rsi, [rdx+0B8h]
0x14000e854  mov     rdi, rcx
0x14000e857  mov     rbx, rdx
0x14000e85a  mov     rbp, [rsi+30h]
0x14000e85e  mov     ecx, [rbp+20h]
0x14000e861  and     ecx, 7
0x14000e864  cmp     ecx, 2
0x14000e867  jz      short loc_14000E880
0x14000e869  mov     esi, 0C000000Dh
0x14000e86e  mov     r8d, esi
0x14000e871  mov     rcx, rdi
0x14000e874  call    CdCompleteRequest
0x14000e879  mov     eax, esi
0x14000e87b  jmp     loc_14000E914
0x14000e880  mov     eax, [rsi+18h]
0x14000e883  mov     rbp, [rbp+18h]
0x14000e887  cmp     eax, 24000h
0x14000e88c  jnz     loc_14000E91E
0x14000e892  mov     rdx, [rbp+78h]
0x14000e896  mov     rcx, rdi
0x14000e899  call    CdVerifyVcb
0x14000e89e  mov     rax, [rbx+0B8h]
0x14000e8a5  lea     rcx, CdDevCtrlCompletionRoutine
0x14000e8ac  movups  xmm0, xmmword ptr [rsi]
0x14000e8af  mov     rdx, rbx; Irp
0x14000e8b2  movups  xmmword ptr [rax-48h], xmm0
0x14000e8b6  movups  xmm1, xmmword ptr [rsi+10h]
0x14000e8ba  movups  xmmword ptr [rax-38h], xmm1
0x14000e8be  movups  xmm0, xmmword ptr [rsi+20h]
0x14000e8c2  movups  xmmword ptr [rax-28h], xmm0
0x14000e8c6  movups  xmm1, xmmword ptr [rsi+30h]
0x14000e8ca  movups  xmmword ptr [rax-18h], xmm1
0x14000e8ce  movsd   xmm0, qword ptr [rsi+40h]
0x14000e8d3  movsd   qword ptr [rax-8], xmm0
0x14000e8d8  mov     rax, [rbx+0B8h]
0x14000e8df  mov     [rax-10h], rcx
0x14000e8e3  mov     qword ptr [rax-8], 0
0x14000e8eb  mov     byte ptr [rax-45h], 0E0h
0x14000e8ef  mov     rcx, [rdi+10h]
0x14000e8f3  mov     rcx, [rcx+10h]; DeviceObject
0x14000e8f7  call    cs:__imp_IofCallDriver
0x14000e8fe  nop     dword ptr [rax+rax+00h]
0x14000e903  xor     r8d, r8d
0x14000e906  xor     edx, edx
0x14000e908  mov     rcx, rdi
0x14000e90b  mov     ebx, eax
0x14000e90d  call    CdCompleteRequest
0x14000e912  mov     eax, ebx
0x14000e914  add     rsp, 28h
0x14000e918  pop     rdi
0x14000e919  pop     rsi
0x14000e91a  pop     rbp
0x14000e91b  pop     rbx
0x14000e91c  retn
0x14000e91e  cmp     eax, 20040h
0x14000e923  jnz     loc_14000E89E
0x14000e929  mov     rdx, [rbp+78h]
0x14000e92d  mov     rcx, rdi
0x14000e930  call    CdVerifyVcb
0x14000e935  cmp     dword ptr [rsi+8], 4
0x14000e939  mov     rdx, rbx
0x14000e93c  jnb     short loc_14000E948
0x14000e93e  mov     esi, 0C0000023h
0x14000e943  jmp     loc_14000E86E
0x14000e948  mov     rax, [rbp+78h]
0x14000e94c  xor     r8d, r8d
0x14000e94f  mov     rcx, [rbx+18h]
0x14000e953  mov     eax, [rax+218h]
0x14000e959  mov     [rcx], eax
0x14000e95b  mov     rcx, rdi
0x14000e95e  mov     qword ptr [rbx+38h], 4
0x14000e966  call    CdCompleteRequest
0x14000e96b  xor     eax, eax
0x14000e96d  jmp     short loc_14000E914
```
