# RuntimeRequest::NoSupportedVersion(int)

- ea: `0x18002b1cc`
- end: `0x18002b5af`
- name: `?NoSupportedVersion@RuntimeRequest@@QEAAJH@Z`
- size: `995`
- prototype: `__int64 __fastcall(RuntimeRequest *__hidden this, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x180009af4`
- `0x180029b70`

## callees

- `0x180007300`
- `0x180007388`
- `0x18000d264`
- `0x18000d614`
- `0x18000da9c`
- `0x18000db8c`
- `0x18002a3b8`
- `0x18002a570`
- `0x18002b19c`
- `0x18002b1cc`
- `0x18002c05c`
- `0x18003e758`
- `0x180041ac0`
- `0x180045030`

## import_xrefs

- `KERNEL32!SetErrorMode` at `0x18002b212`
- `KERNEL32!SetErrorMode` at `0x18002b585`
- `KERNEL32!SetErrorMode` at `0x18002b212`
- `KERNEL32!SetErrorMode` at `0x18002b585`
- `USER32!LoadStringW` at `0x18002b3a4`
- `USER32!LoadStringW` at `0x18002b3cc`
- `USER32!LoadStringW` at `0x18002b4b4`
- `USER32!LoadStringW` at `0x18002b4d8`
- `USER32!LoadStringW` at `0x18002b521`
- `USER32!LoadStringW` at `0x18002b545`
- `USER32!LoadStringW` at `0x18002b3a4`
- `USER32!LoadStringW` at `0x18002b3cc`
- `USER32!LoadStringW` at `0x18002b4b4`
- `USER32!LoadStringW` at `0x18002b4d8`
- `USER32!LoadStringW` at `0x18002b521`
- `USER32!LoadStringW` at `0x18002b545`

## string_xrefs

