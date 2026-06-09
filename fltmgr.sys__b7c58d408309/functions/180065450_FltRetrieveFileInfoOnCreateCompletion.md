# FltRetrieveFileInfoOnCreateCompletion

- ea: `0x180065450`
- end: `0x1800655f6`
- name: `FltRetrieveFileInfoOnCreateCompletion`
- size: `422`
- prototype: `char *__fastcall(__int64, int *, int, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009f20`
- `0x180065450`

## import_xrefs

- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x180065512`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x180065512`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x1800654d2`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x1800654d2`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x180065543`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x180065543`

## pseudocode

```c
char *__fastcall FltRetrieveFileInfoOnCreateCompletion(__int64 a1, int *a2, int a3, _DWORD *a4)
{
  int v6; // eax
  __int64 v7; // rbx
  __int64 v8; // r8
  char v9; // al
  NTSTATUS EcpListFromIrp; // eax
  IRP *v11; // rcx
  NTSTATUS ExtraCreateParameter; // eax
  char *v13; // rcx
  PVOID EcpContext; // [rsp+48h] [rbp+10h] BYREF
  PECP_LIST EcpList; // [rsp+58h] [rbp+20h] BYREF

  *a4 = 0;
  v6 = *a2;
  v7 = 0;
  EcpList = 0;
  EcpContext = 0;
  if ( (v6 & 1) != 0
    && (v8 = *((_QWORD *)a2 + 2), (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(v8 + 4) + 22)) & 2) != 0)
    || (v8 = *((_QWORD *)a2 + 2), v9 = *(_BYTE *)(v8 + 4), v9 == -7)
    || v9 == -14 )
  {
    if ( *(unsigned __int8 *)(v8 + 4) == 242 || *(unsigned __int8 *)(v8 + 4) == 249 )
      v11 = *(IRP **)(v8 + 24);
    else
      v11 = (IRP *)*((_QWORD *)a2 - 23);
    EcpListFromIrp = FsRtlGetEcpListFromIrp(v11, &EcpList);
  }
  else
  {
    EcpListFromIrp = -1073741811;
  }
  if ( (int)FltpDbgStatus(EcpListFromIrp) < 0 )
    return (char *)v7;
  if ( !EcpList )
    return (char *)v7;
  ExtraCreateParameter = FsRtlFindExtraCreateParameter(EcpList, &GUID_ECP_QUERY_ON_CREATE, &EcpContext, 0);
  if ( (int)FltpDbgStatus(ExtraCreateParameter) < 0 )
    return (char *)v7;
  if ( !EcpContext )
    return (char *)v7;
  if ( !FsRtlIsEcpAcknowledged(EcpContext) )
    return (char *)v7;
  v13 = (char *)EcpContext;
  if ( (a3 & *((_DWORD *)EcpContext + 1)) == 0
    || (a3 & *((_DWORD *)EcpContext + 2)) != 0
    || (a3 & *((_DWORD *)EcpContext + 3)) != 0 )
  {
    return (char *)v7;
  }
  *a4 = 0;
  switch ( a3 )
  {
    case 1:
      *a4 = 72;
      return v13 + 16;
    case 4:
      *a4 = 16;
      return v13 + 120;
    case 8:
      *a4 = 24;
      return v13 + 152;
    case 2:
      *a4 = 28;
      return v13 + 88;
    case 16:
      *a4 = 16;
      return v13 + 184;
    default:
      return (char *)v7;
  }
}

```

## disassembly

