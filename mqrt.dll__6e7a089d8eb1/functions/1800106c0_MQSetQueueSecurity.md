# MQSetQueueSecurity

- ea: `0x1800106c0`
- end: `0x180010a4f`
- name: `MQSetQueueSecurity`
- size: `911`
- prototype: `HRESULT __stdcall(LPCWSTR lpwcsFormatName, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005488`
- `0x1800087f8`
- `0x18000d9c8`
- `0x18000dae4`
- `0x1800106c0`
- `0x180013c74`
- `0x180014458`
- `0x180017ce0`
- `0x180018220`
- `0x18001a864`
- `0x18001d560`
- `0x180021060`
- `0x1800216a8`
- `0x180023c36`
- `0x180026010`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorLength` at `0x180010925`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180010925`

## pseudocode

```c
HRESULT __stdcall MQSetQueueSecurity(
        LPCWSTR lpwcsFormatName,
        SECURITY_INFORMATION SecurityInformation,
        PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  unsigned __int16 v5; // r8
  int v6; // ebx
  unsigned int *v8; // r8
  int Size; // ebx
  int v10; // eax
  int v11; // edi
  int v12; // ebx
  int v13; // ecx
  PSECURITY_DESCRIPTOR v14; // rbx
  const wchar_t *v15; // rdi
  bool v16; // dl
  void (*v17)(void); // rcx
  bool v18; // r8
  bool v19; // r9
  __int64 v20; // [rsp+0h] [rbp-D8h] BYREF
  int v21; // [rsp+50h] [rbp-88h]
  int v22; // [rsp+54h] [rbp-84h]
  unsigned int v23; // [rsp+58h] [rbp-80h]
  HRESULT v24; // [rsp+60h] [rbp-78h]
  HRESULT v25; // [rsp+64h] [rbp-74h]
  wchar_t *v26; // [rsp+68h] [rbp-70h] BYREF
  __int64 *v27; // [rsp+70h] [rbp-68h]
  __int128 v28; // [rsp+78h] [rbp-60h] BYREF
  PSECURITY_DESCRIPTOR v29; // [rsp+88h] [rbp-50h]
  _OWORD v30[2]; // [rsp+90h] [rbp-48h] BYREF
  _QWORD v31[5]; // [rsp+B0h] [rbp-28h] BYREF
  HRESULT v32; // [rsp+E8h] [rbp+10h]
  PSECURITY_DESCRIPTOR pSecurityDescriptora; // [rsp+F0h] [rbp+18h] BYREF
  void *v34; // [rsp+F8h] [rbp+20h] BYREF

  pSecurityDescriptora = pSecurityDescriptor;
  v27 = &v20;
  if ( (SecurityInformation & 0xF0000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_048d7302c6dd33c9f28b1c15e91ff05f_Traceguids,
        SecurityInformation);
    v5 = 1138;
    v6 = -1072824314;
    goto LABEL_6;
  }
  v6 = RtpOneTimeThreadInit();
  if ( v6 < 0 )
  {
    v5 = 1142;
LABEL_6:
    LogMsgHR(v6, (wchar_t *)L"rt/queue", v5);
    return v6;
  }
  v23 = 1;
  v34 = 0;
  v26 = 0;
  Size = RTpMakeSelfRelativeSDAndGetSize(&pSecurityDescriptora, &v34, v8);
  v10 = RTpConvertToMQCode(Size, 1u);
  v11 = v10;
  v21 = v10;
  v22 = Size;
  if ( v10 < 0 )
  {
    v32 = LogHR(v10, (wchar_t *)L"rt/queue", 0x1D6u);
    local_unwind_0(v27, &loc_1800107D8);
    return v32;
  }
  memset(v30, 0, sizeof(v30));
  LOWORD(v30[0]) = 0;
  if ( !(unsigned int)FnFormatNameToQueueFormat(lpwcsFormatName, (struct QUEUE_FORMAT *)v30, &v26) )
  {
    v24 = LogHR(-1072824290, (wchar_t *)L"rt/queue", 0x1E0u);
    local_unwind_0(v27, &loc_180010847);
    return v24;
  }
  if ( !(unsigned int)IsLegalFormatNameOperation((const struct QUEUE_FORMAT *)v30) )
  {
    v25 = LogHR(-1072824288, (wchar_t *)L"rt/queue", 0x1EAu);
    local_unwind_0(v27, &loc_18001088E);
    return v25;
  }
  if ( LOBYTE(v30[0]) == 1 )
  {
    v28 = 0;
    v29 = 0;
    LOWORD(v28) = 65;
    v14 = pSecurityDescriptora;
    if ( pSecurityDescriptora )
    {
      DWORD2(v28) = GetSecurityDescriptorLength(pSecurityDescriptora);
      v29 = v14;
    }
    else
    {
      DWORD2(v28) = 0;
      v29 = 0;
    }
    v15 = MachineDomain();
    v12 = ADInit(v17, v16, v18, v19);
    if ( v12 >= 0 )
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, _QWORD, char *, SECURITY_INFORMATION, int, __int128 *))(*(_QWORD *)g_pAD + 112LL))(
              g_pAD,
              0,
              v15,
              0,
              (char *)v30 + 8,
              SecurityInformation,
              1101,
              &v28);
    v13 = v12;
    goto LABEL_24;
  }
  if ( (unsigned int)LOBYTE(v30[0]) - 2 <= 1 )
  {
    v31[0] = 1;
    v31[1] = v30;
    v12 = RtpSetObjectSecurity((struct OBJECT_FORMAT *)v31, SecurityInformation, pSecurityDescriptora);
    v13 = v12;
LABEL_24:
    v21 = RTpConvertToMQCode(v13, 1u);
    v22 = v12;
    v11 = v21;
  }
  MmDeallocate(v34);
  MmDeallocate(v26);
  if ( v11 < 0 )
    LogMsgHR(v11, (wchar_t *)L"rt/queue", 0x1FEu);
  return v11;
}

```

