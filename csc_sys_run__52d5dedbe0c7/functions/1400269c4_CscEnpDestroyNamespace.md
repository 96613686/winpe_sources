# CscEnpDestroyNamespace

- ea: `0x1400269c4`
- end: `0x140026b13`
- name: `CscEnpDestroyNamespace`
- size: `335`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140059edc`
- `0x140071c00`

## callees

- `0x140010e20`
- `0x140018474`
- `0x1400269c4`
- `0x14002a798`
- `0x14002cb18`
- `0x14002d838`
- `0x14005c5f4`
- `0x14005f67c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140026a02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026a36`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026aef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026a02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026a36`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026aef`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400269ee`
- `ntoskrnl!ExDeleteResourceLite` at `0x140026a22`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400269ee`
- `ntoskrnl!ExDeleteResourceLite` at `0x140026a22`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140026abc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140026abc`

## pseudocode

```c
void __fastcall CscEnpDestroyNamespace(__int64 *a1)
{
  __int64 v1; // rbx
  void *v3; // rdi
  void *v4; // rdi
  void *v5; // rcx
  void *v6; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = *(void **)(v1 + 120);
    if ( v3 )
    {
      ExDeleteResourceLite(*(PERESOURCE *)(v1 + 120));
      ExFreePoolWithTag(v3, 0x22407343u);
      *(_QWORD *)(v1 + 120) = 0;
    }
    v4 = *(void **)(v1 + 8);
    if ( v4 )
    {
      ExDeleteResourceLite(*(PERESOURCE *)(v1 + 8));
      ExFreePoolWithTag(v4, 0x22407343u);
      *(_QWORD *)(v1 + 8) = 0;
    }
    if ( *(_QWORD *)(v1 + 40) )
      CscStTuDestroyTunnelCache();
    if ( *(_QWORD *)(v1 + 64) )
    {
      CscStOrphanerClose();
      *(_QWORD *)(v1 + 64) = 0;
    }
    v5 = *(void **)(v1 + 56);
    if ( v5 )
    {
      CscSidMapClose(v5);
      *(_QWORD *)(v1 + 56) = 0;
    }
    if ( *(_QWORD *)(v1 + 48) )
    {
      CscPqClose();
      *(_QWORD *)(v1 + 48) = 0;
    }
    v6 = *(void **)(v1 + 16);
    if ( v6 )
    {
      CscStorepLowIoClose(v6);
      *(_QWORD *)(v1 + 16) = 0;
    }
    if ( *(_QWORD *)(v1 + 80) )
      RtlFreeUnicodeString((PUNICODE_STRING)(v1 + 72));
    if ( *(_QWORD *)(v1 + 96) )
      CscEnpDestroyVersionString(v1 + 88);
    if ( *(_QWORD *)(v1 + 24) )
      CscSeDestroySecurityDescriptor(v1 + 24);
    ExFreePoolWithTag((PVOID)v1, 0x27407343u);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x1400269c4  mov     [rsp+arg_0], rbx
0x1400269c9  mov     [rsp+arg_8], rsi
0x1400269ce  push    rdi
0x1400269cf  sub     rsp, 20h
0x1400269d3  mov     rbx, [rcx]
0x1400269d6  mov     rsi, rcx
0x1400269d9  test    rbx, rbx
0x1400269dc  jz      loc_140026B02
0x1400269e2  mov     rdi, [rbx+78h]
0x1400269e6  test    rdi, rdi
0x1400269e9  jz      short loc_140026A16
0x1400269eb  mov     rcx, rdi; Resource
0x1400269ee  call    cs:__imp_ExDeleteResourceLite
0x1400269f5  nop     dword ptr [rax+rax+00h]
0x1400269fa  mov     edx, 22407343h; Tag
0x1400269ff  mov     rcx, rdi; P
0x140026a02  call    cs:__imp_ExFreePoolWithTag
0x140026a09  nop     dword ptr [rax+rax+00h]
0x140026a0e  mov     qword ptr [rbx+78h], 0
0x140026a16  mov     rdi, [rbx+8]
0x140026a1a  test    rdi, rdi
0x140026a1d  jz      short loc_140026A4A
0x140026a1f  mov     rcx, rdi; Resource
0x140026a22  call    cs:__imp_ExDeleteResourceLite
0x140026a29  nop     dword ptr [rax+rax+00h]
0x140026a2e  mov     edx, 22407343h; Tag
0x140026a33  mov     rcx, rdi; P
0x140026a36  call    cs:__imp_ExFreePoolWithTag
0x140026a3d  nop     dword ptr [rax+rax+00h]
0x140026a42  mov     qword ptr [rbx+8], 0
0x140026a4a  lea     rcx, [rbx+28h]
0x140026a4e  cmp     qword ptr [rcx], 0
0x140026a52  jz      short loc_140026A59
0x140026a54  call    CscStTuDestroyTunnelCache
0x140026a59  mov     rcx, [rbx+40h]
0x140026a5d  test    rcx, rcx
0x140026a60  jz      short loc_140026A6F
0x140026a62  call    CscStOrphanerClose
0x140026a67  mov     qword ptr [rbx+40h], 0
0x140026a6f  mov     rcx, [rbx+38h]; P
0x140026a73  test    rcx, rcx
0x140026a76  jz      short loc_140026A85
0x140026a78  call    CscSidMapClose
0x140026a7d  mov     qword ptr [rbx+38h], 0
0x140026a85  mov     rcx, [rbx+30h]
0x140026a89  test    rcx, rcx
0x140026a8c  jz      short loc_140026A9B
0x140026a8e  call    CscPqClose
0x140026a93  mov     qword ptr [rbx+30h], 0
0x140026a9b  mov     rcx, [rbx+10h]; Handle
0x140026a9f  test    rcx, rcx
0x140026aa2  jz      short loc_140026AB1
0x140026aa4  call    CscStorepLowIoClose
0x140026aa9  mov     qword ptr [rbx+10h], 0
0x140026ab1  cmp     qword ptr [rbx+50h], 0
0x140026ab6  jz      short loc_140026AC8
0x140026ab8  lea     rcx, [rbx+48h]; UnicodeString
0x140026abc  call    cs:__imp_RtlFreeUnicodeString
0x140026ac3  nop     dword ptr [rax+rax+00h]
0x140026ac8  cmp     qword ptr [rbx+60h], 0
0x140026acd  jz      short loc_140026AD8
0x140026acf  lea     rcx, [rbx+58h]
0x140026ad3  call    CscEnpDestroyVersionString
0x140026ad8  lea     rcx, [rbx+18h]
0x140026adc  cmp     qword ptr [rcx], 0
0x140026ae0  jz      short loc_140026AE7
0x140026ae2  call    CscSeDestroySecurityDescriptor
0x140026ae7  mov     edx, 27407343h; Tag
0x140026aec  mov     rcx, rbx; P
0x140026aef  call    cs:__imp_ExFreePoolWithTag
0x140026af6  nop     dword ptr [rax+rax+00h]
0x140026afb  mov     qword ptr [rsi], 0
0x140026b02  mov     rbx, [rsp+28h+arg_0]
0x140026b07  mov     rsi, [rsp+28h+arg_8]
0x140026b0c  add     rsp, 20h
0x140026b10  pop     rdi
0x140026b11  retn
```
