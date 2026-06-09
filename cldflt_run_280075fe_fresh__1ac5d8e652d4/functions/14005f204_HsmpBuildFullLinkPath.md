# HsmpBuildFullLinkPath

- ea: `0x14005f204`
- end: `0x14005f542`
- name: `HsmpBuildFullLinkPath`
- size: `830`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140058f70`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14005e64c`
- `0x14005f204`
- `0x14005f550`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14005f491`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14005f491`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14005f342`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14005f36c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14005f342`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14005f36c`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f3b0`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f3b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f3df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f531`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f3df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f531`
- `ntoskrnl!ExAllocatePool2` at `0x14005f307`
- `ntoskrnl!ExAllocatePool2` at `0x14005f307`
- `FLTMGR!FltClose` at `0x14005f3c5`
- `FLTMGR!FltClose` at `0x14005f3c5`

## pseudocode

```c
__int64 __fastcall HsmpBuildFullLinkPath(__int64 a1, __int64 a2, const UNICODE_STRING *a3, UNICODE_STRING *a4)
{
  struct _FLT_INSTANCE *v8; // rdx
  unsigned int v10; // edi
  __int64 v11; // rdx
  unsigned __int16 v12; // ax
  unsigned __int16 v13; // cx
  PWSTR Buffer; // rbx
  UNICODE_STRING v15; // xmm0
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // [rsp+20h] [rbp-60h]
  HANDLE FileHandle; // [rsp+50h] [rbp-30h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+58h] [rbp-28h] BYREF
  UNICODE_STRING Source; // [rsp+68h] [rbp-18h] BYREF
  PVOID Object; // [rsp+B0h] [rbp+30h] BYREF

  FileHandle = 0;
  Object = 0;
  v8 = *(struct _FLT_INSTANCE **)(a1 + 32);
  Source = 0;
  Destination = 0;
  v10 = HsmpOpenFileByIdEx(
          (const UNICODE_STRING *)a1,
          v8,
          a2,
          0x100080u,
          v19,
          2097153,
          0,
          &FileHandle,
          (PFILE_OBJECT *)&Object);
  HsmDbgBreakOnStatus(v10);
  if ( (v10 & 0x80000000) != 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_13;
    }
    v18 = 19;
LABEL_30:
    WPP_SF_qqd(v17->AttachedDevice, v18, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, a2, v10);
    goto LABEL_13;
  }
  v10 = HsmiQueryFullFilePath(*(_QWORD *)(a1 + 32), v11, (struct _FILE_OBJECT *)Object, 0x101u, &Source);
  HsmDbgBreakOnStatus(v10);
  if ( (v10 & 0x80000000) != 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_13;
    }
    v18 = 20;
    goto LABEL_30;
  }
  if ( !a3 )
  {
    v15 = Source;
    Source.Buffer = 0;
LABEL_12:
    *a4 = v15;
    goto LABEL_13;
  }
  v12 = Source.Length + 2;
  if ( (unsigned __int16)(Source.Length + 2) < Source.Length
    || (v13 = a3->Length + v12, v13 < v12)
    || (unsigned __int16)(v13 + 2) < v13 )
  {
    Destination.MaximumLength = -1;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_13;
    }
    v18 = 21;
    goto LABEL_30;
  }
  Destination.MaximumLength = v13 + 2;
  Destination.Length = 0;
  Destination.Buffer = (PWSTR)ExAllocatePool2(256, (unsigned __int16)(v13 + 2), 1934979912);
  Buffer = Destination.Buffer;
  v10 = Destination.Buffer == 0 ? 0xC000009A : 0;
  HsmDbgBreakOnStatus(v10);
  if ( Buffer )
  {
    RtlAppendUnicodeStringToString(&Destination, &Source);
    if ( Destination.Buffer[((unsigned __int64)Destination.Length >> 1) - 1] != 92 )
      RtlAppendUnicodeToString(&Destination, L"\\");
    RtlAppendUnicodeStringToString(&Destination, a3);
    Destination.Buffer[(unsigned __int64)Destination.Length >> 1] = 0;
    v15 = Destination;
    Destination.Buffer = 0;
    goto LABEL_12;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v18 = 22;
    goto LABEL_30;
  }
LABEL_13:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Source.Buffer )
    ExFreePoolWithTag(Source.Buffer, 0x73557348u);
  if ( Destination.Buffer )
    ExFreePoolWithTag(Destination.Buffer, 0x73557348u);
  return v10;
}

```

## disassembly

