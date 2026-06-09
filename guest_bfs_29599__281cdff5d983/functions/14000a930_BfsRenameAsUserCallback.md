# BfsRenameAsUserCallback

- ea: `0x14000a930`
- end: `0x14000aa9c`
- name: `BfsRenameAsUserCallback`
- size: `364`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x140001008`
- `0x140006c84`
- `0x14000a930`
- `0x14000fdc8`
- `0x140010070`
- `0x140012608`
- `0x140013860`

## import_xrefs

- `FLTMGR!FltSetInformationFile` at `0x14000a9cf`
- `FLTMGR!FltSetInformationFile` at `0x14000a9cf`

## pseudocode

```c
__int64 __fastcall BfsRenameAsUserCallback(__int64 a1, struct _FLT_INSTANCE *a2, __int64 a3, __int64 a4)
{
  void *v4; // rcx
  int v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // edi
  NTSTATUS v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // r14
  __int64 v18; // rbx
  struct _RTL_BITMAP *FileName; // rax
  __int64 v20; // rdx
  FILE_INFORMATION_CLASS FileInformationClass; // [rsp+20h] [rbp-59h]
  FILE_INFORMATION_CLASS FileInformationClassa; // [rsp+20h] [rbp-59h]
  NTSTATUS v24; // [rsp+30h] [rbp-49h] BYREF
  struct _RTL_BITMAP v25; // [rsp+38h] [rbp-41h] BYREF
  struct _RTL_BITMAP v26; // [rsp+48h] [rbp-31h] BYREF
  __int128 v27; // [rsp+58h] [rbp-21h] BYREF
  __int64 v28; // [rsp+68h] [rbp-11h]
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+70h] [rbp-9h] BYREF
  NTSTATUS *v30; // [rsp+90h] [rbp+17h]
  __int64 v31; // [rsp+98h] [rbp+1Fh]

  v4 = *(void **)a4;
  v27 = 0;
  v28 = 0;
  v8 = BfsImpersonateUser(v4, (__int64)&v27);
  v11 = v8;
  if ( v8 >= 0 )
  {
    v12 = FltSetInformationFile(
            a2,
            *(PFILE_OBJECT *)(*(_QWORD *)(a3 + 16) + 8LL),
            *(PVOID *)(*(_QWORD *)(a3 + 16) + 56LL),
            *(_DWORD *)(*(_QWORD *)(a3 + 16) + 24LL),
            *(FILE_INFORMATION_CLASS *)(*(_QWORD *)(a3 + 16) + 32LL));
    *(_DWORD *)(a4 + 32) = v12;
    v11 = v12;
    if ( v12 >= 0 )
    {
      v16 = *(_QWORD *)(a4 + 24);
      if ( v16 )
      {
        v17 = *(_QWORD *)(v16 + 48);
        if ( v17 )
        {
          if ( !*(_BYTE *)(a4 + 36) )
          {
            v18 = *(_QWORD *)(a4 + 8);
            FileName = (struct _RTL_BITMAP *)BfsGetFileName(&v26, v18);
            v20 = *(_QWORD *)(a4 + 16);
            v26 = *FileName;
            v25 = *(struct _RTL_BITMAP *)BfsGetFileName(&v25, v20);
            BfsRenameEntry(v17, v18 + 24, &v26, &v25);
          }
        }
      }
    }
    else if ( (unsigned int)dword_140019000 > 3 )
    {
      v24 = v12;
      v30 = &v24;
      v31 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v13, (unsigned __int8 *)&byte_140016D91, v14, v15, FileInformationClassa, &v29);
    }
    BfsRevertTokenImpersonation((__int64)&v27);
  }
  else if ( (unsigned int)dword_140019000 > 3 )
  {
    v24 = v8;
    v31 = 4;
    v30 = &v24;
    tlgWriteTransfer_EtwWriteTransfer(
      (unsigned int)dword_140019000,
      (unsigned __int8 *)&byte_140016D91,
      v9,
      v10,
      FileInformationClass,
      &v29);
  }
  return v11;
}

