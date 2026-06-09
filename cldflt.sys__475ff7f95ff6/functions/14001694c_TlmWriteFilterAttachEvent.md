# TlmWriteFilterAttachEvent

- ea: `0x14001694c`
- end: `0x140016baf`
- name: `TlmWriteFilterAttachEvent`
- size: `611`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14003bb10`
- `0x14007a214`

## callees

- `0x140001040`
- `0x140003c50`
- `0x14000b5fc`
- `0x14001694c`
- `0x14001e1c0`
- `0x14001e600`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140016b7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016b7f`
- `ntoskrnl!ExAllocatePool2` at `0x140016a06`
- `ntoskrnl!ExAllocatePool2` at `0x140016a06`
- `FLTMGR!FltGetVolumeName` at `0x1400169d6`
- `FLTMGR!FltGetVolumeName` at `0x140016a44`
- `FLTMGR!FltGetVolumeName` at `0x1400169d6`
- `FLTMGR!FltGetVolumeName` at `0x140016a44`

## pseudocode

```c
void __fastcall TlmWriteFilterAttachEvent(int a1, unsigned __int16 *a2, unsigned __int16 *a3, struct _FLT_VOLUME *a4)
{
  int v8; // esi
  PWSTR Buffer; // rbx
  unsigned int v10; // eax
  __int64 v11; // r10
  unsigned __int8 *v12; // rdx
  int v13; // eax
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING VolumeName; // [rsp+38h] [rbp-C8h] BYREF
  ULONG BufferSizeNeeded; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+60h] [rbp-A0h] BYREF
  int *v19; // [rsp+80h] [rbp-80h]
  __int64 v20; // [rsp+88h] [rbp-78h]
  _DWORD *v21; // [rsp+90h] [rbp-70h]
  __int64 v22; // [rsp+98h] [rbp-68h]
  __int64 v23; // [rsp+A0h] [rbp-60h]
  _DWORD v24[2]; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD *v25; // [rsp+B0h] [rbp-50h]
  __int64 v26; // [rsp+B8h] [rbp-48h]
  __int64 v27; // [rsp+C0h] [rbp-40h]
  _DWORD v28[2]; // [rsp+C8h] [rbp-38h] BYREF
  _DWORD *v29; // [rsp+D0h] [rbp-30h]
  __int64 v30; // [rsp+D8h] [rbp-28h]
  PWSTR v31; // [rsp+E0h] [rbp-20h]
  _DWORD v32[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 *v33; // [rsp+F0h] [rbp-10h]
  __int64 v34; // [rsp+F8h] [rbp-8h]
  _BYTE v35[2080]; // [rsp+100h] [rbp+0h] BYREF

  if ( _TLM )
  {
    *(_QWORD *)&VolumeName.Length = 34078720;
    memset(v35, 0, sizeof(v35));
    BufferSizeNeeded = 0;
    VolumeName.Buffer = (PWSTR)v35;
    v8 = 0;
    if ( FltGetVolumeName(a4, &VolumeName, &BufferSizeNeeded) == -1073741789 )
    {
      VolumeName.MaximumLength = BufferSizeNeeded;
      VolumeName.Length = 0;
      VolumeName.Buffer = (PWSTR)ExAllocatePool2(256, (unsigned __int16)BufferSizeNeeded, 1934979912);
      Buffer = VolumeName.Buffer;
      HsmDbgBreakOnStatus(VolumeName.Buffer == 0 ? 0xC000009A : 0);
      if ( Buffer )
      {
        v8 = 1;
        FltGetVolumeName(a4, &VolumeName, 0);
      }
    }
    v10 = **(_DWORD **)&qword_1400295A8;
    if ( a1 >= 0 )
    {
      if ( v10 <= 5 || !tlgKeywordOn(*(__int64 *)&qword_1400295A8, 0x400000000000LL) )
        goto LABEL_13;
      v12 = (unsigned __int8 *)&unk_140023090;
    }
    else
    {
      if ( v10 <= 5 || !tlgKeywordOn(*(__int64 *)&qword_1400295A8, 0x800000000000LL) )
        goto LABEL_13;
      v12 = (unsigned __int8 *)word_140022562;
    }
    v22 = 2;
    v19 = &v14;
    v21 = v24;
    v23 = *((_QWORD *)a2 + 1);
    v13 = *a2;
    v20 = 4;
    v24[0] = v13;
    v14 = a1;
    v25 = v28;
    v27 = *((_QWORD *)a3 + 1);
    v28[0] = *a3;
    v29 = v32;
    v31 = VolumeName.Buffer;
    v32[0] = VolumeName.Length;
    v33 = &v17;
    v24[1] = 0;
    v26 = 2;
    v28[1] = 0;
    v30 = 2;
    v32[1] = 0;
    v17 = 0x1000000;
    v34 = 8;
    tlgWriteTransfer_EtwWriteTransfer(v11, v12, 0, 0, 0xAu, &v18);
LABEL_13:
    if ( v8 )
      ExFreePoolWithTag(VolumeName.Buffer, 0x73557348u);
  }
}

```

