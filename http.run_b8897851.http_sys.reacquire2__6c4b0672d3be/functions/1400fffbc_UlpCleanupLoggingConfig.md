# UlpCleanupLoggingConfig

- ea: `0x1400fffbc`
- end: `0x140100123`
- name: `UlpCleanupLoggingConfig`
- size: `359`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400fd0c0`
- `0x1400fd210`

## callees

- `0x1400b0234`
- `0x1400fffbc`
- `0x14010012c`
- `0x1401007d0`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!SeDeleteClientSecurity` at `0x140100095`
- `ntoskrnl!SeDeleteClientSecurity` at `0x140100095`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x14010007d`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x14010007d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140100044`
- `ntoskrnl!ExFreePoolWithTag` at `0x140100063`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401000aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401000dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140100044`
- `ntoskrnl!ExFreePoolWithTag` at `0x140100063`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401000aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401000dd`

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
0x1400fffbc  mov     [rsp+arg_0], rbx
0x1400fffc1  mov     [rsp+arg_8], rsi
0x1400fffc6  push    rdi
0x1400fffc7  sub     rsp, 20h
0x1400fffcb  mov     rsi, rcx
0x1400fffce  mov     rdi, rdx
0x1400fffd1  lea     rcx, [rdx+8]; void *
0x1400fffd5  call    UlpCleanupLoggingInfo
0x1400fffda  mov     rbx, [rdi+78h]
0x1400fffde  mov     qword ptr [rdi+78h], 0
0x1400fffe6  test    rbx, rbx
0x1400fffe9  jz      loc_1401000E9
0x1400fffef  lea     rax, [rbx+40h]
0x1400ffff3  mov     r8, [rax]
0x1400ffff6  cmp     [r8+8], rax
0x1400ffffa  jnz     loc_14010011C
0x140100000  mov     rcx, [rax+8]
0x140100004  cmp     [rcx], rax
0x140100007  jnz     loc_14010011C
0x14010000d  mov     [rcx], r8
0x140100010  mov     [r8+8], rcx
0x140100014  mov     qword ptr [rbx+48h], 0
0x14010001c  mov     qword ptr [rax], 0
0x140100023  lock dec dword ptr [rsi+0C94h]
0x14010002a  cmp     qword ptr [rbx+38h], 0
0x14010002f  jz      short loc_140100039
0x140100031  mov     rcx, rbx
0x140100034  call    UlpDisableLogFileEntry
0x140100039  mov     rcx, [rbx+28h]; P
0x14010003d  test    rcx, rcx
0x140100040  jz      short loc_140100058
0x140100042  xor     edx, edx; Tag
0x140100044  call    cs:__imp_ExFreePoolWithTag
0x14010004b  nop     dword ptr [rax+rax+00h]
0x140100050  mov     qword ptr [rbx+28h], 0
0x140100058  mov     rcx, [rbx+10h]; P
0x14010005c  test    rcx, rcx
0x14010005f  jz      short loc_14010006F
0x140100061  xor     edx, edx; Tag
0x140100063  call    cs:__imp_ExFreePoolWithTag
0x14010006a  nop     dword ptr [rax+rax+00h]
0x14010006f  mov     rcx, [rbx+78h]
0x140100073  test    rcx, rcx
0x140100076  jz      short loc_140100089
0x140100078  mov     r8b, 1
0x14010007b  xor     edx, edx
0x14010007d  call    cs:__imp_SeReleaseSecurityDescriptor
0x140100084  nop     dword ptr [rax+rax+00h]
0x140100089  mov     rcx, [rbx+88h]
0x140100090  test    rcx, rcx
0x140100093  jz      short loc_1401000C1
0x140100095  call    cs:__imp_SeDeleteClientSecurity
0x14010009c  nop     dword ptr [rax+rax+00h]
0x1401000a1  mov     rcx, [rbx+88h]; P
0x1401000a8  xor     edx, edx; Tag
0x1401000aa  call    cs:__imp_ExFreePoolWithTag
0x1401000b1  nop     dword ptr [rax+rax+00h]
0x1401000b6  mov     qword ptr [rbx+88h], 0
0x1401000c1  mov     rcx, [rbx+0A0h]
0x1401000c8  test    rcx, rcx
0x1401000cb  jz      short loc_1401000D2
0x1401000cd  call    UlFreeLogFileBuffer
0x1401000d2  xor     edx, edx; Tag
0x1401000d4  mov     dword ptr [rbx], 666C4C75h
0x1401000da  mov     rcx, rbx; P
0x1401000dd  call    cs:__imp_ExFreePoolWithTag
0x1401000e4  nop     dword ptr [rax+rax+00h]
0x1401000e9  test    byte ptr cs:xmmword_1401A2CA0+9, 8
0x1401000f0  jz      short loc_14010010B
0x1401000f2  mov     edx, 32h ; '2'
0x1401000f7  lea     r8, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids
0x1401000fe  mov     ecx, 50Bh
0x140100103  mov     r9, rdi
0x140100106  call    WPP_SF_q
0x14010010b  mov     rbx, [rsp+28h+arg_0]
0x140100110  mov     rsi, [rsp+28h+arg_8]
0x140100115  add     rsp, 20h
0x140100119  pop     rdi
0x14010011a  retn
0x14010011c  mov     ecx, 3
0x140100121  int     29h; Win8: RtlFailFast(ecx)
```
