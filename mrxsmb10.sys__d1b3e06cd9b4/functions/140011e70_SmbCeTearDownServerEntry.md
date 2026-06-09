# SmbCeTearDownServerEntry

- ea: `0x140011e70`
- end: `0x14001200d`
- name: `SmbCeTearDownServerEntry`
- size: `413`
- prototype: `void __stdcall(PVOID Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140005c60`
- `0x14000ed10`
- `0x14000fd40`
- `0x140011e70`
- `0x140035200`
- `0x140040c10`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140011f28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011f4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011f69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011f8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011fad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011fcf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011f28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011f4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011f69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011f8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011fad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011fcf`
- `rdbss!RxFinalizeSecurityContext` at `0x140011ef2`
- `rdbss!RxFinalizeSecurityContext` at `0x140011ef2`
- `mrxsmb!SmbCepDereferenceTransport` at `0x140011ff2`
- `mrxsmb!SmbCepDereferenceTransport` at `0x140011ff2`

## pseudocode

```c
void __fastcall SmbCeTearDownServerEntry(_QWORD *Context)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
      (_DWORD)Context,
      (__int64)(Context + 10));
  v2 = (void *)Context[48];
  if ( v2 )
  {
    FsRtlDestroyMidAtlas(v2);
    Context[48] = 0;
  }
  if ( Context[43] )
    SmbCeUninitializeServerTransport(Context, 0, 0);
  RxFinalizeSecurityContext(Context + 70);
  if ( *((_BYTE *)Context + 632) )
  {
    CngRsa32Compat_MD5Final(Context + 75);
    *((_BYTE *)Context + 632) = 0;
  }
  v3 = (void *)Context[69];
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0);
    Context[69] = 0;
  }
  v4 = (void *)Context[11];
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0);
    Context[11] = 0;
  }
  v5 = (void *)Context[13];
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0);
    Context[13] = 0;
  }
  v6 = (void *)Context[82];
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0);
    Context[82] = 0;
  }
  v7 = (void *)Context[15];
  if ( v7 )
  {
    ExFreePoolWithTag(v7, 0);
    Context[15] = 0;
  }
  v8 = (void *)Context[19];
  if ( v8 )
  {
    ExFreePoolWithTag(v8, 0);
    Context[19] = 0;
  }
  if ( Context[42] )
    SmbCepDereferenceTransport();
  SmbMmFreeObjectPool(Context);
}

```

## disassembly

```asm
0x140011e70  push    rbx
0x140011e72  sub     rsp, 30h
0x140011e76  mov     rbx, rcx
0x140011e79  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140011e80  lea     rax, WPP_GLOBAL_Control
0x140011e87  cmp     rcx, rax
0x140011e8a  jz      short loc_140011EB6
0x140011e8c  test    dword ptr [rcx+2Ch], 200h
0x140011e93  jz      short loc_140011EB6
0x140011e95  mov     rcx, [rcx+18h]
0x140011e99  lea     rax, [rbx+50h]
0x140011e9d  mov     edx, 0Fh
0x140011ea2  mov     [rsp+38h+var_18], rax
0x140011ea7  mov     r9, rbx
0x140011eaa  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x140011eb1  call    WPP_SF_qZ
0x140011eb6  mov     rcx, [rbx+180h]; P
0x140011ebd  test    rcx, rcx
0x140011ec0  jz      short loc_140011ED4
0x140011ec2  xor     edx, edx
0x140011ec4  call    FsRtlDestroyMidAtlas
0x140011ec9  mov     qword ptr [rbx+180h], 0
0x140011ed4  cmp     qword ptr [rbx+158h], 0
0x140011edc  jz      short loc_140011EEB
0x140011ede  xor     r8d, r8d
0x140011ee1  xor     edx, edx
0x140011ee3  mov     rcx, rbx
0x140011ee6  call    SmbCeUninitializeServerTransport
0x140011eeb  lea     rcx, [rbx+230h]
0x140011ef2  call    cs:__imp_RxFinalizeSecurityContext
0x140011ef9  nop     dword ptr [rax+rax+00h]
0x140011efe  cmp     byte ptr [rbx+278h], 0
0x140011f05  jz      short loc_140011F1A
0x140011f07  lea     rcx, [rbx+258h]
0x140011f0e  call    CngRsa32Compat_MD5Final
0x140011f13  mov     byte ptr [rbx+278h], 0
0x140011f1a  mov     rcx, [rbx+228h]; P
0x140011f21  test    rcx, rcx
0x140011f24  jz      short loc_140011F3F
0x140011f26  xor     edx, edx; Tag
0x140011f28  call    cs:__imp_ExFreePoolWithTag
0x140011f2f  nop     dword ptr [rax+rax+00h]
0x140011f34  mov     qword ptr [rbx+228h], 0
0x140011f3f  mov     rcx, [rbx+58h]; P
0x140011f43  test    rcx, rcx
0x140011f46  jz      short loc_140011F5E
0x140011f48  xor     edx, edx; Tag
0x140011f4a  call    cs:__imp_ExFreePoolWithTag
0x140011f51  nop     dword ptr [rax+rax+00h]
0x140011f56  mov     qword ptr [rbx+58h], 0
0x140011f5e  mov     rcx, [rbx+68h]; P
0x140011f62  test    rcx, rcx
0x140011f65  jz      short loc_140011F7D
0x140011f67  xor     edx, edx; Tag
0x140011f69  call    cs:__imp_ExFreePoolWithTag
0x140011f70  nop     dword ptr [rax+rax+00h]
0x140011f75  mov     qword ptr [rbx+68h], 0
0x140011f7d  mov     rcx, [rbx+290h]; P
0x140011f84  test    rcx, rcx
0x140011f87  jz      short loc_140011FA2
0x140011f89  xor     edx, edx; Tag
0x140011f8b  call    cs:__imp_ExFreePoolWithTag
0x140011f92  nop     dword ptr [rax+rax+00h]
0x140011f97  mov     qword ptr [rbx+290h], 0
0x140011fa2  mov     rcx, [rbx+78h]; P
0x140011fa6  test    rcx, rcx
0x140011fa9  jz      short loc_140011FC1
0x140011fab  xor     edx, edx; Tag
0x140011fad  call    cs:__imp_ExFreePoolWithTag
0x140011fb4  nop     dword ptr [rax+rax+00h]
0x140011fb9  mov     qword ptr [rbx+78h], 0
0x140011fc1  mov     rcx, [rbx+98h]; P
0x140011fc8  test    rcx, rcx
0x140011fcb  jz      short loc_140011FE6
0x140011fcd  xor     edx, edx; Tag
0x140011fcf  call    cs:__imp_ExFreePoolWithTag
0x140011fd6  nop     dword ptr [rax+rax+00h]
0x140011fdb  mov     qword ptr [rbx+98h], 0
0x140011fe6  mov     rcx, [rbx+150h]
0x140011fed  test    rcx, rcx
0x140011ff0  jz      short loc_140011FFE
0x140011ff2  call    cs:__imp_SmbCepDereferenceTransport
0x140011ff9  nop     dword ptr [rax+rax+00h]
0x140011ffe  mov     rcx, rbx
0x140012001  call    SmbMmFreeObjectPool
0x140012006  add     rsp, 30h
0x14001200a  pop     rbx
0x14001200b  retn
```
