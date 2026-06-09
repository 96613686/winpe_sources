# DeviceCollectionBuildFromMultiSz(ushort * const,_COLLECTION_TYPE,DEVICE_COLLECTION *)

- ea: `0x180002824`
- end: `0x180002c6b`
- name: `?DeviceCollectionBuildFromMultiSz@@YAHQEAGW4_COLLECTION_TYPE@@PEAUDEVICE_COLLECTION@@@Z`
- size: `1095`
- prototype: `__int64 __fastcall(WCHAR *, int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180002c74`
- `0x180006eac`

## callees

- `0x180002824`
- `0x180002d70`
- `0x180002f9c`
- `0x180005610`
- `0x180008760`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800029bc`
- `KERNEL32!LocalFree` at `0x1800029bc`
- `KERNEL32!LocalAlloc` at `0x1800028af`
- `KERNEL32!LocalAlloc` at `0x1800028af`
- `CFGMGR32!CM_Locate_DevNodeW` at `0x1800029ed`
- `CFGMGR32!CM_Locate_DevNodeW` at `0x1800029ed`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x180002aba`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x180002aba`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180002a26`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180002a78`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180002a26`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180002a78`
- `SETUPAPI!pSetupGuidFromString` at `0x18000299b`
- `SETUPAPI!pSetupGuidFromString` at `0x180002adc`
- `SETUPAPI!pSetupGuidFromString` at `0x18000299b`
- `SETUPAPI!pSetupGuidFromString` at `0x180002adc`

## pseudocode

```c
__int64 __fastcall DeviceCollectionBuildFromMultiSz(WCHAR *a1, int a2, __int64 a3)
{
  unsigned int v5; // r14d
  int v6; // r12d
  int v7; // r13d
  _QWORD *v8; // rsi
  WCHAR *v9; // rax
  __int64 v10; // r8
  WCHAR *v11; // r9
  __int64 v12; // rdx
  int v13; // r11d
  __int64 v14; // rcx
  WCHAR v15; // r10
  _QWORD *v16; // rax
  WCHAR *v17; // rax
  __int64 v18; // r8
  WCHAR *v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rcx
  WCHAR v22; // r10
  __int64 v23; // rax
  ULONG pulLength; // [rsp+40h] [rbp-118h] BYREF
  DEVNODE pdnDevInst; // [rsp+44h] [rbp-114h] BYREF
  int Buffer; // [rsp+48h] [rbp-110h] BYREF
  int v28; // [rsp+4Ch] [rbp-10Ch]
  int v29; // [rsp+50h] [rbp-108h] BYREF
  int v30; // [rsp+54h] [rbp-104h]
  int v31; // [rsp+58h] [rbp-100h]
  WCHAR *v32; // [rsp+60h] [rbp-F8h]
  __int64 v33; // [rsp+68h] [rbp-F0h]
  WCHAR *v34; // [rsp+70h] [rbp-E8h]
  __int64 v35; // [rsp+78h] [rbp-E0h]
  int v36; // [rsp+80h] [rbp-D8h]
  WCHAR *v37; // [rsp+88h] [rbp-D0h]
  __int64 v38; // [rsp+90h] [rbp-C8h]
  __int64 v39; // [rsp+98h] [rbp-C0h]
  WCHAR *v40; // [rsp+A0h] [rbp-B8h]
  __int64 v41; // [rsp+A8h] [rbp-B0h]
  __int64 v42; // [rsp+B0h] [rbp-A8h]
  __int64 v43; // [rsp+B8h] [rbp-A0h]
  GUID v44; // [rsp+C0h] [rbp-98h] BYREF
  _BYTE v45[76]; // [rsp+D0h] [rbp-88h] BYREF
  __int16 v46; // [rsp+11Ch] [rbp-3Ch]

  v28 = a2;
  v43 = a3;
  pdnDevInst = 0;
  Buffer = 0;
  v29 = 0;
  pulLength = 0;
  v44 = 0;
  v5 = 0;
  v30 = 0;
  v6 = 0;
  v7 = 0;
  *(_QWORD *)(a3 + 16) = 0;
  *(_QWORD *)(a3 + 24) = 0;
  *(_QWORD *)(a3 + 8) = a3;
  *(_QWORD *)a3 = a3;
  while ( *a1 )
  {
    v8 = LocalAlloc(0x40u, 0x1C8u);
    if ( !v8 )
      goto LABEL_42;
    if ( v28 == 3 )
    {
      v31 = ++v7;
      v9 = (WCHAR *)(v8 + 2);
      v10 = 2147483646;
      v39 = 2147483646;
      v11 = a1;
      v37 = a1;
      v12 = 201;
      v38 = 201;
      v32 = (WCHAR *)(v8 + 2);
      v13 = 0;
      v14 = 0;
      v33 = 0;
      while ( v12 )
      {
        if ( !v10 )
          goto LABEL_12;
        v15 = *v11;
        if ( !*v11 )
          goto LABEL_12;
        v37 = ++v11;
        *v9++ = v15;
        v32 = v9;
        v38 = --v12;
        v39 = --v10;
        v33 = ++v14;
      }
      v32 = --v9;
      v33 = v14 - 1;
      v13 = -2147024774;
LABEL_12:
      *v9 = 0;
      if ( v13 >= 0 && !(unsigned int)pSetupGuidFromString(a1, (char *)v8 + 436) )
      {
        v16 = *(_QWORD **)(a3 + 8);
        if ( *v16 != a3 )
          __fastfail(3u);
        goto LABEL_37;
      }
      LocalFree(v8);
    }
    else
    {
      Buffer = 0;
      v44 = GUID_NULL;
      if ( CM_Locate_DevNodeW(&pdnDevInst, a1, v28 != 4) )
        goto LABEL_28;
      pulLength = 4;
      if ( !CM_Get_DevNode_Registry_Property_ExW(pdnDevInst, 0x10u, 0, &Buffer, &pulLength, 0, 0) )
      {
        if ( (Buffer & 8) != 0 )
          v6 = 1;
        v36 = v6;
      }
      if ( v28 != 2
        || (pulLength = 4, CM_Get_DevNode_Registry_Property_ExW(pdnDevInst, 0xBu, 0, &v29, &pulLength, 0, 0))
        || (v29 & 0x4000) == 0 )
      {
        pulLength = 78;
        if ( !CM_Get_DevNode_Registry_PropertyW(pdnDevInst, 9u, 0, v45, &pulLength, 0) )
        {
          v46 = 0;
          if ( (unsigned int)pSetupGuidFromString(v45, &v44) )
            v44 = GUID_NULL;
        }
LABEL_28:
        v31 = ++v7;
        v17 = (WCHAR *)(v8 + 2);
        v18 = 2147483646;
        v42 = 2147483646;
        v19 = a1;
        v40 = a1;
        v20 = 201;
        v41 = 201;
        v34 = (WCHAR *)(v8 + 2);
        v21 = 0;
        v35 = 0;
        while ( v20 )
        {
          if ( !v18 )
            goto LABEL_35;
          v22 = *v19;
          if ( !*v19 )
            goto LABEL_35;
          v40 = ++v19;
          *v17++ = v22;
          v34 = v17;
          v41 = --v20;
          v42 = --v18;
          v35 = ++v21;
        }
        v34 = --v17;
        v35 = v21 - 1;
LABEL_35:
        *v17 = 0;
        v8[53] = BuildFriendlyName(pdnDevInst);
        *((_DWORD *)v8 + 108) = Buffer;
        *(GUID *)((char *)v8 + 436) = v44;
        v16 = *(_QWORD **)(a3 + 8);
        if ( *v16 != a3 )
          __fastfail(3u);
LABEL_37:
        *v8 = a3;
        v8[1] = v16;
        *v16 = v8;
        *(_QWORD *)(a3 + 8) = v8;
      }
    }
    v23 = -1;
    do
      ++v23;
    while ( a1[v23] );
    a1 += v23 + 1;
  }
  *(_DWORD *)(a3 + 16) = v7;
  *(_DWORD *)(a3 + 20) = v6;
  DeviceCollectionPrepImageList((struct DEVICE_COLLECTION *)a3);
  v5 = 1;
  v30 = 1;
LABEL_42:
  if ( !v5 )
    DeviceCollectionDestroy((struct DEVICE_COLLECTION *)a3);
  return v5;
}

