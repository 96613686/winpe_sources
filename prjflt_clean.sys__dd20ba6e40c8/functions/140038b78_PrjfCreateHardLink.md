# PrjfCreateHardLink

- ea: `0x140038b78`
- end: `0x140038f14`
- name: `PrjfCreateHardLink`
- size: `924`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400368c4`

## callees

- `0x14000bb80`
- `0x14000d008`
- `0x14000d754`
- `0x140038b78`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140038ed8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038ed8`
- `ntoskrnl!ExAllocatePool2` at `0x140038d00`
- `ntoskrnl!ExAllocatePool2` at `0x140038d00`
- `FLTMGR!FltCreateFileEx` at `0x140038c57`
- `FLTMGR!FltCreateFileEx` at `0x140038c57`
- `FLTMGR!FltSetInformationFile` at `0x140038dc9`
- `FLTMGR!FltSetInformationFile` at `0x140038dc9`
- `FLTMGR!FltClose` at `0x140038eed`
- `FLTMGR!FltClose` at `0x140038eed`

## pseudocode

```c
__int64 __fastcall PrjfCreateHardLink(PFLT_INSTANCE Instance, __int64 a2, const void **a3)
{
  __int16 v3; // ax
  NTSTATUS v6; // eax
  int v7; // edx
  int v8; // r8d
  NTSTATUS v9; // ebx
  __int64 Pool2; // rax
  int v11; // edx
  int v12; // r8d
  _QWORD *v13; // rdi
  int v14; // edx
  int v15; // r8d
  _WORD v17[2]; // [rsp+80h] [rbp-9h] BYREF
  int v18; // [rsp+84h] [rbp-5h]
  __int64 v19; // [rsp+88h] [rbp-1h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp+17h] BYREF
  PFILE_OBJECT FileObject; // [rsp+F8h] [rbp+6Fh] BYREF
  void *FileHandle; // [rsp+108h] [rbp+7Fh] BYREF

  v3 = *(_WORD *)(a2 + 4);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v18 = 0;
  v17[0] = v3;
  v17[1] = v3;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v19 = a2 + 6;
  FileHandle = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v17;
  FileObject = 0;
  IoStatusBlock = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = FltCreateFileEx(
         Globals,
         Instance,
         &FileHandle,
         &FileObject,
         0x100100u,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0,
         7u,
         1u,
         0x204020u,
         0,
         0,
         1u);
  v9 = v6;
  if ( v6 >= 0 )
  {
    Pool2 = ExAllocatePool2(256, *(unsigned __int16 *)a3 + 24LL, 1852590672);
    v13 = (_QWORD *)Pool2;
    if ( Pool2 )
    {
      memmove((void *)(Pool2 + 20), a3[1], *(unsigned __int16 *)a3);
      *(_BYTE *)v13 = 0;
      v13[1] = 0;
      *((_DWORD *)v13 + 4) = *(unsigned __int16 *)a3;
      v9 = FltSetInformationFile(Instance, FileObject, v13, *(unsigned __int16 *)a3 + 24, FileLinkInformation);
      if ( v9 == -1073741771 )
      {
        if ( (BYTE8(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v14) = BYTE8(xmmword_14001A3D0) & 0x20;
          LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdZ(
            773,
            v14,
            v15,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            3,
            5,
            133,
            (__int64)&WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
            20,
            53,
            (__int64)a3);
        }
        v9 = 0;
      }
      else if ( v9 < 0
             && ((xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        LOBYTE(v14) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          517,
          v14,
          v15,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          134,
          (__int64)&WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          29,
          v9,
          (__int64)a3);
      }
      ExFreePoolWithTag(v13, 0x6E6C4A50u);
    }
    else
    {
      v9 = -1073741670;
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(
          517,
          v11,
          v12,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          132,
          (__int64)&WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          246);
      }
    }
  }
  else if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = xmmword_14001A3D0 & 0x20;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDdZ(
      517,
      v7,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      5,
      131,
      (__int64)&WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
      234,
      v6,
      (__int64)v17);
  }
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140038b78  mov     [rsp-8+arg_0], rbx
0x140038b7d  mov     [rsp-8+arg_10], rsi
0x140038b82  push    rbp
0x140038b83  push    rdi
0x140038b84  push    r14
0x140038b86  lea     rbp, [rsp-47h]
0x140038b8b  sub     rsp, 0D0h
0x140038b92  movzx   eax, word ptr [rdx+4]
0x140038b96  lea     r9, [rbp+57h+FileObject]; FileObject
0x140038b9a  xorps   xmm0, xmm0
0x140038b9d  mov     qword ptr [rbp+57h+var_40.Length], 30h ; '0'
0x140038ba5  movups  [rbp+57h+var_60], xmm0
0x140038ba9  mov     word ptr [rbp+57h+var_60], ax
0x140038bad  mov     rsi, r8
0x140038bb0  mov     word ptr [rbp+57h+var_60+2], ax
0x140038bb4  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x140038bb8  lea     rax, [rdx+6]
0x140038bbc  mov     qword ptr [rbp+57h+var_40.Attributes], 240h
0x140038bc4  mov     qword ptr [rbp+57h+var_60+8], rax
0x140038bc8  mov     r14, rcx
0x140038bcb  lea     rax, [rbp+57h+var_60]
0x140038bcf  mov     [rbp+57h+FileHandle], 0
0x140038bd7  mov     [rbp+57h+var_40.ObjectName], rax
0x140038bdb  mov     rdx, rcx; Instance
0x140038bde  mov     rcx, cs:Globals; Filter
0x140038be5  mov     eax, 1
0x140038bea  mov     [rsp+0E0h+Flags], eax; Flags
0x140038bee  mov     [rsp+0E0h+EaLength], 0; EaLength
0x140038bf6  mov     [rsp+0E0h+EaBuffer], 0; EaBuffer
0x140038bff  mov     [rsp+0E0h+CreateOptions], 204020h; CreateOptions
0x140038c07  mov     [rsp+0E0h+CreateDisposition], eax; CreateDisposition
0x140038c0b  lea     rax, [rbp+57h+var_50]
0x140038c0f  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x140038c17  mov     [rsp+0E0h+FileAttributes], 0; FileAttributes
0x140038c1f  mov     [rsp+0E0h+AllocationSize], 0; AllocationSize
0x140038c28  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x140038c2d  lea     rax, [rbp+57h+var_40]
0x140038c31  mov     [rsp+0E0h+ObjectAttributes], rax; ObjectAttributes
0x140038c36  mov     [rsp+0E0h+DesiredAccess], 100100h; DesiredAccess
0x140038c3e  mov     [rbp+57h+FileObject], 0
0x140038c46  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x140038c4a  mov     [rbp+57h+var_40.RootDirectory], 0
0x140038c52  movdqu  xmmword ptr [rbp+57h+var_40.SecurityDescriptor], xmm0
0x140038c57  call    cs:__imp_FltCreateFileEx
0x140038c5e  nop     dword ptr [rax+rax+00h]
0x140038c63  mov     ebx, eax
0x140038c65  test    eax, eax
0x140038c67  jns     loc_140038CEE
0x140038c6d  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140038c73  lea     rcx, WPP_RECORDER_INITIALIZED
0x140038c7a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140038c81  setnz   r8b
0x140038c85  and     dl, 20h
0x140038c88  jnz     short loc_140038C93
0x140038c8a  test    r8b, r8b
0x140038c8d  jz      loc_140038EE4
0x140038c93  mov     r9, cs:WPP_GLOBAL_Control
0x140038c9a  lea     rax, [rbp+57h+var_60]
0x140038c9e  mov     qword ptr [rsp+0E0h+CreateOptions], rax
0x140038ca3  mov     ecx, 205h
0x140038ca8  mov     [rsp+0E0h+CreateDisposition], ebx
0x140038cac  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140038cb3  mov     [rsp+0E0h+ShareAccess], 16EAh
0x140038cbb  mov     r9, [r9+40h]
0x140038cbf  mov     qword ptr [rsp+0E0h+FileAttributes], rax
0x140038cc4  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140038ccb  mov     [rsp+0E0h+AllocationSize], rax
0x140038cd0  mov     word ptr [rsp+0E0h+IoStatusBlock], 83h
0x140038cd7  mov     dword ptr [rsp+0E0h+ObjectAttributes], 5
0x140038cdf  mov     byte ptr [rsp+0E0h+DesiredAccess], 2
0x140038ce4  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140038ce9  jmp     loc_140038EE4
0x140038cee  movzx   edx, word ptr [rsi]
0x140038cf1  mov     ecx, 100h
0x140038cf6  add     rdx, 18h
0x140038cfa  mov     r8d, 6E6C4A50h
0x140038d00  call    cs:__imp_ExAllocatePool2
0x140038d07  nop     dword ptr [rax+rax+00h]
0x140038d0c  mov     rdi, rax
0x140038d0f  test    rax, rax
0x140038d12  jnz     short loc_140038D8D
0x140038d14  mov     ebx, 0C000009Ah
0x140038d19  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140038d1f  lea     rcx, WPP_RECORDER_INITIALIZED
0x140038d26  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140038d2d  setnz   r8b
0x140038d31  and     dl, 20h
0x140038d34  jnz     short loc_140038D3F
0x140038d36  test    r8b, r8b
0x140038d39  jz      loc_140038EE4
0x140038d3f  mov     r9, cs:WPP_GLOBAL_Control
0x140038d46  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140038d4d  mov     [rsp+0E0h+ShareAccess], 16F6h
0x140038d55  mov     ecx, 205h
0x140038d5a  mov     qword ptr [rsp+0E0h+FileAttributes], rax
0x140038d5f  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140038d66  mov     [rsp+0E0h+AllocationSize], rax
0x140038d6b  mov     r9, [r9+40h]
0x140038d6f  mov     word ptr [rsp+0E0h+IoStatusBlock], 84h
0x140038d76  mov     dword ptr [rsp+0E0h+ObjectAttributes], 5
0x140038d7e  mov     byte ptr [rsp+0E0h+DesiredAccess], 2
0x140038d83  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140038d88  jmp     loc_140038EE4
0x140038d8d  movzx   r8d, word ptr [rsi]; Size
0x140038d91  lea     rcx, [rax+14h]; void *
0x140038d95  mov     rdx, [rsi+8]; Src
0x140038d99  call    memmove
0x140038d9e  mov     byte ptr [rdi], 0
0x140038da1  mov     r8, rdi; FileInformation
0x140038da4  mov     qword ptr [rdi+8], 0
0x140038dac  mov     rcx, r14; Instance
0x140038daf  movzx   eax, word ptr [rsi]
0x140038db2  mov     [rdi+10h], eax
0x140038db5  movzx   r9d, word ptr [rsi]
0x140038db9  mov     rdx, [rbp+57h+FileObject]; FileObject
0x140038dbd  add     r9d, 18h; Length
0x140038dc1  mov     [rsp+0E0h+DesiredAccess], 0Bh; FileInformationClass
0x140038dc9  call    cs:__imp_FltSetInformationFile
0x140038dd0  nop     dword ptr [rax+rax+00h]
0x140038dd5  mov     ebx, eax
0x140038dd7  mov     eax, 0C0000035h
0x140038ddc  cmp     ebx, eax
0x140038dde  jnz     short loc_140038E58
0x140038de0  mov     dl, byte ptr cs:xmmword_14001A3D0+8
0x140038de6  lea     rcx, WPP_RECORDER_INITIALIZED
0x140038ded  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140038df4  setnz   r8b
0x140038df8  and     dl, 20h
0x140038dfb  jnz     short loc_140038E02
0x140038dfd  test    r8b, r8b
0x140038e00  jz      short loc_140038E54
0x140038e02  mov     r9, cs:WPP_GLOBAL_Control
0x140038e09  mov     ecx, 305h
0x140038e0e  mov     qword ptr [rsp+0E0h+CreateOptions], rsi
0x140038e13  mov     [rsp+0E0h+CreateDisposition], eax
0x140038e17  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140038e1e  mov     [rsp+0E0h+ShareAccess], 1714h
0x140038e26  mov     r9, [r9+40h]
0x140038e2a  mov     qword ptr [rsp+0E0h+FileAttributes], rax
0x140038e2f  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140038e36  mov     [rsp+0E0h+AllocationSize], rax
0x140038e3b  mov     word ptr [rsp+0E0h+IoStatusBlock], 85h
0x140038e42  mov     dword ptr [rsp+0E0h+ObjectAttributes], 5
0x140038e4a  mov     byte ptr [rsp+0E0h+DesiredAccess], 3
0x140038e4f  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140038e54  xor     ebx, ebx
0x140038e56  jmp     short loc_140038ED0
0x140038e58  test    ebx, ebx
0x140038e5a  jns     short loc_140038ED0
0x140038e5c  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140038e62  lea     rcx, WPP_RECORDER_INITIALIZED
0x140038e69  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140038e70  setnz   r8b
0x140038e74  and     dl, 20h
0x140038e77  jnz     short loc_140038E7E
0x140038e79  test    r8b, r8b
0x140038e7c  jz      short loc_140038ED0
0x140038e7e  mov     r9, cs:WPP_GLOBAL_Control
0x140038e85  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140038e8c  mov     qword ptr [rsp+0E0h+CreateOptions], rsi
0x140038e91  mov     ecx, 205h
0x140038e96  mov     [rsp+0E0h+CreateDisposition], ebx
0x140038e9a  mov     [rsp+0E0h+ShareAccess], 171Dh
0x140038ea2  mov     r9, [r9+40h]
0x140038ea6  mov     qword ptr [rsp+0E0h+FileAttributes], rax
0x140038eab  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140038eb2  mov     [rsp+0E0h+AllocationSize], rax
0x140038eb7  mov     word ptr [rsp+0E0h+IoStatusBlock], 86h
0x140038ebe  mov     dword ptr [rsp+0E0h+ObjectAttributes], 5
0x140038ec6  mov     byte ptr [rsp+0E0h+DesiredAccess], 2
0x140038ecb  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140038ed0  mov     edx, 6E6C4A50h; Tag
0x140038ed5  mov     rcx, rdi; P
0x140038ed8  call    cs:__imp_ExFreePoolWithTag
0x140038edf  nop     dword ptr [rax+rax+00h]
0x140038ee4  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140038ee8  test    rcx, rcx
0x140038eeb  jz      short loc_140038EF9
0x140038eed  call    cs:__imp_FltClose
0x140038ef4  nop     dword ptr [rax+rax+00h]
0x140038ef9  lea     r11, [rsp+0E0h+var_10]
0x140038f01  mov     eax, ebx
0x140038f03  mov     rbx, [r11+20h]
0x140038f07  mov     rsi, [r11+30h]
0x140038f0b  mov     rsp, r11
0x140038f0e  pop     r14
0x140038f10  pop     rdi
0x140038f11  pop     rbp
0x140038f12  retn
```
