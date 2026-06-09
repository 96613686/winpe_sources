# PAC_DecodeValidationInformationEx(uchar *,ulong,_NETLOGON_VALIDATION_SAM_INFO4 * *)

- ea: `0x18001e870`
- end: `0x18001e937`
- name: `?PAC_DecodeValidationInformationEx@@YAJPEAEKPEAPEAU_NETLOGON_VALIDATION_SAM_INFO4@@@Z`
- size: `199`
- prototype: `int(unsigned __int8 *, unsigned int, struct _NETLOGON_VALIDATION_SAM_INFO4 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002e40`
- `0x1800044f0`

## callees

- `0x1800057f0`
- `0x18001e870`
- `0x1800200e4`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18001e8ea`
- `RPCRT4!NdrMesTypeDecode3` at `0x18001e8ea`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x18001e8a9`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x18001e8a9`
- `RPCRT4!MesHandleFree` at `0x18001e91f`
- `RPCRT4!MesHandleFree` at `0x18001e91f`

## pseudocode

```c
__int64 __fastcall PAC_DecodeValidationInformationEx(
        unsigned __int8 *a1,
        int a2,
        struct _NETLOGON_VALIDATION_SAM_INFO4 **a3)
{
  int v6; // ebx
  __int128 UserState; // [rsp+30h] [rbp-18h] BYREF
  handle_t pHandle; // [rsp+68h] [rbp+20h] BYREF

  pHandle = 0;
  UserState = 0;
  if ( MesDecodeIncrementalHandleCreate(&UserState, PacReadFcn, &pHandle) )
  {
    v6 = -1073741670;
  }
  else
  {
    DWORD2(UserState) = a2;
    *(_QWORD *)&UserState = a1;
    NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 4u, a3);
    v6 = PacValidateInfo4(*a3);
    if ( v6 < 0 )
    {
      Pku2uFree(*a3);
      *a3 = 0;
    }
  }
  if ( pHandle )
    MesHandleFree(pHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001e870  mov     [rsp+arg_0], rbx
0x18001e875  mov     [rsp+arg_8], rsi
0x18001e87a  push    rdi
0x18001e87b  sub     rsp, 40h
0x18001e87f  mov     rdi, r8
0x18001e882  mov     ebx, edx
0x18001e884  mov     rsi, rcx
0x18001e887  mov     [rsp+48h+pHandle], 0
0x18001e890  xorps   xmm0, xmm0
0x18001e893  movups  [rsp+48h+UserState], xmm0
0x18001e898  lea     r8, [rsp+48h+pHandle]; pHandle
0x18001e89d  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; ReadFn
0x18001e8a4  lea     rcx, [rsp+48h+UserState]; UserState
0x18001e8a9  call    cs:__imp_MesDecodeIncrementalHandleCreate
0x18001e8af  test    eax, eax
0x18001e8b1  jz      short loc_18001E8BA
0x18001e8b3  mov     ebx, 0C000009Ah
0x18001e8b8  jmp     short loc_18001E915
0x18001e8ba  mov     dword ptr [rsp+48h+UserState+8], ebx
0x18001e8be  mov     qword ptr [rsp+48h+UserState], rsi
0x18001e8c3  mov     [rsp+48h+pObject], rdi; pObject
0x18001e8c8  mov     [rsp+48h+nTypeIndex], 4; nTypeIndex
0x18001e8d0  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18001e8d7  lea     r8, pProxyInfo; pProxyInfo
0x18001e8de  lea     rdx, pPicklingInfo; pPicklingInfo
0x18001e8e5  mov     rcx, [rsp+48h+pHandle]; Handle
0x18001e8ea  call    cs:__imp_NdrMesTypeDecode3
0x18001e8f0  nop
0x18001e8f1  mov     rcx, [rdi]; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x18001e8f4  call    ?PacValidateInfo4@@YAJQEAU_NETLOGON_VALIDATION_SAM_INFO4@@@Z; PacValidateInfo4(_NETLOGON_VALIDATION_SAM_INFO4 * const)
0x18001e8f9  mov     ebx, eax
0x18001e8fb  test    eax, eax
0x18001e8fd  jns     short loc_18001E915
0x18001e8ff  mov     rcx, [rdi]; void *
0x18001e902  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18001e907  mov     qword ptr [rdi], 0
0x18001e90e  jmp     short loc_18001E915
0x18001e910  mov     ebx, 0C000000Dh
0x18001e915  mov     rcx, [rsp+48h+pHandle]; Handle
0x18001e91a  test    rcx, rcx
0x18001e91d  jz      short loc_18001E925
0x18001e91f  call    cs:__imp_MesHandleFree
0x18001e925  mov     eax, ebx
0x18001e927  mov     rbx, [rsp+48h+arg_0]
0x18001e92c  mov     rsi, [rsp+48h+arg_8]
0x18001e931  add     rsp, 40h
0x18001e935  pop     rdi
0x18001e936  retn
```
