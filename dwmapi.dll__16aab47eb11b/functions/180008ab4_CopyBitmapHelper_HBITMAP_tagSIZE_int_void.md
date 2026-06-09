# CopyBitmapHelper(HBITMAP__ *,tagSIZE *,int,void *)

- ea: `0x180008ab4`
- end: `0x180008cb8`
- name: `?CopyBitmapHelper@@YAJPEAUHBITMAP__@@PEAUtagSIZE@@HPEAX@Z`
- size: `516`
- prototype: `__int64 __fastcall(HBITMAP hbm, struct tagSIZE *, int, void *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b560`
- `0x180013ca0`
- `0x180013ed0`
- `0x1800143c0`

## callees

- `0x180003370`
- `0x180008ab4`
- `0x18000d0a0`
- `0x180014d70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c43`
- `GDI32!GetDIBits` at `0x180008bbc`
- `GDI32!GetDIBits` at `0x180008bbc`
- `GDI32!DeleteDC` at `0x180008bf4`
- `GDI32!DeleteDC` at `0x180008bf4`
- `GDI32!CreateCompatibleDC` at `0x180008c4b`
- `GDI32!CreateCompatibleDC` at `0x180008c4b`

## pseudocode

```c
__int64 __fastcall CopyBitmapHelper(HBITMAP hbm, struct tagSIZE *a2, int a3, char *a4)
{
  __int64 v6; // rcx
  unsigned int v8; // edx
  int v9; // ecx
  signed int v10; // ebx
  LONG i; // ecx
  LONG j; // eax
  signed int v14; // eax
  char v15; // al
  LONG v16; // ecx
  char *v17; // r8
  __int64 v18; // rcx
  HDC CompatibleDC; // rbp
  signed int LastError; // eax
  int v21; // edx
  unsigned int v22; // ecx
  int v23; // r8d
  LONG v24; // edx
  struct tagBITMAPINFO bmi; // [rsp+40h] [rbp-68h] BYREF

  v6 = a2->cy * (__int64)a2->cx;
  if ( (unsigned __int64)(v6 + 0x80000000LL) > 0xFFFFFFFF )
  {
    v8 = 28;
LABEL_3:
    v9 = -2147024362;
    v10 = -2147024362;
LABEL_4:
    DoStackCaptureDirect(v9, v8);
    return (unsigned int)v10;
  }
  v18 = 4LL * (int)v6;
  if ( (unsigned __int64)(v18 + 0x80000000LL) > 0xFFFFFFFF )
  {
    v8 = 29;
    goto LABEL_3;
  }
  if ( (_DWORD)v18 != a3 )
  {
    v10 = -2147024809;
    v8 = 32;
LABEL_32:
    v9 = v10;
    goto LABEL_4;
  }
  SetLastError(0);
  CompatibleDC = CreateCompatibleDC(0);
  if ( !CompatibleDC )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
      v10 = CheckGUIHandleQuota(v22, v21, v23);
    v8 = 35;
    goto LABEL_32;
  }
  bmi.bmiHeader.biWidth = a2->cx;
  bmi.bmiHeader.biHeight = -a2->cy;
  memset(&bmi.bmiHeader.biSizeImage, 0, 24);
  bmi.bmiHeader.biSize = 44;
  *(_QWORD *)&bmi.bmiHeader.biPlanes = 2097153;
  SetLastError(0);
  if ( GetDIBits(CompatibleDC, hbm, 0, a2->cy, a4, &bmi, 0) )
  {
    v10 = 0;
    v15 = 0;
    v16 = 0;
    v17 = a4;
    while ( v16 < a2->cy )
    {
      v24 = 0;
      do
      {
        if ( v24 >= a2->cx )
          break;
        if ( v17[3] )
          v15 = 1;
        v17 += 4;
        ++v24;
      }
      while ( !v15 );
      ++v16;
      if ( v15 )
        goto LABEL_17;
    }
    for ( i = 0; i < a2->cy; ++i )
    {
      for ( j = 0; j < a2->cx; a4 += 4 )
      {
        a4[3] = -1;
        ++j;
      }
    }
  }
  else
  {
    v14 = GetLastError();
    v10 = v14;
    if ( v14 > 0 )
      v10 = (unsigned __int16)v14 | 0x80070000;
    if ( v10 >= 0 )
      v10 = -2003304445;
    DoStackCaptureDirect(v10, 0x30u);
  }
LABEL_17:
  DeleteDC(CompatibleDC);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180008ab4  push    rbx
0x180008ab6  push    rbp
0x180008ab7  push    rsi
0x180008ab8  push    rdi
0x180008ab9  push    r15
0x180008abb  sub     rsp, 80h
0x180008ac2  mov     rax, cs:__security_cookie
0x180008ac9  xor     rax, rsp
0x180008acc  mov     [rsp+0A8h+var_38], rax
0x180008ad1  movsxd  rax, dword ptr [rdx+4]
0x180008ad5  mov     rbx, rcx
0x180008ad8  movsxd  rcx, dword ptr [rdx]
0x180008adb  mov     rdi, rdx
0x180008ade  imul    rcx, rax
0x180008ae2  mov     edx, 80000000h
0x180008ae7  mov     rsi, r9
0x180008aea  mov     r9d, 0FFFFFFFFh
0x180008af0  lea     rax, [rcx+rdx]
0x180008af4  cmp     rax, r9
0x180008af7  jbe     loc_180008C1E
0x180008afd  mov     edx, 1Ch; unsigned int
0x180008b02  mov     ecx, 80070216h; int
0x180008b07  mov     ebx, ecx
0x180008b09  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180008b0e  mov     eax, ebx
0x180008b10  mov     rcx, [rsp+0A8h+var_38]
0x180008b15  xor     rcx, rsp; StackCookie
0x180008b18  call    __security_check_cookie
0x180008b1d  add     rsp, 80h
0x180008b24  pop     r15
0x180008b26  pop     rdi
0x180008b27  pop     rsi
0x180008b28  pop     rbp
0x180008b29  pop     rbx
0x180008b2a  retn
0x180008b2b  xor     ecx, ecx
0x180008b2d  cmp     [rdi+4], ecx
0x180008b30  jle     loc_180008BF1
0x180008b36  xor     eax, eax
0x180008b38  cmp     [rdi], eax
0x180008b3a  jle     short loc_180008B4B
0x180008b3c  mov     byte ptr [rsi+3], 0FFh
0x180008b40  add     eax, r15d
0x180008b43  add     rsi, 4
0x180008b47  cmp     eax, [rdi]
0x180008b49  jl      short loc_180008B3C
0x180008b4b  add     ecx, r15d
0x180008b4e  cmp     ecx, [rdi+4]
0x180008b51  jl      short loc_180008B36
0x180008b53  jmp     loc_180008BF1
0x180008b58  mov     eax, [rdi]
0x180008b5a  xorps   xmm0, xmm0
0x180008b5d  mov     [rsp+0A8h+bmi.bmiHeader.biWidth], eax
0x180008b61  xor     ecx, ecx; dwErrCode
0x180008b63  mov     eax, [rdi+4]
0x180008b66  mov     r15d, 1
0x180008b6c  neg     eax
0x180008b6e  mov     qword ptr [rsp+0A8h+bmi.bmiHeader.biClrImportant], 0
0x180008b77  mov     [rsp+0A8h+bmi.bmiHeader.biHeight], eax
0x180008b7b  movdqu  xmmword ptr [rsp+0A8h+bmi.bmiHeader.biSizeImage], xmm0
0x180008b81  mov     [rsp+0A8h+bmi.bmiHeader.biSize], 2Ch ; ','
0x180008b89  mov     qword ptr [rsp+0A8h+bmi.bmiHeader.biPlanes], 200001h
0x180008b92  call    cs:__imp_SetLastError
0x180008b98  mov     r9d, [rdi+4]; cLines
0x180008b9c  lea     rax, [rsp+0A8h+bmi]
0x180008ba1  mov     [rsp+0A8h+usage], 0; usage
0x180008ba9  xor     r8d, r8d; start
0x180008bac  mov     [rsp+0A8h+lpbmi], rax; lpbmi
0x180008bb1  mov     rdx, rbx; hbm
0x180008bb4  mov     rcx, rbp; hdc
0x180008bb7  mov     [rsp+0A8h+lpvBits], rsi; lpvBits
0x180008bbc  call    cs:__imp_GetDIBits
0x180008bc2  test    eax, eax
0x180008bc4  jnz     short loc_180008BFF
0x180008bc6  call    cs:__imp_GetLastError
0x180008bcc  mov     ebx, eax
0x180008bce  test    eax, eax
0x180008bd0  jle     short loc_180008BDB
0x180008bd2  movzx   ebx, ax
0x180008bd5  or      ebx, 80070000h
0x180008bdb  test    ebx, ebx
0x180008bdd  mov     eax, 88980003h
0x180008be2  mov     edx, 30h ; '0'; unsigned int
0x180008be7  cmovns  ebx, eax
0x180008bea  mov     ecx, ebx; int
0x180008bec  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180008bf1  mov     rcx, rbp; hdc
0x180008bf4  call    cs:__imp_DeleteDC
0x180008bfa  jmp     loc_180008B0E
0x180008bff  xor     ebx, ebx
0x180008c01  xor     al, al
0x180008c03  xor     ecx, ecx
0x180008c05  mov     r8, rsi
0x180008c08  cmp     ecx, [rdi+4]
0x180008c0b  jge     loc_180008B2B
0x180008c11  test    al, al
0x180008c13  jz      short loc_180008C8E
0x180008c15  add     ecx, r15d
0x180008c18  test    al, al
0x180008c1a  jz      short loc_180008C08
0x180008c1c  jmp     short loc_180008BF1
0x180008c1e  movsxd  rax, ecx
0x180008c21  lea     rcx, ds:0[rax*4]
0x180008c29  lea     rax, [rcx+rdx]
0x180008c2d  cmp     rax, r9
0x180008c30  jbe     short loc_180008C3C
0x180008c32  mov     edx, 1Dh
0x180008c37  jmp     loc_180008B02
0x180008c3c  cmp     ecx, r8d
0x180008c3f  jnz     short loc_180008C82
0x180008c41  xor     ecx, ecx; dwErrCode
0x180008c43  call    cs:__imp_SetLastError
0x180008c49  xor     ecx, ecx; hdc
0x180008c4b  call    cs:__imp_CreateCompatibleDC
0x180008c51  mov     rbp, rax
0x180008c54  test    rax, rax
0x180008c57  jnz     loc_180008B58
0x180008c5d  call    cs:__imp_GetLastError
0x180008c63  mov     ebx, eax
0x180008c65  test    eax, eax
0x180008c67  jle     short loc_180008C72
0x180008c69  movzx   ebx, ax
0x180008c6c  or      ebx, 80070000h
0x180008c72  test    ebx, ebx
0x180008c74  jns     short loc_180008CAF
0x180008c76  mov     edx, 23h ; '#'
0x180008c7b  mov     ecx, ebx
0x180008c7d  jmp     loc_180008B09
0x180008c82  mov     ebx, 80070057h
0x180008c87  mov     edx, 20h ; ' '
0x180008c8c  jmp     short loc_180008C7B
0x180008c8e  xor     edx, edx
0x180008c90  cmp     edx, [rdi]
0x180008c92  jge     short loc_180008C15
0x180008c94  cmp     [r8+3], bl
0x180008c98  movzx   eax, al
0x180008c9b  cmovnz  eax, r15d
0x180008c9f  add     r8, 4
0x180008ca3  add     edx, r15d
0x180008ca6  test    al, al
0x180008ca8  jz      short loc_180008C90
0x180008caa  jmp     loc_180008C15
0x180008caf  call    ?CheckGUIHandleQuota@@YAJKJJ@Z; CheckGUIHandleQuota(ulong,long,long)
0x180008cb4  mov     ebx, eax
0x180008cb6  jmp     short loc_180008C76
```
