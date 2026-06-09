# FileStream::Stat(tagSTATSTG *,ulong)

- ea: `0x1800cc030`
- end: `0x1800cc1fe`
- name: `?Stat@FileStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `462`
- prototype: `__int64 __fastcall(FileStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000cc00`
- `0x18006aafc`
- `0x1800cc030`
- `0x1800e9380`
- `0x1800ea0ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cc07d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cc07d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cc0fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cc0fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc0db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc0db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cc1a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cc1a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cc1cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cc1cb`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800cc0cb`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800cc0cb`

## pseudocode

```c
__int64 __fastcall FileStream::Stat(FileStream *this, struct tagSTATSTG *a2, char a3)
{
  signed int v6; // ebx
  const unsigned __int16 *v7; // rdx
  GpRuntime *v8; // rdi
  void *v9; // rcx
  signed int LastError; // eax
  int v12; // eax
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  const unsigned __int16 *v17; // r15
  GpRuntime *v18; // rax
  unsigned __int64 v19; // r9
  _OWORD v20[2]; // [rsp+30h] [rbp-59h] BYREF
  __int128 v21; // [rsp+50h] [rbp-39h]
  __int128 v22; // [rsp+60h] [rbp-29h]
  __int128 v23; // [rsp+70h] [rbp-19h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+80h] [rbp-9h] BYREF

  memset(&FileInformation, 0, sizeof(FileInformation));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((_QWORD *)this + 9) == -1 )
  {
    v6 = -2147286782;
    goto LABEL_8;
  }
  v6 = 0;
  memset_0(v20, 0, 0x50u);
  if ( (a3 & 1) != 0 )
  {
    v8 = 0;
    *(_QWORD *)&v20[0] = 0;
  }
  else
  {
    v17 = (const unsigned __int16 *)(GpRuntime::UnicodeStringLength(*((GpRuntime **)this + 7), v7) + 1);
    v18 = (GpRuntime *)CoTaskMemAlloc(2LL * (_QWORD)v17);
    *(_QWORD *)&v20[0] = v18;
    v8 = v18;
    if ( !v18 )
    {
      v6 = -2147287032;
LABEL_13:
      if ( v8 )
        CoTaskMemFree(v8);
      goto LABEL_8;
    }
    GpRuntime::UnicodeStringCopyCount(v18, *((unsigned __int16 **)this + 7), v17, v19);
  }
  v9 = (void *)*((_QWORD *)this + 9);
  DWORD2(v20[0]) = 2;
  DWORD1(v22) = 6;
  if ( GetFileInformationByHandle(v9, &FileInformation) )
  {
    v21 = 0u;
    v20[1] = __PAIR64__(FileInformation.nFileSizeHigh, FileInformation.nFileSizeLow);
    v12 = *((_DWORD *)this + 16);
    v13 = __PAIR64__(FileInformation.nFileSizeHigh, FileInformation.nFileSizeLow);
    *(_OWORD *)a2 = v20[0];
    LODWORD(v22) = v12 & 0xFFFFEFFF;
    v14 = v21;
    *((_OWORD *)a2 + 1) = v13;
    v15 = v22;
    *((_OWORD *)a2 + 2) = v14;
    v16 = v23;
    *((_OWORD *)a2 + 3) = v15;
    *((_OWORD *)a2 + 4) = v16;
    goto LABEL_8;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_13;
LABEL_8:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800cc030  mov     [rsp-8+arg_10], rbx
0x1800cc035  mov     [rsp-8+arg_18], rsi
0x1800cc03a  push    rbp
0x1800cc03b  push    rdi
0x1800cc03c  push    r12
0x1800cc03e  push    r14
0x1800cc040  push    r15
0x1800cc042  lea     rbp, [rsp-37h]
0x1800cc047  sub     rsp, 0C0h
0x1800cc04e  mov     rax, cs:__security_cookie
0x1800cc055  xor     rax, rsp
0x1800cc058  mov     [rbp+57h+var_28], rax
0x1800cc05c  xorps   xmm0, xmm0
0x1800cc05f  mov     rsi, rcx
0x1800cc062  xor     eax, eax
0x1800cc064  add     rcx, 8; lpCriticalSection
0x1800cc068  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x1800cc06c  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x1800cc06f  mov     edi, r8d
0x1800cc072  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800cc076  mov     r14, rdx
0x1800cc079  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x1800cc07d  call    cs:__imp_EnterCriticalSection
0x1800cc084  nop     dword ptr [rax+rax+00h]
0x1800cc089  cmp     qword ptr [rsi+48h], 0FFFFFFFFFFFFFFFFh
0x1800cc08e  jz      loc_1800CC187
0x1800cc094  xor     ebx, ebx
0x1800cc096  lea     rcx, [rbp+57h+var_B0]; void *
0x1800cc09a  xor     edx, edx; Val
0x1800cc09c  lea     r8d, [rbx+50h]; Size
0x1800cc0a0  call    memset_0
0x1800cc0a5  test    dil, 1
0x1800cc0a9  jz      loc_1800CC191
0x1800cc0af  xor     edi, edi
0x1800cc0b1  mov     qword ptr [rbp+57h+var_B0], rdi
0x1800cc0b5  mov     rcx, [rsi+48h]; hFile
0x1800cc0b9  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x1800cc0bd  mov     dword ptr [rbp+57h+var_B0+8], 2
0x1800cc0c4  mov     dword ptr [rbp+57h+var_80+4], 6
0x1800cc0cb  call    cs:__imp_GetFileInformationByHandle
0x1800cc0d2  nop     dword ptr [rax+rax+00h]
0x1800cc0d7  test    eax, eax
0x1800cc0d9  jnz     short loc_1800CC134
0x1800cc0db  call    cs:__imp_GetLastError
0x1800cc0e2  nop     dword ptr [rax+rax+00h]
0x1800cc0e7  mov     ebx, eax
0x1800cc0e9  test    eax, eax
0x1800cc0eb  jg      loc_1800CC1F0
0x1800cc0f1  test    ebx, ebx
0x1800cc0f3  js      loc_1800CC1BF
0x1800cc0f9  lea     rcx, [rsi+8]; lpCriticalSection
0x1800cc0fd  call    cs:__imp_LeaveCriticalSection
0x1800cc104  nop     dword ptr [rax+rax+00h]
0x1800cc109  mov     eax, ebx
0x1800cc10b  mov     rcx, [rbp+57h+var_28]
0x1800cc10f  xor     rcx, rsp; StackCookie
0x1800cc112  call    __security_check_cookie
0x1800cc117  lea     r11, [rsp+0E0h+var_20]
0x1800cc11f  mov     rbx, [r11+40h]
0x1800cc123  mov     rsi, [r11+48h]
0x1800cc127  mov     rsp, r11
0x1800cc12a  pop     r15
0x1800cc12c  pop     r14
0x1800cc12e  pop     r12
0x1800cc130  pop     rdi
0x1800cc131  pop     rbp
0x1800cc132  retn
0x1800cc134  mov     eax, [rbp+57h+FileInformation.nFileSizeLow]
0x1800cc137  and     qword ptr [rbp+57h+var_90], rbx
0x1800cc13b  and     qword ptr [rbp+57h+var_90+8], rbx
0x1800cc13f  and     qword ptr [rbp+57h+var_A0+8], rbx
0x1800cc143  movaps  xmm0, [rbp+57h+var_B0]
0x1800cc147  mov     dword ptr [rbp+57h+var_A0], eax
0x1800cc14a  mov     eax, [rbp+57h+FileInformation.nFileSizeHigh]
0x1800cc14d  mov     dword ptr [rbp+57h+var_A0+4], eax
0x1800cc150  mov     eax, [rsi+40h]
0x1800cc153  movaps  xmm1, [rbp+57h+var_A0]
0x1800cc157  btr     eax, 0Ch
0x1800cc15b  movups  xmmword ptr [r14], xmm0
0x1800cc15f  mov     dword ptr [rbp+57h+var_80], eax
0x1800cc162  movaps  xmm0, [rbp+57h+var_90]
0x1800cc166  movups  xmmword ptr [r14+10h], xmm1
0x1800cc16b  movaps  xmm1, [rbp+57h+var_80]
0x1800cc16f  movups  xmmword ptr [r14+20h], xmm0
0x1800cc174  movaps  xmm0, [rbp+57h+var_70]
0x1800cc178  movups  xmmword ptr [r14+30h], xmm1
0x1800cc17d  movups  xmmword ptr [r14+40h], xmm0
0x1800cc182  jmp     loc_1800CC0F9
0x1800cc187  mov     ebx, 80030102h
0x1800cc18c  jmp     loc_1800CC0F9
0x1800cc191  mov     rcx, [rsi+38h]; this
0x1800cc195  call    ?UnicodeStringLength@GpRuntime@@YA_KPEBG@Z; GpRuntime::UnicodeStringLength(ushort const *)
0x1800cc19a  lea     r15, [rax+1]
0x1800cc19e  lea     rcx, [r15+r15]; cb
0x1800cc1a2  call    cs:__imp_CoTaskMemAlloc
0x1800cc1a9  nop     dword ptr [rax+rax+00h]
0x1800cc1ae  mov     qword ptr [rbp+57h+var_B0], rax
0x1800cc1b2  mov     rdi, rax
0x1800cc1b5  test    rax, rax
0x1800cc1b8  jnz     short loc_1800CC1DC
0x1800cc1ba  mov     ebx, 80030008h
0x1800cc1bf  test    rdi, rdi
0x1800cc1c2  jz      loc_1800CC0F9
0x1800cc1c8  mov     rcx, rdi; pv
0x1800cc1cb  call    cs:__imp_CoTaskMemFree
0x1800cc1d2  nop     dword ptr [rax+rax+00h]
0x1800cc1d7  jmp     loc_1800CC0F9
0x1800cc1dc  mov     rdx, [rsi+38h]; unsigned __int16 *
0x1800cc1e0  mov     r8, r15; unsigned __int16 *
0x1800cc1e3  mov     rcx, rax; this
0x1800cc1e6  call    ?UnicodeStringCopyCount@GpRuntime@@YAXPEAGPEBG_K@Z; GpRuntime::UnicodeStringCopyCount(ushort *,ushort const *,unsigned __int64)
0x1800cc1eb  jmp     loc_1800CC0B5
0x1800cc1f0  movzx   ebx, ax
0x1800cc1f3  or      ebx, 80070000h
0x1800cc1f9  jmp     loc_1800CC0F1
```
