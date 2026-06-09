# ResolverGrabNetworkInfo

- ea: `0x180005740`
- end: `0x1800059c1`
- name: `ResolverGrabNetworkInfo`
- size: `641`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1800040a0`
- `0x180005680`

## callees

- `0x180004aa8`
- `0x180005740`
- `0x180005d50`
- `0x18002de14`
- `0x18003e1d4`
- `0x180046ec0`
- `0x18004b858`
- `0x18007aec8`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!NetInfo_CopyNetworkIndex` at `0x180005921`
- `DNSAPI!NetInfo_CopyNetworkIndex` at `0x180005921`
- `DNSAPI!DnsGlobals` at `0x180005767`
- `DNSAPI!DnsGlobals` at `0x18000580e`
- `DNSAPI!NetInfo_Free` at `0x18000583e`
- `DNSAPI!NetInfo_Free` at `0x18000584a`
- `DNSAPI!NetInfo_Free` at `0x1800058b6`
- `DNSAPI!NetInfo_Free` at `0x180005978`
- `DNSAPI!NetInfo_Free` at `0x18000583e`
- `DNSAPI!NetInfo_Free` at `0x18000584a`
- `DNSAPI!NetInfo_Free` at `0x1800058b6`
- `DNSAPI!NetInfo_Free` at `0x180005978`

## pseudocode

