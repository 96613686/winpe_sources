# CscOfflineLviewCacheSyncAndRemoveEntries

- ea: `0x140049150`
- end: `0x14004942c`
- name: `CscOfflineLviewCacheSyncAndRemoveEntries`
- size: `732`
- prototype: `__int64 __fastcall(PERESOURCE Resource, PCUNICODE_STRING String2)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140019f24`
- `0x14004de28`
- `0x140090740`

## callees

- `0x14001a624`
- `0x14001b884`
- `0x140049150`
- `0x140049434`
- `0x140053278`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400491e1`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400491e1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049341`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049341`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004918b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004918b`

## pseudocode

```c
void __fastcall CscOfflineLviewCacheSyncAndRemoveEntries(PERESOURCE Resource, PCUNICODE_STRING String2, char a3)
{
  bool v4; // di
  __int64 v5; // rsi
  PERESOURCE v8; // rax
  struct _LIST_ENTRY *Flink; // r15
  __int64 v10; // rbx
  __int16 v11; // dx
  bool v12; // zf
  _QWORD *v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rdx
  _QWORD *v16; // rcx
  _QWORD *v17; // rbx
  __int64 v18; // rdi
  _QWORD *v19; // rax
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  __int64 v22; // [rsp+30h] [rbp-20h] BYREF
  _QWORD *v23; // [rsp+38h] [rbp-18h] BYREF
  _QWORD **v24; // [rsp+40h] [rbp-10h]
  bool v25; // [rsp+90h] [rbp+40h]

  v24 = &v23;
  v4 = 0;
  v25 = 0;
  v5 = 0;
  v23 = &v23;
  ExAcquireResourceExclusiveLite(Resource, 1u);
  v8 = Resource + 1;
  Flink = Resource[1].SystemResourcesList.Flink;
  while ( Flink != (struct _LIST_ENTRY *)v8 )
  {
    v10 = (__int64)&Flink[-1];
    Flink = Flink->Flink;
    v22 = v10;
    if ( !String2 )
      goto LABEL_11;
    if ( *(_WORD *)(v10 + 176) > String2->Length )
      break;
    v12 = RtlPrefixUnicodeString((PCUNICODE_STRING)(v10 + 176), String2, 1u) == 0;
    v8 = Resource + 1;
    if ( v12 )
    {
      v4 = v25;
    }
    else
    {
      v11 = *(_WORD *)(v10 + 176);
      v12 = v11 == String2->Length;
      if ( v11 == String2->Length )
      {
LABEL_10:
        v4 = v12;
        v25 = v12;
LABEL_11:
        if ( !a3 )
          goto LABEL_16;
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 4));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            WPP_SF_qZ(
              WPP_GLOBAL_Control->AttachedDevice,
              22,
              (unsigned int)WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids,
              v10,
              v10 + 176);
          v5 = v10;
LABEL_16:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids, v10 + 176);
          }
          goto LABEL_19;
        }
        v5 = v10;
LABEL_19:
        v13 = (_QWORD *)(v10 + 16);
        v14 = *(_QWORD *)(v10 + 16);
        if ( *(_QWORD *)(v14 + 8) != v10 + 16 )
          goto LABEL_40;
        v15 = *(_QWORD **)(v10 + 24);
        if ( (_QWORD *)*v15 != v13 )
          goto LABEL_40;
        *v15 = v14;
        *(_QWORD *)(v14 + 8) = v15;
        *(_QWORD *)(v10 + 24) = v13;
        *v13 = v13;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 4), 0xFFFFFFFF) == 1 )
          CscOfflineLviewCachepDeleteListEntry(&v22);
        if ( v5 )
        {
          v16 = v24;
          if ( *v24 != &v23 )
            goto LABEL_40;
          *(_QWORD *)(v5 + 24) = v24;
          *(_QWORD *)(v5 + 16) = &v23;
          *v16 = v5 + 16;
          v24 = (_QWORD **)(v5 + 16);
        }
        v8 = Resource + 1;
        if ( v4 )
          break;
      }
      else
      {
        v4 = v25;
        v8 = Resource + 1;
        if ( String2->Buffer[(unsigned __int64)*(unsigned __int16 *)(v10 + 176) >> 1] == 92 )
        {
          v12 = v11 == String2->Length;
          goto LABEL_10;
        }
      }
    }
  }
  ExReleaseResourceLite(Resource);
  if ( a3 )
  {
    v17 = v23;
    if ( v23 != &v23 )
    {
      while ( 1 )
      {
        v18 = (__int64)(v17 - 2);
        v17 = (_QWORD *)*v17;
        v22 = v18;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids, v18 + 176);
        }
        CscOfflineLviewCachepSetIgnoreEntry(v18, 0, 0);
        v19 = (_QWORD *)(v18 + 16);
        v20 = *(_QWORD *)(v18 + 16);
        if ( *(_QWORD *)(v20 + 8) != v18 + 16 )
          break;
        v21 = *(_QWORD **)(v18 + 24);
        if ( (_QWORD *)*v21 != v19 )
          break;
        *v21 = v20;
        *(_QWORD *)(v20 + 8) = v21;
        *(_QWORD *)(v18 + 24) = v18 + 16;
        *v19 = v19;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v18 + 4), 0xFFFFFFFF) == 1 )
          CscOfflineLviewCachepDeleteListEntry(&v22);
        if ( v17 == &v23 )
          return;
      }
LABEL_40:
      __fastfail(3u);
    }
  }
}

```

