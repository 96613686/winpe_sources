# QueryAccept(void *,_AMMediaType const *,_AMMediaType const *)

- ea: `0x18001ee00`
- end: `0x18001eed2`
- name: `?QueryAccept@@YAJPEAXPEBU_AMMediaType@@1@Z`
- size: `210`
- prototype: `char __fastcall(char *hFile, const struct CMediaType *, const struct CMediaType *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001ed80`
- `0x18001edc0`

## callees

- `0x18000bde0`
- `0x18001bbf8`
- `0x18001ee00`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001eea5`
- `ole32!CoTaskMemFree` at `0x18001eea5`

## pseudocode

```c
char __fastcall QueryAccept(char *hFile, const struct CMediaType *a2, const struct CMediaType *a3)
{
  void *v5; // rdi
  signed int v6; // ebx
  LPVOID pv; // [rsp+40h] [rbp-20h] BYREF
  GUID InBuffer; // [rsp+48h] [rbp-18h] BYREF
  __int64 v9; // [rsp+58h] [rbp-8h]
  DWORD v10; // [rsp+78h] [rbp+18h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+88h] [rbp+28h] BYREF

  pv = 0;
  v9 = 0;
  NumberOfBytesTransferred = 0;
  v10 = 0;
  InBuffer = 0;
  if ( a2 )
    return a3 != a2;
  if ( (int)InitializeDataFormat(a3, 0, &pv, &v10) < 0 )
    return 1;
  v5 = pv;
  InBuffer = GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000;
  v9 = 0x200000004LL;
  v6 = KsSynchronousDeviceControl(hFile, 0x2F0003u, &InBuffer, 0x18u, pv, v10, &NumberOfBytesTransferred);
  CoTaskMemFree(v5);
  return v6 < 0;
}

```

## disassembly

```asm
0x18001ee00  mov     [rsp-8+arg_0], rbx
0x18001ee05  mov     [rsp-8+arg_10], rdi
0x18001ee0a  push    rbp
0x18001ee0b  mov     rbp, rsp
0x18001ee0e  sub     rsp, 60h
0x18001ee12  xor     eax, eax
0x18001ee14  mov     [rbp+pv], 0
0x18001ee1c  mov     [rbp+var_8], rax
0x18001ee20  xorps   xmm0, xmm0
0x18001ee23  mov     [rbp+NumberOfBytesTransferred], eax
0x18001ee26  mov     r10, r8
0x18001ee29  mov     [rbp+arg_8], eax
0x18001ee2c  mov     rbx, rcx
0x18001ee2f  movups  [rbp+InBuffer], xmm0
0x18001ee33  test    rdx, rdx
0x18001ee36  jz      short loc_18001EE40
0x18001ee38  cmp     r8, rdx
0x18001ee3b  setnz   al
0x18001ee3e  jmp     short loc_18001EEBF
0x18001ee40  lea     r9, [rbp+arg_8]; unsigned int *
0x18001ee44  xor     edx, edx; unsigned int
0x18001ee46  lea     r8, [rbp+pv]; void **
0x18001ee4a  mov     rcx, r10; struct CMediaType *
0x18001ee4d  call    ?InitializeDataFormat@@YAJPEBVCMediaType@@KPEAPEAXPEAK@Z; InitializeDataFormat(CMediaType const *,ulong,void * *,ulong *)
0x18001ee52  test    eax, eax
0x18001ee54  js      short loc_18001EEBA
0x18001ee56  movups  xmm0, xmmword ptr cs:_GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000.Data1
0x18001ee5d  mov     rdi, [rbp+pv]
0x18001ee61  lea     rax, [rbp+NumberOfBytesTransferred]
0x18001ee65  mov     [rsp+60h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18001ee6a  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18001ee6e  mov     eax, [rbp+arg_8]
0x18001ee71  mov     r9d, 18h; nInBufferSize
0x18001ee77  mov     [rsp+60h+var_38], eax; DWORD
0x18001ee7b  mov     edx, 2F0003h; dwIoControlCode
0x18001ee80  mov     rcx, rbx; hFile
0x18001ee83  mov     [rsp+60h+var_40], rdi; LPVOID
0x18001ee88  movdqu  [rbp+InBuffer], xmm0
0x18001ee8d  mov     dword ptr [rbp+var_8], 4
0x18001ee94  mov     dword ptr [rbp+var_8+4], 2
0x18001ee9b  call    KsSynchronousDeviceControl
0x18001eea0  mov     rcx, rdi; pv
0x18001eea3  mov     ebx, eax
0x18001eea5  call    cs:__imp_CoTaskMemFree
0x18001eeac  nop     dword ptr [rax+rax+00h]
0x18001eeb1  xor     eax, eax
0x18001eeb3  test    ebx, ebx
0x18001eeb5  sets    al
0x18001eeb8  jmp     short loc_18001EEBF
0x18001eeba  mov     eax, 1
0x18001eebf  lea     r11, [rsp+60h+var_s0]
0x18001eec4  mov     rbx, [r11+10h]
0x18001eec8  mov     rdi, [r11+20h]
0x18001eecc  mov     rsp, r11
0x18001eecf  pop     rbp
0x18001eed0  retn
```
