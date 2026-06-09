# FsmThisLayerStarted

- ea: `0x18000e750`
- end: `0x18000e865`
- name: `FsmThisLayerStarted`
- size: `277`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000bc28`
- `0x18000be0c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000ba40`
- `0x18000e750`
- `0x180011064`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x18000e7b5`: `FsmThisLayerStarted called for protocol = %x, port = %d`

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
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v6 = *(_QWORD *)(a1 + 16);
    LOWORD(v9) = 0;
    FormatRRASErrorString(
      &v9,
      L"FsmThisLayerStarted called for protocol = %x, port = %d",
      *((unsigned int *)CpTable + 44 * v2),
      v6);
    if ( (byte_18004CF34 & 1) != 0 )
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
0x18000e750  mov     [rsp+arg_10], rbx
0x18000e755  mov     [rsp+arg_18], rsi
0x18000e75a  push    rdi
0x18000e75b  sub     rsp, 830h
0x18000e762  mov     rax, cs:__security_cookie
0x18000e769  xor     rax, rsp
0x18000e76c  mov     [rsp+838h+var_18], rax
0x18000e774  mov     edi, edx
0x18000e776  mov     rsi, rcx
0x18000e779  call    GetPointerToCPCB
0x18000e77e  xor     ecx, ecx
0x18000e780  xor     edx, edx; Val
0x18000e782  mov     [rsp+838h+var_818], ecx
0x18000e786  mov     r8d, 7FCh; Size
0x18000e78c  lea     rcx, [rsp+838h+var_814]; void *
0x18000e791  mov     rbx, rax
0x18000e794  call    memset_0
0x18000e799  test    rbx, rbx
0x18000e79c  jnz     short loc_18000E7A5
0x18000e79e  xor     eax, eax
0x18000e7a0  jmp     loc_18000E840
0x18000e7a5  test    cs:byte_18004CF34, 1
0x18000e7ac  jz      short loc_18000E7FD
0x18000e7ae  mov     r8, cs:CpTable
0x18000e7b5  lea     rdx, aFsmthislayerst; "FsmThisLayerStarted called for protocol"...
0x18000e7bc  mov     r9, [rsi+10h]
0x18000e7c0  xor     eax, eax
0x18000e7c2  imul    rcx, rdi, 0B0h
0x18000e7c9  mov     word ptr [rsp+838h+var_818], ax
0x18000e7ce  mov     r8d, [rcx+r8]
0x18000e7d2  lea     rcx, [rsp+838h+var_818]
0x18000e7d7  call    FormatRRASErrorString
0x18000e7dc  test    cs:byte_18004CF34, 1
0x18000e7e3  jz      short loc_18000E7FD
0x18000e7e5  lea     r8, [rsp+838h+var_818]
0x18000e7ea  lea     rdx, RasPppTraceInfo
0x18000e7f1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e7f8  call    McTemplateU0z_EventWriteTransfer
0x18000e7fd  mov     rax, cs:CpTable
0x18000e804  imul    rcx, rdi, 0B0h
0x18000e80b  mov     rax, [rcx+rax+38h]
0x18000e810  test    rax, rax
0x18000e813  jz      short loc_18000E834
0x18000e815  mov     rcx, [rbx+10h]
0x18000e819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e81e  test    eax, eax
0x18000e820  jz      short loc_18000E834
0x18000e822  mov     edx, edi
0x18000e824  mov     [rbx+28h], eax
0x18000e827  mov     rcx, rsi
0x18000e82a  call    FsmClose
0x18000e82f  jmp     loc_18000E79E
0x18000e834  mov     dword ptr [rbx+38h], 1
0x18000e83b  mov     eax, 1
0x18000e840  mov     rcx, [rsp+838h+var_18]
0x18000e848  xor     rcx, rsp; StackCookie
0x18000e84b  call    __security_check_cookie
0x18000e850  lea     r11, [rsp+838h+var_8]
0x18000e858  mov     rbx, [r11+20h]
0x18000e85c  mov     rsi, [r11+28h]
0x18000e860  mov     rsp, r11
0x18000e863  pop     rdi
0x18000e864  retn
```
