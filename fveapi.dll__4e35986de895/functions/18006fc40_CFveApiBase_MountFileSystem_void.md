# CFveApiBase::MountFileSystem(void)

- ea: `0x18006fc40`
- end: `0x18006fe97`
- name: `?MountFileSystem@CFveApiBase@@MEAAJXZ`
- size: `599`
- prototype: `__int64 __fastcall(CFveApiBase *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x1800050c0`
- `0x180005410`
- `0x180008d70`
- `0x1800090c0`
- `0x180009468`
- `0x180023800`
- `0x18003a230`
- `0x18006fc40`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x18006fcec`
- `ntdll!RtlSetThreadErrorMode` at `0x18006fe38`
- `ntdll!RtlSetThreadErrorMode` at `0x1801228e6`
- `ntdll!RtlSetThreadErrorMode` at `0x18006fcec`
- `ntdll!RtlSetThreadErrorMode` at `0x18006fe38`
- `ntdll!RtlSetThreadErrorMode` at `0x1801228e6`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18006fe17`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18006fe17`

## pseudocode

```c
__int64 __fastcall CFveApiBase::MountFileSystem(CFveApiBase *this)
{
  int LastHresultError; // ebx
  unsigned int v3; // r10d
  unsigned int v4; // r10d
  unsigned __int64 v6; // [rsp+48h] [rbp-660h] BYREF
  ULONG OldMode[4]; // [rsp+50h] [rbp-658h] BYREF
  WCHAR RootPathName[264]; // [rsp+60h] [rbp-648h] BYREF
  WCHAR FileSystemNameBuffer[264]; // [rsp+270h] [rbp-438h] BYREF
  WCHAR VolumeNameBuffer[264]; // [rsp+480h] [rbp-228h] BYREF

  OldMode[0] = 0;
  memset_0(RootPathName, 0, 0x20Cu);
  v6 = 0;
  memset_0(VolumeNameBuffer, 0, 0x20Au);
  memset_0(FileSystemNameBuffer, 0, 0x20Au);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids);
  RtlSetThreadErrorMode(0x10u, OldMode);
  if ( !*((_QWORD *)this + 47) )
    goto LABEL_5;
  LastHresultError = CFveApiBase::ResolveVolumeMountName(this);
  if ( LastHresultError >= 0 )
  {
    LastHresultError = StringCchCopyW(RootPathName, 0x106u, *((const unsigned __int16 **)this + 49));
    if ( LastHresultError >= 0 )
    {
      LastHresultError = StringCchLengthW(RootPathName, v3, &v6);
      if ( LastHresultError >= 0 )
      {
        if ( v6 <= 1 )
        {
LABEL_5:
          LastHresultError = -2147024809;
          goto LABEL_20;
        }
        if ( *((_WORD *)&OldMode[3] + v6 + 1) == 92 || *((_WORD *)&OldMode[3] + v6 + 1) == 47 )
        {
          *((_WORD *)&OldMode[3] + v6 + 1) = 92;
        }
        else
        {
          LastHresultError = StringCchCatW(RootPathName, v4, L"\\");
          if ( LastHresultError < 0 )
            goto LABEL_20;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids);
        if ( !GetVolumeInformationW(RootPathName, VolumeNameBuffer, 0x105u, 0, 0, 0, FileSystemNameBuffer, 0x105u) )
          LastHresultError = GetLastHresultError();
      }
    }
  }
