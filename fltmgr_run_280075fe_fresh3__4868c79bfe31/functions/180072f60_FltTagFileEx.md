# FltTagFileEx

- ea: `0x180072f60`
- end: `0x18007318e`
- name: `FltTagFileEx`
- size: `558`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, int, _OWORD *, void *Src, unsigned __int16, int, __int128 *Source1, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180085bb0`

## callees

- `0x180008000`
- `0x180008080`
- `0x180008a70`
- `0x180009f20`
- `0x180024900`
- `0x180072f60`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18007310c`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007310c`
- `ntoskrnl!ExAllocatePool2` at `0x18007304f`
- `ntoskrnl!ExAllocatePool2` at `0x18007304f`
- `ntoskrnl!RtlCompareMemory` at `0x180072fab`
- `ntoskrnl!RtlCompareMemory` at `0x180073159`
- `ntoskrnl!RtlCompareMemory` at `0x180072fab`
- `ntoskrnl!RtlCompareMemory` at `0x180073159`

## pseudocode

```c
__int64 __fastcall FltTagFileEx(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        int a3,
        _OWORD *a4,
        void *Src,
        unsigned __int16 a6,
        int a7,
        __int128 *Source1,
        int a9)
{
  char *Pool2; // rbx
  unsigned int Status; // r14d
  int v16; // eax
  PFLT_CALLBACK_DATA v17; // rdi
  int v18; // r13d
  ULONG v19; // r13d
  __int128 v20; // xmm0
  _OWORD *v21; // rcx
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+20h] [rbp-38h] BYREF

  RetNewCallbackData = 0;
  if ( a3 >= 0 && (!a4 || RtlCompareMemory(a4, &GUID_NULL, 0x10u) == 16) )
    return 3221225485LL;
  if ( a7 > 0 && (!Source1 || RtlCompareMemory(Source1, &GUID_NULL, 0x10u) == 16) )
    return 3221225485LL;
  Pool2 = 0;
  Status = FltAllocateCallbackData(Instance, FileObject, &RetNewCallbackData);
  v16 = FltpDbgStatus(Status, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 6281, 0);
  v17 = RetNewCallbackData;
  if ( v16 >= 0 )
  {
    v18 = 40;
    if ( a4 )
      v18 = 56;
    v19 = a6 + v18;
    Pool2 = (char *)ExAllocatePool2(64, v19, 1886539078);
    if ( Pool2 )
    {
      *(_DWORD *)Pool2 = a9;
      *((_DWORD *)Pool2 + 1) = a7;
      if ( Source1 )
        v20 = *Source1;
      else
        v20 = 0;
      v21 = Pool2 + 40;
      *(_OWORD *)(Pool2 + 8) = v20;
      *((_QWORD *)Pool2 + 3) = 0;
      *((_DWORD *)Pool2 + 8) = a3;
      *((_DWORD *)Pool2 + 9) = a6;
      if ( a4 )
      {
        *v21 = *a4;
        v21 = Pool2 + 56;
      }
      memmove(v21, Src, a6);
      v17->Iopb->MajorFunction = 13;
      v17->Iopb->Parameters.Read.ByteOffset.LowPart = 590860;
      v17->Iopb->Parameters.CreatePipe.Parameters = Pool2;
      v17->Iopb->Parameters.Create.Options = v19;
      v17->Iopb->IrpFlags |= 1u;
      FltPerformSynchronousIo(v17);
      Status = v17->IoStatus.Status;
    }
    else
    {
      Status = -1073741670;
    }
  }
  if ( v17 )
    FltFreeCallbackData(v17);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x70724D46u);
  return Status;
}

