# GuestStateFile::CreateBackingStore(ushort const *,unsigned __int64,_GUID const *)

- ea: `0x180053c84`
- end: `0x180053e1e`
- name: `?CreateBackingStore@GuestStateFile@@CA_NPEBG_KPEBU_GUID@@@Z`
- size: `410`
- prototype: `bool __fastcall(const unsigned __int16 *, unsigned __int64, const struct _GUID *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180053b10`
- `0x18005a870`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x1800526dc`
- `0x180052930`
- `0x180053c84`
- `0x180053e24`
- `0x180053f40`
- `0x1800567f4`
- `0x18005782c`
- `0x18005ac60`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053dab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053dab`
- `VirtDisk!CreateVirtualDisk` at `0x180053d79`
- `VirtDisk!CreateVirtualDisk` at `0x180053d79`

## string_xrefs

- `0x180053ccd`: `GuestStateFileCreateBackingStore`
- `0x180053e0c`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x180053dfd`: `Failed to create file "%ws"`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall GuestStateFile::CreateBackingStore(
        const unsigned __int16 *a1,
        unsigned __int64 a2,
        const struct _GUID *a3)
{
  DWORD v6; // eax
  bool v7; // bl
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+58h] [rbp-A8h] BYREF
  struct _CREATE_VIRTUAL_DISK_PARAMETERS Parameters; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v12[42]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  memset_0(v12, 0, sizeof(v12));
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v12,
    "GuestStateFileCreateBackingStore");
  v12[0] = &GuestStateFileTraceProvider::GuestStateFileCreateBackingStore::`vftable';
  GuestStateFileTraceProvider::GuestStateFileCreateBackingStore::StartActivity(
    (GuestStateFileTraceProvider::GuestStateFileCreateBackingStore *)v12,
    a1,
    a2,
    a3);
  GuestStateFile::EnsureDirectoryExists(a1);
  memset_0(&Parameters, 0, sizeof(Parameters));
  VirtualStorageType.DeviceId = 2;
  VirtualStorageType.VendorId = VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT;
  Parameters.Version = CREATE_VIRTUAL_DISK_VERSION_1;
  *(_OWORD *)&Parameters.Version4.MaximumSize = a2;
  hObject = (HANDLE)-1LL;
  v6 = CreateVirtualDisk(
         &VirtualStorageType,
         a1,
         VIRTUAL_DISK_ACCESS_ALL,
         0,
         CREATE_VIRTUAL_DISK_FLAG_FULL_PHYSICAL_ALLOCATION,
         0,
         &Parameters,
         0,
         &hObject);
  if ( v6 && v6 != 80 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)v6,
      (unsigned int)"Failed to create file \"%ws\"",
      (const char *)a1);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v12);
  v7 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  v12[0] = &GuestStateFileTraceProvider::GuestStateFileCreateBackingStore::`vftable';
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v12);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(v12);
  return v7;
}

```

## disassembly

