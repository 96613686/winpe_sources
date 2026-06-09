# CWicMetadataEnumerator::GetNext(ushort *,uint,tagPROPVARIANT *,ulong *)

- ea: `0x180066880`
- end: `0x1800669de`
- name: `?GetNext@CWicMetadataEnumerator@@QEAAJPEAGIPEAUtagPROPVARIANT@@PEAK@Z`
- size: `350`
- prototype: `__int64 __fastcall(CWicMetadataEnumerator *__hidden this, unsigned __int16 *, unsigned int, struct tagPROPVARIANT *, unsigned int *)`
- caller_count: `14`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180065fe0`
- `0x18006615c`
- `0x1800664c4`
- `0x180066880`
- `0x180066b00`
- `0x180066d6c`
- `0x180067294`
- `0x18006794c`
- `0x180158724`
- `0x18015882c`
- `0x18015893c`
- `0x180159000`
- `0x1801592f4`
- `0x1801593c0`

## callees

- `0x180066880`
- `0x1800669e4`
- `0x180066a20`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180066949`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800669b7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180066949`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800669b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066990`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066990`

## pseudocode

```c
__int64 __fastcall CWicMetadataEnumerator::GetNext(
        CWicMetadataEnumerator *this,
        unsigned __int16 *a2,
        int a3,
        PROPVARIANT *a4,
        unsigned int *a5)
{
  int Next; // ebx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  unsigned int *v12; // r14
  LPVOID pv[5]; // [rsp+30h] [rbp-28h] BYREF
  int v15; // [rsp+70h] [rbp+18h] BYREF

  v15 = a3;
  *(_OWORD *)a4 = 0;
  a4[2] = 0;
  Next = -2147467259;
  if ( !*(_QWORD *)this )
    return (unsigned int)Next;
  v9 = *((_QWORD *)this + 1);
  if ( !v9 )
    return (unsigned int)Next;
  pv[0] = 0;
  v15 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v9 + 24LL))(v9, 1, pv, &v15);
  Next = v10;
  if ( v10 < 0 )
  {
LABEL_12:
    StringCchCopyW(a2, 0xC8u, &qword_18018B1D8);
    PropVariantClear(a4);
    return (unsigned int)Next;
  }
  if ( !v15 || v10 == 1 )
  {
    Next = -2147467259;
    goto LABEL_12;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, PROPVARIANT *))(**(_QWORD **)this + 40LL))(
          *(_QWORD *)this,
          pv[0],
          a4);
  v12 = a5;
  if ( v11 < 0
    || (Next = StringCchCopyW(a2, 0xC8u, (const unsigned __int16 *)pv[0]), Next < 0)
    || v12 && (Next = CWicMetadataEnumerator::GetPropertyId(this, a2, v12), Next < 0) )
  {
    PropVariantClear(a4);
    Next = CWicMetadataEnumerator::GetNext(this, a2, 0xC8u, (struct tagPROPVARIANT *)a4, v12);
  }
  CoTaskMemFree(pv[0]);
  if ( Next < 0 )
    goto LABEL_12;
  return (unsigned int)Next;
}

