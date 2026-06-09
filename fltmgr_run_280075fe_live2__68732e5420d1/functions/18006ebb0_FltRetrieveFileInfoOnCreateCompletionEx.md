# FltRetrieveFileInfoOnCreateCompletionEx

- ea: `0x18006ebb0`
- end: `0x18006ed81`
- name: `FltRetrieveFileInfoOnCreateCompletionEx`
- size: `465`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009f20`
- `0x18006ebb0`

## import_xrefs

- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x18006ec7d`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x18006ec7d`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x18006ec35`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x18006ec35`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x18006ecae`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x18006ecae`

## pseudocode

```c
__int64 __fastcall FltRetrieveFileInfoOnCreateCompletionEx(__int64 a1, __int64 a2, int a3, _DWORD *a4, _QWORD *a5)
{
  _QWORD *v5; // rsi
  __int64 v8; // r8
  char v9; // al
  IRP *v10; // rcx
  unsigned int EcpListFromIrp; // eax
  unsigned int ExtraCreateParameter; // eax
  char *v13; // rcx
  char *v14; // rcx
  PVOID EcpContext; // [rsp+48h] [rbp+10h] BYREF
  PECP_LIST EcpList; // [rsp+58h] [rbp+20h] BYREF

  v5 = a5;
  *a4 = 0;
  EcpList = 0;
  EcpContext = 0;
  *v5 = 0;
  if ( (*(_DWORD *)a2 & 1) != 0
    && (v8 = *(_QWORD *)(a2 + 16), (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(v8 + 4) + 22)) & 2) != 0)
    || (v8 = *(_QWORD *)(a2 + 16), v9 = *(_BYTE *)(v8 + 4), v9 == -14)
    || v9 == -7 )
  {
    if ( *(unsigned __int8 *)(v8 + 4) == 242 || *(unsigned __int8 *)(v8 + 4) == 249 )
      v10 = *(IRP **)(v8 + 24);
    else
      v10 = *(IRP **)(a2 - 184);
    EcpListFromIrp = FsRtlGetEcpListFromIrp(v10, &EcpList);
  }
  else
  {
    EcpListFromIrp = -1073741811;
  }
  if ( (int)FltpDbgStatus(EcpListFromIrp, "minkernel\\fs\\filtermgr\\filter\\ecpsup.c", 1842, 0) < 0 )
    return 3221225659LL;
  if ( !EcpList )
    return 3221225659LL;
  ExtraCreateParameter = FsRtlFindExtraCreateParameter(EcpList, &GUID_ECP_QUERY_ON_CREATE, &EcpContext, 0);
  if ( (int)FltpDbgStatus(ExtraCreateParameter, "minkernel\\fs\\filtermgr\\filter\\ecpsup.c", 1864, 0) < 0 )
    return 3221225659LL;
  if ( !EcpContext )
    return 3221225659LL;
  if ( !FsRtlIsEcpAcknowledged(EcpContext) )
    return 3221225659LL;
  v13 = (char *)EcpContext;
  if ( (a3 & *((_DWORD *)EcpContext + 1)) == 0 )
    return 3221225659LL;
  if ( (a3 & *((_DWORD *)EcpContext + 2)) != 0 )
    return 3221225473LL;
  if ( (a3 & *((_DWORD *)EcpContext + 3)) == 0 )
  {
    *a4 = 0;
    *v5 = 0;
    switch ( a3 )
    {
      case 1:
        *a4 = 72;
        v14 = v13 + 16;
LABEL_19:
        *v5 = v14;
        return 0;
      case 4:
        *a4 = 16;
        v14 = v13 + 120;
        goto LABEL_19;
      case 8:
        *a4 = 24;
        v14 = v13 + 152;
        goto LABEL_19;
      case 2:
        *a4 = 28;
        v14 = v13 + 88;
        goto LABEL_19;
      case 16:
        *a4 = 16;
        v14 = v13 + 184;
        goto LABEL_19;
    }
  }
  return 3221226021LL;
}

