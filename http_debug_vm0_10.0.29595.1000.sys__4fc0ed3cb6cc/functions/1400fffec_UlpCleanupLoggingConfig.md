# UlpCleanupLoggingConfig

- ea: `0x1400fffec`
- end: `0x140100153`
- name: `UlpCleanupLoggingConfig`
- size: `359`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400fd0f0`
- `0x1400fd240`

## callees

- `0x1400b0154`
- `0x1400fffec`
- `0x14010015c`
- `0x140100800`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!SeDeleteClientSecurity` at `0x1401000c5`
- `ntoskrnl!SeDeleteClientSecurity` at `0x1401000c5`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1401000ad`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1401000ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140100074`
- `ntoskrnl!ExFreePoolWithTag` at `0x140100093`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401000da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010010d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140100074`
- `ntoskrnl!ExFreePoolWithTag` at `0x140100093`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401000da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010010d`

## pseudocode

```c
void __fastcall UlpCleanupLoggingConfig(__int64 a1, __int64 a2)
{
  char *v4; // rbx
  _QWORD *v5; // rax
  __int64 v6; // r8
  _QWORD *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx

  UlpCleanupLoggingInfo((void *)(a2 + 8));
  v4 = *(char **)(a2 + 120);
  *(_QWORD *)(a2 + 120) = 0;
  if ( v4 )
  {
    v5 = v4 + 64;
    v6 = *((_QWORD *)v4 + 8);
    if ( *(char **)(v6 + 8) != v4 + 64 || (v7 = (_QWORD *)*((_QWORD *)v4 + 9), (_QWORD *)*v7 != v5) )
      __fastfail(3u);
    *v7 = v6;
    *(_QWORD *)(v6 + 8) = v7;
    *((_QWORD *)v4 + 9) = 0;
    *v5 = 0;
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 3220));
    if ( *((_QWORD *)v4 + 7) )
      UlpDisableLogFileEntry(v4);
    v8 = (void *)*((_QWORD *)v4 + 5);
    if ( v8 )
    {
      ExFreePoolWithTag(v8, 0);
      *((_QWORD *)v4 + 5) = 0;
    }
    v9 = (void *)*((_QWORD *)v4 + 2);
    if ( v9 )
      ExFreePoolWithTag(v9, 0);
    v10 = *((_QWORD *)v4 + 15);
    if ( v10 )
    {
      LOBYTE(v6) = 1;
      SeReleaseSecurityDescriptor(v10, 0, v6);
    }
    v11 = *((_QWORD *)v4 + 17);
    if ( v11 )
    {
      SeDeleteClientSecurity(v11);
      ExFreePoolWithTag(*((PVOID *)v4 + 17), 0);
      *((_QWORD *)v4 + 17) = 0;
    }
    v12 = *((_QWORD *)v4 + 20);
    if ( v12 )
      UlFreeLogFileBuffer(v12);
    *(_DWORD *)v4 = 1718373493;
    ExFreePoolWithTag(v4, 0);
  }
  if ( (BYTE9(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_q(1291, 50, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids, a2);
}

```

## disassembly

```asm
0x1400fffec  mov     [rsp+arg_0], rbx
0x1400ffff1  mov     [rsp+arg_8], rsi
0x1400ffff6  push    rdi
0x1400ffff7  sub     rsp, 20h
0x1400ffffb  mov     rsi, rcx
0x1400ffffe  mov     rdi, rdx
0x140100001  lea     rcx, [rdx+8]; void *
0x140100005  call    UlpCleanupLoggingInfo
0x14010000a  mov     rbx, [rdi+78h]
0x14010000e  mov     qword ptr [rdi+78h], 0
0x140100016  test    rbx, rbx
0x140100019  jz      loc_140100119
0x14010001f  lea     rax, [rbx+40h]
0x140100023  mov     r8, [rax]
0x140100026  cmp     [r8+8], rax
0x14010002a  jnz     loc_14010014C
0x140100030  mov     rcx, [rax+8]
0x140100034  cmp     [rcx], rax
0x140100037  jnz     loc_14010014C
0x14010003d  mov     [rcx], r8
0x140100040  mov     [r8+8], rcx
0x140100044  mov     qword ptr [rbx+48h], 0
0x14010004c  mov     qword ptr [rax], 0
0x140100053  lock dec dword ptr [rsi+0C94h]
0x14010005a  cmp     qword ptr [rbx+38h], 0
0x14010005f  jz      short loc_140100069
0x140100061  mov     rcx, rbx
0x140100064  call    UlpDisableLogFileEntry
0x140100069  mov     rcx, [rbx+28h]; P
0x14010006d  test    rcx, rcx
0x140100070  jz      short loc_140100088
0x140100072  xor     edx, edx; Tag
0x140100074  call    cs:__imp_ExFreePoolWithTag
0x14010007b  nop     dword ptr [rax+rax+00h]
0x140100080  mov     qword ptr [rbx+28h], 0
0x140100088  mov     rcx, [rbx+10h]; P
0x14010008c  test    rcx, rcx
0x14010008f  jz      short loc_14010009F
0x140100091  xor     edx, edx; Tag
0x140100093  call    cs:__imp_ExFreePoolWithTag
0x14010009a  nop     dword ptr [rax+rax+00h]
0x14010009f  mov     rcx, [rbx+78h]
0x1401000a3  test    rcx, rcx
0x1401000a6  jz      short loc_1401000B9
0x1401000a8  mov     r8b, 1
0x1401000ab  xor     edx, edx
0x1401000ad  call    cs:__imp_SeReleaseSecurityDescriptor
0x1401000b4  nop     dword ptr [rax+rax+00h]
0x1401000b9  mov     rcx, [rbx+88h]
0x1401000c0  test    rcx, rcx
0x1401000c3  jz      short loc_1401000F1
0x1401000c5  call    cs:__imp_SeDeleteClientSecurity
0x1401000cc  nop     dword ptr [rax+rax+00h]
0x1401000d1  mov     rcx, [rbx+88h]; P
0x1401000d8  xor     edx, edx; Tag
0x1401000da  call    cs:__imp_ExFreePoolWithTag
0x1401000e1  nop     dword ptr [rax+rax+00h]
0x1401000e6  mov     qword ptr [rbx+88h], 0
0x1401000f1  mov     rcx, [rbx+0A0h]
0x1401000f8  test    rcx, rcx
0x1401000fb  jz      short loc_140100102
0x1401000fd  call    UlFreeLogFileBuffer
0x140100102  xor     edx, edx; Tag
0x140100104  mov     dword ptr [rbx], 666C4C75h
0x14010010a  mov     rcx, rbx; P
0x14010010d  call    cs:__imp_ExFreePoolWithTag
0x140100114  nop     dword ptr [rax+rax+00h]
0x140100119  test    byte ptr cs:xmmword_1401A2CA0+9, 8
0x140100120  jz      short loc_14010013B
0x140100122  mov     edx, 32h ; '2'
0x140100127  lea     r8, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids
0x14010012e  mov     ecx, 50Bh
0x140100133  mov     r9, rdi
0x140100136  call    WPP_SF_q
0x14010013b  mov     rbx, [rsp+28h+arg_0]
0x140100140  mov     rsi, [rsp+28h+arg_8]
0x140100145  add     rsp, 20h
0x140100149  pop     rdi
0x14010014a  retn
0x14010014c  mov     ecx, 3
0x140100151  int     29h; Win8: RtlFailFast(ecx)
```
