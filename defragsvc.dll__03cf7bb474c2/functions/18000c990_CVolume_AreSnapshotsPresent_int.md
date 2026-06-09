# CVolume::AreSnapshotsPresent(int *)

- ea: `0x18000c990`
- end: `0x18000cae1`
- name: `?AreSnapshotsPresent@CVolume@@UEAAJPEAH@Z`
- size: `337`
- prototype: `__int64 __fastcall(CVolume *__hidden this, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18000c990`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c9ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000cab5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c9ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000cab5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ca89`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ca89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ca1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ca1b`

## pseudocode

```c
__int64 __fastcall CVolume::AreSnapshotsPresent(CVolume *this, int *a2)
{
  int v4; // esi
  _WORD *lpOutBuffer; // rbx
  __int16 v6; // ax
  ULONGLONG TickCount64; // rax
  ULONGLONG v8; // rcx
  unsigned int v9; // ebx
  int v11; // [rsp+40h] [rbp-19h] BYREF
  __int16 v12; // [rsp+44h] [rbp-15h]
  __int16 v13; // [rsp+46h] [rbp-13h]
  DWORD BytesReturned; // [rsp+C8h] [rbp+6Fh] BYREF

  v4 = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "CVolume::AreSnapshotsPresent", 2131, 1);
  lpOutBuffer = 0;
  BytesReturned = 0;
  v6 = 2139;
  if ( !a2 )
  {
    v11 = -2147024809;
    goto LABEL_15;
  }
  *a2 = 0;
  v11 = 0;
  v12 = 2139;
  TickCount64 = GetTickCount64();
  v8 = *((_QWORD *)this + 26);
  if ( !v8 || TickCount64 < v8 || TickCount64 - v8 > 0x2710 )
  {
    lpOutBuffer = CoTaskMemAlloc(0x20Cu);
    v6 = 2150;
    if ( lpOutBuffer )
    {
      v11 = 0;
      v12 = 2150;
      if ( (!DeviceIoControl(*((HANDLE *)this + 5), 0x530018u, 0, 0, lpOutBuffer, 0x20Cu, &BytesReturned, 0)
         || !*(_DWORD *)lpOutBuffer
         || !lpOutBuffer[2])
        && GetLastError() != 234 )
      {
        v4 = 0;
      }
      *((_DWORD *)this + 50) = v4;
      *((_QWORD *)this + 26) = GetTickCount64();
      goto LABEL_5;
    }
    v11 = -2147024882;
LABEL_15:
    v13 = v6;
    goto LABEL_6;
  }
LABEL_5:
  *a2 = *((_DWORD *)this + 50);
LABEL_6:
  CoTaskMemFree(lpOutBuffer);
  v9 = v11;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11);
  return v9;
}

```

## disassembly

