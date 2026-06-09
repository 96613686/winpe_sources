# CIsoBurnUI::_GetErrorString(long,ushort *,uint)

- ea: `0x14000bbb0`
- end: `0x14000bd41`
- name: `?_GetErrorString@CIsoBurnUI@@CAXJPEAGI@Z`
- size: `401`
- prototype: `void __fastcall(DWORD dwMessageId, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000af38`

## callees

- `0x140001fa0`
- `0x140009098`
- `0x14000bbb0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000bcc2`
- `KERNEL32!LocalFree` at `0x14000bcc2`
- `KERNEL32!FormatMessageW` at `0x14000bc31`
- `KERNEL32!FormatMessageW` at `0x14000bc31`
- `KERNEL32!GetModuleHandleW` at `0x14000bc0a`
- `KERNEL32!GetModuleHandleW` at `0x14000bc0a`
- `USER32!LoadStringW` at `0x14000bc95`
- `USER32!LoadStringW` at `0x14000bce1`
- `USER32!LoadStringW` at `0x14000bd19`
- `USER32!LoadStringW` at `0x14000bc95`
- `USER32!LoadStringW` at `0x14000bce1`
- `USER32!LoadStringW` at `0x14000bd19`

## string_xrefs

- `0x14000bbfe`: `imapi2.dll`

## pseudocode

```c
void __fastcall CIsoBurnUI::_GetErrorString(DWORD dwMessageId, unsigned __int16 *a2)
{
  unsigned int i; // eax
  HMODULE ModuleHandleW; // rax
  DWORD v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  LPWSTR lpBuffer; // [rsp+20h] [rbp-E0h]
  WCHAR Buffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v11[1024]; // [rsp+50h] [rbp-B0h] BYREF

  *a2 = 0;
  for ( i = 0; i < 0xB; ++i )
  {
    if ( LODWORD(qword_140012930[i]) == dwMessageId )
    {
      LoadStringW(hInstance, HIDWORD(qword_140012930[i]), a2, 1024);
      return;
    }
  }
  *(_QWORD *)Buffer = 0;
  ModuleHandleW = GetModuleHandleW(L"imapi2.dll");
  v6 = FormatMessageW(0x900u, ModuleHandleW, dwMessageId, 0, Buffer, 0, 0);
  v11[0] = 0;
  if ( v6 )
  {
    v7 = *(_QWORD *)Buffer;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v8) );
    while ( (int)v8 > 0 )
    {
      if ( *(_WORD *)(v7 + 2LL * (unsigned int)v8 - 2) == 10 || *(_WORD *)(v7 + 2LL * (unsigned int)v8 - 2) == 13 )
      {
        *(_WORD *)(v7 + 2LL * (unsigned int)v8 - 2) = 0;
        v7 = *(_QWORD *)Buffer;
      }
      LODWORD(v8) = v8 - 1;
    }
    LoadStringW(hInstance, 0x118u, v11, 1024);
    if ( v11[0] )
    {
      LODWORD(lpBuffer) = dwMessageId;
      StringCchPrintfW(a2, 0x400u, v11, *(_QWORD *)Buffer, lpBuffer);
    }
    LocalFree(*(HLOCAL *)Buffer);
  }
  else
  {
    LoadStringW(hInstance, 0x119u, v11, 1024);
    if ( v11[0] )
      StringCchPrintfW(a2, 0x400u, v11, dwMessageId);
  }
}

```

## disassembly

