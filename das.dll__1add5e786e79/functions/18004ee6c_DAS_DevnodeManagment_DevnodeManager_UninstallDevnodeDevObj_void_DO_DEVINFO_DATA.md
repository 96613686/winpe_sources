# DAS::DevnodeManagment::DevnodeManager::UninstallDevnodeDevObj(void *,_DO_DEVINFO_DATA *)

- ea: `0x18004ee6c`
- end: `0x18004f02b`
- name: `?UninstallDevnodeDevObj@DevnodeManager@DevnodeManagment@DAS@@AEAAKPEAXPEAU_DO_DEVINFO_DATA@@@Z`
- size: `447`
- prototype: `unsigned int __fastcall(DAS::DevnodeManagment::DevnodeManager *__hidden this, void *, struct _DO_DEVINFO_DATA *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180028064`

## callees

- `0x180007500`
- `0x18004b700`
- `0x18004ee6c`
- `0x18004fea4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004eeb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f001`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004eeb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f001`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f00f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f00f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004eec5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004eec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eefe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ef3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eefe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ef3b`
- `DEVOBJ!DevObjUninstallDevice` at `0x18004ef31`
- `DEVOBJ!DevObjUninstallDevice` at `0x18004ef31`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18004eeeb`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18004eeeb`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::DevnodeManager::UninstallDevnodeDevObj(
        DAS::DevnodeManagment::DevnodeManager *this,
        void *a2,
        struct _DO_DEVINFO_DATA *a3)
{
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v7; // rax
  char LastError; // al
  int v9; // edx
  int v10; // r8d
  int v11; // edx
  int v12; // r8d
  DWORD v13; // eax
  int v14; // edx
  int v15; // r8d
  int v16; // r9d
  DWORD v17; // edi
  int *v18; // rax
  HANDLE v19; // rax
  int MessageGuid; // [rsp+20h] [rbp-38h]
  int v22; // [rsp+60h] [rbp+8h] BYREF
  int v23; // [rsp+64h] [rbp+Ch]

  v23 = HIDWORD(this);
  v22 = 0;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u || (v5 = 0, *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u) )
  {
    ProcessHeap = GetProcessHeap();
    v7 = HeapAlloc(ProcessHeap, 0, 0x190u);
    v5 = v7;
    if ( v7 )
    {
      MessageGuid = 0;
      if ( !(unsigned int)DevObjGetDeviceInstanceId(a2, a3, v7, 200)
        && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LastError = GetLastError();
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v9,
          v10,
          22,
          &WPP_416e81a390623384018c9851ffc16906_Traceguids,
          LastError);
      }
    }
  }
  if ( (unsigned int)DevObjUninstallDevice(a2, a3, 0, &v22) )
  {
    v18 = *(int **)&WPP_RECORDER_INITIALIZED;
    v17 = 0;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v11,
        v12,
        25,
        &WPP_416e81a390623384018c9851ffc16906_Traceguids,
        (__int64)v5);
      v18 = *(int **)&WPP_RECORDER_INITIALIZED;
    }
    if ( v22 && v18 != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v11,
        v12,
        26,
        &WPP_416e81a390623384018c9851ffc16906_Traceguids,
        (__int64)v5);
  }
  else
  {
    v13 = GetLastError();
    v17 = v13;
    if ( v13 == -536870389 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v14,
          v15,
          23,
          &WPP_416e81a390623384018c9851ffc16906_Traceguids,
          (__int64)v5);
      v17 = 0;
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 5), v14, v15, v16, MessageGuid, (__int64)v5, v13);
    }
  }
  if ( v5 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v5);
  }
  return v17;
}

