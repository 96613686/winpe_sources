# CAssociationContext::IsAssociated(void *)

- ea: `0x1800337e8`
- end: `0x180033981`
- name: `?IsAssociated@CAssociationContext@@IEAAJPEAX@Z`
- size: `409`
- prototype: `__int64 __fastcall(CAssociationContext *__hidden this, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180055614`
- `0x180055e2c`

## callees

- `0x180019d00`
- `0x18001a268`
- `0x180033470`
- `0x1800337e8`
- `0x180034f48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033926`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180033808`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180033913`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180033808`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180033913`

## pseudocode

```c
__int64 __fastcall CAssociationContext::IsAssociated(CAssociationContext *this, void *a2)
{
  int v2; // esi
  signed int LastError; // eax
  int ProviderFromAepId; // ebx
  int v6; // eax
  int v7; // edx
  int v8; // r8d
  int v9; // eax
  int v10; // edx
  int v11; // r8d
  char v12; // al
  int v13; // edx
  int v14; // r8d
  std::_Ref_count_base *v16[2]; // [rsp+40h] [rbp-38h] BYREF

  v2 = 0;
  *(_OWORD *)v16 = 0;
  if ( a2 )
  {
    if ( !SetThreadToken(0, a2) )
    {
      LastError = GetLastError();
      ProviderFromAepId = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return (unsigned int)ProviderFromAepId;
    }
    v2 = 1;
  }
  v6 = IsAepAssociatedShared(*((const unsigned __int16 **)this + 1), 0, (int *)this + 156, (int *)this + 155);
  ProviderFromAepId = v6;
  if ( v6 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_SqD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v7,
        v8,
        112,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        *((_QWORD *)this + 1),
        (char)this,
        v6);
  }
  else
  {
    v9 = IsAepAssociatedShared(
           *((const unsigned __int16 **)this + 1),
           *((const unsigned __int16 **)this + 2),
           (int *)this + 99,
           (int *)this + 157);
    ProviderFromAepId = v9;
    if ( v9 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v10,
          v11,
          113,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)this + 1),
          (char)this,
          v9);
    }
    else
    {
      ProviderFromAepId = DAS::ProviderManagement::ProviderManager::GetProviderFromAepId(
                            g_providerManager,
                            *((_QWORD *)this + 1),
                            v16);
      if ( ProviderFromAepId >= 0 )
        *((_DWORD *)this + 154) = *((_DWORD *)v16[0] + 15);
    }
  }
  if ( v2 && !SetThreadToken(0, 0) && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v12 = GetLastError();
    WPP_RECORDER_SF_SqD(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v13,
      v14,
      114,
      &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
      *((_QWORD *)this + 1),
      (char)this,
      v12);
  }
  if ( v16[1] )
    std::_Ref_count_base::_Decref(v16[1]);
  return (unsigned int)ProviderFromAepId;
}

```

## disassembly

