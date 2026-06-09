# sub_180FCAD7

- ea: `0x180fcad7`
- end: `0x180fccd7`
- name: `sub_180FCAD7`
- size: `512`
- prototype: `int __thiscall(void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x180fcd03`

## callees

- `0x18007b40`
- `0x18007bb2`
- `0x18014c2c`
- `0x1801e56e`
- `0x1801e660`
- `0x18031d31`
- `0x180dccd4`
- `0x180fcad7`
- `0x18127b28`
- `0x18127c1c`
- `0x18127c66`
- `0x18128056`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180fcb99`
- `KERNEL32!HeapFree` at `0x180fcc50`
- `KERNEL32!HeapFree` at `0x180fcb99`
- `KERNEL32!HeapFree` at `0x180fcc50`
- `KERNEL32!HeapAlloc` at `0x180fcbac`
- `KERNEL32!HeapAlloc` at `0x180fcbac`
- `KERNEL32!GetProcessHeap` at `0x180fcb92`
- `KERNEL32!GetProcessHeap` at `0x180fcba2`
- `KERNEL32!GetProcessHeap` at `0x180fcc49`
- `KERNEL32!GetProcessHeap` at `0x180fcb92`
- `KERNEL32!GetProcessHeap` at `0x180fcba2`
- `KERNEL32!GetProcessHeap` at `0x180fcc49`
- `KERNEL32!LoadLibraryW` at `0x180fcc85`
- `KERNEL32!LoadLibraryW` at `0x180fcc85`
- `KERNEL32!GetProcAddress` at `0x180fccc0`
- `KERNEL32!GetProcAddress` at `0x180fccc0`

## string_xrefs

- `0x180fcc80`: `Iphlpapi.dll`

## pseudocode

```c
_DWORD *__thiscall sub_180FCAD7(_DWORD *this)
{
  int v2; // esi
  SIZE_T v3; // esi
  ULONG (__stdcall *v4)(PIP_ADAPTER_INFO, PULONG); // ecx
  int v5; // eax
  HANDLE v6; // eax
  HANDLE ProcessHeap; // eax
  char *v8; // edi
  void *v9; // ecx
  HANDLE v10; // eax
  const char *v12; // [esp-4h] [ebp-54h]
  void *Block[5]; // [esp+10h] [ebp-40h] BYREF
  unsigned int v14; // [esp+24h] [ebp-2Ch]
  void *v15; // [esp+28h] [ebp-28h] BYREF
  _BYTE Src[24]; // [esp+2Ch] [ebp-24h] BYREF
  unsigned int v17; // [esp+44h] [ebp-Ch] BYREF
  unsigned int i; // [esp+48h] [ebp-8h] BYREF

  v12 = "{deadbeef-fade-dead-c0de-cafebabefeed}";
  *this = 0;
  this[4] = 0;
  this[5] = 15;
  _mm_lfence();
  LOBYTE(v15) = 0;
  sub_1801E660(0x26u, (int)v15, (int)v12);
  v2 = *((_DWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + TlsIndex);
  if ( dword_181EF9F4 > *(_DWORD *)(v2 + 4) )
  {
    _Init_thread_header(&dword_181EF9F4);
    if ( dword_181EF9F4 == -1 )
    {
      dword_181EF9F8 = LoadLibraryW(L"Iphlpapi.dll");
      _Init_thread_footer(&dword_181EF9F4);
    }
  }
  if ( dword_181EF9F8 )
  {
    if ( dword_181EF9FC > *(_DWORD *)(v2 + 4) )
    {
      _Init_thread_header(&dword_181EF9FC);
      if ( dword_181EF9FC == -1 )
      {
        GetAdaptersInfo = (ULONG (__stdcall *)(PIP_ADAPTER_INFO, PULONG))GetProcAddress(
                                                                           dword_181EF9F8,
                                                                           "GetAdaptersInfo");
        _Init_thread_footer(&dword_181EF9FC);
      }
    }
    if ( GetAdaptersInfo )
    {
      v3 = 648;
      for ( i = 648; ; v3 = i )
      {
        ProcessHeap = GetProcessHeap();
        v8 = (char *)HeapAlloc(ProcessHeap, 0, v3);
        if ( !v8 )
          break;
        v4 = GetAdaptersInfo;
        v8[8] = 0;
        v5 = ((int (__thiscall *)(ULONG (__stdcall *)(PIP_ADAPTER_INFO, PULONG), char *, unsigned int *))v4)(v4, v8, &i);
        if ( v5 != 111 )
        {
          if ( !v5 && v8 != (char *)-8 )
          {
            Block[0] = 0;
            Block[4] = 0;
            v14 = 15;
            sub_1801E56E(Block, v8 + 8, strlen(v8 + 8));
            sub_180DCCD4(Src, Block);
            if ( v14 >= 0x10 )
            {
              v9 = Block[0];
              v17 = v14 + 1;
              v15 = Block[0];
              if ( v14 + 1 >= 0x1000 )
              {
                std::_Adjust_manually_vector_aligned(&v15, &v17);
                v9 = v15;
              }
              sub_18128056(v9);
            }
            sub_18031D31(this, Src);
            unknown_libname_4(Src);
          }
LABEL_18:
          v10 = GetProcessHeap();
          HeapFree(v10, 0, v8);
          return this;
        }
        if ( i <= 0x288 )
          goto LABEL_18;
        v6 = GetProcessHeap();
        HeapFree(v6, 0, v8);
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180fcad7  push    ebp
0x180fcad8  mov     ebp, esp
0x180fcada  sub     esp, 44h
0x180fcadd  mov     eax, ___security_cookie
0x180fcae2  xor     eax, ebp
0x180fcae4  mov     [ebp+var_4], eax
0x180fcae7  push    ebx
0x180fcae8  mov     ebx, ecx
0x180fcaea  xor     eax, eax
0x180fcaec  push    esi
0x180fcaed  push    edi
0x180fcaee  push    offset aDeadbeefFadeDe; "{deadbeef-fade-dead-c0de-cafebabefeed}"
0x180fcaf3  mov     [ebx], eax
0x180fcaf5  mov     [ebx+10h], eax
0x180fcaf8  mov     dword ptr [ebx+14h], 0Fh
0x180fcaff  lfence
0x180fcb02  mov     byte ptr [ebp+var_28], al
0x180fcb05  push    [ebp+var_28]; int
0x180fcb08  push    26h ; '&'; Size
0x180fcb0a  call    sub_1801E660
0x180fcb0f  mov     eax, large fs:2Ch
0x180fcb15  mov     ecx, TlsIndex
0x180fcb1b  mov     esi, [eax+ecx*4]
0x180fcb1e  mov     eax, dword_181EF9F4
0x180fcb23  cmp     eax, [esi+4]
0x180fcb29  jg      loc_180FCC67
0x180fcb2f  cmp     dword_181EF9F8, 0
0x180fcb36  jz      loc_180FCC56
0x180fcb3c  mov     eax, dword_181EF9FC
0x180fcb41  cmp     eax, [esi+4]
0x180fcb47  jg      loc_180FCC9C
0x180fcb4d  cmp     GetAdaptersInfo, 0
0x180fcb54  jz      loc_180FCC56
0x180fcb5a  mov     esi, 288h
0x180fcb5f  mov     [ebp+var_8], esi
0x180fcb62  jmp     short loc_180FCBA2
0x180fcb64  mov     esi, GetAdaptersInfo
0x180fcb6a  lea     eax, [ebp+var_8]
0x180fcb6d  push    eax
0x180fcb6e  push    edi
0x180fcb6f  mov     ecx, esi
0x180fcb71  mov     byte ptr [edi+8], 0
0x180fcb75  call    ds:___guard_check_icall_fptr
0x180fcb7b  call    esi ; GetAdaptersInfo
0x180fcb7d  cmp     eax, 6Fh ; 'o'
0x180fcb80  jnz     short loc_180FCBBD
0x180fcb82  cmp     [ebp+var_8], 288h
0x180fcb89  jbe     loc_180FCC46
0x180fcb8f  push    edi; lpMem
0x180fcb90  push    0; dwFlags
0x180fcb92  call    ds:GetProcessHeap
0x180fcb98  push    eax; hHeap
0x180fcb99  call    ds:HeapFree
0x180fcb9f  mov     esi, [ebp+var_8]
0x180fcba2  call    ds:GetProcessHeap
0x180fcba8  push    esi; dwBytes
0x180fcba9  push    0; dwFlags
0x180fcbab  push    eax; hHeap
0x180fcbac  call    ds:HeapAlloc
0x180fcbb2  mov     edi, eax
0x180fcbb4  test    edi, edi
0x180fcbb6  jnz     short loc_180FCB64
0x180fcbb8  jmp     loc_180FCC56
0x180fcbbd  test    eax, eax
0x180fcbbf  jnz     loc_180FCC46
0x180fcbc5  lea     edx, [edi+8]
0x180fcbc8  test    edx, edx
0x180fcbca  jz      short loc_180FCC46
0x180fcbcc  and     [ebp+Block], eax
0x180fcbcf  mov     ecx, edx
0x180fcbd1  and     [ebp+var_30], eax
0x180fcbd4  mov     [ebp+var_2C], 0Fh
0x180fcbdb  lea     esi, [ecx+1]
0x180fcbde  mov     al, [ecx]
0x180fcbe0  inc     ecx
0x180fcbe1  test    al, al
0x180fcbe3  jnz     short loc_180FCBDE
0x180fcbe5  sub     ecx, esi
0x180fcbe7  push    ecx; Size
0x180fcbe8  push    edx; Src
0x180fcbe9  lea     ecx, [ebp+Block]; void *
0x180fcbec  call    sub_1801E56E
0x180fcbf1  lea     edx, [ebp+Block]
0x180fcbf4  lea     ecx, [ebp+Src]
0x180fcbf7  call    sub_180DCCD4
0x180fcbfc  mov     eax, [ebp+var_2C]
0x180fcbff  cmp     eax, 10h
0x180fcc02  jb      short loc_180FCC33
0x180fcc04  mov     ecx, [ebp+Block]
0x180fcc07  inc     eax
0x180fcc08  mov     [ebp+var_C], eax
0x180fcc0b  mov     [ebp+var_28], ecx
0x180fcc0e  cmp     eax, 1000h
0x180fcc13  jb      short loc_180FCC2A
0x180fcc15  lea     eax, [ebp+var_C]
0x180fcc18  push    eax; unsigned int *
0x180fcc19  lea     eax, [ebp+var_28]
0x180fcc1c  push    eax; void **
0x180fcc1d  call    ?_Adjust_manually_vector_aligned@std@@YAXAAPAXAAI@Z; std::_Adjust_manually_vector_aligned(void * &,uint &)
0x180fcc22  mov     eax, [ebp+var_C]
0x180fcc25  pop     ecx
0x180fcc26  pop     ecx
0x180fcc27  mov     ecx, [ebp+var_28]
0x180fcc2a  push    eax
0x180fcc2b  push    ecx; Block
0x180fcc2c  call    sub_18128056
0x180fcc31  pop     ecx
0x180fcc32  pop     ecx
0x180fcc33  lea     eax, [ebp+Src]
0x180fcc36  mov     ecx, ebx; void *
0x180fcc38  push    eax; Src
0x180fcc39  call    sub_18031D31
0x180fcc3e  lea     ecx, [ebp+Src]
0x180fcc41  call    unknown_libname_4; Microsoft VisualC 14/net runtime
0x180fcc46  push    edi; lpMem
0x180fcc47  push    0; dwFlags
0x180fcc49  call    ds:GetProcessHeap
0x180fcc4f  push    eax; hHeap
0x180fcc50  call    ds:HeapFree
0x180fcc56  mov     ecx, [ebp+var_4]
0x180fcc59  mov     eax, ebx
0x180fcc5b  pop     edi
0x180fcc5c  pop     esi
0x180fcc5d  xor     ecx, ebp; StackCookie
0x180fcc5f  pop     ebx
0x180fcc60  call    @__security_check_cookie@4; __security_check_cookie(x)
0x180fcc65  leave
0x180fcc66  retn
0x180fcc67  mov     edi, offset dword_181EF9F4
0x180fcc6c  push    edi
0x180fcc6d  call    __Init_thread_header
0x180fcc72  cmp     dword_181EF9F4, 0FFFFFFFFh
0x180fcc79  pop     ecx
0x180fcc7a  jnz     loc_180FCB2F
0x180fcc80  push    offset aIphlpapiDll_0; "Iphlpapi.dll"
0x180fcc85  call    ds:LoadLibraryW
0x180fcc8b  push    edi
0x180fcc8c  mov     dword_181EF9F8, eax
0x180fcc91  call    __Init_thread_footer
0x180fcc96  pop     ecx
0x180fcc97  jmp     loc_180FCB2F
0x180fcc9c  mov     esi, offset dword_181EF9FC
0x180fcca1  push    esi
0x180fcca2  call    __Init_thread_header
0x180fcca7  cmp     dword_181EF9FC, 0FFFFFFFFh
0x180fccae  pop     ecx
0x180fccaf  jnz     loc_180FCB4D
0x180fccb5  push    offset aGetadaptersinf; "GetAdaptersInfo"
0x180fccba  push    dword_181EF9F8; hModule
0x180fccc0  call    ds:GetProcAddress
0x180fccc6  push    esi
0x180fccc7  mov     GetAdaptersInfo, eax
0x180fcccc  call    __Init_thread_footer
0x180fccd1  pop     ecx
0x180fccd2  jmp     loc_180FCB4D
```
