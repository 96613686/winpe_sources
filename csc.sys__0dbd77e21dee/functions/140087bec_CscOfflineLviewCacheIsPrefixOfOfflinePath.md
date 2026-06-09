# CscOfflineLviewCacheIsPrefixOfOfflinePath

- ea: `0x140087bec`
- end: `0x140087e8c`
- name: `CscOfflineLviewCacheIsPrefixOfOfflinePath`
- size: `672`
- prototype: `__int64 __usercall@<rax>(PERESOURCE Resource@<rcx>, PCUNICODE_STRING String1@<rdx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14001406c`

## callees

- `0x14000f8b0`
- `0x1400169d4`
- `0x1400179f8`
- `0x140021030`
- `0x140022138`
- `0x14002f010`
- `0x14002f440`
- `0x140053278`
- `0x140087bec`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140087cbf`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140087cbf`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140087cf5`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140087d2f`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140087cf5`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140087d2f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140087dae`
- `ntoskrnl!ExReleaseResourceLite` at `0x140087dae`

## pseudocode

```c
__int64 __fastcall CscOfflineLviewCacheIsPrefixOfOfflinePath(
        PERESOURCE Resource,
        PCUNICODE_STRING String1,
        char a3,
        char a4,
        _BYTE *a5,
        __int64 a6)
{
  _BYTE *v6; // r14
  struct _LIST_ENTRY *v7; // rdi
  char v8; // si
  char v11; // bl
  int v12; // edx
  int v13; // r8d
  char v14; // r12
  PERESOURCE v15; // r13
  struct _LIST_ENTRY *i; // rbp
  const UNICODE_STRING *v17; // r14
  __int64 result; // rax
  int v20; // [rsp+44h] [rbp-C4h] BYREF
  __int64 v21; // [rsp+48h] [rbp-C0h]
  PERESOURCE Resourcea; // [rsp+50h] [rbp-B8h]
  struct _LIST_ENTRY *v23; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A8h]
  _BYTE v25[80]; // [rsp+70h] [rbp-98h] BYREF

  v6 = a5;
  v7 = 0;
  v8 = 0;
  Resourcea = Resource;
  v21 = (__int64)a5;
  v24 = a6;
  v11 = 1;
  v23 = 0;
  v20 = 0;
  if ( a4 )
  {
    if ( (int)CscRegistryGetValueAsULong(14, &v20) < 0 )
    {
      v14 = 11;
      goto LABEL_30;
    }
    if ( !v20 )
    {
      v14 = 15;
      goto LABEL_30;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids);
  }
  v14 = 0;
  ExAcquireResourceSharedLite(Resource, 1u);
  v15 = Resource + 1;
  for ( i = Resource[1].SystemResourcesList.Flink; i != (struct _LIST_ENTRY *)v15; i = i->Flink )
  {
    v7 = i - 1;
    v17 = (const UNICODE_STRING *)&i[10];
    v23 = i - 1;
    if ( RtlPrefixUnicodeString(v17, String1, 1u)
      && (String1->Length == v17->Length || String1->Buffer[(unsigned __int64)v17->Length >> 1] == 92)
      || !a3
      && RtlPrefixUnicodeString(String1, (PCUNICODE_STRING)&i[10], 1u)
      && (v17->Length == String1->Length
       || *((_WORD *)&i[10].Blink->Flink + ((unsigned __int64)String1->Length >> 1)) == 92) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_ZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          (unsigned int)WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids,
          (_DWORD)String1,
          (__int64)&i[10]);
      v8 = 1;
      _InterlockedAdd((volatile signed __int32 *)&v7->Flink + 1, 1u);
      break;
    }
  }
  ExReleaseResourceLite(Resourcea);
  if ( v8 )
  {
    memset(v25, 0, sizeof(v25));
    if ( (int)CscStoreQueryInformationEntryEx(v7[2].Flink, 0, (unsigned int)v25, 0, 0, 0, 0) >= 0 )
      v11 = v25[4] & 1;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v7->Flink + 1, 0xFFFFFFFF) == 1 )
      CscOfflineLviewCachepDeleteListEntry((__int64 *)&v23);
  }
  v6 = (_BYTE *)v21;
LABEL_30:
  result = v24;
  *v6 = v8;
  *(_BYTE *)result = v11;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 0x20) != 0 )
    {
      LOBYTE(v12) = v11 != 0 ? 89 : 78;
      return WPP_SF_ZccD(WPP_GLOBAL_Control->AttachedDevice, v12, v13, (_DWORD)String1, v8 != 0 ? 89 : 78, v12, v14);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140087bec  mov     [rsp+arg_10], rbx
0x140087bf1  push    rbp
0x140087bf2  push    rsi
0x140087bf3  push    rdi
0x140087bf4  push    r12
0x140087bf6  push    r13
0x140087bf8  push    r14
0x140087bfa  push    r15
0x140087bfc  sub     rsp, 0D0h
0x140087c03  mov     rax, cs:__security_cookie
0x140087c0a  xor     rax, rsp
0x140087c0d  mov     [rsp+108h+var_48], rax
0x140087c15  mov     r14, [rsp+108h+arg_20]
0x140087c1d  lea     r12, WPP_GLOBAL_Control
0x140087c24  mov     rax, [rsp+108h+arg_28]
0x140087c2c  xor     edi, edi
0x140087c2e  xor     sil, sil
0x140087c31  mov     [rsp+108h+var_C8], r8b
0x140087c36  mov     [rsp+108h+Resource], rcx
0x140087c3b  mov     r15, rdx
0x140087c3e  mov     [rsp+108h+var_C0], r14
0x140087c43  mov     rbp, rcx
0x140087c46  mov     [rsp+108h+var_A8], rax
0x140087c4b  mov     ebx, 1
0x140087c50  mov     [rsp+108h+var_B0], rdi
0x140087c55  mov     [rsp+108h+var_C4], edi
0x140087c59  test    r9b, r9b
0x140087c5c  jz      short loc_140087CB7
0x140087c5e  lea     rdx, [rsp+108h+var_C4]
0x140087c63  lea     ecx, [rbx+0Dh]
0x140087c66  call    CscRegistryGetValueAsULong
0x140087c6b  test    eax, eax
0x140087c6d  jns     short loc_140087C81
0x140087c6f  mov     r12d, 40Bh
0x140087c75  lea     r13, WPP_GLOBAL_Control
0x140087c7c  jmp     loc_140087E17
0x140087c81  cmp     [rsp+108h+var_C4], edi
0x140087c85  jnz     short loc_140087C8F
0x140087c87  mov     r12d, 40Fh
0x140087c8d  jmp     short loc_140087C75
0x140087c8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140087c96  cmp     rcx, r12
0x140087c99  jz      short loc_140087CB7
0x140087c9b  mov     eax, [rcx+2Ch]
0x140087c9e  test    al, 20h
0x140087ca0  jz      short loc_140087CB7
0x140087ca2  mov     rcx, [rcx+18h]
0x140087ca6  lea     r8, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids
0x140087cad  mov     edx, 13h
0x140087cb2  call    WPP_SF_
0x140087cb7  xor     r12d, r12d
0x140087cba  mov     dl, bl; Wait
0x140087cbc  mov     rcx, rbp; Resource
0x140087cbf  call    cs:__imp_ExAcquireResourceSharedLite
0x140087cc6  nop     dword ptr [rax+rax+00h]
0x140087ccb  lea     r13, [rbp+68h]
0x140087ccf  mov     rbp, [r13+0]
0x140087cd3  cmp     rbp, r13
0x140087cd6  jz      loc_140087DA2
0x140087cdc  lea     rdi, [rbp-10h]
0x140087ce0  mov     r8b, bl; CaseInSensitive
0x140087ce3  lea     r14, [rdi+0B0h]
0x140087cea  mov     [rsp+108h+var_B0], rdi
0x140087cef  mov     rcx, r14; String1
0x140087cf2  mov     rdx, r15; String2
0x140087cf5  call    cs:__imp_RtlPrefixUnicodeString
0x140087cfc  nop     dword ptr [rax+rax+00h]
0x140087d01  test    al, al
0x140087d03  jz      short loc_140087D1F
0x140087d05  movzx   eax, word ptr [r14]
0x140087d09  cmp     [r15], ax
0x140087d0d  jz      short loc_140087D62
0x140087d0f  mov     ecx, eax
0x140087d11  mov     rax, [r15+8]
0x140087d15  shr     rcx, 1
0x140087d18  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x140087d1d  jz      short loc_140087D62
0x140087d1f  cmp     [rsp+108h+var_C8], sil
0x140087d24  jnz     short loc_140087D59
0x140087d26  mov     r8b, bl; CaseInSensitive
0x140087d29  mov     rdx, r14; String2
0x140087d2c  mov     rcx, r15; String1
0x140087d2f  call    cs:__imp_RtlPrefixUnicodeString
0x140087d36  nop     dword ptr [rax+rax+00h]
0x140087d3b  test    al, al
0x140087d3d  jz      short loc_140087D59
0x140087d3f  movzx   eax, word ptr [r15]
0x140087d43  cmp     [r14], ax
0x140087d47  jz      short loc_140087D62
0x140087d49  mov     ecx, eax
0x140087d4b  mov     rax, [r14+8]
0x140087d4f  shr     rcx, 1
0x140087d52  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x140087d57  jz      short loc_140087D62
0x140087d59  mov     rbp, [rbp+0]
0x140087d5d  jmp     loc_140087CD3
0x140087d62  mov     rcx, cs:WPP_GLOBAL_Control
0x140087d69  lea     r13, WPP_GLOBAL_Control
0x140087d70  cmp     rcx, r13
0x140087d73  jz      short loc_140087D99
0x140087d75  mov     eax, [rcx+2Ch]
0x140087d78  test    al, 40h
0x140087d7a  jz      short loc_140087D99
0x140087d7c  mov     rcx, [rcx+18h]
0x140087d80  lea     r8, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids
0x140087d87  mov     edx, 14h
0x140087d8c  mov     [rsp+108h+var_E8], r14
0x140087d91  mov     r9, r15
0x140087d94  call    WPP_SF_ZZ
0x140087d99  mov     sil, bl
0x140087d9c  lock add [rdi+4], ebx
0x140087da0  jmp     short loc_140087DA9
0x140087da2  lea     r13, WPP_GLOBAL_Control
0x140087da9  mov     rcx, [rsp+108h+Resource]; Resource
0x140087dae  call    cs:__imp_ExReleaseResourceLite
0x140087db5  nop     dword ptr [rax+rax+00h]
0x140087dba  xor     ebp, ebp
0x140087dbc  test    sil, sil
0x140087dbf  jz      short loc_140087E12
0x140087dc1  xor     edx, edx; Val
0x140087dc3  lea     r8d, [rbp+50h]; Size
0x140087dc7  lea     rcx, [rsp+108h+var_98]; void *
0x140087dcc  call    memset
0x140087dd1  mov     rcx, [rdi+20h]
0x140087dd5  lea     r8, [rsp+108h+var_98]
0x140087dda  mov     [rsp+108h+var_D8], rbp
0x140087ddf  xor     r9d, r9d
0x140087de2  mov     [rsp+108h+var_E0], rbp
0x140087de7  xor     edx, edx
0x140087de9  mov     [rsp+108h+var_E8], rbp
0x140087dee  call    CscStoreQueryInformationEntryEx
0x140087df3  test    eax, eax
0x140087df5  js      short loc_140087DFB
0x140087df7  and     bl, [rsp+108h+var_94]
0x140087dfb  or      eax, 0FFFFFFFFh
0x140087dfe  lock xadd [rdi+4], eax
0x140087e03  cmp     eax, 1
0x140087e06  jnz     short loc_140087E12
0x140087e08  lea     rcx, [rsp+108h+var_B0]
0x140087e0d  call    CscOfflineLviewCachepDeleteListEntry
0x140087e12  mov     r14, [rsp+108h+var_C0]
0x140087e17  mov     rax, [rsp+108h+var_A8]
0x140087e1c  mov     [r14], sil
0x140087e1f  mov     [rax], bl
0x140087e21  mov     rcx, cs:WPP_GLOBAL_Control
0x140087e28  cmp     rcx, r13
0x140087e2b  jz      short loc_140087E60
0x140087e2d  mov     eax, [rcx+2Ch]
0x140087e30  test    al, 20h
0x140087e32  jz      short loc_140087E60
0x140087e34  mov     rcx, [rcx+18h]
0x140087e38  neg     bl
0x140087e3a  mov     dword ptr [rsp+108h+var_D8], r12d
0x140087e3f  mov     r9, r15
0x140087e42  sbb     dl, dl
0x140087e44  and     dl, 0Bh
0x140087e47  add     dl, 4Eh ; 'N'
0x140087e4a  neg     sil
0x140087e4d  mov     byte ptr [rsp+108h+var_E0], dl
0x140087e51  sbb     al, al
0x140087e53  and     al, 0Bh
0x140087e55  add     al, 4Eh ; 'N'
0x140087e57  mov     byte ptr [rsp+108h+var_E8], al
0x140087e5b  call    WPP_SF_ZccD
0x140087e60  mov     rcx, [rsp+108h+var_48]
0x140087e68  xor     rcx, rsp; StackCookie
0x140087e6b  call    __security_check_cookie
0x140087e70  mov     rbx, [rsp+108h+arg_10]
0x140087e78  add     rsp, 0D0h
0x140087e7f  pop     r15
0x140087e81  pop     r14
0x140087e83  pop     r13
0x140087e85  pop     r12
0x140087e87  pop     rdi
0x140087e88  pop     rsi
0x140087e89  pop     rbp
0x140087e8a  retn
```
