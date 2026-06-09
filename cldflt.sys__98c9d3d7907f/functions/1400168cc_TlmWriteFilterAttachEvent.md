# TlmWriteFilterAttachEvent

- ea: `0x1400168cc`
- end: `0x140016b2f`
- name: `TlmWriteFilterAttachEvent`
- size: `611`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14003baf0`
- `0x14007a0d4`

## callees

- `0x140001040`
- `0x140003c50`
- `0x14000b5fc`
- `0x1400168cc`
- `0x14001e140`
- `0x14001e580`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140016aff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016aff`
- `ntoskrnl!ExAllocatePool2` at `0x140016986`
- `ntoskrnl!ExAllocatePool2` at `0x140016986`
- `FLTMGR!FltGetVolumeName` at `0x140016956`
- `FLTMGR!FltGetVolumeName` at `0x1400169c4`
- `FLTMGR!FltGetVolumeName` at `0x140016956`
- `FLTMGR!FltGetVolumeName` at `0x1400169c4`

## pseudocode

```c
void __fastcall TlmWriteFilterAttachEvent(int a1, unsigned __int16 *a2, unsigned __int16 *a3, struct _FLT_VOLUME *a4)
{
  int v8; // esi
  PWSTR Buffer; // rbx
  unsigned int v10; // eax
  __int64 v11; // r10
  char *v12; // rdx
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
      if ( v10 <= 5 || !(unsigned __int8)tlgKeywordOn(*(_QWORD *)&qword_1400295A8, 0x400000000000LL) )
        goto LABEL_13;
      v12 = byte_1400230FB;
    }
    else
    {
      if ( v10 <= 5 || !(unsigned __int8)tlgKeywordOn(*(_QWORD *)&qword_1400295A8, 0x800000000000LL) )
        goto LABEL_13;
      v12 = byte_140022845;
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
    tlgWriteTransfer_EtwWriteTransfer(v11, (unsigned __int8 *)v12, 0, 0, 0xAu, &v18);
LABEL_13:
    if ( v8 )
      ExFreePoolWithTag(VolumeName.Buffer, 0x73557348u);
  }
}

```

## disassembly

