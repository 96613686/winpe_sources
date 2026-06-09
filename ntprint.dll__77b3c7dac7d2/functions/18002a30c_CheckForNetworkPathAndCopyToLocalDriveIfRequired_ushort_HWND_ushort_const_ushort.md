# CheckForNetworkPathAndCopyToLocalDriveIfRequired(ushort,HWND__ *,ushort * const,ushort * *)

- ea: `0x18002a30c`
- end: `0x18002a5a6`
- name: `?CheckForNetworkPathAndCopyToLocalDriveIfRequired@@YAJGPEAUHWND__@@QEAGPEAPEAG@Z`
- size: `666`
- prototype: `int(unsigned __int16, HWND, unsigned __int16 *const, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002b2fc`
- `0x18002b960`

## callees

- `0x180002300`
- `0x1800026e0`
- `0x180002f48`
- `0x1800078f0`
- `0x180007944`
- `0x18000b200`
- `0x18000d290`
- `0x18000d7f0`
- `0x18001bc44`
- `0x180020624`
- `0x18002a30c`
- `0x1800310a0`
- `0x180036470`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18002a383`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18002a383`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a48c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a48c`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18002a3a6`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18002a3a6`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002a3df`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002a3df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a574`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a574`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002a451`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002a451`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002a475`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002a475`

## pseudocode