## disassembly

```asm
0x14001694c  push    rbp
0x14001694e  push    rbx
0x14001694f  push    rsi
0x140016950  push    rdi
0x140016951  push    r12
0x140016953  push    r13
0x140016955  push    r14
0x140016957  push    r15
0x140016959  lea     rbp, [rsp-838h]
0x140016961  sub     rsp, 938h
0x140016968  mov     rax, cs:__security_cookie
0x14001696f  xor     rax, rsp
0x140016972  mov     [rbp+870h+var_50], rax
0x140016979  xor     r12d, r12d
0x14001697c  mov     rdi, r9
0x14001697f  cmp     cs:__TLM, r12b
0x140016986  mov     r15, r8
0x140016989  mov     r13, rdx
0x14001698c  mov     r14d, ecx
0x14001698f  jz      loc_140016B8B
0x140016995  xorps   xmm0, xmm0
0x140016998  lea     rcx, [rbp+870h+var_870]; void *
0x14001699c  xor     edx, edx; Val
0x14001699e  mov     r8d, 820h; Size
0x1400169a4  movups  xmmword ptr [rsp+970h+VolumeName.Length], xmm0
0x1400169a9  call    memset
0x1400169ae  lea     rax, [rbp+870h+var_870]
0x1400169b2  mov     [rsp+970h+BufferSizeNeeded], r12d
0x1400169b7  mov     [rsp+970h+VolumeName.Buffer], rax
0x1400169bc  lea     r8, [rsp+970h+BufferSizeNeeded]; BufferSizeNeeded
0x1400169c1  mov     eax, 208h
0x1400169c6  lea     rdx, [rsp+970h+VolumeName]; VolumeName
0x1400169cb  mov     rcx, rdi; Volume
0x1400169ce  mov     [rsp+970h+VolumeName.MaximumLength], ax
0x1400169d3  mov     esi, r12d
0x1400169d6  call    cs:__imp_FltGetVolumeName
0x1400169dd  nop     dword ptr [rax+rax+00h]
0x1400169e2  cmp     eax, 0C0000023h
0x1400169e7  jnz     short loc_140016A50
0x1400169e9  mov     ecx, [rsp+970h+BufferSizeNeeded]
0x1400169ed  mov     r8d, 73557348h
0x1400169f3  mov     [rsp+970h+VolumeName.MaximumLength], cx
0x1400169f8  movzx   edx, cx
0x1400169fb  mov     ecx, 100h
0x140016a00  mov     [rsp+970h+VolumeName.Length], r12w
0x140016a06  call    cs:__imp_ExAllocatePool2
0x140016a0d  nop     dword ptr [rax+rax+00h]
0x140016a12  mov     rdx, rax
0x140016a15  mov     [rsp+970h+VolumeName.Buffer], rax
0x140016a1a  neg     rdx
0x140016a1d  mov     rbx, rax
0x140016a20  sbb     ecx, ecx
0x140016a22  not     ecx
0x140016a24  and     ecx, 0C000009Ah
0x140016a2a  call    HsmDbgBreakOnStatus
0x140016a2f  test    rbx, rbx
0x140016a32  jz      short loc_140016A50
0x140016a34  xor     r8d, r8d; BufferSizeNeeded
0x140016a37  lea     rdx, [rsp+970h+VolumeName]; VolumeName
0x140016a3c  mov     rcx, rdi; Volume
0x140016a3f  lea     esi, [r12+1]
0x140016a44  call    cs:__imp_FltGetVolumeName
0x140016a4b  nop     dword ptr [rax+rax+00h]
0x140016a50  mov     r10, cs:qword_1400295A8
0x140016a57  mov     eax, [r10]
0x140016a5a  test    r14d, r14d
0x140016a5d  jns     short loc_140016A8B
0x140016a5f  cmp     eax, 5
0x140016a62  jbe     loc_140016B71
0x140016a68  mov     rdx, 800000000000h
0x140016a72  mov     rcx, r10
0x140016a75  call    _tlgKeywordOn
0x140016a7a  test    al, al
0x140016a7c  jz      loc_140016B71
0x140016a82  lea     rdx, word_140022562
0x140016a89  jmp     short loc_140016AB5
0x140016a8b  cmp     eax, 5
0x140016a8e  jbe     loc_140016B71
0x140016a94  mov     rdx, 400000000000h
0x140016a9e  mov     rcx, r10
0x140016aa1  call    _tlgKeywordOn
0x140016aa6  test    al, al
0x140016aa8  jz      loc_140016B71
0x140016aae  lea     rdx, unk_140023090
0x140016ab5  lea     rax, [rsp+970h+var_940]
0x140016aba  mov     [rbp+870h+var_8D8], 2
0x140016ac2  mov     [rbp+870h+var_8F0], rax
0x140016ac6  lea     rax, [rbp+870h+var_8C8]
0x140016aca  mov     [rbp+870h+var_8E0], rax
0x140016ace  mov     rax, [r13+8]
0x140016ad2  mov     [rbp+870h+var_8D0], rax
0x140016ad6  movzx   eax, word ptr [r13+0]
0x140016adb  mov     [rbp+870h+var_8E8], 4
0x140016ae3  mov     [rbp+870h+var_8C8], eax
0x140016ae6  xor     r9d, r9d
0x140016ae9  lea     rax, [rbp+870h+var_8A8]
0x140016aed  mov     [rsp+970h+var_940], r14d
0x140016af2  mov     [rbp+870h+var_8C0], rax
0x140016af6  xor     r8d, r8d
0x140016af9  mov     rax, [r15+8]
0x140016afd  mov     rcx, r10
0x140016b00  mov     [rbp+870h+var_8B0], rax
0x140016b04  movzx   eax, word ptr [r15]
0x140016b08  mov     [rbp+870h+var_8A8], eax
0x140016b0b  lea     rax, [rbp+870h+var_888]
0x140016b0f  mov     [rbp+870h+var_8A0], rax
0x140016b13  mov     rax, [rsp+970h+VolumeName.Buffer]
0x140016b18  mov     [rbp+870h+var_890], rax
0x140016b1c  movzx   eax, [rsp+970h+VolumeName.Length]
0x140016b21  mov     [rbp+870h+var_888], eax
0x140016b24  lea     rax, [rsp+970h+var_920]
0x140016b29  mov     [rbp+870h+var_880], rax
0x140016b2d  lea     rax, [rsp+970h+var_910]
0x140016b32  mov     [rsp+970h+var_948], rax
0x140016b37  mov     [rsp+970h+var_950], 0Ah
0x140016b3f  mov     [rbp+870h+var_8C4], r12d
0x140016b43  mov     [rbp+870h+var_8B8], 2
0x140016b4b  mov     [rbp+870h+var_8A4], r12d
0x140016b4f  mov     [rbp+870h+var_898], 2
0x140016b57  mov     [rbp+870h+var_884], r12d
0x140016b5b  mov     [rsp+970h+var_920], 1000000h
0x140016b64  mov     [rbp+870h+var_878], 8
0x140016b6c  call    _tlgWriteTransfer_EtwWriteTransfer
0x140016b71  test    esi, esi
0x140016b73  jz      short loc_140016B8B
0x140016b75  mov     rcx, [rsp+970h+VolumeName.Buffer]; P
0x140016b7a  mov     edx, 73557348h; Tag
0x140016b7f  call    cs:__imp_ExFreePoolWithTag
0x140016b86  nop     dword ptr [rax+rax+00h]
0x140016b8b  mov     rcx, [rbp+870h+var_50]
0x140016b92  xor     rcx, rsp; StackCookie
0x140016b95  call    __security_check_cookie
0x140016b9a  add     rsp, 938h
0x140016ba1  pop     r15
0x140016ba3  pop     r14
0x140016ba5  pop     r13
0x140016ba7  pop     r12
0x140016ba9  pop     rdi
0x140016baa  pop     rsi
0x140016bab  pop     rbx
0x140016bac  pop     rbp
0x140016bad  retn
```
