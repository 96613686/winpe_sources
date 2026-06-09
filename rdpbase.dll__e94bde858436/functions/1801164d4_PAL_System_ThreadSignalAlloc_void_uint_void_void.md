# PAL_System_ThreadSignalAlloc(void * *,uint (*)(void *),void *)

- ea: `0x1801164d4`
- end: `0x1801166c8`
- name: `?PAL_System_ThreadSignalAlloc@@YAJPEAPEAXP6AIPEAX@Z1@Z`
- size: `500`
- prototype: `__int64 __fastcall(void **, unsigned int (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18014d640`

## callees

- `0x1800018a4`
- `0x180113e70`
- `0x1801164d4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180116512`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180116512`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180116619`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180116619`

## string_xrefs

- `0x18011654d`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommon.cpp`
- `0x1801165c7`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommon.cpp`
- `0x180116663`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommon.cpp`
- `0x180116534`: `PAL_System_ThreadSignalAlloc`
- `0x1801165ae`: `PAL_System_ThreadSignalAlloc`
- `0x18011664a`: `PAL_System_ThreadSignalAlloc`
- `0x1801165d9`: `Failed to create thread signal window`
- `0x180116558`: `Failed to allocated thread signal struct`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadSignalAlloc(void **a1, unsigned int (*a2)(void *), void *a3, int a4)
{
  __int64 v7; // rdx
  _QWORD *v8; // rbx
  int v9; // edi
  int *v10; // rdx
  const char **v11; // rax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  const char **v16; // [rsp+40h] [rbp-30h]
  const char *v17; // [rsp+50h] [rbp-20h] BYREF
  const char *v18; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v19[2]; // [rsp+60h] [rbp-10h] BYREF
  HWND v20; // [rsp+A0h] [rbp+30h] BYREF
  int v21; // [rsp+B8h] [rbp+48h] BYREF

  v20 = 0;
  if ( a1 && a2 )
  {
    v8 = LocalAlloc(0x40u, 0x18u);
    if ( v8 )
    {
      v9 = PAL_System_Win32_ThreadCreateWindow(&v20, v7, (int)a3, a4);
      if ( v9 >= 0 )
      {
        v9 = 0;
        *v8 = v20;
        v8[1] = a2;
        v8[2] = a3;
        *a1 = v8;
      }
      else
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v20) = 111;
          v19[0] = "PAL_System_ThreadSignalAlloc";
          v21 = -2147467259;
          v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\system\\tssystempalwincommon.cpp";
          v17 = "Failed to create thread signal window";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v12,
            (unsigned int)word_1801CC0CA,
            v13,
            v14,
            (__int64)&v17,
            (__int64)&v21,
            (__int64)&v18,
            (__int64)&v20,
            (__int64)v19);
        }
        LocalFree(v8);
      }
    }
    else
    {
      v9 = -2147024882;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v20) = 102;
        v17 = "PAL_System_ThreadSignalAlloc";
        v10 = &dword_1801CC154;
        v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\system\\tssystempalwincommon.cpp";
        v19[0] = "Failed to allocated thread signal struct";
        v16 = &v17;
        v11 = (const char **)v19;
LABEL_13:
        v21 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)a1,
          (_DWORD)v10,
          (_DWORD)a3,
          a4,
          (__int64)v11,
          (__int64)&v21,
          (__int64)&v18,
          (__int64)&v20,
          (__int64)v16);
      }
    }
  }
  else
  {
    v9 = -2147024809;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v20) = 91;
      v19[0] = "PAL_System_ThreadSignalAlloc";
      v10 = (int *)&byte_1801CC10F;
      v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\system\\tssystempalwincommon.cpp";
      v17 = "NULL parameter passed";
      v16 = (const char **)v19;
      v11 = &v17;
      goto LABEL_13;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1801164d4  mov     [rsp-28h+arg_8], rbx
