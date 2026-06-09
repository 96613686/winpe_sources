# CWERReporter::CWERReporter(ulong,ushort const *)

- ea: `0x18002ba68`
- end: `0x18002bd09`
- name: `??0CWERReporter@@QEAA@KPEBG@Z`
- size: `673`
- prototype: `CWERReporter *__fastcall(CWERReporter *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1801b1840`

## callees

- `0x180010ac0`
- `0x18002ba68`
- `0x18002bd10`
- `0x180159ccc`
- `0x180259ac0`
- `0x1802651d2`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `msvcrt!rand` at `0x18002bc0a`
- `msvcrt!rand` at `0x18002bc0a`
- `KERNEL32!CreateFileMappingW` at `0x18002bc45`
- `KERNEL32!CreateFileMappingW` at `0x18002bc45`
- `KERNEL32!MapViewOfFile` at `0x18002bc71`
- `KERNEL32!MapViewOfFile` at `0x18002bc71`
- `KERNEL32!UnmapViewOfFile` at `0x18002bc96`
- `KERNEL32!UnmapViewOfFile` at `0x18002bc96`
- `KERNEL32!CloseHandle` at `0x18002bcc2`
- `KERNEL32!CloseHandle` at `0x18002bcc2`
- `KERNEL32!DeleteFileW` at `0x18002bcd1`
- `KERNEL32!DeleteFileW` at `0x18002bcd1`

## pseudocode

