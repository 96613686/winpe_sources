# SetMediaType(void *,CMediaType const *)

- ea: `0x1001f846`
- end: `0x1001f8b3`
- name: `?SetMediaType@@YGJPAXPBVCMediaType@@@Z`
- size: `109`
- prototype: `int __cdecl(void *, const struct CMediaType *)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x10012330`
- `0x100163d0`
- `0x10017097`
- `0x1001b660`

## callees

- `0x1001f3b0`
- `0x1001f6ea`
- `0x1001f846`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1001f8a6`
- `ole32!CoTaskMemFree` at `0x1001f8a6`

## pseudocode

```c
int __fastcall SetMediaType(void *a1, int a2)
{
  int result; // eax
  int v4; // esi
  void **v5; // [esp+0h] [ebp-38h]
  unsigned int *v6; // [esp+4h] [ebp-34h]
  GUID InBuffer; // [esp+10h] [ebp-28h] BYREF
  int v8; // [esp+20h] [ebp-18h]
  int v9; // [esp+24h] [ebp-14h]
  DWORD nOutBufferSize; // [esp+2Ch] [ebp-Ch] BYREF
  DWORD BytesReturned; // [esp+30h] [ebp-8h] BYREF
  LPVOID pv; // [esp+34h] [ebp-4h] BYREF

  BytesReturned = 0;
  result = InitializeDataFormat(0, a2, (const struct CMediaType *)&pv, &nOutBufferSize, v5, v6);
  if ( result >= 0 )
  {
    InBuffer = _GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000;
    v8 = 2;
    v9 = 2;
    v4 = KsSynchronousDeviceControl(a1, 0x2F0003u, &InBuffer, 0x18u, pv, nOutBufferSize, &BytesReturned);
    CoTaskMemFree(pv);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x1001f846  mov     edi, edi
0x1001f848  push    ebp
0x1001f849  mov     ebp, esp
0x1001f84b  sub     esp, 2Ch
0x1001f84e  push    ebx
0x1001f84f  push    esi; unsigned int *
0x1001f850  mov     ebx, ecx
0x1001f852  mov     [ebp+BytesReturned], 0
0x1001f859  push    edi; void **
0x1001f85a  lea     ecx, [ebp+nOutBufferSize]
0x1001f85d  mov     eax, edx
0x1001f85f  push    ecx; unsigned int
0x1001f860  lea     ecx, [ebp+pv]
0x1001f863  xor     edx, edx
0x1001f865  push    ecx; struct CMediaType *
0x1001f866  mov     ecx, eax
0x1001f868  call    ?InitializeDataFormat@@YGJPBVCMediaType@@KPAPAXPAK@Z; InitializeDataFormat(CMediaType const *,ulong,void * *,ulong *)
0x1001f86d  test    eax, eax
0x1001f86f  js      short loc_1001F8AE
0x1001f871  mov     esi, offset __GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000
0x1001f876  lea     edi, [ebp+InBuffer]
0x1001f879  push    2
0x1001f87b  pop     eax
0x1001f87c  movsd
0x1001f87d  movsd
0x1001f87e  movsd
0x1001f87f  movsd
0x1001f880  mov     [ebp+var_18], eax
0x1001f883  mov     [ebp+var_14], eax
0x1001f886  lea     eax, [ebp+BytesReturned]
0x1001f889  push    eax; lpBytesReturned
0x1001f88a  push    [ebp+nOutBufferSize]; nOutBufferSize
0x1001f88d  lea     eax, [ebp+InBuffer]
0x1001f890  push    [ebp+pv]; lpOutBuffer
0x1001f893  push    18h; nInBufferSize
0x1001f895  push    eax; lpInBuffer
0x1001f896  push    2F0003h; dwIoControlCode
0x1001f89b  push    ebx; hDevice
0x1001f89c  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x1001f8a1  push    [ebp+pv]; pv
0x1001f8a4  mov     esi, eax
0x1001f8a6  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001f8ac  mov     eax, esi
0x1001f8ae  pop     edi
0x1001f8af  pop     esi
0x1001f8b0  pop     ebx
0x1001f8b1  leave
0x1001f8b2  retn
```
