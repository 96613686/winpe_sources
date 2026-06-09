# SetMediaType(void *,CMediaType const *)

- ea: `0x18001bb40`
- end: `0x18001bbf0`
- name: `?SetMediaType@@YAJPEAXPEBVCMediaType@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(char *hFile, const struct CMediaType *)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003e50`
- `0x1800192a0`
- `0x180028e20`
- `0x1800315e0`

## callees

- `0x18000bde0`
- `0x18001bb40`
- `0x18001bbf8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001bbd1`
- `ole32!CoTaskMemFree` at `0x18001bbd1`

## pseudocode

```c
__int64 __fastcall SetMediaType(char *hFile, const struct CMediaType *a2)
{
  __int64 result; // rax
  void *v4; // rdi
  unsigned int v5; // ebx
  LPVOID pv; // [rsp+40h] [rbp-20h] BYREF
  GUID InBuffer; // [rsp+48h] [rbp-18h] BYREF
  __int64 v8; // [rsp+58h] [rbp-8h]
  DWORD v9; // [rsp+80h] [rbp+20h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+88h] [rbp+28h] BYREF

  v8 = 0;
  pv = 0;
  NumberOfBytesTransferred = 0;
  InBuffer = 0;
  v9 = 0;
  result = InitializeDataFormat(a2, 0, &pv, &v9);
  if ( (int)result >= 0 )
  {
    v4 = pv;
    v8 = 0x200000002LL;
    InBuffer = GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000;
    v5 = KsSynchronousDeviceControl(hFile, 0x2F0003u, &InBuffer, 0x18u, pv, v9, &NumberOfBytesTransferred);
    CoTaskMemFree(v4);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18001bb40  mov     [rsp-8+arg_0], rbx
0x18001bb45  mov     [rsp-8+arg_8], rdi
0x18001bb4a  push    rbp
0x18001bb4b  mov     rbp, rsp
0x18001bb4e  sub     rsp, 60h
0x18001bb52  mov     rbx, rcx
0x18001bb55  lea     r9, [rbp+arg_10]; unsigned int *
0x18001bb59  xor     ecx, ecx
0x18001bb5b  lea     r8, [rbp+pv]; void **
0x18001bb5f  mov     rax, rdx
0x18001bb62  mov     [rbp+var_8], rcx
0x18001bb66  xor     edi, edi
0x18001bb68  xorps   xmm0, xmm0
0x18001bb6b  mov     rcx, rax; struct CMediaType *
0x18001bb6e  mov     [rbp+pv], rdi
0x18001bb72  xor     edx, edx; unsigned int
0x18001bb74  mov     [rbp+NumberOfBytesTransferred], edi
0x18001bb77  movups  [rbp+InBuffer], xmm0
0x18001bb7b  mov     [rbp+arg_10], edi
0x18001bb7e  call    ?InitializeDataFormat@@YAJPEBVCMediaType@@KPEAPEAXPEAK@Z; InitializeDataFormat(CMediaType const *,ulong,void * *,ulong *)
0x18001bb83  test    eax, eax
0x18001bb85  js      short loc_18001BBDF
0x18001bb87  movups  xmm0, xmmword ptr cs:_GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000.Data1
0x18001bb8e  lea     eax, [rdi+2]
0x18001bb91  mov     r9d, 18h; nInBufferSize
0x18001bb97  mov     rdi, [rbp+pv]
0x18001bb9b  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18001bb9f  mov     dword ptr [rbp+var_8], eax
0x18001bba2  mov     edx, 2F0003h; dwIoControlCode
0x18001bba7  mov     dword ptr [rbp+var_8+4], eax
0x18001bbaa  mov     rcx, rbx; hFile
0x18001bbad  lea     rax, [rbp+NumberOfBytesTransferred]
0x18001bbb1  mov     [rsp+60h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18001bbb6  mov     eax, [rbp+arg_10]
0x18001bbb9  mov     [rsp+60h+var_38], eax; DWORD
0x18001bbbd  mov     [rsp+60h+var_40], rdi; LPVOID
0x18001bbc2  movdqu  [rbp+InBuffer], xmm0
0x18001bbc7  call    KsSynchronousDeviceControl
0x18001bbcc  mov     rcx, rdi; pv
0x18001bbcf  mov     ebx, eax
0x18001bbd1  call    cs:__imp_CoTaskMemFree
0x18001bbd8  nop     dword ptr [rax+rax+00h]
0x18001bbdd  mov     eax, ebx
0x18001bbdf  mov     rbx, [rsp+60h+arg_0]
0x18001bbe4  mov     rdi, [rsp+60h+arg_8]
0x18001bbe9  add     rsp, 60h
0x18001bbed  pop     rbp
0x18001bbee  retn
```