```

## disassembly

```asm
0x180072f60  push    rsi
0x180072f62  push    rdi
0x180072f63  push    r14
0x180072f65  push    r15
0x180072f67  sub     rsp, 38h
0x180072f6b  mov     [rsp+58h+RetNewCallbackData], 0
0x180072f74  mov     rsi, r9
0x180072f77  mov     r15d, r8d
0x180072f7a  mov     rdi, rdx
0x180072f7d  mov     r14, rcx
0x180072f80  test    r8d, r8d
0x180072f83  js      short loc_180072FBD
0x180072f85  test    r9, r9
0x180072f88  jnz     short loc_180072F9B
0x180072f8a  mov     eax, 0C000000Dh
0x180072f8f  add     rsp, 38h
0x180072f93  pop     r15
0x180072f95  pop     r14
0x180072f97  pop     rdi
0x180072f98  pop     rsi
0x180072f99  retn
0x180072f9b  mov     r8d, 10h; Length
0x180072fa1  lea     rdx, GUID_NULL; Source2
0x180072fa8  mov     rcx, rsi; Source1
0x180072fab  call    cs:__imp_RtlCompareMemory
0x180072fb2  nop     dword ptr [rax+rax+00h]
0x180072fb7  cmp     rax, 10h
0x180072fbb  jz      short loc_180072F8A
0x180072fbd  mov     [rsp+58h+arg_8], rbp
0x180072fc2  mov     ebp, [rsp+58h+arg_30]
0x180072fc9  mov     [rsp+58h+arg_10], r12
0x180072fce  mov     r12, [rsp+58h+Source1]
0x180072fd6  test    ebp, ebp
0x180072fd8  jz      short loc_180072FE0
0x180072fda  jns     loc_180073140
0x180072fe0  mov     [rsp+58h+arg_0], rbx
0x180072fe5  lea     r8, [rsp+58h+RetNewCallbackData]; RetNewCallbackData
0x180072fea  mov     rdx, rdi; FileObject
0x180072fed  mov     rcx, r14; Instance
0x180072ff0  xor     ebx, ebx
0x180072ff2  call    FltAllocateCallbackData
0x180072ff7  mov     r8d, 1889h
0x180072ffd  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180073004  xor     r9d, r9d
0x180073007  mov     ecx, eax
0x180073009  mov     r14d, eax
0x18007300c  call    FltpDbgStatus
0x180073011  mov     rdi, [rsp+58h+RetNewCallbackData]
0x180073016  test    eax, eax
0x180073018  js      loc_1800730F2
0x18007301e  movzx   r14d, [rsp+58h+arg_28]
0x180073027  mov     eax, 38h ; '8'
0x18007302c  mov     [rsp+58h+var_28], r13
0x180073031  test    rsi, rsi
0x180073034  mov     r13d, 28h ; '('
0x18007303a  mov     ecx, 40h ; '@'
0x18007303f  cmovnz  r13d, eax
0x180073043  mov     r8d, 70724D46h
0x180073049  add     r13d, r14d
0x18007304c  mov     edx, r13d
0x18007304f  call    cs:__imp_ExAllocatePool2
0x180073056  nop     dword ptr [rax+rax+00h]
0x18007305b  mov     rbx, rax
0x18007305e  test    rax, rax
0x180073061  jz      loc_180073174
0x180073067  mov     eax, [rsp+58h+arg_40]
0x18007306e  mov     [rbx], eax
0x180073070  mov     [rbx+4], ebp
0x180073073  test    r12, r12
0x180073076  jnz     loc_180073136
0x18007307c  xorps   xmm0, xmm0
0x18007307f  mov     rdx, [rsp+58h+Src]; Src
0x180073087  lea     rcx, [rbx+28h]; void *
0x18007308b  movups  xmmword ptr [rbx+8], xmm0
0x18007308f  xor     eax, eax
0x180073091  mov     qword ptr [rbx+18h], 0
0x180073099  mov     [rbx+20h], r15d
0x18007309d  mov     r8, r14; Size
0x1800730a0  mov     [rbx+24h], r14w
0x1800730a5  mov     [rbx+26h], ax
0x1800730a9  test    rsi, rsi
0x1800730ac  jnz     loc_18007317F
0x1800730b2  call    memmove
0x1800730b7  mov     rax, [rdi+10h]
0x1800730bb  mov     rcx, rdi; CallbackData
0x1800730be  mov     byte ptr [rax+4], 0Dh
0x1800730c2  mov     rax, [rdi+10h]
0x1800730c6  mov     dword ptr [rax+28h], 9040Ch
0x1800730cd  mov     rax, [rdi+10h]
0x1800730d1  mov     [rax+30h], rbx
0x1800730d5  mov     rax, [rdi+10h]
0x1800730d9  mov     [rax+20h], r13d
0x1800730dd  mov     rax, [rdi+10h]
0x1800730e1  or      dword ptr [rax], 1
0x1800730e4  call    FltPerformSynchronousIo
0x1800730e9  mov     r14d, [rdi+18h]
0x1800730ed  mov     r13, [rsp+58h+var_28]
0x1800730f2  test    rdi, rdi
0x1800730f5  jz      short loc_1800730FF
0x1800730f7  mov     rcx, rdi; CallbackData
0x1800730fa  call    FltFreeCallbackData
0x1800730ff  test    rbx, rbx
0x180073102  jz      short loc_180073118
0x180073104  mov     edx, 70724D46h; Tag
0x180073109  mov     rcx, rbx; P
0x18007310c  call    cs:__imp_ExFreePoolWithTag
0x180073113  nop     dword ptr [rax+rax+00h]
0x180073118  mov     rbx, [rsp+58h+arg_0]
0x18007311d  mov     eax, r14d
0x180073120  mov     rbp, [rsp+58h+arg_8]
0x180073125  mov     r12, [rsp+58h+arg_10]
0x18007312a  add     rsp, 38h
0x18007312e  pop     r15
0x180073130  pop     r14
0x180073132  pop     rdi
0x180073133  pop     rsi
0x180073134  retn
0x180073136  movups  xmm0, xmmword ptr [r12]
0x18007313b  jmp     loc_18007307F
0x180073140  test    r12, r12
0x180073143  jz      loc_18007B0B8
0x180073149  mov     r8d, 10h; Length
0x18007314f  lea     rdx, GUID_NULL; Source2
0x180073156  mov     rcx, r12; Source1
0x180073159  call    cs:__imp_RtlCompareMemory
0x180073160  nop     dword ptr [rax+rax+00h]
0x180073165  cmp     rax, 10h
0x180073169  jnz     loc_180072FE0
0x18007316f  jmp     loc_18007B0B8
0x180073174  mov     r14d, 0C000009Ah
0x18007317a  jmp     loc_1800730ED
0x18007317f  movups  xmm0, xmmword ptr [rsi]
0x180073182  movups  xmmword ptr [rcx], xmm0
0x180073185  lea     rcx, [rbx+38h]
0x180073189  jmp     loc_1800730B2
0x18007b0b8  mov     eax, 0C000000Dh
0x18007b0bd  jmp     loc_180073120
```
