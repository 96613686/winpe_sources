# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::Lookup(HSTRING__ *,HSTRING__ * *)

- ea: `0x180044170`
- end: `0x18004425d`
- name: `?Lookup@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAU1@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U73456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAPEAU7@@Z`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002e2ac`

## callees

- `0x180036fbc`
- `0x180044170`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800441fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004422b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800441fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004422b`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::Lookup(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v6; // ebx
  unsigned int v7; // ebp
  char v8; // di
  __int64 v9; // rsi
  __int64 v10; // r14
  __int64 v11; // rcx
  char v13; // [rsp+60h] [rbp+8h] BYREF
  HSTRING string; // [rsp+78h] [rbp+20h] BYREF

  v6 = 0;
  v7 = *(_DWORD *)(*(_QWORD *)(a1 + 40) + 12LL);
  v8 = 0;
  v13 = 0;
  v9 = 0;
  while ( (unsigned int)v9 < v7 )
  {
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8 * v9 + 16);
    string = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v10 + 48LL))(v10, &string);
    if ( v6 >= 0 )
    {
      v6 = XWinRT::StringEquals::operator()(v11, a2, string, &v13);
      v8 = v13;
      if ( v6 >= 0 )
      {
        if ( v13 )
        {
          v6 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v10 + 56LL))(v10, a3);
          WindowsDeleteString(string);
          if ( v6 < 0 )
            goto LABEL_11;
          break;
        }
      }
    }
    WindowsDeleteString(string);
    string = 0;
    v9 = (unsigned int)(v9 + 1);
    if ( v6 < 0 )
      goto LABEL_11;
  }
  if ( v8 )
    return (unsigned int)v6;
  v6 = -2147483637;
LABEL_11:
  *a3 = 0;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180044170  mov     [rsp+arg_8], rbx
0x180044175  push    rbp
0x180044176  push    rsi
0x180044177  push    rdi
0x180044178  push    r12
0x18004417a  push    r13
0x18004417c  push    r14
0x18004417e  push    r15
0x180044180  sub     rsp, 20h
0x180044184  mov     r15, r8
0x180044187  mov     r12, rdx
0x18004418a  mov     r13, rcx
0x18004418d  xor     ebx, ebx
0x18004418f  mov     rax, [rcx+28h]
0x180044193  mov     ebp, [rax+0Ch]
0x180044196  xor     dil, dil
0x180044199  mov     [rsp+58h+arg_0], dil
0x18004419e  xor     esi, esi
0x1800441a0  cmp     esi, ebp
0x1800441a2  jnb     loc_180044235
0x1800441a8  mov     rax, [r13+28h]
0x1800441ac  mov     r14, [rax+rsi*8+10h]
0x1800441b1  mov     [rsp+58h+string], 0
0x1800441ba  mov     rax, [r14]
0x1800441bd  lea     rdx, [rsp+58h+string]
0x1800441c2  mov     rcx, r14
0x1800441c5  mov     rax, [rax+30h]
0x1800441c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441ce  mov     ebx, eax
0x1800441d0  test    eax, eax
0x1800441d2  js      short loc_1800441F6
0x1800441d4  lea     r9, [rsp+58h+arg_0]
0x1800441d9  mov     r8, [rsp+58h+string]
0x1800441de  mov     rdx, r12
0x1800441e1  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x1800441e6  mov     ebx, eax
0x1800441e8  mov     dil, [rsp+58h+arg_0]
0x1800441ed  test    eax, eax
0x1800441ef  js      short loc_1800441F6
0x1800441f1  test    dil, dil
0x1800441f4  jnz     short loc_180044212
0x1800441f6  mov     rcx, [rsp+58h+string]; string
0x1800441fb  call    cs:__imp_WindowsDeleteString
0x180044201  mov     [rsp+58h+string], 0
0x18004420a  inc     esi
0x18004420c  test    ebx, ebx
0x18004420e  jns     short loc_1800441A0
0x180044210  jmp     short loc_18004423F
0x180044212  mov     rax, [r14]
0x180044215  mov     rdx, r15
0x180044218  mov     rcx, r14
0x18004421b  mov     rax, [rax+38h]
0x18004421f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044224  mov     ebx, eax
0x180044226  mov     rcx, [rsp+58h+string]; string
0x18004422b  call    cs:__imp_WindowsDeleteString
0x180044231  test    ebx, ebx
0x180044233  js      short loc_18004423F
0x180044235  test    dil, dil
0x180044238  jnz     short loc_180044246
0x18004423a  mov     ebx, 8000000Bh
0x18004423f  mov     qword ptr [r15], 0
0x180044246  mov     eax, ebx
0x180044248  mov     rbx, [rsp+58h+arg_8]
0x18004424d  add     rsp, 20h
0x180044251  pop     r15
0x180044253  pop     r14
0x180044255  pop     r13
0x180044257  pop     r12
0x180044259  pop     rdi
0x18004425a  pop     rsi
0x18004425b  pop     rbp
0x18004425c  retn
```
