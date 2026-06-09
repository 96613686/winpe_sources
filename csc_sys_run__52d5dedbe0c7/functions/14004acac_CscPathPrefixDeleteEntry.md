# CscPathPrefixDeleteEntry

- ea: `0x14004acac`
- end: `0x14004ae40`
- name: `CscPathPrefixDeleteEntry`
- size: `404`
- prototype: `__int64 __fastcall(PERESOURCE Resource)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14004c8b0`

## callees

- `0x140016a04`
- `0x14004acac`
- `0x14004ae48`
- `0x140053870`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14004ada0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ada0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004ad07`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004ad07`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004ad84`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004aded`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004ad84`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004aded`

## pseudocode

```c
__int64 __fastcall CscPathPrefixDeleteEntry(PERESOURCE Resource, char a2, __int64 a3)
{
  PERESOURCE p_Address; // rsi
  struct _ERESOURCE *v8; // rbx
  LIST_ENTRY SystemResourcesList; // xmm0
  __int128 v10; // xmm0
  struct _ERESOURCE *UserInList; // rax
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *Blink; // rcx
  struct _ERESOURCE *v14; // rsi
  LIST_ENTRY v15; // [rsp+20h] [rbp-28h] BYREF
  PVOID Entry[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( (a2 != 0) == (a3 != 0) )
    return 3221226528LL;
  v15.Blink = &v15;
  v15.Flink = &v15;
  Entry[1] = Entry;
  Entry[0] = Entry;
  ExAcquireResourceExclusiveLite(Resource, 1u);
  if ( a2 )
  {
    p_Address = Resource + 1;
    v8 = 0;
    SystemResourcesList = Resource[1].SystemResourcesList;
    Resource[1].SystemResourcesList.Blink = &Resource[1].SystemResourcesList;
    Resource[1].SystemResourcesList.Flink = &Resource[1].SystemResourcesList;
    v15 = SystemResourcesList;
    v10 = *(_OWORD *)&Resource[1].OwnerTable;
    *(_QWORD *)&Resource[1].ActiveCount = (char *)Resource + 120;
    Resource[1].OwnerTable = (POWNER_ENTRY)&Resource[1].OwnerTable;
    *(_OWORD *)Entry = v10;
  }
  else
  {
    UserInList = (struct _ERESOURCE *)CscPathPrefixpFindUserInList(Resource, a3);
    v8 = UserInList;
    if ( UserInList )
    {
      Flink = UserInList->SystemResourcesList.Flink;
      if ( (struct _ERESOURCE *)Flink->Blink != v8
        || (Blink = v8->SystemResourcesList.Blink, (struct _ERESOURCE *)Blink->Flink != v8) )
      {
        __fastfail(3u);
      }
      Blink->Flink = Flink;
      p_Address = (PERESOURCE)&v8->Address;
      Flink->Blink = Blink;
      v15 = *(LIST_ENTRY *)&v8->Address;
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)&Resource[1].Address, v8);
    }
    else
    {
      p_Address = (PERESOURCE)&v15;
    }
  }
  ExReleaseResourceLite(Resource);
  CscPathPrefixpDeletePrefixList(Resource, &v15, p_Address);
  v14 = (struct _ERESOURCE *)Entry[0];
  if ( Entry[0] != Entry )
  {
    while ( v14 != (struct _ERESOURCE *)&Resource[1].OwnerTable )
    {
      v8 = v14;
      v14 = (struct _ERESOURCE *)v14->SystemResourcesList.Flink;
      CscPathPrefixpDeletePrefixList(Resource, &v8->Address, 0);
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)&Resource[1].Address, v8);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_0447301b51063eaec2a18d83656e135e_Traceguids, v8);
  return 0;
}

```

## disassembly

