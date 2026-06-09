# PiDrvDbOverlayNodeHive

- ea: `0x140775d7c`
- end: `0x1407761c0`
- name: `PiDrvDbOverlayNodeHive`
- size: `1092`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140777c50`

## callees

- `0x14053cf40`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406f4880`
- `0x1407757c8`
- `0x140775d7c`
- `0x1408bae00`
- `0x14095e740`
- `0x140960a7c`
- `0x140a85084`
- `0x140bae410`
- `0x140bae8e0`

## string_xrefs

- `0x140775e9c`: `Setup\ResolveFilePaths`
- `0x140775df8`: `ControlSet001\Services`
- `0x1407760c8`: `ControlSet001\Services`

## pseudocode

```c
__int64 __fastcall PiDrvDbOverlayNodeHive(__int64 a1, const wchar_t *a2, int a3)
{
  __int64 v6; // rdi
  int v7; // eax
  int Key; // ebx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rcx
  void *Pool2; // r14
  unsigned int v14; // r15d
  __int64 i; // r8
  __int64 v16; // rcx
  int v17; // edi
  int v18; // esi
  int v19; // r8d
  int v20; // eax
  int v22; // [rsp+20h] [rbp-89h]
  int v23; // [rsp+20h] [rbp-89h]
  int v24; // [rsp+40h] [rbp-69h] BYREF
  int v25; // [rsp+44h] [rbp-65h] BYREF
  int v26; // [rsp+48h] [rbp-61h] BYREF
  int v27; // [rsp+4Ch] [rbp-5Dh] BYREF
  HANDLE v28; // [rsp+50h] [rbp-59h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-51h] BYREF
  HANDLE v30; // [rsp+60h] [rbp-49h] BYREF
  HANDLE v31; // [rsp+68h] [rbp-41h] BYREF
  HANDLE v32; // [rsp+70h] [rbp-39h] BYREF
  HANDLE v33; // [rsp+78h] [rbp-31h] BYREF
  _OWORD v34[4]; // [rsp+80h] [rbp-29h] BYREF

  v33 = 0;
  memset_0(v34, 0, sizeof(v34));
  v31 = 0;
  v30 = 0;
  LODWORD(v6) = 0;
  v28 = 0;
  v32 = 0;
  Handle = 0;
  v26 = 0;
  v27 = 0;
  v25 = 0;
  if ( wcsicmp(a2, L"SYSTEM") )
  {
    if ( !wcsicmp(a2, L"SOFTWARE") && (*(_DWORD *)(a1 + 492) & 0x20) == 0 )
      goto LABEL_3;
  }
  else
  {
    v7 = *(_DWORD *)(a1 + 492);
    if ( (v7 & 0x10) == 0 )
    {
LABEL_3:
      Key = 0;
      goto LABEL_50;
    }
    v34[0] = *(_OWORD *)off_140B79C48;
    v34[1] = *(_OWORD *)off_140B79C58;
    do
      v6 = (unsigned int)(v6 + 1);
    while ( (unsigned int)v6 < 4 );
    if ( (v7 & 0xC0) != 0 )
    {
      v9 = PnpCtxRegOpenKey(0, a3, (unsigned int)L"ControlSet001\\Services", 0, 131097, (__int64)&v28);
      Key = v9;
      if ( v9 == -1073741772 )
      {
        v28 = 0;
      }
      else if ( v9 < 0 )
      {
        goto LABEL_50;
      }
    }
    *((_QWORD *)v34 + v6) = L"ControlSet001\\Services";
    LODWORD(v6) = v6 + 1;
  }
  *((_QWORD *)v34 + (unsigned int)v6) = L"Setup\\ResolveFilePaths";
  v10 = PnpCtxRegOpenKey(
          0,
          -2147483646,
          (unsigned int)L"System\\CurrentControlSet\\Control\\StateSeparation\\PnP\\DriverHiveOverlays",
          0,
          131097,
          (__int64)&v31);
  Key = v10;
  if ( v10 == -1073741772 )
  {
    v31 = 0;
  }
  else
  {
    if ( v10 < 0 )
      goto LABEL_50;
    v11 = PnpCtxRegOpenKey(0, (_DWORD)v31, (_DWORD)a2, 0, 131097, (__int64)&v30);
    Key = v11;
    if ( v11 == -1073741772 )
    {
      v30 = 0;
    }
    else if ( v11 < 0 )
    {
      goto LABEL_50;
    }
  }
  Key = PnpCtxRegOpenKey(0, -2147483646, (_DWORD)a2, 0, 131103, (__int64)&v33);
  if ( Key >= 0 )
  {
    Key = PiDrvDbOverlayCopyKeys(a3, 0, (_DWORD)v33, 0, v22, (__int64)v34, (int)v6 + 1, (__int64)v30);
    if ( Key >= 0 )
    {
      if ( v28 )
      {
        Pool2 = (void *)ExAllocatePool2(256, 520, 1650749520);
        if ( !Pool2 )
        {
          Key = -1073741670;
          goto LABEL_50;
        }
        v14 = 0;
        for ( i = 0; ; i = v14 )
        {
          v24 = 260;
          v20 = PnpCtxRegEnumKey(v12, v28, i, Pool2, &v24);
          if ( v20 == -2147483622 )
          {
LABEL_49:
            ExFreePoolWithTag(Pool2, 0);
            goto LABEL_50;
          }
          if ( v20 < 0 || (int)PnpCtxRegOpenKey(0, (_DWORD)v28, (_DWORD)Pool2, 0, 131097, (__int64)&Handle) < 0 )
            goto LABEL_47;
          v24 = 4;
          if ( (int)PnpCtxRegQueryValue(v12, Handle, L"Type", &v25, &v26, &v24) < 0 || v25 != 4 || v24 != 4 )
            break;
          v24 = 4;
          if ( (int)PnpCtxRegQueryValue(v16, Handle, L"Start", &v25, &v27, &v24) < 0 || v25 != 4 || v24 != 4 )
          {
            v17 = v26;
LABEL_36:
            v27 = 0;
            v18 = 0;
            goto LABEL_37;
          }
          v17 = v26;
          v18 = v27;
LABEL_37:
          ZwClose(Handle);
          if ( !v17 )
            goto LABEL_47;
          if ( (v17 & 0xB) == 0 || v18 == 2 )
          {
            if ( (*(_DWORD *)(a1 + 492) & 0x80u) == 0 )
              goto LABEL_47;
          }
          else if ( (*(_DWORD *)(a1 + 492) & 0x40) == 0 )
          {
            goto LABEL_47;
          }
          v19 = (int)v32;
          if ( !v32 )
          {
            Key = PnpCtxRegCreateKey(
                    0,
                    (_DWORD)v33,
                    (unsigned int)L"ControlSet001\\Services",
                    0,
                    131103,
                    0,
                    (__int64)&v32,
                    0);
            if ( Key < 0 )
              goto LABEL_49;
            v19 = (int)v32;
          }
          Key = PiDrvDbOverlayCopyKeys((_DWORD)v28, (_DWORD)Pool2, v19, (_DWORD)Pool2, v23, 0, 0, 0);
          if ( Key < 0 )
            goto LABEL_49;
LABEL_47:
          ++v14;
        }
        v17 = 0;
        v26 = 0;
        goto LABEL_36;
      }
    }
  }
LABEL_50:
  if ( v30 )
    ZwClose(v30);
  if ( v31 )
    ZwClose(v31);
  if ( v28 )
    ZwClose(v28);
  if ( v32 )
    ZwClose(v32);
  if ( v33 )
    ZwClose(v33);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x140775d7c  mov     [rsp-8+arg_0], rbx
0x140775d81  push    rbp
0x140775d82  push    rsi
0x140775d83  push    rdi
0x140775d84  push    r12
0x140775d86  push    r13
0x140775d88  push    r14
0x140775d8a  push    r15
0x140775d8c  lea     rbp, [rsp-27h]
0x140775d91  sub     rsp, 0D0h
0x140775d98  mov     rax, cs:__security_cookie
0x140775d9f  xor     rax, rsp
0x140775da2  mov     [rbp+57h+var_40], rax
0x140775da6  xor     r12d, r12d
0x140775da9  mov     r14, r8
0x140775dac  mov     rsi, rdx
0x140775daf  mov     [rbp+57h+var_88], r12
0x140775db3  mov     r13, rcx
0x140775db6  xor     edx, edx; Val
0x140775db8  lea     rcx, [rbp+57h+var_80]; void *
0x140775dbc  lea     r8d, [r12+40h]; Size
0x140775dc1  call    memset_0
0x140775dc6  lea     rdx, aSystem; "SYSTEM"
0x140775dcd  mov     [rbp+57h+var_98], r12
0x140775dd1  mov     rcx, rsi; Str1
0x140775dd4  mov     [rbp+57h+var_A0], r12
0x140775dd8  mov     edi, r12d
0x140775ddb  mov     [rbp+57h+var_B0], r12
0x140775ddf  mov     [rbp+57h+var_90], r12
0x140775de3  mov     [rbp+57h+Handle], r12
0x140775de7  mov     [rbp+57h+var_B8], r12d
0x140775deb  mov     [rbp+57h+var_B4], r12d
0x140775def  mov     [rbp+57h+var_BC], r12d
0x140775df3  call    _wcsicmp
0x140775df8  lea     r15, aControlset001S_0; "ControlSet001\\Services"
0x140775dff  test    eax, eax
0x140775e01  jnz     short loc_140775E78
0x140775e03  mov     eax, [r13+1ECh]
0x140775e0a  test    al, 10h
0x140775e0c  jnz     short loc_140775E16
0x140775e0e  mov     ebx, r12d
0x140775e11  jmp     loc_140776150
0x140775e16  movups  xmm0, xmmword ptr cs:off_140B79C48; "Select"
0x140775e1d  movups  xmm1, xmmword ptr cs:off_140B79C58; "DriverDatabase"
0x140775e24  movups  [rbp+57h+var_80], xmm0
0x140775e28  movups  [rbp+57h+var_70], xmm1
0x140775e2c  inc     edi
0x140775e2e  cmp     edi, 4
0x140775e31  jb      short loc_140775E2C
0x140775e33  test    al, 0C0h
0x140775e35  jz      short loc_140775E6F
0x140775e37  lea     rax, [rbp+57h+var_B0]
0x140775e3b  xor     r9d, r9d
0x140775e3e  mov     [rsp+100h+var_D8], rax
0x140775e43  mov     r8, r15
0x140775e46  mov     rdx, r14
0x140775e49  mov     dword ptr [rsp+100h+var_E0], 20019h
0x140775e51  xor     ecx, ecx
0x140775e53  call    _PnpCtxRegOpenKey
0x140775e58  mov     ebx, eax
0x140775e5a  cmp     eax, 0C0000034h
0x140775e5f  jnz     short loc_140775E67
0x140775e61  mov     [rbp+57h+var_B0], r12
0x140775e65  jmp     short loc_140775E6F
0x140775e67  test    eax, eax
0x140775e69  js      loc_140776150
0x140775e6f  mov     qword ptr [rbp+rdi*8+57h+var_80], r15
0x140775e74  inc     edi
0x140775e76  jmp     short loc_140775E9A
0x140775e78  lea     rdx, aSoftware; "SOFTWARE"
0x140775e7f  mov     rcx, rsi; Str1
0x140775e82  call    _wcsicmp
0x140775e87  test    eax, eax
0x140775e89  jnz     short loc_140775E9A
0x140775e8b  mov     eax, [r13+1ECh]
0x140775e92  test    al, 20h
0x140775e94  jz      loc_140775E0E
0x140775e9a  mov     eax, edi
0x140775e9c  lea     rcx, aSetupResolvefi; "Setup\\ResolveFilePaths"
0x140775ea3  mov     r15d, 80000002h
0x140775ea9  lea     r8, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Sta"...
0x140775eb0  xor     r9d, r9d
0x140775eb3  mov     edx, r15d
0x140775eb6  mov     qword ptr [rbp+rax*8+57h+var_80], rcx
0x140775ebb  lea     rax, [rbp+57h+var_98]
0x140775ebf  mov     [rsp+100h+var_D8], rax
0x140775ec4  xor     ecx, ecx
0x140775ec6  mov     dword ptr [rsp+100h+var_E0], 20019h
0x140775ece  call    _PnpCtxRegOpenKey
0x140775ed3  mov     ebx, eax
0x140775ed5  cmp     eax, 0C0000034h
0x140775eda  jnz     short loc_140775EE2
0x140775edc  mov     [rbp+57h+var_98], r12
0x140775ee0  jmp     short loc_140775F23
0x140775ee2  test    eax, eax
0x140775ee4  js      loc_140776150
0x140775eea  mov     rdx, [rbp+57h+var_98]
0x140775eee  lea     rax, [rbp+57h+var_A0]
0x140775ef2  mov     [rsp+100h+var_D8], rax
0x140775ef7  xor     r9d, r9d
0x140775efa  mov     r8, rsi
0x140775efd  mov     dword ptr [rsp+100h+var_E0], 20019h
0x140775f05  xor     ecx, ecx
0x140775f07  call    _PnpCtxRegOpenKey
0x140775f0c  mov     ebx, eax
0x140775f0e  cmp     eax, 0C0000034h
0x140775f13  jnz     short loc_140775F1B
0x140775f15  mov     [rbp+57h+var_A0], r12
0x140775f19  jmp     short loc_140775F23
0x140775f1b  test    eax, eax
0x140775f1d  js      loc_140776150
0x140775f23  lea     rax, [rbp+57h+var_88]
0x140775f27  xor     r9d, r9d
0x140775f2a  mov     [rsp+100h+var_D8], rax
0x140775f2f  mov     r8, rsi
0x140775f32  mov     rdx, r15
0x140775f35  mov     dword ptr [rsp+100h+var_E0], 2001Fh
0x140775f3d  xor     ecx, ecx
0x140775f3f  call    _PnpCtxRegOpenKey
0x140775f44  mov     ebx, eax
0x140775f46  test    eax, eax
0x140775f48  js      loc_140776150
0x140775f4e  mov     rax, [rbp+57h+var_A0]
0x140775f52  lea     edx, [rdi+1]
0x140775f55  mov     r8, [rbp+57h+var_88]
0x140775f59  xor     r9d, r9d
0x140775f5c  mov     [rsp+100h+var_C8], rax
0x140775f61  mov     rcx, r14
0x140775f64  mov     dword ptr [rsp+100h+var_D0], edx
0x140775f68  lea     rax, [rbp+57h+var_80]
0x140775f6c  xor     edx, edx
0x140775f6e  mov     [rsp+100h+var_D8], rax
0x140775f73  call    PiDrvDbOverlayCopyKeys
0x140775f78  mov     ebx, eax
0x140775f7a  test    eax, eax
0x140775f7c  js      loc_140776150
0x140775f82  cmp     [rbp+57h+var_B0], r12
0x140775f86  jz      loc_140776150
0x140775f8c  mov     edx, 208h
0x140775f91  mov     ecx, 100h
0x140775f96  mov     r8d, 62647050h
0x140775f9c  call    ExAllocatePool2
0x140775fa1  mov     r14, rax
0x140775fa4  test    rax, rax
0x140775fa7  jnz     short loc_140775FB3
0x140775fa9  mov     ebx, 0C000009Ah
0x140775fae  jmp     loc_140776150
0x140775fb3  mov     r15d, r12d
0x140775fb6  xor     r8d, r8d
0x140775fb9  jmp     loc_14077611F
0x140775fbe  test    eax, eax
0x140775fc0  js      loc_140776119
0x140775fc6  mov     rdx, [rbp+57h+var_B0]
0x140775fca  lea     rax, [rbp+57h+Handle]
0x140775fce  mov     [rsp+100h+var_D8], rax
0x140775fd3  xor     r9d, r9d
0x140775fd6  mov     r8, r14
0x140775fd9  mov     dword ptr [rsp+100h+var_E0], 20019h
0x140775fe1  xor     ecx, ecx
0x140775fe3  call    _PnpCtxRegOpenKey
0x140775fe8  test    eax, eax
0x140775fea  js      loc_140776119
0x140775ff0  mov     rdx, [rbp+57h+Handle]
0x140775ff4  lea     rax, [rbp+57h+var_C0]
0x140775ff8  mov     [rsp+100h+var_D8], rax
0x140775ffd  lea     r9, [rbp+57h+var_BC]
0x140776001  lea     rax, [rbp+57h+var_B8]
0x140776005  mov     edi, 4
0x14077600a  lea     r8, aType; "Type"
0x140776011  mov     [rsp+100h+var_E0], rax
0x140776016  mov     [rbp+57h+var_C0], edi
0x140776019  call    _PnpCtxRegQueryValue
0x14077601e  test    eax, eax
0x140776020  js      short loc_140776070
0x140776022  cmp     [rbp+57h+var_BC], edi
0x140776025  jnz     short loc_140776070
0x140776027  cmp     [rbp+57h+var_C0], edi
0x14077602a  jnz     short loc_140776070
0x14077602c  mov     rdx, [rbp+57h+Handle]
0x140776030  lea     rax, [rbp+57h+var_C0]
0x140776034  mov     [rsp+100h+var_D8], rax
0x140776039  lea     r9, [rbp+57h+var_BC]
0x14077603d  lea     rax, [rbp+57h+var_B4]
0x140776041  mov     [rbp+57h+var_C0], edi
0x140776044  lea     r8, aStart_0; "Start"
0x14077604b  mov     [rsp+100h+var_E0], rax
0x140776050  call    _PnpCtxRegQueryValue
0x140776055  test    eax, eax
0x140776057  js      short loc_14077606B
0x140776059  cmp     [rbp+57h+var_BC], edi
0x14077605c  jnz     short loc_14077606B
0x14077605e  cmp     [rbp+57h+var_C0], edi
0x140776061  jnz     short loc_14077606B
0x140776063  mov     edi, [rbp+57h+var_B8]
0x140776066  mov     esi, [rbp+57h+var_B4]
0x140776069  jmp     short loc_14077607E
0x14077606b  mov     edi, [rbp+57h+var_B8]
0x14077606e  jmp     short loc_140776077
0x140776070  mov     edi, r12d
0x140776073  mov     [rbp+57h+var_B8], r12d
0x140776077  mov     [rbp+57h+var_B4], r12d
0x14077607b  mov     esi, r12d
0x14077607e  mov     rcx, [rbp+57h+Handle]; Handle
0x140776082  call    ZwClose
0x140776087  test    edi, edi
0x140776089  jz      loc_140776119
0x14077608f  test    dil, 0Bh
0x140776093  jz      short loc_1407760A7
0x140776095  cmp     esi, 2
0x140776098  jz      short loc_1407760A7
0x14077609a  mov     eax, [r13+1ECh]
0x1407760a1  test    al, 40h
0x1407760a3  jz      short loc_140776119
0x1407760a5  jmp     short loc_1407760B2
0x1407760a7  mov     eax, [r13+1ECh]
0x1407760ae  test    al, al
0x1407760b0  jns     short loc_140776119
0x1407760b2  mov     r8, [rbp+57h+var_90]
0x1407760b6  test    r8, r8
0x1407760b9  jnz     short loc_1407760F5
0x1407760bb  mov     rdx, [rbp+57h+var_88]
0x1407760bf  lea     rax, [rbp+57h+var_90]
0x1407760c3  mov     [rsp+100h+var_C8], r12
0x1407760c8  lea     r8, aControlset001S_0; "ControlSet001\\Services"
0x1407760cf  mov     [rsp+100h+var_D0], rax
0x1407760d4  xor     r9d, r9d
0x1407760d7  mov     [rsp+100h+var_D8], r12
0x1407760dc  xor     ecx, ecx
0x1407760de  mov     dword ptr [rsp+100h+var_E0], 2001Fh
0x1407760e6  call    _PnpCtxRegCreateKey
0x1407760eb  mov     ebx, eax
0x1407760ed  test    eax, eax
0x1407760ef  js      short loc_140776146
0x1407760f1  mov     r8, [rbp+57h+var_90]
0x1407760f5  mov     rcx, [rbp+57h+var_B0]
0x1407760f9  mov     r9, r14
0x1407760fc  mov     [rsp+100h+var_C8], r12
0x140776101  mov     rdx, r14
0x140776104  mov     dword ptr [rsp+100h+var_D0], r12d
0x140776109  mov     [rsp+100h+var_D8], r12
0x14077610e  call    PiDrvDbOverlayCopyKeys
0x140776113  mov     ebx, eax
0x140776115  test    eax, eax
0x140776117  js      short loc_140776146
0x140776119  inc     r15d
0x14077611c  mov     r8d, r15d
0x14077611f  mov     rdx, [rbp+57h+var_B0]
0x140776123  lea     rax, [rbp+57h+var_C0]
0x140776127  mov     r9, r14
0x14077612a  mov     [rsp+100h+var_E0], rax
0x14077612f  mov     [rbp+57h+var_C0], 104h
0x140776136  call    _PnpCtxRegEnumKey
0x14077613b  cmp     eax, 8000001Ah
0x140776140  jnz     loc_140775FBE
0x140776146  xor     edx, edx; Tag
0x140776148  mov     rcx, r14; P
0x14077614b  call    ExFreePoolWithTag
0x140776150  mov     rcx, [rbp+57h+var_A0]; Handle
0x140776154  test    rcx, rcx
0x140776157  jz      short loc_14077615E
0x140776159  call    ZwClose
0x14077615e  mov     rcx, [rbp+57h+var_98]; Handle
0x140776162  test    rcx, rcx
0x140776165  jz      short loc_14077616C
0x140776167  call    ZwClose
0x14077616c  mov     rcx, [rbp+57h+var_B0]; Handle
0x140776170  test    rcx, rcx
0x140776173  jz      short loc_14077617A
0x140776175  call    ZwClose
0x14077617a  mov     rcx, [rbp+57h+var_90]; Handle
0x14077617e  test    rcx, rcx
0x140776181  jz      short loc_140776188
0x140776183  call    ZwClose
0x140776188  mov     rcx, [rbp+57h+var_88]; Handle
0x14077618c  test    rcx, rcx
0x14077618f  jz      short loc_140776196
0x140776191  call    ZwClose
0x140776196  mov     eax, ebx
0x140776198  mov     rcx, [rbp+57h+var_40]
0x14077619c  xor     rcx, rsp; StackCookie
0x14077619f  call    __security_check_cookie
0x1407761a4  mov     rbx, [rsp+100h+arg_0]
0x1407761ac  add     rsp, 0D0h
0x1407761b3  pop     r15
0x1407761b5  pop     r14
0x1407761b7  pop     r13
0x1407761b9  pop     r12
0x1407761bb  pop     rdi
0x1407761bc  pop     rsi
0x1407761bd  pop     rbp
0x1407761be  retn
```
