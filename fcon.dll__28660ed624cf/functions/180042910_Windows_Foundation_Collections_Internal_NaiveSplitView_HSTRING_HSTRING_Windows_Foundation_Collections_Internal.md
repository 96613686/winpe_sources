# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::HasKey(HSTRING__ *,uchar *)

- ea: `0x180042910`
- end: `0x1800429c6`
- name: `?HasKey@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAU1@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U73456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAE@Z`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002e320`

## callees

- `0x180036fbc`
- `0x180042910`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004298e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800429ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004298e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800429ad`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::HasKey(
        __int64 a1,
        __int64 a2,
        _BYTE *a3)
{
  unsigned int v6; // ebp
  int v7; // ebx
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rcx
  char v12; // [rsp+50h] [rbp+8h] BYREF
  HSTRING string; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  v6 = *(_DWORD *)(*(_QWORD *)(a1 + 40) + 12LL);
  v12 = 0;
  v7 = 0;
  v8 = 0;
  while ( (unsigned int)v8 < v6 )
  {
    v9 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8 * v8 + 16);
    string = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v9 + 48LL))(v9, &string);
    if ( v7 >= 0 )
    {
      v7 = XWinRT::StringEquals::operator()(v10, a2, string, &v12);
      if ( v7 >= 0 )
      {
        if ( v12 )
        {
          *a3 = 1;
          WindowsDeleteString(string);
          return (unsigned int)v7;
        }
      }
    }
    WindowsDeleteString(string);
    string = 0;
    v8 = (unsigned int)(v8 + 1);
    if ( v7 < 0 )
      return (unsigned int)v7;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180042910  mov     [rsp+arg_8], rbx
0x180042915  push    rbp
0x180042916  push    rsi
0x180042917  push    rdi
0x180042918  push    r14
0x18004291a  push    r15
0x18004291c  sub     rsp, 20h
0x180042920  mov     rsi, r8
0x180042923  mov     r15, rdx
0x180042926  mov     r14, rcx
0x180042929  mov     byte ptr [r8], 0
0x18004292d  mov     rax, [rcx+28h]
0x180042931  mov     ebp, [rax+0Ch]
0x180042934  mov     [rsp+48h+arg_0], 0
0x180042939  xor     ebx, ebx
0x18004293b  xor     edi, edi
0x18004293d  cmp     edi, ebp
0x18004293f  jnb     short loc_1800429B3
0x180042941  mov     rax, [r14+28h]
0x180042945  mov     rcx, [rax+rdi*8+10h]
0x18004294a  mov     [rsp+48h+string], 0
0x180042953  mov     rax, [rcx]
0x180042956  lea     rdx, [rsp+48h+string]
0x18004295b  mov     rax, [rax+30h]
0x18004295f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042964  mov     ebx, eax
0x180042966  test    eax, eax
0x180042968  js      short loc_180042989
0x18004296a  lea     r9, [rsp+48h+arg_0]
0x18004296f  mov     r8, [rsp+48h+string]
0x180042974  mov     rdx, r15
0x180042977  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x18004297c  mov     ebx, eax
0x18004297e  test    eax, eax
0x180042980  js      short loc_180042989
0x180042982  cmp     [rsp+48h+arg_0], 0
0x180042987  jnz     short loc_1800429A5
0x180042989  mov     rcx, [rsp+48h+string]; string
0x18004298e  call    cs:__imp_WindowsDeleteString
0x180042994  mov     [rsp+48h+string], 0
0x18004299d  inc     edi
0x18004299f  test    ebx, ebx
0x1800429a1  jns     short loc_18004293D
0x1800429a3  jmp     short loc_1800429B3
0x1800429a5  mov     byte ptr [rsi], 1
0x1800429a8  mov     rcx, [rsp+48h+string]; string
0x1800429ad  call    cs:__imp_WindowsDeleteString
0x1800429b3  mov     eax, ebx
0x1800429b5  mov     rbx, [rsp+48h+arg_8]
0x1800429ba  add     rsp, 20h
0x1800429be  pop     r15
0x1800429c0  pop     r14
0x1800429c2  pop     rdi
0x1800429c3  pop     rsi
0x1800429c4  pop     rbp
0x1800429c5  retn
```