```asm
0x1800337e8  push    rbx
0x1800337ea  push    rbp
0x1800337eb  push    rsi
0x1800337ec  push    rdi
0x1800337ed  push    r14
0x1800337ef  sub     rsp, 50h
0x1800337f3  xor     esi, esi
0x1800337f5  xorps   xmm0, xmm0
0x1800337f8  mov     rdi, rcx
0x1800337fb  movdqu  xmmword ptr [rsp+78h+var_38], xmm0
0x180033801  test    rdx, rdx
0x180033804  jz      short loc_180033835
0x180033806  xor     ecx, ecx; Thread
0x180033808  call    cs:__imp_SetThreadToken
0x18003380e  test    eax, eax
0x180033810  jnz     short loc_180033830
0x180033812  call    cs:__imp_GetLastError
0x180033818  mov     ebx, eax
0x18003381a  test    eax, eax
0x18003381c  jle     loc_180033974
0x180033822  movzx   ebx, ax
0x180033825  or      ebx, 80070000h
0x18003382b  jmp     loc_180033974
0x180033830  mov     esi, 1
0x180033835  mov     rcx, [rdi+8]; unsigned __int16 *
0x180033839  lea     r9, [rdi+26Ch]; int *
0x180033840  lea     r8, [rdi+270h]; int *
0x180033847  xor     edx, edx; unsigned __int16 *
0x180033849  call    ?IsAepAssociatedShared@@YAJPEBG0PEAH1@Z; IsAepAssociatedShared(ushort const *,ushort const *,int *,int *)
0x18003384e  lea     rbp, WPP_RECORDER_INITIALIZED
0x180033855  mov     ebx, eax
0x180033857  lea     r14, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x18003385e  test    eax, eax
0x180033860  jz      short loc_18003389E
0x180033862  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180033869  jz      loc_18003390B
0x18003386f  mov     rcx, [rdi+8]
0x180033873  mov     r9d, 70h ; 'p'; int
0x180033879  mov     dword ptr [rsp+78h+var_40], eax; char
0x18003387d  mov     qword ptr [rsp+78h+var_48], rdi; char
0x180033882  mov     [rsp+78h+var_50], rcx; __int64
0x180033887  mov     rcx, cs:WPP_GLOBAL_Control
0x18003388e  mov     [rsp+78h+MessageGuid], r14; MessageGuid
0x180033893  mov     rcx, [rcx+28h]; int
0x180033897  call    WPP_RECORDER_SF_SqD
0x18003389c  jmp     short loc_18003390B
0x18003389e  mov     rdx, [rdi+10h]; unsigned __int16 *
0x1800338a2  lea     r9, [rdi+274h]; int *
0x1800338a9  mov     rcx, [rdi+8]; unsigned __int16 *
0x1800338ad  lea     r8, [rdi+18Ch]; int *
0x1800338b4  call    ?IsAepAssociatedShared@@YAJPEBG0PEAH1@Z; IsAepAssociatedShared(ushort const *,ushort const *,int *,int *)
0x1800338b9  mov     ebx, eax
0x1800338bb  test    eax, eax
0x1800338bd  jz      short loc_1800338E2
0x1800338bf  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1800338c6  jz      short loc_18003390B
0x1800338c8  mov     dword ptr [rsp+78h+var_40], eax
0x1800338cc  mov     r9d, 71h ; 'q'
0x1800338d2  mov     rax, [rdi+8]
0x1800338d6  mov     qword ptr [rsp+78h+var_48], rdi
0x1800338db  mov     [rsp+78h+var_50], rax
0x1800338e0  jmp     short loc_180033887
0x1800338e2  mov     rdx, [rdi+8]
0x1800338e6  lea     r8, [rsp+78h+var_38]
0x1800338eb  mov     rcx, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x1800338f2  call    ?GetProviderFromAepId@ProviderManager@ProviderManagement@DAS@@QEAAJPEBGAEAV?$shared_ptr@VProviderContext@@@std@@@Z; DAS::ProviderManagement::ProviderManager::GetProviderFromAepId(ushort const *,std::shared_ptr<ProviderContext> &)
0x1800338f7  mov     ebx, eax
0x1800338f9  test    eax, eax
0x1800338fb  js      short loc_18003390B
0x1800338fd  mov     rax, [rsp+78h+var_38]
0x180033902  mov     ecx, [rax+3Ch]
0x180033905  mov     [rdi+268h], ecx
0x18003390b  test    esi, esi
0x18003390d  jz      short loc_180033965
0x18003390f  xor     edx, edx; Token
0x180033911  xor     ecx, ecx; Thread
0x180033913  call    cs:__imp_SetThreadToken
0x180033919  test    eax, eax
0x18003391b  jnz     short loc_180033965
0x18003391d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180033924  jz      short loc_180033965
0x180033926  call    cs:__imp_GetLastError
0x18003392c  test    eax, eax
0x18003392e  jle     short loc_180033938
0x180033930  movzx   eax, ax
0x180033933  or      eax, 80070000h
0x180033938  mov     rcx, cs:WPP_GLOBAL_Control
0x18003393f  mov     r9d, 72h ; 'r'; int
0x180033945  mov     dword ptr [rsp+78h+var_40], eax; char
0x180033949  mov     rax, [rdi+8]
0x18003394d  mov     qword ptr [rsp+78h+var_48], rdi; char
0x180033952  mov     rcx, [rcx+28h]; int
0x180033956  mov     [rsp+78h+var_50], rax; __int64
0x18003395b  mov     [rsp+78h+MessageGuid], r14; MessageGuid
0x180033960  call    WPP_RECORDER_SF_SqD
0x180033965  mov     rcx, [rsp+78h+var_38+8]; this
0x18003396a  test    rcx, rcx
0x18003396d  jz      short loc_180033974
0x18003396f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180033974  mov     eax, ebx
0x180033976  add     rsp, 50h
0x18003397a  pop     r14
0x18003397c  pop     rdi
0x18003397d  pop     rsi
0x18003397e  pop     rbp
0x18003397f  pop     rbx
0x180033980  retn
```
