# CSystemWriter::AddLegacyDriver(ushort *,IVssCreateWriterMetadata *,void *,SC_HANDLE__ *)

- ea: `0x180007898`
- end: `0x180007961`
- name: `?AddLegacyDriver@CSystemWriter@@AEAA_NPEAGPEAVIVssCreateWriterMetadata@@PEAXPEAUSC_HANDLE__@@@Z`
- size: `201`
- prototype: `bool(CSystemWriter *__hidden this, unsigned __int16 *, struct IVssCreateWriterMetadata *, void *, struct SC_HANDLE__ *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x1800076b0`

## callees

- `0x180005fc0`
- `0x180007898`
- `0x180007968`
- `0x18000be40`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000793b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000793b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800078fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800078fe`

## pseudocode

```c
bool __fastcall CSystemWriter::AddLegacyDriver(
        CSystemWriter *this,
        unsigned __int16 *a2,
        struct IVssCreateWriterMetadata *a3,
        void *a4,
        struct SC_HANDLE__ *a5)
{
  __int64 v7; // rdx
  bool v8; // bl
  HLOCAL hMem; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Dst[264]; // [rsp+30h] [rbp-228h] BYREF

  hMem = 0;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = !(unsigned int)CSystemWriter::FindBinaryForService(a2, v7, (unsigned __int16 **)&hMem, a5)
    && ExpandEnvironmentStringsW((LPCWSTR)hMem, Dst, 0x104u)
    && (unsigned int)pSetupStringTableAddString(a4, Dst) != -1;
  if ( hMem )
    LocalFree(hMem);
  return v8;
}

```

## disassembly

```asm
0x180007898  mov     [rsp+arg_0], rbx
0x18000789d  mov     [rsp+arg_10], rbp
0x1800078a2  push    rsi
0x1800078a3  sub     rsp, 250h
0x1800078aa  mov     rax, cs:__security_cookie
0x1800078b1  xor     rax, rsp
0x1800078b4  mov     [rsp+258h+var_18], rax
0x1800078bc  xor     ebp, ebp
0x1800078be  mov     rbx, r9
0x1800078c1  mov     r9, [rsp+258h+arg_20]; struct SC_HANDLE__ *
0x1800078c9  mov     rax, rdx
0x1800078cc  mov     [rsp+258h+hMem], rbp
0x1800078d1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800078d5  inc     rdx; unsigned __int64
0x1800078d8  cmp     [rax+rdx*2], bp
0x1800078dc  jnz     short loc_1800078D5
0x1800078de  lea     r8, [rsp+258h+hMem]; unsigned __int16 **
0x1800078e3  mov     rcx, rax; Src
0x1800078e6  call    ?FindBinaryForService@CSystemWriter@@CAKPEAG_KPEAPEAGPEAUSC_HANDLE__@@@Z; CSystemWriter::FindBinaryForService(ushort *,unsigned __int64,ushort * *,SC_HANDLE__ *)
0x1800078eb  test    eax, eax
0x1800078ed  jz      short loc_18000792B
0x1800078ef  mov     bl, bpl
0x1800078f2  cmp     [rsp+258h+hMem], rbp
0x1800078f7  jz      short loc_180007904
0x1800078f9  mov     rcx, [rsp+258h+hMem]; hMem
0x1800078fe  call    cs:__imp_LocalFree
0x180007904  mov     al, bl
0x180007906  mov     rcx, [rsp+258h+var_18]
0x18000790e  xor     rcx, rsp; StackCookie
0x180007911  call    __security_check_cookie
0x180007916  lea     r11, [rsp+258h+var_8]
0x18000791e  mov     rbx, [r11+10h]
0x180007922  mov     rbp, [r11+20h]
0x180007926  mov     rsp, r11
0x180007929  pop     rsi
0x18000792a  retn
0x18000792b  mov     rcx, [rsp+258h+hMem]; lpSrc
0x180007930  lea     rdx, [rsp+258h+Dst]; lpDst
0x180007935  mov     r8d, 104h; nSize
0x18000793b  call    cs:__imp_ExpandEnvironmentStringsW
0x180007941  test    eax, eax
0x180007943  jz      short loc_1800078EF
0x180007945  lea     rdx, [rsp+258h+Dst]
0x18000794a  mov     rcx, rbx
0x18000794d  mov     sil, 1
0x180007950  call    pSetupStringTableAddString
0x180007955  cmp     eax, 0FFFFFFFFh
0x180007958  movzx   ebx, sil
0x18000795c  cmovz   ebx, ebp
0x18000795f  jmp     short loc_1800078F2
```
