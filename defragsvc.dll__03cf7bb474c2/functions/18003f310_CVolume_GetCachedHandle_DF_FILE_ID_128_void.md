# CVolume::_GetCachedHandle(_DF_FILE_ID_128 *,void * *)

- ea: `0x18003f310`
- end: `0x18003f558`
- name: `?_GetCachedHandle@CVolume@@IEAAJPEAU_DF_FILE_ID_128@@PEAPEAX@Z`
- size: `584`
- prototype: `__int64 __fastcall(CVolume *__hidden this, struct _DF_FILE_ID_128 *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180063af0`
- `0x180064250`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18003f310`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003f3a8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003f4ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003f3a8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003f4ec`
- `ntdll!NtCreateFile` at `0x18003f4b1`
- `ntdll!NtCreateFile` at `0x18003f4b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f45a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f45a`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003f3e3`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003f3e3`

## string_xrefs

- `0x18003f34a`: `CVolume::_GetCachedHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CVolume::_GetCachedHandle(CVolume *this, struct _DF_FILE_ID_128 *a2, void **a3)
{
  HANDLE *v6; // rsi
  _QWORD *v7; // rbx
  __int64 v8; // rax
  ULONGLONG TickCount64; // r14
  NTSTATUS v10; // eax
  __int16 v11; // ax
  unsigned int v12; // ebx
  __int128 v14; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+70h] [rbp-90h] BYREF
  __int16 v16; // [rsp+74h] [rbp-8Ch]
  __int16 v17; // [rsp+76h] [rbp-8Ah]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp-28h] BYREF
  __int128 FileInformation; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v21; // [rsp+F8h] [rbp-8h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v15, "CVolume::_GetCachedHandle", 1725, 1);
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v14 = 0;
  v6 = (HANDLE *)((char *)this + 168);
  v7 = (_QWORD *)((char *)this + 176);
  if ( ((*((_QWORD *)this + 21) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v8 = *v7 - *(_QWORD *)a2;
    if ( *v7 == *(_QWORD *)a2 )
      v8 = *((_QWORD *)this + 23) - *((_QWORD *)a2 + 1);
    if ( !v8 )
    {
      TickCount64 = GetTickCount64();
      if ( TickCount64 - *((_QWORD *)this + 24) <= 0x2710 )
      {
LABEL_20:
        *a3 = *v6;
        goto LABEL_21;
      }
      FileInformation = 0;
      v21 = 0;
      if ( GetFileInformationByHandleEx(*v6, FileStandardInfo, &FileInformation, 0x18u) && !BYTE4(v21) )
      {
        *((_QWORD *)this + 24) = TickCount64;
        goto LABEL_20;
      }
    }
  }
  (*(void (__fastcall **)(CVolume *))(*(_QWORD *)this + 248LL))(this);
  *(_OWORD *)v7 = *(_OWORD *)a2;
  LODWORD(v14) = 1048592;
  *((_QWORD *)&v14 + 1) = a2;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = (HANDLE)*((_QWORD *)this + 5);
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v14;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( (char *)*v6 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(*v6);
    *v6 = (HANDLE)-1LL;
  }
  v10 = NtCreateFile((PHANDLE)this + 21, 0x80u, &ObjectAttributes, &IoStatusBlock, 0, 0, 1u, 1u, 0x6000u, 0, 0);
  if ( v10 >= 0 )
  {
    *((_QWORD *)this + 24) = GetTickCount64();
    v11 = 1834;
    if ( (((unsigned __int64)*v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v15 = 0;
      v16 = 1834;
      goto LABEL_20;
    }
    v15 = -1996488674;
  }
  else if ( v10 == -1073741533 || v10 == -1073741738 )
  {
    v15 = -805306077;
    v11 = 1824;
  }
  else
  {
    v15 = -1996488674;
    v11 = 1828;
  }
  v17 = v11;
LABEL_21:
  v12 = v15;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v15);
  return v12;
}

```

## disassembly