- `0x18002b55c`: `A fatal error occurred. However, mscorees.dll could not be loaded to display the appropriate error message.\n\nPlease reinstall the .NET Framework.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RuntimeRequest::NoSupportedVersion(const wchar_t **this, int a2)
{
  UINT v3; // r15d
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rbx
  unsigned int v6; // esi
  unsigned __int16 *v7; // rax
  wchar_t i; // cx
  const wchar_t *v9; // r8
  HINSTANCE ResourceInst; // rax
  HINSTANCE v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  size_t v14; // rsi
  wchar_t *v15; // rax
  const unsigned __int16 *v16; // rdi
  unsigned int ShimMBRTLStyle; // eax
  HINSTANCE v18; // rax
  HINSTANCE v19; // rax
  unsigned int v20; // r9d
  WCHAR *v21; // r8
  WCHAR *v22; // rdx
  HINSTANCE v23; // rax
  HINSTANCE v24; // rax
  rsize_t SizeInWords; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h]
  __int64 v30; // [rsp+50h] [rbp-B0h]
  wchar_t Destination[260]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v32[68]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR v33[256]; // [rsp+480h] [rbp+380h] BYREF
  wchar_t Buffer[512]; // [rsp+680h] [rbp+580h] BYREF

  if ( a2 && !(unsigned int)NoGuiFromShim() )
  {
    v3 = SetErrorMode(0);
    if ( (v3 & 1) != 0 )
    {
LABEL_42:
      SetErrorMode(v3);
      return 2148734720LL;
    }
    memset_thunk_772440563353939046(Buffer, 0, 0x400u);
    memset_thunk_772440563353939046(v33, 0, 0x200u);
    v28 = 0;
    v29 = 0;
    v30 = 512;
    if ( !*((_DWORD *)this + 26) )
    {
      v5 = 0;
      v9 = *this;
      if ( *this )
      {
        v29 = 52;
        v5 = Destination;
        wcsncpy_s(Destination, 0x1Au, v9, 0x19u);
        Destination[25] = 0;
LABEL_14:
        v7 = v5;
        for ( i = *v5; i; i = *v7 )
        {
          if ( i == 37 || *v7 == 92 )
            *v7 = 95;
          ++v7;
        }
        if ( GetResourceInst() )
        {
          ResourceInst = GetResourceInst();
          if ( LoadStringW(ResourceInst, 5u, Buffer, 512) > 0 )
          {
            v11 = GetResourceInst();
            if ( LoadStringW(v11, 2u, v33, 256) > 0 )
            {
              v12 = -1;
              v13 = -1;
              do
                ++v13;
              while ( Buffer[v13] );
              do
                ++v12;
              while ( v5[v12] );
              v14 = v13 + v12 + 1;
              v32[0] = 0;
              v32[1] = 0;
              v32[2] = 512;
              v15 = (wchar_t *)CQuickMemoryBase<512,128>::_Alloc<0,0>(v32, 2 * v14);
              v16 = v15;
              if ( v15 )
              {
                swprintf_s(v15, v14, Buffer, v5);
                ShimMBRTLStyle = GetShimMBRTLStyle();
                UtilMessageBoxNonLocalized(0, v16, v33, ShimMBRTLStyle | 0x10, 0, 1);
                CQuickArray<unsigned short>::~CQuickArray<unsigned short>(v32);
LABEL_41:
                CQuickArray<unsigned short>::~CQuickArray<unsigned short>(&v28);
                goto LABEL_42;
              }
              CQuickArray<unsigned short>::~CQuickArray<unsigned short>(v32);
            }
          }
        }
LABEL_32:
        if ( GetResourceInst()
          && (v18 = GetResourceInst(), LoadStringW(v18, 7u, Buffer, 512) > 0)
          && (v19 = GetResourceInst(), LoadStringW(v19, 2u, v33, 256) > 0)
          || GetResourceInst()
          && (v23 = GetResourceInst(), LoadStringW(v23, 6u, Buffer, 512) > 0)
          && (v24 = GetResourceInst(), LoadStringW(v24, 2u, v33, 256) > 0) )
        {
          v20 = GetShimMBRTLStyle() | 0x10;
          v21 = v33;
          v22 = Buffer;
        }
        else
        {
          v20 = 16;
          v21 = (WCHAR *)L"Error";
          v22 = (WCHAR *)L"A fatal error occurred. However, mscorees.dll could not be loaded to display the appropriate er"
                          "ror message.\n"
                          "\n"
                          "Please reinstall the .NET Framework.";
        }
        UtilMessageBoxNonLocalized(0, v22, v21, v20, 0, 1);
        goto LABEL_41;
      }
LABEL_13:
      if ( !v5 )
        goto LABEL_32;
      goto LABEL_14;
    }
    v27 = 0;
    SizeInWords = 0;
    if ( (unsigned __int8)ClrSafeInt<unsigned __int64>::multiply(*((unsigned int *)this + 26), 29, &v27)
      && (unsigned __int8)ClrSafeInt<unsigned __int64>::multiply(v27, 2, &SizeInWords) )
    {
      v4 = (unsigned __int16 *)CQuickMemoryBase<512,128>::_Alloc<0,0>(&v28, SizeInWords);
      v5 = v4;
      if ( v4 )
      {
        *v4 = 0;
        v6 = 0;
        if ( *((_DWORD *)this + 26) )
        {
          do
          {
            wcsncat_s(v5, SizeInWords, *(const wchar_t **)&this[12][4 * v6++], 0x19u);
            if ( v6 >= *((_DWORD *)this + 26) )
              break;
            wcscat_s(v5, SizeInWords, L"\r\n  ");
          }
          while ( v6 < *((_DWORD *)this + 26) );
          goto LABEL_14;
        }
      }
      else
      {
        v5 = (unsigned __int16 *)&word_180050144;
      }
      goto LABEL_13;
    }
    CQuickArray<unsigned short>::~CQuickArray<unsigned short>(&v28);
  }
  return 2148734720LL;
}

```

## disassembly

