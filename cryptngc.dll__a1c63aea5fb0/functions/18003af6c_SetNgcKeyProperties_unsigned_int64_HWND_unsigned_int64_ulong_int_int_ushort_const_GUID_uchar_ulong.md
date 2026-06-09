# SetNgcKeyProperties(unsigned __int64,HWND__ *,unsigned __int64,ulong,int,int,ushort const *,_GUID *,uchar *,ulong)

- ea: `0x18003af6c`
- end: `0x18003b157`
- name: `?SetNgcKeyProperties@@YAJ_KPEAUHWND__@@0KHHPEBGPEAU_GUID@@PEAEK@Z`
- size: `491`
- prototype: `__int64 __usercall@<rax>(NgcUtils *this@<rcx>, HWND@<rdx>, unsigned __int64@<r8>, unsigned int@<r9d>, int, unsigned __int16 *, const unsigned __int16 *, PBYTE pbInput, PBYTE, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002abc0`

## callees

- `0x180006538`
- `0x180019e94`
- `0x18001ae60`
- `0x18002b8c8`
- `0x18003af6c`
- `0x180042a34`
- `0x180042a90`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x18003b0e4`
- `ncrypt!NCryptSetProperty` at `0x18003b121`
- `ncrypt!NCryptSetProperty` at `0x18003b0e4`
- `ncrypt!NCryptSetProperty` at `0x18003b121`

## string_xrefs

- `0x18003afa5`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18003b132`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18003b02d`: `NgcCacheType`
- `0x18003b080`: `PinCacheIsGestureRequired`

## pseudocode

```c
__int64 __fastcall SetNgcKeyProperties(
        NgcUtils *this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int16 *a6,
        const unsigned __int16 *a7,
        PBYTE pbInput,
        PBYTE a9,
        DWORD cbInput)
{
  char v12; // si
  SECURITY_STATUS v14; // edi
  unsigned int v15; // r9d
  __int64 v16; // rdx
  HWND v18; // r8
  unsigned __int64 v19; // r8
  unsigned int v20; // r9d
  __int64 v21; // r8
  int v22; // r9d
  int v23; // r9d
  const unsigned __int16 *v24; // r8
  SECURITY_STATUS v25; // eax
  unsigned int v26; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-38h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v12 = a4;
  v14 = NgcUtils::SetNCryptDwordProperty(this, (unsigned __int64)L"Length", (const unsigned __int16 *)0x800, a4);
  if ( v14 < 0 )
  {
    v16 = 94;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v14,
      dwFlags);
    return (unsigned int)v14;
  }
  v14 = NgcUtils::SetNCryptDwordProperty(this, (unsigned __int64)L"Key Usage", (const unsigned __int16 *)3, v15);
  if ( v14 < 0 )
  {
    v16 = 100;
    goto LABEL_3;
  }
  v14 = NgcUtils::SetNCryptWindowHandle(this, a2, v18);
  if ( v14 < 0 )
  {
    v16 = 104;
    goto LABEL_3;
  }
  v14 = NgcUtils::SetNgcAuthTicket(this, a3, v19);
  if ( v14 < 0 )
  {
    v16 = 108;
    goto LABEL_3;
  }
  if ( (v12 & 0x10) != 0 )
  {
    v21 = 1;
  }
  else
  {
    v21 = 2;
    if ( (v12 & 0x20) == 0 )
      v21 = 4;
  }
  v14 = NgcUtils::SetNCryptDwordProperty(this, (unsigned __int64)L"NgcCacheType", (const unsigned __int16 *)v21, v20);
  if ( v14 < 0 )
  {
    v16 = 138;
    goto LABEL_3;
  }
  v14 = NgcUtils::SetNCryptBoolProperty(
          this,
          (unsigned __int64)L"NgcLogonCapableKey",
          (const unsigned __int16 *)a5,
          v22);
  if ( v14 < 0 )
  {
    v16 = 143;
    goto LABEL_3;
  }
  v24 = (const unsigned __int16 *)(unsigned int)a6;
  if ( (_DWORD)a6 )
  {
    v14 = NgcUtils::SetNCryptBoolProperty(
            this,
            (unsigned __int64)L"PinCacheIsGestureRequired",
            (const unsigned __int16 *)(unsigned int)a6,
            v23);
    if ( v14 < 0 )
    {
      v16 = 150;
      goto LABEL_3;
    }
  }
  v14 = NgcUtils::SetNCryptUiPolicy(this, (unsigned __int64)a7, v24);
  if ( v14 < 0 )
  {
    v16 = 155;
    goto LABEL_3;
  }
  if ( pbInput )
  {
    v14 = NCryptSetProperty((NCRYPT_HANDLE)this, L"NgcUICancellationId", pbInput, 0x10u, 0);
    if ( v14 < 0 )
    {
      v16 = 164;
      goto LABEL_3;
    }
  }
  if ( !a9 )
    return 0;
  v25 = NCryptSetProperty((NCRYPT_HANDLE)this, L"NgcFidoAuthenticatorAccount", a9, cbInput, 0);
  v26 = v25;
  if ( v25 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAE,
    (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
    (const char *)(unsigned int)v25,
    dwFlagsa);
  return v26;
}

