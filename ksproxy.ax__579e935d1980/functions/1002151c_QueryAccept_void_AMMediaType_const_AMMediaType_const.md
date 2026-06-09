# QueryAccept(void *,_AMMediaType const *,_AMMediaType const *)

- ea: `0x1002151c`
- end: `0x100215a7`
- name: `?QueryAccept@@YGJPAXPBU_AMMediaType@@1@Z`
- size: `139`
- prototype: `int __stdcall(void *, const struct _AMMediaType *, const struct _AMMediaType *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x10012030`
- `0x100161b0`

## callees

- `0x1001f3b0`
- `0x1001f6ea`
- `0x1002151c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1002158e`
- `ole32!CoTaskMemFree` at `0x1002158e`

## pseudocode

```c
BOOL __userpurge QueryAccept@<eax>(
        void *a1@<edx>,
        void *a2@<ecx>,
        void *a3,
        const struct _AMMediaType *a4,
        const struct _AMMediaType *a5)
{
  int v7; // esi
  void **v8; // [esp+0h] [ebp-28h]
  GUID InBuffer; // [esp+4h] [ebp-24h] BYREF
  int v10; // [esp+14h] [ebp-14h]
  int v11; // [esp+18h] [ebp-10h]
  DWORD nOutBufferSize; // [esp+1Ch] [ebp-Ch] BYREF
  DWORD BytesReturned; // [esp+20h] [ebp-8h] BYREF
  LPVOID pv; // [esp+24h] [ebp-4h] BYREF

  BytesReturned = 0;
  if ( a1 )
    return a3 != a1;
  if ( InitializeDataFormat(
         0,
         (int)a3,
         (const struct CMediaType *)&pv,
         &nOutBufferSize,
         v8,
         (unsigned int *)InBuffer.Data1) < 0 )
    return 1;
  InBuffer = _GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000;
  v10 = 4;
  v11 = 2;
  v7 = KsSynchronousDeviceControl(a2, 0x2F0003u, &InBuffer, 0x18u, pv, nOutBufferSize, &BytesReturned);
  CoTaskMemFree(pv);
  return v7 < 0;
}

```

## disassembly

```asm
0x1002151c  mov     edi, edi
0x1002151e  push    ebp
0x1002151f  mov     ebp, esp
0x10021521  sub     esp, 24h
0x10021524  mov     [ebp+BytesReturned], 0
0x1002152b  push    ebx; void **
0x1002152c  mov     ebx, ecx
0x1002152e  test    edx, edx
0x10021530  jz      short loc_1002153C
0x10021532  xor     eax, eax
0x10021534  cmp     [ebp+arg_0], edx
0x10021537  setnz   al
0x1002153a  jmp     short loc_100215A2
0x1002153c  mov     ecx, [ebp+arg_0]
0x1002153f  lea     eax, [ebp+nOutBufferSize]
0x10021542  push    eax; unsigned int
0x10021543  lea     eax, [ebp+pv]
0x10021546  xor     edx, edx
0x10021548  push    eax; struct CMediaType *
0x10021549  call    ?InitializeDataFormat@@YGJPBVCMediaType@@KPAPAXPAK@Z; InitializeDataFormat(CMediaType const *,ulong,void * *,ulong *)
0x1002154e  test    eax, eax
0x10021550  js      short loc_1002159F
0x10021552  push    esi
0x10021553  push    edi
0x10021554  mov     esi, offset __GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000
0x10021559  lea     edi, [ebp+InBuffer]
0x1002155c  lea     eax, [ebp+BytesReturned]
0x1002155f  push    eax; lpBytesReturned
0x10021560  push    [ebp+nOutBufferSize]; nOutBufferSize
0x10021563  movsd
0x10021564  lea     eax, [ebp+InBuffer]
0x10021567  push    [ebp+pv]; lpOutBuffer
0x1002156a  push    18h; nInBufferSize
0x1002156c  movsd
0x1002156d  push    eax; lpInBuffer
0x1002156e  push    2F0003h; dwIoControlCode
0x10021573  push    ebx; hDevice
0x10021574  movsd
0x10021575  movsd
0x10021576  mov     [ebp+var_14], 4
0x1002157d  mov     [ebp+var_10], 2
0x10021584  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x10021589  push    [ebp+pv]; pv
0x1002158c  mov     esi, eax
0x1002158e  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10021594  xor     eax, eax
0x10021596  test    esi, esi
0x10021598  pop     edi
0x10021599  sets    al
0x1002159c  pop     esi
0x1002159d  jmp     short loc_100215A2
0x1002159f  xor     eax, eax
0x100215a1  inc     eax
0x100215a2  pop     ebx
0x100215a3  leave
0x100215a4  retn    4
```
