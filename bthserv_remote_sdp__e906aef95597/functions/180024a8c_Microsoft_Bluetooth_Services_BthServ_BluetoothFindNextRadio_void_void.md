# Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)

- ea: `0x180024a8c`
- end: `0x180024c7b`
- name: `?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z`
- size: `495`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ *this, _QWORD *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800247d0`
- `0x180024fc8`
- `0x180025304`
- `0x180027ea8`

## callees

- `0x1800017a0`
- `0x180024a8c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024b4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024bfe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024b4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024bfe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024c12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024c12`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024b64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024bf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024bf0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c49`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024bd6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024bd6`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180024b28`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180024ba3`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180024b28`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180024ba3`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180024aee`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180024aee`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(
        Microsoft::Bluetooth::Services::BthServ *this,
        _QWORD *a2,
        void **a3)
{
  unsigned int v3; // esi
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rcx
  unsigned int v9; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // rax
  WCHAR *v12; // r14
  HANDLE FileW; // rax
  DWORD LastError; // ebx
  HANDLE v15; // rax
  DWORD v16; // ecx
  SIZE_T dwBytes; // [rsp+40h] [rbp-48h] BYREF
  _OWORD v19[2]; // [rsp+48h] [rbp-40h] BYREF

  v3 = 0;
  if ( this )
  {
    while ( 1 )
    {
      v6 = *(unsigned int *)this;
      v7 = *((_QWORD *)this + 1);
      memset(v19, 0, sizeof(v19));
      LODWORD(v19[0]) = 32;
      if ( !(unsigned int)DevObjEnumDeviceInterfaces(v7, 0, &GUID_BTHPORT_DEVICE_INTERFACE, v6, v19) )
        break;
      v8 = *((_QWORD *)this + 1);
      ++*(_DWORD *)this;
      LODWORD(dwBytes) = 0;
      DevObjGetDeviceInterfaceDetail(v8, v19, 0, 0, &dwBytes, 0);
      if ( GetLastError() == 122 )
      {
        v9 = dwBytes;
        ProcessHeap = GetProcessHeap();
        v11 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v9);
        v12 = v11;
        if ( !v11 )
        {
          v16 = 14;
          goto LABEL_14;
        }
        *(_DWORD *)v11 = 8;
        if ( (unsigned int)DevObjGetDeviceInterfaceDetail(
                             *((_QWORD *)this + 1),
                             v19,
                             v11,
                             (unsigned int)dwBytes,
                             &dwBytes,
                             0) )
        {
          FileW = CreateFileW(v12 + 2, 0xC0000000, 3u, 0, 3u, 0, 0);
          if ( FileW != (HANDLE)-1LL )
          {
            *a2 = FileW;
            v3 = 1;
          }
        }
        LastError = GetLastError();
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v12);
        SetLastError(LastError);
      }
      if ( v3 )
        return v3;
    }
    v16 = 259;
  }
  else
  {
    v16 = 6;
  }
LABEL_14:
  SetLastError(v16);
  return v3;
}

```

## disassembly

