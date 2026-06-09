# LipsStateTunnelFilterAddCbNonSecure

- ea: `0x1800491d8`
- end: `0x18004955a`
- name: `LipsStateTunnelFilterAddCbNonSecure`
- size: `898`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180049008`

## callees

- `0x180006f60`
- `0x18000c4d0`
- `0x18000e510`
- `0x180047e20`
- `0x1800491d8`
- `0x18004aec0`
- `0x18004b034`
- `0x18004b274`
- `0x18004d05e`
- `0x18004d090`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18004937b`
- `RPCRT4!UuidCreate` at `0x180049424`
- `RPCRT4!UuidCreate` at `0x18004937b`
- `RPCRT4!UuidCreate` at `0x180049424`

## pseudocode

```c
__int64 __fastcall LipsStateTunnelFilterAddCbNonSecure(__int64 a1, __int64 a2)
{
  int v2; // esi
  __int64 v5; // r15
  int v6; // ebx
  __int64 v7; // rdx
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  bool v11; // zf
  FWP_ACTION_TYPE v12; // eax
  GUID v13; // xmm0
  _DWORD *v14; // rax
  __int64 v15; // rax
  _DWORD *v16; // rax
  __int64 v17; // rsi
  unsigned __int64 v18; // rdi
  FWPM_FILTER0 Uuid; // [rsp+20h] [rbp-E0h] BYREF
  GUID v21; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v22; // [rsp+100h] [rbp+0h]
  LPVOID lpMem; // [rsp+110h] [rbp+10h]
  _QWORD v24[5]; // [rsp+118h] [rbp+18h] BYREF

  v2 = *(_DWORD *)(a1 + 44);
  v5 = 80;
  **(_DWORD **)a2 = 0;
  v6 = *(_DWORD *)(a1 + 236);
  v21 = 0;
  if ( v6 != 8 )
    v5 = 40;
  lpMem = 0;
  v22 = 0;
  memset_0(&Uuid, 0, sizeof(Uuid));
  v7 = 40;
  if ( v6 != 8 )
    v7 = 80;
  v8 = LipsFilterConditionIpAddressFill(&FWPM_CONDITION_IP_LOCAL_ADDRESS, a1 + v7, &v21);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v10 = 21;
    goto LABEL_9;
  }
  v8 = LipsFilterConditionIpAddressFill(&FWPM_CONDITION_IP_REMOTE_ADDRESS, v5 + a1, v24);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v10 = 22;
    goto LABEL_9;
  }
  Uuid.displayData.name = *(wchar_t **)(a1 + 24);
  Uuid.displayData.description = Uuid.displayData.name;
  Uuid.filterCondition = (FWPM_FILTER_CONDITION0 *)&v21;
  v11 = *(_DWORD *)(a1 + 224) == 2;
  Uuid.weight.type = FWP_EMPTY;
  Uuid.numFilterConditions = 2;
  v12 = !v11 + 4097;
  v11 = *(_DWORD *)(a1 + 236) == 8;
  Uuid.action.type = v12;
  if ( v11 )
  {
    if ( v2 )
      v13 = FWPM_LAYER_OUTBOUND_TRANSPORT_V6;
    else
      v13 = FWPM_LAYER_OUTBOUND_TRANSPORT_V4;
  }
  else if ( v2 )
  {
    v13 = FWPM_LAYER_INBOUND_TRANSPORT_V6;
  }
  else
  {
    v13 = FWPM_LAYER_INBOUND_TRANSPORT_V4;
  }
  Uuid.layerKey = v13;
  Uuid.subLayerKey = FWPM_SUBLAYER_IPSEC_TUNNEL;
  v8 = UuidCreate(&Uuid.filterKey);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v10 = 23;
    goto LABEL_9;
  }
  v8 = LipsBfeFilterAdd(&Uuid);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v10 = 24;
LABEL_9:
    WPP_SF_d(v9[2], v10, WPP_4259805821ae3eb6062dce0997567f8e_Traceguids, v8);
    goto LABEL_39;
  }
  v14 = *(_DWORD **)a2;
  if ( *(_DWORD *)(a1 + 236) == 8 )
    *(GUID *)(v14 + 1) = Uuid.filterKey;
  else
    *(GUID *)(v14 + 5) = Uuid.filterKey;
  if ( !v2 )
  {
    Uuid.layerKey = FWPM_LAYER_IPFORWARD_V4;
    UuidCreate(&Uuid.filterKey);
    if ( *(_DWORD *)(a1 + 236) == 8 )
    {
      v21 = FWPM_CONDITION_IP_SOURCE_ADDRESS;
      v24[0] = *(_QWORD *)&FWPM_CONDITION_IP_DESTINATION_ADDRESS.Data1;
      v15 = *(_QWORD *)FWPM_CONDITION_IP_DESTINATION_ADDRESS.Data4;
    }
    else
    {
      v21 = FWPM_CONDITION_IP_DESTINATION_ADDRESS;
      v24[0] = *(_QWORD *)&FWPM_CONDITION_IP_SOURCE_ADDRESS.Data1;
      v15 = *(_QWORD *)FWPM_CONDITION_IP_SOURCE_ADDRESS.Data4;
    }
    v24[1] = v15;
    LipsBfeFilterAdd(&Uuid);
    v16 = *(_DWORD **)a2;
    if ( *(_DWORD *)(a1 + 236) == 8 )
      *(GUID *)(v16 + 9) = Uuid.filterKey;
    else
      *(GUID *)(v16 + 13) = Uuid.filterKey;
  }
LABEL_39:
  v17 = 0;
  v18 = 0;
  do
  {
    switch ( *(_DWORD *)((char *)&v22 + v18 + 8) )
    {
      case 0xB:
        IpsecFreeMem((LPVOID)v24[v18 / 8 - 1]);
        break;
      case 0x100:
        LipsFilterConditionIpAddressV4Free((char *)&v21 + v18);
        break;
      case 0x101:
        LipsFilterConditionIpAddressV6Free((char *)&v21 + v18);
        break;
    }
    ++v17;
    v18 += 40LL;
  }
  while ( v17 != 2 );
  if ( v8 )
  {
    *(_OWORD *)(*(_QWORD *)a2 + 4LL) = 0;
    *(_OWORD *)(*(_QWORD *)a2 + 20LL) = 0;
    *(_OWORD *)(*(_QWORD *)a2 + 36LL) = 0;
    *(_OWORD *)(*(_QWORD *)a2 + 52LL) = 0;
    return (unsigned int)LipsReportError(v8, (int)"LipsStateTunnelFilterAddCbNonSecure");
  }
  return v8;
}

```

