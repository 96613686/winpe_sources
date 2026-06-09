# GuestStateBlockStorage::Mount(void)

- ea: `0x18005e5a0`
- end: `0x18005e925`
- name: `?Mount@GuestStateBlockStorage@@UEAAXXZ`
- size: `901`
- prototype: `void __fastcall(GuestStateBlockStorage *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005e930`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180009e8c`
- `0x18001017c`
- `0x18001587c`
- `0x18004613c`
- `0x18005e5a0`
- `0x18005f300`
- `0x180097848`
- `0x1800992f8`
- `0x180099600`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005e73f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005e759`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005e73f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005e759`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e874`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e861`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e86c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e8b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e86c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e8b5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005e624`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005e624`

## string_xrefs

- `0x18005e7f1`: `onecore\vm\common\gueststate\gueststateblockstorage.cpp`
- `0x18005e839`: `onecore\vm\common\gueststate\gueststateblockstorage.cpp`
- `0x18005e8e6`: `onecore\vm\common\gueststate\gueststateblockstorage.cpp`
- `0x18005e901`: `onecore\vm\common\gueststate\gueststateblockstorage.cpp`
- `0x18005e913`: `onecore\vm\common\gueststate\gueststateblockstorage.cpp`
- `0x18005e7e1`: `Failed to mount file"%ws"`
- `0x18005e829`: `Failed to validate mount of file"%ws"`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GuestStateBlockStorage::Mount(GuestStateBlockStorage *this)
{
  __int64 *v2; // r14
  __int64 FileW; // rsi
  const char *v4; // r9
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  struct _OVERLAPPED *v7; // r8
  const char *v8; // r9
  const char *v9; // rbx
  const char *v10; // r15
  int v11; // eax
  int v12; // eax
  void *v13; // r15
  DWORD LastError; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const struct _GUID *dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  unsigned int dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  const struct _GUID *hTemplateFile; // [rsp+30h] [rbp-D0h]
  unsigned int *v19; // [rsp+38h] [rbp-C8h]
  _SCSI_ADDRESS v20; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v22[4]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v23[5]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+C0h] [rbp-40h]
  _OWORD v25[5]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v26; // [rsp+120h] [rbp+20h]
  _BYTE v27[512]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v28[512]; // [rsp+328h] [rbp+228h] BYREF
  int v29; // [rsp+528h] [rbp+428h]
  _OWORD v30[4]; // [rsp+540h] [rbp+440h] BYREF
  __int64 v31; // [rsp+580h] [rbp+480h]
  __int16 v32; // [rsp+588h] [rbp+488h]
  wil::details::in1diag3 *retaddr; // [rsp+5C8h] [rbp+4C8h]

  v2 = (__int64 *)((char *)this + 128);
  if ( (unsigned __int64)(*((_QWORD *)this + 16) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststateblockstorage.cpp",
      (const char *)0x8007139FLL,
      dwCreationDisposition);
  FileW = (__int64)CreateFileW(L"\\\\.\\STORVSP\\ADAPTER", 0xE0000000, 7u, 0, 1u, 0x100000u, 0);
  v21 = FileW;
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x9A,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststateblockstorage.cpp",
      v4);
  memset_0(v23, 0, 0x58u);
  CommonUtilities::GuidToString(v22, (char *)this + 112);
  v5 = v22;
  if ( v22[3] > 7u )
    v5 = (_QWORD *)v22[0];
  v30[0] = *(_OWORD *)v5;
  v30[1] = *((_OWORD *)v5 + 1);
  v30[2] = *((_OWORD *)v5 + 2);
  v30[3] = *((_OWORD *)v5 + 3);
  v31 = v5[8];
  std::wstring::~wstring(v22);
  v32 = 0;
  v6 = (_QWORD *)((char *)this + 80);
  if ( *((_QWORD *)this + 13) > 7u )
    v6 = (_QWORD *)*v6;
  memset_0((char *)v25 + 8, 0, 0x460u);
  v25[0] = v23[0];
  v25[1] = v23[1];
  v25[2] = v23[2];
  v25[3] = v23[3];
  v25[4] = v23[4];
  v26 = v24;
  v29 = 1538;
  if ( v6 )
    _o_wcsncpy_s(v27, 256, v6, -1);
  _o_wcsncpy_s(v28, 256, v30, -1);
  if ( !(unsigned int)SyncDeviceIoControl((HANDLE)FileW, 0x248004u, v7, v25, 0x468u, 0, 0, v19) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststateblockstorage.cpp",
      v8);
  v20 = 0;
  v9 = (char *)this + 8;
  if ( *((_QWORD *)this + 4) <= 7u )
    v10 = (char *)this + 8;
  else
    v10 = *(const char **)v9;
  v11 = MountDevice(
          *((void **)this + 17),
          (void *)FileW,
          &v20,
          *((_BYTE *)this + 72) & 1,
          dwCreationDispositiona,
          dwFlagsAndAttributes,
          hTemplateFile);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0xAD,
    (unsigned int)"onecore\\vm\\common\\gueststate\\gueststateblockstorage.cpp",
    (const char *)(v11 == 0),
    "Failed to mount file\"%ws\"",
    v10);
  if ( *((_QWORD *)this + 4) > 7u )
    v9 = *(const char **)v9;
  v12 = ValidateMount(*((void **)this + 17));
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0xAF,
    (unsigned int)"onecore\\vm\\common\\gueststate\\gueststateblockstorage.cpp",
    (const char *)(v12 == 0),
    "Failed to validate mount of file\"%ws\"",
    v9);
  if ( v2 != &v21 )
  {
    v13 = (void *)*v2;
    if ( (unsigned __int64)(*v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v13);
      SetLastError(LastError);
    }
    *v2 = FileW;
    FileW = -1;
  }
  *((_DWORD *)this + 36) = v20.Length;
  *((_BYTE *)this + 151) = v20.Lun;
  *((_BYTE *)this + 149) = v20.PathId;
  *((_BYTE *)this + 150) = v20.TargetId;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
}

```

