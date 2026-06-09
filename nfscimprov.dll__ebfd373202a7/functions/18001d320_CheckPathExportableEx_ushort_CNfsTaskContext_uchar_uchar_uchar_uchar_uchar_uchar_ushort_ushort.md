# CheckPathExportableEx(ushort *,CNfsTaskContext *,uchar *,uchar *,uchar *,uchar *,uchar *,uchar *,ushort *,ushort * *)

- ea: `0x18001d320`
- end: `0x18001d4c0`
- name: `?CheckPathExportableEx@@YAKPEAGPEAVCNfsTaskContext@@PEAE222220PEAPEAG@Z`
- size: `416`
- prototype: `unsigned int __usercall@<eax>(unsigned __int16 *@<rcx>, struct CNfsTaskContext *@<rdx>, unsigned __int8 *@<r8>, unsigned __int8 *@<r9>, DWORD pdwValue, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ddd4`
- `0x18001d798`

## callees

- `0x18000219c`
- `0x18001d320`
- `0x1800210b4`
- `0x1800219fc`
- `0x18002c874`
- `0x180037010`

## import_xrefs

- `ext-ms-win-security-slc-l1-1-0!SLGetWindowsInformationDWORD` at `0x18001d495`
- `ext-ms-win-security-slc-l1-1-0!SLGetWindowsInformationDWORD` at `0x18001d495`

## pseudocode

```c
__int64 __fastcall CheckPathExportableEx(
        unsigned __int16 *a1,
        struct CNfsTaskContext *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        _BYTE *pdwValue,
        unsigned __int8 *a6,
        unsigned __int8 *a7,
        unsigned __int8 *a8,
        unsigned __int16 *a9,
        unsigned __int16 **a10)
{
  unsigned __int16 *v13; // rdi
  HRESULT v14; // ecx
  unsigned int v15; // edx
  unsigned int ErrorFromHr; // ebx
  unsigned int v17; // eax
  unsigned __int8 v18; // cl
  unsigned __int8 v19; // al
  unsigned __int8 v20; // al
  char v21; // dl
  unsigned __int8 v22; // dl
  unsigned __int8 v23; // al
  unsigned __int8 *v24; // rsi
  unsigned __int8 v25; // cl
  unsigned __int16 v26; // cx
  bool v27; // al
  unsigned int v29; // [rsp+70h] [rbp+30h] BYREF
  __int64 v30; // [rsp+80h] [rbp+40h] BYREF
  size_t pcchLength; // [rsp+88h] [rbp+48h] BYREF

  v30 = 0;
  v29 = 0;
  pcchLength = 0;
  v13 = a1;
  if ( a1 )
    v14 = StringLengthWorkerW(a1, 0x7FFFu, &pcchLength);
  else
    v14 = -2147024809;
  ErrorFromHr = NfsGetErrorFromHr(v14);
  if ( ErrorFromHr )
  {
LABEL_8:
    v18 = BYTE4(v30);
    v19 = 0;
    goto LABEL_9;
  }
  v17 = NfsDeviceIoControl(L"\\\\.\\NfsSvr", 0x80000000, 0x100004D4u, v13, v15, &v30, 8u, &v29);
  ErrorFromHr = v17;
  if ( v17 )
  {
    if ( v17 == 1005 )
      (*(void (__fastcall **)(struct CNfsTaskContext *, __int64))(*(_QWORD *)a2 + 88LL))(a2, 2147483654LL);
    goto LABEL_8;
  }
  v18 = BYTE4(v30);
  if ( BYTE4(v30) )
    v13 += 2;
  v19 = v30;
LABEL_9:
  *a3 = v19;
  if ( ErrorFromHr )
    v20 = 0;
  else
    v20 = BYTE1(v30);
  *a4 = v20;
  if ( ErrorFromHr )
    v21 = 0;
  else
    v21 = BYTE2(v30);
  *pdwValue = v21;
  if ( ErrorFromHr )
    v22 = 0;
  else
    v22 = BYTE3(v30);
  *a6 = v22;
  if ( ErrorFromHr )
    v23 = 0;
  else
    v23 = v18;
  v24 = a7;
  *a7 = v23;
  if ( ErrorFromHr )
    v25 = 0;
  else
    v25 = BYTE5(v30);
  *a8 = v25;
  if ( ErrorFromHr )
    v26 = 0;
  else
    v26 = HIWORD(v30);
  *a9 = v26;
  if ( ErrorFromHr )
    v13 = 0;
  *a10 = v13;
  v27 = 0;
  if ( *v24 )
  {
    if ( (LODWORD(pdwValue) = 0, (unsigned __int8)IsSLGetWindowsInformationDWORDPresent())
      && SLGetWindowsInformationDWORD(L"nfs-server-databox-disabled", (DWORD *)&pdwValue) < 0
      || !(_DWORD)pdwValue )
    {
      v27 = 1;
    }
  }
  *v24 = v27;
  return ErrorFromHr;
}

```

