# CCatalogServer::RefreshComponents(void)

- ea: `0x18001fd60`
- end: `0x1800203fe`
- name: `?RefreshComponents@CCatalogServer@@UEAAJXZ`
- size: `1694`
- prototype: `__int64 __fastcall(CCatalogServer *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18001ece0`
- `0x18001fd60`
- `0x180020ec0`
- `0x18002f158`
- `0x180031b4c`
- `0x180031cdc`
- `0x1800554f6`
- `0x180055502`
- `0x18005551a`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `comsvcs!GetObjectContext` at `0x180020338`
- `comsvcs!GetObjectContext` at `0x180056359`
- `comsvcs!GetObjectContext` at `0x180020338`
- `comsvcs!GetObjectContext` at `0x180056359`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001fdfe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001fdfe`

## pseudocode

```c
__int64 __fastcall CCatalogServer::RefreshComponents(CCatalogServer *this)
{
  __int64 result; // rax
  struct ISimpleTableWrite *v3; // r8
  int ObjectContext; // eax
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  __int64 v7; // rax
  HRESULT v8; // eax
  __int64 v9; // [rsp+0h] [rbp-F8h] BYREF
  HRESULT Instance; // [rsp+50h] [rbp-A8h]
  int v11; // [rsp+54h] [rbp-A4h] BYREF
  int v12; // [rsp+58h] [rbp-A0h] BYREF
  _QWORD *v13; // [rsp+60h] [rbp-98h] BYREF
  __int64 v14; // [rsp+68h] [rbp-90h] BYREF
  __int64 *v15; // [rsp+70h] [rbp-88h]
  _OWORD *v16; // [rsp+78h] [rbp-80h] BYREF
  struct ISimpleTableDispenser *ppv; // [rsp+80h] [rbp-78h] BYREF
  _DWORD *v18; // [rsp+88h] [rbp-70h] BYREF
  _OWORD v19[3]; // [rsp+90h] [rbp-68h] BYREF
  __int128 Buf2; // [rsp+C0h] [rbp-38h] BYREF
  int v21; // [rsp+D0h] [rbp-28h]
  _OWORD *v22; // [rsp+D8h] [rbp-20h]

  v15 = &v9;
  v12 = 0;
  v11 = 0;
  v16 = 0;
  v18 = 0;
  v13 = 0;
  if ( !*((_DWORD *)this + 44) )
    return 2148598828LL;
  ppv = 0;
  v14 = 0;
  result = TxInitialize();
  Instance = result;
  if ( (int)result >= 0 )
  {
    UTSemReadWrite::LockWrite((UTSemReadWrite *)&g_semRW);
    Instance = CoCreateInstance(&clsidSTDISP, 0, 1u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
    if ( Instance < 0 )
      local_unwind_0(v15, &loc_1800203D9);
    Instance = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int64 *, const struct _GUID *, _QWORD, _QWORD, int, _DWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 didCOMSERVICES,
                 &tidCOMSERVICES_CLASSES_INTERNAL,
                 0,
                 0,
                 1,
                 0,
                 &v14);
    if ( Instance < 0 )
      local_unwind_0(v15, &loc_1800203D9);
    Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
    if ( Instance < 0 )
      local_unwind_0(v15, &loc_1800203D9);
    Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 32LL))(v14);
    if ( Instance < 0 )
      local_unwind_0(v15, &loc_1800203D9);
    while ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14);
      if ( Instance == -2146367487 )
      {
        Instance = 0;
        break;
      }
      if ( Instance < 0 )
        local_unwind_0(v15, &loc_1800203D9);
      Instance = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, _DWORD **))(*(_QWORD *)v14 + 64LL))(
                   v14,
                   31,
                   &v12,
                   &v11,
                   &v18);
      if ( Instance < 0 )
        local_unwind_0(v15, &loc_1800203D9);
      if ( !v18 || !*v18 )
      {
        memset_0(v19, 0, 0x50u);
        Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, int *, _OWORD **))(*(_QWORD *)v14 + 64LL))(
                     v14,
                     0,
                     &v12,
                     &v11,
                     &v16);
        if ( Instance < 0 )
          local_unwind_0(v15, &loc_1800203D9);
        v19[0] = *v16;
        Instance = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, _OWORD **))(*(_QWORD *)v14 + 64LL))(
                     v14,
                     4,
                     &v12,
                     &v11,
                     &v16);
        if ( Instance < 0 )
          local_unwind_0(v15, &loc_1800203D9);
        v19[2] = *v16;
        Instance = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, _OWORD **))(*(_QWORD *)v14 + 64LL))(
                     v14,
                     1,
                     &v12,
                     &v11,
                     &v16);
        if ( Instance < 0 )
          local_unwind_0(v15, &loc_1800203D9);
        Buf2 = *v16;
        if ( !memcmp_0(&guidGlobalPartition, &Buf2, 0x10u) )
        {
          Instance = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, _OWORD **))(*(_QWORD *)v14 + 64LL))(
                       v14,
                       3,
                       &v12,
                       &v11,
                       &v16);
          if ( Instance < 0 )
            local_unwind_0(v15, &loc_1800203D9);
          v21 = *(_DWORD *)v16;
          Instance = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, _OWORD **))(*(_QWORD *)v14 + 64LL))(
                       v14,
                       28,
                       &v12,
                       &v11,
                       &v16);
          if ( Instance < 0 )
            local_unwind_0(v15, &loc_1800203D9);
          v22 = v16;
          Instance = CCatalogServer::SyncClsidAndProgIdFor(
                       (CCatalogServer *)((char *)this - 56),
                       ppv,
                       v3,
                       (struct ClsidUpdateInfoStruct *)v19);
        }
      }
    }
    UTSemReadWrite::UnlockWrite((UTSemReadWrite *)&g_semRW);
    ObjectContext = GetObjectContext(&v13);
    v5 = (unsigned int)ObjectContext;
    v6 = v13;
    if ( ObjectContext >= 0 && v13 )
    {
      v7 = *v13;
      if ( Instance >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v7 + 32))(v13, v5);
        v6 = v13;