```asm
0x180065450  mov     [rsp+arg_0], rbx
0x180065455  push    rbp
0x180065456  push    rsi
0x180065457  push    rdi
0x180065458  sub     rsp, 20h
0x18006545c  xor     ebp, ebp
0x18006545e  mov     rsi, r9
0x180065461  mov     [r9], ebp
0x180065464  mov     edi, r8d
0x180065467  mov     eax, [rdx]
0x180065469  mov     ebx, ebp
0x18006546b  mov     [rsp+38h+EcpList], rbp
0x180065470  mov     [rsp+38h+EcpContext], rbp
0x180065475  test    al, 1
0x180065477  jz      short loc_180065495
0x180065479  mov     r8, [rdx+10h]
0x18006547d  lea     r9, FltpOperationFlags
0x180065484  movzx   eax, byte ptr [r8+4]
0x180065489  add     al, 16h
0x18006548b  movzx   eax, al
0x18006548e  test    byte ptr [rax+r9], 2
0x180065493  jnz     short loc_1800654AD
0x180065495  mov     r8, [rdx+10h]
0x180065499  movzx   eax, byte ptr [r8+4]
0x18006549e  cmp     al, 0F9h
0x1800654a0  jz      short loc_1800654AD
0x1800654a2  cmp     al, 0F2h
0x1800654a4  jz      short loc_1800654AD
0x1800654a6  mov     eax, 0C000000Dh
0x1800654ab  jmp     short loc_1800654DE
0x1800654ad  movzx   eax, byte ptr [r8+4]
0x1800654b2  sub     eax, 0F2h
0x1800654b7  jz      loc_1800655E1
0x1800654bd  cmp     eax, 7
0x1800654c0  jz      loc_1800655E1
0x1800654c6  mov     rcx, [rdx-0B8h]; Irp
0x1800654cd  lea     rdx, [rsp+38h+EcpList]; EcpList
0x1800654d2  call    cs:__imp_FsRtlGetEcpListFromIrp
0x1800654d9  nop     dword ptr [rax+rax+00h]
0x1800654de  mov     r8d, 732h
0x1800654e4  lea     rdx, aMinkernelFsFil_14; "minkernel\\fs\\filtermgr\\filter\\ecpsu"...
0x1800654eb  xor     r9d, r9d
0x1800654ee  mov     ecx, eax
0x1800654f0  call    FltpDbgStatus
0x1800654f5  test    eax, eax
0x1800654f7  js      short loc_180065578
0x1800654f9  mov     rcx, [rsp+38h+EcpList]; EcpList
0x1800654fe  test    rcx, rcx
0x180065501  jz      short loc_180065578
0x180065503  xor     r9d, r9d; EcpContextSize
0x180065506  lea     r8, [rsp+38h+EcpContext]; EcpContext
0x18006550b  lea     rdx, GUID_ECP_QUERY_ON_CREATE; EcpType
0x180065512  call    cs:__imp_FsRtlFindExtraCreateParameter
0x180065519  nop     dword ptr [rax+rax+00h]
0x18006551e  mov     r8d, 748h
0x180065524  lea     rdx, aMinkernelFsFil_14; "minkernel\\fs\\filtermgr\\filter\\ecpsu"...
0x18006552b  mov     ecx, eax
0x18006552d  xor     r9d, r9d
0x180065530  call    FltpDbgStatus
0x180065535  test    eax, eax
0x180065537  js      short loc_180065578
0x180065539  mov     rcx, [rsp+38h+EcpContext]; EcpContext
0x18006553e  test    rcx, rcx
0x180065541  jz      short loc_180065578
0x180065543  call    cs:__imp_FsRtlIsEcpAcknowledged
0x18006554a  nop     dword ptr [rax+rax+00h]
0x18006554f  test    al, al
0x180065551  jz      short loc_180065578
0x180065553  mov     rcx, [rsp+38h+EcpContext]
0x180065558  test    [rcx+4], edi
0x18006555b  jz      short loc_180065578
0x18006555d  test    [rcx+8], edi
0x180065560  jnz     short loc_180065578
0x180065562  test    [rcx+0Ch], edi
0x180065565  jnz     short loc_180065578
0x180065567  mov     [rsi], ebp
0x180065569  cmp     edi, 1
0x18006556c  jnz     short loc_180065589
0x18006556e  mov     dword ptr [rsi], 48h ; 'H'
0x180065574  lea     rbx, [rcx+10h]
0x180065578  mov     rax, rbx
0x18006557b  mov     rbx, [rsp+38h+arg_0]
0x180065580  add     rsp, 20h
0x180065584  pop     rdi
0x180065585  pop     rsi
0x180065586  pop     rbp
0x180065587  retn
0x180065589  cmp     edi, 4
0x18006558c  jz      short loc_1800655A8
0x18006558e  cmp     edi, 8
0x180065591  jz      short loc_1800655C3
0x180065593  cmp     edi, 2
0x180065596  jz      short loc_1800655EA
0x180065598  cmp     edi, 10h
0x18006559b  jnz     short loc_180065578
0x18006559d  mov     [rsi], edi
0x18006559f  lea     rbx, [rcx+0B8h]
0x1800655a6  jmp     short loc_180065578
0x1800655a8  lea     rbx, [rcx+78h]
0x1800655ac  mov     dword ptr [rsi], 10h
0x1800655b2  mov     rax, rbx
0x1800655b5  mov     rbx, [rsp+38h+arg_0]
0x1800655ba  add     rsp, 20h
0x1800655be  pop     rdi
0x1800655bf  pop     rsi
0x1800655c0  pop     rbp
0x1800655c1  retn
0x1800655c3  lea     rbx, [rcx+98h]
0x1800655ca  mov     dword ptr [rsi], 18h
0x1800655d0  mov     rax, rbx
0x1800655d3  mov     rbx, [rsp+38h+arg_0]
0x1800655d8  add     rsp, 20h
0x1800655dc  pop     rdi
0x1800655dd  pop     rsi
0x1800655de  pop     rbp
0x1800655df  retn
0x1800655e1  mov     rcx, [r8+18h]
0x1800655e5  jmp     loc_1800654CD
0x1800655ea  mov     dword ptr [rsi], 1Ch
0x1800655f0  lea     rbx, [rcx+58h]
0x1800655f4  jmp     short loc_180065578
```
