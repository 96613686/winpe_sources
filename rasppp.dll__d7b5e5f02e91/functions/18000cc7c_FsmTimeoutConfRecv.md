# FsmTimeoutConfRecv

- ea: `0x18000cc7c`
- end: `0x18000cdc0`
- name: `FsmTimeoutConfRecv`
- size: `324`
- prototype: `void *__fastcall(__int64, __int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800181b0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000cc7c`
- `0x18000ecac`
- `0x1800115d0`
- `0x18002b0dc`

## string_xrefs

- `0x18000ccd6`: `Peer Conf Recv timeout event received for portid=%d,Id=%d,Protocol=%x,fAuth=%d`
- `0x18000cd42`: `We have sent the Ack, but not received the other side conf, We should complete this Layer forportid=%d,Id=%d,Protocol=%x,fAuth=%d`

## pseudocode

```c
HRESULT __fastcall FsmTimeoutConfRecv(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  __int64 v5; // rdi
  _DWORD *PointerToCPCB; // r14
  HRESULT result; // eax
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
  result = (unsigned int)memset_0(v18, 0, sizeof(v18));
  v10 = byte_18004DF34;
  if ( (byte_18004DF34 & 1) != 0 )
  {
    v11 = *(unsigned int *)(a1 + 64);
    v16 = a4;
    LOWORD(v17) = 0;
    v14 = *((_DWORD *)CpTable + 44 * v5);
    result = FormatRRASErrorString(
               (wchar_t *)&v17,
               L"Peer Conf Recv timeout event received for portid=%d,Id=%d,Protocol=%x,fAuth=%d",
               v11,
               a3,
               v14,
               v16);
    v10 = byte_18004DF34;
    if ( (byte_18004DF34 & 1) != 0 )
    {
      result = McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v17);
      v10 = byte_18004DF34;
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
        (wchar_t *)&v17,
        L"We have sent the Ack, but not received the other side conf, We should complete this Layer forportid=%d,Id=%d,Pro"
         "tocol=%x,fAuth=%d",
        v12,
        a3,
        v13,
        v15);
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v17);
    }
    return FsmThisLayerUp(a1, v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000cc7c  push    rbx
0x18000cc7e  push    rbp
0x18000cc7f  push    rsi
0x18000cc80  push    rdi
0x18000cc81  push    r14
0x18000cc83  sub     rsp, 840h
0x18000cc8a  mov     rax, cs:__security_cookie
0x18000cc91  xor     rax, rsp
0x18000cc94  mov     [rsp+868h+var_38], rax
0x18000cc9c  mov     ebp, r9d
0x18000cc9f  mov     edi, edx
0x18000cca1  mov     esi, r8d
0x18000cca4  mov     rbx, rcx
0x18000cca7  call    GetPointerToCPCB
0x18000ccac  xor     ecx, ecx
0x18000ccae  xor     edx, edx; Val
0x18000ccb0  mov     [rsp+868h+var_838], ecx
0x18000ccb4  mov     r8d, 7FCh; Size
0x18000ccba  lea     rcx, [rsp+868h+var_834]; void *
0x18000ccbf  mov     r14, rax
0x18000ccc2  call    memset_0
0x18000ccc7  mov     cl, cs:byte_18004DF34
0x18000cccd  test    cl, 1
0x18000ccd0  jz      short loc_18000CD33
0x18000ccd2  mov     r8d, [rbx+40h]
0x18000ccd6  lea     rdx, aPeerConfRecvTi; "Peer Conf Recv timeout event received f"...
0x18000ccdd  xor     eax, eax
0x18000ccdf  mov     dword ptr [rsp+868h+var_840], ebp
0x18000cce3  mov     word ptr [rsp+868h+var_838], ax
0x18000cce8  mov     r9d, esi
0x18000cceb  mov     rax, cs:CpTable
0x18000ccf2  imul    rcx, rdi, 0B0h
0x18000ccf9  mov     ecx, [rcx+rax]
0x18000ccfc  mov     dword ptr [rsp+868h+var_848], ecx
0x18000cd00  lea     rcx, [rsp+868h+var_838]
0x18000cd05  call    FormatRRASErrorString
0x18000cd0a  mov     cl, cs:byte_18004DF34
0x18000cd10  test    cl, 1
0x18000cd13  jz      short loc_18000CD33
0x18000cd15  lea     r8, [rsp+868h+var_838]
0x18000cd1a  lea     rdx, RasPppTraceInfo
0x18000cd21  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cd28  call    McTemplateU0z_EventWriteTransfer
0x18000cd2d  mov     cl, cs:byte_18004DF34
0x18000cd33  cmp     dword ptr [r14], 7
0x18000cd37  jnz     short loc_18000CDA1
0x18000cd39  test    cl, 1
0x18000cd3c  jz      short loc_18000CD97
0x18000cd3e  mov     r8d, [rbx+40h]
0x18000cd42  lea     rdx, aWeHaveSentTheA; "We have sent the Ack, but not received "...
0x18000cd49  xor     eax, eax
0x18000cd4b  mov     dword ptr [rsp+868h+var_840], ebp
0x18000cd4f  mov     word ptr [rsp+868h+var_838], ax
0x18000cd54  mov     r9d, esi
0x18000cd57  mov     rax, cs:CpTable
0x18000cd5e  imul    rcx, rdi, 0B0h
0x18000cd65  mov     ecx, [rcx+rax]
0x18000cd68  mov     dword ptr [rsp+868h+var_848], ecx
0x18000cd6c  lea     rcx, [rsp+868h+var_838]
0x18000cd71  call    FormatRRASErrorString
0x18000cd76  test    cs:byte_18004DF34, 1
0x18000cd7d  jz      short loc_18000CD97
0x18000cd7f  lea     r8, [rsp+868h+var_838]
0x18000cd84  lea     rdx, RasPppTraceInfo
0x18000cd8b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cd92  call    McTemplateU0z_EventWriteTransfer
0x18000cd97  mov     edx, edi
0x18000cd99  mov     rcx, rbx
0x18000cd9c  call    FsmThisLayerUp
0x18000cda1  mov     rcx, [rsp+868h+var_38]
0x18000cda9  xor     rcx, rsp; StackCookie
0x18000cdac  call    __security_check_cookie
0x18000cdb1  add     rsp, 840h
0x18000cdb8  pop     r14
0x18000cdba  pop     rdi
0x18000cdbb  pop     rsi
0x18000cdbc  pop     rbp
0x18000cdbd  pop     rbx
0x18000cdbe  retn
```
