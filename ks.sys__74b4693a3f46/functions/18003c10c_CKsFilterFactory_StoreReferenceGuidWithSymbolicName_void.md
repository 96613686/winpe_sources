# CKsFilterFactory::StoreReferenceGuidWithSymbolicName(void)

- ea: `0x18003c10c`
- end: `0x18003c327`
- name: `?StoreReferenceGuidWithSymbolicName@CKsFilterFactory@@QEAAJXZ`
- size: `539`
- prototype: `__int64 __fastcall(CKsFilterFactory *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x18004db2c`

## callees

- `0x18000abec`
- `0x18000b7bc`
- `0x18000c630`
- `0x18003b8d0`
- `0x18003c10c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18003c28b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18003c28b`
- `ntoskrnl!ZwClose` at `0x18003c27a`
- `ntoskrnl!ZwClose` at `0x18003c27a`
- `ntoskrnl!ZwSetValueKey` at `0x18003c264`
- `ntoskrnl!ZwSetValueKey` at `0x18003c264`

## pseudocode

```c
__int64 __fastcall CKsFilterFactory::StoreReferenceGuidWithSymbolicName(CKsFilterFactory *this)
{
  int v1; // edx
  CKsFilterFactory *v2; // r9
  _LIST_ENTRY *p_m_DeviceClasses; // r10
  PVOID *v4; // rdi
  struct _LIST_ENTRY *Flink; // r8
  __int64 v6; // rcx
  _QWORD *v7; // r8
  unsigned int v8; // ebx
  PDEVICE_OBJECT v9; // rcx
  int v10; // r9d
  int v11; // eax
  int v12; // r9d
  __int64 DataSize; // [rsp+28h] [rbp-50h]
  UNICODE_STRING ValueName; // [rsp+30h] [rbp-48h] BYREF
  HANDLE KeyHandle; // [rsp+80h] [rbp+8h] BYREF

  if ( (unsigned int)IsEqualGUIDAligned(&this->m_ReferenceGUID, &GUID_9b365890_165f_11d0_a195_0020afd156e4) )
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
    if ( (unsigned int)IsEqualGUIDAligned(Flink[1].Flink, &GUID_e5323777_f976_4f5b_9b55_b94699c46e44) )
    {
      v4 = (PVOID *)(v7 + 3);
      v2->m_profileGUID = GUID_e5323777_f976_4f5b_9b55_b94699c46e44;
      break;
    }
    if ( !v4 )
    {
      if ( (unsigned int)IsEqualGUIDAligned(v6, &GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca) )
      {
        v4 = (PVOID *)(v7 + 3);
        v2->m_profileGUID = GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca;
      }
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
0x18003c10c  push    rbx
0x18003c10e  push    rbp
0x18003c10f  push    rsi
0x18003c110  push    rdi
0x18003c111  push    r14
0x18003c113  push    r15
0x18003c115  sub     rsp, 48h
0x18003c119  mov     r9, rcx
0x18003c11c  lea     rdx, _GUID_9b365890_165f_11d0_a195_0020afd156e4
0x18003c123  add     rcx, 1ACh
0x18003c12a  call    IsEqualGUIDAligned
0x18003c12f  xor     esi, esi
0x18003c131  lea     r15, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x18003c138  lea     rbp, WPP_RECORDER_INITIALIZED
0x18003c13f  mov     r14d, 1
0x18003c145  test    eax, eax
0x18003c147  jnz     loc_18003C2B3
0x18003c14d  xorps   xmm0, xmm0
0x18003c150  mov     [rsp+78h+KeyHandle], rsi
0x18003c158  lea     r10, [r9+158h]
0x18003c15f  mov     edi, esi
0x18003c161  mov     r8, [r10]
0x18003c164  movups  xmmword ptr [rsp+78h+ValueName.Length], xmm0
0x18003c169  cmp     r8, r10
0x18003c16c  jz      short loc_18003C1C4
0x18003c16e  mov     rcx, [r8+10h]
0x18003c172  lea     rdx, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44
0x18003c179  call    IsEqualGUIDAligned
0x18003c17e  test    eax, eax
0x18003c180  jnz     short loc_18003C1B0
0x18003c182  test    rdi, rdi
0x18003c185  jnz     short loc_18003C1AB
0x18003c187  lea     rdx, _GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca
0x18003c18e  call    IsEqualGUIDAligned
0x18003c193  test    eax, eax
0x18003c195  jz      short loc_18003C1AB
0x18003c197  movups  xmm0, xmmword ptr cs:_GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca.Data1
0x18003c19e  lea     rdi, [r8+18h]
0x18003c1a2  movdqu  xmmword ptr [r9+1C8h], xmm0
0x18003c1ab  mov     r8, [r8]
0x18003c1ae  jmp     short loc_18003C169
0x18003c1b0  movups  xmm0, xmmword ptr cs:_GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data1
0x18003c1b7  lea     rdi, [r8+18h]
0x18003c1bb  movdqu  xmmword ptr [r9+1C8h], xmm0
0x18003c1c4  test    rdi, rdi
0x18003c1c7  jnz     short loc_18003C1ED
0x18003c1c9  mov     ebx, 0C00000BBh
0x18003c1ce  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18003c1d5  jz      loc_18003C317
0x18003c1db  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c1e2  lea     r9d, [rdi+31h]
0x18003c1e6  mov     dl, 2
0x18003c1e8  jmp     loc_18003C2D3
0x18003c1ed  lea     r8, [rsp+78h+ValueName]; struct _UNICODE_STRING *
0x18003c1f2  mov     rcx, r9; this
0x18003c1f5  lea     rdx, [rsp+78h+KeyHandle]; void **
0x18003c1fd  call    ?BuildKeyAndValueName@CKsFilterFactory@@QEAAJPEAPEAXPEAU_UNICODE_STRING@@@Z; CKsFilterFactory::BuildKeyAndValueName(void * *,_UNICODE_STRING *)
0x18003c202  mov     ebx, eax
0x18003c204  test    eax, eax
0x18003c206  jns     short loc_18003C23E
0x18003c208  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18003c20f  jz      loc_18003C317
0x18003c215  mov     r9d, 32h ; '2'
0x18003c21b  mov     dword ptr [rsp+78h+DataSize], eax
0x18003c21f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c226  mov     r8d, r14d
0x18003c229  mov     dl, 2
0x18003c22b  mov     [rsp+78h+Data], r15
0x18003c230  mov     rcx, [rcx+40h]
0x18003c234  call    WPP_RECORDER_SF_D
0x18003c239  jmp     loc_18003C2E4
0x18003c23e  movzx   eax, word ptr [rdi]
0x18003c241  lea     rdx, [rsp+78h+ValueName]; ValueName
0x18003c246  mov     rcx, [rsp+78h+KeyHandle]; KeyHandle
0x18003c24e  add     eax, 2
0x18003c251  mov     dword ptr [rsp+78h+DataSize], eax; DataSize
0x18003c255  mov     r9d, r14d; Type
0x18003c258  mov     rax, [rdi+8]
0x18003c25c  xor     r8d, r8d; TitleIndex
0x18003c25f  mov     [rsp+78h+Data], rax; Data
0x18003c264  call    cs:__imp_ZwSetValueKey
0x18003c26b  nop     dword ptr [rax+rax+00h]
0x18003c270  mov     rcx, [rsp+78h+KeyHandle]; Handle
0x18003c278  mov     ebx, eax
0x18003c27a  call    cs:__imp_ZwClose
0x18003c281  nop     dword ptr [rax+rax+00h]
0x18003c286  lea     rcx, [rsp+78h+ValueName]; UnicodeString
0x18003c28b  call    cs:__imp_RtlFreeUnicodeString
0x18003c292  nop     dword ptr [rax+rax+00h]
0x18003c297  test    ebx, ebx
0x18003c299  jns     short loc_18003C2E4
0x18003c29b  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18003c2a2  jz      short loc_18003C317
0x18003c2a4  mov     r9d, 33h ; '3'
0x18003c2aa  mov     dword ptr [rsp+78h+DataSize], ebx
0x18003c2ae  jmp     loc_18003C21F
0x18003c2b3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18003c2ba  mov     ebx, esi
0x18003c2bc  jz      short loc_18003C317
0x18003c2be  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c2c5  cmp     [rcx+48h], si
0x18003c2c9  jz      short loc_18003C2E4
0x18003c2cb  mov     r9d, 34h ; '4'
0x18003c2d1  mov     dl, 5
0x18003c2d3  mov     rcx, [rcx+40h]
0x18003c2d7  mov     r8d, r14d
0x18003c2da  mov     [rsp+78h+Data], r15
0x18003c2df  call    WPP_RECORDER_SF_
0x18003c2e4  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18003c2eb  jz      short loc_18003C317
0x18003c2ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c2f4  cmp     [rcx+48h], si
0x18003c2f8  jz      short loc_18003C317
0x18003c2fa  mov     rcx, [rcx+40h]
0x18003c2fe  mov     r9d, 35h ; '5'
0x18003c304  mov     dword ptr [rsp+78h+DataSize], ebx
0x18003c308  mov     r8d, r14d
0x18003c30b  mov     dl, 5
0x18003c30d  mov     [rsp+78h+Data], r15
0x18003c312  call    WPP_RECORDER_SF_D
0x18003c317  mov     eax, ebx
0x18003c319  add     rsp, 48h
0x18003c31d  pop     r15
0x18003c31f  pop     r14
0x18003c321  pop     rdi
0x18003c322  pop     rsi
0x18003c323  pop     rbp
0x18003c324  pop     rbx
0x18003c325  retn
```
