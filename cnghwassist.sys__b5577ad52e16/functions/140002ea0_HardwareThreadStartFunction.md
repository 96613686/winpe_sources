# HardwareThreadStartFunction

- ea: `0x140002ea0`
- end: `0x140003055`
- name: `HardwareThreadStartFunction`
- size: `437`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000292c`
- `0x1400029cc`
- `0x140002ea0`
- `0x140003520`
- `0x140003e00`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140002ecd`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003032`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002ecd`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003032`
- `ntoskrnl!KeBugCheck` at `0x140003048`
- `ntoskrnl!KeBugCheck` at `0x140003048`

## pseudocode

```c
void __fastcall __noreturn HardwareThreadStartFunction(__int64 **StartContext)
{
  __int64 *v2; // rbx
  _DWORD *v3; // rsi
  unsigned int v4; // edi
  unsigned int v5; // r8d
  _DWORD *v6; // rdx
  __int64 v7; // rcx
  int v8; // eax
  _DWORD *v9; // [rsp+30h] [rbp-68h]
  int v10; // [rsp+38h] [rbp-60h]
  int *v11; // [rsp+40h] [rbp-58h]
  int v12; // [rsp+48h] [rbp-50h]
  int v13; // [rsp+A0h] [rbp+8h] BYREF

  v13 = 0;
  KeWaitForSingleObject(StartContext + 4, Executive, 0, 0, 0);
  while ( 1 )
  {
    v2 = *StartContext;
    v3 = (_DWORD *)**StartContext;
    if ( !*(_QWORD *)((*StartContext)[1] + 24) )
      break;
    v4 = v3[1];
    v5 = *((_DWORD *)v2 + 8);
    if ( v5 <= v4 + v3[2] )
    {
      v4 = v3[3];
      if ( v5 < v4 )
        v4 = *((_DWORD *)v2 + 8);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_DDD(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_08f1496475303aabf55216639506602d_Traceguids,
        *((unsigned int *)v2 + 39),
        v4,
        v5,
        v9,
        v10,
        v11,
        v12);
    v6 = (_DWORD *)v2[3];
    v12 = v3[6];
    v11 = &v13;
    v7 = *(_QWORD *)(v2[1] + 24);
    v10 = *((_DWORD *)v2 + 16);
    v9 = (_DWORD *)v2[7];
    if ( *((_BYTE *)v2 + 16) )
      v8 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD))(g_pHwCipherFunctionTable + 56))(v7, v6, v4);
    else
      v8 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD))(g_pHwCipherFunctionTable + 48))(v7, v6, v4);
    if ( v8 != -1073740698 || v13 )
    {
      *((_DWORD *)v2 + 22) = v8;
      if ( v8 < 0 )
        break;
      *((_DWORD *)v2 + 8) -= v4;
      *((_DWORD *)v2 + 16) -= v4;
      v2[3] += v4;
      v2[7] += v4;
      *((_DWORD *)v2 + 20) += v13;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          WPP_08f1496475303aabf55216639506602d_Traceguids,
          *((unsigned int *)v2 + 39));
    }
    else
    {
      *((_DWORD *)v2 + 23) |= 1u;
    }
    ScheduleRequestFromHardware(StartContext);
    KeWaitForSingleObject(StartContext + 4, Executive, 0, 0, 0);
  }
  KeBugCheck(0x6C746166u);
}

