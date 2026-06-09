# CMasterClock::UpdateClockList(void)

- ea: `0x18000b274`
- end: `0x18000b563`
- name: `?UpdateClockList@CMasterClock@@AEAAJXZ`
- size: `751`
- prototype: `__int64 __fastcall(CMasterClock *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18000a974`
- `0x18000aad0`
- `0x18000ae14`

## callees

- `0x1800012c4`
- `0x1800016d0`
- `0x1800021a8`
- `0x18000a70c`
- `0x18000b274`
- `0x180015f2c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18000b347`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18000b3f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18000b495`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18000b347`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18000b3f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18000b495`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b2f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b2f4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000b36e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000b41f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000b4be`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000b36e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000b41f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000b4be`

## pseudocode

```c
_BOOL8 __fastcall CMasterClock::UpdateClockList(CMasterClock *this)
{
  char *v1; // rdi
  __int64 i; // rax
  const struct _GUID *v4; // rdx
  int v5; // eax
  __int64 v6; // rbx
  _DWORD *v7; // rcx
  __int64 v8; // rsi
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v11[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+44h] [rbp-BCh]
  GUID v13; // [rsp+4Ch] [rbp-B4h]
  WCHAR WideCharStr[128]; // [rsp+5Ch] [rbp-A4h] BYREF
  int v15; // [rsp+15Ch] [rbp+5Ch]
  __int64 (__fastcall *v16)(struct IReferenceClock **, struct CMasterClock *); // [rsp+160h] [rbp+60h]
  _BYTE v17[4]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v18; // [rsp+174h] [rbp+74h]
  GUID v19; // [rsp+17Ch] [rbp+7Ch]
  WCHAR lpWideCharStr[128]; // [rsp+18Ch] [rbp+8Ch] BYREF
  int v21; // [rsp+28Ch] [rbp+18Ch]
  __int64 (__fastcall *v22)(); // [rsp+290h] [rbp+190h]
  _BYTE v23[4]; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v24; // [rsp+2A4h] [rbp+1A4h]
  GUID v25; // [rsp+2ACh] [rbp+1ACh]
  WCHAR v26[128]; // [rsp+2BCh] [rbp+1BCh] BYREF
  int v27; // [rsp+3BCh] [rbp+2BCh]
  void *v28; // [rsp+3C0h] [rbp+2C0h]
  CHAR Buffer[128]; // [rsp+3D0h] [rbp+2D0h] BYREF
  CHAR MultiByteStr[128]; // [rsp+450h] [rbp+350h] BYREF
  CHAR v31[128]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v1 = (char *)this + 32;
  for ( i = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 4) + 40LL))((char *)this + 32); i; i = *(_QWORD *)(i + 8) )
    **(_DWORD **)(i + 16) = 0;
  hObject[0] = 0;
  if ( !(unsigned int)LookForPortClock((__int64 *)hObject, v4) )
    goto LABEL_10;
  CloseHandle(hObject[0]);
  memset_0(v11, 0, 0x128u);
  v12 = 284;
  v15 = 1;
  v16 = CreatePcClock;
  v13 = GUID_SysClock;
  if ( LoadStringA(g_hModule, 0x3E8u, Buffer, 128) )
    MultiByteToWideChar(0, 0, Buffer, -1, WideCharStr, 128);
  else
    WideCharStr[0] = 0;
  v5 = CMasterClock::AddClock(this, (struct tagCLOCKENTRY *)v11);
  if ( v5 < 0 || v5 == 1 )
  {
LABEL_10:
    if ( !dword_18002A894 )
      dword_18002A894 = 1;
    memset_0(v17, 0, 0x128u);
    v18 = 296;
    v21 = 1;
    v22 = CreateSysClock;
    v19 = GUID_SysClock;
    if ( LoadStringA(g_hModule, 0x3E8u, MultiByteStr, 128) )
      MultiByteToWideChar(0, 0, MultiByteStr, -1, lpWideCharStr, 128);
    else
      lpWideCharStr[0] = 0;
    CMasterClock::AddClock(this, (struct tagCLOCKENTRY *)v17);
  }
  memset_0(v23, 0, 0x128u);
  v24 = 284;
  v27 = 0;
  v28 = &CreateDsClock;
  v25 = GUID_DsClock;
  if ( LoadStringA(g_hModule, 0x3E9u, v31, 128) )
    MultiByteToWideChar(0, 0, v31, -1, v26, 128);
  else
    v26[0] = 0;
  CMasterClock::AddClock(this, (struct tagCLOCKENTRY *)v23);
  v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v1 + 40LL))(v1);
  if ( v6 )
  {
    do
    {
      v7 = *(_DWORD **)(v6 + 16);
      v8 = *(_QWORD *)(v6 + 8);
      if ( !*v7 )
      {
        operator delete(v7);
        (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v1 + 16LL))(v1, v6);
      }
      v6 = v8;
    }
    while ( v8 );
  }
  return (*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v1 + 48LL))(v1) == 0;
}

