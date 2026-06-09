# FsmThisLayerStarted

- ea: `0x18000eb90`
- end: `0x18000eca6`
- name: `FsmThisLayerStarted`
- size: `278`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000c050`
- `0x18000c234`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000be68`
- `0x18000eb90`
- `0x1800115d0`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x18000ebf5`: `FsmThisLayerStarted called for protocol = %x, port = %d`

## pseudocode

```c
__int64 __fastcall FsmThisLayerStarted(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 PointerToCPCB; // rbx
  __int64 v6; // r9
  __int64 (__fastcall *v7)(_QWORD); // rax
  int v8; // eax
  int v9; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v10[2044]; // [rsp+24h] [rbp-814h] BYREF

  v2 = (unsigned int)a2;
  v9 = 0;
  PointerToCPCB = GetPointerToCPCB(a1, a2);
  memset_0(v10, 0, sizeof(v10));
  if ( !PointerToCPCB )
    return 0;
  if ( (byte_18004DF34 & 1) != 0 )
  {
    v6 = *(_QWORD *)(a1 + 16);
    LOWORD(v9) = 0;
    FormatRRASErrorString(
      (wchar_t *)&v9,
      L"FsmThisLayerStarted called for protocol = %x, port = %d",
      *((unsigned int *)CpTable + 44 * v2),
      v6);
    if ( (byte_18004DF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
        (const wchar_t *)&v9);
  }
  v7 = (__int64 (__fastcall *)(_QWORD))*((_QWORD *)CpTable + 22 * v2 + 7);
  if ( v7 )
  {
    v8 = v7(*(_QWORD *)(PointerToCPCB + 16));
    if ( v8 )
    {
      *(_DWORD *)(PointerToCPCB + 40) = v8;
      FsmClose(a1, (unsigned int)v2);
      return 0;
    }
  }
  *(_DWORD *)(PointerToCPCB + 56) = 1;
  return 1;
}

```

## disassembly

```asm
0x18000eb90  mov     [rsp+arg_10], rbx
0x18000eb95  mov     [rsp+arg_18], rsi
0x18000eb9a  push    rdi
0x18000eb9b  sub     rsp, 830h
0x18000eba2  mov     rax, cs:__security_cookie
0x18000eba9  xor     rax, rsp
0x18000ebac  mov     [rsp+838h+var_18], rax
0x18000ebb4  mov     edi, edx
0x18000ebb6  mov     rsi, rcx
0x18000ebb9  call    GetPointerToCPCB
0x18000ebbe  xor     ecx, ecx
0x18000ebc0  xor     edx, edx; Val
0x18000ebc2  mov     [rsp+838h+var_818], ecx
0x18000ebc6  mov     r8d, 7FCh; Size
0x18000ebcc  lea     rcx, [rsp+838h+var_814]; void *
0x18000ebd1  mov     rbx, rax
0x18000ebd4  call    memset_0
0x18000ebd9  test    rbx, rbx
0x18000ebdc  jnz     short loc_18000EBE5
0x18000ebde  xor     eax, eax
0x18000ebe0  jmp     loc_18000EC80
0x18000ebe5  test    cs:byte_18004DF34, 1
0x18000ebec  jz      short loc_18000EC3D
0x18000ebee  mov     r8, cs:CpTable
0x18000ebf5  lea     rdx, aFsmthislayerst; "FsmThisLayerStarted called for protocol"...
0x18000ebfc  mov     r9, [rsi+10h]
0x18000ec00  xor     eax, eax
0x18000ec02  imul    rcx, rdi, 0B0h
0x18000ec09  mov     word ptr [rsp+838h+var_818], ax
0x18000ec0e  mov     r8d, [rcx+r8]
0x18000ec12  lea     rcx, [rsp+838h+var_818]
0x18000ec17  call    FormatRRASErrorString
0x18000ec1c  test    cs:byte_18004DF34, 1
0x18000ec23  jz      short loc_18000EC3D
0x18000ec25  lea     r8, [rsp+838h+var_818]
0x18000ec2a  lea     rdx, RasPppTraceInfo
0x18000ec31  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ec38  call    McTemplateU0z_EventWriteTransfer
0x18000ec3d  mov     rax, cs:CpTable
0x18000ec44  imul    rcx, rdi, 0B0h
0x18000ec4b  mov     rax, [rcx+rax+38h]
0x18000ec50  test    rax, rax
0x18000ec53  jz      short loc_18000EC74
0x18000ec55  mov     rcx, [rbx+10h]
0x18000ec59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec5e  test    eax, eax
0x18000ec60  jz      short loc_18000EC74
0x18000ec62  mov     edx, edi
0x18000ec64  mov     [rbx+28h], eax
0x18000ec67  mov     rcx, rsi
0x18000ec6a  call    FsmClose
0x18000ec6f  jmp     loc_18000EBDE
0x18000ec74  mov     dword ptr [rbx+38h], 1
0x18000ec7b  mov     eax, 1
0x18000ec80  mov     rcx, [rsp+838h+var_18]
0x18000ec88  xor     rcx, rsp; StackCookie
0x18000ec8b  call    __security_check_cookie
0x18000ec90  lea     r11, [rsp+838h+var_8]
0x18000ec98  mov     rbx, [r11+20h]
0x18000ec9c  mov     rsi, [r11+28h]
0x18000eca0  mov     rsp, r11
0x18000eca3  pop     rdi
0x18000eca4  retn
```
