# ReceiveTermReq

- ea: `0x18000b310`
- end: `0x18000b7f7`
- name: `ReceiveTermReq`
- size: `1255`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x1800066b4`
- `0x18000b310`
- `0x18000b9ac`
- `0x18000de5c`
- `0x18000e100`
- `0x18000e364`
- `0x18000f334`
- `0x18000f528`
- `0x180012dcc`
- `0x180013490`
- `0x18002a138`

## import_xrefs

- `rtutils!RouterLogEventA` at `0x18000b692`
- `rtutils!RouterLogEventA` at `0x18000b78f`
- `rtutils!RouterLogEventA` at `0x18000b692`
- `rtutils!RouterLogEventA` at `0x18000b78f`

## string_xrefs

- `0x18000b6b4`: `CoId=%hs: Layer=%hs: SubLayer=%hs: The connection attempt failed on port: %hs because of the authentication protocol selected. Check to see if the authentication protocol is supported in the operating systems at the client and server ends of the connection %d`

## pseudocode

```c
int __fastcall ReceiveTermReq(__int64 a1, unsigned int a2, int *a3, unsigned __int8 *a4)
{
  __int64 v5; // r14
  int result; // eax
  __int64 v9; // r8
  int v10; // r14d
  __int64 v11; // r11
  unsigned int v12; // edx
  DWORD dwErrorCode; // edx
  __int64 v14; // r11
  LPSTR v15[3]; // [rsp+48h] [rbp-B8h] BYREF
  int v16; // [rsp+60h] [rbp-A0h]
  unsigned int v17; // [rsp+64h] [rbp-9Ch]
  char pszDest[136]; // [rsp+68h] [rbp-98h] BYREF
  LPSTR plpszSubStringArray[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v20; // [rsp+100h] [rbp+0h]
  __int128 v21; // [rsp+110h] [rbp+10h]
  int v22; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v23[2044]; // [rsp+124h] [rbp+24h] BYREF

  v5 = a2;
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  result = RemoveFromTimerQ(*(_DWORD *)(a1 + 64), a3[2], *((_DWORD *)CpTable + 44 * v5), 0, 0);
  if ( !(_DWORD)v5 )
    result = RemoveFromTimerQ(*(_DWORD *)(a1 + 64), 0, 0, 0, 2);
  if ( *a3 <= 5 )
  {
    if ( *a3 == 5 || (unsigned int)*a3 >= 2 && (*a3 == 2 || (unsigned int)(*a3 - 3) <= 1) )
    {
      result = FsmSendTermAck(a1, (unsigned int)v5, a4);
      goto LABEL_19;
    }
LABEL_13:
    if ( byte_18004CF33 < 0 )
    {
      v9 = *a3;
      LOWORD(v22) = 0;
      result = FormatRRASErrorString(&v22, L"Illegal transition->CfgNakRej received while in %hs state", FsmStates[v9]);
      if ( byte_18004CF33 < 0 )
        result = McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v22);
    }
    goto LABEL_19;
  }
  if ( *a3 == 6 || *a3 == 7 || *a3 == 8 )
  {
    result = FsmSendTermAck(a1, (unsigned int)v5, a4);
    *a3 = 6;
  }
  else
  {
    if ( *a3 != 9 )
      goto LABEL_13;
    result = FsmThisLayerDown(a1, (unsigned int)v5);
    if ( !result )
      return result;
    *((_QWORD *)a3 + 3) = 0;
    *((_QWORD *)a3 + 4) = 0;
    result = FsmSendTermAck(a1, (unsigned int)v5, a4);
    *a3 = 5;
  }
LABEL_19:
  if ( (_DWORD)v5 )
  {
    if ( !a3[10] )
      a3[10] = 736;
    return FsmThisLayerFinished(a1, v5, 0);
  }
  else
  {
    *(_DWORD *)(a1 + 56) |= 0x20000u;
    if ( (*(_BYTE *)(a1 + 56) & 0x20) != 0 )
    {
      if ( (*(_BYTE *)(a1 + 56) & 4) != 0 )
      {
        memset_0(pszDest, 0, 0x84u);
        v17 = *(_DWORD *)(a1 + 188);
        v16 = 1;
        StringCchCopyA(pszDest, 0x81u, (STRSAFE_LPCSTR)(a1 + 1536));
        if ( (byte_18004CF34 & 1) != 0 )
        {
          LOWORD(v22) = 0;
          FormatRRASErrorString(&v22, L"Notifying server to callback at %hs, delay = %d", pszDest, v17);
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v22);
        }
        return NotifyCaller(a1, 21);
      }
    }
    else
    {
      v10 = 734;
      v11 = *(_QWORD *)(a1 + 1472);
      if ( (a4[2] << 8) + a4[3] == 16
        && a4[7] + (a4[4] << 24) + (a4[6] << 8) + (a4[5] << 16) == *(_DWORD *)(v11 + 1440)
        && a4[11] + (a4[8] << 24) + (a4[10] << 8) + (a4[9] << 16) == 3984756 )
      {
        v12 = a4[15] + (a4[12] << 24) + (a4[14] << 8) + (a4[13] << 16);
        if ( v12 <= 0x1004 )
        {
          v10 = 742;
          if ( v12 != 741 )
          {
            if ( v12 == 742 )
              v12 = 741;
            v10 = v12;
          }
        }
      }
      if ( !a3[10] )
        a3[10] = v10;
      *(_OWORD *)plpszSubStringArray = 0;
      v20 = 0;
      v21 = 0;
      if ( (unsigned int)GetLcpOptionStringfromOptions(v11 + 1296) )
      {
        plpszSubStringArray[0] = (LPSTR)(a1 + 1712);
        plpszSubStringArray[1] = "PPP";
        *(_QWORD *)&v20 = "LCP";
        *((_QWORD *)&v20 + 1) = a1 + 1665;
        if ( !*(_DWORD *)(v14 + 8) )
        {
          if ( dword_18004CA20 )
            RouterLogEventA(hLogHandle, 1u, 0x4F34u, 4u, plpszSubStringArray, dwErrorCode);
          if ( byte_18004CF33 < 0 )
          {
            LOWORD(v22) = 0;
            FormatRRASErrorString(
              &v22,
              L"CoId=%hs: Layer=%hs: SubLayer=%hs: The connection attempt failed on port: %hs because of the authenticatio"
               "n protocol selected. Check to see if the authentication protocol is supported in the operating systems at"
               " the client and server ends of the connection %d");
            if ( byte_18004CF33 < 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v22);
          }
        }
      }
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasPppTraceInfo,
          L"LCP Phase: Received Terminate Request");
      if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
      {
        NotifyCallerOfFailure(a1, (unsigned int)a3[10]);
        if ( v10 == 926 || v10 == 932 )
        {
          v15[0] = (LPSTR)(a1 + 1712);
          v15[1] = (LPSTR)(a1 + 1665);
          if ( (unsigned int)dword_18004CA20 > 2 )
            RouterLogEventA(hLogHandle, 4u, (v10 != 926) + 20263, 2u, v15, 0);
        }
      }
      return InsertInTimerQ(*(_DWORD *)(a1 + 64), *(_QWORD *)(a1 + 16), 0, 0, 0, 2, *(_DWORD *)(a1 + 36));
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b310  push    rbp
0x18000b312  push    rbx
0x18000b313  push    rsi
0x18000b314  push    rdi
0x18000b315  push    r14
0x18000b317  push    r15
0x18000b319  lea     rbp, [rsp-838h]
0x18000b321  sub     rsp, 938h
0x18000b328  mov     rax, cs:__security_cookie
0x18000b32f  xor     rax, rsp
0x18000b332  mov     [rbp+860h+var_40], rax
0x18000b339  mov     rsi, r8
0x18000b33c  mov     r14d, edx
0x18000b33f  mov     rbx, rcx
0x18000b342  xor     r15d, r15d
0x18000b345  xor     edx, edx; Val
0x18000b347  mov     [rbp+860h+var_840], r15d
0x18000b34b  mov     r8d, 7FCh; Size
0x18000b351  lea     rcx, [rbp+860h+var_83C]; void *
0x18000b355  mov     rdi, r9
0x18000b358  call    memset_0
0x18000b35d  mov     r8, cs:CpTable
0x18000b364  xor     r9d, r9d
0x18000b367  mov     edx, [rsi+8]
0x18000b36a  imul    rcx, r14, 0B0h
0x18000b371  mov     dword ptr [rsp+960h+plpszSubStringArray], r15d
0x18000b376  mov     r8d, [rcx+r8]
0x18000b37a  mov     ecx, [rbx+40h]
0x18000b37d  call    RemoveFromTimerQ
0x18000b382  test    r14d, r14d
0x18000b385  jnz     short loc_18000B39F
0x18000b387  mov     ecx, [rbx+40h]
0x18000b38a  xor     r9d, r9d
0x18000b38d  xor     r8d, r8d
0x18000b390  mov     dword ptr [rsp+960h+plpszSubStringArray], 2
0x18000b398  xor     edx, edx
0x18000b39a  call    RemoveFromTimerQ
0x18000b39f  cmp     dword ptr [rsi], 5
0x18000b3a2  jg      short loc_18000B3D3
0x18000b3a4  jz      short loc_18000B3C0
0x18000b3a6  mov     ecx, [rsi]
0x18000b3a8  test    ecx, ecx
0x18000b3aa  jz      short loc_18000B3F5
0x18000b3ac  sub     ecx, 1
0x18000b3af  jz      short loc_18000B3F5
0x18000b3b1  sub     ecx, 1
0x18000b3b4  jz      short loc_18000B3C0
0x18000b3b6  sub     ecx, 1
0x18000b3b9  jz      short loc_18000B3C0
0x18000b3bb  cmp     ecx, 1
0x18000b3be  jnz     short loc_18000B3F5
0x18000b3c0  mov     r8, rdi
0x18000b3c3  mov     edx, r14d
0x18000b3c6  mov     rcx, rbx
0x18000b3c9  call    FsmSendTermAck
0x18000b3ce  jmp     loc_18000B48C
0x18000b3d3  mov     ecx, [rsi]
0x18000b3d5  sub     ecx, 6
0x18000b3d8  jz      loc_18000B478
0x18000b3de  sub     ecx, 1
0x18000b3e1  jz      loc_18000B478
0x18000b3e7  sub     ecx, 1
0x18000b3ea  jz      loc_18000B478
0x18000b3f0  cmp     ecx, 1
0x18000b3f3  jz      short loc_18000B447
0x18000b3f5  cmp     cs:byte_18004CF33, r15b
0x18000b3fc  jge     loc_18000B48C
0x18000b402  movsxd  r8, dword ptr [rsi]
0x18000b405  lea     rax, FsmStates
0x18000b40c  lea     rdx, aIllegalTransit_4; "Illegal transition->CfgNakRej received "...
0x18000b413  mov     word ptr [rbp+860h+var_840], r15w
0x18000b418  lea     rcx, [rbp+860h+var_840]
0x18000b41c  mov     r8, [rax+r8*8]
0x18000b420  call    FormatRRASErrorString
0x18000b425  cmp     cs:byte_18004CF33, r15b
0x18000b42c  jge     short loc_18000B48C
0x18000b42e  lea     r8, [rbp+860h+var_840]
0x18000b432  lea     rdx, RasPppTraceError
0x18000b439  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b440  call    McTemplateU0z_EventWriteTransfer
0x18000b445  jmp     short loc_18000B48C
0x18000b447  mov     edx, r14d
0x18000b44a  mov     rcx, rbx
0x18000b44d  call    FsmThisLayerDown
0x18000b452  test    eax, eax
0x18000b454  jz      loc_18000B7D8
0x18000b45a  mov     r8, rdi
0x18000b45d  mov     [rsi+18h], r15
0x18000b461  mov     edx, r14d
0x18000b464  mov     [rsi+20h], r15
0x18000b468  mov     rcx, rbx
0x18000b46b  call    FsmSendTermAck
0x18000b470  mov     dword ptr [rsi], 5
0x18000b476  jmp     short loc_18000B48C
0x18000b478  mov     r8, rdi
0x18000b47b  mov     edx, r14d
0x18000b47e  mov     rcx, rbx
0x18000b481  call    FsmSendTermAck
0x18000b486  mov     dword ptr [rsi], 6
0x18000b48c  test    r14d, r14d
0x18000b48f  jnz     loc_18000B7BD
0x18000b495  bts     dword ptr [rbx+38h], 11h
0x18000b49a  test    byte ptr [rbx+38h], 20h
0x18000b49e  jz      loc_18000B547
0x18000b4a4  test    byte ptr [rbx+38h], 4
0x18000b4a8  jz      loc_18000B7D8
0x18000b4ae  xor     edx, edx; Val
0x18000b4b0  lea     rcx, [rsp+960h+pszDest]; void *
0x18000b4b5  mov     r8d, 84h; Size
0x18000b4bb  call    memset_0
0x18000b4c0  mov     eax, [rbx+0BCh]
0x18000b4c6  lea     r8, [rbx+600h]; pszSrc
0x18000b4cd  mov     edx, 81h; cchDest
0x18000b4d2  mov     [rsp+960h+var_8FC], eax
0x18000b4d6  lea     rcx, [rsp+960h+pszDest]; pszDest
0x18000b4db  mov     [rsp+960h+var_900], 1
0x18000b4e3  call    StringCchCopyA
0x18000b4e8  test    cs:byte_18004CF34, 1
0x18000b4ef  jz      short loc_18000B530
0x18000b4f1  mov     r9d, [rsp+960h+var_8FC]
0x18000b4f6  lea     r8, [rsp+960h+pszDest]
0x18000b4fb  lea     rdx, aNotifyingServe; "Notifying server to callback at %hs, de"...
0x18000b502  mov     word ptr [rbp+860h+var_840], r15w
0x18000b507  lea     rcx, [rbp+860h+var_840]
0x18000b50b  call    FormatRRASErrorString
0x18000b510  test    cs:byte_18004CF34, 1
0x18000b517  jz      short loc_18000B530
0x18000b519  lea     r8, [rbp+860h+var_840]
0x18000b51d  lea     rdx, RasPppTraceInfo
0x18000b524  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b52b  call    McTemplateU0z_EventWriteTransfer
0x18000b530  lea     r8, [rsp+960h+var_900]
0x18000b535  mov     edx, 15h
0x18000b53a  mov     rcx, rbx
0x18000b53d  call    NotifyCaller
0x18000b542  jmp     loc_18000B7D8
0x18000b547  movzx   edx, byte ptr [rdi+2]
0x18000b54b  mov     ecx, 100h
0x18000b550  movzx   r8d, byte ptr [rdi+3]
0x18000b555  mov     r14d, 2DEh
0x18000b55b  mov     r11, [rbx+5C0h]
0x18000b562  imul    edx, ecx
0x18000b565  add     r8w, dx
0x18000b569  cmp     r8w, 10h
0x18000b56e  jnz     loc_18000B5FF
0x18000b574  movzx   ecx, byte ptr [rdi+5]
0x18000b578  movzx   eax, byte ptr [rdi+6]
0x18000b57c  shl     eax, 8
0x18000b57f  shl     ecx, 10h
0x18000b582  add     ecx, eax
0x18000b584  movzx   eax, byte ptr [rdi+4]
0x18000b588  shl     eax, 18h
0x18000b58b  add     ecx, eax
0x18000b58d  movzx   eax, byte ptr [rdi+7]
0x18000b591  add     ecx, eax
0x18000b593  cmp     ecx, [r11+5A0h]
0x18000b59a  jnz     short loc_18000B5FF
0x18000b59c  movzx   ecx, byte ptr [rdi+9]
0x18000b5a0  movzx   eax, byte ptr [rdi+0Ah]
0x18000b5a4  shl     eax, 8
0x18000b5a7  shl     ecx, 10h
0x18000b5aa  add     ecx, eax
0x18000b5ac  movzx   eax, byte ptr [rdi+8]
0x18000b5b0  shl     eax, 18h
0x18000b5b3  add     ecx, eax
0x18000b5b5  movzx   eax, byte ptr [rdi+0Bh]
0x18000b5b9  add     ecx, eax
0x18000b5bb  cmp     ecx, 3CCD74h
0x18000b5c1  jnz     short loc_18000B5FF
0x18000b5c3  movzx   edx, byte ptr [rdi+0Dh]
0x18000b5c7  movzx   eax, byte ptr [rdi+0Eh]
0x18000b5cb  shl     eax, 8
0x18000b5ce  shl     edx, 10h
0x18000b5d1  add     edx, eax
0x18000b5d3  movzx   eax, byte ptr [rdi+0Ch]
0x18000b5d7  shl     eax, 18h
0x18000b5da  add     edx, eax
0x18000b5dc  movzx   eax, byte ptr [rdi+0Fh]
0x18000b5e0  add     edx, eax
0x18000b5e2  cmp     edx, 1004h
0x18000b5e8  ja      short loc_18000B5FF
0x18000b5ea  lea     eax, [r14+7]
0x18000b5ee  lea     r14d, [rax+1]
0x18000b5f2  cmp     edx, eax
0x18000b5f4  jz      short loc_18000B5FF
0x18000b5f6  cmp     edx, r14d
0x18000b5f9  cmovz   edx, eax
0x18000b5fc  mov     r14d, edx
0x18000b5ff  mov     edx, [rsi+28h]
0x18000b602  test    edx, edx
0x18000b604  jnz     short loc_18000B60D
0x18000b606  mov     [rsi+28h], r14d
0x18000b60a  mov     edx, r14d
0x18000b60d  xorps   xmm0, xmm0
0x18000b610  lea     rcx, [r11+510h]
0x18000b617  movups  xmmword ptr [rbp+860h+var_870], xmm0
0x18000b61b  movups  [rbp+860h+var_860], xmm0
0x18000b61f  movups  [rbp+860h+var_850], xmm0
0x18000b623  call    GetLcpOptionStringfromOptions
0x18000b628  test    eax, eax
0x18000b62a  jz      loc_18000B6F7
0x18000b630  lea     r8, [rbx+6B0h]
0x18000b637  lea     r9, aPpp; "PPP"
0x18000b63e  mov     [rbp+860h+var_870], r8
0x18000b642  lea     rcx, aLcp; "LCP"
0x18000b649  mov     [rbp+860h+var_870+8], r9
0x18000b64d  lea     r10, [rbx+681h]
0x18000b654  mov     qword ptr [rbp+860h+var_860], rcx
0x18000b658  mov     qword ptr [rbp+860h+var_860+8], r10
0x18000b65c  cmp     [r11+8], r15d
0x18000b660  jnz     loc_18000B6F7
0x18000b666  cmp     cs:dword_18004CA20, r15d
0x18000b66d  jbe     short loc_18000B6A8
0x18000b66f  mov     rcx, cs:hLogHandle; hLogHandle
0x18000b676  lea     rax, [rbp+860h+var_870]
0x18000b67a  mov     [rsp+960h+dwErrorCode], edx; dwErrorCode
0x18000b67e  mov     r8d, 4F34h; dwMessageId
0x18000b684  mov     edx, 1; dwEventType
0x18000b689  mov     [rsp+960h+plpszSubStringArray], rax; plpszSubStringArray
0x18000b68e  lea     r9d, [rdx+3]; dwSubStringCount
0x18000b692  call    cs:__imp_RouterLogEventA
0x18000b698  mov     r10, qword ptr [rbp+860h+var_860+8]
0x18000b69c  mov     rcx, qword ptr [rbp+860h+var_860]
0x18000b6a0  mov     r9, [rbp+860h+var_870+8]
0x18000b6a4  mov     r8, [rbp+860h+var_870]
0x18000b6a8  cmp     cs:byte_18004CF33, r15b
0x18000b6af  jge     short loc_18000B6F7
0x18000b6b1  mov     eax, [rsi+28h]
0x18000b6b4  lea     rdx, aCoidHsLayerHsS; "CoId=%hs: Layer=%hs: SubLayer=%hs: The "...
0x18000b6bb  mov     [rsp+960h+var_930], eax
0x18000b6bf  mov     qword ptr [rsp+960h+dwErrorCode], r10
0x18000b6c4  mov     [rsp+960h+plpszSubStringArray], rcx
0x18000b6c9  lea     rcx, [rbp+860h+var_840]
0x18000b6cd  mov     word ptr [rbp+860h+var_840], r15w
0x18000b6d2  call    FormatRRASErrorString
0x18000b6d7  cmp     cs:byte_18004CF33, r15b
0x18000b6de  jge     short loc_18000B6F7
0x18000b6e0  lea     r8, [rbp+860h+var_840]
0x18000b6e4  lea     rdx, RasPppTraceError
0x18000b6eb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b6f2  call    McTemplateU0z_EventWriteTransfer
0x18000b6f7  test    cs:byte_18004CF34, 1
0x18000b6fe  jz      short loc_18000B71A
0x18000b700  lea     r8, aLcpPhaseReceiv; "LCP Phase: Received Terminate Request"
0x18000b707  lea     rdx, RasPppTraceInfo
0x18000b70e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b715  call    McTemplateU0z_EventWriteTransfer
0x18000b71a  test    byte ptr [rbx+38h], 4
0x18000b71e  jnz     short loc_18000B795
0x18000b720  mov     edx, [rsi+28h]
0x18000b723  mov     rcx, rbx
0x18000b726  call    NotifyCallerOfFailure
0x18000b72b  mov     ecx, 39Eh
0x18000b730  cmp     r14d, ecx
0x18000b733  jz      short loc_18000B73E
0x18000b735  cmp     r14d, 3A4h
0x18000b73c  jnz     short loc_18000B795
0x18000b73e  cmp     cs:dword_18004CA20, 2
0x18000b745  lea     rax, [rbx+6B0h]
0x18000b74c  mov     [rsp+960h+var_918], rax
0x18000b751  lea     rax, [rbx+681h]
0x18000b758  mov     [rsp+960h+var_910], rax
0x18000b75d  jbe     short loc_18000B795
0x18000b75f  cmp     r14d, ecx
0x18000b762  mov     [rsp+960h+dwErrorCode], r15d; dwErrorCode
0x18000b767  mov     rcx, cs:hLogHandle; hLogHandle
0x18000b76e  lea     rax, [rsp+960h+var_918]
0x18000b773  mov     r8d, r15d
0x18000b776  mov     [rsp+960h+plpszSubStringArray], rax; plpszSubStringArray
0x18000b77b  mov     edx, 4; dwEventType
0x18000b780  setnz   r8b
0x18000b784  add     r8d, 4F27h; dwMessageId
0x18000b78b  lea     r9d, [rdx-2]; dwSubStringCount
0x18000b78f  call    cs:__imp_RouterLogEventA
0x18000b795  mov     eax, [rbx+24h]
0x18000b798  xor     r9d, r9d
0x18000b79b  mov     rdx, [rbx+10h]
0x18000b79f  xor     r8d, r8d
0x18000b7a2  mov     ecx, [rbx+40h]
0x18000b7a5  mov     [rsp+960h+var_930], eax
0x18000b7a9  mov     [rsp+960h+dwErrorCode], 2
0x18000b7b1  mov     dword ptr [rsp+960h+plpszSubStringArray], r15d
0x18000b7b6  call    InsertInTimerQ
0x18000b7bb  jmp     short loc_18000B7D8
0x18000b7bd  cmp     [rsi+28h], r15d
0x18000b7c1  jnz     short loc_18000B7CA
0x18000b7c3  mov     dword ptr [rsi+28h], 2E0h
0x18000b7ca  xor     r8d, r8d
0x18000b7cd  mov     edx, r14d
0x18000b7d0  mov     rcx, rbx
0x18000b7d3  call    FsmThisLayerFinished
0x18000b7d8  mov     rcx, [rbp+860h+var_40]
0x18000b7df  xor     rcx, rsp; StackCookie
0x18000b7e2  call    __security_check_cookie
0x18000b7e7  add     rsp, 938h
0x18000b7ee  pop     r15
0x18000b7f0  pop     r14
0x18000b7f2  pop     rdi
0x18000b7f3  pop     rsi
0x18000b7f4  pop     rbx
  ... truncated ...
```
