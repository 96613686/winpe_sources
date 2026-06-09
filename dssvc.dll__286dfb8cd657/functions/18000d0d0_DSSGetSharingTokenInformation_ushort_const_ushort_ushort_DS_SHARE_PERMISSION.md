# DSSGetSharingTokenInformation(ushort const *,ushort * *,ushort * *,_DS_SHARE_PERMISSION *)

- ea: `0x18000d0d0`
- end: `0x18000d215`
- name: `?DSSGetSharingTokenInformation@@YAJPEBGPEAPEAG1PEAW4_DS_SHARE_PERMISSION@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(unsigned __int16 *, PVOID *, PVOID *, enum _DS_SHARE_PERMISSION *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800075e0`

## callees

- `0x180006f78`
- `0x18000be3c`
- `0x18000bf80`
- `0x18000c6d8`
- `0x18000d0d0`
- `0x18000da68`
- `0x18000f120`
- `0x18001abbc`

## string_xrefs

- `0x18000d119`: `Failed to get sharing information for token: %s. hr=0x%x`
- `0x18000d12f`: `DSSGetSharingTokenInformation`

## pseudocode

```c
__int64 __fastcall DSSGetSharingTokenInformation(
        unsigned __int16 *a1,
        PVOID *a2,
        PVOID *a3,
        enum _DS_SHARE_PERMISSION *a4)
{
  int AuthorizedSharingToken; // ebx
  DSLogger *v9; // rax
  PVOID v10; // rcx
  utl::_RefCountBase *v12; // rdi
  unsigned __int16 *v13; // rax
  const unsigned __int16 **v14; // r8
  unsigned __int16 *v15; // rax
  const unsigned __int16 **v16; // r8
  PVOID P; // [rsp+30h] [rbp-20h] BYREF
  PVOID v18; // [rsp+38h] [rbp-18h] BYREF
  utl::_RefCountBase *v19[2]; // [rsp+40h] [rbp-10h]

  *(_OWORD *)v19 = 0;
  v18 = 0;
  P = 0;
  if ( !dword_18002B2D0 )
  {
    AuthorizedSharingToken = -1055719422;
LABEL_3:
    v9 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                       a1,
                       a2,
                       a3,
                       a4);
    DSLogger::LogError(
      v9,
      L"DSSGetSharingTokenInformation",
      0x27Au,
      L"Failed to get sharing information for token: %s. hr=0x%x",
      a1,
      AuthorizedSharingToken);
    v10 = P;
    goto LABEL_4;
  }
  AuthorizedSharingToken = GetAuthorizedSharingToken(a1);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_3;
  v12 = v19[0];
  if ( !*((_QWORD *)v19[0] + 19) )
  {
    AuthorizedSharingToken = -1055719420;
    goto LABEL_3;
  }
  v13 = (unsigned __int16 *)tlx::replace<unsigned short,&void tlx::_delete_array<unsigned short>(unsigned short *)>(&v18);
  AuthorizedSharingToken = DSUtils::AssignStringForRpc(*((DSUtils **)v12 + 19), v13, v14);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_3;
  v15 = (unsigned __int16 *)tlx::replace<unsigned short,&void tlx::_delete_array<unsigned short>(unsigned short *)>(&P);
  AuthorizedSharingToken = DSUtils::AssignStringForRpc(*((DSUtils **)v12 + 4), v15, v16);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_3;
  v10 = 0;
  *a2 = v18;
  *a3 = P;
  v18 = 0;
  P = 0;
  *(_DWORD *)a4 = *((_DWORD *)v12 + 30);
LABEL_4:
  if ( v19[1] )
  {
    utl::_RefCountBase::_DecStrong(v19[1]);
    v10 = P;
  }
  if ( v10 )
    Common::GlobalHeap::Free(v10);
  if ( v18 )
    Common::GlobalHeap::Free(v18);
  return (unsigned int)AuthorizedSharingToken;
}

```

## disassembly

