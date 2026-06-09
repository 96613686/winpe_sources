# TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)

- ea: `0x18006f910`
- end: `0x18006fada`
- name: `?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ`
- size: `458`
- prototype: `__int64(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, ...)`
- caller_count: `443`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800150c0`
- `0x180015280`
- `0x180015440`
- `0x18001562c`
- `0x180015824`
- `0x1800159ec`
- `0x180015bec`
- `0x180015dd4`
- `0x180015fb4`
- `0x1800161a8`
- `0x1800163a0`
- `0x180016588`
- `0x180016788`
- `0x180016978`
- `0x180016b6c`
- `0x180016d58`
- `0x180016f38`
- `0x180017128`
- `0x180017310`
- `0x180017528`
- `0x180017734`
- `0x18001794c`
- `0x180017b6c`
- `0x180017d84`
- `0x180017fc8`
- `0x1800181e8`
- `0x18001d0dc`
- `0x18001e83c`
- `0x18001f984`
- `0x18001ff2c`
- `0x18001fff8`
- `0x1800204d0`
- `0x180021fe0`
- `0x18002222c`
- `0x180022508`
- `0x180022f94`
- `0x1800231f4`
- `0x180023724`
- `0x180024650`
- `0x180025560`
- `0x180025650`
- `0x180026660`
- `0x180026bb0`
- `0x180026f30`
- `0x180027078`
- `0x1800281f0`
- `0x18002a7a0`
- `0x18002aa40`
- `0x18002b760`
- `0x18002b9c0`

## callees

- `0x180002f50`
- `0x1800123b0`
- `0x180012400`
- `0x18006f330`
- `0x18006f788`
- `0x18006f910`
- `0x1800a3218`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18006f9bd`
- `ntdll!EtwEventEnabled` at `0x18006f9bd`
- `ntdll!EtwEventWriteString` at `0x18006f9a0`
- `ntdll!EtwEventWriteString` at `0x18006f9a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fa38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006faad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fa38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006faad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006fa47`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006fa47`

## string_xrefs

- `0x18006f971`: `No Event is defined in the manifest for trace type (%d) and level (%d)`

## pseudocode

```c
_BYTE *TraceMsg(unsigned __int8 a1, unsigned int a2, __int64 a3, int a4, wchar_t *a5, ...)
{
  _BYTE *v5; // rbx
  __int128 v8; // xmm6
  _BYTE *result; // rax
  unsigned int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // [rsp+40h] [rbp-C8h]
  wchar_t *v13[2]; // [rsp+48h] [rbp-C0h] BYREF
  HLOCAL v14; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 v15; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE hMem[320]; // [rsp+68h] [rbp-A0h] BYREF
  wchar_t v17[264]; // [rsp+1A8h] [rbp+A0h] BYREF
  va_list va; // [rsp+440h] [rbp+338h] BYREF

  va_start(va, a5);
  v5 = hMem;
  v14 = hMem;
  *(_OWORD *)v13 = 0;
  if ( !(unsigned int)GetEventDescriptor(a2, a1, v13)
    && (int)StringCchPrintfW(v17, 0x105u, L"No Event is defined in the manifest for trace type (%d) and level (%d)") >= 0 )
  {
    EtwEventWriteString(handle, 0, 0, v17);
  }
  v8 = *(_OWORD *)v13;
  result = (_BYTE *)EtwEventEnabled(handle, v13);
  if ( (_BYTE)result )
  {
    v10 = 160;
    v13[0] = 0;
    do
    {
      LODWORD(v12) = a4;
      v13[0] = 0;
      v15 = 0;
      if ( (unsigned int)StringCchPrintfExW((STRSAFE_LPWSTR)v5, v10, v13, &v15, 0x100u, L"%ws (%d): ", a3, v12) == -2147024774
        || (result = (_BYTE *)StringCchVPrintfW(v13[0], v15, a5, va), (_DWORD)result == -2147024774) )
      {
        if ( v5 != hMem )
          LocalFree(v5);
        v10 *= 2;
        result = LocalAlloc(0, 2LL * v10);
        v5 = result;
        v14 = result;
      }
      else if ( !(_DWORD)result )
      {
        break;
      }
    }
    while ( v5 );
    if ( v5 )
    {
      *(_OWORD *)v13 = v8;
      WriteEventEx(v13, v11, &v14);
      result = hMem;
      if ( v14 != hMem )
        return LocalFree(v14);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006f910  mov     rax, rsp
0x18006f913  push    rbp
0x18006f914  push    rbx
0x18006f915  push    rsi
0x18006f916  push    rdi
0x18006f917  push    r13
0x18006f919  push    r14
0x18006f91b  lea     rbp, [rax-308h]
0x18006f922  sub     rsp, 3D8h
0x18006f929  movaps  xmmword ptr [rax-48h], xmm6
0x18006f92d  mov     rax, cs:__security_cookie
0x18006f934  xor     rax, rsp
0x18006f937  mov     [rbp+300h+var_50], rax
0x18006f93e  xorps   xmm0, xmm0
0x18006f941  lea     rbx, [rsp+400h+hMem]
0x18006f946  mov     r14d, r9d
0x18006f949  mov     [rsp+400h+var_3B0], rbx
0x18006f94e  mov     r9d, edx
0x18006f951  mov     rsi, r8
0x18006f954  movzx   edx, cl
0x18006f957  lea     r8, [rsp+400h+var_3C8+8]
0x18006f95c  mov     ecx, r9d
0x18006f95f  movups  xmmword ptr [rsp+400h+var_3C8+8], xmm0
0x18006f964  call    ?GetEventDescriptor@@YAHW4_TraceType@Trace@@EPEAU_EVENT_DESCRIPTOR@@@Z; GetEventDescriptor(Trace::_TraceType,uchar,_EVENT_DESCRIPTOR *)
0x18006f969  test    eax, eax
0x18006f96b  jnz     short loc_18006F9A6
0x18006f96d  mov     [rsp+400h+dwFlags], edx
0x18006f971  lea     r8, aNoEventIsDefin; "No Event is defined in the manifest for"...
0x18006f978  mov     edx, 105h; unsigned __int64
0x18006f97d  lea     rcx, [rbp+300h+var_260]; wchar_t *
0x18006f984  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18006f989  test    eax, eax
0x18006f98b  js      short loc_18006F9A6
0x18006f98d  mov     rcx, cs:?handle@@3_KA; unsigned __int64 handle
0x18006f994  lea     r9, [rbp+300h+var_260]
0x18006f99b  xor     r8d, r8d
0x18006f99e  xor     edx, edx
0x18006f9a0  call    cs:__imp_EtwEventWriteString
0x18006f9a6  movaps  xmm6, xmmword ptr [rsp+400h+var_3C8+8]
0x18006f9ab  lea     rdx, [rsp+400h+var_3C8+8]
0x18006f9b0  mov     rcx, cs:?handle@@3_KA; unsigned __int64 handle
0x18006f9b7  movdqa  xmmword ptr [rsp+400h+var_3C8+8], xmm6
0x18006f9bd  call    cs:__imp_EtwEventEnabled
0x18006f9c3  test    al, al
0x18006f9c5  jz      loc_18006FAB3
0x18006f9cb  mov     edi, 0A0h
0x18006f9d0  mov     [rsp+400h+var_3C8+8], 0
0x18006f9d9  lea     r13, [rbp+300h+arg_28]
0x18006f9e0  mov     dword ptr [rsp+400h+var_3C8], r14d
0x18006f9e5  lea     rax, aWsD; "%ws (%d): "
0x18006f9ec  mov     qword ptr [rsp+400h+var_3D0], rsi
0x18006f9f1  lea     r9, [rsp+400h+var_3A8]; unsigned __int64 *
0x18006f9f6  mov     [rsp+400h+var_3D8], rax; wchar_t *
0x18006f9fb  lea     r8, [rsp+400h+var_3C8+8]; wchar_t **
0x18006fa00  mov     edx, edi; cchDest
0x18006fa02  mov     rcx, rbx; pszDest
0x18006fa05  mov     [rsp+400h+dwFlags], 100h; dwFlags
0x18006fa0d  mov     [rsp+400h+var_3C8+8], 0
0x18006fa16  mov     [rsp+400h+var_3A8], 0
0x18006fa1f  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x18006fa24  cmp     eax, 8007007Ah
0x18006fa29  jnz     short loc_18006FA57
0x18006fa2b  lea     rax, [rsp+400h+hMem]
0x18006fa30  cmp     rbx, rax
0x18006fa33  jz      short loc_18006FA3E
0x18006fa35  mov     rcx, rbx; hMem
0x18006fa38  call    cs:__imp_LocalFree
0x18006fa3e  add     edi, edi
0x18006fa40  xor     ecx, ecx; uFlags
0x18006fa42  mov     edx, edi
0x18006fa44  add     rdx, rdx; uBytes
0x18006fa47  call    cs:__imp_LocalAlloc
0x18006fa4d  mov     rbx, rax
0x18006fa50  mov     [rsp+400h+var_3B0], rax
0x18006fa55  jmp     short loc_18006FA7B
0x18006fa57  mov     r8, [rbp+300h+arg_20]; wchar_t *
0x18006fa5e  mov     r9, r13; char *
0x18006fa61  mov     rdx, [rsp+400h+var_3A8]; unsigned __int64
0x18006fa66  mov     rcx, [rsp+400h+var_3C8+8]; wchar_t *
0x18006fa6b  call    ?StringCchVPrintfW@@YAJPEA_W_KPEB_WPEAD@Z; StringCchVPrintfW(wchar_t *,unsigned __int64,wchar_t const *,char *)
0x18006fa70  cmp     eax, 8007007Ah
0x18006fa75  jz      short loc_18006FA2B
0x18006fa77  test    eax, eax
0x18006fa79  jz      short loc_18006FA84
0x18006fa7b  test    rbx, rbx
0x18006fa7e  jnz     loc_18006F9E0
0x18006fa84  test    rbx, rbx
0x18006fa87  jz      short loc_18006FAB3
0x18006fa89  lea     r8, [rsp+400h+var_3B0]
0x18006fa8e  movdqa  xmmword ptr [rsp+400h+var_3C8+8], xmm6
0x18006fa94  lea     rcx, [rsp+400h+var_3C8+8]
0x18006fa99  call    WriteEventEx
0x18006fa9e  mov     rcx, [rsp+400h+var_3B0]; hMem
0x18006faa3  lea     rax, [rsp+400h+hMem]
0x18006faa8  cmp     rcx, rax
0x18006faab  jz      short loc_18006FAB3
0x18006faad  call    cs:__imp_LocalFree
0x18006fab3  mov     rcx, [rbp+300h+var_50]
0x18006faba  xor     rcx, rsp; StackCookie
0x18006fabd  call    __security_check_cookie
0x18006fac2  movaps  xmm6, [rsp+400h+var_48+8]
0x18006faca  add     rsp, 3D8h
0x18006fad1  pop     r14
0x18006fad3  pop     r13
0x18006fad5  pop     rdi
0x18006fad6  pop     rsi
0x18006fad7  pop     rbx
0x18006fad8  pop     rbp
0x18006fad9  retn
```