```

## disassembly

```asm
0x18003af6c  push    rbx
0x18003af6e  push    rbp
0x18003af6f  push    rsi
0x18003af70  push    rdi
0x18003af71  push    r14
0x18003af73  sub     rsp, 30h
0x18003af77  mov     r14, r8
0x18003af7a  mov     rbp, rdx
0x18003af7d  mov     r8d, 800h; unsigned __int16 *
0x18003af83  lea     rdx, aLength; "Length"
0x18003af8a  mov     esi, r9d
0x18003af8d  mov     rbx, rcx
0x18003af90  call    ?SetNCryptDwordProperty@NgcUtils@@YAJ_KPEBGK@Z; NgcUtils::SetNCryptDwordProperty(unsigned __int64,ushort const *,ulong)
0x18003af95  mov     edi, eax
0x18003af97  test    eax, eax
0x18003af99  jns     short loc_18003AFBB
0x18003af9b  mov     edx, 5Eh ; '^'; void *
0x18003afa0  mov     rcx, [rsp+58h]; this
0x18003afa5  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18003afac  mov     r9d, edi; char *
0x18003afaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003afb4  mov     eax, edi
0x18003afb6  jmp     loc_18003B14C
0x18003afbb  mov     r8d, 3; unsigned __int16 *
0x18003afc1  lea     rdx, aKeyUsage; "Key Usage"
0x18003afc8  mov     rcx, rbx; this
0x18003afcb  call    ?SetNCryptDwordProperty@NgcUtils@@YAJ_KPEBGK@Z; NgcUtils::SetNCryptDwordProperty(unsigned __int64,ushort const *,ulong)
0x18003afd0  mov     edi, eax
0x18003afd2  test    eax, eax
0x18003afd4  jns     short loc_18003AFDD
0x18003afd6  mov     edx, 64h ; 'd'
0x18003afdb  jmp     short loc_18003AFA0
0x18003afdd  mov     rdx, rbp; unsigned __int64
0x18003afe0  mov     rcx, rbx; this
0x18003afe3  call    ?SetNCryptWindowHandle@NgcUtils@@YAJ_KPEAUHWND__@@@Z; NgcUtils::SetNCryptWindowHandle(unsigned __int64,HWND__ *)
0x18003afe8  mov     edi, eax
0x18003afea  test    eax, eax
0x18003afec  jns     short loc_18003AFF5
0x18003afee  mov     edx, 68h ; 'h'
0x18003aff3  jmp     short loc_18003AFA0
0x18003aff5  mov     rdx, r14; unsigned __int64
0x18003aff8  mov     rcx, rbx; this
0x18003affb  call    ?SetNgcAuthTicket@NgcUtils@@YAJ_K0@Z; NgcUtils::SetNgcAuthTicket(unsigned __int64,unsigned __int64)
0x18003b000  mov     edi, eax
0x18003b002  test    eax, eax
0x18003b004  jns     short loc_18003B00D
0x18003b006  mov     edx, 6Ch ; 'l'
0x18003b00b  jmp     short loc_18003AFA0
0x18003b00d  test    sil, 10h
0x18003b011  jz      short loc_18003B01B
0x18003b013  mov     r8d, 1
0x18003b019  jmp     short loc_18003B02D
0x18003b01b  mov     r8d, 2
0x18003b021  test    sil, 20h
0x18003b025  jnz     short loc_18003B02D
0x18003b027  mov     r8d, 4; unsigned __int16 *
0x18003b02d  lea     rdx, aNgccachetype; "NgcCacheType"
0x18003b034  mov     rcx, rbx; this
0x18003b037  call    ?SetNCryptDwordProperty@NgcUtils@@YAJ_KPEBGK@Z; NgcUtils::SetNCryptDwordProperty(unsigned __int64,ushort const *,ulong)
0x18003b03c  mov     edi, eax
0x18003b03e  test    eax, eax
0x18003b040  jns     short loc_18003B04C
0x18003b042  mov     edx, 8Ah
0x18003b047  jmp     loc_18003AFA0
0x18003b04c  mov     r8d, dword ptr [rsp+58h+arg_20]; unsigned __int16 *
0x18003b054  lea     rdx, aNgclogoncapabl; "NgcLogonCapableKey"
0x18003b05b  mov     rcx, rbx; this
0x18003b05e  call    ?SetNCryptBoolProperty@NgcUtils@@YAJ_KPEBGH@Z; NgcUtils::SetNCryptBoolProperty(unsigned __int64,ushort const *,int)
0x18003b063  mov     edi, eax
0x18003b065  test    eax, eax
0x18003b067  jns     short loc_18003B073
0x18003b069  mov     edx, 8Fh
0x18003b06e  jmp     loc_18003AFA0
0x18003b073  mov     r8d, dword ptr [rsp+58h+arg_28]; unsigned __int16 *
0x18003b07b  test    r8d, r8d
0x18003b07e  jz      short loc_18003B09F
0x18003b080  lea     rdx, aPincacheisgest; "PinCacheIsGestureRequired"
0x18003b087  mov     rcx, rbx; this
0x18003b08a  call    ?SetNCryptBoolProperty@NgcUtils@@YAJ_KPEBGH@Z; NgcUtils::SetNCryptBoolProperty(unsigned __int64,ushort const *,int)
0x18003b08f  mov     edi, eax
0x18003b091  test    eax, eax
0x18003b093  jns     short loc_18003B09F
0x18003b095  mov     edx, 96h
0x18003b09a  jmp     loc_18003AFA0
0x18003b09f  mov     rdx, [rsp+58h+arg_30]; unsigned __int64
0x18003b0a7  mov     rcx, rbx; this
0x18003b0aa  call    ?SetNCryptUiPolicy@NgcUtils@@YAJ_KPEBG@Z; NgcUtils::SetNCryptUiPolicy(unsigned __int64,ushort const *)
0x18003b0af  mov     edi, eax
0x18003b0b1  test    eax, eax
0x18003b0b3  jns     short loc_18003B0BF
0x18003b0b5  mov     edx, 9Bh
0x18003b0ba  jmp     loc_18003AFA0
0x18003b0bf  mov     r8, [rsp+58h+pbInput]; pbInput
0x18003b0c7  test    r8, r8
0x18003b0ca  jz      short loc_18003B0FA
0x18003b0cc  mov     r9d, 10h; cbInput
0x18003b0d2  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18003b0da  lea     rdx, aNgcuicancellat; "NgcUICancellationId"
0x18003b0e1  mov     rcx, rbx; hObject
0x18003b0e4  call    cs:__imp_NCryptSetProperty
0x18003b0ea  mov     edi, eax
0x18003b0ec  test    eax, eax
0x18003b0ee  jns     short loc_18003B0FA
0x18003b0f0  mov     edx, 0A4h
0x18003b0f5  jmp     loc_18003AFA0
0x18003b0fa  mov     r8, [rsp+58h+arg_40]; pbInput
0x18003b102  test    r8, r8
0x18003b105  jz      short loc_18003B14A
0x18003b107  mov     r9d, [rsp+58h+cbInput]; cbInput
0x18003b10f  lea     rdx, aNgcfidoauthent; "NgcFidoAuthenticatorAccount"
0x18003b116  mov     rcx, rbx; hObject
0x18003b119  mov     [rsp+58h+dwFlags], 0; int
0x18003b121  call    cs:__imp_NCryptSetProperty
0x18003b127  mov     ebx, eax
0x18003b129  test    eax, eax
0x18003b12b  jns     short loc_18003B14A
0x18003b12d  mov     rcx, [rsp+58h]; this
0x18003b132  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18003b139  mov     r9d, eax; char *
0x18003b13c  mov     edx, 0AEh; void *
0x18003b141  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b146  mov     eax, ebx
0x18003b148  jmp     short loc_18003B14C
0x18003b14a  xor     eax, eax
0x18003b14c  add     rsp, 30h
0x18003b150  pop     r14
0x18003b152  pop     rdi
0x18003b153  pop     rsi
0x18003b154  pop     rbp
0x18003b155  pop     rbx
0x18003b156  retn
```
