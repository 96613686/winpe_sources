# CMsiPath::Remove(bool *)

- ea: `0x18012ad80`
- end: `0x18012b13a`
- name: `?Remove@CMsiPath@@UEAAPEAVIMsiRecord@@PEA_N@Z`
- size: `954`
- prototype: `struct IMsiRecord *__fastcall(CMsiPath *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callees

- `0x18009cdb8`
- `0x18009d06c`
- `0x1800dcef8`
- `0x1800ee66c`
- `0x18012ad80`
- `0x180153e68`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18012ae2d`
- `KERNEL32!GetLastError` at `0x18012aeec`
- `KERNEL32!GetLastError` at `0x18012ae2d`
- `KERNEL32!GetLastError` at `0x18012aeec`
- `KERNEL32!FindFirstFileW` at `0x18012afeb`
- `KERNEL32!FindFirstFileW` at `0x18012afeb`
- `KERNEL32!FindNextFileW` at `0x18012b04b`
- `KERNEL32!FindNextFileW` at `0x18012b04b`
- `KERNEL32!FindClose` at `0x18012b062`
- `KERNEL32!FindClose` at `0x18012b062`
- `KERNEL32!RemoveDirectoryW` at `0x18012ae15`
- `KERNEL32!RemoveDirectoryW` at `0x18012aed4`
- `KERNEL32!RemoveDirectoryW` at `0x18012ae15`
- `KERNEL32!RemoveDirectoryW` at `0x18012aed4`

## pseudocode

```c
struct IMsiRecord *__fastcall CMsiPath::Remove(CMsiPath *this, bool *a2)
{
  int v4; // edi
  const WCHAR *v5; // rax
  BOOL v6; // r12d
  BOOL v7; // r15d
  bool v8; // cl
  DWORD LastError; // esi
  __int64 v10; // rax
  __int64 v11; // rsi
  const WCHAR *v13; // rax
  BOOL v14; // r12d
  bool v15; // cl
  __int64 v16; // r12
  MsiString *v17; // rax
  const WCHAR *v18; // rax
  HANDLE FirstFileW; // r14
  int v20; // edx
  int v21; // edx
  __int64 v22; // rbx
  const unsigned __int16 *v23; // rax
  struct IMsiRecord *v24; // rdi
  void (*v25)(void); // rax
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF

  if ( a2 )
    *a2 = 0;
  v26 = (*(__int64 (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 56LL))(this);
  v4 = 1;
  (*(void (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v26 + 192LL))(v26, 4, 1, &v26);
  if ( *((_DWORD *)this + 12) )
    StartImpersonating();
  v5 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 80LL))(v26);
  v6 = RemoveDirectoryW(v5);
  v7 = v6;
  LastError = GetLastError();
  if ( *((_DWORD *)this + 12) )
    StopImpersonating(v8);
  if ( !v6 && LastError == 5 )
  {
    v10 = *(_QWORD *)this;
    LODWORD(v27) = 0;
    v11 = (*(__int64 (__fastcall **)(CMsiPath *, _QWORD, __int64 *))(v10 + 384))(this, 0, &v27);
    if ( v11
      || (v11 = (*(__int64 (__fastcall **)(CMsiPath *, _QWORD, _QWORD))(*(_QWORD *)this + 392LL))(this, 0, 0)) != 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      return (struct IMsiRecord *)v11;
    }
    if ( *((_DWORD *)this + 12) )
      StartImpersonating();
    v13 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 80LL))(v26);
    v14 = RemoveDirectoryW(v13);
    v7 = v14;
    LastError = GetLastError();
    if ( *((_DWORD *)this + 12) )
      StopImpersonating(v15);
    if ( !v14 )
    {
      v16 = (*(__int64 (__fastcall **)(CMsiPath *, _QWORD, _QWORD))(*(_QWORD *)this + 392LL))(
              this,
              0,
              (unsigned int)v27);
      if ( v16 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        return (struct IMsiRecord *)v16;
      }
    }
  }
  if ( v7 )
  {
    if ( a2 )
      *a2 = 1;
LABEL_40:
    v25 = *(void (**)(void))(*(_QWORD *)this + 576LL);
    goto LABEL_41;
  }
  if ( LastError == 145 || LastError - 2 <= 1 || LastError == 303 )
    goto LABEL_40;
  v27 = (*(__int64 (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 56LL))(this);
  v17 = MsiString::MsiString((MsiString *)&v28, L"*.*");
  MsiString::operator+=(&v27, v17);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v18 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 80LL))(v27);
  FirstFileW = FindFirstFileW(v18, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    while ( 1 )
    {
      v20 = FindFileData.cFileName[0] - 46;
      if ( FindFileData.cFileName[0] == 46 )
        v20 = FindFileData.cFileName[1];
      if ( v20 )
      {
        v21 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
        {
          v21 = FindFileData.cFileName[1] - 46;
          if ( FindFileData.cFileName[1] == 46 )
            v21 = FindFileData.cFileName[2];
        }
        if ( v21 )
          break;
      }
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
        goto LABEL_37;
    }
    v4 = 0;
  }
LABEL_37:
  FindClose(FirstFileW);
  if ( v4 )
  {
    v22 = (*(__int64 (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 56LL))(this);
    v23 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 80LL))(v22);
    v24 = PostError(2327, LastError, v23);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    return v24;
  }
  v25 = *(void (**)(void))(*(_QWORD *)v27 + 16LL);
LABEL_41:
  v25();
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return 0;
}

```

