# PackageEnroller::UnenrollById(_GUID const &,IEnrollEngine *)

- ea: `0x18002cd38`
- end: `0x18002ceee`
- name: `?UnenrollById@PackageEnroller@@SAXAEBU_GUID@@PEAUIEnrollEngine@@@Z`
- size: `438`
- prototype: `void __fastcall(const struct _GUID *, struct IEnrollEngine *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002cbf4`

## callees

- `0x180004d68`
- `0x180005bb8`
- `0x18000864c`
- `0x18001b388`
- `0x180020710`
- `0x18002cd38`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002cdbc`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002cdbc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002cd91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002cd91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce3e`

## string_xrefs

- `0x18002ceb5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002ce9f`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18002cedc`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PackageEnroller::UnenrollById(const struct _GUID *a1, struct IEnrollEngine *a2)
{
  int v4; // eax
  int v5; // ebx
  DWORD v6; // eax
  const char *v7; // r9
  char v8; // al
  const char *v9; // r9
  int v10; // eax
  const char *v11; // r9
  unsigned int v12; // eax
  int v13; // [rsp+20h] [rbp-30h]
  HANDLE hHandle[2]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v15; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v17; // [rsp+88h] [rbp+38h] BYREF
  int v18; // [rsp+90h] [rbp+40h] BYREF
  int v19; // [rsp+98h] [rbp+48h] BYREF

  hHandle[0] = 0;
  v4 = (*(__int64 (__fastcall **)(struct IEnrollEngine *, const struct _GUID *, HANDLE *))(*(_QWORD *)a2 + 72LL))(
         a2,
         a1,
         hHandle);
  if ( v4 == 1 )
    v4 = -2147418113;
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x145,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
      (const char *)(unsigned int)v4,
      v13);
  v5 = 0;
  while ( 1 )
  {
    v6 = WaitForSingleObjectEx(hHandle[0], 0x2BF20u, 0);
    if ( v6 == 258 )
    {
      v8 = 0;
    }
    else
    {
      if ( v6 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB0F,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v7);
      v8 = 1;
    }
    if ( !v8 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x14D,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
        v7);
    if ( !ResetEvent(hHandle[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA06,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v9);
    v19 = 0;
    v18 = 0;
    v17 = 0;
    v15 = (__int128)*a1;
    v10 = (*(__int64 (__fastcall **)(struct IEnrollEngine *, __int128 *, int *, int *))(*(_QWORD *)a2 + 88LL))(
            a2,
            &v15,
            &v17,
            &v19);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x154,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
        (const char *)(unsigned int)v10,
        (int)&v18);
    if ( ((v17 - 5) & 0xFFFFFFFD) == 0 )
      break;
    if ( (unsigned int)++v5 >= 4 )
    {
      if ( v5 == 4 )
      {
        v12 = wil::verify_hresult<long>(0x8000FFFF);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x15E,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
          (const char *)v12,
          (int)&v18);
      }
      break;
    }
  }
  if ( hHandle[0] )
  {
    if ( !CloseHandle(hHandle[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v11);
  }
}

```

## disassembly

