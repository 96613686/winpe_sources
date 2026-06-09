# HidpFdoRegistryQueryULong

- ea: `0x180018d78`
- end: `0x18001900e`
- name: `HidpFdoRegistryQueryULong`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003b748`

## callees

- `0x180018d78`
- `0x18001e600`
- `0x18001e760`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x180018e5f`
- `ntoskrnl!ZwQueryValueKey` at `0x180018e5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180018ff4`
- `ntoskrnl!ExFreePoolWithTag` at `0x180018ff4`
- `ntoskrnl!ExAllocatePool2` at `0x180018da3`
- `ntoskrnl!ExAllocatePool2` at `0x180018da3`

## pseudocode

```c
__int64 __fastcall HidpFdoRegistryQueryULong(__int64 a1, void *a2, struct _UNICODE_STRING *a3, _DWORD *a4)
{
  _DWORD *Pool2; // rax
  int v9; // edx
  int v10; // r8d
  _DWORD *v11; // rdi
  unsigned int v12; // ebx
  NTSTATUS ValueKey; // eax
  int v14; // edx
  int v15; // r8d
  _DEVICE_OBJECT *AttachedDevice; // rcx
  ULONG Length; // [rsp+20h] [rbp-78h]
  int ResultLength; // [rsp+28h] [rbp-70h]
  ULONG v20[14]; // [rsp+60h] [rbp-38h] BYREF

  v20[0] = 16;
  Pool2 = (_DWORD *)ExAllocatePool2(256, 16, 1130654024);
  v11 = Pool2;
  if ( Pool2 )
  {
    ValueKey = ZwQueryValueKey(a2, a3, KeyValuePartialInformation, Pool2, v20[0], v20);
    v12 = ValueKey;
    if ( ValueKey >= 0 )
    {
      if ( v11[2] == 4 )
      {
        *a4 = v11[3];
        LOBYTE(v14) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        if ( (_BYTE)v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_qSL(
            WPP_GLOBAL_Control->AttachedDevice,
            v14,
            v15,
            *(_QWORD *)(a1 + 672),
            Length,
            ResultLength);
        }
        v12 = 0;
        goto LABEL_39;
      }
      v12 = -1073741811;
      LOBYTE(v14) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)v14 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_39:
        ExFreePoolWithTag(v11, 0);
        return v12;
      }
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    }
    else
    {
      if ( ValueKey == -1073741772 )
        goto LABEL_39;
      LOBYTE(v14) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)v14 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_39;
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    }
    WPP_RECORDER_AND_TRACE_SF_qSLd((_DWORD)AttachedDevice, v14, v15, *(_QWORD *)(a1 + 672));
    goto LABEL_39;
  }
  v12 = -1073741670;
  LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
  if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qSLd(WPP_GLOBAL_Control->AttachedDevice, v9, v10, *(_QWORD *)(a1 + 672));
  }
  return v12;
}

```

## disassembly