```

## disassembly

```asm
0x18006ebb0  mov     [rsp+arg_0], rbx
0x18006ebb5  push    rbp
0x18006ebb6  push    rsi
0x18006ebb7  push    rdi
0x18006ebb8  sub     rsp, 20h
0x18006ebbc  mov     rsi, [rsp+38h+arg_20]
0x18006ebc1  xor     ebp, ebp
0x18006ebc3  mov     [r9], ebp
0x18006ebc6  mov     rdi, r9
0x18006ebc9  mov     ebx, r8d
0x18006ebcc  mov     [rsp+38h+EcpList], rbp
0x18006ebd1  mov     [rsp+38h+EcpContext], rbp
0x18006ebd6  mov     [rsi], rbp
0x18006ebd9  mov     eax, [rdx]
0x18006ebdb  test    al, 1
0x18006ebdd  jz      short loc_18006EBFB
0x18006ebdf  mov     r8, [rdx+10h]
0x18006ebe3  lea     r9, FltpOperationFlags
0x18006ebea  movzx   eax, byte ptr [r8+4]
0x18006ebef  add     al, 16h
0x18006ebf1  movzx   eax, al
0x18006ebf4  test    byte ptr [rax+r9], 2
0x18006ebf9  jnz     short loc_18006EC10
0x18006ebfb  mov     r8, [rdx+10h]
0x18006ebff  movzx   eax, byte ptr [r8+4]
0x18006ec04  cmp     al, 0F2h
0x18006ec06  jz      short loc_18006EC10
0x18006ec08  cmp     al, 0F9h
0x18006ec0a  jnz     loc_18006ED4F
0x18006ec10  movzx   eax, byte ptr [r8+4]
0x18006ec15  sub     eax, 0F2h
0x18006ec1a  jz      loc_18006ED46
0x18006ec20  cmp     eax, 7
0x18006ec23  jz      loc_18006ED46
0x18006ec29  mov     rcx, [rdx-0B8h]; Irp
0x18006ec30  lea     rdx, [rsp+38h+EcpList]; EcpList
0x18006ec35  call    cs:__imp_FsRtlGetEcpListFromIrp
0x18006ec3c  nop     dword ptr [rax+rax+00h]
0x18006ec41  mov     r8d, 732h
0x18006ec47  lea     rdx, aMinkernelFsFil_14; "minkernel\\fs\\filtermgr\\filter\\ecpsu"...
0x18006ec4e  xor     r9d, r9d
0x18006ec51  mov     ecx, eax
0x18006ec53  call    FltpDbgStatus
0x18006ec58  test    eax, eax
0x18006ec5a  js      loc_18006ECFD
0x18006ec60  mov     rcx, [rsp+38h+EcpList]; EcpList
0x18006ec65  test    rcx, rcx
0x18006ec68  jz      loc_18006ECFD
0x18006ec6e  xor     r9d, r9d; EcpContextSize
0x18006ec71  lea     r8, [rsp+38h+EcpContext]; EcpContext
0x18006ec76  lea     rdx, GUID_ECP_QUERY_ON_CREATE; EcpType
0x18006ec7d  call    cs:__imp_FsRtlFindExtraCreateParameter
0x18006ec84  nop     dword ptr [rax+rax+00h]
0x18006ec89  mov     r8d, 748h
0x18006ec8f  lea     rdx, aMinkernelFsFil_14; "minkernel\\fs\\filtermgr\\filter\\ecpsu"...
0x18006ec96  mov     ecx, eax
0x18006ec98  xor     r9d, r9d
0x18006ec9b  call    FltpDbgStatus
0x18006eca0  test    eax, eax
0x18006eca2  js      short loc_18006ECFD
0x18006eca4  mov     rcx, [rsp+38h+EcpContext]; EcpContext
0x18006eca9  test    rcx, rcx
0x18006ecac  jz      short loc_18006ECFD
0x18006ecae  call    cs:__imp_FsRtlIsEcpAcknowledged
0x18006ecb5  nop     dword ptr [rax+rax+00h]
0x18006ecba  test    al, al
0x18006ecbc  jz      short loc_18006ECFD
0x18006ecbe  mov     rcx, [rsp+38h+EcpContext]
0x18006ecc3  test    [rcx+4], ebx
0x18006ecc6  jz      short loc_18006ECFD
0x18006ecc8  test    [rcx+8], ebx
0x18006eccb  jnz     loc_18006ED59
0x18006ecd1  test    [rcx+0Ch], ebx
0x18006ecd4  jnz     short loc_18006ED18
0x18006ecd6  mov     [rdi], ebp
0x18006ecd8  mov     [rsi], rbp
0x18006ecdb  cmp     ebx, 1
0x18006ecde  jnz     short loc_18006ED04
0x18006ece0  mov     dword ptr [rdi], 48h ; 'H'
0x18006ece6  add     rcx, 10h
0x18006ecea  mov     [rsi], rcx
0x18006eced  xor     eax, eax
0x18006ecef  mov     rbx, [rsp+38h+arg_0]
0x18006ecf4  add     rsp, 20h
0x18006ecf8  pop     rdi
0x18006ecf9  pop     rsi
0x18006ecfa  pop     rbp
0x18006ecfb  retn
0x18006ecfd  mov     eax, 0C00000BBh
0x18006ed02  jmp     short loc_18006ECEF
0x18006ed04  cmp     ebx, 4
0x18006ed07  jz      short loc_18006ED2B
0x18006ed09  cmp     ebx, 8
0x18006ed0c  jz      short loc_18006ED37
0x18006ed0e  cmp     ebx, 2
0x18006ed11  jz      short loc_18006ED72
0x18006ed13  cmp     ebx, 10h
0x18006ed16  jz      short loc_18006ED60
0x18006ed18  mov     rbx, [rsp+38h+arg_0]
0x18006ed1d  mov     eax, 0C0000225h
0x18006ed22  add     rsp, 20h
0x18006ed26  pop     rdi
0x18006ed27  pop     rsi
0x18006ed28  pop     rbp
0x18006ed29  retn
0x18006ed2b  mov     dword ptr [rdi], 10h
0x18006ed31  add     rcx, 78h ; 'x'
0x18006ed35  jmp     short loc_18006ECEA
0x18006ed37  mov     dword ptr [rdi], 18h
0x18006ed3d  add     rcx, 98h
0x18006ed44  jmp     short loc_18006ECEA
0x18006ed46  mov     rcx, [r8+18h]
0x18006ed4a  jmp     loc_18006EC30
0x18006ed4f  mov     eax, 0C000000Dh
0x18006ed54  jmp     loc_18006EC41
0x18006ed59  mov     eax, 0C0000001h
0x18006ed5e  jmp     short loc_18006ECEF
0x18006ed60  mov     dword ptr [rdi], 10h
0x18006ed66  add     rcx, 0B8h
0x18006ed6d  jmp     loc_18006ECEA
0x18006ed72  mov     dword ptr [rdi], 1Ch
0x18006ed78  add     rcx, 58h ; 'X'
0x18006ed7c  jmp     loc_18006ECEA
```