```

## disassembly

```asm
0x180002824  mov     [rsp+arg_8], rbx
0x180002829  mov     [rsp+arg_18], rsi
0x18000282e  push    rdi
0x18000282f  push    r12
0x180002831  push    r13
0x180002833  push    r14
0x180002835  push    r15
0x180002837  sub     rsp, 130h
0x18000283e  mov     rax, cs:__security_cookie
0x180002845  xor     rax, rsp
0x180002848  mov     [rsp+158h+var_38], rax
0x180002850  mov     rdi, r8
0x180002853  mov     [rsp+158h+var_10C], edx
0x180002857  mov     r15, rcx
0x18000285a  mov     [rsp+158h+var_A0], r8
0x180002862  xor     ebx, ebx
0x180002864  mov     [rsp+158h+pdnDevInst], ebx
0x180002868  mov     [rsp+158h+Buffer], ebx
0x18000286c  mov     [rsp+158h+var_108], ebx
0x180002870  mov     [rsp+158h+var_118], ebx
0x180002874  xorps   xmm0, xmm0
0x180002877  movups  [rsp+158h+var_98], xmm0
0x18000287f  mov     r14d, ebx
0x180002882  mov     [rsp+158h+var_104], ebx
0x180002886  mov     r12d, ebx
0x180002889  mov     r13d, ebx
0x18000288c  mov     [r8+10h], rbx
0x180002890  mov     [r8+18h], rbx
0x180002894  mov     [r8+8], r8
0x180002898  mov     [r8], r8
0x18000289b  cmp     [r15], bx
0x18000289f  jz      loc_180002C04
0x1800028a5  mov     edx, 1C8h; uBytes
0x1800028aa  mov     ecx, 40h ; '@'; uFlags
0x1800028af  call    cs:__imp_LocalAlloc
0x1800028b5  mov     rsi, rax
0x1800028b8  test    rax, rax
0x1800028bb  jz      loc_180002C1F
0x1800028c1  mov     eax, [rsp+158h+var_10C]
0x1800028c5  cmp     eax, 3
0x1800028c8  jnz     loc_1800029C7
0x1800028ce  lea     r10d, [rax-2]
0x1800028d2  add     r13d, r10d
0x1800028d5  mov     [rsp+158h+var_100], r13d
0x1800028da  lea     rax, [rsi+10h]
0x1800028de  mov     r8d, 7FFFFFFEh
0x1800028e4  mov     [rsp+158h+var_C0], r8
0x1800028ec  mov     r9, r15
0x1800028ef  mov     [rsp+158h+var_D0], r15
0x1800028f7  mov     edx, 0C9h
0x1800028fc  mov     [rsp+158h+var_C8], rdx
0x180002904  mov     [rsp+158h+var_F8], rax
0x180002909  mov     r11d, ebx
0x18000290c  mov     rcx, rbx
0x18000290f  mov     [rsp+158h+var_F0], rbx
0x180002914  test    rdx, rdx
0x180002917  jz      short loc_180002972
0x180002919  test    r8, r8
0x18000291c  jz      short loc_18000296D
0x18000291e  movzx   r10d, word ptr [r9]
0x180002922  test    r10w, r10w
0x180002926  jz      short loc_180002967
0x180002928  add     r9, 2
0x18000292c  mov     [rsp+158h+var_D0], r9
0x180002934  mov     [rax], r10w
0x180002938  add     rax, 2
0x18000293c  mov     [rsp+158h+var_F8], rax
0x180002941  mov     r10d, 1
0x180002947  sub     rdx, r10
0x18000294a  mov     [rsp+158h+var_C8], rdx
0x180002952  sub     r8, r10
0x180002955  mov     [rsp+158h+var_C0], r8
0x18000295d  add     rcx, r10
0x180002960  mov     [rsp+158h+var_F0], rcx
0x180002965  jmp     short loc_180002914
0x180002967  mov     r10d, 1
0x18000296d  test    rdx, rdx
0x180002970  jnz     short loc_180002989
0x180002972  sub     rax, 2
0x180002976  mov     [rsp+158h+var_F8], rax
0x18000297b  sub     rcx, r10
0x18000297e  mov     [rsp+158h+var_F0], rcx
0x180002983  mov     r11d, 8007007Ah
0x180002989  mov     [rax], bx
0x18000298c  test    r11d, r11d
0x18000298f  js      short loc_1800029B9
0x180002991  lea     rdx, [rsi+1B4h]
0x180002998  mov     rcx, r15
0x18000299b  call    cs:__imp_pSetupGuidFromString
0x1800029a1  test    eax, eax
0x1800029a3  jnz     short loc_1800029B9
0x1800029a5  mov     rax, [rdi+8]
0x1800029a9  cmp     [rax], rdi
0x1800029ac  jz      loc_180002BDB
0x1800029b2  mov     ecx, 3
0x1800029b7  int     29h; Win8: RtlFailFast(ecx)
0x1800029b9  mov     rcx, rsi; hMem
0x1800029bc  call    cs:__imp_LocalFree
0x1800029c2  jmp     loc_180002BE9
0x1800029c7  mov     [rsp+158h+Buffer], ebx
0x1800029cb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800029d2  movdqu  [rsp+158h+var_98], xmm0
0x1800029db  mov     r8d, ebx
0x1800029de  cmp     eax, 4
0x1800029e1  setnz   r8b; ulFlags
0x1800029e5  mov     rdx, r15; pDeviceID
0x1800029e8  lea     rcx, [rsp+158h+pdnDevInst]; pdnDevInst
0x1800029ed  call    cs:__imp_CM_Locate_DevNodeW
0x1800029f3  test    eax, eax
0x1800029f5  jnz     loc_180002AF6
0x1800029fb  mov     [rsp+158h+var_118], 4
0x180002a03  mov     [rsp+158h+hMachine], rbx; hMachine
0x180002a08  mov     [rsp+158h+ulFlags], ebx; ulFlags
0x180002a0c  lea     rax, [rsp+158h+var_118]
0x180002a11  mov     [rsp+158h+pulLength], rax; pulLength
0x180002a16  lea     r9, [rsp+158h+Buffer]; Buffer
0x180002a1b  xor     r8d, r8d; pulRegDataType
0x180002a1e  lea     edx, [r8+10h]; ulProperty
0x180002a22  mov     ecx, [rsp+158h+pdnDevInst]; dnDevInst
0x180002a26  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x180002a2c  test    eax, eax
0x180002a2e  jnz     short loc_180002A46
0x180002a30  test    byte ptr [rsp+158h+Buffer], 8
0x180002a35  mov     eax, 1
0x180002a3a  cmovnz  r12d, eax
0x180002a3e  mov     [rsp+158h+var_D8], r12d
0x180002a46  cmp     [rsp+158h+var_10C], 2
0x180002a4b  jnz     short loc_180002A91
0x180002a4d  mov     [rsp+158h+var_118], 4
0x180002a55  mov     [rsp+158h+hMachine], rbx; hMachine
0x180002a5a  mov     [rsp+158h+ulFlags], ebx; ulFlags
0x180002a5e  lea     rax, [rsp+158h+var_118]
0x180002a63  mov     [rsp+158h+pulLength], rax; pulLength
0x180002a68  lea     r9, [rsp+158h+var_108]; Buffer
0x180002a6d  xor     r8d, r8d; pulRegDataType
0x180002a70  lea     edx, [r8+0Bh]; ulProperty
0x180002a74  mov     ecx, [rsp+158h+pdnDevInst]; dnDevInst
0x180002a78  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x180002a7e  test    eax, eax
0x180002a80  jnz     short loc_180002A91
0x180002a82  test    [rsp+158h+var_108], 4000h
0x180002a8a  jz      short loc_180002A91
0x180002a8c  jmp     loc_180002BE9
0x180002a91  mov     [rsp+158h+var_118], 4Eh ; 'N'
0x180002a99  mov     [rsp+158h+ulFlags], ebx; ulFlags
0x180002a9d  lea     rax, [rsp+158h+var_118]
0x180002aa2  mov     [rsp+158h+pulLength], rax; pulLength
0x180002aa7  lea     r9, [rsp+158h+var_88]; Buffer
0x180002aaf  xor     r8d, r8d; pulRegDataType
0x180002ab2  lea     edx, [r8+9]; ulProperty
0x180002ab6  mov     ecx, [rsp+158h+pdnDevInst]; dnDevInst
0x180002aba  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x180002ac0  test    eax, eax
0x180002ac2  jnz     short loc_180002AF6
0x180002ac4  mov     [rsp+158h+var_3C], bx
0x180002acc  lea     rdx, [rsp+158h+var_98]
0x180002ad4  lea     rcx, [rsp+158h+var_88]
0x180002adc  call    cs:__imp_pSetupGuidFromString
0x180002ae2  test    eax, eax
0x180002ae4  jz      short loc_180002AF6
0x180002ae6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180002aed  movdqu  [rsp+158h+var_98], xmm0
0x180002af6  mov     r11d, 1
0x180002afc  add     r13d, r11d
0x180002aff  mov     [rsp+158h+var_100], r13d
0x180002b04  lea     rax, [rsi+10h]
0x180002b08  mov     r8d, 7FFFFFFEh
0x180002b0e  mov     [rsp+158h+var_A8], r8
0x180002b16  mov     r9, r15
0x180002b19  mov     [rsp+158h+var_B8], r15
0x180002b21  mov     edx, 0C9h
0x180002b26  mov     [rsp+158h+var_B0], rdx
0x180002b2e  mov     [rsp+158h+var_E8], rax
0x180002b33  mov     rcx, rbx
0x180002b36  mov     [rsp+158h+var_E0], rbx
0x180002b3b  test    rdx, rdx
0x180002b3e  jz      short loc_180002B8D
0x180002b40  test    r8, r8
0x180002b43  jz      short loc_180002B88
0x180002b45  movzx   r10d, word ptr [r9]
0x180002b49  test    r10w, r10w
0x180002b4d  jz      short loc_180002B88
0x180002b4f  add     r9, 2
0x180002b53  mov     [rsp+158h+var_B8], r9
0x180002b5b  mov     [rax], r10w
0x180002b5f  add     rax, 2
0x180002b63  mov     [rsp+158h+var_E8], rax
0x180002b68  sub     rdx, r11
0x180002b6b  mov     [rsp+158h+var_B0], rdx
0x180002b73  sub     r8, r11
0x180002b76  mov     [rsp+158h+var_A8], r8
0x180002b7e  add     rcx, r11
0x180002b81  mov     [rsp+158h+var_E0], rcx
0x180002b86  jmp     short loc_180002B3B
0x180002b88  test    rdx, rdx
0x180002b8b  jnz     short loc_180002B9E
0x180002b8d  sub     rax, 2
0x180002b91  mov     [rsp+158h+var_E8], rax
0x180002b96  sub     rcx, r11
0x180002b99  mov     [rsp+158h+var_E0], rcx
0x180002b9e  mov     [rax], bx
0x180002ba1  mov     ecx, [rsp+158h+pdnDevInst]; dnDevInst
0x180002ba5  call    ?BuildFriendlyName@@YAPEAGK@Z; BuildFriendlyName(ulong)
0x180002baa  mov     [rsi+1A8h], rax
0x180002bb1  mov     eax, [rsp+158h+Buffer]
0x180002bb5  mov     [rsi+1B0h], eax
0x180002bbb  movups  xmm0, [rsp+158h+var_98]
0x180002bc3  movdqu  xmmword ptr [rsi+1B4h], xmm0
0x180002bcb  mov     rax, [rdi+8]
0x180002bcf  cmp     [rax], rdi
0x180002bd2  jz      short loc_180002BDB
0x180002bd4  mov     ecx, 3
0x180002bd9  int     29h; Win8: RtlFailFast(ecx)
0x180002bdb  mov     [rsi], rdi
0x180002bde  mov     [rsi+8], rax
0x180002be2  mov     [rax], rsi
0x180002be5  mov     [rdi+8], rsi
0x180002be9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002bed  inc     rax
0x180002bf0  cmp     [r15+rax*2], bx
0x180002bf5  jnz     short loc_180002BED
0x180002bf7  lea     r15, [r15+rax*2]
0x180002bfb  add     r15, 2
0x180002bff  jmp     loc_18000289B
0x180002c04  mov     [rdi+10h], r13d
0x180002c08  mov     [rdi+14h], r12d
0x180002c0c  mov     rcx, rdi; struct DEVICE_COLLECTION *
0x180002c0f  call    ?DeviceCollectionPrepImageList@@YAHPEAUDEVICE_COLLECTION@@@Z; DeviceCollectionPrepImageList(DEVICE_COLLECTION *)
0x180002c14  mov     r14d, 1
0x180002c1a  mov     [rsp+158h+var_104], r14d
0x180002c1f  jmp     short loc_180002C2E
0x180002c21  mov     r14d, [rsp+158h+var_104]
0x180002c26  mov     rdi, [rsp+158h+var_A0]
0x180002c2e  test    r14d, r14d
0x180002c31  jnz     short loc_180002C3B
0x180002c33  mov     rcx, rdi; struct DEVICE_COLLECTION *
0x180002c36  call    ?DeviceCollectionDestroy@@YAXPEAUDEVICE_COLLECTION@@@Z; DeviceCollectionDestroy(DEVICE_COLLECTION *)
0x180002c3b  mov     eax, r14d
0x180002c3e  mov     rcx, [rsp+158h+var_38]
0x180002c46  xor     rcx, rsp; StackCookie
0x180002c49  call    __security_check_cookie
0x180002c4e  lea     r11, [rsp+158h+var_28]
0x180002c56  mov     rbx, [r11+38h]
0x180002c5a  mov     rsi, [r11+48h]
0x180002c5e  mov     rsp, r11
0x180002c61  pop     r15
0x180002c63  pop     r14
0x180002c65  pop     r13
0x180002c67  pop     r12
0x180002c69  pop     rdi
0x180002c6a  retn
```