```

## disassembly

```asm
0x140002ea0  mov     rax, rsp
0x140002ea3  push    rbx
0x140002ea4  push    rbp
0x140002ea5  push    rsi
0x140002ea6  push    rdi
0x140002ea7  push    r12
0x140002ea9  push    r14
0x140002eab  sub     rsp, 68h
0x140002eaf  mov     r14, rcx
0x140002eb2  mov     dword ptr [rax+8], 0
0x140002eb9  add     rcx, 20h ; ' '; Object
0x140002ebd  mov     qword ptr [rax-78h], 0
0x140002ec5  xor     r9d, r9d; Alertable
0x140002ec8  xor     r8d, r8d; WaitMode
0x140002ecb  xor     edx, edx; WaitReason
0x140002ecd  call    cs:__imp_KeWaitForSingleObject
0x140002ed4  nop     dword ptr [rax+rax+00h]
0x140002ed9  lea     r12, WPP_GLOBAL_Control
0x140002ee0  mov     rbx, [r14]
0x140002ee3  mov     rax, [rbx+8]
0x140002ee7  mov     rsi, [rbx]
0x140002eea  cmp     qword ptr [rax+18h], 0
0x140002eef  jz      loc_140003043
0x140002ef5  mov     ecx, [rsi+8]
0x140002ef8  mov     edi, [rsi+4]
0x140002efb  add     ecx, edi
0x140002efd  mov     r8d, [rbx+20h]
0x140002f01  cmp     r8d, ecx
0x140002f04  ja      short loc_140002F10
0x140002f06  mov     edi, [rsi+0Ch]
0x140002f09  cmp     r8d, edi
0x140002f0c  cmovb   edi, r8d
0x140002f10  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f17  cmp     rcx, r12
0x140002f1a  jz      short loc_140002F48
0x140002f1c  mov     eax, [rcx+2Ch]
0x140002f1f  test    al, 4
0x140002f21  jz      short loc_140002F48
0x140002f23  mov     r9d, [rbx+9Ch]
0x140002f2a  mov     edx, 0Bh
0x140002f2f  mov     rcx, [rcx+18h]
0x140002f33  mov     [rsp+98h+var_70], r8d
0x140002f38  lea     r8, WPP_08f1496475303aabf55216639506602d_Traceguids
0x140002f3f  mov     dword ptr [rsp+98h+Timeout], edi
0x140002f43  call    WPP_SF_DDD
0x140002f48  mov     ecx, [rsi+18h]
0x140002f4b  mov     r8d, [rbx+40h]
0x140002f4f  mov     r9, [rbx+38h]
0x140002f53  mov     rsi, [rbx+8]
0x140002f57  mov     r10d, [rbx+30h]
0x140002f5b  mov     r11, [rbx+28h]
0x140002f5f  mov     rdx, [rbx+18h]
0x140002f63  mov     rax, cs:g_pHwCipherFunctionTable
0x140002f6a  mov     [rsp+98h+var_50], ecx
0x140002f6e  lea     rcx, [rsp+98h+arg_0]
0x140002f76  mov     [rsp+98h+var_58], rcx
0x140002f7b  mov     rcx, [rsi+18h]
0x140002f7f  mov     [rsp+98h+var_60], r8d
0x140002f84  mov     r8d, edi
0x140002f87  mov     [rsp+98h+var_68], r9
0x140002f8c  xor     r9d, r9d
0x140002f8f  mov     [rsp+98h+var_70], r10d
0x140002f94  mov     [rsp+98h+Timeout], r11
0x140002f99  cmp     [rbx+10h], r9b
0x140002f9d  jz      short loc_140002FA5
0x140002f9f  mov     rax, [rax+38h]
0x140002fa3  jmp     short loc_140002FA9
0x140002fa5  mov     rax, [rax+30h]
0x140002fa9  call    _guard_dispatch_icall
0x140002fae  cmp     eax, 0C0000466h
0x140002fb3  jnz     short loc_140002FC5
0x140002fb5  cmp     [rsp+98h+arg_0], 0
0x140002fbd  jnz     short loc_140002FC5
0x140002fbf  or      dword ptr [rbx+5Ch], 1
0x140002fc3  jmp     short loc_140003015
0x140002fc5  mov     [rbx+58h], eax
0x140002fc8  test    eax, eax
0x140002fca  js      short loc_140003043
0x140002fcc  sub     [rbx+20h], edi
0x140002fcf  sub     [rbx+40h], edi
0x140002fd2  mov     eax, edi
0x140002fd4  add     [rbx+18h], rax
0x140002fd8  add     [rbx+38h], rax
0x140002fdc  mov     eax, [rsp+98h+arg_0]
0x140002fe3  add     [rbx+50h], eax
0x140002fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x140002fed  cmp     rcx, r12
0x140002ff0  jz      short loc_140003015
0x140002ff2  mov     eax, [rcx+2Ch]
0x140002ff5  test    al, 4
0x140002ff7  jz      short loc_140003015
0x140002ff9  mov     r9d, [rbx+9Ch]
0x140003000  lea     r8, WPP_08f1496475303aabf55216639506602d_Traceguids
0x140003007  mov     rcx, [rcx+18h]
0x14000300b  mov     edx, 0Dh
0x140003010  call    WPP_SF_D
0x140003015  mov     rcx, r14
0x140003018  call    ScheduleRequestFromHardware
0x14000301d  xor     r9d, r9d; Alertable
0x140003020  mov     [rsp+98h+Timeout], 0; Timeout
0x140003029  xor     r8d, r8d; WaitMode
0x14000302c  lea     rcx, [r14+20h]; Object
0x140003030  xor     edx, edx; WaitReason
0x140003032  call    cs:__imp_KeWaitForSingleObject
0x140003039  nop     dword ptr [rax+rax+00h]
0x14000303e  jmp     loc_140002EE0
0x140003043  mov     ecx, 6C746166h; BugCheckCode
0x140003048  call    cs:__imp_KeBugCheck
```