```c
__int64 __fastcall CheckForNetworkPathAndCopyToLocalDriveIfRequired(
        unsigned __int16 a1,
        HWND a2,
        unsigned __int16 *const a3,
        unsigned __int16 **a4)
{
  unsigned __int16 v6; // bx
  unsigned __int64 v8; // rsi
  unsigned __int16 *v9; // r15
  int LastErrorAsFailHR; // edi
  unsigned __int16 v11; // bx
  UINT DriveTypeW; // eax
  NCoreLibrary *v13; // rcx
  HWND v14; // rax
  wchar_t *v15; // rbx
  GUID pguid; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  v6 = a1;
  memset_0(Buffer, 0, 0x208u);
  v8 = 0;
  *(_QWORD *)&pguid.Data1 = 0;
  if ( !a4 )
    return (unsigned int)-2147024809;
  v9 = 0;
  *a4 = 0;
  LastErrorAsFailHR = 0;
  if ( a3[1] == 58 && (unsigned int)_o_iswalpha(*a3) && a3[2] == 92 )
  {
    v11 = a3[3];
    a3[3] = 0;
    DriveTypeW = GetDriveTypeW(a3);
    a3[3] = v11;
    if ( DriveTypeW == 4 )
    {
      v6 = a1;
      goto LABEL_8;
    }
LABEL_30:
    *a4 = v9;
    return (unsigned int)LastErrorAsFailHR;
  }
  if ( !(unsigned int)IsUNCPath(a3) )
    goto LABEL_30;
LABEL_8:
  if ( GetTempPathW(0x104u, Buffer) <= 0x104 )
  {
    LastErrorAsFailHR = StringCchLengthW(Buffer, 0x104u, (unsigned __int64 *)&pguid.Data1);
    if ( LastErrorAsFailHR < 0 )
      return (unsigned int)LastErrorAsFailHR;
    v8 = *(_QWORD *)&pguid.Data1;
  }
  if ( Buffer[v8 - 1] != 92 )
  {
    if ( v8 >= 0x103 )
      return (unsigned int)-2147024774;
    Buffer[v8++] = 92;
    if ( 2 * v8 >= 0x208 )
      _report_rangecheckfailure();
    Buffer[v8] = 0;
  }
  pguid = 0;
  LastErrorAsFailHR = CoCreateGuid(&pguid);
  if ( LastErrorAsFailHR >= 0 )
  {
    LastErrorAsFailHR = StringFromGUID2(&pguid, &Buffer[v8], 260 - v8);
    if ( LastErrorAsFailHR >= 0 )
    {
      if ( CreateDirectoryW(Buffer, 0)
        || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v13), LastErrorAsFailHR >= 0) )
      {
        v9 = (unsigned __int16 *)AllocStr(Buffer);
        if ( !v9 )
          return (unsigned int)-2147024882;
        v14 = HWND_MESSAGE|0x2LL;
        if ( a2 )
          v14 = a2;
        LastErrorAsFailHR = PSetupCopyDriverPackageFiles(a3, Buffer, v6, 0, v14);
        if ( LastErrorAsFailHR >= 0 )
        {
          v15 = wcsrchr(a3, 0x5Cu);
          if ( v15 )
          {
            LastErrorAsFailHR = StringCchCatW(Buffer, 0x104u, L"\\");
            if ( LastErrorAsFailHR >= 0 )
            {
              LastErrorAsFailHR = StringCchCatW(Buffer, 0x104u, v15 + 1);
              if ( LastErrorAsFailHR >= 0 )
              {
                LastErrorAsFailHR = StringCchCopyW(a3, 0x104u, Buffer);
                if ( LastErrorAsFailHR >= 0 )
                  goto LABEL_30;
              }
            }
          }
          else
          {
            LastErrorAsFailHR = -2147024809;
          }
        }
        RecursivelyDeleteDirectory(v9, 5);
        LocalFree(v9);
      }
    }
  }
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x18002a30c  push    rbp
0x18002a30e  push    rbx
0x18002a30f  push    rsi
0x18002a310  push    rdi
0x18002a311  push    r12
0x18002a313  push    r13
0x18002a315  push    r14
0x18002a317  push    r15
0x18002a319  lea     rbp, [rsp-178h]
0x18002a321  sub     rsp, 278h
0x18002a328  mov     rax, cs:__security_cookie
0x18002a32f  xor     rax, rsp
0x18002a332  mov     [rbp+1B0h+var_50], rax
0x18002a339  mov     r14, r8
0x18002a33c  mov     [rsp+2B0h+var_280], cx
0x18002a341  mov     r13, rdx
0x18002a344  movzx   ebx, cx
0x18002a347  xor     edx, edx; Val
0x18002a349  lea     rcx, [rsp+2B0h+Buffer]; void *
0x18002a34e  mov     r8d, 208h; Size
0x18002a354  mov     r12, r9
0x18002a357  call    memset_0
0x18002a35c  xor     esi, esi
0x18002a35e  mov     qword ptr [rsp+2B0h+pguid.Data1], rsi
0x18002a363  test    r12, r12
0x18002a366  jz      loc_18002A57C
0x18002a36c  xor     r15d, r15d
0x18002a36f  mov     [r12], rsi
0x18002a373  xor     edi, edi
0x18002a375  lea     eax, [rsi+3Ah]
0x18002a378  cmp     ax, [r14+2]
0x18002a37d  jnz     short loc_18002A3C1
0x18002a37f  movzx   ecx, word ptr [r14]
0x18002a383  call    cs:__imp__o_iswalpha
0x18002a389  test    eax, eax
0x18002a38b  jz      short loc_18002A3C1
0x18002a38d  lea     edx, [rsi+5Ch]
0x18002a390  cmp     dx, [r14+4]
0x18002a395  jnz     short loc_18002A3C1
0x18002a397  movzx   ebx, word ptr [r14+6]
0x18002a39c  xor     eax, eax
0x18002a39e  mov     rcx, r14; lpRootPathName
0x18002a3a1  mov     [r14+6], ax
0x18002a3a6  call    cs:__imp_GetDriveTypeW
0x18002a3ac  mov     [r14+6], bx
0x18002a3b1  cmp     eax, 4
0x18002a3b4  jnz     loc_18002A559
0x18002a3ba  movzx   ebx, [rsp+2B0h+var_280]
0x18002a3bf  jmp     short loc_18002A3D1
0x18002a3c1  mov     rcx, r14
0x18002a3c4  call    IsUNCPath
0x18002a3c9  test    eax, eax
0x18002a3cb  jz      loc_18002A559
0x18002a3d1  mov     r15d, 104h
0x18002a3d7  lea     rdx, [rsp+2B0h+Buffer]; lpBuffer
0x18002a3dc  mov     ecx, r15d; nBufferLength
0x18002a3df  call    cs:__imp_GetTempPathW
0x18002a3e5  cmp     eax, r15d
0x18002a3e8  ja      short loc_18002A40B
0x18002a3ea  lea     r8, [rsp+2B0h+pguid]; unsigned __int64 *
0x18002a3ef  mov     edx, r15d; unsigned __int64
0x18002a3f2  lea     rcx, [rsp+2B0h+Buffer]; unsigned __int16 *
0x18002a3f7  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002a3fc  mov     edi, eax
0x18002a3fe  test    eax, eax
0x18002a400  js      loc_18002A581
0x18002a406  mov     rsi, qword ptr [rsp+2B0h+pguid.Data1]
0x18002a40b  mov     eax, 5Ch ; '\'
0x18002a410  cmp     [rsp+rsi*2+2B0h+var_262], ax
0x18002a415  jz      short loc_18002A444
0x18002a417  cmp     rsi, 103h
0x18002a41e  jnb     loc_18002A4C7
0x18002a424  mov     [rsp+rsi*2+2B0h+Buffer], ax
0x18002a429  inc     rsi
0x18002a42c  lea     rcx, [rsi+rsi]
0x18002a430  cmp     rcx, 208h
0x18002a437  jnb     loc_18002A4C1
0x18002a43d  xor     eax, eax
0x18002a43f  mov     [rsp+rcx+2B0h+Buffer], ax
0x18002a444  xorps   xmm0, xmm0
0x18002a447  lea     rcx, [rsp+2B0h+pguid]; pguid
0x18002a44c  movups  xmmword ptr [rsp+2B0h+pguid.Data1], xmm0
0x18002a451  call    cs:__imp_CoCreateGuid
0x18002a457  mov     edi, eax
0x18002a459  test    eax, eax
0x18002a45b  js      loc_18002A581
0x18002a461  mov     r8d, r15d
0x18002a464  lea     rdx, [rsp+2B0h+Buffer]
0x18002a469  sub     r8d, esi; cchMax
0x18002a46c  lea     rdx, [rdx+rsi*2]; lpsz
0x18002a470  lea     rcx, [rsp+2B0h+pguid]; rguid
0x18002a475  call    cs:__imp_StringFromGUID2
0x18002a47b  mov     edi, eax
0x18002a47d  test    eax, eax
0x18002a47f  js      loc_18002A581
0x18002a485  xor     edx, edx; lpSecurityAttributes
0x18002a487  lea     rcx, [rsp+2B0h+Buffer]; lpPathName
0x18002a48c  call    cs:__imp_CreateDirectoryW
0x18002a492  test    eax, eax
0x18002a494  jnz     short loc_18002A4A5
0x18002a496  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002a49b  mov     edi, eax
0x18002a49d  test    eax, eax
0x18002a49f  js      loc_18002A581
0x18002a4a5  lea     rcx, [rsp+2B0h+Buffer]; unsigned __int16 *
0x18002a4aa  call    AllocStr
0x18002a4af  mov     r15, rax
0x18002a4b2  test    rax, rax
0x18002a4b5  jnz     short loc_18002A4D1
0x18002a4b7  mov     edi, 8007000Eh
0x18002a4bc  jmp     loc_18002A581
0x18002a4c1  call    __report_rangecheckfailure
0x18002a4c7  mov     edi, 8007007Ah
0x18002a4cc  jmp     loc_18002A581
0x18002a4d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a4d5  lea     rdx, [rsp+2B0h+Buffer]; unsigned __int16 *
0x18002a4da  test    r13, r13
0x18002a4dd  movzx   r8d, bx
0x18002a4e1  mov     rcx, r14; unsigned __int16 *
0x18002a4e4  cmovnz  rax, r13
0x18002a4e8  xor     r9d, r9d
0x18002a4eb  mov     [rsp+2B0h+var_290], rax; HWND
0x18002a4f0  call    PSetupCopyDriverPackageFiles
0x18002a4f5  mov     edi, eax
0x18002a4f7  test    eax, eax
0x18002a4f9  js      short loc_18002A564
0x18002a4fb  mov     edx, 5Ch ; '\'; Ch
0x18002a500  mov     rcx, r14; Str
0x18002a503  call    ?wcsrchr@@YAPEAGPEAGG@Z; wcsrchr(ushort *,ushort)
0x18002a508  mov     rbx, rax
0x18002a50b  test    rax, rax
0x18002a50e  jz      short loc_18002A55F
0x18002a510  mov     esi, 104h
0x18002a515  lea     r8, SubBlock; "\\"
0x18002a51c  mov     edx, esi; unsigned __int64
0x18002a51e  lea     rcx, [rsp+2B0h+Buffer]; unsigned __int16 *
0x18002a523  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a528  mov     edi, eax
0x18002a52a  test    eax, eax
0x18002a52c  js      short loc_18002A564
0x18002a52e  lea     r8, [rbx+2]; unsigned __int16 *
0x18002a532  mov     edx, esi; unsigned __int64
0x18002a534  lea     rcx, [rsp+2B0h+Buffer]; unsigned __int16 *
0x18002a539  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a53e  mov     edi, eax
0x18002a540  test    eax, eax
0x18002a542  js      short loc_18002A564
0x18002a544  lea     r8, [rsp+2B0h+Buffer]; unsigned __int16 *
0x18002a549  mov     edx, esi; unsigned __int64
0x18002a54b  mov     rcx, r14; unsigned __int16 *
0x18002a54e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a553  mov     edi, eax
0x18002a555  test    eax, eax
0x18002a557  js      short loc_18002A564
0x18002a559  mov     [r12], r15
0x18002a55d  jmp     short loc_18002A581
0x18002a55f  mov     edi, 80070057h
0x18002a564  mov     edx, 5
0x18002a569  mov     rcx, r15
0x18002a56c  call    RecursivelyDeleteDirectory
0x18002a571  mov     rcx, r15; hMem
0x18002a574  call    cs:__imp_LocalFree
0x18002a57a  jmp     short loc_18002A581
0x18002a57c  mov     edi, 80070057h
0x18002a581  mov     eax, edi
0x18002a583  mov     rcx, [rbp+1B0h+var_50]
0x18002a58a  xor     rcx, rsp; StackCookie
0x18002a58d  call    __security_check_cookie
0x18002a592  add     rsp, 278h
0x18002a599  pop     r15
0x18002a59b  pop     r14
0x18002a59d  pop     r13
0x18002a59f  pop     r12
0x18002a5a1  pop     rdi
0x18002a5a2  pop     rsi
0x18002a5a3  pop     rbx
0x18002a5a4  pop     rbp
0x18002a5a5  retn
```
