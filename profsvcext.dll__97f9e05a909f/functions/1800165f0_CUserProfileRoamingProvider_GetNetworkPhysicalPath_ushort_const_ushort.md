# CUserProfileRoamingProvider::_GetNetworkPhysicalPath(ushort const *,ushort * *)

- ea: `0x1800165f0`
- end: `0x180016779`
- name: `?_GetNetworkPhysicalPath@CUserProfileRoamingProvider@@AEAAKPEBGPEAPEAG@Z`
- size: `393`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180006774`

## callees

- `0x18000aef8`
- `0x18000ccfc`
- `0x180011454`
- `0x1800165f0`
- `0x18001e580`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016652`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800166d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016652`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800166d0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016663`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800166de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016663`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800166de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016749`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016749`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800166f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800166f1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016637`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016637`
- `ntdll!NtQueryInformationFile` at `0x180016696`
- `ntdll!NtQueryInformationFile` at `0x180016696`
- `ntdll!RtlNtStatusToDosError` at `0x180016730`
- `ntdll!RtlNtStatusToDosError` at `0x180016730`

## pseudocode

```c
__int64 __fastcall CUserProfileRoamingProvider::_GetNetworkPhysicalPath(
        CUserProfileRoamingProvider *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  CUserProfileRoamingProvider *v4; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int *v6; // rax
  unsigned int *v7; // rdi
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rax
  size_t v11; // r15
  HANDLE v12; // rax
  unsigned __int16 *v13; // rax
  DWORD LastError; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-38h] BYREF
  CUserProfileRoamingProvider *FileW; // [rsp+80h] [rbp+8h] BYREF

  FileW = this;
  *a3 = 0;
  FileW = (CUserProfileRoamingProvider *)CreateFileW(a2, 0, 7u, 0, 3u, 0x2000000u, 0);
  v4 = FileW;
  if ( FileW == (CUserProfileRoamingProvider *)-1LL )
  {
    LastError = GetLastError();
  }
  else
  {
    ProcessHeap = GetProcessHeap();
    v6 = (unsigned int *)HeapAlloc(ProcessHeap, 0, 0x10006u);
    v7 = v6;
    if ( v6 )
    {
      IoStatusBlock = 0;
      v8 = NtQueryInformationFile(v4, &IoStatusBlock, v6, 0x10004u, FileNetworkPhysicalNameInformation);
      if ( v8 < 0 )
      {
        LastError = RtlNtStatusToDosError(v8);
      }
      else
      {
        v9 = *v7 >> 1;
        *((_WORD *)v7 + v9 + 2) = 0;
        v10 = (unsigned int)(v9 - 1);
        if ( *((_WORD *)v7 + v10 + 2) == 92 )
          *((_WORD *)v7 + v10 + 2) = 0;
        v11 = *v7 + 4;
        v12 = GetProcessHeap();
        v13 = (unsigned __int16 *)HeapAlloc(v12, 0, (unsigned int)v11);
        if ( v13 )
        {
          *a3 = v13;
          LastError = 0;
          memset_0(v13, 0, v11);
          **a3 = 92;
          memcpy_0(*a3 + 1, v7 + 1, *v7 + 2LL);
        }
        else
        {
          LastError = 8;
          SetLastError(8u);
          *a3 = 0;
        }
      }
      Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v7);
    }
    else
    {
      LastError = 8;
    }
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
  return LastError;
}

