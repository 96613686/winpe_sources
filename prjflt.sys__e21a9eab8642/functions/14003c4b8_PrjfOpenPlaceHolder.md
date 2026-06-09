# PrjfOpenPlaceHolder

- ea: `0x14003c4b8`
- end: `0x14003c65f`
- name: `PrjfOpenPlaceHolder`
- size: `423`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, struct _UNICODE_STRING *, __int64, void **, PVOID *, _BYTE *)`
- caller_count: `7`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x140001b3c`
- `0x14000752c`
- `0x140007cec`
- `0x140024184`
- `0x140040670`
- `0x140041a3c`
- `0x140043844`

## callees

- `0x14000ba20`
- `0x14000d754`
- `0x14003c4b8`
- `0x14003c668`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14003c62d`
- `ntoskrnl!ObfDereferenceObject` at `0x14003c62d`
- `FLTMGR!FltClose` at `0x14003c618`
- `FLTMGR!FltClose` at `0x14003c618`

## pseudocode

```c
__int64 __fastcall PrjfOpenPlaceHolder(
        struct _FLT_INSTANCE *a1,
        struct _UNICODE_STRING *a2,
        __int64 a3,
        void **a4,
        PVOID *a5,
        _BYTE *a6)
{
  int v8; // edx
  int v9; // esi
  int v10; // r8d
  void *v11; // rcx
  int v13; // [rsp+28h] [rbp-71h]
  void *FileHandle; // [rsp+60h] [rbp-39h] BYREF
  PVOID Object; // [rsp+68h] [rbp-31h] BYREF
  __int64 v16[2]; // [rsp+70h] [rbp-29h] BYREF
  _QWORD v17[2]; // [rsp+80h] [rbp-19h] BYREF
  int v18; // [rsp+90h] [rbp-9h]
  int v19; // [rsp+94h] [rbp-5h]
  __int128 v20; // [rsp+98h] [rbp-1h]
  __int64 v21; // [rsp+A8h] [rbp+Fh]

  v17[0] = v16;
  v21 = 48;
  v17[1] = v16;
  FileHandle = 0;
  v16[0] = (__int64)v17;
  Object = 0;
  v16[1] = (__int64)v17;
  v18 = -1879048164;
  v20 = 0;
  v19 = -2147483644;
  v9 = PrjfOpenReparsePoint(a1, a2, 0, 0x80u, 0x29u, v13, (PVOID *)v16, &FileHandle, (PFILE_OBJECT *)&Object);
  if ( v9 < 0 )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = BYTE1(xmmword_14001A3D0) & 4;
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        522,
        v8,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        10,
        59,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        194,
        v9,
        (__int64)a2);
    }
    v11 = FileHandle;
    goto LABEL_10;
  }
  if ( a6 )
    *a6 = v19 & 1;
  v11 = 0;
  *a4 = FileHandle;
  FileHandle = 0;
  if ( a5 )
  {
    *a5 = Object;
    Object = 0;
LABEL_10:
    if ( v11 )
      FltClose(v11);
  }
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14003c4b8  mov     [rsp-8+arg_10], rbx
0x14003c4bd  push    rbp
0x14003c4be  push    rsi
0x14003c4bf  push    rdi
0x14003c4c0  push    r14
0x14003c4c2  push    r15
0x14003c4c4  lea     rbp, [rsp-27h]
0x14003c4c9  sub     rsp, 0C0h
0x14003c4d0  mov     rax, cs:__security_cookie
0x14003c4d7  xor     rax, rsp
0x14003c4da  mov     [rbp+47h+var_30], rax
0x14003c4de  mov     rdi, [rbp+47h+arg_20]
0x14003c4e2  lea     rax, [rbp+47h+var_70]
0x14003c4e6  mov     rbx, [rbp+47h+arg_28]
0x14003c4ea  mov     r14, r9
0x14003c4ed  mov     [rbp+47h+var_60], rax
0x14003c4f1  xorps   xmm0, xmm0
0x14003c4f4  lea     rax, [rbp+47h+var_70]
0x14003c4f8  mov     [rbp+47h+var_38], 30h ; '0'
0x14003c500  mov     [rbp+47h+var_58], rax
0x14003c504  mov     r9d, 80h
0x14003c50a  lea     rax, [rbp+47h+var_60]
0x14003c50e  mov     [rbp+47h+var_80], 0
0x14003c516  mov     [rbp+47h+var_70], rax
0x14003c51a  xor     r8d, r8d
0x14003c51d  lea     rax, [rbp+47h+var_60]
0x14003c521  mov     [rbp+47h+Object], 0
0x14003c529  mov     [rbp+47h+var_68], rax
0x14003c52d  mov     r15, rdx
0x14003c530  lea     rax, [rbp+47h+Object]
0x14003c534  mov     [rbp+47h+var_50], 9000001Ch
0x14003c53b  mov     [rsp+0E0h+FileObject], rax; FileObject
0x14003c540  lea     rax, [rbp+47h+var_80]
0x14003c544  mov     [rsp+0E0h+FileHandle], rax; FileHandle
0x14003c549  lea     rax, [rbp+47h+var_70]
0x14003c54d  mov     [rsp+0E0h+var_B0], rax; __int64
0x14003c552  mov     [rsp+0E0h+var_C0], 29h ; ')'; ULONG
0x14003c55a  movups  [rbp+47h+var_48], xmm0
0x14003c55e  mov     [rbp+47h+var_4C], 80000004h
0x14003c565  call    PrjfOpenReparsePoint
0x14003c56a  mov     esi, eax
0x14003c56c  test    eax, eax
0x14003c56e  jns     short loc_14003C5EA
0x14003c570  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003c576  lea     rax, WPP_RECORDER_INITIALIZED
0x14003c57d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003c584  setnz   r8b
0x14003c588  and     dl, 4
0x14003c58b  jnz     short loc_14003C592
0x14003c58d  test    r8b, r8b
0x14003c590  jz      short loc_14003C5E4
0x14003c592  mov     r9, cs:WPP_GLOBAL_Control
0x14003c599  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003c5a0  mov     [rsp+0E0h+var_88], r15
0x14003c5a5  mov     ecx, 20Ah
0x14003c5aa  mov     [rsp+0E0h+var_90], esi
0x14003c5ae  mov     [rsp+0E0h+var_98], 9C2h
0x14003c5b6  mov     r9, [r9+40h]
0x14003c5ba  mov     [rsp+0E0h+FileObject], rax
0x14003c5bf  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003c5c6  mov     [rsp+0E0h+FileHandle], rax
0x14003c5cb  mov     word ptr [rsp+0E0h+var_B0], 3Bh ; ';'
0x14003c5d2  mov     [rsp+0E0h+var_B8], 0Ah
0x14003c5da  mov     byte ptr [rsp+0E0h+var_C0], 2
0x14003c5df  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x14003c5e4  mov     rcx, [rbp+47h+var_80]
0x14003c5e8  jmp     short loc_14003C613
0x14003c5ea  test    rbx, rbx
0x14003c5ed  jz      short loc_14003C5F6
0x14003c5ef  mov     al, byte ptr [rbp+47h+var_4C]
0x14003c5f2  and     al, 1
0x14003c5f4  mov     [rbx], al
0x14003c5f6  mov     rax, [rbp+47h+var_80]
0x14003c5fa  xor     ecx, ecx; FileHandle
0x14003c5fc  mov     [r14], rax
0x14003c5ff  mov     [rbp+47h+var_80], rcx
0x14003c603  test    rdi, rdi
0x14003c606  jz      short loc_14003C624
0x14003c608  mov     rax, [rbp+47h+Object]
0x14003c60c  mov     [rdi], rax
0x14003c60f  mov     [rbp+47h+Object], rcx
0x14003c613  test    rcx, rcx
0x14003c616  jz      short loc_14003C624
0x14003c618  call    cs:__imp_FltClose
0x14003c61f  nop     dword ptr [rax+rax+00h]
0x14003c624  mov     rcx, [rbp+47h+Object]; Object
0x14003c628  test    rcx, rcx
0x14003c62b  jz      short loc_14003C639
0x14003c62d  call    cs:__imp_ObfDereferenceObject
0x14003c634  nop     dword ptr [rax+rax+00h]
0x14003c639  mov     eax, esi
0x14003c63b  mov     rcx, [rbp+47h+var_30]
0x14003c63f  xor     rcx, rsp; StackCookie
0x14003c642  call    __security_check_cookie
0x14003c647  mov     rbx, [rsp+0E0h+arg_10]
0x14003c64f  add     rsp, 0C0h
0x14003c656  pop     r15
0x14003c658  pop     r14
0x14003c65a  pop     rdi
0x14003c65b  pop     rsi
0x14003c65c  pop     rbp
0x14003c65d  retn
```