```c
CWERReporter *__fastcall CWERReporter::CWERReporter(CWERReporter *this, int a2, const unsigned __int16 *a3)
{
  unsigned __int16 **v3; // r14
  CWERReporter *v7; // rcx
  char *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  char *v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // r8d
  HANDLE FileMappingW; // rax
  void *v15; // rbx
  int Src; // [rsp+30h] [rbp-708h] BYREF
  unsigned __int16 v18[39]; // [rsp+34h] [rbp-704h] BYREF
  unsigned __int16 v19[256]; // [rsp+82h] [rbp-6B6h] BYREF
  unsigned __int16 v20[256]; // [rsp+282h] [rbp-4B6h] BYREF
  unsigned __int16 v21[33]; // [rsp+482h] [rbp-2B6h] BYREF
  char v22; // [rsp+4C4h] [rbp-274h] BYREF
  unsigned __int16 v23[38]; // [rsp+6C4h] [rbp-74h] BYREF

  *((_DWORD *)this + 3) = a2;
  v3 = (unsigned __int16 **)((char *)this + 552);
  *((_BYTE *)this + 8) = 0;
  *((_DWORD *)this + 6) = 0;
  *(_QWORD *)this = &CWERReporter::`vftable';
  *((_QWORD *)this + 2) = -1;
  *((_QWORD *)this + 69) = 0;
  memset_0(v18, 0, 0x6D4u);
  if ( g_scServerContext == 3 )
  {
    if ( a3 )
    {
      if ( a2 )
      {
        Src = 3;
        if ( CWERReporter::GetWERRuntimeModuleName(v7, v3) )
        {
          if ( (int)StringCchPrintfW(v23, 0x21u, L"%.2f", DOUBLE_5_0) >= 0 )
          {
            v8 = &v22;
            v9 = 256;
            v10 = 2147483646;
            do
            {
              if ( !v10 )
                break;
              if ( !*a3 )
                break;
              *(_WORD *)v8 = *a3++;
              v8 += 2;
              --v10;
              --v9;
            }
            while ( v9 );
            v11 = v8 - 2;
            if ( v9 )
              v11 = v8;
            *(_WORD *)v11 = 0;
            if ( v9
              && (CWERReporter::CopyPropertyTo(this, L"ProductCode", v18, 0x27u) & 0x80000000) == 0
              && (CWERReporter::CopyPropertyTo(this, L"ProductName", v19, 0x100u) & 0x80000000) == 0
              && (CWERReporter::CopyPropertyTo(this, L"Manufacturer", v20, 0x100u) & 0x80000000) == 0
              && (CWERReporter::CopyPropertyTo(this, L"ProductVersion", v21, 0x21u) & 0x80000000) == 0 )
            {
              v12 = rand();
              *((_DWORD *)this + 6) = v12;
              if ( !WERGetFullSharedMemoryName((void *)v12, (unsigned __int16 *)this + 14, v13) )
              {
                FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x6D8u, (LPCWSTR)this + 14);
                *((_QWORD *)this + 2) = FileMappingW;
                if ( FileMappingW )
                {
                  v15 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, 0x6D8u);
                  memcpy_0(v15, &Src, 0x6D8u);
                  UnmapViewOfFile(v15);
                }
              }
              if ( (int)((__int64 (__fastcall *)(unsigned __int16 *, _QWORD))KERNEL32::WerRegisterRuntimeExceptionModule)(
                          *v3,
                          *((unsigned int *)this + 6)) < 0 )
              {
                CloseHandle(*((HANDLE *)this + 2));
                DeleteFileW((LPCWSTR)this + 14);
              }
              else
              {
                *((_BYTE *)this + 8) = 1;
              }
            }
          }
        }
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x18002ba68  mov     [rsp+arg_8], rbx
0x18002ba6d  mov     [rsp+arg_10], rbp
0x18002ba72  push    rsi
0x18002ba73  push    rdi
0x18002ba74  push    r14
0x18002ba76  sub     rsp, 720h
0x18002ba7d  mov     rax, cs:__security_cookie
0x18002ba84  xor     rax, rsp
0x18002ba87  mov     [rsp+738h+var_28], rax
0x18002ba8f  xor     ebp, ebp
0x18002ba91  mov     [rcx+0Ch], edx
0x18002ba94  lea     r14, [rcx+228h]
0x18002ba9b  mov     [rcx+8], bpl
0x18002ba9f  lea     rax, ??_7CWERReporter@@6B@; const CWERReporter::`vftable'
0x18002baa6  mov     [rcx+18h], ebp
0x18002baa9  mov     [rcx], rax
0x18002baac  mov     rbx, r8
0x18002baaf  mov     esi, edx
0x18002bab1  mov     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x18002bab9  mov     rdi, rcx
0x18002babc  mov     [r14], rbp
0x18002babf  lea     rcx, [rsp+738h+var_704]; void *
0x18002bac4  xor     edx, edx; Val
0x18002bac6  mov     r8d, 6D4h; Size
0x18002bacc  call    memset_0
0x18002bad1  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 3; scEnum g_scServerContext
0x18002bad8  jnz     loc_18002BCDD
0x18002bade  test    rbx, rbx
0x18002bae1  jz      loc_18002BCDD
0x18002bae7  test    esi, esi
0x18002bae9  jz      loc_18002BCDD
0x18002baef  mov     rdx, r14; unsigned __int16 **
0x18002baf2  mov     [rsp+738h+Src], 3
0x18002bafa  call    ?GetWERRuntimeModuleName@CWERReporter@@AEAAKPEAPEAG@Z; CWERReporter::GetWERRuntimeModuleName(ushort * *)
0x18002baff  test    eax, eax
0x18002bb01  jz      loc_18002BCDD
0x18002bb07  movsd   xmm3, cs:__real@4014000000000000
0x18002bb0f  lea     r8, a2f; "%.2f"
0x18002bb16  movq    r9, xmm3
0x18002bb1b  lea     edx, [rbp+21h]; unsigned __int64
0x18002bb1e  lea     rcx, [rsp+738h+var_74]; unsigned __int16 *
0x18002bb26  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bb2b  test    eax, eax
0x18002bb2d  js      loc_18002BCDD
0x18002bb33  mov     esi, 100h
0x18002bb38  lea     rax, [rsp+738h+var_274]
0x18002bb40  mov     edx, esi
0x18002bb42  mov     ecx, 7FFFFFFEh
0x18002bb47  test    rcx, rcx
0x18002bb4a  jz      short loc_18002BB6B
0x18002bb4c  movzx   r8d, word ptr [rbx]
0x18002bb50  test    r8w, r8w
0x18002bb54  jz      short loc_18002BB6B
0x18002bb56  mov     [rax], r8w
0x18002bb5a  add     rbx, 2
0x18002bb5e  add     rax, 2
0x18002bb62  dec     rcx
0x18002bb65  sub     rdx, 1
0x18002bb69  jnz     short loc_18002BB47
0x18002bb6b  test    rdx, rdx
0x18002bb6e  lea     rcx, [rax-2]
0x18002bb72  cmovnz  rcx, rax
0x18002bb76  mov     [rcx], bp
0x18002bb79  jz      loc_18002BCDD
0x18002bb7f  mov     r9d, 27h ; '''; unsigned int
0x18002bb85  lea     r8, [rsp+738h+var_704]; unsigned __int16 *
0x18002bb8a  lea     rdx, aProductcode; "ProductCode"
0x18002bb91  mov     rcx, rdi; this
0x18002bb94  call    ?CopyPropertyTo@CWERReporter@@AEAAKPEBGPEAGK@Z; CWERReporter::CopyPropertyTo(ushort const *,ushort *,ulong)
0x18002bb99  test    eax, eax
0x18002bb9b  js      loc_18002BCDD
0x18002bba1  mov     r9d, esi; unsigned int
0x18002bba4  lea     r8, [rsp+738h+var_6B6]; unsigned __int16 *
0x18002bbac  lea     rdx, aProductname; "ProductName"
0x18002bbb3  mov     rcx, rdi; this
0x18002bbb6  call    ?CopyPropertyTo@CWERReporter@@AEAAKPEBGPEAGK@Z; CWERReporter::CopyPropertyTo(ushort const *,ushort *,ulong)
0x18002bbbb  test    eax, eax
0x18002bbbd  js      loc_18002BCDD
0x18002bbc3  mov     r9d, esi; unsigned int
0x18002bbc6  lea     r8, [rsp+738h+var_4B6]; unsigned __int16 *
0x18002bbce  lea     rdx, aManufacturer; "Manufacturer"
0x18002bbd5  mov     rcx, rdi; this
0x18002bbd8  call    ?CopyPropertyTo@CWERReporter@@AEAAKPEBGPEAGK@Z; CWERReporter::CopyPropertyTo(ushort const *,ushort *,ulong)
0x18002bbdd  test    eax, eax
0x18002bbdf  js      loc_18002BCDD
0x18002bbe5  mov     r9d, 21h ; '!'; unsigned int
0x18002bbeb  lea     r8, [rsp+738h+var_2B6]; unsigned __int16 *
0x18002bbf3  lea     rdx, aProductversion; "ProductVersion"
0x18002bbfa  mov     rcx, rdi; this
0x18002bbfd  call    ?CopyPropertyTo@CWERReporter@@AEAAKPEBGPEAGK@Z; CWERReporter::CopyPropertyTo(ushort const *,ushort *,ulong)
0x18002bc02  test    eax, eax
0x18002bc04  js      loc_18002BCDD
0x18002bc0a  call    cs:__imp_rand
0x18002bc11  nop     dword ptr [rax+rax+00h]
0x18002bc16  mov     ecx, eax; void *
0x18002bc18  lea     rsi, [rdi+1Ch]
0x18002bc1c  mov     rdx, rsi; unsigned __int16 *
0x18002bc1f  mov     [rdi+18h], ecx
0x18002bc22  call    ?WERGetFullSharedMemoryName@@YAKPEAXPEAGK@Z; WERGetFullSharedMemoryName(void *,ushort *,ulong)
0x18002bc27  test    eax, eax
0x18002bc29  jnz     short loc_18002BCA2
0x18002bc2b  mov     [rsp+738h+lpName], rsi; lpName
0x18002bc30  lea     r8d, [rax+4]; flProtect
0x18002bc34  xor     r9d, r9d; dwMaximumSizeHigh
0x18002bc37  mov     [rsp+738h+dwMaximumSizeLow], 6D8h; dwMaximumSizeLow
0x18002bc3f  xor     edx, edx; lpFileMappingAttributes
0x18002bc41  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18002bc45  call    cs:__imp_CreateFileMappingW
0x18002bc4c  nop     dword ptr [rax+rax+00h]
0x18002bc51  mov     [rdi+10h], rax
0x18002bc55  test    rax, rax
0x18002bc58  jz      short loc_18002BCA2
0x18002bc5a  xor     r9d, r9d; dwFileOffsetLow
0x18002bc5d  mov     qword ptr [rsp+738h+dwMaximumSizeLow], 6D8h; dwNumberOfBytesToMap
0x18002bc66  xor     r8d, r8d; dwFileOffsetHigh
0x18002bc69  mov     edx, 0F001Fh; dwDesiredAccess
0x18002bc6e  mov     rcx, rax; hFileMappingObject
0x18002bc71  call    cs:__imp_MapViewOfFile
0x18002bc78  nop     dword ptr [rax+rax+00h]
0x18002bc7d  lea     rdx, [rsp+738h+Src]; Src
0x18002bc82  mov     r8d, 6D8h; Size
0x18002bc88  mov     rcx, rax; void *
0x18002bc8b  mov     rbx, rax
0x18002bc8e  call    memcpy_0
0x18002bc93  mov     rcx, rbx; lpBaseAddress
0x18002bc96  call    cs:__imp_UnmapViewOfFile
0x18002bc9d  nop     dword ptr [rax+rax+00h]
0x18002bca2  mov     edx, [rdi+18h]
0x18002bca5  mov     rcx, [r14]
0x18002bca8  mov     rax, cs:?WerRegisterRuntimeExceptionModule@KERNEL32@@3P6AJPEBGPEAX@ZEA; long (*KERNEL32::WerRegisterRuntimeExceptionModule)(ushort const *,void *)
0x18002bcaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcb4  test    eax, eax
0x18002bcb6  js      short loc_18002BCBE
0x18002bcb8  mov     byte ptr [rdi+8], 1
0x18002bcbc  jmp     short loc_18002BCDD
0x18002bcbe  mov     rcx, [rdi+10h]; hObject
0x18002bcc2  call    cs:__imp_CloseHandle
0x18002bcc9  nop     dword ptr [rax+rax+00h]
0x18002bcce  mov     rcx, rsi; lpFileName
0x18002bcd1  call    cs:__imp_DeleteFileW
0x18002bcd8  nop     dword ptr [rax+rax+00h]
0x18002bcdd  mov     rax, rdi
0x18002bce0  mov     rcx, [rsp+738h+var_28]
0x18002bce8  xor     rcx, rsp; StackCookie
0x18002bceb  call    __security_check_cookie
0x18002bcf0  lea     r11, [rsp+738h+var_18]
0x18002bcf8  mov     rbx, [r11+28h]
0x18002bcfc  mov     rbp, [r11+30h]
0x18002bd00  mov     rsp, r11
0x18002bd03  pop     r14
0x18002bd05  pop     rdi
0x18002bd06  pop     rsi
0x18002bd07  retn
```