```

## disassembly

```asm
0x14000a930  push    rbp
0x14000a932  push    rbx
0x14000a933  push    rsi
0x14000a934  push    rdi
0x14000a935  push    r14
0x14000a937  lea     rbp, [rsp-37h]
0x14000a93c  sub     rsp, 0B0h
0x14000a943  mov     rax, cs:__security_cookie
0x14000a94a  xor     rax, rsp
0x14000a94d  mov     [rbp+57h+var_30], rax
0x14000a951  mov     rcx, [r9]
0x14000a954  mov     rbx, rdx
0x14000a957  xorps   xmm0, xmm0
0x14000a95a  lea     rdx, [rbp+57h+var_78]
0x14000a95e  xor     eax, eax
0x14000a960  mov     rsi, r9
0x14000a963  movups  [rbp+57h+var_78], xmm0
0x14000a967  mov     [rbp+57h+var_68], rax
0x14000a96b  mov     r14, r8
0x14000a96e  call    BfsImpersonateUser
0x14000a973  mov     edi, eax
0x14000a975  test    eax, eax
0x14000a977  jns     short loc_14000A9B5
0x14000a979  mov     ecx, cs:dword_140019000; int
0x14000a97f  cmp     ecx, 3
0x14000a982  jbe     loc_14000AA7F
0x14000a988  mov     [rbp+57h+var_A0], eax
0x14000a98b  lea     rdx, byte_140016D91; int
0x14000a992  lea     rax, [rbp+57h+var_A0]
0x14000a996  mov     [rbp+57h+var_38], 4
0x14000a99e  mov     [rbp+57h+var_40], rax
0x14000a9a2  lea     rax, [rbp+57h+var_60]
0x14000a9a6  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x14000a9ab  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a9b0  jmp     loc_14000AA7F
0x14000a9b5  mov     rdx, [r14+10h]
0x14000a9b9  mov     rcx, rbx; Instance
0x14000a9bc  mov     eax, [rdx+20h]
0x14000a9bf  mov     r9d, [rdx+18h]; Length
0x14000a9c3  mov     r8, [rdx+38h]; FileInformation
0x14000a9c7  mov     rdx, [rdx+8]; FileObject
0x14000a9cb  mov     [rsp+0D0h+FileInformationClass], eax; int
0x14000a9cf  call    cs:__imp_FltSetInformationFile
0x14000a9d6  nop     dword ptr [rax+rax+00h]
0x14000a9db  mov     [rsi+20h], eax
0x14000a9de  mov     edi, eax
0x14000a9e0  test    eax, eax
0x14000a9e2  jns     short loc_14000AA1D
0x14000a9e4  mov     eax, cs:dword_140019000
0x14000a9ea  cmp     eax, 3
0x14000a9ed  jbe     loc_14000AA76
0x14000a9f3  lea     rax, [rbp+57h+var_A0]
0x14000a9f7  mov     [rbp+57h+var_A0], edi
0x14000a9fa  mov     [rbp+57h+var_40], rax
0x14000a9fe  lea     rdx, byte_140016D91; int
0x14000aa05  lea     rax, [rbp+57h+var_60]
0x14000aa09  mov     [rbp+57h+var_38], 4
0x14000aa11  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x14000aa16  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000aa1b  jmp     short loc_14000AA76
0x14000aa1d  mov     rax, [rsi+18h]
0x14000aa21  test    rax, rax
0x14000aa24  jz      short loc_14000AA76
0x14000aa26  mov     r14, [rax+30h]
0x14000aa2a  test    r14, r14
0x14000aa2d  jz      short loc_14000AA76
0x14000aa2f  cmp     byte ptr [rsi+24h], 0
0x14000aa33  jnz     short loc_14000AA76
0x14000aa35  mov     rbx, [rsi+8]
0x14000aa39  lea     rcx, [rbp+57h+var_88]
0x14000aa3d  mov     rdx, rbx
0x14000aa40  call    BfsGetFileName
0x14000aa45  mov     rdx, [rsi+10h]
0x14000aa49  lea     rcx, [rbp+57h+var_98]
0x14000aa4d  movups  xmm1, xmmword ptr [rax]
0x14000aa50  movdqu  [rbp+57h+var_88], xmm1
0x14000aa55  call    BfsGetFileName
0x14000aa5a  lea     rdx, [rbx+18h]
0x14000aa5e  mov     rcx, r14
0x14000aa61  lea     r9, [rbp+57h+var_98]
0x14000aa65  lea     r8, [rbp+57h+var_88]
0x14000aa69  movups  xmm1, xmmword ptr [rax]
0x14000aa6c  movdqu  [rbp+57h+var_98], xmm1
0x14000aa71  call    BfsRenameEntry
0x14000aa76  lea     rcx, [rbp+57h+var_78]
0x14000aa7a  call    BfsRevertTokenImpersonation
0x14000aa7f  mov     eax, edi
0x14000aa81  mov     rcx, [rbp+57h+var_30]
0x14000aa85  xor     rcx, rsp; StackCookie
0x14000aa88  call    __security_check_cookie
0x14000aa8d  add     rsp, 0B0h
0x14000aa94  pop     r14
0x14000aa96  pop     rdi
0x14000aa97  pop     rsi
0x14000aa98  pop     rbx
0x14000aa99  pop     rbp
0x14000aa9a  retn
```