LABEL_42:
        Instance = v8;
        goto LABEL_43;
      }
      (*(void (__fastcall **)(_QWORD *, __int64))(v7 + 40))(v13, v5);
      v6 = v13;
    }
    else if ( ObjectContext != -2147164156 )
    {
      v8 = Instance;
      if ( Instance >= 0 )
        v8 = v5;
      goto LABEL_42;
    }
LABEL_43:
    if ( v6 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
      v13 = 0;
    }
    if ( ppv )
    {
      (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
    }
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    return (unsigned int)Instance;
  }
  return result;
}

```

## disassembly

```asm
0x18001fd60  mov     r11, rsp
0x18001fd63  mov     [r11+10h], rbx
0x18001fd67  push    rdi
0x18001fd68  sub     rsp, 0F0h
0x18001fd6f  mov     rax, cs:__security_cookie
0x18001fd76  xor     rax, rsp
0x18001fd79  mov     [rsp+0F8h+var_18], rax
0x18001fd81  mov     [rsp+0F8h+var_88], rsp
0x18001fd86  mov     rdi, rcx
0x18001fd89  xor     ebx, ebx
0x18001fd8b  mov     [rsp+0F8h+var_A0], ebx
0x18001fd8f  mov     [rsp+0F8h+var_A4], ebx
0x18001fd93  mov     [r11-80h], rbx
0x18001fd97  mov     [r11-70h], rbx
0x18001fd9b  mov     [rsp+0F8h+var_98], rbx
0x18001fda0  cmp     [rcx+0B0h], ebx
0x18001fda6  jnz     short loc_18001FDB2
0x18001fda8  mov     eax, 8011042Ch
0x18001fdad  jmp     loc_1800203DD
0x18001fdb2  mov     [rsp+0F8h+var_78], rbx
0x18001fdba  mov     [rsp+0F8h+var_90], rbx
0x18001fdbf  call    ?TxInitialize@@YAJXZ; TxInitialize(void)
0x18001fdc4  mov     [rsp+0F8h+var_A8], eax
0x18001fdc8  test    eax, eax
0x18001fdca  js      loc_1800203DD
0x18001fdd0  lea     rcx, ?g_semRW@@3VUTSemReadWrite@@A; this
0x18001fdd7  call    ?LockWrite@UTSemReadWrite@@QEAAXXZ; UTSemReadWrite::LockWrite(void)
0x18001fddc  nop
0x18001fddd  lea     rax, [rsp+0F8h+var_78]
0x18001fde5  mov     [rsp+0F8h+ppv], rax; ppv
0x18001fdea  lea     r9, IID_ISimpleTableDispenser; riid
0x18001fdf1  xor     edx, edx; pUnkOuter
0x18001fdf3  lea     r8d, [rdx+1]; dwClsContext
0x18001fdf7  lea     rcx, clsidSTDISP; rclsid
0x18001fdfe  call    cs:__imp_CoCreateInstance
0x18001fe04  mov     [rsp+0F8h+var_A8], eax
0x18001fe08  mov     eax, [rsp+0F8h+var_A8]
0x18001fe0c  test    eax, eax
0x18001fe0e  jns     short loc_18001FE46
0x18001fe10  mov     eax, [rsp+0F8h+var_A8]
0x18001fe14  cmp     eax, 8007000Eh
0x18001fe19  jz      short loc_18001FE35
0x18001fe1b  mov     eax, [rsp+0F8h+var_A8]
0x18001fe1f  cmp     eax, 800705AFh
0x18001fe24  jz      short loc_18001FE35
0x18001fe26  mov     eax, [rsp+0F8h+var_A8]
0x18001fe2a  cmp     eax, 8007045Bh
0x18001fe2f  jz      short loc_18001FE35
0x18001fe31  mov     eax, [rsp+0F8h+var_A8]
0x18001fe35  lea     rdx, loc_1800203D9
0x18001fe3c  mov     rcx, [rsp+0F8h+var_88]
0x18001fe41  call    _local_unwind_0
0x18001fe46  mov     rcx, [rsp+0F8h+var_78]
0x18001fe4e  mov     rax, [rcx]
0x18001fe51  lea     rdx, [rsp+0F8h+var_90]
0x18001fe56  mov     [rsp+0F8h+var_C0], rdx
0x18001fe5b  mov     [rsp+0F8h+var_C8], ebx
0x18001fe5f  mov     [rsp+0F8h+var_D0], 1
0x18001fe67  mov     [rsp+0F8h+ppv], rbx
0x18001fe6c  xor     r9d, r9d
0x18001fe6f  lea     r8, tidCOMSERVICES_CLASSES_INTERNAL
0x18001fe76  lea     rdx, didCOMSERVICES
0x18001fe7d  mov     rax, [rax+18h]
0x18001fe81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe86  mov     [rsp+0F8h+var_A8], eax
0x18001fe8a  mov     eax, [rsp+0F8h+var_A8]
0x18001fe8e  test    eax, eax
0x18001fe90  jns     short loc_18001FEC8
0x18001fe92  mov     eax, [rsp+0F8h+var_A8]
0x18001fe96  cmp     eax, 8007000Eh
0x18001fe9b  jz      short loc_18001FEB7
0x18001fe9d  mov     eax, [rsp+0F8h+var_A8]
0x18001fea1  cmp     eax, 800705AFh
0x18001fea6  jz      short loc_18001FEB7
0x18001fea8  mov     eax, [rsp+0F8h+var_A8]
0x18001feac  cmp     eax, 8007045Bh
0x18001feb1  jz      short loc_18001FEB7
0x18001feb3  mov     eax, [rsp+0F8h+var_A8]
0x18001feb7  lea     rdx, loc_1800203D9
0x18001febe  mov     rcx, [rsp+0F8h+var_88]
0x18001fec3  call    _local_unwind_0
0x18001fec8  mov     rcx, [rsp+0F8h+var_90]
0x18001fecd  mov     rax, [rcx]
0x18001fed0  mov     rax, [rax+18h]
0x18001fed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fed9  mov     [rsp+0F8h+var_A8], eax
0x18001fedd  mov     eax, [rsp+0F8h+var_A8]
0x18001fee1  test    eax, eax
0x18001fee3  jns     short loc_18001FF1B
0x18001fee5  mov     eax, [rsp+0F8h+var_A8]
0x18001fee9  cmp     eax, 8007000Eh
0x18001feee  jz      short loc_18001FF0A
0x18001fef0  mov     eax, [rsp+0F8h+var_A8]
0x18001fef4  cmp     eax, 800705AFh
0x18001fef9  jz      short loc_18001FF0A
0x18001fefb  mov     eax, [rsp+0F8h+var_A8]
0x18001feff  cmp     eax, 8007045Bh
0x18001ff04  jz      short loc_18001FF0A
0x18001ff06  mov     eax, [rsp+0F8h+var_A8]
0x18001ff0a  lea     rdx, loc_1800203D9
0x18001ff11  mov     rcx, [rsp+0F8h+var_88]
0x18001ff16  call    _local_unwind_0
0x18001ff1b  mov     rcx, [rsp+0F8h+var_90]
0x18001ff20  mov     rax, [rcx]
0x18001ff23  mov     rax, [rax+20h]
0x18001ff27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff2c  mov     [rsp+0F8h+var_A8], eax
0x18001ff30  mov     eax, [rsp+0F8h+var_A8]
0x18001ff34  test    eax, eax
0x18001ff36  jns     short loc_18001FF6E
0x18001ff38  mov     eax, [rsp+0F8h+var_A8]
0x18001ff3c  cmp     eax, 8007000Eh
0x18001ff41  jz      short loc_18001FF5D
0x18001ff43  mov     eax, [rsp+0F8h+var_A8]
0x18001ff47  cmp     eax, 800705AFh
0x18001ff4c  jz      short loc_18001FF5D
0x18001ff4e  mov     eax, [rsp+0F8h+var_A8]
0x18001ff52  cmp     eax, 8007045Bh
0x18001ff57  jz      short loc_18001FF5D
0x18001ff59  mov     eax, [rsp+0F8h+var_A8]
0x18001ff5d  lea     rdx, loc_1800203D9
0x18001ff64  mov     rcx, [rsp+0F8h+var_88]
0x18001ff69  call    _local_unwind_0
0x18001ff6e  mov     eax, [rsp+0F8h+var_A8]
0x18001ff72  test    eax, eax
0x18001ff74  js      loc_180020323
0x18001ff7a  mov     rcx, [rsp+0F8h+var_90]
0x18001ff7f  mov     rax, [rcx]
0x18001ff82  mov     rax, [rax+28h]
0x18001ff86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff8b  mov     [rsp+0F8h+var_A8], eax
0x18001ff8f  mov     eax, [rsp+0F8h+var_A8]
0x18001ff93  cmp     eax, 80110801h
0x18001ff98  jnz     short loc_18001FFA3
0x18001ff9a  mov     [rsp+0F8h+var_A8], ebx
0x18001ff9e  jmp     loc_180020323
0x18001ffa3  mov     eax, [rsp+0F8h+var_A8]
0x18001ffa7  test    eax, eax
0x18001ffa9  jns     short loc_18001FFE1
0x18001ffab  mov     eax, [rsp+0F8h+var_A8]
0x18001ffaf  cmp     eax, 8007000Eh
0x18001ffb4  jz      short loc_18001FFD0
0x18001ffb6  mov     eax, [rsp+0F8h+var_A8]
0x18001ffba  cmp     eax, 800705AFh
0x18001ffbf  jz      short loc_18001FFD0
0x18001ffc1  mov     eax, [rsp+0F8h+var_A8]
0x18001ffc5  cmp     eax, 8007045Bh
0x18001ffca  jz      short loc_18001FFD0
0x18001ffcc  mov     eax, [rsp+0F8h+var_A8]
0x18001ffd0  lea     rdx, loc_1800203D9
0x18001ffd7  mov     rcx, [rsp+0F8h+var_88]
0x18001ffdc  call    _local_unwind_0
0x18001ffe1  mov     rcx, [rsp+0F8h+var_90]
0x18001ffe6  mov     rax, [rcx]
0x18001ffe9  lea     rdx, [rsp+0F8h+var_70]
0x18001fff1  mov     [rsp+0F8h+ppv], rdx
0x18001fff6  lea     r9, [rsp+0F8h+var_A4]
0x18001fffb  lea     r8, [rsp+0F8h+var_A0]
0x180020000  mov     edx, 1Fh
0x180020005  mov     rax, [rax+40h]
0x180020009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002000e  mov     [rsp+0F8h+var_A8], eax
0x180020012  mov     eax, [rsp+0F8h+var_A8]
0x180020016  test    eax, eax
0x180020018  jns     short loc_180020050
0x18002001a  mov     eax, [rsp+0F8h+var_A8]
0x18002001e  cmp     eax, 8007000Eh
0x180020023  jz      short loc_18002003F
0x180020025  mov     eax, [rsp+0F8h+var_A8]
0x180020029  cmp     eax, 800705AFh
0x18002002e  jz      short loc_18002003F
0x180020030  mov     eax, [rsp+0F8h+var_A8]
0x180020034  cmp     eax, 8007045Bh
0x180020039  jz      short loc_18002003F
0x18002003b  mov     eax, [rsp+0F8h+var_A8]
0x18002003f  lea     rdx, loc_1800203D9
0x180020046  mov     rcx, [rsp+0F8h+var_88]
0x18002004b  call    _local_unwind_0
0x180020050  mov     rax, [rsp+0F8h+var_70]
0x180020058  test    rax, rax
0x18002005b  jz      short loc_180020065
0x18002005d  cmp     [rax], ebx
0x18002005f  jnz     loc_18002031E
0x180020065  xor     edx, edx; Val
0x180020067  lea     r8d, [rdx+50h]; Size
0x18002006b  lea     rcx, [rsp+0F8h+var_68]; void *
0x180020073  call    memset_0
0x180020078  mov     rcx, [rsp+0F8h+var_90]
0x18002007d  mov     rax, [rcx]
0x180020080  lea     rdx, [rsp+0F8h+var_80]
0x180020085  mov     [rsp+0F8h+ppv], rdx
0x18002008a  lea     r9, [rsp+0F8h+var_A4]
0x18002008f  lea     r8, [rsp+0F8h+var_A0]
0x180020094  xor     edx, edx
0x180020096  mov     rax, [rax+40h]
0x18002009a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002009f  mov     [rsp+0F8h+var_A8], eax
0x1800200a3  mov     eax, [rsp+0F8h+var_A8]
0x1800200a7  test    eax, eax
0x1800200a9  jns     short loc_1800200E1
0x1800200ab  mov     eax, [rsp+0F8h+var_A8]
0x1800200af  cmp     eax, 8007000Eh
0x1800200b4  jz      short loc_1800200D0
0x1800200b6  mov     eax, [rsp+0F8h+var_A8]
0x1800200ba  cmp     eax, 800705AFh
0x1800200bf  jz      short loc_1800200D0
0x1800200c1  mov     eax, [rsp+0F8h+var_A8]
0x1800200c5  cmp     eax, 8007045Bh
0x1800200ca  jz      short loc_1800200D0
0x1800200cc  mov     eax, [rsp+0F8h+var_A8]
0x1800200d0  lea     rdx, loc_1800203D9
0x1800200d7  mov     rcx, [rsp+0F8h+var_88]
0x1800200dc  call    _local_unwind_0
0x1800200e1  mov     rax, [rsp+0F8h+var_80]
0x1800200e6  movups  xmm0, xmmword ptr [rax]
0x1800200e9  movdqu  [rsp+0F8h+var_68], xmm0
0x1800200f2  mov     rcx, [rsp+0F8h+var_90]
0x1800200f7  mov     rax, [rcx]
0x1800200fa  lea     rdx, [rsp+0F8h+var_80]
0x1800200ff  mov     [rsp+0F8h+ppv], rdx
0x180020104  lea     r9, [rsp+0F8h+var_A4]
0x180020109  lea     r8, [rsp+0F8h+var_A0]
0x18002010e  mov     edx, 4
0x180020113  mov     rax, [rax+40h]
0x180020117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002011c  mov     [rsp+0F8h+var_A8], eax
0x180020120  mov     eax, [rsp+0F8h+var_A8]
0x180020124  test    eax, eax
0x180020126  jns     short loc_18002015E
0x180020128  mov     eax, [rsp+0F8h+var_A8]
0x18002012c  cmp     eax, 8007000Eh
0x180020131  jz      short loc_18002014D
0x180020133  mov     eax, [rsp+0F8h+var_A8]
0x180020137  cmp     eax, 800705AFh
0x18002013c  jz      short loc_18002014D
0x18002013e  mov     eax, [rsp+0F8h+var_A8]
0x180020142  cmp     eax, 8007045Bh
0x180020147  jz      short loc_18002014D
0x180020149  mov     eax, [rsp+0F8h+var_A8]
0x18002014d  lea     rdx, loc_1800203D9
0x180020154  mov     rcx, [rsp+0F8h+var_88]
0x180020159  call    _local_unwind_0
0x18002015e  mov     rax, [rsp+0F8h+var_80]
0x180020163  movups  xmm0, xmmword ptr [rax]
0x180020166  movdqu  [rsp+0F8h+var_48], xmm0
0x18002016f  mov     rcx, [rsp+0F8h+var_90]
0x180020174  mov     rax, [rcx]
0x180020177  lea     rdx, [rsp+0F8h+var_80]
0x18002017c  mov     [rsp+0F8h+ppv], rdx
0x180020181  lea     r9, [rsp+0F8h+var_A4]
0x180020186  lea     r8, [rsp+0F8h+var_A0]
0x18002018b  mov     edx, 1
0x180020190  mov     rax, [rax+40h]
0x180020194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020199  mov     [rsp+0F8h+var_A8], eax
0x18002019d  mov     eax, [rsp+0F8h+var_A8]
0x1800201a1  test    eax, eax
0x1800201a3  jns     short loc_1800201DB
0x1800201a5  mov     eax, [rsp+0F8h+var_A8]
0x1800201a9  cmp     eax, 8007000Eh
0x1800201ae  jz      short loc_1800201CA
0x1800201b0  mov     eax, [rsp+0F8h+var_A8]
0x1800201b4  cmp     eax, 800705AFh
0x1800201b9  jz      short loc_1800201CA
0x1800201bb  mov     eax, [rsp+0F8h+var_A8]
0x1800201bf  cmp     eax, 8007045Bh
0x1800201c4  jz      short loc_1800201CA
0x1800201c6  mov     eax, [rsp+0F8h+var_A8]
0x1800201ca  lea     rdx, loc_1800203D9
0x1800201d1  mov     rcx, [rsp+0F8h+var_88]
0x1800201d6  call    _local_unwind_0
0x1800201db  mov     rax, [rsp+0F8h+var_80]
0x1800201e0  movups  xmm0, xmmword ptr [rax]
0x1800201e3  movdqu  [rsp+0F8h+Buf2], xmm0
0x1800201ec  mov     r8d, 10h; Size
0x1800201f2  lea     rdx, [rsp+0F8h+Buf2]; Buf2
0x1800201fa  lea     rcx, guidGlobalPartition; Buf1
0x180020201  call    memcmp_0
0x180020206  test    eax, eax
0x180020208  jnz     loc_18002031E
0x18002020e  mov     rcx, [rsp+0F8h+var_90]
0x180020213  mov     rax, [rcx]
0x180020216  lea     rdx, [rsp+0F8h+var_80]
0x18002021b  mov     [rsp+0F8h+ppv], rdx
0x180020220  lea     r9, [rsp+0F8h+var_A4]
0x180020225  lea     r8, [rsp+0F8h+var_A0]
0x18002022a  mov     edx, 3
0x18002022f  mov     rax, [rax+40h]
0x180020233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020238  mov     [rsp+0F8h+var_A8], eax
0x18002023c  mov     eax, [rsp+0F8h+var_A8]
0x180020240  test    eax, eax
0x180020242  jns     short loc_18002027A
0x180020244  mov     eax, [rsp+0F8h+var_A8]
0x180020248  cmp     eax, 8007000Eh
0x18002024d  jz      short loc_180020269
0x18002024f  mov     eax, [rsp+0F8h+var_A8]
0x180020253  cmp     eax, 800705AFh
0x180020258  jz      short loc_180020269
0x18002025a  mov     eax, [rsp+0F8h+var_A8]
  ... truncated ...
```