## disassembly

```asm
0x18005e5a0  mov     [rsp-8+arg_8], rbx
0x18005e5a5  mov     [rsp-8+arg_10], rsi
0x18005e5aa  push    rbp
0x18005e5ab  push    rdi
0x18005e5ac  push    r13
0x18005e5ae  push    r14
0x18005e5b0  push    r15
0x18005e5b2  lea     rbp, [rsp-4A0h]
0x18005e5ba  sub     rsp, 5A0h
0x18005e5c1  mov     rax, cs:__security_cookie
0x18005e5c8  xor     rax, rsp
0x18005e5cb  mov     [rbp+4C0h+var_30], rax
0x18005e5d2  mov     rdi, rcx
0x18005e5d5  lea     r14, [rcx+80h]
0x18005e5dc  mov     rax, [r14]
0x18005e5df  dec     rax
0x18005e5e2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005e5e6  setbe   al
0x18005e5e9  mov     rcx, [rbp+4C8h]; this
0x18005e5f0  test    al, al
0x18005e5f2  jnz     loc_18005E8FB
0x18005e5f8  mov     [rsp+5C0h+hTemplateFile], 0; hTemplateFile
0x18005e601  mov     [rsp+5C0h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x18005e609  mov     [rsp+5C0h+dwCreationDisposition], 1; dwCreationDisposition
0x18005e611  xor     r9d, r9d; lpSecurityAttributes
0x18005e614  mov     edx, 0E0000000h; dwDesiredAccess
0x18005e619  lea     r8d, [r9+7]; dwShareMode
0x18005e61d  lea     rcx, FileName; "\\\\.\\STORVSP\\ADAPTER"
0x18005e624  call    cs:__imp_CreateFileW
0x18005e62a  mov     rsi, rax
0x18005e62d  mov     [rsp+5C0h+var_578], rax
0x18005e632  inc     rax
0x18005e635  test    rax, 0FFFFFFFFFFFFFFFEh
0x18005e63b  setz    al
0x18005e63e  mov     rcx, [rbp+4C8h]; this
0x18005e645  test    al, al
0x18005e647  jnz     loc_18005E913
0x18005e64d  xor     edx, edx; Val
0x18005e64f  lea     r8d, [rdx+58h]; Size
0x18005e653  lea     rcx, [rsp+5C0h+var_550]; void *
0x18005e658  call    memset_0
0x18005e65d  lea     rdx, [rdi+70h]
0x18005e661  lea     rcx, [rsp+5C0h+var_570]
0x18005e666  call    ?GuidToString@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; CommonUtilities::GuidToString(_GUID const &,bool)
0x18005e66b  lea     rax, [rsp+5C0h+var_570]
0x18005e670  cmp     [rsp+5C0h+var_558], 7
0x18005e676  cmova   rax, [rsp+5C0h+var_570]
0x18005e67c  movups  xmm0, xmmword ptr [rax]
0x18005e67f  movaps  [rbp+4C0h+var_80], xmm0
0x18005e686  movups  xmm1, xmmword ptr [rax+10h]
0x18005e68a  movaps  [rbp+4C0h+var_70], xmm1
0x18005e691  movups  xmm0, xmmword ptr [rax+20h]
0x18005e695  movaps  [rbp+4C0h+var_60], xmm0
0x18005e69c  movups  xmm1, xmmword ptr [rax+30h]
0x18005e6a0  movaps  [rbp+4C0h+var_50], xmm1
0x18005e6a7  movsd   xmm0, qword ptr [rax+40h]
0x18005e6ac  movsd   [rbp+4C0h+var_40], xmm0
0x18005e6b4  lea     rcx, [rsp+5C0h+var_570]
0x18005e6b9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005e6be  xor     eax, eax
0x18005e6c0  mov     [rbp+4C0h+var_38], ax
0x18005e6c7  lea     rbx, [rdi+50h]
0x18005e6cb  cmp     qword ptr [rbx+18h], 7
0x18005e6d0  jbe     short loc_18005E6D5
0x18005e6d2  mov     rbx, [rbx]
0x18005e6d5  xor     edx, edx; Val
0x18005e6d7  mov     r8d, 460h; Size
0x18005e6dd  lea     rcx, [rbp+4C0h+var_4F0+8]; void *
0x18005e6e1  call    memset_0
0x18005e6e6  movaps  xmm0, [rsp+5C0h+var_550]
0x18005e6eb  movaps  [rbp+4C0h+var_4F0], xmm0
0x18005e6ef  movaps  xmm1, [rbp+4C0h+var_540]
0x18005e6f3  movaps  [rbp+4C0h+var_4E0], xmm1
0x18005e6f7  movaps  xmm0, [rbp+4C0h+var_530]
0x18005e6fb  movaps  [rbp+4C0h+var_4D0], xmm0
0x18005e6ff  movaps  xmm1, [rbp+4C0h+var_520]
0x18005e703  movaps  [rbp+4C0h+var_4C0], xmm1
0x18005e707  movaps  xmm0, [rbp+4C0h+var_510]
0x18005e70b  movaps  [rbp+4C0h+var_4B0], xmm0
0x18005e70f  movsd   xmm1, [rbp+4C0h+var_500]
0x18005e714  movsd   [rbp+4C0h+var_4A0], xmm1
0x18005e719  mov     [rbp+4C0h+var_98], 602h
0x18005e723  or      r13, 0FFFFFFFFFFFFFFFFh
0x18005e727  mov     r15d, 100h
0x18005e72d  test    rbx, rbx
0x18005e730  jz      short loc_18005E745
0x18005e732  mov     r9, r13
0x18005e735  mov     r8, rbx
0x18005e738  mov     edx, r15d
0x18005e73b  lea     rcx, [rbp+4C0h+var_498]
0x18005e73f  call    cs:__imp__o_wcsncpy_s
0x18005e745  mov     r9, r13
0x18005e748  lea     r8, [rbp+4C0h+var_80]
0x18005e74f  mov     rdx, r15
0x18005e752  lea     rcx, [rbp+4C0h+var_298]
0x18005e759  call    cs:__imp__o_wcsncpy_s
0x18005e75f  mov     rbx, [rbp+4C8h]
0x18005e766  mov     dword ptr [rsp+5C0h+hTemplateFile], 0; struct _GUID *
0x18005e76e  mov     qword ptr [rsp+5C0h+dwFlagsAndAttributes], 0; unsigned int
0x18005e777  mov     [rsp+5C0h+dwCreationDisposition], 468h; struct _GUID *
0x18005e77f  lea     r9, [rbp+4C0h+var_4F0]; void *
0x18005e783  mov     edx, 248004h; dwIoControlCode
0x18005e788  mov     rcx, rsi; hFile
0x18005e78b  call    ?SyncDeviceIoControl@@YAHPEAXKPEAU_OVERLAPPED@@0K0KPEAK@Z; SyncDeviceIoControl(void *,ulong,_OVERLAPPED *,void *,ulong,void *,ulong,ulong *)
0x18005e790  test    eax, eax
0x18005e792  jz      loc_18005E8E6
0x18005e798  mov     qword ptr [rsp+5C0h+var_580.Length], 0
0x18005e7a1  mov     r9b, [rdi+48h]
0x18005e7a5  and     r9b, 1; unsigned __int8
0x18005e7a9  lea     rbx, [rdi+8]
0x18005e7ad  cmp     qword ptr [rbx+18h], 7
0x18005e7b2  jbe     short loc_18005E7B9
0x18005e7b4  mov     r15, [rbx]
0x18005e7b7  jmp     short loc_18005E7BC
0x18005e7b9  mov     r15, rbx
0x18005e7bc  lea     r8, [rsp+5C0h+var_580]; struct _SCSI_ADDRESS *
0x18005e7c1  mov     rdx, rsi; void *
0x18005e7c4  mov     rcx, [rdi+88h]; void *
0x18005e7cb  call    ?MountDevice@@YAHPEAX0PEBU_SCSI_ADDRESS@@EPEBU_GUID@@K2@Z; MountDevice(void *,void *,_SCSI_ADDRESS const *,uchar,_GUID const *,ulong,_GUID const *)
0x18005e7d0  test    eax, eax
0x18005e7d2  setz    al
0x18005e7d5  mov     rcx, [rbp+4C8h]; this
0x18005e7dc  mov     qword ptr [rsp+5C0h+dwFlagsAndAttributes], r15; char *
0x18005e7e1  lea     rdx, aFailedToMountF; "Failed to mount file\"%ws\""
0x18005e7e8  mov     qword ptr [rsp+5C0h+dwCreationDisposition], rdx; void *
0x18005e7ed  movzx   r9d, al; char *
0x18005e7f1  lea     r8, aOnecoreVmCommo_25; "onecore\\vm\\common\\gueststate\\guests"...
0x18005e7f8  mov     edx, 0ADh; void *
0x18005e7fd  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18005e802  cmp     qword ptr [rbx+18h], 7
0x18005e807  jbe     short loc_18005E80C
0x18005e809  mov     rbx, [rbx]
0x18005e80c  mov     rcx, [rdi+88h]; void *
0x18005e813  call    ?ValidateMount@@YAHPEAX@Z; ValidateMount(void *)
0x18005e818  test    eax, eax
0x18005e81a  setz    al
0x18005e81d  mov     rcx, [rbp+4C8h]; this
0x18005e824  mov     qword ptr [rsp+5C0h+dwFlagsAndAttributes], rbx; char *
0x18005e829  lea     rdx, aFailedToValida; "Failed to validate mount of file\"%ws\""
0x18005e830  mov     qword ptr [rsp+5C0h+dwCreationDisposition], rdx; void *
0x18005e835  movzx   r9d, al; char *
0x18005e839  lea     r8, aOnecoreVmCommo_25; "onecore\\vm\\common\\gueststate\\guests"...
0x18005e840  mov     edx, 0AFh; void *
0x18005e845  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18005e84a  lea     rax, [rsp+5C0h+var_578]
0x18005e84f  cmp     r14, rax
0x18005e852  jz      short loc_18005E880
0x18005e854  mov     r15, [r14]
0x18005e857  lea     rax, [r15-1]
0x18005e85b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005e85f  ja      short loc_18005E87A
0x18005e861  call    cs:__imp_GetLastError
0x18005e867  mov     ebx, eax
0x18005e869  mov     rcx, r15; hObject
0x18005e86c  call    cs:__imp_CloseHandle
0x18005e872  mov     ecx, ebx; dwErrCode
0x18005e874  call    cs:__imp_SetLastError
0x18005e87a  mov     [r14], rsi
0x18005e87d  mov     rsi, r13
0x18005e880  mov     eax, [rsp+5C0h+var_580.Length]
0x18005e884  mov     [rdi+90h], eax
0x18005e88a  mov     al, [rsp+5C0h+var_580.Lun]
0x18005e88e  mov     [rdi+97h], al
0x18005e894  mov     al, [rsp+5C0h+var_580.PathId]
0x18005e898  mov     [rdi+95h], al
0x18005e89e  mov     al, [rsp+5C0h+var_580.TargetId]
0x18005e8a2  mov     [rdi+96h], al
0x18005e8a8  lea     rax, [rsi-1]
0x18005e8ac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005e8b0  ja      short loc_18005E8BB
0x18005e8b2  mov     rcx, rsi; hObject
0x18005e8b5  call    cs:__imp_CloseHandle
0x18005e8bb  mov     rcx, [rbp+4C0h+var_30]
0x18005e8c2  xor     rcx, rsp; StackCookie
0x18005e8c5  call    __security_check_cookie
0x18005e8ca  lea     r11, [rsp+5C0h+var_20]
0x18005e8d2  mov     rbx, [r11+38h]
0x18005e8d6  mov     rsi, [r11+40h]
0x18005e8da  mov     rsp, r11
0x18005e8dd  pop     r15
0x18005e8df  pop     r14
0x18005e8e1  pop     r13
0x18005e8e3  pop     rdi
0x18005e8e4  pop     rbp
0x18005e8e5  retn
0x18005e8e6  lea     r8, aOnecoreVmCommo_25; "onecore\\vm\\common\\gueststate\\guests"...
0x18005e8ed  mov     edx, 0A5h; void *
0x18005e8f2  mov     rcx, rbx; this
0x18005e8f5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005e8fb  mov     r9d, 8007139Fh; char *
0x18005e901  lea     r8, aOnecoreVmCommo_25; "onecore\\vm\\common\\gueststate\\guests"...
0x18005e908  mov     edx, 96h; void *
0x18005e90d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e913  lea     r8, aOnecoreVmCommo_25; "onecore\\vm\\common\\gueststate\\guests"...
0x18005e91a  mov     edx, 9Ah; void *
0x18005e91f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
