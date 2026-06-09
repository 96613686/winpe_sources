# IkeGetMsTcpipProtocolInfo

- ea: `0x1800017b0`
- end: `0x1800019e5`
- name: `IkeGetMsTcpipProtocolInfo`
- size: `565`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006fc4c`
- `0x180070044`

## callees

- `0x1800017b0`
- `0x1800037c4`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x18004aa3c`
- `0x180050850`

## import_xrefs

- `WS2_32!WSCEnumProtocols` at `0x18000182a`
- `WS2_32!WSCEnumProtocols` at `0x180001875`
- `WS2_32!WSCEnumProtocols` at `0x18000182a`
- `WS2_32!WSCEnumProtocols` at `0x180001875`

## string_xrefs

- `0x1800017f9`: `IkeGetMsTcpipProtocolInfo`
- `0x180001984`: `IkeGetMsTcpipProtocolInfo`
- `0x1800019a7`: `IkeGetMsTcpipProtocolInfo`
- `0x1800019b3`: `IkeGetMsTcpipProtocolInfo`
- `0x18000188c`: `WSCEnumProtocols`

## pseudocode

```c
__int64 __fastcall IkeGetMsTcpipProtocolInfo(int a1, __int64 a2, __int64 a3, _OWORD *a4)
{
  __int64 *v6; // r14
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdi
  LPWSAPROTOCOL_INFOW v11; // rsi
  int v12; // r10d
  const char *v13; // rdx
  int i; // edx
  struct _WSAPROTOCOL_INFOW *v15; // rax
  __int64 v16; // rcx
  __int128 v17; // xmm1
  LPWSAPROTOCOL_INFOW lpProtocolBuffer; // [rsp+20h] [rbp-20h] BYREF
  int Errno; // [rsp+28h] [rbp-18h] BYREF
  DWORD dwBufferLength; // [rsp+2Ch] [rbp-14h] BYREF

  Errno = 0;
  lpProtocolBuffer = 0;
  dwBufferLength = 0;
  TraceLogHelper("IkeGetMsTcpipProtocolInfo", 1);
  v6 = qword_180121378;
  if ( a1 != 2 )
    v6 = qword_180121388;
  v7 = WSCEnumProtocols(0, 0, &dwBufferLength, &Errno);
  v9 = (unsigned int)Errno;
  if ( v7 != -1 || Errno != 10055 )
  {
    if ( Errno )
    {
LABEL_8:
      v13 = "WSCEnumProtocols";
LABEL_25:
      v10 = WfpReportSysErrorAsWinError(v8, v13, v9, 1);
      goto LABEL_26;
    }
LABEL_24:
    v13 = "IkeGetMsTcpipProtocolInfo";
    v9 = 1168;
    goto LABEL_25;
  }
  v10 = WfpMemAlloc(dwBufferLength, 0, &lpProtocolBuffer);
  if ( !v10 )
  {
    v11 = lpProtocolBuffer;
    v12 = WSCEnumProtocols(0, lpProtocolBuffer, &dwBufferLength, &Errno);
    if ( v12 == -1 )
    {
      v9 = (unsigned int)Errno;
      if ( Errno )
        goto LABEL_8;
    }
    for ( i = 0; i < v12; ++i )
    {
      v15 = &v11[i];
      if ( v15->ProtocolChain.ChainLen == 1
        && v15->iAddressFamily == a1
        && v15->iSocketType == 2
        && v15->iProtocol == 17 )
      {
        v8 = *(_QWORD *)&v15->ProviderId.Data1 - *v6;
        if ( !v8 )
          v8 = *(_QWORD *)v15->ProviderId.Data4 - v6[1];
        if ( !v8 )
        {
          if ( !v15 )
            goto LABEL_24;
          v16 = 4;
          do
          {
            *a4 = *(_OWORD *)&v15->dwServiceFlags1;
            a4[1] = *(_OWORD *)&v15->dwProviderFlags;
            a4[2] = *(_OWORD *)&v15->ProviderId.Data4[4];
            a4[3] = *(_OWORD *)&v15->ProtocolChain.ChainEntries[1];
            a4[4] = *(_OWORD *)&v15->ProtocolChain.ChainEntries[5];
            a4[5] = *(_OWORD *)&v15->iMaxSockAddr;
            a4[6] = *(_OWORD *)&v15->iProtocolMaxOffset;
            v17 = *(_OWORD *)&v15->dwProviderReserved;
            v15 = (struct _WSAPROTOCOL_INFOW *)((char *)v15 + 128);
            a4[7] = v17;
            a4 += 8;
            --v16;
          }
          while ( v16 );
          *a4 = *(_OWORD *)&v15->dwServiceFlags1;
          a4[1] = *(_OWORD *)&v15->dwProviderFlags;
          a4[2] = *(_OWORD *)&v15->ProviderId.Data4[4];
          a4[3] = *(_OWORD *)&v15->ProtocolChain.ChainEntries[1];
          a4[4] = *(_OWORD *)&v15->ProtocolChain.ChainEntries[5];
          a4[5] = *(_OWORD *)&v15->iMaxSockAddr;
          a4[6] = *(_OWORD *)&v15->iProtocolMaxOffset;
          *((_DWORD *)a4 + 28) = v15->dwProviderReserved;
          goto LABEL_26;
        }
      }
    }
    goto LABEL_24;
  }
LABEL_26:
  WfpMemFree((LPCVOID *)&lpProtocolBuffer);
  TraceLogHelper("IkeGetMsTcpipProtocolInfo", 0);
  return IkeReturnError(v10, "IkeGetMsTcpipProtocolInfo");
}

```