```asm
0x180018d78  push    rbx
0x180018d7a  push    rbp
0x180018d7b  push    rsi
0x180018d7c  push    rdi
0x180018d7d  push    r14
0x180018d7f  sub     rsp, 70h
0x180018d83  mov     rbx, rdx
0x180018d86  mov     rbp, r8
0x180018d89  mov     edx, 10h
0x180018d8e  mov     r14, rcx
0x180018d91  mov     ecx, 100h
0x180018d96  mov     [rsp+98h+var_38], edx
0x180018d9a  mov     r8d, 43646948h
0x180018da0  mov     rsi, r9
0x180018da3  call    cs:__imp_ExAllocatePool2
0x180018daa  nop     dword ptr [rax+rax+00h]
0x180018daf  mov     rdi, rax
0x180018db2  test    rax, rax
0x180018db5  jnz     loc_180018E3E
0x180018dbb  mov     ebx, 0C000009Ah
0x180018dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180018dc7  lea     rax, WPP_GLOBAL_Control
0x180018dce  cmp     rcx, rax
0x180018dd1  jz      short loc_180018DE4
0x180018dd3  mov     eax, [rcx+2Ch]
0x180018dd6  test    al, 4
0x180018dd8  jz      short loc_180018DE4
0x180018dda  cmp     byte ptr [rcx+29h], 2
0x180018dde  jb      short loc_180018DE4
0x180018de0  mov     dl, 1
0x180018de2  jmp     short loc_180018DE6
0x180018de4  xor     dl, dl
0x180018de6  lea     rax, WPP_RECORDER_INITIALIZED
0x180018ded  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180018df4  setnz   r8b
0x180018df8  test    dl, dl
0x180018dfa  jnz     short loc_180018E05
0x180018dfc  test    r8b, r8b
0x180018dff  jz      loc_180019000
0x180018e05  mov     eax, [rsp+98h+var_38]
0x180018e09  mov     r9, [r14+2A0h]
0x180018e10  mov     rcx, [rcx+18h]
0x180018e14  mov     [rsp+98h+var_40], ebx
0x180018e18  mov     [rsp+98h+var_48], eax
0x180018e1c  mov     rax, [rbp+8]
0x180018e20  mov     [rsp+98h+var_50], rax
0x180018e25  mov     rax, [r14]
0x180018e28  mov     [rsp+98h+var_58], rax
0x180018e2d  mov     [rsp+98h+var_68], 1Ch
0x180018e34  call    WPP_RECORDER_AND_TRACE_SF_qSLd
0x180018e39  jmp     loc_180019000
0x180018e3e  lea     rax, [rsp+98h+var_38]
0x180018e43  mov     r9, rdi; KeyValueInformation
0x180018e46  mov     [rsp+98h+ResultLength], rax; ResultLength
0x180018e4b  mov     r8d, 2; KeyValueInformationClass
0x180018e51  mov     eax, [rsp+98h+var_38]
0x180018e55  mov     rdx, rbp; ValueName
0x180018e58  mov     rcx, rbx; KeyHandle
0x180018e5b  mov     [rsp+98h+Length], eax; Length
0x180018e5f  call    cs:__imp_ZwQueryValueKey
0x180018e66  nop     dword ptr [rax+rax+00h]
0x180018e6b  mov     ebx, eax
0x180018e6d  test    eax, eax
0x180018e6f  jns     loc_180018F01
0x180018e75  cmp     eax, 0C0000034h
0x180018e7a  jz      loc_180018FEF
0x180018e80  mov     r10, cs:WPP_GLOBAL_Control
0x180018e87  lea     rax, WPP_GLOBAL_Control
0x180018e8e  cmp     r10, rax
0x180018e91  jz      short loc_180018EA7
0x180018e93  mov     ecx, [r10+2Ch]
0x180018e97  test    cl, 4
0x180018e9a  jz      short loc_180018EA7
0x180018e9c  cmp     byte ptr [r10+29h], 2
0x180018ea1  jb      short loc_180018EA7
0x180018ea3  mov     dl, 1
0x180018ea5  jmp     short loc_180018EA9
0x180018ea7  xor     dl, dl
0x180018ea9  lea     rax, WPP_RECORDER_INITIALIZED
0x180018eb0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180018eb7  setnz   r8b
0x180018ebb  test    dl, dl
0x180018ebd  jnz     short loc_180018EC8
0x180018ebf  test    r8b, r8b
0x180018ec2  jz      loc_180018FEF
0x180018ec8  mov     eax, [rsp+98h+var_38]
0x180018ecc  mov     rcx, [r10+18h]
0x180018ed0  mov     [rsp+98h+var_40], ebx
0x180018ed4  mov     [rsp+98h+var_48], eax
0x180018ed8  mov     rax, [rbp+8]
0x180018edc  mov     [rsp+98h+var_50], rax
0x180018ee1  mov     rax, [r14]
0x180018ee4  mov     [rsp+98h+var_58], rax
0x180018ee9  mov     [rsp+98h+var_68], 1Dh
0x180018ef0  mov     r9, [r14+2A0h]
0x180018ef7  call    WPP_RECORDER_AND_TRACE_SF_qSLd
0x180018efc  jmp     loc_180018FEF
0x180018f01  mov     r9d, [rdi+8]
0x180018f05  cmp     r9d, 4
0x180018f09  jz      short loc_180018F7F
0x180018f0b  mov     ebx, 0C000000Dh
0x180018f10  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f17  lea     rax, WPP_GLOBAL_Control
0x180018f1e  cmp     rcx, rax
0x180018f21  jz      short loc_180018F34
0x180018f23  mov     eax, [rcx+2Ch]
0x180018f26  test    al, 4
0x180018f28  jz      short loc_180018F34
0x180018f2a  cmp     byte ptr [rcx+29h], 2
0x180018f2e  jb      short loc_180018F34
0x180018f30  mov     dl, 1
0x180018f32  jmp     short loc_180018F36
0x180018f34  xor     dl, dl
0x180018f36  lea     rax, WPP_RECORDER_INITIALIZED
0x180018f3d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180018f44  setnz   r8b
0x180018f48  test    dl, dl
0x180018f4a  jnz     short loc_180018F55
0x180018f4c  test    r8b, r8b
0x180018f4f  jz      loc_180018FEF
0x180018f55  mov     rax, [rbp+8]
0x180018f59  mov     rcx, [rcx+18h]
0x180018f5d  mov     [rsp+98h+var_40], ebx
0x180018f61  mov     [rsp+98h+var_48], r9d
0x180018f66  mov     [rsp+98h+var_50], rax
0x180018f6b  mov     rax, [r14]
0x180018f6e  mov     [rsp+98h+var_58], rax
0x180018f73  mov     [rsp+98h+var_68], 1Eh
0x180018f7a  jmp     loc_180018EF0
0x180018f7f  mov     r9d, [rdi+0Ch]
0x180018f83  mov     [rsi], r9d
0x180018f86  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f8d  lea     rax, WPP_GLOBAL_Control
0x180018f94  cmp     rcx, rax
0x180018f97  jz      short loc_180018FAA
0x180018f99  mov     eax, [rcx+2Ch]
0x180018f9c  test    al, 4
0x180018f9e  jz      short loc_180018FAA
0x180018fa0  cmp     byte ptr [rcx+29h], 4
0x180018fa4  jb      short loc_180018FAA
0x180018fa6  mov     dl, 1
0x180018fa8  jmp     short loc_180018FAC
0x180018faa  xor     dl, dl
0x180018fac  lea     rax, WPP_RECORDER_INITIALIZED
0x180018fb3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180018fba  setnz   r8b
0x180018fbe  test    dl, dl
0x180018fc0  jnz     short loc_180018FC7
0x180018fc2  test    r8b, r8b
0x180018fc5  jz      short loc_180018FED
0x180018fc7  mov     rax, [rbp+8]
0x180018fcb  mov     rcx, [rcx+18h]
0x180018fcf  mov     [rsp+98h+var_48], r9d
0x180018fd4  mov     r9, [r14+2A0h]
0x180018fdb  mov     [rsp+98h+var_50], rax
0x180018fe0  mov     rax, [r14]
0x180018fe3  mov     [rsp+98h+var_58], rax
0x180018fe8  call    WPP_RECORDER_AND_TRACE_SF_qSL
0x180018fed  xor     ebx, ebx
0x180018fef  xor     edx, edx; Tag
0x180018ff1  mov     rcx, rdi; P
0x180018ff4  call    cs:__imp_ExFreePoolWithTag
0x180018ffb  nop     dword ptr [rax+rax+00h]
0x180019000  mov     eax, ebx
0x180019002  add     rsp, 70h
0x180019006  pop     r14
0x180019008  pop     rdi
0x180019009  pop     rsi
0x18001900a  pop     rbp
0x18001900b  pop     rbx
0x18001900c  retn
```
