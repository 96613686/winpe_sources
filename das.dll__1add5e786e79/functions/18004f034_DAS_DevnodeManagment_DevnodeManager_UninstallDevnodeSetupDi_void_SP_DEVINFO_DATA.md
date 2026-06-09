# DAS::DevnodeManagment::DevnodeManager::UninstallDevnodeSetupDi(void *,_SP_DEVINFO_DATA *)

- ea: `0x18004f034`
- end: `0x18004f20f`
- name: `?UninstallDevnodeSetupDi@DevnodeManager@DevnodeManagment@DAS@@AEAAKPEAXPEAU_SP_DEVINFO_DATA@@@Z`
- size: `475`
- prototype: `unsigned int(DAS::DevnodeManagment::DevnodeManager *__hidden this, void *, struct _SP_DEVINFO_DATA *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18004f218`

## callees

- `0x180007500`
- `0x18001a760`
- `0x18002394c`
- `0x18004f034`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f07c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f1e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f07c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f1e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f1f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f1f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004f08d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004f08d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f0c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f10a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f0c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f10a`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetDeviceInstanceIdW` at `0x18004f0b3`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetDeviceInstanceIdW` at `0x18004f0b3`
- `ext-ms-win-newdev-config-l1-1-0!DiUninstallDevice` at `0x18004f100`
- `ext-ms-win-newdev-config-l1-1-0!DiUninstallDevice` at `0x18004f100`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::DevnodeManager::UninstallDevnodeSetupDi(
        DAS::DevnodeManagment::DevnodeManager *this,
        void *a2,
        struct _SP_DEVINFO_DATA *a3)
{
  WCHAR *v5; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v7; // rax
  char LastError; // al
  int v9; // edx
  int v10; // r8d
  int v11; // edx
  int v12; // r8d
  int v13; // edx
  DWORD v14; // edi
  int v15; // r8d
  int *v16; // rax
  HANDLE v17; // rax
  WINBOOL NeedReboot; // [rsp+60h] [rbp+8h] BYREF
  int v20; // [rsp+64h] [rbp+Ch]

  v20 = HIDWORD(this);
  NeedReboot = 0;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u || (v5 = 0, *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u) )
  {
    ProcessHeap = GetProcessHeap();
    v7 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x190u);
    v5 = v7;
    if ( v7 )
    {
      if ( !SetupDiGetDeviceInstanceIdW(a2, a3, v7, 0xC8u, 0)
        && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LastError = GetLastError();
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v9,
          v10,
          33,
          &WPP_416e81a390623384018c9851ffc16906_Traceguids,
          LastError);
      }
    }
  }
  if ( DiUninstallDevice(0, a2, a3, 0, &NeedReboot) )
  {
    v16 = *(int **)&WPP_RECORDER_INITIALIZED;
    v14 = 0;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v11,
        v12,
        36,
        &WPP_416e81a390623384018c9851ffc16906_Traceguids,
        (__int64)v5);
      v16 = *(int **)&WPP_RECORDER_INITIALIZED;
    }
    if ( NeedReboot && v16 != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v11,
        v12,
        37,
        &WPP_416e81a390623384018c9851ffc16906_Traceguids,
        (__int64)v5);
  }
  else
  {
    v14 = GetLastError();
    if ( v14 == -536870389 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v13,
          v15,
          34,
          &WPP_416e81a390623384018c9851ffc16906_Traceguids,
          (__int64)v5,
          11);
      v14 = 0;
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v13,
        v15,
        35,
        &WPP_416e81a390623384018c9851ffc16906_Traceguids,
        (__int64)v5,
        v14);
    }
  }
  if ( v5 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v5);
  }
  return v14;
}

```

## disassembly

