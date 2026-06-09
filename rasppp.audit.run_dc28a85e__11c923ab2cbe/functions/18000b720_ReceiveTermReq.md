# ReceiveTermReq

- ea: `0x18000b720`
- end: `0x18000bc14`
- name: `ReceiveTermReq`
- size: `1268`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180006954`
- `0x18000b720`
- `0x18000bdd0`
- `0x18000e298`
- `0x18000e540`
- `0x18000e7a4`
- `0x18000f780`
- `0x18000f984`
- `0x18001348c`
- `0x180013b54`
- `0x18002b0dc`

## import_xrefs

- `rtutils!RouterLogEventA` at `0x18000baa2`
- `rtutils!RouterLogEventA` at `0x18000bba5`
- `rtutils!RouterLogEventA` at `0x18000baa2`
- `rtutils!RouterLogEventA` at `0x18000bba5`

## string_xrefs

- `0x18000baca`: `CoId=%hs: Layer=%hs: SubLayer=%hs: The connection attempt failed on port: %hs because of the authentication protocol selected. Check to see if the authentication protocol is supported in the operating systems at the client and server ends of the connection %d`

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
    if ( byte_18004DF33 < 0 )
    {
      v9 = *a3;
      LOWORD(v22) = 0;
      result = FormatRRASErrorString(&v22, L"Illegal transition->CfgNakRej received while in %hs state", FsmStates[v9]);
      if ( byte_18004DF33 < 0 )
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
        if ( (byte_18004DF34 & 1) != 0 )
        {
          LOWORD(v22) = 0;
          FormatRRASErrorString(&v22, L"Notifying server to callback at %hs, delay = %d", pszDest, v17);
          if ( (byte_18004DF34 & 1) != 0 )
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
          if ( dword_18004DA20 )
            RouterLogEventA(hLogHandle, 1u, 0x4F34u, 4u, plpszSubStringArray, dwErrorCode);
          if ( byte_18004DF33 < 0 )
          {
            LOWORD(v22) = 0;
            FormatRRASErrorString(
              &v22,
              L"CoId=%hs: Layer=%hs: SubLayer=%hs: The connection attempt failed on port: %hs because of the authenticatio"
               "n protocol selected. Check to see if the authentication protocol is supported in the operating systems at"
               " the client and server ends of the connection %d");
            if ( byte_18004DF33 < 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v22);
          }
        }
      }
      if ( (byte_18004DF34 & 1) != 0 )
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
          if ( (unsigned int)dword_18004DA20 > 2 )
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
0x18000b720  push    rbp
0x18000b722  push    rbx
0x18000b723  push    rsi
0x18000b724  push    rdi
0x18000b725  push    r14
0x18000b727  push    r15
0x18000b729  lea     rbp, [rsp-838h]
0x18000b731  sub     rsp, 938h
0x18000b738  mov     rax, cs:__security_cookie
0x18000b73f  xor     rax, rsp
0x18000b742  mov     [rbp+860h+var_40], rax
0x18000b749  mov     rsi, r8
0x18000b74c  mov     r14d, edx
0x18000b74f  mov     rbx, rcx
0x18000b752  xor     r15d, r15d
0x18000b755  xor     edx, edx; Val
0x18000b757  mov     [rbp+860h+var_840], r15d
0x18000b75b  mov     r8d, 7FCh; Size
0x18000b761  lea     rcx, [rbp+860h+var_83C]; void *
0x18000b765  mov     rdi, r9
0x18000b768  call    memset_0
0x18000b76d  mov     r8, cs:CpTable
0x18000b774  xor     r9d, r9d
0x18000b777  mov     edx, [rsi+8]
0x18000b77a  imul    rcx, r14, 0B0h
0x18000b781  mov     dword ptr [rsp+960h+plpszSubStringArray], r15d
0x18000b786  mov     r8d, [rcx+r8]
0x18000b78a  mov     ecx, [rbx+40h]
0x18000b78d  call    RemoveFromTimerQ
0x18000b792  test    r14d, r14d
0x18000b795  jnz     short loc_18000B7AF
0x18000b797  mov     ecx, [rbx+40h]
0x18000b79a  xor     r9d, r9d
0x18000b79d  xor     r8d, r8d
0x18000b7a0  mov     dword ptr [rsp+960h+plpszSubStringArray], 2
0x18000b7a8  xor     edx, edx
0x18000b7aa  call    RemoveFromTimerQ
0x18000b7af  cmp     dword ptr [rsi], 5
0x18000b7b2  jg      short loc_18000B7E3
0x18000b7b4  jz      short loc_18000B7D0
0x18000b7b6  mov     ecx, [rsi]
0x18000b7b8  test    ecx, ecx
0x18000b7ba  jz      short loc_18000B805
0x18000b7bc  sub     ecx, 1
0x18000b7bf  jz      short loc_18000B805
0x18000b7c1  sub     ecx, 1
0x18000b7c4  jz      short loc_18000B7D0
0x18000b7c6  sub     ecx, 1
0x18000b7c9  jz      short loc_18000B7D0
0x18000b7cb  cmp     ecx, 1
0x18000b7ce  jnz     short loc_18000B805
0x18000b7d0  mov     r8, rdi
0x18000b7d3  mov     edx, r14d
0x18000b7d6  mov     rcx, rbx
0x18000b7d9  call    FsmSendTermAck
0x18000b7de  jmp     loc_18000B89C
0x18000b7e3  mov     ecx, [rsi]
0x18000b7e5  sub     ecx, 6
0x18000b7e8  jz      loc_18000B888
0x18000b7ee  sub     ecx, 1
0x18000b7f1  jz      loc_18000B888
0x18000b7f7  sub     ecx, 1
0x18000b7fa  jz      loc_18000B888
0x18000b800  cmp     ecx, 1
0x18000b803  jz      short loc_18000B857
0x18000b805  cmp     cs:byte_18004DF33, r15b
0x18000b80c  jge     loc_18000B89C
0x18000b812  movsxd  r8, dword ptr [rsi]
0x18000b815  lea     rax, FsmStates
0x18000b81c  lea     rdx, aIllegalTransit_4; "Illegal transition->CfgNakRej received "...
0x18000b823  mov     word ptr [rbp+860h+var_840], r15w
0x18000b828  lea     rcx, [rbp+860h+var_840]
0x18000b82c  mov     r8, [rax+r8*8]
0x18000b830  call    FormatRRASErrorString
0x18000b835  cmp     cs:byte_18004DF33, r15b
0x18000b83c  jge     short loc_18000B89C
0x18000b83e  lea     r8, [rbp+860h+var_840]
0x18000b842  lea     rdx, RasPppTraceError
0x18000b849  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b850  call    McTemplateU0z_EventWriteTransfer
0x18000b855  jmp     short loc_18000B89C
0x18000b857  mov     edx, r14d
0x18000b85a  mov     rcx, rbx
0x18000b85d  call    FsmThisLayerDown
0x18000b862  test    eax, eax
0x18000b864  jz      loc_18000BBF4
0x18000b86a  mov     r8, rdi
0x18000b86d  mov     [rsi+18h], r15
0x18000b871  mov     edx, r14d
0x18000b874  mov     [rsi+20h], r15
0x18000b878  mov     rcx, rbx
0x18000b87b  call    FsmSendTermAck
0x18000b880  mov     dword ptr [rsi], 5
0x18000b886  jmp     short loc_18000B89C
0x18000b888  mov     r8, rdi
0x18000b88b  mov     edx, r14d
0x18000b88e  mov     rcx, rbx
0x18000b891  call    FsmSendTermAck
0x18000b896  mov     dword ptr [rsi], 6
0x18000b89c  test    r14d, r14d
0x18000b89f  jnz     loc_18000BBD9
0x18000b8a5  bts     dword ptr [rbx+38h], 11h
0x18000b8aa  test    byte ptr [rbx+38h], 20h
0x18000b8ae  jz      loc_18000B957
0x18000b8b4  test    byte ptr [rbx+38h], 4
0x18000b8b8  jz      loc_18000BBF4
0x18000b8be  xor     edx, edx; Val
0x18000b8c0  lea     rcx, [rsp+960h+pszDest]; void *
0x18000b8c5  mov     r8d, 84h; Size
0x18000b8cb  call    memset_0
0x18000b8d0  mov     eax, [rbx+0BCh]
0x18000b8d6  lea     r8, [rbx+600h]; pszSrc
0x18000b8dd  mov     edx, 81h; cchDest
0x18000b8e2  mov     [rsp+960h+var_8FC], eax
0x18000b8e6  lea     rcx, [rsp+960h+pszDest]; pszDest
0x18000b8eb  mov     [rsp+960h+var_900], 1
0x18000b8f3  call    StringCchCopyA
0x18000b8f8  test    cs:byte_18004DF34, 1
0x18000b8ff  jz      short loc_18000B940
0x18000b901  mov     r9d, [rsp+960h+var_8FC]
0x18000b906  lea     r8, [rsp+960h+pszDest]
0x18000b90b  lea     rdx, aNotifyingServe; "Notifying server to callback at %hs, de"...
0x18000b912  mov     word ptr [rbp+860h+var_840], r15w
0x18000b917  lea     rcx, [rbp+860h+var_840]
0x18000b91b  call    FormatRRASErrorString
0x18000b920  test    cs:byte_18004DF34, 1
0x18000b927  jz      short loc_18000B940
0x18000b929  lea     r8, [rbp+860h+var_840]
0x18000b92d  lea     rdx, RasPppTraceInfo
0x18000b934  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b93b  call    McTemplateU0z_EventWriteTransfer
0x18000b940  lea     r8, [rsp+960h+var_900]
0x18000b945  mov     edx, 15h
0x18000b94a  mov     rcx, rbx
0x18000b94d  call    NotifyCaller
0x18000b952  jmp     loc_18000BBF4
0x18000b957  movzx   edx, byte ptr [rdi+2]
0x18000b95b  mov     ecx, 100h
0x18000b960  movzx   r8d, byte ptr [rdi+3]
0x18000b965  mov     r14d, 2DEh
0x18000b96b  mov     r11, [rbx+5C0h]
0x18000b972  imul    edx, ecx
0x18000b975  add     r8w, dx
0x18000b979  cmp     r8w, 10h
0x18000b97e  jnz     loc_18000BA0F
0x18000b984  movzx   ecx, byte ptr [rdi+5]
0x18000b988  movzx   eax, byte ptr [rdi+6]
0x18000b98c  shl     eax, 8
0x18000b98f  shl     ecx, 10h
0x18000b992  add     ecx, eax
0x18000b994  movzx   eax, byte ptr [rdi+4]
0x18000b998  shl     eax, 18h
0x18000b99b  add     ecx, eax
0x18000b99d  movzx   eax, byte ptr [rdi+7]
0x18000b9a1  add     ecx, eax
0x18000b9a3  cmp     ecx, [r11+5A0h]
0x18000b9aa  jnz     short loc_18000BA0F
0x18000b9ac  movzx   ecx, byte ptr [rdi+9]
0x18000b9b0  movzx   eax, byte ptr [rdi+0Ah]
0x18000b9b4  shl     eax, 8
0x18000b9b7  shl     ecx, 10h
0x18000b9ba  add     ecx, eax
0x18000b9bc  movzx   eax, byte ptr [rdi+8]
0x18000b9c0  shl     eax, 18h
0x18000b9c3  add     ecx, eax
0x18000b9c5  movzx   eax, byte ptr [rdi+0Bh]
0x18000b9c9  add     ecx, eax
0x18000b9cb  cmp     ecx, 3CCD74h
0x18000b9d1  jnz     short loc_18000BA0F
0x18000b9d3  movzx   edx, byte ptr [rdi+0Dh]
0x18000b9d7  movzx   eax, byte ptr [rdi+0Eh]
0x18000b9db  shl     eax, 8
0x18000b9de  shl     edx, 10h
0x18000b9e1  add     edx, eax
0x18000b9e3  movzx   eax, byte ptr [rdi+0Ch]
0x18000b9e7  shl     eax, 18h
0x18000b9ea  add     edx, eax
0x18000b9ec  movzx   eax, byte ptr [rdi+0Fh]
0x18000b9f0  add     edx, eax
0x18000b9f2  cmp     edx, 1004h
0x18000b9f8  ja      short loc_18000BA0F
0x18000b9fa  lea     eax, [r14+7]
0x18000b9fe  lea     r14d, [rax+1]
0x18000ba02  cmp     edx, eax
0x18000ba04  jz      short loc_18000BA0F
0x18000ba06  cmp     edx, r14d
0x18000ba09  cmovz   edx, eax
0x18000ba0c  mov     r14d, edx
0x18000ba0f  mov     edx, [rsi+28h]
0x18000ba12  test    edx, edx
0x18000ba14  jnz     short loc_18000BA1D
0x18000ba16  mov     [rsi+28h], r14d
0x18000ba1a  mov     edx, r14d
0x18000ba1d  xorps   xmm0, xmm0
0x18000ba20  lea     rcx, [r11+510h]
0x18000ba27  movups  xmmword ptr [rbp+860h+var_870], xmm0
0x18000ba2b  movups  [rbp+860h+var_860], xmm0
0x18000ba2f  movups  [rbp+860h+var_850], xmm0
0x18000ba33  call    GetLcpOptionStringfromOptions
0x18000ba38  test    eax, eax
0x18000ba3a  jz      loc_18000BB0D
0x18000ba40  lea     r8, [rbx+6B0h]
0x18000ba47  lea     r9, aPpp; "PPP"
0x18000ba4e  mov     [rbp+860h+var_870], r8
0x18000ba52  lea     rcx, aLcp; "LCP"
0x18000ba59  mov     [rbp+860h+var_870+8], r9
0x18000ba5d  lea     r10, [rbx+681h]
0x18000ba64  mov     qword ptr [rbp+860h+var_860], rcx
0x18000ba68  mov     qword ptr [rbp+860h+var_860+8], r10
0x18000ba6c  cmp     [r11+8], r15d
0x18000ba70  jnz     loc_18000BB0D
0x18000ba76  cmp     cs:dword_18004DA20, r15d
0x18000ba7d  jbe     short loc_18000BABE
0x18000ba7f  mov     rcx, cs:hLogHandle; hLogHandle
0x18000ba86  lea     rax, [rbp+860h+var_870]
0x18000ba8a  mov     [rsp+960h+dwErrorCode], edx; dwErrorCode
0x18000ba8e  mov     r8d, 4F34h; dwMessageId
0x18000ba94  mov     edx, 1; dwEventType
0x18000ba99  mov     [rsp+960h+plpszSubStringArray], rax; plpszSubStringArray
0x18000ba9e  lea     r9d, [rdx+3]; dwSubStringCount
0x18000baa2  call    cs:__imp_RouterLogEventA
0x18000baa9  nop     dword ptr [rax+rax+00h]
0x18000baae  mov     r10, qword ptr [rbp+860h+var_860+8]
0x18000bab2  mov     rcx, qword ptr [rbp+860h+var_860]
0x18000bab6  mov     r9, [rbp+860h+var_870+8]
0x18000baba  mov     r8, [rbp+860h+var_870]
0x18000babe  cmp     cs:byte_18004DF33, r15b
0x18000bac5  jge     short loc_18000BB0D
0x18000bac7  mov     eax, [rsi+28h]
0x18000baca  lea     rdx, aCoidHsLayerHsS; "CoId=%hs: Layer=%hs: SubLayer=%hs: The "...
0x18000bad1  mov     [rsp+960h+var_930], eax
0x18000bad5  mov     qword ptr [rsp+960h+dwErrorCode], r10
0x18000bada  mov     [rsp+960h+plpszSubStringArray], rcx
0x18000badf  lea     rcx, [rbp+860h+var_840]
0x18000bae3  mov     word ptr [rbp+860h+var_840], r15w
0x18000bae8  call    FormatRRASErrorString
0x18000baed  cmp     cs:byte_18004DF33, r15b
0x18000baf4  jge     short loc_18000BB0D
0x18000baf6  lea     r8, [rbp+860h+var_840]
0x18000bafa  lea     rdx, RasPppTraceError
0x18000bb01  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bb08  call    McTemplateU0z_EventWriteTransfer
0x18000bb0d  test    cs:byte_18004DF34, 1
0x18000bb14  jz      short loc_18000BB30
0x18000bb16  lea     r8, aLcpPhaseReceiv; "LCP Phase: Received Terminate Request"
0x18000bb1d  lea     rdx, RasPppTraceInfo
0x18000bb24  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bb2b  call    McTemplateU0z_EventWriteTransfer
0x18000bb30  test    byte ptr [rbx+38h], 4
0x18000bb34  jnz     short loc_18000BBB1
0x18000bb36  mov     edx, [rsi+28h]
0x18000bb39  mov     rcx, rbx
0x18000bb3c  call    NotifyCallerOfFailure
0x18000bb41  mov     ecx, 39Eh
0x18000bb46  cmp     r14d, ecx
0x18000bb49  jz      short loc_18000BB54
0x18000bb4b  cmp     r14d, 3A4h
0x18000bb52  jnz     short loc_18000BBB1
0x18000bb54  cmp     cs:dword_18004DA20, 2
0x18000bb5b  lea     rax, [rbx+6B0h]
0x18000bb62  mov     [rsp+960h+var_918], rax
0x18000bb67  lea     rax, [rbx+681h]
0x18000bb6e  mov     [rsp+960h+var_910], rax
0x18000bb73  jbe     short loc_18000BBB1
0x18000bb75  cmp     r14d, ecx
0x18000bb78  mov     [rsp+960h+dwErrorCode], r15d; dwErrorCode
0x18000bb7d  mov     rcx, cs:hLogHandle; hLogHandle
0x18000bb84  lea     rax, [rsp+960h+var_918]
0x18000bb89  mov     r8d, r15d
0x18000bb8c  mov     [rsp+960h+plpszSubStringArray], rax; plpszSubStringArray
0x18000bb91  mov     edx, 4; dwEventType
0x18000bb96  setnz   r8b
0x18000bb9a  add     r8d, 4F27h; dwMessageId
0x18000bba1  lea     r9d, [rdx-2]; dwSubStringCount
0x18000bba5  call    cs:__imp_RouterLogEventA
0x18000bbac  nop     dword ptr [rax+rax+00h]
0x18000bbb1  mov     eax, [rbx+24h]
0x18000bbb4  xor     r9d, r9d
0x18000bbb7  mov     rdx, [rbx+10h]
0x18000bbbb  xor     r8d, r8d
0x18000bbbe  mov     ecx, [rbx+40h]
0x18000bbc1  mov     [rsp+960h+var_930], eax
0x18000bbc5  mov     [rsp+960h+dwErrorCode], 2
0x18000bbcd  mov     dword ptr [rsp+960h+plpszSubStringArray], r15d
0x18000bbd2  call    InsertInTimerQ
0x18000bbd7  jmp     short loc_18000BBF4
0x18000bbd9  cmp     [rsi+28h], r15d
0x18000bbdd  jnz     short loc_18000BBE6
0x18000bbdf  mov     dword ptr [rsi+28h], 2E0h
0x18000bbe6  xor     r8d, r8d
0x18000bbe9  mov     edx, r14d
0x18000bbec  mov     rcx, rbx
0x18000bbef  call    FsmThisLayerFinished
0x18000bbf4  mov     rcx, [rbp+860h+var_40]
0x18000bbfb  xor     rcx, rsp; StackCookie
0x18000bbfe  call    __security_check_cookie
0x18000bc03  add     rsp, 938h
0x18000bc0a  pop     r15
0x18000bc0c  pop     r14
0x18000bc0e  pop     rdi
  ... truncated ...
```
