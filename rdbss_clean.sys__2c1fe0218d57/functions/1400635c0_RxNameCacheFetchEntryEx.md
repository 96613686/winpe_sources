# RxNameCacheFetchEntryEx

- ea: `0x1400635c0`
- end: `0x140063986`
- name: `RxNameCacheFetchEntryEx`
- size: `966`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140014e40`
- `0x140025d00`
- `0x1400635c0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x1400636f3`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400636f3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140063668`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140063668`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140063741`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400637ac`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140063741`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400637ac`
- `ntoskrnl!RtlHashUnicodeString` at `0x140063645`
- `ntoskrnl!RtlHashUnicodeString` at `0x140063645`

## pseudocode

```c
_QWORD *__fastcall RxNameCacheFetchEntryEx(__int64 a1, const UNICODE_STRING *a2, _QWORD *a3, __int64 a4)
{
  __int64 v7; // rbx
  _QWORD *v8; // r14
  int v9; // ebp
  __int64 v10; // r15
  _QWORD *v11; // rbx
  _QWORD *v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // rcx
  _QWORD *v15; // rax
  _QWORD *v16; // rdx
  __int64 v17; // rdx
  _QWORD *v18; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rcx
  void (__fastcall *v22)(_QWORD, _QWORD *); // rax
  __int64 v23; // rdx
  _QWORD *v24; // rax
  _QWORD *v25; // rcx
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  _QWORD *v29; // rax
  ULONG HashValue; // [rsp+80h] [rbp+8h] BYREF
  PCUNICODE_STRING String1; // [rsp+88h] [rbp+10h]
  _QWORD *v32; // [rsp+90h] [rbp+18h]
  unsigned __int64 v33; // [rsp+98h] [rbp+20h]

  v32 = a3;
  String1 = a2;
  v33 = MEMORY[0xFFFFF78000000008];
  HashValue = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 16, &WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids, a2);
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 104));
  RtlHashUnicodeString(a2, 1u, 0, &HashValue);
  v7 = HashValue % *(_DWORD *)(a1 + 168);
  ExAcquirePushLockExclusiveEx(a1 + 48, 0);
  if ( !a4 || (v8 = *(_QWORD **)(a4 + 96), v20 = (_QWORD *)(a4 + 96), v8 == (_QWORD *)(a4 + 96)) )
  {
    v8 = *(_QWORD **)(*(_QWORD *)(a1 + 176) + 16 * v7);
  }
  else
  {
    if ( (_QWORD *)v8[1] != v20 )
      goto LABEL_17;
    v21 = *(_QWORD **)(a4 + 104);
    if ( (_QWORD *)*v21 != v20 )
      goto LABEL_17;
    *v21 = v8;
    v8[1] = v21;
    *(_QWORD *)(a4 + 104) = a4 + 96;
    *v20 = v20;
  }
  v9 = 0;
  v10 = 16 * v7;
  while ( 1 )
  {
    do
    {
      if ( v8 == (_QWORD *)(v10 + *(_QWORD *)(a1 + 176)) )
      {
        v11 = 0;
        ExReleasePushLockExclusiveEx(a1 + 48, 0);
        return v11;
      }
      v11 = v8 - 12;
      v12 = v8;
      v8 = (_QWORD *)*v8;
    }
    while ( *(_WORD *)v11 == 0xEBAA );
    if ( *((_DWORD *)v11 + 28) == HashValue
      && String1->Length == *((_WORD *)v11 + 40)
      && (!String1->Length || RtlEqualUnicodeString(String1, (PCUNICODE_STRING)v11 + 5, *((_BYTE *)v11 + 128)))
      && (!v32 || v11[15] == *v32) )
    {
      break;
    }
    if ( v33 >= v11[7] )
    {
      v22 = *(void (__fastcall **)(_QWORD, _QWORD *))(a1 + 136);
      if ( v22 )
      {
        v22(*(_QWORD *)(a1 + 144), v11);
        v11[5] = 0;
      }
      v23 = v11[8];
      v24 = v11 + 8;
      if ( *(_QWORD **)(v23 + 8) != v11 + 8 )
        goto LABEL_17;
      v25 = (_QWORD *)v11[9];
      if ( (_QWORD *)*v25 != v24 )
        goto LABEL_17;
      *v25 = v23;
      *(_QWORD *)(v23 + 8) = v25;
      v26 = (_QWORD *)(a1 + 72);
      v27 = *(_QWORD *)(a1 + 72);
      if ( *(_QWORD *)(v27 + 8) != a1 + 72 )
        goto LABEL_17;
      *v24 = v27;
      v11[9] = v26;
      *(_QWORD *)(v27 + 8) = v24;
      *v26 = v24;
      v28 = *v12;
      if ( *(_QWORD **)(*v12 + 8LL) != v12 )
        goto LABEL_17;
      v29 = (_QWORD *)v12[1];
      if ( (_QWORD *)*v29 != v12 )
        goto LABEL_17;
      *v29 = v28;
      *(_QWORD *)(v28 + 8) = v29;
      v12[1] = v12;
      *v12 = v12;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 17, &WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids, v11 + 10);
      }
    }
    ++v9;
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 108));
  if ( !v9 )
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 112));
  if ( a4 )
  {
    v13 = *v12;
    if ( *(_QWORD **)(*v12 + 8LL) != v12 )
      goto LABEL_17;
    *(_QWORD *)(a4 + 96) = v13;
    *(_QWORD *)(a4 + 104) = v12;
    *(_QWORD *)(v13 + 8) = a4 + 96;
    *v12 = a4 + 96;
  }
  v14 = v11[8];
  v15 = v11 + 8;
  if ( *(_QWORD **)(v14 + 8) != v11 + 8
    || (v16 = (_QWORD *)v11[9], (_QWORD *)*v16 != v15)
    || (*v16 = v14, *(_QWORD *)(v14 + 8) = v16,
                    v11[9] = v11 + 8,
                    *v15 = v15,
                    v17 = *v12,
                    *(_QWORD **)(*v12 + 8LL) != v12)
    || (v18 = (_QWORD *)v12[1], (_QWORD *)*v18 != v12) )
  {
LABEL_17:
    __fastfail(3u);
  }
  *v18 = v17;
  *(_QWORD *)(v17 + 8) = v18;
  v12[1] = v12;
  *v12 = v12;
  ExReleasePushLockExclusiveEx(a1 + 48, 0);
  if ( v11
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 18, &WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids, v11 + 10);
  }
  return v11;
}

