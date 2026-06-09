# CheckPrivilege

- ea: `0x18000c2e0`
- end: `0x18000c443`
- name: `CheckPrivilege`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000b140`

## callees

- `0x18000c2e0`
- `0x18000c44c`
- `0x180021f1c`

## import_xrefs

- `ntoskrnl!SeSinglePrivilegeCheck` at `0x18000c323`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x18000c323`

## pseudocode

```c
BOOLEAN __fastcall CheckPrivilege(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  KPROCESSOR_MODE v7; // dl
  char v8; // bp
  BOOLEAN result; // al
  int v10; // edx
  int v11; // r8d
  __int64 v12; // rdx

  v3 = *(_QWORD *)(a3 + 184);
  if ( (*(_BYTE *)(v3 + 2) & 1) != 0 )
  {
    v8 = 1;
    v7 = 1;
  }
  else
  {
    v7 = *(_BYTE *)(a3 + 64);
    v8 = 0;
  }
  result = SeSinglePrivilegeCheck((LUID)7LL, v7);
  if ( !result )
  {
    LOBYTE(v10) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdqqdd(WPP_GLOBAL_Control->AttachedDevice, v10, v11, *(_QWORD *)(a1 + 672), 4, 4, 47);
    }
    if ( v8 )
    {
      v12 = *(_QWORD *)(a1 + 152) + 424LL * *(unsigned int *)(a2 + 12);
      TraceLoggingPrivilegeNotFoundForCreateWithSFAC(
        a1,
        *(unsigned __int16 *)(v12 + 8),
        *(unsigned __int16 *)(v12 + 10),
        *(unsigned __int8 *)(a3 + 64),
        *(_DWORD *)(*(_QWORD *)(v3 + 8) + 16LL));
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000c2e0  push    rbx
0x18000c2e2  push    rbp
0x18000c2e3  push    rsi
0x18000c2e4  push    rdi
0x18000c2e5  push    r14
0x18000c2e7  push    r15
0x18000c2e9  sub     rsp, 78h
0x18000c2ed  mov     rsi, [r8+0B8h]
0x18000c2f4  mov     rbx, r8
0x18000c2f7  mov     r14, rdx
0x18000c2fa  mov     qword ptr [rsp+0A8h+PrivilegeValue.LowPart], 7
0x18000c306  mov     r15, rcx
0x18000c309  test    byte ptr [rsi+2], 1
0x18000c30d  jnz     loc_18000C3FF
0x18000c313  movzx   edx, byte ptr [r8+40h]; PreviousMode
0x18000c318  xor     bpl, bpl
0x18000c31b  mov     rcx, qword ptr [rsp+0A8h+PrivilegeValue.LowPart]; PrivilegeValue
0x18000c323  call    cs:__imp_SeSinglePrivilegeCheck
0x18000c32a  nop     dword ptr [rax+rax+00h]
0x18000c32f  movzx   edi, al
0x18000c332  test    al, al
0x18000c334  jnz     short loc_18000C377
0x18000c336  mov     r11, cs:WPP_GLOBAL_Control
0x18000c33d  lea     rax, WPP_GLOBAL_Control
0x18000c344  cmp     r11, rax
0x18000c347  jnz     loc_18000C3E0
0x18000c34d  xor     dl, dl
0x18000c34f  lea     rax, WPP_RECORDER_INITIALIZED
0x18000c356  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000c35d  setnz   r8b
0x18000c361  test    dl, dl
0x18000c363  jnz     short loc_18000C385
0x18000c365  test    r8b, r8b
0x18000c368  jnz     short loc_18000C385
0x18000c36a  test    bpl, bpl
0x18000c36d  jnz     loc_18000C40B
0x18000c373  movzx   eax, dil
0x18000c377  add     rsp, 78h
0x18000c37b  pop     r15
0x18000c37d  pop     r14
0x18000c37f  pop     rdi
0x18000c380  pop     rsi
0x18000c381  pop     rbp
0x18000c382  pop     rbx
0x18000c383  retn
0x18000c385  movsx   r9d, byte ptr [rbx+40h]
0x18000c38a  mov     r10, [r14+40h]
0x18000c38e  mov     rcx, [r11+18h]
0x18000c392  movzx   eax, bpl
0x18000c396  mov     [rsp+0A8h+var_40], eax
0x18000c39a  mov     rax, [r14+30h]
0x18000c39e  mov     [rsp+0A8h+var_48], r9d
0x18000c3a3  mov     r9, [r15+2A0h]
0x18000c3aa  mov     [rsp+0A8h+var_50], rbx
0x18000c3af  mov     [rsp+0A8h+var_58], rax
0x18000c3b4  mov     eax, [r14+8]
0x18000c3b8  mov     [rsp+0A8h+var_60], eax
0x18000c3bc  mov     rax, [r10+20h]
0x18000c3c0  mov     [rsp+0A8h+var_68], rax
0x18000c3c5  mov     [rsp+0A8h+var_78], 2Fh ; '/'
0x18000c3cc  mov     [rsp+0A8h+var_80], 4
0x18000c3d4  mov     byte ptr [rsp+0A8h+var_88], 4
0x18000c3d9  call    WPP_RECORDER_AND_TRACE_SF_qdqqdd
0x18000c3de  jmp     short loc_18000C36A
0x18000c3e0  mov     ecx, [r11+2Ch]
0x18000c3e4  test    cl, 8
0x18000c3e7  jz      loc_18000C34D
0x18000c3ed  cmp     byte ptr [r11+29h], 4
0x18000c3f2  jb      loc_18000C34D
0x18000c3f8  mov     dl, 1
0x18000c3fa  jmp     loc_18000C34F
0x18000c3ff  mov     bpl, 1
0x18000c402  movzx   edx, bpl
0x18000c406  jmp     loc_18000C31B
0x18000c40b  mov     eax, [r14+0Ch]
0x18000c40f  movzx   r9d, byte ptr [rbx+40h]
0x18000c414  imul    rdx, rax, 1A8h
0x18000c41b  mov     rax, [rsi+8]
0x18000c41f  add     rdx, [r15+98h]
0x18000c426  mov     ecx, [rax+10h]
0x18000c429  movzx   r8d, word ptr [rdx+0Ah]
0x18000c42e  movzx   edx, word ptr [rdx+8]
0x18000c432  mov     [rsp+0A8h+var_88], ecx
0x18000c436  mov     rcx, r15
0x18000c439  call    TraceLoggingPrivilegeNotFoundForCreateWithSFAC
0x18000c43e  jmp     loc_18000C373
```
