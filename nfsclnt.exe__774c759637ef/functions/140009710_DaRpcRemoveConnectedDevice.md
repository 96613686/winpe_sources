# DaRpcRemoveConnectedDevice

- ea: `0x140009710`
- end: `0x140009b79`
- name: `DaRpcRemoveConnectedDevice`
- size: `1129`
- prototype: `__int64 __fastcall(__int64, int, int, const wchar_t *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation`

## callees

- `0x140002bd8`
- `0x140002c40`
- `0x140002fbc`
- `0x140004bd4`
- `0x140004e64`
- `0x140004f0c`
- `0x140009710`
- `0x140009b80`
- `0x14000a0b0`
- `0x14000a3c8`
- `0x14000a64c`
- `0x14000a7c0`
- `0x140018350`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000986e`
- `KERNEL32!EnterCriticalSection` at `0x14000986e`
- `KERNEL32!GlobalFree` at `0x140009a9f`
- `KERNEL32!GlobalFree` at `0x140009a9f`
- `KERNEL32!LeaveCriticalSection` at `0x140009975`
- `KERNEL32!LeaveCriticalSection` at `0x140009af5`
- `KERNEL32!LeaveCriticalSection` at `0x140009975`
- `KERNEL32!LeaveCriticalSection` at `0x140009af5`
- `msvcrt!_wcsicmp` at `0x1400098e9`
- `msvcrt!_wcsicmp` at `0x1400099d9`
- `msvcrt!_wcsicmp` at `0x1400098e9`
- `msvcrt!_wcsicmp` at `0x1400099d9`
- `RPCRT4!RpcImpersonateClient` at `0x1400097aa`
- `RPCRT4!RpcImpersonateClient` at `0x1400097aa`

## string_xrefs

- `0x140009741`: `DaRpcRemoveConnectedDevice`

## pseudocode

```c
__int64 __fastcall DaRpcRemoveConnectedDevice(__int64 a1, int a2, int a3, const wchar_t *a4)
{
  RPC_STATUS v6; // eax
  __int64 v8; // rcx
  void *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  int v12; // edx
  int v13; // r8d
  _UNKNOWN **v14; // rcx
  int *i; // rbx
  int v16; // eax
  int v17; // edx
  __int64 v18; // rcx
  __int64 v19; // rcx
  struct _LUID DestinationLuid; // [rsp+50h] [rbp-9h] BYREF
  char v21[32]; // [rsp+58h] [rbp-1h] BYREF

  DestinationLuid = 0;
  strcpy(v21, "DaRpcRemoveConnectedDevice");
  if ( !a3 || !a4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v21);
    return 2250;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)&WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
      (unsigned int)v21,
      (__int64)a4,
      a2);
  v6 = RpcImpersonateClient(0);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)&WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
        (unsigned int)v21,
        v6);
    return 5;
  }
  if ( (int)GetLuid(&DestinationLuid) < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids);
    SafeRpcRevertToSelf(v9, 400);
    return 5;
  }
  v10 = SafeRpcRevertToSelf(v8, 404);
  v11 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)&WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
        (unsigned int)v21,
        v10);
    return v11;
  }
  EnterCriticalSection(&DeviceListCS);
  v14 = (_UNKNOWN **)WPP_GLOBAL_Control;
  for ( i = (int *)pDeviceList; i; i = (int *)*((_QWORD *)i + 8) )
  {
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
    {
      WPP_SF_sS(
        (unsigned int)v14[2],
        30,
        (unsigned int)&WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
        (unsigned int)v21,
        *((_QWORD *)i + 4));
      v14 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    v16 = *i;
    if ( a2 )
    {
      if ( DestinationLuid.LowPart == v16 && DestinationLuid.HighPart == i[1] && *((_QWORD *)i + 4) )
      {
        if ( !_wcsicmp(*((const wchar_t **)i + 4), a4) )
        {
          v14 = (_UNKNOWN **)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_37;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              31,
              &WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
              *((_QWORD *)i + 5));
LABEL_33:
            v14 = (_UNKNOWN **)WPP_GLOBAL_Control;
            break;
          }
          break;
        }
        goto LABEL_49;
      }
    }
    else if ( DestinationLuid.LowPart == v16
           && DestinationLuid.HighPart == i[1]
           && *((_QWORD *)i + 5)
           && !*((_QWORD *)i + 4) )
    {
      if ( !_wcsicmp(*((const wchar_t **)i + 5), a4) )
        goto LABEL_33;
LABEL_49:
      v14 = (_UNKNOWN **)WPP_GLOBAL_Control;
      continue;
    }
  }
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
  {
    WPP_SF_sq((unsigned int)v14[2], v12, v13, (unsigned int)v21, (char)i);
    v14 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
LABEL_37:
  if ( !i )
  {
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 )
      WPP_SF_s(v14[2], 33, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v21);
    LeaveCriticalSection(&DeviceListCS);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        (unsigned int)&WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
        (unsigned int)v21,
        202);
    return 2250;
  }
  v17 = i[2];
  if ( v17 == 1 )
  {
    v18 = *((_QWORD *)i + 9);
    if ( v18 )
      *(_QWORD *)(v18 + 64) = *((_QWORD *)i + 8);
    v19 = *((_QWORD *)i + 8);
    if ( v19 )
      *(_QWORD *)(v19 + 72) = *((_QWORD *)i + 9);
    if ( i == pDeviceList )
      pDeviceList = (HGLOBAL)*((_QWORD *)pDeviceList + 8);
    *((_QWORD *)i + 9) = 0;
    *((_QWORD *)i + 8) = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_sDDSSS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        i[1],
        *i,
        *((_QWORD *)i + 4),
        *((_QWORD *)i + 5),
        *((_QWORD *)i + 6));
    GlobalFree(i);
  }
  else
  {
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
      WPP_SF_sdDDSSS((TRACEHANDLE)v14[2], v17, i[1], *i, *((_QWORD *)i + 4), *((_QWORD *)i + 5), *((_QWORD *)i + 6));
    --i[2];
  }
  LeaveCriticalSection(&DeviceListCS);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v21);
  return 0;
}

