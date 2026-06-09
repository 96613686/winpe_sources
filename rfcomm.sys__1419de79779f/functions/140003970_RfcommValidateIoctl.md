# RfcommValidateIoctl

- ea: `0x140003970`
- end: `0x140003bec`
- name: `RfcommValidateIoctl`
- size: `636`
- prototype: `char *__fastcall(__int64, __int64, _QWORD *, _QWORD *, __int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140001eec`

## callees

- `0x140003970`
- `0x140003bf4`
- `0x140003cb4`
- `0x14000aba8`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003abd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003abd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003b07`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003b07`

## string_xrefs

- `0x140003aee`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`
- `0x140003b30`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`

## pseudocode

```c
char *__fastcall RfcommValidateIoctl(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4, __int64 *a5, _QWORD *a6)
{
  char *v6; // rbx
  int v7; // r11d
  __int64 v8; // rdi
  __int64 v9; // rsi
  __int64 v10; // r15
  __int64 i; // r10
  int v14; // r9d
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  char *result; // rax

  v6 = 0;
  v7 = *(_DWORD *)(a2 + 24);
  v8 = 0;
  v9 = 0;
  v10 = 0;
  *a6 = 0;
  for ( i = 0; i != 12; ++i )
  {
    if ( v7 == *(_DWORD *)&g_IoctlDispatch[16 * i] )
      v6 = &g_IoctlDispatch[16 * i];
  }
  if ( v6 )
  {
    if ( *(_DWORD *)(a2 + 16) < *((_DWORD *)v6 + 1) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_12:
        v6 = 0;
        goto LABEL_43;
      }
      v14 = 78;
LABEL_11:
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        15,
        v14,
        (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids);
      goto LABEL_12;
    }
    if ( *(_DWORD *)(a2 + 8) < *((_DWORD *)v6 + 2) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_12;
      v14 = 79;
      goto LABEL_11;
    }
    v15 = *(_QWORD *)(a2 + 48);
    *a3 = 0;
    *a4 = 0;
    if ( v15 )
    {
      if ( *(_QWORD *)(v15 + 32) == 1 )
      {
        v9 = *(_QWORD *)(v15 + 24);
        if ( v9 && *(_DWORD *)(v9 + 16) == 1380205633 )
          RefObj_AddRefEx(v9 + 24, 1145981254, 1636, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c");
        else
          v9 = 0;
      }
      else if ( *(_QWORD *)(v15 + 32) == 2 )
      {
        v8 = *(_QWORD *)(v15 + 24);
        if ( !v8 || *(_DWORD *)(v8 + 16) != 1313754947 )
          v8 = 0;
        if ( v8 )
        {
          *(_BYTE *)(v8 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 48));
          v16 = TdiReferenceChannelLocked(v8, 1145981254);
          v9 = *(_QWORD *)(v8 + 104);
          v10 = v16;
          if ( v9 )
            RefObj_AddRefEx(v9 + 24, 1145981254, 1651, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c");
          KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 48), *(_BYTE *)(v8 + 56));
        }
      }
    }
    v17 = *((_DWORD *)v6 + 3);
    if ( v17 == 1 )
    {
      if ( !v9 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_12;
        v14 = 80;
        goto LABEL_11;
      }
    }
    else if ( v17 == 2 )
    {
      if ( !v8 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_12;
        v14 = 81;
        goto LABEL_11;
      }
    }
    else if ( v17 == 3 && !v10 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_12;
      v14 = 82;
      goto LABEL_11;
    }
    *a6 = *((unsigned int *)v6 + 2);
    goto LABEL_43;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      77,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      v7);
LABEL_43:
  result = v6;
  *a3 = v9;
  *a4 = v8;
  *a5 = v10;
  return result;
}

```

## disassembly

