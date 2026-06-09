# MQDeleteQueue

- ea: `0x18000ec20`
- end: `0x18000ee4f`
- name: `MQDeleteQueue`
- size: `559`
- prototype: `HRESULT __stdcall(LPCWSTR lpwcsFormatName)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180005488`
- `0x18000dae4`
- `0x18000ec20`
- `0x180013c74`
- `0x180014458`
- `0x180017ce0`
- `0x18001a864`
- `0x18001d3d8`
- `0x180021060`
- `0x1800216a8`
- `0x180023c36`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000ed88`
- `RPCRT4!NdrClientCall3` at `0x18000ed88`
- `KERNEL32!TlsGetValue` at `0x18000ed5b`
- `KERNEL32!TlsGetValue` at `0x18000ed5b`

## pseudocode

```c
HRESULT __stdcall MQDeleteQueue(LPCWSTR lpwcsFormatName)
{
  int v2; // eax
  HRESULT v3; // ebx
  int v5; // edi
  LPVOID Value; // rax
  CLIENT_CALL_RETURN v7; // rax
  int Pointer; // ebx
  const wchar_t *v9; // rax
  __int64 v10; // r8
  __int64 v11; // [rsp+0h] [rbp-88h] BYREF
  HRESULT v12; // [rsp+30h] [rbp-58h]
  HRESULT v13; // [rsp+34h] [rbp-54h]
  __int64 *v14; // [rsp+38h] [rbp-50h]
  int v15; // [rsp+40h] [rbp-48h]
  int v16; // [rsp+44h] [rbp-44h]
  unsigned int v17; // [rsp+48h] [rbp-40h]
  _QWORD v18[2]; // [rsp+50h] [rbp-38h] BYREF
  _OWORD v19[2]; // [rsp+60h] [rbp-28h] BYREF
  wchar_t *v20; // [rsp+98h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v21; // [rsp+A0h] [rbp+18h]

  v14 = &v11;
  v2 = RtpOneTimeThreadInit();
  v3 = v2;
  if ( v2 < 0 )
  {
    LogMsgHR(v2, (wchar_t *)L"rt/queue", 0x458u);
    return v3;
  }
  v17 = 1;
  v20 = 0;
  memset(v19, 0, sizeof(v19));
  LOWORD(v19[0]) = 0;
  if ( !(unsigned int)FnFormatNameToQueueFormat(lpwcsFormatName, (struct QUEUE_FORMAT *)v19, &v20) )
  {
    v12 = LogHR(-1072824290, (wchar_t *)L"rt/queue", 0x46u);
    local_unwind_0(v14, &loc_18000ECD3);
    return v12;
  }
  if ( !(unsigned int)IsLegalFormatNameOperation((const struct QUEUE_FORMAT *)v19) )
  {
    v13 = LogHR(-1072824288, (wchar_t *)L"rt/queue", 0x50u);
    local_unwind_0(v14, &loc_18000ED15);
    return v13;
  }
  if ( LOBYTE(v19[0]) == 1 )
  {
    v9 = MachineDomain();
    LODWORD(v7.Pointer) = ADDeleteObjectGuid(0, v9, v10, (char *)v19 + 8);
    Pointer = (int)v7.Pointer;
    goto LABEL_12;
  }
  if ( (unsigned int)LOBYTE(v19[0]) - 2 < 2 )
  {
    v18[0] = 1;
    v18[1] = v19;
    Value = TlsGetValue(g_hBindIndex);
    v21.Simple = 0;
    v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 9u, 0, Value, v18).Pointer;
    Pointer = (int)v7.Pointer;
    v21.Pointer = v7.Pointer;
LABEL_12:
    v15 = RTpConvertToMQCode(v7.Simple, 1u);
    v16 = Pointer;
    v5 = v15;
    goto LABEL_13;
  }
  v5 = v15;
LABEL_13:
  MmDeallocate(v20);
  if ( v5 < 0 )
    LogMsgHR(v5, (wchar_t *)L"rt/queue", 0x64u);
  return v5;
}

