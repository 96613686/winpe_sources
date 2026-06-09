# CKsFilterFactory::StoreReferenceGuidWithSymbolicName(void)

- ea: `0x18003c0fc`
- end: `0x18003c317`
- name: `?StoreReferenceGuidWithSymbolicName@CKsFilterFactory@@QEAAJXZ`
- size: `539`
- prototype: `__int64 __fastcall(CKsFilterFactory *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x18004dccc`

## callees

- `0x18000abec`
- `0x18000b7bc`
- `0x18000c630`
- `0x18003b8c0`
- `0x18003c0fc`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18003c27b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18003c27b`
- `ntoskrnl!ZwClose` at `0x18003c26a`
- `ntoskrnl!ZwClose` at `0x18003c26a`
- `ntoskrnl!ZwSetValueKey` at `0x18003c254`
- `ntoskrnl!ZwSetValueKey` at `0x18003c254`

## pseudocode

```c
__int64 __fastcall CKsFilterFactory::StoreReferenceGuidWithSymbolicName(CKsFilterFactory *this)
{
  int v1; // edx
  CKsFilterFactory *v2; // r9
  _LIST_ENTRY *p_m_DeviceClasses; // r10
  PVOID *v4; // rdi
  struct _LIST_ENTRY *Flink; // r8
  _QWORD *v6; // rcx
  _QWORD *v7; // r8
  unsigned int v8; // ebx
  PDEVICE_OBJECT v9; // rcx
  int v10; // r9d
  int v11; // eax
  int v12; // r9d
  __int64 DataSize; // [rsp+28h] [rbp-50h]
  UNICODE_STRING ValueName; // [rsp+30h] [rbp-48h] BYREF
  HANDLE KeyHandle; // [rsp+80h] [rbp+8h] BYREF

  if ( IsEqualGUIDAligned(&this->m_ReferenceGUID.Data1, &GUID_9b365890_165f_11d0_a195_0020afd156e4) )
  {
    v8 = 0;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v8;
    v9 = WPP_GLOBAL_Control;
    if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      goto LABEL_24;
    v10 = 52;
    LOBYTE(v1) = 5;
    goto LABEL_23;
  }
  KeyHandle = 0;
  p_m_DeviceClasses = &v2->m_DeviceClasses;
  v4 = 0;
  Flink = v2->m_DeviceClasses.Flink;
  ValueName = 0;
  while ( Flink != p_m_DeviceClasses )
  {
    if ( IsEqualGUIDAligned(&Flink[1].Flink->Flink, &GUID_e5323777_f976_4f5b_9b55_b94699c46e44) )
    {
      v4 = (PVOID *)(v7 + 3);
      v2->m_profileGUID = GUID_e5323777_f976_4f5b_9b55_b94699c46e44;
      break;
    }
    if ( !v4 && IsEqualGUIDAligned(v6, &GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca) )
    {
      v4 = (PVOID *)(v7 + 3);
      v2->m_profileGUID = GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca;
    }
    Flink = (struct _LIST_ENTRY *)*v7;
  }
  if ( !v4 )
  {
    v8 = -1073741637;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v8;
    v9 = WPP_GLOBAL_Control;
    v10 = 49;
    LOBYTE(v1) = 2;
LABEL_23:
    WPP_RECORDER_SF_(v9->DeviceExtension, v1, 1, v10, (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids);
    goto LABEL_24;
  }
  v11 = CKsFilterFactory::BuildKeyAndValueName(v2, &KeyHandle, &ValueName);
  v8 = v11;
  if ( v11 >= 0 )
  {
    v8 = ZwSetValueKey(KeyHandle, &ValueName, 0, 1u, v4[1], *(unsigned __int16 *)v4 + 2);
    ZwClose(KeyHandle);
    RtlFreeUnicodeString(&ValueName);
    if ( (v8 & 0x80000000) == 0 )
      goto LABEL_24;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v8;
    v12 = 51;
    LODWORD(DataSize) = v8;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v8;
    v12 = 50;
    LODWORD(DataSize) = v11;
  }
  LOBYTE(v1) = 2;
  WPP_RECORDER_SF_D(
    WPP_GLOBAL_Control->DeviceExtension,
    v1,
    1,
    v12,
    (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
    DataSize,
    *(_QWORD *)&ValueName.Length,
    ValueName.Buffer);
LABEL_24:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(DataSize) = v8;
    LOBYTE(v1) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v1,
      1,
      53,
      (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
      DataSize);
  }
  return v8;
}

```

## disassembly

```asm
0x18003c0fc  push    rbx
0x18003c0fe  push    rbp
0x18003c0ff  push    rsi
0x18003c100  push    rdi
0x18003c101  push    r14
0x18003c103  push    r15
0x18003c105  sub     rsp, 48h
0x18003c109  mov     r9, rcx
0x18003c10c  lea     rdx, _GUID_9b365890_165f_11d0_a195_0020afd156e4
0x18003c113  add     rcx, 1ACh
0x18003c11a  call    IsEqualGUIDAligned
0x18003c11f  xor     esi, esi
0x18003c121  lea     r15, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x18003c128  lea     rbp, WPP_RECORDER_INITIALIZED
0x18003c12f  mov     r14d, 1
0x18003c135  test    eax, eax
0x18003c137  jnz     loc_18003C2A3
0x18003c13d  xorps   xmm0, xmm0
0x18003c140  mov     [rsp+78h+KeyHandle], rsi
0x18003c148  lea     r10, [r9+158h]
0x18003c14f  mov     edi, esi
0x18003c151  mov     r8, [r10]
0x18003c154  movups  xmmword ptr [rsp+78h+ValueName.Length], xmm0
0x18003c159  cmp     r8, r10
0x18003c15c  jz      short loc_18003C1B4
0x18003c15e  mov     rcx, [r8+10h]
0x18003c162  lea     rdx, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44
0x18003c169  call    IsEqualGUIDAligned
0x18003c16e  test    eax, eax
0x18003c170  jnz     short loc_18003C1A0
0x18003c172  test    rdi, rdi
0x18003c175  jnz     short loc_18003C19B
0x18003c177  lea     rdx, _GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca
0x18003c17e  call    IsEqualGUIDAligned
0x18003c183  test    eax, eax
0x18003c185  jz      short loc_18003C19B
0x18003c187  movups  xmm0, xmmword ptr cs:_GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca.Data1
0x18003c18e  lea     rdi, [r8+18h]
0x18003c192  movdqu  xmmword ptr [r9+1C8h], xmm0
0x18003c19b  mov     r8, [r8]
0x18003c19e  jmp     short loc_18003C159
0x18003c1a0  movups  xmm0, xmmword ptr cs:_GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data1
0x18003c1a7  lea     rdi, [r8+18h]
0x18003c1ab  movdqu  xmmword ptr [r9+1C8h], xmm0
0x18003c1b4  test    rdi, rdi
0x18003c1b7  jnz     short loc_18003C1DD
0x18003c1b9  mov     ebx, 0C00000BBh
0x18003c1be  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18003c1c5  jz      loc_18003C307
0x18003c1cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c1d2  lea     r9d, [rdi+31h]
0x18003c1d6  mov     dl, 2
0x18003c1d8  jmp     loc_18003C2C3
0x18003c1dd  lea     r8, [rsp+78h+ValueName]; struct _UNICODE_STRING *
0x18003c1e2  mov     rcx, r9; this
0x18003c1e5  lea     rdx, [rsp+78h+KeyHandle]; void **
0x18003c1ed  call    ?BuildKeyAndValueName@CKsFilterFactory@@QEAAJPEAPEAXPEAU_UNICODE_STRING@@@Z; CKsFilterFactory::BuildKeyAndValueName(void * *,_UNICODE_STRING *)
0x18003c1f2  mov     ebx, eax
0x18003c1f4  test    eax, eax
0x18003c1f6  jns     short loc_18003C22E
0x18003c1f8  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18003c1ff  jz      loc_18003C307
0x18003c205  mov     r9d, 32h ; '2'
0x18003c20b  mov     dword ptr [rsp+78h+DataSize], eax
0x18003c20f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c216  mov     r8d, r14d
0x18003c219  mov     dl, 2
0x18003c21b  mov     [rsp+78h+Data], r15
0x18003c220  mov     rcx, [rcx+40h]
0x18003c224  call    WPP_RECORDER_SF_D
0x18003c229  jmp     loc_18003C2D4
0x18003c22e  movzx   eax, word ptr [rdi]
0x18003c231  lea     rdx, [rsp+78h+ValueName]; ValueName
0x18003c236  mov     rcx, [rsp+78h+KeyHandle]; KeyHandle
0x18003c23e  add     eax, 2
0x18003c241  mov     dword ptr [rsp+78h+DataSize], eax; DataSize
0x18003c245  mov     r9d, r14d; Type
0x18003c248  mov     rax, [rdi+8]
0x18003c24c  xor     r8d, r8d; TitleIndex
0x18003c24f  mov     [rsp+78h+Data], rax; Data
0x18003c254  call    cs:__imp_ZwSetValueKey
0x18003c25b  nop     dword ptr [rax+rax+00h]
0x18003c260  mov     rcx, [rsp+78h+KeyHandle]; Handle
0x18003c268  mov     ebx, eax
0x18003c26a  call    cs:__imp_ZwClose
0x18003c271  nop     dword ptr [rax+rax+00h]
0x18003c276  lea     rcx, [rsp+78h+ValueName]; UnicodeString
0x18003c27b  call    cs:__imp_RtlFreeUnicodeString
0x18003c282  nop     dword ptr [rax+rax+00h]
0x18003c287  test    ebx, ebx
0x18003c289  jns     short loc_18003C2D4
0x18003c28b  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18003c292  jz      short loc_18003C307
0x18003c294  mov     r9d, 33h ; '3'
0x18003c29a  mov     dword ptr [rsp+78h+DataSize], ebx
0x18003c29e  jmp     loc_18003C20F
0x18003c2a3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18003c2aa  mov     ebx, esi
0x18003c2ac  jz      short loc_18003C307
0x18003c2ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c2b5  cmp     [rcx+48h], si
0x18003c2b9  jz      short loc_18003C2D4
0x18003c2bb  mov     r9d, 34h ; '4'
0x18003c2c1  mov     dl, 5
0x18003c2c3  mov     rcx, [rcx+40h]
0x18003c2c7  mov     r8d, r14d
0x18003c2ca  mov     [rsp+78h+Data], r15
0x18003c2cf  call    WPP_RECORDER_SF_
0x18003c2d4  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18003c2db  jz      short loc_18003C307
0x18003c2dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c2e4  cmp     [rcx+48h], si
0x18003c2e8  jz      short loc_18003C307
0x18003c2ea  mov     rcx, [rcx+40h]
0x18003c2ee  mov     r9d, 35h ; '5'
0x18003c2f4  mov     dword ptr [rsp+78h+DataSize], ebx
0x18003c2f8  mov     r8d, r14d
0x18003c2fb  mov     dl, 5
0x18003c2fd  mov     [rsp+78h+Data], r15
0x18003c302  call    WPP_RECORDER_SF_D
0x18003c307  mov     eax, ebx
0x18003c309  add     rsp, 48h
0x18003c30d  pop     r15
0x18003c30f  pop     r14
0x18003c311  pop     rdi
0x18003c312  pop     rsi
0x18003c313  pop     rbp
0x18003c314  pop     rbx
0x18003c315  retn
```
