# CscOfflineLviewCacheAddEntryEx

- ea: `0x1400709b0`
- end: `0x140070c65`
- name: `CscOfflineLviewCacheAddEntryEx`
- size: `693`
- prototype: `__int64 __usercall@<rax>(PERESOURCE Resource@<rcx>, __int64)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x140049b5c`
- `0x14004de28`
- `0x140062b70`
- `0x14006f360`
- `0x140075770`

## callees

- `0x14001a69c`
- `0x14001fb20`
- `0x1400530fc`
- `0x140053278`
- `0x1400709b0`
- `0x14008d304`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140070a17`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140070a17`
- `ntoskrnl!ExReleaseResourceLite` at `0x140070a8c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140070b06`
- `ntoskrnl!ExReleaseResourceLite` at `0x140070a8c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140070b06`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140070aa0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140070aa0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140070a5e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140070a5e`

## pseudocode

```c
__int64 __fastcall CscOfflineLviewCacheAddEntryEx(
        PERESOURCE Resource,
        UNICODE_STRING *a2,
        __int64 a3,
        char a4,
        __int64 *a5)
{
  __int64 v5; // rbx
  _QWORD *v7; // rcx
  int v10; // ebp
  char v11; // dl
  char v12; // si
  signed int v13; // edi
  char v14; // r14
  PERESOURCE v15; // rdi
  _QWORD *i; // rsi
  const UNICODE_STRING *v17; // rcx
  int ListEntry; // eax
  _QWORD *v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // rdx
  _QWORD *v23; // rcx
  _QWORD *v24; // [rsp+38h] [rbp-50h]
  __int64 v25[9]; // [rsp+40h] [rbp-48h] BYREF

  v5 = 0;
  v25[0] = 0;
  v7 = 0;
  v24 = 0;
  v10 = (int)a2;
  if ( a3 )
  {
    ExAcquireResourceSharedLite(Resource, 1u);
    v14 = 1;
    v15 = Resource + 1;
    while ( 1 )
    {
      for ( i = &v15->SystemResourcesList.Flink->Flink; ; i = (_QWORD *)*i )
      {
        if ( i == (_QWORD *)v15 )
          goto LABEL_11;
        v17 = (const UNICODE_STRING *)(i + 20);
        if ( v17->Length > a2->Length )
          goto LABEL_11;
        if ( v17->Length == a2->Length && RtlEqualUnicodeString(v17, a2, 1u) )
          break;
      }
      v7 = i - 2;
      v24 = i - 2;
      if ( i != (_QWORD *)16 )
      {
        v13 = 0;
        if ( !a4 )
        {
          CscOfflineLviewCachepClearIgnoreFlag();
          _InterlockedAnd((volatile signed __int32 *)i - 2, 0xFFFFFFFD);
          v10 = (int)a2;
          v12 = 0;
          goto LABEL_15;
        }
        v10 = (int)a2;
        v12 = 0;
        goto LABEL_16;
      }
LABEL_11:
      if ( !v14 )
        break;
      ExReleaseResourceLite(Resource);
      v14 = 0;
      ExAcquireResourceExclusiveLite(Resource, 1u);
    }
    v10 = (int)a2;
    ListEntry = CscOfflineLviewCachepCreateListEntry(a3, (const void **)a2, v25, a4);
    v5 = v25[0];
    v13 = ListEntry;
    if ( ListEntry < 0 )
    {
      v12 = -89;
      goto LABEL_35;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v25[0] + 4));
    v20 = (_QWORD *)i[1];
    if ( (_QWORD *)*v20 != i )
      goto LABEL_43;
    *(_QWORD *)(v5 + 16) = i;
    *(_QWORD *)(v5 + 24) = v20;
    *v20 = v5 + 16;
    i[1] = v5 + 16;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_ZD(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        (unsigned int)WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids,
        (_DWORD)a2,
        *(_BYTE *)(v5 + 12));
    v12 = 0;
LABEL_35:
    if ( v5 && v13 < 0 )
    {
      v21 = (_QWORD *)(v5 + 16);
      v22 = *(_QWORD *)(v5 + 16);
      if ( *(_QWORD *)(v22 + 8) == v5 + 16 )
      {
        v23 = *(_QWORD **)(v5 + 24);
        if ( (_QWORD *)*v23 == v21 )
        {
          *v23 = v22;
          *(_QWORD *)(v22 + 8) = v23;
          *(_QWORD *)(v5 + 24) = v5 + 16;
          *v21 = v21;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 4), 0xFFFFFFFF) == 1 )
            CscOfflineLviewCachepDeleteListEntry(v25);
          v5 = 0;
          goto LABEL_15;
        }
      }
LABEL_43:
      __fastfail(3u);
    }
LABEL_15:
    v7 = v24;
