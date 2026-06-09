# UpdateLastMasterKeySync(void *)

- ea: `0x180039d90`
- end: `0x180039f7a`
- name: `?UpdateLastMasterKeySync@@YAKPEAX@Z`
- size: `490`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180008af0`
- `0x18002a03c`
- `0x18002ae48`
- `0x18002c0a0`
- `0x18002d7e0`

## callees

- `0x180001e60`
- `0x180007f10`
- `0x180008498`
- `0x18000dd40`
- `0x180013bec`
- `0x18001c0a4`
- `0x18001c9c0`
- `0x18001d810`
- `0x180039d90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039f19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039f19`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180039ec7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180039ef2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180039ec7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180039ef2`

## string_xrefs

- `0x180039f36`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysync.cpp`

## pseudocode

```c
__int64 __fastcall UpdateLastMasterKeySync(_QWORD *a1)
{
  unsigned int MasterKeySyncHash; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9
  const char *v5; // rdx
  __int64 v6; // rcx
  unsigned int v8; // [rsp+28h] [rbp-41h]
  unsigned int v9; // [rsp+30h] [rbp-39h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+34h] [rbp-35h] BYREF
  HANDLE hFile; // [rsp+38h] [rbp-31h] BYREF
  struct _MK_LOCATION *v12; // [rsp+40h] [rbp-29h] BYREF
  HANDLE *p_hFile; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v14[2]; // [rsp+50h] [rbp-19h] BYREF
  __int64 Buffer; // [rsp+60h] [rbp-9h] BYREF
  int v16; // [rsp+68h] [rbp-1h]
  unsigned __int8 v17[64]; // [rsp+70h] [rbp+7h] BYREF

  hFile = (HANDLE)-1LL;
  p_hFile = &hFile;
  Buffer = 0;
  v16 = 0;
  NumberOfBytesWritten = 0;
  v12 = 0;
  v9 = 0;
  v14[0] = &v12;
  v14[1] = &v9;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids);
  MasterKeySyncHash = EnumerateMasterKeys(a1, &v12, &v9);
  v3 = MasterKeySyncHash;
  if ( MasterKeySyncHash )
  {
    v4 = 519;
LABEL_14:
    v5 = "dwLastError";
    v6 = MasterKeySyncHash;
    goto LABEL_15;
  }
  hFile = (HANDLE)OpenSyncHistoryFile(a1, 0xC0000000);
  if ( hFile != (HANDLE)-1LL )
  {
    Buffer = 0x800E00000001LL;
    v16 = 64;
    MasterKeySyncHash = GetMasterKeySyncHash(a1, v12, v9, 0x800Eu, v17, v8);
    v3 = MasterKeySyncHash;
    if ( MasterKeySyncHash )
    {
      v4 = 542;
    }
    else
    {
      if ( WriteFile(hFile, &Buffer, 0xCu, &NumberOfBytesWritten, 0)
        && WriteFile(hFile, v17, 0x40u, &NumberOfBytesWritten, 0) )
      {
        ScopedSSFreeMK_LOCATION_Array::~ScopedSSFreeMK_LOCATION_Array((ScopedSSFreeMK_LOCATION_Array *)v14);
        ScopedCloseHandle::~ScopedCloseHandle((ScopedCloseHandle *)&p_hFile);
        return 0;
      }
      MasterKeySyncHash = GetLastError();
      v3 = MasterKeySyncHash;
      v4 = 561;
    }
    goto LABEL_14;
  }
  v4 = 526;
  v5 = "ERROR_NOT_FOUND";
  v3 = 1168;
  v6 = 1168;
LABEL_15:
  DebugTraceError(v6, v5, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysync.cpp", v4);
  ScopedSSFreeMK_LOCATION_Array::~ScopedSSFreeMK_LOCATION_Array((ScopedSSFreeMK_LOCATION_Array *)v14);
  ScopedCloseHandle::~ScopedCloseHandle((ScopedCloseHandle *)&p_hFile);
  return v3;
}