LABEL_20:
  RtlSetThreadErrorMode(OldMode[0], 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids,
      (unsigned int)LastHresultError);
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x18006fc40  mov     [rsp+arg_8], rbx
0x18006fc45  mov     [rsp+arg_10], rdi
0x18006fc4a  push    r14
0x18006fc4c  sub     rsp, 6A0h
0x18006fc53  mov     rax, cs:__security_cookie
0x18006fc5a  xor     rax, rsp
0x18006fc5d  mov     [rsp+6A8h+var_18], rax
0x18006fc65  mov     rdi, rcx
0x18006fc68  mov     [rsp+6A8h+OldMode], 0
0x18006fc70  xor     edx, edx; Val
0x18006fc72  mov     r8d, 20Ch; Size
0x18006fc78  lea     rcx, [rsp+6A8h+RootPathName]; void *
0x18006fc7d  call    memset_0
0x18006fc82  mov     [rsp+6A8h+var_660], 0
0x18006fc8b  mov     ebx, 20Ah
0x18006fc90  mov     r8d, ebx; Size
0x18006fc93  xor     edx, edx; Val
0x18006fc95  lea     rcx, [rsp+6A8h+VolumeNameBuffer]; void *
0x18006fc9d  call    memset_0
0x18006fca2  mov     r8d, ebx; Size
0x18006fca5  xor     edx, edx; Val
0x18006fca7  lea     rcx, [rsp+6A8h+FileSystemNameBuffer]; void *
0x18006fcaf  call    memset_0
0x18006fcb4  lea     r14, WPP_GLOBAL_Control
0x18006fcbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fcc2  cmp     rcx, r14
0x18006fcc5  jz      short loc_18006FCE2
0x18006fcc7  test    byte ptr [rcx+1Ch], 20h
0x18006fccb  jz      short loc_18006FCE2
0x18006fccd  mov     edx, 14h
0x18006fcd2  lea     r8, WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids
0x18006fcd9  mov     rcx, [rcx+10h]
0x18006fcdd  call    WPP_SF_
0x18006fce2  lea     rdx, [rsp+6A8h+OldMode]; OldMode
0x18006fce7  mov     ecx, 10h; NewMode
0x18006fcec  call    cs:__imp_RtlSetThreadErrorMode
0x18006fcf3  nop     dword ptr [rax+rax+00h]
0x18006fcf8  nop
0x18006fcf9  cmp     qword ptr [rdi+178h], 0
0x18006fd01  jnz     short loc_18006FD11
0x18006fd03  mov     ebx, 80070057h
0x18006fd08  mov     [rsp+6A8h+var_668], ebx
0x18006fd0c  jmp     loc_18006FE32
0x18006fd11  mov     rcx, rdi; this
0x18006fd14  call    ?ResolveVolumeMountName@CFveApiBase@@QEAAJXZ; CFveApiBase::ResolveVolumeMountName(void)
0x18006fd19  mov     ebx, eax
0x18006fd1b  mov     [rsp+6A8h+var_668], eax
0x18006fd1f  test    eax, eax
0x18006fd21  js      loc_18006FE32
0x18006fd27  mov     r8, [rdi+188h]; unsigned __int16 *
0x18006fd2e  mov     r10d, 106h
0x18006fd34  mov     edx, r10d; unsigned __int64
0x18006fd37  lea     rcx, [rsp+6A8h+RootPathName]; unsigned __int16 *
0x18006fd3c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006fd41  mov     ebx, eax
0x18006fd43  mov     [rsp+6A8h+var_668], eax
0x18006fd47  test    eax, eax
0x18006fd49  js      loc_18006FE32
0x18006fd4f  lea     r8, [rsp+6A8h+var_660]; unsigned __int64 *
0x18006fd54  mov     edx, r10d; unsigned __int64
0x18006fd57  lea     rcx, [rsp+6A8h+RootPathName]; unsigned __int16 *
0x18006fd5c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006fd61  mov     ebx, eax
0x18006fd63  mov     [rsp+6A8h+var_668], eax
0x18006fd67  test    eax, eax
0x18006fd69  js      loc_18006FE32
0x18006fd6f  mov     rax, [rsp+6A8h+var_660]
0x18006fd74  cmp     rax, 1
0x18006fd78  jbe     short loc_18006FD03
0x18006fd7a  mov     ecx, 5Ch ; '\'
0x18006fd7f  cmp     [rsp+rax*2+6A8h+var_64A], cx
0x18006fd84  jz      short loc_18006FDB1
0x18006fd86  cmp     [rsp+rax*2+6A8h+var_64A], 2Fh ; '/'
0x18006fd8c  jz      short loc_18006FDB1
0x18006fd8e  lea     r8, asc_180134CC8; "\\"
0x18006fd95  mov     edx, r10d; unsigned __int64
0x18006fd98  lea     rcx, [rsp+6A8h+RootPathName]; unsigned __int16 *
0x18006fd9d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006fda2  mov     ebx, eax
0x18006fda4  mov     [rsp+6A8h+var_668], eax
0x18006fda8  test    eax, eax
0x18006fdaa  jns     short loc_18006FDB6
0x18006fdac  jmp     loc_18006FE32
0x18006fdb1  mov     [rsp+rax*2+6A8h+var_64A], cx
0x18006fdb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fdbd  cmp     rcx, r14
0x18006fdc0  jz      short loc_18006FDDD
0x18006fdc2  test    byte ptr [rcx+1Ch], 8
0x18006fdc6  jz      short loc_18006FDDD
0x18006fdc8  mov     edx, 15h
0x18006fdcd  lea     r8, WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids
0x18006fdd4  mov     rcx, [rcx+10h]
0x18006fdd8  call    WPP_SF_
0x18006fddd  mov     r8d, 105h; nVolumeNameSize
0x18006fde3  mov     [rsp+6A8h+nFileSystemNameSize], r8d; nFileSystemNameSize
0x18006fde8  lea     rax, [rsp+6A8h+FileSystemNameBuffer]
0x18006fdf0  mov     [rsp+6A8h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x18006fdf5  mov     [rsp+6A8h+lpFileSystemFlags], 0; lpFileSystemFlags
0x18006fdfe  mov     [rsp+6A8h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x18006fe07  xor     r9d, r9d; lpVolumeSerialNumber
0x18006fe0a  lea     rdx, [rsp+6A8h+VolumeNameBuffer]; lpVolumeNameBuffer
0x18006fe12  lea     rcx, [rsp+6A8h+RootPathName]; lpRootPathName
0x18006fe17  call    cs:__imp_GetVolumeInformationW
0x18006fe1e  nop     dword ptr [rax+rax+00h]
0x18006fe23  test    eax, eax
0x18006fe25  jnz     short loc_18006FE32
0x18006fe27  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18006fe2c  mov     ebx, eax
0x18006fe2e  mov     [rsp+6A8h+var_668], eax
0x18006fe32  xor     edx, edx; OldMode
0x18006fe34  mov     ecx, [rsp+6A8h+OldMode]; NewMode
0x18006fe38  call    cs:__imp_RtlSetThreadErrorMode
0x18006fe3f  nop     dword ptr [rax+rax+00h]
0x18006fe44  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fe4b  cmp     rcx, r14
0x18006fe4e  jz      short loc_18006FE6E
0x18006fe50  test    byte ptr [rcx+1Ch], 20h
0x18006fe54  jz      short loc_18006FE6E
0x18006fe56  mov     edx, 16h
0x18006fe5b  mov     r9d, ebx
0x18006fe5e  lea     r8, WPP_da00f36848ba3e1a1ff5c089a938cc48_Traceguids
0x18006fe65  mov     rcx, [rcx+10h]
0x18006fe69  call    WPP_SF_d
0x18006fe6e  mov     eax, ebx
0x18006fe70  mov     rcx, [rsp+6A8h+var_18]
0x18006fe78  xor     rcx, rsp; StackCookie
0x18006fe7b  call    __security_check_cookie
0x18006fe80  lea     r11, [rsp+6A8h+var_8]
0x18006fe88  mov     rbx, [r11+18h]
0x18006fe8c  mov     rdi, [r11+20h]
0x18006fe90  mov     rsp, r11
0x18006fe93  pop     r14
0x18006fe95  retn
0x1801228d8  push    rbp
0x1801228da  sub     rsp, 40h
0x1801228de  mov     rbp, rdx
0x1801228e1  xor     edx, edx; OldMode
0x1801228e3  mov     ecx, [rbp+50h]; NewMode
0x1801228e6  call    cs:__imp_RtlSetThreadErrorMode
0x1801228ed  nop     dword ptr [rax+rax+00h]
0x1801228f2  nop
0x1801228f3  add     rsp, 40h
0x1801228f7  pop     rbp
0x1801228f8  retn
```