```c
__int64 __fastcall ResolverGrabNetworkInfo(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // r14d
  int v5; // edi
  _DWORD *v6; // rsi
  int v7; // edi
  int v8; // r15d
  int v9; // eax
  __int64 v10; // rsi
  unsigned int v11; // ebx
  __int64 v14; // [rsp+40h] [rbp-20h] BYREF
  void *v15; // [rsp+48h] [rbp-18h] BYREF

  v15 = 0;
  v3 = a2;
  v14 = 0;
  v5 = DnsGlobals[28];
  v6 = (_DWORD *)(a1 + 404);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qldld(a1, a2, a3, a1, a2, *v6, *(_DWORD *)(a1 + 408), DnsGlobals[28]);
  if ( v5 || (v7 = 1, *v6) )
    v7 = 0;
  if ( g_fVelocityNetinfoCleanup )
  {
    v9 = GrabNetworkInfo(v7, &v14, (__int64 *)&v15);
    v8 = v7;
  }
  else
  {
    v8 = 0;
    v9 = GrabNetworkInfoOld(v7, 1, &v14, &v15);
  }
  if ( v9 )
    goto LABEL_23;
  if ( !*(_DWORD *)(a1 + 408) || *(_DWORD *)(a1 + 404) )
  {
    if ( v3 && *v6 && (unsigned int)IsConnectedInterfaceNotAvailable(v14) )
    {
      NetInfo_Free(v14);
      v14 = 0;
      DeRefServerMapView(v15);
      v15 = 0;
      UpdateNetworkInfo(0, 0);
      UpdateNetworkInfo(0, 1);
      if ( g_fVelocityNetinfoCleanup
         ? GrabNetworkInfo(v8 & (unsigned int)-(v7 != 0), &v14, (__int64 *)&v15)
         : (unsigned int)GrabNetworkInfoOld(v7, 1, &v14, &v15) )
      {
        goto LABEL_23;
      }
    }
    v10 = v14;
LABEL_11:
    *(_QWORD *)(a1 + 3456) = v15;
    *(_DWORD *)(a1 + 328) = dword_1800AB364;
    *(_DWORD *)(a1 + 476) = v7;
    *(_QWORD *)(a1 + 1024) = v10;
    v14 = 0;
    v15 = 0;
    *(_DWORD *)(a1 + 480) = DnsGlobals[29] != 0;
    v11 = 0;
    goto LABEL_12;
  }
  v10 = NetInfo_CopyNetworkIndex(v14, *(unsigned int *)(a1 + 412));
  if ( v10 )
  {
    NetInfo_Free(v14);
    v7 = 0;
    goto LABEL_11;
  }
LABEL_23:
  v11 = 9852;
LABEL_12:
  DeRefServerMapView(v15);
  v15 = 0;
  NetInfo_Free(v14);
  v14 = 0;
  NetInfo_Free(0);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 47, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180005740  mov     [rsp-28h+arg_8], rbx
0x180005745  mov     [rsp-28h+arg_10], rsi
0x18000574a  push    rbp
0x18000574b  push    rdi
0x18000574c  push    r12
0x18000574e  push    r14
0x180005750  push    r15
0x180005752  mov     rbp, rsp
0x180005755  sub     rsp, 60h
0x180005759  mov     rax, cs:__security_cookie
0x180005760  xor     rax, rsp
0x180005763  mov     [rbp+var_10], rax
0x180005767  mov     rax, cs:__imp_DnsGlobals
0x18000576e  xor     r12d, r12d
0x180005771  mov     [rbp+var_18], r12
0x180005775  mov     r14d, edx
0x180005778  mov     [rbp+var_20], r12
0x18000577c  mov     rbx, rcx
0x18000577f  mov     edi, [rax+70h]
0x180005782  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180005789  lea     rsi, [rcx+194h]
0x180005790  jnz     loc_180005939
0x180005796  test    edi, edi
0x180005798  jz      loc_180005884
0x18000579e  mov     edi, r12d
0x1800057a1  cmp     cs:g_fVelocityNetinfoCleanup, r12d
0x1800057a8  mov     ecx, edi
0x1800057aa  jnz     loc_18000595F
0x1800057b0  lea     r9, [rbp+var_18]
0x1800057b4  mov     edx, 1
0x1800057b9  lea     r8, [rbp+var_20]
0x1800057bd  mov     r15d, r12d
0x1800057c0  call    GrabNetworkInfoOld
0x1800057c5  test    eax, eax
0x1800057c7  jnz     loc_18000592F
0x1800057cd  cmp     [rbx+198h], r12d
0x1800057d4  jnz     loc_18000590A
0x1800057da  test    r14d, r14d
0x1800057dd  jnz     loc_180005897
0x1800057e3  mov     rsi, [rbp+var_20]
0x1800057e7  mov     rax, [rbp+var_18]
0x1800057eb  mov     ecx, r12d
0x1800057ee  mov     [rbx+0D80h], rax
0x1800057f5  mov     eax, cs:dword_1800AB364
0x1800057fb  mov     [rbx+148h], eax
0x180005801  mov     [rbx+1DCh], edi
0x180005807  mov     [rbx+400h], rsi
0x18000580e  mov     rax, cs:__imp_DnsGlobals
0x180005815  mov     [rbp+var_20], r12
0x180005819  mov     [rbp+var_18], r12
0x18000581d  cmp     [rax+74h], r12d
0x180005821  setnz   cl
0x180005824  mov     [rbx+1E0h], ecx
0x18000582a  mov     ebx, r12d
0x18000582d  mov     rcx, [rbp+var_18]; void *
0x180005831  call    DeRefServerMapView
0x180005836  mov     rcx, [rbp+var_20]
0x18000583a  mov     [rbp+var_18], r12
0x18000583e  call    cs:__imp_NetInfo_Free
0x180005844  xor     ecx, ecx
0x180005846  mov     [rbp+var_20], r12
0x18000584a  call    cs:__imp_NetInfo_Free
0x180005850  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180005857  jnz     loc_1800059A3
0x18000585d  mov     eax, ebx
0x18000585f  mov     rcx, [rbp+var_10]
0x180005863  xor     rcx, rsp; StackCookie
0x180005866  call    __security_check_cookie
0x18000586b  lea     r11, [rsp+60h+var_s0]
0x180005870  mov     rbx, [r11+38h]
0x180005874  mov     rsi, [r11+40h]
0x180005878  mov     rsp, r11
0x18000587b  pop     r15
0x18000587d  pop     r14
0x18000587f  pop     r12
0x180005881  pop     rdi
0x180005882  pop     rbp
0x180005883  retn
0x180005884  mov     edi, 1
0x180005889  cmp     [rsi], r12d
0x18000588c  jz      loc_1800057A1
0x180005892  jmp     loc_18000579E
0x180005897  mov     edx, [rsi]
0x180005899  test    edx, edx
0x18000589b  jz      loc_1800057E3
0x1800058a1  mov     rcx, [rbp+var_20]
0x1800058a5  call    IsConnectedInterfaceNotAvailable
0x1800058aa  test    eax, eax
0x1800058ac  jz      loc_1800057E3
0x1800058b2  mov     rcx, [rbp+var_20]
0x1800058b6  call    cs:__imp_NetInfo_Free
0x1800058bc  mov     rcx, [rbp+var_18]; void *
0x1800058c0  mov     [rbp+var_20], r12
0x1800058c4  call    DeRefServerMapView
0x1800058c9  xor     edx, edx
0x1800058cb  mov     [rbp+var_18], r12
0x1800058cf  xor     ecx, ecx
0x1800058d1  call    UpdateNetworkInfo
0x1800058d6  mov     edx, 1
0x1800058db  xor     ecx, ecx
0x1800058dd  call    UpdateNetworkInfo
0x1800058e2  cmp     cs:g_fVelocityNetinfoCleanup, r12d
0x1800058e9  jz      loc_180005986
0x1800058ef  mov     eax, edi
0x1800058f1  lea     r8, [rbp+var_18]
0x1800058f5  neg     eax
0x1800058f7  lea     rdx, [rbp+var_20]
0x1800058fb  sbb     ecx, ecx
0x1800058fd  and     ecx, r15d
0x180005900  call    GrabNetworkInfo
0x180005905  jmp     loc_18000599A
0x18000590a  cmp     [rbx+194h], r12d
0x180005911  jnz     loc_1800057DA
0x180005917  mov     edx, [rbx+19Ch]
0x18000591d  mov     rcx, [rbp+var_20]
0x180005921  call    cs:__imp_NetInfo_CopyNetworkIndex
0x180005927  mov     rsi, rax
0x18000592a  test    rax, rax
0x18000592d  jnz     short loc_180005974
0x18000592f  mov     ebx, 267Ch
0x180005934  jmp     loc_18000582D
0x180005939  mov     eax, [rcx+198h]
0x18000593f  mov     r9, rbx
0x180005942  mov     [rsp+60h+var_28], edi
0x180005946  mov     [rsp+60h+var_30], eax
0x18000594a  mov     eax, [rsi]
0x18000594c  mov     [rsp+60h+var_38], eax
0x180005950  mov     [rsp+60h+var_40], r14d
0x180005955  call    WPP_SF_qldld
0x18000595a  jmp     loc_180005796
0x18000595f  lea     r8, [rbp+var_18]
0x180005963  lea     rdx, [rbp+var_20]
0x180005967  call    GrabNetworkInfo
0x18000596c  mov     r15d, edi
0x18000596f  jmp     loc_1800057C5
0x180005974  mov     rcx, [rbp+var_20]
0x180005978  call    cs:__imp_NetInfo_Free
0x18000597e  mov     edi, r12d
0x180005981  jmp     loc_1800057E7
0x180005986  lea     r9, [rbp+var_18]
0x18000598a  mov     edx, 1
0x18000598f  lea     r8, [rbp+var_20]
0x180005993  mov     ecx, edi
0x180005995  call    GrabNetworkInfoOld
0x18000599a  test    eax, eax
0x18000599c  jnz     short loc_18000592F
0x18000599e  jmp     loc_1800057E3
0x1800059a3  mov     edx, 2Fh ; '/'
0x1800059a8  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x1800059af  mov     ecx, 40Bh
0x1800059b4  mov     r9d, ebx
0x1800059b7  call    WPP_SF_d
0x1800059bc  jmp     loc_18000585D
```