```asm
0x18000d0d0  push    rbp
0x18000d0d2  push    rbx
0x18000d0d3  push    rsi
0x18000d0d4  push    rdi
0x18000d0d5  push    r12
0x18000d0d7  push    r14
0x18000d0d9  push    r15
0x18000d0db  mov     rbp, rsp
0x18000d0de  sub     rsp, 50h
0x18000d0e2  cmp     cs:dword_18002B2D0, 0
0x18000d0e9  xorps   xmm0, xmm0
0x18000d0ec  movdqu  xmmword ptr [rbp+var_10], xmm0
0x18000d0f1  mov     r14, r9
0x18000d0f4  mov     [rbp+var_18], 0
0x18000d0fc  mov     r15, r8
0x18000d0ff  mov     [rbp+P], 0
0x18000d107  mov     r12, rdx
0x18000d10a  mov     rsi, rcx
0x18000d10d  jnz     short loc_18000D180
0x18000d10f  mov     ebx, 0C1130002h
0x18000d114  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000d119  lea     r9, aFailedToGetSha; "Failed to get sharing information for t"...
0x18000d120  mov     [rsp+50h+var_28], ebx
0x18000d124  mov     r8d, 27Ah; unsigned int
0x18000d12a  mov     [rsp+50h+var_30], rsi
0x18000d12f  lea     rdx, aDssgetsharingt; "DSSGetSharingTokenInformation"
0x18000d136  mov     rcx, rax; this
0x18000d139  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000d13e  mov     rcx, [rbp+P]
0x18000d142  mov     rax, [rbp+var_10+8]
0x18000d146  test    rax, rax
0x18000d149  jz      short loc_18000D157
0x18000d14b  mov     rcx, rax; this
0x18000d14e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18000d153  mov     rcx, [rbp+P]; P
0x18000d157  test    rcx, rcx
0x18000d15a  jz      short loc_18000D161
0x18000d15c  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000d161  mov     rcx, [rbp+var_18]; P
0x18000d165  test    rcx, rcx
0x18000d168  jz      short loc_18000D16F
0x18000d16a  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000d16f  mov     eax, ebx
0x18000d171  add     rsp, 50h
0x18000d175  pop     r15
0x18000d177  pop     r14
0x18000d179  pop     r12
0x18000d17b  pop     rdi
0x18000d17c  pop     rsi
0x18000d17d  pop     rbx
0x18000d17e  pop     rbp
0x18000d17f  retn
0x18000d180  lea     r8, [rbp+var_10]
0x18000d184  mov     edx, 1
0x18000d189  call    GetAuthorizedSharingToken
0x18000d18e  mov     ebx, eax
0x18000d190  test    eax, eax
0x18000d192  js      short loc_18000D114
0x18000d194  mov     rdi, [rbp+var_10]
0x18000d198  cmp     qword ptr [rdi+98h], 0
0x18000d1a0  jnz     short loc_18000D1AC
0x18000d1a2  mov     ebx, 0C1130004h
0x18000d1a7  jmp     loc_18000D114
0x18000d1ac  lea     rcx, [rbp+var_18]
0x18000d1b0  call    ??$replace@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@tlx@@YAPEAPEAGAEAV?$auto_array_ptr@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@0@@Z; tlx::replace<ushort,&tlx::_delete_array<ushort>(ushort *)>(tlx::auto_array_ptr<ushort,&tlx::_delete_array<ushort>(ushort *)> &)
0x18000d1b5  mov     rcx, [rdi+98h]; this
0x18000d1bc  mov     rdx, rax; unsigned __int16 *
0x18000d1bf  call    ?AssignStringForRpc@DSUtils@@YAJPEBGPEAPEBG@Z; DSUtils::AssignStringForRpc(ushort const *,ushort const * *)
0x18000d1c4  mov     ebx, eax
0x18000d1c6  test    eax, eax
0x18000d1c8  js      loc_18000D114
0x18000d1ce  lea     rcx, [rbp+P]
0x18000d1d2  call    ??$replace@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@tlx@@YAPEAPEAGAEAV?$auto_array_ptr@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@0@@Z; tlx::replace<ushort,&tlx::_delete_array<ushort>(ushort *)>(tlx::auto_array_ptr<ushort,&tlx::_delete_array<ushort>(ushort *)> &)
0x18000d1d7  mov     rcx, [rdi+20h]; this
0x18000d1db  mov     rdx, rax; unsigned __int16 *
0x18000d1de  call    ?AssignStringForRpc@DSUtils@@YAJPEBGPEAPEBG@Z; DSUtils::AssignStringForRpc(ushort const *,ushort const * *)
0x18000d1e3  mov     ebx, eax
0x18000d1e5  test    eax, eax
0x18000d1e7  js      loc_18000D114
0x18000d1ed  mov     rax, [rbp+var_18]
0x18000d1f1  xor     ecx, ecx
0x18000d1f3  mov     [r12], rax
0x18000d1f7  mov     rax, [rbp+P]
0x18000d1fb  mov     [r15], rax
0x18000d1fe  mov     [rbp+var_18], 0
0x18000d206  mov     [rbp+P], rcx
0x18000d20a  mov     eax, [rdi+78h]
0x18000d20d  mov     [r14], eax
0x18000d210  jmp     loc_18000D142
```