```

## disassembly

```asm
0x1800165f0  mov     rax, rsp
0x1800165f3  mov     [rax+10h], rbx
0x1800165f7  mov     [rax+18h], rbp
0x1800165fb  mov     [rax+8], rcx
0x1800165ff  push    rsi
0x180016600  push    rdi
0x180016601  push    r12
0x180016603  push    r14
0x180016605  push    r15
0x180016607  sub     rsp, 50h
0x18001660b  mov     qword ptr [rax-48h], 0
0x180016613  xor     r9d, r9d; lpSecurityAttributes
0x180016616  mov     r14, r8
0x180016619  mov     qword ptr [r8], 0
0x180016620  mov     rcx, rdx; lpFileName
0x180016623  mov     dword ptr [rax-50h], 2000000h
0x18001662a  xor     edx, edx; dwDesiredAccess
0x18001662c  mov     dword ptr [rax-58h], 3
0x180016633  lea     r8d, [r9+7]; dwShareMode
0x180016637  call    cs:__imp_CreateFileW
0x18001663d  mov     [rsp+78h+arg_0], rax
0x180016645  mov     rbx, rax
0x180016648  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001664c  jz      loc_180016749
0x180016652  call    cs:__imp_GetProcessHeap
0x180016658  xor     edx, edx; dwFlags
0x18001665a  mov     r8d, 10006h; dwBytes
0x180016660  mov     rcx, rax; hHeap
0x180016663  call    cs:__imp_HeapAlloc
0x180016669  mov     rdi, rax
0x18001666c  test    rax, rax
0x18001666f  jz      loc_180016742
0x180016675  xorps   xmm0, xmm0
0x180016678  mov     [rsp+78h+FileInformationClass], 31h ; '1'; FileInformationClass
0x180016680  mov     r9d, 10004h; Length
0x180016686  lea     rdx, [rsp+78h+IoStatusBlock]; IoStatusBlock
0x18001668b  mov     r8, rax; FileInformation
0x18001668e  mov     rcx, rbx; FileHandle
0x180016691  movups  xmmword ptr [rsp+78h+IoStatusBlock], xmm0
0x180016696  call    cs:__imp_NtQueryInformationFile
0x18001669c  test    eax, eax
0x18001669e  js      loc_18001672E
0x1800166a4  mov     ecx, [rdi]
0x1800166a6  xor     eax, eax
0x1800166a8  shr     ecx, 1
0x1800166aa  mov     r12d, 5Ch ; '\'
0x1800166b0  mov     [rdi+rcx*2+4], ax
0x1800166b5  lea     eax, [rcx-1]
0x1800166b8  mov     ecx, eax
0x1800166ba  cmp     [rdi+rax*2+4], r12w
0x1800166c0  jnz     short loc_1800166C9
0x1800166c2  xor     eax, eax
0x1800166c4  mov     [rdi+rcx*2+4], ax
0x1800166c9  mov     r15d, [rdi]
0x1800166cc  add     r15d, 4
0x1800166d0  call    cs:__imp_GetProcessHeap
0x1800166d6  mov     r8d, r15d; dwBytes
0x1800166d9  xor     edx, edx; dwFlags
0x1800166db  mov     rcx, rax; hHeap
0x1800166de  call    cs:__imp_HeapAlloc
0x1800166e4  mov     rbp, rax
0x1800166e7  test    rax, rax
0x1800166ea  jnz     short loc_1800166FC
0x1800166ec  lea     ebx, [rax+8]
0x1800166ef  mov     ecx, ebx; dwErrCode
0x1800166f1  call    cs:__imp_SetLastError
0x1800166f7  mov     [r14], rbp
0x1800166fa  jmp     short loc_180016738
0x1800166fc  mov     r8, r15; Size
0x1800166ff  mov     [r14], rbp
0x180016702  xor     edx, edx; Val
0x180016704  mov     rcx, rbp; void *
0x180016707  xor     ebx, ebx
0x180016709  call    memset_0
0x18001670e  mov     rax, [r14]
0x180016711  lea     rdx, [rdi+4]; Src
0x180016715  mov     [rax], r12w
0x180016719  mov     r8d, [rdi]
0x18001671c  mov     rcx, [r14]
0x18001671f  add     r8, 2; Size
0x180016723  add     rcx, 2; void *
0x180016727  call    memcpy_0
0x18001672c  jmp     short loc_180016738
0x18001672e  mov     ecx, eax; Status
0x180016730  call    cs:__imp_RtlNtStatusToDosError
0x180016736  mov     ebx, eax
0x180016738  mov     rcx, rdi
0x18001673b  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180016740  jmp     short loc_180016751
0x180016742  mov     ebx, 8
0x180016747  jmp     short loc_180016751
0x180016749  call    cs:__imp_GetLastError
0x18001674f  mov     ebx, eax
0x180016751  lea     rcx, [rsp+78h+arg_0]
0x180016759  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001675e  lea     r11, [rsp+78h+var_28]
0x180016763  mov     eax, ebx
0x180016765  mov     rbx, [r11+38h]
0x180016769  mov     rbp, [r11+40h]
0x18001676d  mov     rsp, r11
0x180016770  pop     r15
0x180016772  pop     r14
0x180016774  pop     r12
0x180016776  pop     rdi
0x180016777  pop     rsi
0x180016778  retn
```
