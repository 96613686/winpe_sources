# GuestStateBlockStorage::Reopen(void)

- ea: `0x18005f0b0`
- end: `0x18005f2d4`
- name: `?Reopen@GuestStateBlockStorage@@UEAAXXZ`
- size: `548`
- prototype: `void __fastcall(GuestStateBlockStorage *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18001017c`
- `0x180011894`
- `0x18005f0b0`
- `0x18005f300`
- `0x18005f35c`
- `0x18009739c`
- `0x180097848`
- `0x1800992f8`
- `0x180099600`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f0e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f264`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f0e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f0d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f0d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f251`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f0df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f25c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f27e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f0df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f25c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f27e`

## string_xrefs

- `0x18005f1e4`: `onecore\vm\common\gueststate\gueststateblockstorage.cpp`
- `0x18005f229`: `onecore\vm\common\gueststate\gueststateblockstorage.cpp`
- `0x18005f291`: `onecore\vm\common\gueststate\gueststateblockstorage.cpp`
- `0x18005f2c2`: `onecore\vm\common\gueststate\gueststateblockstorage.cpp`
- `0x18005f1d4`: `Failed to mount file"%ws"`
- `0x18005f219`: `Failed to validate mount of file"%ws"`
- `0x18005f128`: `GuestStateBlockStorage::Reopen`
- `0x18005f2bb`: `Failed to reopen file "%ws"`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GuestStateBlockStorage::Reopen(GuestStateBlockStorage *this)
{
  __int64 *v2; // rsi
  char *v3; // rdi
  DWORD LastError; // ebx
  unsigned __int8 v5; // r14
  const char *v6; // rbx
  char *v7; // rcx
  __int64 v8; // rdx
  __int64 DeviceVHDEx; // rdi
  struct _OVERLAPPED *v10; // r8
  __int64 v11; // r9
  const char *v12; // r9
  const char *v13; // r15
  int v14; // eax
  int v15; // eax
  void *v16; // rbp
  DWORD v17; // ebx
  const char *v18; // rax
  const struct _GUID *nInBufferSize; // [rsp+20h] [rbp-68h]
  char *v20; // [rsp+28h] [rbp-60h]
  struct _GUID *v21; // [rsp+30h] [rbp-58h]
  unsigned int *v22; // [rsp+38h] [rbp-50h]
  struct _SCSI_ADDRESS v23; // [rsp+40h] [rbp-48h] BYREF
  __int64 v24; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v2 = (__int64 *)((char *)this + 136);
  v3 = (char *)*((_QWORD *)this + 17);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v3);
    SetLastError(LastError);
  }
  *v2 = -1;
  v5 = *((_BYTE *)this + 72) & 1;
  v6 = (char *)this + 8;
  if ( *((_QWORD *)this + 4) <= 7u )
    v7 = (char *)this + 8;
  else
    v7 = *(char **)v6;
  LODWORD(v21) = 197;
  v20 = "GuestStateBlockStorage::Reopen";
  nInBufferSize = (const struct _GUID *)((char *)this + 112);
  DeviceVHDEx = CreateDeviceVHDEx(v7, ((unsigned __int8)!(*((_BYTE *)this + 72) & 1) << 8) + 3);
  v24 = DeviceVHDEx;
  if ( ((DeviceVHDEx + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v18 = (const char *)std::wstring::c_str((char *)this + 8, v8, v10, v11);
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststateblockstorage.cpp",
      "Failed to reopen file \"%ws\"",
      v18);
  }
  if ( !v5 && !(unsigned int)SyncDeviceIoControl((HANDLE)DeviceVHDEx, 0x248260u, v10, 0, 0, 0, 0, v22) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xCE,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststateblockstorage.cpp",
      v12);
  v23 = 0;
  if ( *((_QWORD *)this + 4) <= 7u )
    v13 = (char *)this + 8;
  else
    v13 = *(const char **)v6;
  v14 = MountDevice((void *)DeviceVHDEx, *((void **)this + 16), &v23, v5, nInBufferSize, (unsigned int)v20, v21);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0xD4,
    (unsigned int)"onecore\\vm\\common\\gueststate\\gueststateblockstorage.cpp",
    (const char *)(v14 == 0),
    "Failed to mount file\"%ws\"",
    v13);
  if ( *((_QWORD *)this + 4) > 7u )
    v6 = *(const char **)v6;
  v15 = ValidateMount((void *)DeviceVHDEx);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0xD6,
    (unsigned int)"onecore\\vm\\common\\gueststate\\gueststateblockstorage.cpp",
    (const char *)(v15 == 0),
    "Failed to validate mount of file\"%ws\"",
    v6);
  if ( v2 != &v24 )
  {
    v16 = (void *)*v2;
    if ( (unsigned __int64)(*v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v17 = GetLastError();
      CloseHandle(v16);
      SetLastError(v17);
    }
    *v2 = DeviceVHDEx;
    DeviceVHDEx = -1;
  }
  if ( (unsigned __int64)(DeviceVHDEx - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)DeviceVHDEx);
}

```