```

## disassembly

```asm
0x1400635c0  mov     [rsp+arg_10], r8
0x1400635c5  mov     [rsp+String1], rdx
0x1400635ca  push    rbx
0x1400635cb  push    rsi
0x1400635cc  push    r12
0x1400635ce  push    r13
0x1400635d0  sub     rsp, 58h
0x1400635d4  mov     rax, 0FFFFF78000000008h
0x1400635de  mov     r13, r9
0x1400635e1  mov     rbx, rdx
0x1400635e4  mov     rsi, rcx
0x1400635e7  mov     rax, [rax]
0x1400635ea  mov     [rsp+78h+arg_18], rax
0x1400635f2  mov     [rsp+78h+HashValue], 0
0x1400635fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140063604  lea     rax, WPP_GLOBAL_Control
0x14006360b  cmp     rcx, rax
0x14006360e  jz      short loc_14006361D
0x140063610  test    dword ptr [rcx+2Ch], 800h
0x140063617  jnz     loc_14006395F
0x14006361d  mov     [rsp+78h+var_28], rbp
0x140063622  mov     [rsp+78h+var_30], rdi
0x140063627  mov     [rsp+78h+var_38], r14
0x14006362c  mov     [rsp+78h+var_40], r15
0x140063631  lock inc dword ptr [rsi+68h]
0x140063635  lea     r9, [rsp+78h+HashValue]; HashValue
0x14006363d  xor     r8d, r8d; HashAlgorithm
0x140063640  mov     dl, 1; CaseInSensitive
0x140063642  mov     rcx, rbx; String
0x140063645  call    cs:__imp_RtlHashUnicodeString
0x14006364c  nop     dword ptr [rax+rax+00h]
0x140063651  mov     eax, [rsp+78h+HashValue]
0x140063658  lea     rcx, [rsi+30h]
0x14006365c  xor     edx, edx
0x14006365e  div     dword ptr [rsi+0A8h]
0x140063664  mov     ebx, edx
0x140063666  xor     edx, edx
0x140063668  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006366f  nop     dword ptr [rax+rax+00h]
0x140063674  test    r13, r13
0x140063677  jnz     loc_140063845
0x14006367d  mov     rax, [rsi+0B0h]
0x140063684  mov     rcx, rbx
0x140063687  add     rcx, rcx
0x14006368a  mov     r14, [rax+rcx*8]
0x14006368e  mov     r15, rbx
0x140063691  xor     ebp, ebp
0x140063693  shl     r15, 4
0x140063697  mov     edx, 0EBAAh
0x14006369c  mov     rcx, [rsi+0B0h]
0x1400636a3  add     rcx, r15
0x1400636a6  cmp     r14, rcx
0x1400636a9  jz      loc_140063739
0x1400636af  lea     rbx, [r14-60h]
0x1400636b3  mov     rdi, r14
0x1400636b6  mov     r14, [r14]
0x1400636b9  cmp     [rbx], dx
0x1400636bc  jz      short loc_14006369C
0x1400636be  mov     eax, [rsp+78h+HashValue]
0x1400636c5  cmp     [rbx+70h], eax
0x1400636c8  jnz     loc_1400637E0
0x1400636ce  mov     rcx, [rsp+78h+String1]; String1
0x1400636d6  lea     rdx, [rbx+50h]; String2
0x1400636da  movzx   eax, word ptr [rcx]
0x1400636dd  cmp     ax, [rdx]
0x1400636e0  jnz     loc_1400637E0
0x1400636e6  test    ax, ax
0x1400636e9  jz      short loc_140063707
0x1400636eb  movzx   r8d, byte ptr [rbx+80h]; CaseInSensitive
0x1400636f3  call    cs:__imp_RtlEqualUnicodeString
0x1400636fa  nop     dword ptr [rax+rax+00h]
0x1400636ff  test    al, al
0x140063701  jz      loc_1400637E0
0x140063707  mov     rax, [rsp+78h+arg_10]
0x14006370f  test    rax, rax
0x140063712  jnz     loc_140063836
0x140063718  lock inc dword ptr [rsi+6Ch]
0x14006371c  test    ebp, ebp
0x14006371e  jnz     short loc_140063724
0x140063720  lock inc dword ptr [rsi+70h]
0x140063724  test    r13, r13
0x140063727  jz      short loc_140063761
0x140063729  mov     rcx, [rdi]
0x14006372c  cmp     [rcx+8], rdi
0x140063730  jz      short loc_14006374F
0x140063732  mov     ecx, 3
0x140063737  int     29h; Win8: RtlFailFast(ecx)
0x140063739  xor     ebx, ebx
0x14006373b  lea     rcx, [rsi+30h]
0x14006373f  xor     edx, edx
0x140063741  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140063748  nop     dword ptr [rax+rax+00h]
0x14006374d  jmp     short loc_1400637BD
0x14006374f  lea     rax, [r13+60h]
0x140063753  mov     [rax], rcx
0x140063756  mov     [rax+8], rdi
0x14006375a  mov     [rcx+8], rax
0x14006375e  mov     [rdi], rax
0x140063761  mov     rcx, [rbx+40h]
0x140063765  lea     rax, [rbx+40h]
0x140063769  cmp     [rcx+8], rax
0x14006376d  jnz     short loc_140063732
0x14006376f  mov     rdx, [rax+8]
0x140063773  cmp     [rdx], rax
0x140063776  jnz     short loc_140063732
0x140063778  mov     [rdx], rcx
0x14006377b  mov     [rcx+8], rdx
0x14006377f  mov     [rax+8], rax
0x140063783  mov     [rax], rax
0x140063786  mov     rdx, [rdi]
0x140063789  cmp     [rdx+8], rdi
0x14006378d  jnz     short loc_140063732
0x14006378f  mov     rax, [rdi+8]
0x140063793  cmp     [rax], rdi
0x140063796  jnz     short loc_140063732
0x140063798  mov     [rax], rdx
0x14006379b  mov     [rdx+8], rax
0x14006379f  mov     [rdi+8], rdi
0x1400637a3  mov     [rdi], rdi
0x1400637a6  xor     edx, edx
0x1400637a8  lea     rcx, [rsi+30h]
0x1400637ac  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400637b3  nop     dword ptr [rax+rax+00h]
0x1400637b8  test    rbx, rbx
0x1400637bb  jnz     short loc_1400637F9
0x1400637bd  mov     r15, [rsp+78h+var_40]
0x1400637c2  mov     rax, rbx
0x1400637c5  mov     r14, [rsp+78h+var_38]
0x1400637ca  mov     rdi, [rsp+78h+var_30]
0x1400637cf  mov     rbp, [rsp+78h+var_28]
0x1400637d4  add     rsp, 58h
0x1400637d8  pop     r13
0x1400637da  pop     r12
0x1400637dc  pop     rsi
0x1400637dd  pop     rbx
0x1400637de  retn
0x1400637e0  mov     rax, [rsp+78h+arg_18]
0x1400637e8  cmp     rax, [rbx+38h]
0x1400637ec  jnb     loc_140063880
0x1400637f2  inc     ebp
0x1400637f4  jmp     loc_140063697
0x1400637f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140063800  lea     rax, WPP_GLOBAL_Control
0x140063807  cmp     rcx, rax
0x14006380a  jz      short loc_1400637BD
0x14006380c  test    dword ptr [rcx+2Ch], 800h
0x140063813  jz      short loc_1400637BD
0x140063815  cmp     byte ptr [rcx+29h], 4
0x140063819  jb      short loc_1400637BD
0x14006381b  mov     rcx, [rcx+18h]
0x14006381f  lea     r9, [rbx+50h]
0x140063823  mov     edx, 12h
0x140063828  lea     r8, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids
0x14006382f  call    WPP_SF_Z
0x140063834  jmp     short loc_1400637BD
0x140063836  mov     rax, [rax]
0x140063839  cmp     [rbx+78h], rax
0x14006383d  jz      loc_140063718
0x140063843  jmp     short loc_1400637E0
0x140063845  mov     r14, [r13+60h]
0x140063849  lea     rax, [r13+60h]
0x14006384d  cmp     r14, rax
0x140063850  jz      loc_14006367D
0x140063856  cmp     [r14+8], rax
0x14006385a  jnz     loc_140063732
0x140063860  mov     rcx, [rax+8]
0x140063864  cmp     [rcx], rax
0x140063867  jnz     loc_140063732
0x14006386d  mov     [rcx], r14
0x140063870  mov     [r14+8], rcx
0x140063874  mov     [rax+8], rax
0x140063878  mov     [rax], rax
0x14006387b  jmp     loc_14006368E
0x140063880  mov     rax, [rsi+88h]
0x140063887  test    rax, rax
0x14006388a  jz      short loc_1400638A3
0x14006388c  mov     rcx, [rsi+90h]
0x140063893  mov     rdx, rbx
0x140063896  call    _guard_dispatch_icall
0x14006389b  mov     qword ptr [rbx+28h], 0
0x1400638a3  mov     rdx, [rbx+40h]
0x1400638a7  lea     rax, [rbx+40h]
0x1400638ab  cmp     [rdx+8], rax
0x1400638af  jnz     loc_140063732
0x1400638b5  mov     rcx, [rbx+48h]
0x1400638b9  cmp     [rcx], rax
0x1400638bc  jnz     loc_140063732
0x1400638c2  mov     [rcx], rdx
0x1400638c5  mov     [rdx+8], rcx
0x1400638c9  lea     rcx, [rsi+48h]
0x1400638cd  mov     rdx, [rcx]
0x1400638d0  cmp     [rdx+8], rcx
0x1400638d4  jnz     loc_140063732
0x1400638da  mov     [rax], rdx
0x1400638dd  mov     [rax+8], rcx
0x1400638e1  mov     [rdx+8], rax
0x1400638e5  mov     rdx, rdi
0x1400638e8  mov     [rcx], rax
0x1400638eb  mov     rcx, [rdi]
0x1400638ee  cmp     [rcx+8], rdi
0x1400638f2  jnz     loc_140063732
0x1400638f8  mov     rax, [rdi+8]
0x1400638fc  cmp     [rax], rdx
0x1400638ff  jnz     loc_140063732
0x140063905  mov     [rax], rcx
0x140063908  mov     [rcx+8], rax
0x14006390c  mov     [rdi+8], rdx
0x140063910  mov     [rdi], rdx
0x140063913  mov     rcx, cs:WPP_GLOBAL_Control
0x14006391a  lea     rax, WPP_GLOBAL_Control
0x140063921  cmp     rcx, rax
0x140063924  jz      loc_1400637F2
0x14006392a  test    dword ptr [rcx+2Ch], 800h
0x140063931  jz      loc_1400637F2
0x140063937  cmp     byte ptr [rcx+29h], 4
0x14006393b  jb      loc_1400637F2
0x140063941  mov     rcx, [rcx+18h]
0x140063945  lea     r9, [rbx+50h]
0x140063949  mov     edx, 11h
0x14006394e  lea     r8, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids
0x140063955  call    WPP_SF_Z
0x14006395a  jmp     loc_1400637F2
0x14006395f  cmp     byte ptr [rcx+29h], 4
0x140063963  jb      loc_14006361D
0x140063969  mov     rcx, [rcx+18h]
0x14006396d  lea     r8, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids
0x140063974  mov     edx, 10h
0x140063979  mov     r9, rbx
0x14006397c  call    WPP_SF_Z
0x140063981  jmp     loc_14006361D
```