```asm
0x14004acac  push    rbp
0x14004acae  push    rbx
0x14004acaf  push    rsi
0x14004acb0  push    rdi
0x14004acb1  push    r14
0x14004acb3  push    r15
0x14004acb5  mov     rbp, rsp
0x14004acb8  sub     rsp, 48h
0x14004acbc  xor     r9d, r9d
0x14004acbf  mov     rbx, r8
0x14004acc2  test    dl, dl
0x14004acc4  mov     sil, dl
0x14004acc7  mov     rdi, rcx
0x14004acca  setnz   r9b
0x14004acce  xor     eax, eax
0x14004acd0  test    r8, r8
0x14004acd3  setnz   al
0x14004acd6  cmp     r9d, eax
0x14004acd9  jnz     short loc_14004ACE5
0x14004acdb  mov     eax, 0C0000420h
0x14004ace0  jmp     loc_14004AE32
0x14004ace5  lea     rax, [rbp+var_28]
0x14004ace9  mov     dl, 1; Wait
0x14004aceb  mov     qword ptr [rbp+var_28+8], rax
0x14004acef  lea     rax, [rbp+var_28]
0x14004acf3  mov     qword ptr [rbp+var_28], rax
0x14004acf7  lea     rax, [rbp+Entry]
0x14004acfb  mov     [rbp+Entry+8], rax
0x14004acff  lea     rax, [rbp+Entry]
0x14004ad03  mov     [rbp+Entry], rax
0x14004ad07  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004ad0e  nop     dword ptr [rax+rax+00h]
0x14004ad13  test    sil, sil
0x14004ad16  jz      short loc_14004AD42
0x14004ad18  lea     rsi, [rdi+68h]
0x14004ad1c  xor     ebx, ebx
0x14004ad1e  movups  xmm0, xmmword ptr [rsi]
0x14004ad21  lea     rax, [rdi+78h]
0x14004ad25  mov     [rsi+8], rsi
0x14004ad29  mov     [rsi], rsi
0x14004ad2c  movdqu  [rbp+var_28], xmm0
0x14004ad31  movups  xmm0, xmmword ptr [rax]
0x14004ad34  mov     [rax+8], rax
0x14004ad38  mov     [rax], rax
0x14004ad3b  movdqu  xmmword ptr [rbp+Entry], xmm0
0x14004ad40  jmp     short loc_14004AD9D
0x14004ad42  mov     rdx, rbx
0x14004ad45  mov     rcx, rdi
0x14004ad48  call    CscPathPrefixpFindUserInList
0x14004ad4d  mov     rbx, rax
0x14004ad50  test    rax, rax
0x14004ad53  jz      short loc_14004AD99
0x14004ad55  mov     rax, [rax]
0x14004ad58  cmp     [rax+8], rbx
0x14004ad5c  jnz     short loc_14004AD92
0x14004ad5e  mov     rcx, [rbx+8]
0x14004ad62  cmp     [rcx], rbx
0x14004ad65  jnz     short loc_14004AD92
0x14004ad67  mov     [rcx], rax
0x14004ad6a  lea     rsi, [rbx+58h]
0x14004ad6e  mov     [rax+8], rcx
0x14004ad72  mov     rdx, rbx; Entry
0x14004ad75  movups  xmm0, xmmword ptr [rsi]
0x14004ad78  lea     rcx, [rdi+0C0h]; Lookaside
0x14004ad7f  movdqu  [rbp+var_28], xmm0
0x14004ad84  call    cs:__imp_ExFreeToPagedLookasideList
0x14004ad8b  nop     dword ptr [rax+rax+00h]
0x14004ad90  jmp     short loc_14004AD9D
0x14004ad92  mov     ecx, 3
0x14004ad97  int     29h; Win8: RtlFailFast(ecx)
0x14004ad99  lea     rsi, [rbp+var_28]
0x14004ad9d  mov     rcx, rdi; Resource
0x14004ada0  call    cs:__imp_ExReleaseResourceLite
0x14004ada7  nop     dword ptr [rax+rax+00h]
0x14004adac  mov     r8, rsi
0x14004adaf  lea     rdx, [rbp+var_28]
0x14004adb3  mov     rcx, rdi
0x14004adb6  call    CscPathPrefixpDeletePrefixList
0x14004adbb  mov     rsi, [rbp+Entry]
0x14004adbf  lea     rax, [rbp+Entry]
0x14004adc3  cmp     rsi, rax
0x14004adc6  jz      short loc_14004ADFE
0x14004adc8  lea     r14, [rdi+78h]
0x14004adcc  jmp     short loc_14004ADF9
0x14004adce  mov     rbx, rsi
0x14004add1  xor     r8d, r8d
0x14004add4  mov     rsi, [rsi]
0x14004add7  mov     rcx, rdi
0x14004adda  lea     rdx, [rbx+58h]
0x14004adde  call    CscPathPrefixpDeletePrefixList
0x14004ade3  mov     rdx, rbx; Entry
0x14004ade6  lea     rcx, [rdi+0C0h]; Lookaside
0x14004aded  call    cs:__imp_ExFreeToPagedLookasideList
0x14004adf4  nop     dword ptr [rax+rax+00h]
0x14004adf9  cmp     rsi, r14
0x14004adfc  jnz     short loc_14004ADCE
0x14004adfe  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ae05  lea     rax, WPP_GLOBAL_Control
0x14004ae0c  cmp     rcx, rax
0x14004ae0f  jz      short loc_14004AE30
0x14004ae11  mov     eax, [rcx+2Ch]
0x14004ae14  test    al, 40h
0x14004ae16  jz      short loc_14004AE30
0x14004ae18  mov     rcx, [rcx+18h]
0x14004ae1c  lea     r8, WPP_0447301b51063eaec2a18d83656e135e_Traceguids
0x14004ae23  mov     edx, 10h
0x14004ae28  mov     r9, rbx
0x14004ae2b  call    WPP_SF_q
0x14004ae30  xor     eax, eax
0x14004ae32  add     rsp, 48h
0x14004ae36  pop     r15
0x14004ae38  pop     r14
0x14004ae3a  pop     rdi
0x14004ae3b  pop     rsi
0x14004ae3c  pop     rbx
0x14004ae3d  pop     rbp
0x14004ae3e  retn
```