```asm
0x1400168cc  push    rbp
0x1400168ce  push    rbx
0x1400168cf  push    rsi
0x1400168d0  push    rdi
0x1400168d1  push    r12
0x1400168d3  push    r13
0x1400168d5  push    r14
0x1400168d7  push    r15
0x1400168d9  lea     rbp, [rsp-838h]
0x1400168e1  sub     rsp, 938h
0x1400168e8  mov     rax, cs:__security_cookie
0x1400168ef  xor     rax, rsp
0x1400168f2  mov     [rbp+870h+var_50], rax
0x1400168f9  xor     r12d, r12d
0x1400168fc  mov     rdi, r9
0x1400168ff  cmp     cs:__TLM, r12b
0x140016906  mov     r15, r8
0x140016909  mov     r13, rdx
0x14001690c  mov     r14d, ecx
0x14001690f  jz      loc_140016B0B
0x140016915  xorps   xmm0, xmm0
0x140016918  lea     rcx, [rbp+870h+var_870]; void *
0x14001691c  xor     edx, edx; Val
0x14001691e  mov     r8d, 820h; Size
0x140016924  movups  xmmword ptr [rsp+970h+VolumeName.Length], xmm0
0x140016929  call    memset
0x14001692e  lea     rax, [rbp+870h+var_870]
0x140016932  mov     [rsp+970h+BufferSizeNeeded], r12d
0x140016937  mov     [rsp+970h+VolumeName.Buffer], rax
0x14001693c  lea     r8, [rsp+970h+BufferSizeNeeded]; BufferSizeNeeded
0x140016941  mov     eax, 208h
0x140016946  lea     rdx, [rsp+970h+VolumeName]; VolumeName
0x14001694b  mov     rcx, rdi; Volume
0x14001694e  mov     [rsp+970h+VolumeName.MaximumLength], ax
0x140016953  mov     esi, r12d
0x140016956  call    cs:__imp_FltGetVolumeName
0x14001695d  nop     dword ptr [rax+rax+00h]
0x140016962  cmp     eax, 0C0000023h
0x140016967  jnz     short loc_1400169D0
0x140016969  mov     ecx, [rsp+970h+BufferSizeNeeded]
0x14001696d  mov     r8d, 73557348h
0x140016973  mov     [rsp+970h+VolumeName.MaximumLength], cx
0x140016978  movzx   edx, cx
0x14001697b  mov     ecx, 100h
0x140016980  mov     [rsp+970h+VolumeName.Length], r12w
0x140016986  call    cs:__imp_ExAllocatePool2
0x14001698d  nop     dword ptr [rax+rax+00h]
0x140016992  mov     rdx, rax
0x140016995  mov     [rsp+970h+VolumeName.Buffer], rax
0x14001699a  neg     rdx
0x14001699d  mov     rbx, rax
0x1400169a0  sbb     ecx, ecx
0x1400169a2  not     ecx
0x1400169a4  and     ecx, 0C000009Ah
0x1400169aa  call    HsmDbgBreakOnStatus
0x1400169af  test    rbx, rbx
0x1400169b2  jz      short loc_1400169D0
0x1400169b4  xor     r8d, r8d; BufferSizeNeeded
0x1400169b7  lea     rdx, [rsp+970h+VolumeName]; VolumeName
0x1400169bc  mov     rcx, rdi; Volume
0x1400169bf  lea     esi, [r12+1]
0x1400169c4  call    cs:__imp_FltGetVolumeName
0x1400169cb  nop     dword ptr [rax+rax+00h]
0x1400169d0  mov     r10, cs:qword_1400295A8
0x1400169d7  mov     eax, [r10]
0x1400169da  test    r14d, r14d
0x1400169dd  jns     short loc_140016A0B
0x1400169df  cmp     eax, 5
0x1400169e2  jbe     loc_140016AF1
0x1400169e8  mov     rdx, 800000000000h
0x1400169f2  mov     rcx, r10
0x1400169f5  call    _tlgKeywordOn
0x1400169fa  test    al, al
0x1400169fc  jz      loc_140016AF1
0x140016a02  lea     rdx, byte_140022845
0x140016a09  jmp     short loc_140016A35
0x140016a0b  cmp     eax, 5
0x140016a0e  jbe     loc_140016AF1
0x140016a14  mov     rdx, 400000000000h
0x140016a1e  mov     rcx, r10
0x140016a21  call    _tlgKeywordOn
0x140016a26  test    al, al
0x140016a28  jz      loc_140016AF1
0x140016a2e  lea     rdx, byte_1400230FB
0x140016a35  lea     rax, [rsp+970h+var_940]
0x140016a3a  mov     [rbp+870h+var_8D8], 2
0x140016a42  mov     [rbp+870h+var_8F0], rax
0x140016a46  lea     rax, [rbp+870h+var_8C8]
0x140016a4a  mov     [rbp+870h+var_8E0], rax
0x140016a4e  mov     rax, [r13+8]
0x140016a52  mov     [rbp+870h+var_8D0], rax
0x140016a56  movzx   eax, word ptr [r13+0]
0x140016a5b  mov     [rbp+870h+var_8E8], 4
0x140016a63  mov     [rbp+870h+var_8C8], eax
0x140016a66  xor     r9d, r9d
0x140016a69  lea     rax, [rbp+870h+var_8A8]
0x140016a6d  mov     [rsp+970h+var_940], r14d
0x140016a72  mov     [rbp+870h+var_8C0], rax
0x140016a76  xor     r8d, r8d
0x140016a79  mov     rax, [r15+8]
0x140016a7d  mov     rcx, r10
0x140016a80  mov     [rbp+870h+var_8B0], rax
0x140016a84  movzx   eax, word ptr [r15]
0x140016a88  mov     [rbp+870h+var_8A8], eax
0x140016a8b  lea     rax, [rbp+870h+var_888]
0x140016a8f  mov     [rbp+870h+var_8A0], rax
0x140016a93  mov     rax, [rsp+970h+VolumeName.Buffer]
0x140016a98  mov     [rbp+870h+var_890], rax
0x140016a9c  movzx   eax, [rsp+970h+VolumeName.Length]
0x140016aa1  mov     [rbp+870h+var_888], eax
0x140016aa4  lea     rax, [rsp+970h+var_920]
0x140016aa9  mov     [rbp+870h+var_880], rax
0x140016aad  lea     rax, [rsp+970h+var_910]
0x140016ab2  mov     [rsp+970h+var_948], rax
0x140016ab7  mov     [rsp+970h+var_950], 0Ah
0x140016abf  mov     [rbp+870h+var_8C4], r12d
0x140016ac3  mov     [rbp+870h+var_8B8], 2
0x140016acb  mov     [rbp+870h+var_8A4], r12d
0x140016acf  mov     [rbp+870h+var_898], 2
0x140016ad7  mov     [rbp+870h+var_884], r12d
0x140016adb  mov     [rsp+970h+var_920], 1000000h
0x140016ae4  mov     [rbp+870h+var_878], 8
0x140016aec  call    _tlgWriteTransfer_EtwWriteTransfer
0x140016af1  test    esi, esi
0x140016af3  jz      short loc_140016B0B
0x140016af5  mov     rcx, [rsp+970h+VolumeName.Buffer]; P
0x140016afa  mov     edx, 73557348h; Tag
0x140016aff  call    cs:__imp_ExFreePoolWithTag
0x140016b06  nop     dword ptr [rax+rax+00h]
0x140016b0b  mov     rcx, [rbp+870h+var_50]
0x140016b12  xor     rcx, rsp; StackCookie
0x140016b15  call    __security_check_cookie
0x140016b1a  add     rsp, 938h
0x140016b21  pop     r15
0x140016b23  pop     r14
0x140016b25  pop     r13
0x140016b27  pop     r12
0x140016b29  pop     rdi
0x140016b2a  pop     rsi
0x140016b2b  pop     rbx
0x140016b2c  pop     rbp
0x140016b2d  retn
```
