# CbsOfflineUtil::CbsCreateOfflineSessionFromExternalStack(wchar_t const *,ICbsSession * *)

- ea: `0x140024de0`
- end: `0x140024ec3`
- name: `?CbsCreateOfflineSessionFromExternalStack@CbsOfflineUtil@@UEAAJPEB_WPEAPEAUICbsSession@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(CbsOfflineUtil *__hidden this, const wchar_t *, struct ICbsSession **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400056ac`
- `0x140024604`
- `0x140024aa0`
- `0x140024de0`
- `0x1400258f0`
- `0x140025b08`
- `0x14002a010`

## string_xrefs

- `0x140024e16`: `\cbscore.dll`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CbsCreateOfflineSessionFromExternalStack(
        CbsOfflineUtil *this,
        const wchar_t *a2,
        struct ICbsSession **a3)
{
  int SessionFromCbsCorePath; // ebx
  __int64 v6; // rdx
  struct ICbsSession **InitPointer; // rax
  struct ICbsSession *v9; // [rsp+20h] [rbp-10h] BYREF
  wchar_t *v10; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]

  *a3 = 0;
  v9 = 0;
  v10 = 0;
  SessionFromCbsCorePath = ConcatTwoStrings(a2, L"\\cbscore.dll", &v10);
  if ( SessionFromCbsCorePath < 0 )
  {
    v6 = 317;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
      (const char *)(unsigned int)SessionFromCbsCorePath,
      (int)v9);
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v10);
    if ( v9 )
      (*(void (__fastcall **)(struct ICbsSession *))(*(_QWORD *)v9 + 16LL))(v9);
    return (unsigned int)SessionFromCbsCorePath;
  }
  InitPointer = (struct ICbsSession **)Windows::AutoComPtr<ICbsSession>::GetInitPointer(&v9);
  SessionFromCbsCorePath = CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(this, v10, InitPointer);
  if ( SessionFromCbsCorePath < 0 )
  {
    v6 = 318;
    goto LABEL_3;
  }
  *a3 = v9;
  v9 = 0;
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v10);
  if ( v9 )
    (*(void (__fastcall **)(struct ICbsSession *))(*(_QWORD *)v9 + 16LL))(v9);
  return 0;
}

```

## disassembly

```asm
0x140024de0  mov     [rsp-18h+arg_18], rbx
0x140024de5  push    rbp
0x140024de6  push    rsi
0x140024de7  push    rdi
0x140024de8  mov     rbp, rsp
0x140024deb  sub     rsp, 30h
0x140024def  mov     rax, rdx
0x140024df2  mov     qword ptr [r8], 0
0x140024df9  mov     rdi, r8
0x140024dfc  mov     [rbp+var_10], 0
0x140024e04  mov     rsi, rcx
0x140024e07  mov     [rbp+var_8], 0
0x140024e0f  mov     rcx, rax
0x140024e12  lea     r8, [rbp+var_8]
0x140024e16  lea     rdx, aCbscoreDll; "\\cbscore.dll"
0x140024e1d  call    ConcatTwoStrings
0x140024e22  mov     ebx, eax
0x140024e24  test    eax, eax
0x140024e26  jns     short loc_140024E62
0x140024e28  mov     edx, 13Dh; void *
0x140024e2d  mov     rcx, [rbp+18h]; this
0x140024e31  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x140024e38  mov     r9d, ebx; char *
0x140024e3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024e40  lea     rcx, [rbp+var_8]
0x140024e44  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x140024e49  mov     rcx, [rbp+var_10]
0x140024e4d  test    rcx, rcx
0x140024e50  jz      short loc_140024E5E
0x140024e52  mov     rax, [rcx]
0x140024e55  mov     rax, [rax+10h]
0x140024e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024e5e  mov     eax, ebx
0x140024e60  jmp     short loc_140024EB6
0x140024e62  lea     rcx, [rbp+var_10]
0x140024e66  call    ?GetInitPointer@?$AutoComPtr@UICbsSession@@@Windows@@QEAAPEAPEAUICbsSession@@XZ; Windows::AutoComPtr<ICbsSession>::GetInitPointer(void)
0x140024e6b  mov     rdx, [rbp+var_8]; wchar_t *
0x140024e6f  mov     r8, rax; struct ICbsSession **
0x140024e72  mov     rcx, rsi; this
0x140024e75  call    ?CbsCreateSessionFromCbsCorePath@CbsOfflineUtil@@QEAAJPEB_WPEAPEAUICbsSession@@@Z; CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(wchar_t const *,ICbsSession * *)
0x140024e7a  mov     ebx, eax
0x140024e7c  test    eax, eax
0x140024e7e  jns     short loc_140024E87
0x140024e80  mov     edx, 13Eh
0x140024e85  jmp     short loc_140024E2D
0x140024e87  mov     rax, [rbp+var_10]
0x140024e8b  lea     rcx, [rbp+var_8]
0x140024e8f  mov     [rdi], rax
0x140024e92  mov     [rbp+var_10], 0
0x140024e9a  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x140024e9f  mov     rcx, [rbp+var_10]
0x140024ea3  test    rcx, rcx
0x140024ea6  jz      short loc_140024EB4
0x140024ea8  mov     rax, [rcx]
0x140024eab  mov     rax, [rax+10h]
0x140024eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024eb4  xor     eax, eax
0x140024eb6  mov     rbx, [rsp+30h+arg_18]
0x140024ebb  add     rsp, 30h
0x140024ebf  pop     rdi
0x140024ec0  pop     rsi
0x140024ec1  pop     rbp
0x140024ec2  retn
```
