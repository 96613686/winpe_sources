# EdppNotifyEnterpriseFileWrite

- ea: `0x140053460`
- end: `0x1400534f1`
- name: `EdppNotifyEnterpriseFileWrite`
- size: `145`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x14004e16c`
- `0x14004e1e0`
- `0x140053460`
- `0x140058688`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400534c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400534d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400534c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400534d5`

## pseudocode

```c
void __fastcall EdppNotifyEnterpriseFileWrite(_QWORD *P)
{
  _QWORD *v1; // rbx
  __int64 v3; // rbp
  __int64 v4; // r14
  __int64 v5; // r15
  __int64 v6; // r12

  v1 = (_QWORD *)P[4];
  EfsTriggerServiceStart();
  v3 = v1[5];
  v4 = v1[9];
  v5 = v1[7];
  v6 = v1[1];
  if ( EfsWaitForServiceReady() >= 0 )
    EfsNotifyEnterpriseFileWriteClient(v6, v3 != 0 ? (_DWORD)v1 + 16 : 0, v3, v5, v4);
  ExFreePoolWithTag(v1, 0x6D736645u);
  ExFreePoolWithTag(P, 0x6D736645u);
}

```

## disassembly

```asm
0x140053460  push    rbx
0x140053462  push    rbp
0x140053463  push    rsi
0x140053464  push    rdi
0x140053465  push    r12
0x140053467  push    r14
0x140053469  push    r15
0x14005346b  sub     rsp, 30h
0x14005346f  mov     rbx, [rcx+20h]
0x140053473  mov     rsi, rcx
0x140053476  call    EfsTriggerServiceStart
0x14005347b  mov     rbp, [rbx+28h]
0x14005347f  lea     r9, [rbx+10h]
0x140053483  mov     r14, [rbx+48h]
0x140053487  mov     rax, rbp
0x14005348a  mov     r15, [rbx+38h]
0x14005348e  neg     rax
0x140053491  mov     r12, [rbx+8]
0x140053495  sbb     rdi, rdi
0x140053498  and     rdi, r9
0x14005349b  call    EfsWaitForServiceReady
0x1400534a0  test    eax, eax
0x1400534a2  js      short loc_1400534BA
0x1400534a4  mov     r9, r15
0x1400534a7  mov     [rsp+68h+var_48], r14
0x1400534ac  mov     r8, rbp
0x1400534af  mov     rdx, rdi
0x1400534b2  mov     rcx, r12
0x1400534b5  call    EfsNotifyEnterpriseFileWriteClient
0x1400534ba  mov     edi, 6D736645h
0x1400534bf  mov     rcx, rbx; P
0x1400534c2  mov     edx, edi; Tag
0x1400534c4  call    cs:__imp_ExFreePoolWithTag
0x1400534cb  nop     dword ptr [rax+rax+00h]
0x1400534d0  mov     edx, edi; Tag
0x1400534d2  mov     rcx, rsi; P
0x1400534d5  call    cs:__imp_ExFreePoolWithTag
0x1400534dc  nop     dword ptr [rax+rax+00h]
0x1400534e1  add     rsp, 30h
0x1400534e5  pop     r15
0x1400534e7  pop     r14
0x1400534e9  pop     r12
0x1400534eb  pop     rdi
0x1400534ec  pop     rsi
0x1400534ed  pop     rbp
0x1400534ee  pop     rbx
0x1400534ef  retn
```