LABEL_16:
    v11 = 1;
  }
  else
  {
    v11 = 0;
    v12 = 91;
    v13 = a5 != 0 ? 0xC000000D : 0;
  }
  if ( a5 && v13 >= 0 )
  {
    if ( v7 )
      v5 = (__int64)v7;
    *a5 = v5;
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 4));
  }
  if ( v11 )
    ExReleaseResourceLite(Resource);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_ZDD(
      WPP_GLOBAL_Control->AttachedDevice,
      18,
      (unsigned int)WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids,
      v10,
      v13,
      v12);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400709b0  mov     [rsp+arg_0], rbx
0x1400709b5  mov     [rsp+String2], rdx
0x1400709ba  push    rbp
0x1400709bb  push    rsi
0x1400709bc  push    rdi
0x1400709bd  push    r12
0x1400709bf  push    r13
0x1400709c1  push    r14
0x1400709c3  push    r15
0x1400709c5  sub     rsp, 50h
0x1400709c9  xor     ebx, ebx
0x1400709cb  lea     r14, WPP_GLOBAL_Control
0x1400709d2  mov     r15, rcx
0x1400709d5  mov     [rsp+88h+var_48], rbx
0x1400709da  xor     ecx, ecx
0x1400709dc  mov     r12b, r9b
0x1400709df  mov     [rsp+88h+var_50], rcx
0x1400709e4  mov     r13, r8
0x1400709e7  mov     rbp, rdx
0x1400709ea  test    r8, r8
0x1400709ed  jnz     short loc_140070A0E
0x1400709ef  mov     rax, [rsp+88h+arg_20]
0x1400709f7  xor     dl, dl
0x1400709f9  neg     rax
0x1400709fc  mov     esi, 35Bh
0x140070a01  sbb     edi, edi
0x140070a03  and     edi, 0C000000Dh
0x140070a09  jmp     loc_140070AE0
0x140070a0e  mov     [rsp+88h+var_58], ecx
0x140070a12  mov     dl, 1; Wait
0x140070a14  mov     rcx, r15; Resource
0x140070a17  call    cs:__imp_ExAcquireResourceSharedLite
0x140070a1e  nop     dword ptr [rax+rax+00h]
0x140070a23  mov     r14b, 1
0x140070a26  lea     rdi, [r15+68h]
0x140070a2a  mov     [rsp+88h+arg_10], r14b
0x140070a32  mov     rsi, [rdi]
0x140070a35  cmp     rsi, rdi
0x140070a38  jz      short loc_140070A80
0x140070a3a  mov     r9, [rsp+88h+String2]
0x140070a42  lea     rbp, [rsi-10h]
0x140070a46  lea     rcx, [rbp+0B0h]; String1
0x140070a4d  movzx   eax, word ptr [r9]
0x140070a51  cmp     [rcx], ax
0x140070a54  ja      short loc_140070A80
0x140070a56  jnz     short loc_140070A6E
0x140070a58  mov     r8b, 1; CaseInSensitive
0x140070a5b  mov     rdx, r9; String2
0x140070a5e  call    cs:__imp_RtlEqualUnicodeString
0x140070a65  nop     dword ptr [rax+rax+00h]
0x140070a6a  test    al, al
0x140070a6c  jnz     short loc_140070A73
0x140070a6e  mov     rsi, [rsi]
0x140070a71  jmp     short loc_140070A35
0x140070a73  mov     rcx, rbp
0x140070a76  mov     [rsp+88h+var_50], rcx
0x140070a7b  test    rbp, rbp
0x140070a7e  jnz     short loc_140070AAE
0x140070a80  test    r14b, r14b
0x140070a83  jz      loc_140070B60
0x140070a89  mov     rcx, r15; Resource
0x140070a8c  call    cs:__imp_ExReleaseResourceLite
0x140070a93  nop     dword ptr [rax+rax+00h]
0x140070a98  mov     dl, 1; Wait
0x140070a9a  mov     rcx, r15; Resource
0x140070a9d  xor     r14b, r14b
0x140070aa0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140070aa7  nop     dword ptr [rax+rax+00h]
0x140070aac  jmp     short loc_140070A32
0x140070aae  xor     edi, edi
0x140070ab0  test    r12b, r12b
0x140070ab3  jnz     loc_140070C48
0x140070ab9  call    CscOfflineLviewCachepClearIgnoreFlag
0x140070abe  lock and dword ptr [rbp+8], 0FFFFFFFDh
0x140070ac3  mov     rbp, [rsp+88h+String2]
0x140070acb  lea     r14, WPP_GLOBAL_Control
0x140070ad2  mov     esi, ebx
0x140070ad4  mov     rcx, [rsp+88h+var_50]
0x140070ad9  mov     dl, [rsp+88h+arg_10]
0x140070ae0  mov     rax, [rsp+88h+arg_20]
0x140070ae8  test    rax, rax
0x140070aeb  jz      short loc_140070AFF
0x140070aed  test    edi, edi
0x140070aef  js      short loc_140070AFF
0x140070af1  test    rcx, rcx
0x140070af4  cmovnz  rbx, rcx
0x140070af8  mov     [rax], rbx
0x140070afb  lock inc dword ptr [rbx+4]
0x140070aff  test    dl, dl
0x140070b01  jz      short loc_140070B12
0x140070b03  mov     rcx, r15; Resource
0x140070b06  call    cs:__imp_ExReleaseResourceLite
0x140070b0d  nop     dword ptr [rax+rax+00h]
0x140070b12  mov     rcx, cs:WPP_GLOBAL_Control
0x140070b19  cmp     rcx, r14
0x140070b1c  jz      short loc_140070B45
0x140070b1e  mov     eax, [rcx+2Ch]
0x140070b21  test    al, 20h
0x140070b23  jz      short loc_140070B45
0x140070b25  mov     rcx, [rcx+18h]
0x140070b29  lea     r8, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids
0x140070b30  mov     edx, 12h
0x140070b35  mov     [rsp+88h+var_60], esi
0x140070b39  mov     r9, rbp
0x140070b3c  mov     [rsp+88h+var_68], edi
0x140070b40  call    WPP_SF_ZDD
0x140070b45  mov     rbx, [rsp+88h+arg_0]
0x140070b4d  mov     eax, edi
0x140070b4f  add     rsp, 50h
0x140070b53  pop     r15
0x140070b55  pop     r14
0x140070b57  pop     r13
0x140070b59  pop     r12
0x140070b5b  pop     rdi
0x140070b5c  pop     rsi
0x140070b5d  pop     rbp
0x140070b5e  retn
0x140070b60  mov     rbp, [rsp+88h+String2]
0x140070b68  lea     r8, [rsp+88h+var_48]
0x140070b6d  mov     rdx, rbp
0x140070b70  mov     r9b, r12b
0x140070b73  mov     rcx, r13
0x140070b76  call    CscOfflineLviewCachepCreateListEntry
0x140070b7b  mov     rbx, [rsp+88h+var_48]
0x140070b80  mov     edi, eax
0x140070b82  test    eax, eax
0x140070b84  jns     short loc_140070B94
0x140070b86  mov     esi, 3A7h
0x140070b8b  lea     r14, WPP_GLOBAL_Control
0x140070b92  jmp     short loc_140070BF5
0x140070b94  lock inc dword ptr [rbx+4]
0x140070b98  mov     rcx, [rsi+8]
0x140070b9c  cmp     [rcx], rsi
0x140070b9f  jnz     loc_140070C5E
0x140070ba5  lea     rax, [rbx+10h]
0x140070ba9  mov     [rax], rsi
0x140070bac  mov     [rax+8], rcx
0x140070bb0  mov     [rcx], rax
0x140070bb3  mov     [rsi+8], rax
0x140070bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140070bbe  lea     r14, WPP_GLOBAL_Control
0x140070bc5  cmp     rcx, r14
0x140070bc8  jz      short loc_140070BF1
0x140070bca  mov     eax, [rcx+2Ch]
0x140070bcd  test    al, 20h
0x140070bcf  jz      short loc_140070BF1
0x140070bd1  movzx   eax, byte ptr [rbx+0Ch]
0x140070bd5  lea     r8, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids
0x140070bdc  mov     rcx, [rcx+18h]
0x140070be0  mov     edx, 11h
0x140070be5  mov     r9, rbp
0x140070be8  mov     [rsp+88h+var_68], eax
0x140070bec  call    WPP_SF_ZD
0x140070bf1  mov     esi, [rsp+88h+var_58]
0x140070bf5  test    rbx, rbx
0x140070bf8  jz      loc_140070AD4
0x140070bfe  test    edi, edi
0x140070c00  jns     loc_140070AD4
0x140070c06  lea     rax, [rbx+10h]
0x140070c0a  mov     rdx, [rax]
0x140070c0d  cmp     [rdx+8], rax
0x140070c11  jnz     short loc_140070C5E
0x140070c13  mov     rcx, [rax+8]
0x140070c17  cmp     [rcx], rax
0x140070c1a  jnz     short loc_140070C5E
0x140070c1c  mov     [rcx], rdx
0x140070c1f  mov     [rdx+8], rcx
0x140070c23  mov     [rax+8], rax
0x140070c27  mov     [rax], rax
0x140070c2a  or      eax, 0FFFFFFFFh
0x140070c2d  lock xadd [rbx+4], eax
0x140070c32  cmp     eax, 1
0x140070c35  jnz     short loc_140070C41
0x140070c37  lea     rcx, [rsp+88h+var_48]
0x140070c3c  call    CscOfflineLviewCachepDeleteListEntry
0x140070c41  xor     ebx, ebx
0x140070c43  jmp     loc_140070AD4
0x140070c48  mov     rbp, [rsp+88h+String2]
0x140070c50  lea     r14, WPP_GLOBAL_Control
0x140070c57  mov     esi, ebx
0x140070c59  jmp     loc_140070AD9
0x140070c5e  mov     ecx, 3
0x140070c63  int     29h; Win8: RtlFailFast(ecx)
```