```

## disassembly

```asm
0x180039d90  mov     [rsp-8+arg_8], rbx
0x180039d95  mov     [rsp-8+arg_10], rdi
0x180039d9a  push    rbp
0x180039d9b  lea     rbp, [rsp-57h]
0x180039da0  sub     rsp, 0C0h
0x180039da7  mov     rax, cs:__security_cookie
0x180039dae  xor     rax, rsp
0x180039db1  mov     [rbp+57h+var_10], rax
0x180039db5  mov     rdi, rcx
0x180039db8  mov     [rbp+57h+hFile], 0FFFFFFFFFFFFFFFFh
0x180039dc0  lea     rax, [rbp+57h+hFile]
0x180039dc4  mov     [rbp+57h+var_78], rax
0x180039dc8  xor     eax, eax
0x180039dca  mov     [rbp+57h+Buffer], rax
0x180039dce  mov     [rbp+57h+var_58], eax
0x180039dd1  mov     [rbp+57h+NumberOfBytesWritten], eax
0x180039dd4  mov     [rbp+57h+var_80], rax
0x180039dd8  mov     [rbp+57h+var_90], eax
0x180039ddb  lea     rax, [rbp+57h+var_80]
0x180039ddf  mov     [rbp+57h+var_70], rax
0x180039de3  lea     rax, [rbp+57h+var_90]
0x180039de7  mov     [rbp+57h+var_68], rax
0x180039deb  lea     rax, WPP_GLOBAL_Control
0x180039df2  mov     rcx, cs:WPP_GLOBAL_Control
0x180039df9  cmp     rcx, rax
0x180039dfc  jz      short loc_180039E19
0x180039dfe  test    byte ptr [rcx+1Ch], 4
0x180039e02  jz      short loc_180039E19
0x180039e04  mov     edx, 19h
0x180039e09  lea     r8, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids
0x180039e10  mov     rcx, [rcx+10h]
0x180039e14  call    WPP_SF_
0x180039e19  lea     r8, [rbp+57h+var_90]; unsigned int *
0x180039e1d  lea     rdx, [rbp+57h+var_80]; struct _MK_LOCATION **
0x180039e21  mov     rcx, rdi; void *
0x180039e24  call    ?EnumerateMasterKeys@@YAKPEAXPEAPEAU_MK_LOCATION@@PEAK@Z; EnumerateMasterKeys(void *,_MK_LOCATION * *,ulong *)
0x180039e29  mov     ebx, eax
0x180039e2b  test    eax, eax
0x180039e2d  jz      short loc_180039E3A
0x180039e2f  mov     r9d, 207h
0x180039e35  jmp     loc_180039F2D
0x180039e3a  mov     edx, 0C0000000h; unsigned int
0x180039e3f  mov     rcx, rdi; void *
0x180039e42  call    ?OpenSyncHistoryFile@@YAPEAXPEAXK@Z; OpenSyncHistoryFile(void *,ulong)
0x180039e47  mov     [rbp+57h+hFile], rax
0x180039e4b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039e4f  jnz     short loc_180039E6A
0x180039e51  mov     r9d, 20Eh
0x180039e57  lea     rdx, aErrorNotFound; "ERROR_NOT_FOUND"
0x180039e5e  mov     ebx, 490h
0x180039e63  mov     ecx, ebx
0x180039e65  jmp     loc_180039F36
0x180039e6a  mov     dword ptr [rbp+57h+Buffer], 1
0x180039e71  mov     [rbp+57h+var_58], 40h ; '@'
0x180039e78  mov     r9d, 800Eh; unsigned int
0x180039e7e  mov     dword ptr [rbp+57h+Buffer+4], r9d
0x180039e82  lea     rax, [rbp+57h+var_50]
0x180039e86  mov     [rsp+0C0h+lpOverlapped], rax; unsigned __int8 *
0x180039e8b  mov     r8d, [rbp+57h+var_90]; unsigned int
0x180039e8f  mov     rdx, [rbp+57h+var_80]; struct _MK_LOCATION *
0x180039e93  mov     rcx, rdi; void *
0x180039e96  call    ?GetMasterKeySyncHash@@YAKPEAXPEAU_MK_LOCATION@@KKPEAEK@Z; GetMasterKeySyncHash(void *,_MK_LOCATION *,ulong,ulong,uchar *,ulong)
0x180039e9b  mov     ebx, eax
0x180039e9d  test    eax, eax
0x180039e9f  jz      short loc_180039EAC
0x180039ea1  mov     r9d, 21Eh
0x180039ea7  jmp     loc_180039F2D
0x180039eac  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x180039eb5  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180039eb9  mov     r8d, 0Ch; nNumberOfBytesToWrite
0x180039ebf  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180039ec3  mov     rcx, [rbp+57h+hFile]; hFile
0x180039ec7  call    cs:__imp_WriteFile
0x180039ece  nop     dword ptr [rax+rax+00h]
0x180039ed3  test    eax, eax
0x180039ed5  jz      short loc_180039F19
0x180039ed7  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x180039ee0  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180039ee4  mov     r8d, 40h ; '@'; nNumberOfBytesToWrite
0x180039eea  lea     rdx, [rbp+57h+var_50]; lpBuffer
0x180039eee  mov     rcx, [rbp+57h+hFile]; hFile
0x180039ef2  call    cs:__imp_WriteFile
0x180039ef9  nop     dword ptr [rax+rax+00h]
0x180039efe  test    eax, eax
0x180039f00  jz      short loc_180039F19
0x180039f02  lea     rcx, [rbp+57h+var_70]; this
0x180039f06  call    ??1ScopedSSFreeMK_LOCATION_Array@@QEAA@XZ; ScopedSSFreeMK_LOCATION_Array::~ScopedSSFreeMK_LOCATION_Array(void)
0x180039f0b  nop
0x180039f0c  lea     rcx, [rbp+57h+var_78]; this
0x180039f10  call    ??1ScopedCloseHandle@@QEAA@XZ; ScopedCloseHandle::~ScopedCloseHandle(void)
0x180039f15  xor     eax, eax
0x180039f17  jmp     short loc_180039F58
0x180039f19  call    cs:__imp_GetLastError
0x180039f20  nop     dword ptr [rax+rax+00h]
0x180039f25  mov     ebx, eax
0x180039f27  mov     r9d, 231h
0x180039f2d  lea     rdx, aDwlasterror; "dwLastError"
0x180039f34  mov     ecx, eax
0x180039f36  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180039f3d  call    DebugTraceError
0x180039f42  nop
0x180039f43  lea     rcx, [rbp+57h+var_70]; this
0x180039f47  call    ??1ScopedSSFreeMK_LOCATION_Array@@QEAA@XZ; ScopedSSFreeMK_LOCATION_Array::~ScopedSSFreeMK_LOCATION_Array(void)
0x180039f4c  nop
0x180039f4d  lea     rcx, [rbp+57h+var_78]; this
0x180039f51  call    ??1ScopedCloseHandle@@QEAA@XZ; ScopedCloseHandle::~ScopedCloseHandle(void)
0x180039f56  mov     eax, ebx
0x180039f58  mov     rcx, [rbp+57h+var_10]
0x180039f5c  xor     rcx, rsp; StackCookie
0x180039f5f  call    __security_check_cookie
0x180039f64  lea     r11, [rsp+0C0h+var_s0]
0x180039f6c  mov     rbx, [r11+18h]
0x180039f70  mov     rdi, [r11+20h]
0x180039f74  mov     rsp, r11
0x180039f77  pop     rbp
0x180039f78  retn
```