```

## disassembly

```asm
0x180066880  mov     r11, rsp
0x180066883  mov     [r11+10h], rbx
0x180066887  mov     [r11+20h], rbp
0x18006688b  mov     [r11+18h], r8d
0x18006688f  push    rsi
0x180066890  push    rdi
0x180066891  push    r14
0x180066893  sub     rsp, 40h
0x180066897  xor     eax, eax
0x180066899  xorps   xmm0, xmm0
0x18006689c  movups  xmmword ptr [r9], xmm0
0x1800668a0  mov     [r9+10h], rax
0x1800668a4  mov     r14d, 80004005h
0x1800668aa  mov     rdi, r9
0x1800668ad  mov     rbp, rdx
0x1800668b0  mov     rsi, rcx
0x1800668b3  mov     ebx, r14d
0x1800668b6  cmp     [rcx], rax
0x1800668b9  jz      loc_1800669C3
0x1800668bf  mov     rcx, [rcx+8]
0x1800668c3  test    rcx, rcx
0x1800668c6  jz      loc_1800669C3
0x1800668cc  and     [r11-28h], rax
0x1800668d0  lea     r9, [r11+18h]
0x1800668d4  and     [rsp+58h+arg_10], eax
0x1800668d8  lea     r8, [r11-28h]
0x1800668dc  mov     rax, [rcx]
0x1800668df  mov     edx, 1
0x1800668e4  mov     rax, [rax+18h]
0x1800668e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800668ed  mov     ebx, eax
0x1800668ef  test    eax, eax
0x1800668f1  js      loc_1800669A0
0x1800668f7  cmp     [rsp+58h+arg_10], 0
0x1800668fc  jbe     loc_1800669D9
0x180066902  cmp     eax, 1
0x180066905  jz      loc_1800669D9
0x18006690b  mov     rcx, [rsi]
0x18006690e  mov     r8, rdi
0x180066911  mov     rdx, [rsp+58h+pv]
0x180066916  mov     rax, [rcx]
0x180066919  mov     rax, [rax+28h]
0x18006691d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066922  mov     r14, [rsp+58h+arg_20]
0x18006692a  test    eax, eax
0x18006692c  js      short loc_180066946
0x18006692e  mov     r8, [rsp+58h+pv]; unsigned __int16 *
0x180066933  mov     edx, 0C8h; unsigned __int64
0x180066938  mov     rcx, rbp; unsigned __int16 *
0x18006693b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180066940  mov     ebx, eax
0x180066942  test    eax, eax
0x180066944  jns     short loc_180066972
0x180066946  mov     rcx, rdi; pvar
0x180066949  call    cs:__imp_PropVariantClear
0x180066950  nop     dword ptr [rax+rax+00h]
0x180066955  mov     r9, rdi; struct tagPROPVARIANT *
0x180066958  mov     [rsp+58h+var_38], r14; unsigned int *
0x18006695d  mov     r8d, 0C8h; unsigned int
0x180066963  mov     rdx, rbp; unsigned __int16 *
0x180066966  mov     rcx, rsi; this
0x180066969  call    ?GetNext@CWicMetadataEnumerator@@QEAAJPEAGIPEAUtagPROPVARIANT@@PEAK@Z; CWicMetadataEnumerator::GetNext(ushort *,uint,tagPROPVARIANT *,ulong *)
0x18006696e  mov     ebx, eax
0x180066970  jmp     short loc_18006698B
0x180066972  test    r14, r14
0x180066975  jz      short loc_18006698B
0x180066977  mov     r8, r14; unsigned int *
0x18006697a  mov     rdx, rbp; unsigned __int16 *
0x18006697d  mov     rcx, rsi; this
0x180066980  call    ?GetPropertyId@CWicMetadataEnumerator@@IEBAJPEBGPEAK@Z; CWicMetadataEnumerator::GetPropertyId(ushort const *,ulong *)
0x180066985  mov     ebx, eax
0x180066987  test    eax, eax
0x180066989  js      short loc_180066946
0x18006698b  mov     rcx, [rsp+58h+pv]; pv
0x180066990  call    cs:__imp_CoTaskMemFree
0x180066997  nop     dword ptr [rax+rax+00h]
0x18006699c  test    ebx, ebx
0x18006699e  jns     short loc_1800669C3
0x1800669a0  lea     r8, qword_18018B1D8; unsigned __int16 *
0x1800669a7  mov     edx, 0C8h; unsigned __int64
0x1800669ac  mov     rcx, rbp; unsigned __int16 *
0x1800669af  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800669b4  mov     rcx, rdi; pvar
0x1800669b7  call    cs:__imp_PropVariantClear
0x1800669be  nop     dword ptr [rax+rax+00h]
0x1800669c3  mov     rbp, [rsp+58h+arg_18]
0x1800669c8  mov     eax, ebx
0x1800669ca  mov     rbx, [rsp+58h+arg_8]
0x1800669cf  add     rsp, 40h
0x1800669d3  pop     r14
0x1800669d5  pop     rdi
0x1800669d6  pop     rsi
0x1800669d7  retn
0x1800669d9  mov     ebx, r14d
0x1800669dc  jmp     short loc_1800669A0
```