```

## disassembly

```asm
0x140009710  push    rbp
0x140009712  push    rbx
0x140009713  push    rsi
0x140009714  push    rdi
0x140009715  push    r14
0x140009717  push    r15
0x140009719  lea     rbp, [rsp-2Fh]
0x14000971e  sub     rsp, 88h
0x140009725  mov     rax, cs:__security_cookie
0x14000972c  xor     rax, rsp
0x14000972f  mov     [rbp+57h+var_38], rax
0x140009733  mov     qword ptr [rbp+57h+DestinationLuid.LowPart], 0
0x14000973b  mov     r14, r9
0x14000973e  mov     r15d, edx
0x140009741  movups  xmm0, xmmword ptr cs:aDarpcremovecon; "DaRpcRemoveConnectedDevice"
0x140009748  movups  xmm1, xmmword ptr cs:aDarpcremovecon+0Bh; "ConnectedDevice"
0x14000974f  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x140009753  movups  xmmword ptr [rbp+57h+var_58+0Bh], xmm1
0x140009757  test    r8d, r8d
0x14000975a  jz      loc_140009B26
0x140009760  test    r9, r9
0x140009763  jz      loc_140009B26
0x140009769  mov     rcx, cs:WPP_GLOBAL_Control
0x140009770  lea     rdi, WPP_GLOBAL_Control
0x140009777  lea     rsi, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x14000977e  cmp     rcx, rdi
0x140009781  jz      short loc_1400097A8
0x140009783  test    byte ptr [rcx+1Ch], 1
0x140009787  jz      short loc_1400097A8
0x140009789  mov     rcx, [rcx+10h]
0x14000978d  mov     edx, 1Ah
0x140009792  mov     dword ptr [rsp+0B0h+var_88], r15d
0x140009797  mov     r8, rsi
0x14000979a  mov     qword ptr [rsp+0B0h+var_90], r9
0x14000979f  lea     r9, [rbp+57h+var_58]
0x1400097a3  call    WPP_SF_sSd
0x1400097a8  xor     ecx, ecx; BindingHandle
0x1400097aa  call    cs:__imp_RpcImpersonateClient
0x1400097b0  test    eax, eax
0x1400097b2  jz      short loc_1400097E9
0x1400097b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400097bb  cmp     rcx, rdi
0x1400097be  jz      short loc_1400097DF
0x1400097c0  test    byte ptr [rcx+1Ch], 2
0x1400097c4  jz      short loc_1400097DF
0x1400097c6  mov     rcx, [rcx+10h]
0x1400097ca  lea     r9, [rbp+57h+var_58]
0x1400097ce  mov     edx, 1Bh
0x1400097d3  mov     dword ptr [rsp+0B0h+var_90], eax
0x1400097d7  mov     r8, rsi
0x1400097da  call    WPP_SF_sd
0x1400097df  mov     eax, 5
0x1400097e4  jmp     loc_140009B5D
0x1400097e9  lea     rcx, [rbp+57h+DestinationLuid]; DestinationLuid
0x1400097ed  call    GetLuid
0x1400097f2  test    eax, eax
0x1400097f4  jns     short loc_140009825
0x1400097f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400097fd  cmp     rcx, rdi
0x140009800  jz      short loc_140009819
0x140009802  test    byte ptr [rcx+1Ch], 2
0x140009806  jz      short loc_140009819
0x140009808  mov     rcx, [rcx+10h]
0x14000980c  mov     edx, 1Ch
0x140009811  mov     r8, rsi
0x140009814  call    WPP_SF_
0x140009819  mov     edx, 190h
0x14000981e  call    SafeRpcRevertToSelf
0x140009823  jmp     short loc_1400097DF
0x140009825  mov     edx, 194h
0x14000982a  call    SafeRpcRevertToSelf
0x14000982f  mov     ebx, eax
0x140009831  test    eax, eax
0x140009833  jz      short loc_140009867
0x140009835  mov     rcx, cs:WPP_GLOBAL_Control
0x14000983c  cmp     rcx, rdi
0x14000983f  jz      short loc_140009860
0x140009841  test    byte ptr [rcx+1Ch], 2
0x140009845  jz      short loc_140009860
0x140009847  mov     rcx, [rcx+10h]
0x14000984b  lea     r9, [rbp+57h+var_58]
0x14000984f  mov     edx, 1Dh
0x140009854  mov     dword ptr [rsp+0B0h+var_90], eax
0x140009858  mov     r8, rsi
0x14000985b  call    WPP_SF_sd
0x140009860  mov     eax, ebx
0x140009862  jmp     loc_140009B5D
0x140009867  lea     rcx, DeviceListCS; lpCriticalSection
0x14000986e  call    cs:__imp_EnterCriticalSection
0x140009874  mov     rcx, cs:WPP_GLOBAL_Control
0x14000987b  mov     rbx, cs:pDeviceList
0x140009882  jmp     loc_1400099F2
0x140009887  cmp     rcx, rdi
0x14000988a  jz      short loc_1400098B7
0x14000988c  test    byte ptr [rcx+1Ch], 8
0x140009890  jz      short loc_1400098B7
0x140009892  mov     rax, [rbx+20h]
0x140009896  lea     r9, [rbp+57h+var_58]
0x14000989a  mov     rcx, [rcx+10h]
0x14000989e  mov     edx, 1Eh
0x1400098a3  mov     r8, rsi
0x1400098a6  mov     qword ptr [rsp+0B0h+var_90], rax
0x1400098ab  call    WPP_SF_sS
0x1400098b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400098b7  mov     eax, [rbx]
0x1400098b9  test    r15d, r15d
0x1400098bc  jz      loc_1400099B7
0x1400098c2  cmp     [rbp+57h+DestinationLuid.LowPart], eax
0x1400098c5  jnz     loc_1400099EE
0x1400098cb  mov     eax, [rbx+4]
0x1400098ce  cmp     [rbp+57h+DestinationLuid.HighPart], eax
0x1400098d1  jnz     loc_1400099EE
0x1400098d7  cmp     qword ptr [rbx+20h], 0
0x1400098dc  jz      loc_1400099EE
0x1400098e2  mov     rcx, [rbx+20h]; String1
0x1400098e6  mov     rdx, r14; String2
0x1400098e9  call    cs:__imp__wcsicmp
0x1400098ef  test    eax, eax
0x1400098f1  jnz     loc_1400099E7
0x1400098f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400098fe  cmp     rcx, rdi
0x140009901  jz      short loc_140009947
0x140009903  test    byte ptr [rcx+1Ch], 8
0x140009907  jz      short loc_140009923
0x140009909  mov     r9, [rbx+28h]
0x14000990d  lea     edx, [rax+1Fh]
0x140009910  mov     rcx, [rcx+10h]
0x140009914  mov     r8, rsi
0x140009917  call    WPP_SF_S
0x14000991c  mov     rcx, cs:WPP_GLOBAL_Control
0x140009923  cmp     rcx, rdi
0x140009926  jz      short loc_140009947
0x140009928  test    byte ptr [rcx+1Ch], 8
0x14000992c  jz      short loc_140009947
0x14000992e  mov     rcx, [rcx+10h]
0x140009932  lea     r9, [rbp+57h+var_58]
0x140009936  mov     qword ptr [rsp+0B0h+var_90], rbx
0x14000993b  call    WPP_SF_sq
0x140009940  mov     rcx, cs:WPP_GLOBAL_Control
0x140009947  test    rbx, rbx
0x14000994a  jnz     loc_140009A00
0x140009950  cmp     rcx, rdi
0x140009953  jz      short loc_14000996E
0x140009955  test    byte ptr [rcx+1Ch], 2
0x140009959  jz      short loc_14000996E
0x14000995b  mov     rcx, [rcx+10h]
0x14000995f  lea     edx, [rbx+21h]
0x140009962  lea     r9, [rbp+57h+var_58]
0x140009966  mov     r8, rsi
0x140009969  call    WPP_SF_s
0x14000996e  lea     rcx, DeviceListCS; lpCriticalSection
0x140009975  call    cs:__imp_LeaveCriticalSection
0x14000997b  mov     rcx, cs:WPP_GLOBAL_Control
0x140009982  cmp     rcx, rdi
0x140009985  jz      loc_140009B58
0x14000998b  test    byte ptr [rcx+1Ch], 2
0x14000998f  jz      loc_140009B58
0x140009995  mov     rcx, [rcx+10h]
0x140009999  lea     r9, [rbp+57h+var_58]
0x14000999d  mov     edx, 25h ; '%'
0x1400099a2  mov     dword ptr [rsp+0B0h+var_90], 8CAh
0x1400099aa  mov     r8, rsi
0x1400099ad  call    WPP_SF_sd
0x1400099b2  jmp     loc_140009B58
0x1400099b7  cmp     [rbp+57h+DestinationLuid.LowPart], eax
0x1400099ba  jnz     short loc_1400099EE
0x1400099bc  mov     eax, [rbx+4]
0x1400099bf  cmp     [rbp+57h+DestinationLuid.HighPart], eax
0x1400099c2  jnz     short loc_1400099EE
0x1400099c4  cmp     qword ptr [rbx+28h], 0
0x1400099c9  jz      short loc_1400099EE
0x1400099cb  cmp     qword ptr [rbx+20h], 0
0x1400099d0  jnz     short loc_1400099EE
0x1400099d2  mov     rcx, [rbx+28h]; String1
0x1400099d6  mov     rdx, r14; String2
0x1400099d9  call    cs:__imp__wcsicmp
0x1400099df  test    eax, eax
0x1400099e1  jz      loc_14000991C
0x1400099e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400099ee  mov     rbx, [rbx+40h]
0x1400099f2  test    rbx, rbx
0x1400099f5  jnz     loc_140009887
0x1400099fb  jmp     loc_140009923
0x140009a00  mov     edx, [rbx+8]
0x140009a03  cmp     edx, 1
0x140009a06  jnz     loc_140009AA7
0x140009a0c  mov     rcx, [rbx+48h]
0x140009a10  test    rcx, rcx
0x140009a13  jz      short loc_140009A1D
0x140009a15  mov     rax, [rbx+40h]
0x140009a19  mov     [rcx+40h], rax
0x140009a1d  mov     rcx, [rbx+40h]
0x140009a21  test    rcx, rcx
0x140009a24  jz      short loc_140009A2E
0x140009a26  mov     rax, [rbx+48h]
0x140009a2a  mov     [rcx+48h], rax
0x140009a2e  mov     rax, cs:pDeviceList
0x140009a35  cmp     rbx, rax
0x140009a38  jnz     short loc_140009A45
0x140009a3a  mov     rax, [rax+40h]
0x140009a3e  mov     cs:pDeviceList, rax
0x140009a45  mov     qword ptr [rbx+48h], 0
0x140009a4d  mov     qword ptr [rbx+40h], 0
0x140009a55  mov     rcx, cs:WPP_GLOBAL_Control
0x140009a5c  cmp     rcx, rdi
0x140009a5f  jz      short loc_140009A9C
0x140009a61  test    byte ptr [rcx+1Ch], 8
0x140009a65  jz      short loc_140009A9C
0x140009a67  mov     rax, [rbx+30h]
0x140009a6b  lea     r9, [rbp+57h+var_58]
0x140009a6f  mov     rcx, [rcx+10h]; LoggerHandle
0x140009a73  mov     [rsp+0B0h+var_70], rax; __int64
0x140009a78  mov     rax, [rbx+28h]
0x140009a7c  mov     [rsp+0B0h+var_78], rax; __int64
0x140009a81  mov     rax, [rbx+20h]
0x140009a85  mov     qword ptr [rsp+0B0h+var_80], rax; __int64
0x140009a8a  mov     eax, [rbx]
0x140009a8c  mov     dword ptr [rsp+0B0h+var_88], eax; char
0x140009a90  mov     eax, [rbx+4]
0x140009a93  mov     dword ptr [rsp+0B0h+var_90], eax; char
0x140009a97  call    WPP_SF_sDDSSS
0x140009a9c  mov     rcx, rbx; hMem
0x140009a9f  call    cs:__imp_GlobalFree
0x140009aa5  jmp     short loc_140009AEE
0x140009aa7  cmp     rcx, rdi
0x140009aaa  jz      short loc_140009AEB
0x140009aac  test    byte ptr [rcx+1Ch], 8
0x140009ab0  jz      short loc_140009AEB
0x140009ab2  mov     rax, [rbx+30h]
0x140009ab6  lea     r9, [rbp+57h+var_58]
0x140009aba  mov     rcx, [rcx+10h]; LoggerHandle
0x140009abe  mov     [rsp+0B0h+var_68], rax; __int64
0x140009ac3  mov     rax, [rbx+28h]
0x140009ac7  mov     [rsp+0B0h+var_70], rax; __int64
0x140009acc  mov     rax, [rbx+20h]
0x140009ad0  mov     [rsp+0B0h+var_78], rax; __int64
0x140009ad5  mov     eax, [rbx]
0x140009ad7  mov     dword ptr [rsp+0B0h+var_80], eax; char
0x140009adb  mov     eax, [rbx+4]
0x140009ade  mov     dword ptr [rsp+0B0h+var_88], eax; char
0x140009ae2  mov     dword ptr [rsp+0B0h+var_90], edx; char
0x140009ae6  call    WPP_SF_sdDDSSS
0x140009aeb  dec     dword ptr [rbx+8]
0x140009aee  lea     rcx, DeviceListCS; lpCriticalSection
0x140009af5  call    cs:__imp_LeaveCriticalSection
0x140009afb  mov     rcx, cs:WPP_GLOBAL_Control
0x140009b02  cmp     rcx, rdi
0x140009b05  jz      short loc_140009B22
0x140009b07  test    byte ptr [rcx+1Ch], 1
0x140009b0b  jz      short loc_140009B22
0x140009b0d  mov     rcx, [rcx+10h]
0x140009b11  lea     r9, [rbp+57h+var_58]
0x140009b15  mov     edx, 24h ; '$'
0x140009b1a  mov     r8, rsi
0x140009b1d  call    WPP_SF_s
0x140009b22  xor     eax, eax
0x140009b24  jmp     short loc_140009B5D
0x140009b26  mov     rcx, cs:WPP_GLOBAL_Control
0x140009b2d  lea     rdi, WPP_GLOBAL_Control
0x140009b34  cmp     rcx, rdi
0x140009b37  jz      short loc_140009B58
0x140009b39  test    byte ptr [rcx+1Ch], 2
0x140009b3d  jz      short loc_140009B58
0x140009b3f  mov     rcx, [rcx+10h]
0x140009b43  lea     r9, [rbp+57h+var_58]
0x140009b47  mov     edx, 19h
0x140009b4c  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140009b53  call    WPP_SF_s
0x140009b58  mov     eax, 8CAh
0x140009b5d  mov     rcx, [rbp+57h+var_38]
0x140009b61  xor     rcx, rsp; StackCookie
0x140009b64  call    __security_check_cookie
0x140009b69  add     rsp, 88h
0x140009b70  pop     r15
0x140009b72  pop     r14
0x140009b74  pop     rdi
0x140009b75  pop     rsi
0x140009b76  pop     rbx
0x140009b77  pop     rbp
0x140009b78  retn
```