```asm
0x18002b1cc  push    rbp
0x18002b1ce  push    rbx
0x18002b1cf  push    rsi
0x18002b1d0  push    rdi
0x18002b1d1  push    r12
0x18002b1d3  push    r15
0x18002b1d5  lea     rbp, [rsp-998h]
0x18002b1dd  sub     rsp, 0A98h
0x18002b1e4  mov     rax, cs:__security_cookie
0x18002b1eb  xor     rax, rsp
0x18002b1ee  mov     [rbp+9C0h+var_40], rax
0x18002b1f5  mov     rdi, rcx
0x18002b1f8  xor     r12d, r12d
0x18002b1fb  test    edx, edx
0x18002b1fd  jz      loc_18002B58B
0x18002b203  call    ?NoGuiFromShim@@YAHXZ; NoGuiFromShim(void)
0x18002b208  test    eax, eax
0x18002b20a  jnz     loc_18002B58B
0x18002b210  xor     ecx, ecx; uMode
0x18002b212  call    cs:__imp_SetErrorMode
0x18002b218  mov     r15d, eax
0x18002b21b  test    al, 1
0x18002b21d  jnz     loc_18002B582
0x18002b223  xor     edx, edx; Val
0x18002b225  mov     r8d, 400h; Size
0x18002b22b  lea     rcx, [rbp+9C0h+Buffer]; void *
0x18002b232  call    memset$thunk$772440563353939046
0x18002b237  mov     ebx, 200h
0x18002b23c  mov     r8d, ebx; Size
0x18002b23f  xor     edx, edx; Val
0x18002b241  lea     rcx, [rbp+9C0h+var_640]; void *
0x18002b248  call    memset$thunk$772440563353939046
0x18002b24d  mov     [rsp+0AC0h+var_A80], r12
0x18002b252  mov     [rsp+0AC0h+var_A78], r12
0x18002b257  mov     [rsp+0AC0h+var_A70], rbx
0x18002b25c  cmp     [rdi+68h], r12d
0x18002b260  jz      loc_18002B32C
0x18002b266  mov     [rsp+0AC0h+var_A88], r12
0x18002b26b  mov     [rsp+0AC0h+SizeInWords], r12
0x18002b270  mov     ecx, [rdi+68h]
0x18002b273  lea     r8, [rsp+0AC0h+var_A88]
0x18002b278  lea     edx, [r12+1Dh]
0x18002b27d  call    ?multiply@?$ClrSafeInt@_K@@SA_N_K0AEA_K@Z; ClrSafeInt<unsigned __int64>::multiply(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x18002b282  test    al, al
0x18002b284  jz      loc_18002B31D
0x18002b28a  lea     r8, [rsp+0AC0h+SizeInWords]
0x18002b28f  lea     edx, [r12+2]
0x18002b294  mov     rcx, [rsp+0AC0h+var_A88]
0x18002b299  call    ?multiply@?$ClrSafeInt@_K@@SA_N_K0AEA_K@Z; ClrSafeInt<unsigned __int64>::multiply(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x18002b29e  test    al, al
0x18002b2a0  jz      short loc_18002B31D
0x18002b2a2  mov     rdx, [rsp+0AC0h+SizeInWords]
0x18002b2a7  lea     rcx, [rsp+0AC0h+var_A80]
0x18002b2ac  call    ??$_Alloc@$0A@$0A@@?$CQuickMemoryBase@$0CAA@$0IA@@@IEAAPEAX_K@Z; CQuickMemoryBase<512,128>::_Alloc<0,0>(unsigned __int64)
0x18002b2b1  mov     rbx, rax
0x18002b2b4  test    rax, rax
0x18002b2b7  jz      short loc_18002B305
0x18002b2b9  mov     [rax], r12w
0x18002b2bd  mov     esi, r12d
0x18002b2c0  cmp     [rdi+68h], r12d
0x18002b2c4  jbe     short loc_18002B30C
0x18002b2c6  mov     eax, esi
0x18002b2c8  mov     r8, [rdi+60h]
0x18002b2cc  mov     r9d, 19h; MaxCount
0x18002b2d2  mov     r8, [r8+rax*8]; Source
0x18002b2d6  mov     rdx, [rsp+0AC0h+SizeInWords]; SizeInWords
0x18002b2db  mov     rcx, rbx; Destination
0x18002b2de  call    wcsncat_s
0x18002b2e3  inc     esi
0x18002b2e5  cmp     esi, [rdi+68h]
0x18002b2e8  jnb     short loc_18002B315
0x18002b2ea  lea     r8, asc_180050138; "\r\n  "
0x18002b2f1  mov     rdx, [rsp+0AC0h+SizeInWords]; SizeInWords
0x18002b2f6  mov     rcx, rbx; Destination
0x18002b2f9  call    wcscat_s
0x18002b2fe  cmp     esi, [rdi+68h]
0x18002b301  jb      short loc_18002B2C6
0x18002b303  jmp     short loc_18002B315
0x18002b305  lea     rbx, word_180050144
0x18002b30c  test    rbx, rbx
0x18002b30f  jz      loc_18002B490
0x18002b315  mov     rax, rbx
0x18002b318  movzx   ecx, word ptr [rbx]
0x18002b31b  jmp     short loc_18002B377
0x18002b31d  lea     rcx, [rsp+0AC0h+var_A80]
0x18002b322  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x18002b327  jmp     loc_18002B58B
0x18002b32c  mov     rbx, r12
0x18002b32f  mov     r8, [rdi]; Source
0x18002b332  test    r8, r8
0x18002b335  jz      short loc_18002B30C
0x18002b337  mov     [rsp+0AC0h+var_A78], 34h ; '4'
0x18002b340  lea     rbx, [rsp+0AC0h+Destination]
0x18002b345  mov     edx, 1Ah; SizeInWords
0x18002b34a  lea     r9d, [rdx-1]; MaxCount
0x18002b34e  lea     rcx, [rsp+0AC0h+Destination]; Destination
0x18002b353  call    wcsncpy_s
0x18002b358  mov     [rbp+9C0h+var_A36], r12w
0x18002b35d  jmp     short loc_18002B315
0x18002b35f  cmp     cx, 25h ; '%'
0x18002b363  jz      short loc_18002B36B
0x18002b365  cmp     word ptr [rax], 5Ch ; '\'
0x18002b369  jnz     short loc_18002B370
0x18002b36b  mov     word ptr [rax], 5Fh ; '_'
0x18002b370  add     rax, 2
0x18002b374  movzx   ecx, word ptr [rax]
0x18002b377  test    cx, cx
0x18002b37a  jnz     short loc_18002B35F
0x18002b37c  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x18002b381  test    rax, rax
0x18002b384  jz      loc_18002B490
0x18002b38a  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x18002b38f  mov     rcx, rax; hInstance
0x18002b392  mov     r9d, 200h; cchBufferMax
0x18002b398  lea     r8, [rbp+9C0h+Buffer]; lpBuffer
0x18002b39f  mov     edx, 5; uID
0x18002b3a4  call    cs:__imp_LoadStringW
0x18002b3aa  test    eax, eax
0x18002b3ac  jle     loc_18002B490
0x18002b3b2  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x18002b3b7  mov     rcx, rax; hInstance
0x18002b3ba  mov     r9d, 100h; cchBufferMax
0x18002b3c0  lea     r8, [rbp+9C0h+var_640]; lpBuffer
0x18002b3c7  mov     edx, 2; uID
0x18002b3cc  call    cs:__imp_LoadStringW
0x18002b3d2  test    eax, eax
0x18002b3d4  jle     loc_18002B490
0x18002b3da  lea     rdx, [rbp+9C0h+Buffer]
0x18002b3e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b3e5  mov     rcx, rax
0x18002b3e8  inc     rcx
0x18002b3eb  cmp     [rdx+rcx*2], r12w
0x18002b3f0  jnz     short loc_18002B3E8
0x18002b3f2  inc     rax
0x18002b3f5  cmp     [rbx+rax*2], r12w
0x18002b3fa  jnz     short loc_18002B3F2
0x18002b3fc  lea     rsi, [rax+1]
0x18002b400  add     rsi, rcx
0x18002b403  mov     [rbp+9C0h+var_860], r12
0x18002b40a  mov     [rbp+9C0h+var_858], r12
0x18002b411  mov     [rbp+9C0h+var_850], 200h
0x18002b41c  lea     rdx, [rsi+rsi]
0x18002b420  lea     rcx, [rbp+9C0h+var_860]
0x18002b427  call    ??$_Alloc@$0A@$0A@@?$CQuickMemoryBase@$0CAA@$0IA@@@IEAAPEAX_K@Z; CQuickMemoryBase<512,128>::_Alloc<0,0>(unsigned __int64)
0x18002b42c  mov     rdi, rax
0x18002b42f  test    rax, rax
0x18002b432  jz      short loc_18002B484
0x18002b434  mov     r9, rbx
0x18002b437  lea     r8, [rbp+9C0h+Buffer]; Format
0x18002b43e  mov     rdx, rsi; BufferCount
0x18002b441  mov     rcx, rax; Buffer
0x18002b444  call    swprintf_s
0x18002b449  call    ?GetShimMBRTLStyle@@YAIXZ; GetShimMBRTLStyle(void)
0x18002b44e  or      eax, 10h
0x18002b451  mov     [rsp+0AC0h+var_A98], 1; int
0x18002b459  mov     qword ptr [rsp+0AC0h+var_AA0], r12; int
0x18002b45e  mov     r9d, eax; unsigned int
0x18002b461  lea     r8, [rbp+9C0h+var_640]; unsigned __int16 *
0x18002b468  mov     rdx, rdi; unsigned __int16 *
0x18002b46b  xor     ecx, ecx; HWND
0x18002b46d  call    ?UtilMessageBoxNonLocalized@@YAHPEAUHWND__@@PEBG1IHHZZ; UtilMessageBoxNonLocalized(HWND__ *,ushort const *,ushort const *,uint,int,int,...)
0x18002b472  nop
0x18002b473  lea     rcx, [rbp+9C0h+var_860]
0x18002b47a  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x18002b47f  jmp     loc_18002B578
0x18002b484  lea     rcx, [rbp+9C0h+var_860]
0x18002b48b  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x18002b490  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x18002b495  test    rax, rax
0x18002b498  jz      short loc_18002B4FD
0x18002b49a  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x18002b49f  mov     rcx, rax; hInstance
0x18002b4a2  mov     r9d, 200h; cchBufferMax
0x18002b4a8  lea     r8, [rbp+9C0h+Buffer]; lpBuffer
0x18002b4af  mov     edx, 7; uID
0x18002b4b4  call    cs:__imp_LoadStringW
0x18002b4ba  test    eax, eax
0x18002b4bc  jle     short loc_18002B4FD
0x18002b4be  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x18002b4c3  mov     rcx, rax; hInstance
0x18002b4c6  mov     r9d, 100h; cchBufferMax
0x18002b4cc  lea     r8, [rbp+9C0h+var_640]; lpBuffer
0x18002b4d3  mov     edx, 2; uID
0x18002b4d8  call    cs:__imp_LoadStringW
0x18002b4de  test    eax, eax
0x18002b4e0  jle     short loc_18002B4FD
0x18002b4e2  call    ?GetShimMBRTLStyle@@YAIXZ; GetShimMBRTLStyle(void)
0x18002b4e7  or      eax, 10h
0x18002b4ea  mov     r9d, eax
0x18002b4ed  lea     r8, [rbp+9C0h+var_640]
0x18002b4f4  lea     rdx, [rbp+9C0h+Buffer]
0x18002b4fb  jmp     short loc_18002B563
0x18002b4fd  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x18002b502  test    rax, rax
0x18002b505  jz      short loc_18002B54F
0x18002b507  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x18002b50c  mov     rcx, rax; hInstance
0x18002b50f  mov     r9d, 200h; cchBufferMax
0x18002b515  lea     r8, [rbp+9C0h+Buffer]; lpBuffer
0x18002b51c  mov     edx, 6; uID
0x18002b521  call    cs:__imp_LoadStringW
0x18002b527  test    eax, eax
0x18002b529  jle     short loc_18002B54F
0x18002b52b  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x18002b530  mov     rcx, rax; hInstance
0x18002b533  mov     r9d, 100h; cchBufferMax
0x18002b539  lea     r8, [rbp+9C0h+var_640]; lpBuffer
0x18002b540  mov     edx, 2; uID
0x18002b545  call    cs:__imp_LoadStringW
0x18002b54b  test    eax, eax
0x18002b54d  jg      short loc_18002B4E2
0x18002b54f  mov     r9d, 10h; unsigned int
0x18002b555  lea     r8, aError; "Error"
0x18002b55c  lea     rdx, aAFatalErrorOcc; "A fatal error occurred. However, mscore"...
0x18002b563  mov     [rsp+0AC0h+var_A98], 1; int
0x18002b56b  mov     qword ptr [rsp+0AC0h+var_AA0], r12; int
0x18002b570  xor     ecx, ecx; HWND
0x18002b572  call    ?UtilMessageBoxNonLocalized@@YAHPEAUHWND__@@PEBG1IHHZZ; UtilMessageBoxNonLocalized(HWND__ *,ushort const *,ushort const *,uint,int,int,...)
0x18002b577  nop
0x18002b578  lea     rcx, [rsp+0AC0h+var_A80]
0x18002b57d  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x18002b582  mov     ecx, r15d; uMode
0x18002b585  call    cs:__imp_SetErrorMode
0x18002b58b  mov     eax, 80131700h
0x18002b590  mov     rcx, [rbp+9C0h+var_40]
0x18002b597  xor     rcx, rsp; StackCookie
0x18002b59a  call    __security_check_cookie
0x18002b59f  add     rsp, 0A98h
0x18002b5a6  pop     r15
0x18002b5a8  pop     r12
0x18002b5aa  pop     rdi
0x18002b5ab  pop     rsi
0x18002b5ac  pop     rbx
0x18002b5ad  pop     rbp
0x18002b5ae  retn
```