## disassembly

```asm
0x1800106c0  mov     [rsp+arg_0], rbx
0x1800106c5  mov     [rsp+pSecurityDescriptor], r8
0x1800106ca  push    rdi
0x1800106cb  push    r12
0x1800106cd  push    r15
0x1800106cf  sub     rsp, 0C0h
0x1800106d6  mov     [rsp+0D8h+var_68], rsp
0x1800106db  mov     r15d, edx
0x1800106de  mov     r12, rcx
0x1800106e1  test    edx, 0F0000000h
0x1800106e7  jz      short loc_18001074A
0x1800106e9  lea     rax, WPP_GLOBAL_Control
0x1800106f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106f7  cmp     rcx, rax
0x1800106fa  jz      short loc_18001071A
0x1800106fc  test    byte ptr [rcx+1Ch], 1
0x180010700  jz      short loc_18001071A
0x180010702  mov     edx, 12h
0x180010707  mov     r9d, r15d
0x18001070a  lea     r8, WPP_048d7302c6dd33c9f28b1c15e91ff05f_Traceguids
0x180010711  mov     rcx, [rcx+10h]
0x180010715  call    WPP_SF_d
0x18001071a  mov     r8d, 472h; unsigned __int16
0x180010720  mov     ebx, 0C00E0006h
0x180010725  lea     rdx, aRtQueue; "rt/queue"
0x18001072c  mov     ecx, ebx; int
0x18001072e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180010733  mov     eax, ebx
0x180010735  mov     rbx, [rsp+0D8h+arg_0]
0x18001073d  add     rsp, 0C0h
0x180010744  pop     r15
0x180010746  pop     r12
0x180010748  pop     rdi
0x180010749  retn
0x18001074a  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x18001074f  mov     ebx, eax
0x180010751  test    eax, eax
0x180010753  jns     short loc_18001075D
0x180010755  mov     r8d, 476h
0x18001075b  jmp     short loc_180010725
0x18001075d  mov     [rsp+0D8h+var_80], 1
0x180010765  mov     [rsp+0D8h+arg_18], 0
0x180010771  mov     [rsp+0D8h+var_70], 0
0x18001077a  lea     rdx, [rsp+0D8h+arg_18]; void **
0x180010782  lea     rcx, [rsp+0D8h+pSecurityDescriptor]; void **
0x18001078a  call    ?RTpMakeSelfRelativeSDAndGetSize@@YAJPEAPEAX0PEAK@Z; RTpMakeSelfRelativeSDAndGetSize(void * *,void * *,ulong *)
0x18001078f  mov     ebx, eax
0x180010791  mov     edx, 1; unsigned int
0x180010796  mov     ecx, eax; int
0x180010798  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18001079d  mov     edi, eax
0x18001079f  mov     [rsp+0D8h+var_88], eax
0x1800107a3  mov     [rsp+0D8h+var_84], ebx
0x1800107a7  test    eax, eax
0x1800107a9  jns     short loc_1800107E4
0x1800107ab  mov     r8d, 1D6h; unsigned __int16
0x1800107b1  lea     rdx, aRtQueue; "rt/queue"
0x1800107b8  mov     ecx, eax; int
0x1800107ba  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x1800107bf  mov     [rsp+0D8h+arg_8], eax
0x1800107c6  lea     rdx, loc_1800107D8
0x1800107cd  mov     rcx, [rsp+0D8h+var_68]
0x1800107d2  call    _local_unwind_0
0x1800107d7  nop
0x1800107d8  mov     eax, [rsp+0D8h+arg_8]
0x1800107df  jmp     loc_180010735
0x1800107e4  xorps   xmm0, xmm0
0x1800107e7  movups  [rsp+0D8h+var_48], xmm0
0x1800107ef  movups  [rsp+0D8h+var_38], xmm0
0x1800107f7  mov     word ptr [rsp+0D8h+var_48], 0
0x180010801  lea     r8, [rsp+0D8h+var_70]; wchar_t **
0x180010806  lea     rdx, [rsp+0D8h+var_48]; struct QUEUE_FORMAT *
0x18001080e  mov     rcx, r12; wchar_t *
0x180010811  call    ?FnFormatNameToQueueFormat@@YAHPEB_WPEAUQUEUE_FORMAT@@PEAPEA_W@Z; FnFormatNameToQueueFormat(wchar_t const *,QUEUE_FORMAT *,wchar_t * *)
0x180010816  test    eax, eax
0x180010818  jnz     short loc_180010850
0x18001081a  mov     r8d, 1E0h; unsigned __int16
0x180010820  lea     rdx, aRtQueue; "rt/queue"
0x180010827  mov     ecx, 0C00E001Eh; int
0x18001082c  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x180010831  mov     [rsp+0D8h+var_78], eax
0x180010835  lea     rdx, loc_180010847
0x18001083c  mov     rcx, [rsp+0D8h+var_68]
0x180010841  call    _local_unwind_0
0x180010846  nop
0x180010847  mov     eax, [rsp+0D8h+var_78]
0x18001084b  jmp     loc_180010735
0x180010850  lea     rcx, [rsp+0D8h+var_48]; struct QUEUE_FORMAT *
0x180010858  call    ?IsLegalFormatNameOperation@@YAHPEBUQUEUE_FORMAT@@@Z; IsLegalFormatNameOperation(QUEUE_FORMAT const *)
0x18001085d  test    eax, eax
0x18001085f  jnz     short loc_180010897
0x180010861  mov     r8d, 1EAh; unsigned __int16
0x180010867  lea     rdx, aRtQueue; "rt/queue"
0x18001086e  mov     ecx, 0C00E0020h; int
0x180010873  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x180010878  mov     [rsp+0D8h+var_74], eax
0x18001087c  lea     rdx, loc_18001088E
0x180010883  mov     rcx, [rsp+0D8h+var_68]
0x180010888  call    _local_unwind_0
0x18001088d  nop
0x18001088e  mov     eax, [rsp+0D8h+var_74]
0x180010892  jmp     loc_180010735
0x180010897  movzx   ecx, byte ptr [rsp+0D8h+var_48]
0x18001089f  sub     ecx, 1
0x1800108a2  jz      short loc_1800108F9
0x1800108a4  sub     ecx, 1
0x1800108a7  jz      short loc_1800108B2
0x1800108a9  cmp     ecx, 1
0x1800108ac  jnz     loc_1800109BD
0x1800108b2  xorps   xmm0, xmm0
0x1800108b5  movups  xmmword ptr [rsp+0D8h+var_28], xmm0
0x1800108bd  mov     dword ptr [rsp+0D8h+var_28], 1
0x1800108c8  lea     rax, [rsp+0D8h+var_48]
0x1800108d0  mov     [rsp+0D8h+var_28+8], rax
0x1800108d8  mov     r8, [rsp+0D8h+pSecurityDescriptor]; void *
0x1800108e0  mov     edx, r15d; unsigned int
0x1800108e3  lea     rcx, [rsp+0D8h+var_28]; struct OBJECT_FORMAT *
0x1800108eb  call    ?RtpSetObjectSecurity@@YAJPEAUOBJECT_FORMAT@@KPEAX@Z; RtpSetObjectSecurity(OBJECT_FORMAT *,ulong,void *)
0x1800108f0  mov     ebx, eax
0x1800108f2  mov     ecx, eax
0x1800108f4  jmp     loc_1800109A9
0x1800108f9  xorps   xmm0, xmm0
0x1800108fc  xor     eax, eax
0x1800108fe  movups  [rsp+0D8h+var_60], xmm0
0x180010903  mov     [rsp+0D8h+var_50], rax
0x18001090b  mov     eax, 41h ; 'A'
0x180010910  mov     word ptr [rsp+0D8h+var_60], ax
0x180010915  mov     rbx, [rsp+0D8h+pSecurityDescriptor]
0x18001091d  test    rbx, rbx
0x180010920  jz      short loc_18001093C
0x180010922  mov     rcx, rbx; pSecurityDescriptor
0x180010925  call    cs:__imp_GetSecurityDescriptorLength
0x18001092b  mov     dword ptr [rsp+0D8h+var_60+8], eax
0x180010932  mov     [rsp+0D8h+var_50], rbx
0x18001093a  jmp     short loc_180010953
0x18001093c  mov     dword ptr [rsp+0D8h+var_60+8], 0
0x180010947  mov     [rsp+0D8h+var_50], 0
0x180010953  call    ?MachineDomain@@YAPEB_WXZ; MachineDomain(void)
0x180010958  mov     rdi, rax
0x18001095b  call    ?ADInit@@YAJP6AXXZ_N11@Z; ADInit(void (*)(void),bool,bool,bool)
0x180010960  mov     ebx, eax
0x180010962  test    eax, eax
0x180010964  js      short loc_1800109A7
0x180010966  mov     rcx, cs:?g_pAD@@3V?$P@VCBaseADProvider@@@@A; P<CBaseADProvider> g_pAD
0x18001096d  mov     rax, [rcx]
0x180010970  lea     rdx, [rsp+0D8h+var_60]
0x180010975  mov     [rsp+0D8h+var_A0], rdx
0x18001097a  mov     [rsp+0D8h+var_A8], 44Dh
0x180010982  mov     [rsp+0D8h+var_B0], r15d
0x180010987  lea     rdx, [rsp+0D8h+var_48+8]
0x18001098f  mov     [rsp+0D8h+var_B8], rdx
0x180010994  xor     r9d, r9d
0x180010997  mov     r8, rdi
0x18001099a  xor     edx, edx
0x18001099c  mov     rax, [rax+70h]
0x1800109a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109a5  mov     ebx, eax
0x1800109a7  mov     ecx, ebx; int
0x1800109a9  mov     edx, 1; unsigned int
0x1800109ae  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x1800109b3  mov     [rsp+0D8h+var_88], eax
0x1800109b7  mov     [rsp+0D8h+var_84], ebx
0x1800109bb  mov     edi, eax
0x1800109bd  jmp     short loc_180010A19
0x1800109bf  mov     ebx, eax
0x1800109c1  mov     edx, [rsp+0D8h+var_80]; unsigned int
0x1800109c5  mov     ecx, eax; int
0x1800109c7  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x1800109cc  mov     edi, eax
0x1800109ce  mov     [rsp+0D8h+var_88], eax
0x1800109d2  mov     [rsp+0D8h+var_84], ebx
0x1800109d6  test    eax, eax
0x1800109d8  jg      short loc_1800109DE
0x1800109da  mov     ecx, eax
0x1800109dc  jmp     short loc_1800109E7
0x1800109de  movzx   ecx, di
0x1800109e1  or      ecx, 80070000h; int
0x1800109e7  mov     r8d, 1F4h; unsigned __int16
0x1800109ed  lea     rdx, aRtQueue; "rt/queue"
0x1800109f4  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x1800109f9  test    edi, edi
0x1800109fb  js      short loc_180010A19
0x1800109fd  mov     edx, [rsp+0D8h+var_80]; unsigned int
0x180010a01  mov     ecx, 0C00E000Bh; int
0x180010a06  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x180010a0b  mov     edi, eax
0x180010a0d  mov     [rsp+0D8h+var_88], eax
0x180010a11  mov     [rsp+0D8h+var_84], 0C00E000Bh
0x180010a19  mov     rcx, [rsp+0D8h+arg_18]; void *
0x180010a21  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x180010a26  mov     rcx, [rsp+0D8h+var_70]; void *
0x180010a2b  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x180010a30  test    edi, edi
0x180010a32  jns     short loc_180010A48
0x180010a34  mov     r8d, 1FEh; unsigned __int16
0x180010a3a  lea     rdx, aRtQueue; "rt/queue"
0x180010a41  mov     ecx, edi; int
0x180010a43  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180010a48  mov     eax, edi
0x180010a4a  jmp     loc_180010735
0x1800247c7  push    rbp
0x1800247c9  sub     rsp, 50h
0x1800247cd  mov     rbp, rdx
0x1800247d0  mov     rcx, [rbp+0F8h]; void *
0x1800247d7  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x1800247dc  mov     rcx, [rbp+68h]; void *
0x1800247e0  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x1800247e5  nop
0x1800247e6  add     rsp, 50h
0x1800247ea  pop     rbp
0x1800247eb  retn
```