```asm
0x140003970  push    rbx
0x140003972  push    rbp
0x140003973  push    rsi
0x140003974  push    rdi
0x140003975  push    r12
0x140003977  push    r13
0x140003979  push    r14
0x14000397b  push    r15
0x14000397d  sub     rsp, 38h
0x140003981  mov     r14, [rsp+78h+arg_28]
0x140003989  xor     ebx, ebx
0x14000398b  mov     r11d, [rdx+18h]
0x14000398f  xor     edi, edi
0x140003991  xor     esi, esi
0x140003993  xor     r15d, r15d
0x140003996  mov     r12, r9
0x140003999  mov     r13, r8
0x14000399c  mov     [r14], rbx
0x14000399f  xor     r10d, r10d
0x1400039a2  mov     rax, r10
0x1400039a5  lea     rcx, g_IoctlDispatch; "t"
0x1400039ac  shl     rax, 4
0x1400039b0  add     rcx, rax
0x1400039b3  cmp     r11d, [rcx]
0x1400039b6  cmovz   rbx, rcx
0x1400039ba  inc     r10
0x1400039bd  cmp     r10, 0Ch
0x1400039c1  jnz     short loc_1400039A2
0x1400039c3  test    rbx, rbx
0x1400039c6  jnz     short loc_140003A0A
0x1400039c8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400039cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400039d6  jz      loc_140003BC4
0x1400039dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400039e3  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x1400039ea  mov     [rsp+78h+var_50], r11d
0x1400039ef  lea     r9d, [r10+41h]
0x1400039f3  lea     r8d, [r10+3]
0x1400039f7  mov     [rsp+78h+var_58], rax
0x1400039fc  mov     rcx, [rcx+40h]
0x140003a00  call    WPP_RECORDER_SF_d
0x140003a05  jmp     loc_140003BC4
0x140003a0a  mov     eax, [rbx+4]
0x140003a0d  cmp     [rdx+10h], eax
0x140003a10  jnb     short loc_140003A51
0x140003a12  lea     rax, WPP_RECORDER_INITIALIZED
0x140003a19  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003a20  jz      short loc_140003A4A
0x140003a22  mov     r9d, 4Eh ; 'N'
0x140003a28  mov     rcx, cs:WPP_GLOBAL_Control
0x140003a2f  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140003a36  mov     r8d, 0Fh
0x140003a3c  mov     [rsp+78h+var_58], rax
0x140003a41  mov     rcx, [rcx+40h]
0x140003a45  call    WPP_RECORDER_SF_
0x140003a4a  xor     ebx, ebx
0x140003a4c  jmp     loc_140003BC4
0x140003a51  mov     eax, [rbx+8]
0x140003a54  cmp     [rdx+8], eax
0x140003a57  jnb     short loc_140003A71
0x140003a59  lea     rax, WPP_RECORDER_INITIALIZED
0x140003a60  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003a67  jz      short loc_140003A4A
0x140003a69  mov     r9d, 4Fh ; 'O'
0x140003a6f  jmp     short loc_140003A28
0x140003a71  mov     rcx, [rdx+30h]
0x140003a75  mov     [r8], rsi
0x140003a78  mov     [r9], rsi
0x140003a7b  test    rcx, rcx
0x140003a7e  jz      loc_140003B46
0x140003a84  mov     rax, [rcx+20h]
0x140003a88  sub     rax, 1
0x140003a8c  jz      loc_140003B15
0x140003a92  cmp     rax, 1
0x140003a96  jnz     loc_140003B46
0x140003a9c  mov     rdi, [rcx+18h]
0x140003aa0  test    rdi, rdi
0x140003aa3  jz      short loc_140003AAE
0x140003aa5  cmp     dword ptr [rdi+10h], 4E4E4F43h
0x140003aac  jz      short loc_140003AB0
0x140003aae  xor     edi, edi
0x140003ab0  test    rdi, rdi
0x140003ab3  jz      loc_140003B46
0x140003ab9  lea     rcx, [rdi+30h]; SpinLock
0x140003abd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003ac4  nop     dword ptr [rax+rax+00h]
0x140003ac9  mov     edx, 444E4946h
0x140003ace  mov     rcx, rdi
0x140003ad1  mov     [rdi+38h], al
0x140003ad4  call    TdiReferenceChannelLocked
0x140003ad9  mov     rsi, [rdi+68h]
0x140003add  mov     r15, rax
0x140003ae0  test    rsi, rsi
0x140003ae3  jz      short loc_140003B00
0x140003ae5  lea     rcx, [rsi+18h]
0x140003ae9  mov     edx, 444E4946h
0x140003aee  lea     r9, File; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140003af5  mov     r8d, 673h
0x140003afb  call    RefObj_AddRefEx
0x140003b00  mov     dl, [rdi+38h]; NewIrql
0x140003b03  lea     rcx, [rdi+30h]; SpinLock
0x140003b07  call    cs:__imp_KeReleaseSpinLock
0x140003b0e  nop     dword ptr [rax+rax+00h]
0x140003b13  jmp     short loc_140003B46
0x140003b15  mov     rsi, [rcx+18h]
0x140003b19  test    rsi, rsi
0x140003b1c  jz      short loc_140003B44
0x140003b1e  cmp     dword ptr [rsi+10h], 52444441h
0x140003b25  jnz     short loc_140003B44
0x140003b27  lea     rcx, [rsi+18h]
0x140003b2b  mov     edx, 444E4946h
0x140003b30  lea     r9, File; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140003b37  mov     r8d, 664h
0x140003b3d  call    RefObj_AddRefEx
0x140003b42  jmp     short loc_140003B46
0x140003b44  xor     esi, esi
0x140003b46  mov     eax, [rbx+0Ch]
0x140003b49  cmp     eax, 1
0x140003b4c  jnz     short loc_140003B70
0x140003b4e  test    rsi, rsi
0x140003b51  jnz     short loc_140003BBE
0x140003b53  lea     rax, WPP_RECORDER_INITIALIZED
0x140003b5a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003b61  jz      loc_140003A4A
0x140003b67  lea     r9d, [rsi+50h]
0x140003b6b  jmp     loc_140003A28
0x140003b70  cmp     eax, 2
0x140003b73  jnz     short loc_140003B97
0x140003b75  test    rdi, rdi
0x140003b78  jnz     short loc_140003BBE
0x140003b7a  lea     rax, WPP_RECORDER_INITIALIZED
0x140003b81  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003b88  jz      loc_140003A4A
0x140003b8e  lea     r9d, [rdi+51h]
0x140003b92  jmp     loc_140003A28
0x140003b97  cmp     eax, 3
0x140003b9a  jnz     short loc_140003BBE
0x140003b9c  test    r15, r15
0x140003b9f  jnz     short loc_140003BBE
0x140003ba1  lea     rax, WPP_RECORDER_INITIALIZED
0x140003ba8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003baf  jz      loc_140003A4A
0x140003bb5  lea     r9d, [r15+52h]
0x140003bb9  jmp     loc_140003A28
0x140003bbe  mov     ecx, [rbx+8]
0x140003bc1  mov     [r14], rcx
0x140003bc4  mov     rcx, [rsp+78h+arg_20]
0x140003bcc  mov     rax, rbx
0x140003bcf  mov     [r13+0], rsi
0x140003bd3  mov     [r12], rdi
0x140003bd7  mov     [rcx], r15
0x140003bda  add     rsp, 38h
0x140003bde  pop     r15
0x140003be0  pop     r14
0x140003be2  pop     r13
0x140003be4  pop     r12
0x140003be6  pop     rdi
0x140003be7  pop     rsi
0x140003be8  pop     rbp
0x140003be9  pop     rbx
0x140003bea  retn
```
