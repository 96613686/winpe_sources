# PAL_System_ThreadSignalAlloc(void * *,uint (*)(void *),void *)

- ea: `0x140043768`
- end: `0x140043958`
- name: `?PAL_System_ThreadSignalAlloc@@YAJPEAPEAXP6AIPEAX@Z1@Z`
- size: `496`
- prototype: `__int64 __fastcall(void **, unsigned int (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400201f0`

## callees

- `0x1400014d4`
- `0x1400186e4`
- `0x140041348`
- `0x140043768`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400438a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400438a9`

## string_xrefs

- `0x1400437c4`: `PAL_System_ThreadSignalAlloc`
- `0x14004383e`: `PAL_System_ThreadSignalAlloc`
- `0x1400438da`: `PAL_System_ThreadSignalAlloc`
- `0x1400437e8`: `Failed to allocated thread signal struct`
- `0x1400437dd`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommon.cpp`
- `0x140043857`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommon.cpp`
- `0x1400438f3`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommon.cpp`
- `0x140043869`: `Failed to create thread signal window`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadSignalAlloc(HWND **a1, unsigned int (*a2)(void *), HWND a3, int a4)
{
  __int64 v7; // rdx
  HWND *v8; // rbx
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
    v8 = (HWND *)PAL_System_MemAlloc(24);
    if ( v8 )
    {
      v9 = PAL_System_Win32_ThreadCreateWindow(&v20, v7, (int)a3, a4);
      if ( v9 >= 0 )
      {
        v9 = 0;
        *v8 = v20;
        v8[1] = (HWND)a2;
        v8[2] = a3;
        *a1 = v8;
      }
      else
      {
        if ( (unsigned int)dword_1400880C8 > 2 )
        {
          LODWORD(v20) = 111;
          v19[0] = "PAL_System_ThreadSignalAlloc";
          v21 = -2147467259;
          v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\system\\tssystempalwincommon.cpp";
          v17 = "Failed to create thread signal window";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v12,
            (unsigned int)word_1400809F2,
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
      if ( (unsigned int)dword_1400880C8 > 2 )
      {
        LODWORD(v20) = 102;
        v17 = "PAL_System_ThreadSignalAlloc";
        v10 = &dword_140080A7C;
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
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      LODWORD(v20) = 91;
      v19[0] = "PAL_System_ThreadSignalAlloc";
      v10 = (int *)&byte_140080A37;
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
0x140043768  mov     [rsp-28h+arg_8], rbx
0x14004376d  push    rbp
0x14004376e  push    rsi
0x14004376f  push    rdi
0x140043770  push    r14
0x140043772  push    r15
0x140043774  mov     rbp, rsp
0x140043777  sub     rsp, 70h
0x14004377b  mov     [rbp+arg_0], 0
0x140043783  mov     r15, r8
0x140043786  mov     rsi, rdx
0x140043789  mov     r14, rcx
0x14004378c  test    rcx, rcx
0x14004378f  jz      loc_1400438CA
0x140043795  test    rdx, rdx
0x140043798  jz      loc_1400438CA
0x14004379e  mov     ecx, 18h
0x1400437a3  call    PAL_System_MemAlloc
0x1400437a8  mov     rbx, rax
0x1400437ab  test    rax, rax
0x1400437ae  jnz     short loc_140043820
0x1400437b0  mov     eax, cs:dword_1400880C8
0x1400437b6  mov     edi, 8007000Eh
0x1400437bb  cmp     eax, 2
0x1400437be  jbe     loc_140043942
0x1400437c4  lea     rax, aPalSystemThrea_0; "PAL_System_ThreadSignalAlloc"
0x1400437cb  mov     dword ptr [rbp+arg_0], 66h ; 'f'
0x1400437d2  mov     [rbp+var_20], rax
0x1400437d6  lea     rdx, dword_140080A7C
0x1400437dd  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1400437e4  mov     [rbp+var_18], rax
0x1400437e8  lea     rax, aFailedToAlloca; "Failed to allocated thread signal struc"...
0x1400437ef  mov     [rbp+var_10], rax
0x1400437f3  lea     rax, [rbp+var_20]
0x1400437f7  mov     [rsp+70h+var_30], rax
0x1400437fc  lea     rax, [rbp+arg_0]
0x140043800  mov     [rsp+70h+var_38], rax
0x140043805  lea     rax, [rbp+var_18]
0x140043809  mov     [rsp+70h+var_40], rax
0x14004380e  lea     rax, [rbp+arg_18]
0x140043812  mov     [rsp+70h+var_48], rax
0x140043817  lea     rax, [rbp+var_10]
0x14004381b  jmp     loc_140043931
0x140043820  lea     rcx, [rbp+arg_0]; HWND *
0x140043824  call    ?PAL_System_Win32_ThreadCreateWindow@@YAJPEAPEAUHWND__@@@Z; PAL_System_Win32_ThreadCreateWindow(HWND__ * *)
0x140043829  mov     edi, eax
0x14004382b  test    eax, eax
0x14004382d  jns     loc_1400438B4
0x140043833  mov     eax, cs:dword_1400880C8
0x140043839  cmp     eax, 2
0x14004383c  jbe     short loc_1400438A6
0x14004383e  lea     rax, aPalSystemThrea_0; "PAL_System_ThreadSignalAlloc"
0x140043845  mov     dword ptr [rbp+arg_0], 6Fh ; 'o'
0x14004384c  mov     [rbp+var_10], rax
0x140043850  lea     rdx, word_1400809F2
0x140043857  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14004385e  mov     [rbp+arg_18], 80004005h
0x140043865  mov     [rbp+var_18], rax
0x140043869  lea     rax, aFailedToCreate_13; "Failed to create thread signal window"
0x140043870  mov     [rbp+var_20], rax
0x140043874  lea     rax, [rbp+var_10]
0x140043878  mov     [rsp+70h+var_30], rax
0x14004387d  lea     rax, [rbp+arg_0]
0x140043881  mov     [rsp+70h+var_38], rax
0x140043886  lea     rax, [rbp+var_18]
0x14004388a  mov     [rsp+70h+var_40], rax
0x14004388f  lea     rax, [rbp+arg_18]
0x140043893  mov     [rsp+70h+var_48], rax
0x140043898  lea     rax, [rbp+var_20]
0x14004389c  mov     [rsp+70h+var_50], rax
0x1400438a1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400438a6  mov     rcx, rbx; hMem
0x1400438a9  call    cs:__imp_LocalFree
0x1400438af  jmp     loc_140043942
0x1400438b4  mov     rax, [rbp+arg_0]
0x1400438b8  xor     edi, edi
0x1400438ba  mov     [rbx], rax
0x1400438bd  mov     [rbx+8], rsi
0x1400438c1  mov     [rbx+10h], r15
0x1400438c5  mov     [r14], rbx
0x1400438c8  jmp     short loc_140043942
0x1400438ca  mov     eax, cs:dword_1400880C8
0x1400438d0  mov     edi, 80070057h
0x1400438d5  cmp     eax, 2
0x1400438d8  jbe     short loc_140043942
0x1400438da  lea     rax, aPalSystemThrea_0; "PAL_System_ThreadSignalAlloc"
0x1400438e1  mov     dword ptr [rbp+arg_0], 5Bh ; '['
0x1400438e8  mov     [rbp+var_10], rax
0x1400438ec  lea     rdx, byte_140080A37
0x1400438f3  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1400438fa  mov     [rbp+var_18], rax
0x1400438fe  lea     rax, aNullParameterP; "NULL parameter passed"
0x140043905  mov     [rbp+var_20], rax
0x140043909  lea     rax, [rbp+var_10]
0x14004390d  mov     [rsp+70h+var_30], rax
0x140043912  lea     rax, [rbp+arg_0]
0x140043916  mov     [rsp+70h+var_38], rax
0x14004391b  lea     rax, [rbp+var_18]
0x14004391f  mov     [rsp+70h+var_40], rax
0x140043924  lea     rax, [rbp+arg_18]
0x140043928  mov     [rsp+70h+var_48], rax
0x14004392d  lea     rax, [rbp+var_20]
0x140043931  mov     [rsp+70h+var_50], rax
0x140043936  mov     [rbp+arg_18], 80004005h
0x14004393d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140043942  mov     rbx, [rsp+70h+arg_8]
0x14004394a  mov     eax, edi
0x14004394c  add     rsp, 70h
0x140043950  pop     r15
0x140043952  pop     r14
0x140043954  pop     rdi
0x140043955  pop     rsi
0x140043956  pop     rbp
0x140043957  retn
```