## disassembly

```asm
0x18001d320  mov     [rsp-28h+arg_8], rbx
0x18001d325  push    rbp
0x18001d326  push    rsi
0x18001d327  push    rdi
0x18001d328  push    r14
0x18001d32a  push    r15
0x18001d32c  mov     rbp, rsp
0x18001d32f  sub     rsp, 40h
0x18001d333  mov     [rbp+arg_10], 0
0x18001d33b  mov     r15, r9
0x18001d33e  mov     [rbp+arg_0], 0
0x18001d345  mov     r14, r8
0x18001d348  mov     [rbp+pcchLength], 0
0x18001d350  mov     rsi, rdx
0x18001d353  mov     rdi, rcx
0x18001d356  test    rcx, rcx
0x18001d359  jz      short loc_18001D379
0x18001d35b  lea     r8, [rbp+pcchLength]; pcchLength
0x18001d35f  mov     edx, 7FFFh; cchMax
0x18001d364  call    StringLengthWorkerW
0x18001d369  mov     ecx, eax
0x18001d36b  test    eax, eax
0x18001d36d  js      short loc_18001D37E
0x18001d36f  mov     rax, [rbp+pcchLength]
0x18001d373  lea     rdx, [rax+rax]
0x18001d377  jmp     short loc_18001D380
0x18001d379  mov     ecx, 80070057h; int
0x18001d37e  xor     edx, edx
0x18001d380  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x18001d385  mov     ebx, eax
0x18001d387  test    eax, eax
0x18001d389  jnz     short loc_18001D3E4
0x18001d38b  lea     rax, [rbp+arg_0]
0x18001d38f  mov     r9, rdi; void *
0x18001d392  mov     [rsp+40h+var_8], rax; unsigned int *
0x18001d397  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x18001d39e  lea     rax, [rbp+arg_10]
0x18001d3a2  mov     [rsp+40h+var_10], 8; unsigned int
0x18001d3aa  mov     [rsp+40h+var_18], rax; void *
0x18001d3af  mov     r8d, 100004D4h; unsigned int
0x18001d3b5  mov     [rsp+40h+var_20], edx; unsigned int
0x18001d3b9  mov     edx, 80000000h; unsigned int
0x18001d3be  call    ?NfsDeviceIoControl@@YAKPEBGKKPEAXK1KPEAK@Z; NfsDeviceIoControl(ushort const *,ulong,ulong,void *,ulong,void *,ulong,ulong *)
0x18001d3c3  mov     ebx, eax
0x18001d3c5  test    eax, eax
0x18001d3c7  jz      short loc_18001D3F6
0x18001d3c9  cmp     eax, 3EDh
0x18001d3ce  jnz     short loc_18001D3E4
0x18001d3d0  mov     rcx, [rsi]
0x18001d3d3  mov     edx, 80000006h
0x18001d3d8  mov     rax, [rcx+58h]
0x18001d3dc  mov     rcx, rsi
0x18001d3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3e4  mov     cl, byte ptr [rbp+arg_10+4]
0x18001d3e7  xor     eax, eax
0x18001d3e9  mov     [r14], al
0x18001d3ec  test    ebx, ebx
0x18001d3ee  jnz     short loc_18001D407
0x18001d3f0  movzx   eax, byte ptr [rbp+arg_10+1]
0x18001d3f4  jmp     short loc_18001D409
0x18001d3f6  mov     cl, byte ptr [rbp+arg_10+4]
0x18001d3f9  test    cl, cl
0x18001d3fb  jz      short loc_18001D401
0x18001d3fd  add     rdi, 4
0x18001d401  movzx   eax, byte ptr [rbp+arg_10]
0x18001d405  jmp     short loc_18001D3E9
0x18001d407  xor     eax, eax
0x18001d409  mov     [r15], al
0x18001d40c  test    ebx, ebx
0x18001d40e  jnz     short loc_18001D416
0x18001d410  movzx   edx, byte ptr [rbp+arg_10+2]
0x18001d414  jmp     short loc_18001D418
0x18001d416  xor     edx, edx
0x18001d418  mov     rax, [rbp+pdwValue]
0x18001d41c  mov     [rax], dl
0x18001d41e  test    ebx, ebx
0x18001d420  jnz     short loc_18001D428
0x18001d422  movzx   edx, byte ptr [rbp+arg_10+3]
0x18001d426  jmp     short loc_18001D42A
0x18001d428  xor     edx, edx
0x18001d42a  mov     rax, [rbp+arg_28]
0x18001d42e  mov     [rax], dl
0x18001d430  test    ebx, ebx
0x18001d432  jnz     short loc_18001D439
0x18001d434  movzx   eax, cl
0x18001d437  jmp     short loc_18001D43B
0x18001d439  xor     eax, eax
0x18001d43b  mov     rsi, [rbp+arg_30]
0x18001d43f  mov     [rsi], al
0x18001d441  test    ebx, ebx
0x18001d443  jnz     short loc_18001D44B
0x18001d445  movzx   ecx, byte ptr [rbp+arg_10+5]
0x18001d449  jmp     short loc_18001D44D
0x18001d44b  xor     ecx, ecx
0x18001d44d  mov     rax, [rbp+arg_38]
0x18001d451  mov     [rax], cl
0x18001d453  test    ebx, ebx
0x18001d455  jnz     short loc_18001D45D
0x18001d457  movzx   ecx, word ptr [rbp+arg_10+6]
0x18001d45b  jmp     short loc_18001D45F
0x18001d45d  xor     ecx, ecx
0x18001d45f  mov     rax, [rbp+arg_40]
0x18001d463  mov     [rax], cx
0x18001d466  xor     eax, eax
0x18001d468  test    ebx, ebx
0x18001d46a  cmovnz  rdi, rax
0x18001d46e  mov     rax, [rbp+arg_48]
0x18001d472  mov     [rax], rdi
0x18001d475  cmp     byte ptr [rsi], 0
0x18001d478  jz      short loc_18001D4A9
0x18001d47a  mov     dword ptr [rbp+pdwValue], 0
0x18001d481  call    IsSLGetWindowsInformationDWORDPresent
0x18001d486  test    al, al
0x18001d488  jz      short loc_18001D49F
0x18001d48a  lea     rdx, [rbp+pdwValue]; pdwValue
0x18001d48e  lea     rcx, pwszValueName; "nfs-server-databox-disabled"
0x18001d495  call    cs:__imp_SLGetWindowsInformationDWORD
0x18001d49b  test    eax, eax
0x18001d49d  js      short loc_18001D4A5
0x18001d49f  cmp     dword ptr [rbp+pdwValue], 0
0x18001d4a3  jnz     short loc_18001D4A9
0x18001d4a5  mov     al, 1
0x18001d4a7  jmp     short loc_18001D4AB
0x18001d4a9  xor     eax, eax
0x18001d4ab  mov     [rsi], al
0x18001d4ad  mov     eax, ebx
0x18001d4af  mov     rbx, [rsp+40h+arg_8]
0x18001d4b4  add     rsp, 40h
0x18001d4b8  pop     r15
0x18001d4ba  pop     r14
0x18001d4bc  pop     rdi
0x18001d4bd  pop     rsi
0x18001d4be  pop     rbp
0x18001d4bf  retn
```