```asm
0x14005f204  mov     r11, rsp
0x14005f207  mov     [r11+10h], rbx
0x14005f20b  mov     [r11+18h], rsi
0x14005f20f  push    rbp
0x14005f210  push    rdi
0x14005f211  push    r13
0x14005f213  push    r14
0x14005f215  push    r15
0x14005f217  mov     rbp, rsp
0x14005f21a  sub     rsp, 80h
0x14005f221  lea     rax, [rbp+Object]
0x14005f225  mov     [rbp+FileHandle], 0
0x14005f22d  mov     [r11-68h], rax
0x14005f231  mov     r15, r8
0x14005f234  lea     rax, [rbp+FileHandle]
0x14005f238  mov     [rbp+Object], 0
0x14005f240  mov     [r11-70h], rax
0x14005f244  mov     r13, r9
0x14005f247  mov     r14, rdx
0x14005f24a  mov     [rsp+80h+var_50], 0
0x14005f24f  xorps   xmm0, xmm0
0x14005f252  mov     [rsp+80h+var_58], 200001h
0x14005f25a  xorps   xmm1, xmm1
0x14005f25d  mov     r8, rdx
0x14005f260  mov     rdx, [rcx+20h]
0x14005f264  mov     r9d, 100080h
0x14005f26a  mov     rsi, rcx
0x14005f26d  movups  xmmword ptr [rbp+Source.Length], xmm0
0x14005f271  movups  xmmword ptr [rbp+Destination.Length], xmm1
0x14005f275  call    HsmpOpenFileByIdEx
0x14005f27a  mov     ecx, eax
0x14005f27c  mov     edi, eax
0x14005f27e  call    HsmDbgBreakOnStatus
0x14005f283  test    edi, edi
0x14005f285  js      loc_14005F453
0x14005f28b  mov     r8, [rbp+Object]
0x14005f28f  lea     rax, [rbp+Source]
0x14005f293  mov     rcx, [rsi+20h]
0x14005f297  mov     r9d, 101h
0x14005f29d  mov     [rsp+80h+var_60], rax
0x14005f2a2  call    HsmiQueryFullFilePath
0x14005f2a7  mov     ecx, eax
0x14005f2a9  mov     edi, eax
0x14005f2ab  call    HsmDbgBreakOnStatus
0x14005f2b0  test    edi, edi
0x14005f2b2  js      loc_14005F4C8
0x14005f2b8  test    r15, r15
0x14005f2bb  jz      loc_14005F393
0x14005f2c1  movzx   eax, [rbp+Source.Length]
0x14005f2c5  add     ax, 2
0x14005f2c9  cmp     ax, [rbp+Source.Length]
0x14005f2cd  jb      loc_14005F417
0x14005f2d3  movzx   ecx, ax
0x14005f2d6  add     cx, [r15]
0x14005f2da  cmp     cx, ax
0x14005f2dd  jb      loc_14005F417
0x14005f2e3  lea     edx, [rcx+2]
0x14005f2e6  cmp     dx, cx
0x14005f2e9  jb      loc_14005F417
0x14005f2ef  mov     [rbp+Destination.MaximumLength], dx
0x14005f2f3  xor     eax, eax
0x14005f2f5  movzx   edx, dx
0x14005f2f8  mov     ecx, 100h
0x14005f2fd  mov     r8d, 73557348h
0x14005f303  mov     [rbp+Destination.Length], ax
0x14005f307  call    cs:__imp_ExAllocatePool2
0x14005f30e  nop     dword ptr [rax+rax+00h]
0x14005f313  mov     rcx, rax
0x14005f316  mov     [rbp+Destination.Buffer], rax
0x14005f31a  neg     rcx
0x14005f31d  mov     rbx, rax
0x14005f320  sbb     edi, edi
0x14005f322  not     edi
0x14005f324  and     edi, 0C000009Ah
0x14005f32a  mov     ecx, edi
0x14005f32c  call    HsmDbgBreakOnStatus
0x14005f331  test    rbx, rbx
0x14005f334  jz      loc_14005F4FB
0x14005f33a  lea     rdx, [rbp+Source]; Source
0x14005f33e  lea     rcx, [rbp+Destination]; Destination
0x14005f342  call    cs:__imp_RtlAppendUnicodeStringToString
0x14005f349  nop     dword ptr [rax+rax+00h]
0x14005f34e  movzx   ecx, [rbp+Destination.Length]
0x14005f352  mov     rax, [rbp+Destination.Buffer]
0x14005f356  shr     rcx, 1
0x14005f359  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14005f35f  jnz     loc_14005F486
0x14005f365  mov     rdx, r15; Source
0x14005f368  lea     rcx, [rbp+Destination]; Destination
0x14005f36c  call    cs:__imp_RtlAppendUnicodeStringToString
0x14005f373  nop     dword ptr [rax+rax+00h]
0x14005f378  movzx   edx, [rbp+Destination.Length]
0x14005f37c  mov     rax, [rbp+Destination.Buffer]
0x14005f380  shr     rdx, 1
0x14005f383  xor     ecx, ecx
0x14005f385  mov     [rax+rdx*2], cx
0x14005f389  movups  xmm0, xmmword ptr [rbp+Destination.Length]
0x14005f38d  mov     [rbp+Destination.Buffer], rcx
0x14005f391  jmp     short loc_14005F39F
0x14005f393  movups  xmm0, xmmword ptr [rbp+Source.Length]
0x14005f397  mov     [rbp+Source.Buffer], 0
0x14005f39f  movdqu  xmmword ptr [r13+0], xmm0
0x14005f3a5  cmp     [rbp+Object], 0
0x14005f3aa  jz      short loc_14005F3BC
0x14005f3ac  mov     rcx, [rbp+Object]; Object
0x14005f3b0  call    cs:__imp_ObfDereferenceObject
0x14005f3b7  nop     dword ptr [rax+rax+00h]
0x14005f3bc  mov     rcx, [rbp+FileHandle]; FileHandle
0x14005f3c0  test    rcx, rcx
0x14005f3c3  jz      short loc_14005F3D1
0x14005f3c5  call    cs:__imp_FltClose
0x14005f3cc  nop     dword ptr [rax+rax+00h]
0x14005f3d1  mov     rcx, [rbp+Source.Buffer]; P
0x14005f3d5  test    rcx, rcx
0x14005f3d8  jz      short loc_14005F3EB
0x14005f3da  mov     edx, 73557348h; Tag
0x14005f3df  call    cs:__imp_ExFreePoolWithTag
0x14005f3e6  nop     dword ptr [rax+rax+00h]
0x14005f3eb  mov     rcx, [rbp+Destination.Buffer]; P
0x14005f3ef  test    rcx, rcx
0x14005f3f2  jnz     loc_14005F52C
0x14005f3f8  lea     r11, [rsp+80h+var_s0]
0x14005f400  mov     eax, edi
0x14005f402  mov     rbx, [r11+38h]
0x14005f406  mov     rsi, [r11+40h]
0x14005f40a  mov     rsp, r11
0x14005f40d  pop     r15
0x14005f40f  pop     r14
0x14005f411  pop     r13
0x14005f413  pop     rdi
0x14005f414  pop     rbp
0x14005f415  retn
0x14005f417  mov     eax, 0FFFFh
0x14005f41c  mov     [rbp+Destination.MaximumLength], ax
0x14005f420  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f427  lea     rax, WPP_GLOBAL_Control
0x14005f42e  cmp     rcx, rax
0x14005f431  jz      loc_14005F3A5
0x14005f437  mov     eax, [rcx+2Ch]
0x14005f43a  test    al, 8
0x14005f43c  jz      loc_14005F3A5
0x14005f442  cmp     byte ptr [rcx+29h], 2
0x14005f446  jb      loc_14005F3A5
0x14005f44c  mov     edx, 15h
0x14005f451  jmp     short loc_14005F4A7
0x14005f453  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f45a  lea     rax, WPP_GLOBAL_Control
0x14005f461  cmp     rcx, rax
0x14005f464  jz      loc_14005F3A5
0x14005f46a  mov     eax, [rcx+2Ch]
0x14005f46d  test    al, 8
0x14005f46f  jz      loc_14005F3A5
0x14005f475  cmp     byte ptr [rcx+29h], 2
0x14005f479  jb      loc_14005F3A5
0x14005f47f  mov     edx, 13h
0x14005f484  jmp     short loc_14005F4A7
0x14005f486  lea     rdx, asc_1400206E8; "\\"
0x14005f48d  lea     rcx, [rbp+Destination]; Destination
0x14005f491  call    cs:__imp_RtlAppendUnicodeToString
0x14005f498  nop     dword ptr [rax+rax+00h]
0x14005f49d  jmp     loc_14005F365
0x14005f4a2  mov     edx, 16h
0x14005f4a7  mov     rcx, [rcx+18h]
0x14005f4ab  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005f4b2  mov     [rsp+80h+var_58], edi
0x14005f4b6  mov     r9, rsi
0x14005f4b9  mov     [rsp+80h+var_60], r14
0x14005f4be  call    WPP_SF_qqd
0x14005f4c3  jmp     loc_14005F3A5
0x14005f4c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f4cf  lea     rax, WPP_GLOBAL_Control
0x14005f4d6  cmp     rcx, rax
0x14005f4d9  jz      loc_14005F3A5
0x14005f4df  mov     eax, [rcx+2Ch]
0x14005f4e2  test    al, 8
0x14005f4e4  jz      loc_14005F3A5
0x14005f4ea  cmp     byte ptr [rcx+29h], 2
0x14005f4ee  jb      loc_14005F3A5
0x14005f4f4  mov     edx, 14h
0x14005f4f9  jmp     short loc_14005F4A7
0x14005f4fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f502  lea     rax, WPP_GLOBAL_Control
0x14005f509  cmp     rcx, rax
0x14005f50c  jz      loc_14005F3A5
0x14005f512  mov     eax, [rcx+2Ch]
0x14005f515  test    al, 8
0x14005f517  jz      loc_14005F3A5
0x14005f51d  cmp     byte ptr [rcx+29h], 2
0x14005f521  jb      loc_14005F3A5
0x14005f527  jmp     loc_14005F4A2
0x14005f52c  mov     edx, 73557348h; Tag
0x14005f531  call    cs:__imp_ExFreePoolWithTag
0x14005f538  nop     dword ptr [rax+rax+00h]
0x14005f53d  jmp     loc_14005F3F8
```
