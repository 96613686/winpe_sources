# FsmTimeoutConfRecv

- ea: `0x18000c854`
- end: `0x18000c997`
- name: `FsmTimeoutConfRecv`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017990`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000c854`
- `0x18000e86c`
- `0x180011064`
- `0x18002a138`

## string_xrefs

- `0x18000c8ae`: `Peer Conf Recv timeout event received for portid=%d,Id=%d,Protocol=%x,fAuth=%d`
- `0x18000c91a`: `We have sent the Ack, but not received the other side conf, We should complete this Layer forportid=%d,Id=%d,Protocol=%x,fAuth=%d`

## pseudocode

```c
void *__fastcall FsmTimeoutConfRecv(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  __int64 v5; // rdi
  _DWORD *PointerToCPCB; // r14
  void *result; // rax
  char v10; // cl
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // [rsp+20h] [rbp-848h]
  int v14; // [rsp+20h] [rbp-848h]
  __int64 v15; // [rsp+28h] [rbp-840h]
  int v16; // [rsp+28h] [rbp-840h]
  int v17; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v18[2044]; // [rsp+34h] [rbp-834h] BYREF

  v5 = (unsigned int)a2;
  v17 = 0;
  PointerToCPCB = (_DWORD *)GetPointerToCPCB(a1, a2);
  result = memset_0(v18, 0, sizeof(v18));
  v10 = byte_18004CF34;
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v11 = *(unsigned int *)(a1 + 64);
    v16 = a4;
    LOWORD(v17) = 0;
    v14 = *((_DWORD *)CpTable + 44 * v5);
    result = (void *)FormatRRASErrorString(
                       &v17,
                       L"Peer Conf Recv timeout event received for portid=%d,Id=%d,Protocol=%x,fAuth=%d",
                       v11,
                       a3,
                       v14,
                       v16);
    v10 = byte_18004CF34;
    if ( (byte_18004CF34 & 1) != 0 )
    {
      result = (void *)McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v17);
      v10 = byte_18004CF34;
    }
  }
  if ( *PointerToCPCB == 7 )
  {
    if ( (v10 & 1) != 0 )
    {
      v12 = *(unsigned int *)(a1 + 64);
      LODWORD(v15) = a4;
      LOWORD(v17) = 0;
      LODWORD(v13) = *((_DWORD *)CpTable + 44 * v5);
      FormatRRASErrorString(
        &v17,
        L"We have sent the Ack, but not received the other side conf, We should complete this Layer forportid=%d,Id=%d,Pro"
         "tocol=%x,fAuth=%d",
        v12,
        a3,
        v13,
        v15);
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v17);
    }
    return (void *)FsmThisLayerUp(a1, v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000c854  push    rbx
0x18000c856  push    rbp
0x18000c857  push    rsi
0x18000c858  push    rdi
0x18000c859  push    r14
0x18000c85b  sub     rsp, 840h
0x18000c862  mov     rax, cs:__security_cookie
0x18000c869  xor     rax, rsp
0x18000c86c  mov     [rsp+868h+var_38], rax
0x18000c874  mov     ebp, r9d
0x18000c877  mov     edi, edx
0x18000c879  mov     esi, r8d
0x18000c87c  mov     rbx, rcx
0x18000c87f  call    GetPointerToCPCB
0x18000c884  xor     ecx, ecx
0x18000c886  xor     edx, edx; Val
0x18000c888  mov     [rsp+868h+var_838], ecx
0x18000c88c  mov     r8d, 7FCh; Size
0x18000c892  lea     rcx, [rsp+868h+var_834]; void *
0x18000c897  mov     r14, rax
0x18000c89a  call    memset_0
0x18000c89f  mov     cl, cs:byte_18004CF34
0x18000c8a5  test    cl, 1
0x18000c8a8  jz      short loc_18000C90B
0x18000c8aa  mov     r8d, [rbx+40h]
0x18000c8ae  lea     rdx, aPeerConfRecvTi; "Peer Conf Recv timeout event received f"...
0x18000c8b5  xor     eax, eax
0x18000c8b7  mov     dword ptr [rsp+868h+var_840], ebp
0x18000c8bb  mov     word ptr [rsp+868h+var_838], ax
0x18000c8c0  mov     r9d, esi
0x18000c8c3  mov     rax, cs:CpTable
0x18000c8ca  imul    rcx, rdi, 0B0h
0x18000c8d1  mov     ecx, [rcx+rax]
0x18000c8d4  mov     dword ptr [rsp+868h+var_848], ecx
0x18000c8d8  lea     rcx, [rsp+868h+var_838]
0x18000c8dd  call    FormatRRASErrorString
0x18000c8e2  mov     cl, cs:byte_18004CF34
0x18000c8e8  test    cl, 1
0x18000c8eb  jz      short loc_18000C90B
0x18000c8ed  lea     r8, [rsp+868h+var_838]
0x18000c8f2  lea     rdx, RasPppTraceInfo
0x18000c8f9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c900  call    McTemplateU0z_EventWriteTransfer
0x18000c905  mov     cl, cs:byte_18004CF34
0x18000c90b  cmp     dword ptr [r14], 7
0x18000c90f  jnz     short loc_18000C979
0x18000c911  test    cl, 1
0x18000c914  jz      short loc_18000C96F
0x18000c916  mov     r8d, [rbx+40h]
0x18000c91a  lea     rdx, aWeHaveSentTheA; "We have sent the Ack, but not received "...
0x18000c921  xor     eax, eax
0x18000c923  mov     dword ptr [rsp+868h+var_840], ebp
0x18000c927  mov     word ptr [rsp+868h+var_838], ax
0x18000c92c  mov     r9d, esi
0x18000c92f  mov     rax, cs:CpTable
0x18000c936  imul    rcx, rdi, 0B0h
0x18000c93d  mov     ecx, [rcx+rax]
0x18000c940  mov     dword ptr [rsp+868h+var_848], ecx
0x18000c944  lea     rcx, [rsp+868h+var_838]
0x18000c949  call    FormatRRASErrorString
0x18000c94e  test    cs:byte_18004CF34, 1
0x18000c955  jz      short loc_18000C96F
0x18000c957  lea     r8, [rsp+868h+var_838]
0x18000c95c  lea     rdx, RasPppTraceInfo
0x18000c963  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c96a  call    McTemplateU0z_EventWriteTransfer
0x18000c96f  mov     edx, edi
0x18000c971  mov     rcx, rbx
0x18000c974  call    FsmThisLayerUp
0x18000c979  mov     rcx, [rsp+868h+var_38]
0x18000c981  xor     rcx, rsp; StackCookie
0x18000c984  call    __security_check_cookie
0x18000c989  add     rsp, 840h
0x18000c990  pop     r14
0x18000c992  pop     rdi
0x18000c993  pop     rsi
0x18000c994  pop     rbp
0x18000c995  pop     rbx
0x18000c996  retn
```
