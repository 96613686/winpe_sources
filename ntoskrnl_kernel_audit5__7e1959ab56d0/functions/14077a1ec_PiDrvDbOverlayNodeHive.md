# PiDrvDbOverlayNodeHive

- ea: `0x14077a1ec`
- end: `0x14077a630`
- name: `PiDrvDbOverlayNodeHive`
- size: `1092`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x14077c0c0`

## callees

- `0x140544600`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406f7380`
- `0x140779c38`
- `0x14077a1ec`
- `0x14086daf0`
- `0x14086fe2c`
- `0x1408efd10`
- `0x140a8ba44`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x14077a30c`: `Setup\ResolveFilePaths`
- `0x14077a268`: `ControlSet001\Services`
- `0x14077a538`: `ControlSet001\Services`

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
  int v24; // [rsp+28h] [rbp-81h]
  int v25; // [rsp+40h] [rbp-69h] BYREF
  int v26; // [rsp+44h] [rbp-65h] BYREF
  int v27; // [rsp+48h] [rbp-61h] BYREF
  int v28; // [rsp+4Ch] [rbp-5Dh] BYREF
  HANDLE v29; // [rsp+50h] [rbp-59h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-51h] BYREF
  HANDLE v31; // [rsp+60h] [rbp-49h] BYREF
  HANDLE v32; // [rsp+68h] [rbp-41h] BYREF
  HANDLE v33; // [rsp+70h] [rbp-39h] BYREF
  HANDLE v34; // [rsp+78h] [rbp-31h] BYREF
  _OWORD v35[4]; // [rsp+80h] [rbp-29h] BYREF

  v34 = 0;
  memset_0(v35, 0, sizeof(v35));
  v32 = 0;
  v31 = 0;
  LODWORD(v6) = 0;
  v29 = 0;
  v33 = 0;
  Handle = 0;
  v27 = 0;
  v28 = 0;
  v26 = 0;
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
    v35[0] = *(_OWORD *)off_140B7C068;
    v35[1] = *(_OWORD *)off_140B7C078;
    do
      v6 = (unsigned int)(v6 + 1);
    while ( (unsigned int)v6 < 4 );
    if ( (v7 & 0xC0) != 0 )
    {
      v9 = PnpCtxRegOpenKey(0, a3, (unsigned int)L"ControlSet001\\Services", 0, 131097, (__int64)&v29);
      Key = v9;
      if ( v9 == -1073741772 )
      {
        v29 = 0;
      }
      else if ( v9 < 0 )
      {
        goto LABEL_50;
      }
    }
    *((_QWORD *)v35 + v6) = L"ControlSet001\\Services";
    LODWORD(v6) = v6 + 1;
  }
  *((_QWORD *)v35 + (unsigned int)v6) = L"Setup\\ResolveFilePaths";
  v10 = PnpCtxRegOpenKey(
          0,
          -2147483646,
          (unsigned int)L"System\\CurrentControlSet\\Control\\StateSeparation\\PnP\\DriverHiveOverlays",
          0,
          131097,
          (__int64)&v32);
  Key = v10;
  if ( v10 == -1073741772 )
  {
    v32 = 0;
  }
  else
  {
    if ( v10 < 0 )
      goto LABEL_50;
    v11 = PnpCtxRegOpenKey(0, (_DWORD)v32, (_DWORD)a2, 0, 131097, (__int64)&v31);
    Key = v11;
    if ( v11 == -1073741772 )
    {
      v31 = 0;
    }
    else if ( v11 < 0 )
    {
      goto LABEL_50;
    }
  }
  Key = PnpCtxRegOpenKey(0, -2147483646, (_DWORD)a2, 0, 131103, (__int64)&v34);
  if ( Key >= 0 )
  {
    Key = PiDrvDbOverlayCopyKeys(a3, 0, (_DWORD)v34, 0, v22, (__int64)v35, (int)v6 + 1, (__int64)v31);
    if ( Key >= 0 )
    {
      if ( v29 )
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
          v25 = 260;
          v20 = PnpCtxRegEnumKey(v12, v29, i, Pool2, &v25, v24);
          if ( v20 == -2147483622 )
          {
LABEL_49:
            ExFreePoolWithTag(Pool2, 0);
            goto LABEL_50;
          }
          if ( v20 < 0 || (int)PnpCtxRegOpenKey(0, (_DWORD)v29, (_DWORD)Pool2, 0, 131097, (__int64)&Handle) < 0 )
            goto LABEL_47;
          v25 = 4;
          if ( (int)PnpCtxRegQueryValue(v12, Handle, L"Type", &v26, &v27, &v25) < 0 || v26 != 4 || v25 != 4 )
            break;
          v25 = 4;
          if ( (int)PnpCtxRegQueryValue(v16, Handle, L"Start", &v26, &v28, &v25) < 0 || v26 != 4 || v25 != 4 )
          {
            v17 = v27;
LABEL_36:
            v28 = 0;
            v18 = 0;
            goto LABEL_37;
          }
          v17 = v27;
          v18 = v28;
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
          v19 = (int)v33;
          if ( !v33 )
          {
            Key = PnpCtxRegCreateKey(
                    0,
                    (_DWORD)v34,
                    (unsigned int)L"ControlSet001\\Services",
                    0,
                    131103,
                    0,
                    (__int64)&v33,
                    0);
            if ( Key < 0 )
              goto LABEL_49;
            v19 = (int)v33;
          }
          Key = PiDrvDbOverlayCopyKeys((_DWORD)v29, (_DWORD)Pool2, v19, (_DWORD)Pool2, v23, 0, 0, 0);
          if ( Key < 0 )
            goto LABEL_49;
LABEL_47:
          ++v14;
        }
        v17 = 0;
        v27 = 0;
        goto LABEL_36;
      }
    }
  }
LABEL_50:
  if ( v31 )
    ZwClose(v31);
  if ( v32 )
    ZwClose(v32);
  if ( v29 )
    ZwClose(v29);
  if ( v33 )
    ZwClose(v33);
  if ( v34 )
    ZwClose(v34);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x14077a1ec  mov     [rsp-8+arg_0], rbx
0x14077a1f1  push    rbp
0x14077a1f2  push    rsi
0x14077a1f3  push    rdi
0x14077a1f4  push    r12
0x14077a1f6  push    r13
0x14077a1f8  push    r14
0x14077a1fa  push    r15
0x14077a1fc  lea     rbp, [rsp-27h]
0x14077a201  sub     rsp, 0D0h
0x14077a208  mov     rax, cs:__security_cookie
0x14077a20f  xor     rax, rsp
0x14077a212  mov     [rbp+57h+var_40], rax
0x14077a216  xor     r12d, r12d
0x14077a219  mov     r14, r8
0x14077a21c  mov     rsi, rdx
0x14077a21f  mov     [rbp+57h+var_88], r12
0x14077a223  mov     r13, rcx
0x14077a226  xor     edx, edx; Val
0x14077a228  lea     rcx, [rbp+57h+var_80]; void *
0x14077a22c  lea     r8d, [r12+40h]; Size
0x14077a231  call    memset_0
0x14077a236  lea     rdx, aSystem; "SYSTEM"
0x14077a23d  mov     [rbp+57h+var_98], r12
0x14077a241  mov     rcx, rsi; Str1
0x14077a244  mov     [rbp+57h+var_A0], r12
0x14077a248  mov     edi, r12d
0x14077a24b  mov     [rbp+57h+var_B0], r12
0x14077a24f  mov     [rbp+57h+var_90], r12
0x14077a253  mov     [rbp+57h+Handle], r12
0x14077a257  mov     [rbp+57h+var_B8], r12d
0x14077a25b  mov     [rbp+57h+var_B4], r12d
0x14077a25f  mov     [rbp+57h+var_BC], r12d
0x14077a263  call    _wcsicmp
0x14077a268  lea     r15, aControlset001S_0; "ControlSet001\\Services"
0x14077a26f  test    eax, eax
0x14077a271  jnz     short loc_14077A2E8
0x14077a273  mov     eax, [r13+1ECh]
0x14077a27a  test    al, 10h
0x14077a27c  jnz     short loc_14077A286
0x14077a27e  mov     ebx, r12d
0x14077a281  jmp     loc_14077A5C0
0x14077a286  movups  xmm0, xmmword ptr cs:off_140B7C068; "Select"
0x14077a28d  movups  xmm1, xmmword ptr cs:off_140B7C078; "DriverDatabase"
0x14077a294  movups  [rbp+57h+var_80], xmm0
0x14077a298  movups  [rbp+57h+var_70], xmm1
0x14077a29c  inc     edi
0x14077a29e  cmp     edi, 4
0x14077a2a1  jb      short loc_14077A29C
0x14077a2a3  test    al, 0C0h
0x14077a2a5  jz      short loc_14077A2DF
0x14077a2a7  lea     rax, [rbp+57h+var_B0]
0x14077a2ab  xor     r9d, r9d
0x14077a2ae  mov     [rsp+100h+var_D8], rax
0x14077a2b3  mov     r8, r15
0x14077a2b6  mov     rdx, r14
0x14077a2b9  mov     dword ptr [rsp+100h+var_E0], 20019h
0x14077a2c1  xor     ecx, ecx
0x14077a2c3  call    _PnpCtxRegOpenKey
0x14077a2c8  mov     ebx, eax
0x14077a2ca  cmp     eax, 0C0000034h
0x14077a2cf  jnz     short loc_14077A2D7
0x14077a2d1  mov     [rbp+57h+var_B0], r12
0x14077a2d5  jmp     short loc_14077A2DF
0x14077a2d7  test    eax, eax
0x14077a2d9  js      loc_14077A5C0
0x14077a2df  mov     qword ptr [rbp+rdi*8+57h+var_80], r15
0x14077a2e4  inc     edi
0x14077a2e6  jmp     short loc_14077A30A
0x14077a2e8  lea     rdx, aSoftware; "SOFTWARE"
0x14077a2ef  mov     rcx, rsi; Str1
0x14077a2f2  call    _wcsicmp
0x14077a2f7  test    eax, eax
0x14077a2f9  jnz     short loc_14077A30A
0x14077a2fb  mov     eax, [r13+1ECh]
0x14077a302  test    al, 20h
0x14077a304  jz      loc_14077A27E
0x14077a30a  mov     eax, edi
0x14077a30c  lea     rcx, aSetupResolvefi; "Setup\\ResolveFilePaths"
0x14077a313  mov     r15d, 80000002h
0x14077a319  lea     r8, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Sta"...
0x14077a320  xor     r9d, r9d
0x14077a323  mov     edx, r15d
0x14077a326  mov     qword ptr [rbp+rax*8+57h+var_80], rcx
0x14077a32b  lea     rax, [rbp+57h+var_98]
0x14077a32f  mov     [rsp+100h+var_D8], rax
0x14077a334  xor     ecx, ecx
0x14077a336  mov     dword ptr [rsp+100h+var_E0], 20019h
0x14077a33e  call    _PnpCtxRegOpenKey
0x14077a343  mov     ebx, eax
0x14077a345  cmp     eax, 0C0000034h
0x14077a34a  jnz     short loc_14077A352
0x14077a34c  mov     [rbp+57h+var_98], r12
0x14077a350  jmp     short loc_14077A393
0x14077a352  test    eax, eax
0x14077a354  js      loc_14077A5C0
0x14077a35a  mov     rdx, [rbp+57h+var_98]
0x14077a35e  lea     rax, [rbp+57h+var_A0]
0x14077a362  mov     [rsp+100h+var_D8], rax
0x14077a367  xor     r9d, r9d
0x14077a36a  mov     r8, rsi
0x14077a36d  mov     dword ptr [rsp+100h+var_E0], 20019h
0x14077a375  xor     ecx, ecx
0x14077a377  call    _PnpCtxRegOpenKey
0x14077a37c  mov     ebx, eax
0x14077a37e  cmp     eax, 0C0000034h
0x14077a383  jnz     short loc_14077A38B
0x14077a385  mov     [rbp+57h+var_A0], r12
0x14077a389  jmp     short loc_14077A393
0x14077a38b  test    eax, eax
0x14077a38d  js      loc_14077A5C0
0x14077a393  lea     rax, [rbp+57h+var_88]
0x14077a397  xor     r9d, r9d
0x14077a39a  mov     [rsp+100h+var_D8], rax
0x14077a39f  mov     r8, rsi
0x14077a3a2  mov     rdx, r15
0x14077a3a5  mov     dword ptr [rsp+100h+var_E0], 2001Fh
0x14077a3ad  xor     ecx, ecx
0x14077a3af  call    _PnpCtxRegOpenKey
0x14077a3b4  mov     ebx, eax
0x14077a3b6  test    eax, eax
0x14077a3b8  js      loc_14077A5C0
0x14077a3be  mov     rax, [rbp+57h+var_A0]
0x14077a3c2  lea     edx, [rdi+1]
0x14077a3c5  mov     r8, [rbp+57h+var_88]
0x14077a3c9  xor     r9d, r9d
0x14077a3cc  mov     [rsp+100h+var_C8], rax
0x14077a3d1  mov     rcx, r14
0x14077a3d4  mov     dword ptr [rsp+100h+var_D0], edx
0x14077a3d8  lea     rax, [rbp+57h+var_80]
0x14077a3dc  xor     edx, edx
0x14077a3de  mov     [rsp+100h+var_D8], rax
0x14077a3e3  call    PiDrvDbOverlayCopyKeys
0x14077a3e8  mov     ebx, eax
0x14077a3ea  test    eax, eax
0x14077a3ec  js      loc_14077A5C0
0x14077a3f2  cmp     [rbp+57h+var_B0], r12
0x14077a3f6  jz      loc_14077A5C0
0x14077a3fc  mov     edx, 208h
0x14077a401  mov     ecx, 100h
0x14077a406  mov     r8d, 62647050h
0x14077a40c  call    ExAllocatePool2
0x14077a411  mov     r14, rax
0x14077a414  test    rax, rax
0x14077a417  jnz     short loc_14077A423
0x14077a419  mov     ebx, 0C000009Ah
0x14077a41e  jmp     loc_14077A5C0
0x14077a423  mov     r15d, r12d
0x14077a426  xor     r8d, r8d
0x14077a429  jmp     loc_14077A58F
0x14077a42e  test    eax, eax
0x14077a430  js      loc_14077A589
0x14077a436  mov     rdx, [rbp+57h+var_B0]
0x14077a43a  lea     rax, [rbp+57h+Handle]
0x14077a43e  mov     [rsp+100h+var_D8], rax
0x14077a443  xor     r9d, r9d
0x14077a446  mov     r8, r14
0x14077a449  mov     dword ptr [rsp+100h+var_E0], 20019h
0x14077a451  xor     ecx, ecx
0x14077a453  call    _PnpCtxRegOpenKey
0x14077a458  test    eax, eax
0x14077a45a  js      loc_14077A589
0x14077a460  mov     rdx, [rbp+57h+Handle]
0x14077a464  lea     rax, [rbp+57h+var_C0]
0x14077a468  mov     [rsp+100h+var_D8], rax
0x14077a46d  lea     r9, [rbp+57h+var_BC]
0x14077a471  lea     rax, [rbp+57h+var_B8]
0x14077a475  mov     edi, 4
0x14077a47a  lea     r8, aType; "Type"
0x14077a481  mov     [rsp+100h+var_E0], rax
0x14077a486  mov     [rbp+57h+var_C0], edi
0x14077a489  call    _PnpCtxRegQueryValue
0x14077a48e  test    eax, eax
0x14077a490  js      short loc_14077A4E0
0x14077a492  cmp     [rbp+57h+var_BC], edi
0x14077a495  jnz     short loc_14077A4E0
0x14077a497  cmp     [rbp+57h+var_C0], edi
0x14077a49a  jnz     short loc_14077A4E0
0x14077a49c  mov     rdx, [rbp+57h+Handle]
0x14077a4a0  lea     rax, [rbp+57h+var_C0]
0x14077a4a4  mov     [rsp+100h+var_D8], rax
0x14077a4a9  lea     r9, [rbp+57h+var_BC]
0x14077a4ad  lea     rax, [rbp+57h+var_B4]
0x14077a4b1  mov     [rbp+57h+var_C0], edi
0x14077a4b4  lea     r8, aStart_0; "Start"
0x14077a4bb  mov     [rsp+100h+var_E0], rax
0x14077a4c0  call    _PnpCtxRegQueryValue
0x14077a4c5  test    eax, eax
0x14077a4c7  js      short loc_14077A4DB
0x14077a4c9  cmp     [rbp+57h+var_BC], edi
0x14077a4cc  jnz     short loc_14077A4DB
0x14077a4ce  cmp     [rbp+57h+var_C0], edi
0x14077a4d1  jnz     short loc_14077A4DB
0x14077a4d3  mov     edi, [rbp+57h+var_B8]
0x14077a4d6  mov     esi, [rbp+57h+var_B4]
0x14077a4d9  jmp     short loc_14077A4EE
0x14077a4db  mov     edi, [rbp+57h+var_B8]
0x14077a4de  jmp     short loc_14077A4E7
0x14077a4e0  mov     edi, r12d
0x14077a4e3  mov     [rbp+57h+var_B8], r12d
0x14077a4e7  mov     [rbp+57h+var_B4], r12d
0x14077a4eb  mov     esi, r12d
0x14077a4ee  mov     rcx, [rbp+57h+Handle]; Handle
0x14077a4f2  call    ZwClose
0x14077a4f7  test    edi, edi
0x14077a4f9  jz      loc_14077A589
0x14077a4ff  test    dil, 0Bh
0x14077a503  jz      short loc_14077A517
0x14077a505  cmp     esi, 2
0x14077a508  jz      short loc_14077A517
0x14077a50a  mov     eax, [r13+1ECh]
0x14077a511  test    al, 40h
0x14077a513  jz      short loc_14077A589
0x14077a515  jmp     short loc_14077A522
0x14077a517  mov     eax, [r13+1ECh]
0x14077a51e  test    al, al
0x14077a520  jns     short loc_14077A589
0x14077a522  mov     r8, [rbp+57h+var_90]
0x14077a526  test    r8, r8
0x14077a529  jnz     short loc_14077A565
0x14077a52b  mov     rdx, [rbp+57h+var_88]
0x14077a52f  lea     rax, [rbp+57h+var_90]
0x14077a533  mov     [rsp+100h+var_C8], r12
0x14077a538  lea     r8, aControlset001S_0; "ControlSet001\\Services"
0x14077a53f  mov     [rsp+100h+var_D0], rax
0x14077a544  xor     r9d, r9d
0x14077a547  mov     [rsp+100h+var_D8], r12
0x14077a54c  xor     ecx, ecx
0x14077a54e  mov     dword ptr [rsp+100h+var_E0], 2001Fh
0x14077a556  call    _PnpCtxRegCreateKey
0x14077a55b  mov     ebx, eax
0x14077a55d  test    eax, eax
0x14077a55f  js      short loc_14077A5B6
0x14077a561  mov     r8, [rbp+57h+var_90]
0x14077a565  mov     rcx, [rbp+57h+var_B0]
0x14077a569  mov     r9, r14
0x14077a56c  mov     [rsp+100h+var_C8], r12
0x14077a571  mov     rdx, r14
0x14077a574  mov     dword ptr [rsp+100h+var_D0], r12d
0x14077a579  mov     [rsp+100h+var_D8], r12
0x14077a57e  call    PiDrvDbOverlayCopyKeys
0x14077a583  mov     ebx, eax
0x14077a585  test    eax, eax
0x14077a587  js      short loc_14077A5B6
0x14077a589  inc     r15d
0x14077a58c  mov     r8d, r15d
0x14077a58f  mov     rdx, [rbp+57h+var_B0]
0x14077a593  lea     rax, [rbp+57h+var_C0]
0x14077a597  mov     r9, r14
0x14077a59a  mov     [rsp+100h+var_E0], rax
0x14077a59f  mov     [rbp+57h+var_C0], 104h
0x14077a5a6  call    _PnpCtxRegEnumKey
0x14077a5ab  cmp     eax, 8000001Ah
0x14077a5b0  jnz     loc_14077A42E
0x14077a5b6  xor     edx, edx; Tag
0x14077a5b8  mov     rcx, r14; P
0x14077a5bb  call    ExFreePoolWithTag
0x14077a5c0  mov     rcx, [rbp+57h+var_A0]; Handle
0x14077a5c4  test    rcx, rcx
0x14077a5c7  jz      short loc_14077A5CE
0x14077a5c9  call    ZwClose
0x14077a5ce  mov     rcx, [rbp+57h+var_98]; Handle
0x14077a5d2  test    rcx, rcx
0x14077a5d5  jz      short loc_14077A5DC
0x14077a5d7  call    ZwClose
0x14077a5dc  mov     rcx, [rbp+57h+var_B0]; Handle
0x14077a5e0  test    rcx, rcx
0x14077a5e3  jz      short loc_14077A5EA
0x14077a5e5  call    ZwClose
0x14077a5ea  mov     rcx, [rbp+57h+var_90]; Handle
0x14077a5ee  test    rcx, rcx
0x14077a5f1  jz      short loc_14077A5F8
0x14077a5f3  call    ZwClose
0x14077a5f8  mov     rcx, [rbp+57h+var_88]; Handle
0x14077a5fc  test    rcx, rcx
0x14077a5ff  jz      short loc_14077A606
0x14077a601  call    ZwClose
0x14077a606  mov     eax, ebx
0x14077a608  mov     rcx, [rbp+57h+var_40]
0x14077a60c  xor     rcx, rsp; StackCookie
0x14077a60f  call    __security_check_cookie
0x14077a614  mov     rbx, [rsp+100h+arg_0]
0x14077a61c  add     rsp, 0D0h
0x14077a623  pop     r15
0x14077a625  pop     r14
0x14077a627  pop     r13
0x14077a629  pop     r12
0x14077a62b  pop     rdi
0x14077a62c  pop     rsi
0x14077a62d  pop     rbp
0x14077a62e  retn
```