```asm
0x18000c990  push    rbp
0x18000c992  push    rbx
0x18000c993  push    rsi
0x18000c994  push    rdi
0x18000c995  push    r14
0x18000c997  push    r15
0x18000c999  lea     rbp, [rsp-2Fh]
0x18000c99e  sub     rsp, 88h
0x18000c9a5  mov     r14, rdx
0x18000c9a8  mov     rdi, rcx
0x18000c9ab  mov     esi, 1
0x18000c9b0  mov     r9d, esi; unsigned __int16
0x18000c9b3  mov     r8d, 853h; unsigned __int16
0x18000c9b9  lea     rdx, aCvolumeAresnap; "CVolume::AreSnapshotsPresent"
0x18000c9c0  lea     rcx, [rbp+57h+var_70]; this
0x18000c9c4  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000c9c9  nop
0x18000c9ca  xor     r15d, r15d
0x18000c9cd  mov     ebx, r15d
0x18000c9d0  mov     [rbp+57h+BytesReturned], r15d
0x18000c9d4  mov     eax, 85Bh
0x18000c9d9  test    r14, r14
0x18000c9dc  jz      loc_18000CAD7
0x18000c9e2  mov     [r14], r15d
0x18000c9e5  mov     [rbp+57h+var_70], r15d
0x18000c9e9  mov     [rbp+57h+var_6C], ax
0x18000c9ed  call    cs:__imp_GetTickCount64
0x18000c9f3  mov     rcx, [rdi+0D0h]
0x18000c9fa  test    rcx, rcx
0x18000c9fd  jz      short loc_18000CA3F
0x18000c9ff  cmp     rax, rcx
0x18000ca02  jb      short loc_18000CA3F
0x18000ca04  sub     rax, rcx
0x18000ca07  cmp     rax, 2710h
0x18000ca0d  ja      short loc_18000CA3F
0x18000ca0f  mov     eax, [rdi+0C8h]
0x18000ca15  mov     [r14], eax
0x18000ca18  mov     rcx, rbx; pv
0x18000ca1b  call    cs:__imp_CoTaskMemFree
0x18000ca21  mov     ebx, [rbp+57h+var_70]
0x18000ca24  lea     rcx, [rbp+57h+var_70]; this
0x18000ca28  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000ca2d  mov     eax, ebx
0x18000ca2f  add     rsp, 88h
0x18000ca36  pop     r15
0x18000ca38  pop     r14
0x18000ca3a  pop     rdi
0x18000ca3b  pop     rsi
0x18000ca3c  pop     rbx
0x18000ca3d  pop     rbp
0x18000ca3e  retn
0x18000ca3f  mov     ecx, 20Ch; cb
0x18000ca44  call    cs:__imp_CoTaskMemAlloc
0x18000ca4a  mov     rbx, rax
0x18000ca4d  test    rax, rax
0x18000ca50  mov     eax, 866h
0x18000ca55  jz      short loc_18000CAC7
0x18000ca57  mov     [rbp+57h+var_70], r15d
0x18000ca5b  mov     [rbp+57h+var_6C], ax
0x18000ca5f  mov     [rsp+0B0h+lpOverlapped], r15; lpOverlapped
0x18000ca64  lea     rax, [rbp+57h+BytesReturned]
0x18000ca68  mov     [rsp+0B0h+lpBytesReturned], rax; lpBytesReturned
0x18000ca6d  mov     [rsp+0B0h+nOutBufferSize], 20Ch; nOutBufferSize
0x18000ca75  mov     [rsp+0B0h+lpOutBuffer], rbx; lpOutBuffer
0x18000ca7a  xor     r9d, r9d; nInBufferSize
0x18000ca7d  xor     r8d, r8d; lpInBuffer
0x18000ca80  mov     edx, 530018h; dwIoControlCode
0x18000ca85  mov     rcx, [rdi+28h]; hDevice
0x18000ca89  call    cs:__imp_DeviceIoControl
0x18000ca8f  test    eax, eax
0x18000ca91  jz      short loc_18000CA9F
0x18000ca93  cmp     [rbx], r15d
0x18000ca96  jbe     short loc_18000CA9F
0x18000ca98  cmp     [rbx+4], r15w
0x18000ca9d  jnz     short loc_18000CAAF
0x18000ca9f  call    cs:__imp_GetLastError
0x18000caa5  cmp     eax, 0EAh
0x18000caaa  jz      short loc_18000CAAF
0x18000caac  mov     esi, r15d
0x18000caaf  mov     [rdi+0C8h], esi
0x18000cab5  call    cs:__imp_GetTickCount64
0x18000cabb  mov     [rdi+0D0h], rax
0x18000cac2  jmp     loc_18000CA0F
0x18000cac7  mov     [rbp+57h+var_70], 8007000Eh
0x18000cace  mov     [rbp+57h+var_6A], ax
0x18000cad2  jmp     loc_18000CA18
0x18000cad7  mov     [rbp+57h+var_70], 80070057h
0x18000cade  jmp     short loc_18000CACE
```
