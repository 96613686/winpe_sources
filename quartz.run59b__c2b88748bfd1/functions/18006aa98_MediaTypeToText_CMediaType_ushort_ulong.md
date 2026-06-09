# MediaTypeToText(CMediaType,ushort * *,ulong *)

- ea: `0x18006aa98`
- end: `0x18006ac23`
- name: `?MediaTypeToText@@YAJVCMediaType@@PEAPEAGPEAK@Z`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180063cb8`

## callees

- `0x180004924`
- `0x18002f03c`
- `0x18006aa98`
- `0x18015bb98`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18006abec`
- `ole32!CoTaskMemFree` at `0x18006abec`
- `ole32!CoTaskMemAlloc` at `0x18006aac1`
- `ole32!CoTaskMemAlloc` at `0x18006aac1`
- `ole32!StringFromGUID2` at `0x18006aaee`
- `ole32!StringFromGUID2` at `0x18006ab19`
- `ole32!StringFromGUID2` at `0x18006ab99`
- `ole32!StringFromGUID2` at `0x18006aaee`
- `ole32!StringFromGUID2` at `0x18006ab19`
- `ole32!StringFromGUID2` at `0x18006ab99`

## pseudocode

```c
__int64 __fastcall MediaTypeToText(struct _AMMediaType *a1, LPVOID *a2, unsigned int *a3)
{
  unsigned int v4; // eax
  OLECHAR *v6; // rax
  OLECHAR *v7; // rbx
  int v8; // edi

  v4 = a1->cbFormat + 286;
  if ( a1->cbFormat >= 0xFFFFFEE2 )
  {
    *a3 = -1;
    v8 = -2147220920;
  }
  else
  {
    *a3 = v4;
    v6 = (OLECHAR *)CoTaskMemAlloc(v4);
    *a2 = v6;
    v7 = v6;
    if ( v6 )
    {
      v8 = StringFromGUID2(&a1->majortype, v6, 39);
      if ( v8 < 0 )
        goto LABEL_8;
      v7[38] = 32;
      v8 = StringFromGUID2(&a1->subtype, v7 + 39, 39);
      if ( v8 < 0
        || (v7[77] = 32,
            v7[78] = a1->bFixedSizeSamples + 48,
            v7[79] = 32,
            v7[80] = a1->bTemporalCompression + 48,
            v7[81] = 32,
            StringCchPrintfW(v7 + 82, 0xBu, L"%010d ", a1->lSampleSize),
            v8 = StringFromGUID2(&a1->formattype, v7 + 93, 39),
            v8 < 0) )
      {
LABEL_8:
        CoTaskMemFree(*a2);
        *a2 = 0;
      }
      else
      {
        v7[131] = 32;
        StringCchPrintfW(v7 + 132, 0xBu, L"%010d", a1->cbFormat);
        v7[142] = 32;
        memcpy_0(v7 + 143, a1->pbFormat, a1->cbFormat);
      }
    }
    else
    {
      v8 = -2147024882;
    }
  }
  FreeMediaType(a1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006aa98  push    rbx
0x18006aa9a  push    rbp
0x18006aa9b  push    rsi
0x18006aa9c  push    rdi
0x18006aa9d  push    r14
0x18006aa9f  sub     rsp, 20h
0x18006aaa3  mov     eax, [rcx+48h]
0x18006aaa6  mov     r14, rdx
0x18006aaa9  add     eax, 11Eh
0x18006aaae  mov     rsi, rcx
0x18006aab1  cmp     eax, 11Eh
0x18006aab6  jb      loc_18006AC01
0x18006aabc  mov     ecx, eax; cb
0x18006aabe  mov     [r8], eax
0x18006aac1  call    cs:__imp_CoTaskMemAlloc
0x18006aac8  nop     dword ptr [rax+rax+00h]
0x18006aacd  mov     [r14], rax
0x18006aad0  mov     rbx, rax
0x18006aad3  test    rax, rax
0x18006aad6  jnz     short loc_18006AAE2
0x18006aad8  mov     edi, 8007000Eh
0x18006aadd  jmp     loc_18006AC0D
0x18006aae2  mov     r8d, 27h ; '''; cchMax
0x18006aae8  mov     rdx, rbx; lpsz
0x18006aaeb  mov     rcx, rsi; rguid
0x18006aaee  call    cs:__imp_StringFromGUID2
0x18006aaf5  nop     dword ptr [rax+rax+00h]
0x18006aafa  mov     edi, eax
0x18006aafc  test    eax, eax
0x18006aafe  js      loc_18006ABE9
0x18006ab04  mov     ebp, 20h ; ' '
0x18006ab09  lea     rcx, [rsi+10h]; rguid
0x18006ab0d  lea     rdx, [rbx+4Eh]; lpsz
0x18006ab11  mov     [rbx+4Ch], bp
0x18006ab15  lea     r8d, [rbp+7]; cchMax
0x18006ab19  call    cs:__imp_StringFromGUID2
0x18006ab20  nop     dword ptr [rax+rax+00h]
0x18006ab25  mov     edi, eax
0x18006ab27  test    eax, eax
0x18006ab29  js      loc_18006ABE9
0x18006ab2f  mov     [rbx+9Ah], bp
0x18006ab36  lea     r8, a010d_0; "%010d "
0x18006ab3d  mov     eax, [rsi+20h]
0x18006ab40  lea     edx, [rbp-15h]; unsigned __int64
0x18006ab43  neg     eax
0x18006ab45  sbb     cx, cx
0x18006ab48  neg     cx
0x18006ab4b  add     cx, 30h ; '0'
0x18006ab4f  mov     [rbx+9Ch], cx
0x18006ab56  mov     [rbx+9Eh], bp
0x18006ab5d  mov     eax, [rsi+24h]
0x18006ab60  neg     eax
0x18006ab62  sbb     cx, cx
0x18006ab65  neg     cx
0x18006ab68  add     cx, 30h ; '0'
0x18006ab6c  mov     [rbx+0A0h], cx
0x18006ab73  lea     rcx, [rbx+0A4h]; Buffer
0x18006ab7a  mov     [rbx+0A2h], bp
0x18006ab81  mov     r9d, [rsi+28h]
0x18006ab85  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006ab8a  lea     rcx, [rsi+2Ch]; rguid
0x18006ab8e  lea     r8d, [rbp+7]; cchMax
0x18006ab92  lea     rdx, [rbx+0BAh]; lpsz
0x18006ab99  call    cs:__imp_StringFromGUID2
0x18006aba0  nop     dword ptr [rax+rax+00h]
0x18006aba5  mov     edi, eax
0x18006aba7  test    eax, eax
0x18006aba9  js      short loc_18006ABE9
0x18006abab  mov     [rbx+106h], bp
0x18006abb2  lea     r8, a010d; "%010d"
0x18006abb9  mov     r9d, [rsi+48h]
0x18006abbd  lea     edx, [rbp-15h]; unsigned __int64
0x18006abc0  lea     rcx, [rbx+108h]; Buffer
0x18006abc7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006abcc  mov     [rbx+11Ch], bp
0x18006abd3  lea     rcx, [rbx+11Eh]; void *
0x18006abda  mov     r8d, [rsi+48h]; Size
0x18006abde  mov     rdx, [rsi+50h]; Src
0x18006abe2  call    memcpy_0
0x18006abe7  jmp     short loc_18006AC0D
0x18006abe9  mov     rcx, [r14]; pv
0x18006abec  call    cs:__imp_CoTaskMemFree
0x18006abf3  nop     dword ptr [rax+rax+00h]
0x18006abf8  mov     qword ptr [r14], 0
0x18006abff  jmp     short loc_18006AC0D
0x18006ac01  mov     dword ptr [r8], 0FFFFFFFFh
0x18006ac08  mov     edi, 80040248h
0x18006ac0d  mov     rcx, rsi; struct _AMMediaType *
0x18006ac10  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18006ac15  mov     eax, edi
0x18006ac17  add     rsp, 20h
0x18006ac1b  pop     r14
0x18006ac1d  pop     rdi
0x18006ac1e  pop     rsi
0x18006ac1f  pop     rbp
0x18006ac20  pop     rbx
0x18006ac21  retn
```