```asm
0x18003f310  push    rbp
0x18003f312  push    rbx
0x18003f313  push    rsi
0x18003f314  push    rdi
0x18003f315  push    r12
0x18003f317  push    r14
0x18003f319  push    r15
0x18003f31b  lea     rbp, [rsp-10h]
0x18003f320  sub     rsp, 110h
0x18003f327  mov     rax, cs:__security_cookie
0x18003f32e  xor     rax, rsp
0x18003f331  mov     [rbp+40h+var_40], rax
0x18003f335  mov     r12, r8
0x18003f338  mov     r15, rdx
0x18003f33b  mov     rdi, rcx
0x18003f33e  mov     r9d, 1; unsigned __int16
0x18003f344  mov     r8d, 6BDh; unsigned __int16
0x18003f34a  lea     rdx, aCvolumeGetcach; "CVolume::_GetCachedHandle"
0x18003f351  lea     rcx, [rsp+140h+var_D0]; this
0x18003f356  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003f35b  nop
0x18003f35c  xorps   xmm0, xmm0
0x18003f35f  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x18003f363  xorps   xmm1, xmm1
0x18003f366  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm1
0x18003f36a  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm1
0x18003f36e  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm1
0x18003f372  movups  [rsp+140h+var_E0], xmm0
0x18003f377  lea     rsi, [rdi+0A8h]
0x18003f37e  mov     rax, [rsi]
0x18003f381  inc     rax
0x18003f384  lea     rbx, [rdi+0B0h]
0x18003f38b  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003f391  jz      short loc_18003F3FF
0x18003f393  mov     rax, [rbx]
0x18003f396  sub     rax, [r15]
0x18003f399  jnz     short loc_18003F3A3
0x18003f39b  mov     rax, [rbx+8]
0x18003f39f  sub     rax, [r15+8]
0x18003f3a3  test    rax, rax
0x18003f3a6  jnz     short loc_18003F3FF
0x18003f3a8  call    cs:__imp_GetTickCount64
0x18003f3ae  mov     r14, rax
0x18003f3b1  mov     rcx, rax
0x18003f3b4  sub     rcx, [rdi+0C0h]
0x18003f3bb  cmp     rcx, 2710h
0x18003f3c2  jbe     loc_18003F523
0x18003f3c8  xorps   xmm0, xmm0
0x18003f3cb  xor     eax, eax
0x18003f3cd  movups  [rbp+40h+FileInformation], xmm0
0x18003f3d1  mov     [rbp+40h+var_48], rax
0x18003f3d5  lea     r9d, [rax+18h]; dwBufferSize
0x18003f3d9  lea     r8, [rbp+40h+FileInformation]; lpFileInformation
0x18003f3dd  lea     edx, [rax+1]; FileInformationClass
0x18003f3e0  mov     rcx, [rsi]; hFile
0x18003f3e3  call    cs:__imp_GetFileInformationByHandleEx
0x18003f3e9  test    eax, eax
0x18003f3eb  jz      short loc_18003F3FF
0x18003f3ed  cmp     byte ptr [rbp+40h+var_48+4], 0
0x18003f3f1  jnz     short loc_18003F3FF
0x18003f3f3  mov     [rdi+0C0h], r14
0x18003f3fa  jmp     loc_18003F523
0x18003f3ff  mov     rax, [rdi]
0x18003f402  mov     rcx, rdi
0x18003f405  mov     rax, [rax+0F8h]
0x18003f40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f411  movups  xmm0, xmmword ptr [r15]
0x18003f415  movdqu  xmmword ptr [rbx], xmm0
0x18003f419  mov     dword ptr [rsp+140h+var_E0], 100010h
0x18003f421  mov     qword ptr [rsp+140h+var_E0+8], r15
0x18003f426  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x18003f42d  mov     rax, [rdi+28h]
0x18003f431  mov     [rbp+40h+ObjectAttributes.RootDirectory], rax
0x18003f435  mov     [rbp+40h+ObjectAttributes.Attributes], 40h ; '@'
0x18003f43c  lea     rax, [rsp+140h+var_E0]
0x18003f441  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x18003f445  xorps   xmm0, xmm0
0x18003f448  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003f44d  mov     rcx, [rsi]; hObject
0x18003f450  lea     rax, [rcx-1]
0x18003f454  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003f458  ja      short loc_18003F467
0x18003f45a  call    cs:__imp_CloseHandle
0x18003f460  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18003f467  mov     [rsp+140h+EaLength], 0; EaLength
0x18003f46f  mov     [rsp+140h+EaBuffer], 0; EaBuffer
0x18003f478  mov     [rsp+140h+CreateOptions], 6000h; CreateOptions
0x18003f480  mov     [rsp+140h+CreateDisposition], 1; CreateDisposition
0x18003f488  mov     [rsp+140h+ShareAccess], 1; ShareAccess
0x18003f490  mov     [rsp+140h+FileAttributes], 0; FileAttributes
0x18003f498  mov     [rsp+140h+AllocationSize], 0; AllocationSize
0x18003f4a1  lea     r9, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x18003f4a5  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x18003f4a9  mov     edx, 80h; DesiredAccess
0x18003f4ae  mov     rcx, rsi; FileHandle
0x18003f4b1  call    cs:__imp_NtCreateFile
0x18003f4b7  test    eax, eax
0x18003f4b9  jns     short loc_18003F4EC
0x18003f4bb  cmp     eax, 0C0000123h
0x18003f4c0  jz      short loc_18003F4D8
0x18003f4c2  cmp     eax, 0C0000056h
0x18003f4c7  jz      short loc_18003F4D8
0x18003f4c9  mov     [rsp+140h+var_D0], 8900001Eh
0x18003f4d1  mov     eax, 724h
0x18003f4d6  jmp     short loc_18003F4E5
0x18003f4d8  mov     [rsp+140h+var_D0], 0D0000123h
0x18003f4e0  mov     eax, 720h
0x18003f4e5  mov     [rsp+140h+var_CA], ax
0x18003f4ea  jmp     short loc_18003F52A
0x18003f4ec  call    cs:__imp_GetTickCount64
0x18003f4f2  mov     [rdi+0C0h], rax
0x18003f4f9  mov     rax, [rsi]
0x18003f4fc  inc     rax
0x18003f4ff  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003f505  mov     eax, 72Ah
0x18003f50a  jnz     short loc_18003F516
0x18003f50c  mov     [rsp+140h+var_D0], 8900001Eh
0x18003f514  jmp     short loc_18003F4E5
0x18003f516  mov     [rsp+140h+var_D0], 0
0x18003f51e  mov     [rsp+140h+var_CC], ax
0x18003f523  mov     rax, [rsi]
0x18003f526  mov     [r12], rax
0x18003f52a  mov     ebx, [rsp+140h+var_D0]
0x18003f52e  lea     rcx, [rsp+140h+var_D0]; this
0x18003f533  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003f538  mov     eax, ebx
0x18003f53a  mov     rcx, [rbp+40h+var_40]
0x18003f53e  xor     rcx, rsp; StackCookie
0x18003f541  call    __security_check_cookie
0x18003f546  add     rsp, 110h
0x18003f54d  pop     r15
0x18003f54f  pop     r14
0x18003f551  pop     r12
0x18003f553  pop     rdi
0x18003f554  pop     rsi
0x18003f555  pop     rbx
0x18003f556  pop     rbp
0x18003f557  retn
```