## disassembly

```asm
0x18005f0b0  push    rbx
0x18005f0b2  push    rbp
0x18005f0b3  push    rsi
0x18005f0b4  push    rdi
0x18005f0b5  push    r14
0x18005f0b7  push    r15
0x18005f0b9  sub     rsp, 58h
0x18005f0bd  mov     rbp, rcx
0x18005f0c0  lea     rsi, [rcx+88h]
0x18005f0c7  mov     rdi, [rsi]
0x18005f0ca  lea     rax, [rdi-1]
0x18005f0ce  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005f0d2  ja      short loc_18005F0ED
0x18005f0d4  call    cs:__imp_GetLastError
0x18005f0da  mov     ebx, eax
0x18005f0dc  mov     rcx, rdi; hObject
0x18005f0df  call    cs:__imp_CloseHandle
0x18005f0e5  mov     ecx, ebx; dwErrCode
0x18005f0e7  call    cs:__imp_SetLastError
0x18005f0ed  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18005f0f4  mov     al, [rbp+48h]
0x18005f0f7  and     al, 1
0x18005f0f9  movzx   r14d, al
0x18005f0fd  mov     edx, r14d
0x18005f100  xor     edx, 1
0x18005f103  shl     edx, 8
0x18005f106  add     edx, 3
0x18005f109  lea     rbx, [rbp+8]
0x18005f10d  cmp     qword ptr [rbx+18h], 7
0x18005f112  jbe     short loc_18005F119
0x18005f114  mov     rcx, [rbx]
0x18005f117  jmp     short loc_18005F11C
0x18005f119  mov     rcx, rbx
0x18005f11c  lea     rax, [rbp+70h]
0x18005f120  mov     dword ptr [rsp+88h+var_58], 0C5h
0x18005f128  lea     r8, aGueststatebloc; "GuestStateBlockStorage::Reopen"
0x18005f12f  mov     [rsp+88h+var_60], r8
0x18005f134  mov     qword ptr [rsp+88h+nInBufferSize], rax
0x18005f139  call    ?CreateDeviceVHDEx@@YAPEAXPEBGKHW4CreateStorageDeviceFlags@@PEBU_GUID@@PEBDK2@Z; CreateDeviceVHDEx(ushort const *,ulong,int,CreateStorageDeviceFlags,_GUID const *,char const *,ulong,_GUID const *)
0x18005f13e  mov     rdi, rax
0x18005f141  mov     [rsp+88h+var_40], rax
0x18005f146  inc     rax
0x18005f149  test    rax, 0FFFFFFFFFFFFFFFEh
0x18005f14f  jz      loc_18005F2A6
0x18005f155  test    r14b, r14b
0x18005f158  jnz     short loc_18005F193
0x18005f15a  mov     r15, [rsp+88h]
0x18005f162  mov     dword ptr [rsp+88h+var_58], 0; struct _GUID *
0x18005f16a  mov     [rsp+88h+var_60], 0; unsigned int
0x18005f173  mov     [rsp+88h+nInBufferSize], 0; struct _GUID *
0x18005f17b  xor     r9d, r9d; void *
0x18005f17e  mov     edx, 248260h; dwIoControlCode
0x18005f183  mov     rcx, rdi; hFile
0x18005f186  call    ?SyncDeviceIoControl@@YAHPEAXKPEAU_OVERLAPPED@@0K0KPEAK@Z; SyncDeviceIoControl(void *,ulong,_OVERLAPPED *,void *,ulong,void *,ulong,ulong *)
0x18005f18b  test    eax, eax
0x18005f18d  jz      loc_18005F291
0x18005f193  mov     qword ptr [rsp+88h+var_48.Length], 0
0x18005f19c  cmp     qword ptr [rbx+18h], 7
0x18005f1a1  jbe     short loc_18005F1A8
0x18005f1a3  mov     r15, [rbx]
0x18005f1a6  jmp     short loc_18005F1AB
0x18005f1a8  mov     r15, rbx
0x18005f1ab  mov     r9b, r14b; unsigned __int8
0x18005f1ae  lea     r8, [rsp+88h+var_48]; struct _SCSI_ADDRESS *
0x18005f1b3  mov     rdx, [rbp+80h]; void *
0x18005f1ba  mov     rcx, rdi; void *
0x18005f1bd  call    ?MountDevice@@YAHPEAX0PEBU_SCSI_ADDRESS@@EPEBU_GUID@@K2@Z; MountDevice(void *,void *,_SCSI_ADDRESS const *,uchar,_GUID const *,ulong,_GUID const *)
0x18005f1c2  test    eax, eax
0x18005f1c4  setz    al
0x18005f1c7  mov     rcx, [rsp+88h]; this
0x18005f1cf  mov     [rsp+88h+var_60], r15; char *
0x18005f1d4  lea     rdx, aFailedToMountF; "Failed to mount file\"%ws\""
0x18005f1db  mov     qword ptr [rsp+88h+nInBufferSize], rdx; void *
0x18005f1e0  movzx   r9d, al; char *
0x18005f1e4  lea     r8, aOnecoreVmCommo_25; "onecore\\vm\\common\\gueststate\\guests"...
0x18005f1eb  mov     edx, 0D4h; void *
0x18005f1f0  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18005f1f5  cmp     qword ptr [rbx+18h], 7
0x18005f1fa  jbe     short loc_18005F1FF
0x18005f1fc  mov     rbx, [rbx]
0x18005f1ff  mov     rcx, rdi; void *
0x18005f202  call    ?ValidateMount@@YAHPEAX@Z; ValidateMount(void *)
0x18005f207  test    eax, eax
0x18005f209  setz    al
0x18005f20c  mov     rcx, [rsp+88h]; this
0x18005f214  mov     [rsp+88h+var_60], rbx; char *
0x18005f219  lea     rdx, aFailedToValida; "Failed to validate mount of file\"%ws\""
0x18005f220  mov     qword ptr [rsp+88h+nInBufferSize], rdx; void *
0x18005f225  movzx   r9d, al; char *
0x18005f229  lea     r8, aOnecoreVmCommo_25; "onecore\\vm\\common\\gueststate\\guests"...
0x18005f230  mov     edx, 0D6h; void *
0x18005f235  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18005f23a  lea     rax, [rsp+88h+var_40]
0x18005f23f  cmp     rsi, rax
0x18005f242  jz      short loc_18005F271
0x18005f244  mov     rbp, [rsi]
0x18005f247  lea     rax, [rbp-1]
0x18005f24b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005f24f  ja      short loc_18005F26A
0x18005f251  call    cs:__imp_GetLastError
0x18005f257  mov     ebx, eax
0x18005f259  mov     rcx, rbp; hObject
0x18005f25c  call    cs:__imp_CloseHandle
0x18005f262  mov     ecx, ebx; dwErrCode
0x18005f264  call    cs:__imp_SetLastError
0x18005f26a  mov     [rsi], rdi
0x18005f26d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005f271  lea     rax, [rdi-1]
0x18005f275  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005f279  ja      short loc_18005F284
0x18005f27b  mov     rcx, rdi; hObject
0x18005f27e  call    cs:__imp_CloseHandle
0x18005f284  add     rsp, 58h
0x18005f288  pop     r15
0x18005f28a  pop     r14
0x18005f28c  pop     rdi
0x18005f28d  pop     rsi
0x18005f28e  pop     rbp
0x18005f28f  pop     rbx
0x18005f290  retn
0x18005f291  lea     r8, aOnecoreVmCommo_25; "onecore\\vm\\common\\gueststate\\guests"...
0x18005f298  mov     edx, 0CEh; void *
0x18005f29d  mov     rcx, r15; this
0x18005f2a0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005f2a6  mov     rcx, rbx
0x18005f2a9  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18005f2ae  mov     rcx, [rsp+88h]; this
0x18005f2b6  mov     qword ptr [rsp+88h+nInBufferSize], rax; char *
0x18005f2bb  lea     r9, aFailedToReopen; "Failed to reopen file \"%ws\""
0x18005f2c2  lea     r8, aOnecoreVmCommo_25; "onecore\\vm\\common\\gueststate\\guests"...
0x18005f2c9  mov     edx, 0C9h; void *
0x18005f2ce  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