0x1801164d9  push    rbp
0x1801164da  push    rsi
0x1801164db  push    rdi
0x1801164dc  push    r14
0x1801164de  push    r15
0x1801164e0  mov     rbp, rsp
0x1801164e3  sub     rsp, 70h
0x1801164e7  mov     [rbp+arg_0], 0
0x1801164ef  mov     r15, r8
0x1801164f2  mov     rsi, rdx
0x1801164f5  mov     r14, rcx
0x1801164f8  test    rcx, rcx
0x1801164fb  jz      loc_18011663A
0x180116501  test    rdx, rdx
0x180116504  jz      loc_18011663A
0x18011650a  mov     edx, 18h; uBytes
0x18011650f  lea     ecx, [rdx+28h]; uFlags
0x180116512  call    cs:__imp_LocalAlloc
0x180116518  mov     rbx, rax
0x18011651b  test    rax, rax
0x18011651e  jnz     short loc_180116590
0x180116520  mov     eax, cs:CallbackContext
0x180116526  mov     edi, 8007000Eh
0x18011652b  cmp     eax, 2
0x18011652e  jbe     loc_1801166B2
0x180116534  lea     rax, aPalSystemThrea_1; "PAL_System_ThreadSignalAlloc"
0x18011653b  mov     dword ptr [rbp+arg_0], 66h ; 'f'
0x180116542  mov     [rbp+var_20], rax
0x180116546  lea     rdx, dword_1801CC154
0x18011654d  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180116554  mov     [rbp+var_18], rax
0x180116558  lea     rax, aFailedToAlloca; "Failed to allocated thread signal struc"...
0x18011655f  mov     [rbp+var_10], rax
0x180116563  lea     rax, [rbp+var_20]
0x180116567  mov     [rsp+70h+var_30], rax
0x18011656c  lea     rax, [rbp+arg_0]
0x180116570  mov     [rsp+70h+var_38], rax
0x180116575  lea     rax, [rbp+var_18]
0x180116579  mov     [rsp+70h+var_40], rax
0x18011657e  lea     rax, [rbp+arg_18]
0x180116582  mov     [rsp+70h+var_48], rax
0x180116587  lea     rax, [rbp+var_10]
0x18011658b  jmp     loc_1801166A1
0x180116590  lea     rcx, [rbp+arg_0]; HWND *
0x180116594  call    ?PAL_System_Win32_ThreadCreateWindow@@YAJPEAPEAUHWND__@@@Z; PAL_System_Win32_ThreadCreateWindow(HWND__ * *)
0x180116599  mov     edi, eax
0x18011659b  test    eax, eax
0x18011659d  jns     loc_180116624
0x1801165a3  mov     eax, cs:CallbackContext
0x1801165a9  cmp     eax, 2
0x1801165ac  jbe     short loc_180116616
0x1801165ae  lea     rax, aPalSystemThrea_1; "PAL_System_ThreadSignalAlloc"
0x1801165b5  mov     dword ptr [rbp+arg_0], 6Fh ; 'o'
0x1801165bc  mov     [rbp+var_10], rax
0x1801165c0  lea     rdx, word_1801CC0CA
0x1801165c7  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1801165ce  mov     [rbp+arg_18], 80004005h
0x1801165d5  mov     [rbp+var_18], rax
0x1801165d9  lea     rax, aFailedToCreate_41; "Failed to create thread signal window"
0x1801165e0  mov     [rbp+var_20], rax
0x1801165e4  lea     rax, [rbp+var_10]
0x1801165e8  mov     [rsp+70h+var_30], rax
0x1801165ed  lea     rax, [rbp+arg_0]
0x1801165f1  mov     [rsp+70h+var_38], rax
0x1801165f6  lea     rax, [rbp+var_18]
0x1801165fa  mov     [rsp+70h+var_40], rax
0x1801165ff  lea     rax, [rbp+arg_18]
0x180116603  mov     [rsp+70h+var_48], rax
0x180116608  lea     rax, [rbp+var_20]
0x18011660c  mov     [rsp+70h+var_50], rax
0x180116611  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180116616  mov     rcx, rbx; hMem
0x180116619  call    cs:__imp_LocalFree
0x18011661f  jmp     loc_1801166B2
0x180116624  mov     rax, [rbp+arg_0]
0x180116628  xor     edi, edi
0x18011662a  mov     [rbx], rax
0x18011662d  mov     [rbx+8], rsi
0x180116631  mov     [rbx+10h], r15
0x180116635  mov     [r14], rbx
0x180116638  jmp     short loc_1801166B2
0x18011663a  mov     eax, cs:CallbackContext
0x180116640  mov     edi, 80070057h
0x180116645  cmp     eax, 2
0x180116648  jbe     short loc_1801166B2
0x18011664a  lea     rax, aPalSystemThrea_1; "PAL_System_ThreadSignalAlloc"
0x180116651  mov     dword ptr [rbp+arg_0], 5Bh ; '['
0x180116658  mov     [rbp+var_10], rax
0x18011665c  lea     rdx, byte_1801CC10F
0x180116663  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18011666a  mov     [rbp+var_18], rax
0x18011666e  lea     rax, aNullParameterP; "NULL parameter passed"
0x180116675  mov     [rbp+var_20], rax
0x180116679  lea     rax, [rbp+var_10]
0x18011667d  mov     [rsp+70h+var_30], rax
0x180116682  lea     rax, [rbp+arg_0]
0x180116686  mov     [rsp+70h+var_38], rax
0x18011668b  lea     rax, [rbp+var_18]
0x18011668f  mov     [rsp+70h+var_40], rax
0x180116694  lea     rax, [rbp+arg_18]
0x180116698  mov     [rsp+70h+var_48], rax
0x18011669d  lea     rax, [rbp+var_20]
0x1801166a1  mov     [rsp+70h+var_50], rax
0x1801166a6  mov     [rbp+arg_18], 80004005h
0x1801166ad  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801166b2  mov     rbx, [rsp+70h+arg_8]
0x1801166ba  mov     eax, edi
0x1801166bc  add     rsp, 70h
0x1801166c0  pop     r15
0x1801166c2  pop     r14
0x1801166c4  pop     rdi
0x1801166c5  pop     rsi
0x1801166c6  pop     rbp
0x1801166c7  retn
```
