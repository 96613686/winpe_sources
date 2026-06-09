# EapCacheIdentityInfo

- ea: `0x18002578c`
- end: `0x1800258bf`
- name: `EapCacheIdentityInfo`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180009540`
- `0x180024860`

## callees

- `0x180005440`
- `0x1800129b0`
- `0x1800214f0`
- `0x180025740`
- `0x18002578c`

## import_xrefs

- `MobileNetworking!SetBufferAndLength` at `0x18002583f`
- `MobileNetworking!SetBufferAndLength` at `0x18002583f`
- `MobileNetworking!FreeMemory` at `0x18002587d`
- `MobileNetworking!FreeMemory` at `0x18002587d`

## string_xrefs

- `0x180025871`: `EapCacheIdentityInfo`

## pseudocode

```c
__int64 __fastcall EapCacheIdentityInfo(EAP_SESSIONID *a1)
{
  __int64 v1; // rax
  unsigned int v3; // esi
  unsigned int EaphostAuthStatusData; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  DWORD v9; // [rsp+50h] [rbp+8h] BYREF
  __int64 v10; // [rsp+58h] [rbp+10h] BYREF

  v1 = *(_QWORD *)a1;
  v9 = 0;
  v3 = *(_DWORD *)(v1 + 20);
  v10 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 314, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
  EaphostAuthStatusData = EapGetEaphostAuthStatusData(a1, 0, &v10, &v9);
  v5 = EaphostAuthStatusData;
  if ( EaphostAuthStatusData )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v7 = 315;
LABEL_8:
      WPP_SF_dD(v6[7], v7, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v3, EaphostAuthStatusData);
    }
  }
  else
  {
    EaphostAuthStatusData = SetBufferAndLength(a1 + 10, a1 + 8, v10, v9);
    v5 = EaphostAuthStatusData;
    if ( !EaphostAuthStatusData )
    {
      a1[7] = 1;
      goto LABEL_14;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v7 = 316;
      goto LABEL_8;
    }
  }
LABEL_14:
  FreeMemory(&v10, "EapCacheIdentityInfo", 2904);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 317, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18002578c  mov     [rsp+arg_10], rbx
0x180025791  push    rbp
0x180025792  push    rsi
0x180025793  push    rdi
0x180025794  sub     rsp, 30h
0x180025798  mov     rax, [rcx]
0x18002579b  mov     rdi, rcx
0x18002579e  mov     [rsp+48h+arg_0], 0
0x1800257a6  mov     esi, [rax+14h]
0x1800257a9  mov     [rsp+48h+arg_8], 0
0x1800257b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257b9  lea     rbp, WPP_GLOBAL_Control
0x1800257c0  cmp     rcx, rbp
0x1800257c3  jz      short loc_1800257E3
0x1800257c5  test    dword ptr [rcx+44h], 800h
0x1800257cc  jz      short loc_1800257E3
0x1800257ce  mov     rcx, [rcx+38h]
0x1800257d2  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x1800257d9  mov     edx, 13Ah
0x1800257de  call    WPP_SF_
0x1800257e3  lea     r9, [rsp+48h+arg_0]
0x1800257e8  xor     edx, edx
0x1800257ea  lea     r8, [rsp+48h+arg_8]
0x1800257ef  mov     rcx, rdi
0x1800257f2  call    EapGetEaphostAuthStatusData
0x1800257f7  mov     ebx, eax
0x1800257f9  test    eax, eax
0x1800257fb  jz      short loc_18002582D
0x1800257fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180025804  cmp     rcx, rbp
0x180025807  jz      short loc_18002586B
0x180025809  test    byte ptr [rcx+44h], 1
0x18002580d  jz      short loc_18002586B
0x18002580f  mov     edx, 13Bh
0x180025814  mov     rcx, [rcx+38h]
0x180025818  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18002581f  mov     r9d, esi
0x180025822  mov     [rsp+48h+var_28], eax
0x180025826  call    WPP_SF_dD
0x18002582b  jmp     short loc_18002586B
0x18002582d  mov     r9d, [rsp+48h+arg_0]
0x180025832  lea     rdx, [rdi+20h]
0x180025836  mov     r8, [rsp+48h+arg_8]
0x18002583b  lea     rcx, [rdi+28h]
0x18002583f  call    cs:__imp_SetBufferAndLength
0x180025845  mov     ebx, eax
0x180025847  test    eax, eax
0x180025849  jz      short loc_180025864
0x18002584b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025852  cmp     rcx, rbp
0x180025855  jz      short loc_18002586B
0x180025857  test    byte ptr [rcx+44h], 1
0x18002585b  jz      short loc_18002586B
0x18002585d  mov     edx, 13Ch
0x180025862  jmp     short loc_180025814
0x180025864  mov     dword ptr [rdi+1Ch], 1
0x18002586b  mov     r8d, 0B58h
0x180025871  lea     rdx, aEapcacheidenti; "EapCacheIdentityInfo"
0x180025878  lea     rcx, [rsp+48h+arg_8]
0x18002587d  call    cs:__imp_FreeMemory
0x180025883  mov     rcx, cs:WPP_GLOBAL_Control
0x18002588a  cmp     rcx, rbp
0x18002588d  jz      short loc_1800258B0
0x18002588f  test    dword ptr [rcx+44h], 800h
0x180025896  jz      short loc_1800258B0
0x180025898  mov     rcx, [rcx+38h]
0x18002589c  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x1800258a3  mov     edx, 13Dh
0x1800258a8  mov     r9d, ebx
0x1800258ab  call    WPP_SF_D
0x1800258b0  mov     eax, ebx
0x1800258b2  mov     rbx, [rsp+48h+arg_10]
0x1800258b7  add     rsp, 30h
0x1800258bb  pop     rdi
0x1800258bc  pop     rsi
0x1800258bd  pop     rbp
0x1800258be  retn
```