## disassembly

```asm
0x1800017b0  mov     [rsp-28h+arg_0], rbx
0x1800017b5  mov     [rsp-28h+arg_8], rsi
0x1800017ba  push    rbp
0x1800017bb  push    rdi
0x1800017bc  push    r13
0x1800017be  push    r14
0x1800017c0  push    r15
0x1800017c2  mov     rbp, rsp
0x1800017c5  sub     rsp, 40h
0x1800017c9  mov     rax, cs:__security_cookie
0x1800017d0  xor     rax, rsp
0x1800017d3  mov     [rbp+var_10], rax
0x1800017d7  mov     r15d, ecx
0x1800017da  mov     [rbp+Errno], 0
0x1800017e1  mov     r13d, 1
0x1800017e7  mov     [rbp+lpProtocolBuffer], 0
0x1800017ef  mov     edx, r13d
0x1800017f2  mov     [rbp+dwBufferLength], 0
0x1800017f9  lea     rcx, aIkegetmstcpipp; "IkeGetMsTcpipProtocolInfo"
0x180001800  mov     rbx, r9
0x180001803  call    TraceLogHelper
0x180001808  lea     rax, qword_180121388
0x18000180f  cmp     r15d, 2
0x180001813  lea     r14, qword_180121378
0x18000181a  cmovnz  r14, rax
0x18000181e  lea     r9, [rbp+Errno]; lpErrno
0x180001822  xor     edx, edx; lpProtocolBuffer
0x180001824  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x180001828  xor     ecx, ecx; lpiProtocols
0x18000182a  call    cs:__imp_WSCEnumProtocols
0x180001830  mov     r8d, [rbp+Errno]
0x180001834  cmp     eax, 0FFFFFFFFh
0x180001837  jnz     loc_18000197B
0x18000183d  cmp     r8d, 2747h
0x180001844  jnz     loc_18000197B
0x18000184a  mov     ecx, [rbp+dwBufferLength]; dwBytes
0x18000184d  lea     r8, [rbp+lpProtocolBuffer]
0x180001851  xor     edx, edx; dwFlags
0x180001853  call    WfpMemAlloc
0x180001858  mov     rdi, rax
0x18000185b  test    rax, rax
0x18000185e  jnz     loc_18000199C
0x180001864  mov     rsi, [rbp+lpProtocolBuffer]
0x180001868  lea     r9, [rbp+Errno]; lpErrno
0x18000186c  mov     rdx, rsi; lpProtocolBuffer
0x18000186f  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x180001873  xor     ecx, ecx; lpiProtocols
0x180001875  call    cs:__imp_WSCEnumProtocols
0x18000187b  mov     r10d, eax
0x18000187e  cmp     eax, 0FFFFFFFFh
0x180001881  jnz     short loc_180001898
0x180001883  mov     r8d, [rbp+Errno]
0x180001887  test    r8d, r8d
0x18000188a  jz      short loc_180001898
0x18000188c  lea     rdx, aWscenumprotoco; "WSCEnumProtocols"
0x180001893  jmp     loc_180001991
0x180001898  xor     edx, edx
0x18000189a  cmp     edx, r10d
0x18000189d  jge     loc_180001984
0x1800018a3  movsxd  rax, edx
0x1800018a6  imul    rax, 274h
0x1800018ad  add     rax, rsi
0x1800018b0  cmp     [rax+28h], r13d
0x1800018b4  jnz     short loc_1800018DE
0x1800018b6  cmp     [rax+4Ch], r15d
0x1800018ba  jnz     short loc_1800018DE
0x1800018bc  cmp     dword ptr [rax+58h], 2
0x1800018c0  jnz     short loc_1800018DE
0x1800018c2  cmp     dword ptr [rax+5Ch], 11h
0x1800018c6  jnz     short loc_1800018DE
0x1800018c8  mov     rcx, [rax+14h]
0x1800018cc  sub     rcx, [r14]
0x1800018cf  jnz     short loc_1800018D9
0x1800018d1  mov     rcx, [rax+1Ch]
0x1800018d5  sub     rcx, [r14+8]
0x1800018d9  test    rcx, rcx
0x1800018dc  jz      short loc_1800018E3
0x1800018de  add     edx, r13d
0x1800018e1  jmp     short loc_18000189A
0x1800018e3  test    rax, rax
0x1800018e6  jz      loc_180001984
0x1800018ec  mov     ecx, 4
0x1800018f1  lea     edx, [rcx+7Ch]
0x1800018f4  movups  xmm0, xmmword ptr [rax]
0x1800018f7  movups  xmmword ptr [rbx], xmm0
0x1800018fa  movups  xmm1, xmmword ptr [rax+10h]
0x1800018fe  movups  xmmword ptr [rbx+10h], xmm1
0x180001902  movups  xmm0, xmmword ptr [rax+20h]
0x180001906  movups  xmmword ptr [rbx+20h], xmm0
0x18000190a  movups  xmm1, xmmword ptr [rax+30h]
0x18000190e  movups  xmmword ptr [rbx+30h], xmm1
0x180001912  movups  xmm0, xmmword ptr [rax+40h]
0x180001916  movups  xmmword ptr [rbx+40h], xmm0
0x18000191a  movups  xmm1, xmmword ptr [rax+50h]
0x18000191e  movups  xmmword ptr [rbx+50h], xmm1
0x180001922  movups  xmm0, xmmword ptr [rax+60h]
0x180001926  movups  xmmword ptr [rbx+60h], xmm0
0x18000192a  movups  xmm1, xmmword ptr [rax+70h]
0x18000192e  add     rax, rdx
0x180001931  movups  xmmword ptr [rbx+70h], xmm1
0x180001935  add     rbx, rdx
0x180001938  sub     rcx, r13
0x18000193b  jnz     short loc_1800018F4
0x18000193d  movups  xmm0, xmmword ptr [rax]
0x180001940  movups  xmmword ptr [rbx], xmm0
0x180001943  movups  xmm1, xmmword ptr [rax+10h]
0x180001947  movups  xmmword ptr [rbx+10h], xmm1
0x18000194b  movups  xmm0, xmmword ptr [rax+20h]
0x18000194f  movups  xmmword ptr [rbx+20h], xmm0
0x180001953  movups  xmm1, xmmword ptr [rax+30h]
0x180001957  movups  xmmword ptr [rbx+30h], xmm1
0x18000195b  movups  xmm0, xmmword ptr [rax+40h]
0x18000195f  movups  xmmword ptr [rbx+40h], xmm0
0x180001963  movups  xmm1, xmmword ptr [rax+50h]
0x180001967  movups  xmmword ptr [rbx+50h], xmm1
0x18000196b  movups  xmm0, xmmword ptr [rax+60h]
0x18000196f  movups  xmmword ptr [rbx+60h], xmm0
0x180001973  mov     eax, [rax+70h]
0x180001976  mov     [rbx+70h], eax
0x180001979  jmp     short loc_18000199C
0x18000197b  test    r8d, r8d
0x18000197e  jnz     loc_18000188C
0x180001984  lea     rdx, aIkegetmstcpipp; "IkeGetMsTcpipProtocolInfo"
0x18000198b  mov     r8d, 490h
0x180001991  mov     r9d, r13d
0x180001994  call    WfpReportSysErrorAsWinError
0x180001999  mov     rdi, rax
0x18000199c  lea     rcx, [rbp+lpProtocolBuffer]
0x1800019a0  call    WfpMemFree
0x1800019a5  xor     edx, edx
0x1800019a7  lea     rcx, aIkegetmstcpipp; "IkeGetMsTcpipProtocolInfo"
0x1800019ae  call    TraceLogHelper
0x1800019b3  lea     rdx, aIkegetmstcpipp; "IkeGetMsTcpipProtocolInfo"
0x1800019ba  mov     rcx, rdi
0x1800019bd  call    IkeReturnError
0x1800019c2  mov     rcx, [rbp+var_10]
0x1800019c6  xor     rcx, rsp; StackCookie
0x1800019c9  call    __security_check_cookie
0x1800019ce  mov     rbx, [rsp+40h+arg_0]
0x1800019d3  mov     rsi, [rsp+40h+arg_8]
0x1800019d8  add     rsp, 40h
0x1800019dc  pop     r15
0x1800019de  pop     r14
0x1800019e0  pop     r13
0x1800019e2  pop     rdi
0x1800019e3  pop     rbp
0x1800019e4  retn
```
