# PAC_DecodeValidationInformation(uchar *,ulong,_NETLOGON_VALIDATION_SAM_INFO3 * *)

- ea: `0x180004440`
- end: `0x1800044e4`
- name: `?PAC_DecodeValidationInformation@@YAJPEAEKPEAPEAU_NETLOGON_VALIDATION_SAM_INFO3@@@Z`
- size: `164`
- prototype: `int(unsigned __int8 *, unsigned int, struct _NETLOGON_VALIDATION_SAM_INFO3 **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e40`
- `0x1800044f0`

## callees

- `0x180004440`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x1800044b8`
- `RPCRT4!NdrMesTypeDecode3` at `0x1800044b8`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x180004472`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x180004472`
- `RPCRT4!MesHandleFree` at `0x1800044d2`
- `RPCRT4!MesHandleFree` at `0x1800044d2`

## pseudocode

```c
__int64 __fastcall PAC_DecodeValidationInformation(
        unsigned __int8 *a1,
        int a2,
        struct _NETLOGON_VALIDATION_SAM_INFO3 **a3)
{
  unsigned int v6; // ebx
  __int128 v8; // [rsp+30h] [rbp-38h] BYREF
  handle_t Handle; // [rsp+88h] [rbp+20h] BYREF

  Handle = 0;
  v8 = 0;
  if ( MesDecodeIncrementalHandleCreate(&v8, PacReadFcn, &Handle) )
  {
    v6 = -1073741670;
  }
  else
  {
    v6 = 0;
    DWORD2(v8) = a2;
    *(_QWORD *)&v8 = a1;
    NdrMesTypeDecode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 1u, a3);
  }
  if ( Handle )
    MesHandleFree(Handle);
  return v6;
}

```

## disassembly

```asm
0x180004440  mov     rax, rsp
0x180004443  push    rbx
0x180004444  push    rsi
0x180004445  push    rdi
0x180004446  push    r14
0x180004448  sub     rsp, 48h
0x18000444c  mov     r14, r8
0x18000444f  mov     edi, edx
0x180004451  mov     rsi, rcx
0x180004454  mov     qword ptr [rax+20h], 0
0x18000445c  xorps   xmm0, xmm0
0x18000445f  movups  xmmword ptr [rax-38h], xmm0
0x180004463  lea     r8, [rax+20h]; pHandle
0x180004467  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; ReadFn
0x18000446e  lea     rcx, [rax-38h]; UserState
0x180004472  call    cs:__imp_MesDecodeIncrementalHandleCreate
0x180004478  test    eax, eax
0x18000447a  jz      short loc_180004483
0x18000447c  mov     ebx, 0C000009Ah
0x180004481  jmp     short loc_1800044C5
0x180004483  xor     ebx, ebx
0x180004485  mov     [rsp+68h+var_30], edi
0x180004489  mov     [rsp+68h+var_38], rsi
0x18000448e  mov     [rsp+68h+pObject], r14; pObject
0x180004493  mov     [rsp+68h+nTypeIndex], 1; nTypeIndex
0x18000449b  lea     r9, ArrTypeOffset; ArrTypeOffset
0x1800044a2  lea     r8, pProxyInfo; pProxyInfo
0x1800044a9  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800044b0  mov     rcx, [rsp+68h+Handle]; Handle
0x1800044b8  call    cs:__imp_NdrMesTypeDecode3
0x1800044be  jmp     short loc_1800044C5
0x1800044c0  mov     ebx, 0C000000Dh
0x1800044c5  mov     rcx, [rsp+68h+Handle]; Handle
0x1800044cd  test    rcx, rcx
0x1800044d0  jz      short loc_1800044D8
0x1800044d2  call    cs:__imp_MesHandleFree
0x1800044d8  mov     eax, ebx
0x1800044da  add     rsp, 48h
0x1800044de  pop     r14
0x1800044e0  pop     rdi
0x1800044e1  pop     rsi
0x1800044e2  pop     rbx
0x1800044e3  retn
```