```asm
0x180024a8c  mov     [rsp+arg_10], rbx
0x180024a91  mov     [rsp+arg_18], rsi
0x180024a96  push    rdi
0x180024a97  push    r14
0x180024a99  push    r15
0x180024a9b  sub     rsp, 70h
0x180024a9f  mov     rax, cs:__security_cookie
0x180024aa6  xor     rax, rsp
0x180024aa9  mov     [rsp+88h+var_20], rax
0x180024aae  xor     esi, esi
0x180024ab0  mov     r15, rdx
0x180024ab3  mov     rdi, rcx
0x180024ab6  test    rcx, rcx
0x180024ab9  jz      loc_180024C44
0x180024abf  mov     r9d, [rdi]
0x180024ac2  lea     rax, [rsp+88h+var_40]
0x180024ac7  mov     rcx, [rdi+8]
0x180024acb  lea     r8, GUID_BTHPORT_DEVICE_INTERFACE
0x180024ad2  xorps   xmm0, xmm0
0x180024ad5  mov     qword ptr [rsp+88h+dwCreationDisposition], rax
0x180024ada  movups  [rsp+88h+var_40], xmm0
0x180024adf  xor     edx, edx
0x180024ae1  mov     dword ptr [rsp+88h+var_40], 20h ; ' '
0x180024ae9  movups  [rsp+88h+var_30], xmm0
0x180024aee  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180024af5  nop     dword ptr [rax+rax+00h]
0x180024afa  test    eax, eax
0x180024afc  jz      loc_180024C3D
0x180024b02  and     [rsp+88h+var_60], 0
0x180024b08  lea     rax, [rsp+88h+dwBytes]
0x180024b0d  mov     rcx, [rdi+8]
0x180024b11  lea     rdx, [rsp+88h+var_40]
0x180024b16  inc     dword ptr [rdi]
0x180024b18  xor     r9d, r9d
0x180024b1b  and     dword ptr [rsp+88h+dwBytes], 0
0x180024b20  xor     r8d, r8d
0x180024b23  mov     qword ptr [rsp+88h+dwCreationDisposition], rax
0x180024b28  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180024b2f  nop     dword ptr [rax+rax+00h]
0x180024b34  call    cs:__imp_GetLastError
0x180024b3b  nop     dword ptr [rax+rax+00h]
0x180024b40  cmp     eax, 7Ah ; 'z'
0x180024b43  jnz     loc_180024C2C
0x180024b49  mov     ebx, dword ptr [rsp+88h+dwBytes]
0x180024b4d  call    cs:__imp_GetProcessHeap
0x180024b54  nop     dword ptr [rax+rax+00h]
0x180024b59  mov     r8d, ebx; dwBytes
0x180024b5c  mov     edx, 8; dwFlags
0x180024b61  mov     rcx, rax; hHeap
0x180024b64  call    cs:__imp_HeapAlloc
0x180024b6b  nop     dword ptr [rax+rax+00h]
0x180024b70  mov     r14, rax
0x180024b73  test    rax, rax
0x180024b76  jz      loc_180024C36
0x180024b7c  and     [rsp+88h+var_60], 0
0x180024b82  lea     rdx, [rsp+88h+var_40]
0x180024b87  mov     dword ptr [rax], 8
0x180024b8d  mov     r8, r14
0x180024b90  mov     r9d, dword ptr [rsp+88h+dwBytes]
0x180024b95  lea     rax, [rsp+88h+dwBytes]
0x180024b9a  mov     rcx, [rdi+8]
0x180024b9e  mov     qword ptr [rsp+88h+dwCreationDisposition], rax
0x180024ba3  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180024baa  nop     dword ptr [rax+rax+00h]
0x180024baf  test    eax, eax
0x180024bb1  jz      short loc_180024BF0
0x180024bb3  and     [rsp+88h+var_58], 0
0x180024bb9  lea     rcx, [r14+4]; lpFileName
0x180024bbd  and     dword ptr [rsp+88h+var_60], 0
0x180024bc2  xor     r9d, r9d; lpSecurityAttributes
0x180024bc5  mov     edx, 0C0000000h; dwDesiredAccess
0x180024bca  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x180024bd2  lea     r8d, [r9+3]; dwShareMode
0x180024bd6  call    cs:__imp_CreateFileW
0x180024bdd  nop     dword ptr [rax+rax+00h]
0x180024be2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024be6  jz      short loc_180024BF0
0x180024be8  mov     [r15], rax
0x180024beb  mov     esi, 1
0x180024bf0  call    cs:__imp_GetLastError
0x180024bf7  nop     dword ptr [rax+rax+00h]
0x180024bfc  mov     ebx, eax
0x180024bfe  call    cs:__imp_GetProcessHeap
0x180024c05  nop     dword ptr [rax+rax+00h]
0x180024c0a  mov     r8, r14; lpMem
0x180024c0d  xor     edx, edx; dwFlags
0x180024c0f  mov     rcx, rax; hHeap
0x180024c12  call    cs:__imp_HeapFree
0x180024c19  nop     dword ptr [rax+rax+00h]
0x180024c1e  mov     ecx, ebx; dwErrCode
0x180024c20  call    cs:__imp_SetLastError
0x180024c27  nop     dword ptr [rax+rax+00h]
0x180024c2c  test    esi, esi
0x180024c2e  jz      loc_180024ABF
0x180024c34  jmp     short loc_180024C55
0x180024c36  mov     ecx, 0Eh
0x180024c3b  jmp     short loc_180024C49
0x180024c3d  mov     ecx, 103h
0x180024c42  jmp     short loc_180024C49
0x180024c44  mov     ecx, 6; dwErrCode
0x180024c49  call    cs:__imp_SetLastError
0x180024c50  nop     dword ptr [rax+rax+00h]
0x180024c55  mov     eax, esi
0x180024c57  mov     rcx, [rsp+88h+var_20]
0x180024c5c  xor     rcx, rsp; StackCookie
0x180024c5f  call    __security_check_cookie
0x180024c64  lea     r11, [rsp+88h+var_18]
0x180024c69  mov     rbx, [r11+30h]
0x180024c6d  mov     rsi, [r11+38h]
0x180024c71  mov     rsp, r11
0x180024c74  pop     r15
0x180024c76  pop     r14
0x180024c78  pop     rdi
0x180024c79  retn
```