## disassembly

```asm
0x18012ad80  mov     [rsp-8+arg_10], rbx
0x18012ad85  mov     [rsp-8+arg_18], rsi
0x18012ad8a  push    rbp
0x18012ad8b  push    rdi
0x18012ad8c  push    r12
0x18012ad8e  push    r14
0x18012ad90  push    r15
0x18012ad92  lea     rbp, [rsp-1B0h]
0x18012ad9a  sub     rsp, 2B0h
0x18012ada1  mov     rax, cs:__security_cookie
0x18012ada8  xor     rax, rsp
0x18012adab  mov     [rbp+1D0h+var_30], rax
0x18012adb2  mov     r14, rdx
0x18012adb5  mov     rbx, rcx
0x18012adb8  test    rdx, rdx
0x18012adbb  jz      short loc_18012ADC0
0x18012adbd  mov     byte ptr [rdx], 0
0x18012adc0  mov     rax, [rcx]
0x18012adc3  mov     rax, [rax+38h]
0x18012adc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012adcc  mov     [rsp+2D0h+var_2A0], rax
0x18012add1  lea     r9, [rsp+2D0h+var_2A0]
0x18012add6  mov     edi, 1
0x18012addb  mov     r8d, edi
0x18012adde  mov     rcx, [rax]
0x18012ade1  lea     edx, [rdi+3]
0x18012ade4  mov     r10, [rcx+0C0h]
0x18012adeb  mov     rcx, rax
0x18012adee  mov     rax, r10
0x18012adf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012adf6  cmp     dword ptr [rbx+30h], 0
0x18012adfa  jz      short loc_18012AE01
0x18012adfc  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x18012ae01  mov     rcx, [rsp+2D0h+var_2A0]
0x18012ae06  mov     rax, [rcx]
0x18012ae09  mov     rax, [rax+50h]
0x18012ae0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ae12  mov     rcx, rax; lpPathName
0x18012ae15  call    cs:__imp_RemoveDirectoryW
0x18012ae1c  nop     dword ptr [rax+rax+00h]
0x18012ae21  xor     r15d, r15d
0x18012ae24  mov     r12d, eax
0x18012ae27  test    eax, eax
0x18012ae29  setnz   r15b
0x18012ae2d  call    cs:__imp_GetLastError
0x18012ae34  nop     dword ptr [rax+rax+00h]
0x18012ae39  cmp     dword ptr [rbx+30h], 0
0x18012ae3d  mov     esi, eax
0x18012ae3f  jz      short loc_18012AE46
0x18012ae41  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x18012ae46  test    r12d, r12d
0x18012ae49  jnz     loc_18012AF44
0x18012ae4f  cmp     esi, 5
0x18012ae52  jnz     loc_18012AF44
0x18012ae58  mov     rax, [rbx]
0x18012ae5b  lea     r8, [rsp+2D0h+var_298]
0x18012ae60  xor     edx, edx
0x18012ae62  mov     dword ptr [rsp+2D0h+var_298], r12d
0x18012ae67  mov     rcx, rbx
0x18012ae6a  mov     rax, [rax+180h]
0x18012ae71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ae76  mov     rsi, rax
0x18012ae79  test    rax, rax
0x18012ae7c  jz      short loc_18012AE97
0x18012ae7e  mov     rcx, [rsp+2D0h+var_2A0]
0x18012ae83  mov     rdx, [rcx]
0x18012ae86  mov     rax, [rdx+10h]
0x18012ae8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ae8f  mov     rax, rsi
0x18012ae92  jmp     loc_18012B10E
0x18012ae97  mov     rax, [rbx]
0x18012ae9a  xor     r8d, r8d
0x18012ae9d  xor     edx, edx
0x18012ae9f  mov     rcx, rbx
0x18012aea2  mov     rax, [rax+188h]
0x18012aea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012aeae  mov     rsi, rax
0x18012aeb1  test    rax, rax
0x18012aeb4  jnz     short loc_18012AE7E
0x18012aeb6  cmp     [rbx+30h], eax
0x18012aeb9  jz      short loc_18012AEC0
0x18012aebb  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x18012aec0  mov     rcx, [rsp+2D0h+var_2A0]
0x18012aec5  mov     rax, [rcx]
0x18012aec8  mov     rax, [rax+50h]
0x18012aecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012aed1  mov     rcx, rax; lpPathName
0x18012aed4  call    cs:__imp_RemoveDirectoryW
0x18012aedb  nop     dword ptr [rax+rax+00h]
0x18012aee0  xor     r15d, r15d
0x18012aee3  mov     r12d, eax
0x18012aee6  test    eax, eax
0x18012aee8  setnz   r15b
0x18012aeec  call    cs:__imp_GetLastError
0x18012aef3  nop     dword ptr [rax+rax+00h]
0x18012aef8  cmp     dword ptr [rbx+30h], 0
0x18012aefc  mov     esi, eax
0x18012aefe  jz      short loc_18012AF05
0x18012af00  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x18012af05  test    r12d, r12d
0x18012af08  jnz     short loc_18012AF44
0x18012af0a  mov     rax, [rbx]
0x18012af0d  xor     edx, edx
0x18012af0f  mov     r8d, dword ptr [rsp+2D0h+var_298]
0x18012af14  mov     rcx, rbx
0x18012af17  mov     rax, [rax+188h]
0x18012af1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012af23  mov     r12, rax
0x18012af26  test    rax, rax
0x18012af29  jz      short loc_18012AF44
0x18012af2b  mov     rcx, [rsp+2D0h+var_2A0]
0x18012af30  mov     rdx, [rcx]
0x18012af33  mov     rax, [rdx+10h]
0x18012af37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012af3c  mov     rax, r12
0x18012af3f  jmp     loc_18012B10E
0x18012af44  test    r15d, r15d
0x18012af47  jz      short loc_18012AF5A
0x18012af49  test    r14, r14
0x18012af4c  jz      short loc_18012AF51
0x18012af4e  mov     [r14], dil
0x18012af51  cmp     r15d, edi
0x18012af54  jz      loc_18012B0E9
0x18012af5a  cmp     esi, 91h
0x18012af60  jz      loc_18012B0E9
0x18012af66  lea     eax, [rsi-2]
0x18012af69  cmp     eax, edi
0x18012af6b  jbe     loc_18012B0E9
0x18012af71  cmp     esi, 12Fh
0x18012af77  jz      loc_18012B0E9
0x18012af7d  mov     rax, [rbx]
0x18012af80  mov     rcx, rbx
0x18012af83  mov     rax, [rax+38h]
0x18012af87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012af8c  lea     rdx, asc_180290C50; "*.*"
0x18012af93  mov     [rsp+2D0h+var_298], rax
0x18012af98  lea     rcx, [rsp+2D0h+var_290]; this
0x18012af9d  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x18012afa2  mov     rdx, rax
0x18012afa5  lea     rcx, [rsp+2D0h+var_298]
0x18012afaa  call    ??YMsiString@@QEAAAEAV0@AEBV0@@Z; MsiString::operator+=(MsiString const &)
0x18012afaf  mov     rcx, [rsp+2D0h+var_290]
0x18012afb4  mov     rax, [rcx]
0x18012afb7  mov     rax, [rax+10h]
0x18012afbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012afc0  xor     edx, edx; Val
0x18012afc2  lea     rcx, [rsp+2D0h+FindFileData]; void *
0x18012afc7  mov     r8d, 250h; Size
0x18012afcd  call    memset_0
0x18012afd2  mov     rcx, [rsp+2D0h+var_298]
0x18012afd7  mov     rax, [rcx]
0x18012afda  mov     rax, [rax+50h]
0x18012afde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012afe3  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x18012afe8  mov     rcx, rax; lpFileName
0x18012afeb  call    cs:__imp_FindFirstFileW
0x18012aff2  nop     dword ptr [rax+rax+00h]
0x18012aff7  mov     r14, rax
0x18012affa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18012affe  jz      short loc_18012B05F
0x18012b000  mov     r15d, 2Eh ; '.'
0x18012b006  movzx   edx, [rsp+2D0h+FindFileData.cFileName]
0x18012b00b  sub     edx, r15d
0x18012b00e  jnz     short loc_18012B01C
0x18012b010  movzx   edx, [rsp+2D0h+FindFileData.cFileName+2]
0x18012b015  xor     eax, eax
0x18012b017  movzx   ecx, ax
0x18012b01a  sub     edx, ecx
0x18012b01c  test    edx, edx
0x18012b01e  jz      short loc_18012B043
0x18012b020  movzx   edx, [rsp+2D0h+FindFileData.cFileName]
0x18012b025  sub     edx, r15d
0x18012b028  jnz     short loc_18012B03F
0x18012b02a  movzx   edx, [rsp+2D0h+FindFileData.cFileName+2]
0x18012b02f  sub     edx, r15d
0x18012b032  jnz     short loc_18012B03F
0x18012b034  movzx   edx, [rbp+1D0h+FindFileData.cFileName+4]
0x18012b038  xor     eax, eax
0x18012b03a  movzx   ecx, ax
0x18012b03d  sub     edx, ecx
0x18012b03f  test    edx, edx
0x18012b041  jnz     short loc_18012B05D
0x18012b043  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x18012b048  mov     rcx, r14; hFindFile
0x18012b04b  call    cs:__imp_FindNextFileW
0x18012b052  nop     dword ptr [rax+rax+00h]
0x18012b057  cmp     eax, edi
0x18012b059  jz      short loc_18012B006
0x18012b05b  jmp     short loc_18012B05F
0x18012b05d  xor     edi, edi
0x18012b05f  mov     rcx, r14; hFindFile
0x18012b062  call    cs:__imp_FindClose
0x18012b069  nop     dword ptr [rax+rax+00h]
0x18012b06e  test    edi, edi
0x18012b070  jz      short loc_18012B0DB
0x18012b072  mov     rax, [rbx]
0x18012b075  mov     rcx, rbx
0x18012b078  mov     rax, [rax+38h]
0x18012b07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b081  mov     rbx, rax
0x18012b084  mov     rcx, [rax]
0x18012b087  mov     rax, [rcx+50h]
0x18012b08b  mov     rcx, rbx
0x18012b08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b093  mov     r8, rax; unsigned __int16 *
0x18012b096  mov     edx, esi; int
0x18012b098  mov     ecx, 917h; int
0x18012b09d  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x18012b0a2  mov     rcx, [rbx]
0x18012b0a5  mov     rdi, rax
0x18012b0a8  mov     rax, [rcx+10h]
0x18012b0ac  mov     rcx, rbx
0x18012b0af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b0b4  mov     rcx, [rsp+2D0h+var_298]
0x18012b0b9  mov     rdx, [rcx]
0x18012b0bc  mov     rax, [rdx+10h]
0x18012b0c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b0c5  mov     rcx, [rsp+2D0h+var_2A0]
0x18012b0ca  mov     rax, [rcx]
0x18012b0cd  mov     rax, [rax+10h]
0x18012b0d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b0d6  mov     rax, rdi
0x18012b0d9  jmp     short loc_18012B10E
0x18012b0db  mov     rcx, [rsp+2D0h+var_298]
0x18012b0e0  mov     rax, [rcx]
0x18012b0e3  mov     rax, [rax+10h]
0x18012b0e7  jmp     short loc_18012B0F6
0x18012b0e9  mov     rax, [rbx]
0x18012b0ec  mov     rcx, rbx
0x18012b0ef  mov     rax, [rax+240h]
0x18012b0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b0fb  mov     rcx, [rsp+2D0h+var_2A0]
0x18012b100  mov     rax, [rcx]
0x18012b103  mov     rax, [rax+10h]
0x18012b107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b10c  xor     eax, eax
0x18012b10e  mov     rcx, [rbp+1D0h+var_30]
0x18012b115  xor     rcx, rsp; StackCookie
0x18012b118  call    __security_check_cookie
0x18012b11d  lea     r11, [rsp+2D0h+var_20]
0x18012b125  mov     rbx, [r11+40h]
0x18012b129  mov     rsi, [r11+48h]
0x18012b12d  mov     rsp, r11
0x18012b130  pop     r15
0x18012b132  pop     r14
0x18012b134  pop     r12
0x18012b136  pop     rdi
0x18012b137  pop     rbp
0x18012b138  retn
```