```

## disassembly

```asm
0x18004ee6c  mov     rax, rsp
0x18004ee6f  mov     [rax+10h], rbx
0x18004ee73  mov     [rax+18h], rsi
0x18004ee77  mov     [rax+8], rcx
0x18004ee7b  push    rdi
0x18004ee7c  push    r14
0x18004ee7e  push    r15
0x18004ee80  sub     rsp, 40h
0x18004ee84  mov     dword ptr [rax+8], 0
0x18004ee8b  lea     r15, WPP_416e81a390623384018c9851ffc16906_Traceguids
0x18004ee92  mov     rax, cs:WPP_GLOBAL_Control
0x18004ee99  lea     r14, WPP_RECORDER_INITIALIZED
0x18004eea0  mov     rdi, r8
0x18004eea3  mov     rsi, rdx
0x18004eea6  cmp     byte ptr [rax+19h], 4
0x18004eeaa  jnb     short loc_18004EEB4
0x18004eeac  xor     ebx, ebx
0x18004eeae  cmp     byte ptr [rax+19h], 2
0x18004eeb2  jb      short loc_18004EF23
0x18004eeb4  call    cs:__imp_GetProcessHeap
0x18004eeba  xor     edx, edx; dwFlags
0x18004eebc  mov     r8d, 190h; dwBytes
0x18004eec2  mov     rcx, rax; hHeap
0x18004eec5  call    cs:__imp_HeapAlloc
0x18004eecb  mov     rbx, rax
0x18004eece  test    rax, rax
0x18004eed1  jz      short loc_18004EF23
0x18004eed3  mov     r9d, 0C8h
0x18004eed9  mov     [rsp+58h+MessageGuid], 0
0x18004eee2  mov     r8, rax
0x18004eee5  mov     rdx, rdi
0x18004eee8  mov     rcx, rsi
0x18004eeeb  call    cs:__imp_DevObjGetDeviceInstanceId
0x18004eef1  test    eax, eax
0x18004eef3  jnz     short loc_18004EF23
0x18004eef5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18004eefc  jz      short loc_18004EF23
0x18004eefe  call    cs:__imp_GetLastError
0x18004ef04  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef0b  mov     r9d, 16h; int
0x18004ef11  mov     dword ptr [rsp+58h+var_30], eax; char
0x18004ef15  mov     [rsp+58h+MessageGuid], r15; MessageGuid
0x18004ef1a  mov     rcx, [rcx+28h]; int
0x18004ef1e  call    WPP_RECORDER_SF_D
0x18004ef23  lea     r9, [rsp+58h+arg_0]
0x18004ef28  xor     r8d, r8d
0x18004ef2b  mov     rdx, rdi
0x18004ef2e  mov     rcx, rsi
0x18004ef31  call    cs:__imp_DevObjUninstallDevice
0x18004ef37  test    eax, eax
0x18004ef39  jnz     short loc_18004EF9E
0x18004ef3b  call    cs:__imp_GetLastError
0x18004ef41  mov     edi, eax
0x18004ef43  cmp     eax, 0E000020Bh
0x18004ef48  jnz     short loc_18004EF7A
0x18004ef4a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18004ef51  jz      short loc_18004EF73
0x18004ef53  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef5a  mov     r9d, 17h; int
0x18004ef60  mov     qword ptr [rsp+58h+var_30], rbx; __int64
0x18004ef65  mov     [rsp+58h+MessageGuid], r15; MessageGuid
0x18004ef6a  mov     rcx, [rcx+28h]; int
0x18004ef6e  call    WPP_RECORDER_SF_s
0x18004ef73  xor     edi, edi
0x18004ef75  jmp     loc_18004EFFC
0x18004ef7a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18004ef81  jz      short loc_18004EFFC
0x18004ef83  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef8a  mov     [rsp+58h+var_28], eax
0x18004ef8e  mov     qword ptr [rsp+58h+var_30], rbx
0x18004ef93  mov     rcx, [rcx+28h]
0x18004ef97  call    WPP_RECORDER_SF_sD
0x18004ef9c  jmp     short loc_18004EFFC
0x18004ef9e  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18004efa5  xor     edi, edi
0x18004efa7  cmp     rax, r14
0x18004efaa  jz      short loc_18004EFD1
0x18004efac  mov     rcx, cs:WPP_GLOBAL_Control
0x18004efb3  lea     r9d, [rdi+19h]; int
0x18004efb7  mov     qword ptr [rsp+58h+var_30], rbx; __int64
0x18004efbc  mov     [rsp+58h+MessageGuid], r15; MessageGuid
0x18004efc1  mov     rcx, [rcx+28h]; int
0x18004efc5  call    WPP_RECORDER_SF_s
0x18004efca  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18004efd1  cmp     [rsp+58h+arg_0], edi
0x18004efd5  jz      short loc_18004EFFC
0x18004efd7  cmp     rax, r14
0x18004efda  jz      short loc_18004EFFC
0x18004efdc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004efe3  mov     r9d, 1Ah; int
0x18004efe9  mov     qword ptr [rsp+58h+var_30], rbx; __int64
0x18004efee  mov     [rsp+58h+MessageGuid], r15; MessageGuid
0x18004eff3  mov     rcx, [rcx+28h]; int
0x18004eff7  call    WPP_RECORDER_SF_s
0x18004effc  test    rbx, rbx
0x18004efff  jz      short loc_18004F015
0x18004f001  call    cs:__imp_GetProcessHeap
0x18004f007  mov     r8, rbx; lpMem
0x18004f00a  xor     edx, edx; dwFlags
0x18004f00c  mov     rcx, rax; hHeap
0x18004f00f  call    cs:__imp_HeapFree
0x18004f015  mov     rbx, [rsp+58h+arg_8]
0x18004f01a  mov     eax, edi
0x18004f01c  mov     rsi, [rsp+58h+arg_10]
0x18004f021  add     rsp, 40h
0x18004f025  pop     r15
0x18004f027  pop     r14
0x18004f029  pop     rdi
0x18004f02a  retn
```