```

## disassembly

```asm
0x18000ec20  mov     [rsp+arg_0], rbx
0x18000ec25  push    rdi
0x18000ec26  sub     rsp, 80h
0x18000ec2d  mov     [rsp+88h+var_50], rsp
0x18000ec32  mov     rdi, rcx
0x18000ec35  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x18000ec3a  mov     ebx, eax
0x18000ec3c  test    eax, eax
0x18000ec3e  jns     short loc_18000EC67
0x18000ec40  mov     r8d, 458h; unsigned __int16
0x18000ec46  lea     rdx, aRtQueue; "rt/queue"
0x18000ec4d  mov     ecx, eax; int
0x18000ec4f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000ec54  mov     eax, ebx
0x18000ec56  mov     rbx, [rsp+88h+arg_0]
0x18000ec5e  add     rsp, 80h
0x18000ec65  pop     rdi
0x18000ec66  retn
0x18000ec67  mov     [rsp+88h+var_40], 1
0x18000ec6f  mov     [rsp+88h+arg_8], 0
0x18000ec7b  xorps   xmm0, xmm0
0x18000ec7e  movups  [rsp+88h+var_28], xmm0
0x18000ec83  movups  [rsp+88h+var_18], xmm0
0x18000ec88  mov     word ptr [rsp+88h+var_28], 0
0x18000ec8f  lea     r8, [rsp+88h+arg_8]; wchar_t **
0x18000ec97  lea     rdx, [rsp+88h+var_28]; struct QUEUE_FORMAT *
0x18000ec9c  mov     rcx, rdi; wchar_t *
0x18000ec9f  call    ?FnFormatNameToQueueFormat@@YAHPEB_WPEAUQUEUE_FORMAT@@PEAPEA_W@Z; FnFormatNameToQueueFormat(wchar_t const *,QUEUE_FORMAT *,wchar_t * *)
0x18000eca4  test    eax, eax
0x18000eca6  jnz     short loc_18000ECDC
0x18000eca8  lea     r8d, [rax+46h]; unsigned __int16
0x18000ecac  lea     rdx, aRtQueue; "rt/queue"
0x18000ecb3  mov     ecx, 0C00E001Eh; int
0x18000ecb8  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000ecbd  mov     [rsp+88h+var_58], eax
0x18000ecc1  lea     rdx, loc_18000ECD3
0x18000ecc8  mov     rcx, [rsp+88h+var_50]
0x18000eccd  call    _local_unwind_0
0x18000ecd2  nop
0x18000ecd3  mov     eax, [rsp+88h+var_58]
0x18000ecd7  jmp     loc_18000EC56
0x18000ecdc  lea     rcx, [rsp+88h+var_28]; struct QUEUE_FORMAT *
0x18000ece1  call    ?IsLegalFormatNameOperation@@YAHPEBUQUEUE_FORMAT@@@Z; IsLegalFormatNameOperation(QUEUE_FORMAT const *)
0x18000ece6  test    eax, eax
0x18000ece8  jnz     short loc_18000ED1E
0x18000ecea  lea     r8d, [rax+50h]; unsigned __int16
0x18000ecee  lea     rdx, aRtQueue; "rt/queue"
0x18000ecf5  mov     ecx, 0C00E0020h; int
0x18000ecfa  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000ecff  mov     [rsp+88h+var_54], eax
0x18000ed03  lea     rdx, loc_18000ED15
0x18000ed0a  mov     rcx, [rsp+88h+var_50]
0x18000ed0f  call    _local_unwind_0
0x18000ed14  nop
0x18000ed15  mov     eax, [rsp+88h+var_54]
0x18000ed19  jmp     loc_18000EC56
0x18000ed1e  movzx   ecx, byte ptr [rsp+88h+var_28]
0x18000ed23  sub     ecx, 1
0x18000ed26  jz      short loc_18000ED9B
0x18000ed28  sub     ecx, 1
0x18000ed2b  jz      short loc_18000ED3B
0x18000ed2d  cmp     ecx, 1
0x18000ed30  jz      short loc_18000ED3B
0x18000ed32  mov     edi, [rsp+88h+var_48]
0x18000ed36  jmp     loc_18000EDC7
0x18000ed3b  xorps   xmm0, xmm0
0x18000ed3e  movups  [rsp+88h+var_38], xmm0
0x18000ed43  mov     dword ptr [rsp+88h+var_38], 1
0x18000ed4b  lea     rax, [rsp+88h+var_28]
0x18000ed50  mov     qword ptr [rsp+88h+var_38+8], rax
0x18000ed55  mov     ecx, cs:?g_hBindIndex@@3KA; dwTlsIndex
0x18000ed5b  call    cs:__imp_TlsGetValue
0x18000ed61  mov     [rsp+88h+arg_10], 0
0x18000ed6d  lea     rcx, [rsp+88h+var_38]
0x18000ed72  mov     [rsp+88h+var_68], rcx
0x18000ed77  mov     r9, rax
0x18000ed7a  xor     r8d, r8d; pReturnValue
0x18000ed7d  lea     edx, [r8+9]; nProcNum
0x18000ed81  lea     rcx, pProxyInfo; pProxyInfo
0x18000ed88  call    cs:__imp_NdrClientCall3
0x18000ed8e  mov     rbx, rax
0x18000ed91  mov     [rsp+88h+arg_10], rax
0x18000ed99  jmp     short loc_18000EDB1
0x18000ed9b  call    ?MachineDomain@@YAPEB_WXZ; MachineDomain(void)
0x18000eda0  lea     r9, [rsp+88h+var_28+8]
0x18000eda5  mov     rdx, rax
0x18000eda8  xor     ecx, ecx
0x18000edaa  call    ?ADDeleteObjectGuid@@YAJW4AD_OBJECT@@PEB_W_NPEBU_GUID@@@Z; ADDeleteObjectGuid(AD_OBJECT,wchar_t const *,bool,_GUID const *)
0x18000edaf  mov     ebx, eax
0x18000edb1  mov     edx, 1; unsigned int
0x18000edb6  mov     ecx, eax; int
0x18000edb8  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000edbd  mov     [rsp+88h+var_48], eax
0x18000edc1  mov     [rsp+88h+var_44], ebx
0x18000edc5  mov     edi, eax
0x18000edc7  jmp     short loc_18000EE23
0x18000edc9  mov     ebx, eax
0x18000edcb  mov     edx, [rsp+88h+var_40]; unsigned int
0x18000edcf  mov     ecx, eax; int
0x18000edd1  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000edd6  mov     edi, eax
0x18000edd8  mov     [rsp+88h+var_48], eax
0x18000eddc  mov     [rsp+88h+var_44], ebx
0x18000ede0  test    eax, eax
0x18000ede2  jg      short loc_18000EDE8
0x18000ede4  mov     ecx, eax
0x18000ede6  jmp     short loc_18000EDF1
0x18000ede8  movzx   ecx, di
0x18000edeb  or      ecx, 80070000h; int
0x18000edf1  mov     r8d, 5Ah ; 'Z'; unsigned __int16
0x18000edf7  lea     rdx, aRtQueue; "rt/queue"
0x18000edfe  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000ee03  test    edi, edi
0x18000ee05  js      short loc_18000EE23
0x18000ee07  mov     edx, [rsp+88h+var_40]; unsigned int
0x18000ee0b  mov     ecx, 0C00E000Bh; int
0x18000ee10  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000ee15  mov     edi, eax
0x18000ee17  mov     [rsp+88h+var_48], eax
0x18000ee1b  mov     [rsp+88h+var_44], 0C00E000Bh
0x18000ee23  mov     rcx, [rsp+88h+arg_8]; void *
0x18000ee2b  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x18000ee30  test    edi, edi
0x18000ee32  jns     short loc_18000EE48
0x18000ee34  mov     r8d, 64h ; 'd'; unsigned __int16
0x18000ee3a  lea     rdx, aRtQueue; "rt/queue"
0x18000ee41  mov     ecx, edi; int
0x18000ee43  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000ee48  mov     eax, edi
0x18000ee4a  jmp     loc_18000EC56
0x1800246d9  push    rbp
0x1800246db  sub     rsp, 30h
0x1800246df  mov     rbp, rdx
0x1800246e2  mov     rcx, [rbp+98h]; void *
0x1800246e9  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x1800246ee  nop
0x1800246ef  add     rsp, 30h
0x1800246f3  pop     rbp
0x1800246f4  retn
```