```

## disassembly

```asm
0x18000b274  mov     [rsp-8+arg_8], rbx
0x18000b279  mov     [rsp-8+arg_10], rsi
0x18000b27e  push    rbp
0x18000b27f  push    rdi
0x18000b280  push    r13
0x18000b282  lea     rbp, [rsp-460h]
0x18000b28a  sub     rsp, 560h
0x18000b291  mov     rax, cs:__security_cookie
0x18000b298  xor     rax, rsp
0x18000b29b  mov     [rbp+470h+var_20], rax
0x18000b2a2  lea     rdi, [rcx+20h]
0x18000b2a6  mov     rbx, rcx
0x18000b2a9  mov     rax, [rdi]
0x18000b2ac  mov     rcx, rdi
0x18000b2af  mov     rax, [rax+28h]
0x18000b2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2b8  jmp     short loc_18000B2C8
0x18000b2ba  mov     rcx, [rax+10h]
0x18000b2be  mov     dword ptr [rcx], 0
0x18000b2c4  mov     rax, [rax+8]
0x18000b2c8  test    rax, rax
0x18000b2cb  jnz     short loc_18000B2BA
0x18000b2cd  lea     rcx, [rsp+570h+hObject]
0x18000b2d2  mov     [rsp+570h+hObject], rax
0x18000b2d7  call    LookForPortClock
0x18000b2dc  mov     esi, 80h
0x18000b2e1  mov     r13d, 128h
0x18000b2e7  test    eax, eax
0x18000b2e9  jz      loc_18000B397
0x18000b2ef  mov     rcx, [rsp+570h+hObject]; hObject
0x18000b2f4  call    cs:__imp_CloseHandle
0x18000b2fa  mov     r8d, r13d; Size
0x18000b2fd  lea     rcx, [rsp+570h+var_530]; void *
0x18000b302  xor     edx, edx; Val
0x18000b304  call    memset_0
0x18000b309  movups  xmm0, xmmword ptr cs:GUID_SysClock.Data1
0x18000b310  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hInstance
0x18000b317  lea     rax, ?CreatePcClock@@YAJPEAPEAUIReferenceClock@@PEAVCMasterClock@@@Z; CreatePcClock(IReferenceClock * *,CMasterClock *)
0x18000b31e  mov     r9d, esi; cchBufferMax
0x18000b321  mov     [rsp+570h+var_52C], 11Ch
0x18000b32a  lea     r8, [rbp+470h+Buffer]; lpBuffer
0x18000b331  mov     [rbp+470h+var_414], 1
0x18000b338  mov     edx, 3E8h; uID
0x18000b33d  mov     [rbp+470h+var_410], rax
0x18000b341  movdqu  [rsp+570h+var_524], xmm0
0x18000b347  call    cs:__imp_LoadStringA
0x18000b34d  test    eax, eax
0x18000b34f  jz      short loc_18000B376
0x18000b351  lea     rax, [rsp+570h+WideCharStr]
0x18000b356  mov     [rsp+570h+cchWideChar], esi; cchWideChar
0x18000b35a  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000b35e  mov     [rsp+570h+lpWideCharStr], rax; lpWideCharStr
0x18000b363  lea     r8, [rbp+470h+Buffer]; lpMultiByteStr
0x18000b36a  xor     edx, edx; dwFlags
0x18000b36c  xor     ecx, ecx; CodePage
0x18000b36e  call    cs:__imp_MultiByteToWideChar
0x18000b374  jmp     short loc_18000B37D
0x18000b376  xor     eax, eax
0x18000b378  mov     [rsp+570h+WideCharStr], ax
0x18000b37d  lea     rdx, [rsp+570h+var_530]; struct tagCLOCKENTRY *
0x18000b382  mov     rcx, rbx; this
0x18000b385  call    ?AddClock@CMasterClock@@QEAAJPEAUtagCLOCKENTRY@@@Z; CMasterClock::AddClock(tagCLOCKENTRY *)
0x18000b38a  test    eax, eax
0x18000b38c  js      short loc_18000B397
0x18000b38e  cmp     eax, 1
0x18000b391  jnz     loc_18000B43C
0x18000b397  cmp     cs:dword_18002A894, 0
0x18000b39e  jnz     short loc_18000B3AA
0x18000b3a0  mov     cs:dword_18002A894, 1
0x18000b3aa  mov     r8, r13; Size
0x18000b3ad  lea     rcx, [rbp+470h+var_400]; void *
0x18000b3b1  xor     edx, edx; Val
0x18000b3b3  call    memset_0
0x18000b3b8  movups  xmm0, xmmword ptr cs:GUID_SysClock.Data1
0x18000b3bf  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hInstance
0x18000b3c6  lea     rax, CreateSysClock
0x18000b3cd  mov     r9d, esi; cchBufferMax
0x18000b3d0  mov     [rbp+470h+var_3FC], r13
0x18000b3d4  lea     r8, [rbp+470h+MultiByteStr]; lpBuffer
0x18000b3db  mov     [rbp+470h+var_2E4], 1
0x18000b3e5  mov     edx, 3E8h; uID
0x18000b3ea  mov     [rbp+470h+var_2E0], rax
0x18000b3f1  movdqu  [rbp+470h+var_3F4], xmm0
0x18000b3f6  call    cs:__imp_LoadStringA
0x18000b3fc  test    eax, eax
0x18000b3fe  jz      short loc_18000B427
0x18000b400  lea     rax, [rbp+470h+var_3E4]
0x18000b407  mov     [rsp+570h+cchWideChar], esi; cchWideChar
0x18000b40b  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000b40f  mov     [rsp+570h+lpWideCharStr], rax; lpWideCharStr
0x18000b414  lea     r8, [rbp+470h+MultiByteStr]; lpMultiByteStr
0x18000b41b  xor     edx, edx; dwFlags
0x18000b41d  xor     ecx, ecx; CodePage
0x18000b41f  call    cs:__imp_MultiByteToWideChar
0x18000b425  jmp     short loc_18000B430
0x18000b427  xor     eax, eax
0x18000b429  mov     [rbp+470h+var_3E4], ax
0x18000b430  lea     rdx, [rbp+470h+var_400]; struct tagCLOCKENTRY *
0x18000b434  mov     rcx, rbx; this
0x18000b437  call    ?AddClock@CMasterClock@@QEAAJPEAUtagCLOCKENTRY@@@Z; CMasterClock::AddClock(tagCLOCKENTRY *)
0x18000b43c  mov     r8, r13; Size
0x18000b43f  lea     rcx, [rbp+470h+var_2D0]; void *
0x18000b446  xor     edx, edx; Val
0x18000b448  call    memset_0
0x18000b44d  movups  xmm0, xmmword ptr cs:GUID_DsClock.Data1
0x18000b454  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hInstance
0x18000b45b  lea     rax, CreateDsClock
0x18000b462  mov     r9d, esi; cchBufferMax
0x18000b465  mov     [rbp+470h+var_2CC], 11Ch
0x18000b470  lea     r8, [rbp+470h+var_A0]; lpBuffer
0x18000b477  mov     [rbp+470h+var_1B4], 0
0x18000b481  mov     edx, 3E9h; uID
0x18000b486  mov     [rbp+470h+var_1B0], rax
0x18000b48d  movdqu  [rbp+470h+var_2C4], xmm0
0x18000b495  call    cs:__imp_LoadStringA
0x18000b49b  test    eax, eax
0x18000b49d  jz      short loc_18000B4C6
0x18000b49f  lea     rax, [rbp+470h+var_2B4]
0x18000b4a6  mov     [rsp+570h+cchWideChar], esi; cchWideChar
0x18000b4aa  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000b4ae  mov     [rsp+570h+lpWideCharStr], rax; lpWideCharStr
0x18000b4b3  lea     r8, [rbp+470h+var_A0]; lpMultiByteStr
0x18000b4ba  xor     edx, edx; dwFlags
0x18000b4bc  xor     ecx, ecx; CodePage
0x18000b4be  call    cs:__imp_MultiByteToWideChar
0x18000b4c4  jmp     short loc_18000B4CF
0x18000b4c6  xor     eax, eax
0x18000b4c8  mov     [rbp+470h+var_2B4], ax
0x18000b4cf  lea     rdx, [rbp+470h+var_2D0]; struct tagCLOCKENTRY *
0x18000b4d6  mov     rcx, rbx; this
0x18000b4d9  call    ?AddClock@CMasterClock@@QEAAJPEAUtagCLOCKENTRY@@@Z; CMasterClock::AddClock(tagCLOCKENTRY *)
0x18000b4de  mov     rax, [rdi]
0x18000b4e1  mov     rcx, rdi
0x18000b4e4  mov     rax, [rax+28h]
0x18000b4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4ed  mov     rbx, rax
0x18000b4f0  test    rax, rax
0x18000b4f3  jz      short loc_18000B524
0x18000b4f5  mov     rcx, [rbx+10h]; void *
0x18000b4f9  mov     rsi, [rbx+8]
0x18000b4fd  cmp     dword ptr [rcx], 0
0x18000b500  jnz     short loc_18000B51C
0x18000b502  mov     rdx, r13; unsigned __int64
0x18000b505  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b50a  mov     rcx, [rdi]
0x18000b50d  mov     rdx, rbx
0x18000b510  mov     rax, [rcx+10h]
0x18000b514  mov     rcx, rdi
0x18000b517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b51c  mov     rbx, rsi
0x18000b51f  test    rsi, rsi
0x18000b522  jnz     short loc_18000B4F5
0x18000b524  mov     rax, [rdi]
0x18000b527  mov     rcx, rdi
0x18000b52a  mov     rax, [rax+30h]
0x18000b52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b533  xor     ecx, ecx
0x18000b535  test    eax, eax
0x18000b537  setz    cl
0x18000b53a  mov     eax, ecx
0x18000b53c  mov     rcx, [rbp+470h+var_20]
0x18000b543  xor     rcx, rsp; StackCookie
0x18000b546  call    __security_check_cookie
0x18000b54b  lea     r11, [rsp+570h+var_10]
0x18000b553  mov     rbx, [r11+28h]
0x18000b557  mov     rsi, [r11+30h]
0x18000b55b  mov     rsp, r11
0x18000b55e  pop     r13
0x18000b560  pop     rdi
0x18000b561  pop     rbp
0x18000b562  retn
```
