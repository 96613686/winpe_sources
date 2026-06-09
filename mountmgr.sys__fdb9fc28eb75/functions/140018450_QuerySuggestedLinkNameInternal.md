# QuerySuggestedLinkNameInternal

- ea: `0x140018450`
- end: `0x140018558`
- name: `QuerySuggestedLinkNameInternal`
- size: `264`
- prototype: `__int64 __fastcall(__int64, PDEVICE_OBJECT DeviceObject)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140017a20`

## callees

- `0x140017bf0`
- `0x140018450`
- `0x140019ca0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140018490`
- `ntoskrnl!ExAllocatePool2` at `0x140018490`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018532`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018532`

## pseudocode

```c
__int64 __fastcall QuerySuggestedLinkNameInternal(struct _FILE_OBJECT *a1, PDEVICE_OBJECT DeviceObject, __int64 a3)
{
  bool v3; // zf
  USHORT *Pool2; // rax
  USHORT *v8; // rbp
  NTSTATUS v10; // edi
  UNICODE_STRING String2; // [rsp+40h] [rbp-18h] BYREF

  v3 = *(_BYTE *)(a3 + 127) == 0;
  String2 = 0;
  if ( !v3 )
    return 0;
  Pool2 = (USHORT *)ExAllocatePool2(258, 32, 1098149453);
  v8 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  v10 = MountMgrSendDeviceControl(DeviceObject, 0x4D000Cu, 0, 0, Pool2, 0x20u, a1);
  if ( v10 >= 0 )
  {
    if ( v8[1] )
    {
      String2.Length = v8[1];
      String2.MaximumLength = v8[1];
      String2.Buffer = v8 + 2;
      if ( (unsigned __int8)IsDriveLetter(&String2) )
        *(_BYTE *)(a3 + 128) = *((_BYTE *)String2.Buffer + 24);
    }
    else
    {
      *(_BYTE *)(a3 + 127) = 1;
    }
  }
  ExFreePoolWithTag(v8, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140018450  mov     [rsp+arg_8], rbx
0x140018455  mov     [rsp+arg_10], rsi
0x14001845a  push    rdi
0x14001845b  sub     rsp, 50h
0x14001845f  cmp     byte ptr [r8+7Fh], 0
0x140018464  xorps   xmm0, xmm0
0x140018467  movups  xmmword ptr [rsp+58h+String2.Length], xmm0
0x14001846c  mov     rbx, r8
0x14001846f  mov     rdi, rdx
0x140018472  mov     rsi, rcx
0x140018475  jnz     loc_140018545
0x14001847b  mov     edx, 20h ; ' '
0x140018480  mov     [rsp+58h+arg_0], rbp
0x140018485  mov     ecx, 102h
0x14001848a  mov     r8d, 41746E4Dh
0x140018490  call    cs:__imp_ExAllocatePool2
0x140018497  nop     dword ptr [rax+rax+00h]
0x14001849c  mov     rbp, rax
0x14001849f  test    rax, rax
0x1400184a2  jnz     short loc_1400184BF
0x1400184a4  mov     eax, 0C000009Ah
0x1400184a9  mov     rbp, [rsp+58h+arg_0]
0x1400184ae  mov     rbx, [rsp+58h+arg_8]
0x1400184b3  mov     rsi, [rsp+58h+arg_10]
0x1400184b8  add     rsp, 50h
0x1400184bc  pop     rdi
0x1400184bd  retn
0x1400184bf  mov     [rsp+58h+var_28], rsi; __int64
0x1400184c4  xor     r9d, r9d; InputBufferLength
0x1400184c7  mov     [rsp+58h+var_30], 20h ; ' '; ULONG
0x1400184cf  xor     r8d, r8d; InputBuffer
0x1400184d2  mov     edx, 4D000Ch; IoControlCode
0x1400184d7  mov     [rsp+58h+var_38], rbp; PVOID
0x1400184dc  mov     rcx, rdi; DeviceObject
0x1400184df  call    MountMgrSendDeviceControl
0x1400184e4  mov     edi, eax
0x1400184e6  test    eax, eax
0x1400184e8  js      short loc_14001852D
0x1400184ea  movzx   eax, word ptr [rbp+2]
0x1400184ee  test    ax, ax
0x1400184f1  jnz     short loc_1400184F9
0x1400184f3  mov     byte ptr [rbx+7Fh], 1
0x1400184f7  jmp     short loc_14001852D
0x1400184f9  mov     [rsp+58h+String2.Length], ax
0x1400184fe  lea     rcx, [rsp+58h+String2]; String2
0x140018503  movzx   eax, word ptr [rbp+2]
0x140018507  mov     [rsp+58h+String2.MaximumLength], ax
0x14001850c  lea     rax, [rbp+4]
0x140018510  mov     [rsp+58h+String2.Buffer], rax
0x140018515  call    IsDriveLetter
0x14001851a  test    al, al
0x14001851c  jz      short loc_14001852D
0x14001851e  mov     rax, [rsp+58h+String2.Buffer]
0x140018523  movzx   ecx, byte ptr [rax+18h]
0x140018527  mov     [rbx+80h], cl
0x14001852d  xor     edx, edx; Tag
0x14001852f  mov     rcx, rbp; P
0x140018532  call    cs:__imp_ExFreePoolWithTag
0x140018539  nop     dword ptr [rax+rax+00h]
0x14001853e  mov     eax, edi
0x140018540  jmp     loc_1400184A9
0x140018545  mov     rbx, [rsp+58h+arg_8]
0x14001854a  xor     eax, eax
0x14001854c  mov     rsi, [rsp+58h+arg_10]
0x140018551  add     rsp, 50h
0x140018555  pop     rdi
0x140018556  retn
```
