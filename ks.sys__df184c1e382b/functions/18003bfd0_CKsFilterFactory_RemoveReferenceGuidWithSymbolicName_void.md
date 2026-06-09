# CKsFilterFactory::RemoveReferenceGuidWithSymbolicName(void)

- ea: `0x18003bfd0`
- end: `0x18003c0f5`
- name: `?RemoveReferenceGuidWithSymbolicName@CKsFilterFactory@@QEAAJXZ`
- size: `293`
- prototype: `__int64 __fastcall(CKsFilterFactory *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x180056ea4`

## callees

- `0x18000abec`
- `0x18000c630`
- `0x18003b8c0`
- `0x18003bfd0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18003c074`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18003c074`
- `ntoskrnl!ZwClose` at `0x18003c063`
- `ntoskrnl!ZwClose` at `0x18003c063`
- `ntoskrnl!ZwDeleteValueKey` at `0x18003c050`
- `ntoskrnl!ZwDeleteValueKey` at `0x18003c050`

## pseudocode

```c
__int64 __fastcall CKsFilterFactory::RemoveReferenceGuidWithSymbolicName(CKsFilterFactory *this)
{
  unsigned int v1; // ebx
  int v2; // edx
  CKsFilterFactory *v3; // r9
  int v4; // eax
  int v5; // r9d
  __int64 v7; // [rsp+28h] [rbp-40h]
  unsigned int v8; // [rsp+28h] [rbp-40h]
  UNICODE_STRING ValueName; // [rsp+30h] [rbp-38h] BYREF
  HANDLE KeyHandle; // [rsp+70h] [rbp+8h] BYREF

  v1 = 0;
  if ( !IsEqualGUIDAligned(&this->m_ReferenceGUID.Data1, &GUID_9b365890_165f_11d0_a195_0020afd156e4) )
  {
    KeyHandle = 0;
    ValueName = 0;
    v4 = CKsFilterFactory::BuildKeyAndValueName(v3, &KeyHandle, &ValueName);
    v1 = v4;
    if ( v4 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v1;
      v5 = 54;
      v8 = v4;
      goto LABEL_8;
    }
    v1 = ZwDeleteValueKey(KeyHandle, &ValueName);
    ZwClose(KeyHandle);
    RtlFreeUnicodeString(&ValueName);
    if ( (v1 & 0x80000000) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v1;
      v5 = 55;
      v8 = v1;
LABEL_8:
      LOBYTE(v2) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v2,
        1,
        v5,
        (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
        v8);
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(v7) = v1;
    LOBYTE(v2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v2,
      1,
      56,
      (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
      v7);
  }
  return v1;
}

```

## disassembly

```asm
0x18003bfd0  push    rbx
0x18003bfd2  push    rsi
0x18003bfd3  push    rdi
0x18003bfd4  push    r14
0x18003bfd6  sub     rsp, 48h
0x18003bfda  mov     r9, rcx
0x18003bfdd  lea     rdx, _GUID_9b365890_165f_11d0_a195_0020afd156e4
0x18003bfe4  xor     edi, edi
0x18003bfe6  add     rcx, 1ACh
0x18003bfed  mov     ebx, edi
0x18003bfef  call    IsEqualGUIDAligned
0x18003bff4  lea     rsi, WPP_RECORDER_INITIALIZED
0x18003bffb  lea     r14, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x18003c002  test    eax, eax
0x18003c004  jnz     loc_18003C0B4
0x18003c00a  xorps   xmm0, xmm0
0x18003c00d  mov     [rsp+68h+KeyHandle], rdi
0x18003c012  lea     r8, [rsp+68h+ValueName]; struct _UNICODE_STRING *
0x18003c017  mov     rcx, r9; this
0x18003c01a  lea     rdx, [rsp+68h+KeyHandle]; void **
0x18003c01f  movups  xmmword ptr [rsp+68h+ValueName.Length], xmm0
0x18003c024  call    ?BuildKeyAndValueName@CKsFilterFactory@@QEAAJPEAPEAXPEAU_UNICODE_STRING@@@Z; CKsFilterFactory::BuildKeyAndValueName(void * *,_UNICODE_STRING *)
0x18003c029  mov     ebx, eax
0x18003c02b  test    eax, eax
0x18003c02d  jns     short loc_18003C046
0x18003c02f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18003c036  jz      loc_18003C0E8
0x18003c03c  lea     r9d, [rdi+36h]
0x18003c040  mov     dword ptr [rsp+68h+var_40], eax
0x18003c044  jmp     short loc_18003C097
0x18003c046  mov     rcx, [rsp+68h+KeyHandle]; KeyHandle
0x18003c04b  lea     rdx, [rsp+68h+ValueName]; ValueName
0x18003c050  call    cs:__imp_ZwDeleteValueKey
0x18003c057  nop     dword ptr [rax+rax+00h]
0x18003c05c  mov     rcx, [rsp+68h+KeyHandle]; Handle
0x18003c061  mov     ebx, eax
0x18003c063  call    cs:__imp_ZwClose
0x18003c06a  nop     dword ptr [rax+rax+00h]
0x18003c06f  lea     rcx, [rsp+68h+ValueName]; UnicodeString
0x18003c074  call    cs:__imp_RtlFreeUnicodeString
0x18003c07b  nop     dword ptr [rax+rax+00h]
0x18003c080  test    ebx, ebx
0x18003c082  jns     short loc_18003C0B4
0x18003c084  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18003c08b  jz      short loc_18003C0E8
0x18003c08d  mov     r9d, 37h ; '7'
0x18003c093  mov     dword ptr [rsp+68h+var_40], ebx
0x18003c097  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c09e  mov     r8d, 1
0x18003c0a4  mov     dl, 2
0x18003c0a6  mov     [rsp+68h+var_48], r14
0x18003c0ab  mov     rcx, [rcx+40h]
0x18003c0af  call    WPP_RECORDER_SF_D
0x18003c0b4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18003c0bb  jz      short loc_18003C0E8
0x18003c0bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c0c4  cmp     [rcx+48h], di
0x18003c0c8  jz      short loc_18003C0E8
0x18003c0ca  mov     rcx, [rcx+40h]
0x18003c0ce  mov     r9d, 38h ; '8'
0x18003c0d4  mov     dword ptr [rsp+68h+var_40], ebx
0x18003c0d8  mov     dl, 5
0x18003c0da  mov     [rsp+68h+var_48], r14
0x18003c0df  lea     r8d, [r9-37h]
0x18003c0e3  call    WPP_RECORDER_SF_D
0x18003c0e8  mov     eax, ebx
0x18003c0ea  add     rsp, 48h
0x18003c0ee  pop     r14
0x18003c0f0  pop     rdi
0x18003c0f1  pop     rsi
0x18003c0f2  pop     rbx
0x18003c0f3  retn
```
