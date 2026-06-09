# SipFile::Open(SIP_SUBJECTINFO_ const *,bool)

- ea: `0x180004834`
- end: `0x180004910`
- name: `?Open@SipFile@@QEAAKPEBUSIP_SUBJECTINFO_@@_N@Z`
- size: `220`
- prototype: `unsigned int __fastcall(SipFile *__hidden this, const struct SIP_SUBJECTINFO_ *, bool)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800037bc`
- `0x1800043d0`
- `0x180004a40`
- `0x180004dd4`
- `0x1800050b0`

## callees

- `0x180003424`
- `0x180003ab0`
- `0x180004834`
- `0x180004918`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800048d2`
- `KERNEL32!CreateFileW` at `0x1800048d2`
- `KERNEL32!GetLastError` at `0x1800048e2`
- `KERNEL32!GetLastError` at `0x1800048e2`

## pseudocode

```c
__int64 __fastcall SipFile::Open(SipFile *this, const struct SIP_SUBJECTINFO_ *a2, unsigned __int8 a3)
{
  DWORD v5; // ebx
  const unsigned __int16 *pwsFileName; // rdx
  char *hFile; // rcx
  const WCHAR *v8; // rbx
  HANDLE FileW; // rax
  DWORD LastError; // eax

  if ( !a2 )
    return 87;
  if ( a2->psFlat )
  {
    *((_QWORD *)this + 1) = a2;
    *((_DWORD *)this + 13) = DetermineFileType(a2->psFlat->pIndirectData, *(&a2->psFlat->cbStruct + 1));
    pwsFileName = a2->pwsFileName;
    return SipFile::OpenCommon(this, pwsFileName);
  }
  hFile = (char *)a2->hFile;
  *((_QWORD *)this + 3) = hFile;
  if ( (unsigned __int64)(hFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    *((_QWORD *)this + 4) = hFile;
    pwsFileName = a2->pwsFileName;
    return SipFile::OpenCommon(this, pwsFileName);
  }
  v8 = a2->pwsFileName;
  if ( !v8 )
    return 87;
  FileW = CreateFileW(v8, ((unsigned int)a3 + 2) << 30, 3u, 0, 3u, 0x10000000u, 0);
  *((_QWORD *)this + 4) = FileW;
  if ( FileW == (HANDLE)-1LL )
    LastError = GetLastError();
  else
    LastError = SipFile::OpenCommon(this, v8);
  v5 = LastError;
  if ( LastError )
    SipFile::Close(this);
  return v5;
}

```

## disassembly

```asm
0x180004834  mov     [rsp+arg_0], rbx
0x180004839  push    rdi
0x18000483a  sub     rsp, 40h
0x18000483e  mov     rbx, rdx
0x180004841  mov     rdi, rcx
0x180004844  test    rdx, rdx
0x180004847  jnz     short loc_180004853
0x180004849  mov     ebx, 57h ; 'W'
0x18000484e  jmp     loc_180004903
0x180004853  cmp     qword ptr [rdx+70h], 0
0x180004858  jz      short loc_180004877
0x18000485a  mov     [rcx+8], rbx
0x18000485e  mov     rcx, [rdx+70h]
0x180004862  mov     edx, [rcx+4]
0x180004865  mov     rcx, [rcx+8]
0x180004869  call    ?DetermineFileType@@YA?AW4FileType@@PEBEI@Z; DetermineFileType(uchar const *,uint)
0x18000486e  mov     [rdi+34h], eax
0x180004871  mov     rdx, [rbx+18h]
0x180004875  jmp     short loc_180004891
0x180004877  mov     rcx, [rdx+10h]
0x18000487b  mov     [rdi+18h], rcx
0x18000487f  lea     rax, [rcx-1]
0x180004883  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180004887  ja      short loc_18000489D
0x180004889  mov     [rdi+20h], rcx
0x18000488d  mov     rdx, [rdx+18h]; unsigned __int16 *
0x180004891  mov     rcx, rdi; this
0x180004894  call    ?OpenCommon@SipFile@@AEAAKPEBG@Z; SipFile::OpenCommon(ushort const *)
0x180004899  mov     ebx, eax
0x18000489b  jmp     short loc_180004903
0x18000489d  mov     rbx, [rdx+18h]
0x1800048a1  test    rbx, rbx
0x1800048a4  jz      short loc_180004849
0x1800048a6  movzx   edx, r8b
0x1800048aa  xor     r9d, r9d; lpSecurityAttributes
0x1800048ad  add     edx, 2
0x1800048b0  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800048b9  mov     r8d, 3; dwShareMode
0x1800048bf  shl     edx, 1Eh; dwDesiredAccess
0x1800048c2  mov     [rsp+48h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x1800048ca  mov     rcx, rbx; lpFileName
0x1800048cd  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800048d2  call    cs:__imp_CreateFileW
0x1800048d8  mov     [rdi+20h], rax
0x1800048dc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800048e0  jnz     short loc_1800048EA
0x1800048e2  call    cs:__imp_GetLastError
0x1800048e8  jmp     short loc_1800048F5
0x1800048ea  mov     rdx, rbx; unsigned __int16 *
0x1800048ed  mov     rcx, rdi; this
0x1800048f0  call    ?OpenCommon@SipFile@@AEAAKPEBG@Z; SipFile::OpenCommon(ushort const *)
0x1800048f5  mov     ebx, eax
0x1800048f7  test    eax, eax
0x1800048f9  jz      short loc_180004903
0x1800048fb  mov     rcx, rdi; this
0x1800048fe  call    ?Close@SipFile@@QEAAKXZ; SipFile::Close(void)
0x180004903  mov     eax, ebx
0x180004905  mov     rbx, [rsp+48h+arg_0]
0x18000490a  add     rsp, 40h
0x18000490e  pop     rdi
0x18000490f  retn
```