## disassembly

```asm
0x140049150  mov     [rsp-38h+arg_8], rbx
0x140049155  push    rbp
0x140049156  push    rsi
0x140049157  push    rdi
0x140049158  push    r12
0x14004915a  push    r13
0x14004915c  push    r14
0x14004915e  push    r15
0x140049160  mov     rbp, rsp
0x140049163  sub     rsp, 50h
0x140049167  lea     rax, [rbp+var_18]
0x14004916b  mov     r14, rdx
0x14004916e  mov     [rbp+var_10], rax
0x140049172  xor     dil, dil
0x140049175  lea     rax, [rbp+var_18]
0x140049179  mov     [rbp+arg_0], dil
0x14004917d  xor     esi, esi
0x14004917f  mov     [rbp+var_18], rax
0x140049183  mov     dl, 1; Wait
0x140049185  mov     r12b, r8b
0x140049188  mov     r13, rcx
0x14004918b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140049192  nop     dword ptr [rax+rax+00h]
0x140049197  lea     rax, [r13+68h]
0x14004919b  mov     r15, [rax]
0x14004919e  lea     r9, WPP_GLOBAL_Control
0x1400491a5  jmp     short loc_1400491AB
0x1400491a7  mov     dil, [rbp+arg_0]
0x1400491ab  cmp     r15, rax
0x1400491ae  jz      loc_14004933E
0x1400491b4  lea     rbx, [r15-10h]
0x1400491b8  mov     r15, [r15]
0x1400491bb  mov     [rbp+var_20], rbx
0x1400491bf  test    r14, r14
0x1400491c2  jz      short loc_14004923B
0x1400491c4  movzx   eax, word ptr [r14]
0x1400491c8  lea     rdi, [rbx+0B0h]
0x1400491cf  cmp     [rdi], ax
0x1400491d2  ja      loc_14004933E
0x1400491d8  mov     r8b, 1; CaseInSensitive
0x1400491db  mov     rdx, r14; String2
0x1400491de  mov     rcx, rdi; String1
0x1400491e1  call    cs:__imp_RtlPrefixUnicodeString
0x1400491e8  nop     dword ptr [rax+rax+00h]
0x1400491ed  test    al, al
0x1400491ef  lea     r9, WPP_GLOBAL_Control
0x1400491f6  lea     rax, [r13+68h]
0x1400491fa  jz      short loc_1400491A7
0x1400491fc  movzx   r8d, word ptr [r14]
0x140049200  movzx   edx, word ptr [rdi]
0x140049203  cmp     dx, r8w
0x140049207  jz      short loc_14004922C
0x140049209  mov     rax, [r14+8]
0x14004920d  lea     r9, WPP_GLOBAL_Control
0x140049214  mov     dil, [rbp+arg_0]
0x140049218  mov     ecx, edx
0x14004921a  shr     rcx, 1
0x14004921d  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x140049222  lea     rax, [r13+68h]
0x140049226  jnz     short loc_1400491AB
0x140049228  cmp     dx, r8w
0x14004922c  setz    dil
0x140049230  lea     r9, WPP_GLOBAL_Control
0x140049237  mov     [rbp+arg_0], dil
0x14004923b  test    r12b, r12b
0x14004923e  jz      short loc_14004928D
0x140049240  lock inc dword ptr [rbx+4]
0x140049244  mov     rcx, cs:WPP_GLOBAL_Control
0x14004924b  cmp     rcx, r9
0x14004924e  jz      loc_14004941D
0x140049254  mov     eax, [rcx+2Ch]
0x140049257  test    al, 40h
0x140049259  jz      loc_140049415
0x14004925f  mov     rcx, [rcx+18h]
0x140049263  lea     rax, [rbx+0B0h]
0x14004926a  mov     edx, 16h
0x14004926f  mov     [rsp+50h+var_30], rax
0x140049274  mov     r9, rbx
0x140049277  lea     r8, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids
0x14004927e  call    WPP_SF_qZ
0x140049283  lea     r9, WPP_GLOBAL_Control
0x14004928a  mov     rsi, rbx
0x14004928d  mov     rcx, cs:WPP_GLOBAL_Control
0x140049294  cmp     rcx, r9
0x140049297  jz      short loc_1400492BC
0x140049299  mov     eax, [rcx+2Ch]
0x14004929c  test    al, 40h
0x14004929e  jz      short loc_1400492BC
0x1400492a0  mov     rcx, [rcx+18h]
0x1400492a4  lea     r9, [rbx+0B0h]
0x1400492ab  mov     edx, 17h
0x1400492b0  lea     r8, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids
0x1400492b7  call    WPP_SF_Z
0x1400492bc  lea     rax, [rbx+10h]
0x1400492c0  mov     rcx, [rax]
0x1400492c3  cmp     [rcx+8], rax
0x1400492c7  jnz     loc_140049425
0x1400492cd  mov     rdx, [rbx+18h]
0x1400492d1  cmp     [rdx], rax
0x1400492d4  jnz     loc_140049425
0x1400492da  mov     [rdx], rcx
0x1400492dd  mov     [rcx+8], rdx
0x1400492e1  mov     [rbx+18h], rax
0x1400492e5  mov     [rax], rax
0x1400492e8  or      eax, 0FFFFFFFFh
0x1400492eb  lock xadd [rbx+4], eax
0x1400492f0  cmp     eax, 1
0x1400492f3  jnz     short loc_1400492FE
0x1400492f5  lea     rcx, [rbp+var_20]
0x1400492f9  call    CscOfflineLviewCachepDeleteListEntry
0x1400492fe  test    rsi, rsi
0x140049301  jz      short loc_14004932A
0x140049303  mov     rcx, [rbp+var_10]
0x140049307  lea     rax, [rbp+var_18]
0x14004930b  cmp     [rcx], rax
0x14004930e  jnz     loc_140049425
0x140049314  lea     rax, [rsi+10h]
0x140049318  mov     [rax+8], rcx
0x14004931c  lea     rdx, [rbp+var_18]
0x140049320  mov     [rax], rdx
0x140049323  mov     [rcx], rax
0x140049326  mov     [rbp+var_10], rax
0x14004932a  lea     rax, [r13+68h]
0x14004932e  lea     r9, WPP_GLOBAL_Control
0x140049335  test    dil, dil
0x140049338  jz      loc_1400491AB
0x14004933e  mov     rcx, r13; Resource
0x140049341  call    cs:__imp_ExReleaseResourceLite
0x140049348  nop     dword ptr [rax+rax+00h]
0x14004934d  test    r12b, r12b
0x140049350  jz      loc_1400493FC
0x140049356  mov     rbx, [rbp+var_18]
0x14004935a  lea     rax, [rbp+var_18]
0x14004935e  cmp     rbx, rax
0x140049361  jz      loc_1400493FC
0x140049367  lea     rsi, WPP_GLOBAL_Control
0x14004936e  lea     rdi, [rbx-10h]
0x140049372  mov     rbx, [rbx]
0x140049375  mov     [rbp+var_20], rdi
0x140049379  mov     rcx, cs:WPP_GLOBAL_Control
0x140049380  cmp     rcx, rsi
0x140049383  jz      short loc_1400493A8
0x140049385  mov     eax, [rcx+2Ch]
0x140049388  test    al, 40h
0x14004938a  jz      short loc_1400493A8
0x14004938c  mov     rcx, [rcx+18h]
0x140049390  lea     r9, [rdi+0B0h]
0x140049397  mov     edx, 18h
0x14004939c  lea     r8, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids
0x1400493a3  call    WPP_SF_Z
0x1400493a8  xor     r8d, r8d
0x1400493ab  xor     edx, edx
0x1400493ad  mov     rcx, rdi
0x1400493b0  call    CscOfflineLviewCachepSetIgnoreEntry
0x1400493b5  lea     rax, [rdi+10h]
0x1400493b9  mov     rdx, [rax]
0x1400493bc  cmp     [rdx+8], rax
0x1400493c0  jnz     short loc_140049425
0x1400493c2  mov     rcx, [rax+8]
0x1400493c6  cmp     [rcx], rax
0x1400493c9  jnz     short loc_140049425
0x1400493cb  mov     [rcx], rdx
0x1400493ce  mov     [rdx+8], rcx
0x1400493d2  mov     [rax+8], rax
0x1400493d6  mov     [rax], rax
0x1400493d9  or      eax, 0FFFFFFFFh
0x1400493dc  lock xadd [rdi+4], eax
0x1400493e1  cmp     eax, 1
0x1400493e4  jnz     short loc_1400493EF
0x1400493e6  lea     rcx, [rbp+var_20]
0x1400493ea  call    CscOfflineLviewCachepDeleteListEntry
0x1400493ef  lea     rax, [rbp+var_18]
0x1400493f3  cmp     rbx, rax
0x1400493f6  jnz     loc_14004936E
0x1400493fc  mov     rbx, [rsp+50h+arg_8]
0x140049404  add     rsp, 50h
0x140049408  pop     r15
0x14004940a  pop     r14
0x14004940c  pop     r13
0x14004940e  pop     r12
0x140049410  pop     rdi
0x140049411  pop     rsi
0x140049412  pop     rbp
0x140049413  retn
0x140049415  mov     rsi, rbx
0x140049418  jmp     loc_14004928D
0x14004941d  mov     rsi, rbx
0x140049420  jmp     loc_1400492BC
0x140049425  mov     ecx, 3
0x14004942a  int     29h; Win8: RtlFailFast(ecx)
```