```asm
0x14000bbb0  mov     [rsp-8+arg_10], rbx
0x14000bbb5  push    rbp
0x14000bbb6  push    rsi
0x14000bbb7  push    rdi
0x14000bbb8  lea     rbp, [rsp-760h]
0x14000bbc0  sub     rsp, 860h
0x14000bbc7  mov     rax, cs:__security_cookie
0x14000bbce  xor     rax, rsp
0x14000bbd1  mov     [rbp+770h+var_20], rax
0x14000bbd8  xor     esi, esi
0x14000bbda  mov     ebx, ecx
0x14000bbdc  mov     [rdx], si
0x14000bbdf  lea     rcx, qword_140012930
0x14000bbe6  mov     eax, esi
0x14000bbe8  mov     rdi, rdx
0x14000bbeb  movsxd  rdx, eax
0x14000bbee  cmp     [rcx+rdx*8], ebx
0x14000bbf1  jz      loc_14000BD05
0x14000bbf7  inc     eax
0x14000bbf9  cmp     eax, 0Bh
0x14000bbfc  jb      short loc_14000BBEB
0x14000bbfe  lea     rcx, aImapi2Dll; "imapi2.dll"
0x14000bc05  mov     qword ptr [rsp+870h+Buffer], rsi
0x14000bc0a  call    cs:__imp_GetModuleHandleW
0x14000bc10  mov     [rsp+870h+Arguments], rsi; Arguments
0x14000bc15  xor     r9d, r9d; dwLanguageId
0x14000bc18  mov     rdx, rax; lpSource
0x14000bc1b  mov     [rsp+870h+nSize], esi; nSize
0x14000bc1f  lea     rax, [rsp+870h+Buffer]
0x14000bc24  mov     r8d, ebx; dwMessageId
0x14000bc27  mov     ecx, 900h; dwFlags
0x14000bc2c  mov     [rsp+870h+lpBuffer], rax; lpBuffer
0x14000bc31  call    cs:__imp_FormatMessageW
0x14000bc37  mov     [rsp+870h+var_820], si
0x14000bc3c  test    eax, eax
0x14000bc3e  jz      loc_14000BCCA
0x14000bc44  mov     rdx, qword ptr [rsp+870h+Buffer]
0x14000bc49  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000bc4d  inc     rcx
0x14000bc50  cmp     [rdx+rcx*2], si
0x14000bc54  jnz     short loc_14000BC4D
0x14000bc56  jmp     short loc_14000BC7A
0x14000bc58  mov     r8d, ecx
0x14000bc5b  cmp     word ptr [rdx+r8*2-2], 0Ah
0x14000bc62  jz      short loc_14000BC6D
0x14000bc64  cmp     word ptr [rdx+r8*2-2], 0Dh
0x14000bc6b  jnz     short loc_14000BC78
0x14000bc6d  mov     [rdx+r8*2-2], si
0x14000bc73  mov     rdx, qword ptr [rsp+870h+Buffer]
0x14000bc78  dec     ecx
0x14000bc7a  test    ecx, ecx
0x14000bc7c  jg      short loc_14000BC58
0x14000bc7e  mov     rcx, cs:hInstance; hInstance
0x14000bc85  lea     r8, [rsp+870h+var_820]; lpBuffer
0x14000bc8a  mov     r9d, 400h; cchBufferMax
0x14000bc90  mov     edx, 118h; uID
0x14000bc95  call    cs:__imp_LoadStringW
0x14000bc9b  cmp     [rsp+870h+var_820], si
0x14000bca0  jz      short loc_14000BCBD
0x14000bca2  mov     r9, qword ptr [rsp+870h+Buffer]
0x14000bca7  lea     r8, [rsp+870h+var_820]; unsigned __int16 *
0x14000bcac  mov     edx, 400h; unsigned __int64
0x14000bcb1  mov     dword ptr [rsp+870h+lpBuffer], ebx
0x14000bcb5  mov     rcx, rdi; unsigned __int16 *
0x14000bcb8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000bcbd  mov     rcx, qword ptr [rsp+870h+Buffer]; hMem
0x14000bcc2  call    cs:__imp_LocalFree
0x14000bcc8  jmp     short loc_14000BD1F
0x14000bcca  mov     rcx, cs:hInstance; hInstance
0x14000bcd1  lea     r8, [rsp+870h+var_820]; lpBuffer
0x14000bcd6  mov     r9d, 400h; cchBufferMax
0x14000bcdc  mov     edx, 119h; uID
0x14000bce1  call    cs:__imp_LoadStringW
0x14000bce7  cmp     [rsp+870h+var_820], si
0x14000bcec  jz      short loc_14000BD1F
0x14000bcee  mov     r9d, ebx
0x14000bcf1  lea     r8, [rsp+870h+var_820]; unsigned __int16 *
0x14000bcf6  mov     edx, 400h; unsigned __int64
0x14000bcfb  mov     rcx, rdi; unsigned __int16 *
0x14000bcfe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000bd03  jmp     short loc_14000BD1F
0x14000bd05  mov     edx, [rcx+rdx*8+4]; uID
0x14000bd09  mov     r9d, 400h; cchBufferMax
0x14000bd0f  mov     rcx, cs:hInstance; hInstance
0x14000bd16  mov     r8, rdi; lpBuffer
0x14000bd19  call    cs:__imp_LoadStringW
0x14000bd1f  mov     rcx, [rbp+770h+var_20]
0x14000bd26  xor     rcx, rsp; StackCookie
0x14000bd29  call    __security_check_cookie
0x14000bd2e  mov     rbx, [rsp+870h+arg_10]
0x14000bd36  add     rsp, 860h
0x14000bd3d  pop     rdi
0x14000bd3e  pop     rsi
0x14000bd3f  pop     rbp
0x14000bd40  retn
```