```asm
0x18002cd38  push    rbp
0x18002cd3a  push    rbx
0x18002cd3b  push    rsi
0x18002cd3c  push    rdi
0x18002cd3d  push    r15
0x18002cd3f  mov     rbp, rsp
0x18002cd42  sub     rsp, 50h
0x18002cd46  mov     rdi, rdx
0x18002cd49  mov     rsi, rcx
0x18002cd4c  mov     [rbp+hHandle], 0
0x18002cd54  mov     rax, [rdx]
0x18002cd57  lea     r8, [rbp+hHandle]
0x18002cd5b  mov     rdx, rcx
0x18002cd5e  mov     rcx, rdi
0x18002cd61  mov     rax, [rax+48h]
0x18002cd65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd6a  mov     r15d, 8000FFFFh
0x18002cd70  cmp     eax, 1
0x18002cd73  cmovz   eax, r15d
0x18002cd77  mov     rcx, [rbp+28h]; this
0x18002cd7b  test    eax, eax
0x18002cd7d  js      loc_18002CE65
0x18002cd83  xor     ebx, ebx
0x18002cd85  xor     r8d, r8d; bAlertable
0x18002cd88  mov     edx, 2BF20h; dwMilliseconds
0x18002cd8d  mov     rcx, [rbp+hHandle]; hHandle
0x18002cd91  call    cs:__imp_WaitForSingleObjectEx
0x18002cd97  cmp     eax, 102h
0x18002cd9c  jz      short loc_18002CDAA
0x18002cd9e  test    eax, eax
0x18002cda0  jnz     loc_18002CE9B
0x18002cda6  mov     al, 1
0x18002cda8  jmp     short loc_18002CDAC
0x18002cdaa  xor     al, al
0x18002cdac  mov     rcx, [rbp+28h]; this
0x18002cdb0  test    al, al
0x18002cdb2  jz      loc_18002CE53
0x18002cdb8  mov     rcx, [rbp+hHandle]; hEvent
0x18002cdbc  call    cs:__imp_ResetEvent
0x18002cdc2  mov     rcx, [rbp+28h]; this
0x18002cdc6  test    eax, eax
0x18002cdc8  jz      loc_18002CEDC
0x18002cdce  mov     [rbp+arg_18], 0
0x18002cdd5  mov     [rbp+arg_10], 0
0x18002cddc  mov     [rbp+arg_8], 0
0x18002cde3  movups  xmm0, xmmword ptr [rsi]
0x18002cde6  movdqu  [rbp+var_10], xmm0
0x18002cdeb  mov     rax, [rdi]
0x18002cdee  lea     rcx, [rbp+arg_10]
0x18002cdf2  mov     qword ptr [rsp+50h+var_30], rcx; int
0x18002cdf7  lea     r9, [rbp+arg_18]
0x18002cdfb  lea     r8, [rbp+arg_8]
0x18002cdff  lea     rdx, [rbp+var_10]
0x18002ce03  mov     rcx, rdi
0x18002ce06  mov     rax, [rax+58h]
0x18002ce0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce0f  mov     rcx, [rbp+28h]; this
0x18002ce13  test    eax, eax
0x18002ce15  js      loc_18002CEC7
0x18002ce1b  mov     eax, [rbp+arg_8]
0x18002ce1e  add     eax, 0FFFFFFFBh
0x18002ce21  test    eax, 0FFFFFFFDh
0x18002ce26  jz      short loc_18002CE35
0x18002ce28  inc     ebx
0x18002ce2a  cmp     ebx, 4
0x18002ce2d  jb      loc_18002CD85
0x18002ce33  jz      short loc_18002CE7A
0x18002ce35  mov     rcx, [rbp+hHandle]; hObject
0x18002ce39  test    rcx, rcx
0x18002ce3c  jz      short loc_18002CE48
0x18002ce3e  call    cs:__imp_CloseHandle
0x18002ce44  test    eax, eax
0x18002ce46  jz      short loc_18002CEB1
0x18002ce48  add     rsp, 50h
0x18002ce4c  pop     r15
0x18002ce4e  pop     rdi
0x18002ce4f  pop     rsi
0x18002ce50  pop     rbx
0x18002ce51  pop     rbp
0x18002ce52  retn
0x18002ce53  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x18002ce5a  mov     edx, 14Dh; void *
0x18002ce5f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002ce65  mov     r9d, eax; char *
0x18002ce68  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x18002ce6f  mov     edx, 145h; void *
0x18002ce74  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ce7a  mov     ecx, r15d
0x18002ce7d  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002ce82  mov     r9d, eax; char *
0x18002ce85  mov     rcx, [rbp+28h]; this
0x18002ce89  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x18002ce90  mov     edx, 15Eh; void *
0x18002ce95  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ce9b  mov     rcx, [rbp+28h]; this
0x18002ce9f  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cea6  mov     edx, 0B0Fh; void *
0x18002ceab  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002ceb1  mov     rcx, [rbp+28h]; this
0x18002ceb5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cebc  mov     edx, 0A0Bh; void *
0x18002cec1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002cec7  mov     r9d, eax; char *
0x18002ceca  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x18002ced1  mov     edx, 154h; void *
0x18002ced6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002cedc  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cee3  mov     edx, 0A06h; void *
0x18002cee8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