```asm
0x18004f034  mov     rax, rsp
0x18004f037  mov     [rax+10h], rbx
0x18004f03b  mov     [rax+18h], rsi
0x18004f03f  mov     [rax+8], rcx
0x18004f043  push    rdi
0x18004f044  push    r14
0x18004f046  push    r15
0x18004f048  sub     rsp, 40h
0x18004f04c  mov     dword ptr [rax+8], 0
0x18004f053  lea     r15, WPP_416e81a390623384018c9851ffc16906_Traceguids
0x18004f05a  mov     rax, cs:WPP_GLOBAL_Control
0x18004f061  lea     r14, WPP_RECORDER_INITIALIZED
0x18004f068  mov     rdi, r8
0x18004f06b  mov     rsi, rdx
0x18004f06e  cmp     byte ptr [rax+19h], 4
0x18004f072  jnb     short loc_18004F07C
0x18004f074  xor     ebx, ebx
0x18004f076  cmp     byte ptr [rax+19h], 2
0x18004f07a  jb      short loc_18004F0EB
0x18004f07c  call    cs:__imp_GetProcessHeap
0x18004f082  xor     edx, edx; dwFlags
0x18004f084  mov     r8d, 190h; dwBytes
0x18004f08a  mov     rcx, rax; hHeap
0x18004f08d  call    cs:__imp_HeapAlloc
0x18004f093  mov     rbx, rax
0x18004f096  test    rax, rax
0x18004f099  jz      short loc_18004F0EB
0x18004f09b  mov     r9d, 0C8h; DeviceInstanceIdSize
0x18004f0a1  mov     [rsp+58h+RequiredSize], 0; RequiredSize
0x18004f0aa  mov     r8, rax; DeviceInstanceId
0x18004f0ad  mov     rdx, rdi; DeviceInfoData
0x18004f0b0  mov     rcx, rsi; DeviceInfoSet
0x18004f0b3  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x18004f0b9  test    eax, eax
0x18004f0bb  jnz     short loc_18004F0EB
0x18004f0bd  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18004f0c4  jz      short loc_18004F0EB
0x18004f0c6  call    cs:__imp_GetLastError
0x18004f0cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f0d3  mov     r9d, 21h ; '!'; int
0x18004f0d9  mov     dword ptr [rsp+58h+var_30], eax; char
0x18004f0dd  mov     [rsp+58h+RequiredSize], r15; MessageGuid
0x18004f0e2  mov     rcx, [rcx+28h]; int
0x18004f0e6  call    WPP_RECORDER_SF_D
0x18004f0eb  lea     rax, [rsp+58h+NeedReboot]
0x18004f0f0  xor     r9d, r9d; Flags
0x18004f0f3  mov     r8, rdi; DeviceInfoData
0x18004f0f6  mov     [rsp+58h+RequiredSize], rax; NeedReboot
0x18004f0fb  mov     rdx, rsi; DeviceInfoSet
0x18004f0fe  xor     ecx, ecx; hwndParent
0x18004f100  call    cs:__imp_DiUninstallDevice
0x18004f106  test    eax, eax
0x18004f108  jnz     short loc_18004F182
0x18004f10a  call    cs:__imp_GetLastError
0x18004f110  mov     edi, eax
0x18004f112  mov     eax, 0E000020Bh
0x18004f117  cmp     edi, eax
0x18004f119  jnz     short loc_18004F14F
0x18004f11b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18004f122  jz      short loc_18004F148
0x18004f124  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f12b  mov     r9d, 22h ; '"'; int
0x18004f131  mov     dword ptr [rsp+58h+var_28], eax; char
0x18004f135  mov     qword ptr [rsp+58h+var_30], rbx; __int64
0x18004f13a  mov     [rsp+58h+RequiredSize], r15; MessageGuid
0x18004f13f  mov     rcx, [rcx+28h]; int
0x18004f143  call    WPP_RECORDER_SF_Sd
0x18004f148  xor     edi, edi
0x18004f14a  jmp     loc_18004F1E0
0x18004f14f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18004f156  jz      loc_18004F1E0
0x18004f15c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f163  mov     r9d, 23h ; '#'; int
0x18004f169  mov     dword ptr [rsp+58h+var_28], edi; char
0x18004f16d  mov     qword ptr [rsp+58h+var_30], rbx; __int64
0x18004f172  mov     [rsp+58h+RequiredSize], r15; MessageGuid
0x18004f177  mov     rcx, [rcx+28h]; int
0x18004f17b  call    WPP_RECORDER_SF_Sd
0x18004f180  jmp     short loc_18004F1E0
0x18004f182  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18004f189  xor     edi, edi
0x18004f18b  cmp     rax, r14
0x18004f18e  jz      short loc_18004F1B5
0x18004f190  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f197  lea     r9d, [rdi+24h]; int
0x18004f19b  mov     qword ptr [rsp+58h+var_30], rbx; __int64
0x18004f1a0  mov     [rsp+58h+RequiredSize], r15; MessageGuid
0x18004f1a5  mov     rcx, [rcx+28h]; int
0x18004f1a9  call    WPP_RECORDER_SF_S
0x18004f1ae  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18004f1b5  cmp     [rsp+58h+NeedReboot], edi
0x18004f1b9  jz      short loc_18004F1E0
0x18004f1bb  cmp     rax, r14
0x18004f1be  jz      short loc_18004F1E0
0x18004f1c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f1c7  mov     r9d, 25h ; '%'; int
0x18004f1cd  mov     qword ptr [rsp+58h+var_30], rbx; __int64
0x18004f1d2  mov     [rsp+58h+RequiredSize], r15; MessageGuid
0x18004f1d7  mov     rcx, [rcx+28h]; int
0x18004f1db  call    WPP_RECORDER_SF_S
0x18004f1e0  test    rbx, rbx
0x18004f1e3  jz      short loc_18004F1F9
0x18004f1e5  call    cs:__imp_GetProcessHeap
0x18004f1eb  mov     r8, rbx; lpMem
0x18004f1ee  xor     edx, edx; dwFlags
0x18004f1f0  mov     rcx, rax; hHeap
0x18004f1f3  call    cs:__imp_HeapFree
0x18004f1f9  mov     rbx, [rsp+58h+arg_8]
0x18004f1fe  mov     eax, edi
0x18004f200  mov     rsi, [rsp+58h+arg_10]
0x18004f205  add     rsp, 40h
0x18004f209  pop     r15
0x18004f20b  pop     r14
0x18004f20d  pop     rdi
0x18004f20e  retn
```
