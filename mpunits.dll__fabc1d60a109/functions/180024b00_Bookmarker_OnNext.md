# Bookmarker_OnNext

- ea: `0x180024b00`
- end: `0x180024d6f`
- name: `Bookmarker_OnNext`
- size: `623`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180024b00`
- `0x18004484e`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024bf7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024bf7`
- `miutils!Instance_New` at `0x180024c39`
- `miutils!Instance_New` at `0x180024c39`

## string_xrefs

- `0x180024c11`: `MSFT_DSCConfigurationOutput`

## pseudocode

```c
__int64 __fastcall Bookmarker_OnNext(__int64 a1, __int128 *a2)
{
  bool v3; // zf
  __int64 v4; // rbx
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int64 v8; // rcx
  __int64 *v9; // rcx
  __int64 *v10; // rax
  int v11; // eax
  __int64 result; // rax
  __int64 *v13; // [rsp+30h] [rbp-59h] BYREF
  __int64 v14; // [rsp+38h] [rbp-51h] BYREF
  _QWORD v15[2]; // [rsp+40h] [rbp-49h] BYREF
  int v16; // [rsp+50h] [rbp-39h]
  int v17; // [rsp+54h] [rbp-35h]
  _OWORD v18[2]; // [rsp+60h] [rbp-29h] BYREF
  __int64 v19; // [rsp+80h] [rbp-9h]
  _OWORD v20[3]; // [rsp+88h] [rbp-1h] BYREF
  __int64 v21; // [rsp+B8h] [rbp+2Fh]
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+C0h] [rbp+37h] BYREF

  v3 = *((_DWORD *)a2 + 10) == 15;
  v4 = a1;
  *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
  v19 = 0;
  v5 = *a2;
  v13 = 0;
  memset(v18, 0, sizeof(v18));
  v6 = a2[1];
  v20[0] = v5;
  v7 = a2[2];
  v20[1] = v6;
  *(_QWORD *)&v6 = *((_QWORD *)a2 + 6);
  v20[2] = v7;
  v21 = v6;
  if ( !v3 || !*(_QWORD *)a2 )
    return ObserverProtocol_PostErrorAndDispose(a1);
  if ( NITS_PRESENCE_STUB != 1 )
  {
    v16 = 59;
    v15[0] = "Bookmarker_OnNext";
    v17 = 10000;
    v15[1] = "admin\\wmi\\winomi\\mp\\etw\\bookmarker.c";
    if ( ((unsigned int (__fastcall *)(_QWORD *, __int64))NITS_STUB[0])(v15, 1) )
      goto LABEL_5;
  }
  DWORD2(v18[0]) = 16;
  *(_QWORD *)&v18[0] = SystemTimeAsFileTime;
  SystemTimeAsFileTime[0] = (struct _FILETIME)_InterlockedIncrement64((volatile signed __int64 *)(v4 + 152));
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime[1]);
  v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 8LL) + 56LL);
  if ( v8 && !wcscmp_0(*(const wchar_t **)(v8 + 8), L"MSFT_DSCConfigurationOutput") )
  {
    v9 = v13;
    v10 = *(__int64 **)&v20[0];
  }
  else
  {
    if ( (unsigned int)Instance_New(&MSFT_DSCConfigurationOutputWriteObject_rtti, &v13) )
    {
      a1 = v4;
      return ObserverProtocol_PostErrorAndDispose(a1);
    }
    v14 = *(_QWORD *)a2;
    v11 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v13 + 80))(v13, 2, &v14);
    v9 = v13;
    if ( v11 )
      goto LABEL_12;
    v10 = v13;
    *(_QWORD *)&v20[0] = v13;
  }
  if ( !v10 || !*v10 )
  {
LABEL_12:
    if ( v9 )
    {
      if ( *v9 )
        (*(void (__fastcall **)(__int64 *))(*v9 + 16))(v9);
    }
LABEL_5:
    a1 = v4;
    return ObserverProtocol_PostErrorAndDispose(a1);
  }
  if ( (*(unsigned int (__fastcall **)(__int64 *, const wchar_t *, _OWORD *, __int64, int))(*v10 + 72))(
         v10,
         L"Bookmark",
         v18,
         17,
         0x40000000) )
  {
    v9 = v13;
    goto LABEL_12;
  }
  _InterlockedIncrement64(&g_bookmarkerNumberOnNextsFromLastInstantiation);
  result = ((__int64 (__fastcall *)(__int64, _OWORD *))ObserverProtocol_PostNext)(v4, v20);
  if ( v13 )
  {
    result = *v13;
    if ( *v13 )
      return (*(__int64 (**)(void))(result + 16))();
  }
  return result;
}

```

