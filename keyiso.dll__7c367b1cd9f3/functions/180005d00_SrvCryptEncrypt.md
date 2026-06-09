# SrvCryptEncrypt

- ea: `0x180005d00`
- end: `0x180005ef3`
- name: `SrvCryptEncrypt`
- size: `499`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180004470`
- `0x1800048f0`
- `0x1800055e0`
- `0x180005d00`
- `0x180005f00`
- `0x180019010`

## string_xrefs

- `0x180005dd8`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180005e31`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180005e94`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptEncrypt(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        int a8,
        __int64 a9)
{
  __int64 v10; // rax
  int v11; // edx
  int v12; // r8d
  __int64 v13; // rdi
  int v14; // edx
  unsigned int v15; // ebx
  int v16; // r8d
  int v17; // ebx
  int v18; // eax

  if ( a1 )
  {
    v10 = SrvLookupAndReferenceKey(a1, a3, 0);
    v13 = v10;
    if ( v10 )
    {
      if ( a4 && a5 && (v11 = a9, a9) )
      {
        v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)(v10 + 32) + 144LL))(
                *(_QWORD *)(*(_QWORD *)(v10 + 32) + 296LL),
                *(_QWORD *)(v10 + 40),
                a4);
        if ( v15 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v14,
              v16,
              (unsigned int)"Status",
              v15,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
              126);
          v17 = NormalizeNteStatus(v15);
        }
        else
        {
          v17 = 0;
        }
      }
      else
      {
        v17 = -2146893785;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v11,
            v12,
            (unsigned int)"Status",
            39,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
            105);
      }
      v18 = SrvDereferenceKey(v13);
      if ( v18 < 0 && v17 >= 0 )
        return (unsigned int)v18;
    }
    else
    {
      v17 = -2146893786;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          v12,
          (unsigned int)"Status",
          38,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          96);
    }
  }
  else
  {
    v17 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        87);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180005d00  mov     [rsp+arg_0], rbx
0x180005d05  push    rdi
0x180005d06  sub     rsp, 50h
0x180005d0a  mov     rbx, r9
0x180005d0d  mov     rax, r8
0x180005d10  test    rcx, rcx
0x180005d13  jz      loc_180005E07
0x180005d19  xor     r8d, r8d
0x180005d1c  mov     rdx, rax
0x180005d1f  call    SrvLookupAndReferenceKey
0x180005d24  mov     rdi, rax
0x180005d27  test    rax, rax
0x180005d2a  jz      loc_180005EBE
0x180005d30  test    rbx, rbx
0x180005d33  jz      loc_180005E72
0x180005d39  mov     r9d, [rsp+58h+arg_20]
0x180005d41  test    r9d, r9d
0x180005d44  jz      loc_180005E72
0x180005d4a  mov     rdx, [rsp+58h+arg_40]
0x180005d52  test    rdx, rdx
0x180005d55  jz      loc_180005E72
0x180005d5b  mov     rcx, [rax+20h]
0x180005d5f  mov     r8, rbx
0x180005d62  mov     eax, [rsp+58h+arg_48]
0x180005d69  mov     [rsp+58h+var_18], eax
0x180005d6d  mov     eax, [rsp+58h+arg_38]
0x180005d74  mov     r10, [rcx+90h]
0x180005d7b  mov     rcx, [rcx+128h]
0x180005d82  mov     [rsp+58h+var_20], rdx
0x180005d87  mov     rdx, [rdi+28h]
0x180005d8b  mov     [rsp+58h+var_28], eax
0x180005d8f  mov     rax, [rsp+58h+arg_30]
0x180005d97  mov     [rsp+58h+var_30], rax
0x180005d9c  mov     rax, [rsp+58h+arg_28]
0x180005da4  mov     [rsp+58h+var_38], rax
0x180005da9  mov     rax, r10
0x180005dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005db1  mov     ebx, eax
0x180005db3  test    eax, eax
0x180005db5  jz      loc_180005E53
0x180005dbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dc2  lea     rax, WPP_GLOBAL_Control
0x180005dc9  cmp     rcx, rax
0x180005dcc  jz      short loc_180005DFC
0x180005dce  test    byte ptr [rcx+1Ch], 1
0x180005dd2  jz      short loc_180005DFC
0x180005dd4  mov     rcx, [rcx+10h]
0x180005dd8  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005ddf  mov     [rsp+58h+var_28], 37Eh
0x180005de7  lea     r9, aStatus; "Status"
0x180005dee  mov     [rsp+58h+var_30], rax
0x180005df3  mov     dword ptr [rsp+58h+var_38], ebx
0x180005df7  call    WPP_SF_sDsd
0x180005dfc  mov     ecx, ebx
0x180005dfe  call    NormalizeNteStatus
0x180005e03  mov     ebx, eax
0x180005e05  jmp     short loc_180005E55
0x180005e07  mov     ebx, 80090026h
0x180005e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e13  lea     rax, WPP_GLOBAL_Control
0x180005e1a  cmp     rcx, rax
0x180005e1d  jz      short loc_180005E65
0x180005e1f  test    byte ptr [rcx+1Ch], 1
0x180005e23  jz      short loc_180005E65
0x180005e25  mov     [rsp+58h+var_28], 357h
0x180005e2d  mov     rcx, [rcx+10h]
0x180005e31  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005e38  mov     [rsp+58h+var_30], rax
0x180005e3d  lea     r9, aStatus; "Status"
0x180005e44  mov     dword ptr [rsp+58h+var_38], 80090026h
0x180005e4c  call    WPP_SF_sDsd
0x180005e51  jmp     short loc_180005E65
0x180005e53  xor     ebx, ebx
0x180005e55  mov     rcx, rdi
0x180005e58  call    SrvDereferenceKey
0x180005e5d  test    eax, eax
0x180005e5f  js      loc_180005EE9
0x180005e65  mov     eax, ebx
0x180005e67  mov     rbx, [rsp+58h+arg_0]
0x180005e6c  add     rsp, 50h
0x180005e70  pop     rdi
0x180005e71  retn
0x180005e72  mov     ebx, 80090027h
0x180005e77  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e7e  lea     rax, WPP_GLOBAL_Control
0x180005e85  cmp     rcx, rax
0x180005e88  jz      short loc_180005E55
0x180005e8a  test    byte ptr [rcx+1Ch], 1
0x180005e8e  jz      short loc_180005E55
0x180005e90  mov     rcx, [rcx+10h]
0x180005e94  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005e9b  mov     [rsp+58h+var_28], 369h
0x180005ea3  lea     r9, aStatus; "Status"
0x180005eaa  mov     [rsp+58h+var_30], rax
0x180005eaf  mov     dword ptr [rsp+58h+var_38], 80090027h
0x180005eb7  call    WPP_SF_sDsd
0x180005ebc  jmp     short loc_180005E55
0x180005ebe  mov     ebx, 80090026h
0x180005ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x180005eca  lea     rax, WPP_GLOBAL_Control
0x180005ed1  cmp     rcx, rax
0x180005ed4  jz      short loc_180005E65
0x180005ed6  test    byte ptr [rcx+1Ch], 1
0x180005eda  jz      short loc_180005E65
0x180005edc  mov     [rsp+58h+var_28], 360h
0x180005ee4  jmp     loc_180005E2D
0x180005ee9  test    ebx, ebx
0x180005eeb  cmovns  ebx, eax
0x180005eee  jmp     loc_180005E65
```
