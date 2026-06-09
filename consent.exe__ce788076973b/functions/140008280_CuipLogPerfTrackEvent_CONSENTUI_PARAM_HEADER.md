# CuipLogPerfTrackEvent(_CONSENTUI_PARAM_HEADER *)

- ea: `0x140008280`
- end: `0x1400083a1`
- name: `?CuipLogPerfTrackEvent@@YAXPEAU_CONSENTUI_PARAM_HEADER@@@Z`
- size: `289`
- prototype: `void __fastcall(struct _CONSENTUI_PARAM_HEADER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001a080`

## callees

- `0x140008280`
- `0x14001e050`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1400082f2`
- `ntdll!EtwEventWrite` at `0x1400082f2`
- `ntdll!NtQueryVolumeInformationFile` at `0x140008349`
- `ntdll!NtQueryVolumeInformationFile` at `0x140008349`

## pseudocode

```c
void __fastcall CuipLogPerfTrackEvent(struct _CONSENTUI_PARAM_HEADER *a1)
{
  int v1; // eax
  unsigned int v3; // edi
  int v4; // eax
  int v5; // eax
  int v6; // eax
  __int64 *v7; // rdx
  void *v8; // rcx
  __int64 FsInformation; // [rsp+30h] [rbp-48h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v11[4]; // [rsp+48h] [rbp-30h] BYREF

  v1 = *((_DWORD *)a1 + 1);
  v3 = 1;
  if ( !v1 )
  {
    v8 = (void *)*((_QWORD *)a1 + 25);
    FsInformation = 0;
    IoStatusBlock = 0;
    if ( v8 != (void *)-1LL
      && NtQueryVolumeInformationFile(v8, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation) >= 0
      && (FsInformation & 0x1000000000LL) != 0 )
    {
      v7 = AppInfo_PerfTrack_Elevation_EXE_Network_Stop;
      goto LABEL_8;
    }
    v7 = AppInfo_PerfTrack_Elevation_EXE_Stop;
LABEL_15:
    v11[3] = 4;
    v11[2] = &qword_140021530;
    v3 = 2;
    goto LABEL_8;
  }
  v4 = v1 - 1;
  if ( !v4 )
  {
    v7 = AppInfo_PerfTrack_Elevation_COM_Stop;
    goto LABEL_15;
  }
  v5 = v4 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      if ( v6 != 2 )
        return;
      v7 = AppInfo_PerfTrack_Elevation_PackagedApp_Stop;
    }
    else
    {
      v7 = AppInfo_PerfTrack_Elevation_AxIS_Stop;
    }
  }
  else
  {
    v7 = AppInfo_PerfTrack_Elevation_MSI_Stop;
  }
LABEL_8:
  v11[0] = (char *)a1 + 52;
  v11[1] = 4;
  EtwEventWrite(g_ConsentPerfRegHandle, v7, v3, v11);
}

```

## disassembly

```asm
0x140008280  mov     [rsp+arg_8], rbx
0x140008285  push    rdi
0x140008286  sub     rsp, 70h
0x14000828a  mov     rax, cs:__security_cookie
0x140008291  xor     rax, rsp
0x140008294  mov     [rsp+78h+var_10], rax
0x140008299  mov     eax, [rcx+4]
0x14000829c  mov     rbx, rcx
0x14000829f  mov     edi, 1
0x1400082a4  test    eax, eax
0x1400082a6  jz      short loc_140008313
0x1400082a8  sub     eax, edi
0x1400082aa  jz      loc_140008398
0x1400082b0  sub     eax, edi
0x1400082b2  jz      short loc_1400082CA
0x1400082b4  sub     eax, edi
0x1400082b6  jz      loc_14000838C
0x1400082bc  cmp     eax, 2
0x1400082bf  jnz     short loc_1400082F8
0x1400082c1  lea     rdx, AppInfo_PerfTrack_Elevation_PackagedApp_Stop
0x1400082c8  jmp     short loc_1400082D1
0x1400082ca  lea     rdx, AppInfo_PerfTrack_Elevation_MSI_Stop
0x1400082d1  mov     rcx, cs:?g_ConsentPerfRegHandle@@3_KA; unsigned __int64 g_ConsentPerfRegHandle
0x1400082d8  lea     rax, [rbx+34h]
0x1400082dc  lea     r9, [rsp+78h+var_30]
0x1400082e1  mov     [rsp+78h+var_30], rax
0x1400082e6  mov     r8d, edi
0x1400082e9  mov     [rsp+78h+var_28], 4
0x1400082f2  call    cs:__imp_EtwEventWrite
0x1400082f8  mov     rcx, [rsp+78h+var_10]
0x1400082fd  xor     rcx, rsp; StackCookie
0x140008300  call    __security_check_cookie
0x140008305  mov     rbx, [rsp+78h+arg_8]
0x14000830d  add     rsp, 70h
0x140008311  pop     rdi
0x140008312  retn
0x140008313  mov     rcx, [rcx+0C8h]; FileHandle
0x14000831a  xorps   xmm0, xmm0
0x14000831d  mov     [rsp+78h+FsInformation], 0
0x140008326  movups  xmmword ptr [rsp+78h+IoStatusBlock], xmm0
0x14000832b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000832f  jz      short loc_140008366
0x140008331  mov     r9d, 8; Length
0x140008337  mov     [rsp+78h+FsInformationClass], 4; FsInformationClass
0x14000833f  lea     r8, [rsp+78h+FsInformation]; FsInformation
0x140008344  lea     rdx, [rsp+78h+IoStatusBlock]; IoStatusBlock
0x140008349  call    cs:__imp_NtQueryVolumeInformationFile
0x14000834f  test    eax, eax
0x140008351  js      short loc_140008366
0x140008353  test    byte ptr [rsp+78h+FsInformation+4], 10h
0x140008358  jz      short loc_140008366
0x14000835a  lea     rdx, AppInfo_PerfTrack_Elevation_EXE_Network_Stop
0x140008361  jmp     loc_1400082D1
0x140008366  lea     rdx, AppInfo_PerfTrack_Elevation_EXE_Stop
0x14000836d  lea     rax, qword_140021530
0x140008374  mov     [rsp+78h+var_18], 4
0x14000837d  mov     [rsp+78h+var_20], rax
0x140008382  mov     edi, 2
0x140008387  jmp     loc_1400082D1
0x14000838c  lea     rdx, AppInfo_PerfTrack_Elevation_AxIS_Stop
0x140008393  jmp     loc_1400082D1
0x140008398  lea     rdx, AppInfo_PerfTrack_Elevation_COM_Stop
0x14000839f  jmp     short loc_14000836D
```