## disassembly

```asm
0x180024b00  mov     [rsp-8+arg_10], rbx
0x180024b05  mov     [rsp-8+arg_18], rdi
0x180024b0a  push    rbp
0x180024b0b  lea     rbp, [rsp-57h]
0x180024b10  sub     rsp, 0E0h
0x180024b17  mov     rax, cs:__security_cookie
0x180024b1e  xor     rax, rsp
0x180024b21  mov     [rbp+57h+var_10], rax
0x180024b25  xorps   xmm1, xmm1
0x180024b28  xorps   xmm0, xmm0
0x180024b2b  xor     eax, eax
0x180024b2d  mov     rdi, rdx
0x180024b30  cmp     dword ptr [rdx+28h], 0Fh
0x180024b34  mov     rbx, rcx
0x180024b37  movups  xmmword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x180024b3b  mov     [rbp+57h+var_60], rax
0x180024b3f  movups  xmm0, xmmword ptr [rdx]
0x180024b42  mov     [rbp+57h+var_B0], rax
0x180024b46  movups  [rbp+57h+var_80], xmm1
0x180024b4a  movups  [rbp+57h+var_70], xmm1
0x180024b4e  movups  xmm1, xmmword ptr [rdx+10h]
0x180024b52  movups  [rbp+57h+var_58], xmm0
0x180024b56  movups  xmm0, xmmword ptr [rdx+20h]
0x180024b5a  movups  [rbp+57h+var_48], xmm1
0x180024b5e  movsd   xmm1, qword ptr [rdx+30h]
0x180024b63  movups  [rbp+57h+var_38], xmm0
0x180024b67  movsd   [rbp+57h+var_28], xmm1
0x180024b6c  jnz     loc_180024D36
0x180024b72  cmp     [rdx], rax
0x180024b75  jz      loc_180024D36
0x180024b7b  cmp     cs:NITS_PRESENCE_STUB, 1
0x180024b83  jz      short loc_180024BCF
0x180024b85  lea     rax, aBookmarkerOnne; "Bookmarker_OnNext"
0x180024b8c  mov     [rbp+57h+var_90], 3Bh ; ';'
0x180024b93  mov     [rbp+57h+var_A0], rax
0x180024b97  lea     rcx, [rbp+57h+var_A0]
0x180024b9b  lea     rax, aAdminWmiWinomi_13; "admin\\wmi\\winomi\\mp\\etw\\bookmarker"...
0x180024ba2  mov     [rbp+57h+var_8C], 2710h
0x180024ba9  mov     [rbp+57h+var_98], rax
0x180024bad  mov     edx, 1
0x180024bb2  mov     rax, cs:NITS_STUB
0x180024bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bbe  test    eax, eax
0x180024bc0  jz      short loc_180024BCF
0x180024bc2  mov     edx, 15h
0x180024bc7  mov     rcx, rbx
0x180024bca  jmp     loc_180024D3B
0x180024bcf  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x180024bd3  mov     dword ptr [rbp+57h+var_80+8], 10h
0x180024bda  mov     qword ptr [rbp+57h+var_80], rax
0x180024bde  mov     eax, 1
0x180024be3  lock xadd [rbx+98h], rax
0x180024bec  inc     rax
0x180024bef  lea     rcx, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x180024bf3  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180024bf7  call    cs:__imp_GetSystemTimeAsFileTime
0x180024bfd  mov     rax, [rdi]
0x180024c00  mov     rcx, [rax+8]
0x180024c04  mov     rcx, [rcx+38h]
0x180024c08  test    rcx, rcx
0x180024c0b  jz      short loc_180024C2E
0x180024c0d  mov     rcx, [rcx+8]; String1
0x180024c11  lea     rdx, aMsftDscconfigu_2; "MSFT_DSCConfigurationOutput"
0x180024c18  call    wcscmp_0
0x180024c1d  test    eax, eax
0x180024c1f  jnz     short loc_180024C2E
0x180024c21  mov     rcx, [rbp+57h+var_B0]
0x180024c25  mov     rax, qword ptr [rbp+57h+var_58]
0x180024c29  jmp     loc_180024CB3
0x180024c2e  lea     rdx, [rbp+57h+var_B0]
0x180024c32  lea     rcx, MSFT_DSCConfigurationOutputWriteObject_rtti
0x180024c39  call    cs:__imp_Instance_New
0x180024c3f  mov     edx, eax
0x180024c41  test    eax, eax
0x180024c43  jz      short loc_180024C58
0x180024c45  mov     rcx, cs:off_180047BB0
0x180024c4c  mov     rax, [rcx+60h]
0x180024c50  mov     rcx, rbx
0x180024c53  jmp     loc_180024D46
0x180024c58  mov     rax, [rdi]
0x180024c5b  lea     r8, [rbp+57h+var_A8]
0x180024c5f  mov     rcx, [rbp+57h+var_B0]
0x180024c63  mov     r9d, 0Fh
0x180024c69  mov     [rbp+57h+var_A8], rax
0x180024c6d  mov     [rsp+0E0h+var_C0], 40000000h
0x180024c75  mov     rax, [rcx]
0x180024c78  lea     edx, [r9-0Dh]
0x180024c7c  mov     rax, [rax+50h]
0x180024c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c85  mov     rcx, [rbp+57h+var_B0]
0x180024c89  mov     edi, eax
0x180024c8b  test    eax, eax
0x180024c8d  jz      short loc_180024CAC
0x180024c8f  test    rcx, rcx
0x180024c92  jz      short loc_180024CA5
0x180024c94  mov     rax, [rcx]
0x180024c97  test    rax, rax
0x180024c9a  jz      short loc_180024CA5
0x180024c9c  mov     rax, [rax+10h]
0x180024ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ca5  mov     edx, edi
0x180024ca7  jmp     loc_180024BC7
0x180024cac  mov     rax, rcx
0x180024caf  mov     qword ptr [rbp+57h+var_58], rcx
0x180024cb3  test    rax, rax
0x180024cb6  jz      short loc_180024D2C
0x180024cb8  mov     r10, [rax]
0x180024cbb  test    r10, r10
0x180024cbe  jz      short loc_180024D2C
0x180024cc0  mov     rcx, rax
0x180024cc3  mov     [rsp+0E0h+var_C0], 40000000h
0x180024ccb  mov     rax, [r10+48h]
0x180024ccf  lea     r8, [rbp+57h+var_80]
0x180024cd3  mov     r9d, 11h
0x180024cd9  lea     rdx, aBookmark; "Bookmark"
0x180024ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ce5  mov     edi, eax
0x180024ce7  test    eax, eax
0x180024ce9  jz      short loc_180024CF1
0x180024ceb  mov     rcx, [rbp+57h+var_B0]
0x180024cef  jmp     short loc_180024C8F
0x180024cf1  lock inc cs:g_bookmarkerNumberOnNextsFromLastInstantiation
0x180024cf9  mov     rax, cs:off_180047BB0
0x180024d00  lea     rdx, [rbp+57h+var_58]
0x180024d04  mov     rcx, rbx
0x180024d07  mov     rax, [rax+20h]
0x180024d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d10  mov     rcx, [rbp+57h+var_B0]
0x180024d14  test    rcx, rcx
0x180024d17  jz      short loc_180024D4E
0x180024d19  mov     rax, [rcx]
0x180024d1c  test    rax, rax
0x180024d1f  jz      short loc_180024D4E
0x180024d21  mov     rax, [rax+10h]
0x180024d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d2a  jmp     short loc_180024D4E
0x180024d2c  mov     edi, 4
0x180024d31  jmp     loc_180024C8F
0x180024d36  mov     edx, 4
0x180024d3b  mov     rax, cs:off_180047BB0
0x180024d42  mov     rax, [rax+60h]
0x180024d46  xor     r8d, r8d
0x180024d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d4e  mov     rcx, [rbp+57h+var_10]
0x180024d52  xor     rcx, rsp; StackCookie
0x180024d55  call    __security_check_cookie
0x180024d5a  lea     r11, [rsp+0E0h+var_s0]
0x180024d62  mov     rbx, [r11+20h]
0x180024d66  mov     rdi, [r11+28h]
0x180024d6a  mov     rsp, r11
0x180024d6d  pop     rbp
0x180024d6e  retn
```