```asm
0x180053c84  mov     [rsp-8+arg_10], rbx
0x180053c89  mov     [rsp-8+arg_18], rsi
0x180053c8e  push    rbp
0x180053c8f  push    rdi
0x180053c90  push    r14
0x180053c92  lea     rbp, [rsp-190h]
0x180053c9a  sub     rsp, 290h
0x180053ca1  mov     rax, cs:__security_cookie
0x180053ca8  xor     rax, rsp
0x180053cab  mov     [rbp+1A0h+var_20], rax
0x180053cb2  mov     rbx, r8
0x180053cb5  mov     rdi, rdx
0x180053cb8  mov     rsi, rcx
0x180053cbb  xor     edx, edx; Val
0x180053cbd  mov     r8d, 150h; Size
0x180053cc3  lea     rcx, [rbp+1A0h+var_170]; void *
0x180053cc7  call    memset_0
0x180053ccc  nop
0x180053ccd  lea     rdx, aGueststatefile_0; "GuestStateFileCreateBackingStore"
0x180053cd4  lea     rcx, [rbp+1A0h+var_170]
0x180053cd8  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180053cdd  lea     r14, ??_7GuestStateFileCreateBackingStore@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileCreateBackingStore::`vftable'
0x180053ce4  mov     [rbp+1A0h+var_170], r14
0x180053ce8  mov     r9, rbx; struct _GUID *
0x180053ceb  mov     r8, rdi; unsigned __int64
0x180053cee  mov     rdx, rsi; unsigned __int16 *
0x180053cf1  lea     rcx, [rbp+1A0h+var_170]; this
0x180053cf5  call    ?StartActivity@GuestStateFileCreateBackingStore@GuestStateFileTraceProvider@@QEAAXPEBG_KPEBU_GUID@@@Z; GuestStateFileTraceProvider::GuestStateFileCreateBackingStore::StartActivity(ushort const *,unsigned __int64,_GUID const *)
0x180053cfa  nop
0x180053cfb  mov     rcx, rsi; unsigned __int16 *
0x180053cfe  call    ?EnsureDirectoryExists@GuestStateFile@@CAXPEBG@Z; GuestStateFile::EnsureDirectoryExists(ushort const *)
0x180053d03  nop
0x180053d04  xor     edx, edx; Val
0x180053d06  mov     r8d, 0B8h; Size
0x180053d0c  lea     rcx, [rsp+2A0h+var_230]; void *
0x180053d11  call    memset_0
0x180053d16  mov     [rsp+2A0h+VirtualStorageType.DeviceId], 2
0x180053d1e  movups  xmm0, xmmword ptr cs:VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT.Data1
0x180053d25  movdqu  xmmword ptr [rsp+2A0h+VirtualStorageType.VendorId.Data1], xmm0
0x180053d2b  mov     ecx, 1
0x180053d30  mov     [rsp+2A0h+var_230.Version], ecx
0x180053d34  mov     qword ptr [rbp+1A0h+var_230.8+10h], rdi
0x180053d38  xor     ebx, ebx
0x180053d3a  mov     qword ptr [rbp+1A0h+var_230.8+18h], rbx
0x180053d3e  mov     [rsp+2A0h+hObject], 0FFFFFFFFFFFFFFFFh
0x180053d47  lea     rax, [rsp+2A0h+hObject]
0x180053d4c  mov     [rsp+2A0h+Handle], rax; Handle
0x180053d51  mov     [rsp+2A0h+Overlapped], rbx; Overlapped
0x180053d56  lea     rax, [rsp+2A0h+var_230]
0x180053d5b  mov     [rsp+2A0h+Parameters], rax; Parameters
0x180053d60  mov     [rsp+2A0h+ProviderSpecificFlags], ebx; ProviderSpecificFlags
0x180053d64  mov     [rsp+2A0h+Flags], ecx; Flags
0x180053d68  xor     r9d, r9d; SecurityDescriptor
0x180053d6b  mov     r8d, 3F0000h; VirtualDiskAccessMask
0x180053d71  mov     rdx, rsi; Path
0x180053d74  lea     rcx, [rsp+2A0h+VirtualStorageType]; VirtualStorageType
0x180053d79  call    cs:__imp_CreateVirtualDisk
0x180053d7f  test    eax, eax
0x180053d81  jz      short loc_180053D88
0x180053d83  cmp     eax, 50h ; 'P'
0x180053d86  jnz     short loc_180053DF1
0x180053d88  lea     rcx, [rbp+1A0h+var_170]
0x180053d8c  call    ?Stop@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180053d91  mov     rcx, [rsp+2A0h+hObject]; hObject
0x180053d96  lea     rax, [rcx-1]
0x180053d9a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180053d9e  setbe   bl
0x180053da1  lea     rdx, [rcx-1]
0x180053da5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180053da9  ja      short loc_180053DB2
0x180053dab  call    cs:__imp_CloseHandle
0x180053db1  nop
0x180053db2  mov     [rbp+1A0h+var_170], r14
0x180053db6  lea     rcx, [rbp+1A0h+var_170]
0x180053dba  call    ?Destroy@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180053dbf  lea     rcx, [rbp+1A0h+var_170]
0x180053dc3  call    ??1?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180053dc8  mov     al, bl
0x180053dca  mov     rcx, [rbp+1A0h+var_20]
0x180053dd1  xor     rcx, rsp; StackCookie
0x180053dd4  call    __security_check_cookie
0x180053dd9  lea     r11, [rsp+2A0h+var_10]
0x180053de1  mov     rbx, [r11+30h]
0x180053de5  mov     rsi, [r11+38h]
0x180053de9  mov     rsp, r11
0x180053dec  pop     r14
0x180053dee  pop     rdi
0x180053def  pop     rbp
0x180053df0  retn
0x180053df1  mov     rcx, [rbp+1A8h]; this
0x180053df8  mov     qword ptr [rsp+2A0h+ProviderSpecificFlags], rsi; char *
0x180053dfd  lea     rdx, aFailedToCreate_0; "Failed to create file \"%ws\""
0x180053e04  mov     qword ptr [rsp+2A0h+Flags], rdx; unsigned int
0x180053e09  mov     r9d, eax; char *
0x180053e0c  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x180053e13  mov     edx, 104h; void *
0x180053e18  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