## disassembly

```asm
0x1800491d8  mov     [rsp-8+arg_10], rbx
0x1800491dd  mov     [rsp-8+arg_18], rsi
0x1800491e2  push    rbp
0x1800491e3  push    rdi
0x1800491e4  push    r12
0x1800491e6  push    r14
0x1800491e8  push    r15
0x1800491ea  lea     rbp, [rsp-50h]
0x1800491ef  sub     rsp, 150h
0x1800491f6  mov     rax, cs:__security_cookie
0x1800491fd  xor     rax, rsp
0x180049200  mov     [rbp+70h+var_30], rax
0x180049204  mov     rax, [rdx]
0x180049207  mov     r12d, 50h ; 'P'
0x18004920d  mov     esi, [rcx+2Ch]
0x180049210  xorps   xmm0, xmm0
0x180049213  mov     r14, rdx
0x180049216  mov     rdi, rcx
0x180049219  mov     r15d, r12d
0x18004921c  mov     dword ptr [rax], 0
0x180049222  lea     r8d, [r12+78h]; Size
0x180049227  mov     ebx, [rcx+0ECh]
0x18004922d  lea     eax, [r12-28h]
0x180049232  cmp     ebx, 8
0x180049235  lea     rcx, [rsp+170h+Uuid]; void *
0x18004923a  movups  [rbp+70h+var_80], xmm0
0x18004923e  cmovnz  r15d, eax
0x180049242  xor     eax, eax
0x180049244  xor     edx, edx; Val
0x180049246  mov     [rbp+70h+lpMem], rax
0x18004924a  movups  [rbp+70h+var_70], xmm0
0x18004924e  call    memset_0
0x180049253  cmp     ebx, 8
0x180049256  lea     edx, [r12-28h]
0x18004925b  lea     r8, [rbp+70h+var_80]
0x18004925f  cmovnz  edx, r12d
0x180049263  lea     rcx, FWPM_CONDITION_IP_LOCAL_ADDRESS
0x18004926a  add     rdx, rdi
0x18004926d  call    LipsFilterConditionIpAddressFill
0x180049272  mov     ebx, eax
0x180049274  test    eax, eax
0x180049276  jz      short loc_1800492B6
0x180049278  mov     rcx, cs:WPP_GLOBAL_Control
0x18004927f  lea     rax, WPP_GLOBAL_Control
0x180049286  cmp     rcx, rax
0x180049289  jz      loc_1800494B0
0x18004928f  test    byte ptr [rcx+1Ch], 10h
0x180049293  jz      loc_1800494B0
0x180049299  lea     edx, [r12-3Bh]
0x18004929e  mov     rcx, [rcx+10h]
0x1800492a2  lea     r8, WPP_4259805821ae3eb6062dce0997567f8e_Traceguids
0x1800492a9  mov     r9d, ebx
0x1800492ac  call    WPP_SF_d
0x1800492b1  jmp     loc_1800494B0
0x1800492b6  lea     rdx, [r15+rdi]
0x1800492ba  lea     r8, [rbp+70h+var_58]
0x1800492be  lea     rcx, FWPM_CONDITION_IP_REMOTE_ADDRESS
0x1800492c5  call    LipsFilterConditionIpAddressFill
0x1800492ca  mov     ebx, eax
0x1800492cc  test    eax, eax
0x1800492ce  jz      short loc_1800492F8
0x1800492d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800492d7  lea     rax, WPP_GLOBAL_Control
0x1800492de  cmp     rcx, rax
0x1800492e1  jz      loc_1800494B0
0x1800492e7  test    byte ptr [rcx+1Ch], 10h
0x1800492eb  jz      loc_1800494B0
0x1800492f1  mov     edx, 16h
0x1800492f6  jmp     short loc_18004929E
0x1800492f8  mov     rax, [rdi+18h]
0x1800492fc  mov     [rsp+170h+var_140], rax
0x180049301  mov     [rsp+170h+var_138], rax
0x180049306  lea     rax, [rbp+70h+var_80]
0x18004930a  mov     [rbp+70h+var_D8], rax
0x18004930e  xor     eax, eax
0x180049310  cmp     dword ptr [rdi+0E0h], 2
0x180049317  mov     [rbp+70h+var_F0], 0
0x18004931e  setnz   al
0x180049321  mov     [rbp+70h+var_E0], 2
0x180049328  add     eax, 1001h
0x18004932d  cmp     dword ptr [rdi+0ECh], 8
0x180049334  mov     [rbp+70h+var_D0], eax
0x180049337  jnz     short loc_18004934F
0x180049339  test    esi, esi
0x18004933b  jnz     short loc_180049346
0x18004933d  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_TRANSPORT_V4.Data1
0x180049344  jmp     short loc_180049363
0x180049346  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_TRANSPORT_V6.Data1
0x18004934d  jmp     short loc_180049363
0x18004934f  test    esi, esi
0x180049351  jnz     short loc_18004935C
0x180049353  movups  xmm0, xmmword ptr cs:FWPM_LAYER_INBOUND_TRANSPORT_V4.Data1
0x18004935a  jmp     short loc_180049363
0x18004935c  movups  xmm0, xmmword ptr cs:FWPM_LAYER_INBOUND_TRANSPORT_V6.Data1
0x180049363  movdqu  [rsp+170h+var_110], xmm0
0x180049369  lea     rcx, [rsp+170h+Uuid]; Uuid
0x18004936e  movups  xmm0, xmmword ptr cs:FWPM_SUBLAYER_IPSEC_TUNNEL.Data1
0x180049375  movdqu  [rsp+170h+var_100], xmm0
0x18004937b  call    cs:__imp_UuidCreate
0x180049381  mov     ebx, eax
0x180049383  test    eax, eax
0x180049385  jz      short loc_1800493B2
0x180049387  mov     rcx, cs:WPP_GLOBAL_Control
0x18004938e  lea     rax, WPP_GLOBAL_Control
0x180049395  cmp     rcx, rax
0x180049398  jz      loc_1800494B0
0x18004939e  test    byte ptr [rcx+1Ch], 10h
0x1800493a2  jz      loc_1800494B0
0x1800493a8  mov     edx, 17h
0x1800493ad  jmp     loc_18004929E
0x1800493b2  lea     rcx, [rsp+170h+Uuid]; filter
0x1800493b7  call    LipsBfeFilterAdd
0x1800493bc  mov     ebx, eax
0x1800493be  test    eax, eax
0x1800493c0  jz      short loc_1800493ED
0x1800493c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800493c9  lea     rax, WPP_GLOBAL_Control
0x1800493d0  cmp     rcx, rax
0x1800493d3  jz      loc_1800494B0
0x1800493d9  test    byte ptr [rcx+1Ch], 10h
0x1800493dd  jz      loc_1800494B0
0x1800493e3  mov     edx, 18h
0x1800493e8  jmp     loc_18004929E
0x1800493ed  cmp     dword ptr [rdi+0ECh], 8
0x1800493f4  mov     rax, [r14]
0x1800493f7  movaps  xmm0, xmmword ptr [rsp+170h+Uuid.Data1]
0x1800493fc  jnz     short loc_180049405
0x1800493fe  movdqu  xmmword ptr [rax+4], xmm0
0x180049403  jmp     short loc_18004940A
0x180049405  movdqu  xmmword ptr [rax+14h], xmm0
0x18004940a  test    esi, esi
0x18004940c  jnz     loc_1800494B0
0x180049412  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPFORWARD_V4.Data1
0x180049419  lea     rcx, [rsp+170h+Uuid]; Uuid
0x18004941e  movdqu  [rsp+170h+var_110], xmm0
0x180049424  call    cs:__imp_UuidCreate
0x18004942a  cmp     dword ptr [rdi+0ECh], 8
0x180049431  jnz     short loc_18004945D
0x180049433  mov     rax, qword ptr cs:FWPM_CONDITION_IP_SOURCE_ADDRESS.Data1
0x18004943a  mov     qword ptr [rbp+70h+var_80], rax
0x18004943e  mov     rax, qword ptr cs:FWPM_CONDITION_IP_SOURCE_ADDRESS.Data4
0x180049445  mov     qword ptr [rbp+70h+var_80+8], rax
0x180049449  mov     rax, qword ptr cs:FWPM_CONDITION_IP_DESTINATION_ADDRESS.Data1
0x180049450  mov     [rbp+70h+var_58], rax
0x180049454  mov     rax, qword ptr cs:FWPM_CONDITION_IP_DESTINATION_ADDRESS.Data4
0x18004945b  jmp     short loc_180049485
0x18004945d  mov     rax, qword ptr cs:FWPM_CONDITION_IP_DESTINATION_ADDRESS.Data1
0x180049464  mov     qword ptr [rbp+70h+var_80], rax
0x180049468  mov     rax, qword ptr cs:FWPM_CONDITION_IP_DESTINATION_ADDRESS.Data4
0x18004946f  mov     qword ptr [rbp+70h+var_80+8], rax
0x180049473  mov     rax, qword ptr cs:FWPM_CONDITION_IP_SOURCE_ADDRESS.Data1
0x18004947a  mov     [rbp+70h+var_58], rax
0x18004947e  mov     rax, qword ptr cs:FWPM_CONDITION_IP_SOURCE_ADDRESS.Data4
0x180049485  lea     rcx, [rsp+170h+Uuid]; filter
0x18004948a  mov     [rbp+70h+var_50], rax
0x18004948e  call    LipsBfeFilterAdd
0x180049493  cmp     dword ptr [rdi+0ECh], 8
0x18004949a  mov     rax, [r14]
0x18004949d  movaps  xmm0, xmmword ptr [rsp+170h+Uuid.Data1]
0x1800494a2  jnz     short loc_1800494AB
0x1800494a4  movdqu  xmmword ptr [rax+24h], xmm0
0x1800494a9  jmp     short loc_1800494B0
0x1800494ab  movdqu  xmmword ptr [rax+34h], xmm0
0x1800494b0  xor     esi, esi
0x1800494b2  xor     edi, edi
0x1800494b4  mov     ecx, dword ptr [rbp+rdi+70h+var_70+8]
0x1800494b8  sub     ecx, 0Bh
0x1800494bb  jz      short loc_1800494E6
0x1800494bd  sub     ecx, 0F5h
0x1800494c3  jz      short loc_1800494D8
0x1800494c5  cmp     ecx, 1
0x1800494c8  jnz     short loc_1800494F0
0x1800494ca  lea     rcx, [rbp+70h+var_80]
0x1800494ce  add     rcx, rdi
0x1800494d1  call    LipsFilterConditionIpAddressV6Free
0x1800494d6  jmp     short loc_1800494F0
0x1800494d8  lea     rcx, [rbp+70h+var_80]
0x1800494dc  add     rcx, rdi
0x1800494df  call    LipsFilterConditionIpAddressV4Free
0x1800494e4  jmp     short loc_1800494F0
0x1800494e6  mov     rcx, [rbp+rdi+70h+lpMem]; lpMem
0x1800494eb  call    IpsecFreeMem
0x1800494f0  inc     rsi
0x1800494f3  add     rdi, 28h ; '('
0x1800494f7  cmp     rsi, 2
0x1800494fb  jnz     short loc_1800494B4
0x1800494fd  test    ebx, ebx
0x1800494ff  jz      short loc_180049530
0x180049501  mov     rax, [r14]
0x180049504  lea     rdx, aLipsstatetunne_0; "LipsStateTunnelFilterAddCbNonSecure"
0x18004950b  xorps   xmm0, xmm0
0x18004950e  mov     ecx, ebx
0x180049510  movups  xmmword ptr [rax+4], xmm0
0x180049514  mov     rax, [r14]
0x180049517  movups  xmmword ptr [rax+14h], xmm0
0x18004951b  mov     rax, [r14]
0x18004951e  movups  xmmword ptr [rax+24h], xmm0
0x180049522  mov     rax, [r14]
0x180049525  movups  xmmword ptr [rax+34h], xmm0
0x180049529  call    LipsReportError
0x18004952e  mov     ebx, eax
0x180049530  mov     eax, ebx
0x180049532  mov     rcx, [rbp+70h+var_30]
0x180049536  xor     rcx, rsp; StackCookie
0x180049539  call    __security_check_cookie
0x18004953e  lea     r11, [rsp+170h+var_20]
0x180049546  mov     rbx, [r11+40h]
0x18004954a  mov     rsi, [r11+48h]
0x18004954e  mov     rsp, r11
0x180049551  pop     r15
0x180049553  pop     r14
0x180049555  pop     r12
0x180049557  pop     rdi
0x180049558  pop     rbp
0x180049559  retn
```
